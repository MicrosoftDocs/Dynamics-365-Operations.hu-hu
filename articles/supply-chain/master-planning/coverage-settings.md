---
title: Fedezeti beállítások
description: Az alapütemezés a fedezeti beállítások segítségével számítja ki a cikkszükségleteket.
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqGroup, ReqItemTable, ReqItemTableWizard
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2494
ms.assetid: 5a95ae4f-ca75-47d9-a1c3-68c97b42f166
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 50f47394a4d4e95b4e158ea42a630d9e6e91f05b
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "322559"
---
# <a name="coverage-settings"></a>Fedezeti beállítások

[!include [banner](../includes/banner.md)]

Az alapütemezés a fedezeti beállítások segítségével számítja ki a cikkszükségleteket. 

A fedezeti beállítások többféleképpen is megadhatók:

-   Fedezeti csoport fedezeti beállításainak meghatározása. Létrehozhat egy fedezeti csoportot, amely tartalmazza minden hozzákapcsolt termék fedezeti beállításait. Kattintson az **Alaptervezés &gt; Beállítás &gt; Fedezet &gt; Fedezeti csoportok** lehetőségekre fedezeti csoport létrehozásához. A fedezeti csoportot hozzákapcsolhatja egy termékhez is. Ha a kapcsolat egy adott telephely, raktár vagy termékdimenzió esetében specifikus használja a **Fedezetcsoport** mezőt a **Cikkfedezet** lapon. Ha a kapcsolat általános, függetlenül a cikkdimenzióktól, használja a **Fedezeti csoport** lehetőséget a **Terv** gyorslapján a **Termékadatok** lapon. Ha nem csatol fedezeti csoportot egy termékhez, az alaptervezés az **Általános fedezetcsoport** lehetőséget használja, amely meg van adva az **Alaptervezés paraméterei** oldalon, alapértelmezettként.

-   Termék fedezeti beállításainak meghatározása. Létrehozhatja egy adott termék fedezeti beállításait is. Kattintson a **Termékinformációk kezelése &gt; Termékek &gt; Kiadott termékek** lehetőségre. Válassza ki a terméket a **Műveleti ablakmodulon**, a **Terv** lapon, a **Fedezeti csoportrészben** kattintson **Cikkfedezet** lehetőségre a **Cikkfedezet** lap megnyitásához. Ha a termék már össze van kapcsolva egy fedezeti csoporttal, akkor a **Felülbírálás** mező beállításával felülbírálhatja a fedezeti csoport beállításait. A fedezeti beállítások a**Cikkfedezet** lapon elsőbbséget élveznek a **Fedezeti csoport** lap beállításaival szemben.

<!-- -->

-   Termék fedezeti beállításainak meghatározása varázslóval. A varázsló olyan útmutató, amely segít beállítani az elsődleges cikkfedezeti paramétereket. A **Cikkfedezet** lapon kattintson a **Varázsló** lehetőségre a **Cikkfedezet varázsló** megnyitásához.

<!-- -->

- Dimenziócsoport fedezeti beállításainak meghatározása. Kattintson a **Termékinformációk kezelése &gt; Közös &gt; Kiadott termékek** lehetőségre. A **Kiadott termék részletei** oldalon, az **Általános** fülön, az **Adminisztráció** csoportban kattintson a **Tárolásidimenzió-csoport** hivatkozásra. A **Tárolásidimenzió-csoport** oldalon válassza a **Fedezeti terv dimenziónként** mezőt cikkfedezeti beállítások létrehozására egy dimenzióhoz a tárolásidimenzió-csoportban. Minden termékdimenzió, például a konfiguráció, szín, méret, stílus, kell, hogy rendelkezzen egy kiválasztott **Fedezeti terv dimenziónként** mezővel.



<a name="additional-resources"></a>További erőforrások
--------

[Alaptervek](master-plans.md)



