### Praktikum 9 - ressursihaldus

| -- | Küsimus | Linux | Windows | Linuxis kasutatud käsklus | Windowsis kasutatud tööriist|
| -- | -- | -- | -- | -- | -- |
| 1. | Mitu protsessi kokku arvutis käib? | 227 | 122 | ps -aux \| wc -l | Task Manager -> Jõudlus | 
| 2. | Milline on kõige esimesena käivitatud protsess? | /sbin/init splash | smss.exe | ps axo pid,cmd,comm,etime | Process Explorer -> Start Time | 
| 3. | Milliste kasutajate protsesse arvutis käib? | root, systemd+, avahi, message+, kernoops, neleliis | Nele-Liis, Local service, Network service, System | ps -eo user | Process Explorer -> User Name | 
| 4. | Kui kaua on arvuti järjest töötanud (up time)? | 13 min | 30 min 15 sek | uptime | Task Manager -> Jõudlus | 
| 5. | Milline protsess käivitati kõige hiljem (viimasena)? | -- | SearchProtocolHost.exe | -- | Process Explorer -> Start Time | 
| 6. | Milline on kõige rohkem protsessoriaega võttev protsess ja kui mitu protsenti protsessoriajast ta tarbib? | -- | Task Manager, 9,3% | -- | Task Manager -> Protsessid | 
| 7. | Milline on kõige rohkem virtuaalmälu (aadressiruumi, commit, Virtual Size) võttev protsess? | -- | MsMpEng.exe | -- | Task Manager -> Üksikasjad | 
| 8. | Milline on kõige rohkem füüsilist mälu (working set) võttev protsess? | -- | WebView2 vidinad  | -- | Task Manager -> Protsessid | 
| 9. | Kui palju füüsilisest mälust (Physical Memory) on vaba ja kui palju hõivatud? | -- | 1,7 GB / 2,3 GB | -- | Task Manager -> Jõudlus | 
| 10. | Kui palju on põhikettal (C:, /) vaba ruumi mahult (GB) ja protsentuaalselt? | -- | 30,16 GB / 48% | -- | Disk Manager | 
| 11. | Milline on kõige suurem arvutis olev fail ja kõige rohkem andmemahtu hõivav kaust (arvesse võta ka alamkaustade mahtu, ja jätta juurkaust / või C: välja)? | -- | pagefile.sys / Windows | -- | WinDirStat | 
| 12. | Võrrelge terminali käskude: sha1sum /dev/zero \| sha1sum /dev/zero ja sha1sum /dev/urandom \| sha1sum /dev/urandom protsessori kasutust. Kirjutage millisele CPU alamtegevusele (us, sy, id, wa, st jne) kulub enim protsessori aega kummagi käsu puhul. | -- | - | -- | - | 
| 13.1. | Milline protsess kõige rohkem salvestusseadmele kirjutab? | - | TiWorker.exe | - | Resource Monitor -> Disk | 
| 13.2. | Millisesse faili eelmise küsimuse protsess kõige rohkem kirjutab? | - | C:\$LogFile | - | Resource Monitor -> Disk | 
| 13.3. | Milline protsess kõige rohkem salvestusseadmelt loeb? | - | svchost.exe | - | Resource Monitor -> Disk | 
| 13.4. | Millisest failist eelmise küsimuse protsess kõige rohkem loeb? | - | storport.sys | - | Resource Monitor -> Disk | 
| 14. | Millise protsessi poolt tekitatud võrguliiklus on suurima mahuga? Kohalik IP-aadress, kohalik port, ühenduse teise poole IP-aadress, port, latents ja antud ühenduse poolt kasutatav võrguliikluse kogumaht. | - | nextcloud.exe / 10.0.2.15 / 55226 / 193.40.5.90 / 443 / 1ms / 643B/s | - | Resource Monitor -> Network | 
| 15. | Sõber kurdab, et tema arvuti on oluliselt aeglasemaks muutunud. Milliseid konkreetseid programme või käsureakäske kasutad põhjustaja tuvastamiseks. | - | Kõige lihtsam ja esimene valik oleks vaadata tegumihalduri sakist 'protsessid', millised protsessid võtavad kõige rohkem protsessori ja mälu ressursse. | - | Task Manager -> Protsessid | 
