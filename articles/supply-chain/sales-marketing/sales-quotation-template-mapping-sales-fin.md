---
title: Értékesítésiajánlat-fejlécek és -sorok közvetlen szinkronizálása a Sales szolgáltatásból a Finance and Operations szolgáltatásba
description: Ez a témakör a sablonokat és alapul szolgáló feladatokat mutatja be, amelyeket használnak az ajánlatfejlécek és sorok közvetlen szinkronizálásához a Microsoft Dynamics 365 for Sales és a Microsoft Dynamics 365 for Finance and Operations között.
author: ChristianRytt
manager: AnnBe
ms.date: 10/25/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: 0894f4728d3f1df21db130cd9e87d9881726e7fa
ms.sourcegitcommit: 45f8cea6ac75bd2f4187380546a201c056072c59
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/12/2019
ms.locfileid: "1743371"
---
# <a name="synchronize-sales-quotation-headers-and-lines-directly-from-sales-to-finance-and-operations"></a>Értékesítésiajánlat-fejlécek és -sorok szinkronizálása közvetlenül a Sales szolgáltatásból a Finance and Operations szolgáltatásba

[!include [banner](../includes/banner.md)]

Ez a témakör a sablonokat és alapul szolgáló feladatokat mutatja be, amelyeket használnak az ajánlatfejlécek és sorok közvetlen szinkronizálásához a Microsoft Dynamics 365 for Sales és a Microsoft Dynamics 365 for Finance and Operations között.

