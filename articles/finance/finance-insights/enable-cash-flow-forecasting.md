---
title: Pénzforgalmi előrejelzés engedélyezése (előzetes verzió)
description: Ez a témakör azt mutatja be, hogyan lehet bekapcsolni a Pénzforgalmi előrejelzések funkcióját a pénzügyi elemzésekben.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 07/24/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-07-24
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 321c716c10b136769ea3a48a3b60a8a717798338
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/25/2020
ms.locfileid: "4646229"
---
# <a name="enable-cash-flow-forecasting-preview"></a>Pénzforgalmi előrejelzés engedélyezése (előzetes verzió)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Ez a témakör azt mutatja be, hogyan lehet bekapcsolni a Pénzforgalmi előrejelzések funkcióját a pénzügyi elemzésekben.

> [!NOTE]
> Ha fizetési előrejelzéseket szeretne használni a pénzforgalomban, be kell állítania a Vevői fizetési előrejelzések funkciót a [Vevői fizetési előrejelzések engedélyezése](enable-cust-paymnt-prediction.md) című részben leírtak szerint.

1. A Microsoft Dynamics Lifecycle Services (LCS) környezet lapjáról származó információk használatával csatlakozhat az Azure SQL elsődleges példányához az adott környezetben. Futtassa a következő Transact-SQL (T-SQL) parancsot a tesztkörnyezetben a teszteléshez kiadás bekapcsolásához. (Előfordulhat, hogy az LCS-ben be kell kapcsolnia az IP-cím hez való hozzáférést, mielőtt távolról csatlakozhatna az Application Object Server szolgáltatáshoz \[AOS\].)

    `INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED) VALUES ('CashflowInsightsFeature', 1)`

    > [!NOTE]
    > Ha a Microsoft Dynamics 365 Finance központi telepítése egy Service Fabric üzemelő példány, kihagyhatja ezt a lépést. A pénzügyi elemzési csoportnak már be kellett kapcsolnia a tesztelés kiadását az Ön számára. Ha nem látja a funkciókat a **Funkciókezelés** munkaterületen, vagy ha problémákat tapasztal, amikor megpróbálja bekapcsolni őket, keressen fel minket: <fiap@microsoft.com>.
  
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

## <a name="privacy-notice"></a>Adatvédelmi nyilatkozat

Az előzetes verziók (1) kevesebb adatvédelmi és biztonsági intézkedést alkalmazhatnak, mint a Dynamics 365 Finance and Operations szolgáltatás (2) és nem vonatkozik a szolgáltatásiszint-szerződés (SLA) ehhez a szolgáltatáshoz, (3) nem használhatók olyan személyes adatok vagy más adatok feldolgozásához, melyekhez törvényi vagy jogszabályi megfelelési követelmények tartoznak, és (4) korlátozott támogatás tartozik hozzá.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]