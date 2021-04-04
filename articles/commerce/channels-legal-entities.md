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
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 016b67631a53139d12d65dfaf594f49b030326b1
ms.sourcegitcommit: c88b54ba13a4dfe39b844ffaced4dc435560c47d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/19/2021
ms.locfileid: "5478212"
---
# <a name="create-legal-entities"></a><span data-ttu-id="43a04-103">Jogi személyek létrehozása</span><span class="sxs-lookup"><span data-stu-id="43a04-103">Create legal entities</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="43a04-104">Ez a témakör azt mutatja be, hogyan lehet jogi személyeket létrehozni a Microsoft Dynamics 365 Commerce szolgáltatásban, amelyet a csatornák létrehozása előtt létre kell hozni és be kell állítani.</span><span class="sxs-lookup"><span data-stu-id="43a04-104">This topic describes how to create legal entities in Microsoft Dynamics 365 Commerce, which must be created and configured before creating channels.</span></span>

<span data-ttu-id="43a04-105">A jogi személy olyan szervezet, amely bejegyzett vagy törvényben szabályozott jogi struktúrával rendelkezik.</span><span class="sxs-lookup"><span data-stu-id="43a04-105">A legal entity is an organization that has a registered or legislated legal structure.</span></span> <span data-ttu-id="43a04-106">A jogi személyek törvényes szerződéseket köthetnek, teljesítményükről pedig tájékoztató beszámolókat kell készíteniük.</span><span class="sxs-lookup"><span data-stu-id="43a04-106">Legal entities can enter into legal contracts and are required to prepare statements that report on their performance.</span></span>

<span data-ttu-id="43a04-107">A vállalat is jogi személy.</span><span class="sxs-lookup"><span data-stu-id="43a04-107">A company is a type of legal entity.</span></span> <span data-ttu-id="43a04-108">Jelenleg a vállalatok az egyetlen típusú jogi személy, amelyet létrehozhat, és minden jogi személyhez tartozik egy vállalati azonosító.</span><span class="sxs-lookup"><span data-stu-id="43a04-108">Currently, companies are the only kind of legal entity that you can create, and every legal entity is associated with a company ID.</span></span> <span data-ttu-id="43a04-109">Erre a társításra azért van szükség, mert a program egyes funkcionális területeinek modelljei vállalat azonosítót vagy *DataAreaId*-t használnak.</span><span class="sxs-lookup"><span data-stu-id="43a04-109">This association exists because some functional areas in the program use a company ID, or *DataAreaId*, in their data models.</span></span> <span data-ttu-id="43a04-110">Ezeken a funkcionális területeken a vállalatokat határként használják az adatbiztonsághoz.</span><span class="sxs-lookup"><span data-stu-id="43a04-110">In these functional areas, companies are used as a boundary for data security.</span></span> <span data-ttu-id="43a04-111">A felhasználók csak annak a vállalatnak a részére férhetnek hozzá adatokhoz, amelyen éppen bejelentkeznek.</span><span class="sxs-lookup"><span data-stu-id="43a04-111">Users can access data only for the company that they are currently logged on to.</span></span> 

<span data-ttu-id="43a04-112">Csatorna létrehozásakor meg kell adnia, hogy melyik jogi személy tartozik a csatornához.</span><span class="sxs-lookup"><span data-stu-id="43a04-112">When creating a channel, you must specify which legal entity that channel belongs to.</span></span>

## <a name="create-a-new-legal-entity"></a><span data-ttu-id="43a04-113">Új jogi személy létrehozása</span><span class="sxs-lookup"><span data-stu-id="43a04-113">Create a new legal entity</span></span>

<span data-ttu-id="43a04-114">Új jogi személy létrehozásához a Dynamics 365 Commerce szolgáltatásban kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="43a04-114">To create a new legal entity in Dynamics 365 Commerce, follow these steps.</span></span>

