---
title: Eszközök és eszköztípusok garanciái
description: Ez a témakör azt mutatja be, hogyan lehet eszközökre és eszköztípusokra garanciákat beállítani az Eszközkezelés modulban.
author: josaw1
manager: AnnBe
ms.date: 08/30/2019
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
ms.openlocfilehash: 3b13f8aba7e1d2448495f97a4772eb573e08c025
ms.sourcegitcommit: 802dbf0a744d70f9e546632d419415b0993331ab
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/13/2019
ms.locfileid: "1874601"
---
# <a name="warranty-on-assets-and-asset-types"></a>Eszközök és eszköztípusok garanciája

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


Ez a témakör azt mutatja be, hogyan lehet eszközökre és eszköztípusokra garanciákat beállítani az Eszközkezelés modulban.

## <a name="set-up-a-warranty-on-an-asset-type"></a>Garancia beállítása egy eszköztípusra

1. Válassza ki az **Eszközkezelés** \> **Beállítás** \> **Eszköztípusok** \> **Eszköztípusok** lehetőséget.
2. A bal oldali ablaktáblában válassza ki azt a eszköztípust, amelyhez szállítói garanciamegállapodást kíván csatolni, majdválassza ki az **Eszköztípus alapértelmezései** elemet.
3. Az **Általános** gyorslapon a **Szállítói garancia** mezőben válassza ki a szerződést.

## <a name="set-up-a-warranty-on-an-asset"></a>Garancia beállítása egy eszközre

1. Válassza ki az **Eszközkezelés** \> **Általános** \> **Eszközök** \> **Összes eszköz** lehetőséget.
2. Jelöljön ki egy eszközt, és kattintson a **Szerkesztés** gombra.
3. A **Szállító** gyorslap **Szállítói garancia** szakaszának **Garancia** mezőjében válassza ki a garanciaszerződést.
4. Válassza ki a kezdési és befejezési dátumokat a **Garancia kezdete** és **Garancia vége** mezőkben.

    > [!IMPORTANT]
    > Ha egy munkarendelésen kiválasztottak egy dátumot a **Garancia kezdete** mezőben, akkor a munkarendelésre vonatkozó garancia az adott dátumon érvénybe lép. A munkarendelések létrehozásakor a rendszer a **Garancia kezdete** mezőt automatikusan a létrehozás dátumára állítja. A dátum azonban módosítható úgy, hogy a megfelel például a garanciaszerződés kezdő dátumának.
    >
    > ![1. ábra](media/02-warranty.png)

> [!NOTE]
> Amikor egy szállítói garancia által fedezett eszközhöz hoz létre munkarendelést, ha a munkarendelés elvárt kezdési dátummal rendelkezik a garanciaidőszak folyamán, akkor értesítést kap a garanciaszerződésről. Ezután szükség esetén a munkarendelést érvényteleníteni lehet.
