---
title: Ármódosítások és engedmények
description: Ez a cikk ármódosításokkal és engedményekkel kapcsolatban tartalmaz tájékoztatást a Dynamics 365 Commerce rendszerben.
author: scott-tucker
manager: AnnBe
ms.date: 11/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailParameters, RetailPeriodicDiscount
audience: Application User
ms.reviewer: josaw
ms.custom: 15891
ms.assetid: bab5adf3-ddf0-4c22-a2eb-b4d25b88de99
ms.search.region: global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: f29e90e1c61792c70d4d6eaeee7758676bf193b2
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4972481"
---
# <a name="price-adjustments-and-discounts"></a>Ármódosítások és engedmények

[!include [banner](includes/banner.md)]

Ez a cikk ármódosításokkal és engedményekkel kapcsolatban tartalmaz tájékoztatást a Dynamics 365 Commerce rendszerben.

A Commerce rendszerben módosíthatja a termékek árát, és engedményeket állíthat be egy sortételre vagy pénztári (POS) tranzakcióra, a hívásközpont értékesítési rendelésére, vagy akár egy online megrendelésre is. Az ármódosításokat és az engedményeket konkrét árcsoportokhoz is hozzákötheti. Ármódosítások és engedmények esetében is megadhat egyetlen kezdő és záró dátumot vagy egy ismétlődő időtartamot, egy engedménykódot, és néhány további attribútumot. 

Az ármódosítások és engedmények alkalmazhatók termékekre, változatokra vagy kategóriákra is. Ha egynél több engedmény vonatkozik egy termékre, a vevő megkaphatja az egyiket, vagy egy kombinált engedményt, az engedmény beállításaitól függően. A Commerce rendszer automatikusan alkalmazza az engedményt vagy az engedménykombinációt, és a vevő számára a legjobb árat adja. Ármódosítás vagy engedmény beállításakor mindenképpen győződjön meg arról, hogy az árcsoportok a megfelelő csatornákhoz, katalógusokhoz, fiókokhoz vagy hűségprogramokhoz vannak hozzárendelve, amelyekre szeretné, hogy vonatkozzon az engedmény. Továbbá, ha szeretne automatikusan engedmény-azonosítót generálni, akkor a **Commerce paraméterek** oldalon az új engedmény vagy ármódosítás megadása előtt beállíthatja a számsorozatokat.

> [!NOTE]
> Az ármódosítások és az engedmények törölhetők is. A statisztikai adatok azonban el fognak veszni.

## <a name="types-of-discounts"></a>Kedvezmények típusai

Számos típusú engedmény érhető el:

- **Egyszerű engedmény** – egy adott százalék vagy összeg.
- **Mennyiségi engedmény** – A két vagy több termék megvásárlásakor alkalmazott engedmény.
- **Kombinációs engedmény** – A kombinációs engedmény akkor biztosít engedményt, ha a termékek meghatározott kombinációját vásárolják meg.
- **Küszöbérték szerinti engedmény** – Olyan engedmény, amely esetében a tranzakció összege több mint egy meghatározott mennyiség.
- **Fizetőeszköz-alapú engedmény** – Olyan engedmény, amely akkor kerül alkalmazásra, ha a tranzakció összege meghaladja a megadott összeget, és egy adott fizetési típus (például készpénz, hitel vagy betéti kártya) kerül a fizetéshez.
- **Szállítási engedmény** – Olyan engedmény, amely akkor kerül alkalmazásra, ha a tranzakció összege meghaladja a megadott összeget, és a rendelésen egy adott szállítási mód (például kétnapos szállítás vagy egynapos szállítás) kerül alkalmazásra.

Az ármódosításokat és az engedményeket konkrét árcsoportokhoz is hozzárendelheti. Az árcsoportok ezután társíthatók csatornákhoz, katalógusokhoz, fiókokhoz és hűségprogramokhoz.
