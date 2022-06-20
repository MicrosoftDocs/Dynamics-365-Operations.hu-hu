---
title: Készletláthatóság alkalmazás
description: Ez a cikk a Készlet láthatósága alkalmazás használatát ismerteti.
author: yufeihuang
ms.date: 05/27/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: db158e3b6ae76f69149db04096f99d3dc4251146
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8895757"
---
# <a name="use-the-inventory-visibility-app"></a>Az Inventory Visibility alkalmazás használata

[!include [banner](../includes/banner.md)]


Ez a cikk a Készlet láthatósága alkalmazás használatát ismerteti.

A Készletláthatóság modellvezérelt alkalmazást biztosít a vizualizációhoz. Az alkalmazás három oldalt tartalmaz: **Konfiguráció**, **Üzemeltetési láthatóság** és **Készlet-összefoglaló**. A következő jellemzőkkel rendelkezik:

- Felhasználói felületet (UI) biztosít a kézi konfigurációhoz és a lágy foglalások konfigurálásához.
- Támogatja a különböző dimenziókombinációk valós idejű készletlekérdezéseit.
- Felhasználói felületet biztosít a foglalási kérelmek feladásához.
- Egyénre szabott nézetet nyújt a termékek készletéről, az összes dimenzióval együtt.

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

Amikor kiválasztja az **Kézi lekérdezés** lapot, a rendszer lekéri az Ön hitelesítő adatait, hogy megkapja a Bearer tokent, amely a Készletláthatósági szolgáltatás lekérdezéséhez szükséges. A **BearerToken** mezőbe egyszerűen beillesztheti a Bearer tokent, és bezárhatja a párbeszédpanelt. Ezután feltehet egy kézhez kapott lekérdezési kérelmet.

Ha a **BearerToken** mezőbe be kell illesztenie egy újat, ha a BearerToken jelszó érvénytelen vagy lejárt. Adja meg a megfelelő **ügyfél-azonosító**, **bérlőazonosító** és **ügyféltitok** értékeket, majd válassza a **Frissítés** lehetőséget. A rendszer automatikusan kap egy új, érvényes bearer tokent.

Kézi lekérdezés feladásához adja meg a lekérdezést a kérés törzsében. Használja a [lekérdezésben leírt mintát a post módszer használatával](inventory-visibility-api.md#query-with-post-method).

![Kézi lekérdezés beállításai](media/inventory-visibility-query-settings.png "Kézi lekérdezés beállításai")

### <a name="reservation-posting"></a>Foglalási feladás

Használja a **Foglalások közzététele** lapot a foglalási kérelem feladásához. Mielőtt foglalási kérelmet adhatna fel, be kell kapcsolnia az *OnHandReservation* funkciót. A funkcióval kapcsolatos további információkért lásd a [Készletláthatósági fenntartások](inventory-visibility-reservations.md) című részt.

A foglalási kérelem elküldéséhez meg kell adnia egy értéket a kérelem törzsében. Használja az [Egy foglalási esemény létrehozása](inventory-visibility-api.md#create-one-reservation-event) című fejezetben leírt mintát. Ezután válassza a **Feladás** menüpontot. A kérelemre adott válasz részleteinek megtekintéséhez válassza a **Részletek megjelenítése** lehetőséget. A `reservationId` értéket a válasz adataiból is lekérdezheti.

## <a name="inventory-summary"></a><a name="inventory-summary"></a>Készlet-összesítő

A **Készletösszesítő** a *Készlet OnHand Sum Entitás* testreszabott nézete. A termékek készlet összesítését az összes dimenzióval együtt biztosítja. A készletösszegzési adatokat a rendszer rendszeresen szinkronizálja a Készlet láthatósága alapján 15 percenként. A Készletösszegzés **lapon** az adatok a Funkciókezelés lapon be kell kapcsolniuk az *OnHandMostSpecificBackgroundService* **szolgáltatást**, **és ki kell választani a Konfiguráció frissítése lehetőséget**.

> [!NOTE]
> Az *OnHandMostSpecificBackgroundService* szolgáltatás csak a funkció bekapcsolása után történt, az adott terméken végrehajtott módosításokat követi nyomon. A szolgáltatás bekapcsolása óta nem módosult termékek adatai nem szinkronizálódnak a készletszolgáltatás gyorsítótára és a környezet Dataverse között. Ha a **Készletösszegző** lap nem mutatja az összes várt aktuális készletinformációt, **akkor menjen a Készletkezelés > A** Készlet láthatósága integrációval >, tiltsa le a kötegelt feladatot, és adja újra. Ezzel meg fogja tenni a kezdeti küldést, *és* az összes adat szinkronizálva lesz az aktuális készlet összege entitással a következő 15 perc múlva. Ha használni szeretné ezt a funkciót, **ajánlott be kapcsolni, mielőtt bármilyen aktuális készletváltozást hoz létre, és engedélyezze a Készlet láthatósága integráció** kötegelt feladatot.

A Dataverse által biztosított **Speciális szűrő** használatával létrehozhat egy olyan személyes nézetet, amely az Ön számára fontos sorokat mutatja. A fejlett szűrési lehetőségekkel a nézetek széles skáláját hozhatja létre, az egyszerűtől az összetettig. Lehetővé teszik továbbá, hogy csoportosított és egymásba ágyazott feltételeket adjon a szűrőkhöz. Ha többet szeretne megtudni a **Speciális szűrő** használatáról, lásd: [Személyes nézetek szerkesztése vagy létrehozása a speciális rácsszűrők használatával](/powerapps/user/grid-filters-advanced).

A testreszabott nézet tetején három mező található: **Alapértelmezett dimenzió**, **Egyéni dimenzió** és **Méret**. Ezekkel a mezőkkel szabályozhatja, hogy mely oszlopok legyenek láthatóak.

Kiválaszthatja az oszlopfejlécet az aktuális eredmény szűréséhez vagy rendezéséhez.

A testreszabott nézet alján olyan információk jelennek meg, mint például „50 rekord (29 kiválasztott)” vagy „50 rekord”. Ez az információ a **Speciális szűrő** eredményéből jelenleg betöltött rekordokra vonatkozik. A „29 kiválasztott” szöveg a betöltött rekordok oszlopfejlécszűrőjének használatával kiválasztott rekordok számára utal.

A nézet alján található a **Továbbiak betöltése** gomb, amellyel további rekordokat tölthet be a Dataverse rendszerből. A betöltött rekordok alapértelmezett száma 50. Ha a **Továbbiak betöltése** lehetőséget választja, a következő 1000 elérhető rekord kerül betöltésre a nézetbe. A **Továbbiak betöltése** gombon megjelenő szám a jelenleg betöltött rekordokat és a **Speciális szűrő** eredményének összes rekordját jelzi.

![Készlet-összesítő](media/inventory-visibility-onhand-list.png "Készlet-összesítő")
