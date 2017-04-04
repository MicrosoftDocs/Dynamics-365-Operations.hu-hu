---
title: "Kisértékű tárgyi eszközök"
description: "Ez a témakör a kisértékű tárgyi eszközök Magyarországra vonatkozó információt."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 264684
ms.assetid: 8452cf9f-13fa-4ea0-a4e2-c35335c863b8
ms.search.region: Hungary
ms.author: epopov
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 6bb98cc72c2ec0c1551412dd39d5bea3ce10e2cd
ms.openlocfilehash: dd27276533276181ea9a7cb4244ec3b401882370
ms.lasthandoff: 03/31/2017


---

# <a name="low-cost-fixed-assets"></a>Kisértékű tárgyi eszközök

Ez a témakör a kisértékű tárgyi eszközök Magyarországra vonatkozó információt.

A kisértékű tárgyi eszköz egy eszköz, amelynek beszerzési költsége nem haladja meg egy előre meghatározott összeget. Magyar adójog határozza meg a korlátot (küszöbérték) alacsony költségű eszközök. Ezek az eszközök teljes mértékben leírható beszerzett egy időben.

## <a name="set-up-parameters-for-lowcost-fixed-assets"></a>Tárgyi eszközök lowcost paramétereinek beállítása
### <a name="set-up-the-low-cost-asset-threshold"></a>Állítsa be a kisértékű tárgyi eszköz küszöbértéke

Kisértékű eszközök a korlát beállításához kattintson a **tárgyi eszközök**&gt;**a telepítő**&gt;**tárgyi eszközök paraméterei**. Majd, a **kisértékű tárgyi eszköz küszöbértékét** mezőjébe írja be az értékhatár kisértékű eszközök.

### <a name="set-up-books"></a>Könyvek beállítása

Egy alacsony költségű eszközök könyv használó eszközre beszerzési tranzakciót hoz létre, amikor az értékcsökkenés automatikusan létrejön.

1.  Kattintson a **tárgyi eszközök**&gt;**a telepítő**&gt;**könyvek**.
2.  Válassza ki a könyvet a kisértékű eszközök, és válassza ki a **kisértékű tárgyi eszköz** jelölőnégyzetet.

**Megjegyzés:** érték modellek által használt a "kézi" vagy "lineáris-élettartam" értékcsökkenési profilok globális módszerek, illetve a "Lineáris (Hu)" Magyarország-specifikus módszer, csak alacsony költségű értékcsökkenés rendelkezésre állnak.

### <a name="generate-acquisition-and-depreciation-transactions-for-low-cost-fixed-assets"></a>A kisértékű tárgyi eszközök beszerzési és értékcsökkenési tranzakciók létrehozása

Amikor egy eszköz, beszerzési tranzakciót hoz létre a beszerzés előtti tranzakcióból. A kisértékű tárgyi eszköz esetében a beszerzési tranzakció könyvelésekor automatikusan létrejön az értékcsökkenési tranzakció.


