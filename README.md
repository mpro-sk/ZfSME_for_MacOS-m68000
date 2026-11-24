ZfSME_for_MacOS-m68000

Add Czech and Slovak language support for Plain TeX in OzTeX (Classic Mac OS).

OzTeX: https://macintoshgarden.org/apps/oztex-2

CSTeX: https://petr.olsak.net/cstex.html

OPmac: https://petr.olsak.net/opmac.html

ZfSME: https://www.overleaf.com/read/qmybtpksbhps

V tomto repozitári sa nachádza podpora pre používanie formátu csplain 
v distribúcii TeX pre procesory Motorola 680x0 a Macintosh System 7 -- 
OzTeX 2.1, ako aj podpora pre použitie makrobalíkov OPmac a ZfSME pre 
formát csplain.

Všetky súbory v adresári ZfSME, aj na mnohých ďaľších miestach, majú 
formátovanie konca riadkov, tak ako sa používalo v klasickom MacOS. Tam kde
sa vyskytuje diakritika, sú znaky v kódovaní Mac CE (pre použitie znakov 
jazykov strednej Európy).

V adresári OzTeX2.1 sú všetky súbory potrebné pre formát csplain, ktoré stačí
nakopírovať do adresárovej štruktúry OzTeX. Jedná sa o nové súbory v tejto
adresárovej štruktúre. Jedinou výnimkou je prepísanie súboru 
OzTeX 2.1:Configs:Default, ktorý umožňuje používať doplnené menu, ako aj
nastavenie parametrov, aby bolo možné robiť úpravy a vytvoriť podľa nich
vlastný formát csplain.fmt

V adresári SystemFolder-Fonts sa nachádzajú systémové fonty Bookman, New Century
Schoolbook, Palatino a Times, ktoré je možné použiť v csplain. Pre emuláciu
písacieho stroja (pomocou prepínača \tt) sa v tomto prípade používa systémový
font Courier. Pokiaľ by niektoré z týchto fontov chýbali v adresári
System Folder:Fonts, je možné ich doplniť do tohto adresára.

Adresár ZfSME obsahuje makrá opmac.tex a upravený ams-math.tex (redukcia 
načítania fontov), ktorý opmac volá, ako aj makrá ZfSME2.tex, ktorý môže volať
súbory AKindle.tex a BBQ10.tex upravujúce veľkosť strany a formátovanie pre
konkrétne zariadenia, epsf.tex pre načítanie obrázkov vo formáte eps a pomocné
makro NumOn.tex pre opätovné zapnutie číslovania položiek obsahu.

Makrá z balíkov opmac a ZfSME sa používajú pri preklade súboru Trilogie.tex,
ktorého výstupom je Trilogie.dvi (možné zobraziť integrovaným prhliadačom 
OzTeX-u). ktorý môže volať jednotlivé novely zbierky Hordubal.tex, Povetron.tex,
a Obycejny_zivot.tex. Pre potreby odladenia spätného prekódovania súboru
Trilogie.ref z ISO8859-2 do MacCE pre automatické generovanie obsahu sa používal
súbor TestDia.tex, ale po odladení už nie je potrebný. Pri behu TeX-u sa
generujú aj súbory o priebehu prekladu do dvi -- Trilogie.log a pomocný súbor
Trilogie.ref.

Testované v emulátore Basilisk II, s ROM Quadra 630 
https://en.wikipedia.org/wiki/Macintosh_Quadra_630,
36 MB RAM, System 7.5.3, (v rovnakej konfigurácii, akú som mal možnosť používať 
niekedy v 2. polovici 90. rokov). 
Možné je používať väčšinu funkcií, ktoré umožňuje výstup do dvi,
ale niektoré funkcie nefungujú (kapitálky, zavesené interpunkčné znamienka).
Z tohto dôvodu boli upravené niektoré makrá v ZfSME.tex, aby sa aj pri ich
výbere v nastavení neukončil beh TeX-u chybou.
Generovanie niektorých znakov pomocou OzMF (METAFONT) pri použitom rozlíšení
vykazuje pre cs-fonty chyby. Viditeľné je to pri čísliciach 3, 6 a 9, ako aj
pri písmene veľké B. Zobrazenie bitmapových fontov aj tak nevyzerá veľmi
dobre. Odporúčam preto používať systémové fonty, ktoré používajú v prehliadači
DVI pre ich zobrazenie QuickDraw, takže zobrazenie je lepšie (hlavne ak sa
používa iná, ako 100% veľkosť zobrazenia). Pred ich použitím je potrebné, aby
sa aktivovali cez menu Config > Add System PS Fonts.

Uvedená verzia OzTeX-u dokonca funguje aj v emulátore Mini vMac, ktorý emuluje 
Apple Macintosh Plus 
https://en.wikipedia.org/wiki/Macintosh_Plus
(s 4 MB RAM) so System 7.0.1, tak aby pre OzTeX bolo 
k dispozícii aspoň 3,1 MB RAM. Dá sa to dosiahnuť potlačením načítania 
rozšírení (Extensions) a minimalizovaním diskovej cache na hodnotu 32 kB.
Ani v tomto prípade však nie je možný multitasking s textovým editorom, lebo 
OzTeX obsadí celú voľnú časť RAM. Reálne použitie je preto obmedzené, hlavne
ak je nastavená aj v emulátore pôvodná rýchlosť, ktorá by bola pri použití 
8 MHz procesora Motorola 68000 v Macintosh Plus. Treba však mať na pamäti,
že v čase uvedenia tohto počítača na trh (január 1986) ani pre TeX nebola
k dispozícia verzia 3, ktorá by umožnila použitie formátu csplain.  Z dôvodu
absencie potrebných systémových fontov a obmedzené použitie QuicDraw pri 
množstve voľnej RAM, je v tomto prípade použitie obmedzené na bitmapové (.pk)
cs-fonty.
