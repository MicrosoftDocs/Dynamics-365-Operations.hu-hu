---
title: Az előrejelzési modell javítása (előzetes verzió)
description: Ez a témakör az előrejelzési modellek teljesítményének javítására használható funkciókat ismerteti.
author: ShivamPandey-msft
ms.date: 06/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-05-28
ms.dyn365.ops.version: AX 10.0.8
ms.openlocfilehash: 184a1cb5d3851e26b41340b711c51ef38e06eb53
ms.sourcegitcommit: ebcd9019cbb88a7f2afd9e701812e222566fd43d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/04/2021
ms.locfileid: "6186642"
---
# <a name="improve-the-prediction-model-preview"></a>Az előrejelzési modell javítása (előzetes verzió)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Ez a témakör az előrejelzési modellek teljesítményének javítására használható funkciókat ismerteti. A modell javítását a Microsoft Dynamics 365 Finance **Vevői fizetési előrejelzések** munkaterületen kezdi el. A fejlesztési lépéseket ezután az AI Builder fejezi be.

## <a name="select-historical-outcomes"></a>Előzményalapú eredmény kiválasztása

Először a számlák három lehetséges kimenetele közül válasszon ki egyet vagy többet: **Időben**, **Későn** és a **Nagyon későn**. Mindhárom eredményt ki kell választani. Ha törli az eredmények bármelyikének kiválasztását, a számlák ki lesznek szűrve a betanítási folyamatból, és az előrejelzés pontossága csökken.

[![Eredmények megerősítése](./media/confirm-3-outcomes.png)](./media/confirm-3-outcomes.png)

Ha a szervezet csak két eredményt igényel, módosítsa a **Későn** és a **Nagyon későn** küszöbértékeket 0 (nulla) napra. Így hatékonyan összecsukhatja az előrejelzést az **Időben** vagy a **Későn** bináris állapotában.

## <a name="select-fields"></a>Mezők kijelölése

Amikor a modellbe felvenni kívánt mezőket választja, vegye figyelembe, hogy a lista tartalmazza a Microsoft Dataverse-tábla összes elérhető mezőjét, amely az Azure Data Lake-ben lévő adatokhoz van rendelve. A mezők némelyikét **Nem** szabad kijelölni. A ki nem jelölendő mezők a következő három kategória egyikébe tartoznak:

- A mező kitöltése szükséges a Dataverse-táblához, de nincsenek háttéradatok a Data Lake-ben.
- A mező egy azonosító, ezért nincs értelme a gépi tanulási funkciónak.
- A mező olyan információkat mutat, amelyek nem érhetők el az előrejelzés során.

A következő szakaszok a számla és a vevőentitások számára rendelkezésre álló mezőket mutatják be, és felsorolják azokat a mezőket, amelyeket **nem** szabad betanításra kiválasztani. Az egyes mezőkhöz megadott kategória az előző listában szereplő kategóriákra vonatkozik.
 
### <a name="invoice-dataverse-table"></a>Dataverse-számlatábla

A következő ábra a számlatáblához rendelkezésre álló mezőket mutatja be.

[![A számlatábla elérhető mezői](./media/available-fields.png)](./media/available-fields.png)

A következő mezőket nem szabad kiválasztani betanításhoz:

- **Számlafiók** (2. kategória)
- **Le van zárva** (3. kategória) – Ez a mező a betanítási (lezárt) és előrejelzési (le nem lezárt) számlák szűrésére szolgál.
- **Név** (1. kategória)
- **Erőforrásazonosító** (2. kategória)
- **Erőforrásrekord** (2. kategória)
- **Forrástábla** (2. kategória)

### <a name="customer-dataverse-table"></a>Dataverse vevői tábla

A következő ábra a vevőtáblához rendelkezésre álló mezőket mutatja be.

[![A vevőtábla elérhető mezői](./media/related-entities.png)](./media/related-entities.png)

A következő mezőt nem szabad kiválasztani betanításhoz:

- **Sor egyedi kulcsa** (2. kategória)

## <a name="filters"></a>Szűrők

A szűrők jelenleg nem támogatják az Ügyfél fizetési előrejelzési forgatókönyvet. Ezért válassza a **Lépés kihagyása** lehetőséget, majd menjen az összesítő lapra.

[![Fókuszmodell szűrőkkel](./media/focus-model-with-filters.png)](./media/focus-model-with-filters.png)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
