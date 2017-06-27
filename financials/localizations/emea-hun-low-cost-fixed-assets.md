---
title: "Kis értékű tárgyi eszközök"
description: "Ez a témakör a Magyarországon használt kis értékű tárgyi eszközökhöz tartalmaz információt."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations, Core
ms.custom: 264684
ms.search.region: Hungary
ms.author: epopov
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: d55bf512edd56f47f2419fc2dd3c2050a342e8a1
ms.contentlocale: hu-hu
ms.lasthandoff: 05/25/2017


---

# <a name="low-cost-fixed-assets"></a>Kis értékű tárgyi eszközök

[!include[banner](../includes/banner.md)]


Ez a témakör a Magyarországon használt kis értékű tárgyi eszközökhöz tartalmaz információt.

A kis értékű tárgyi eszköz olyan eszköz, amelynek a beszerzési költsége nem halad meg egy előre meghatározott összeget. A magyar adójog meghatározza a kis értékű tárgyi eszközök összeghatárát (küszöbértékét). Ezek az eszközök teljes mértékben leírhatók a beszerzéssel egy időben.

## <a name="set-up-parameters-for-lowcost-fixed-assets"></a>Paraméterek beállítása a kis érétkű tárgyi eszközökhöz
### <a name="set-up-the-low-cost-asset-threshold"></a>A kis értékű tárgyi eszköz küszöbértékének beállítása

A kis értékű tárgyi eszköz küszöbértékének beállításához kattintson a **Tárgyi eszközök** &gt; **Beállítás** &gt; **Tárgyi eszközök paraméterei** elemre. Ezután a **Kis értékű tárgyi eszköz küszöbértéke** mezőjébe írja be a kis értékű tárgyi eszközök értékhatárát.

### <a name="set-up-books"></a>Könyvek beállítása

Amikor beszerzési tranzakciót hoz létre egy olyan eszközhöz, amely a kis értékű tárgyi eszközök könyvét használja, az értékcsökkenés automatikusan létrejön.

1.  Kattintson a **Tárgyi eszközök** &gt; **Beállítás** &gt; **Könyvek** elemre.
2.  Válassza ki a kis értékű tárgyi eszközökhöz használandó könyvet, majd jelölje be a **Kis értékű tárgyi eszköz** jelölőnégyzetet.

**Megjegyzés:** a kis értékű értékcsökkenéshez csak a „Kézi” vagy „Lineáris - élettartam” értékcsökkenési profilokat/globális módszereket használó értékmodellek, illetve a Magyarország-specifikus „Lineáris (Hu)” módszer áll rendelkezésre.

### <a name="generate-acquisition-and-depreciation-transactions-for-low-cost-fixed-assets"></a>Beszerzési és értékcsökkenési tranzakciók létrehozása kis értékű tárgyi eszközökhöz

Eszköz megszerzésekor egy beszerzési tranzakciót hoz létre a beszerzést megelőző tranzakcióból. Amikor feladja a kis értékű tárgyi eszköz beszerzési tranzakcióját, az értékcsökkenési tranzakció automatikusan létrejön.




