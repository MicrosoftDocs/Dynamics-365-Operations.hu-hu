---
title: Készletzárolás létrehozása és karbantartása
description: Ez az eljárás azt mutatja, hogyan előzheti meg a fizikai, aktuális készletek lefoglalását más kimenő forrásbizonylatokkal a készletzárolás segítségével.
author: perlynne
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventBlocking, InventItemIdLookupSimple, InventLocationIdLookup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 845d517ad10245df3b208874df61e235c199c7fe
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/01/2019
ms.locfileid: "1836401"
---
# <a name="create-and-maintain-an-inventory-blocking"></a>Készletzárolás létrehozása és karbantartása

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

