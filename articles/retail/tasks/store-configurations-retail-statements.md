--- 
title: "Kiskereskedelmi kimutatásokat befolyásoló boltbeállítások konfigurálása"
description: "Ez az eljárás a Kiskereskedelmi kimutatások létrehozásának és feladásának módját befolyásoló Kiskereskedelmi-üzlet konfigurációkat mutatja be."
author: jashanno
manager: AnnBe
ms.date: 11/14/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 5098fb3339403b6f2779dfe3bb7ef5c4ca78051f
ms.openlocfilehash: fdfb233a3e6c3ab17577afb67aa0fdd0d4588020
ms.contentlocale: hu-hu
ms.lasthandoff: 08/09/2018

---
# <a name="configure-store-settings-that-affect-retail-statements"></a><span data-ttu-id="82557-103">Kiskereskedelmi kimutatásokat befolyásoló boltbeállítások konfigurálása</span><span class="sxs-lookup"><span data-stu-id="82557-103">Configure store settings that affect retail statements</span></span>

[!include [task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="82557-104">Ez az eljárás a Kiskereskedelmi kimutatások létrehozásának és feladásának módját befolyásoló Kiskereskedelmi-üzlet konfigurációkat mutatja be.</span><span class="sxs-lookup"><span data-stu-id="82557-104">This procedure walks through configurations for the Retail store that affect how Retail statements get created and posted.</span></span> <span data-ttu-id="82557-105">A Kiskereskedelmi üzletekkel kapcsolatos pénzügyi dimenziókat egy másik eljárás mutatja be.</span><span class="sxs-lookup"><span data-stu-id="82557-105">Financial dimensions on Retail stores are covered in another procedure.</span></span> <span data-ttu-id="82557-106">Ez az eljárás az USRT bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="82557-106">This procedure uses the USRT demo company.</span></span>

1. <span data-ttu-id="82557-107">Nyissa meg a következőt: Kiskereskedelem és kereskedelem > Csatornák > Kiskereskedelmi áruházak > Minden kiskereskedelmi üzlet.</span><span class="sxs-lookup"><span data-stu-id="82557-107">Go to Retail and commerce > Channels > Retail stores > All retail stores.</span></span>
2. <span data-ttu-id="82557-108">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="82557-108">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="82557-109">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="82557-109">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="82557-110">A Kimutatás/zárás szakasz beállításai hatással vannak a kimutatások létrehozására, ellenőrzésére és az üzlet részére történő feladására.</span><span class="sxs-lookup"><span data-stu-id="82557-110">The settings in the Statement/closing section affect the statement creation, validation, and posting for the store.</span></span>  <span data-ttu-id="82557-111">Nyissa meg a Kimutatás/zárás szakaszt.</span><span class="sxs-lookup"><span data-stu-id="82557-111">Open the Statement/closing section.</span></span>  
    * <span data-ttu-id="82557-112">Válassza ki a kimutatássorok csoportosításához használni kívánt módszert.</span><span class="sxs-lookup"><span data-stu-id="82557-112">Select the method you want to use to group the statement lines by.</span></span>  
    * <span data-ttu-id="82557-113">Válassza az "Igen" lehetőséget, ha csak napi egy kimutatást szeretne létrehozni amikor a kimutatás létrehozása kötegelt feladat segítségével hoz létre kimutatásokat.</span><span class="sxs-lookup"><span data-stu-id="82557-113">Select "Yes" if there should only be one statement created per day when creating statements from the statement creation batch job.</span></span>  
    * <span data-ttu-id="82557-114">A fizetőeszköz-elszámolás számítási mező határozza meg, hogy a rendszer összeadja-e a fizetőeszköz-elszámolásokat, vagy az utolsó elemet használja.</span><span class="sxs-lookup"><span data-stu-id="82557-114">The Tender declaration calculation field defines whether tender declarations should be added together or if the last one should be used.</span></span>  
    * <span data-ttu-id="82557-115">Állítsa be, hogy a kerekítési különbségek a főkönyvi számlába kerüljenek feladásra.</span><span class="sxs-lookup"><span data-stu-id="82557-115">Select the ledger account to post rounding differences into.</span></span>  
    * <span data-ttu-id="82557-116">A Kerekítés maximális összege mezőben megadhatja a maximálisan megengedett kerekítési összeget.</span><span class="sxs-lookup"><span data-stu-id="82557-116">In the Maximum rounding difference field, you can enter the maximum rounding difference allowed.</span></span>  
    * <span data-ttu-id="82557-117">A Feladás mezőben megadhatja egy adott kimutatás esetén engedélyezett maximális teljes feladási eltérést.</span><span class="sxs-lookup"><span data-stu-id="82557-117">In the Posting field, you can enter the maximum total posting difference allowed for a statement.</span></span>  
    * <span data-ttu-id="82557-118">A Műszak mezőben megadhatja egy adott műszak esetén engedélyezett maximális teljes eltérést.</span><span class="sxs-lookup"><span data-stu-id="82557-118">In the Shift field, you can enter the maximum total difference within a shift in a statement.</span></span>  
    * <span data-ttu-id="82557-119">A Tranzakció mezőben megadhatja egy adott kimutatás sorban engedélyezett maximális teljes eltérést.</span><span class="sxs-lookup"><span data-stu-id="82557-119">In the Transaction field, you can enter the maximum total difference in a statement line.</span></span>  
    * <span data-ttu-id="82557-120">A Zárási mód mezőben meghatározhatja, hogy a kimutatásban csak lezárt műszak részét képező tranzakciók szerepelhessenek-e, vagy bekerülhessen bármilyen, az adott dátum/idősávba eső tranzakció.</span><span class="sxs-lookup"><span data-stu-id="82557-120">In the Closing method field, you can define whether transactions that will be included in a statement should be part of a closed shift or if they can be any transactions within the defined date/time range.</span></span>  
    * <span data-ttu-id="82557-121">A Munkanap vége mezőben tud megadni megfelelő időpontot, ha azt szeretné, hogy az éjfél utáni tranzakciók az előző napra vonatkozóan kerüljenek feladásra.</span><span class="sxs-lookup"><span data-stu-id="82557-121">In the End of business day field, you can enter a time if transactions that happen after midnight should be posted with the previous day.</span></span>  
    * <span data-ttu-id="82557-122">Válassza az „Igen” lehetőséget, ha azt szeretné, hogy az éjfél utáni tranzakciók az előző napra vonatkozóan kerüljenek feladásra</span><span class="sxs-lookup"><span data-stu-id="82557-122">Select "Yes" if transactions that happen after midnight should be posted as part of the previous day.</span></span>  
    * <span data-ttu-id="82557-123">Válassza az „Igen” lehetőséget, ha szeretné, hogy a rendszer hozzon létre kimutatást minden megjelölt kimutatásmódszer segítségével.</span><span class="sxs-lookup"><span data-stu-id="82557-123">Select "Yes" to get statements created for each statement method defined.</span></span> <span data-ttu-id="82557-124">Ez akkor lehet hasznos, ha a feladás teljesítményét javítani szükséges a magas tranzakciószámmal működő üzletek esetében, így ugyanis a rendszer több kisebb, párhuzamosan feldolgozható kimutatást hoz létre.</span><span class="sxs-lookup"><span data-stu-id="82557-124">This can be useful if the performance of the posting needs to be improved for stores with high transaction volumes since it will create many smaller statements that can be processed in parallel.</span></span>  
    * <span data-ttu-id="82557-125">Az Alapértelmezett vevő mezőben tudja kiválasztani az utcáról betérő vevőkhöz használni kívánt vevőszámlát.</span><span class="sxs-lookup"><span data-stu-id="82557-125">In the Default customer field, you can select the customer account to use for sales to walk-in customers.</span></span>  


