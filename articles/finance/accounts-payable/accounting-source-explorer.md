---
title: Könyvelési források böngészője
description: Ez a cikk a Könyvelési forrás intéző lapról nyújt tájékoztatást, amely a főkönyvi könyvelési tételeken alapuló forrásinformációk részletes elemzésére használható.
author: RyanCCarlson2
ms.date: 11/21/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AccountingSourceExplorer
audience: Application User
ms.reviewer: kfend
ms.custom: 15391
ms.assetid: 57b95899-7298-43c0-8034-45b5d993cbf2
ms.search.region: Global
ms.author: rcarlson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5bd5580dc0be37ec89e6c7934b47c7d5593d8716
ms.sourcegitcommit: 5f8f042f3f7c3aee1a7303652ea66e40d34216e3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/29/2022
ms.locfileid: "9806433"
---
# <a name="accounting-source-explorer"></a>Könyvelési források böngészője

[!include [banner](../includes/banner.md)]

Ez a cikk a **Könyvelési forrás intéző** lapról nyújt tájékoztatást, amely a főkönyvi könyvelési tételeken alapuló forrásinformációk részletes elemzésére használható.

A **Könyvelés forrás intéző lapja** a forrásadatokat jeleníti meg. Különálló eszközként vagy a főkönyvi könyvelési tételeken túli részletek elemzésére használható. A lap használatával például a legrészletesebb forrásadatokat lehet kapni a számlaegyenleg egyenlege vagy egy bizonylattranzakció esetében. Ezután az **Exportálás AZ MS Excel**  Microsoft Excel  programba funkció használatával tovább szeletelheti és kockába adhatja az adatokat (például kimutatásban vagy kimutatásos jelentésben).

A **Könyvelés forrás intéző** lapja mindig ugyanazt a főkönyvi számlánkénti teljes összeget mutatja, mint a főkönyv (például főkönyvi számláknál). Mint a próbaegyenleg, a szegmenseket külön oszlopokban is meg lehet jelenni. Csak válassza ki a megfelelő pénzügyi dimenzió készletet. 

Paraméterek segítségével meghatározhatja za elemzési időszakot. Ez a funkció hasonlít a próbaegyenleg funkcióhoz is.

A forrásdokumentum-keretrendszert használja minden dokumentum esetén a **Könyvelés forrás intézője** lap további információkat is megjeleníti a könyvelési felosztások, illetve szükség esetén a projektkönyvelési felosztások alapján. Ezek közé tartozik **a pénzügyi összeg típusa**, **a Projekt**, **a Tevékenység**, **a Kategória** és a **Sor tulajdonság értéke** . Következzék pár példa az elvégezhető elemzésekre:

- A beszerzési rendelés és szállítói számla közötti különbségek, mert minden eltérést egy pénzösszeg típus jelez, például költségeltérés
- Számlázható és a nem számlázható órák és kiadások projekt, üzleti egység és a fő számla

A forrásdokumentum-hivatkozási **azonosítók koncepcióját használja forrásdokumentumok esetén a Könyvelési forrás intéző** lapja még több részletet is megjeleníti, **például** a Vevő, **a** Szállító, **a** Dolgozó,a Termék,a **·** **Mennyiség**, **az Egység** **szövege és a Leírás** értékét. Következzék pár példa az elvégezhető elemzésekre:

- A szállodai költségek üzleti egységre bontva és a szálloda márka a pénzügyi időszakra, költségjelentések alapján
- Engedmény szállítókra, termékre, részletre bontva

Ezeken a dokumentumokon a **tényleges forrásdokumentumot a Könyvelési forrás intéző lapról is meg lehet** jelenni.

> [!NOTE]
> A 10.0.31-es verziónak megfelelő új Könyvelési forrás intéző **speciális szűrési funkciója elérhető a** Funkciókezelésben. Ez a funkció lecseréli **a Frissítés** gombot, hogy hatékonyabb, speciális lekérdezési lehetőségeket biztosítson, amelyek hasonlítanak a **Bizonylattranzakciók lapon elérhetőhez** . A speciális szűrő segítségével a **bizonylattranzakciók lekérdezési lapján hasonló mezőkre szűrheti a mezőket, például a főkönyvi számlát,**  **·** **az üzleti egységet,** **a** költségközpontot és a részleget. **·** 

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
