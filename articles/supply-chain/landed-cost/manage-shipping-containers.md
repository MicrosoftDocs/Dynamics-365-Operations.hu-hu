---
title: Szállítókonténerek kezelése
description: Ez a témakör azt ismerteti, hogyan kell dolgozni a szállítási tárolókval. A szállítókonténerek az áruk fizikai csoportosítására használhatók. Akkor is használatosak, ha a költségeket csak az adott áruk között kell megosztani, általában azért, mert fizikailag együtt vannak.
author: Weijiesa
ms.date: 12/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ITMContainersListPage, ITMContainers
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2020-12-14
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 22f2512125679f160cb658923893d5f5aa739a2d
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8906153"
---
# <a name="manage-shipping-containers"></a>Szállítókonténerek kezelése

[!include [banner](../../includes/banner.md)]

A szállítókonténerek az áruk fizikai csoportosítására használhatók. Akkor is használatosak, ha a költségeket csak az adott áruk között kell megosztani, általában azért, mert fizikailag együtt vannak.

Az áruknak a szállítókonténer oldalon keresztül történő megtekintéséhez és feldolgozásához lépjen a **Partraszállítási költség \> Szállítókonténerek \> Összes szállítókonténer** lehetőségre. Az **Összes szállítókonténer** oldalon látható az összes elérhető szállítókonténer listája. A Művelet panel gombjaival szállítókonténereket hozhat létre, törölhet és kezelhet. A lista bármely szállítókonténerét kiválasztva megtekintheti a részleteit **Szállítókonténerek** oldalon.

A szállítókonténer részletes oldalának felső részén a szállítókonténerre vonatkozó és a költségszámítási adatok láthatóak. A **Sorok** szakasz a konténerhez csatolt leveleket, cikkeket, beszerzési rendeléseket és átmozgatási rendeléseket mutatja.

## <a name="action-pane"></a>Műveleti panel

Az **Összes szállítókonténer** és **Szállítókonténerek** oldalak Művelet panelje olyan gombokat tartalmaz, amelyek segítségével a kiválasztott szállítókonténerrel lehet dolgozni. Minden gomb egyetlen műveletet hajt végre. A Művelet panel lapokat is tartalmaz, amelyek viszont kapcsolódó gombokat biztosítanak. A jelezett kivételtől függően az alábbi alszakaszok alatt leírt gombok és lapok mind a listanézetben (azaz az **Összes szállítókonténer** oldalon), mind a részletes nézetben (azaz a **Szállítókonténerek** oldalon) elérhetők.

### <a name="buttons-on-the-manage-tab"></a>Gombok a Kezelés lapon

A következő táblázat a Művelet panel **Kezelés** lapján elérhető gombok leírását tartalmazza.

| Gomb | Leírások |
|---|---|
| Bevételezési lista feladása | Bevételezési lista feladása vagy a szállítókonténerben található összes beszerzésirendelés-sor termékbevételezési listájának megtekintése. Többvállalatos szállítmányok használata esetén minden vállalat számára új bevételezésilista-feladási párbeszédpanel nyílik meg. |
| Termékbevételezés feladása | Termékbevételezés feladása a szállítókonténerben található összes beszerzésirendelés-sorhoz. |
| Számlafeladás | Számla feladása a szállítókonténerben található összes beszerzésirendelés-sorhoz. Többvállalatos szállítmányok használata esetén minden vállalat számára új számlafeladási párbeszédpanel nyílik meg. |
| Átmozgatási rendelések szállítása | Átszállítási rendelés szállítmányának feladása a szállítókonténerben található összes átszállításirendelés-sorhoz. A párbeszédpanelen a szállítókonténernek csak azok a sorai jelennek meg, amelyek átszállítási rendelés típusúak. |
| Átmozgatási rendelés bevételezése | Átszállítási rendelés bevételezésének feladása a szállítókonténerben található összes átszállításirendelés-sorhoz. A bevételezési párbeszédpanel a szállítókonténerben vagy hajóúton lévő áruk bevételezésének legegyszerűbb módja, amely a három lehetséges lehetőség egyike. Érkeztetési naplókból és mobileszközös feldolgozásból is lehet bevételezni. |
| Érkezési napló létrehozása | A szervezetek érkeztetési naplóját speciális raktári funkciók használatával lehet létrehozni. A lehetőségek a _Mennyiség inicializálása_ (ajánlott), illetve a _Létrehozás úton lévő árukból_ vagy a _Létrehozás beszerzési rendelésekből_. Az utolsó két lehetőség attól függ, hogy használatban van-e az úton lévő áruk feldolgozása. |
| Átnevezés | Egy párbeszédpanel megnyitása, ahol átnevezheti a kiválasztott szállítókonténert. |
| Utazási sablon módosítása | A hajóútsablon módosítása. A hajóútsablon módosítása után lehet, hogy az **Automatikus költségek kerese** lehetőséget kell választani, vagy manuiálisan újra hozzá kell adni a költségeket, mert a szállítási költségek törlődnek. |
| Átalakítás bérelhető típusúvá | Kiválasztott szállítókonténer átalakítása bérelt szállítókonténerré. |

