---
title: Kiskereskedelmi termékek engedményeinek megakadályozásának lehetőségei
description: Különböző okai lehetnek annak, hogy a kiskereskedők megakadályozzák bizonyos termékek engedménnyel való ellátását, akár promóció, akár a POS-ban történő eladás során.
author: jblucher
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailPeriodicDiscount
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 85183
ms.assetid: e8c5a24f-7edd-4fd6-af80-5e0ac9f03127
ms.search.region: Global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 64f54c1a63706ccd9225d47df96ffc3f88cf3332
ms.sourcegitcommit: e2fb0846fcc6298050a0ec82c302e5eb5254e0b5
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/27/2019
ms.locfileid: "1606918"
---
# <a name="options-for-preventing-discounts-for-retail-products"></a>Kiskereskedelmi termékek engedményeinek megakadályozásának lehetőségei

[!include [banner](includes/banner.md)]

Különböző okai lehetnek annak, hogy a kiskereskedők megakadályozzák bizonyos termékek engedménnyel való ellátását, akár promóció, akár a POS-ban történő eladás során.

A következő opciók, amelyek a kiadott termékek **Kiskereskedelem** lapján találhatók, lehetővé teszik a termék konfigurálását az összes vagy a manuális kedvezmények megakadályozása érdekében. A beállítások kategóriaszinten is meghatározhatók a kiskereskedelmi kategóriák hierarchiájából.

- **Minden kedvezmény megakadályozása** – Válassza ezt a lehetőséget, hogy megakadályozza bármilyen típusú kedvezmény alkalmazását erre a termékre. Ilyenek például a kombinációs engedmények, a mennyiségi engedmények és a küszöbérték szerinti engedmények, valamint a POS-felhasználó által az értékesítés során alkalmazott manuális sor- és tranzakciós engedmények.
- **Manuális engedmények megakadályozása** – Ezzel a beállítással csak a POS-felhasználó által az értékesítés során alkalmazott manuális vagy tranzakciós engedményeket akadályozza meg. Az ezzel a lehetőséggel rendelkező termékek továbbra is jogosultak az olyan promóciókra, mint például a kombinációs engedmények, a mennyiségi és a küszöbérték szerinti engedmények.

> [!NOTE]
> Ezek a beállítások nem korlátozzák az árfelülírás műveletet, mivel a beállítás az alapárat határozza meg, és nem minősül kedvezménynek.

[![Engedmények megakadályozása mező](./media/prevent-discounts.png)](./media/prevent-discounts.png)
