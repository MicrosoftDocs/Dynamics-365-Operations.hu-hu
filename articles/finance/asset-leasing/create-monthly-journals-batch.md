---
title: Havi naplóbejegyzések létrehozása kötegben
description: Ez a cikk bemutatja, hogyan lehet naplóbejegyzéseket létrehozni egy kötegben a hatékonyság növelése érdekében a havi bérleti költségek rögzítésekor.
author: moaamer
ms.date: 08/10/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: Dialog
audience: Application User
ms.reviewer: kfend
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: fb5c65b0a2c982171fa0ae88141d92c2f1ead6ac
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8894993"
---
# <a name="create-monthly-journal-entries-in-a-batch"></a>Havi naplóbejegyzések létrehozása kötegben

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]


Ez a cikk bemutatja, hogyan lehet naplóbejegyzéseket létrehozni egy kötegben a hatékonyság növelése érdekében a havi bérleti költségek rögzítésekor. A kötegelt feldolgozás segítségével több ütemezésből hozhat létre naplóbejegyzéseket. Ezek a naplóbejegyzések magukban foglalhatják a lízingkifizetéseket, a kötelezettségamortizációt, a használatijog-eszköz (ROU) amortizációját és a végrehajtási költségköltségeket. Kötegelt feldolgozással egyszerre több lízing kezdeti megjelenítését is elvégezheti, vagy egyszerre több lízinghez is létrehozhat átmeneti korrekciókat.

Kötegelt feldolgozás beállításához, illetve több lízing kifizetési számláinak, értékcsökkenésének vagy kamatának feldolgozásához nyissa meg az **Eszközlízing \> Időszakos \> Kötegnapló létrehozása** című szakaszt. A megjelenő párbeszédpanelen kiválaszthatja azt az ütemezést, amelyből a naplóbejegyzéseket létre kell hozni. Azt is megadhatja, hogy a kötegelt folyamatot meghatározott entitásokhoz, lízingcsoportokhoz vagy lízingkönyvekhez kell-e futtatni.

> [!NOTE]
> A későbbi tranzakciók, például a kötelezettségek amortizációs ütemezései, a kifizetések, az értékcsökkenés és a kiadások csak a megfelelő lízingek kezdeti megjelenítésének feladása után kerülnek feladásra.
>
> A naplóbejegyzések létrejönnek, de nem kerülnek feladásra, amíg ki nem választja a **Futtatás** parancsot.

Ha a kezdeti megjelenítési naplót a lízing kezdőnapjától eltérő időpontban kívánja könyvelni, válassza a **Kezdeti megjelenítés könyvelési dátumának hozzárendelése** lehetőséget. Megjelenik egy **Dátum** mező, amelyben megadhatja a helyes könyvelési dátumot.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
