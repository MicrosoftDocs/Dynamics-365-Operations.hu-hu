---
title: "A Sales-kapcsolatok közvetlen szinkronizálása a Finance and Operations-kapcsolatokra vagy -ügyfelekre"
description: "Ez a témakör azokat a sablonokat és kapcsolódó feladatokat mutatja be, melyek a Microsoft Dynamics 365 for Finance and Operations, Enterprise edition és a Microsoft Dynamics 365 for Sales közötti szinkronizálásra használhatók a névjegyek entitásainak esetében."
author: ChristianRytt
manager: AnnBe
ms.date: 10/25/2017
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
ms.openlocfilehash: 8de9a920f384b69c9b3764a0431208bbdcb395bf
ms.contentlocale: hu-hu
ms.lasthandoff: 11/03/2017

---

# <a name="synchronize-contacts-directly-from-sales-to-contacts-or-customers-in-finance-and-operations"></a>A Sales-kapcsolatok közvetlen szinkronizálása a Finance and Operations-kapcsolatokra vagy -ügyfelekre

[!include[banner](../includes/banner.md)]

> [!NOTE]
> A potenciális ügyfelek készpénzre váltása megoldás használata előtt meg kell ismernie: [Dynamics 365 integráció](/common-data-service/entity-reference/dynamics-365-integration).

Ez a témakör azokat a sablonokat és kapcsolódó feladatokat mutatja be, melyek a Microsoft Dynamics 365 for Finance and Operations, Enterprise edition és a Microsoft Dynamics 365 for Sales közötti közvetlen szinkronizálásra használhatók a névjegyek entitásainak esetében.

## <a name="data-flow-in-prospect-to-cash"></a>A potenciális ügyfelek készpénzre váltása adatfolyama

A potenciális ügyfelek készpénzre váltása megoldás az adatszinkronizálás funkción keresztül szinkronizálja az adatokat Finance and Operations and Sales példányai között. Az Adatintegrációs szolgáltatásban rendelkezésre álló A potenciális ügyfelek készpénzre váltása sablonok lehetővé teszik a termék-, ügyfél-, kapcsolatfelvételi és eladási számlákra vonatkozó adatok áramlását a Finance and Operations és a Sales között. A következő ábra bemutatja a Finance and Operations és a Sales közötti adatszinkronizálást.

