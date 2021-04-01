---
title: Intézkedési kódok beállítása
description: Ezzel az eljárással intézkedési kódot hozhat létre, amely mobileszközön használható a visszárurendelés bevételezési folyamatához.
author: ShylaThompson
manager: tfehr
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSDispositionTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d8eeba07aafbcbc327aa5e28a10d10c16b0e0f43
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5236543"
---
# <a name="set-up-dispositions-codes"></a>Intézkedési kódok beállítása

[!include [banner](../../includes/banner.md)]

Ezzel az eljárással intézkedési kódot hozhat létre, amely mobileszközön használható a visszárurendelés bevételezési folyamatához. Az intézkedési kódok olyan szabálygyűjtemények, melyeket áru beérkezésekor használnak. Például amikor egy munkafelhasználó mobileszközt használ sérült cikkek érkeztetéséhez, a felhasználónak egy intézkedési kódot kell beolvasni a sérült cikkekhez. A kapott áruk készletállapotát, a munkasablont és a helyirányelvet a beolvasott intézkedési kódból lehet meghatározni. A beszerzési rendelés bevételezési folyamathoz és a termelési rendelés jelentés készre jelentési folyamatához intézkedési kód használata nem kötelező. Az értékesítési rendelés visszáru bevételezési folyamatánál, ha a cikkek regisztrálása mobileszközzel történt, intézkedési kód használata kötelező.  Ez az útmutató a USMF bemutatócég segítségével lett létrehozva. Ezt az eljárást a raktári vezető használja. 

1. Ugorjon a a Raktárkezelés > Beállítás > Mobileszköz > Intézkedési kódok menüre.
2. Kattintson az Új lehetőségre.
    * Hozzon létre egy új, vevői visszáruhoz használandó intézkedési kódot.  
3. Írjon be egy értéket az Intézkedési kód mezőbe.
4. A Készlet állapota mezőben válasszon ki egy készletállapotot, ahol a készletzárolás van.
    * Ha USMF-et használ, jelölje be a "Blocking" opciót. Egy készletállapotot adhat az intézkedési kódhoz, ha felül szeretné bírálni az alapértelmezett állapotot, amely a rendelési sorokon van.  
5. Írjon be egy értéket a Munkasablon mezőbe.
    * Választható: A visszárurendeléshez társított munkasablonkód kiválasztása. Ha nincs érték megadva, a munkasablon a rendszerben szokásos szabályok segítségével lesz beállítva. Egy munkasablon kiválasztása korlátozza a folyamatokat, amelyekkel ez az intézkedéskód használható. Például ha egy intézkedési kódhoz egy Munkarendelés típusú beszerzési rendeléssel rendelkező munkasablon tartozik, nem használható vevők által visszaküldött cikkek regisztrálásához.  
6. Írjon be egy értéket a Visszáru-iIntézkedési kód mezőbe.
    * A visszaküldési intézkedéskód meghatározza a regisztrált cikkek visszáru-rendelési folyamatának többi részét. Ebben a példában a vevőnek jóváírást kell kapnia. Adjon hozzá egy visszáru intézkedési kódot, amely egy Jóváírás műveletet tartalmaz.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]