--- 
title: "Gépi tanulási alapú termékajánlások konfigurálása"
description: "Ez az eljárás frissíti azokat az adatokat az entitástárban, amelyeket a termékajánlásokért felelős gépi tanulási rendszer használ, majd ezt követően engedélyezi a termékajánlásokat a pénztárügyfeleken."
author: ashishmsft
manager: AnnBe
ms.date: 10/27/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: d9b080ff46a0fbc73ed4f8fa3f03d71e9d758cc2
ms.openlocfilehash: 4d7e9b3afdae77246a8c30147e81f565bbc0fca5
ms.contentlocale: hu-hu
ms.lasthandoff: 01/17/2018

---
# <a name="configure-machine-learning-powered-product-recommendations"></a><span data-ttu-id="e86fe-103">Gépi tanulási alapú termékajánlások konfigurálása</span><span class="sxs-lookup"><span data-stu-id="e86fe-103">Configure machine learning-powered product recommendations</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="e86fe-104">Ez az eljárás frissíti azokat az adatokat az entitástárban, amelyeket a termékajánlásokért felelős gépi tanulási rendszer használ, majd ezt követően engedélyezi a termékajánlásokat a pénztárügyfeleken.</span><span class="sxs-lookup"><span data-stu-id="e86fe-104">This procedure refreshes the data in the Entity store that is used by the machine learning system that powers product recommendations, and then enables product recommendations on POS clients.</span></span> <span data-ttu-id="e86fe-105">Ez az eljárás az USRT cég adatait használja, mint bemutatóadatokat.</span><span class="sxs-lookup"><span data-stu-id="e86fe-105">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="e86fe-106">Ugrás a Rendszerfelügyelet > Beállítás > Entitástár elemre.</span><span class="sxs-lookup"><span data-stu-id="e86fe-106">Go to System administration > Setup > Entity Store.</span></span>
2. <span data-ttu-id="e86fe-107">Keresse meg és jelölje ki a „RetailSales” rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="e86fe-107">In the list, find and select the record 'RetailSales'.</span></span>
3. <span data-ttu-id="e86fe-108">Kattintson a Frissítés gombra.</span><span class="sxs-lookup"><span data-stu-id="e86fe-108">Click Refresh.</span></span>
4. <span data-ttu-id="e86fe-109">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="e86fe-109">Click OK.</span></span>
5. <span data-ttu-id="e86fe-110">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="e86fe-110">Close the page.</span></span>
6. <span data-ttu-id="e86fe-111">Ugrás a Kiskereskedelem > Központ beállítás > Paraméterek > Kiskereskedelmi paraméterek elemre.</span><span class="sxs-lookup"><span data-stu-id="e86fe-111">Go to Retail and commerce > Headquarters setup > Parameters > Retail parameters.</span></span>
7. <span data-ttu-id="e86fe-112">Kattintson a Gépi tanulás fülre.</span><span class="sxs-lookup"><span data-stu-id="e86fe-112">Click the Machine learning tab.</span></span>
8. <span data-ttu-id="e86fe-113">Válassza az „Igen” lehetőséget a Termékajánlatok engedélyezése mezőben.</span><span class="sxs-lookup"><span data-stu-id="e86fe-113">Select 'Yes' in the Enable product recommendations field.</span></span>
    * <span data-ttu-id="e86fe-114">Ha „Az ajánlatmodellek beolvasása sikertelen volt” üzenet jelenik meg, ez azért történik, mert a közelmúltban frissítette az entitástárat, és előfordulhat, hogy a rendszer még nem végzett az új adatok feldolgozásával.</span><span class="sxs-lookup"><span data-stu-id="e86fe-114">If you receive the message "The recommendation models couldn't be retrieved", it’s because you refreshed the Entity Store very recently and the system may not have finished assimilating the new data.</span></span> <span data-ttu-id="e86fe-115">Várjon 2-3 órát, majd próbálkozzon újra.</span><span class="sxs-lookup"><span data-stu-id="e86fe-115">Wait 2-3 hours and try again.</span></span>  
9. <span data-ttu-id="e86fe-116">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="e86fe-116">Click Save.</span></span>
10. <span data-ttu-id="e86fe-117">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="e86fe-117">Close the page.</span></span>


