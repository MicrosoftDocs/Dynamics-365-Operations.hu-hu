---
title: "A termékek szinkronizálása Sales-termékekre közvetlenül a Finance and Operations szolgáltatásból"
description: "Ez a témakör azokat a sablonokat és kapcsolódó feladatokat mutatja be, melyek a Microsoft Dynamics 365 for Finance and Operations és a Microsoft Dynamics 365 for Sales közötti termékszinkronizálásra használhatók."
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
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: 3ae50372edcd473f2288f8172b71eac33e24b636
ms.contentlocale: hu-hu
ms.lasthandoff: 03/26/2018

---

# <a name="synchronize-products-directly-from-finance-and-operations-to-products-in-sales"></a>A Finance and Operations-termékek közvetlen szinkronizálása a Sales-termékekre

[!INCLUDE [banner](../includes/banner.md)]

> [!NOTE]
> A potenciális ügyfelek készpénzre váltása megoldás használata előtt meg kell ismernie: [Dynamics 365 integráció](/common-data-service/entity-reference/dynamics-365-integration).

Ez a témakör azokat a sablonokat és kapcsolódó feladatokat mutatja be, melyek a Microsoft Dynamics 365 for Finance and Operations és a Microsoft Dynamics 365 for Sales közötti közvetlen termékszinkronizálásra használhatók.

## <a name="data-flow-in-prospect-to-cash"></a>A potenciális ügyfelek készpénzre váltása adatfolyama

A potenciális ügyfelek készpénzre váltása megoldás az adatszinkronizálás funkción keresztül szinkronizálja az adatokat Finance and Operations and Sales példányai között. Az Adatintegrációs szolgáltatásban rendelkezésre álló A potenciális ügyfelek készpénzre váltása sablonok lehetővé teszik a termék-, ügyfél-, kapcsolatfelvételi és eladási számlákra vonatkozó adatok áramlását a Finance and Operations és a Sales között. A következő ábra bemutatja a Finance and Operations és a Sales közötti adatszinkronizálást.

