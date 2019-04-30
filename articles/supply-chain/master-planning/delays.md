---
title: Késések
description: Ez a témakör az alaptervezésben szereplő késleltetett dátumokról szolgál információval. A késleltetett dátum egy olyan valós határidő, amelyet a tranzakció kap meg, akkor ha az alaptervezés által kiszámított legkorábbi teljesítési dátum későbbre esik, mint a kért dátum.
author: roxanadiaconu
manager: AnnBe
ms.date: 03/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqTransFuturesListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 19311
ms.assetid: 5ffb1486-2e08-4cdc-bd34-b47ae795ef0f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7c26fedf15118a304469604527c33a25871356be
ms.sourcegitcommit: 8eac5eee94bb32143df44c82a2dfdbe903967af8
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/20/2019
ms.locfileid: "878310"
---
# <a name="delays"></a>Késések

[!include [banner](../includes/banner.md)]

Ez a témakör az alaptervezésben szereplő késleltetett dátumokról szolgál információval. A késleltetett dátum egy olyan valós határidő, amelyet a tranzakció kap meg, akkor ha az alaptervezés által kiszámított legkorábbi teljesítési dátum későbbre esik, mint a kért dátum.

Az alaptervezés kiszámíthatja egy tranzakció legkorábbi teljesítési dátumát, az átfutási idők, az anyagok rendelkezésre állása, a rendelkezésre álló kapacitás és a különböző tervezési paraméterek alapján. 

Ha az alaptervezés olyan rendelési dátumot számít ki, amely az aktuális dátumnál korábbi, akkor a rendelés időben nem teljesíthető. Emiatt a rendelés késik. Ebben az esetben az alaptervezés az aktuális dátumtól kezdve előretolja a tervet, és figyelembe veszi az átfutási időket is. Ezek az átfutási idők bármely alacsonyabb szintű összetevő elemmel kezdődhetnek. A rendelés ezután egy késleltetett dátumot kap. A késleltetett dátum egy valószerű, a tényleges adatokon alapuló dátum lesz. Az alaptervezés emellett a késés napjait is kiszámítja. 

Bizonyos esetekben előfordulhat, hogy nem kívánja kiszámolni a késést, például amikor a felhasználók tudják, hogy alternatív szállítási módok kiválasztásával megsürgethetik az átfutási időt. 

Beállíthatja, hogyan számítsa ki a rendszer a fedezetcsoport késéseit. Ezt követően csatolhatja a fedezetcsoportot egy cikkhez. 

Az **Alaptervezés paraméterei** lapon beállíthatja a késések számításának kezdő időpontját. Ha egy rendelés ezen időpont után teljesül, akkor egy nap hozzáadódik a rendelés késési dátumához. 

> [!Megjegyzés} A korábbi változatokban a késések kiszámítását *határidő-üzeneteknek* nevezték, a késleltetett dátum neve *határidő dátum* volt, a késleltetett tranzakcióé pedig *beállított jövőbeli tranzakció*.

## <a name="desired-date"></a>Kívánt dátum

A **Tervezett rendelés** oldalon a **Késések** lapon található a tervezett rendelés **Kívánt dátuma**. Egy tervezett rendelés kívánt dátuma a késések alapdátuma, amely egy számított dátum, a **Kért dátum** értékével egyezik meg, amelyet a **Nettó követelmény** értékéből számítottak. Ha a tervezett rendelés anyagjegyzéksor, termelési sor vagy kanbansor, akkor a kívánt dátum kiszámítása a **Követelmény dátuma** értékén alapul, és a kívánt dátum nem jelenik meg a **Tervezett rendelés** oldalon.

<a name="additional-resources"></a>További erőforrások
--------

[Fedezeti beállítások](coverage-settings.md)
