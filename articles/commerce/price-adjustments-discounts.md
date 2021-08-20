---
title: Ármódosítások és engedmények
description: Ez a cikk ármódosításokkal és engedményekkel kapcsolatban tartalmaz tájékoztatást a Dynamics 365 Commerce rendszerben.
author: scott-tucker
ms.date: 06/11/2021
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 96a695df250cda514b7bd8b9716c0f03fb2bfd28d3af4daedaf1335c3099fbb6
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6748498"
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

> [!NOTE]
> A kombinációs engedménynek és a küszöbérték-engedménynek vannak „Kedvezményre nem jogosult termékek számolása” és „Kedvezményre nem jogosult termékek számolása a küszöbbel szemben” tulajdonságaik. Ha ezek a tulajdonságok engedélyezve vannak, akkor lehet olyan cikk esetében is lehetséges érvényesíteni a tranzakciót, amelyik nem jogosult az engedményre, de a nem jogosult cikk nem kap engedményt. 
> 
> Ha például két sorból – A és B – áll a kombinációs engedmény, ahol a vevőnek 10%-os kedvezményt kell kapnia mindkét cikkből, de az A cikknél be van jelölve az "Összes engedmény megakadályozása" konfiguráció, akkor ez általában megakadályozza, hogy az A cikk beleszámítson az engedménybe. Ha viszont engedélyezve van a „Kedvezményre nem jogosult termékek számolása” tulajdonság, az "A" cikk felhasználható a kombinációs engedményre való jogosultságra, de a 10% engedmény csak a B cikkre lesz érvényes. Hasonló logika vonatkozik a küszöbérték-engedményre is. 
>
> A "Kedvezményre nem jogosult termékek számolása a küszöbbel szemben" tulajdonság azonban további képességeket is képes alkalmazni a kombinációs engedmények "Kedvezményre nem jogosult termékek számolása" tulajdonsághoz képest. Ha engedélyezve van a küszöbérték-engedmény, és van olyan cikk, amelynek van olyan engedménye, amely megakadályozza, hogy a cikk más engedményeket kapjon, akkor az adott cikkért fizetett ár megfelelő lesz a küszöbértéknek, de ez a cikk nem fog kapni további engedményt.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
