---
title: Jogi személyek létrehozása
description: Ez a témakör azt mutatja be, hogyan lehet jogi személyeket létrehozni a Microsoft Dynamics 365 Commerce szolgáltatásban, amelyet a csatornák létrehozása előtt létre kell hozni és be kell állítani.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 28cbcc42505f1dc90c420adc812735841541c8e0
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/01/2020
ms.locfileid: "3002404"
---
# <a name="create-legal-entities"></a><span data-ttu-id="4c877-103">Jogi személyek létrehozása</span><span class="sxs-lookup"><span data-stu-id="4c877-103">Create legal entities</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="4c877-104">Ez a témakör azt mutatja be, hogyan lehet jogi személyeket létrehozni a Microsoft Dynamics 365 Commerce szolgáltatásban, amelyet a csatornák létrehozása előtt létre kell hozni és be kell állítani.</span><span class="sxs-lookup"><span data-stu-id="4c877-104">This topic describes how to create legal entities in Microsoft Dynamics 365 Commerce, which must be created and configured before creating channels.</span></span>

## <a name="overview"></a><span data-ttu-id="4c877-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="4c877-105">Overview</span></span>

<span data-ttu-id="4c877-106">A jogi személy olyan szervezet, amely bejegyzett vagy törvényben szabályozott jogi struktúrával rendelkezik.</span><span class="sxs-lookup"><span data-stu-id="4c877-106">A legal entity is an organization that has a registered or legislated legal structure.</span></span> <span data-ttu-id="4c877-107">A jogi személyek törvényes szerződéseket köthetnek, teljesítményükről pedig tájékoztató beszámolókat kell készíteniük.</span><span class="sxs-lookup"><span data-stu-id="4c877-107">Legal entities can enter into legal contracts and are required to prepare statements that report on their performance.</span></span>

<span data-ttu-id="4c877-108">A vállalat is jogi személy.</span><span class="sxs-lookup"><span data-stu-id="4c877-108">A company is a type of legal entity.</span></span> <span data-ttu-id="4c877-109">Jelenleg a vállalatok az egyetlen típusú jogi személy, amelyet létrehozhat, és minden jogi személyhez tartozik egy vállalati azonosító.</span><span class="sxs-lookup"><span data-stu-id="4c877-109">Currently, companies are the only kind of legal entity that you can create, and every legal entity is associated with a company ID.</span></span> <span data-ttu-id="4c877-110">Erre a társításra azért van szükség, mert a program egyes funkcionális területeinek modelljei vállalat azonosítót vagy *DataAreaId*-t használnak.</span><span class="sxs-lookup"><span data-stu-id="4c877-110">This association exists because some functional areas in the program use a company ID, or *DataAreaId*, in their data models.</span></span> <span data-ttu-id="4c877-111">Ezeken a funkcionális területeken a vállalatokat határként használják az adatbiztonsághoz.</span><span class="sxs-lookup"><span data-stu-id="4c877-111">In these functional areas, companies are used as a boundary for data security.</span></span> <span data-ttu-id="4c877-112">A felhasználók csak annak a vállalatnak a részére férhetnek hozzá adatokhoz, amelyen éppen bejelentkeznek.</span><span class="sxs-lookup"><span data-stu-id="4c877-112">Users can access data only for the company that they are currently logged on to.</span></span> 

<span data-ttu-id="4c877-113">Csatorna létrehozásakor meg kell adnia, hogy melyik jogi személy tartozik a csatornához.</span><span class="sxs-lookup"><span data-stu-id="4c877-113">When creating a channel, you must specify which legal entity that channel belongs to.</span></span>

## <a name="create-a-new-legal-entity"></a><span data-ttu-id="4c877-114">Új jogi személy létrehozása</span><span class="sxs-lookup"><span data-stu-id="4c877-114">Create a new legal entity</span></span>

<span data-ttu-id="4c877-115">Új jogi személy létrehozásához a Dynamics 365 Commerce szolgáltatásban kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="4c877-115">To create a new legal entity in Dynamics 365 Commerce, follow these steps.</span></span>

