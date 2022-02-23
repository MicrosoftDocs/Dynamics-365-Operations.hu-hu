---
title: Termelési rendelés indítása
description: Ezzel az eljárással lehet megkezdeni egy termelési rendelést az üzemirányítással.
author: johanhoffmann
manager: tfehr
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: JmgRegistrationStartJob
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 47915a93151b1adc99ddb4e3facb29bf8db49dd6
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4429438"
---
# <a name="start-a-production-order"></a>Termelési rendelés indítása

[!include [banner](../../includes/banner.md)]

Ezzel az eljárással lehet megkezdeni egy termelési rendelést az üzemirányítással. Ebben a folyamatban jelentheti az idő- és nyersanyag-felhasználást. Ez az eljárás az USMF bemutatócéget használja. Ez az ötödik eljárás abból a hétből, amely bemutatja a termelési rendelés életciklusát.


## <a name="start-a-production-order"></a>Termelési rendelés indítása
1. Ugrás a Gyártásvezérlés > Termelési rendelések > Minden termelési rendelésre.
    * Válasszon ki egy Kiadott állapotú termelési rendelést.  
2. A Művelet panelen kattintson a Termelési rendelés elemre.
3. Kattintson a Start elemre.
    * Ezen a lapon erősítse meg a termelési rendelés kezdetét.  
4. Kattintson az Általános fülre.
5. A Kezdő műveletben. Szám mezőbe írja be a 10 értéket.
6. Az automatikus útvonal-felhasználás mezőben válassza ki ezt: „Mindig”.
7. Jelölje be az Útvonalkártya feladása most jelölőnégyzetet.
8. Az automatikus BOM-felhasználás mezőben válassza ki ezt: „Mindig”.
9. Kattintson a Kitárolási lista feladása most jelölőnégyzetet.
10. Kattintson a Kitárolási lista nyomtatása jelölőnégyzetet.
11. Kattintson az OK gombra.
    * Ez az a nyomtatott kitárolási lista, amely a termelési rendeléshez felhasznált anyagokat jeleníti meg.  
12. Zárja be a lapot.

## <a name="validate-the-picking-list"></a>Kitárolási lista érvényesítése
1. A Művelet panelen kattintson a Nézet elemre.
2. Kattintson a Kitárolási lista elemre.
3. Keresse meg és jelölje ki a kívánt rekordot a listán.
4. A listában kattintson a kijelölt sorban lévő hivatkozásra.
5. Kattintson a Szerkesztés lehetőségre.
6. Adjon meg egy számot a Fogyasztás mezőben.
7. Kattintson a Feladás lehetőségre.
8. Kattintson az OK gombra.
    * A kitárolásilista-naplóban a program feladja a termelési rendeléshez felhasznált anyagokat. A napló feladása előtt kiigazíthatja a becsült mennyiség és a tényleges felhasznált mennyiség közötti eltérést.  
9. Kattintson a GridPanel fülre.
10. Zárja be a lapot.

## <a name="verify-the-route-card-journal"></a>Az útvonalkártya-napló ellenőrzése
1. A Művelet panelen kattintson a Nézet elemre.
2. Kattintson az Útvonalkártya elemre.
3. Keresse meg és jelölje ki a kívánt rekordot a listán.
4. A listában kattintson a kijelölt sorban lévő hivatkozásra.
5. Kattintson a Szerkesztés lehetőségre.
6. Adjon meg egy számot az Órák mezőben.
7. Kattintson a Feladás lehetőségre.
8. Kattintson az OK gombra.
    * Az Útvonalkártya-naplóban rögzítheti az egyes műveletekkel töltött időt. A jó és a hibás mennyiséget is jelenteni kell.  
