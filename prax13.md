### Praktikum 13 - Skriptimine Windowsis

```
#$nr:	küsimuse number
#$param: mis parameetriga tegemist (võimalikult lühidalt)
#$sisu:	väljastatav sisu
function valjasta{
	param ($nr, $param, $sisu)
	$fail = ".\tulemus.txt"
	$aeg = Get-Date -Format "HH:mm:ss.fff"
	if($sisu -eq $null){
		$rida = "$nr.	$aeg	${param}:	NULL"
		Write-Output $rida
		$rida | Out-File -FilePath $fail -Append
	}elseif($sisu.GetType().Name -eq "Object[]"){
		$rida = "$nr.	$aeg	${param}:"
		Write-Output $rida $sisu
		$rida | Out-File -FilePath $fail -Append
		$sisu | Out-File -FilePath $fail -Append
	}else{
		$rida = "$nr.	$aeg	${param}:	$sisu"
		Write-Output $rida
		$rida | Out-File -FilePath $fail -Append
	}
}

[int]$aegA = (Get-Date).Millisecond
Valjasta 0 "ALGUS" ("Aeg: "+(Get-Date -Format "dddd MM/dd/yyyy HH:mm K"))

# Ülesanne 1 - Masina nimi (hostname), PowerShelli versioon ja Windowsi versioon
Valjasta 1 "host " (hostname)
Valjasta 1 "PowerShelli versioon " ($PSVersionTable.PSVersion)
Valjasta 1 "Windowsi versioon " ((Get-CimInstance Win32_OperatingSystem).Caption)

# Ülesanne 2 - Võrgu konfiguratsioon (IP-aadress, võrgumask (network mask), gateway, kas DHCP on lubatud ja MAC-aadress

# Ülesanne 3 - Arvuti protsessori kirjeldus ja põhimälu RAM kogus
$systeem = Get-CimInstance Win32_ComputerSystem
Valjasta 3 "protsessor " ((Get-ComputerInfo).CsProcessors.Name)
Valjasta 3 "RAM " ([math]::Round($systeem.TotalPhysicalMemory / 1GB, 2))

# Ülesanne 4 - Graafikakaardi nimi, draiveri versioon, kuupäev ja ekraani lahutus
$graafika = Get-CimInstance Win32_VideoController
#Valjasta $graafika
foreach ($c in $graafika){
    Valjasta 4 "graafikakaardi nimi " ($c.Name)
    Valjasta 4 "draiveri versioon " ($c.DriverVersion)
    Valjasta 4 "draiveri kuupäev " ($c.DriverDate)
    Valjasta 4 "ekraani lahutus $($c.CurrentHorizontalResolution)x$($c.CurrentVerticalResolution)"
    }

# Ülesanne 5 - Arvuti kõvaketaste informatsioon (partitsioonitabel, mitu GB on arvuti kettad mahutavuselt, mitu GB vaba ruumi on C:-kettal)
$ketas = Get-CimInstance Win32_LogicalDisk | Where-Object { $_.DriveType -eq 3 }
foreach ($d in $ketas) {
    Valjasta 5 "ketas " ($d.DeviceID)
    Valjasta 5 "mahutavus " ([math]::Round($d.Size / 1GB, 2))
    if ($d.DeviceID -eq "C:") {Valjasta 5 "C: vaba " ([math]::Round($d.FreeSpace / 1GB, 2))}
}


# Ülesanne 6 - PCI-siinil olevate seadmete draiverite info (kirjeldus, tootja ja versioon)
$draiver = Get-WmiObject  Win32_PnpSignedDriver
foreach ($d in $draiver){
    Valjasta 6 "draiver: $($d.Name), kirjeldus: $($d.Description), tootja: $($d.Manufacturer), versioon: $($d.DriverVersion)"
}

# Ülesanne 7 - Arvutis olevad kasutajad (nimi, kirjeldus, kas on lokaalne kasutaja (LocalAccount) ja kas on keelatud (Disabled))
$kasutajad = Get-CimInstance Win32_UserAccount
foreach ($k in $kasutajad){
    Valjasta 7 "kasutaja nimi: $($k.Name), kirjeldus: $($k.Description), lokaalne: $($k.LocalAccount), keelatud: $($k.Disabled)" 
}

# Ülesanne 8 - Käimasolevate protsesside arv
Valjasta 11 "protsesside arv " ((Get-Process).Count)

# Ülesanne 9 - 10 viimasena käivitatud protsessi (nimi, PID ja käivitamise aeg (StartTime)). Sorteerimise aluseks võtta parameeter StartTime.

# Ülesanne 10 - Arvuti kuupäev ja kellaaeg
Valjasta 10 "arvuti kuupäev ja kellaaeg " (Get-Date)


#Näidisülesanne:
#$naide = Get-Process | Where-Object { $_.ProcessName -eq "dllhost" }
#Valjasta 2 "NAIDE" $naide

[int]$aegL = (Get-Date).Millisecond
$ajakulu = ($aegL - $aegA)

Valjasta 11 "TEHTUD" "$ajakulu`n`n"
```
[tulemus.txt](https://github.com/user-attachments/files/18189299/tulemus.txt)
