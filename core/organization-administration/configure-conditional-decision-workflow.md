---
title: "A feltételes döntés a munkafolyamat beállítása"
description: "Ezt követően a következő eljárás segítségével állítsa be egy feltételes döntés tulajdonságait."
author: sericks007
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 195703
ms.assetid: cd5554a4-210c-4c20-a7d3-4b1563c2b5df
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 3bba3d849d02cd84c2c0e0c5c15f7b649b3e125c
ms.lasthandoff: 03/31/2017


---

# <a name="configure-a-conditional-decision-in-a-workflow"></a>A feltételes döntés a munkafolyamat beállítása

Ezt követően a következő eljárás segítségével állítsa be egy feltételes döntés tulajdonságait.

A feltételes döntés egy olyan pont, ahol a munkafolyamat két ágra válik szét. A munkafolyamat-szerkesztő feltételes döntésének konfigurálásához kattintson a jobb gombbal a feltételes döntésre, és kattintson a **Tulajdonságok** űrlap megnyitásához a **Tulajdonságok** lehetőségre.

## <a name="name-a-decision"></a>A döntés elnevezése
A következő lépések segítségével elnevezheti a feltételes döntést.
1.  A bal oldali panelen kattintson az **Alapbeállítások** gombra.
2.  Adja meg a feltételes döntés egyedi nevét a **Név** mezőben.

## <a name="set-conditions"></a> Feltételek beállítása
A rendszer eldönti, hogy mely ágat használja: a benyújtott dokumentum kiértékelésével határozza meg, hogy az megfelel-e bizonyos feltételeknek.
1.  A bal oldali panelen kattintson az **Alapbeállítások** gombra.
2.  Click **Add condition**.
3.  Feltétel megadása.
4.  Ha szükséges, adjon meg további feltételeket.
5.  Ha ellenőrizni szeretné, hogy a megadott feltételek helyesen vannak-e konfigurálva, végezze el a következő lépéseket:
    1.  Kattintson a **Teszt** elemre a **Munkafolyamati feltétel tesztelése** űrlap megnyitásához.
    2.  Válasszon ki egy bejegyzést a képernyő **Feltétel érvényesítése** területén.
    3.  Kattintson a **Teszt** gombra. A rendszer értékeli a bejegyzést, annak érdekében, hogy meghatározza, hogy a meghatározott feltételeknek megfeleljen-e.
    4.  Kattintson a **OK** vagy **Mégse** való visszatéréshez a **tulajdonságok** formában.




