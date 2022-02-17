---
title: Kölcsöncikkek létrehozása
description: A kölcsöncikkek olyan rekordok, amelyek segítik követni a dolgozóknak kölcsönzött fizikai cikkeket, például telefonokat vagy számítógépeket.
author: twheeloc
ms.date: 10/28/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: HcmLoanType, DefaultDashboard, HcmLoanItem, HcmWorkerLookUp, HcmPersonnelManagementWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 21127c46615015c30e06465b390f67b835e746cb
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/31/2022
ms.locfileid: "8068134"
---
# <a name="create-loan-items"></a>Kölcsöncikkek létrehozása


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



A kölcsöncikkek olyan rekordok, amelyek segítik követni a dolgozóknak kölcsönzött fizikai cikkeket, például telefonokat vagy számítógépeket. Minden fizikai cikknek rendelkeznie kell egy megfelelő kölcsöncikkel. Minden kölcsöncikk rekordnál le kell írni a kölcsönzött tételt, meg kell adni a kölcsönzésért felelős személyt, és a tétel kölcsönzési idejét (napokban). Ezzel egy időben több kölcsöncikk, például kulcsok, belépőkártyák vagy egyenruhák is létrehozhatók. Ez az eljárás az USMF bemutatócéget használja.


## <a name="create-loan-types"></a>Kölcsöntípus létrehozása
1. Menj **Emberi Erőforrások** > **Munkások** > **Kölcsön cikkek** > **Hiteltípusok**.
2. Kattintson az **Új** elemre.
3. Ban,-ben **Kölcsön típusa** mezőbe írjon be egy értéket.
4. Írjon egy értéket a **Leírás** mezőbe.
5. Adja meg azon napok számát, ahány nappal túlléphető a határidő az e kölcsöntípushoz rendelt cikkek esetében. 
6. Kattintson a **Mentés** gombra.
7. Zárja be a lapot.
8. Frissítse a lapot..

## <a name="create-loan-items"></a>Kölcsöncikkek létrehozása
1. Menj **Emberi Erőforrások** > **Munkások** > **Kölcsön cikkek** > **Kölcsön cikkek**.
2. Kattintson **Hitelelemek létrehozása**.
3. Ban,-ben **Menny.** mezőbe írjon be egy számot.
4. Írjon egy értéket a **Leírás** mezőbe.
5. Ban,-ben **Kölcsön típusa** mezőben kattintson a legördülő gombra a keresés megnyitásához.
6. A kívánt rekord megkeresése és kijelölése a listán
7. A listában kattintson a kijelölt sorban lévő hivatkozásra.
8. Adja meg, hogy hány napra kölcsönözhető a cikk.
    * A Kölcsönzött felszerelés oldal Tervezett visszakerülés mezőjének alapértelmezés szerinti értékét a rendszer az aktuális dátumból, plusz ebből a számból számítja ki.  
9. Ban,-ben **Felelős személy** mezőben kattintson a legördülő gombra a keresés megnyitásához.
10. Kattintson a **Kiválasztás** lehetőségre.
11. Ban,-ben **Kiinduló érték** mezőbe írjon be egy számot.
12. Az **Intervallum** mezőben adjon meg egy számot.
13. Ban,-ben **Formátum** mezőbe írjon be egy értéket.
    * Például, ha egy kölcsöncikk kezdőszáma 10, írjon be két számszimbólumot a **Formátum** terület.  
14. Kattintson az **OK** gombra.
15. Frissítse a lapot..



[!INCLUDE[footer-include](../includes/footer-banner.md)]
