---
title: Intézkedési kódok beállítása
description: Ezzel az eljárással intézkedési kódot hozhat létre, amely mobileszközön használható a visszárurendelés bevételezési folyamatához.
author: Mirzaab
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WHSDispositionTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fb83108c934e864da0df39ec4ee36a0bc7ba7588
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/29/2021
ms.locfileid: "7574065"
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