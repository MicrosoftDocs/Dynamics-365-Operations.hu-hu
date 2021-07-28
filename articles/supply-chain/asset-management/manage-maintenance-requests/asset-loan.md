---
title: Kölcsönzött eszközök
description: Ez a témakör bemutatja, hogyan eszközök kölcsönadását regisztrálni az Eszközkezelés modulban.
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
ms.openlocfilehash: 9be41f459b8ec8ca8ccad2360218b32299cb319e
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/06/2021
ms.locfileid: "6354929"
---
# <a name="asset-loans"></a>Kölcsönzött eszközök

[!include [banner](../../includes/banner.md)]

 

Ha a vállalat a javítási vagy karbantartási feladatokhoz a belső helyekről vagy a vevőkről kap eszközöket, és ha ideiglenesen kölcsönbe ad eszközöket, ezekre a helyekre vagy ügyfeleknek, az Eszközkezelésben nyomon követheti ezeket az eszközkölcsönzéseket.

## <a name="register-asset-loans-on-a-maintenance-request"></a>Kölcsönzött eszközök rögzítése karbantartási kéréshez

1. Válassza az **Eszközkezelés** \> **Közös** \> **Karbantartási kérések** \> **Összes karbantartási kérés** vagy **Aktív karbantartási kérések** lehetőséget.
2. Válassza ki azt a karbantartási kérést, amelyre azeszköz kölcsönzését regisztrálni szeretné, majd válassza a **Szerkesztés** parancsot.
3. A **Kérelem** oldalon válassza a **Kölcsönzött eszköz küldése** lehetőséget.
4. Válassza ki az eszközt, és adja meg a várható visszaadási dátumot.
5. Válassza ki az **OK** lehetőséget.

> [!NOTE]
> - Csak akkor küldhet kölcsönzött eszközt, ha az eszközhöz hasonló eszköz rendelkezésre áll.
> - A kölcsön tárgyát képező eszköznek olyan eszközéletciklus-állapotúnak kell lennie, amely lehetővé teszi, hogy az kölcsön eszközként legyen használva, például **InStorage**. Amikor a kölcsönzött eszköz regisztrálása megtörtént, a program automatikusan frissíti az eszköz életciklus-állapotát, például **OnLoan** értékre.

Ha meg szeretné tekinteni az összes olyan eszköz listáját, amelyet más helyekre vagy vevőknek kölcsönzött akkor válassza az **Eszközkezelés** \> **Közös** \> **Kölcsönzött eszköz** \> **Összes kölcsönzött eszköz** lehetőséget. Ha egy eszköz esetében be van jelölve a **Befejezve** jelölőnégyzet, akkor a program a vállalatnak visszaküldöttként regisztrálja az eszközt.

![Karbantartási kérések kezelése.](media/06-manage-maintenance-requests.png)

Az **Aktív eszköz kölcsönzése** lapon megtekintheti az összes olyan eszköz listáját, amely még nincs visszaküldve a vállalatnak.

## <a name="register-loan-assets-as-returned"></a>A kölcsönzött eszköz rögzítése visszaküldöttként

1. Válassza az **Eszközkezelés** \> **Általános** \> **Kölcsönzött eszköz** \> **Aktív kölcsönzött eszközök** lehetőséget.
2. Válassza ki a visszaküldöttként regisztrálni kívánt tárgyi eszközt, majd válassza a **Kölcsönzött eszköz visszaküldése** lehetőséget.
3. A **Visszaadva** mezőben adja meg dátumot és az időt.
4. Válassza ki az **OK** lehetőséget.
5. Frissítse az **Aktív eszköz kölcsönzése** listaoldalt és figyelje meg, hogy az eszköz kölcsönzése már nem jelenik meg a listában.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]