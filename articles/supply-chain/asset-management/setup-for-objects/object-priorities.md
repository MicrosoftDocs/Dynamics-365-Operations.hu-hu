---
title: Eszköz szolgáltatásszintjei
description: Ez a témakör bemutatja az Eszközkezelés eszközökhöz tartozó szolgáltatási szintjeit.
author: johanhoffmann
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5e4f7daa10931ce406a5d2bdbbc1dced067e3de5065cdb61cce369d617709d67
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6723599"
---
# <a name="asset-service-levels"></a>Eszköz szolgáltatásszintjei

[!include [banner](../../includes/banner.md)]

 

Ez a témakör bemutatja az Eszközkezelés eszközökhöz tartozó szolgáltatási szintjeit. Az eszköz szolgáltatási szintje az eszközökhöz kapcsolódnak, és átkerülnek a karbantartási kérésekre és munkarendelésekre. A Munkarendelés ütemezése során a munkarendelések prioritásának kiszámításához használatosak. Az eszköz szolgáltatási szintjei módosíthatók, ha szükségesek a változtatások.

A munkarendelés ütemezéséhez szükséges értékelési pontszámok kiszámításával kapcsolatos beállításra vonatkozó további információkat az [Eszközkezelés paraméterei](../setup-for-objects/enterprise-asset-management-parameters.md) részben találhat. Az eszköz szolgáltatási szintjéhez legalább egy alapértelmezett rekordot be kell állítania. Ez az alapértelmezett rekord akkor használatos, ha a Munkarendelés ütemezése során nem találhatók egyéb egyezések.

**1. példa** : Az alapértelmezett szolgáltatási szint, amely akkor használatos, ha a rendszer nem talál más egyezést. Ebben a rekordban csak szolgáltatási szintet lehet kiválasztani.

**2. példa** : Egy magas szolgáltatási szint, amely a Volvo teherautó-motor feladatainak ütemezéséhez használatos. Ebben a rekordban kiválaszthatja a megfelelő eszköztípust ( Például **Teherautó-motor**), a gyártót (**Volvo**) és szolgáltatási szintet.

## <a name="set-up-asset-service-levels"></a>Eszköz szolgáltatásszintjeinek beállítása

1. Válassza ki az **Eszközkezelés** \> **Beállítás** \> **Eszköz szolgáltatási szintjei** elemet.
2. Válassza az **Új** lehetőséget egy rekord létrehozásához.
3. Az eszköz szolgáltatási szintjéhez szüksége részletességi szinttől függően végezze el a releváns kiválasztásokat a következő mezőkben: **munkavégzési helyszín**, **Eszköztípus**, **Gyártó**, **Modell**, **Eszköz**, **Munkarendelés típusa** és **Szolgáltatási szint**.

    > [!NOTE]
    > Amikor az eszköz szolgáltatási szintjét karbantartási kérésekhez és munkarendelésekhez használják, az Eszközkezelés végigmegy az összes eszközszolgáltatási szinthez kapcsolódó rekordon lehetséges egyezést keresve. Mindig a leginkább meghatározott kombinációt ellenőrzi először. Más szóval az Eszközkezelés modul először a **Munkarendelés típusa** mezővel való egyezést ellenőrzi. Ha nem talál egyezést, akkor az **Eszköz** mezővel való egyezést ellenőrzi, és így tovább. Ahogy az az **Eszköz szolgáltatási szintje** oldal elrendezésében is látható, ez a viselkedésmód azt jelenti, hogy a legspecifikusabb kombináció megkereséséhez az Eszközkezelés minden egyes rekordot jobbról balra ellenőriz egyezést keresve. Ha nem talál egyezést, akkor a rendszer azt az alapértelmezett rekordot használja, amely azon mezők egyikében sem tartalmaz választási lehetőséget.

4. A **Szolgáltatási szint** mezőben válassza ki azt a számot, amely a szolgáltatási szintet (prioritást) jelzi.


> [!NOTE]
> Ha módosítja az eszköz szolgáltatási szintjéhez tartozó rekordot az **Eszköz szolgáltatási szintje** oldalon , miután már használta egy munkarendelésen, a karbantartási kérések és munkarendelések szolgáltatási szintje nem frissül ennek megfelelően.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]