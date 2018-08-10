--- 
title: "Mértékegység kezelése"
description: "Ez az eljárás bemutatja, hogyan lehet meghatározni egy mértékegységet, meghatározni fordításokat a mértékegységhez és a leírását, és átváltási szabályokat megadni a kapcsolódó egységekhez."
author: sorenva
manager: AnnBe
ms.date: 02/12/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 6bb7a5133e9412f4ed6fb74f0d3ee595c07a0c4b
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="manage-unit-of-measure"></a>Mértékegység kezelése

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ez az eljárás bemutatja, hogyan lehet meghatározni egy mértékegységet, meghatározni fordításokat a mértékegységhez és a leírását, és átváltási szabályokat megadni a kapcsolódó egységekhez. Ezt a folyamatot bemutatóadatokkal vagy saját adatokkal is elvégezheti.

1. Lépjen a Kiadott termék karbantartásra.
2. Kattintson a Mértékegységekre.

## <a name="create-a-unit-of-measure"></a>Mértékegység létrehozása
1. Kattintson az Új lehetőségre.
2. Írjon be egy értéket a Mértékegység mezőbe.
    * Adja meg a mértékegységre történő hivatkozás során használt azonosítót vagy szimbólumot.  
3. A Leírás mezőben adjon meg egy értéket.
    * Írjon be egy jellemző nevet a mértékegységnek a rendszer nyelvén.  
4. Válasszon ki egy lehetőséget a Mértékegységosztály mezőben.
    * Az egységosztály határozza meg, hogy milyen logikai csoport, például terület, tömeg vagy mennyiség része a mértékegység.  
5. A Tizedes pontosság mezőben meg kell adnia egy számot.
    * Adja meg a tizedesek számát, amelyre az átalakított mértékegységet kerekíteni kell a mértékegység számítás befejeztével.  
6. Kattintson a Mentés gombra.

## <a name="define-unit-translations"></a>Egység fordításainak meghatározása
1. Kattintson a Mértékegység szövegek pontra.
2. Kattintson az Új lehetőségre.
    * Használjon egységes szöveget az azonosító fordítására vagy egy mértékegységet képviselő szimbólumot külső dokumentumokhoz vevő vagy szállító-specifikus nyelveken.  
3. A Nyelv mezőben adjon meg vagy válasszon ki egy értéket.
4. Írjon be egy értéket a Szöveg mezőbe.
5. Kattintson a Mentés gombra.
6. Zárja be a lapot.
7. Kattintson a Lefordított egységleírásokra.
8. Kattintson az Új lehetőségre.
    * Határozzon meg nyelvspecifikus leírásokat a mértékegységhez.  
9. A Nyelv mezőben adjon meg vagy válasszon ki egy értéket.
10. A Leírás mezőben adjon meg egy értéket.
11. Kattintson a Mentés gombra.
12. Zárja be a lapot.

## <a name="define-unit-conversion-rules"></a>Egység átváltási szabályok definiálása
1. Kattintson az Egységátváltásokra.
    * Adjon meg szabályokat a mértékegységek átalakításához más mértékegységekről és -re a kijelölt egységosztályban.  
2. Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.
3. Az Arány mezőben adjon meg egy számot.
    * Átszámítási arány a forrás és a cél mértékegység között. Például a centiméterről méterre való átváltási arány 100, mert egy méter 100 centiméterből áll.  
4. A Cél egység mezőben adjon meg vagy válasszon ki egy értéket.
5. A Kerekítés mezőben válasszon egy lehetőséget.
    * Határozza meg, hogyan kell kerekíteni a konvertált értéket.  
6. Kattintson az OK gombra.
7. Zárja be a lapot.


