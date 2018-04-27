---
title: "Fedezeti beállítások"
description: "Az alapütemezés a fedezeti beállítások segítségével számítja ki a cikkszükségleteket."
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqGroup, ReqItemTable, ReqItemTableWizard
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 2494
ms.assetid: 5a95ae4f-ca75-47d9-a1c3-68c97b42f166
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 591b1cd739bb3be61299f33f180ca7c264d21a35
ms.contentlocale: hu-hu
ms.lasthandoff: 04/13/2018

---

# <a name="coverage-settings"></a>Fedezeti beállítások

[!INCLUDE [banner](../includes/banner.md)]

Az alapütemezés a fedezeti beállítások segítségével számítja ki a cikkszükségleteket. 

A fedezeti beállítások többféleképpen is megadhatók:

-   Fedezeti csoport fedezeti beállításainak meghatározása. Létrehozhat egy fedezeti csoportot, amely tartalmazza minden hozzákapcsolt termék fedezeti beállításait. Kattintson az **Alaptervezés &gt; Beállítás &gt; Fedezet &gt; Fedezeti csoportok** lehetőségekre fedezeti csoport létrehozásához. A fedezeti csoportot hozzákapcsolhatja egy termékhez is. Ha a kapcsolat egy adott telephely, raktár vagy termékdimenzió esetében specifikus használja a **Fedezetcsoport** mezőt a **Cikkfedezet** lapon. Ha a kapcsolat általános, függetlenül a cikkdimenzióktól, használja a **Fedezeti csoport** lehetőséget a **Terv** gyorslapján a **Termékadatok** lapon. Ha nem csatol fedezeti csoportot egy termékhez, az alaptervezés az **Általános fedezetcsoport** lehetőséget használja, amely meg van adva az **Alaptervezés paraméterei** oldalon, alapértelmezettként.

-   Termék fedezeti beállításainak meghatározása. Létrehozhatja egy adott termék fedezeti beállításait is. Kattintson a **Termékinformációk kezelése &gt; Termékek &gt; Kiadott termékek** lehetőségre. Válassza ki a terméket a **Műveleti ablakmodulon**, a **Terv** lapon, a **Fedezeti csoportrészben** kattintson **Cikkfedezet** lehetőségre a **Cikkfedezet** lap megnyitásához. Ha a termék már össze van kapcsolva egy fedezeti csoporttal, akkor a **Felülbírálás** mező beállításával felülbírálhatja a fedezeti csoport beállításait. A fedezeti beállítások a**Cikkfedezet** lapon elsőbbséget élveznek a **Fedezeti csoport** lap beállításaival szemben.

<!-- -->

-   Termék fedezeti beállításainak meghatározása varázslóval. A varázsló olyan útmutató, amely segít beállítani az elsődleges cikkfedezeti paramétereket. A **Cikkfedezet** lapon kattintson a **Varázsló** lehetőségre a **Cikkfedezet varázsló** megnyitásához.

<!-- -->

- Dimenziócsoport fedezeti beállításainak meghatározása. Kattintson a <strong>Termékinformációk kezelése &gt; Közös &gt; Kiadott termékek</strong> lehetőségre. A <strong>Megjelent termék részletei **lapon, az **Általános</strong> lapon a <strong>Felügyelet</strong> csoportban kattintson a <strong>Tárolásidimenzió-csoport</strong> hivatkozásra. A <strong>Tárolásidimenzió-csoport</strong> oldalon válassza a <strong>Fedezeti terv dimenziónként</strong> mezőt cikkfedezeti beállítások létrehozására egy dimenzióhoz a tárolásidimenzió-csoportban. Minden termékdimenzió, például a konfiguráció, szín, méret, stílus, kell, hogy rendelkezzen egy kiválasztott <strong>Fedezeti terv dimenziónként</strong> mezővel.



<a name="see-also"></a>Lásd még
--------

[Alaptervek](master-plans.md)




