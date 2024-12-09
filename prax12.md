## Skriptimine Linuxis
Käesolevas praktikumis tutvusin käsurea skriptidega Linuxis.

### ülesanne 3
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

### ülesanne 4
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

### ülesanne 5
pid.sh:
```
#!/bin/bash
protsess=$(ps -A | grep -i "$1")
echo "$protsess" | awk '{print "ID: "$1", nimi: "$4}'
```
![image](https://github.com/user-attachments/assets/9dd70c97-b5b4-49d0-b2f3-17c1dab12e2a)

### ülesanne 6
astendamine.sh:
```
#!/bin/bash
astenda () {
if [ $2 -ne 0 ]
then
    echo $(( $1 * $(astenda $1 $(( $2-1 ))) ))
else
    echo "1"
fi
}

echo $(astenda 9 5)
```
![image](https://github.com/user-attachments/assets/09308ce0-0a5c-4b0c-8c4a-1c5b270a6107)

### ülesanne 7
![image](https://github.com/user-attachments/assets/632e1d06-3bf7-4800-bf70-22db44dcddcf)
![image](https://github.com/user-attachments/assets/5a6522be-d8d4-448d-a007-7284806f15e4)

