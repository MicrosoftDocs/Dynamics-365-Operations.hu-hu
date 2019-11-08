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
ms.openlocfilehash: cb809e596fd6bf3030bcee460838798435512b95
ms.sourcegitcommit: d37fb09101c30858bcb975931b3d8f947d72017b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/10/2019
ms.locfileid: "2572129"
---
[!include [banner](../includes/banner.md)]

# <a name="report-as-finished-to-a-license-plate-controlled-location-from-the-job-card-device"></a><span data-ttu-id="1a98d-103">Készként történő jelentés egy azonosítótáblás szabályozású helyen a Feladatkártya eszközről</span><span class="sxs-lookup"><span data-stu-id="1a98d-103">Report as finished to a license plate controlled location from the Job card device</span></span> 

<span data-ttu-id="1a98d-104">A Készre jelentés nevű folyamat fejezi be a termelési rendelésen szereplő késztermékeket a készletbe.</span><span class="sxs-lookup"><span data-stu-id="1a98d-104">The process called Reporting as finished completes finished products on a production order to the inventory.</span></span> <span data-ttu-id="1a98d-105">Ha a késztermék a speciális raktári folyamatokhoz engedélyezve van, akkor a termék készként jelentve lesz a termelési kimeneti helynek nevezett helyre.</span><span class="sxs-lookup"><span data-stu-id="1a98d-105">If the finished product is enabled for the advanced warehouse processes, the product is reported as finished to a location called the production output location.</span></span> <span data-ttu-id="1a98d-106">A termelési kimeneti hely beállításával kapcsolatos további tudnivalókat lásd [Termelési kimeneti hely](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/production-control/production-output-location).</span><span class="sxs-lookup"><span data-stu-id="1a98d-106">For information about setting up the production output location, see [Production output location](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/production-control/production-output-location).</span></span>

<span data-ttu-id="1a98d-107">A feladat végrehajtásához ki kell választania egy meglévő azonosítótábla-számot.</span><span class="sxs-lookup"><span data-stu-id="1a98d-107">You must select an existing license plate number to complete this task.</span></span> <span data-ttu-id="1a98d-108">Ha a termelési kimeneti helyet úgy állította be, hogy az azonosítótábla által nyomon követhető, akkor a termelési kimeneti hely készként jelentésekor fel kell tüntetni az azonosítótábla számát.</span><span class="sxs-lookup"><span data-stu-id="1a98d-108">If the production output location is set up to be tracked by license plate, then a license plate number must be included when reporting the production output location as finished.</span></span> <span data-ttu-id="1a98d-109">Az **Azonosítótábla** mező látható a **Jelentés az előrehaladásról** figyelmeztetésében a **Feladatkártya-eszköz** lapján.</span><span class="sxs-lookup"><span data-stu-id="1a98d-109">The **License plate** field is visible on the **Report progress** prompt on the **Job card device** page.</span></span> <span data-ttu-id="1a98d-110">Ez a mező csak akkor látható a **Jelentés az előrehaladásról** kijelzésen, amikor a termelési rendelés utolsó műveletéről készül jelentés.</span><span class="sxs-lookup"><span data-stu-id="1a98d-110">The field is only visible on the **Report progress** prompt when reporting on the last operation of the production order.</span></span> <span data-ttu-id="1a98d-111">Ez a mező csak akkor jelenik meg, ha a termelési rendeléshez tartozó tétel engedélyezve van a raktárkezelési folyamatokhoz.</span><span class="sxs-lookup"><span data-stu-id="1a98d-111">The field is only shown if the item for the production order is enabled for the warehouse management processes.</span></span> 
