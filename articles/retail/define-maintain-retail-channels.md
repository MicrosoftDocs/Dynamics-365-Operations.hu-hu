---
title: A kiskereskedelmi csatornák definiálása és karbantartása
description: Ez a témakör a hagyományos üzlethelyiségek beállításának folyamatáról nyújt áttekintést (ezekre a Dynamics 365 Retail rendszer „kiskereskedelmi üzlet”-ként hivatkozik). A kiskereskedelmi üzlet beállítása előtt és után elvégzendő feladatokkal kapcsolatban is itt tájékozódhat.
author: mugunthanm
manager: AnnBe
ms.date: 01/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
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
ms.openlocfilehash: 45d0386d215da15103a417502debb245c91f6309
ms.sourcegitcommit: 4d77d06a07ec9e7a3fcbd508afdffaa406fd3dd8
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/06/2020
ms.locfileid: "2934608"
---
# <a name="define-and-maintain-retail-channels"></a><span data-ttu-id="e0c47-104">A kiskereskedelmi csatornák definiálása és karbantartása</span><span class="sxs-lookup"><span data-stu-id="e0c47-104">Define and maintain retail channels</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="e0c47-105">Ez a témakör a hagyományos üzlethelyiségek beállításának folyamatáról nyújt áttekintést (ezekre a Dynamics 365 Retail rendszer „kiskereskedelmi üzlet”-ként hivatkozik).</span><span class="sxs-lookup"><span data-stu-id="e0c47-105">This topic provides an overview of the process for setting up brick-and-mortar stores, which are referred to as retail stores in Dynamics 365 Retail.</span></span> <span data-ttu-id="e0c47-106">A kiskereskedelmi üzlet beállítása előtt és után elvégzendő feladatokkal kapcsolatban is itt tájékozódhat.</span><span class="sxs-lookup"><span data-stu-id="e0c47-106">It includes information about the tasks that you must complete both before and after you set up a retail store.</span></span>

<span data-ttu-id="e0c47-107">A Retail számos kiskereskedelmi csatornát támogat, például online áruházakat, hívásközpontokat és fizikailag létező üzleteket.</span><span class="sxs-lookup"><span data-stu-id="e0c47-107">Retail supports multiple retail channels, such as online stores, call centers, and brick-and-mortar stores.</span></span> <span data-ttu-id="e0c47-108">A tényleges, "tégla" üzletet kiskereskedelmi áruháznak neveznek.</span><span class="sxs-lookup"><span data-stu-id="e0c47-108">A brick-and-mortar store is called a retail store.</span></span> <span data-ttu-id="e0c47-109">Az üzletek saját fizetési módokkal, árcsoportokkal, (POS) pénztárgépekkel, bevételi és kiadási számlákkal, valamint munkatársakkal rendelkezhetnek.</span><span class="sxs-lookup"><span data-stu-id="e0c47-109">Each retail store can have its own payment methods, price groups, point of sale (POS) registers, income accounts and expense accounts, and staff.</span></span> <span data-ttu-id="e0c47-110">Az üzlethez kapcsolódó összes elemet be kell állítania, létrehozás előtt.</span><span class="sxs-lookup"><span data-stu-id="e0c47-110">You must set up all these elements for a retail store before you create it.</span></span> <span data-ttu-id="e0c47-111">Miután létrehozta a kiskereskedelmi üzletet, rendelje hozzá az üzlet által kezelendő termékeket.</span><span class="sxs-lookup"><span data-stu-id="e0c47-111">After you create the retail store, you assign the products that you want it to carry.</span></span> <span data-ttu-id="e0c47-112">Rendelje hozzá az alkalmazottakat, a jegyzékeket, pénztárgépeket és a fogyasztókat is az üzlethez.</span><span class="sxs-lookup"><span data-stu-id="e0c47-112">You also assign employees, registers, and customers to the store.</span></span> <span data-ttu-id="e0c47-113">Végül helyezze el az új üzletet a szervezeti hierarchiában.</span><span class="sxs-lookup"><span data-stu-id="e0c47-113">Finally, you add the new store to an organization hierarchy.</span></span>

## <a name="setting-up-retail-stores"></a><span data-ttu-id="e0c47-114">Kiskereskedelmi áruházak beállításai</span><span class="sxs-lookup"><span data-stu-id="e0c47-114">Setting up retail stores</span></span>

