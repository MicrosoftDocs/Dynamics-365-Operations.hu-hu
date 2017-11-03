---
title: "A kiskereskedelmi csatornák definiálása és karbantartása"
description: "Ez a cikk a hagyományos üzlethelyiségek beállításának folyamatáról nyújt áttekintést (ezekre a Microsoft Dynamics 365 for Retail rendszer „kiskereskedelmi üzlet”-ként hivatkozik). A kiskereskedelmi üzlet beállítása előtt és után elvégzendő feladatokkal kapcsolatban is itt tájékozódhat."
author: mugunthanm
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailStoreTable, RetailStoreTableListPagePreviewPane
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 16481
ms.assetid: 14496d96-1c72-43ce-a2e7-8467bab4ae46
ms.search.region: Global
ms.search.industry: Retail
ms.author: mumani
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 2a78df20ce5a9ff0aae7b2b3e93d00c46f747f07
ms.contentlocale: hu-hu
ms.lasthandoff: 11/03/2017

---

# <a name="define-and-maintain-retail-channels"></a><span data-ttu-id="a39f4-104">A kiskereskedelmi csatornák definiálása és karbantartása</span><span class="sxs-lookup"><span data-stu-id="a39f4-104">Define and maintain retail channels</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="a39f4-105">Ez a cikk a hagyományos üzlethelyiségek beállításának folyamatáról nyújt áttekintést (ezekre a Microsoft Dynamics 365 for Retail rendszer „kiskereskedelmi üzlet”-ként hivatkozik).</span><span class="sxs-lookup"><span data-stu-id="a39f4-105">This article provides an overview of the process for setting up brick-and-mortar stores, which are referred to as retail stores in Microsoft Dynamics 365 for Retail.</span></span> <span data-ttu-id="a39f4-106">A kiskereskedelmi üzlet beállítása előtt és után elvégzendő feladatokkal kapcsolatban is itt tájékozódhat.</span><span class="sxs-lookup"><span data-stu-id="a39f4-106">It includes information about the tasks that you must complete both before and after you set up a retail store.</span></span>

<span data-ttu-id="a39f4-107">A Dynamics 365 for Retail számos kiskereskedelmi csatornát támogat, például online áruházakat, online piactereket, fizikailag létező üzleteket és hívásközpontokat.</span><span class="sxs-lookup"><span data-stu-id="a39f4-107">Dynamics 365 for Retail supports multiple retail channels, such as online stores, call centers, and brick-and-mortar stores.</span></span> <span data-ttu-id="a39f4-108">A tényleges, "tégla" üzletet kiskereskedelmi áruháznak neveznek.</span><span class="sxs-lookup"><span data-stu-id="a39f4-108">A brick-and-mortar store is called a retail store.</span></span> <span data-ttu-id="a39f4-109">Az üzletek saját fizetési módokkal, árcsoportokkal, (POS) pénztárgépekkel, bevételi és kiadási számlákkal, valamint munkatársakkal rendelkezhetnek.</span><span class="sxs-lookup"><span data-stu-id="a39f4-109">Each retail store can have its own payment methods, price groups, point of sale (POS) registers, income accounts and expense accounts, and staff.</span></span> <span data-ttu-id="a39f4-110">Az üzlethez kapcsolódó összes elemet be kell állítania, létrehozás előtt.</span><span class="sxs-lookup"><span data-stu-id="a39f4-110">You must set up all these elements for a retail store before you create it.</span></span> <span data-ttu-id="a39f4-111">Miután létrehozta a kiskereskedelmi üzletet, rendelje hozzá az üzlet által kezelendő termékeket.</span><span class="sxs-lookup"><span data-stu-id="a39f4-111">After you create the retail store, you assign the products that you want it to carry.</span></span> <span data-ttu-id="a39f4-112">Rendelje hozzá az alkalmazottakat, a jegyzékeket, pénztárgépeket és a fogyasztókat is az üzlethez.</span><span class="sxs-lookup"><span data-stu-id="a39f4-112">You also assign employees, registers, and customers to the store.</span></span> <span data-ttu-id="a39f4-113">Végül helyezze el az új üzletet a szervezeti hierarchiában.</span><span class="sxs-lookup"><span data-stu-id="a39f4-113">Finally, you add the new store to an organization hierarchy.</span></span>

