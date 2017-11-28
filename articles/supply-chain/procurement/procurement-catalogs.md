---
title: "Beszerzési katalógusok"
description: "Ez a cikk magas szinten leírja, hogy a beszerzési szakemberek hogyan állíthatnak be és tarthatnak fenn beszerzési katalógusokat. A beszerzési katalógusok határozzák meg a cikkeket és szolgáltatásokat, amelyeket a vállalati alkalmazottak megrendelhetnek belső használat céljából."
author: mkirknel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: f51fb41e19a47a9db02166de91b9e027154d6a7d
ms.contentlocale: hu-hu
ms.lasthandoff: 11/03/2017

---

# <a name="procurement-catalogs"></a>Beszerzési katalógusok

[!include[banner](../includes/banner.md)]


Ez a cikk magas szinten leírja, hogy a beszerzési szakemberek hogyan állíthatnak be és tarthatnak fenn beszerzési katalógusokat. A beszerzési katalógusok határozzák meg a cikkeket és szolgáltatásokat, amelyeket a vállalati alkalmazottak megrendelhetnek belső használat céljából.

A beszerzési szakemberek a beszerezhető cikkekre és szolgáltatásokra vonatkozó, a vállalaton belüli használatra szóló katalógusokat hozhatnak létre és karbantarthatják azokat. Katalógusok beállítása után a vállalat alkalmazottai beszerzési igényléseket hozhatnak létre a katalógusokból való rendelésekhez. A katalógusok használatával lehet érvényesíteni a beszerzési irányelveket, úgy, hogy az alkalmazottak csak olyan cikkeket és szolgáltatásokat rendelhetnek, amelyek engedélyezve vannak a vásárló jogi személyük számára. Beszerzési katalógus létrehozása esetén a következő feladatok elvégzését kell átgondolnia:

-   A katalógus létrehozása előtt állítsa be a beszerzési kategóriák hierarchiáját.
-   Határozza meg, mely termékeket rendelhessék meg az alkalmazottak. Megjelenítheti vagy elrejtheti az adott termékeket a katalógus csomópontban, vagy megjelenítheti vagy elrejtheti a csomópontban az összes terméket.
-   Határozza meg, hány beszerzési katalógusra van szüksége. A beszerzési katalógushoz való hozzáférést a katalógus szabálya határozza meg, amelyet konfigurál a jogi személyhez és az üzemi egységhez, amelyhez az alkalmazott hozzá van rendelve.

Számos tényező határozza meg azokat a termékeket, amelyeket az alkalmazottak megrendelhetnek, illetve a lehetséges beszerzési kategóriákat, amelyeket használhatnak a beszerzési igénylések létrehozásakor:

-   A kategóriához való hozzáférésre vonatkozó irányelvszabály határozza meg, hogy mely beszerzési kategóriák érhetők el a beszerzési igénylésben. Ha nincs meghatározva szabály, akkor az összes beszerzési kategória elérhető.
-   Az alkalmazottak egy terméket csak akkor rendelhetnek meg, ha az aktív az Ön szervezetének katalógusában, és ha engedélyezett csomópontban van, és nincs elrejtve. A terméknek ezen felül olyan kategóriában kell lennie, amelyhez az adott alkalmazottnak hozzáférése van a kategória hozzáférési irányelvszabálya szerint.
-   A katalógus-irányelvszabály adja meg a használt katalógust. Ha nincs a katalógus-irányelvszabály beállítva, akkor egyedül a kategória hozzáférési szabálya határozza meg, hogy egy alkalmazott az igénylésben mely termékeket rendelheti meg.

## <a name="prerequisites"></a>Előfeltételek
A következő táblázat leírja a feladatokat, amelyeket el kell végezni mielőtt a beszerzési szakember beszerzési katalógust hozhat létre.

