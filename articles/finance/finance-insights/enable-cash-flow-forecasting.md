---
title: A pénzforgalom előrejelzésének lehetővé tétele
description: Ez a témakör azt mutatja be, hogyan lehet bekapcsolni a Pénzforgalmi előrejelzések funkcióját a pénzügyi elemzésekben.
author: ShivamPandey-msft
ms.date: 02/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-07-24
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 763818f70095964d77ff82cf02178367d05eaf23
ms.sourcegitcommit: 3105642fca2392edef574b60b4748a82cda0a386
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/12/2022
ms.locfileid: "8109579"
---
# <a name="enable-cash-flow-forecasting"></a>A pénzforgalom előrejelzésének lehetővé tétele

[!include [banner](../includes/banner.md)]

Ez a témakör bemutatja a Pénzügyi információk pénzforgalmi előrejelzési funkció bekapcsolt funkcióját.

> [!NOTE]
> Ha fizetési előrejelzéseket szeretne használni a pénzforgalomban, be kell állítania a Vevői fizetési előrejelzések funkciót a [Vevői fizetési előrejelzések engedélyezése](enable-cust-paymnt-prediction.md) című részben leírtak szerint.
  
1. Nyissa meg a **Funkciókezelés** munkaterületet, és kövesse az alábbi lépéseket:

    1. Válassza a **Frissítések keresése** elemet.
    2. A Mind **lapon** keressen rá a pénzforgalmi **előrejelzésekre**. Ha nem találja ezt a funkciót, **keressen pénzforgalmi előrejelzéseket (előnézet)**. 
    3. A funkció bekapcsolva.

2. Nyissa meg a **Készpénz- és bankkezelés \> Pénzforgalom-előrejelzés** lehetőséget, és adja hozzá az előrejelzésekben szerepeltetni kívánt likviditási számlákat. A Kinnlevőségek **és** **kötelezettségek lapon a kifizetések likviditási számlájának** beállítása is. Győződjön meg róla, hogy újraszámálja a pénzforgalmi előrejelzést.

    > [!NOTE]
    > Ha a likviditási számlák nincsenek beállítva, a pénzforgalom nem generálható.
    >
    > A pénzforgalmi előrejelzések beállításának további tudnivalókat lásd [a Pénzforgalmi előrejelzésben](../cash-bank-management/cash-flow-forecasting.md).

3. Nyissa meg a **Készpénz- és bankkezelés \> Beállítás \> Pénzügyi elemzések (előzetes verzió) \> Pénzforgalmi előrejelzések (előzetes verzió)** című részt, és kövesse az alábbi lépéseket:

    1. A **Pénzforgalmi előrejelzés** lapon válassza a **Funkció engedélyezése** lehetőséget.
    2. Válassza az **Előrejelzési modell létrehozása** lehetőséget.

> [!NOTE]
> A **pénzforgalmi előrejelzési modell** képzéséhez 100 vagy több olyan tranzakció szükséges, amely egy évnél több adatokat tartalmaz. Javasoljuk, hogy legalább két évnyi adatot és több mint 1000 tranzakciót tartalmaz.

A pénzforgalmi előrejelzés képesség beállításával kapcsolatos további tudnivalókat lásd: [Pénzforgalmi előrejelzés](cash-flow-forecast-intro.md).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
