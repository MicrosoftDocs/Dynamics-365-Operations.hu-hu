---
title: Számlastruktúra aktiválásának teljesítményfejlesztése
description: Ez a cikk bemutatja a számlastruktúra aktiválási folyamatának új teljesítményfejlesztőjavító funkcióját.
author: RyanCCarlson2
ms.date: 10/31/2022
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: rcarlson
ms.search.validFrom: 2022-10-08
ms.dyn365.ops.version: 10.0.31
ms.openlocfilehash: 42f8fcebba6465261489f74a9bb1dd46c2d5fa16
ms.sourcegitcommit: c6c2486be2359bd30106f7f52bda788239147d8c
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/22/2022
ms.locfileid: "9713999"
---
# <a name="account-structure-activation-performance-enhancement"></a>Számlastruktúra aktiválásának teljesítményfejlesztése

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

Ezzel a teljesítményfejlesztő funkcióval gyorsabban aktiválhatja a számlastruktúrát, ha egyszerre több tranzakciófrissítést futtat. Ezenkívül maga a struktúra is aktívként lesz megjelölve az ellenőrzés után, és a tranzakciófeldolgozás folytatódhat, miközben a meglévő, fel nem adott tranzakciókat frissítik az új struktúrára. Mivel a tranzakciók frissítései egy kis időbe telhetnek, nyomon követheti az aktiválás állapotát, ha kiválasztja a **Számlastruktúrák** oldalon lévő rács felett található **Aktiválási állapot megtekintése** lehetőséget. Az aktiválás állapotát úgy is megtekintheti, ha kiválasztja az Akció panelen lévő **Megtekintés** elemet, majd kiválasztja az **Aktiválás állapota** lehetőséget a legördülő menüből.

[![Számlastruktúrák oldala.](./media/AccountStructure1.png)](./media/AccountStructure1.png)

Miután kiválasztotta az **Aktiválási állapot megtekintése** lehetőséget, megjelenik egy párbeszédpanel, amely az aktiválási folyamat részeként futó egyes feladatokat mutatja. Minden feladatnál megtekinteni az állapotot, illetve a feladat befejezése után a befejezés dátumát és időpontját.

[![Számlastruktúra aktiválási idősora.](./media/AccountStructureTimeline.png)](./media/AccountStructureTimeline.png)

## <a name="account-structure-activation-tips"></a>Számlastruktúra-aktiválási tippek

A számlastruktúra aktiválására szolgáló párbeszédpanel, amely akkor jelenik meg, amikor kiválasztja az **Aktiválás** elemet a piszkozat számlastruktúránál, amely rendelkezik egy **Még fel nem adott tranzakciók frissítése** lap résszel. Ez a szakasz rendelkezik egy **Kényszerített frissítés** lehetőséggel. Ezzel a beállítással az összes fel nem adott tranzakciót az aktuális struktúrára frissítheti. Ezt a lehetőséget azonban csak hiba esetén, vagy akkor használhatja, ha a Microsoft ügyfélszolgálata arra felkéri.

Íme néhány olyan tényező, amely befolyásolhatja az aktiválási folyamat teljesítményét:

- Nagy számú fel nem adott naplórekord
- Nagy számú nyílt forráskódú dokumentum-rekord, például szabadszöveges számlák, szállítói számlák és kapcsolódó dokumentumok, amelyek a forrásdokumentum keretrendszerét használják, és nyitott könyvelési felosztással rendelkeznek
- Az adatok mennyisége a TaxUncommitted lehetőségben
- A nyílt költségvetési adatok összege
- Naplóadatok importálása az aktiválási feladatok futtatása közben

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
