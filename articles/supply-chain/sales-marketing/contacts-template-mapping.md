---
title: "A Sales-kapcsolatok szinkronizálása a Finance and Operations-kapcsolatokra vagy -ügyfelekre"
description: "Ez a témakör azokat a sablonokat és kapcsolódó feladatokat mutatja be, melyek a Microsoft Dynamics 365 for Finance and Operations, Enterprise edition és a Microsoft Dynamics 365 for Sales közötti szinkronizálásra használhatók a névjegyek esetében."
author: ChristianRytt
manager: AnnBe
ms.date: 08/28/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: c838fef502f643c764fade9cd79ae770ffc36974
ms.contentlocale: hu-hu
ms.lasthandoff: 11/03/2017

---

# <a name="synchronize-contacts-from-sales-to-contacts-or-customers-in-finance-and-operations"></a>A Sales-kapcsolatok szinkronizálása a Finance and Operations-kapcsolatokra vagy -ügyfelekre

[!include[banner](../includes/banner.md)]

> [!NOTE]
> A potenciális vevő készpénzfizetési Solution használata előtt meg kell ismernie: [Dynamics 365 adatintegráció](/common-data-service/entity-reference/dynamics-365-integration). 

Ez a témakör azokat a sablonokat és kapcsolódó feladatokat mutatja be, melyek a Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (Finance and Operations) és a Microsoft Dynamics 365 for Sales (Sales) közötti szinkronizálásra használhatók a névjegyek esetében.

## <a name="templates-and-tasks"></a>Sablonok és feladatok

A következő sablonokat és alapul szolgáló feladatokat használják a névjegyek szinkronizálásához a Sales és a Finance and Operations között:

- **Sablonok nevei.**

    - Kapcsolattartók (Fin és Ops értékesítés)
    - Kapcsolattartók ügyfélhez (Fin és Ops értékesítés)

- **A projekt tevékenységeinek neve:**

    - Kapcsolattartók
    - ContactToCustomer

A kapcsolattartó-szinkronizálás előtt szükséges a következő szinkronizálási feladat: számlák (Fin és Ops értékesítés)

## <a name="entity-sets"></a>Entitáskészletek

| Értékesítés    | CDS     | Finance and Operations |
|----------|---------|------------------------|
| Kapcsolattartók | Kapcsolat | CDS-kapcsolattartók           |
| Kapcsolattartók | Könyvelési számla | Vevők V2           |

## <a name="entity-flow"></a>Entitás folyamata

Kapcsolattartók kezeli az értékesítési és a közös adatok szolgáltatás CD- és késedelmi a műveletekhez pedig szinkronizálva vannak-e.

Az értékesítési kapcsolattartó válhat a kapcsolattartót a CD- és a pénzügyi és a műveletek. Azt is megteheti hogy lehessen egy számlát a CD-k és a vevő késedelmi és a műveletek. Annak meghatározásához, hogy kapcsolattartó kell vehetők át az értékesítési szinkronizálás CD- és a pénzügyi és a műveletek (például az értékesítési kapcsolattartók &gt;lépjen kapcsolatba a CD &gt;kapcsolattartók Finance and Operations), a rendszer megvizsgálja a következő tulajdonságokat az értékesítésben a kapcsolattartó:

- **CD számláján és a vevő késedelmi és műveletek szinkronizálása:** kapcsolatba lép a where **van az aktív vevő** értéke **Igen**
- **CD kapcsolattartó és a pénzügyi és a műveletek a kapcsolattartó szinkronizálása:** kapcsolatba lép a where **van az aktív vevő** értéke **nem** és **vállalat** (szülő partner vagy kapcsolattartó) mutat fiókja (nem kapcsolattartó)

## <a name="prospect-to-cash-solution-for-sales"></a>Potenciális vevő értékesítési készpénzfizetési megoldáshoz 

Új **van az aktív vevő** mezőt adtak a kapcsolattartóval. Ebben a mezőben értékesítési tevékenység kapcsolattartóit és értékesítési tevékenység nincs szegmensből megkülönböztetésére szolgál. **Aktív vevő** értéke **Igen** csak a kapcsolattartók, ajánlatok, rendelések vagy számlák köthető. A Sales-kapcsolatok szinkronizálása a Finance and Operations--ügyfelekre

Új **IsCompanyAnAccount** mezőt adtak a kapcsolattartóval. Ez a mező segítségével adja meg, hogy a kapcsolattartó a vállalat (szülő partner vagy kapcsolattartó) kapcsolódik a **számla** típusa. Ez az információ Finance and Operations kapcsolattartóként kell szinkronizálandó kapcsolattartók azonosítására szolgál.

Új **kapcsolattartó száma** mező hozzá lett adva a kapcsolattartó a természetes és egyedi kulcs az integráció biztosítása érdekében. Új kapcsolattartó létrehozásakor egy **kapcsolattartó száma** értéke automatikusan létrejön egy számsorozat alapján. Az érték áll **CON**, amelyet egy növekvő számsorozat és utótag hat karakterből követ. Íme, egy példa: **CON-01000-BVRCPS**

Az integrációs megoldás értékesítési hozzáadná az értékesítésekhez, amikor beállítja a frissítési parancsprogram a **kapcsolattartó száma** meglévő korábban ismertetett számsorozatot használó ügyfelek mezőt. Is beállítja a frissítési parancsfájl a **van az aktív vevő** mezőt **Igen** minden értékesítési tevékenység rendelkező kapcsolattartók.

