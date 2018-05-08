---
title: "Készletzárolás létrehozása és karbantartása"
description: "Ez az eljárás azt mutatja, hogyan előzheti meg a fizikai, aktuális készletek lefoglalását más kimenő forrásbizonylatokkal a készletzárolás segítségével."
author: perlynne
manager: AnnBe
ms.date: 12/02/2015
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 7272349cf16b9459823a752b8d3df915f42606ef
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="create-and-maintain-inventory-blocking"></a>Készletzárolás létrehozása és karbantartása

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ez az eljárás azt mutatja, hogyan előzheti meg a fizikai, aktuális készletek lefoglalását más kimenő forrásbizonylatokkal a készletzárolás segítségével. Ezt az eljárást az USMF bemutató vállalatban is futtathatja a megjelenített példákat használva. Az eljárás megkezdése előtt rendelkeznie kell egy fizikai, aktuális készletű cikkel.


## <a name="create-an-inventory-blocking"></a>Készletzárolás létrehozása
1. Ugorjon a Készletkezelés > Időszakos feladatok > Készletzárolás lehetőségre.
2. Kattintson az Új lehetőségre.
3. A Cikkszám mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
4. A listából válassza ki a használni kívánt cikket.
    * Válasszon ki egy blokkolni kívánt cikkszámot fizikai aktuális készlettel. Az USMF használata esetén választhatja a „M9201” cikket.  
5. Adjon meg egy számot a Mennyiség mezőben.
    * Az M9201 használata esetén kevesebb, mint 200-at kell választania.  
6. Bontsa ki a Készletdimenziók szakaszt.
7. A Raktár mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
8. Keresse meg és jelölje ki a kívánt rekordot a listán.
    * Az M9201 használata esetén kiválaszthatja az 51. raktárat.  
9. Kattintson a Mentés gombra.

## <a name="update-the-conditions-of-the-inventory-blocking"></a>Készletzárolás feltételeinek frissítése
1. Adjon meg egy számot a Mennyiség mezőben.
    * Frissítse a készletmennyiség mezőt, hogy megfeleljen a blokkolni kívánt mennyiségnek.  
2. Adjon meg egy dátumot a Várható dátum mezőben.
    * A várható dátum megadásával érdemes jelezni, hogy a blokkolt készlet a tervek szerint mikor foglalható újra. Ha a Várt bevételezések lehetőség van kiválasztva a készletzároláshoz, mint ahogy az alapértelmezett esetben a blokkolás létrehozásakor történik, ez a dátum jelenik meg a várható tranzakción.  
3. Kattintson a Mentés gombra.

## <a name="remove-the-inventory-blocking"></a>Készletzárolás megszüntetése
1. Kattintson a Törlés gombra.
2. Kattintson az Igen gombra.
3. Zárja be a lapot.

