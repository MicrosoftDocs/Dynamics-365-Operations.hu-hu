---
title: "Sortétel munkafolyamatának beállítása"
description: "Ez a témakör bemutatja a sortétel-munkafolyamat-elem beállításának menetét."
author: sericks007
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 195833
ms.assetid: 3237347e-71d5-4569-bc9a-0d0fc9410b78
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28T00:00:00.000Z
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 2781a0344f1de5caf0031d7c3d5b88678be153a4
ms.contentlocale: hu-hu
ms.lasthandoff: 05/25/2017

---

# <a name="configure-a-line-item-workflow"></a>Sortétel munkafolyamatának beállítása

[!include[banner](../includes/banner.md)]


Ez a témakör bemutatja a sortétel-munkafolyamat-elem beállításának menetét.

A sortétel munkafolyamatának a munkafolyamat-szerkesztőben történő beállításához kattintson a jobb gombbal az elemre, és kattintson **Tulajdonságok** lap megnyitásához a **Tulajdonságok** lehetőségre. Ezután a következő eljárások segítségével beállíthatja a sortétel munkafolyamat-elem különféle tulajdonságait.

## <a name="name-the-lineitem-workflow-element"></a>A sortétel-munkafolyamat-elem elnevezése
A következő lépések segítségével elnevezheti a sortétel munkafolyamat-elemet.

1.  A bal oldali panelen kattintson az **Alapbeállítások** gombra.
2.  A **Név** mezőbe írja be a sortétel munkafolyamat-elem egyedi nevét.

## <a name="specify-whether-the-same-workflow-is-used-to-process-all-line-items"></a>Adja meg, hogy ugyanazon munkafolyamat segítségével dolgozza-e fel az összes sortételt
A következőképpen határozhatja meg, hogy ugyanazon munkafolyamat segítségével akarja-e feldolgozni a dokumentum összes sortételét.

1.  A bal oldali panelen kattintson az **Alapbeállítások** gombra.
2.  Ha ugyanazon munkafolyamattal akarja feldolgozni a dokumentum összes sortételét, kattintson az **Egyetlen munkafolyamat indítása az összes sortételhez** lehetőségre. Ezután válassza ki a sortételek feldolgozásához használni kívánt munkafolyamatot.
3.  Ha egy bizonyos feltételkészletnek megfelelő sortételeket egy bizonyos munkafolyamattal akarja feldolgozni, kattintson a **Külön munkafolyamat indítása minden egyes sortételhez** lehetőségre. Ezután hajtsa végre a következő lépéseket a feltételkészlet meghatározásához:
    1.  Kattintson a **Hozzáadás** gombra.
    2.  Válassza ki a táblán levő feltételt.
    3.  A **Feltétel neve** lapon írja be a meghatározni kívánt feltételkészlet nevét.
    4.  Kattintson a **Feltétel hozzáadása** lehetőségre a feltétel beírásához.
    5.  Adja meg a további szükséges feltételeket.
    6.  Ha ellenőrizni szeretné a megadott feltételkészlet beállításának helyességét, kattintson a **Teszt** lehetőségre. A **Munkafolyamati feltétel tesztelése** lapon, a **Feltétel érvényesítése** területen válasszon ki egy rekordot, majd kattintson a **Teszt** lehetőségre. A rendszer értékeli a bejegyzést, annak érdekében, hogy meghatározza, hogy a meghatározott feltételeknek megfeleljen-e. Kattintson az **OK** vagy a **Mégse** lehetőségre a **Tulajdonságok** lapra történő visszalépéshez.

    A **Munkafolyamat** lapon válassza ki azon sortételek feldolgozásához használni kívánt munkafolyamatot, amelyek megfelelnek a meghatározott feltételkészletnek.





