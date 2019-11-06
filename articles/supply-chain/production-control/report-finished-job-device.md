---
title: Készként történő jelentés egy azonosítótáblás szabályozású helyen a Feladatkártya eszközről
description: Ez a témakör egy termelési rendelés késztermékinek készletre történő teljesítésének folyamatát ismerteti, amikor egy azonosítótábla vezérli a helyet.
author: johanhoffmann
manager: AnnBe
ms.date: 09/06/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: JmgRegistration, ProdJournalTransJob, ProdJournalTransRoute, ProdParmReportFinished
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 19351
ms.assetid: bcc9e242-b4b8-4144-b14d-c3c106fb40ec
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2019-09-06
ms.dyn365.ops.version: AX 10.0.6
ms.openlocfilehash: 35ad27a6b8a52bfd086fbe4fc57b1681ff88fd5b
ms.sourcegitcommit: 58db26b7edf02e7c33aaaf1c934e3263aa74b01f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/11/2019
ms.locfileid: "1995142"
---
[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

# <a name="report-as-finished-to-a-license-plate-controlled-location-from-the-job-card-device"></a>Készként történő jelentés egy azonosítótáblás szabályozású helyen a Feladatkártya eszközről 

A Készre jelentés nevű folyamat fejezi be a termelési rendelésen szereplő késztermékeket a készletbe. Ha a késztermék a speciális raktári folyamatokhoz engedélyezve van, akkor a termék készként jelentve lesz a termelési kimeneti helynek nevezett helyre. A termelési kimeneti hely beállításával kapcsolatos további tudnivalókat lásd [Termelési kimeneti hely](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/production-control/production-output-location).

A feladat végrehajtásához ki kell választania egy meglévő azonosítótábla-számot. Ha a termelési kimeneti helyet úgy állította be, hogy az azonosítótábla által nyomon követhető, akkor a termelési kimeneti hely készként jelentésekor fel kell tüntetni az azonosítótábla számát. Az **Azonosítótábla** mező látható a **Jelentés az előrehaladásról** figyelmeztetésében a **Feladatkártya-eszköz** lapján. Ez a mező csak akkor látható a **Jelentés az előrehaladásról** kijelzésen, amikor a termelési rendelés utolsó műveletéről készül jelentés. Ez a mező csak akkor jelenik meg, ha a termelési rendeléshez tartozó tétel engedélyezve van a raktárkezelési folyamatokhoz. 