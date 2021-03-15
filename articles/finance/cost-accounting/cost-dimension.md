---
title: Dimenziók létrehozása és dimenziótagok importálása
description: A költségkönyvelés független modul, amely alapadatokat igényel más modulokból.
author: ShylaThompson
manager: AnnBe
ms.date: 09/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMDimension
audience: Application User
ms.reviewer: roschlom
ms.custom: 256254
ms.assetid: e1b0a6e3-0c72-4a7d-90e1-20f870c6dbad
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 610a9302610af7a074a91dfc2a8c87725b0a1a82
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "5009493"
---
# <a name="create-dimensions-and-import-dimension-members"></a>Dimenziók létrehozása és dimenziótagok importálása

[!include [banner](../includes/banner.md)]

A költségkönyvelés független modul, amely adatokat igényel más modulokból. Az adatok a következők szerint csoportosíthatók:

-  Költségösszetevők
-  Költségobjektumok
-  Statisztikai dimenziók

Egy **költségösszetevő** a számlatükör valamely költségfüggő elemének felel meg. A **költségobjektum** bármilyen típusú pénzügyi dimenziónak felel meg, például termékek, költséghelyek és projektek, amelyekre becslést kíván végezni, költségeket akar rendelni, vagy közvetlenül mérni szeretné őket. A **statisztikai dimenzió** és a tagjai a nem monetáris tételek regisztrálására szolgálnak. A statisztikai dimenziótagok felosztási alapként használhatók a költségfelosztásben és a felosztásban 

A következő ábra bemutatja a költségkönyvelésben használt dimenziókat.

[![Költségkönyvelés dimenziók](./media/cost-eos-dimensions.png)](./media/cost-eos-dimensions.png)

Miután a költségkönyvelésbe importálta az adatokat, különféle szempontok létrehozásához használhatja, hogy információkat nyújthasson a vezetőknek a szervezet minden szintjén. Az alábbi témakörök a dimenziók létrehozásával és a dimenziótagok importálásával kapcsolatban nyújtanak tájékoztatást. 

-  [Költségösszetevő-dimenziók](cost-elements.md)
-  [Költségösszetevők létrehozása](./tasks/create-cost-elements.md)
-  [Költségobjektum-dimenziók](cost-objects.md)
-  [Költségösszetevő-dimenziótagok hozzárendelése a dimenziótagok általános készletéhez](map-cost-elements-dimension-members.md)
-  [Költségösszetevő-dimenzió feltérképezése](./tasks/map-cost-element-dimension.md)
-  [Statisztikai dimenziótagok és statisztikaimérték-szolgáltató sablonok](statistical-measure-provider-template.md)








[!INCLUDE[footer-include](../../includes/footer-banner.md)]