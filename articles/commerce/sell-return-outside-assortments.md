---
title: Értékesített és a visszaküldött termékek, amelyek nem részei egy üzlet szortimentjének
description: Szortimenten kívüli termékek eladása és visszavétele a Dynamics 365 Commerce rendszerben.
author: pdp1207
manager: AnnBe
ms.date: 05/24/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailAssortmentDetails
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.search.region: Global
ms.search.industry: retail
ms.author: prabhup
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 4f0801828086a7c5cc316895b5426a184a345ce1
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4982400"
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
