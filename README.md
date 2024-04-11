# linux-notes
- zobrazení souboru: nano [filename]
- vytvoření složky: mkdir [-p] [path/dir_name]
- vytvoření souboru: touch [path/file_name]
- kopírování: cp -R [dir] [destination_dir]
- zobrazení procesů: ps -A
- update repositářů: sudo apt upgrade
- vytvoreni usera:useradd -d /directory -s /shell [nazev_uctu] nebo adduser [nazev_uctu]
- vypsání deamonů: /etc/init.d/[app_name] status [app_name]
  [app_name]
- ověření statu: service/systemctl [app_name] [status/start]
- složky spojené s uživatelích
  1. /etc/passwd
  2. /etc/group - admin, sudi
- nastavení hesla: passwd [user]
- změna vlastníka: chown [user] [podřazená_dir]
- změna přístupu: chmod [700] || [uga+-rxw] [dirfile_name]
- vytvoření skupiny: groupadd [groupname]
- cron: crontab -e >> 1 >> min hod dayofmonth month dayofweek [path/dirfilename]
instalace:
     1. openjdk - sudo apt-get install openjdk-8-jre
     2.  intellij com. - sudo snap install intellij-idea-community --classic --edge
     3.  inkscape - sudo apt install inkscape
     4.  dhcp - sudo apt-get install isc-dhcp-server
     5.  dns - sudo apt-get install bind9 -y
     6.  tasksel - sudo apt install tasksel >> +LAMP Server
     7.  lamp - sudo tasksel install lamp
     8.  apache2 - sudo apt install apache2
- konfigurace
    1. LAMP >> apache2
       - https://ubuntu.com/tutorials/install-and-configure-apache#2-installing-apache
       -cd /etc/apache2/sites-available
       - cp 000-default.conf myconf.conf
       - změnit alias/domain/dirname
       - mkdir /myweb >> nano index.html
    3. DHCP
      - nano /etc/dhcp/dhcpd.conf >> subnet [address] netmask [netmask] { range [from_ip_address] [to_ip_address]}
      - host [name] { hardware erhernet XX:XX:XX:XX:XX:XX:XX}
      - nastavení interfacu: nano /etc/default/isc-dhcp-server
      -ip na XXX.XXX.XXX.XXX/XX dev enp0s8
    5. DNS
      -cd /etc/bind9
      -cat named.conf.default >> zkopírovat zónu
      -sudo nano named.conf.[name.net] >> uložit a přrejmenovat zónu na [name.net]
      -sudo nano named.conf >> include "/etc/bind/named.conf.[name.net]"
       -cp dev .local [name.net]
-------------------------------------------------------------------------------------
2. Vytvoření admina:
•	Sudo mkdir  -p /admin/data (Tímto vytvořím domovský adresář)
•	Sudo useradd -d /admin/data -s /bin/bash admin (Tímto vytvořím admina)
•	Sudo passwd admin (Tímto vytvořím heslo pro admina)
•	Sudo nano /etc/passwd (Napíšu jmeno v adresáři, Linux Administrator)Sudo 
•	Sudo nano /etc/group ( přidám oprávnění k adminovi: adm, sudo)
•	Sudo cp -R /etc/skel /admin/data (Překopírování dat z skel)
•	Sudo Chown admin data (Oprávnění pro admina, být v rootu /admin#)
•	Sudo Chmod 700 data (Odebrání rootu) 
•	ll /admin/data (Podívání do složky data)
•	cd /admin/data (adresář)
•	su admin (přihlášení admina)
•	cd ~ (Domovský adresář)

 Vytvoření uživatele:
•	Sudo groupadd delon (Vytvoření skupiny delon)
•	Sudo adduser alan (vytvoření uživatele alan)
•	Sudo nano /etc/group (přidání alana ke skupině delon)
•	Sudo Sudo chgrp delon alan (alan ve složce delon)
•	Sudo Chmod 740 alan (pouze na čtení v adresáři)
•	Su alan (Přihlášení na alana)

3. Vložení příkazu:
•	Sudo nano test.sh
1.	Cp -R ~/Dokumenty /tmp
2.	Kill -kill 15658
3.	Mkdir ~/Script
4.	Touch test.sh
5.	Chmod ug+x test.sh
6.	Chown alan test.sh
7.	Ps -A

4. Spuštení scriptu každě pondělí v 1 hodinu
•	Crontab -e (upravení cronu)
1.	0 1 * * * ~/test.sh

5. Instalace Inkscape
•	Sudo apt update (aktualizace)
•	Sudo apt install inkscape ( instalace inkscape)
•	Sudo snap install  –-classic intelliJ idea ...(možné stáhnutí na ubuntu software)

