---
title: Kölcsönzött eszközök
description: Ez a témakör azt ismerteti, hogyan lehet regisztrálni a kölcsön tárgyi eszközöket az Eszközkezelésben.
author: johanhoffmann
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetObjectLoanSend, EntAssetObjectLoanListPage, EntAssetObjectLoanReturn, EntAssetObjectLoanInfoPart
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: f70b29ef69b80160f108e6f53edda12b86c2c9db
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/15/2022
ms.locfileid: "9015754"
---
# <a name="asset-loans"></a>Kölcsönzött eszközök

[!include [banner](../../includes/banner.md)]

 

Ha a vállalat a javítási vagy karbantartási feladatokhoz a belső helyekről vagy a vevőkről kap eszközöket, és ha ideiglenesen kölcsönbe ad eszközöket, ezekre a helyekre vagy ügyfeleknek, az Eszközkezelésben nyomon követheti ezeket az eszközkölcsönzéseket.

## <a name="register-asset-loans-on-a-maintenance-request"></a>Kölcsönzött eszközök rögzítése karbantartási kéréshez

1. Válassza ki **az eszközkezelés** \> **karbantartási kérését** \> **, amely minden karbantartási kérést vagy** az aktív **karbantartási kérést kéri.**
2. Válassza ki azt a karbantartási kérést, amelyre azeszköz kölcsönzését regisztrálni szeretné, majd válassza a **Szerkesztés** parancsot.
3. A **Kérelem** oldalon válassza a **Kölcsönzött eszköz küldése** lehetőséget.
4. Válassza ki az eszközt, és adja meg a várható visszaadási dátumot.
5. Válassza ki az **OK** lehetőséget.

> [!NOTE]
> - Csak akkor küldhet kölcsönzött eszközt, ha az eszközhöz hasonló eszköz rendelkezésre áll.
> - A kölcsön tárgyát képező eszköznek olyan eszközéletciklus-állapotúnak kell lennie, amely lehetővé teszi, hogy az kölcsön eszközként legyen használva, például **InStorage**. Amikor a kölcsönzött eszköz regisztrálása megtörtént, a program automatikusan frissíti az eszköz életciklus-állapotát, például **OnLoan** értékre.

A más helyekre **vagy vevőkhöz kölcsönadott összes eszköz listájának megtekintéséhez válassza az Eszközkezelés** \> **·** \> **eszközkölcsönzése – minden eszközkölcsönzést.** Ha egy eszköz esetében be van jelölve a **Befejezve** jelölőnégyzet, akkor a program a vállalatnak visszaküldöttként regisztrálja az eszközt.

![Karbantartási kérések kezelése.](media/06-manage-maintenance-requests.png)

Az **Aktív eszköz kölcsönzése** lapon megtekintheti az összes olyan eszköz listáját, amely még nincs visszaküldve a vállalatnak.

## <a name="register-loan-assets-as-returned"></a>A kölcsönzött eszköz rögzítése visszaküldöttként

1. Válassza ki **az Eszközkezelés eszközkölcsönzése** \> **·** \> **- aktív eszközkölcsönzés.**
2. Válassza ki a visszaküldöttként regisztrálni kívánt tárgyi eszközt, majd válassza a **Kölcsönzött eszköz visszaküldése** lehetőséget.
3. A **Visszaadva** mezőben adja meg dátumot és az időt.
4. Válassza ki az **OK** lehetőséget.
5. Frissítse az **Aktív eszköz kölcsönzése** listaoldalt és figyelje meg, hogy az eszköz kölcsönzése már nem jelenik meg a listában.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]