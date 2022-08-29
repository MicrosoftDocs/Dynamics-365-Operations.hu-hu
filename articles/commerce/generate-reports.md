---
title: Online csatornajelentések készítése
description: Ez a témakör azt ismerteti, hogyan lehet jelentéseket generálni a webhely online csatornáiról Microsoft Dynamics 365 Commerce.
author: josaw1
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: 0523e74d2bfb4191e467edc001daf9178c7b4bf6
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9268321"
---
# <a name="generate-online-channel-reports"></a>Online csatornajelentések készítése

[!include [banner](includes/banner.md)]

Ez a témakör azt ismerteti, hogyan lehet jelentéseket generálni a webhely online csatornáiról Microsoft Dynamics 365 Commerce.

A Commerce alkalmazásban számos jelentés létrehozható és tekinthető meg, hogy megtudja, hogyan teljesít online csatornája.

## <a name="channel-summary-report"></a>Csatorna-összefoglaló jelentés

A **Csatorna-összefoglaló** jelentés a következő tranzakciók összesítését jeleníti meg a kiválasztott csatornához:

- Értékesítési tranzakciók
- Fizetési tranzakciók
- Adótranzakciók
- Engedményes tranzakciók

A **Csatorna-összesítő** jelentés létrehozásához hajtsa végre az alábbi lépéseket.

1. Nyissa meg a **Retail és Commerce \> Lekérdezések és jelentések \> Értékesítési jelentések \> Csatornaösszesítő-jelentés** elemet.
1. Adjon meg egy dátumot a **Kezdő dátum** mezőben.
1. Adjon meg egy dátumot a **Záró dátum** mezőben.
1. Válassza ki az online csatornát a **Csatorna** mezőben.
1. Válassza ki az **OK** lehetőséget.
 
## <a name="channel-sales-by-year-report"></a>Csatorna értékesítése év szerint – jelentés 

A **Csatorna értékesítése év szerint** jelentés egy adott üzlet értékesítésének évek szerinti összehasonlítását jeleníti meg. Válassza ki az évet, amelyhez hasonlítani szeretné az értékesítést, és a jelentés összeveti a kiválasztott év értékesítéseit az előző évhez képest.

A **Csatorna értékesítése év szerint** jelentés létrehozásához hajtsa végre az alábbi lépéseket.

1. Nyissa meg a **Retail és Commerce \> Lekérdezések és jelentések \> Értékesítési jelentések \> Csatorna értékesítése év szerint – jelentés** elemet.
1. Adjon meg egy évet a **Kezdő naptári év** mezőben.
1. Adjon meg egy évet a **Befejező naptári év** mezőben.
1. Válassza ki az online csatornát a **Csatorna** mezőben.
1. Válassza ki az **OK** lehetőséget.

## <a name="channel-sales-by-hour-report"></a>Csatorna értékesítése óra szerint – jelentés

A **Csatorna értékesítése óra szerint** jelentés megjeleníti az óránkénti értékesítési metrikákat a kiválasztott csatornához vagy üzemi egységhez.

A **Csatorna értékesítése óra szerint** jelentés létrehozásához hajtsa végre az alábbi lépéseket.

1. Nyissa meg a **Retail és Commerce \> Lekérdezések és jelentések \> Értékesítési jelentések \> Csatorna értékesítése óra szerint – jelentés** elemet.
1. Adjon meg egy dátumot a **Kezdő dátum** mezőben.
1. Adjon meg egy dátumot a **Záró dátum** mezőben.
1. Válassza ki az online csatornát a **Csatorna** mezőben.
1. Válassza ki az **OK** lehetőséget.

## <a name="top-customers-report"></a>Legfőbb vevők – jelentés

A **Legfőbb vevők** jelentés megjeleníti a kiválasztott csatorna vagy üzemi egység felső *N* vevőinek értékesítési metrikáját. Az *N* érték egy 10 és 100 közötti szám, amely a felhasználó által kiválasztott összesítő mérőszámon alapul.

A **Legfőbb vevők** jelentés létrehozásához hajtsa végre az alábbi lépéseket.