1. <span data-ttu-id="43a04-115">A navigációs ablakban nyissa meg a **Modulok \> központi telepítése \> jogi személyek** elemet.</span><span class="sxs-lookup"><span data-stu-id="43a04-115">In the navigation pane, go to  **Modules \> Headquarters setup \> Legal entities**.</span></span>
1. <span data-ttu-id="43a04-116">A műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="43a04-116">On the action pane, select **New**.</span></span> <span data-ttu-id="43a04-117">A jobb oldalon megjelenik az **Új jogi személy** ablaktábla.</span><span class="sxs-lookup"><span data-stu-id="43a04-117">The **New legal entity** pane appears on the right.</span></span>
1. <span data-ttu-id="43a04-118">A **Név** mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="43a04-118">In the **Name** field, enter a value.</span></span>
1. <span data-ttu-id="43a04-119">A **Vállalat** mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="43a04-119">In the **Company** field, enter a value.</span></span>
1. <span data-ttu-id="43a04-120">Az **Ország/régió** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="43a04-120">In the **Country/region** field, enter or select a value.</span></span>
1. <span data-ttu-id="43a04-121">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="43a04-121">Select **OK**.</span></span> 

   ![Jogi személy létrehozása](media/legal-entities.png)

1. <span data-ttu-id="43a04-123">Az **Általános** szakaszban adja meg a következő általános információkat a jogi személyről:</span><span class="sxs-lookup"><span data-stu-id="43a04-123">In the **General** section, provide the following general information about the legal entity:</span></span> 
   1. <span data-ttu-id="43a04-124">Szükség esetén írja be a keresési nevet.</span><span class="sxs-lookup"><span data-stu-id="43a04-124">Enter a search name, if a search name is required.</span></span> <span data-ttu-id="43a04-125">A keresési név olyan másodlagos név, amelynek használatával elvégezheti a keresést a jogi személyre vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="43a04-125">A search name is an alternate name that can be used to search for this legal entity.</span></span> 
   1. <span data-ttu-id="43a04-126">Adja meg, hogy ez a jogi személy konszolidációs vállalatként használatos-e.</span><span class="sxs-lookup"><span data-stu-id="43a04-126">Select whether this legal entity is being used as a consolidation company.</span></span>
   1. <span data-ttu-id="43a04-127">Adja meg, hogy ez a jogi személy eltávolítási vállalatként használatos-e.</span><span class="sxs-lookup"><span data-stu-id="43a04-127">Select whether this legal entity is being used as an elimination company.</span></span> 
   1. <span data-ttu-id="43a04-128">Jelölje ki az **alapértelmezett nyelvet** az entitáshoz.</span><span class="sxs-lookup"><span data-stu-id="43a04-128">Select the **default language** for the entity.</span></span> 
   1. <span data-ttu-id="43a04-129">Válassza ki az entitás **időzónáját**.</span><span class="sxs-lookup"><span data-stu-id="43a04-129">Select the **time zone** for the entity.</span></span>
