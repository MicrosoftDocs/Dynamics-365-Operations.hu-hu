---
title: A Sales-kapcsolatok közvetlen szinkronizálása a Supply Chain Management-kapcsolatokra vagy -ügyfelekre
description: Ez a témakör bemutatja a sablonokat és a mögöttes feladatokat, amelyek a Dynamics 365 Sales Névjegy (Névjegyek) és Névjegy (Vevők) entitások közvetlenül a Dynamics 365 Supply Chain Management alkalmazásba történő szinkronizálására használatosak.
author: ChristianRytt
ms.date: 10/25/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: 81cf79c866ad70bf5bf2a9475a235bf3135d6e50
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5840797"
---
# <a name="synchronize-contacts-directly-from-sales-to-contacts-or-customers-in-supply-chain-management"></a>A Sales-kapcsolatok közvetlen szinkronizálása a Supply Chain Management-kapcsolatokra vagy -ügyfelekre

[!include [banner](../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

> [!NOTE]
> A potenciális ügyfelek készpénzre váltása megoldás használata előtt meg kell ismernie az [Adatintegrálással a Microsoft Dataverse for Apps szolgáltatásban](https://docs.microsoft.com/powerapps/administrator/data-integrator).

Ez a témakör bemutatja a sablonokat és a mögöttes feladatokat, amelyek a Dynamics 365 Sales Névjegy (Névjegyek) és Névjegy (Vevők) táblát közvetlenül a Dynamics 365 Supply Chain Management alkalmazásba történő szinkronizálására használatosak.

## <a name="data-flow-in-prospect-to-cash"></a>A potenciális ügyfelek készpénzre váltása adatfolyama

A potenciális ügyfelek készpénzre váltása megoldás az adatszinkronizálás funkción keresztül szinkronizálja az adatokat Supply Chain Management és a Sales példányai között. Az Adatintegrációs szolgáltatásban rendelkezésre álló A potenciális ügyfelek készpénzre váltása sablonok lehetővé teszik a termék-, ügyfél-, kapcsolatfelvételi és eladási számlákkal kapcsolatos adatok áramlását a Supply Chain Management és a Sales között. A következő ábra bemutatja a Supply Chain Management és a Sales közötti adatszinkronizálást.

[![A potenciális ügyfelek készpénzre váltása adatfolyama](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)

## <a name="templates-and-tasks"></a>Sablonok és feladatok

A rendelkezésre álló sablonok megtekintéséhez nyissa meg a [PowerApps Admin Centert](https://preview.admin.powerapps.com/dataintegration). Válassza a **Projektek** lehetőséget, és ezután kattintson a jobb felső sarkában az **Új projekt** elemre a nyilvános sablonok kiválasztásához.

A következő sablonokat és alapul szolgáló feladatokat használják a névjegy táblák szinkronizálásához a Sales és a Supply Chain Management között:

- **A sablonok nevei az adatintegrációban**

    - Névjegyek (Sales – Supply Chain Management ) – közvetlen
    - Kapcsolatok az ügyfelekre (Sales – Supply Chain Management) – közvetlen

- **A feladatok nevei az adatintegrációs projektben**

    - Névjegyek
    - ContactToCustomer

A kapcsolattartó-szinkronizálás előtt szükséges a következő szinkronizálási feladat: számlák (Sales – Supply Chain Management)

## <a name="entity-sets"></a>Entitáskészletek

| Értékesítés    | Ellátásilánc-kezelés |
|----------|------------------------|
| Kapcsolattartók | Dataverse kapcsolattartók           |
| Kapcsolattartók | Vevők V2           |

## <a name="entity-flow"></a>Entitás folyamata

A névjegyek kezelése a Salesben történik, majd szinkronizálódnak a Supply Chain Management programban.

A Sales kapcsolattartójából kapcsolattartó vagy vevő lehet a Supply Chain Managementben. Annak a megállapításához, hogy egy Sales-kapcsolattartót a Supply Chain Management alkalmazásban kapcsolattartóként vagy vevőként kell szinkronizálni, a rendszer megvizsgálja a következő tulajdonságokat a kapcsolattartó esetében a Salesben:

- **Szinkronizálás vevőbe a Supply Chain Management alkalmazásban:** kapcsolattartók, ahol a **van aktív vevő** értéke **Igen**
- **Szinkronizálás kapcsolattartóba a Supply Chain Management alkalmazásban:** kapcsolattartók, ahol a **van aktív vevő** értéke **nem**, és a **vállalat** (szülő számla/névjegy) fiókra mutat (nem kapcsolattartó)

## <a name="prospect-to-cash-solution-for-sales"></a>Potenciális vevő értékesítési készpénzfizetési megoldáshoz

Új **van aktív vevő** oszlopot adtak a kapcsolattartóval. Ebben az oszlopban értékesítési tevékenység kapcsolattartóit és értékesítési tevékenység nincs szegmensből megkülönböztetésére szolgál. A **van aktív vevő** értéke **Igen** csak a kapcsolattartók esetében, akikhez ajánlatok, rendelések vagy számlák köthetők. Csak ezek a kapcsolattartók szinkronizálódnak a Supply Chain Management alkalmazásba vevőként.

Új **IsCompanyAnAccount** oszlopot adtak a kapcsolattartóval. Az oszlop segítségével adhatja meg, hogy a kapcsolattartó **Számla** típusú vállalathoz (szülő partner vagy kapcsolattartó) kapcsolódik-e. Ez az információ a Supply Chain Management alkalmazásban kapcsolattartóként szinkronizálandó kapcsolattartók azonosítására szolgál.

Új **kapcsolattartó száma** oszlop hozzá lett adva a kapcsolattartó a természetes és egyedi kulcs az integráció biztosítása érdekében. Új kapcsolattartó létrehozásakor egy **kapcsolattartó száma** értéke automatikusan létrejön egy számsorozat alapján. Az érték áll **CON**, amelyet egy növekvő számsorozat és utótag hat karakterből követ. Íme, egy példa: **CON-01000-BVRCPS**

A Sales integrációs megoldásának alkalmazásakor egy frissítési parancsprogram beállítja a **kapcsolattartó száma** oszlopot a meglévő kapcsolattartónál a korábban ismertetett számsorozat használatával. A frissítési parancsfájl beállítja a **van aktív vevő** oszlopot **Igen** értékre minden értékesítési tevékenységgel rendelkező kapcsolattartónál.

## <a name="in-supply-chain-management"></a>A Supply Chain Management alkalmazásban

Kapcsolattartók vannak megjelölt használatával a **IsContactPersonExternallyMaintained** tulajdonság. Ez a tulajdonság jelzi, hogy kapcsolattartó külsőleg tarthatók karban. Ebben az esetben a külsőleg karbantartott kapcsolattartók karbantartása a Salesben történik.

## <a name="preconditions-and-mapping-setup"></a>Előfeltételek és hozzárendelési beállítás

### <a name="contact-to-customer"></a>Kapcsolattartóból vevő

- A **CustomerGroup** kötelező a Supply Chain Managementben. Szinkronizációs hibák elkerülésének elősegítése érdekében az alapértelmezett értéket adhat meg a hozzárendelésben. Az alapértelmezett érték akkor használatos, ha az oszlop üres, az értékesítési.

    Az alapértelmezett sablonérték **10**.

- A következő hozzárendelésének eltávolítása hozzáadásával CD cél, segítséget nyújthat manuális, amelyek szükségesek a Supply Chain Management számának csökkentésével lehetséges. Használhatja az alapértelmezett értékek vagy hozzárendelése, például **ország/régió** vagy **Város**.

    - **SiteId** – alapértelmezett helyét is meg lehet adni a Supply Chain Managementben. Egy hely a Supply Chain Management árajánlatok és értékesítési rendelések sorainak létrehozásához szükséges.

        Sablon értéket **SiteId** nincs definiálva.

    - **WarehouseId** – alapértelmezett raktárat is meg lehet adni a Supply Chain Managementben. Egy raktár a Supply Chain Management árajánlatok és értékesítési rendelések sorainak létrehozásához szükséges.

        Sablon értéket **WarehouseId** nincs definiálva.

    - **LanguageId** – Egy nyelv a Supply Chain Management árajánlatok és értékesítési rendelések létrehozásához szükséges.
    
        Az alapértelmezett sablonérték **en-us**.

## <a name="template-mapping-in-data-integration"></a>Sablonleképezés az adatintegrátorban

Az alábbi ábrákon sablon hozzárendelést például adatok integrátor megjelenítése. 

> [!NOTE]
> A leképezést mutatja, hogy melyik oszlopadatok szinkronizálódnak a Sales – Supply Chain Management irányban.

### <a name="contact-to-contact"></a>Kapcsolattartóból kapcsolattartó

![Sablonleképezés az adatintegrátorban](./media/contacts-direct-template-mapping-data-integrator-1.png)

### <a name="contact-to-customer"></a>Kapcsolattartóból vevő

![Sablonleképezés az adatintegrátorban](./media/contacts-direct-template-mapping-data-integrator-2.png)


## <a name="related-topics"></a>Kapcsolódó témakörök

[A potenciális vevők készpénzre váltása](prospect-to-cash.md)

[A Supply Chain Management-ügyfelek közvetlen szinkronizálása a Sales-ügyfelekre](accounts-template-mapping-direct.md)

[A Supply Chain Management-termékek közvetlen szinkronizálása a Sales-termékekre](products-template-mapping-direct.md)

[Értékesítési rendelés szinkronizálása közvetlenül a Sales szolgáltatás és a Supply Chain Management szolgáltatás között](sales-order-template-mapping-direct-two-ways.md)

[Értékesítésiszámla-fejlécek és -sorok szinkronizálása közvetlenül a Supply Chain Management szolgáltatásból a Sales szolgáltatásba](sales-invoice-template-mapping-direct.md)




[!INCLUDE[footer-include](../../includes/footer-banner.md)]