1. Nyissa meg a **Retail és Commerce \> Lekérdezések és jelentések \> Értékesítési jelentések \> Legfőbb vevők – jelentés** elemet.
1. Adjon meg egy dátumot a **Kezdő dátum** mezőben.
1. Adjon meg egy dátumot a **Záró dátum** mezőben.
1. Válassza ki az online csatornát a **Csatorna** mezőben.
1. Válassza ki az **OK** lehetőséget.

## <a name="top-discounts-report"></a>Legnagyobb engedmények jelentése

A **Legnagyobb engedmények** jelentés megjeleníti a kiválasztott csatorna vagy üzemi egység legnagyobb *N* kedvezményének értékesítési metrikáját. Az *N* érték egy 10 és 100 közötti szám, amely a felhasználó által kiválasztott összesítő mérőszámon alapul.

A **Legnagyobb engedmények** jelentés létrehozásához hajtsa végre az alábbi lépéseket.

1. Nyissa meg a **Retail és Commerce \> Lekérdezések és jelentések \> Értékesítési jelentések \> Legnagyobb engedmények jelentése** elemet.
1. Adjon meg egy dátumot a **Kezdő dátum** mezőben.
1. Adjon meg egy dátumot a **Záró dátum** mezőben.
1. Válassza ki az online csatornát a **Csatorna** mezőben.
1. Válassza ki az **OK** lehetőséget.

## <a name="top-products-report"></a>Vezető termékek jelentése

A **Vezető termékek** jelentés megjeleníti a kiválasztott csatorna vagy üzemi egység vezető *N* termék értékesítési metrikáját. Az *N* érték egy 10 és 100 közötti szám, amely a felhasználó által kiválasztott összesítő mérőszámon alapul.

A **Vezető termékek** jelentés létrehozásához hajtsa végre az alábbi lépéseket.

1. Nyissa meg a **Retail és Commerce \> Lekérdezések és jelentések \> Értékesítési jelentések \> Vezető termékek jelentése** elemet.
1. Adjon meg egy dátumot a **Kezdő dátum** mezőben.
1. Adjon meg egy dátumot a **Záró dátum** mezőben.
1. Válassza ki az online csatornát a **Csatorna** mezőben.
1. Válassza ki az **OK** lehetőséget.

## <a name="category-sales-report"></a>Kategória értékesítése – jelentés

A **Kategória értékesítései** jelentés egy kiválasztott időszakra vonatkozóan megjeleníti az értékesítési mérőszámokat a kiválasztott csatornához vagy üzemi egységhez tartozó kategória-hierarchia egyes csomópontjaihoz.

A **Kategória értékesítései** jelentés létrehozásához hajtsa végre az alábbi lépéseket.

1. Lépjen a **Retail és Commerce \> Lekérdezések és jelentések \> Értékesítési jelentések \> Értékesítési kategória-jelentés** elemre.
1. Adjon meg egy dátumot a **Kezdő dátum** mezőben.
1. Adjon meg egy dátumot a **Záró dátum** mezőben.
1. Válassza ki az online csatornát a **Csatorna** mezőben.
1. Válassza ki az **OK** lehetőséget.

## <a name="organization-sales-report"></a>Szervezeti értékesítés – jelentés

A **Szervezeti értékesítés** jelentés a szervezeti egység szerint jeleníti meg az üzletek teljesítményét. Ez a jelentés tartalmazza az értékesítési mennyiséget és az összeget üzletenként, valamint az egyes üzletek haszonkulcsát. A szervezeti egység az alapértelmezett jelentési hierarchián alapul.

Egy **Szervezeti értékesítés** jelentés létrehozásához hajtsa végre az alábbi lépéseket.

1. Ugorjon a **Retail és Commerce \> Lekérdezések és jelentések \> Értékesítési jelentések \> Szervezeti kategória-jelentés** elemre.
1. Adjon meg egy dátumot a **Kezdő dátum** mezőben.
1. Adjon meg egy dátumot a **Záró dátum** mezőben.
1. Válassza ki az **OK** lehetőséget.

## <a name="additional-resources"></a>További erőforrások

- [Commerce kezdőlap](./index.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
