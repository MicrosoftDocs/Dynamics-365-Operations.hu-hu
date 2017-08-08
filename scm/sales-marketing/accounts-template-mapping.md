---
title: "A Sales-számlák szinkronizálása a Finance and Operations-ügyfelekre"
description: "A témakör azokat a sablonokat és kapcsolódó feladatokat mutatja be, melyek a Microsoft Dynamics 365 for Finance and Operations, Enterprise edition és a Microsoft Dynamics 365 for Sales közötti szinkronizálásra használhatók."
author: ChristianRytt
manager: AnnBe
ms.date: 07/03/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: yuyus
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: ChristianRytt
ms.dyn365.ops.intro: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: b497f078d9786a5c7630e924da6bb04cad37f5e9
ms.contentlocale: hu-hu
ms.lasthandoff: 07/27/2017

---

# <a name="synchronize-accounts-from-sales-to-customers-in-finance-and-operations"></a>A Sales-számlák szinkronizálása a Finance and Operations-ügyfelekre

[!include[banner](../includes/banner.md)]

> [!NOTE]
> A potenciális vevő készpénzfizetési Solution használata előtt meg kell ismernie: [Dynamics 365 adatintegráció](https://docs.microsoft.com/en-us/common-data-service/entity-reference/dynamics-365-integration). 

A témakör azokat a sablonokat és kapcsolódó feladatokat mutatja be, melyek a Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (Finance and Operations) és a Microsoft Dynamics 365 for Sales (Sales) közötti szinkronizálásra használhatók a fiókok esetében.

## <a name="template-and-task"></a>Sablon és feladat

A következő sablonokat és alapul szolgáló feladatokat használják a fiókok szinkronizálásához a Sales és a Finance and Operations között:

- **Sablon neve:** Fiókok (Sales – Fin and Ops)
- **A feladat neve a projektben:** Fiókok – számla - vevők

Szinkronizálási feladatok szükségessége a szinkronizálás előtt: Nincs

## <a name="entity-set"></a>Entitás beállítása

| Értékesítés    | CDS     | Finance and Operations |
|----------|---------|------------------------|
| Számlák | Könyvelési számla | Vevők              |

## <a name="entity-flow"></a>Entitás folyamata

A számlákat a Sales modulban kezeli a rendszer, és a Finance and Operationsben szinkronizálódnak. A **külsőleg megmarad** ilyen vevő tulajdonságának értéke **Igen**, amely az értékesítési ajánlatból vevők nyomon követésére. A számlázás során a adatok szinkronizálva vannak-e az értékesítési számlák szűréséhez.

## <a name="prospect-to-cash-solution-for-sales"></a>Potenciális vevő értékesítési készpénzfizetési megoldáshoz

A **számlaszám** a mező akkor érhető el a **számla** oldalon. Tették integráláshoz a természetes és egyedi kulcs. A vevő kapcsolat kezelés (CRM) megoldás természetes kulcselemét hatással lehet a vevőknek, akik már használja a **számlaszám** használó egyedi nem, de a mező **számlaszám** számlánként értékeket. Az integrációs megoldás jelenleg ebben az esetben nem támogatja.

Új számla létrehozása esetén, ha egy **számlaszám** értéke nem létezik, szerint egy számsorozat alapján automatikusan történik. Az érték áll **számlás**, amelyet egy növekvő számsorozat és utótag hat karakterből követ. Íme, egy példa: **ACC-01000-BVRCPS**

Az integrációs megoldás értékesítési kiegyenlítésekor beállítja a frissítési parancsprogram a **számlaszám** létező számlák, értékesítési mezőt. Ha nem **számlaszám** értékeit, a számsorozatot, amely a fentebb leírt használatos.

## <a name="preconditions-and-mapping-setup"></a>Előfeltételek és hozzárendelési beállítás

- **CustomerGroupId** frissíteni kell, hogy a pénzügyi és műveletek egy érvényes értéket. Meghatározhat egy alapértelmezett értéket, vagy az érték beállítható egy Értékmegfeleltetés használatával. Az alapértelmezett sablonérték **10**.
- **A cím, ország, terület kódja** kell lennie a pénzügyi és a műveletek. Szinkronizációs hibák elkerülése érdekében megadhatja az alapértelmezett érték. Az alapértelmezett érték akkor használatos, ha a mező üres, az értékesítési.

    - A sablon alapértelmezett **AddressCountryRegionISOCode** értéke **USA**.
    - A sablon alapértelmezett **DeliveryAddressCountryRegionISOCode** értéke **USA**.

- A következő hozzárendelésének eltávolítása hozzáadásával **CD &gt;cél**, segítséget nyújthat manuális, amelyek szükségesek a Pénzügy és műveletek számának csökkentésével lehetséges. Használhatja az alapértelmezett értékek vagy hozzárendelése, például **ország/régió** vagy **Város**.

    - **SiteId** – hely a Pénzügy és műveletek árajánlatok és értékesítési rendelések sorainak létrehozásához szükséges. Alapértelmezett webhely készíthetők a terméket, vagy a vevő a rendelés fejlécében. A sablon alapértelmezett **SiteId** értéke **USA**.
    - **WarehouseId** – hely a raktár és műveletek árajánlatok és értékesítési rendelések sorainak létrehozásához szükséges. Alapértelmezett raktár készíthető a termék vagy a vevő a rendelés fejlécében a Finance and Operations programban. A sablon alapértelmezett **WarehouseId** értéke **13**.
    - **LanguageId** – nyelv a Pénzügy és műveletek árajánlatok és értékesítési rendelések sorainak létrehozásához szükséges. Alapértelmezés szerint a vevő a rendelés fejlécéből a nyelvet használja. A sablon alapértelmezett **LanguageId** értéke **en-us**.

- CD szervezeti azonosító frissítése (**Organization_OrganizationId**) található a **forrás &gt;CD** hozzárendelés. Az alapértelmezett sablonérték **ORG001**.

## <a name="template-mapping-in-data-integrator"></a>Sablonleképezés az adatintegrátorban

> [!NOTE]
> A **fizetési feltételek**, **feltételek áruszállítási**, **szállítási feltételek**, **szállítási mód**, és **szállítási mód** mezők nem szerepelnek a alapértelmezett-leképezései. Ezek a mezők megfeleltetéséhez be kell állítania egy értékmegfeleltetések. Érték-hozzárendelésre vonatkoznak a szervezetek között szinkronizált entitás adatait.

Az alábbi ábrákon sablon hozzárendelést például adatok integrátor megjelenítése.

![Sablonleképezés az adatintegrátorban](./media/accounts-template-mapping-data-integrator-1.png)

![Sablonleképezés a számlákhoz az adatintegrátorban](./media/accounts-template-mapping-data-integrator-2.png)

## <a name="related-topics"></a>Kapcsolódó témakörök

[A Finance and Operations-termékek szinkronizálása a Sales-termékekre](products-template-mapping.md)

[A Sales-kapcsolatok szinkronizálása a Finance and Operations-kapcsolatokra vagy -ügyfelekre](contacts-template-mapping.md)

[Értékesítésiajánlat-fejlécek és -sorok szinkronizálása a Sales szolgáltatásból a Finance and Operations szolgáltatásba](sales-quotation-template-mapping.md)