## <a name="setting-up-retail-stores"></a><span data-ttu-id="a39f4-114">Kiskereskedelmi áruházak beállításai</span><span class="sxs-lookup"><span data-stu-id="a39f4-114">Setting up retail stores</span></span>
<span data-ttu-id="a39f4-115">A kiskereskedelmi üzlet a Dynamics 365 for Retail programban való beállítása előtt el kell végeznie néhány előfeltétel feladatot.</span><span class="sxs-lookup"><span data-stu-id="a39f4-115">Before you can set up a retail store in Dynamics 365 for Retail, you must complete some prerequisite tasks.</span></span> <span data-ttu-id="a39f4-116">Ezután létrehozhatja a kiskereskedelmi üzletet, és megadhatja a részleteket.</span><span class="sxs-lookup"><span data-stu-id="a39f4-116">You can then create the retail store and add details.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="a39f4-117">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="a39f4-117">Prerequisites</span></span>

<span data-ttu-id="a39f4-118">Kiskereskedelmi üzlet beállítása előtt el kell végeznie az alábbi feladatokat:</span><span class="sxs-lookup"><span data-stu-id="a39f4-118">You must complete the following tasks before you can set up a retail store:</span></span>

1.  <span data-ttu-id="a39f4-119">Konfigurálja a szervezeti struktúráját, majd állítsa be a szervezeti hierarchiát a kiskereskedelmi szortimenthez, feltöltéshez és jelentéshez.</span><span class="sxs-lookup"><span data-stu-id="a39f4-119">Configure your organization structure, and set up organization hierarchies for retail assortments, replenishment, and reporting.</span></span>
2.  <span data-ttu-id="a39f4-120">Állítson be egy raktárt, amely a kiskereskedelmi üzletet képviseli.</span><span class="sxs-lookup"><span data-stu-id="a39f4-120">Set up a warehouse that represents the retail store.</span></span>
3.  <span data-ttu-id="a39f4-121">Adjon meg számsorozatokat a kiskereskedelmi áruházakhoz, áruházi kivonatokhoz és a kivonati bizonylatokhoz.</span><span class="sxs-lookup"><span data-stu-id="a39f4-121">Set up number sequences for retail stores, store statements, and statement vouchers.</span></span>
4.  <span data-ttu-id="a39f4-122">A kiskereskedelem paramétereinek konfigurálása.</span><span class="sxs-lookup"><span data-stu-id="a39f4-122">Configure parameters for Retail.</span></span>
5.  <span data-ttu-id="a39f4-123">Az üzlet által elfogadott fizetési módok beállítása.</span><span class="sxs-lookup"><span data-stu-id="a39f4-123">Set up the methods of payment that the store accepts.</span></span>
6.  <span data-ttu-id="a39f4-124">Beállíthat fizetési szolgáltatásokat is a kiskereskedelmi (POS) pénztárgépek által kezelendő hitelkártya tranzakciók feldolgozásához.</span><span class="sxs-lookup"><span data-stu-id="a39f4-124">To process credit card transactions at retail POS registers, you can also set up payment services.</span></span>
7.  <span data-ttu-id="a39f4-125">Áfacsoportok beállítása.</span><span class="sxs-lookup"><span data-stu-id="a39f4-125">Set up sales tax groups.</span></span>
8.  <span data-ttu-id="a39f4-126">Kereskedelmi termékek beállítása.</span><span class="sxs-lookup"><span data-stu-id="a39f4-126">Set up retail products.</span></span> <span data-ttu-id="a39f4-127">A feladat részeként állítson be kiskereskedelmi termék hierarchiát, termékváltozatot és termék szortimentet.</span><span class="sxs-lookup"><span data-stu-id="a39f4-127">As part of this task, you also set up retail product hierarchies, product variants, and product assortments.</span></span>
9.  <span data-ttu-id="a39f4-128">Termékárcsoportok beállítása.</span><span class="sxs-lookup"><span data-stu-id="a39f4-128">Set up product price groups.</span></span>
10. <span data-ttu-id="a39f4-129">Kiskereskedelmi termékárképzés beállítása.</span><span class="sxs-lookup"><span data-stu-id="a39f4-129">Set up retail product pricing.</span></span> <span data-ttu-id="a39f4-130">A feladat további részeként állítson be árkorrekciókat, engedményeket és kedvezmények időszakokat.</span><span class="sxs-lookup"><span data-stu-id="a39f4-130">As part of this task, you also set up price adjustments, discounts, and discount periods.</span></span>
11. <span data-ttu-id="a39f4-131">Munkatársak beállításai.</span><span class="sxs-lookup"><span data-stu-id="a39f4-131">Set up staff members.</span></span> <span data-ttu-id="a39f4-132">**Megjegyzés:** Megfelelő engedélyeket kell társítania a dolgozókhoz, hogy bejelentkezhessenek és feladatokat hajthassanak végre a kiskereskedelmi POS pénztár Dynamics 365 for Retail rendszerében.</span><span class="sxs-lookup"><span data-stu-id="a39f4-132">**Note:** You must also assign appropriate permissions to the workers, so that they can sign in and perform tasks by using the Dynamics 365 for Retail for Retail POS system.</span></span>
12. <span data-ttu-id="a39f4-133">Konfigurálja a kiskereskedelmi POS pénztárban az üzlethez hozzárendelendő profilokat.</span><span class="sxs-lookup"><span data-stu-id="a39f4-133">Configure the Retail POS profiles to assign to the store.</span></span> <span data-ttu-id="a39f4-134">Ez a feladat számos egyéb feladatot foglal magában, mint például a pénztárgépek és jegyzékek, offline profilok és bevételezési formátumok megadása és azok paramétereinek beállítása.</span><span class="sxs-lookup"><span data-stu-id="a39f4-134">This task includes many other tasks, such as setting up registers, setting up offline profiles, and setting up receipt formats and profiles.</span></span>