## <a name="in-finance-and-operations"></a>A Finance and Operations alkalmazásban 

Kapcsolattartók vannak megjelölt használatával a **IsContactPersonExternallyMaintained** tulajdonság. Ez a tulajdonság jelzi, hogy kapcsolattartó külsőleg tarthatók karban. Ebben az esetben külsőleg karbantartani kapcsolattartók karbantartása az értékesítés.

## <a name="preconditions-and-mapping-setup"></a>Előfeltételek és hozzárendelési beállítás

### <a name="contact-to-contact"></a>Névjegy - névjegy

- Frissítés **CD Szervezetazonosító** a a **forrás &gt;CD** hozzárendelés.

    - A sablon alapértelmezésre **Organization_OrganizationId [Szervezetazonosító]** van **ORG001**.
    - A sablon alapértelmezésre **PrimaryAccount_Organization_OrganizationId [Organization ID]** - **ORG001**.

- **A cím, ország, terület kódja** kell lennie a pénzügyi és a műveletek. Szinkronizációs hibák elkerülése érdekében az alapértelmezett értéket adhat a **CD &gt;műveletek** hozzárendelés. Az alapértelmezett érték akkor használatos, ha a mező üres, az értékesítési. A sablon alapértelmezett **PrimaryAddressCountryRegionISOCode** értéke **USA**.
- Győződjön meg arról, hogy egy értéket a következő mező szerepel a pénzügyi és a műveletek. Az adatok a Finance and Operations nincs szükség esetén távolíthatja el a hozzárendelést a a **CD &gt;cél** hozzárendelés.

    - **Finance and Operations mezőnév:** határozat
    - **Leképezés:** PrimaryAccountRole = DecisionMakingRole

### <a name="contact-to-customer"></a>Konvertálás vevővé

- Frissítés **CD Szervezetazonosító** a a **forrás &gt;CD** hozzárendelés. A sablon alapértelmezésre **Organization_OrganizationId [Szervezetazonosító]** van **ORG001**.
- **A cím, ország, terület kódja** kell lennie a pénzügyi és a műveletek. Szinkronizációs hibák elkerülése érdekében az alapértelmezett értéket adhat a **CD &gt;Cél** hozzárendelés. Az alapértelmezett érték akkor használatos, ha a mező üres, az értékesítési. A sablon alapértelmezett **PrimaryAddressCountryRegionISOCode** értéke **USA**.
- **CustomerGroup** kell lennie a pénzügyi és a műveletek. Szinkronizációs hibák elkerülése érdekében az alapértelmezett értéket adhat a **CD &gt;Cél** hozzárendelés. Az alapértelmezett érték akkor használatos, ha a mező üres, az értékesítési. A sablon alapértelmezett **CustomerGroupId** értéke **USA**.
- A következő hozzárendelésének eltávolítása hozzáadásával **CD &gt;cél**, segítséget nyújthat manuális, amelyek szerepelnek a Finance and Operations számának csökkentésével lehetséges. Használhatja az alapértelmezett értékek vagy hozzárendelése, például **ország/régió** vagy **Város**.

    - **SiteId** -alapértelmezett helyét is meg lehet adni a Finance and Operationsben. Hely a Finance and Operations árajánlatok és értékesítési rendelések létrehozásához szükséges. Sablon értéket **SiteId** nincs definiálva.
    - **WarehouseId** -alapértelmezett helyét is meg lehet adni a Finance and Operationsben. Raktár a Finance and Operations árajánlatok és értékesítési rendelések létrehozásához szükséges. Sablon értéket **WarehouseId** nincs definiálva.
    - **LanguageId** - nyelv a Finance and Operations árajánlatok és értékesítési rendelések sorainak létrehozásához szükséges. A sablon alapértelmezett **LanguageId** értéke **en-us**.

## <a name="template-mapping-in-data-integrator"></a>Sablonleképezés az adatintegrátorban

Az alábbi ábrákon sablon hozzárendelést például adatok integrátor megjelenítése.

### <a name="contact-to-contact"></a>Névjegy - névjegy

![Sablonleképezés az adatintegrátorban](./media/contacts-template-mapping-data-integrator-1.png)

![Sablonleképezés a névjegyekhez az adatintegrátorban](./media/contacts-template-mapping-data-integrator-2.png)

### <a name="contact-to-customer"></a>Konvertálás vevővé

![Sablonleképezés az adatintegrátorban](./media/contacts-template-mapping-data-integrator-3.png)

![Sablonleképezés a névjegyekhez az adatintegrátorban](./media/contacts-template-mapping-data-integrator-4.png)


## <a name="related-topics"></a>Kapcsolódó témakörök

[A Finance and Operations-termékek szinkronizálása a Sales-termékekre](products-template-mapping.md)

[A Sales-számlák szinkronizálása a Finance and Operations-ügyfelekre](accounts-template-mapping.md)

[Értékesítésiajánlat-fejlécek és -sorok szinkronizálása a Sales szolgáltatásból a Finance and Operations szolgáltatásba](sales-quotation-template-mapping.md)

[Értékesítésirendelés-fejlécek és -sorok szinkronizálása a Finance and Operations szolgáltatásból a Sales szolgáltatásba](sales-order-template-mapping.md)

[Értékesítésiszámla-fejlécek és -sorok szinkronizálása a Finance and Operations szolgáltatásból a Sales szolgáltatásba](sales-invoice-template-mapping.md)

