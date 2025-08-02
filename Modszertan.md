# A támogatott gyógyszerpiac adatainak feldolgozása
## _Hevenyészett módszertan a publikus adatok elemzéséhez_

Az elemzéseim során a magyarországi támogatott gyógyszerellátás idősoros (publikus) tényadatait dolgozom fel.

Látni kell, hogy a gyógyszertárakban alapvetően kiskereskedelmi tranzakciók történnek. Ami egyedivé teszi, az az, hogy különleges információkkal ellátva, minden esetben szakmai segítséggel juthatunk gyógyszerhez, illetve az, hogy sokszor nem annyit fizetünk érte, amennyi az ára, hanem kevesebbet — ez a TB-támogatás. A patikák ezeket az összegeket megelőlegzik a betegeknek majd később visszaigénylik a társadalombiztosítástól tételes elszámolás formájában.

A gyógyszerek árához nyújtott támogatás igénylése és kezelése éves szinten többszáz milliárd forintot mozgató pénzügyi folyamat (közfinanszírozás), amelynek adatfeldolgozási háttere is részletesen szabályozott ([BÉVER-elszámolás oldal](https://www.neak.gov.hu/felso_menu/szakmai_oldalak/informatika/bever-elszamolas/bever_elsz) a NEAK honlapján). Itt megtekinthető az eredeti adatforrás is (a patikai elszámolások rekordszerkezete), amelyből a NEAK havi rendszerességgel riportokat készít a közfinanszírozási elszámolások alapján és közzéteszi honlapján.

A havi felösszegzett tény-adatokat a NEAK (és elődje az OEP) régebb óta közöl:
- a 2003–2005 közötti időszakról elérhető források **.pdf** formátumban tölthetők le, feldolgozásuk nem vállalható;
- a 2006-tól napjainkig terjedő időszakban viszont feldolgozható, **dBase III** illetve **MS-Access** formátumban érhetőek el adatok.

A lassan húsz évadnyi (havi bontású) adathalmaz kezelhetetlen számosságú file-t jelent (2006–2024 augusztus időszakban 224 állomány), ezért volt szükséges használhatóbb állapotba hozni az adathalmazt: a havi partíciók helyett éves táblák alkalmazása ésszerűnek tűnik. 

Fontos szempont még a **Jupyter** / **Pandas** illetve a **Power BI** könnyű elérhetőség biztosítása is. Mindehhez egy kisebb erőforrásigényű, könnyen telepíthető adatbázismotort (**SQLite3**) választottam.

Python / Jupyter környezetben **Pandas**, **Numpy**, **PyODBC**, **SQLite3** és **OS** csomagok segítségével egy áttöltő alkalmazást fejlesztettem, amely naplózza az MS-Access file-ok olvasását és az adatbázis-írást. Az adatokat havi helyett éves partíciókba rendeztettem. A leválogatást megkönnyítik a view-k összeállítása. A logika Pandas megvalósítás. A vizualizáció többféle programot használok igény szerint:
- Excel-t természetesen az ad hoc feladatokra (hiszen az Excel örök…),
- PowerBI-ban szabvány dashboard-okat építettem, a gyorsjelentések pl. ezen a platformon készülnek,
- Datawrapper-t az adatújságíráshoz használok.

A folyamatos feldolgozás során évek alatt egy közös adatbázist építettem SQLite segítségével (ez jelenleg több mint 24 millió rekordot tárol), amelyből szabvány SQL-lekérdezésekkel állíthatók elő a kívánt statisztikák. Előnye, hogy Google **COLAB** környeztettel kompatibilis ez a tárolási mód.

Néhány fontos tudnivaló (amolyan *disclaimer*):
- ezek az adatsorok nem a közvetlen gyógyszertári kiskereskedelem teljes adatai: a támogatott adatok ennek egy részét jelentik csak (csökkenő mértékben, kb 60%); ez fontos különbségtétel, mert számtalanszor jelentetnek meg egyes datascience cégek elemzéseket a *teljes* gyógyszerpiacról, kizárólag a NEAK-adataira támaszkodva;
- bár a TB-elszámolásokban és a publikus riportokban is az un. TTT-kód szerepel, mint termékazonosító, tudnivaló, hogy egy-egy terméknek évek alatt több TTT-kódja, sőt több forgalmazója is lehet — megszorításokkal használható ez a kódolás;
- bár időben változhat egy-egy termék TTT-kódja, de ezen kód első 2 karaktere jellemzően termékcsoportokat kódol: gyógyszer(alap)anyagok és drogok, galenikumok, gyári gyógyszer-specialitások, kötszerek, gyógyászati segédeszközök, csomagoló-anyagok és magisztrális készítési eljárások, stb. — egyes kimutatásokban ezen kódolást használom;
- a havi riportokban külön dimenzió a recept-típus: lehet M (azaz magisztrális) illetve G (azaz gyári gyógyszerspecialitás) a recept típusa; az ársávok illetve a nettó kiskereskedelmi árrések számításánál kizárólag G-típusú rekordokat veszek figyelembe;
- körültekintést igényelnek továbbá az ATC-kódok, a brand-megnevezések és kvázi-térítési díj mezők használata is: szakmai ellenőrzés nélkül félrevezető adatokat számolhatunk.

**Fontos: ezek az elemzések magánvéleményt tükröznek.**