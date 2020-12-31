---
title: A lízingkötelezettség rövid távú részének átsorolása
description: Ez a témakör bemutatja, hogyan hozhat létre havi naplóbejegyzést a lízingkötelezettség egy részének rövid távúként történő átsorolásához.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 46bcd396c93bc1d2944241165d438f8ccc013e20
ms.sourcegitcommit: aeee39c01d3f93a6dfcf2013965fa975a740596a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/28/2020
ms.locfileid: "4444171"
---
# <a name="reclassify-the-short-term-portion-of-lease-liability"></a>A lízingkötelezettség rövid távú részének átsorolása

[!include [banner](../includes/banner.md)]

Ez a témakör bemutatja, hogyan hozhat létre havi naplóbejegyzést a lízingkötelezettség egy részének rövid távúként történő átsorolásához. Ha a kötegfolyamatban kiválasztott ütemezés **Rövidtávú lízingkötelezettség átsorolásakor** egy naplóbejegyzés jön létre. Ez a bejegyzés a lízingkötelezettség aktuális részének feladására szolgál a hónap utolsó napján. Ezzel egy időben a következő hónap első napjától a függvény a következő hónap első napjától adja fel a sztornírozott bejegyzést.

A lízingkötelezettség rövid távú része a kötelezettség amortizációs ütemezésében jelenik meg. A naplóbejegyzés feladásakor elérhetővé válik a **Létrehozott kötelezettség-átsorolási napló** oszlopa, és a naplóazonosító is ki lesz töltve az ütemezésben.

A rövid távú kötelezettség újraosztályzási naplóbejegyzés létrehozásához és feladásához kövesse az alábbi lépéseket.

1. Nyissa meg az **Eszközlízing \> Időszakos \> Kötegelt napló létrehozása** lehetőséget.
2. Válassza ki a **Kötegelt napló létrehozása** párbeszédpanel **Ütemezés kiválasztása** mezőjében a **Rövid távú lízingkötelezettség újraosztályozása** lehetőséget.
3. Válassza ki a **Lízingcsoport** mezőben a lízingcsoportot. Másik lehetőségként a **Könyv azonosítója** mezőben válassza ki a könyv azonosítóját.
4. Kapcsolja be a **Feladás** paramétert. Azt is megteheti, hogy ha a bejegyzést létre kell hozni, de nem szabad feladni, akkor kikapcsolva hagyja ezt a paramétert.
5. A feladás előtt kapcsolja be az **Előzetes verzió feladás előtt** paramétert, hogy a bejegyzést megtekinthesse feladás előtt.
6. Válassza ki az **OK** lehetőséget.
