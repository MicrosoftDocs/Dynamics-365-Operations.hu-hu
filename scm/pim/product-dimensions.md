---
title: "Termékdimenziók"
description: "Négy termékdimenzió létezik: szín, konfiguráció, méret és stílus. A termékdimenziókat dimenziócsoportokban kombinálhatja és hozzárendelheti a dimenziócsoportokat az alaptermékekhez. A cikkdimenziók kombinációi meghatározzák a termékváltozatokat is."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: EcoResProductDimension, EcoResProductDimensionGroup, EcoResProductMasterDimension, RetailEcoResColor, RetailEcoResSize, RetailEcoResStyle
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 19171
ms.assetid: 81fa3709-4ab8-4fbf-9806-359892a05985
ms.search.region: Global
ms.search.industry: Retail
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: 43cb4ed2ca77592fc23100fd74cb2bfa23c17f47
ms.contentlocale: hu-hu
ms.lasthandoff: 04/25/2017


---

# <a name="product-dimensions"></a>Termékdimenziók

[!include[banner](../includes/banner.md)]


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






