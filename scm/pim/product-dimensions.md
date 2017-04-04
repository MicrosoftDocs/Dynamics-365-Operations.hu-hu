---
title: "Termékdimenziók"
description: "Vannak négy cikkdimenziók – szín, konfiguráció, méretét és stílusát. A termékdimenziókat dimenziócsoportokban kombinálhatja és hozzárendelheti a dimenziócsoportokat az alaptermékekhez. A cikkdimenziók kombinációi meghatározzák a termékváltozatokat is."
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
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 8854ab94a71cc363bcd073d2df47bc01a243b6cd
ms.lasthandoff: 03/31/2017


---

# <a name="product-dimensions"></a>Termékdimenziók

Vannak négy cikkdimenziók – szín, konfiguráció, méretét és stílusát. A termékdimenziókat dimenziócsoportokban kombinálhatja és hozzárendelheti a dimenziócsoportokat az alaptermékekhez. A cikkdimenziók kombinációi meghatározzák a termékváltozatokat is.

Termékdimenziók olyan jellemzőket termékváltozat azonosítására szolgál. Cikkdimenziók kombinációi használhatja termékváltozatok meghatározására. Termékváltozat létrehozásához meg kell adnia legalább egy termékdimenzió alaptermék.
Termékváltozatok
----------------

Termékváltozatok is nevezik cikkeket. Cikk tárgyi eszközök termék, amely nem azonos a szolgáltatás fut. Egyben a szolgáltatástípushoz alaptermék definiálhat. A Szolgáltatástípus használatával megadhat szolgáltatásokat magukba foglaló termékváltozatokat. Például megadhatja a tanácsadói munka és a termékbevételezés változatok vezető tanácsadók és beosztott tanácsadók által végrehajtott munka alaptermék.

## <a name="product-dimensions"></a>Termékdimenziók
Érhetők el a következő cikkdimenziók: konfiguráció, szín, méret és stílus. Termékváltozat termék dimenzió értékek alapján jön létre.

Termék dimenzió értékek, például a méret, szín és stílus hozható létre a a **méretét**, **szín** és **stílus** lapok, amelyek a következő helyekről érhető el: **Termékinformációk kezelése**&gt;**a telepítő**&gt;**dimenzió- és változatszűrők csoportok**&gt;**méretek-színek-stílusok**. A Konfigurációdimenzió termékdimenzió-értékei általában a Termékkonfiguráló vagy a Dimenzión alapuló konfiguráló használatával hozhatók létre. A termékdimenziók létrehozása és karbantartása a **Termékdimenziók** oldalon lehetséges, amely a következő helyekről érhető el:
-   Kattintson a **Termékinformációk kezelése**&gt;**termékek**&gt;**alaptermékekhez**. A a **műveletpanel**, kattintson a **termékdimenziók**.
-   Kattintson a **Termékinformációk kezelése**&gt;**termékek**&gt;**minden termék és alaptermék**. Válasszon ki egy alapterméket. A a **műveletpanel**, kattintson a **termékdimenziók**.
-   Kattintson a **Termékinformációk kezelése**&gt;**, amely a termékek**. Válasszon ki egy alapterméket. A a **műveletpanel**, kattintson a **termék**. Az **Alaptermék** csoportban kattintson a **Termékdimenziók** gombra.

A változatok létrehozható egy cikkhez száma lehetséges termék cikkdimenzió-kombinációk száma korlátozza.
| **Tipp **                                                                                                                                              |
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




