---
title: A szabadságok vásárlásával és eladásával kapcsolatos irányelvek kezelése
description: Engedélyezheti az alkalmazottaknak, hogy vásárolják és eladják a szabadságukat a Dynamics 365 Human Resources alkalmazásban.
author: twheeloc
ms.date: 10/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LeaveBuySellPolicy, LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-06-01
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 23c743c29869f8c02ad67aa4b4fe54ec6ec0d016
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/04/2022
ms.locfileid: "8691554"
---
# <a name="manage-buy-and-sell-leave-policies"></a>Szabadság vásárlásával és eladásával kapcsolatos irányelv kezelése

>[!Important]
>Az ebben a témakörben említett funkciók jelenleg csak a különálló Dynamics 365 Human Resources rendszerében lévő vevőknek érhetők el. A funkciók egy része vagy egésze a Finance infrastruktúra jövőbeni kiadásának részeként lesz elérhető a Finance 10.0.26-ös kiadása után.


[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Engedélyezheti az alkalmazottaknak, hogy szabadságot vegyenek és adjanak el egy szabadságvásárlási és eladási irányelv létrehozásával. Ezeket a szabályokat konfigurálhatja úgy, hogy munkafolyamatot használjon jóváhagyásra, beállítsa a maximális összegeket és mértékeket, valamint megadhatja a beszerzési és eladási árat. 

## <a name="enable-employees-to-buy-and-sell-leave"></a>Szabadság vásárlásának és eladásának engedélyezése az alkalmazottak számára

1. A **Szabadság- és távollét** paraméterei oldalon válassza az **Igen** lehetőséget a **Szabadság eladásának engedélyezése az alkalmazottak számára** **Szabadság eladásának engedélyezése a munkavállalók számára** lehetőséget.

## <a name="create-a-buy-and-sell-leave-policy"></a>Szabadság vásárlási és eladási irányelv létrehozása

1. A **Szabadság és távollét** oldalon válassza a **Hivatkozások** lapot. 

2. Válassza ki a **Szabadságok vásárlásával és eladásával kapcsolatos irányelv** lehetőséget.

3. Válassza az **Új** lehetőséget.

4. Adja meg a **Név** és **Leírás** elemet a **Szabadságok vásárlásával és eladásával kapcsolatos irányelv** alatti irányelvhez. 

5. Válassza ki az **Irányelv típusa** lehetőséget. 

   A rendelkezésre álló irányelvtípusok az **Összeg** és az **Órák hetente**. Válassza ki az **Összeg** elemet egy **Rögzített szám** megadásához az alkalmazottak által vásárolható és eladható maximális összeg megadásához. Ha az **Órák hetente** lehetőséget választja, az alkalmazott hozzárendelt munkanaptárban megadott munkaidőt használja a program a maximális összeg megállapítására. 

6. Válassza ki a **Kezdő dátum** és **Záró dátum** lehetőséget az irányelv esetében. A vásárlásra vagy eladásra irányuló kérelem csak ebben az időkeretben érhető el elküldéshez. 

7. Válassza ki a házirend **Munkafolyamat-azonosítóját**. A vásárlási és eladási kérelmek ezt a munkafolyamatot használják áttekintés és jóváhagyás céljából. 

8. A **Vásárlási irányelv** alatt válassza a válassza ki a **Teljes munkaidő egyenérték** (FTE) lehetőséget a maximális összegnek az alkalmazott beosztásához megadott FTE alapján történő meghatározásához. Ha az irányelv típusa **Összeg**, adja meg a **Maximális rögzített összeg** értékét. 

9. Válassza a **Hozzáadás** lehetőséget azon alkalmazottak típusának megadásához, akik szabadságot vásárolhatnak. Az irányelvhez több szabadságtípust is hozzáadhat. 

10. Adja meg a szabadságtípus **Munkaviszony hossza hónapokban** elemét annak engedélyezéséhez, hogy a munkaviszony hossza hónapokban határozza meg a maximális összeget, amennyit egy alkalmazott vásárolhat. 

11. Adja meg a szabadságtípushoz a **Maximális összeg** elemet. 

12. Adja meg az **Arány** elemet, amely megadja a megvásárolható szabadság mértékét. 

13. Tetszés szerint adja meg a szabadságvásárláshoz használt **Bevételkódot**. 

14. Opcionálisan azt is beállíthatja, hogy az FTE használatával határozza meg a szabadságtípus maximális összegét. 

15. Értékesítési irányelv létrehozásához kövesse a 8–14. lépéseket az **Eladási irányelv** részben. 

## <a name="add-the-buy-and-sell-leave-policy-to-a-leave-and-absence-plan"></a>A szabadság vásárlásával és eladásával kapcsolatos irányelv hozzáadása egy szabadsági és távolléti tervhez

1. A **Szabadság és távollét** oldalon válasszon ki egy szabadság és távollét tervet.

2. A **Szabályok** alatt válassza ki a **Szabadságok vásárlásával és eladásával kapcsolatos irányelv** lehetőséget.

## <a name="see-also"></a>Lásd még

[Szabadság és távollét áttekintése](hr-leave-and-absence-overview.md)</br>
[Szabadság- és távolléttípusok konfigurálása](hr-leave-and-absence-types.md)</br>
[Szabadság- és távolléti tervek elhatárolása](hr-leave-and-absence-accrue.md)</br>
[Szabadság vásárlása és eladása](hr-employee-self-service-buy-sell-leave.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