### <a name="buttons-on-the-general-tab"></a>Gombok az Általános lapon

A következő táblázat a Művelet panel **Általános** lapján elérhető gombok leírását tartalmazza.

| Gomb | Leírások |
|---|---|
| Bevételezések listája | Bevételezési lista feladása a szállítókonténerben található összes beszerzésirendelés-sorhoz. Többvállalatos hajóút használata esetén minden vállalat számára új bevételezésilista-feladási párbeszédpanel nyílik meg. |
| Termékbevételezés | A termékbevételezési rekord megtekintése, ha használatban van. A termékbevételezési folyamatot csak akkor használja a rendszer, ha az áruk nem használják az úton lévő áruk funkciót. |
| Cikk érkezése | A szállítókonténer cikkérkeztetési naplójának megtekintése, amennyiben ez a napló van használva. |
| Szakaszok | A szakaszokat a hajóút különböző részeinek azonosítására használják. Az átfutási idők az egyes szakaszokkal társíthatók a szállítmánykövetés segítségével. A további tudnivalókat lásd: [Többszakaszos út beállítása](multi-leg-journey-setup.md). |
| Nyomon követés | Szállítmánykövetés megtekintése vagy frissítése. |
| Úton lévő áruk rendelései | Az **Úton lévő áruk** oldalát közvetlenül a kontlnerből lehet megnyitni. Ez az oldal csak a kiválasztott szállítókonténerben található, úton lévő árukra vonatkozó rekordokat jeleníti meg. |

## <a name="header-view"></a>Fejlécnézet

A **Fejléc** nézet megnyitásához nyisson meg egy szállítókonténert, majd válassza a szállítókonténer fejlécének jobb felső részén található **Fejléc** lapot.

### <a name="settings-on-the-general-fasttab"></a>Az Általános gyorslap beállításai

Az alábbi táblázat leírja azokat a beállításokat, amelyek az szállítókonténer **Fejléc** nézetében, az **Általános** gyorlapon érhetők el.