<span data-ttu-id="e0c47-115">Kiskereskedelmi üzlet a Retail rendszerben való beállítása előtt el kell végeznie néhány előfeltételnek számító feladatot.</span><span class="sxs-lookup"><span data-stu-id="e0c47-115">Before you can set up a retail store in Retail, you must complete some prerequisite tasks.</span></span> <span data-ttu-id="e0c47-116">Ezután létrehozhatja a kiskereskedelmi üzletet, és megadhatja a részleteket.</span><span class="sxs-lookup"><span data-stu-id="e0c47-116">You can then create the retail store and add details.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="e0c47-117">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="e0c47-117">Prerequisites</span></span>

<span data-ttu-id="e0c47-118">Kiskereskedelmi üzlet beállítása előtt el kell végeznie az alábbi feladatokat:</span><span class="sxs-lookup"><span data-stu-id="e0c47-118">You must complete the following tasks before you can set up a retail store:</span></span>

1. <span data-ttu-id="e0c47-119">Konfigurálja a szervezeti struktúráját, majd állítsa be a szervezeti hierarchiát a kiskereskedelmi szortimenthez, feltöltéshez és jelentéshez.</span><span class="sxs-lookup"><span data-stu-id="e0c47-119">Configure your organization structure, and set up organization hierarchies for retail assortments, replenishment, and reporting.</span></span>
2. <span data-ttu-id="e0c47-120">Állítson be egy raktárt, amely a kiskereskedelmi üzletet képviseli.</span><span class="sxs-lookup"><span data-stu-id="e0c47-120">Set up a warehouse that represents the retail store.</span></span>
3. <span data-ttu-id="e0c47-121">Adjon meg számsorozatokat a kiskereskedelmi áruházakhoz, áruházi kivonatokhoz és a kivonati bizonylatokhoz.</span><span class="sxs-lookup"><span data-stu-id="e0c47-121">Set up number sequences for retail stores, store statements, and statement vouchers.</span></span>
4. <span data-ttu-id="e0c47-122">A kiskereskedelem paramétereinek konfigurálása.</span><span class="sxs-lookup"><span data-stu-id="e0c47-122">Configure parameters for Retail.</span></span>
5. <span data-ttu-id="e0c47-123">Az üzlet által elfogadott fizetési módok beállítása.</span><span class="sxs-lookup"><span data-stu-id="e0c47-123">Set up the methods of payment that the store accepts.</span></span>
6. <span data-ttu-id="e0c47-124">Beállíthat fizetési szolgáltatásokat is a kiskereskedelmi (POS) pénztárgépek által kezelendő hitelkártya tranzakciók feldolgozásához.</span><span class="sxs-lookup"><span data-stu-id="e0c47-124">To process credit card transactions at retail POS registers, you can also set up payment services.</span></span>
7. <span data-ttu-id="e0c47-125">Áfacsoportok beállítása.</span><span class="sxs-lookup"><span data-stu-id="e0c47-125">Set up sales tax groups.</span></span>
8. <span data-ttu-id="e0c47-126">Kereskedelmi termékek beállítása.</span><span class="sxs-lookup"><span data-stu-id="e0c47-126">Set up retail products.</span></span> <span data-ttu-id="e0c47-127">A feladat részeként állítson be kiskereskedelmi termék hierarchiát, termékváltozatot és termék szortimentet.</span><span class="sxs-lookup"><span data-stu-id="e0c47-127">As part of this task, you also set up retail product hierarchies, product variants, and product assortments.</span></span>
9. <span data-ttu-id="e0c47-128">Termékárcsoportok beállítása.</span><span class="sxs-lookup"><span data-stu-id="e0c47-128">Set up product price groups.</span></span>
10. <span data-ttu-id="e0c47-129">Kiskereskedelmi termékárképzés beállítása.</span><span class="sxs-lookup"><span data-stu-id="e0c47-129">Set up retail product pricing.</span></span> <span data-ttu-id="e0c47-130">A feladat további részeként állítson be árkorrekciókat, engedményeket és kedvezmények időszakokat.</span><span class="sxs-lookup"><span data-stu-id="e0c47-130">As part of this task, you also set up price adjustments, discounts, and discount periods.</span></span>
11. <span data-ttu-id="e0c47-131">Munkatársak beállításai.</span><span class="sxs-lookup"><span data-stu-id="e0c47-131">Set up staff members.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e0c47-132">Megfelelő engedélyeket kell társítania a dolgozókhoz, hogy bejelentkezhessenek és feladatokat hajthassanak végre a Retail POS használatával.</span><span class="sxs-lookup"><span data-stu-id="e0c47-132">You must also assign appropriate permissions to the workers, so that they can sign in and perform tasks by using the Retail POS system.</span></span>