<span data-ttu-id="a39f4-135">Tekintse át az előfeltételekben foglalt valamennyi feladatot, és hajtsa végre közülük azokat, amelyek Önre vonatkoznak.</span><span class="sxs-lookup"><span data-stu-id="a39f4-135">Review all the tasks that are included in the prerequisite, and complete only the tasks that apply to you.</span></span>

### <a name="set-up-a-retail-store"></a><span data-ttu-id="a39f4-136">Kiskereskedelmi áruház beállítása</span><span class="sxs-lookup"><span data-stu-id="a39f4-136">Set up a retail store</span></span>

<span data-ttu-id="a39f4-137">Miután befejezte az előfeltétel feladatait, hajtsa végre ezeket a feladatokat a kiskereskedelmi üzlet adatainak beállításához:</span><span class="sxs-lookup"><span data-stu-id="a39f4-137">After you complete the prerequisite tasks, complete these tasks to set up the details for the retail store:</span></span>

1.  <span data-ttu-id="a39f4-138">Kiskereskedelmi üzlet létrehozása.</span><span class="sxs-lookup"><span data-stu-id="a39f4-138">Create a retail store.</span></span>
2.  <span data-ttu-id="a39f4-139">Áfacsoportok hozzárendelése az üzlethez.</span><span class="sxs-lookup"><span data-stu-id="a39f4-139">Assign a sales tax group to the store.</span></span>
3.  <span data-ttu-id="a39f4-140">Az elfogadott fizetési módok hozzárendelése az üzlethez.</span><span class="sxs-lookup"><span data-stu-id="a39f4-140">Assign the accepted payment methods to the store.</span></span>
4.  <span data-ttu-id="a39f4-141">Termékleírások hozzáadása a kiskereskedelmi üzletekben kínált egyes termékekhez.</span><span class="sxs-lookup"><span data-stu-id="a39f4-141">Add details to the product descriptions for products that you offer in your retail stores.</span></span> <span data-ttu-id="a39f4-142">Megadhat például multimédiás szöveget és képeket.</span><span class="sxs-lookup"><span data-stu-id="a39f4-142">For example, you can add rich text and images.</span></span> <span data-ttu-id="a39f4-143">Ezek a termék részletek különböző helyeken jelennek meg, például a POS pénztárakban vagy a nyomtatott címkéken.</span><span class="sxs-lookup"><span data-stu-id="a39f4-143">These product details appear in various contexts, such as on the POS register or on printed labels.</span></span>
5.  <span data-ttu-id="a39f4-144">Adja hozzá az üzletet egy olyan alapértelmezett szervezeti hierarchiához, ami hozzá van rendelve az alábbi feladatok valamelyikéhez: **Kiskereskedelmi szortiment**, **Kiskereskedelmi feltöltés**, **Kiskereskedelmi jelentés**.</span><span class="sxs-lookup"><span data-stu-id="a39f4-144">Add the store to an the default organization hierarchy that is assigned to a purpose of **Retail assortment**, **Retail replenishment**, or **Retail reporting**.</span></span>

