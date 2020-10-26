---
title: Központi kiegészítő szolgáltatások díjainak és kiegészítő alaptermékek beállítása
description: Ez az eljárás bemutatja, hogyan lehet kiegészítő szolgáltatások alapadatokat létrehozni egy központ számára, és az alapadatok segítségével egy központi kiegészítő díjat létrehozni.
author: ShylaThompson
manager: tfehr
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSHubAccessorial,TMSAccessorialMaster
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 82cd18c7109b5a0287ee2eb8b7adf901c97ec7c7
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/10/2020
ms.locfileid: "3982624"
---
# <a name="set-up-hub-accessorial-charges-and-accessorial-masters"></a>Központi kiegészítő szolgáltatások díjainak és kiegészítő alaptermékek beállítása

[!include [banner](../../includes/banner.md)]

Ez az eljárás bemutatja, hogyan lehet kiegészítő szolgáltatások alapadatokat létrehozni egy központ számára, és az alapadatok segítségével egy központi kiegészítő díjat létrehozni. Az eljárás az USMF adatkészletet használja. Ezt a beállítást általában egy szállítási koordinátor végzi.


## <a name="set-up-a-hub-master"></a>Központ alapadatainak beállítása
1. Lépjen a Szállításkezelés > Beállítás > Minősítés > Kiegészítő alapszolgáltatások pontra.
2. Kattintson az Új lehetőségre.
3. A Kiegészítő alapszolgáltatások mezőbe írjon be egy értéket.
4. Írjon be egy értéket a Név mezőbe.
5. A Kiegészítő szolgáltatás típusa mezőben válassza ki a „Központ” elemet.
6. Kattintson a Mentés gombra.
7. Zárja be a lapot.

## <a name="set-up-a-hub-accessorial-charge"></a>Központi kiegészítő szolgáltatások díj létrehozása
1. Lépjen a Szállításkezelés > Beállítás > Minősítés > Központi kiegészítő szolgáltatások díjai pontra.
2. Kattintson az Új lehetőségre.
3. Írjon be egy értéket a Központi kiegészítő szolgáltatások azonosító mezőbe.
4. A Központ mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
5. Keresse meg és jelölje ki a kívánt rekordot a listán.
6. A Központ pozíciója mezőben válasszon ki egy lehetőséget.
    * A költség lehet felvételi vagy lerakati. A választástól függően a költség a megfelelő szállítási szegmensre fog vonatkozni az útvonalon.  
7. A Kiegészítő alapszolgáltatás mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
8. A listában kattintson a kijelölt sorban lévő hivatkozásra.
    * Jelölje ki az előbb létrehozott alapadatot.  
9. Kattintson a Mentés gombra.
10. Zárja be a lapot.

