---
title: A kiskereskedelmi csatornák definiálása és karbantartása
description: Ez a témakör a hagyományos üzlethelyiségek beállításának folyamatáról nyújt áttekintést (ezekre a Dynamics 365 Commerce rendszer „üzlet”-ként hivatkozik). Az üzlet beállítása előtt és után elvégzendő feladatokkal kapcsolatban is itt tájékozódhat.
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
ms.custom: 16481
ms.assetid: 14496d96-1c72-43ce-a2e7-8467bab4ae46
ms.search.region: Global
ms.search.industry: Retail
ms.author: mumani
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 51524ad6918d962d70a8a700f135f96e236f7d34
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "5000875"
---
# <a name="define-and-maintain-retail-channels"></a><span data-ttu-id="3154a-104">A kiskereskedelmi csatornák definiálása és karbantartása</span><span class="sxs-lookup"><span data-stu-id="3154a-104">Define and maintain retail channels</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="3154a-105">Ez a témakör a hagyományos üzlethelyiségek beállításának folyamatáról nyújt áttekintést (ezekre a Dynamics 365 Commerce rendszer „üzlet”-ként hivatkozik).</span><span class="sxs-lookup"><span data-stu-id="3154a-105">This topic provides an overview of the process for setting up brick-and-mortar stores, which are referred to as stores in Dynamics 365 Commerce.</span></span> <span data-ttu-id="3154a-106">Az üzlet beállítása előtt és után elvégzendő feladatokkal kapcsolatban is itt tájékozódhat.</span><span class="sxs-lookup"><span data-stu-id="3154a-106">It includes information about the tasks that you must complete both before and after you set up a store.</span></span>

<span data-ttu-id="3154a-107">A Commerce számos kiskereskedelmi csatornát támogat, például online áruházakat, hívásközpontokat, és fizikailag létező üzleteket.</span><span class="sxs-lookup"><span data-stu-id="3154a-107">Commerce supports multiple channels, such as online stores, call centers, and brick-and-mortar stores.</span></span> <span data-ttu-id="3154a-108">A tényleges, fizikailag létező boltot üzletnek nevezzük.</span><span class="sxs-lookup"><span data-stu-id="3154a-108">A brick-and-mortar store is called a store.</span></span> <span data-ttu-id="3154a-109">Az üzletek saját fizetési módokkal, árcsoportokkal, (POS) pénztárgépekkel, bevételi és kiadási számlákkal, valamint munkatársakkal rendelkezhetnek.</span><span class="sxs-lookup"><span data-stu-id="3154a-109">Each store can have its own payment methods, price groups, point of sale (POS) registers, income accounts and expense accounts, and staff.</span></span> <span data-ttu-id="3154a-110">Az üzlethez kapcsolódó összes elemet be kell állítania, létrehozás előtt.</span><span class="sxs-lookup"><span data-stu-id="3154a-110">You must set up all these elements for a store before you create it.</span></span> <span data-ttu-id="3154a-111">Miután létrehozta az üzletet, rendelje hozzá az üzlet által kezelendő termékeket.</span><span class="sxs-lookup"><span data-stu-id="3154a-111">After you create the store, you assign the products that you want it to carry.</span></span> <span data-ttu-id="3154a-112">Rendelje hozzá az alkalmazottakat, a jegyzékeket, pénztárgépeket és a fogyasztókat is az üzlethez.</span><span class="sxs-lookup"><span data-stu-id="3154a-112">You also assign employees, registers, and customers to the store.</span></span> <span data-ttu-id="3154a-113">Végül helyezze el az új üzletet a szervezeti hierarchiában.</span><span class="sxs-lookup"><span data-stu-id="3154a-113">Finally, you add the new store to an organization hierarchy.</span></span>

## <a name="setting-up-stores"></a><span data-ttu-id="3154a-114">Üzletek beállításai</span><span class="sxs-lookup"><span data-stu-id="3154a-114">Setting up stores</span></span>

