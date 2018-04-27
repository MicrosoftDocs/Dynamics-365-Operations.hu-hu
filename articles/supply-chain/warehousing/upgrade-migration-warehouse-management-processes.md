---
title: "Termékek és raktárkezelés áttelepítése AX 2012-ről Finance and Operations szolgáltatásra"
description: "Ez a témakör áttekintést nyújt a termékek és a raktárkezelés áttelepítési beállításairól."
author: perlynne
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventLocationWHSProcessEnablement, WHSLocationProfile, InventTableStorageDimensionGroupChange, InventUpdateBlockedItem, WHSParameters, WHSReservationHierarchy, WHSUOMSeqGroupTable
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 1714054
ms.assetid: 79a1a3b9-3a36-4162-8839-ec39b5e26602
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: 92d0b4dd9611de4d717f30dc8736c673835bea29
ms.contentlocale: hu-hu
ms.lasthandoff: 03/26/2018

---

# <a name="migrate-products-and-warehouse-management-from-ax-2012-to-finance-and-operations"></a>Termékek és raktárkezelés áttelepítése AX 2012-ről Finance and Operations szolgáltatásra

[!INCLUDE [banner](../includes/banner.md)]

Ez a témakör áttekintést nyújt a Microsoft Dynamics 365 for Finance and Operations rendszer termék- és raktárkezelési áthelyezési beállításairól.

<a name="introduction"></a>Bevezetés
------------

A Finance and Operations rendszerre történő frissítéskor a termékek zárolva vannak, ha olyan tárolási dimenziócsoporthoz vannak társítva, amelynek beállításai nem egyeznek a tárolási dimenziócsoport beállításainak a Finance and Operations rendszerben. Azonban a frissítés után a frissítéskor zárolt termékek feloldhatja a **Tárolási dimenziócsoportok módosítása cikkekhez** folyamatban található áttelepítési lehetőségekkel. Ezután feldolgozhatja a termékekhez tartozó tranzakciókat. Megtörténhet, hogy a cikkek egy része már társítva van olyan tárolási dimenziócsoportokhoz, amelyek esetében a Telephely, Raktár és a Hely készlete aktív és fizikailag követik. Ebben az esetben használhatja a **Tárolási dimenziócsoport módosítása cikkekhez** folyamatot ahhoz, hogy engedélyezze ezen cikkek raktárkezelési folyamatokban történő használatát. Ez a funkció akkor hasznos, ha a raktárkezelési funkciót már meglévő cikkekhez szeretné használni.

## <a name="upgrading-to-finance-and-operations-when-ax-2012-r3-wmsii-is-used"></a>Frissítés a Finance and Operations rendszerre AX 2012 R3 WMSII használata esetén
A Finance and Operations rendszer már nem támogatja a Microsoft Dynamics AX 2012 rendszerből származó örökölt **WMSII** modult. Ehelyett az új **Raktárkezelés** modult használhatja. Az előző verziókban a Hely és a Raklap-azonosító készletdimenziókat ki lehetett választani pénzügyi készlethez. A frissítési folyamat részeként azonban a raklap-azonosító készletdimenzió már nem engedélyezhető a pénzügyi készlethez. A raklap-azonosító készletdimenziót használó tárolási dimenziócsoporthoz társított termékeket zárolja és nem dolgozza fel a rendszer.

### <a name="enabling-items-in-finance-and-operations"></a>Cikkek engedélyezése a Finance and Operations rendszerben

A Finance and Operations rendszerben a raktárkezelési folyamatok részeként használt cikkeket olyan tárolási dimenziócsoporthoz kell társítani, amelyben a **Raktárkezelési folyamatok használata** paraméter van kiválasztva. Ha ez a beállítás be van jelölve, aktívvá válnak a Telephely, a Raktár, a Készlet állapota, a Hely és az Azonosítótábla készletdimenziók. Az ilyen típusú a tárolási dimenziócsoportra csak azoknál a cikkeknél válthat át, amelyek már társítva vannak azokkal a tárolási dimenziócsoportokkal, amelyek esetén a Hely készletdimenzió aktív.

### <a name="items-that-are-blocked-for-inventory-updates"></a>Készletfrissítésekből kitiltott elemek

A frissítés során blokkolt és nem feldolgozható kiadott termékek listájának megjelenítéséhez kattintson ide: **Készletkezelés** &gt; **Beállítás** &gt; **Készlet** &gt; **Készletfrissítésekből kitiltott elemek**.

### <a name="reapplying-blocked-products"></a>Kitiltott termékek újbóli alkalmazása

A frissítés során blokkolt termékek zárolásának feloldásához ki kell választania egy új tárolási dimenziócsoportot a termékekhez. Ne feledje, hogy akkor is módosíthatja a tárolási dimenziócsoportot, ha nyitott készlettranzakciók léteznek. Ha a frissítés során blokkolt cikkeket szeretné használni, két lehetőség közül választhat:

-   Módosítsa a cikk tárolási dimenziócsoportját olyan tárolási dimenziócsoportra, amely csak a Telephely, Raktár és Hely készletdimenziókat használja. A módosítás miatt a raklap-azonosító készletdimenzió már nincs használatban.
-   Módosítsa a cikk tárolási dimenziócsoportját olyan tárolási dimenziócsoportra, amely a raktárkezelési eljárásokat használja. A módosítás miatt az Azonosítótábla készletdimenzió aktív lesz.

