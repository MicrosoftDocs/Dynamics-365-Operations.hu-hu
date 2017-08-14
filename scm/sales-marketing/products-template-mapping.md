---
title: "A Finance and Operations-termékek szinkronizálása a Sales-termékekre"
description: "Ez a témakör azokat a sablonokat és kapcsolódó feladatokat mutatja be, melyek a Microsoft Dynamics 365 for Finance and Operations, Enterprise edition és a Microsoft Dynamics 365 for Sales közötti szinkronizálásra használhatók."
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
ms.openlocfilehash: 2f14b06b57930256f9211f2085512aa589df083e
ms.contentlocale: hu-hu
ms.lasthandoff: 07/27/2017

---

# <a name="synchronize-products-from-finance-and-operations-to-products-in-sales"></a>A Finance and Operations-termékek szinkronizálása a Sales-termékekre

[!include[banner](../includes/banner.md)]

> [!NOTE]
> A potenciális vevő készpénzfizetési Solution használata előtt meg kell ismernie: [Dynamics 365 adatintegráció](https://docs.microsoft.com/en-us/common-data-service/entity-reference/dynamics-365-integration). 

Ez a témakör azokat a sablonokat és kapcsolódó feladatokat mutatja be, melyek a Microsoft Dynamics 365 for Finance and Operations, Enterprise edition és a Microsoft Dynamics 365 for Sales közötti szinkronizálásra használhatók.

## <a name="template-and-task"></a>Sablon és feladat

A következő sablonok és kapcsolódó feladatok a Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (Finance and Operations) és a Microsoft Dynamics 365 for Sales (Sales) közötti szinkronizálásra használhatók.

-   Sablon neve: Termékek (Fin and Ops – Sales)

-   A projektben lévő feladat neve: Termékek

Szinkronizálási feladatok szükségessége a termékszinkronizálás előtt: Nincs

## <a name="entity-set"></a>Entitás beállítása

| **Finance and Operations** | **CDS** | **Értékesítések**  |
|----------------------------|---------|------------|
| Értékesíthető kiadott termékek | Termék | Termékek   |

## <a name="entity-flow"></a>Entitás folyamata

A termékek kezelése a Finance and Operationsben történik, majd szinkronizálás történik a Sales programmal. A Finance and Operations **Értékesíthető kiadott termékek** adatentitása csak olyan termékeket exportál, amelyek eladhatók, ami azt jelenti, hogy a termékek rendelkeznek az értékesítési rendeléshez szükséges információkkal. Ugyanazok a szabályok vonatkoznak, ha egy termék ellenőrizve a **érvényesítése** működni a **megjelent termék** oldalon.

A **termékszám** szolgál a kulcs, ami azt jelenti, változatok CD-és értékesítési szinkronizálta egyedi termék **termék azonosítók** / **termékváltozat**.

## <a name="prospect-to-cash-solution-for-sales"></a>Potenciális vevő értékesítési készpénzfizetési megoldáshoz

Az értékesítési, a termékek új mezőt **külsőleg megmarad** hozzáadódik jelezheti, hogy egy adott termék külsőleg tarthatók karban. Az érték **Igen** értékesítési importálás során alapértelmezés szerint.

-   **Külsőleg karbantartani van = Yes**: termék származik, pénzügyi és a műveletek, és nem lesz szerkeszthető az értékesítésben.

-   **Külsőleg karbantartani van = nem**: termék közvetlenül az értékesítési kerül.

-   **Külsőleg karbantartani van = üres**: termék létezik az értékesítésben a potenciális vevő készpénzfizetési Solution engedélyezése előtt.

A **külsőleg megmarad** adatok annak biztosítására, hogy csak a **ajánlatok** és **értékesítési rendelések** tartalmazó **külsőleg karbantartása termékek** késedelmi a műveletekhez pedig szinkronizálja.

**Külsőleg karbantartása termékek** a program automatikusan hozzáadja az első érvényes **árlista**, ugyanabban a pénznemben. Megjegyzés: a lista betűrend szerint vannak rendezve **neve**. Pénzügy és a műveletek a termék eladási ára ár egyben az a **árlista**. Ez azt jelenti, hogy szükséges a **árlista** minden egyes értékesítési **termék értékesítési pénznem** Finance and Operationset. A kiadott termékhez árusítási pénznem a jogi személynél, amelyből a termék exportálja a könyvelési pénznemben van beállítva.

> [!NOTE]
> Termék szinkronizálás nélkül nem fog sikerülni egy **árlista** a megfelelő pénznemben.

## <a name="preconditions-and-mapping-setup"></a>Előfeltételek és hozzárendelési beállítás

-   Mielőtt futtatná a legelső szinkronizálás, ki kell tölteni a **egyedi termék tábla** pénzügyi és a műveletek a meglévő termékek. Ez a feladat befejezéséig nem lesz szinkronizálva meglévő terméken.

    -   A Finance and Operations esetén akkor a keresés kereséséhez **feltöltése egyedi termék tábla**.

    -   Kattintson az **Egyedi termék tábla feltöltése** lehetőségre a feladat futtatásához. Ezt a feladatot csak egyszer kell futtatni.

-   Győződjön meg arról, hogy a szükséges **ValueMap** értékesítési **mértékegység** (Mértékegységet) Finance and Operations szerepel a **forrás -\> SalesUnitSymbol leképezése CD / DefaultSellingUnitOfMeasure**.

-   Győződjön meg arról, hogy **tizedesjegyek** mértékegység a saját igényeinek a **CD -\> cél**. Ha különböző értékeket a mértékegység van szüksége, ez nem végezhető **ValueMap** egységtől, például [minden: 0] & [font: 2].

    -   A sablon alapértéke 0.

-   CD szervezeti azonosító frissítése: **Organization_OrganizationId** található a **forrás \>CD** hozzárendelés.

    -   A sablon alapértéke ORG001.

-   Frissítés **ValueMap** a **egység csoport** (**defaultuomscheduleid.name**) a **CD -\> cél** megfelelően a **csoportjai** értékesítési.

    -   A sablon alapértéke az **Alapértelmezett egység**.

-   Ellenőrizze, hogy az összes termék UOMs eladási késedelmi és műveletek értékesítés szerepel-e a **CD választási listák** értéke.

-   Győződjön meg arról, hogy **árlisták** minden egyes pénznemhez termék eladási késedelmi és műveletek értékesítési szerepel.

-   Termékek hozhatja létre az értékesítési állapot **"vázlat"** vagy **aktív**. Ez **rendszerbeállítások** alapján **értékesítési** értékesítés.

    -   Vázlat állapotú létrehozott termékeket kell aktiválni kell, mielőtt azok adhatók hozzá **ajánlat** vagy **eladási rendelés**.

## <a name="template-mapping-in-data-integrator"></a>Sablonleképezés az adatintegrátorban

Az alábbi ábrákon sablon hozzárendelést például adatok integrátor megjelenítése.

![sablonleképezés az adatintegrátorban](./media/products-template-mapping-data-integrator-1.png)

![sablonleképezés a termékekhez az adatintegrátorban](./media/products-template-mapping-data-integrator-2.png)

## <a name="related-topics"></a>Kapcsolódó témakörök

[A Sales-számlák szinkronizálása a Finance and Operations-ügyfelekre](accounts-template-mapping.md)

[A Sales-kapcsolatok szinkronizálása a Finance and Operations-kapcsolatokra vagy -ügyfelekre](contacts-template-mapping.md)

[Értékesítésiajánlat-fejlécek és -sorok szinkronizálása a Sales szolgáltatásból a Finance and Operations szolgáltatásba](sales-quotation-template-mapping.md)


