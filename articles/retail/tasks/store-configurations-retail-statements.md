--- 
title: " Konfigurációk tárolása kiskereskedelmi kimutatásokhoz"
description: "Ez az eljárás a Kiskereskedelmi kimutatások létrehozásának és feladásának módját befolyásoló Kiskereskedelmi-üzlet konfigurációkat mutatja be."
author: jashanno
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: cac676c9c6ebb6769fe7e30ac08a2c8334befc24
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="store-configurations-for-retail-statements"></a><span data-ttu-id="fe2cd-103"> Konfigurációk tárolása kiskereskedelmi kimutatásokhoz</span><span class="sxs-lookup"><span data-stu-id="fe2cd-103">Store configurations for Retail statements</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="fe2cd-104">Ez az eljárás a Kiskereskedelmi kimutatások létrehozásának és feladásának módját befolyásoló Kiskereskedelmi-üzlet konfigurációkat mutatja be.</span><span class="sxs-lookup"><span data-stu-id="fe2cd-104">This procedure walks through configurations for the Retail store that affect how Retail statements get created and posted.</span></span> <span data-ttu-id="fe2cd-105">A Kiskereskedelmi üzletekkel kapcsolatos pénzügyi dimenziókat egy másik eljárás mutatja be.</span><span class="sxs-lookup"><span data-stu-id="fe2cd-105">Financial dimensions on Retail stores are covered in another procedure.</span></span> <span data-ttu-id="fe2cd-106">Ez az eljárás az USRT bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="fe2cd-106">This procedure uses the USRT demo company.</span></span>

