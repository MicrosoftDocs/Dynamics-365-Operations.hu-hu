---
title: Sortétel munkafolyamatok konfigurálása
description: Ez a témakör bemutatja a sortétel-munkafolyamat-elem beállításának menetét.
author: ChrisGarty
manager: AnnBe
ms.date: 11/03/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 195833
ms.assetid: 3237347e-71d5-4569-bc9a-0d0fc9410b78
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 46de2bc3683ed907f1879afc13c60adce261d402
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/09/2021
ms.locfileid: "5567015"
---
# <a name="configure-line-item-workflows"></a>Sortétel munkafolyamatok konfigurálása

[!include [banner](../includes/banner.md)]

Ez a témakör bemutatja a sortétel-munkafolyamat-elem beállításának menetét.

A sortétel munkafolyamatának a munkafolyamat-szerkesztőben történő beállításához kattintson a jobb gombbal az elemre, és kattintson **Tulajdonságok** lap megnyitásához a **Tulajdonságok** lehetőségre. Ezután a következő eljárások segítségével beállíthatja a sortétel munkafolyamat-elem különféle tulajdonságait.

## <a name="name-the-line-item-workflow-element"></a>A sortétel-munkafolyamat-elem elnevezése

A következő lépések segítségével elnevezheti a sortétel munkafolyamat-elemet.

1. A bal oldali panelen kattintson az **Alapbeállítások** gombra.
2. A **Név** mezőbe írja be a sortétel munkafolyamat-elem egyedi nevét.

## <a name="specify-whether-the-same-workflow-is-used-to-process-all-line-items"></a>Adja meg, hogy ugyanazon munkafolyamat segítségével dolgozza-e fel az összes sortételt

A következőképpen határozhatja meg, hogy ugyanazon munkafolyamat segítségével akarja-e feldolgozni a dokumentum összes sortételét.

1. A bal oldali panelen kattintson az **Alapbeállítások** gombra.
2. Ha ugyanazon munkafolyamattal akarja feldolgozni a dokumentum összes sortételét, kattintson az **Egyetlen munkafolyamat indítása az összes sortételhez** lehetőségre. Ezután válassza ki a sortételek feldolgozásához használni kívánt munkafolyamatot.
3. Ha egy bizonyos feltételkészletnek megfelelő sortételeket egy bizonyos munkafolyamattal akarja feldolgozni, kattintson a **Külön munkafolyamat indítása minden egyes sortételhez** lehetőségre. Ezután hajtsa végre a következő lépéseket a feltételkészlet meghatározásához:

    1. Kattintson a **Hozzáadás** gombra.
    2. Válassza ki a táblán levő feltételt.
    3. A **Feltétel neve** lapon írja be a meghatározni kívánt feltételkészlet nevét.
    4. Kattintson a **Feltétel hozzáadása** lehetőségre a feltétel beírásához.
    5. Adja meg a további szükséges feltételeket.
    6. Ha ellenőrizni szeretné a megadott feltételkészlet beállításának helyességét, kattintson a **Teszt** lehetőségre. A **Munkafolyamati feltétel tesztelése** lapon, a **Feltétel érvényesítése** területen válasszon ki egy rekordot, majd kattintson a **Teszt** lehetőségre. A rendszer értékeli a bejegyzést, annak érdekében, hogy meghatározza, hogy a meghatározott feltételeknek megfeleljen-e. Kattintson az **OK** vagy a **Mégse** lehetőségre a **Tulajdonságok** lapra történő visszalépéshez.

    A **Munkafolyamat** lapon válassza ki azon sortételek feldolgozásához használni kívánt munkafolyamatot, amelyek megfelelnek a meghatározott feltételkészletnek.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]