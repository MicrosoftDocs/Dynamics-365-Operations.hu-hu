---
title: SEPA beszedési megbízás beállítása
description: Az egységes eurófizetési térség (SEPA) beszedési megbízással a hitelező pénzt szedhet be a vevő bankszámlájáról, feltéve , ha a vevő aláírt meghatalmazást adott a hitelezőnek.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustParameters
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 59491
ms.assetid: 653a135f-c515-4ae3-9da2-82b5e1f103b5
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 757f3f6e0c5443054d2d6bd21381d9f692e1b9a5
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "334818"
---
# <a name="set-up-sepa-direct-debit-mandate"></a>SEPA beszedési megbízás beállítása

[!include [banner](../includes/banner.md)]

Az egységes eurófizetési térség (SEPA) beszedési megbízással a hitelező pénzt szedhet be a vevő bankszámlájáról, feltéve , ha a vevő aláírt meghatalmazást adott a hitelezőnek. A rendelet, amit a vevő aláírás engedélyez egy hitelezőnek, hogy gyűjtse össze a fizetéstést és utasítja a vevő bankját a beszedés kifizetésére. A témakör célja, hogy bemutassa a SEPA beszedési megbízási felhatalmazások beállításának folyamatát.

## <a name="prerequisites"></a>Előfeltételek
Az alábbi táblázat bemutatja a munka megkezdése előtt biztosítandó előfeltételeket.

| Kategória       | Előfeltételek                                                                                                                                              |
|----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|
| Ország/régió | A jogi személy elsődleges címének a következő ország/régió valamelyikében kell lennie: Ausztria, Belgium, Németország, Spanyolország, Franciaország, Olaszország vagy Hollandia. |

1. Állítson be egy számsorozatok a beszedési megbízásoktól. Minden egyes beszedési megbízásnak egyedi számmal kell rendelkeznie. A **Számsorozatok** oldalon a beszedési megbízási meghatalmazások számára számsorozatot hozhat létre. Ezzel az azonosítóval rendelheti hozzá a számsorozatot a beszedési megbízási felhatalmazás rendszeréhez a **Fiók Kinnlevőségek paraméterei** képernyőn.

2. A beszedési megbízási meghatalmazásokhoz tartozó Kinnlevőségek modul paramétereinek beállítása Használja a **Kinnlevőségek paraméterei** oldalt a beszedési megbízási felhatalmazások paramétereinek beállítására. A paraméterek beállításához a **Beszedési megbízás** lapon módosítsa az alapértelmezett paramétereket igény szerint. Ezt követően, a **Számsorozatok** lapon frissítse a **Beszedési megbízási felhatalmazás azonosítója** mezőt a korábban megadott számsorozattal.

3. A beszedési megbízási felhatalmazások fizetési mód beállítása – A beszedési megbízási meghatalmazásokhoz fizetési módot is be kell állítani. Ezt a fizetési módot használhatja azon számlák lekérdezéseihez, amelyekhez beszedési megbízásos kifizetést kíván létrehozni. Hasznélja a **Fizetési módszerek** lapot a fizetési módszerek beállításához. A beszedési megbízási felhatalmazások fizetési mód beállításához be kell tartani a fizetési mód következő lépéseit:

-   A **Fizetés típus** mezőben válassza ki az **Elektronikus fizetés** lehetőséget.
-   Opcionális lépés: Ha valószínűsíti, hogy vevői egynél több beszedési megbízást fognak fenntartani, akkor az **Időszak** mezőben a **Számla** beállítást válassza. Ez minden számlához külön kifizetést hoz létre, és minden kifizetés a számlában meghatározott meghatalmazást használja.
-   Válassza ki a **Felhatalmazás igénylése** lehetőséget a beszedési megbízási felhatalmazások használata által a kifizetések létrehozásához. A **Felhatalmazás igénylése** lehetőség csak akkor érhető el, ha az **Elektronikus fizetés** be van jelölve a **Fizetés típusa** mezőben.

További erőforrások

[Beszedési megbízás – áttekintés](sepa-direct-debit-overview.md) 

[Beszedési megbízási felhatalmazás létrehozása vevő részére](tasks/create-direct-debit-mandate-customer.md) 

