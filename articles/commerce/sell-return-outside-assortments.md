---
title: Értékesített és a visszaküldött termékek, amelyek nem részei egy üzlet szortimentjének
description: Szortimenten kívüli termékek eladása és visszavétele a Dynamics 365 Commerce rendszerben.
author: josaw1
ms.date: 05/24/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.custom: ''
ms.search.industry: retail
ms.search.form: RetailAssortmentDetails
ms.openlocfilehash: d2444d7812cffc832986589825b332d60a508b18
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9275032"
---
# <a name="sell-and-return-products-that-arent-part-of-a-stores-assortment"></a>Értékesített és a visszaküldött termékek, amelyek nem részei egy üzlet szortimentjének

[!include [banner](includes/banner.md)]

Minden kiskereskedőben közös, hogy termékeket értékesítenek az ügyfeleknek, vagy visszárut fogadnak el a vevőktől, még akkor is, ha az adott termék nem található meg az üzletben (vagyis a termékek nem tartoznak az üzlet szortimentjébe).

Íme néhány tipikus forgatókönyv:

+ Egy kiskereskedő nem tartja minden termékét egy adott üzletben. A fennmaradó termékeket a raktárban tárolják. Az üzlet alkalmazottja segítséget nyújthat az ügyfélnek a raktárban lévő termékek keresése vagy tallózása révén, hozzáadhatja azokat a kosárhoz, és elvégezheti a fizetést egy kiszállítási mód kiválasztásával, például a raktárból egy adott címre történő elküldésével, vagy a terméknek a vevő által az aktuális üzletből vagy egy másik üzletből történő felvételével.
+ A kiskereskedő üzletében nincsenek ott a kontkrét termékek, vagy nincsenek készleten abban az üzletben, ahol a vevő járt, de a termékek elérhetők más üzletekben. Az üzlet alkalmazottja segítséget nyújthat az ügyfélnek a raktárban lévő termékek keresése vagy tallózása révén, hozzáadhatja azokat a kosárhoz, és elvégezheti a fizetést egy kiszállítási mód kiválasztásával.
+ A kiskereskedő számos üzlettel rendelkezik egy bizonyos város vagy irányítószám körzetében, és nem akarja az ügyfeleket arra kényszeríteni, hogy ugyanabba az üzletbe vigyék vissza a termékeket, amelyikben vásárolták őket. Ehelyett a vevők bármelyik üzletbe visszavihetik a termékeket.

A Commerce használatával ezek az általános forgatókönyvek elérhetők a kiskereskedők számára. A Commerce alkalmazással a következőket teheti:

+ Más üzletekben lévő termékek keresése vagy tallózása.
+ Az összes kiadott termék keresése vagy tallózása.
+ Cash-and-carry típusú tranzakciók vagy vevői rendelések létrehozása.
+ Vevői rendelések szállítási lehetőségeinek kiválasztása.
+ Termékek átvétele az aktuális üzletben vagy egy másik üzletben.
+ Rendelés érvénytelenítése az aktuális üzletben vagy egy másik üzletben.
+ Visszárurendelés nyugtával vagy anélkül a jelenlegi vagy egy másik üzletben.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
