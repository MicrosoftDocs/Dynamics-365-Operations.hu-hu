---
title: Késések
description: Ez a cikk az alaptervezésben szereplő késleltetett dátumokról szolgál információval. A késleltetett dátum egy olyan valós határidő, amelyet a tranzakció kap meg, akkor ha az alaptervezés által kiszámított legkorábbi teljesítési dátum későbbre esik, mint a kért dátum.
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
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
ms.openlocfilehash: a87b19732f413aa2844101f76dea83535da86599
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "359612"
---
# <a name="delays"></a>Késések

[!include [banner](../includes/banner.md)]

Ez a cikk az alaptervezésben szereplő késleltetett dátumokról szolgál információval. A késleltetett dátum egy olyan valós határidő, amelyet a tranzakció kap meg, akkor ha az alaptervezés által kiszámított legkorábbi teljesítési dátum későbbre esik, mint a kért dátum.

Az alaptervezés kiszámíthatja egy tranzakció legkorábbi teljesítési dátumát, az átfutási idők, az anyagok rendelkezésre állása, a rendelkezésre álló kapacitás és a különböző tervezési paraméterek alapján. 

Ha az alaptervezés olyan rendelési dátumot számít ki, amely az aktuális dátumnál korábbi, akkor a rendelés időben nem teljesíthető. Emiatt a rendelés késik. Ebben az esetben az alaptervezés az aktuális dátumtól kezdve előretolja a tervet, és figyelembe veszi az átfutási időket is. Ezek az átfutási idők bármely alacsonyabb szintű összetevő elemmel kezdődhetnek. A rendelés ezután egy késleltetett dátumot kap. A késleltetett dátum egy valószerű, a tényleges adatokon alapuló dátum lesz. Az alaptervezés emellett a késés napjait is kiszámítja. 

Bizonyos esetekben előfordulhat, hogy nem kívánja kiszámolni a késést, például amikor a felhasználók tudják, hogy alternatív szállítási módok kiválasztásával megsürgethetik az átfutási időt. 

Beállíthatja, hogyan számítsa ki a rendszer a fedezetcsoport késéseit. Ezt követően csatolhatja a fedezetcsoportot egy cikkhez. 

Az **Alaptervezés paraméterei** lapon beállíthatja a késések számításának kezdő időpontját. Ha egy rendelés ezen időpont után teljesül, akkor egy nap hozzáadódik a rendelés késési dátumához. 

**Megjegyzés:** A korábbi változatokban a késések kiszámítását *határidő-üzeneteknek* nevezték, a késleltetett dátum neve *határiő dátum* volt, a késleltetett tranzakcióé pedig *beállított jövőbeli tranzakció*.

<a name="additional-resources"></a>További erőforrások
--------

[Fedezeti beállítások](coverage-settings.md)



