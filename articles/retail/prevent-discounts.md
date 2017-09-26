---
title: "Kiskereskedelmi termékek engedményeinek megakadályozása"
description: "Különböző okai lehetnek annak, hogy a kiskereskedők megakadályozzák bizonyos termékek engedménnyel való ellátását, akár promóció, akár a POS-ban történő eladás során."
author: jeffbl
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 85183
ms.assetid: e8c5a24f-7edd-4fd6-af80-5e0ac9f03127
ms.search.region: Global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: c124ecf104bdb3de786c9dd98c2b07a4c9c04041
ms.openlocfilehash: 0debfe984a83295dde145fe4b8c2deb836345cd6
ms.contentlocale: hu-hu
ms.lasthandoff: 07/31/2017

---

# <a name="prevent-discounts-for-retail-products"></a>Kiskereskedelmi termékek engedményeinek megakadályozása

[!include[banner](includes/banner.md)]

Különböző okai lehetnek annak, hogy a kiskereskedők megakadályozzák bizonyos termékek engedménnyel való ellátását, akár promóció, akár a POS-ban történő eladás során.

A következő opciók, amelyek a kiadott termékek **Kiskereskedelem** lapján találhatók, lehetővé teszik a termék konfigurálását az összes vagy a manuális kedvezmények megakadályozása érdekében. A beállítások kategóriaszinten is meghatározhatók a kiskereskedelmi kategóriák hierarchiájából.

**Minden kedvezmény megakadályozása**: Válassza ezt a lehetőséget, hogy megakadályozza bármilyen típusú kedvezmény alkalmazását erre a termékre. Ilyenek például a kombinációs engedmények, a mennyiségi engedmények és a küszöbérték szerinti engedmények, valamint a POS-felhasználó által az értékesítés során alkalmazott manuális sor- és tranzakciós engedmények.

**Manuális engedmények megakadályozása**: Ezzel a beállítással csak a POS-felhasználó által az értékesítés során alkalmazott manuális vagy tranzakciós engedményeket akadályozza meg. Az ezzel a lehetőséggel rendelkező termékek továbbra is jogosultak az olyan promóciókra, mint például a kombinációs engedmények, a mennyiségi és a küszöbérték szerinti engedmények.

**Megjegyzés:**: Ezek a beállítások nem korlátozzák az árfelülírás műveletet, mivel a beállítás az alapárat határozza meg, és nem minősül kedvezménynek.  

![engedmények megakadályozása mező](/media/prevent-discounts.png)