<span data-ttu-id="3154a-115">Üzlet Commerce rendszerben való beállítása előtt el kell végeznie néhány előfeltételnek számító feladatot.</span><span class="sxs-lookup"><span data-stu-id="3154a-115">Before you can set up a store in Commerce, you must complete some prerequisite tasks.</span></span> <span data-ttu-id="3154a-116">Ezután létrehozhatja az üzletet, és megadhatja a részleteket.</span><span class="sxs-lookup"><span data-stu-id="3154a-116">You can then create the store and add details.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="3154a-117">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="3154a-117">Prerequisites</span></span>

<span data-ttu-id="3154a-118">Üzlet beállítása előtt el kell végeznie az alábbi feladatokat:</span><span class="sxs-lookup"><span data-stu-id="3154a-118">You must complete the following tasks before you can set up a store:</span></span>

1. <span data-ttu-id="3154a-119">Konfigurálja a szervezeti struktúráját, majd állítsa be a szervezeti hierarchiát a kiskereskedelmi szortimenthez, feltöltéshez és jelentéshez.</span><span class="sxs-lookup"><span data-stu-id="3154a-119">Configure your organization structure, and set up organization hierarchies for retail assortments, replenishment, and reporting.</span></span>
2. <span data-ttu-id="3154a-120">Állítson be egy raktárt, amely az üzletet képviseli.</span><span class="sxs-lookup"><span data-stu-id="3154a-120">Set up a warehouse that represents the store.</span></span>
3. <span data-ttu-id="3154a-121">Adjon meg számsorozatokat az üzletekhez, üzleti kivonatokhoz és a kivonati bizonylatokhoz.</span><span class="sxs-lookup"><span data-stu-id="3154a-121">Set up number sequences for stores, store statements, and statement vouchers.</span></span>
4. <span data-ttu-id="3154a-122">Paraméterek konfigurálása a Commerce számára.</span><span class="sxs-lookup"><span data-stu-id="3154a-122">Configure parameters for Commerce.</span></span>
5. <span data-ttu-id="3154a-123">Az üzlet által elfogadott fizetési módok beállítása.</span><span class="sxs-lookup"><span data-stu-id="3154a-123">Set up the methods of payment that the store accepts.</span></span>
6. <span data-ttu-id="3154a-124">Beállíthat fizetési szolgáltatásokat is a (POS) pénztárgépek által kezelendő hitelkártya tranzakciók feldolgozásához.</span><span class="sxs-lookup"><span data-stu-id="3154a-124">To process credit card transactions at POS registers, you can also set up payment services.</span></span>
7. <span data-ttu-id="3154a-125">Áfacsoportok beállítása.</span><span class="sxs-lookup"><span data-stu-id="3154a-125">Set up sales tax groups.</span></span>
8. <span data-ttu-id="3154a-126">Termékek beállítása.</span><span class="sxs-lookup"><span data-stu-id="3154a-126">Set up products.</span></span> <span data-ttu-id="3154a-127">A feladat részeként állítson be termékhierarchiát, termékváltozatot és termék szortimentet.</span><span class="sxs-lookup"><span data-stu-id="3154a-127">As part of this task, you also set up product hierarchies, product variants, and product assortments.</span></span>
9. <span data-ttu-id="3154a-128">Termékárcsoportok beállítása.</span><span class="sxs-lookup"><span data-stu-id="3154a-128">Set up product price groups.</span></span>
10. <span data-ttu-id="3154a-129">Termékárazás beállítása.</span><span class="sxs-lookup"><span data-stu-id="3154a-129">Set up product pricing.</span></span> <span data-ttu-id="3154a-130">A feladat további részeként állítson be árkorrekciókat, engedményeket és kedvezmények időszakokat.</span><span class="sxs-lookup"><span data-stu-id="3154a-130">As part of this task, you also set up price adjustments, discounts, and discount periods.</span></span>
11. <span data-ttu-id="3154a-131">Munkatársak beállításai.</span><span class="sxs-lookup"><span data-stu-id="3154a-131">Set up staff members.</span></span>

    > [!NOTE]
    > <span data-ttu-id="3154a-132">Megfelelő engedélyeket kell társítania a dolgozókhoz, hogy bejelentkezhessenek és feladatokat hajthassanak végre a POS használatával.</span><span class="sxs-lookup"><span data-stu-id="3154a-132">You must also assign appropriate permissions to the workers, so that they can sign in and perform tasks by using the POS system.</span></span>

