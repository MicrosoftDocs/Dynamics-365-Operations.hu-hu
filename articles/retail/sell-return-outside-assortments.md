---
title: "Szortimenten kívüli termékek eladása és visszavétele"
description: "A Dynamics 365 for Retail segítségével szortimenteken kívüli termékeket értékesíthet és küldhet vissza."
author: pdp1207
manager: AnnBe
ms.date: 05/24/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailAssortmentDetails
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 
ms.search.region: Global
ms.search.industry: retail
ms.author: prabhup
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: fd00da1242964dddda5c19d46e61da33997e6d02
ms.contentlocale: hu-hu
ms.lasthandoff: 11/03/2017

---

# <a name="sell-and-return-products-outside-of-an-assortment"></a>Szortimenten kívüli termékek eladása és visszavétele
Minden kiskereskedőben közös, hogy termékeket értékesítenek az ügyfeleknek, vagy visszárut fogadnak el a vevőktől, még akkor is, ha az adott termék nem található meg az üzletben (vagyis a termékek nem tartoznak az üzlet szortimentjébe).
Íme néhány tipikus forgatókönyv:

+ Egy kiskereskedő nem tartja minden termékét egy adott üzletben. A fennmaradó termékeket a raktárban tárolják. Az üzlet alkalmazottja segítséget nyújthat az ügyfélnek a raktárban lévő termékek keresése vagy tallózása révén, hozzáadhatja azokat a kosárhoz, és elvégezheti a fizetést egy kiszállítási mód kiválasztásával, például a raktárból egy adott címre történő elküldésével, vagy a terméknek a vevő által az aktuális üzletből vagy egy másik üzletből történő felvételével.
+ A kiskereskedő üzletében nincsenek ott a kontkrét termékek, vagy nincsenek készleten abban az üzletben, ahol a vevő járt, de a termékek elérhetők más üzletekben. Az üzlet alkalmazottja segítséget nyújthat az ügyfélnek a raktárban lévő termékek keresése vagy tallózása révén, hozzáadhatja azokat a kosárhoz, és elvégezheti a fizetést egy kiszállítási mód kiválasztásával.
+ A kiskereskedő számos üzlettel rendelkezik egy bizonyos város vagy irányítószám körzetében, és nem akarja az ügyfeleket arra kényszeríteni, hogy ugyanabba az üzletbe vigyék vissza a termékeket, amelyikben vásárolták őket. Ehelyett a vevők bármelyik üzletbe visszavihetik a termékeket.


A Dynamics 365 for Retail használatával ezek az általános forgatókönyvek elérhetők a kiskereskedők számára. A Retail alkalmazással a következőket teheti:
+ Más üzletekben lévő termékek keresése vagy tallózása.
+ Az összes kiadott termék keresése vagy tallózása.
+ Cash-and-carry típusú tranzakciók vagy vevői rendelések létrehozása.
+ Vevői rendelések szállítási lehetőségeinek kiválasztása.
+ Termékek átvétele az aktuális üzletben vagy egy másik üzletben.
+ Rendelés érvénytelenítése az aktuális üzletben vagy egy másik üzletben.
+ Visszárurendelés nyugtával vagy anélkül a jelenlegi vagy egy másik üzletben.