12. <span data-ttu-id="e0c47-133">Konfigurálja a kiskereskedelmi POS pénztárban az üzlethez hozzárendelendő profilokat.</span><span class="sxs-lookup"><span data-stu-id="e0c47-133">Configure the Retail POS profiles to assign to the store.</span></span> <span data-ttu-id="e0c47-134">Ez a feladat számos egyéb feladatot foglal magában, mint például a pénztárgépek és jegyzékek, offline profilok és bevételezési formátumok megadása és azok paramétereinek beállítása.</span><span class="sxs-lookup"><span data-stu-id="e0c47-134">This task includes many other tasks, such as setting up registers, setting up offline profiles, and setting up receipt formats and profiles.</span></span>

<span data-ttu-id="e0c47-135">Tekintse át az előfeltételekben foglalt valamennyi feladatot, és hajtsa végre közülük azokat, amelyek Önre vonatkoznak.</span><span class="sxs-lookup"><span data-stu-id="e0c47-135">Review all the tasks that are included in the prerequisite, and complete only the tasks that apply to you.</span></span>

### <a name="set-up-a-retail-store"></a><span data-ttu-id="e0c47-136">Kiskereskedelmi áruház beállítása</span><span class="sxs-lookup"><span data-stu-id="e0c47-136">Set up a retail store</span></span>

<span data-ttu-id="e0c47-137">Miután befejezte az előfeltétel feladatait, hajtsa végre ezeket a feladatokat a kiskereskedelmi üzlet adatainak beállításához:</span><span class="sxs-lookup"><span data-stu-id="e0c47-137">After you complete the prerequisite tasks, complete these tasks to set up the details for the retail store:</span></span>

1. <span data-ttu-id="e0c47-138">Kiskereskedelmi üzlet létrehozása.</span><span class="sxs-lookup"><span data-stu-id="e0c47-138">Create a retail store.</span></span>
2. <span data-ttu-id="e0c47-139">Áfacsoportok hozzárendelése az üzlethez.</span><span class="sxs-lookup"><span data-stu-id="e0c47-139">Assign a sales tax group to the store.</span></span>
3. <span data-ttu-id="e0c47-140">Az elfogadott fizetési módok hozzárendelése az üzlethez.</span><span class="sxs-lookup"><span data-stu-id="e0c47-140">Assign the accepted payment methods to the store.</span></span>
4. <span data-ttu-id="e0c47-141">Termékleírások hozzáadása a kiskereskedelmi üzletekben kínált egyes termékekhez.</span><span class="sxs-lookup"><span data-stu-id="e0c47-141">Add details to the product descriptions for products that you offer in your retail stores.</span></span> <span data-ttu-id="e0c47-142">Megadhat például multimédiás szöveget és képeket.</span><span class="sxs-lookup"><span data-stu-id="e0c47-142">For example, you can add rich text and images.</span></span> <span data-ttu-id="e0c47-143">Ezek a termék részletek különböző helyeken jelennek meg, például a POS pénztárakban vagy a nyomtatott címkéken.</span><span class="sxs-lookup"><span data-stu-id="e0c47-143">These product details appear in various contexts, such as on the POS register or on printed labels.</span></span>
5. <span data-ttu-id="e0c47-144">Adja hozzá az üzletet egy olyan alapértelmezett szervezeti hierarchiához, ami hozzá van rendelve az alábbi feladatok valamelyikéhez: **Kiskereskedelmi szortiment**, **Kiskereskedelmi feltöltés**, **Kiskereskedelmi jelentés**.</span><span class="sxs-lookup"><span data-stu-id="e0c47-144">Add the store to the default organization hierarchy that is assigned to a purpose of **Retail assortment**, **Retail replenishment**, or **Retail reporting**.</span></span>

### <a name="after-you-set-up-a-retail-store"></a><span data-ttu-id="e0c47-145">Miután beállította a kiskereskedelmi üzletet</span><span class="sxs-lookup"><span data-stu-id="e0c47-145">After you set up a retail store</span></span>

<span data-ttu-id="e0c47-146">Miután megadta a kiskereskedelmi áruház részletes adatait, hajtsa végre ezeket a feladatokat az új áruház adatainak a kiskereskedelemi POS pénztár rendszerbe történő küldéséhez.</span><span class="sxs-lookup"><span data-stu-id="e0c47-146">After you enter the details for the retail store, complete these tasks to send the new retail store data to Retail POS:</span></span>

