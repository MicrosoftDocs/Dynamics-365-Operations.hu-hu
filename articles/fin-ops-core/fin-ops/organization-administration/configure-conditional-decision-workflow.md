---
title: Feltételes döntések konfigurálása munkafolyamatban
description: Ezt követően a következő eljárás segítségével állítsa be egy feltételes döntés tulajdonságait.
author: ChrisGarty
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 195703
ms.assetid: cd5554a4-210c-4c20-a7d3-4b1563c2b5df
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0fa708b4ac1f17a9ed6852a9eeb3e764b750a4a4
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/31/2022
ms.locfileid: "8070958"
---
# <a name="configure-conditional-decisions-in-a-workflow"></a>Feltételes döntések konfigurálása munkafolyamatban

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

Ezt követően a következő eljárás segítségével állítsa be egy feltételes döntés tulajdonságait.

A feltételes döntés egy olyan pont, ahol a munkafolyamat két ágra válik szét. A munkafolyamat-szerkesztő feltételes döntésének konfigurálásához kattintson a jobb gombbal a feltételes döntésre, és kattintson a **Tulajdonságok** űrlap megnyitásához a **Tulajdonságok** lehetőségre.

## <a name="name-a-decision"></a>A döntés elnevezése

A következő lépések segítségével elnevezheti a feltételes döntést.

1. A bal oldali panelen kattintson az **Alapbeállítások** gombra.
2. Adja meg a feltételes döntés egyedi nevét a **Név** mezőben.

## <a name="set-conditions"></a>Feltételek beállítása

A rendszer eldönti, hogy mely ágat használja: a benyújtott dokumentum kiértékelésével határozza meg, hogy az megfelel-e bizonyos feltételeknek.

1. A bal oldali panelen kattintson az **Alapbeállítások** gombra.
2. Kattintson a **Feltétel hozzáadása** parancsra.
3. Feltétel megadása.
4. Ha szükséges, adjon meg további feltételeket.
5. Ha ellenőrizni szeretné, hogy a megadott feltételek helyesen vannak-e konfigurálva, végezze el a következő lépéseket:

    1. Kattintson a **Teszt** elemre a **Munkafolyamati feltétel tesztelése** űrlap megnyitásához.
    2. Válasszon ki egy bejegyzést a képernyő **Feltétel érvényesítése** területén.
    3. Kattintson a **Teszt** gombra. A rendszer értékeli a bejegyzést, annak érdekében, hogy meghatározza, hogy a meghatározott feltételeknek megfeleljen-e.
    4. Kattintson az **OK** vagy a **Mégse** lehetőségre a **Tulajdonságok** űrlapra történő visszalépéshez.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]