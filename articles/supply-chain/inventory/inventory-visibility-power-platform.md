---
title: Készletláthatóság alkalmazás
description: Ez a cikk a Készlet láthatósága alkalmazás használatát ismerteti.
author: yufeihuang
ms.date: 09/15/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 9886ddbf0b072283cffd73d4bfdc20835ccb3b7c
ms.sourcegitcommit: 49f8973f0e121eac563876d50bfff00c55344360
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/14/2022
ms.locfileid: "9762700"
---
# <a name="use-the-inventory-visibility-app"></a>A Készletláthatóság alkalmazás használata

[!include [banner](../includes/banner.md)]

Ez a cikk a Készlet láthatósága alkalmazás használatát ismerteti.

A Készletláthatóság modellvezérelt alkalmazást biztosít a vizualizációhoz. Az alkalmazás három oldalt tartalmaz: **Konfiguráció**, **Üzemeltetési láthatóság** és **Készlet-összefoglaló**. A következő jellemzőkkel rendelkezik:

- Felhasználói felületet (UI) biztosít a kézi konfigurációhoz és a lágy foglalások konfigurálásához.
- Támogatja a különböző dimenziókombinációk valós idejű készletlekérdezéseit.
- Felhasználói felületet biztosít a foglalási kérelmek feladásához.
- Az aktuális készlet és a dimenziók áttekintését adja a termékekről.
- Betekent egy nézetet az előre definiált dimenziókkal együtt a termékek aktuális készletlistáról. A cikklistanézet lehet teljes összegzés vagy az előzetesen betöltött eredmény egy adott lekérdezésből.

## <a name="prerequisites"></a>Előfeltételek

Mielőtt elkezdené, telepítse és állítsa be a Készletláthatóság bővítményt a [Készletláthatóság telepítés és beállítása](inventory-visibility-setup.md) című fejezetben leírtak szerint.

## <a name="open-and-authenticate-the-inventory-visibility-app"></a><a name="open-authenticate"></a> A Készlet láthatósága alkalmazás megnyitása és hitelesítése

A Készlet láthatósága alkalmazás megnyitásához és hitelesítéséhez hajtsa végre a következő lépéseket.

1. Jelentkezzen be a környezetbe Power Apps.
1. A Készlet láthatósága **alkalmazás** megnyitása
1. Az Üzemeltetés láthatósága **lap** megnyitása a bal oldali ablaktáblából.
1. Az oldal **tetején** válassza a Beállítások gombot (fogaskerekek szimbólumát).
1. A Beállítások **párbeszédpanelen** adja meg az ügyfélazonosító, **a** bérlőazonosító és az ügyfél titkos azonosítója értékét, **·** **·**[amelyekre a készlet láthatóságának beállításakor és telepítésekor jegyeztek fel.](inventory-visibility-setup.md)
1. Kattintson a **Frissítés** gombra a **Jogkivonat mező** mellett. A rendszer új jogkivonatot hoz létre a megadott információk alapján.

    ![Az idő lekérdezési beállításai.](media/inventory-visibility-query-settings.png "Kézi lekérdezés beállításai")

1. Ha érvényes jogkivonatot kap, zárja be a párbeszédpanelt. A jogkivonat egy idő után lejár. Emiatt időnként frissítenie kell a frissítést, amikor frissítenie kell a konfigurációt, a postai adatokat vagy a lekérdezésadatokat.

## <a name="configure-the-inventory-visibility-app"></a><a name="configuration"></a> A Készlet láthatósága alkalmazás konfigurálása

A **Készlet** láthatósága alkalmazás konfigurációs lapja segít beállítani az általános adatkezelési konfigurációt és funkciókonfigurációt. A bővítmény telepítése után az alapértelmezett konfiguráció tartalmazza a Microsoft Dynamics 365 Supply Chain Management (a `fno` adatforrás) alapértelmezett beállítását. Az alapértelmezett beállítást felülvizsgálhatja. Ezután az üzleti követelmények és a külső rendszer készletfeladási követelményei alapján módosítani lehet a konfigurációt, hogy szabványosítható legyen a készletváltozások feladási, rendszerezhető és lekérdezhető módja a több rendszer között.

A megoldás konfigurálásával kapcsolatos részletes információk itt olvashatók [Készletláthatóság konfigurálása](inventory-visibility-configuration.md).

## <a name="operational-visibility"></a>Operatív láthatóság

Az **Üzemeltetés láthatósága** lap a valós idejű készletlekérdezés, a foglalások feladása és a különböző dimenziókombinációk alapján történő felosztás eredményeit tartalmazza. Ha az *OnHandReservation* szolgáltatás [be](inventory-visibility-configuration.md) van kapcsolva, **a foglalási kéréseket az Üzemeltetés láthatósága lapról is fel lehet** majd függesni.