| Feladat                                                | Szerepkör               | Leírás                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|-----------------------------------------------------|--------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Beszerzési kategóriahierarchia beállítása.            | Beszerzési vezető | A beszerzési kategóriahierarchiák segítségével a cikkek vagy tranzakciók besorolhatók jelentéskészítés és elemzés céljából. Beszerzési kategóriahierarchia használatával a vállalatok stratégiailag kezelhetik a kategóriákat, termékeket, szállítókat és egyéb beszerzési tényezőket egy központi helyről. Egy teljes szervezet számára egy beszerzési kategóriahierarchia van meghatározva. A katalógus a beszerzési kategóriák hierarchiáján alapszik: a hierarchia kategóriái a katalógusban csomópontok lesznek. A szállítók és a termékek benne vannak az Ön katalógusában. |
| Szállítók és termékek hozzáadása a beszerzési kategóriákhoz. | Beszerzési vezető | A szervezet számára a beszerzési kategóriahierarchia létrehozása után minden egyes beszerzési kategória társítható a meghatározott szállítókkal, termékekkel és így tovább. Ezek a társítások automatikusan bele lesznek másolva a katalógusba.                                                                                                                                                                                                                                                                                           |

## <a name="setting-up-a-catalog"></a>Katalógus beállítása
Miután teljesültek az előfeltételek, beállíthatja a katalógusokat. Létrehozhat egy katalógust, amelyet a teljes szervezet használ, vagy több katalógust a szervezeten belüli különböző osztályok számára. Ha létrehoz egy katalógust a teljes szervezet számára, a katalógushoz való hozzáférést a beszerzési irányelvek vezérlik.  

A katalógus határozza meg, hogy mely termékek állnak rendelkezésre, amikor a beszerzési igénylések létrejönnek, de használhat kategória-hozzáférési irányelveket további megkötések alkalmazása céljából. Mivel a katalógus csomópontjai beszerzési kategóriák, azok letilthatók egy kategória-hozzáférési irányelvvel. Ebben az esetben az adott kategóriába tartozó termékek nem állnak rendelkezésre az alkalmazottak számára az igénylésekhez való használathoz. A kategória-hozzáférési irányelvszabályokat a **Beszerzési irányelvek** oldalon adhatja meg. A következő táblázat leírja a katalógus beállításához elvégzendő feladatokat.

| Feladat                                                   | Szerepkör             | Leírás                                                                                                                                                                                                                                                                                                                  |
|--------------------------------------------------------|------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Új katalógus létrehozása.                                  | Beszerzési ügynök | A katalógus létrehozásakor megadja a katalógus nevét és a katalógus leírását. Megadhatja azt is, hogy manuálisan vagy automatikusan frissül a katalógus, és megadhatja a katalógus tulajdonosát.                                                                                                                                      |
| Ellenőrizze, hogy elérhetők-e termékek a katalógusban. | Beszerzési ügynök | Mivel a termékek a beszerzési kategóriákból öröklődnek, az összes a megfelelő katalógus csomópontjában jelenik meg. Szabályozhatja, hogy a csomópontban lévő összes termék el legyen rejtve vagy látszódjon, amikor a katalógust használják egy beszerzési igénylésnél. Beállíthatja azt is, hogy a csomópont egyes termékei rejtve legyenek vagy látszódjanak. |
| Katalógus közzététele.                                   | Beszerzési ügynök | Mielőtt a katalógus érhető lesz az alkalmazottak számára egy igényléshez, meg kell határoznia a katalógus számára egy katalógus-irányelvszabályt, be kell állítania a katalógus állapotát az **Aktív** lehetőségre, és közzé kell tennie a katalógust. Inaktiválhatja a katalógusokat, amelyekről nem szeretné, hogy elérhetőek legyenek a felhasználók számára.                                              |

A frissítéseket automatikusan vagy manuálisan teszik közzé, attól függően, hogy milyen beállítást választ az **Alapértelmezett frissítéstípus** mezőben a **Katalógusok** oldalon. A következő alapértelmezett frissítéstípusok érhetők el a katalógusok számára:

-   **Dinamikus** – A katalógus automatikusan frissül, ahányszor csak megváltozik.
-   **Statikus** – A katalógusokat kézzel kell frissíteni.
-   **Mindkét** – Ha a katalógus tartalmaz, megadhat egy alapértelmezett típusának módosítása termékkategóriák **statikus**, akkor kézzel kell frissíteni ezekbe a kategóriákba frissítésekor. Ha a katalógus olyan termékkategóriákat tartalmaz, amelyeknek az alapértelmezett frissítési típusa **Dinamikus**, automatikusan frissül, amennyiben megváltoznak.


<a name="see-also"></a>Lásd még
--------

[Beszerzési kategóriahierarchia beállítása (feladat-útmutató)](tasks/set-up-procurement-category-hierarchy.md)