### <a name="after-you-set-up-a-retail-store"></a><span data-ttu-id="a39f4-145">Miután beállította a kiskereskedelmi üzletet</span><span class="sxs-lookup"><span data-stu-id="a39f4-145">After you set up a retail store</span></span>

<span data-ttu-id="a39f4-146">Miután megadta a kiskereskedelmi áruház részletes adatait, hajtsa végre ezeket a feladatokat az új áruház adatainak a kiskereskedelemi POS pénztár rendszerbe történő küldéséhez.</span><span class="sxs-lookup"><span data-stu-id="a39f4-146">After you enter the details for the retail store, complete these tasks to send the new retail store data to Retail POS:</span></span>

1.  <span data-ttu-id="a39f4-147">Állítsa be az üzletben használt POS pénztárgépek paramétereit.</span><span class="sxs-lookup"><span data-stu-id="a39f4-147">Configure the POS registers for the store.</span></span>
2.  <span data-ttu-id="a39f4-148">Szortimentek hozzáadása az online áruházhoz</span><span class="sxs-lookup"><span data-stu-id="a39f4-148">Assign product assortments to the store.</span></span>
3.  <span data-ttu-id="a39f4-149">Szortimentek feldolgozása a kiskereskedelmi üzlet szortimentjének tételes kilistázása, és az üzletben kínált termékek elérhetővé tétele érdekében.</span><span class="sxs-lookup"><span data-stu-id="a39f4-149">Process assortments to generate the list of products that are included in the assortment and to make the products available in the retail store.</span></span>
4.  <span data-ttu-id="a39f4-150">Számsorozatok, hardverprofilok, POS pénztárgép képernyő-elrendezések adatainak tovább küldése a kiskereskedelmi POS pénztár rendszer nyilvántartásába.</span><span class="sxs-lookup"><span data-stu-id="a39f4-150">Send data such as number sequences, hardware profiles, and POS screen layouts to the Retail POS registers.</span></span>
5.  <span data-ttu-id="a39f4-151">Tegye közzé a kiskereskedelmi üzletet az üzlet-adatok kiskereskedelmi POS pénztár rendszerbe való továbbításához.</span><span class="sxs-lookup"><span data-stu-id="a39f4-151">Publish the retail store to send store data to Retail POS.</span></span>
6.  <span data-ttu-id="a39f4-152">Az üzlet-adatok kiskereskedelmi POS pénztár rendszerbe történő küldésére szolgáló munka futtatása.</span><span class="sxs-lookup"><span data-stu-id="a39f4-152">Run the jobs to send the store data to Retail POS.</span></span>

## <a name="organization-hierarchies"></a><span data-ttu-id="a39f4-153">Szervezeti hierarchiák</span><span class="sxs-lookup"><span data-stu-id="a39f4-153">Organization hierarchies</span></span>
<span data-ttu-id="a39f4-154">A Retail alrendszer szervezeti hierarchiákat használ a kiskereskedelmi csatornák strukturált kialakításához.</span><span class="sxs-lookup"><span data-stu-id="a39f4-154">Retail uses organization hierarchies to structure retail channels.</span></span> <span data-ttu-id="a39f4-155">A szervezeti hierarchiák az üzleti rendszer-struktúrát alkotó szervezetek között kapcsolatokat jelölik.</span><span class="sxs-lookup"><span data-stu-id="a39f4-155">Organization hierarchies represent the relationships between the organizations that make up your business.</span></span> <span data-ttu-id="a39f4-156">Amikor egy üzletet konfigurál, azt egy szervezeti hierarchiához is hozzáadhatja.</span><span class="sxs-lookup"><span data-stu-id="a39f4-156">When you set up stores, you can add them to an organization hierarchy.</span></span> <span data-ttu-id="a39f4-157">Az üzletek ezt követően megoszthatják a szortimentekhez, a feltöltéshez és jelentéshez használt adatokat.</span><span class="sxs-lookup"><span data-stu-id="a39f4-157">The stores then share data that is used for assortments, replenishment, and reporting.</span></span>




