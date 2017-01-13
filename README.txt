#[WDKKP] Projekt - HarvesterJob
# __author__ = 'Micha³ Bogdanowicz'

wersja1 - napastnik ma dostêp do internetu
wersja2 - napastnik nie ma dostêpu do internetu

########WERSJA 1 i 2 - Ofiara

Na potrzeby wyobra¿enia sobie skali zagro¿enia jakie nios¹ za sob¹ strony phishing'owe przyjmijmy, ¿e w³aœnie wsiadamy do naszego ulubionego poci¹gu, niech to bêdziê stare dobre InterCity, by wyruszyæ w d³ug¹, ¿mudn¹ podró¿ w kierunku rodzinnego domu w jedyny wolny weekend w tym semestrze.. Wszystko by³o by do prze¿ycia gdyby nie to, ¿e po chwili od startu gubimy zasiêg, a nieodœwie¿ona playLista dawno nam siê przejad³a.  

"...mo¿e jest tu Wi-Fi albo ktoœ ma jakiœ niezabezpieczony HotSpot, ja, Student informatyki kontra WEP? Co to dla mnie..." 

########WERSJA 1 - Ofiara

61-02-ED-6C-21-C6 --- IterCity Wi-Fi Free --- unsecured
D7-69-EB-D7-2A-EC --- Manager Biedronki --- WPA-AES
83-02-2F-5B-19-46 --- Xperia-Z3 --- unsecured

"Czy¿by los siê do mnie uœmiechn¹³?" :)

facebook, twitter, usos, email, wszystko, dos³ownie wszystko chodzi³o piêknie (wiadomo czasem by³y przerwy, ale by³o darmo wiêc nie ma co narzekaæ). 

########WERSJA 2 - Ofiara

61-02-ED-6C-21-C6 --- IterCity OnlyFacebook* --- unsecured
D7-69-EB-D7-2A-EC --- Manager Biedronki --- WPA-AES
83-02-2F-5B-19-46 --- Xperia-Z3 --- WPA-AES

*lub jakikolwiek inny znany portal, do ktorego ludzie chêtnie zajrz¹, który oczywiœcie wi¹¿e ze sob¹ koniecznoœæ logowania.

"Nie jest tak Ÿle, chocia¿ fejsa przejrzê.." :)

"wpisa³em has³o, coœ nie dzia³a, mo¿e jeszcze raz.. to pkp siê nied³ugo rozleci" - ostentacyjnie zak³adam s³uchawki.

########UWAGA - Ofiara

Mog¹ pojawiæ siê ostrze¿enia, ¿e sieæ nie jest bezpieczna, ale w koñcu jest publiczna, wiêc wiekszoœæ siê tym zbytnio nie przejmie. Bystre oko zaktualizowanej przegl¹darki równie¿ mo¿e doszukaæ siê problemu w w³asnorecznie podpisanym certyfikacie i podœwietliæ go na "¿ó³to", po najechaniu jednak na ten button widaæ, ¿e wystawiono go dla facebook'a.

########WERSJA 1 i 2 - Napastnik

Jak mi³o patrzeæ jak ludzie mkn¹ przed siebie, otoczeni technologi¹, maj¹c œwiat na wyci¹gniecie rêki, z³udne poczucie bezpieczeñstwa i bliskoœci innych zasypuj¹c siê danymi, czêsto pozbawiaj¹c siê resztek prywatnoœci. Dopijam kawê i wsiadam zaj¹æ jakieœ wygodne miejsce w najbardziej opustosza³ym przedziale, tak by nikt mi nie zagl¹da³ w komputer. A jednak ludzka ciekawoœæ, dziadzia siedz¹cy obok i tak pewnie nic nie zrozumie ale lepiej nie kusiæ losu, dobrze, ¿e kupi³em dziœ ten filtr prywatyzuj¹cy, popatrzy siê co najwy¿ej w szary mat. Wyciagam laptop, zanim jednak plecak wrzucê na pó³kê, nie wyci¹gaj¹c z niego odpalam bezprzewodowy router o doœæ du¿ym zasiêgu pod³aczony pod powerbanka. Cudo. 

Muszê w koñcu porozsy³aæ ten spam z SuperXXX16hot, gdzie na moich goœci czeka równie wyrafinowany exploit wprost z Metasploit OpenSource(prglng.Ruby). A mo¿e znowu ktoœ siê z³apie na œledzenie swojego znajomego przez subskrybcjê na DOtPayu. Czy Ci ludzie naprawdê ³ykaj¹ wszystko? 

No dobrze, zobaczmy jak bardzo otaczaj¹cy mnie ludzie s¹ mobilni.. Za³o¿e siê, ¿e ktoœ na pewno wejdzie na facebook, dobre miejsce na rozes³anie spamu.
Teraz mogê albo uruchomiæ przegl¹darkê, wpisaæ:

https://facebook.com/login.php

Prawy przycisk -> zapisz stronê i wrzuciæ to w: /var/www/

Ale chwila, raz ¿e mo¿e nie skopiowaæ siê ca³a zawartoœæ, dwa jest 21 wiek, mam od tego narzêdzia do socjotechnicznych pentestów. Czarny t³o terminala zdobi ekran Debiana:

root@kali:~# setoolkit 			#wymagany jest root komenda: su / sudo
set> 1					# 1) Social-Engineering Attacks
set> 2					# 2) Website Attack Vectors
set> 3					# 3) Credential Harvester Attack Method

Mo¿emy skorzystaæ z gotowych templates ale nie musz¹ one byæ zgodne z aktualnymi, u¿yjmy zawartê w tym zbiorze Clonera:

set:webattack>2				# 2) Site Cloner

Nastêpnie musimy podaæ swoje ip, lub ip serwera który odbierze dane wys³ane przez ofiarê. Odpalny drugi terminal:

root@kali:~# ifconfig 			#eth0 lub wlan0 i tam inet

Wracamy do pierwszego:

set:webattack>127.0.0.1 		#ip z drugiego terminala
set:webattack>https://www.facebook.com 	#tutaj wpisujemy host panelu logowania wybranej strony

Wystarczy chwilê poczekaæ, a nasza strona ju¿ jest dostêpna w naszej sieci dziêki oprogramowaniu apache2.
Gdy jednak poszliœmy manualn¹ drog¹ kopiujemy stronê do /var/www, odpalamy terminal :

root@kali:~# apt-get install apache2
root@kali:~# /etc/init.d/apache2 start

Problemem jest tylko to, ¿e "mojego" facebooka zobacz¹ tylko ludzie znaj¹cy IP mojego komputera...


......
		



