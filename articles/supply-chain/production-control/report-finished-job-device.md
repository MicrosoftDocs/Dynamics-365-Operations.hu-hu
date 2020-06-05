---
title: Készként történő jelentés egy azonosítótáblás szabályozású helyen a Feladatkártya eszközről
description: Ez a témakör egy termelési rendelés késztermékinek készletre történő teljesítésének folyamatát ismerteti, amikor egy azonosítótábla vezérli a helyet.
author: johanhoffmann
manager: tfehr
ms.date: 01/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: JmgRegistration, ProdJournalTransJob, ProdJournalTransRoute, ProdParmReportFinished
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 19351
ms.assetid: bcc9e242-b4b8-4144-b14d-c3c106fb40ec
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2019-09-06
ms.dyn365.ops.version: AX 10.0.6
ms.openlocfilehash: 74e1e30f5afe51cd0ecec2530ffcb9a59eec5fee
ms.sourcegitcommit: 89022f39502b19c24c0997ae3a01a64b93280f42
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/12/2020
ms.locfileid: "3367245"
---
# <a name="report-as-finished-to-a-license-plate-controlled-location-from-the-job-card-device"></a><span data-ttu-id="8e2dc-103">Készként történő jelentés egy azonosítótáblás szabályozású helyen a Feladatkártya eszközről</span><span class="sxs-lookup"><span data-stu-id="8e2dc-103">Report as finished to a license plate controlled location from the Job card device</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8e2dc-104">A Készre jelentés nevű folyamat fejezi be a termelési rendelésen szereplő késztermékeket a készletbe.</span><span class="sxs-lookup"><span data-stu-id="8e2dc-104">The process called Reporting as finished completes finished products on a production order to the inventory.</span></span> <span data-ttu-id="8e2dc-105">Ha a késztermék a speciális raktári folyamatokhoz engedélyezve van, akkor a termék készként jelentve lesz a termelési kimeneti helynek nevezett helyre.</span><span class="sxs-lookup"><span data-stu-id="8e2dc-105">If the finished product is enabled for the advanced warehouse processes, the product is reported as finished to a location called the production output location.</span></span> <span data-ttu-id="8e2dc-106">A termelési kimeneti hely beállításával kapcsolatos további tudnivalókat lásd [Termelési kimeneti hely](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/production-control/production-output-location).</span><span class="sxs-lookup"><span data-stu-id="8e2dc-106">For information about setting up the production output location, see [Production output location](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/production-control/production-output-location).</span></span>

<span data-ttu-id="8e2dc-107">Ha a gyártási kimenet helye azonosítótábla-vezérelt, akkor a készként való jelentéskor meg kell adni az azonosítótáblát.</span><span class="sxs-lookup"><span data-stu-id="8e2dc-107">If the production output location is license plate controlled, then a license plate must be provided when reporting as finished.</span></span> <span data-ttu-id="8e2dc-108">Az **Azonosítótábla** mező látható a **Jelentés az előrehaladásról** figyelmeztetésében a **Feladatkártya-eszköz** lapján.</span><span class="sxs-lookup"><span data-stu-id="8e2dc-108">The **License plate** field is visible on the **Report progress** prompt on the **Job card device** page.</span></span> <span data-ttu-id="8e2dc-109">A mező csak akkor látható az **Előrehaladás jelentése** figyelmeztetésben, amikor a jelentés a termelési rendelés utolsó műveletéről készül, és a termelési rendeléshez tartozó cikk engedélyezve van a raktárkezelési folyamatokban.</span><span class="sxs-lookup"><span data-stu-id="8e2dc-109">The field is only visible on the **Report progress** prompt when reporting on the last operation of the production order and the item for the production order is enabled for the warehouse management processes.</span></span>

<span data-ttu-id="8e2dc-110">Két lehetőség van az azonosítótábla megadására:</span><span class="sxs-lookup"><span data-stu-id="8e2dc-110">There are two options for providing the license plate:</span></span>

- <span data-ttu-id="8e2dc-111">A felhasználó egy meglévő azonosítótáblát kijelöl az azonosítótábla-mezőben.</span><span class="sxs-lookup"><span data-stu-id="8e2dc-111">The user selects an existing license plate in the license plate field.</span></span>
- <span data-ttu-id="8e2dc-112">Az azonosítótábla automatikusan létrejön egy számsorozatból, és alapértelmezettként az azonosítótábla-mezőbe kerül.</span><span class="sxs-lookup"><span data-stu-id="8e2dc-112">The license plate is automatically generated from a number sequence and defaulted to the license plate field.</span></span>

<span data-ttu-id="8e2dc-113">Az azonosítótábla automatikus generálási lehetőségének beállításához válassza az **Azonosítótábla előállítása** lehetőséget a **Feladatkártya konfigurálása az eszközökhöz** lapon.</span><span class="sxs-lookup"><span data-stu-id="8e2dc-113">The option to have the license plate generated automatically is configured by selecting the option **Generate license plate** on the **Configure job card for devices** page.</span></span>
