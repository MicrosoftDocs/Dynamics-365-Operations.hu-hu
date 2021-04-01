---
title: Eszközök és eszköztípusok garanciái
description: Ez a témakör azt mutatja be, hogyan lehet eszközökre és eszköztípusokra garanciákat beállítani az Eszközkezelés modulban.
author: josaw1
manager: tfehr
ms.date: 08/30/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 78ac93b1e681fca7d7eefd921f282a8496aa9d0a
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5245323"
---
# <a name="warranties-on-assets-and-asset-types"></a>Eszközök és eszköztípusok garanciái

[!include [banner](../../includes/banner.md)]

 


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
    > ![Munkarendelés lap](media/02-warranty.png)

> [!NOTE]
> Amikor egy szállítói garancia által fedezett eszközhöz hoz létre munkarendelést, ha a munkarendelés elvárt kezdési dátummal rendelkezik a garanciaidőszak folyamán, akkor értesítést kap a garanciaszerződésről. Ezután szükség esetén a munkarendelést érvényteleníteni lehet.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]