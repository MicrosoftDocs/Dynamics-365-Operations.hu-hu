---
title: Többcsatornás speciális automatikus költségek
description: Ez a témakör a Commerce csatornarendelések egyéb rendelési költségeinek speciális automatikus díjak funkcióval való kezelésére nyújt lehetőségeket.
author: hhainesms
ms.date: 03/24/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: global
ms.author: hhaines
ms.search.validFrom: ''
ms.dyn365.ops.version: 10
ms.custom: ''
ms.assetid: ''
ms.search.industry: Retail
ms.search.form: ''
ms.openlocfilehash: d44bc4ef61341c394b627ddbe10768d2ddf98de0
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9292705"
---
# <a name="omni-channel-advanced-auto-charges"></a>Többcsatornás speciális automatikus költségek

[!include [banner](includes/banner.md)]

Ez a cikk a Dynamics 365 for Retail 10.0-s verzióban elérhető automatikus díjak speciális funkcióinak konfigurálásjával és telepítéssel kapcsolatban tartalmaz tájékoztatást.

Ha a speciális automatikus költségek funkciók engedélyezve vannak, akkor az összes támogatott Commerce-csatornában (pénztár (POS), hívásközpont, és az interneten keresztül) kihasználhatja az [automatikus költségek](/dynamics365/unified-operations/retail/configure-call-center-delivery#define-charges-for-delivery-services) konfigurációk előnyeit, amelyeket a fejléc- és sorszintű kapcsolódó költségekre vonatkozóan meghatároztak az ERP-alkalmazásban.

A Retail 10.0 verzió előtti kiadásokban az [automatikus költség](/dynamics365/unified-operations/retail/configure-call-center-delivery#define-charges-for-delivery-services) konfigurációi csak az elektronikus kereskedelmi és a hívásközponti csatornákban létrehozott rendelések számára hozzáférhetők. A 10.0 és a későbbi verziókban a pénztár által létrehozott rendelések is használhatják az automatikus költségek konfigurációit. Ezzel a módszerrel a extra vegyes költségek szisztematikusan hozzáadhatók az értékesítési tranzakciókhoz.

A 10.0-s verzió előtti kiadások használata esetén a pénztárfelhasználót a rendszer felkéri arra, hogy manuálisan adja meg a szállítási díjat egy „összes szállítása” vagy „kiválasztottak szállítása” pénztártranzakció létrehozása során. Míg az alkalmazás vegyes költségekre vonatkozó lehetőségei a költségek rendelésben való leírásával kapcsolatban használhatók, ezek nem nyújtanak szisztematikus számítást – a számítás a felhasználó által beírt adatokon alapul a költségek értékek meghatározásakor. A költségeket csak egyszeri „szállítással” kapcsolatos költségkóddal lehet hozzáadni, és a létrehozás után nem lehet egyszerűen szerkeszteni és módosítani őket a pénztárban.

Szállítási költségek hozzáadására a kézi beavatkozások használata továbbra is elérhető a 10.0 és újabb verziókban. Ha a szervezet nem engedélyezi a **Speciális automatikus költségek** paramétert, a pénztár felkérései a költségek manuális bevitelére változatlanok maradnak.

A speciális automatikus költségek funkcióval a POS-felhasználó számításokat végezhet bármely meghatározott vegyes költséggel az automatikus költségek beállítási táblái alapján. Ezenkívül a felhasználók képesek lesznek további költségek és díjak korlátlan számok hozzáadására vagy szerkesztésére bármelyik pénztári értékesítési tranzakcióhoz fejléc- vagy sorszinten (átvétel és fizetés helyben vagy vevői rendelés esetén).

## <a name="enable-advanced-auto-charges"></a>Speciális automatikus költségek engedélyezése

A **Retail és Commerce \> Központ beállítása \> Paraméterek \> Commerce paraméterek** oldalon lépjen a **Vevői rendelések** lapra. A **Költségek** gyorslapon állítsa a **Speciális automatikus költségek használata** beállítást **Igen** értékre.

![Speciális automatikus költségek paraméter.](media/advancedchargesparameter.png)

Ha a speciális automatikus költségek engedélyezve vannak, a felhasználókat már nem szólítja fel a rendszer, hogy manuálisan adja meg a POS terminálon a szállítási költséget összes szállítása vagy kiválasztottak szállítása típusú vevői rendelés létrehozásakor. A pénztár rendelési költségeket a rendszer szisztematikusan kiszámítja és hozzáadja a pénztártranzakcióhoz (ha megtalálható a megfelelő automatikus költségek tábla, amely megfelel a létrehozott rendelés feltételének). A felhasználók hozzáadhatnak vagy karbantarthatnak fejléc- vagy sorszintű költségeket manuálisan az újonnan hozzáadott pénztárműveleteken keresztül, amelyeket hozzá lehet adni a pénztár képernyő-elrendezésekhez.

Ha speciális automatikus költségek engedélyezve vannak, a meglévő **Commerce-paraméterek**, amelyek a **Szállítási költségek kódja** és **Szállítási költségek visszatérítése** pontokhoz tartoznak, nem használatosak. Ezek a paraméterek csak akkor érvényesek, ha a **Speciális automatikus költségek használata** paraméter értéke **Nem**.

Mielőtt engedélyezi ezt a funkciót, győződjön meg róla, hogy tesztelte és képezte az alkalmazottakat, mivel az engedélyezett funkció megváltoztatja a szállítási és egyéb költségek kiszámításának és a pénztár értékesítési rendeléseinek hozzáadásának folyamatát. Ellenőrizze, hogy megérti a folyamat hatását a tranzakciók létrehozására a pénztárból. Hívásközpontból származó és e-kereskedelmi rendelések esetén a speciális automatikus költségek engedélyezésének hatása minimális. Hívásközpont és az elektronikus kereskedelmi alkalmazások továbbra is ugyanúgy viselkednek majd, ahogy korábban tették az automatikus költségekre vonatkozó táblákhoz kapcsolódó extra rendelési díjak kiszámításához. Hívásközpont csatorna felhasználói továbbra is manuálisan szerkeszthetik a rendszer által kiszámított automatikus költségeket a fejléc vagy sorok szintjén, vagy manuális hozzáadhatnak a további vegyes költségeket a fejléc vagy sorok szintjén.

## <a name="add-pos-operations"></a>Pénztárműveletek hozzádása

Ahhoz, hogy a speciális automatikus költségek megfelelően működjenek a pénztáralkalmazás környezetében, új pénztárműveleteket adtunk hozzá. Ezeket a műveleteket hozzá kell adnia a [Pénztár képernyő-elrendezései](/dynamics365/unified-operations/retail/pos-screen-layouts) részhez, és telepítenie kell a pénztár eszközeihez a speciális automatikus költségek telepítésével együtt. Ha ezek a műveletek hozzáadása nem történik meg, a felhasználók nem tudják majd kezelni vagy karbantartani a vegyes költségeket a pénztártranzakciókon, és nem lesz lehetőségük kiigazítani vagy módosítani a rendszer által számított, automatikus költségek konfiguráción alapuló költségértékeket. Legalább ajánlott, hogy telepítse a **Költségek kezelése** műveletet a pénztár elrendezéséhez.

Az új műveletek alább láthatók.

- **142 – Költségek kezelése** – Használja ezt a műveletet arra, hogy engedélyezze a pénztár felhasználóknak a vegyes költségek megjelenítését és szerkesztését a pénztártranzakcióknál, amelyeket vagy kézzel vagy rendszer által kerültek hozzáadásra automatikus költségek számításain keresztül.
- **141 – Fejlécköltségek hozzáadása** – Használja ezt a műveletet arra, hogy lehetőséget adjon a felhasználónak a fejléc szintű vegyes költségek manuális hozzáadására a pénztár értékesítési tranzakcióhoz (és válassza ki a használandó költségkódot).
- **140 – Sorköltségek hozzáadása** – Használja ezt a műveletet arra, hogy lehetőséget adjon a felhasználónak a sorszintű vegyes költségek manuális hozzáadására a pénztár értékesítési tranzakció sorához (és válassza ki a használandó költségkódot).
- **143 – Költségek újraszámolása** – A művelet segítségével az értékesítési tranzakcióhoz a költségek teljes újraszámítását végrehajthatja. Bármely korábbi felhasználó által felülbírált automatikus költségek újra lesznek számítva a bevásárlókocsi aktuális konfigurációja alapján.

Mint minden pénztárműveletnál, a biztonsági konfigurációk beállíthatók úgy, hogy vezetői jóváhagyást igényeljenek a művelet végrehajtásához.

Fontos megjegyezni, hogy a fent felsorolt POS-műveletek a POS-elrendezés akkor is hozzáadhatók, ha a **Speciális automatikus költségek használat** paraméter le van tiltva. Ebben az esetben a szervezetek még további előnyöket élvezhetnek, azáltal hogy a manuálisan hozzáadott díjakat megtekinthetik és szerkesztheti a **Költségek kezelése** művelettel. Felhasználók használhatják a **Fejlécköltségek hozzáadása** és **Sorköltségek hozzáadása** műveleteket POS-tranzakciókhoz, még akkor is, ha a **Speciális automatikus költségek használata** paraméter le van tiltva. A **Költségek újraszámolása** művelet kevesebb funkcióval rendelkezik, ha a **Speciális automatikus költésgek használata** le van tiltva. Ebben a szituációban semmi nem lesz újraszámítva, és a manuálisan hozzáadott díjak a tranzakcióhoz visszaállnak $0.00 értékre.

## <a name="use-case-examples"></a>Használati eset példái

Ebben a szakaszban használati eseteket mutatunk be, amellyel jobban megértheti az automatikus költségek és vegyes költségek beállítását és használatát a csatorna rendelései vonatkozásában. Az alábbi példák bemutatják az alkalmazás működését, amikor a **Speciális automatikus díjak használata** paraméter engedélyezve van.

### <a name="auto-charges-header-charges-example"></a>Automatikus költségek fejlécköltségek példa

#### <a name="use-case-scenario"></a>Használati eset forgatókönyve

A kiskereskedő szeretne automatikusan költségeket hozzáadni a szállításhoz a bármely Commerce-csatornában létrehozott tranzakciók esetén, ahol a termékeket el kell szállítani a vevőhöz. A kiskereskedő kínál két szállítási módot: földi és légi. Ha a vevő a Földi szállítást választja és a rendelés értéke kisebb, mint 100 USD, a kiskereskedő 10 USD fuvardíjat akar a vevőre terhelni. Ha a rendelés értéke több mint 100 USD, és a vevő a földi szállítás mellet dönt, a vevőnek nem számolnak fel extra szállítási díjakat. Ha a vevő légi módot választ az összes megrendeléshez, összértékétől függetlenül, 20 USD szállítási díjat kell felszámítani.

#### <a name="setup-and-configuration"></a>Beállítás és konfigurálás

Ebben az esetben a két automatikus költségekre vonatkozó tábla konfigurációja szükséges.

Ugorjon a **Kinnlevőségek \> Költségek beállítása \> Automatikus költségek** pontra.

Két különböző fejléc szintű automatikus költséget konfiguráljon. Állítson be egyet a „földi szállítási módhoz” és egyet a „légi szállítási módhoz” Ebben az esetben azokat az "Összes vevő" használatára kell konfigurálni.

A földi szállítási költségekhez az **Automatikus költségek** oldal sorokat tartalmazó szakaszában határozza meg a költséget 10 USD-nak, amelyeket a 0,01 és 100 dollár közti rendelésekhez alkalmaz. Hozzon létre egy másik költségek sort, ahol jelzi, hogy a 100,01 USD feletti rendeléseknek nincs költsége.

![Példa két automatikus költség táblára.](media/headerchargesexample.png)

A légi szállítási költségekhez az Automatikus költségek képernyő sorokat tartalmazó szakaszában határozza meg a költséget 20 USD-nak, amelyeket mindent rendeléshez alkalmaz (0,01 és 9 999 999 USD közti érték esetén).

Küldje el a módosításokat a Commerce Scale Unit/csatorna-adatbázishoz, hogy a pénztár használhassa őket a **1040 elosztási ütemezés** feladat futtatásával.

#### <a name="sales-processing-for-this-scenario"></a>Értékesítés feldolgozása ebben az esetben

A fenti konfigurációs lépések végrehajtása és a módosítások csatorna-adatbázisra alkalmazása után, bármely vevői rendelés vagy értékesítési tranzakció, amelyet a pénztárban, hívásközpontban, vagy elektronikus kereskedelmi csatornákban hoztak létre, amelyeknél a fejlécben beállították a földi vagy légi szállítási módot, használja ezeket a költségeket és automatikusan hozzáadja őket az értékesítéshez.

Ekkor minden olyan értékesítési tranzakcióra vonatkoznak a költségek, amelyeket a szállítási módokat használó jogi személyen belül létrehoztak, mivel nincs olyan funkció, amellyel az automatikus költségek konfigurációt csak egy adott értékesítési csatornára alkalmazzanak.

A POS és az elektronikus kereskedelem eseteiben,mivel ezeketn a rendeléseken nincs pontosan meghatározott „fejléc”, a fejléc szintű költségek csak akkor érvényesek, ha a tranzakció összes értékesítési sorához pontosan ugyanaz a szállítási mód van beállítva. Ha a pénztár vagy elektronikus kereskedelem által létrehozott tranzakciók esetén „vegyes teljesítési módok” vannak, csak sorszintű automatikus díjakat fog a rendszer figyelembe venni és alkalmazni.

A hívásközpont helyzeteinél a felhasználó rendelkezik hatalommal a szállítási mód beállítására a rendelés fejlécében, ezért fejléc szintű költségek vonatkoznak ezekre a rendelésekre, akkor is, ha az egyes értékesítési sorok különböző szállítási mód használatára vannak beállítva. A hívásközpont rendelések fejléc szintű költségei mindig a szállítási mód alapján történik, amely az értékesítési rendelés fejlécének szintjén meg van határozva.

### <a name="auto-charges-line-charges-example"></a>Automatikus költségek sorköltségek példa

#### <a name="use-case-scenario"></a>Használati eset forgatókönyve 

A kiskereskedő szeretne hozzáadni egy extra díjat a vevőnek a beállítási díjakra, amikor a vevő egy bizonyos típusú számítógépet szerez be. Ezen a számítógépen további nem választható beállítási műveletre van szükség, amelyet a kiskereskedő hajt végre a vevőnek. A kiskereskedő tájékoztatta vevőket, hogy ezért a beállításért járulékos díj lesz. A kiskereskedő a díjjal kapcsolatos költségeket a termék eladási árától külön kívánja kezelni pénzügyi jelentési célok miatt. Ezen számítógép bármely csatornán való megvásárlásakor a vevőnek 19,99 USD beállítási díjat kell fizetnie.

#### <a name="setup-and-configuration"></a>Beállítás és konfigurálás

Ebben az esetben egy sorszintű automatikus költségekre vonatkozó tábla konfigurációja szükséges.

Ugorjon a **Kinnlevőségek \> Költségek beállítása \> Automatikus költségek** pontra.

Állítsa a **Szint** legördülő menüt **Sor** értékre, és hozzon létre egy új automatikus költségek rekordot az összes vevőre és az adott termékre vagy termékcsoportra vonatkozóan, ahol a beállítási díjakat kell fizetnie.

![Példa egy sor szintű automatikus költség táblára.](media/linechargesexample.png)

Küldje el a díjakat a Commerce Scale Unit/csatorna-adatbázishoz, hogy a pénztár használhassa őket a **1040 elosztási ütemezés** feladat futtatásával.

#### <a name="sales-processing-for-this-scenario"></a>Értékesítés feldolgozása ebben az esetben

A fenti konfigurációs lépések végrehajtása és a módosítások csatorna-adatbázisra alkalmazása után, bármely vevői rendelés vagy értékesítési tranzakció, amelyet a pénztárban, hívásközpontban, vagy elektronikus kereskedelmi csatornákban hoztak létre, amelyeknél az adott cikk szerepel a rendelésben, egy sorszintű költség rendelés végösszegéhez való szisztematikus hozzáadását kezdeményezi.

Ekkor a költségek minden olyan értékesítési sorra vonatkoznak a költségek, amely megfelel az adott jogi személyen belül a sorszintű automatikus költségek konfigurációjának, mivel nincs olyan funkció, amellyel a sorszintű automatikus költségeknek csak egy bizonyos értékesítési csatornára való alkalmazását szabályozzák.

### <a name="manual-header-charges-example"></a>Manuális fejlécköltségek példa

#### <a name="use-case-scenario-description"></a>Használati eset forgatókönyv leírása

A kiskereskedő kivételt tett a jellemző folyamatokban, amikor termékek speciális házhozszállítását ajánlotta a vevőknek, aki termékeket rendelt az áruházban. A kiskereskedő és a vevő megállapodtak, hogy a vevő kifizet további 25 USD kezelési díjat erre a szolgáltatásra. A rendelés átvevőjének hozzá kell adnia ezt a díjat a tranzakcióhoz. Mivel a díj egy általános díj, és nem kapcsolódik egyetlen termékhez sem a rendelésen, fejlécköltséget használnak.

#### <a name="setup-and-configuration"></a>Beállítás és konfigurálás

Győződjön meg róla, hogy az ebben az esetben használandó költségkód megfelelően van beállítva: nyissa meg a **Kinnlevőségek \> Költségek beállítása \> Költségek** lapot az esethez megfelelő költségkód meghatározásához.

![Költségek példa.](media/chargesexample.png)

Ha a költséget „szállításhoz” kapcsolódó költségként kell figyelembe venni, szállítási engedmény vagy promóció céljából, a költségkód **Szállítási költség** beállítását állítsa **Igen** értékre. Ha ezt a költséget jogosult a pénztáralkalmazásban a rendszer egy visszáru-tranzakció feldolgozása során szisztematikusan visszatéríteni, állítsa a **Visszatéríthető** beállítást **Igen** értékre. A **Visszatéríthető** jelző csak akkor alkalmazható, amikor a **Speciális automatikus költségek használata** paraméter értéke **Igen**.

Küldje el a díjakat a Commerce Scale Unit/csatorna-adatbázishoz, hogy a pénztár használhassa őket a **1040 elosztási ütemezés** feladat futtatásával.

A **Fejlécdíj hozzáadása** műveletet meg kell adni a [POS képernyő-elrendezés](/dynamics365/unified-operations/retail/pos-screen-layouts) részben úgy, hogy a felhasználó számára a pénztárból elérhető gomb lehívható ez a művelet (141-es művelet). A képernyő-elrendezés módosításait meg kell osztani a csatornán, valamint az elosztási ütemezés funkción.

#### <a name="sales-processing-of-manual-header-charges"></a>Manuális fejlécköltségek értékesítési feldolgozása

A forgatókönyv végrehajtásához a pénztár alkalmazásban a pénztár felhasználónak létre kell hoznia szokásos módon az értékesítési tranzakciót, a termékek és egyéb konfigurációk hozzáadásával az értékesítéshez. A fizetés begyűjtése előtt a felhasználónak végre kell hajtania a **Fejlécköltség hozzáadása** műveletet, amely figyelmezteti a felhasználót a költségkód kiválasztására és a költségértékek megadására. Ha a felhasználó befejezi a folyamatot, a költség hozzáadódik az értékesítési rendeléshez fejléc szintű díjként.

Ez a folyamat alkalmazható a hívásközpontban a meglévő **Költségek** funkcióval, amely az **Értékesítés** lapon található az eszköztáron. A **Költségek karbantartása** oldalon a felhasználó hozzáadhat egy új költségsort a rendelés fejlécéhez.

### <a name="manual-line-charges-example"></a>Manuális sorköltségek példa

#### <a name="use-case-scenario"></a>Használati eset forgatókönyve

A vevő kérte, hogy az értékelési rendelésen két cikk az ötből kapjon ajándékcsomagolást. A kiskereskedő ezt a nem kötelező szolgáltatást cikkenként 2 USD díjért nyújtja. A rendelés átvevőjének hozzá kell adnia ezeket a díjat az ajándékcsomagolást kapó cikkekhez.

#### <a name="setup-and-configuration"></a>Beállítás és konfigurálás

Győződjön meg róla, hogy az ebben az esetben használandó költségkód megfelelően van beállítva: nyissa meg a **Kinnlevőségek \> Költségek beállítása \> Költségek** lapot az esethez megfelelő költségkód meghatározásához.

Ha a költséget „szállításhoz” kapcsolódó költségként kell figyelembe venni, szállítási engedmény vagy promóció céljából, a költségkód **Szállítási költség** beállítását állítsa **Igen** értékre. Ha ezt a költséget jogosult a pénztáralkalmazásban a rendszer egy visszáru-tranzakció feldolgozása során szisztematikusan visszatéríteni, állítsa a **Visszatéríthető** beállítást **Igen** értékre. A **Visszatéríthető** jelző csak akkor alkalmazható, amikor a **Speciális automatikus költségek használata** paraméter értéke **Igen**.

Küldje el a díjakat a Commerce Scale Unit/csatorna-adatbázishoz, hogy a pénztár használhassa őket a **1040 elosztási ütemezés** feladat futtatásával.

A **Sorköltség hozzáadása** műveletet meg kell adni a [POS képernyő-elrendezés](/dynamics365/unified-operations/retail/pos-screen-layouts) részben úgy, hogy a felhasználó számára a pénztárból elérhető gomb lehívható ez a művelet (140-es művelet). A képernyő-elrendezés módosításait meg kell osztani a csatornán, valamint az elosztási ütemezés funkción.

#### <a name="sales-processing-of-the-manual-line-charge"></a>Manuális sorköltségek értékesítési feldolgozása

A forgatókönyv végrehajtásához a pénztár alkalmazásban a pénztár felhasználónak létre kell hoznia szokásos módon az értékesítési tranzakciót, a termékek és egyéb konfigurációk hozzáadásával az értékesítéshez. A fizetés begyűjtése előtt a felhasználónak ki kell választania a meghatározott sort a pénztárcikkek megjelenített listájából, amire a költségek vonatkoznak, és végre kell hajtania a **Sorköltség hozzáadása** műveletet. A felhasználót a program kéri, hogy válassza ki a költségkódot, és adja meg a költségek értékét. Ha a felhasználó befejezi a folyamatot, a költség hozzákapcsolódik a sorhoz, és hozzáadódik az értékesítési rendeléshez sor szintű költségként. A felhasználó szükség esetén megismételheti a folyamatot, és a tranzakció további cikkének sorához is hozzáadhat sorköltségeket.

Ugyanezt az eljárást lehet alkalmazni a hívásközpontban a „költségek karbantartása” funkcióval, amely a **Pénzügyek** legördülő menü alatt található az **Értékesítésirendelés-sorok** szakaszban az **Értékesítési rendelés** lapon. A beállítás kiválasztásának hatására megnyílik a **Költségek karbantartása** lap, amelyen a felhasználó hozzáadhat egy új sorspecifikus költséget a tranzakcióhoz.

## <a name="additional-features"></a>További szolgáltatások

### <a name="editing-charges-on-a-pos-sales-transaction"></a>Költségek szerkesztése a pénztár értékesítési tranzakcióin

A **Költségek kezelése** műveletet (142) hozzá kell adni a [POS képernyő-elrendezés](/dynamics365/unified-operations/retail/pos-screen-layouts) részhez, így a felhasználó megtekintheti és módosíthatja, vagy felülbírálhatja a rendszer által kiszámított vagy manuálisan létrehozott fejléc vagy sor szintű költségeket. Ha nem adják hozzá a műveletet, a felhasználók nem tudják módosítani a költségek értékét a pénztártranzakción, és nem tudják majd megtekinteni a költségek részleteit, például a költséghez kapcsolt költségkód típusát.

A **Költségek kezelése** lapon a pénztárban a felhasználó megtekintheti a fejléc és a sor szintű költségek részleteit. A felhasználó használhatja az ezen a lapon elérhető **Szerkesztés** funkciót, amellyel módosíthatja a meghatározott költségsorban felszámított összeget. Amikor egy költségsort manuálisan felülbíráltak, a rendszer nem számítja újra szisztematikusan, kivéve, ha a felhasználó elindítja a **Költségek újraszámolása** műveletet.

Ha a **Költség-felülbírálás okkódja** úgy van beállítva a **Commerce paraméterek** beállító oldalon, akkor a rendszer kéri a felhasználót egy okkód megadására, amikor a kölrségek módosulnak a pénztáralkalmazásban.

Ha az okkódot rögzítették a felülírt költségekre, új jelentés érthető el, a felülbírálások áttekintésére és ellenőrzésére. A jelentés itt található: **Retail és Commerce \> Lekérdezések és jelentések \> Költség-felülbírálás előzményei**.

### <a name="refunding-charges-on-a-pos-return-transaction"></a>Költségek visszatérítése pénztár visszáru-tranzakciójában

Ha a **Speciális automatikus költségek használata** paraméter értéke **Igen**, a meglévő **Szállítási költségek visszatérítése** Commerce-paraméter már nem érvényes. Annak jelzésére, hogy a speciális automatikus költségek alkalmazása esetén mely költségeket kell szisztematikusan visszatéríteni a vevőnek, győződjön meg arról, hogy a kapcsolódó költségkódot **Visszatéríthető** értékkel konfigurálta a **Költségkód** beállító oldalon. Győződjön meg arról, hogy a beállításokat szinkronizálta a Commerce csatorna-adatbázisokkal az elosztási ütemezés feldolgozásán keresztül.

> [!TIP]
> Útmutatásért, amely segítséget nyújt annak biztosítására, hogy a sor szintű visszatéríthető költségek számítása a visszaküldött mennyiség alapján történik, [lásd: A visszatéríthető költségek számítása nem a visszaküldött mennyiség alapján történik](/troubleshoot/Refund-charges-miscalculated-for-partial-quantity-returned.md).

### <a name="refunding-charges-on-a-return-order-transaction"></a>Költségek visszatérítése visszárurendelési tranzakcióban

A költségeket nem térítik vissza szisztematikusan a Commerce szolgáltatásban létrehozott **Visszárurendelések** esetén. A felhasználóknak ki kell jelölniük a **Költségek másolása** lehetőséget a **Visszárurendelés** létrehozásakor. Ha a **Költségek másolása** nincs bejelölve, az eredeti értékesítési tranzakció költségeit nem téríti vissza automatikusan. Ha a **Költségek másolása** ki van választva, a rendszer az összes költséget átmásolja a visszárurendelésre, és a felhasználó manuálisan módosíthatja vagy törölheti azokat, amelyeket nem szeretne visszatéríteni. A hívásközpont visszáru-rendelési folyamata jelenleg nem támogat a **Visszatéríthető** a jelzőt a **Költségkód** beállításakor.

### <a name="configuring-pos-receipts-to-show-charges"></a>Pénztárnyugták konfigurálása a költségek mutatására

A következő nyugtaelemeket hozzáadta a rendszer a nyugta sorához és láblécéhez a speciális automatikus költségek funkció támogatásához.

- **Sor szállítási költségei** – Ez a sorszintű elem az olyan specifikus költségkódok összefoglalására használatos, amelyeket az értékesítési sorra alkalmaztak. Itt csak az olyan költségkódok jelennek meg, amelyet **Szállítási** költségként jelöltek meg a **Költségkód** oldalon.
- **Sor egyéb költségei** – Ez a sorszintű elem az olyan nem szállításspecifikus költségkódok összefoglalására használatos, amelyeket az értékesítési sorra alkalmaztak. A **Sor egyéb költségei** a költségkódok, ahol a **Szállítás** jelző a **Költségkód** lapon nincs engedélyezve.
- **Megrendelés szállítási költségeinek részletei** – Ez a láblécszintű elem megjeleníti a rendelésre alkalmazott költségkódok leírásait, amelyeket **Szállítási** költségként jelöltek meg a **Költségkód** beállító oldalon.
- **Rendelés szállítási költségei** – Ezzel a lábléc szintű elemmel a szállítással kapcsolatos költségek dollárértékét jeleníti meg.
- **Megrendelés egyéb költségeinek részletei** – Ez a láblécszintű elem megjeleníti a rendelésre alkalmazott költségkódok leírásait, amelyeket nem szállítással kapcsolatos költségként jelöltek meg.
- **Rendelés egyéb költségei** – Ezzel a lábléc szintű elemmel a nem szállítással kapcsolatos költségek dollárértékét jeleníti meg.

Azt ajánljuk, hogy a szervezet szabadszöveges mezőket is adjon hozzá a nyugta láblécéhez annak érdekében, hogy meghatározza azokat a területeket, ahol a költségeket összefoglalják.

### <a name="preventing-charges-from-being-calculated-until-the-pos-order-is-completed"></a>Megakadályozza, hogy a költségeket kiszámítsák a pénztárrendelés befejezéséig

Előfordulhat, hogy egyes szervezetek szívesebben várnak, amíg a felhasználó befejezte az összes értékesítés hozzáadását a pénztártranzakcióhoz a költségek számítása előtt. Annak megakadályozására, hogy a költségek számítását cikkekként hozzáadják a pénztártranzakciókhoz, kapcsolja be a **Manuális költségszámítás** paramétert az üzlet által használt **Funkcióprofil** oldalán. Ez a paraméter engedélyezése arra kötelezi a pénztárfelhasználót, hogy a **Teljes összeg kiszámítása** műveletet használja, amikor a termékek hozzáadása a pénztártranzakcióhoz befejeződött. A **Teljes összeg kiszámítása** művelet majd elindítja a rendelés fejlécére vagy megfelelő sorokra vonatkozó automatikus díjak számítását.

### <a name="charges-override-reports"></a>Költség-felülbírálási jelentések

Ha felhasználó manuálisan felülírja a számított költségeket vagy manuálisan ad hozzá költséget a tranzakcióhoz, ez az adatot lesz elérhető ellenőrzésre a **Költség-felülbírálás előzményei** jelentésben. A jelentés itt érhető el: **Retail és Commerce \> Lekérdezések és jelentések \> Költség-felülbírálás előzményei**. Fontos megjegyezni, hogy a jelentéshez szükséges adatokat importálása a csatorna-adatbázisból történik a központba „P” elosztási munkaütemezésen keresztül. Emiatt a POS-ban végrehajtott felülbírálások adatait nem lesznek azonnal elérhetők a jelentésben mindaddig, amíg a feladat fel nincs töltve az üzlet tranzakciós adatokaiba a központban.

## <a name="additional-resources"></a>További erőforrások

[Automatikus költségek csatorna szerinti engedélyezése és konfigurálása](auto-charges-by-channel.md)

[Fejlécköltségek arányosítása az egyező értékesítési sorokhoz](pro-rate-charges-matching-lines.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
