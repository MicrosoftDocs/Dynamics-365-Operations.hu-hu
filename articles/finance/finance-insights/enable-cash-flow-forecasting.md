---
title: Pénzforgalmi előrejelzés engedélyezése (előzetes verzió)
description: Ez a témakör azt mutatja be, hogyan lehet bekapcsolni a Pénzforgalmi előrejelzések funkcióját a pénzügyi elemzésekben.
author: ShivamPandey-msft
ms.date: 07/16/2021
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
ms.openlocfilehash: 29118557a1de4d3521f8125395b26471f7f48f3e
ms.sourcegitcommit: e42c7dd495829b0853cebdf827b86a7cf655cf86
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/17/2021
ms.locfileid: "6638621"
---
# <a name="enable-cash-flow-forecasting-preview"></a>Pénzforgalmi előrejelzés engedélyezése (előzetes verzió)

[!include [banner](../includes/banner.md)]

Ez a témakör azt mutatja be, hogyan lehet bekapcsolni a Pénzforgalmi előrejelzések funkcióját a pénzügyi elemzésekben.

> [!NOTE]
> Ha fizetési előrejelzéseket szeretne használni a pénzforgalomban, be kell állítania a Vevői fizetési előrejelzések funkciót a [Vevői fizetési előrejelzések engedélyezése](enable-cust-paymnt-prediction.md) című részben leírtak szerint.

1. A Microsoft Dynamics Lifecycle Services (LCS) környezet lapjáról származó információk használatával csatlakozhat az Azure SQL elsődleges példányához az adott környezetben. Futtassa a következő Transact-SQL (T-SQL) parancsot a tesztkörnyezetben a teszteléshez kiadás bekapcsolásához. (Előfordulhat, hogy az LCS-ben be kell kapcsolnia az IP-cím hez való hozzáférést, mielőtt távolról csatlakozhatna az Application Object Server szolgáltatáshoz \[AOS\].)

    `INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED) VALUES ('CashflowInsightsFeature', 1)`

    > [!NOTE]
    > Hagyja ki ezt a lépést, ha a 10.0.20-as vagy újabb verziót használja, vagy ha Service Fabric-telepítést használ. A pénzügyi elemzési csoportnak már be kellett kapcsolnia a tesztelés kiadását az Ön számára. Ha nem látja a funkciót a **Funkciókezelés** munkaterületen, vagy ha problémákat tapasztal, amikor megpróbálja bekapcsolni, keressen fel minket: <fiap@microsoft.com>.
  
2. Nyissa meg a **Funkciókezelés** munkaterületet, és kövesse az alábbi lépéseket:

    1. Válassza a **Frissítések keresése** elemet.
    2. Kapcsolja be a következő szolgáltatásokat:

        - Új rácsvezérlő
        - Csoportosítás rácsokba (előzetes verzió) 
        - Vevői fizetési előrejelzések (előzetes verzió)
        - Pénzforgalmi előrejelzések (előzetes verzió)

3. Nyissa meg a **Készpénz- és bankkezelés \> Pénzforgalom-előrejelzés** lehetőséget, és adja hozzá az előrejelzésekben szerepeltetni kívánt likviditási számlákat.

    > [!NOTE]
    > Ha a likviditási számlák nincsenek beállítva, a pénzforgalom nem generálható.

4. Nyissa meg a **Készpénz- és bankkezelés \> Beállítás \> Pénzügyi elemzések (előzetes verzió) \> Pénzforgalmi előrejelzések (előzetes verzió)** című részt, és kövesse az alábbi lépéseket:

    1. A **Pénzforgalmi előrejelzés** lapon válassza a **Funkció engedélyezése** lehetőséget.
    2. Válassza az **Előrejelzési modell létrehozása** lehetőséget.

A pénzforgalmi előrejelzés képesség beállításával kapcsolatos további tudnivalókat lásd: [Pénzforgalmi előrejelzés](cash-flow-forecast-intro.md).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
