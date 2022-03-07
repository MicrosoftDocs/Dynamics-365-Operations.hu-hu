---
title: Nem található a "Munkafolyamat" legördülő párbeszédpanel a készletnaplókhoz
description: A naplóoldalon nem található a "Munkafolyamat" legördülő párbeszédpanel, vagy a kapcsolódó munkafolyamat-műveletek nem érhetők el
author: sherry-zheng
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 8b2772a75c2388f4d78a459f9dfb72ad7c1be4ab
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476534"
---
# <a name="you-cant-find-the-workflow-drop-down-dialog-box-for-inventory-journals"></a>Nem található a "Munkafolyamat" legördülő párbeszédpanel a készletnaplókhoz

## <a name="symptoms"></a>Tünetek

A naplóoldalon nem található a **Munkafolyamat** legördülő párbeszédpanel, vagy a kapcsolód munkafolyamat-műveletek nem érhetők el.

Ez a probléma három okból fordulhat elő, az alábbi szakaszok szerint.

## <a name="resolution-1"></a>1. megoldás

Ha a probléma az összes felhasználóra vonatkozik, akkor előfordulhat, hogy a jóváhagyási munkafolyamat nincs hozzárendelve a naplónévhez. Egy hiba javításához kövesse az alábbi lépéseket.

1. Ugorjon a **Készletkezelés &gt; Beállítás &gt; Naplónevek &gt; Készlet** pontra.
1. A beállítások megnyitásához válassza ki a napló nevét a lista paneljén.
1. Az **Általános** gyorslapon állítsa a **Jóváhagyási munkafolyamat** beállítást *Igen* értékre. Kattintson az **Igen** gombra, ha a rendszer a módosítás megerősítését kéri.
1. A **Munkafolyamat** mezőben válassza ki azt a munkafolyamatot, amelyet a kiválasztott naplónévhez használni szeretne.

## <a name="resolution-2"></a>2. megoldás

Ha a munkafolyamat egyedi kódot használ, problémák léphetnek fel a rendszer frissítése után. Például a napló munkafolyamatában a **Küldés** gomb szürke színnel jelenhet meg, így nem jelölheti ki a küldés jóváhagyásához.

Ha a **Küldés** gomb szürke színű, lehet, hogy testre szabták munkafolyamatot, ami azt jelenti, hogy a munkafolyamat módszere – a `canSubmitToWorkflow()` a `FormDataUtil` értékben – meg lett hosszabbítva. A probléma megoldásához módosítsa a `canSubmitToWorkflow()` módszer hosszabbításának módját, hogy a következő példában szereplő szerkezetet használja.

```xpp
[ExtensionOf(formStr(InventJournalMovement))]
public final class InventJournalMovement_extension
{
    public boolean canSubmitToWorkflow()
    {
        boolean ret = YourLogicOfCanSubmitToWorkflow();

        return ret;
    }
}
```

## <a name="resolution-3"></a>3. megoldás

Ha a probléma csak néhány konkrét felhasználóra vonatkozik, akkor lehet, hogy ezeknek a felhasználóknak nincsenek meg a készletnaplókban a munkafolyamat-műveletek futtatásához szükséges biztonsági jogosultságai. Ellenőrizze, hogy minden érintett felhasználó rendelkezik-e a *Készletnapló munkafolyamatának karbantartása* biztonsági jogosultsággal. Alapértelmezés szerint ez a jogosultság ugyanolyan nevű feladathoz van hozzárendelve, és ez a feladat a *Raktári dolgozó* és *Raktárvezető* szerepkörre vonatkozik.