1. <span data-ttu-id="e0c47-147">Állítsa be az üzletben használt POS pénztárgépek paramétereit.</span><span class="sxs-lookup"><span data-stu-id="e0c47-147">Configure the POS registers for the store.</span></span>
2. <span data-ttu-id="e0c47-148">Szortimentek hozzáadása az online áruházhoz</span><span class="sxs-lookup"><span data-stu-id="e0c47-148">Assign product assortments to the store.</span></span>
3. <span data-ttu-id="e0c47-149">Szortimentek feldolgozása a kiskereskedelmi üzlet szortimentjének tételes kilistázása, és az üzletben kínált termékek elérhetővé tétele érdekében.</span><span class="sxs-lookup"><span data-stu-id="e0c47-149">Process assortments to generate the list of products that are included in the assortment and to make the products available in the retail store.</span></span>
4. <span data-ttu-id="e0c47-150">Számsorozatok, hardverprofilok, POS pénztárgép képernyő-elrendezések adatainak tovább küldése a kiskereskedelmi POS pénztár rendszer nyilvántartásába.</span><span class="sxs-lookup"><span data-stu-id="e0c47-150">Send data such as number sequences, hardware profiles, and POS screen layouts to the Retail POS registers.</span></span>
5. <span data-ttu-id="e0c47-151">Tegye közzé a kiskereskedelmi üzletet az üzlet-adatok kiskereskedelmi POS pénztár rendszerbe való továbbításához.</span><span class="sxs-lookup"><span data-stu-id="e0c47-151">Publish the retail store to send store data to Retail POS.</span></span>
6. <span data-ttu-id="e0c47-152">Az üzlet-adatok kiskereskedelmi POS pénztár rendszerbe történő küldésére szolgáló munka futtatása.</span><span class="sxs-lookup"><span data-stu-id="e0c47-152">Run the jobs to send the store data to Retail POS.</span></span>

## <a name="organization-hierarchies"></a><span data-ttu-id="e0c47-153">Szervezeti hierarchiák</span><span class="sxs-lookup"><span data-stu-id="e0c47-153">Organization hierarchies</span></span>

<span data-ttu-id="e0c47-154">A Retail alrendszer szervezeti hierarchiákat használ a kiskereskedelmi csatornák strukturált kialakításához.</span><span class="sxs-lookup"><span data-stu-id="e0c47-154">Retail uses organization hierarchies to structure retail channels.</span></span> <span data-ttu-id="e0c47-155">A szervezeti hierarchiák az üzleti rendszer-struktúrát alkotó szervezetek között kapcsolatokat jelölik.</span><span class="sxs-lookup"><span data-stu-id="e0c47-155">Organization hierarchies represent the relationships between the organizations that make up your business.</span></span> <span data-ttu-id="e0c47-156">Amikor egy üzletet konfigurál, azt egy szervezeti hierarchiához is hozzáadhatja.</span><span class="sxs-lookup"><span data-stu-id="e0c47-156">When you set up stores, you can add them to an organization hierarchy.</span></span> <span data-ttu-id="e0c47-157">Az üzletek ezt követően megoszthatják a szortimentekhez, a feltöltéshez és jelentéshez használt adatokat.</span><span class="sxs-lookup"><span data-stu-id="e0c47-157">The stores then share data that is used for assortments, replenishment, and reporting.</span></span>

> [!NOTE]
> <span data-ttu-id="e0c47-158">A Retail értékesítési funkciójának használatához engedélyezni kell a **Több célhely** konfigurációs kulcsát.</span><span class="sxs-lookup"><span data-stu-id="e0c47-158">To use Retail sales functionality, the configuration key for **Multiple ship-to** must be enabled.</span></span> <span data-ttu-id="e0c47-159">Ez a konfigurációs kulcs megtalálható a **Kereskedelem konfiguráció** kulcsai között a **Rendszerfelügyelet**\> **Beállítás** \> **Licenckonfiguráció** alatt.</span><span class="sxs-lookup"><span data-stu-id="e0c47-159">This configuration key can be found in the **Trade configuration** keys under **System Administration**\> **Setup** \> **License Configuration**.</span></span> <span data-ttu-id="e0c47-160">Ez a Retail funkciók miatt szükséges, amelyek az értékesítésirendelés-sor szintjén konfigurált kézbesítési cím alapján különböző érvényesítéseket hajtanak végre.</span><span class="sxs-lookup"><span data-stu-id="e0c47-160">This is required due to Retail functionality that performs various validations based on the delivery address configured at the sales order line level.</span></span>