1. <span data-ttu-id="4c877-116">A navigációs ablakban nyissa meg a **Modulok \> központi telepítése \> jogi személyek** elemet.</span><span class="sxs-lookup"><span data-stu-id="4c877-116">In the navigation pane, go to  **Modules \> Headquarters setup \> Legal entities**.</span></span>
1. <span data-ttu-id="4c877-117">A műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="4c877-117">On the action pane, select **New**.</span></span> <span data-ttu-id="4c877-118">A jobb oldalon megjelenik az **Új jogi személy** ablaktábla.</span><span class="sxs-lookup"><span data-stu-id="4c877-118">The **New legal entity** pane appears on the right.</span></span>
1. <span data-ttu-id="4c877-119">A **Név** mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="4c877-119">In the **Name** field, enter a value.</span></span>
1. <span data-ttu-id="4c877-120">A **Vállalat** mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="4c877-120">In the **Company** field, enter a value.</span></span>
1. <span data-ttu-id="4c877-121">Az **Ország/régió** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="4c877-121">In the **Country/region** field, enter or select a value.</span></span>
1. <span data-ttu-id="4c877-122">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4c877-122">Select **OK**.</span></span> 

   ![Jogi személy létrehozása](media/legal-entities.png)

1. <span data-ttu-id="4c877-124">Az **Általános** szakaszban adja meg a következő általános információkat a jogi személyről:</span><span class="sxs-lookup"><span data-stu-id="4c877-124">In the **General** section, provide the following general information about the legal entity:</span></span> 
   1. <span data-ttu-id="4c877-125">Szükség esetén írja be a keresési nevet.</span><span class="sxs-lookup"><span data-stu-id="4c877-125">Enter a search name, if a search name is required.</span></span> <span data-ttu-id="4c877-126">A keresési név olyan másodlagos név, amelynek használatával elvégezheti a keresést a jogi személyre vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="4c877-126">A search name is an alternate name that can be used to search for this legal entity.</span></span> 
   1. <span data-ttu-id="4c877-127">Adja meg, hogy ez a jogi személy konszolidációs vállalatként használatos-e.</span><span class="sxs-lookup"><span data-stu-id="4c877-127">Select whether this legal entity is being used as a consolidation company.</span></span>
   1. <span data-ttu-id="4c877-128">Adja meg, hogy ez a jogi személy eltávolítási vállalatként használatos-e.</span><span class="sxs-lookup"><span data-stu-id="4c877-128">Select whether this legal entity is being used as an elimination company.</span></span> 
   1. <span data-ttu-id="4c877-129">Jelölje ki az **alapértelmezett nyelvet** az entitáshoz.</span><span class="sxs-lookup"><span data-stu-id="4c877-129">Select the **default language** for the entity.</span></span> 
   1. <span data-ttu-id="4c877-130">Válassza ki az entitás **időzónáját**.</span><span class="sxs-lookup"><span data-stu-id="4c877-130">Select the **time zone** for the entity.</span></span>