### <a name="migration-processes"></a>Áttelepítési folyamatok

A Finance and Operations rendszerben a cikkek követése a raktárkezelési folyamatok része. E folyamatokhoz minden raktárat és azok helyeit egy helyprofilhoz kell társítani. Fogalmi szinten ha szeretné használni a raktárkezelési folyamatokat, két folyamatot kell kezelni:

-   A meglévő raktáraknak engedélyezni kell a raktárkezelési folyamatok használatát.
-   A meglévő kiadott termékeket egy új tárolási dimenziócsoporthoz kell társítani, amely raktárkezelési folyamatokat használ.

Ha a forrás tárolási dimenziócsoportok a raklap-azonosítót használják, a raklap-azonosító dimenziót használó, meglévő aktuális készlet helyeit egy olyan helyi profilhoz kell társítani, amelyben az **Azonosítótábla követésének használata** paraméter van kiválasztva. Ha a már meglévő raktárak nem engedélyezhetők a raktárkezelési folyamatok használatához, módosíthatja a meglévő aktuális készlet tárolási dimenziócsoportjait olyan csoportokra, amelyek csak a Telephely, a Raktár és a Hely készletdimenziókat kezelik.

### <a name="using-the-warehouse-management-processes"></a>Raktárkezelési folyamatok használata

Mielőtt használhatná a kiadott termékeket a **Raktárkezelés** modulban, a termékeknek egy tárolási dimenziócsoportot kell használniuk, ahol a **Raktárkezelési folyamatok használata** paraméter van kiválasztva.

#### <a name="enable-warehouses-to-use-warehouse-management-processes"></a>Raktárak engedélyezése a raktárkezelési folyamatok használatára

1.  Hozzon létre legalább egy új helyprofilt.
2.  Kattintson a **Raktárkezelés** &gt; **Beállítás** &gt; **Raktárkezelési folyamatok engedélyezése** &gt; **Raktár beállításának engedélyezése** lehetőségre.
3.  A **Raktárbeállítások engedélyezése** oldalon adja hozzá az engedélyezni kívánt raktárakat. Ezt a lépést közvetlenül az oldalon vagy a Microsoft Office-integráció használatával teheti meg.
4.  Társítson helyprofilt az összes helyhez. Ezt a lépést könnyen megteheti a Microsoft Office-integráció használatával közvetlenül az oldalon. Exportálhatja és importálhatja az adatokat, vagy használhatja az adatentitások feldolgozását az [Adatkezelés](../../dev-itpro/data-entities/data-entities.md) lehetőségben.
5.  Ellenőrizze a módosításokat. Az ellenőrzési folyamat részeként az adatok integritását különböző ellenőrzések révén vizsgálja a rendszer. A nagyobb frissítési folyamat részeként hibák fordulhatnak elő, amelyeket esetleg a forrásvégrehajtásban kell módosítani. Ebben az esetben egy további adatfrissítésre lesz szükség.
6.  Dolgozza fel a módosításokat.

#### <a name="change-the-storage-dimension-group-for-items-so-that-it-uses-warehouse-management-processes"></a>A cikkek tárolási dimenziócsoportjának módosítása úgy, hogy az raktárkezelési folyamatokat használjon

1.  Hozzon létre egy új **Készletállapot** értéket, és rendelje hozzá **Alapértelmezett készletállapot-azonosító** értékként a **Raktárkezelési paraméterek** beállításaihoz.
2.  Hozzon létre egy új tárolási dimenziócsoportot, ahol a **Raktárkezelési folyamatok használata** paraméter van kiválasztva.
3.  A **Foglalási hierarchia** lapon határozzon meg egy új foglalási hierarchiát a cikk tárolási és nyomon követési dimenziócsoportjai alapján.
4.  Hozzon létre egy vagy több egységszekvencia-csoportot, amelyek ugyanazokat a mértékegységeket tartalmazzák, amelyeket a cikk készletegységében használnak.
5.  Kattintson a **Raktárkezelés** &gt; **Beállítás** &gt; **Raktárkezelési folyamatok engedélyezése** &gt; **Tárolási dimenziócsoportok módosítása cikkekhez** lehetőségre.
6.  A **Tárolási dimenziócsoport módosítása cikkekhez** lapon adja hozzá a cikkszámokat, a tárolási dimenziócsoportokat és az egységszekvencia-csoportokat. Ezt a lépést közvetlenül az oldalon végezheti el a Microsoft Office-integráció használatával vagy az adatentitás folyamat segítségével az [Adatkezelés](../../dev-itpro/data-entities/data-entities.md) lehetőségben.
7.  Ellenőrizze a módosításokat. Az ellenőrzési folyamat részeként az adatok integritását különböző ellenőrzések révén vizsgálja a rendszer. A nagyobb frissítési folyamat részeként hibák fordulhatnak elő, amelyeket esetleg a forrásvégrehajtásban kell módosítani. Ebben az esetben egy további adatfrissítésre lesz szükség.
8.  Dolgozza fel a módosításokat. A készletdimenziók frissítése eltarthat egy ideig. A kötegelt feladatok segítségével figyelemmel követheti a folyamat állapotát.



