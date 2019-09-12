---
title: Szolgáltatási szint és leírás
description: Ez a témakör az Eszközkezelés modul szolgáltatási szintjeit és azok leírását ismerteti.
author: josaw1
manager: AnnBe
ms.date: 08/13/2019
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
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 5e645c25208f55b1032bc7f7c181c72db7a2f265
ms.sourcegitcommit: 802dbf0a744d70f9e546632d419415b0993331ab
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/13/2019
ms.locfileid: "1874647"
---
# <a name="service-level-and-description"></a>Szolgáltatási szint és leírás

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

Munkarendelések létrehozásakor megadhatja, hogy az adott munkarendelés milyen szolgáltatási szinteket és leírást tartalmazzon. Munkarendelési szolgáltatási szintet a **Munkarendelési szolgáltatási szintek** lapon és a **Munkarendelési szolgáltatási leírás** lapon hozhat létre.

## <a name="create-a-service-level"></a>Szolgáltatási szint létrehozása

1. Válassza ki az **Eszközkezelés** \> **Beállítás** \> **Munkarendelések** \> **Szolgáltatási szint** elemet.
2. Válassza az **Új** lehetőséget.
3. A **Szolgáltatási szint** mezőben adja meg a szolgáltatási szintet (például egy számot).
4. A **Név** mezőben adjon meg egy nevet.

    A **Munkarendelések** gyorslapon meghatározhatja a várt kezdő és befejező dátumokat és időpontokat. A gyorslap mezői határozzák meg azt az időszakot, amikor a munkarendeléseket el kell indítani és be kell fejezni. Ezek a saját kezűleg létrehozott munkarendelések, valamint a karbantartási kérések alapján létrehozott munkarendelések esetében használhatók. 

5. A **Kezdő nap** mezőben adja meg azt az időszakot (napok számát), ameddig a munkarendelésnek meg kell kezdődnie. A napok számát a munkarendelés létrehozásától kezdődően számolja ki a rendszer. Ha például a munkarendelést a létrehozáskor kell elindítani, adja meg a **0**értéket. Ha a munkarendelést a létrehozása után egy héten belül el kell indítani, akkor a **7-et** írja be.
6. Ha a munkarendelés kezdő időpontját is meg szeretné adni a kezdő dátumon kívül, állítsa a **Kezdő dátum beállítása** lehetőséget **Igen** értékre. Ezután írja be a kezdő időpontot a **Kezdő időpont** mezőbe. Ha a beállítást **Nem**értékre állítja, akkor a program az aktuális időpontot használja.
7. A **Záró nap** mezőben adja meg azt az időszakot (napok számát), ameddig a munkarendelésnek be kell fejeződnie. A napok számát a munkarendelés kezdő dátumától kezdődően számolja ki a rendszer. Ha például a munkarendelésnek a kezdő dátumtól számítva egy héten belül be kell fejeződnie, akkor a **7-et** írja be.
8. Ha a munkarendelés záró időpontját is meg szeretné adni a záró dátumon kívül, állítsa a **Záró dátum beállítása** lehetőséget **Igen** értékre. Ezután írja be a záró időpontot a **Záró időpont** mezőbe. Ha a beállítást **Nem**értékre állítja, akkor a program az aktuális időpontot használja.
9. Válassza a **Mentés** lehetőséget.

![1. ábra](media/19-setup-for-work-orders.png)

## <a name="create-a-description"></a>Leírás létrehozása

1. Válassza ki az **Eszközkezelés** \> **Beállítás** \> **Munkarendelések** \> **Leírások** elemet.
2. Válassza az **Új** lehetőséget.
3. Adjon meg egy leírást a **Leírás** mezőben.
4. Válassza a **Mentés** lehetőséget.
