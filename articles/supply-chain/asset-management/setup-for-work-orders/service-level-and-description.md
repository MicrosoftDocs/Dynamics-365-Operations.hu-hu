---
title: Szolgáltatási szint és leírás
description: Ez a témakör az Eszközkezelés modul szolgáltatási szintjeit és azok leírását ismerteti.
author: johanhoffmann
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetObjectServiceLevel, EntAssetWorkOrderStandardDescription, EntAssetWorkOrderServiceLevel, EntAssetServiceLevelLookup
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: bb342e700c9390e1eb9f2a9e9d67b874b3e19b8e
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5808256"
---
# <a name="service-level-and-description"></a>Szolgáltatási szint és leírás

[!include [banner](../../includes/banner.md)]

 

Munkarendelések létrehozásakor megadhatja, hogy az adott munkarendelés milyen szolgáltatási szinteket és leírást tartalmazzon. Munkarendelési szolgáltatási szintet a **Munkarendelési szolgáltatási szintek** lapon és a **Munkarendelési szolgáltatási leírás** lapon hozhat létre.

## <a name="create-a-service-level"></a>Szolgáltatási szint létrehozása

1. Válassza ki az **Eszközkezelés** \> **Beállítás** \> **Munkarendelések** \> **Szolgáltatási szint** elemet.
2. Válassza az **Új** lehetőséget.
3. A **Szolgáltatási szint** mezőben adja meg a szolgáltatási szintet (például egy számot).
4. A **Név** mezőben adjon meg egy nevet.

    A **Munkarendelések** gyorslapon meghatározhatja a várt kezdő és befejező dátumokat és időpontokat. A gyorslap mezői határozzák meg azt az időszakot, amikor a munkarendeléseket el kell indítani és be kell fejezni. Ezek a saját kezűleg létrehozott munkarendelések, valamint a karbantartási kérések alapján létrehozott munkarendelések esetében használhatók. 

5. A **Kezdő nap** mezőben adja meg azt az időszakot (napok számát), ameddig a munkarendelésnek meg kell kezdődnie. A napok számát a munkarendelés létrehozásától kezdődően számolja ki a rendszer. Ha például a munkarendelést a létrehozáskor kell elindítani, adja meg a **0** értéket. Ha a munkarendelést a létrehozása után egy héten belül el kell indítani, akkor a **7-et** írja be.
6. Ha a munkarendelés kezdő időpontját is meg szeretné adni a kezdő dátumon kívül, állítsa a **Kezdő dátum beállítása** lehetőséget **Igen** értékre. Ezután írja be a kezdő időpontot a **Kezdő időpont** mezőbe. Ha a beállítást **Nem** értékre állítja, akkor a program az aktuális időpontot használja.
7. A **Záró nap** mezőben adja meg azt az időszakot (napok számát), ameddig a munkarendelésnek be kell fejeződnie. A napok számát a munkarendelés kezdő dátumától kezdődően számolja ki a rendszer. Ha például a munkarendelésnek a kezdő dátumtól számítva egy héten belül be kell fejeződnie, akkor a **7-et** írja be.
8. Ha a munkarendelés záró időpontját is meg szeretné adni a záró dátumon kívül, állítsa a **Záró dátum beállítása** lehetőséget **Igen** értékre. Ezután írja be a záró időpontot a **Záró időpont** mezőbe. Ha a beállítást **Nem** értékre állítja, akkor a program az aktuális időpontot használja.
9. Válassza a **Mentés** lehetőséget.

![Munkarendelések szolgáltatási szintje oldal](media/19-setup-for-work-orders.png)

## <a name="create-a-description"></a>Leírás létrehozása

1. Válassza ki az **Eszközkezelés** \> **Beállítás** \> **Munkarendelések** \> **Leírások** elemet.
2. Válassza az **Új** lehetőséget.
3. Adjon meg egy leírást a **Leírás** mezőben.
4. Válassza a **Mentés** lehetőséget.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]