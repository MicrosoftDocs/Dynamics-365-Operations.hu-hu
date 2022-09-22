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
ms.openlocfilehash: 674adb70cc4372a8c5ca8c75ed3ef840d8ec7b79
ms.sourcegitcommit: d2046cad5de570e6302a4390b41881a7ecb12e26
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/15/2022
ms.locfileid: "9520864"
---
# <a name="use-the-inventory-visibility-app"></a>A Készletláthatóság alkalmazás használata

[!include [banner](../includes/banner.md)]

Ez a cikk a Készlet láthatósága alkalmazás használatát ismerteti.

A Készletláthatóság modellvezérelt alkalmazást biztosít a vizualizációhoz. Az alkalmazás három oldalt tartalmaz: **Konfiguráció**, **Üzemeltetési láthatóság** és **Készlet-összefoglaló**. A következő jellemzőkkel rendelkezik:

- Felhasználói felületet (UI) biztosít a kézi konfigurációhoz és a lágy foglalások konfigurálásához.
- Támogatja a különböző dimenziókombinációk valós idejű készletlekérdezéseit.
- Felhasználói felületet biztosít a foglalási kérelmek feladásához.
- Az aktuális készlet és a dimenziók áttekintését adja a termékekről.
- A termék aktuális készletének listáját, valamint az előre meghatározott dimenziókat tartalmazza.


## <a name="prerequisites"></a>Előfeltételek

Mielőtt elkezdené, telepítse és állítsa be a Készletláthatóság bővítményt a [Készletláthatóság telepítés és beállítása](inventory-visibility-setup.md) című fejezetben leírtak szerint.

## <a name="open-the-inventory-visibility-app"></a>A készletláthatóság alkalmazás megnyitása

A Készletláthatóság alkalmazás megnyitásához jelentkezzen be a Power Apps környezetbe, és nyissa meg a **Készletláthatóság** alkalmazást.

## <a name="configuration"></a><a name="configuration"></a>Konfiguráció

A Készletláthatóság alkalmazás **Konfiguráció** oldala segít a kézi konfiguráció és a lágy foglalási konfiguráció beállításában. A bővítmény telepítése után az alapértelmezett konfiguráció tartalmazza a Microsoft Dynamics 365 Supply Chain Management (a `fno` adatforrás) alapértelmezett beállítását. Az alapértelmezett beállítást felülvizsgálhatja. Ezután az Ön üzleti követelményei és a külső rendszer készletkönyvelési követelményei alapján módosíthatja a konfigurációt, hogy egységesítse a készletváltozások könyvelésének, rendszerezésének és lekérdezésének módját több rendszerben.

A megoldás konfigurálásával kapcsolatos részletes információk itt olvashatók [Készletláthatóság konfigurálása](inventory-visibility-configuration.md).

## <a name="operational-visibility"></a>Operatív láthatóság

Az **Operatív láthatóság** oldal a különböző dimenziókombinációk alapján egy valós idejű készletlekérdezés eredményeit mutatja be. Ha az *OnHandReservation* funkció be van kapcsolva, akkor az **Operatív láthatóság** oldalról is közzéteheti a foglalási kérelmeket.

### <a name="on-hand-query"></a>Kézi lekérdezés

Az **Kézi lekérdezés** lapon a valós idejű készletlekérdezés eredményei láthatók.

Amikor **megnyitja** **az** Üzemeltetés láthatósága lap Aktuális készlet lekérdezését, a rendszer be kéri a hitelesítő adatait, hogy be tudja szerezni a készlet láthatósági szolgáltatásának lekérdezéséhez szükséges jogkivonatot. A **BearerToken** mezőbe egyszerűen beillesztheti a Bearer tokent, és bezárhatja a párbeszédpanelt. Ezután feltehet egy kézhez kapott lekérdezési kérelmet.

Ha a **BearerToken** mezőbe be kell illesztenie egy újat, ha a BearerToken jelszó érvénytelen vagy lejárt. Adja meg a megfelelő **ügyfél-azonosító**, **bérlőazonosító** és **ügyféltitok** értékeket, majd válassza a **Frissítés** lehetőséget. A rendszer automatikusan kap egy új, érvényes bearer tokent.

