---
title: Raktárkezelés frissítése a Microsoft Dynamics AX 2012-ről a Supply Chain Management szolgáltatásra
description: Ez a cikk áttekintést nyújt a termékek és raktárak kezelési áttelepítési beállításairól.
author: perlynne
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventLocationWHSProcessEnablement, WHSLocationProfile, InventTableStorageDimensionGroupChange, InventUpdateBlockedItem, WHSParameters, WHSReservationHierarchy, WHSUOMSeqGroupTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 1714054
ms.assetid: 79a1a3b9-3a36-4162-8839-ec39b5e26602
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7a88c5a615ec860890578873eaee736fabbeaf08
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/29/2022
ms.locfileid: "9065810"
---
# <a name="upgrade-warehouse-management-from-microsoft-dynamics-ax-2012-to-supply-chain-management"></a>Raktárkezelés frissítése a Microsoft Dynamics AX 2012-ről a Supply Chain Management szolgáltatásra 


[!include [banner](../includes/banner.md)]

Ez a cikk áttekintést nyújt Microsoft Dynamics AX a 2012 R3 frissítésének folyamatról, amely a WMSII modult futtatja az Ellátásilánc-kezelés modulban.

A Supply Chain Management rendszer már nem támogatja a Microsoft Dynamics AX 2012 rendszerből származó örökölt **WMSII** modult. Ehelyett a **Raktárkezelés** modult használhatja. A WMSII modulban a pénzügyi készlethez ki lehet választani a hely és raklap-azonosító készletdimenziókat, azonban a raklap-azonosító készletdimenzió nem használható pénzügyi készletként, a Supply Chain Management alkalmazásban.

Frissítés közben az összes olyan termék, amely hozzá van rendelve egy tárolásidimenzió-csoporthoz, amely használja a raklap-azonosító készletdimenziót, a rendszer azonosítja, zároltként jelöli meg, és nem lesz feldolgozva a frissítéshez.

## <a name="upgrading-to-supply-chain-management-when-ax-2012-r3-wmsii-is-used"></a>Frissítés a Supply Chain Management szolgáltatásra az AX 2012 R3 WMSII használata esetén
A frissítés után a frissítéskor zárolt termékeket feloldhatja a **Tárolási dimenziócsoportok módosítása cikkekhez** folyamatban található áttelepítési lehetőségekkel, ami után a termékekhez tartozó tranzakciók feldolgozhatók.

### <a name="enabling-items-in-supply-chain-management"></a>Cikkek engedélyezése a Supply Chain Management szolgáltatásban 
Erre a módosításra azért van szükség, mert az Ellátásilánc-kezelésben a cikkkövetés része a raktárkezelési folyamatoknak (WMS). E folyamatokhoz minden raktárat és azok helyeit egy helyprofilhoz kell társítani. Ha WMS-t szeretne használni, a következőket kell konfigurálni:
-   A WMS csak akkor használható, ha engedélyezve vannak a meglévő raktárak. 
-   A meglévő kiadott termékeknek olyan tárolásidimenzió-csoporthoz kell társítva lennie, amely WMS-t használ. 

Ha a forrás tárolási dimenziócsoportok a raklap-azonosítót használják, a raklap-azonosító dimenziót használó, meglévő aktuális készlet helyeit egy olyan helyi profilhoz kell társítani, amelyben az **Azonosítótábla követésének használata** paraméter van kiválasztva. Ha a meglévő raktárakban nem lehet engedélyezni a WMS használatát, a meglévő aktuális készlet tárolásidimenzió-csoportjait olyan csoportokra lehet módosítani, amelyek csak a Hely, Raktár és Hely készletdimenziókat kezelik. 

> [!NOTE] 
>  Akkor is módosíthatja a tárolási dimenziócsoportot egy elemhez, ha nyitott készlettranzakciók léteznek.

## <a name="find-products-that-were-blocked-because-of-pallet-id"></a>Raklap-azonosító miatt blokkolt termék megkeresése.
A frissítés során blokkolt és nem feldolgozható kiadott termékek listájának megjelenítéséhez kattintson ide: **Készletkezelés** &gt; **Beállítás** &gt; **Készlet** &gt; **Készletfrissítésekből kitiltott elemek**.

## <a name="change-storage-dimension-group-for-blocked-products"></a>Letiltott termék tárolásidimenzió-csoportjának módosítása 
 
A raktárkezelési folyamatok részeként való használathoz a cikkeket olyan tárolási dimenziócsoporthoz kell társítani, amelyben a helyi készlet dimenzió aktív, és a **Raktárkezelési folyamatok használata** paraméter van kiválasztva. Ha ez a beállítás be van jelölve, aktívvá válnak a Telephely, a Raktár, a Készlet állapota, a Hely és az Azonosítótábla készletdimenziók.

