### Praktikum 5 - failiõigused Linuxis
Praktikumi käigus sain ülevaate erinevatest Unixi failiõigustest ja parameetritest.

1. a) kaustal execute, failil read õigused.
   b) kaustal execute ja write, failil midagi.

2. Skripti käivitamiseks oleks vaja ka lugemisõigust, et skripti üldse failist lugeda, 'a=x' aga eemaldab lugemis- ja kirjutamisõigused.

3. Sellega tagatakse parem kasutaja failide turvalisus, kui kasutaja loodud failid luuakse, siis saab määrata, et neile pääseb ligi ainult vastava grupi liige ning suvalised kasutajad ei pääse ligi teiste andmetele.

4.
![image](https://github.com/user-attachments/assets/4f0584a0-664c-43c5-a43f-18c54f43f589)

5.
![image](https://github.com/user-attachments/assets/3a6681c9-9c2a-4b7b-924e-eaed96abff0a)
Setuid õigust on vaja, et kasutaja, kellel pole õigust faili lugeda, saaks ikka käivitada programmi, mis kasutab seda faili.

7. Setuid võib vähendada turvalisust, kui kasutusel sellised programmid, mis väljastavad infot nendest väheste lugemisõigustega failidest.

8. Faile said kustutada opetaja, kasutaja1 (peeter) ja juurkasutaja.
   
9. # file: hinded.txt\
'# owner: opetaja\
'# group: opetaja\
'user::rw-\
'group::---\
'group:direktor:rw-\
'mask::rw-\
'other::---

10. Juurkasutaja või piisavate süsteemi õigustega kasutaja saab eemaldada faililt +i-parameetri ja seejärel sisu muuta.
Faililt tuleb esiteks eemaldada +i-parameeter käsuga: sudo chattr -i testfail-2. Seejärel kustutada fail: rm testfail-2.