Kézi lekérdezés feladásához adja meg a lekérdezést a kérés törzsében. Használja a [lekérdezésben leírt mintát a post módszer használatával](inventory-visibility-api.md#query-with-post-method).

![Kézi lekérdezés beállításai](media/inventory-visibility-query-settings.png "Kézi lekérdezés beállításai")

### <a name="reservation-posting"></a>Foglalási feladás

Foglalási **kérések feladására** használja **az Üzemeltetés láthatósága** lap Foglalás feladása lapját. Mielőtt foglalási kérelmet adhatna fel, be kell kapcsolnia az *OnHandReservation* funkciót. Erről a funkcióról és bekapcsolásról a Készlet [láthatósági foglalása nyújt további tájékoztatást](inventory-visibility-reservations.md).

A foglalási kérelem elküldéséhez meg kell adnia egy értéket a kérelem törzsében. Használja az [Egy foglalási esemény létrehozása](inventory-visibility-api.md#create-one-reservation-event) című fejezetben leírt mintát. Ezután válassza a **Feladás** menüpontot. A kérelemre adott válasz részleteinek megtekintéséhez válassza a **Részletek megjelenítése** lehetőséget. A `reservationId` értéket a válasz adataiból is lekérdezheti.

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

## <a name="preload-a-streamlined-on-hand-query"></a><a name="preload-the-inventory-visibility-onhand-query"></a> Racionalizált, előzetes betöltési lekérdezés

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]
<!-- KFM: Preview until further notice -->

Az ellátásilánc-kezelés nagy mennyiségben tárol információkat az aktuális készletről, és sokféle célra elérhetővé teszi azt. Azonban számos napi művelet és külső fél integrációja ezeknek az adatoknak csak egy kis halmazát igényli, és a rendszer mindegyikről történő lekérdezése nagy adathalmazokat eredményezhet, amelyek összeállítása és átvitele sok időt igényel. A Készlet láthatósága szolgáltatás ennek megfelelően rendszeres időközönként beolvasással és tárolja az aktuális készletadatok leegyszerűsített készletét, hogy az optimális információkat folyamatosan elérhetővé tegye. A tárolt aktuális készlet részleteinek szűrése konfigurálható üzleti feltételek alapján történik, így garantálható, hogy csak a leginkább releváns információk is bekerülnek. Mivel a szűrt aktuális készletlistákat helyben tárolják a Készlet láthatósága szolgáltatásban, és rendszeresen frissítik őket, ezért támogatják a gyors elérést, az igény szerinti adatexportációt és a külső rendszerekkel történő leegyszerűsített integrációt.

> [!NOTE]
> A funkció aktuális előnézeti verziója csak olyan előre betöltött eredményeket nyújthat, amelyek tartalmazzák a helyet és a helyet. A funkció végső verziója várhatóan lehetővé teszi más dimenziók kiválasztását az eredmények előzetes betöltése érdekében.

A **készlet láthatósági összefoglaló lapja** nézetet biztosít az *aktuális készletindex lekérdezésének előzetes betöltési eredményei entitáshoz*. A Készletösszegzés *entitástól* *eltérően az aktuális index lekérdezés előzetes betöltési eredményei* entitás tényleges készletlistát biztosít a kiválasztott dimenziókkal együtt a termékekhez. A készlet láthatósága 15 percenként szinkronizálja az előzetesen betöltött összesített adatokat.

A Készlet láthatósági összegzése lap adatainak előzetes megtekintéséhez be kell kapcsolnia az OnHandIndexQueryPreloadBackgroundService **szolgáltatást** a Konfiguráció lap *Funkciókezelés* **·** **lapján, majd ki kell választania a Konfiguráció frissítése lehetőséget (** **lásd még a Készlet láthatóságának konfigurálása).**[...](inventory-visibility-configuration.md)

> [!NOTE]
> *Az OnHandMostSpecificBackgroudService* *szolgáltatáshoz hasonló onHandIndexQueryPreloadBackgroundService szolgáltatás* csak a funkció bekapcsolása után történt tényleges készlet változásait követi nyomon. A szolgáltatás bekapcsolása óta nem módosult termékek adatai nem szinkronizálódnak a készletszolgáltatás gyorsítótára és a környezet Dataverse között. Ha a **Készletösszegző** lap nem mutatja az összes várt aktuális készletinformációt, **akkor menjen a Készletkezelés > A** Készlet láthatósága integrációval >, tiltsa le a kötegelt feladatot, és adja újra. Ezzel meg fogja tenni a kezdeti küldést, *és az összes adat szinkronizálva lesz az elérhető index lekérdezés előzetes* betöltési eredményei entitással a következő 15 perc múlva. Ha használni szeretné ezt a funkciót, **ajánlott be kapcsolni, mielőtt bármilyen aktuális készletváltozást hoz létre, és engedélyezze a Készlet láthatósága integráció** kötegelt feladatot.

## <a name="filter-and-browse-the-inventory-summaries"></a><a name="additional-tip-for-viewing-data"></a> Szűrés és böngészés a készlet összegzésében

A Dataverse által biztosított **Speciális szűrő** használatával létrehozhat egy olyan személyes nézetet, amely az Ön számára fontos sorokat mutatja. A fejlett szűrési lehetőségekkel a nézetek széles skáláját hozhatja létre, az egyszerűtől az összetettig. Lehetővé teszik továbbá, hogy csoportosított és egymásba ágyazott feltételeket adjon a szűrőkhöz. A speciális szűrő használatával kapcsolatos további tudnivalókat lásd [a Személyes nézetek szerkesztése és létrehozása speciális rácsszűrők használatával](/powerapps/user/grid-filters-advanced).

A **Készlet összegző lapja** a rács fölött három mezőt tartalmaz (**Alapértelmezett** dimenzió, **·** **Egyéni** dimenzió és Mérték), amelyek a látható oszlopok szabályozására használhatók. Bármelyik oszlopfejlécet kiválasztva az adott oszlop alapján szűrheti vagy rendezheti az aktuális eredményt. A következő képernyőképen látható a készletösszegzési lapon elérhető dimenzió, szűrés, eredmények száma és "Terhelés több" **mezője**.

![A Készlet összegző lapja.](media/inventory-visibility-onhand-list.png "A Készlet összegző lapja")

Mivel a rendszer előre definiált dimenziókat használ az összegző adatok betöltéséhez, **a** Készlet láthatósága összefoglaló lap a dimenziókkal kapcsolatos oszlopokat jeleníti meg. *A dimenziók nem testreszabhatók&mdash;, mert a rendszer csak az előre betöltött elérhető listák hely- és helydimenzióit támogatja.* A **Készlet láthatósága összefoglaló** **lap** a Készletösszegzés lapon találhatóhoz hasonló szűrőket biztosít, kivéve a dimenziók már ki vannak jelölve. A következő képernyőkép mutatja be a **készlet láthatóságának összefoglaló lapján elérhető szűrési mezőket**.

![A Készlet láthatósága összefoglaló oldal előzetes betöltése](media/inventory-visibility-preload-onhand-list.png "A Készlet láthatósága összefoglaló oldal előzetes betöltése")

A Készlet **láthatósági** **összegzése** és a Készletösszegzési lapok alsó részén olyan információkat találhat, mint például "50 rekord (29 kiválasztott)" vagy "50 rekord". Ez az információ a **Speciális szűrő** eredményéből jelenleg betöltött rekordokra vonatkozik. A „29 kiválasztott” szöveg a betöltött rekordok oszlopfejlécszűrőjének használatával kiválasztott rekordok számára utal. Van még egy Rakomány **több** gomb, amely további rekordok betöltésére használható Dataverse. A betöltött rekordok alapértelmezett száma 50. Ha a Rakomány több **lehetőséget választja**, a következő 1000 elérhető rekord betöltődik a nézetbe. A **Továbbiak betöltése** gombon megjelenő szám a jelenleg betöltött rekordokat és a **Speciális szűrő** eredményének összes rekordját jelzi.
