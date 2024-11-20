### Praktikum 9 - ressursihaldus

| -- | Küsimus | Linux | Windows | Linuxis kasutatud käsklus | Windowsis kasutatud tööriist|
| -- | -- | -- | -- | -- | -- |
| 1. | Mitu protsessi kokku arvutis käib? | 227 | 122 | ps -aux \| wc -l | Task Manager -> Jõudlus | 
| 2. | Milline on kõige esimesena käivitatud protsess? | /sbin/init splash | smss.exe | ps axo pid,cmd,comm,etime | Process Explorer -> Start Time | 
| 3. | Milliste kasutajate protsesse arvutis käib? | root, systemd+, avahi, message+, kernoops, neleliis | Nele-Liis, Local service, Network service, System | ps -eo user | Process Explorer -> User Name | 
| 4. | Kui kaua on arvuti järjest töötanud (up time)? | 13 min | 30 min 15 sek | uptime | Task Manager -> Jõudlus | 
| 5. | Milline protsess käivitati kõige hiljem (viimasena)? | [kworker/1:0]  | SearchProtocolHost.exe | ps -eo pid,args,etime \| sort -k3 -n | Process Explorer -> Start Time | 
| 6. | Milline on kõige rohkem protsessoriaega võttev protsess ja kui mitu protsenti protsessoriajast ta tarbib? | gnome-shell / 5.5% | Task Manager, 9,3% | Htop -> CPU% | Task Manager -> Protsessid | 
| 7. | Milline on kõige rohkem virtuaalmälu (aadressiruumi, commit, Virtual Size) võttev protsess? | gnome-shell | MsMpEng.exe | Htop -> VIRT | Task Manager -> Üksikasjad | 
| 8. | Milline on kõige rohkem füüsilist mälu (working set) võttev protsess? | gnome-shell | WebView2 vidinad  | Htop -> RES | Task Manager -> Protsessid | 
| 9. | Kui palju füüsilisest mälust (Physical Memory) on vaba ja kui palju hõivatud? | 552Mi / 903Mi | 1,7 GB / 2,3 GB | free -h -> free / used | Task Manager -> Jõudlus | 
| 10. | Kui palju on põhikettal (C:, /) vaba ruumi mahult (GB) ja protsentuaalselt? | 8,5G / 58% | 30,16 GB / 48% | df -h / | Disk Manager | 
| 11. | Milline on kõige suurem arvutis olev fail ja kõige rohkem andmemahtu hõivav kaust (arvesse võta ka alamkaustade mahtu, ja jätta juurkaust / või C: välja)? | gnome-42-2204_176.snap / /usr | pagefile.sys / Windows | sudo find / -type f -exec du -h {} + \| sort -rh \| head -n 1 / sudo du -ah /* \| sort -rh \| head -n 1 | WinDirStat | 
| 12. | Võrrelge terminali käskude: sha1sum /dev/zero \| sha1sum /dev/zero ja sha1sum /dev/urandom \| sha1sum /dev/urandom protsessori kasutust. Kirjutage millisele CPU alamtegevusele (us, sy, id, wa, st jne) kulub enim protsessori aega kummagi käsu puhul. | Käsk sha1sum /dev/zero \| sha1sum /dev/zero kulus enim kasutaja alamtegevustele (us), käsul sha1sum /dev/urandom \| sha1sum /dev/urandom kulus enim süsteemi alamtegevustele (sy). | - | Top -> %Cpu(s) | - | 
| 13.1. | Milline protsess kõige rohkem salvestusseadmele kirjutab? | - | TiWorker.exe | - | Resource Monitor -> Disk | 
| 13.2. | Millisesse faili eelmise küsimuse protsess kõige rohkem kirjutab? | - | C:\$LogFile | - | Resource Monitor -> Disk | 
| 13.3. | Milline protsess kõige rohkem salvestusseadmelt loeb? | - | svchost.exe | - | Resource Monitor -> Disk | 
| 13.4. | Millisest failist eelmise küsimuse protsess kõige rohkem loeb? | - | storport.sys | - | Resource Monitor -> Disk | 
| 14. | Millise protsessi poolt tekitatud võrguliiklus on suurima mahuga? Kohalik IP-aadress, kohalik port, ühenduse teise poole IP-aadress, port, latents ja antud ühenduse poolt kasutatav võrguliikluse kogumaht. | - | nextcloud.exe / 10.0.2.15 / 55226 / 193.40.5.90 / 443 / 1ms / 643B/s | - | Resource Monitor -> Network | 
| 15. | Sõber kurdab, et tema arvuti on oluliselt aeglasemaks muutunud. Milliseid konkreetseid programme või käsureakäske kasutad põhjustaja tuvastamiseks. | - | Kõige lihtsam ja esimene valik oleks vaadata tegumihalduri sakist 'protsessid', millised protsessid võtavad kõige rohkem protsessori ja mälu ressursse. | - | Task Manager -> Protsessid | 

![image](https://github.com/user-attachments/assets/5fac6ee4-95fc-46de-8c77-a5bfeee6d097)

![image](https://github.com/user-attachments/assets/19fed22b-f5d1-4926-af31-451205e49eca)