1. <span data-ttu-id="43a04-130">A **Címek** szakaszban kattintson a **Szerkesztés** lehetőségre, és adja meg a cím adatait, mint például az utca nevet és a számot, az irányítószámot és a várost.</span><span class="sxs-lookup"><span data-stu-id="43a04-130">In the **Addresses** section, select **Edit** to enter address information, such as the street name and number, postal code, and city.</span></span>
1. <span data-ttu-id="43a04-131">A **Kapcsolattartási adatok** szakaszban adja meg a kommunikációs módszerekkel kapcsolatos adatokat, például a e-mail címeket, az URL-címeket és a telefonszámokat.</span><span class="sxs-lookup"><span data-stu-id="43a04-131">In the **Contact information** section, enter information about methods of communication, such as email addresses, URLs, and telephone numbers.</span></span>
1. <span data-ttu-id="43a04-132">A **Kötelezően előírt jelentéskészítés** szakaszban adja meg a kötelező jelentési célokra használt nyilvántartási számokat.</span><span class="sxs-lookup"><span data-stu-id="43a04-132">In the **Statutory reporting** section, enter the registration numbers that are used for statutory reporting.</span></span>
1. <span data-ttu-id="43a04-133">A **Regisztrációs számok** szakaszban adja meg a jogi személy által igényelt információkat.</span><span class="sxs-lookup"><span data-stu-id="43a04-133">In the **Registration numbers** section, enter any information required by the legal entity.</span></span>
1. <span data-ttu-id="43a04-134">A **Bankszámla adatok** szakaszban adja meg a bankszámlaákat és a regisztrációs azonosítót a jogi személyre vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="43a04-134">In the **Bank account information** section, enter bank accounts and routing numbers for the legal entity.</span></span>
1. <span data-ttu-id="43a04-135">A **Külföldi kereskedelem és logisztika** szakaszban adja meg a szállítási adatokat a jogi személyre vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="43a04-135">In the **Foreign trade and logistics** section, enter shipping information for the legal entity.</span></span>
1. <span data-ttu-id="43a04-136">A **Számsorozat** gyorslapon megtekintheti a jogi személyhez kapcsolódó számsorozatokat.</span><span class="sxs-lookup"><span data-stu-id="43a04-136">In the **Number sequences** section, you can view the number sequences that are associated with the legal entity.</span></span> <span data-ttu-id="43a04-137">Ez a mező üresen marad eredetileg.</span><span class="sxs-lookup"><span data-stu-id="43a04-137">This will be empty to start with.</span></span>
1. <span data-ttu-id="43a04-138">Az **Irányítópult képei** szakaszban tekintse meg vagy módosítsa a jogi személyhez társított emblémát és/vagy irányítópultot.</span><span class="sxs-lookup"><span data-stu-id="43a04-138">In the **Dashboard image** section, view or change the logo and dashboard image associated with the legal entity.</span></span>
1. <span data-ttu-id="43a04-139">Az **Adóregisztráció** szakaszban adja meg az adóhatóságnál tett jelentéshez használt nyilvántartási számokat.</span><span class="sxs-lookup"><span data-stu-id="43a04-139">In the **Tax registration** section, enter the registration numbers that are used to report to tax authorities.</span></span>
1. <span data-ttu-id="43a04-140">Az **Adó - 1099** szakaszban adja meg a 1099-es adatokat a jogi személyre vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="43a04-140">In the **Tax 1099** section, enter 1099 information for the legal entity.</span></span>
1. <span data-ttu-id="43a04-141">Az **Adózási adatok** szakaszban adja meg az adózási adatokat a jogi személyre vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="43a04-141">In the **Tax invormation** section, enter tax information for the legal entity.</span></span>
1. <span data-ttu-id="43a04-142">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="43a04-142">Select **Save**.</span></span>

<span data-ttu-id="43a04-143">A következő kép egy példa jogi személy részleteit mutatja.</span><span class="sxs-lookup"><span data-stu-id="43a04-143">The following image shows details of an example legal entity.</span></span>

![Jogi személy általános szakasza](media/legal-entities-general.png)
   
## <a name="additional-resources"></a><span data-ttu-id="43a04-145">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="43a04-145">Additional resources</span></span>

[<span data-ttu-id="43a04-146">Szervezetek és szervezeti hierarchiák áttekintése</span><span class="sxs-lookup"><span data-stu-id="43a04-146">Organizations and organizational hierarchies overview</span></span>](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="43a04-147">Szervezeti hierarchia megtervezése</span><span class="sxs-lookup"><span data-stu-id="43a04-147">Plan your organizational hierarchy</span></span>](../fin-ops-core/fin-ops/organization-administration/plan-organizational-hierarchy.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="43a04-148">Szervezeti hierarchiák</span><span class="sxs-lookup"><span data-stu-id="43a04-148">Organization hierarchies</span></span>](channels-org-hierarchies.md)

[<span data-ttu-id="43a04-149">Csatornák áttekintése</span><span class="sxs-lookup"><span data-stu-id="43a04-149">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="43a04-150">Csatornák beállításának előfeltételei</span><span class="sxs-lookup"><span data-stu-id="43a04-150">Channel setup prerequisites</span></span>](channels-prerequisites.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
