---
title: A Supply Chain Management-termékek közvetlen szinkronizálása a Sales-termékekre
description: Ez a témakör bemutatja a sablonokat és a mögöttes feladatokat, amelyek a Dynamics 365 Supply Chain Management termékeinek közvetlenül a Dynamics 365 Sales szolgáltatásba történő szinkronizálására használatosak.
author: ChristianRytt
ms.date: 06/10/2019
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
ms.openlocfilehash: 576516e17f015e33ca54bb6beceec43158bee79cfb7bd9a2db132085674bc035
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6742656"
---
# <a name="synchronize-products-directly-from-supply-chain-management-to-products-in-sales"></a>A Supply Chain Management-termékek közvetlen szinkronizálása a Sales-termékekre

[!include [banner](../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

> [!NOTE]
> A potenciális ügyfelek készpénzre váltása megoldás használata előtt meg kell ismernie az [Adatintegrálással a Microsoft Dataverse for Apps szolgáltatásban](/powerapps/administrator/data-integrator).

Ez a témakör bemutatja a sablonokat és a mögöttes feladatokat, amelyek a Dynamics 365 Supply Chain Management termékeinek közvetlenül a Dynamics 365 Sales szolgáltatásba történő szinkronizálására használatosak.

## <a name="data-flow-in-prospect-to-cash"></a>A potenciális ügyfelek készpénzre váltása adatfolyama

A potenciális ügyfelek készpénzre váltása megoldás az adatszinkronizálás funkción keresztül szinkronizálja az adatokat Supply Chain Management és a Sales példányai között. Az Adatintegrációs szolgáltatásban rendelkezésre álló A potenciális ügyfelek készpénzre váltása sablonok lehetővé teszik a termék-, ügyfél-, kapcsolatfelvételi és eladási számlákkal kapcsolatos adatok áramlását a Supply Chain Management és a Sales között. A következő ábra bemutatja a Supply Chain Management és a Sales közötti adatszinkronizálást.

[![A potenciális ügyfelek készpénzre váltása adatfolyama.](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)

## <a name="templates-and-tasks"></a>Sablonok és feladatok

A rendelkezésre álló sablonok megtekintéséhez nyissa meg a [Power Apps Admin Centert](https://admin.powerapps.com/dataintegration). Válassza a **Projektek** lehetőséget, és ezután kattintson a jobb felső sarkában az **Új projekt** elemre a nyilvános sablonok kiválasztásához.

A következő sablonokat és alapul szolgáló feladatokat használják a termékek szinkronizálásához a Supply Chain Management és a Sales között:

- **Sablon neve az adatintegrációban:** Termékek (Supply Chain Management – Sales) – Közvetlen
- **A feladat neve az adatintegrációs projektben:** Termékek

Szinkronizálási feladat nem szükséges a fiókszinkronizálás előtt.

## <a name="entity-set"></a>Entitás beállítása

| Ellátásilánc-kezelés    | Értékesítés    |
|----------------------------|----------|
| Értékesíthető kiadott termékek | Termékek |

## <a name="entity-flow"></a>Entitás folyamata

A termékek kezelése a Supply Chain Management történik, majd szinkronizálódnak a Sales programban. A Supply Chain Management **Értékesíthető kiadott termékek** adatentitása csak *értékesíthető* termékeket exportál. Az értékesíthető termékek olyan termékek, amelyek rendelkeznek az általuk megkövetelt információkkal annak érdekében, hogy azokat értékesítési rendelésekben használják. Ugyanazok a szabályok vonatkoznak, ha egy termék ellenőrizve van az **Érvényesítés** funkcióval a **Kiadott termék** oldalon.

A termékszám kulcsként használható. Ezért ha a termékváltozatok szinkronizálásra kerülnek a Sales-szel, minden termékváltozat egyedi termékazonosítóval rendelkezik.

## <a name="prospect-to-cash-solution-for-sales"></a>Potenciális vevő értékesítési készpénzfizetési megoldáshoz

A Sales szolgáltatásba az új **Külsőleg karbantartott** mező került a termékekhez, amely azt jelzi, hogy a terméket külsőleg tartják karban. Az érték alapértelmezésben **Igen** a Sales-be való importálás során. A következő értékek állnak rendelkezésre:

- **Igen** – A termék a Supply Chain Management szolgáltatásból származik, és nem lesz szerkeszthető a Sales szolgáltatásban.
- **Nem** – A terméket közvetlenül a Sales szolgáltatásban adták meg.
- **(Üres)** – A termék már létezett a Sales szolgáltatásban a Potenciális ügyfelek készpénzre váltása engedélyezése előtt.

A **Külsőleg karbantartott** mező segít annak garantálásában, hogy csak azok az árajánlatok és értékesítési megbízások, amelyek külsőleg karbantartott termékeket tartalmaznak, szinkronizálnak a Supply Chain Management szolgáltatással.

Külsőleg karbantartása termékek a program automatikusan hozzáadja az első érvényes árlista, ugyanabban a pénznemben. Az árlisták betűrendben, név szerint vannak rendezve. A Supply Chain Management termékeladási ára egyben az árlistán szereplő ár. Ezért győződjön meg arról, hogy tartozik árlista minden egyes Sales termékeladási pénznemhez a Supply Chain Management szolgáltatásban. A felszabadított, eladható termékek pénznemét a jogi személy számviteli pénznemére kell beállítani, ahonnan a terméket exportálják.

> [!NOTE]
> - A termékszinkronizálás nem fog sikerülni, hacsak nem létezik olyan árlista, amelynek megfelelő pénzneme van.
> - A használt árlista az integrációval szabályozható a pricelevelid.name [alapértelmezett árlista (név)] leképezésével az adatintegrációs projektben. A beírásnál csak kisbetűk használhatók. Például a „Szabványos” nevű értékesítési árlista alapértelmezetten ez lenne: Célmező: pricelevelid.name [alapértelmezett árlista (név)] és Leképezés típusa: [ { "transformType": "Default", "defaultValue": "standard" } ].

## <a name="preconditions-and-mapping-setup"></a>Előfeltételek és hozzárendelési beállítás

- Mielőtt először futtatná a szinkronizálást, töltse ki az Egyedi terméktáblázatot a Supply Chain Management meglévő termékeihez. A feladat befejezéséig nem lesznek szinkronizálva a meglévő termékek.

    1. A Supply Chain Management esetén akkor a keresés kereséséhez **feltöltése egyedi termék tábla**.
    2. Válassza az **Egyedi termék tábla feltöltése** lehetőséget a feladat futtatásához. Ez a feladat csak egyszer futtatható.

- Győződjön meg róla, hogy megvan a szükséges értékhozzárendelés az értékesítési mértékegységre vonatkozóan a Supply Chain Management és a Sales között a **SalesUnitSymbol** **DefaultUnit (Name)** leképezésénél.
- Frissítse az **Egységcsoport** (**defaultuomscheduleid.name**) értékleképezését, hogy megegyezzen az **Egységcsoportok** értékével a Sales-ben.

    A sablon alapértéke az **Alapértelmezett egység**.

- Győződjön meg arról, hogy az összes termék értékesítési mértékegysége a Supply Chain Management szolgáltatásból létezik a Sales szolgáltatásban is.
- Győződjön meg arról, hogy árlisták a Supply Chain Management minden termékeladási pénzneméhez léteznek a Sales szolgáltatásban.
- Amikor létrejönnek a termékek a Sales szolgáltatásban, akkor állapotuk **Sablon** vagy **Aktív** lehet. A viselkedés ellenőrzése a **Beállítások** > **Felügyelet** > **Tendszerbeállítások** > **Értékesítés** pontban történik a Sales szolgáltatásban.

    A létrehozásukkor **Vázlat** állapotú termékeket aktiválni kell, mielőtt azok hozzáadhatók lennének az árajánlatokhoz vagy az értékesítési rendelésekhez.

## <a name="template-mapping-in-data-integration"></a>Sablonleképezés az adatintegrátorban

Az alábbi ábrán sablon hozzárendelést például adatok integrátor megjelenítése. 

> [!NOTE]
> A leképezést mutatja, hogy melyik mezőadatok szinkronizálódnak a Sales – Supply Chain Management irányban.

![Sablonleképezés az adatintegrátorban.](./media/products-direct-template-mapping-data-integrator-1.png)


## <a name="related-topics"></a>Kapcsolódó témakörök

[Potenciális vevők készpénzre váltása](prospect-to-cash.md)

[A Supply Chain Management-ügyfelek közvetlen szinkronizálása a Sales-ügyfelekre](accounts-template-mapping-direct.md)

[A Sales-kapcsolatok közvetlen szinkronizálása a Supply Chain Management-kapcsolatokra vagy -ügyfelekre](contacts-template-mapping-direct.md)

[Értékesítési rendelés szinkronizálása közvetlenül a Sales szolgáltatás és a Supply Chain Management szolgáltatás között](sales-order-template-mapping-direct-two-ways.md)

[Értékesítésiszámla-fejlécek és -sorok szinkronizálása közvetlenül a Supply Chain Management szolgáltatásból a Sales szolgáltatásba](sales-invoice-template-mapping-direct.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]