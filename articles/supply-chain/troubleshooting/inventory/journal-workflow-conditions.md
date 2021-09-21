---
title: A készletnapló munkafolyamat-feltételei naplószinten érvényesek, nem sorszinten.
description: A készletnapló munkafolyamat-feltételei csak a napló szintjén érvényesek, a sor szintjén nem.
author: sherry-zheng
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 46bdde7f09c639fbefd46162431762b056d521ae
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476551"
---
# <a name="inventory-journal-workflow-conditions-apply-at-the-journal-level-not-line-level"></a>A készletnapló munkafolyamat-feltételei naplószinten érvényesek, nem sorszinten.

## <a name="symptoms"></a>Tünetek

Ezt a problémát például akkor tapasztalhatja, ha a költség összegére egy készletnapló-munkafolyamati feltételt próbál beállítani. Úgy állítsa be a feltételt, hogy az 1. lépés csak akkor fusson, ha a költség összege kisebb, mint 100. Ezután úgy állítson be egy másik feltételt, hogy az 2. lépés csak akkor fusson, ha a költség összege több, mint 100 vagy azzal egyenlő. Ezután a munkafolyamat futtatásakor a munkafolyamat előzményei csak egy sort mutatnak, és az első feltétel kiértékelése mindig *igaz*, függetlenül az elküldött értéktől.

## <a name="workaround"></a>Megkerülő megoldás

A jelenlegi verzióban a készlet munkafolyamat-feltételei csak a napló szintjén érvényesek, a sor szintjén nem. Ez szándékosan van. Azt ajánljuk, hogy csak naplószintű attribútumokkal állítsa be a feltételi kritériumokat.