| Mező | Leírás |
|---|---|
| Szállítási konténer | A szállítókonténer neve. |
| Út | A szállítókonténerhez kapcsolódó hajóút. |
| Szállítási konténer típusa | Adja meg a szállítókonténer típusát. Ezt a mezőt be kell állítani. A fuvardíj meghatározására használhatja, például a szállítókonténer-típushoz kapcsolódó automatikus költség kiválasztásával. |
| Hajó | Adja meg vagy válassza ki a hajót. Ha a hajó nincs értékként felsorolva, akkor a hajó azonosítóját megadhatja szabad szövegként. Ebben az esetben a főtábla nem frissül, hogy később ki lehessen választani a hajó azonosítóját ebben a mezőben. A további tudnivalókat lásd: [Hajók](shipping-information-setup.md#vessels). |
| Egységtípus | Az egységtípusok a szállítókonténerek csoportosításának és azonosításának további eszközként használhatók. Megjelennek és ki vannak jelölve a szállítókonténer oldalán. További tudnivalókért lásd: [Egységtípusok beállítása](shipping-container-setup.md#unit-types). |
| Hűtés típusa | A hűtéstípusok a szállítókonténerek (általában hűtött konténerek) csoportosításának és azonosításának további eszközként használhatók. Megjelennek és ki vannak jelölve a szállítókonténer oldalán. További tudnivalókért lásd: [Hűtéstípusok beállítása](shipping-container-setup.md#refrigeration-types). |
| Mértékegység | Ez a mező teszi lehetővé a **Partraszállítási költség** modulban megadott mérték beállítását. A mértékeket gyakran használják azok a szervezetek, amelyek nem ismerik az áruk egyedi mennyiségét vagy súlyát, de pontosabb arányosítást igényelnek, mint amit az összeg vagy mennyiség biztosít. A fuvarozó megadja a súlyt kilogrammban vagy a köbméteres mértéket, és azt elhelyezheti egy cikk vagy a beszerzési rendelés szintjén. A paraméter kiválasztása esetén automatikusan frissíthető, illetve manuálisan is meg lehet adni. |
| Mértékegység | A **Mérték** mezőben taláklható számra vonatkozó mértékegység. |
| Tényleges súly | Rögzítheti a karton vagy a konténer tényleges súlyát. Ez az érték a szállítókonténer beállítása során megengedett maximális tömeg ellenőrzése céljából használható. |
| Kartondobozok száma | A rendszer automatikusan frissíti a kartonok számát, ha ez a paraméter be van jelölve. |
| Áruk leírása | Az áruk leírása a szállítókonténerben vagy a levélfejlécben választható ki. A hajóút, a szállítókonténer vagy az árulevelek azonosítására használatos. További információért tekintse meg az [Áruk leírása](shipping-information-setup.md#description-of-goods) részt. |
| Házi légi fuvarlevél/fuvarlevél | Megadhatja a házon belüli légi fuvarlevelet vagy fuvarlevelet a szállítókonténerhez. |
| Megjegyzések | A szállítókonténerre vonatkozó kiegészítő információk. |
| Visszaküldhető | Ez az érték jelzi, hogy vissza lehet-e küldeni a szállítókonténert az út után. |
| Út állapota | A szállítókonténerhez kapcsolódó út állapota. |
| Beszerzési rendelés állapota | A szállítókonténerhez kapcsolódó beszerzési rendelés állapota. |

### <a name="settings-on-the-delivery-fasttab"></a>A Szállítás gyorslap beállításai

Az alábbi táblázat leírja azokat a beállításokat, amelyek az szállítókonténer **Fejléc** nézetében, az **Szállítás** gyorlapon érhetők el.

| Mező | Leírás |
|---|---|
| Létrehozás dátuma és időpontja | A konténer létrehozásának dátuma és ideje. |
| Gyári átvétel dátuma | Ezt a dátumot általában a gyár/szállító adja meg, amely jelzi, hogy várhatóan mikor hagyják el az áruk a telephelyét. Ha ázsiaiában található gyárral működik együtt, akkor gyakran ez a dátum szükséges, nem pedig az a dátum, amikorra a cikkekre számít. (Ellentétben a helyi szállítással, ahol az a dátum szükséges, amikorra az árut várják.) Ezt a mezőt ki lehet tölteni a szállítókonténerek listájában található beszerzésirendelés-sorok alapján. Itt is megadhatja manuálisan. |
| Szállítási dátum | Ez a dátum a beszerzési rendelés dokumentumára nyomtatható. Általában tájékoztatja az üzemet/szállítót arról a dátumról, amikorra az árut a kikötőbe kell szállítani. Ez a mező csak tájékoztatásra szolgál. Nem használatos a szállítókonténerben található áruk várható szállítási dátumának becslésére. A mező beállítható úgy, hogy automatikusan frissüljön a nyomon követési ellenőrző lap frissítése esetén. |
| Üzletbe kerülés dátuma | A legkorábbi dátum, amikor a hajóúthoz kapcsolódó beszerzési rendelésekből származó áruk elérhetők lesznek értékesítésre.|
| Becsült szállítási dátum | Általában az a dátum, amikorra az áru megérkezik a raktárba. Ez a mező csak tájékoztatásra szolgál. Ez nem használatos a szállítókonténerben található beszerzésirendelés-sorok alaptervezésének kiszámítására. A beszerzésirendelés-sorok várható szállítási dátuma a nyomon követési ellenőrzésen keresztül frissül. A mező beállítható úgy, hogy frissüljön a nyomon követési ellenőrző lap frissítése esetén. |
| Indulás dátuma | Altalában az a dátum, amikor a repülőgép vagy hajó ténylegesen elhagyja a tengerentúli kikötőt. |
| A becsült érkezési időpont a szállítási kikötőnél | A becsült érkezési dátum a célkikötőnél („cél” kikötő). |
| Az eredeti dokumentumok beérkeztek | Opcionális: Frissítse az eredeti dokumentumok beérkezési dátumát. |
| Ügynök tanácsa szerint | Opcionális: A közvetítő értesítési dátumának frissítése. |
| Eredeti fuvarlevél elküldve | Opcionális: Az eredeti fuvarlevél elküldési dátumának frissítése. |
| Kiadott áruk | Opcionális: Az áruk kiadási dátumának frissítése. |
| Vevői találkozó | Opcionális: A vevői találkozó dátumának frissítése. |
| Kiszállítva a raktárba | Opcionális: Az áru raktárba szállítási dátumának frissítése. |
| Ellenőrzési dátum | Nem kötelező: Az ellenőrzési dátum frissítése. |
| Szállítási utasítások | Opcionális: A szállítási utasítások dátumának frissítése. |
| Kiindulási kikötő | Az a kikötő, amelyből a cikkeket szállítani fogják. |
| Célkikötő | Az a kikötő, amelybe a cikkeket szállítani fogják. |
| Helyi fuvarozó | Ez a mező csak tájékoztatásra szolgál. A helyi szállítmányozónak kiválaszthatónak kell lennie a szállítói táblából. |
| Helyi szállítás dátuma | Megadja a dátumot, amikorra a helyi szállítás le van foglalva. Ez a mező segítséget ad a raktárnak a tervezésben. |
| Helyi szállítás időpontja | Adja meg az idősávot. Ez a mező segítséget ad a raktárnak a tervezésben. |
| Utazássablon | A hajóúthoz megadott útsablon. Az útsablon tartalmazza a „cél” és „indulási” kikötőket, valamint a szállítókonténer nyomon követési ellenőrzéséhez társított átfutási időket. |

### <a name="settings-on-the-other-fasttab"></a>Az Egyéb gyorslap beállításai

Az alábbi táblázat leírja azokat a beállításokat, amelyek az szállítókonténer **Fejléc** nézetében, az **Egyéb** gyorlapon érhetők el.

| Mező | Leírás |
|---|---|
| Bérelhető | Ez az érték jelzi, hogy a szállítókonténer bérelt szállítókonténer-e. A bérletköltségek a bérelt konténerekhez társíthatóak. |
| Átalakítva bérelhető típusúvá | Ez az érték jelzi, hogy a szállítókonténer bérelt szállítókonténerré lett-e átalakítva. A bérletköltségek a bérelt konténerekhez társíthatóak. |
| Eredeti út | Ha a szállítókonténert egy új hajóútra helyezték át, az eredeti hajóút. |
| Felhasználva | Ezt a rekordot használja annak rögzítéséhez, hogy bérelt szállítókonténer van-e használatban. Ez csak tájékoztatásra szolgál. |
| Várható berakodási dátum | Az a dátum, amikor a szállítókonténert várhatóan megrakodják az árukkal. |
| Saját sorozatszám | Adja meg a saját vállalata által a szállítókonténerhez belsőleg használt sorozatszámot. |
| Szállítmányozó vállalat sorozatszáma | Adja meg a szállítmányozó vállalat vagy ügynök által a szállítókonténerhez megadott sorozatszámot. |
| Vizsgálati tanúsítvány alkalmazásának dátuma | Az a dátum, amikor a szállítókonténerre vonatkozó vizsgálatot kértek. |
| Vizsgálati tanúsítvány beérkezésének dátuma | A dátum, amikor a vizsgálati tanúsítványt megkapták. |
| Vizsgálati tanúsítvány lejáratának dátuma | A dátum, amikor a vizsgálati tanúsítvány lejár. |
| Vizsgálati tanúsítvány száma | A vizsgálatot követően kiállított tanúsítvány tanúsítványszáma. |

## <a name="lines-view"></a>Sorok nézet

A **Sorok** nézet megnyitásához nyisson meg egy szállítókonténert, majd válassza a szállítókonténer fejlécének jobb felső részén található **Sorok** lapot.

### <a name="information-on-the-shipping-container-fasttab"></a>Információ a Szállítókonténer gyorslapon

A **Sorok** nézet **Szállítókonténer** gyorslapja a levéladatait jeleníti meg. A legtöbb ilyen információ a **fejlécnézetben** is megjelenik, a jelen cikk korábbi leírásának megfelelő módon.

### <a name="information-and-buttons-on-the-lines-fasttab"></a>A Sorok gyorslap információi és gombjai

A **Sorok** nézet **Sorok** gyorslapja az aktuális szállítókonténerbe foglalt teljes vagy részleges beszerzésirendelés-sorok részletes adatait jeleníti meg.

A következő táblázat a **Sorok** nézet **Sorok** gyorslapján elérhető gombok leírását tartalmazza.

| Gomb | Leírás |
|---|---|
| Eltávolítás | A kiválasztott beszerzésirendelés-sor eltávolítása az hajóútról. |
| Készlet \> Tranzakciók | A kiválasztott beszerzésirendelés-sor készlettranzakcióinak megtekintése. Ne feledje, hogy ha úton lévő árukat használ, akkor az eredeti rendelés és az úton lévő áruk rendelései is megjelennek. |
| Készlet \> Dimenziók megjelenítése | Egy párbeszédpanel megnyitása, ahol kiválaszthatja a megtekintett tranzakciókhoz megjelenő készletdimenziókat. |
| Frissítés | A kiválasztott beszerzésirendelés-sor sormennyiségével, súlyával vagy térfogatával kapcsolatos adatok frissítése. |

### <a name="information-on-the-lines-details-fasttab"></a>Információk a Sorok részletei gyorslapon

A **Sorok** nézetében található **Sorok részletei** gyorslap további részleteket jelenít meg a **Sorok** gyorslapon jelenleg kiválasztott beszerzésirendelés-sorról.
