---
title: A szabadságok vásárlásával és eladásával kapcsolatos irányelvek kezelése
description: Engedélyezheti az alkalmazottaknak, hogy vásárolják és eladják a szabadságukat a Dynamics 365 Human Resources alkalmazásban.
author: andreabichsel
manager: AnnBe
ms.date: 06/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: LeaveBuySellPolicy, LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-06-01
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 859445f2b6e980b5960e512e69129f6a8fc6df2b
ms.sourcegitcommit: ba340f836e472f13f263dec46a49847c788fca44
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/04/2020
ms.locfileid: "3429013"
---
# <a name="manage-buy-and-sell-leave-policies"></a>A szabadságok vásárlásával és eladásával kapcsolatos irányelvek kezelése

[!include [banner](includes/preview-feature.md)]

Engedélyezheti az alkalmazottaknak, hogy szabadságot vegyenek egy szabadságvásárlási irányelv létrehozásával.  

## <a name="enable-employees-to-buy-and-sell-leave"></a>Szabadság vásárlásának és eladásának engedélyezése az alkalmazottak számára

1. A **Szabadság- és távollétparaméterek** oldalon válassza az **Igen** lehetőséget a **Szabadság vásárlásának engedélyezése az alkalmazottak számára** esetében. 

## <a name="create-a-buy-leave-policy"></a>Szabadságvásárlási irányelv létrehozása

1. A **Szabadság és távollét** oldalon válassza a **Hivatkozások** lapot. 

2. Válassza ki a **Szabadságok vásárlásával és eladásával kapcsolatos irányelv** lehetőséget.

3. Válassza az **Új** lehetőséget.

4. Adja meg a **Név** és **Leírás** elemet a **Szabadságok vásárlásával és eladásával kapcsolatos irányelv** alatti irányelvhez. 

5. Válassza ki az **Irányelv típusa** lehetőséget. 

   A rendelkezésre álló irányelvtípusok az **Összeg** és az **Órák hetente**. Válassza ki az **Összeg** elemet egy **Rögzített szám** megadásához az alkalmazottak által vásárolható és eladható maximális összeg megadásához. Ha az **Órák hetente** lehetőséget választja, az alkalmazott hozzárendelt munkanaptárban megadott munkaidőt használja a program a maximális összeg megállapítására. 

6. Válassza ki a **Kezdő dátum** és **Záró dátum** lehetőséget az irányelv esetében. A vásárlásra vagy eladásra irányuló kérelem csak ebben az időkeretben érhető el elküldéshez. 

7. A **Vásárlási irányelv** alatt válassza a válassza ki a **Teljes munkaidő egyenérték** (FTE) lehetőséget a maximális összegnek az alkalmazott beosztásához megadott FTE alapján történő meghatározásához. Ha az irányelv típusa **Összeg**, adja meg a **Maximális rögzített összeg** értékét. 

8. Válassza a **Hozzáadás** lehetőséget azon alkalmazottak típusának megadásához, akik szabadságot vásárolhatnak. Az irányelvhez több szabadságtípust is hozzáadhat. 

9. Adja meg a szabadságtípus **Munkaviszony hossza hónapokban** elemét annak engedélyezéséhez, hogy a munkaviszony hossza hónapokban határozza meg a maximális összeget, amennyit egy alkalmazott vásárolhat. 

10. Adja meg a szabadságtípushoz a **Maximális összeg** elemet. 

11. Adja meg az **Arány** elemet, amely megadja a megvásárolható szabadság mértékét. 

12. Tetszés szerint adja meg a szabadságvásárláshoz használt **Bevételkódot**. 

13. Opcionálisan azt is beállíthatja, hogy az FTE használatával határozza meg a szabadságtípus maximális összegét. 

## <a name="add-the-buy-and-sell-leave-policy-to-a-leave-and-absence-plan"></a>A szabadság vásárlásával és eladásával kapcsolatos irányelv hozzáadása egy szabadsági és távolléti tervhez

1. A **Szabadság és távollét** oldalon válasszon ki egy szabadság és távollét tervet.

2. A **Szabályok** alatt válassza ki a **Szabadságok vásárlásával és eladásával kapcsolatos irányelv** lehetőséget.

## <a name="see-also"></a>Lásd még

[Szabadság és távollét áttekintése](hr-leave-and-absence-overview.md)</br>
[Szabadság- és távolléttípusok konfigurálása](hr-leave-and-absence-types.md)</br>
[Szabadság- és távolléti tervek elhatárolása](hr-leave-and-absence-accrue.md)</br>
[Szabadság vásárlása és eladása](hr-employee-self-service-buy-sell-leave.md)

