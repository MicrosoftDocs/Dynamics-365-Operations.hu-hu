---
title: "Termékdimenziók"
description: "Négy termékdimenzió létezik: szín, konfiguráció, méret és stílus. A termékdimenziókat dimenziócsoportokban kombinálhatja és hozzárendelheti a dimenziócsoportokat az alaptermékekhez. A cikkdimenziók kombinációi meghatározzák a termékváltozatokat is."
author: cvocph
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResProductDimension, EcoResProductDimensionGroup, EcoResProductMasterDimension, RetailEcoResColor, RetailEcoResSize, RetailEcoResStyle
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 19171
ms.assetid: 81fa3709-4ab8-4fbf-9806-359892a05985
ms.search.region: Global
ms.search.industry: Retail
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ea07d8e91c94d9fdad4c2d05533981e254420188
ms.openlocfilehash: 9cb4bded4b8d841c6d164e6b8ded2cb3fb4d0978
ms.contentlocale: hu-hu
ms.lasthandoff: 02/07/2018

---

# <a name="product-dimensions"></a>Termékdimenziók

[!include [banner](../includes/banner.md)]

[!include [Retail name](../includes/retail-name.md)]

Négy termékdimenzió létezik: szín, konfiguráció, méret és stílus. A termékdimenziókat dimenziócsoportokban kombinálhatja és hozzárendelheti a dimenziócsoportokat az alaptermékekhez. A cikkdimenziók kombinációi meghatározzák a termékváltozatokat is.

Termékdimenziók olyan jellemzőket termékváltozat azonosítására szolgál. Cikkdimenziók kombinációi használhatja termékváltozatok meghatározására. Termékváltozat létrehozásához meg kell adnia legalább egy termékdimenzió alaptermék.
Termékváltozatok
----------------

Termékváltozatok is nevezik cikkeket. Cikk tárgyi eszközök termék, amely nem azonos a szolgáltatás fut. Azonban lehetőség van alaptermék meghatározására is a szolgáltatástípussal. A Szolgáltatástípus használatával megadhat szolgáltatásokat magukba foglaló termékváltozatokat. Például megadhatja a tanácsadói munka és a termékbevételezés változatok vezető tanácsadók és beosztott tanácsadók által végrehajtott munka alaptermék.

## <a name="product-dimensions"></a>Termékdimenziók
A következő termékdimenziók léteznek: szín, konfiguráció, méret és stílus. Termékváltozat hozható létre a termékdimenzió-értékek alapján.

Termékdimenzió-értékek, mint például méret, szín és stílus a **Méret**, **Szín** és **Stílus** lapokon hozhatók létre, amelyek a következő helyekről érhetők el: **Termékinformációk kezelése** &gt; **Beállítás** &gt; **Dimenzió- és változatcsoportok** &gt; **Méretek/Színek/Stílusok**. A Konfigurációdimenzió termékdimenzió-értékei általában a Termékkonfiguráló vagy a Dimenzión alapuló konfiguráló használatával hozhatók létre. A termékdimenziók létrehozása és karbantartása a **Termékdimenziók** oldalon lehetséges, amely a következő helyekről érhető el:
-   Kattintson a **Termékinformációk kezelése** &gt; **Termékek** &gt; **Alaptermékek** lehetőségekre. A **Műveleti panel** modulon kattintson a **Termékdimenziók** elemre.
-   Kattintson a  **Termékinformációk kezelése** &gt; **Termékek** &gt; **Minden termék és alaptermék** lehetőségekre. Válasszon ki egy alapterméket. A **Műveleti panel** modulon kattintson a **Termékdimenziók** elemre.
-   Kattintson a **Termékinformációk kezelése** &gt; **Kiadott termékek** lehetőségekre. Válasszon ki egy alapterméket. A **Műveleti panel** modulon kattintson a **Termék** elemre. Az **Alaptermék** csoportban kattintson a **Termékdimenziók** gombra.

A változatok létrehozható egy cikkhez száma lehetséges termék cikkdimenzió-kombinációk száma korlátozza.

| **Tipp**                                                                                                                                              |
|------------------------------------------------------------------------------------------------------------------------------------------------------|
| Használatakor a termék, például egy olyan rendeléssort, választhat a termékdimenziókat, amellyel dolgozni szeretne termékváltozat azonosításához. |

## <a name="example"></a>Példa
Egy vállalat farmernadrágokat értékesít. A Farmernadrág cikknél a Szín és a Méret termékdimenziókat alkalmazzák. A farmernadrágok három különböző színben és hat különböző méretben kaphatók. Színek: Kék, Fekete, Barna Méretek: XS, S, M, L, XL, XXL Nem minden méretben érhető el mindhárom szín. Ha minden kombináció érvényes lenne, az 18 féle farmernadrágot jelentene. Ebben a példában csak a következő kilenc termék változat kombináció legyártva.

| Szín | Méret |
|-------|------|
| Kék  | XS   |
| Kék  | V    |
| Kék  | H    |
| Fekete | H    |
| Fekete | EREDMÉNY    |
| Fekete | XL   |
| Barna | K    |
| Barna | XL   |
| Barna | XXL  |