### <a name="on-hand-query"></a>Kézi lekérdezés

Az **Üzemeltetés láthatósága** lap **Aktuális** készlet lap lehetővé teszi a valós idejű aktuális készlet lekérdezését. Az alábbi lépések szerint állíthatja be és futtathat egy lekérdezést.

1. A Készlet láthatósága **alkalmazás** megnyitása
1. Az Üzemeltetés láthatósága **lap** megnyitása a bal oldali ablaktáblából.
1. Adja meg az **Onhand lekérdezés** lapon **a** lekérdezni kívánt szervezetazonosítót, **·** **telephely**-azonosítót és helyazonosítót.
1. A Termékazonosító **mezőben** adjon meg egy vagy több termékazonosítót, hogy a lekérdezés pontos egyezést adjon meg. Ha üresen hagyja a **Termékazonosító** mezőt, az eredmények az összes terméket a megadott helyen és helyen fogják tartalmazni.
1. Ha részletesebb eredményt (például dimenzióértékek, például szín vagy méret szerint) is meg lehet tekinteni, válassza ki **a csoportosítási dimenziókat a Csoport eredmény szerint mezőben**.
1. Olyan cikkek megkeresése, amelyekhez meghatározott dimenzióérték (például szín = piros), **válassza ki a dimenziót a Dimenziók** szűrése mezőben, majd adjon meg egy dimenzióértéket.
1. Lekérdezés **kiválasztása**. Vagy sikeres (zöld) üzenetet, vagy sikertelen (piros) üzenetet kap. Ha a lekérdezés sikertelen, ellenőrizze a lekérdezési feltételeket, és győződjön meg arról, [hogy a jogkivonat](#open-authenticate) nem járt le.

Az elérhető lekérdezések egy másik módja a közvetlen API-kérések létrehozása. Használhatja az egyiket vagy a (1) `/api/environment/{environmentId}/onhand/indexquery` használhatja `/api/environment/{environmentId}/onhand`. A további tudnivalókat lásd [a Készlet láthatósága nyilvános API-kban](inventory-visibility-api.md).

### <a name="reservation-posting"></a>Foglalási feladás

Foglalási **kérések feladására** használja **az Üzemeltetés láthatósága** lap Foglalás feladása lapját. Mielőtt foglalási kérelmet adhatna fel, be kell kapcsolnia az *OnHandReservation* funkciót. Erről a funkcióról és bekapcsolásról a Készlet [láthatósági foglalása nyújt további tájékoztatást](inventory-visibility-reservations.md).

> [!NOTE]
> Az, hogy a felhasználói felületen egyszerű foglalást lehet-e tenni, lehetővé teszi a funkció tesztelését. Minden egyes soft foglalási kérést tranzakciórendelési sorváltozáshoz kell hozzárendelni (létrehozás, módosítás, törlés stb.). Ezért javasoljuk, hogy csak olyan soft foglalásokat rendeljen el, amelyek utánrendeléshez kapcsolódnak. További információért lásd a [Készletláthatósági foglalások](inventory-visibility-reservations.md) című részt.

Az alábbi lépésekkel a felhasználói felület segítségével fel lehet majd edni az egyszerű foglalási kéréseket.

1. A Készlet láthatósága **alkalmazás** megnyitása
1. Az Üzemeltetés láthatósága **lap** megnyitása a bal oldali ablaktáblából.
1. A Foglalás **feladása** lap **Mennyiség** mezőjében adja meg azt a mennyiséget, amelyből az étét nélkül szeretné lefoglalni.
1. Törölje a negatív **készlet engedélyezése jelölőnégyzetet**, ha meg szeretné akadályozni, hogy a készlet túl lett tartva vagy túl lett foglalva.
1. **Az Operátor mezőben** válassza ki az adatforrást és a fizikai mértéket, amely az előre lefoglalt mennyiségre vonatkozik.
1. Adja meg **a lekérdezni** **kívánt** szervezetazonosítót, telephely-azonosítót **,** **helyazonosítót** és termékazonosító-értékeket.
1. A részletesebb eredmény érdekében válasszon ki egy adatforrást, dimenziókat és dimenzióértékeket.

Az előzetes foglalások fel szintén feledhetőek, ha közvetlen API-kéréseket lehet kérni. Használja az [Egy foglalási esemény létrehozása](inventory-visibility-api.md#create-one-reservation-event) című fejezetben leírt mintát. Ezután válassza a **Feladás** menüpontot. A kérelemre adott válasz részleteinek megtekintéséhez válassza a **Részletek megjelenítése** lehetőséget. A `reservationId` értéket a válasz adataiból is lekérdezheti.

### <a name="allocation"></a>Felosztás

A felosztások felhasználói felületről és API-kból történő kezelésével kapcsolatos tudnivalókat [lásd a Készlet láthatósága készletfelosztásban](inventory-visibility-allocation.md).

## <a name="inventory-summary"></a><a name="inventory-summary"></a>Készlet-összesítő

A **Készletösszegzés** lap a termékekkel és az összes dimenzióval együtt egy készletösszegzést tartalmaz. Az aktuális készlet összege entitás testreszabott *nézete*. A készletösszegzési adatokat a rendszer rendszeres időközönként szinkronizálja a készlet láthatóságával.

A Készletösszegzés **oldal engedélyezéséhez** és a szinkronizálás gyakoriságának beállításához hajtsa végre a következő lépéseket:

1. Nyissa meg a **Konfiguráció** oldalt.
1. Nyissa meg a **Funkciókezelés & Beállítások lapot**.
1. **Az OnHandMostSpecificBackgroundService** szolgáltatás váltása Igen *beállítással*
1. Ha a funkció engedélyezve van, **elérhetővé** válik a **Szolgáltatáskonfiguráció szakasz, és tartalmaz egy sort az OnHandMostSpecificBackgroundService szolgáltatás konfigurálásához**. Ezzel a beállítással megadhatja, hogy milyen gyakorisággal szinkronizálja a rendszer a készletösszegzési adatokat. Az Érték **oszlop** **Fel és Le** **gombjaival** módosíthatja a szinkronizálások közötti időt (akár 5 perc is lehet). Majd válassza a **Mentés** lehetőséget.

    ![Az OnHandMostSpecificBackgroundService beállítása](media/inventory-visibility-ohms-freq.png "Az OnHandMostSpecificBackgroundService beállítása")

1. Az összes **módosítás mentéséhez** válassza a Frissítés konfigurációt.

> [!NOTE]
> Az *OnHandMostSpecificBackgroundService* szolgáltatás csak a funkció bekapcsolása után történt tényleges készlet változásait követi nyomon. A szolgáltatás bekapcsolása óta nem módosult termékek adatai nem szinkronizálódnak a készletszolgáltatás gyorsítótára és a környezet Dataverse között. **Ha** a Készletösszegző lap nem mutatja az összes várt aktuális készletinformációt, nyissa meg az Ellátásilánc-kezelés szakaszt, **nyissa** meg > Készletáttekintő adatok integrálásával > Időszakos feladatok >, tiltsa le a kötegelt feladatot, és adja újra. Ezzel meg fogja tenni a kezdeti küldést, *és* az összes adat szinkronizálva lesz az aktuális készlet összege entitással a következő 15 perc múlva. *Az OnHandMostSpecificBackgroundService* **szolgáltatás** használatához ajánlott az aktuális készleten végrehajtott módosítások létrehozása előtt bekapcsolni, és engedélyezni a Készlet láthatósága integráció kötegelt feladatot.

## <a name="preload-a-streamlined-on-hand-query"></a><a name="preload-streamlined-onhand-query"></a> Racionalizált, előzetes betöltési lekérdezés

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]
<!-- KFM: Preview until further notice -->

Az ellátásilánc-kezelés nagy mennyiségben tárol információkat az aktuális készletről, és sokféle célra elérhetővé teszi azt. Azonban számos napi művelet és külső fél integrációja ezeknek az adatoknak csak egy kis halmazát igényli, és a rendszer mindegyikről történő lekérdezése nagy adathalmazokat eredményezhet, amelyek összeállítása és átvitele sok időt igényel. A Készlet láthatósága szolgáltatás ennek megfelelően rendszeres időközönként beolvasással és tárolja az aktuális készletadatok leegyszerűsített készletét, hogy az optimális információkat folyamatosan elérhetővé tegye. A tárolt aktuális készlet részleteinek szűrése konfigurálható üzleti feltételek alapján történik, így garantálható, hogy csak a leginkább releváns információk is bekerülnek. Mivel a szűrt aktuális készletlistákat helyben tárolják a Készlet láthatósága szolgáltatásban, és rendszeresen frissítik őket, ezért támogatják a gyors elérést, az igény szerinti adatexportációt és a külső rendszerekkel történő leegyszerűsített integrációt.

A **készlet láthatósági összefoglaló lapja** nézetet biztosít az *aktuális készletindex lekérdezésének előzetes betöltési eredményei entitáshoz*. A Készletösszegzés *entitástól* *eltérően az aktuális index lekérdezés előzetes betöltési eredményei* entitás tényleges készletlistát biztosít a kiválasztott dimenziókkal együtt a termékekhez. A készlet láthatósága 15 percenként szinkronizálja az előzetesen betöltött összesített adatokat.

A Készlet láthatósági összegzése lap adatainak előzetes megtekintéséhez be kell kapcsolnia az OnHandIndexQueryPreloadBackgroundService **szolgáltatást** a Konfiguráció lap *Funkciókezelés* **·** **lapján, majd ki kell választania a Konfiguráció frissítése lehetőséget (** **lásd még a Készlet láthatóságának konfigurálása).**[...](inventory-visibility-configuration.md)

> [!NOTE]
> *Az OnHandMostSpecificBackgroudService* *szolgáltatáshoz hasonló onHandIndexQueryPreloadBackgroundService szolgáltatás* csak a funkció bekapcsolása után történt tényleges készlet változásait követi nyomon. A szolgáltatás bekapcsolása óta nem módosult termékek adatai nem szinkronizálódnak a készletszolgáltatás gyorsítótára és a környezet Dataverse között. Ha a **Készletösszegző** lap nem mutatja az összes várt aktuális készletinformációt, **akkor menjen a Készletkezelés > A** Készlet láthatósága integrációval >, tiltsa le a kötegelt feladatot, és adja újra. Ezzel meg fogja tenni a kezdeti küldést, *és az összes adat szinkronizálva lesz az elérhető index lekérdezés előzetes* betöltési eredményei entitással a következő 15 perc múlva. Ha használni szeretné ezt a funkciót, **ajánlott be kapcsolni, mielőtt bármilyen aktuális készletváltozást hoz létre, és engedélyezze a Készlet láthatósága integráció** kötegelt feladatot.

## <a name="filter-and-browse-the-inventory-summaries"></a><a name="additional-tip-for-viewing-data"></a> Szűrés és böngészés a készlet összegzésében

A Dataverse által biztosított **Speciális szűrő** használatával létrehozhat egy olyan személyes nézetet, amely az Ön számára fontos sorokat mutatja. A fejlett szűrési lehetőségekkel a nézetek széles skáláját hozhatja létre, az egyszerűtől az összetettig. Lehetővé teszik továbbá, hogy csoportosított és egymásba ágyazott feltételeket adjon a szűrőkhöz. A speciális szűrő használatával kapcsolatos további tudnivalókat lásd [a Személyes nézetek szerkesztése és létrehozása speciális rácsszűrők használatával](/powerapps/user/grid-filters-advanced).

A **Készlet összegző lapja** a rács fölött három mezőt tartalmaz (**Alapértelmezett** dimenzió, **·** **Egyéni** dimenzió és Mérték), amelyek a látható oszlopok szabályozására használhatók. Bármelyik oszlopfejlécet kiválasztva az adott oszlop alapján szűrheti vagy rendezheti az aktuális eredményt. A következő képernyőképen látható a készletösszegzési lapon elérhető dimenzió, szűrés, eredmények száma és "Terhelés több" **mezője**.

![A Készlet összegző lapja.](media/inventory-visibility-onhand-list.png "A Készlet összegző lapja")

Mivel az összegző adatok betöltésére használt dimenziók előre definiáltak, **a Készlet láthatósága** összefoglaló lap dimenziókkal kapcsolatos oszlopokat jelenít meg. *A dimenziók nem testreszabhatók&mdash;, mert a rendszer csak az előre betöltött elérhető listák hely- és helydimenzióit támogatja.* A **Készlet láthatósága összefoglaló** **lap** a Készletösszegzés lapon találhatóhoz hasonló szűrőket biztosít, kivéve a dimenziók már ki vannak jelölve. A következő képernyőkép mutatja be a **készlet láthatóságának összefoglaló lapján elérhető szűrési mezőket**.

![A Készlet láthatósága összefoglaló oldal előzetes betöltése](media/inventory-visibility-preload-onhand-list.png "A Készlet láthatósága összefoglaló oldal előzetes betöltése")

A Készlet **láthatósági** **összegzése** és a Készletösszegzési lapok alsó részén olyan információkat találhat, mint például "50 rekord (29 kiválasztott)" vagy "50 rekord". Ez az információ a **Speciális szűrő** eredményéből jelenleg betöltött rekordokra vonatkozik. A „29 kiválasztott” szöveg a betöltött rekordok oszlopfejlécszűrőjének használatával kiválasztott rekordok számára utal. Egy További rakomány gomb is **található**, amely további rekordok betöltésére használható a innen Dataverse. A betöltött rekordok alapértelmezett száma 50. Ha a Rakomány több **lehetőséget választja**, a következő 1000 elérhető rekord betöltődik a nézetbe. A **Továbbiak betöltése** gombon megjelenő szám a jelenleg betöltött rekordokat és a **Speciális szűrő** eredményének összes rekordját jelzi.
