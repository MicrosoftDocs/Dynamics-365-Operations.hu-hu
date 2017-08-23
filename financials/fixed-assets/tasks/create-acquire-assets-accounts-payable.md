--- 
title: "Eszközök létrehozása és beszerzése a követelések modulból"
description: "A feladat-útmutató végigvezeti a tárgyi eszköz létrehozásán és a beszerzésén a beszerzési folyamaton keresztül."
author: saraschi2
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: f814d20bc16bb3334ae4bc449cc0d45843487023
ms.contentlocale: hu-hu
ms.lasthandoff: 07/27/2017

---
# <a name="create-and-acquire-assets-from-accounts-payable"></a>Eszközök létrehozása és beszerzése a követelések modulból

[!include[task guide banner](../../includes/task-guide-banner.md)]

A feladat-útmutató végigvezeti a tárgyi eszköz létrehozásán és a beszerzésén a beszerzési folyamaton keresztül.  A Könyvelő és Kötelezettségek ügyintézőket és a bemutató USMF vállalatot használja.


## <a name="set-fixed-assets-parameters"></a>Tárgyi eszközök paramétereinek beállítása
1. Ugorjon a Tárgyi eszközök > Beállítás > Tárgyi eszköz paraméterek pontra.
2. Bontsa ki vagy csukja össze a Beszerzési rendelések szakaszt.
3. Jelölje be a Beszerzés modulból való tárgyieszköz-beszerzés engedélyezése négyzetet.
4. Jelölje be a Tárgyi eszköz létrehozása termékbevételezés vagy számla feladása közben négyzetet.

## <a name="create-a-new-vendor-invoice"></a>Új szállítói számla létrehozása
1. Ugorjon a Kötelezettségek > Munkaterületek > Szállítói számla bevitele elemre.
2. Kattintson az Új szállítói számla gombra.
3. A Számlafiók mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
4. A listában kattintson a kijelölt sorban lévő hivatkozásra.
5. Érték beírása a Szám mezőbe.
6. A Feladási dátum mezőben adjon meg egy dátumot.
7. Kattintson az Új sor hozzáadása lehetőségre.
8. A Cikkszám mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
    * Nem raktározott cikkek vagy beszerzési kategóriák használhatók tárgyieszköz-beszerzésekhez is.  
9. A listában kattintson a kijelölt sorban lévő hivatkozásra.
10. Adjon meg egy számot a Mennyiség mezőben.
    * Egy számlasor csak egy tárgyi eszközt hoz létre a mennyiségtől függetlenül.  A számlamennyiség mező értékét átviszi a tárgyi eszköz mennyiségbe.  
11. Adjon meg egy számot az Egységár mezőben.
12. Bontsa ki vagy csukja össze a Soradatok szakaszt.
13. Kattintson a Tárgyi eszközök lapra.
14. Jelölje be az Új tárgyi eszköz létrehozása jelölőnégyzetet.
15. A Tárgyieszköz-csoport mezőben kattintson a legördülő gombra a keresőlista megnyitásához.
16. A listából válassza ki az új tárgyi eszköz létrehozásakor használni kívánt tárgyieszköz-csoportot.
17. A listában kattintson a kijelölt sorban lévő hivatkozásra.
18. Kattintson a Feladás lehetőségre.
    * A tárgyi eszköz létrejön, és átkerül a számla feladásakor.  


