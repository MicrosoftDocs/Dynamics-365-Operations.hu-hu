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
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2020-09-08
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: fb0d98729046330037f96ab7e13a1bf897e35a1e
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5233343"
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


[!INCLUDE[footer-include](../../includes/footer-banner.md)]