12. <span data-ttu-id="3154a-133">Konfigurálja az üzlethez hozzárendelendő profilokat.</span><span class="sxs-lookup"><span data-stu-id="3154a-133">Configure the POS profiles to assign to the store.</span></span> <span data-ttu-id="3154a-134">Ez a feladat számos egyéb feladatot foglal magában, mint például a pénztárgépek és jegyzékek, offline profilok és bevételezési formátumok megadása és azok paramétereinek beállítása.</span><span class="sxs-lookup"><span data-stu-id="3154a-134">This task includes many other tasks, such as setting up registers, setting up offline profiles, and setting up receipt formats and profiles.</span></span>

<span data-ttu-id="3154a-135">Tekintse át az előfeltételekben foglalt valamennyi feladatot, és hajtsa végre közülük azokat, amelyek Önre vonatkoznak.</span><span class="sxs-lookup"><span data-stu-id="3154a-135">Review all the tasks that are included in the prerequisites, and complete only the tasks that apply to you.</span></span>

### <a name="set-up-a-store"></a><span data-ttu-id="3154a-136">Egy üzlet beállítása</span><span class="sxs-lookup"><span data-stu-id="3154a-136">Set up a store</span></span>

<span data-ttu-id="3154a-137">Miután befejezte az előfeltétel feladatait, hajtsa végre ezeket a feladatokat az üzlet adatainak beállításához:</span><span class="sxs-lookup"><span data-stu-id="3154a-137">After you complete the prerequisite tasks, complete these tasks to set up the details for the store:</span></span>

1. <span data-ttu-id="3154a-138">Üzlet létrehozása.</span><span class="sxs-lookup"><span data-stu-id="3154a-138">Create a store.</span></span>
2. <span data-ttu-id="3154a-139">Áfacsoportok hozzárendelése az üzlethez.</span><span class="sxs-lookup"><span data-stu-id="3154a-139">Assign a sales tax group to the store.</span></span>
3. <span data-ttu-id="3154a-140">Az elfogadott fizetési módok hozzárendelése az üzlethez.</span><span class="sxs-lookup"><span data-stu-id="3154a-140">Assign the accepted payment methods to the store.</span></span>
4. <span data-ttu-id="3154a-141">Termékleírások hozzáadása az üzletekben kínált egyes termékekhez.</span><span class="sxs-lookup"><span data-stu-id="3154a-141">Add details to the product descriptions for products that you offer in your stores.</span></span> <span data-ttu-id="3154a-142">Megadhat például multimédiás szöveget és képeket.</span><span class="sxs-lookup"><span data-stu-id="3154a-142">For example, you can add rich text and images.</span></span> <span data-ttu-id="3154a-143">Ezek a termék részletek különböző helyeken jelennek meg, például a POS pénztárakban vagy a nyomtatott címkéken.</span><span class="sxs-lookup"><span data-stu-id="3154a-143">These product details appear in various contexts, such as on the POS register or on printed labels.</span></span>
5. <span data-ttu-id="3154a-144">Adja hozzá az üzletet egy olyan alapértelmezett szervezeti hierarchiához, ami hozzá van rendelve az alábbi feladatok valamelyikéhez: **Kiskereskedelmi szortiment**, **Kiskereskedelmi feltöltés**, **Kiskereskedelmi jelentés**.</span><span class="sxs-lookup"><span data-stu-id="3154a-144">Add the store to the default organization hierarchy that is assigned to a purpose of **Retail assortment**, **Retail replenishment**, or **Retail reporting**.</span></span>

### <a name="after-you-set-up-a-store"></a><span data-ttu-id="3154a-145">Miután beállította az üzletet</span><span class="sxs-lookup"><span data-stu-id="3154a-145">After you set up a store</span></span>

<span data-ttu-id="3154a-146">Miután megadta az üzlet részletes adatait, hajtsa végre ezeket a feladatokat az új üzlet adatainak a POS rendszerbe történő küldéséhez:</span><span class="sxs-lookup"><span data-stu-id="3154a-146">After you enter the details for the store, complete these tasks to send the new store data to POS:</span></span>

