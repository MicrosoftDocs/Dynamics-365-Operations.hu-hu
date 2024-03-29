---
title: Kis értékű tárgyi eszközök
description: Ez a cikk a kis költségű tárgyi eszközökről nyújt tájékoztatást Magyarország számára.
author: EvgenyPopovMBS
ms.date: 10/31/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetParameters
audience: Application User
ms.reviewer: kfend
ms.custom: 264684
ms.search.region: Hungary
ms.author: epopov
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: c15b92d5727f1605e9918a63bb3d04d421cfbbad
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8880628"
---
# <a name="low-cost-fixed-assets"></a>Kis értékű tárgyi eszközök

[!include [banner](../includes/banner.md)]

Ez a cikk a kis költségű tárgyi eszközökről nyújt tájékoztatást Magyarország számára.

A kis értékű tárgyi eszköz olyan eszköz, amelynek a beszerzési költsége nem halad meg egy előre meghatározott összeget. A magyar adójog meghatározza a kis értékű tárgyi eszközök összeghatárát (küszöbértékét). Ezek az eszközök teljes mértékben leírhatók a beszerzéssel egy időben.

## <a name="set-up-the-low-cost-asset-threshold"></a>A kis értékű tárgyi eszköz küszöbértékének beállítása

A kis értékű tárgyi eszköz küszöbértékének beállításához kattintson a **Tárgyi eszközök** &gt; **Beállítás** &gt; **Tárgyi eszközök paraméterei** elemre. Ezután a **Kis értékű tárgyi eszköz küszöbértéke** mezőjébe írja be a kis értékű tárgyi eszközök értékhatárát.

## <a name="set-up-books-for-low-cost-fixed-assets"></a>Könyvek beállítása a kis értékű tárgyi eszközökhöz

Amikor beszerzési tranzakciót hoz létre egy olyan eszközhöz, amely a kis értékű tárgyi eszközök könyvét használja, az értékcsökkenés automatikusan létrejön.

1.  Kattintson a **Tárgyi eszközök** &gt; **Beállítás** &gt; **Könyvek** elemre.
2.  Válassza ki a kis értékű tárgyi eszközökhöz használandó könyvet, majd jelölje be a **Kis értékű tárgyi eszköz** jelölőnégyzetet.

**Megjegyzés:** a kis értékű értékcsökkenéshez csak a „Kézi” vagy „Lineáris - élettartam” értékcsökkenési profilokat/globális módszereket használó értékmodellek, illetve a Magyarország-specifikus „Lineáris (Hu)” módszer áll rendelkezésre.

## <a name="generate-acquisition-and-depreciation-transactions-for-low-cost-fixed-assets"></a>Beszerzési és értékcsökkenési tranzakciók létrehozása kis értékű tárgyi eszközökhöz

Eszköz megszerzésekor egy beszerzési tranzakciót hoz létre a beszerzést megelőző tranzakcióból. Amikor feladja a kis értékű tárgyi eszköz beszerzési tranzakcióját, az értékcsökkenési tranzakció automatikusan létrejön.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]