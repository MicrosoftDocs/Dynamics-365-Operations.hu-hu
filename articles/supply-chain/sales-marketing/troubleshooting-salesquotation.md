---
title: Értékesítési ajánlatok hibaelhárítása
description: Ez a témakör azt mutatja be, hogyan lehet javítani az értékesítési árajánlatok használata során felmerülő problémákat.
author: SmithaNataraj
manager: tfehr
ms.date: 09/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesQuotationTable, SalesQuotationTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-9-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 98011dbf22ff55b7651ce63557fa4a360130b6af
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4974760"
---
# <a name="troubleshoot-sales-quotations"></a><span data-ttu-id="53b94-103">Értékesítési ajánlatok hibaelhárítása</span><span class="sxs-lookup"><span data-stu-id="53b94-103">Troubleshoot sales quotations</span></span>

<span data-ttu-id="53b94-104">Ez a témakör azt mutatja be, hogyan lehet javítani az értékesítési árajánlatok használata során felmerülő problémákat.</span><span class="sxs-lookup"><span data-stu-id="53b94-104">This topic describes how to fix issues that you might encounter while you work with sales quotations.</span></span>

## <a name="i-cant-change-the-sales-quantity-of-a-sales-quotation-for-a-service-item"></a><span data-ttu-id="53b94-105">Nem lehet módosítani egy szolgáltatási tétel értékesítési ajánlatának értékesítési mennyiségét.</span><span class="sxs-lookup"><span data-stu-id="53b94-105">I can't change the sales quantity of a sales quotation for a service item.</span></span>

### <a name="issue-description"></a><span data-ttu-id="53b94-106">Probléma leírása</span><span class="sxs-lookup"><span data-stu-id="53b94-106">Issue description</span></span>

<span data-ttu-id="53b94-107">Ha az értékesítési mennyiséget (**SalesQty** mező) egy *Szolgáltatás* típusú elemhez próbálja beállítani egy értékesítési árajénlat sorában, a következő üzenetet kapja: „Frissítés nem engedélyezett a Mennyiség mezőhöz”.</span><span class="sxs-lookup"><span data-stu-id="53b94-107">If you try to set a sales quantity (**SalesQty** field) for an item of the *Service* type on a sales quotation line, you will receive the following message: "Update not allowed for field Quantity."</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="53b94-108">Probléma megoldása</span><span class="sxs-lookup"><span data-stu-id="53b94-108">Issue resolution</span></span>

<span data-ttu-id="53b94-109">Nem állíthat be értékesítési mennyiséget a szolgáltatási tétel termékekhez.</span><span class="sxs-lookup"><span data-stu-id="53b94-109">You can't set a sales quantity for products that are service items.</span></span> <span data-ttu-id="53b94-110">Ha például egy terméket telepítésével kapcsolatos szolgáltatást kínál, akkor nincs értelme a mennyiséget rögzítenie, mert nincs tényleges tétel.</span><span class="sxs-lookup"><span data-stu-id="53b94-110">For example, if you offer a service to install an item, it doesn't make sense to record a quantity, because there is no physical item.</span></span> <span data-ttu-id="53b94-111">Csak egy szolgáltatás van.</span><span class="sxs-lookup"><span data-stu-id="53b94-111">There is only a service.</span></span>

