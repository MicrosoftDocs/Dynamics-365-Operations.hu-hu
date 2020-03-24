---
title: Készként történő jelentés egy azonosítótáblás szabályozású helyen a Feladatkártya eszközről
description: Ez a témakör egy termelési rendelés késztermékinek készletre történő teljesítésének folyamatát ismerteti, amikor egy azonosítótábla vezérli a helyet.
author: johanhoffmann
manager: AnnBe
ms.date: 01/06/2020
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
ms.openlocfilehash: 5f61c1abfb115f02e6ff314f6a3e42bb1d3b543f
ms.sourcegitcommit: f38302b9430f2ab3efe91d0a7beff946bc610e8f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/28/2020
ms.locfileid: "3092568"
---
[!include [banner](../includes/banner.md)]

# <a name="report-as-finished-to-a-license-plate-controlled-location-from-the-job-card-device"></a>Készként történő jelentés egy azonosítótáblás szabályozású helyen a Feladatkártya eszközről 

A Készre jelentés nevű folyamat fejezi be a termelési rendelésen szereplő késztermékeket a készletbe. Ha a késztermék a speciális raktári folyamatokhoz engedélyezve van, akkor a termék készként jelentve lesz a termelési kimeneti helynek nevezett helyre. A termelési kimeneti hely beállításával kapcsolatos további tudnivalókat lásd [Termelési kimeneti hely](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/production-control/production-output-location).

Ha a gyártási kimenet helye azonosítótábla-vezérelt, akkor a készként való jelentéskor meg kell adni az azonosítótáblát. Az **Azonosítótábla** mező látható a **Jelentés az előrehaladásról** figyelmeztetésében a **Feladatkártya-eszköz** lapján. A mező csak akkor látható az **Előrehaladás jelentése** figyelmeztetésben, amikor a jelentés a termelési rendelés utolsó műveletéről készül, és a termelési rendeléshez tartozó cikk engedélyezve van a raktárkezelési folyamatokban. 

Két lehetőség van az azonosítótábla megadására
- A felhasználó egy meglévő azonosítótáblát kijelöl az azonosítótábla-mezőben.
- Az azonosítótábla automatikusan létrejön egy számsorozatból, és alapértelmezettként az azonosítótábla-mezőbe kerül.

Az azonosítótábla automatikus generálási lehetőségének beállításához válassza az **Azonosítótábla előállítása** lehetőséget a **Feladatkártya konfigurálása az eszközökhöz** lapon.
