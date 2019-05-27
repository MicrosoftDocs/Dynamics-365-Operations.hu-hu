---
title: Fedezeti beállítások
description: Ez a témakör az alapütemezés által a cikkszükségletek számításához használt fedezeti beállításokkal kapcsolatban tartalmaz tájékoztatást.
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
ms.openlocfilehash: 99e094a7131b6d3a299fc72abd0141529908ddd2
ms.sourcegitcommit: 9e50bee6a67f0fe2fa6f86e02c7e8de16d0e2482
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/08/2019
ms.locfileid: "1538894"
---
# <a name="coverage-settings"></a>Fedezeti beállítások

[!include [banner](../includes/banner.md)]

Az alapütemezés a fedezeti beállítások segítségével számítja ki a cikkszükségleteket.

A fedezeti beállítások többféleképpen is megadhatók:

- Fedezeti csoport fedezeti beállításainak meghatározása.

    Létrehozhat egy fedezeti csoportot, amely tartalmazza minden hozzákapcsolt termék fedezeti beállításait. Fedezeti csoport létrehozásához kattintson az **Alaptervezés &gt; Beállítás &gt; Fedezet &gt; Fedezeti csoportok** lehetőségre. A fedezeti csoportot hozzákapcsolhatja egy termékhez is. Ha a kapcsolat egy adott telephely, raktár vagy termékdimenzió esetében specifikus használja a **Fedezetcsoport** mezőt a **Cikkfedezet** lapon. Ha a kapcsolat általános, függetlenül a cikkdimenzióktól, használja a **Fedezeti csoport** mezőt a **Terv** gyorslapján a **Termékadatok** lapon. Alapértelmezett módon ha nem csatol fedezeti csoportot egy termékhez, az alaptervezés az Általános fedezetcsoport lehetőséget használja, amely meg van adva az **Alaptervezés paraméterei** oldalon.

- Termék fedezeti beállításainak meghatározása.

    Létrehozhatja egy adott termék fedezeti beállításait is. Kattintson a **Termékinformációk kezelése &gt; Termékek &gt; Kiadott termékek** lehetőségre. Válassza ki a terméket, majd a Műveleti ablakmodulon a **Terv** lapon, a **Fedezet** csoportban válassza a **Cikkfedezet** lehetőségre a **Cikkfedezet** lap megnyitásához. Ha a termék már össze van kapcsolva egy fedezeti csoporttal, akkor a **Felülbírálás** mező beállításával felülbírálhatja a fedezeti csoport beállításait. A fedezeti beállítások a**Cikkfedezet** lapon elsőbbséget élveznek a **Fedezeti csoport** lap beállításaival szemben.

- Termék fedezeti beállításainak meghatározása varázslóval.

    A varázsló lépésenként végigvezeti az elsődleges cikkfedezeti paraméterek beállításának lépésein. A **Cikkfedezet** lapon, a műveleti ablaktáblán kattintson a **Varázsló** lehetőségre a **Cikkfedezet varázsló** megnyitásához.

- Dimenziócsoport fedezeti beállításainak meghatározása.

    Kattintson a **Termékinformációk kezelése &gt; Termékek &gt; Kiadott termékek** lehetőségre. A **Kiadott termék részletei** oldalon, az **Általános** gyorslapon, az **Adminisztráció** szakaszban válassza a **Tárolásidimenzió-csoport** hivatkozást. A **Tárolásidimenzió-csoportok** oldalon válassza a **Fedezeti terv dimenziónként** jelölőnégyzetet a cikkfedezeti beállítások létrehozására egy dimenzióhoz a tárolásidimenzió-csoportban. Minden termékdimenzió, például a konfiguráció, szín, méret, stílus esetén ki kell választani a **Fedezeti terv dimenziónként** mezőt.

## <a name="additional-resources"></a>További erőforrások

[Alaptervek](master-plans.md)
