### Praktikum 6 - protsessid ja signaalid
Praktikumis õppisin protsessidele signaalide saatmist ning sisendi/väljundi suunamist.

1. ![image](https://github.com/user-attachments/assets/878d0a12-768f-4c25-8caa-33ef3210bae6)
2. ![image](https://github.com/user-attachments/assets/bf89d34e-19cb-411d-b729-aefc809fc97b)
3. ![image](https://github.com/user-attachments/assets/98f50e1a-bc68-48e8-9078-201af405bc33)
ps -axu | grep daemon | tr -s " " |cut -d" " -f11- | grep daemon

4. ![image](https://github.com/user-attachments/assets/b59b4a9d-7b40-460c-b930-3179f2f3ffde)
ip a | grep 'inet ' | grep -v '127.0.0.1' | cut -d" " -f6 | cut -d"/" -f1
