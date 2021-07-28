---
title: A Supply Chain Management-ügyfelek közvetlen szinkronizálása a Sales-ügyfelekre
description: Ez a témakör bemutatja a sablonokat és a mögöttes feladatokat, amelyek a Dynamics 365 Sales ügyfelek a Supply Chain Management alkalmazásba szinkronizálására használatosak.
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
ms.openlocfilehash: 270d83552a3e35042c32cb85888439d40068ff0c
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/06/2021
ms.locfileid: "6355949"
---
# <a name="synchronize-accounts-directly-from-sales-to-customers-in-supply-chain-management"></a>A Supply Chain Management-ügyfelek közvetlen szinkronizálása a Sales-ügyfelekre

[!include [banner](../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

> [!NOTE]
> A potenciális ügyfelek készpénzre váltása megoldás használata előtt meg kell ismernie az [Adatintegrálással a Microsoft Dataverse for Apps szolgáltatásban](/powerapps/administrator/data-integrator).

Ez a témakör bemutatja a sablonokat és a mögöttes feladatokat, amelyek a Dynamics 365 Sales ügyfeleinek köztvetlenül a Dynamics 365 Supply Chain Management alkalmazásba történő szinkronizálására használatosak.

## <a name="data-flow-in-prospect-to-cash"></a>A potenciális ügyfelek készpénzre váltása adatfolyama

A potenciális ügyfelek készpénzre váltása megoldás az adatszinkronizálás funkción keresztül szinkronizálja az adatokat Supply Chain Management és a Sales példányai között.  Az Adatintegrációs szolgáltatásban rendelkezésre álló A potenciális ügyfelek készpénzre váltása sablonok lehetővé teszik a termék-, ügyfél-, kapcsolatfelvételi és eladási számlákkal kapcsolatos adatok áramlását a Supply Chain Management és a Sales között. A következő ábra bemutatja a Supply Chain Management és a Sales közötti adatszinkronizálást.

[![A potenciális ügyfelek készpénzre váltása adatfolyama.](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)

## <a name="templates-and-tasks"></a>Sablonok és feladatok

A rendelkezésre álló sablonok megtekintéséhez nyissa meg a [Power Apps Admin Centert](https://preview.admin.powerapps.com/dataintegration). Válassza a **Projektek** lehetőséget, és ezután kattintson a jobb felső sarkában az **Új projekt** elemre a nyilvános sablonok kiválasztásához.

A következő sablonokat és alapul szolgáló feladatot használják a termékek szinkronizálásához a Sales és a Supply Chain Management között:

- **Sablon neve az adatintegrációban:** Fiókok (Sales – Fin and Ops) – Közvetlen
- **A feladat neve a projektben:** Fiókok – Vevők

Szinkronizálási feladat nem szükséges a Számla/ügyfél szinkronizálás előtt.

## <a name="entity-set"></a>Entitás beállítása

| Értékesítés    | Ellátásilánc-kezelés |
|----------|------------------------|
| Számlák | Vevők V2           |

## <a name="entity-flow"></a>Entitás folyamata

Az ügyfelek kezelése a Salesben történik, majd szinkronizálódnak a Supply Chain Management alkalmazásban ügyfélként. A **Külsőleg karbantartott** tulajdonságának beállítása ezeknél az ügyfeleknél **Igen** a Sales szolgáltatásból érkező vevők nyomon követésére. A számlázás során a adatok szinkronizálva vannak-e az értékesítési számlák szűréséhez.

## <a name="prospect-to-cash-solution-for-sales"></a>Potenciális vevő értékesítési készpénzfizetési megoldáshoz

A **számlaszám** oszlop akkor érhető el a **számla** oldalon. Tették integráláshoz a természetes és egyedi kulcs. A vevői kapcsolatkezelés (CRM) megoldás természetes kulcs funkciója hatással lehet a vevőkre, akik már használják a **számlaszám** oszlopot, de nem használják az egyedi **számlaszám** értéket számlánként. Az integrációs megoldás jelenleg ebben az esetben nem támogatja.

Új számla létrehozása esetén, ha egy **számlaszám** értéke nem létezik, szerint egy számsorozat alapján automatikusan történik. Az érték áll **számlás**, amelyet egy növekvő számsorozat és utótag hat karakterből követ. Íme, egy példa: **ACC-01000-BVRCPS**

A Sales integrációs megoldásának használatakor egy frissítési parancsfájl beállítja a **Számlaszám** oszlopot a létező számlákhoz a Salesben. Ha nem **Számlaszám** értékeit, a számsorozatot, amely a fentebb leírt használatos.

## <a name="preconditions-and-mapping-setup"></a>Előfeltételek és hozzárendelési beállítás

- A **CustomerGroupId** leképezést frissíteni kell a Supply Chain Management egy érvényes értékére. Meghatározhat egy alapértelmezett értéket, vagy az érték beállítható egy Értékmegfeleltetés használatával.

    Az alapértelmezett sablonérték **10**.

- A következő hozzárendelésének eltávolítása hozzáadásával CD cél, segítséget nyújthat manuális, amelyek szükségesek a Supply Chain Management számának csökkentésével lehetséges. Használhatja az alapértelmezett értékek vagy hozzárendelése, például **ország/régió** vagy **Város**.

    - **SiteId** – hely a Supply Chain Management árajánlatok és értékesítési rendelések sorainak létrehozásához szükséges. Alapértelmezett webhely készíthetők a terméket, vagy a vevő a rendelés fejlécében.

        Az alapértelmezett sablonérték **1**.

    - **WarehouseId** – hely a raktár és műveletek árajánlatok és értékesítési rendelések sorainak létrehozásához szükségesek Supply Chain Management alkalmazásban. Alapértelmezett raktár készíthető a termék vagy a vevő a rendelés fejlécében a Supply Chain Management programban.

        Az alapértelmezett sablonérték **13**.

    - **LanguageId** – Egy nyelv a Supply Chain Management árajánlatok és értékesítési rendelések létrehozásához szükséges. Alapértelmezés szerint a vevő a rendelés fejlécéből a nyelvet használja.

        Az alapértelmezett sablonérték **en-us**.

## <a name="template-mapping-in-data-integration"></a>Sablonleképezés az adatintegrátorban

> [!NOTE]
> A **fizetési feltételek**, **feltételek áruszállítási**, **szállítási feltételek**, **szállítási mód**, és **szállítási mód** oszlopok nem szerepelnek a alapértelmezett-leképezései. Ezen oszlopok megfeleltetéséhez be kell állítania egy értékmegfeleltetést, amely az adott szervezetek adataira specifikus, amelyek között a tábla szinkronizálódik.

Az alábbi ábrákon sablon hozzárendelést például adatok integrátor megjelenítése. 

> [!NOTE]
> A leképezést mutatja, hogy melyik oszlopadatok szinkronizálódnak a Sales – Supply Chain Management irányban.

![Sablonleképezés az adatintegrátorban.](./media/accounts-direct-template-mapping-data-integrator-1.png)

## <a name="related-topics"></a>Kapcsolódó témakörök


[Potenciális vevők készpénzre váltása](prospect-to-cash.md)

[A Supply Chain Management-ügyfelek közvetlen szinkronizálása a Sales-ügyfelekre](accounts-template-mapping-direct.md)

[A Sales-kapcsolatok közvetlen szinkronizálása a Supply Chain Management-kapcsolatokra vagy -ügyfelekre](contacts-template-mapping-direct.md)

[Értékesítési rendelés szinkronizálása közvetlenül a Sales szolgáltatás és a Supply Chain Management szolgáltatás között](sales-order-template-mapping-direct-two-ways.md)

[Értékesítésiszámla-fejlécek és -sorok szinkronizálása közvetlenül a Supply Chain Management szolgáltatásból a Sales szolgáltatásba](sales-invoice-template-mapping-direct.md)



[!INCLUDE[footer-include](../../includes/footer-banner.md)]