---
title: "Ármódosítások és engedmények"
description: "Ez a cikk ismerteti ármódosítások és engedmények kiskereskedelmi és kereskedelmi műveletek a Microsoft Dynamics 365."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 15891
ms.assetid: bab5adf3-ddf0-4c22-a2eb-b4d25b88de99
ms.search.region: global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 01f249cbdabc6febf23dcd7103d4587cecdaad08
ms.lasthandoff: 03/31/2017


---

# <a name="price-adjustments-and-discounts"></a>Ármódosítások és engedmények

Ez a cikk ismerteti ármódosítások és engedmények kiskereskedelmi és kereskedelmi műveletek a Microsoft Dynamics 365.

Dynamics 365 - műveletekhez kiskereskedelmi, végezhet szervizdíj-helyesbítés termékek és is beállíthatja, hogy sortétel vagy tranzakció eladási (POS), engedmények can hívás center értékesítési rendelés vagy online megrendelés. Az ármódosításokat és az engedményeket konkrét árcsoportokhoz is hozzákötheti. Ármódosítások és engedmények esetében is megadhat egyetlen kezdő és záró dátumot vagy egy ismétlődő időtartamot, egy engedménykódot, és néhány további attribútumot. Az ármódosítások és engedmények alkalmazhatók termékekre, változatokra vagy kategóriákra is. Ha egynél több engedmény vonatkozik egy termékre, a vevő megkaphatja az egyiket, vagy egy kombinált engedményt, az engedmény beállításaitól függően. 365 Dynamics műveletek automatikusan alkalmazza a kedvezmény vagy engedmények kombinációja, amely a legjobb áron biztosít az ügyfélnek. Ármódosítás vagy engedmény beállításakor mindenképpen győződjön meg arról, hogy az árcsoportok a megfelelő csatornákhoz, katalógusokhoz, fiókokhoz vagy hűségprogramokhoz vannak hozzárendelve, amelyekre szeretné, hogy vonatkozzon az engedmény. Továbbá, ha szeretne automatikusan engedmény-azonosítót generálni, akkor a **Kiskereskedelmi paraméterek** oldalon az új engedmény vagy ármódosítás megadása előtt beállíthatja a számsorozatokat. **Megjegyzés:** Az ármódosítások és az engedmények törölhetők is. A statisztikai adatok azonban el fognak veszni.

### <a name="types-of-discounts"></a>Kedvezmények típusai

Négyféle kiskereskedelmi engedmény érhető el:

-   **Egyszerű engedmény** – egy adott százalék vagy összeg.
-   **Mennyiségi engedmény** – A két vagy több termék megvásárlásakor alkalmazott engedmény.
-   **Kombinációs engedmény** – A kombinációs engedmény akkor biztosít engedményt, ha a termékek meghatározott kombinációját vásárolják meg.
-   **Küszöbérték szerinti engedmény** – Olyan engedmény, amely esetében a tranzakció összege több mint egy meghatározott mennyiség.

Az ármódosításokat és az engedményeket konkrét árcsoportokhoz is hozzárendelheti. Az árcsoportok ezután társíthatók csatornákhoz, katalógusokhoz, fiókokhoz és hűségprogramokhoz.