1. <span data-ttu-id="3154a-147">Állítsa be az üzletben használt POS pénztárgépek paramétereit.</span><span class="sxs-lookup"><span data-stu-id="3154a-147">Configure the POS registers for the store.</span></span>
2. <span data-ttu-id="3154a-148">Szortimentek hozzáadása az online áruházhoz</span><span class="sxs-lookup"><span data-stu-id="3154a-148">Assign product assortments to the store.</span></span>
3. <span data-ttu-id="3154a-149">Szortimentek feldolgozása az üzlet szortimentjének tételes kilistázása, és az üzletben kínált termékek elérhetővé tétele érdekében.</span><span class="sxs-lookup"><span data-stu-id="3154a-149">Process assortments to generate the list of products that are included in the assortment and to make the products available in the store.</span></span>
4. <span data-ttu-id="3154a-150">Számsorozatok, hardverprofilok, POS pénztárgép képernyő-elrendezések adatainak tovább küldése a POS pénztár rendszer nyilvántartásába.</span><span class="sxs-lookup"><span data-stu-id="3154a-150">Send data such as number sequences, hardware profiles, and POS screen layouts to the POS registers.</span></span>
5. <span data-ttu-id="3154a-151">Tegye közzé az üzletet az üzlet-adatok POS rendszerbe való továbbításához.</span><span class="sxs-lookup"><span data-stu-id="3154a-151">Publish the store to send store data to POS.</span></span>
6. <span data-ttu-id="3154a-152">Az üzletadatok POS rendszerbe történő küldésére szolgáló rutin futtatása.</span><span class="sxs-lookup"><span data-stu-id="3154a-152">Run the jobs to send the store data to POS.</span></span>

## <a name="organization-hierarchies"></a><span data-ttu-id="3154a-153">Szervezeti hierarchiák</span><span class="sxs-lookup"><span data-stu-id="3154a-153">Organization hierarchies</span></span>

<span data-ttu-id="3154a-154">A Commerce szervezeti hierarchiákat használ a csatornák strukturált kialakításához.</span><span class="sxs-lookup"><span data-stu-id="3154a-154">Commerce uses organization hierarchies to structure channels.</span></span> <span data-ttu-id="3154a-155">A szervezeti hierarchiák az üzleti rendszer-struktúrát alkotó szervezetek között kapcsolatokat jelölik.</span><span class="sxs-lookup"><span data-stu-id="3154a-155">Organization hierarchies represent the relationships between the organizations that make up your business.</span></span> <span data-ttu-id="3154a-156">Amikor egy üzletet konfigurál, azt egy szervezeti hierarchiához is hozzáadhatja.</span><span class="sxs-lookup"><span data-stu-id="3154a-156">When you set up stores, you can add them to an organization hierarchy.</span></span> <span data-ttu-id="3154a-157">Az üzletek ezt követően megoszthatják a szortimentekhez, a feltöltéshez és jelentéshez használt adatokat.</span><span class="sxs-lookup"><span data-stu-id="3154a-157">The stores then share data that is used for assortments, replenishment, and reporting.</span></span>

> [!NOTE]
> <span data-ttu-id="3154a-158">A Commerce értékesítési funkciójának használatához engedélyezni kell a **Több célhely** konfigurációs kulcsát.</span><span class="sxs-lookup"><span data-stu-id="3154a-158">To use Commerce sales functionality, the configuration key for **Multiple ship-to** must be enabled.</span></span> <span data-ttu-id="3154a-159">Ez a konfigurációs kulcs megtalálható a **Kereskedelem konfiguráció** kulcsai között a **Rendszerfelügyelet**\> **Beállítás** \> **Licenckonfiguráció** alatt.</span><span class="sxs-lookup"><span data-stu-id="3154a-159">This configuration key can be found in the **Trade configuration** keys under **System Administration**\> **Setup** \> **License Configuration**.</span></span> <span data-ttu-id="3154a-160">Ez az értékesítésirendelés-sor szintjén konfigurált kézbesítési cím alapján végrehajtott különböző érvényesítések miatt szükséges.</span><span class="sxs-lookup"><span data-stu-id="3154a-160">This is required due to various validations based on the delivery address configured at the sales order line level.</span></span>

