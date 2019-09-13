---
title: Munkarendelések létrehozása
description: Ez a cikk azt mutatja be, hogyan lehet munkarendeléseket létrehozni az Eszközkezelés modulban.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-15
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: b23ed3251b2f6cf4f34b423ce2f85301d6ab31a1
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875688"
---
# <a name="creating-work-orders"></a>Munkarendelések létrehozása


[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


A megelőző karbantartási feladatok ütemezése után a következő lépés a feladatok munkarendeléseinek létrehozása. Ezt a karbantartási ütemezés képernyőn kell elvégezni: A karbantartási ütemezésben szereplő ütemezett feladatok különböző hivatkozási típusokkal rendelkezhetnek:

| Hivatkozás típusa | Leírás                    |
|-----------------------|------------------------------------------------------------------------------------------------------------|
| Karbantartási tervek     | Megelőző karbantartási feladatok az „idő” vagy a „számláló” típusú karbantartási konstrukciók alapján.                       |
| Karbantartási körök    | Olyan megelőző karbantartási feladatok, amelyek számos, hasonló típusú karbantartást igénylő eszközt tartalmaznak.           |
| Karbantartási kérés   | Egy eszköz karbantartására vagy javítására irányuló, manuálisan létrehozott kérelem, amely átalakítható munkarendelésbe. |


1. Kattintson az **Eszközkezelés** > **Közös** > **Összes karbantartási ütemezés** vagy **Nyitott karbantartási ütemezési sorok** vagy **Nyitott karbantartási ütemezési csoportok** elemre.

2. Válassza ki azt azokat az ütemezett karbantartási munkákat, amelyhez munkarendelést szeretne létrehozni, majd kattintson a **Munkarendelés** elemre. A kiválasztott sorokhoz tartozó összes előrejelzési órák száma a **Karbantartási előrejelzési órák** mezőben látható.

3. A **Paraméterek** szakaszban válassza ki, hogy hány munkarendelést kell létrehozni. Karbantartási ütemezés soronként létrehozhat egy munkarendelést, illetve számos munkarendelést az **Egy munkarendelés per** alapján.

4. Válassza ki azt a **Munkarendelés-típust**, amelyet a létrehozott összes munkarendelésnél használni fog.

5. Kattintson az **OK** gombra. Egy vagy több munkarendelést hoz létre a program.

![1. ábra](media/18-preventive-maintenance.png)