1. <span data-ttu-id="4c877-131">A **Címek** szakaszban kattintson a **Szerkesztés** lehetőségre, és adja meg a cím adatait, mint például az utca nevet és a számot, az irányítószámot és a várost.</span><span class="sxs-lookup"><span data-stu-id="4c877-131">In the **Addresses** section, select **Edit** to enter address information, such as the street name and number, postal code, and city.</span></span>
1. <span data-ttu-id="4c877-132">A **Kapcsolattartási adatok** szakaszban adja meg a kommunikációs módszerekkel kapcsolatos adatokat, például a e-mail címeket, az URL-címeket és a telefonszámokat.</span><span class="sxs-lookup"><span data-stu-id="4c877-132">In the **Contact information** section, enter information about methods of communication, such as email addresses, URLs, and telephone numbers.</span></span>
1. <span data-ttu-id="4c877-133">A **Kötelezően előírt jelentéskészítés** szakaszban adja meg a kötelező jelentési célokra használt nyilvántartási számokat.</span><span class="sxs-lookup"><span data-stu-id="4c877-133">In the **Statutory reporting** section, enter the registration numbers that are used for statutory reporting.</span></span>
1. <span data-ttu-id="4c877-134">A **Regisztrációs számok** szakaszban adja meg a jogi személy által igényelt információkat.</span><span class="sxs-lookup"><span data-stu-id="4c877-134">In the **Registration numbers** section, enter any information required by the legal entity.</span></span>
1. <span data-ttu-id="4c877-135">A **Bankszámla adatok** szakaszban adja meg a bankszámlaákat és a regisztrációs azonosítót a jogi személyre vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="4c877-135">In the **Bank account information** section, enter bank accounts and routing numbers for the legal entity.</span></span>
1. <span data-ttu-id="4c877-136">A **Külföldi kereskedelem és logisztika** szakaszban adja meg a szállítási adatokat a jogi személyre vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="4c877-136">In the **Foreign trade and logistics** section, enter shipping information for the legal entity.</span></span>
1. <span data-ttu-id="4c877-137">A **Számsorozat** gyorslapon megtekintheti a jogi személyhez kapcsolódó számsorozatokat.</span><span class="sxs-lookup"><span data-stu-id="4c877-137">In the **Number sequences** section, you can view the number sequences that are associated with the legal entity.</span></span> <span data-ttu-id="4c877-138">Ez a mező üresen marad eredetileg.</span><span class="sxs-lookup"><span data-stu-id="4c877-138">This will be empty to start with.</span></span>
1. <span data-ttu-id="4c877-139">Az **Irányítópult képei** szakaszban tekintse meg vagy módosítsa a jogi személyhez társított emblémát és/vagy irányítópultot.</span><span class="sxs-lookup"><span data-stu-id="4c877-139">In the **Dashboard image** section, view or change the logo and dashboard image associated with the legal entity.</span></span>
1. <span data-ttu-id="4c877-140">Az **Adóregisztráció** szakaszban adja meg az adóhatóságnál tett jelentéshez használt nyilvántartási számokat.</span><span class="sxs-lookup"><span data-stu-id="4c877-140">In the **Tax registration** section, enter the registration numbers that are used to report to tax authorities.</span></span>
1. <span data-ttu-id="4c877-141">Az **Adó - 1099** szakaszban adja meg a 1099-es adatokat a jogi személyre vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="4c877-141">In the **Tax 1099** section, enter 1099 information for the legal entity.</span></span>
1. <span data-ttu-id="4c877-142">Az **Adózási adatok** szakaszban adja meg az adózási adatokat a jogi személyre vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="4c877-142">In the **Tax invormation** section, enter tax information for the legal entity.</span></span>
1. <span data-ttu-id="4c877-143">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4c877-143">Select **Save**.</span></span>

<span data-ttu-id="4c877-144">A következő kép egy példa jogi személy részleteit mutatja.</span><span class="sxs-lookup"><span data-stu-id="4c877-144">The following image shows details of an example legal entity.</span></span>

![Jogi személy általános szakasza](media/legal-entities-general.png)
   
## <a name="additional-resources"></a><span data-ttu-id="4c877-146">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="4c877-146">Additional resources</span></span>

[<span data-ttu-id="4c877-147">Szervezetek és szervezeti hierarchiák áttekintése</span><span class="sxs-lookup"><span data-stu-id="4c877-147">Organizations and organizational hierarchies overview</span></span>](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="4c877-148">Szervezeti hierarchia megtervezése</span><span class="sxs-lookup"><span data-stu-id="4c877-148">Plan your organizational hierarchy</span></span>](../fin-ops-core/fin-ops/organization-administration/plan-organizational-hierarchy.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="4c877-149">Szervezeti hierarchiák</span><span class="sxs-lookup"><span data-stu-id="4c877-149">Organization hierarchies</span></span>](channels-org-hierarchies.md)

[<span data-ttu-id="4c877-150">Csatornák áttekintése</span><span class="sxs-lookup"><span data-stu-id="4c877-150">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="4c877-151">Csatornák beállításának előfeltételei</span><span class="sxs-lookup"><span data-stu-id="4c877-151">Channel setup prerequisites</span></span>](channels-prerequisites.md)
