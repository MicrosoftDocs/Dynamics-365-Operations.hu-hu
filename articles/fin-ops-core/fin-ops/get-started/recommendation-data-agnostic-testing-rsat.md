---
title: Adatagnosztikus tesztelés a Regression Suite Automation Tool segítségével
description: Ez a cikk a Regression Suite Automation Tool.
author: FrankDahl
ms.date: 09/13/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: fdahl
ms.search.validFrom: 2019-09-11
ms.dyn365.ops.version: AX 7.0.0, Operations
ms.custom: 21761
ms.openlocfilehash: f4322cb76d1d83c02ec9d4dcb997a1cd4730d090
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9269591"
---
# <a name="data-agnostic-testing-using-the-regression-suite-automation-tool"></a>Adatagnosztikus tesztelés a Regression Suite Automation Tool használatával

[!include [banner](../includes/banner.md)]

Noha egy ERP-alkalmazás működési ellenőrzése nem lehet teljes mértékben agnosztikus, több fázis és megközelítés létezik a teszteléshez. Ezek a tesztelési fázisok például a következők:  

- SysTest keretrendszer
- ATL-keretrendszer
- Regression Suite Automation Tool (RSAT)

[![Tesztbesorolási piramis.](./media/rsat-data-agnostic-testing-01.PNG)](./media/rsat-data-agnostic-testing-01.PNG)

## <a name="overview"></a>Áttekintés
-   **SysTest keretrendszer** – A SysTest keretrendszer megbízható a fajlagos tesztek elvégzéséhez. Mivel az egységtesztek általában egy módszer vagy funkció tesztelésére szolgálnak, mindig adatagnosztikusnak kell lenniük, és csak a teszt részeként megadott bemeneti adatoktól függhetnek.
-   **ATL-keretrendszer** – A Microsoft egy ATL-keretrendszert tartalmaz, amely egy absztrakció a SysTest-keretrendszeren, és a funkcionális teszt írását sokkal egyszerűbben és megbízhatóbban teszi lehetővé. Ezt a keretrendszert kell használni az összetevőtesztek vagy egyszerű integrációs tesztek írásához.
-   **RSAT** – Az RSAT az integrációs tesztekhez és az üzleti ciklusok tesztjeihez használatos. Az üzleti ciklusok tesztjei, más néven a regresszió-ellenőrzési tesztek, a meglévő adatoktól függenek. Ezek a tesztek azonban akkor válhatnak adatagnosztikussá, ha további tényezőket is figyelembe vesz. 

    - o Miközben az egységtesztek és az összetevőtesztek alacsony szintűek, és teljes egészében adatagnosztikusak (nem függenek a meglévő adathalmaztól), az üzleti ciklus vagy a regresszió-ellenőrzési tesztek néhány meglévő adattól függenek. Ezek közé tartozik a beállítás, a konfigurációs beállítások (paraméterek) és az alapadatok (vevők, szállítók, cikkek stb.), de nem tranzakciós adatok. Győződjön meg róla, hogy a teszt során, ha ezek közül bármelyik módosult, a végső teszt részeként visszaállították.
    - Alapadatok kiválasztása meghatározott feltételek alapján az adott rekord kiválasztása helyett. Ha például egy cikk kiválasztása a dimenzióértékek és a készlet elérhetősége alapján történik, akkor szűrje a terméklistát ezekkel az értékekkel, válassza ki az első elemet, majd másolja át a jövőbeli tesztekhez használandó számot. Ha egyszerű alapadatsor – például vevő, szállító vagy termék –, akkor az automatizálás részeként lehet létrehozni, és a későbbiekben a láncolási tesztekben használatos. 
    - o írja be az egyedi azonosítókat, például a számlaszámot, a számsorozaton keresztül vagy a következő Microsoft Excel funkciókkal: =TEXT(NOW(),"yyyymmddhhmm"). Ez a funkció percenként ad egyedi számot, amely lehetővé teszi, hogy nyomon követhesse a művelet megtörténtét. Ez használható olyan változóknál, mint a termékbizonylat-számok és a szállítói számlák száma. Ez a teszt továbbra is ugyanazokon az adatbázisokon dolgozik újra és újra, anélkül, hogy helyreállításra lenne szüksége.
    - Mindig állítsuk be a környezet **szerkesztési módját** **Olvasás** vagy **Szerkesztés** értékre az első tesztként, mert az alapértelmezett beállítás **Automatikus**. Az **Automatikus** lehetőségek mindig az előző beállítást használja, és nem megbízható teszteket okozhat. 
 
    [![Beállítások lap, Teljesítmény lap.](./media/rsat-data-agnostic-testing-02.PNG)](./media/rsat-data-agnostic-testing-02.PNG)
 
    - Érvényesítést csak az adott tranzakcióra vonatkozó szűrés után végezzen, az általános érvényesítés helyett. A rekordok számának megadásához például tranzakció számára vagy a tranzakció dátumára szűrjön, hogy az ellenőrzés kizárja az összes többi tranzakciót. 
    - Ha bejelöli a vevői egyenleget vagy a költségvetés-ellenőrzést, először mentse az értéket, majd adja hozzá a tranzakció értékét, hogy a várt eredményt érvényesítse a fix várt érték ellenőrzése helyett. 
 


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
