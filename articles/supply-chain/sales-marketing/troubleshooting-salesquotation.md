---
title: Értékesítési ajánlatok hibaelhárítása
description: Ez a témakör azt mutatja be, hogyan lehet javítani az értékesítési árajánlatok használata során felmerülő problémákat.
author: SmithaNataraj
ms.date: 09/16/2020
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 09529ba729170be7281e2ae04008d3ba4a58e060
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5824750"
---
# <a name="troubleshoot-sales-quotations"></a><span data-ttu-id="db8d5-103">Értékesítési ajánlatok hibaelhárítása</span><span class="sxs-lookup"><span data-stu-id="db8d5-103">Troubleshoot sales quotations</span></span>

<span data-ttu-id="db8d5-104">Ez a témakör azt mutatja be, hogyan lehet javítani az értékesítési árajánlatok használata során felmerülő problémákat.</span><span class="sxs-lookup"><span data-stu-id="db8d5-104">This topic describes how to fix issues that you might encounter while you work with sales quotations.</span></span>

## <a name="i-cant-change-the-sales-quantity-of-a-sales-quotation-for-a-service-item"></a><span data-ttu-id="db8d5-105">Nem lehet módosítani egy szolgáltatási tétel értékesítési ajánlatának értékesítési mennyiségét.</span><span class="sxs-lookup"><span data-stu-id="db8d5-105">I can't change the sales quantity of a sales quotation for a service item.</span></span>

### <a name="issue-description"></a><span data-ttu-id="db8d5-106">Probléma leírása</span><span class="sxs-lookup"><span data-stu-id="db8d5-106">Issue description</span></span>

<span data-ttu-id="db8d5-107">Ha az értékesítési mennyiséget (**SalesQty** mező) egy *Szolgáltatás* típusú elemhez próbálja beállítani egy értékesítési árajénlat sorában, a következő üzenetet kapja: „Frissítés nem engedélyezett a Mennyiség mezőhöz”.</span><span class="sxs-lookup"><span data-stu-id="db8d5-107">If you try to set a sales quantity (**SalesQty** field) for an item of the *Service* type on a sales quotation line, you will receive the following message: "Update not allowed for field Quantity."</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="db8d5-108">Probléma megoldása</span><span class="sxs-lookup"><span data-stu-id="db8d5-108">Issue resolution</span></span>

<span data-ttu-id="db8d5-109">Nem állíthat be értékesítési mennyiséget a szolgáltatási tétel termékekhez.</span><span class="sxs-lookup"><span data-stu-id="db8d5-109">You can't set a sales quantity for products that are service items.</span></span> <span data-ttu-id="db8d5-110">Ha például egy terméket telepítésével kapcsolatos szolgáltatást kínál, akkor nincs értelme a mennyiséget rögzítenie, mert nincs tényleges tétel.</span><span class="sxs-lookup"><span data-stu-id="db8d5-110">For example, if you offer a service to install an item, it doesn't make sense to record a quantity, because there is no physical item.</span></span> <span data-ttu-id="db8d5-111">Csak egy szolgáltatás van.</span><span class="sxs-lookup"><span data-stu-id="db8d5-111">There is only a service.</span></span>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]