1. <span data-ttu-id="fe2cd-107">Nyissa meg a következőt: Kiskereskedelem és kereskedelem > Csatornák > Kiskereskedelmi áruházak > Minden kiskereskedelmi üzlet.</span><span class="sxs-lookup"><span data-stu-id="fe2cd-107">Go to Retail and commerce > Channels > Retail stores > All retail stores.</span></span>
2. <span data-ttu-id="fe2cd-108">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="fe2cd-108">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="fe2cd-109">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="fe2cd-109">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="fe2cd-110">A Kimutatás/zárás szakasz beállításai hatással vannak a kimutatások létrehozására, ellenőrzésére és az üzlet részére történő feladására.</span><span class="sxs-lookup"><span data-stu-id="fe2cd-110">The settings in the Statement/closing section affect the statement creation, validation, and posting for the store.</span></span>  <span data-ttu-id="fe2cd-111">Nyissa meg a Kimutatás/zárás szakaszt.</span><span class="sxs-lookup"><span data-stu-id="fe2cd-111">Open the Statement/closing section.</span></span>  
    * <span data-ttu-id="fe2cd-112">Válassza ki a kimutatássorok csoportosításához használni kívánt módszert.</span><span class="sxs-lookup"><span data-stu-id="fe2cd-112">Select the method you want to use to to group the statement lines by.</span></span>  
    * <span data-ttu-id="fe2cd-113">Válassza az "Igen" lehetőséget, ha csak napi egy kimutatást szeretne létrehozni amikor a kimutatás létrehozása kötegelt feladat segítségével hoz létre kimutatásokat.</span><span class="sxs-lookup"><span data-stu-id="fe2cd-113">Select "Yes" if there should only be one statement created per day when creating statements from the statement creation batch job.</span></span>  
    * <span data-ttu-id="fe2cd-114">A fizetőeszköz-elszámolás számítási mező határozza meg, hogy a rendszer összeadja-e a fizetőeszköz-elszámolásokat, vagy az utolsó elemet használja.</span><span class="sxs-lookup"><span data-stu-id="fe2cd-114">The Tender declaration calculation field defines whether tender declarations should be added together or if the last one should be used.</span></span>  
    * <span data-ttu-id="fe2cd-115">Állítsa be, hogy a kerekítési különbségek a főkönyvi számlába kerüljenek feladásra.</span><span class="sxs-lookup"><span data-stu-id="fe2cd-115">Select the ledger account to post rounding differences into.</span></span>  
    * <span data-ttu-id="fe2cd-116">A Kerekítés maximális összege mezőben megadhatja a maximálisan megengedett kerekítési összeget.</span><span class="sxs-lookup"><span data-stu-id="fe2cd-116">In the Maximum rounding difference field, you can enter the maximum rounding difference allowed.</span></span>  
    * <span data-ttu-id="fe2cd-117">A Feladás mezőben megadhatja egy adott kimutatás esetén engedélyezett maximális teljes feladási eltérést.</span><span class="sxs-lookup"><span data-stu-id="fe2cd-117">In the Posting field, you can enter the maximum total posting difference allowed for a statement.</span></span>  
    * <span data-ttu-id="fe2cd-118">A Műszak mezőben megadhatja egy adott műszak esetén engedélyezett maximális teljes eltérést.</span><span class="sxs-lookup"><span data-stu-id="fe2cd-118">In the Shift field, you can enter the maximum total difference within a shift in a statement.</span></span>  
    * <span data-ttu-id="fe2cd-119">A Tranzakció mezőben megadhatja egy adott kimutatás sorban engedélyezett maximális teljes eltérést.</span><span class="sxs-lookup"><span data-stu-id="fe2cd-119">In the Transaction field, you can enter the maximum total difference in a statement line.</span></span>  
    * <span data-ttu-id="fe2cd-120">A Zárási mód mezőben meghatározhatja, hogy a kimutatásban csak lezárt műszak részét képező tranzakciók szerepelhessenek-e, vagy bekerülhessen bármilyen, az adott dátum/idősávba eső tranzakció.</span><span class="sxs-lookup"><span data-stu-id="fe2cd-120">In the Closing method field, you can define whether transactions that will be included in a statement should be part of a closed shift or if they can be any transactions within the defined date/time range.</span></span>  
    * <span data-ttu-id="fe2cd-121">A Munkanap vége mezőben tud megadni megfelelő időpontot, ha azt szeretné, hogy az éjfél utáni tranzakciók az előző napra vonatkozóan kerüljenek feladásra.</span><span class="sxs-lookup"><span data-stu-id="fe2cd-121">In the End of business day field, you can enter a time if transactions that happen after midnight should be posted with the previous day.</span></span>  
    * <span data-ttu-id="fe2cd-122">Válassza az „Igen” lehetőséget, ha azt szeretné, hogy az éjfél utáni tranzakciók az előző napra vonatkozóan kerüljenek feladásra</span><span class="sxs-lookup"><span data-stu-id="fe2cd-122">Select "Yes" if transactions that happen after midnight should be posted as part of the previous day.</span></span>  
    * <span data-ttu-id="fe2cd-123">Válassza az „Igen” lehetőséget, ha szeretné, hogy a rendszer hozzon létre kimutatást minden megjelölt kimutatásmódszer segítségével.</span><span class="sxs-lookup"><span data-stu-id="fe2cd-123">Select "Yes" to get statements created for each statement method defined.</span></span> <span data-ttu-id="fe2cd-124">Ez akkor lehet hasznos, ha a feladás teljesítményét javítani szükséges a magas tranzakciószámmal működő üzletek esetében, így ugyanis a rendszer több kisebb, párhuzamosan feldolgozható kimutatást hoz létre.</span><span class="sxs-lookup"><span data-stu-id="fe2cd-124">This can be useful if the performance of the posting needs to be improved for stores with high transaction volumes since it will create many smaller statements that can be processed in parallel.</span></span>  
    * <span data-ttu-id="fe2cd-125">Az Alapértelmezett vevő mezőben tudja kiválasztani az utcáról betérő vevőkhöz használni kívánt vevőszámlát.</span><span class="sxs-lookup"><span data-stu-id="fe2cd-125">In the Default customer field, you can select the customer account to use for sales to walk-in customers.</span></span>  

