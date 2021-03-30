---
title: Értékesítési rendelések hibaelhárítása
description: Ez a témakör azt mutatja be, hogyan lehet javítani az értékesítési rendelések használata során felmerülő problémákat.
author: SmithaNataraj
manager: tfehr
ms.date: 09/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTable, SalesTableListPage, SalesTableListPage_SalesCancelOrder
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-9-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 346ebee598e282abfe01a399793cc259aff3c22d
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5232230"
---
# <a name="troubleshoot-sales-orders"></a>Értékesítési rendelések hibaelhárítása

Ez a témakör azt mutatja be, hogyan lehet javítani az értékesítési rendelések használata során felmerülő problémákat.

## <a name="the-tax-information-isnt-updated-if-i-change-the-location-on-a-sales-order-header"></a>Az adózási információk nem frissülnek, ha módosítom a helyet egy értékesítési rendelés fejlécében.

### <a name="issue-description"></a>Probléma leírása

Ha a hely, a raktár vagy a szállítási cím egy értékesítési rendelés fejlécében vagy sor szintjén módosul, akkor a program nem frissíti automatikusan az eset adózási információit a sorokban.

### <a name="issue-resolution"></a>Probléma megoldása

Ez szándékosan van. A probléma oka az, hogy a szállítási cím, a hely és a raktár nem változik meg automatikusan a sor szintjén. Ezeket manuálisan kell frissítenie.

## <a name="if-there-are-two-trade-agreements-for-the-same-period-or-overlapping-periods-the-same-agreement-line-is-always-selected"></a>Ha ugyanarra az időszakra vagy egymást átfedő időszakokra két kereskedelmi megállapodás van kiválasztva, akkor minden esetben ugyanaz a szerződési sor van kiválasztva.

### <a name="issue-description"></a>Probléma leírása

Ha ugyanarra az időszakra vagy egymást átfedő időszakokra két kereskedelmi megállapodást határoznak meg, minden alkalommal úgy tűnik, hogy az adott cikkeket tartalmazó értékesítésirendelés-sorok létrehozásakor ugyanez a kereskedelmi megállapodás van kiválasztva.

### <a name="issue-resolution"></a>Probléma megoldása

