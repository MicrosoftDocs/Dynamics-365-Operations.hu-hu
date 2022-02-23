---
title: Szállításkezelési állapotok
description: Ez a témakör azt mutatja be, hogyan lehet egy szállítási állapotot létrehozni, és az állapotot a szállítmányozó állapotához rendelni.
author: Henrikan
manager: tfehr
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2020-09-08
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 3f7d471771ec2b4703d878fbf395cd90902b6669
ms.sourcegitcommit: fe7ac653efcb1ac6318083f482394b96ed82b4c7
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/29/2020
ms.locfileid: "4429981"
---
# <a name="transportation-management-statuses"></a>Szállításkezelési állapotok

[!include [banner](../includes/banner.md)]

A rendelkezésre álló szállítási állapotok szállítási törzskódjainak beállításával értelmezheti a szállítmányozók kódjait. Ez lehetővé teszi a szállítmányozók számára, hog megadják az állapotukat. A szállítási törzskódhoz meghatározott szállítási állapot alapján követheti nyomon egy rakomány, egy szállítás vagy egy tároló állapotát. Egy rakomány, szállítmány vagy tároló konkrét szállítási állapota csak adatintegrációval frissíthető, és nem a felhasználói felületen keresztül.

## <a name="create-a-transportation-status"></a>Szállítmányozási állapot létrehozása

A szállítmányozási állapot létrehozásához kövesse az alábbi lépéseket:

1. Ugorjon a **Szállításkezelés \> Beállítás \> Szállítmányozási törzsállapotok** lehetőségre.
1. Az új szállítási törzsállapot létrehozásához kattintson az **Új** elemre.
1. A **Szállítmányozási törzsállapot** mezőbe írja be a szállítási állapot egyedi kódját.
1. A **Szállítás típusa** mezőben válassza ki a *Szállítmányozó* vagy a *Központ* lehetőséget a szállítás típusának.
1. Adjon meg egy nevet és egy szállítási állapotot.
1. Zárja be a lapot.

## <a name="map-a-transportation-status-to-a-carrier-status"></a>Szállítási állapot hozzárendelése a szállítmányozó állapotához

Ha egy szállítási állapotot szállítmányozói állapothoz kíván hozzárendelni, hajtsa végre az alábbi lépéseket:

1. Ugorjon a **Szállításkezelés \> Beállítás \> Szállítmányozók \> Szállítmányozó szállítási állapota** lehetőségre.
1. Az **Új** gombra kattitnva rendelhet össze egy szállítmányozói kódot egy szállítói állapot törzskódhoz.
1. Válassza ki a szállítmányozó és a szállítmányozási szolgáltatás egyedi azonosítóját.
1. Válassza ki azt a szállítási állapotkódot, amelyet a kiválasztott szállítmányozó kódjához hozzá akar rendelni.
1. Adja meg a szállítmányozó által használt külső kódot.
1. Zárja be a lapot.
