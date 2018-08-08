--- 
title: "Cikkek újbóli felosztására vonatkozó szabályok rövid kitárolásának beállítása"
description: "Ez az eljárás bemutatja, hogyan engedélyezze a raktári dolgozók számára az alternatív helyek gyorsan megtalálását, ha nincs elegendő készlet a helyen, ahová átirányították őket."
author: ShylaThompson
manager: AnnBe
ms.date: 10/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: b67965b6c8641b5d91ab3c5b0a7a7fd28a07cba6
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-short-picking-item-reallocation"></a>Cikkek újbóli felosztására vonatkozó szabályok rövid kitárolásának beállítása

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ez az eljárás bemutatja, hogyan engedélyezze a raktári dolgozók számára az alternatív helyek gyorsan megtalálását, ha nincs elegendő készlet a helyen, ahová átirányították őket. Lehetőség van automatikus újbóli felosztási folyamat használatára, amely helyirányelvek segítségével teszi lehetővé áruk lekérését, ha elérhetők egy másik helyen. Ha engedélyezve van a manuális újbóli felosztás, a mobileszközön megjelenik a helyek listája az elérhető mennyiségekkel, lehetővé téve a raktáros számára annak a kiválasztását, hogy melyik helyről szeretné használni a készletet. Az USMF bemutatócég adataiban használhatja ezt az eljárást. Ez az eljárás egy olyan funkcióra vonatkozik, amely a Dynamics 365 for Operations 1611-es verziójába került be.


## <a name="set-up-work-exceptions"></a>Munkakivételek beállítása
1. Ugrás a Raktárkezelés > Beállítás > Munka > Munkakivételek elemre.
2. Kattintson az Új lehetőségre.
    * Lehetőség van több munkakivétel meghatározására eltérő cikkfelosztási irányelvekkel, amelyek lehetővé teszik, hogy a raktáros válasszon egyet a feldolgozott szállítmány szükségletei szerint.  
3. Írjon be egy értéket a Munkakivételkód mezőbe.
    * Adjon olyan címet a munkakivételnek, amelyik arra utal, hogy mire használják. Például: Rövid kitárolási kézikönyv.  
4. A Leírás mezőben adjon meg egy értéket.
5. A Kivételtípus mezőben válassza ki a „Rövid kitárolás” lehetőséget.
6. Jelölje be a Készlethelyesbítés jelölőnégyzetet.
    * Ez a beállítás azt jelenti, hogy automatikusan megtörténik a készlet helyesbítése 0-ra a rövid kitárolás helyén.  
7. Adjon meg vagy válasszon ki egy értéket az Alapértelmezett helyesbítéstípus-kód mezőben.
    * Az USMF esetében például kiválasztható a következő: „Remove Res Adj Out”.  
8. A Cikk újbóli felosztása mezőben válassza ki a „Manuális” lehetőséget.
    * Ha bejelöli a manuális, vagy az automatikus és manuális lehetőséget, a raktáros számára engedélyezni kell a manuális újbóli felosztást.  

## <a name="set-up-a-worker-to-use-manual-item-reallocation"></a>A dolgozó beállítása a manuális cikk-újbólifelosztás használatára
1. Zárja be a lapot.
2. Ugrás a Raktárkezelés > Beállítás > Dolgozó elemre.
3. Kattintson a Szerkesztés lehetőségre.
4. A listában válassza a 24. dolgozó elemet.
5. Bontsa ki a Dolgozó szakaszt.
6. Válassza ki az Igen lehetőséget a Cikk újbóli manuális felosztásának engedélyezése mezőben.