Ha egy adott dátumra vonatkozóan egynél több kereskedelmi megállapodás van megadva, a legalacsonyabb árat tartalmazó kereskedelmi megállapodás van mindig kiválasztva. További tájékoztatásért töltse le a következő tanulmányt: [Kereskedelmi megállapodások a Microsoft Dynamics AX 2012-ben](https://www.axug.com/HigherLogic/System/DownloadDocumentFile.ashx?DocumentFileKey=3396a3a8-1f48-4d85-8cd6-5fa982f62e90).

## <a name="can-i-link-a-purchase-order-to-a-sales-order-to-fulfill-demand"></a>Kapcsolható a beszerzési rendelés egy értékesítési rendeléshez igény teljesítéséhez?

Beszerzési rendelést létrehozhat értékesítési rendelésből. További információ: [Beszerzési rendelés létrehozása értékesítési rendelésből](tasks/create-purchase-order-sales-order.md).

## <a name="i-cant-cancel-or-delete-a-return-order-or-a-sales-order"></a>Nem tudom érvényteleníteni vagy törölni a visszárurendelést vagy az értékesítési rendelést.

Csak a *Létrehozva* állapotú értékesítési rendelések és visszárurendelések vonhatók vissza. További információkkal kapcsolatban lásd: [Visszárurendelések törlése](../service-management/cancel-return-order.md).

## <a name="when-i-try-to-cancel-a-sales-order-i-receive-a-reservations-cannot-be-removed-because-there-is-work-created-which-relies-on-the-reservations-error"></a>Amikor megpróbálok érvényteleníteni egy értékesítési rendelést, a „Foglalások nem távolíthatók el, mert van olyan munkafolyamat, amely a foglalásokon alapul” hibaüzenet jelenik meg.

Hibakód: WAX4661

Ha van munka egy értékesítési rendeléshez van társítva, akkor az értékesítési rendelés nem törölhető, amíg a munka nincs érvénytelenítve és visszavonva. Ez a követelmény akkor is érvényes, ha az értékesítési rendeléshez társított munka le van zárva.

Ezen hiba javításához kövesse az alábbi lépéseket.

1. Vonja vissza a munkát és a készletet helyezze vissza a kívánt helyre. Nyissa meg az értékesítési rendelés megfelelő rakományát, majd válassza a **Kitárolt mennyiség csökkentése** lehetőséget a rakománysorban vagy a **Munka sztornírozása** lehetőséget Műveleti ablaktáblán.

    A munka állapota most *Érvénytelenítve*, és a rendszer automatikusan létrehozza és feldolgozza az új készletmozgatási munkát, hogy a készletet visszahelyezze arra a helyre, amely a sztornírozásnál le van írva.

2. Törölje a rakományt. A szállítmány is törölve lesz.
3. Most el kell tudnia menni az értékesítési rendeléshez, és érvényteleníteni azt.

## <a name="i-cant-cancel-an-intercompany-purchase-order-that-is-linked-to-a-sales-order"></a>Nem tudok érvényteleníteni egy értékesítési rendeléshez kapcsolódó vállalatközi beszerzési rendelést.

### <a name="issue-description"></a>Probléma leírása

Ha egy értékesítési rendeléshez kapcsolódó vállalatközi beszerzési rendelést próbál meg törölni, a következő hibaüzenet jelenhet meg: „a mennyiség nem csökkenthető, mert a fennmaradó frissítési mennyiség megváltoztatja a jelet.”

### <a name="issue-resolution"></a>Probléma megoldása

Ez a probléma a Microsoft Dynamics 365 Supply Chain Management 10.0.13-as verziójában javítva lett. Ebben a verzióban és a későbbi verziókban már érvényteleníteni lehet egy értékesítési rendeléshez kapcsolódó vállalatközi beszerzési rendelést.

## <a name="can-i-restore-an-invoiced-sales-order-that-was-deleted"></a>Visszaállíthatók egy számlázott értékesítési rendelést, amely törölve lett?

### <a name="issue-description"></a>Probléma leírása

A számlázott értékesítési rendelés tévedésből törölve lett, és vissza szeretné állítani vagy megtekinteni annak adatait.

### <a name="issue-resolution"></a>Probléma megoldása

Ha a törölt értékesítési rendelés már számlázva van, nyissa meg a **Vevői számla \> Tranzakciók \> Eredeti dokumentum \> Részletek megtekintése** lehetőséget. Keresse meg a keresett számlát, és válassza ki, hogy megtekintse az adatait. Ezek a részletek az értékesítési rendelés hivatkozását tartalmazzák. Erről a lapról az értékesítési rendelés részleteit is elérheti.

## <a name="the-deadline-of-a-sales-order-header-cant-be-found-in-the-salesorderheaderv2entity-data-entity"></a>Az értékesítési rendelés fejlécének határideje nem található a SalesOrderHeaderV2Entity adatentitásban.

A határidő mező nem létezik a *SalesOrderHeaderV2Entity* entitásban.

## <a name="i-must-delete-orphaned-sales-order-records"></a>Az elárvult értékesítési rendelési rekordokat törölnöm kell.

Az elárvult értékesítési rendelések rekordjainak törléséhez futtassa az *Értékesítési rendelés törlése* ismétlődő feladatot a következő helyek valamelyikéről:

- Értékesítés és marketing \> Időszakos feladatok \> Adattisztítás \> Értékesítési rendelések törlése
- Kiskereskedelem és kereskedelem \> Kiskereskedelem és kereskedelem IT \> Adattisztítás \> Értékesítési rendelések törlése

## <a name="is-there-a-way-to-calculate-commissions-on-invoices-that-have-already-been-posted"></a>Van mód jutalékok kiszámítására a már feladott számlákon?

A Supply Chain Management jelenleg nem támogatja a jutalékok számítását a feladott számlákra vonatkozóan.

## <a name="a-bundle-item-isnt-supported-in-an-intercompany-process"></a>Egy csomagolt cikk nem támogatott a vállalatközi folyamatban.

A csomagolt cikk nem érhető el a beszerzési rendeléshez, mivel a csomagolt cikkhez tartozó értékesítésirendelés-sorok vizsgálatakor láthatja, hogy a mennyiség *0* (nulla), és az állapot *Visszavonva*. Ez szándékosan van. Az értékesítési rendelés csak a csomagolt cikk elemeit vásárolja. Nem vásárolja meg magát a csomagolt elemet.

Ha csomagban kell vásárolnia, gondolja végig, hogy csomagként kell-e megjelölni , mivel ez a funkció a bevétel-megjelenítési forgatókönyvekhez van tervezve. További információ a csomagolt cikkekkel kapcsolatosan: [Csomagok](../../finance/accounts-receivable/revenue-recognition-setup.md#bundles).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]