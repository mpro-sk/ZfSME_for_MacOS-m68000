ZfSME_for_MacOS-m68000

Add Czech and Slovak language support for Plain TeX in OzTeX (Classic Mac OS).

V tomto repozitári sa nachádza podpora pre používanie formátu csplain 
v distribúcii TeX pre procesory Motorola 680x0 a MacOS7 -- OzTeX 2.1, ako aj
podpora pre použitie makrobalíkov OPmac a ZfSME pre formát csplain.

Všetky súbory v adresároch majú formátovanie konca riadkov, tak ako sa 
používalo v klasickom MacOS. Tam kde sa vyskytuje diakritika sú znaky kódované
v kódovaní Mac CE (pre použitie znakov jazykov strednej Európy).

V adresári OzTeX2.1 sú všetky súbory potrebné pre formát csplain, ktoré stačí
nakopírovať do adresárovej štruktúry OzTeX. Jedná sa o nové súbory v tejto
adresárovej štruktúre. Jedinou výnimkou je prepísanie súboru 
OzTeX2.1:Configs:Default, ktorý umožňuje používať doplnené menu, ako aj
nastavenie parametrov, aby bolo možné robiť úpravy a vytvoriť podľa nich
vlastný formát csplain.fmt

V adresári SystemFolder-Fonts sa nachádzajú systémové fonty Bookman, New Century
Schoolbook, Palatino a Times, ktoré je možné použiť v csplain. Pre emuláciu
písacieho stroja (pomocou prepínača \tt) sa v tomto prípade používa systémový
font Courier. Pokiaľ by niektoré z týchto fontov chýbali v adresári
System Folder:Fonts je možné ich doplniť do tohto adresára.

Adresár obsahuje makrá opmac.tex a upravený ams-math.tex (redukcia načítania
fontov), ktorý opmac volá, ako aj makrá ZfSME2.tex, ktorý môže volať súbory
AKindle.tex a BBQ10.tex upravujúce veľkosť strany a formátovanie pre konkrétne
zariadenia, epsf.tex pre načítanie obrázkov vo formáte eps a pomocné makro 
NumOn.tex pre opätovné zapnutie číslovania položiek obsahu.

Makrá z balíkov opmac a ZfSME sa používajú pri preklade súboru Trilogie.tex,
ktorého výstupom je Trilogie.dvi (možné zobraziť integrovaným prhliadačom 
OzTeX-u). ktorý môže volať jednotlivé novely zbierky Hordubal.tex, Povetron.tex,
a Obycejny_zivot.tex. Pre potreby odladenia spätného prekódovania súboru
Trilogie.ref z ISO8859-2 do MacCE pre automatické generovanie obsahu sa používal
súbor TestDia.tex, ale po odladení už nie je potrebný. Pri behu TeX-u sa
generujú aj súbory o priebehu prekladu do dvi Trilogie.log a pomocný, už
spomínaný súbor, Trilogie.ref.