> [!NOTE]
> A potenciális ügyfelek készpénzre váltása megoldás használata előtt meg kell ismernie az [Adatintegrálással a Common Data Service for Apps szolgáltatásban](https://docs.microsoft.com/powerapps/administrator/data-integrator).

## <a name="data-flow-in-prospect-to-cash"></a>A potenciális ügyfelek készpénzre váltása adatfolyama

A potenciális ügyfelek készpénzre váltása megoldás az adatszinkronizálás funkción keresztül szinkronizálja az adatokat Finance and Operations and Sales példányai között. Az Adatintegrációs szolgáltatásban rendelkezésre álló A potenciális ügyfelek készpénzre váltása sablonok lehetővé teszik a termék-, ügyfél-, kapcsolatfelvételi és eladási számlákra vonatkozó adatok áramlását a Finance and Operations és a Sales között. A következő ábra bemutatja a Finance and Operations és a Sales közötti adatszinkronizálást.

[![A potenciális ügyfelek készpénzre váltása adatfolyama](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)

## <a name="template-and-tasks"></a>Sablon és feladatok

A következő sablont és alapul szolgáló feladatokat használják az értékesítési ajánlati fejlécek és sorok közvetlen szinkronizálásához a Sales és a Finance and Operations között:

- **Sablon neve az adatintegrációban:** Értékesítési ajánlatok (Sales – Fin and Ops) – Közvetlen
- **A feladatok nevei az adatintegrációs projektben:**

    - QuoteHeader
    - QuoteLine

A következő szinkronizálási feladatok kötelezőek, mielőtt az értékesítési ajánlat fejlécének és sorainak szinkronizálása megtörténhetne:

- Termékek (Fin and Ops – Sales) – Közvetlen
- Számlák (Sales a Fin and Opshoz) – Közvetlen (ha van)
- Kapcsolattartók vevőkkel (Sales a Fin and Opshoz) – közvetlen (ha van)

## <a name="entity-set"></a>Entitás beállítása

| Értékesítés        | Finance and Operations     |
|--------------|----------------------------|
| Idézetek       | CDS értékesítésiajánlat-fejléc |
| QuoteDetails | CDS értékesítési ajánlat sorai  |

## <a name="entity-flow"></a>Entitás folyamata

Az értékesítési ajánlatok létrehozása a Sales-ben történik, majd szinkronizálódnak a Finance and Operations programban.

A Sales értékesítési ajánlatai csak akkor szinkronizálódnak, ha teljesülnek az alábbi feltételek:

- Az értékesítési ajánlatban szereplő összes termék külsőleg van karbantartva.
- Miután rákattint az **Ajánlat aktiválása** lehetőségre, az értékesítési árajánlat aktívvá válik.

## <a name="prospect-to-cash-solution-for-sales"></a>Potenciális vevő értékesítési készpénzfizetési megoldáshoz

A **Csak külsőleg karbantartott termékei vannak** mező hozzáadódott az **Ajánlat** entitáshoz annak érdekében, hogy konzisztensen követni lehessen, hogy az értékesítési ajánlat teljes mértékben külsőleg karbantartott termékekből áll-e. Ha az értékesítési árfolyamok csak külsőleg fenntartott termékeket tartalmaznak, a termékeket a Finance and Operations kezeli. Ez a viselkedés garantálja, hogy nem próbálja szinkronizálni az értékesítési ajánlati sorokat olyan termékekkel, amelyek ismeretlenek a Finance and Operations számára.

Az értékesítési ajánlat minden terméke frissül a **Csak külsőleg karbantartott termékei vannak** információval az árajánlat fejlécéből. Ezek az információk megtalálhatók az **Ajánlat csak külsőleg fenntartott termékekre vonatkozik** mezőben, a **QuoteDetails** entitásnál.

Kedvezményt lehet hozzáadni az idevonatkozó termékhez, és szinkronizálva lesz a Finance and Operations szolgáltatással. A fejlécen az **Engedmény**, **Költségek** és **Adó** mezők a Finance and Operations szolgáltatásból szabályozhatók. Ezzel a beállítással jelenleg nem támogatott integrációs megfeleltetés. Az aktuális modellben az **Ár**, **Engedmény**, **Költség** és az **Adó** mezők lezárt fájlrendszer és kezeli a Finance and Operations felületén.

Az értékesítési a megoldás teszi a következő mezők írásvédett, mivel az értékek nem szinkronizálja a késedelmi a műveletekhez pedig:

- Csak olvasható mezőket az értékesítésiajánlat-fejlécen:**Árengedmény%** Árengedmény%, **Árengedmény** és**Fuvardíj**
- Csak olvasható mezők az ajánlat termékein: **Adó**

## <a name="preconditions-and-mapping-setup"></a>Előfeltételek és hozzárendelési beállítás

Értékesítési ajánlatok szinkronizálása előtt fontos frissíteni a rendszert a következő beállításokkal.

### <a name="setup-in-sales"></a>Beállítás a Salesben

- Győződjön meg róla, hogy beállították az engedélyeket ahhoz a csapathoz, amelytől a Sales kapcsolatkészletének felhasználója hozzá van rendelve. Bemutatóadatok használatakor rendszerint a felhasználó rendelkezik rendszergazdai hozzáféréssel, de nem a csoport. Ha a csapatnak nincs adminisztrátori hozzáférése, akkor ha a projektet az adatintegrálásból futtatja, hibaüzenet jelenik meg, amely azt jelzi, hogy a fő csapat hiányzik.

    A csoport engedélyeinek beállításához kattintson a **beállítások**&gt;**biztonsági**&gt;**csapatok**, és válassza ki a csapatot. Válasszon **szerepkörök kezelése**, és válassza ki a kívánt engedélyeket, például rendelkező szerepkör **rendszergazda**.

- Lépjen a **Beállítások** &gt; **Adminisztráció** &gt; **Rendszerbeállítások** &gt; **Értékesítés** pontra, és győződjön meg róla, hogy a következő beállításokat használja:

    - A **Rendszer díjazási számítási rendszerének használata** beállítás értéke **Igen**.
    - Az **Engedményszámítási módszer** mező értéke a **Sortétel**.

### <a name="setup-in-the-data-integration-project"></a>Beállítás az adatintegrációs projektben

#### <a name="quoteheader"></a>QuoteHeader

- Győződjön meg róla, hogy a szükséges leképezés létezik: **Shipto\_country** – **DeliveryAddressCountryRegionISOCode**. Az Értékmegfeleltetés is megadható egy alapértelmezett érték, amely akkor használható, ha az érték üresen marad. egyszerűen állítsa a bal oldalt az "Üres" értékre, és állítsa a jobb oldalt a kívánt országra vagy régióra. Ezzel a módszerrel nem kell beírni az országot vagy régiót a belföldi rendeléseknél.

    A sablon értéke olyan értékkérkép, amelyben több ország vagy régió van leképezve, és ahol az üres érték = **Amerikai Egyesült Államok**.

#### <a name="quoteline"></a>QuoteLine

- Győződjön meg arról, hogy a **SalesUnitSymbol** szükséges értékmegfeleltetése meg van adva a Finance and Operations szolgáltatásban.
- Győződjön meg róla, hogy a szükséges mértékegységek meghatározása a Sales szolgáltatásban történik.

    Olyan sablonérték, amely rendelkezik értékmegfeleltetéssel az **oumid.name** esetében a **SalesUnitSymbol** értékkel.

- Nem kötelező: a következő leképezések hozzáadásával biztosíthatja, hogy az értékesítési árlisták beillesztése a Finance and Operations szolgáltatásba, ha az ügyfél vagy a termék nem tartalmaz alapértelmezett információkat:

    - **SiteId** – hely a Pénzügy és műveletek árajánlatok és értékesítési rendelések sorainak létrehozásához szükséges. Nincs alapértelmezett sablonérték a **SiteId** elemnél.
    - **WarehouseId** – hely a raktár és műveletek árajánlatok és értékesítési rendelések sorainak létrehozásához szükséges. Nincs alapértelmezett sablonérték a **WarehouseId** elemnél.

## <a name="template-mapping-in-data-integrator"></a>Sablonleképezés az adatintegrátorban

> [!NOTE]
> - A **engedmény**, **költségek**, és **adó** mezők egy összetett-beállítást a pénzügyi és műveletek szabályozhatók. Ezzel a beállítással jelenleg nem támogatott integrációs megfeleltetés. Az aktuális modellben a **ár**, **engedmény**, **költség**, és **adó** mezők lezárt fájlrendszer a Finance and Operations.
> - A **fizetési feltételek**, **feltételek áruszállítási**, **szállítási feltételek**, **szállítási mód**, és **szállítási mód** mezők nem találhatók meg a alapértelmezett-leképezései. Ezek a mezők megfeleltetéséhez be kell állítania egy adott szervezetek között szinkronizált entitás adatainak értékmegfeleltetések.

Az alábbi ábrákon sablon hozzárendelést például adatok integrátor megjelenítése.

### <a name="quoteheader"></a>QuoteHeader

![Sablonleképezés az adatintegrátorban](./media/sales-quotation-direct-template-mapping-data-integrator-1.png)

### <a name="quoteline"></a>QuoteLine

![Sablonleképezés az adatintegrátorban](./media/sales-quotation-direct-template-mapping-data-integrator-2.png)

## <a name="related-topics"></a>Kapcsolódó témakörök

[A potenciális ügyfelek készpénzre váltása](prospect-to-cash.md)