[![A potenciális ügyfelek készpénzre váltása adatfolyama](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)

## <a name="templates-and-tasks"></a>Sablonok és feladatok

A rendelkezésre álló sablonok megtekintéséhez nyissa meg a [PowerApps Admin Centert](https://preview.admin.powerapps.com/dataintegration). Válassza a **Projektek** lehetőséget, és ezután kattintson a jobb felső sarkában az **Új projekt** elemre a nyilvános sablonok kiválasztásához.

A következő sablonokat és alapul szolgáló feladatokat használják a termékek szinkronizálásához a Finance and Operations és a Sales között:

- **Sablon neve az adatintegrációban:** Termékek (Fin and Ops – Sales) – Közvetlen
- **A feladat neve az adatintegrációs projektben:** Termékek

Szinkronizálási feladat nem szükséges a fiókszinkronizálás előtt.

## <a name="entity-set"></a>Entitás beállítása

| Finance and Operations     | Értékesítés    |
|----------------------------|----------|
| Értékesíthető kiadott termékek | Termékek |

## <a name="entity-flow"></a>Entitás folyamata

A termékek kezelése a Finance and Operationsben történik, majd szinkronizálás történik a Sales programmal. A Finance and Operations **Értékesíthető kiadott termékek** adatentitása csak *értékesíthető* termékeket exportál. Az értékesíthető termékek olyan termékek, amelyek rendelkeznek az általuk megkövetelt információkkal annak érdekében, hogy azokat értékesítési rendelésekben használják. Ugyanazok a szabályok vonatkoznak, ha egy termék ellenőrizve van az **Érvényesítés** funkcióval a **Kiadott termék** oldalon.

A termékszám kulcsként használható. Ezért ha a termékváltozatok szinkronizálásra kerülnek a Sales-szel, minden termékváltozat egyedi termékazonosítóval rendelkezik.

## <a name="prospect-to-cash-solution-for-sales"></a>Potenciális vevő értékesítési készpénzfizetési megoldáshoz

A Sales szolgáltatásba az új **Külsőleg karbantartott** mező került a termékekhez, amely azt jelzi, hogy a terméket külsőleg tartják karban. Az érték alapértelmezésben **Igen** a Sales-be való importálás során. A következő értékek állnak rendelkezésre:

- **Igen** – A termék a Finance and Operations szolgáltatásból származik, és nem lesz szerkeszthető a Sales szolgáltatásban.
- **Nem** – A terméket közvetlenül a Sales szolgáltatásban adták meg.
- **(Üres)** – A termék már létezett a Sales szolgáltatásban a Potenciális ügyfelek készpénzre váltása engedélyezése előtt.

A **Külsőleg karbantartott** mező segít annak garantálásában, hogy csak azok az árajánlatok és értékesítési megbízások, amelyek külsőleg karbantartott termékeket tartalmaznak, szinkronizálnak a Finance and Operations szolgáltatással.

Külsőleg karbantartása termékek a program automatikusan hozzáadja az első érvényes árlista, ugyanabban a pénznemben. Az árlisták betűrendben, név szerint vannak rendezve. A Finance and Operations termékeladási ára egyben az árlistán szereplő ár. Ezért győződjön meg arról, hogy tartozik árlista minden egyes Sales termékeladási pénznemhez a Finance and Operations szolgáltatásban. A felszabadított, eladható termékek pénznemét a jogi személy számviteli pénznemére kell beállítani, ahonnan a terméket exportálják.

> [!NOTE]
> A termékszinkronizálás nem fog sikerülni, hacsak nem létezik olyan árlista, amelynek megfelelő pénzneme van.

## <a name="preconditions-and-mapping-setup"></a>Előfeltételek és hozzárendelési beállítás

- Mielőtt először futtatná a szinkronizálást, töltse ki az Egyedi terméktáblázatot a Finance and Operations meglévő termékeihez. A feladat befejezéséig nem lesznek szinkronizálva a meglévő termékek.

    1. A Finance and Operations esetén akkor a keresés kereséséhez **feltöltése egyedi termék tábla**.
    2. Válassza az **Egyedi termék tábla feltöltése** lehetőséget a feladat futtatásához. Ez a feladat csak egyszer futtatható.

- Győződjön meg róla, hogy megvan a szükséges értékhozzárendelés az értékesítési mértékegységre vonatkozóan a Finance and Operations és a Sales között a **SalesUnitSymbol** **DefaultUnit (Name)** leképezésénél.
- Frissítse az **Egységcsoport** (**defaultuomscheduleid.name**) értékleképezését, hogy megegyezzen az **Egységcsoportok** értékével a Sales-ben.

    A sablon alapértéke az **Alapértelmezett egység**.

- Győződjön meg arról, hogy az összes termék értékesítési mértékegysége a Finance and Operations szolgáltatásból létezik a Sales szolgáltatásban is.
- Győződjön meg arról, hogy árlisták a Finance and Operations minden termékeladási pénzneméhez léteznek a Sales szolgáltatásban.
- Amikor létrejönnek a termékek a Sales szolgáltatásban, akkor állapotuk **Sablon** vagy **Aktív** lehet. A viselkedés ellenőrzése a **Beállítások** > **Felügyelet** > **Tendszerbeállítások** > **Értékesítés** pontban történik a Sales szolgáltatásban.

    A létrehozásukkor **Vázlat** állapotú termékeket aktiválni kell, mielőtt azok hozzáadhatók lennének az árajánlatokhoz vagy az értékesítési rendelésekhez.

## <a name="template-mapping-in-data-integration"></a>Sablonleképezés az adatintegrátorban

Az alábbi ábrán sablon hozzárendelést például adatok integrátor megjelenítése. 

> [!NOTE]
> A leképezést mutatja, hogy melyik mezőadatok szinkronizálódnak a Sales – Finance and Operations irányban.

![Sablonleképezés az adatintegrátorban](./media/products-direct-template-mapping-data-integrator-1.png)


## <a name="related-topics"></a>Kapcsolódó témakörök

[A potenciális ügyfelek készpénzre váltása](prospect-to-cash.md)

[A Sales-számlák közvetlen szinkronizálása a Finance and Operations-ügyfelekre](accounts-template-mapping-direct.md)

[A Sales-kapcsolatok közvetlen szinkronizálása a Finance and Operations-kapcsolatokra vagy -ügyfelekre](contacts-template-mapping-direct.md)

[Értékesítésirendelés-fejlécek és -sorok szinkronizálása közvetlenül a Finance and Operations szolgáltatásból a Sales szolgáltatásba](sales-order-template-mapping-direct-two-ways.md)

[Értékesítésiszámla-fejlécek és -sorok közvetlen szinkronizálása a Finance and Operations szolgáltatásból a Sales szolgáltatásba](sales-invoice-template-mapping-direct.md)




