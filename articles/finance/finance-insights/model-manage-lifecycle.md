---
title: Modellkezelés életciklusa (előzetes verzió)
description: Ez a témakör leírja, hogyan lehet karbantartani a szervezet gépi tanulási modelljeit a generált előrejelzések optimalizálása érdekében.
author: ShivamPandey-msft
ms.date: 07/16/2021
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
ms.openlocfilehash: c84f0a6079d7e599ed1f3e44c26c625e548c06d5a91447c46fc722ce6a6cf414
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6741560"
---
# <a name="model-management-lifecycle-preview"></a>Modellkezelés életciklusa (előzetes verzió)

[!include [banner](../includes/banner.md)]

Ez a témakör leírja, hogyan lehet karbantartani a szervezet gépi tanulási modelljeit a generált előrejelzések optimalizálása érdekében.

Javasoljuk, hogy az AI-modellt egy tesztkörnyezetben tanítsa fel, majd felügyelt megoldások segítségével telepítse éles környezetben. Ez a megközelítés segít gondoskodni arról, hogy a modell életciklusának kezeléséhez megfelelő vezérlők legyenek a helyükön.

Mivel az AI-modell a rendelkezésre álló számla- és vevőadatokon alapul, fontos, hogy a tesztkörnyezet rendelkezzen az éles rendszerek adataival. A modellek feltanítását a [Vevői fizetési előrejelzések használata](use-customer-payment-predictions.md) lépéseinek követésével kezdheti el. A modell újrabetanítása után az eredményeket [A kezdeti vevői fizetési előrejelzési modell kiértékelése](evaluate-payment-prediction.md) szakaszban leírtak szerint értékelheti. Használja [Az előrejelzési modell javítása](improve-model.md) információit az olyan funkció- és szűrőkombinációkkal való kísérletezéshez, amely segíthet a modell továbbfejlesztésében.

Ha meg van elégedve a képzés eredményeivel, kövesse az [AI-modell kiosztása](https://docs.microsoft.com/ai-builder/distribute-model) lépéseit a modell éles környezetre valóát állítása érdekében.
