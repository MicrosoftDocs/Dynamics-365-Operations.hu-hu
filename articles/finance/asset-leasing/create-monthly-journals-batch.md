---
title: Havi naplóbejegyzések létrehozása kötegben
description: Ez a témakör bemutatja, hogyan hozhat létre naplóbejegyzéseket egy kötegben a havi lízingköltségek rögzítésekor a hatékonyság növelése érdekében.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: Dialog
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: ca84e56569ea5ddbb4d5335d0944a6bd8a50a1b1
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/13/2021
ms.locfileid: "5881204"
---
# <a name="create-monthly-journal-entries-in-a-batch"></a>Havi naplóbejegyzések létrehozása kötegben

[!include [banner](../includes/banner.md)]

Ez a témakör bemutatja, hogyan hozhat létre naplóbejegyzéseket egy kötegben a havi lízingköltségek rögzítésekor a hatékonyság növelése érdekében. A kötegelt feldolgozás segítségével több ütemezésből hozhat létre naplóbejegyzéseket. Ezek a naplóbejegyzések magukban foglalhatják a lízingkifizetéseket, a kötelezettségamortizációt, a használatijog-eszköz (ROU) amortizációját és a végrehajtási költségköltségeket. Kötegelt feldolgozással egyszerre több lízing kezdeti megjelenítését is elvégezheti, vagy egyszerre több lízinghez is létrehozhat átmeneti korrekciókat.

Kötegelt feldolgozás beállításához, illetve több lízing kifizetési számláinak, értékcsökkenésének vagy kamatának feldolgozásához nyissa meg az **Eszközlízing \> Időszakos \> Kötegnapló létrehozása** című szakaszt. A megjelenő párbeszédpanelen kiválaszthatja azt az ütemezést, amelyből a naplóbejegyzéseket létre kell hozni. Azt is megadhatja, hogy a kötegelt folyamatot meghatározott entitásokhoz, lízingcsoportokhoz vagy lízingkönyvekhez kell-e futtatni.

> [!NOTE]
> A későbbi tranzakciók, például a kötelezettségek amortizációs ütemezései, a kifizetések, az értékcsökkenés és a kiadások csak a megfelelő lízingek kezdeti megjelenítésének feladása után kerülnek feladásra.
>
> A naplóbejegyzések létrejönnek, de nem kerülnek feladásra, amíg ki nem választja a **Futtatás** parancsot.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
