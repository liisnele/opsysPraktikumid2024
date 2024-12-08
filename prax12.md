## Skriptimine Linuxis

### 1. ülesanne
esimene.sh:
```
#!/bin/sh
echo "Sisesta oma nimi: "
read sisse1
echo "Sisesta oma eriala: "
read sisse2
echo "Sisesta matriklinumber: "
read sisse3
echo "Nimi: $sisse1, eriala: $sisse2, matriklinumber: $sisse3."
```
![image](https://github.com/user-attachments/assets/50ff9663-cee6-4c97-8222-d940a8f00548)

laiend.sh:
```
#!/bin/bash -x
kaust=$1
laiend1=$2
laiend2=$3

for i in $(ls $kaust)
do
    if [ ${i##*.} = $laiend1 ]
    then
        echo "muudetav fail: $i"
        mv "$kaust/$i" "$kaust/${i%%.*}.$laiend2"
    fi
done
```
![image](https://github.com/user-attachments/assets/da6d4850-433f-4753-8a10-2f0955f8c322)


### 2. ülesanne
