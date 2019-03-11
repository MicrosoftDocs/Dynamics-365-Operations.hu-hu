---
title: Kölcsöncikkek létrehozása
description: A kölcsöncikkek olyan rekordok, amelyek segítik követni a dolgozóknak kölcsönzött fizikai cikkeket, például telefonokat vagy számítógépeket.
author: kherr75
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HcmLoanType, DefaultDashboard, HcmLoanItem, HcmWorkerLookUp
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e17005bda302c58f5a6560fe9c4eda04e918c92f
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "341833"
---
# <a name="create-loan-items"></a>Kölcsöncikkek létrehozása

[!include [task guide banner](../../includes/task-guide-banner.md)]

A kölcsöncikkek olyan rekordok, amelyek segítik követni a dolgozóknak kölcsönzött fizikai cikkeket, például telefonokat vagy számítógépeket. Minden fizikai cikknek rendelkeznie kell egy megfelelő kölcsöncikkel. Minden kölcsöncikk rekordnál le kell írni a kölcsönzött tételt, meg kell adni a kölcsönzésért felelős személyt, és a tétel kölcsönzési idejét (napokban). Ezzel egy időben több kölcsöncikk, például kulcsok, belépőkártyák vagy egyenruhák is létrehozhatók. Ez az eljárás az USMF bemutatócéget használja.


## <a name="create-loan-types"></a>Kölcsöntípus létrehozása
1. Ugorjon az Emberi erőforrások > Dolgozók > Kölcsöncikkek > Kölcsöntípusok lehetőségre.
2. Kattintson az Új lehetőségre.
3. Írjon be egy értéket a Kölcsön típusa mezőbe.
4. A Leírás mezőben adjon meg egy értéket.
5. Adja meg azon napok számát, ahány nappal túlléphető a határidő az e kölcsöntípushoz rendelt cikkek esetében. 
6. Kattintson a Mentés gombra.
7. Zárja be a lapot.
8. Frissítse a lapot..

## <a name="create-loan-items"></a>Kölcsöncikkek létrehozása
1. Ugorjon az Emberi erőforrások > Dolgozók > Kölcsöncikkek > Kölcsöncikkek lehetőségre.
2. Kattintson a Kölcsöncikk létrehozása lehetőségre.
3. A menny. mezőben adjon meg egy számot.
4. A Leírás mezőben adjon meg egy értéket.
5. A Kölcsön típusa mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
6. A kívánt rekord megkeresése és kijelölése a listán
7. A listában kattintson a kijelölt sorban lévő hivatkozásra.
8. Adja meg, hogy hány napra kölcsönözhető a cikk.
    * A Kölcsönzött felszerelés oldal Tervezett visszakerülés mezőjének alapértelmezés szerinti értékét a rendszer az aktuális dátumból, plusz ebből a számból számítja ki.  
9. A Felelős személy mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
10. Kattintson a Kiválasztás lehetőségre.
11. A Kezdőérték mezőben adjon meg egy számot.
12. Az Intervallum mezőben adjon meg egy számot.
13. A Formátum mezőben adjon meg egy értéket.
    * Ha például a kölcsöncikk kezdőszáma 10, akkor két számszimbólumot kell beírni a Formátum mezőbe.  
14. Kattintson az OK gombra.
15. Frissítse a lapot..