A frissítés során blokkolt termékek zárolásának feloldásához ki kell választania egy új tárolási dimenziócsoportot a termékekhez. Ne feledje, hogy akkor is módosíthatja a tárolási dimenziócsoportot, ha nyitott készlettranzakciók léteznek. Ha a frissítés során blokkolt cikkeket szeretné használni, két lehetőség közül választhat:

-   Módosítsa a cikk tárolási dimenziócsoportját olyan tárolási dimenziócsoportra, amely csak a Telephely, Raktár és Hely készletdimenziókat használja. A módosítás miatt a raklap-azonosító készletdimenzió már nincs használatban.
-   A cikk tárolásidimenzió-csoportjának módosítása WMS-t használó tárolásidimenzió-csoportra. A módosítás miatt az Azonosítótábla készletdimenzió aktív lesz.

## <a name="configure-wms"></a>Az WMS beállítása
Mielőtt használhatná a kiadott termékeket a **Raktárkezelés** modulban, a termékeknek egy tárolási dimenziócsoportot kell használniuk, ahol a **Raktárkezelési folyamatok használata** paraméter van kiválasztva.

### <a name="enable-warehouses-to-use-wms"></a>Raktárak engedélyezése a WMS használatára

1.  Hozzon létre legalább egy új helyprofilt.
2.  Kattintson a **Raktárkezelés** &gt; **Beállítás** &gt; **Raktárkezelési folyamatok engedélyezése** &gt; **Raktár beállításának engedélyezése** lehetőségre.
3.  A **Raktárbeállítások engedélyezése** oldalon adja hozzá az engedélyezni kívánt raktárakat. Ezt a lépést közvetlenül az oldalon vagy a Microsoft Office-integráció használatával teheti meg.
4.  Társítson helyprofilt az összes helyhez. Ezt a lépést könnyen megteheti a Microsoft Office-integráció használatával közvetlenül az oldalon. Exportálhatja és importálhatja az adatokat, vagy használhatja az adatentitások feldolgozását az [Adatkezelés](../../fin-ops-core/dev-itpro/data-entities/data-entities.md) lehetőségben.
5.  Ellenőrizze a módosításokat. Az ellenőrzési folyamat részeként az adatok integritását különböző ellenőrzések révén vizsgálja a rendszer. A nagyobb frissítési folyamat részeként hibák fordulhatnak elő, amelyeket esetleg a forrásvégrehajtásban kell módosítani. Ebben az esetben egy további adatfrissítésre lesz szükség.
6.  Dolgozza fel a módosításokat.

### <a name="change-the-storage-dimension-group-for-items-so-that-it-uses-wms"></a>A cikkek tárolásidimenzió-csoportjának módosítása a WMS használatával

1.  Hozzon létre egy új **Készletállapot** értéket, és rendelje hozzá **Alapértelmezett készletállapot-azonosító** értékként a **Raktárkezelési paraméterek** beállításaihoz.
2.  Hozzon létre egy új tárolási dimenziócsoportot, ahol a **Raktárkezelési folyamatok használata** paraméter van kiválasztva.
3.  A **Foglalási hierarchia** lapon határozzon meg egy új foglalási hierarchiát a cikk tárolási és nyomon követési dimenziócsoportjai alapján.
4.  Hozzon létre egy vagy több egységszekvencia-csoportot, amelyek ugyanazokat a mértékegységeket tartalmazzák, amelyeket a cikk készletegységében használnak.
5.  Kattintson a **Raktárkezelés** &gt; **Beállítás** &gt; **Raktárkezelési folyamatok engedélyezése** &gt; **Tárolási dimenziócsoportok módosítása cikkekhez** lehetőségre.
6.  A **Tárolási dimenziócsoport módosítása cikkekhez** lapon adja hozzá a cikkszámokat, a tárolási dimenziócsoportokat és az egységszekvencia-csoportokat. Ezt a lépést közvetlenül az oldalon végezheti el a Microsoft Office-integráció használatával vagy az adatentitás folyamat segítségével az [Adatkezelés lehetőségben](../../fin-ops-core/dev-itpro/data-entities/data-entities.md).
7.  Ellenőrizze a módosításokat. Az ellenőrzési folyamat részeként az adatok integritását különböző ellenőrzések révén vizsgálja a rendszer. A nagyobb frissítési folyamat részeként hibák fordulhatnak elő, amelyeket esetleg a forrásvégrehajtásban kell módosítani. Ebben az esetben egy további adatfrissítésre lesz szükség.
8.  Dolgozza fel a módosításokat. A készletdimenziók frissítése eltarthat egy ideig. A kötegelt feladatok segítségével figyelemmel követheti a folyamat állapotát.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]