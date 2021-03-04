---
title: Fedezeti beállítások
description: Ez a témakör az alapütemezés által a cikkszükségletek számításához használt fedezeti beállításokkal kapcsolatban tartalmaz tájékoztatást.
author: roxanadiaconu
manager: tfehr
ms.date: 09/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqGroup, ReqItemTable, ReqItemTableWizard, ReqItemTableSetup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 2494
ms.assetid: 5a95ae4f-ca75-47d9-a1c3-68c97b42f166
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b1134f734f1025151a56b2a72266a6baa5763ba4
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4429764"
---
# <a name="coverage-settings"></a>Fedezeti beállítások

[!include [banner](../includes/banner.md)]

Az alapütemezés a fedezeti beállítások segítségével számítja ki a cikkszükségleteket.

A fedezeti beállítások többféleképpen is megadhatók:

- Fedezeti csoport fedezeti beállításainak meghatározása.

    Létrehozhat egy fedezeti csoportot, amely tartalmazza minden hozzákapcsolt termék fedezeti beállításait. Fedezeti csoport létrehozásához kattintson az **Alaptervezés &gt; Beállítás &gt; Fedezet &gt; Fedezeti csoportok** lehetőségre. A fedezeti csoportot hozzákapcsolhatja egy termékhez is. Ha a kapcsolat egy adott telephely, raktár vagy termékdimenzió esetében specifikus használja a **Fedezetcsoport** mezőt a **Cikkfedezet** lapon. Ha a kapcsolat általános, függetlenül a cikkdimenzióktól, használja a **Fedezeti csoport** mezőt a **Terv** gyorslapján a **Termékadatok** lapon. Alapértelmezett módon ha nem csatol fedezeti csoportot egy termékhez, az alaptervezés az Általános fedezetcsoport lehetőséget használja, amely meg van adva az **Alaptervezés paraméterei** oldalon.

- Termék fedezeti beállításainak meghatározása.

    Létrehozhatja egy adott termék fedezeti beállításait is. Kattintson a **Termékinformációk kezelése &gt; Termékek &gt; Kiadott termékek** lehetőségre. Válassza ki a terméket, majd a Műveleti ablakmodulon a **Terv** lapon, a **Fedezet** csoportban válassza a **Cikkfedezet** lehetőségre a **Cikkfedezet** lap megnyitásához. Ha a termék már össze van kapcsolva egy fedezeti csoporttal, akkor a **Felülbírálás** mező beállításával felülbírálhatja a fedezeti csoport beállításait. A fedezeti beállítások a **Cikkfedezet** lapon elsőbbséget élveznek a **Fedezeti csoport** lap beállításaival szemben.

- Termék fedezeti beállításainak meghatározása varázslóval.

    A varázsló lépésenként végigvezeti az elsődleges cikkfedezeti paraméterek beállításának lépésein. A **Cikkfedezet** lapon, a műveleti ablaktáblán kattintson a **Varázsló** lehetőségre a **Cikkfedezet varázsló** megnyitásához.

- Dimenziócsoport fedezeti beállításainak meghatározása.

    Kattintson a **Termékinformációk kezelése &gt; Termékek &gt; Kiadott termékek** lehetőségre. A **Kiadott termék részletei** oldalon, az **Általános** gyorslapon, az **Adminisztráció** szakaszban válassza a **Tárolásidimenzió-csoport** hivatkozást. A **Tárolásidimenzió-csoportok** oldalon válassza a **Fedezeti terv dimenziónként** jelölőnégyzetet a cikkfedezeti beállítások létrehozására egy dimenzióhoz a tárolásidimenzió-csoportban. Minden termékdimenzió, például a konfiguráció, szín, méret, stílus esetén ki kell választani a **Fedezeti terv dimenziónként** mezőt.


## <a name="coverage-codes"></a>Fedezeti kódok

Az Alaptervezés beállítható úgy, hogy különböző feltöltési módokat használjon. A feltöltési módok vagy a tételméretezés módszere a rendszer által a beszerzett vagy termelt cikkek kötegméretének meghatározására használt technika. 

Minden feltöltési mód a következő fedezeti kódok egyikéhez van hozzárendelve:

- **Manuális** – Az adagméretezési módszer, amelyen a rendszer nem javasol beszerzési, átviteli vagy termelési rendeléseket a cikkhez. A termékhez tartozó tervező lesz felelős a cikkek feltöltéséhez szükséges rendelések létrehozásához.
- **Igény szerint** – Az az adagméretezési módszer, amelyben a rendszer a termékre vonatkozó szükséglet alapján tervezett beszerzési, átmozgatási vagy termelési rendelést hoz létre. Ez általában akkor használatos, ha drága cikkekkel dolgoznak, változó igényekkel.  
- **Időszakonként** – Az az adag-méretezési módszer, amely az adott időszakra vonatkozó összes igényt egy rendelésbe egyesíti a cikkre vonatkozóan. A rendelést az időszak első napján kell megtervezni, és a mennyisége a meghatározott időszakban teljesíti a nettó szükségletet. Az időszak a cikk első igényével kezdődik, és a megadott időtartamra vonatkozik. A következő időszak a cikk következő igényével kezdődik.
- **Min/max** – Az az adagméretezési módszer, amely a készlet feltöltését tartalmazza egy bizonyos szintig, amikor az előre jelzett aktuális készlet egy küszöbérték alatt van. A feltöltési mennyiség a maximális szint és az előre jelzett aktuális szint közötti különbség lesz.


## <a name="additional-resources"></a>További erőforrások

[Alaptervek áttekintése](master-plans.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]