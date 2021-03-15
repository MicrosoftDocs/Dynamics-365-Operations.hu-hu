---
title: Köteg és azonosítótábla megerősítése
description: Ez a témakör a kötegalkalmazás és az azonosítótábla-megerősítés mobileszközről való beállítását és alkalmazását mutatja be.
author: Mirzaab
manager: tfehr
ms.date: 11/11/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFAutoConfirm
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 97790b91d4de536b89b580c26ef1e37145f7d7c6
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4977438"
---
# <a name="batch-and-license-plate-confirmation"></a>Köteg és azonosítótábla megerősítése

[!include [banner](../includes/banner.md)]

A kötegelés megerősítésével meggyőződhet arról, hogy a helyes tételt tárolta ki a mobileszközről. A csak a fenti tételek kitárolásánál, amennyiben a fentiek kötegelése azt jelzi, hogy a köteg tartománya magasabb, mint a hely a keresési hierarchiában, így ellenőriznie kell, hogy a kitárolt köteg egyezik a munkasoron lévő köteggel.

Az azonosítótábla megerősítésével meggyőződhet arról, hogy a helyes azonosítótáblát tárolta ki a mobileszközről. Amikor egy betervezett helyről tárol ki munkát, ellenőriznie kell, hogy a kitárolni kívánt azonosítótábla egyezik-e a munkához kapcsolódó azonosítótáblával. Ha a munka azonosítótábla leolvasásával kezdődik, akkor ezt a megerősítő lépést átugorja a rendszer.

## <a name="where-it-applies"></a>Alkalmazási kör

A visszaigazolás az alábbi esetekben alkalmazandó:

- A kötegelés megerősítése a fenti cikkek munkáinak kezdeti kitárolására vonatkozik.
- Az azonosítótábla megerősítése az előkészítési helyeknél lévő kitárolásokra érvényes.

> [!IMPORTANT]
> A feltöltés nem támogatott az azonosítótábla megerősítéséhez. A feltöltési munka végrehajtásakor nem jön létre azonosítótábla-megerősítési lépés.

## <a name="set-up-batch-and-license-plate-confirmation"></a>Köteg és azonosítótábla beállításának megerősítése

Ez a témakör a kötegalkalmazás és az azonosítótábla-megerősítés mobileszközről való beállítását és alkalmazását mutatja be.

1. Lépjen be a munka-visszaigazolás beállításához a mobileszköz menüelemeitől.  
1. Válassza ki, hogy kötegelést vagy azonosítótábla-megerősítést szeretne végezni. Mindkét lehetőség rendelkezésre áll azoknál a munkatípus-kitárolásoknál, amelyeknél nincs engedélyezve az automatikus visszaigazolás.  


[!INCLUDE[footer-include](../../includes/footer-banner.md)]