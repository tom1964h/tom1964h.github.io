# Adatforrás - a magyar támogatott gyógyszer- és GYSE-piac adatai
## _Társadalombiztosítási adatok bemutatása_

A [társadalombiztosítás](https://hu.wikipedia.org/wiki/T%C3%A1rsadalombiztos%C3%ADt%C3%A1s#:~:text=A%20t%C3%A1rsadalombiztos%C3%ADt%C3%A1s%20(r%C3%B6viden%20tb)%20az,saj%C3%A1t%20munk%C3%A1jukkal%20gondoskodni%2C%20tartal%C3%A9kk%C3%A9pz%C3%A9sre%20k%C3%B6telezik.) a társadalom működésének fontos része.
Magyarországon a _felosztó-kiróvó_ társadalombiztosítási (**TB**-) rendszernek és az ennek működtetését végző állami adatfeldolgozó szolgáltatásoknak köszönhetően egyedülállóan teljes és komplex egészségügyi adatvagyon halmozódott fel.

A közvetlen lakossági (kiskereskedelmi), ártámogatott gyógyszer- és gyógyászati segédeszköz-ellátást több törvény és rendelet szabályozza, többek között, pl.:
- a [_217/1997. (XII. 1.) Korm. rendelet
a kötelező egészségbiztosítás ellátásairól szóló 1997. évi LXXXIII. törvény végrehajtásáról_](https://net.jogtar.hu/jogszabaly?docid=99700217.KOR) illetve pl.
- az [_1/2003. (I. 21.) ESzCsM rendelet
a társadalombiztosítási támogatással rendelhető gyógyszerekről és a támogatás összegéről_](https://net.jogtar.hu/jogszabaly?docid=a0300001.esc)

További információk a gyógyszerek árának támogatásáról lásd: [gyógyszerek ártámogatása](https://egeszsegvonal.gov.hu/gyogyszerek-a-z/gyogyszertamogatasi-rendszer.html).

Az adatok szempontjából meghatározó a havi granularitás (mert kiskereskedelmi örökség a _havi zárás_ gyakorlata és ez a TB-elszámolások ütemezésében is tovább él). Az *elszámolási adatok* a NEAK rendszerébe érkeznek, pontosan meghatározott felépítésben, lásd bővebben itt: [BÉVER elszámolás - Fehér Könyv](https://www.neak.gov.hu/letoltheto/ATFO_dok/gyogyszer/feher_konyv).

Az elszámolási rendszer fontos eleme a központi terméktörzs, a [Publikus Gyógyszertörzs (PUPHA)](https://www.neak.gov.hu/felso_menu/szakmai_oldalak/gyogyszer_segedeszkoz_gyogyfurdo_tamogatas/egeszsegugyi_vallalkozasoknak/pupha/Publikus_Gyogyszertorzs), hiszen az elszámolt gyógyszerek központi azonosítása alapvetően fontos: a TB-elszámolások egyik tengelye a TTT-kódolás (termékkódok). A NEAK gyógyszertörzs adatainál a kezdetektől fogva (kb. 30 éve) alkalmazzák ezt a kódolási technikát. Ez a rendszer erősen veszített következetességéből az elmúlt években. Az eredetileg minden támogatott (sőt: nemtámogatott) gyógyszerre alkalmazni kívánt azonosítási rendszer csoportkódjait a 9 jegyű kódok első két karakterében találhatjuk:
- 1-essel kezdődő TTT-vel kódolják a “magisztrális” készítményeket:
  - 11-es, 13-as és 14-es kódok: gyógyszeranyagok és gyógynövények (ezekből készítenek a patikákban gyógyszert vagy szerelik ki)
  - 12-es kódok: gyógyszertári készítmények a FoNo (szabványos vényminták szerint): pl. kanalas orvosságok vagy kúpok
- a 2-essel kezdődő TTT-kódok “gyári gyógyszerspecialitások”:
  - 21-es, 27-es kódok: gyógyszerkészítmények
  - 22-es kódok: immunterápiás készítmények és vakcinák (többnyire)
  - 23-as kódok: gyógytápszerek, speciális táplálási igényt kielégítő készítmények
- 51-es kóddal kezdődnek a csomagolóanyagok kódjai, amelyeket a gyógyszertári gyógyszerkészítéshez használnak fel (pl. flakonok, palackok, tégelyek, stb.)
- 61-es kóddal kezdődnek azok a rekordok, amelyekkel a gyógyszertári gyógyszerkészítés során alkalmazott eljárásokat kódolják, pl. mérés, elegyítés, kenőcs készítése, stb.

A NEAK elszámolórendszerébe havonta beérkező többmillió elszámolási rekordból különböző felösszegzésekkel állítják elő azt a publikus forgalmi adatbázist, amelyet MS ACCESS **.mdb** formátumban tesznek közzé. A forgalmi adatok közvetlen elérése:
- lásd [Gyógyszerforgalmi adatok](https://neak.gov.hu/felso_menu/szakmai_oldalak/publikus_forgalmi_adatok/gyogyszer_forgalmi_adatok/gyogyszer_forgalmi_adatok)
- lásd [Gyógyászati segédeszköz forgalmi adatok](https://neak.gov.hu/felso_menu/szakmai_oldalak/publikus_forgalmi_adatok/gyse_forgalmi_adatok/gyse_forg_adat)

A forrásadatok oldalán rendre megtalálható egy-egy link, amely az adatmezők leírására mutat.

Gyógyszer területen havonta 100-120 ezer sornyi adatot publikálnak így, ez évente 1,2 - 1,4 millió sort jelent. Az adatbázisban vannak megyei és országos bontású táblák is. Mindegyikben termékszintű forgalmi adatok találhatóak.

Érdekesség, hogy a PUPHA (és így a forgalmi adatok is) [WHO ATC](https://atcddd.fhi.no/atc_ddd_index/) rendszert használ, ami eltérhet az [EPHMRA](https://www.ephmra.org/anatomical-classification) ATC kódkiosztásától.

A havi felösszegzett tény-adatokat a NEAK (és elődje az OEP) régebb óta közöl:
- a 2003–2005 közötti időszakról elérhető források **.pdf** formátumban tölthetők le, feldolgozásuk nem vállalható;
- a 2006-tól napjainkig terjedő időszakban viszont feldolgozható, **dBase III** illetve **MS-Access** formátumban érhetőek el adatok.

