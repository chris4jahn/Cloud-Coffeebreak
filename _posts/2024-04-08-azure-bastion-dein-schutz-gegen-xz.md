Wie schütze ich meine Fernzugänge gegen Angriffe wie den xz-Supply-Chain-Angriff?

💭 Ich habe mir über Fernwartungszugänge und SSH auf Grund der aktuellen xz-Supply-Chain-Attacke wieder mal Gedanken gemacht und bin dabei auf einen interessanten Aspekt bezüglich Wireguard gestoßen, der mir so bisher nicht klar war. Und den möchte ich teilen.

💣 Die xz-Supply-Chain-Attacke hat auf SSHd gezielt. Ein Bastion-Host, der über SSH erreichbar ist, hätte also meine interne Infrastruktur nicht geschützt. Dienste wie OpenVPN hätten auf demselben Weg genau so gut angegriffen werden können.

📜 Wenn ich einen Bastion-Host betreibe, dann sollte ich meine Audit-Logs sofort auf eine Append-Only-Remote-Logsenke wegschreiben, die im Idealfall an ein IDS gekoppelt ist. Das hilft mir dabei, Angriffe frühzeitig zu erkennen (und die Erkennung eines Angriffs ist immer noch der wichtigste Schutz, den wir haben, weil wir notfalls den Stecker ziehen können).
Das wird einer der Gründe gewesen sein, warum die xz-Malware eine Remote-Code-Execution-Lücke aufmacht und nicht einfach einen weiteren Key hinterlegt. Eine SSH Config-Änderung/eine Authentication über einen neuen Key würde in einem Audit-Log landen und ggf. sofort unwiderruflich aufgezeichnet werden.

⭐ Wireguard hat hier einen entscheidenden Vorteil: es ist ein Kernelmodul. Und das bringt mehrere Vorteile mit:

🐧 Der Kernel ist eines der am besten überwachten und gereviewten Stücke Software (auch im vgl. zu Lösungen von Drittherstellern). Die Wahrscheinlichkeit, dass jemand in ein Kernel-Archiv - unbemerkt von den Kernel-Maintainern - eine Backdoor einbaut, ist verschwindend gering.

⚔️ Ich kann das Wireguard-Modul über Secure-Boot schützen. Und ich kann mir sogar, als Appliance-Hersteller, genau meinen einen Signing-Key in der Firmware hinterlegen, so dass ein eventuell gestohlener Signing Key (z.B. von Microsoft) keinen Schaden mehr anrichten kann. 

➡️ Zusammengefasst: dass in den Wireguard Code direkt Hintertüren eingeschleust werden, ist extrem unwahrscheinlich und die Firmware kann mich mit Secure-Boot davor schützen, dass mein Wireguard-Modul kompromittiert wird.

🚨 Natürlich kann jemand über eine Supply-Chain-Attacke im Userspace dann einfach einen neuen Wireguard-Schlüssel erstellen und so Fernzugriff erlauben. In dem Augenblick, wo ein Angreifer das aber tut, wird er durch ausgeleitete Systemlogs sofort sichtbar. Und per Malware alle Logging-Lösungen zu erwischen, ist schon wieder sehr viel schwieriger. Je höher die Komplexität eines Angriffs ist und je mehr Aufwand der Angreifer treiben muss, desto höher ist auch die Erkennungswahrscheinlichkeit.

🧱 Wireguard bietet also keinen absoluten Schutz, aber es ist erheblich aufwändiger dort anzugreifen, als bei Userspace VPN/IAP-Lösungen.