[![A potenciális ügyfelek készpénzre váltása adatfolyama](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)

## <a name="templates-and-tasks"></a>Sablonok és feladatok

A rendelkezésre álló sablonok megtekintéséhez nyissa meg a [PowerApps Admin Centert](https://preview.admin.powerapps.com/dataintegration). Válassza a **Projektek** lehetőséget, és ezután kattintson a jobb felső sarkában az **Új projekt** elemre a nyilvános sablonok kiválasztásához.

A következő sablonokat és alapul szolgáló feladatokat használják a névjegyentitások szinkronizálásához a Sales és a Finance and Operations között:

- **A sablonok nevei az adatintegrációban:**

    - Kapcsolattartók (Sales – Fin and Ops) – Közvetlen
    - Kapcsolattartók ügyfélhez (Sales – Fin and Ops) – Közvetlen

- **A feladatok nevei az adatintegrációs projektben:**

    - Kapcsolattartók
    - ContactToCustomer

A kapcsolattartó-szinkronizálás előtt szükséges a következő szinkronizálási feladat: számlák (Sales – Fin and Ops)

## <a name="entity-sets"></a>Entitáskészletek

| Értékesítés    | Finance and Operations |
|----------|------------------------|
| Kapcsolattartók | CDS-kapcsolattartók           |
| Kapcsolattartók | Vevők V2           |

## <a name="entity-flow"></a>Entitás folyamata

A kapcsolattartók kezelése a Sales programban történik, majd szinkronizálás történik a Finance and Operations programmal.

A Sales kapcsolattartójából kapcsolattartó vagy vevő lehet a Finance and Operationsben. Annak a megállapításához, hogy egy Sales-kapcsolattartót az Finance and Operationsben kapcsolattartóként vagy vevőként kell szinkronizálni, a rendszer megvizsgálja a következő tulajdonságokat a kapcsolattartó esetében a Salesben:

- **Szinkronizálás vevőbe a Finance and Operationsben:** kapcsolattartók, ahol a **van aktív vevő** értéke **Igen**
- **Szinkronizálás kapcsolattartóba a Finance and Operationsben:** kapcsolattartók, ahol a **van aktív vevő** értéke **nem**, és a **vállalat** (szülő számla/névjegy) fiókra mutat (nem kapcsolattartó)

## <a name="prospect-to-cash-solution-for-sales"></a>Potenciális vevő értékesítési készpénzfizetési megoldáshoz

Új **van aktív vevő** mezőt adtak a kapcsolattartóval. Ebben a mezőben értékesítési tevékenység kapcsolattartóit és értékesítési tevékenység nincs szegmensből megkülönböztetésére szolgál. A **van aktív vevő** értéke **Igen** csak a kapcsolattartók esetében, akikhez ajánlatok, rendelések vagy számlák köthetők. Csak ezek a kapcsolattartók szinkronizálódnak a Finance and Operationsbe vevőként.

Új **IsCompanyAnAccount** mezőt adtak a kapcsolattartóval. A mező segítségével adhatja meg, hogy a kapcsolattartó **Számla** típusú vállalathoz (szülő partner vagy kapcsolattartó) kapcsolódik-e. Ez az információ a Finance and Operationsben kapcsolattartóként szinkronizálandó kapcsolattartók azonosítására szolgál.

Új **kapcsolattartó száma** mező hozzá lett adva a kapcsolattartó a természetes és egyedi kulcs az integráció biztosítása érdekében. Új kapcsolattartó létrehozásakor egy **kapcsolattartó száma** értéke automatikusan létrejön egy számsorozat alapján. Az érték áll **CON**, amelyet egy növekvő számsorozat és utótag hat karakterből követ. Íme, egy példa: **CON-01000-BVRCPS**

A Sales integrációs megoldásának alkalmazásakor egy frissítési parancsprogram beállítja a **kapcsolattartó száma** mezőt a meglévő kapcsolattartónál a korábban ismertetett számsorozat használatával. A frissítési parancsfájl beállítja a **van aktív vevő** mezőt **Igen** értékre minden értékesítési tevékenységgel rendelkező kapcsolattartónál.

## <a name="in-finance-and-operations"></a>A Finance and Operations alkalmazásban

Kapcsolattartók vannak megjelölt használatával a **IsContactPersonExternallyMaintained** tulajdonság. Ez a tulajdonság jelzi, hogy kapcsolattartó külsőleg tarthatók karban. Ebben az esetben a külsőleg karbantartott kapcsolattartók karbantartása a Salesben történik.

## <a name="preconditions-and-mapping-setup"></a>Előfeltételek és hozzárendelési beállítás

### <a name="contact-to-customer"></a>Kapcsolattartóból vevő

- **CustomerGroup** kell lennie a pénzügyi és a műveletek. Szinkronizációs hibák elkerülésének elősegítése érdekében az alapértelmezett értéket adhat meg a hozzárendelésben. Az alapértelmezett érték akkor használatos, ha a mező üres, az értékesítési.

    Az alapértelmezett sablonérték **10**.

- A következő hozzárendelésének eltávolítása hozzáadásával CD cél, segítséget nyújthat manuális, amelyek szükségesek a Finance and Operations számának csökkentésével lehetséges. Használhatja az alapértelmezett értékek vagy hozzárendelése, például **ország/régió** vagy **Város**.

    - **SiteId** – alapértelmezett helyét is meg lehet adni a Finance and Operationsben. Hely a Finance and Operations árajánlatok és értékesítési rendelések létrehozásához szükséges.

        Sablon értéket **SiteId** nincs definiálva.

    - **WarehouseId** – alapértelmezett helyét is meg lehet adni a Finance and Operationsben. Raktár a Finance and Operations árajánlatok és értékesítési rendelések létrehozásához szükséges.

        Sablon értéket **WarehouseId** nincs definiálva.

    - **LanguageId** – nyelv a Pénzügy és műveletek árajánlatok és értékesítési rendelések sorainak létrehozásához szükséges.
    
        Az alapértelmezett sablonérték **en-us**.

## <a name="template-mapping-in-data-integration"></a>Sablonleképezés az adatintegrátorban

Az alábbi ábrákon sablon hozzárendelést például adatok integrátor megjelenítése. 

> [!NOTE]
> A leképezést mutatja, hogy melyik mezőadatok szinkronizálódnak a Sales – Finance and Operations irányban.

### <a name="contact-to-contact"></a>Kapcsolattartóból kapcsolattartó

![Sablonleképezés az adatintegrátorban](./media/contacts-direct-template-mapping-data-integrator-1.png)

### <a name="contact-to-customer"></a>Kapcsolattartóból vevő

![Sablonleképezés az adatintegrátorban](./media/contacts-direct-template-mapping-data-integrator-2.png)


## <a name="related-topics"></a>Kapcsolódó témakörök

[A potenciális ügyfelek készpénzre váltása](prospect-to-cash.md)

[A Sales-számlák közvetlen szinkronizálása a Finance and Operations-ügyfelekre](accounts-template-mapping-direct.md)

[A Finance and Operations-termékek közvetlen szinkronizálása a Sales-termékekre](products-template-mapping-direct.md)

[Értékesítésirendelés-fejlécek és -sorok közvetlen szinkronizálása a Finance and Operations szolgáltatásból a Sales szolgáltatásba](sales-order-template-mapping-direct.md)

[Értékesítésiszámla-fejlécek és -sorok közvetlen szinkronizálása a Finance and Operations szolgáltatásból a Sales szolgáltatásba](sales-invoice-template-mapping-direct.md)



