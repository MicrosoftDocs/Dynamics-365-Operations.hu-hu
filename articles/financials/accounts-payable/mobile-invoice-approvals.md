---
title: Mobil számlajóváhagyások
description: Ez a témakör gyakorlati megközelítést biztosít a Dynamics 365 for Finance and Operations mobilforgatókönyveinek tervezéséhez használati esetként mobilos szállítóiszámla-jóváhagyások figyelembevételével.
author: abruer
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 262034
ms.assetid: 9db38b3f-26b3-436e-8449-7ff243568a18
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 5a48ea7b0c1faf5726de21a246e3d8b4d98f166a
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/07/2019
ms.locfileid: "1511660"
---
# <a name="mobile-invoice-approvals"></a><span data-ttu-id="e1c07-103">Mobil számlajóváhagyások</span><span class="sxs-lookup"><span data-stu-id="e1c07-103">Mobile invoice approvals</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e1c07-104">Mobil lehetőségek a Microsoft Dynamics 365 for Finance and Operations alkalmazásban lehetővé teszi az üzleti felhasználónak a mobilélmények tervezését.</span><span class="sxs-lookup"><span data-stu-id="e1c07-104">Mobile capabilities in Microsoft Dynamics 365 for Finance and Operations let a business user design mobile experiences.</span></span> <span data-ttu-id="e1c07-105">Speciális esetekben a platformon a fejlesztők is igényeik szerint bővíthetik lehetőségeiket.</span><span class="sxs-lookup"><span data-stu-id="e1c07-105">For advanced scenarios, the platform also lets developers extend the capabilities as they desire.</span></span> <span data-ttu-id="e1c07-106">A leghatékonyabb módszer a mobilon elérhető új lehetőségek megismeréséhez a forgatókönyvek tervezési folyamatának többszöri végigjárása.</span><span class="sxs-lookup"><span data-stu-id="e1c07-106">The most effective way to learn some of the new concepts on mobile is to go through the process of designing a few scenarios.</span></span> <span data-ttu-id="e1c07-107">Ez a témakör gyakorlati megközelítést biztosít mobilforgatókönyvek tervezéséhez használati esetként mobilos szállítóiszámla-jóváhagyások figyelembevételével.</span><span class="sxs-lookup"><span data-stu-id="e1c07-107">This topic is intended to provide a practical approach to designing mobile scenarios by taking vendor invoice approvals for mobile as a use case.</span></span> <span data-ttu-id="e1c07-108">A témakör segít a forgatókönyvek egyéb változatainak megtervezésében, és szállítói számlákhoz nem kapcsolódó más forgatókönyvekhez is alkalmazható.</span><span class="sxs-lookup"><span data-stu-id="e1c07-108">This topic should help you design other variations of the scenarios and can also be applied to other scenarios that aren’t related to vendor invoices.</span></span>

<a name="prerequisites"></a><span data-ttu-id="e1c07-109">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="e1c07-109">Prerequisites</span></span>
-------------

| <span data-ttu-id="e1c07-110">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="e1c07-110">Prerequisite</span></span>                                                                                            | <span data-ttu-id="e1c07-111">Leírás</span><span class="sxs-lookup"><span data-stu-id="e1c07-111">Description</span></span>                                                                                                                                                          |
|---------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="e1c07-112">Mobil kézikönyv előzetes olvasás</span><span class="sxs-lookup"><span data-stu-id="e1c07-112">Mobile handbook pre-read</span></span>                                                                                |[<span data-ttu-id="e1c07-113">Mobil platform</span><span class="sxs-lookup"><span data-stu-id="e1c07-113">Mobile platform</span></span>](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md)                                                                                                  |
| <span data-ttu-id="e1c07-114">Dynamics 365 for Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="e1c07-114">Dynamics 365 for Finance and Operations</span></span>                                                                             | <span data-ttu-id="e1c07-115">Egy környezet, amely Microsoft Dynamics 365 for Operations 1611-os verzióval és Microsoft Dynamics for Operations platform update 3 (2016. november) rendelkezik</span><span class="sxs-lookup"><span data-stu-id="e1c07-115">An environment that has Microsoft Dynamics 365 for Operations version 1611 and Microsoft Dynamics for Operations platform update 3 (November 2016)</span></span>                   |
| <span data-ttu-id="e1c07-116">Telepítse a 3204341 számú tudásbáziscikkhez tartozó gyorsjavítást.</span><span class="sxs-lookup"><span data-stu-id="e1c07-116">Install hotfix KB 3204341.</span></span>                                                                              | <span data-ttu-id="e1c07-117">A Feladatrögzítő tévesen két Bezárás parancsot rögzíthet legördülő párbeszédpaneleknél - ez a Dynamics 365 for Operation 3. platformfrissítésében található (2016. novemberi frissítés)</span><span class="sxs-lookup"><span data-stu-id="e1c07-117">Task recorder can erroneously record two Close commands for dropdown dialogs this is included in Dynamics 365 for Operation platform update 3 (November 2016 update)</span></span> |
| <span data-ttu-id="e1c07-118">Telepítse a 3207800 számú tudásbáziscikkhez tartozó gyorsjavítást.</span><span class="sxs-lookup"><span data-stu-id="e1c07-118">Install hotfix KB 3207800.</span></span>                                                                              | <span data-ttu-id="e1c07-119">Ez a gyorsjavítás lehetővé teszi a mellékletek megtekintését mobil kliensen - - ez a Dynamics 365 for Operation 3. platformfrissítésében található (2016. novemberi frissítés).</span><span class="sxs-lookup"><span data-stu-id="e1c07-119">This hotfix enables attachments to be viewed on the mobile client this is included in Dynamics 365 for Operation platform update 3 (November 2016 update).</span></span>           |
| <span data-ttu-id="e1c07-120">Telepítse a 3208224 számú tudásbáziscikkhez tartozó gyorsjavítást.</span><span class="sxs-lookup"><span data-stu-id="e1c07-120">Install hotfix KB 3208224.</span></span>                                                                              | <span data-ttu-id="e1c07-121">Alkalmazáskód a szállítói számla jóváhagyására szolgáló mobilalkalmazáshoz - ez a Microsoft Dynamics AX alkalmazás 7.0.1 (2016. május) verziójában szerepel.</span><span class="sxs-lookup"><span data-stu-id="e1c07-121">Application code for the mobile vendor invoice approval application this is included in Microsoft Dynamics AX application 7.0.1 (May 2016).</span></span>                          |
| <span data-ttu-id="e1c07-122">Android-, iOS- vagy Windows-eszköz, amelyre telepítve van a Finance and Operations mobilalkalmazása</span><span class="sxs-lookup"><span data-stu-id="e1c07-122">An Android or iOS or a Windows device that has the mobile app installed for Finance and Operations</span></span> | <span data-ttu-id="e1c07-123">Keresse meg az alkalmazást a megfelelő alkalmazásáruházban.</span><span class="sxs-lookup"><span data-stu-id="e1c07-123">Search for the app in the appropriate app store.</span></span>                                                                                                                     |

## <a name="introduction"></a><span data-ttu-id="e1c07-124">Bevezetés</span><span class="sxs-lookup"><span data-stu-id="e1c07-124">Introduction</span></span>
<span data-ttu-id="e1c07-125">A szállítói számlák mobil jóváhagyásához az „Előfeltételek” című szakaszban említett három gyorsjavításra van szükség.</span><span class="sxs-lookup"><span data-stu-id="e1c07-125">Mobile approvals for vendor invoices require the three hotfixes that are mentioned in the “Prerequisites” section.</span></span> <span data-ttu-id="e1c07-126">Ezek a gyorsjavítások nem biztosítanak munkaterületet számlajóváhagyáshoz.</span><span class="sxs-lookup"><span data-stu-id="e1c07-126">These hotfixes don’t provide a workspace for the invoice approvals.</span></span> <span data-ttu-id="e1c07-127">A munkaterület mobil környezetben való jelentésének megismeréséhez olvassa el az „Előfeltételek” című részben említett mobil kézikönyvet.</span><span class="sxs-lookup"><span data-stu-id="e1c07-127">To learn what a workspace is in the context of mobile, read the mobile handbook that is mentioned in the “Prerequisites” section.</span></span> <span data-ttu-id="e1c07-128">A számlajóváhagyások munkaterületét ki kell alakítani.</span><span class="sxs-lookup"><span data-stu-id="e1c07-128">The invoice approvals workspace must be designed.</span></span> 

<span data-ttu-id="e1c07-129">Minden szervezet eltérő módon szervezi és határozza meg a szállítói számlákkal kapcsolatos üzleti folyamatát.</span><span class="sxs-lookup"><span data-stu-id="e1c07-129">Every organization orchestrates and defines its business process for vendor invoices differently.</span></span> <span data-ttu-id="e1c07-130">Mielőtt szállítói számlák jóváhagyásához mobilfelületet tervezne, vegye figyelembe az üzleti folyamat következő szempontjait.</span><span class="sxs-lookup"><span data-stu-id="e1c07-130">Before you design a mobile experience for vendor invoice approvals, you should consider the following aspects of the business process.</span></span> <span data-ttu-id="e1c07-131">Az elképzelés lényege, hogy ezen adatpontokat a lehető legjobban kihasználjuk a felhasználói élmény az eszközön való optimalizálására.</span><span class="sxs-lookup"><span data-stu-id="e1c07-131">The idea is to use these data points as much as possible to optimize the user experience on the device.</span></span>

-   <span data-ttu-id="e1c07-132">A számlafejléc mely mezőit szeretné a felhasználó látni a mobil felületen, és milyen sorrendben?</span><span class="sxs-lookup"><span data-stu-id="e1c07-132">What fields from the invoice header will the user want to see in the mobile experience, and in what order?</span></span>
-   <span data-ttu-id="e1c07-133">A számlasorok mely mezőit szeretné a felhasználó látni a mobil felületen, és milyen sorrendben?</span><span class="sxs-lookup"><span data-stu-id="e1c07-133">What fields from the invoice lines will the user want to see in the mobile experience, and in what order?</span></span>
-   <span data-ttu-id="e1c07-134">Hány számlasor van a számlán?</span><span class="sxs-lookup"><span data-stu-id="e1c07-134">How many invoice lines are there in an invoice?</span></span> <span data-ttu-id="e1c07-135">Itt alkalmazza a 80-20-as szabályt, és optimalizáljon 80%-ra.</span><span class="sxs-lookup"><span data-stu-id="e1c07-135">Apply the 80-20 rule here, and optimize for the 80 percent.</span></span>
-   <span data-ttu-id="e1c07-136">A felhasználók akarnak könyvelési felosztásokat (számlakódolást) látni a mobileszközön ellenőrzések során?</span><span class="sxs-lookup"><span data-stu-id="e1c07-136">Will users want to see accounting distributions (invoice coding) on the mobile device during reviews?</span></span> <span data-ttu-id="e1c07-137">Ha erre a kérdésre a válasz Igen, gondolja át a következő kérdéseket:</span><span class="sxs-lookup"><span data-stu-id="e1c07-137">If the answer to this question is yes, consider the following questions:</span></span>
    -   <span data-ttu-id="e1c07-138">Hány könyvelési felosztás (kiterjesztett ár, áfa, költségek, megosztások stb.) van egy-egy számlasornál?</span><span class="sxs-lookup"><span data-stu-id="e1c07-138">How many accounting distributions (extended price, sales tax, charges, splits, and so on) are there for an invoice line?</span></span> <span data-ttu-id="e1c07-139">Ismételten alkalmazza a 80-20-as szabályt.</span><span class="sxs-lookup"><span data-stu-id="e1c07-139">Again, apply the 80-20 rule.</span></span>
    -   <span data-ttu-id="e1c07-140">A számlák szintén rendelkeznek könyvelési felosztásokkal a számla fejlécében?</span><span class="sxs-lookup"><span data-stu-id="e1c07-140">Do the invoices also have accounting distributions on the invoice header?</span></span> <span data-ttu-id="e1c07-141">Ha igen, e könyvelési felosztásoknak rendelkezésre kell állniuk a készüléken?</span><span class="sxs-lookup"><span data-stu-id="e1c07-141">If so, should these accounting distributions be available on the device?</span></span>

> [!NOTE]
> <span data-ttu-id="e1c07-142">Ez a témakör nem magyarázza el, hogyan szerkeszthetők a könyvelési felosztások, mert ez a funkció jelenleg a mobilváltozatokban nem támogatott.</span><span class="sxs-lookup"><span data-stu-id="e1c07-142">This topic doesn’t explain how to edit accounting distributions, because this functionality isn’t currently supported for mobile scenarios.</span></span>

-   <span data-ttu-id="e1c07-143">A felhasználók látni szeretnék a számlához tartozó mellékleteket az eszközön?</span><span class="sxs-lookup"><span data-stu-id="e1c07-143">Will users want to see attachments for the invoice on the device?</span></span>

<span data-ttu-id="e1c07-144">A számlajóváhagyási mobilfelület kialakítása az e kérdésekre adott válaszoktól függően eltérő lesz.</span><span class="sxs-lookup"><span data-stu-id="e1c07-144">The design of the mobile experience for invoice approvals will differ, depending on the answers to these questions.</span></span> <span data-ttu-id="e1c07-145">A cél: optimalizálni a szervezet üzleti folyamatának felhasználói élményét a mobilon.</span><span class="sxs-lookup"><span data-stu-id="e1c07-145">The objective is to optimize the user experience for the business process on mobile in an organization.</span></span> <span data-ttu-id="e1c07-146">A témakör többi részében két forgatókönyv-változatot vizsgálunk meg közelebbről, amelyek az előző kérdésekre adott különböző válaszokon alapulnak.</span><span class="sxs-lookup"><span data-stu-id="e1c07-146">In the rest of this topic, we will look at two scenario variations that are based on different answers to the preceding questions.</span></span> 

<span data-ttu-id="e1c07-147">Általános iránymutatásként a mobiltervezővel való munka során ügyeljen, hogy „tegye közzé” a módosításokat, nehogy elveszítse a frissítéseket.</span><span class="sxs-lookup"><span data-stu-id="e1c07-147">As a general guidance, when working with the mobile designer, make sure to 'publish' the changes to prevent losing the updates.</span></span>

## <a name="designing-a-simple-invoice-approval-scenario-for-contoso"></a><span data-ttu-id="e1c07-148">Egyszerű számlajóváhagyási forgatókönyv tervezése a Contoso számára</span><span class="sxs-lookup"><span data-stu-id="e1c07-148">Designing a simple invoice approval scenario for Contoso</span></span>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e1c07-149">Változatattribútum</span><span class="sxs-lookup"><span data-stu-id="e1c07-149">Scenario attribute</span></span></th>
<th><span data-ttu-id="e1c07-150">Válasz</span><span class="sxs-lookup"><span data-stu-id="e1c07-150">Answer</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="e1c07-151">A számlafejléc mely mezőit szeretné a felhasználó látni a mobil felületen, és milyen sorrendben?</span><span class="sxs-lookup"><span data-stu-id="e1c07-151">What fields from the invoice header will the user want to see in the mobile experience, and in what order?</span></span></td>
<td><ol>
<li><span data-ttu-id="e1c07-152">Szállító neve</span><span class="sxs-lookup"><span data-stu-id="e1c07-152">Vendor name</span></span></li>
<li><span data-ttu-id="e1c07-153">Számla összege</span><span class="sxs-lookup"><span data-stu-id="e1c07-153">Invoice total</span></span></li>
<li><span data-ttu-id="e1c07-154">Számlafogadó</span><span class="sxs-lookup"><span data-stu-id="e1c07-154">Invoice account</span></span></li>
<li><span data-ttu-id="e1c07-155">Számla száma</span><span class="sxs-lookup"><span data-stu-id="e1c07-155">Invoice number</span></span></li>
<li><span data-ttu-id="e1c07-156">Számla dátuma</span><span class="sxs-lookup"><span data-stu-id="e1c07-156">Invoice date</span></span></li>
<li><span data-ttu-id="e1c07-157">Számla leírása</span><span class="sxs-lookup"><span data-stu-id="e1c07-157">Invoice description</span></span></li>
<li><span data-ttu-id="e1c07-158">Esedékes</span><span class="sxs-lookup"><span data-stu-id="e1c07-158">Due date</span></span></li>
<li><span data-ttu-id="e1c07-159">Számla pénzneme</span><span class="sxs-lookup"><span data-stu-id="e1c07-159">Invoice currency</span></span></li>
</ol></td>
</tr>
<tr class="even">
<td><span data-ttu-id="e1c07-160">A számlasorok mely mezőit szeretné a felhasználó látni a mobil felületen, és milyen sorrendben?</span><span class="sxs-lookup"><span data-stu-id="e1c07-160">What fields from the invoice lines will the user want to see in the mobile experience, and in what order?</span></span></td>
<td><ol>
<li><span data-ttu-id="e1c07-161">Beszerzési kategória</span><span class="sxs-lookup"><span data-stu-id="e1c07-161">Procurement category</span></span></li>
<li><span data-ttu-id="e1c07-162">Mennyiség</span><span class="sxs-lookup"><span data-stu-id="e1c07-162">Quantity</span></span></li>
<li><span data-ttu-id="e1c07-163">Egységár</span><span class="sxs-lookup"><span data-stu-id="e1c07-163">Unit price</span></span></li>
<li><span data-ttu-id="e1c07-164">Sor nettó összege</span><span class="sxs-lookup"><span data-stu-id="e1c07-164">Line net amount</span></span></li>
<li><span data-ttu-id="e1c07-165">1099-es összeg</span><span class="sxs-lookup"><span data-stu-id="e1c07-165">1099 amount</span></span></li>
</ol></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="e1c07-166">Hány számlasor van a számlán?</span><span class="sxs-lookup"><span data-stu-id="e1c07-166">How many invoice lines are there in an invoice?</span></span> <span data-ttu-id="e1c07-167">Itt alkalmazza a 80-20-as szabályt, és optimalizáljon 80%-ra.</span><span class="sxs-lookup"><span data-stu-id="e1c07-167">Apply the 80-20 rule here, and optimize for the 80 percent.</span></span></td>
<td><span data-ttu-id="e1c07-168">1</span><span class="sxs-lookup"><span data-stu-id="e1c07-168">1</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="e1c07-169">A felhasználók akarnak könyvelési felosztásokat (számlakódolást) látni a mobileszközön ellenőrzések során?</span><span class="sxs-lookup"><span data-stu-id="e1c07-169">Will users want to see accounting distributions (invoice coding) on the mobile device during reviews?</span></span></td>
<td><span data-ttu-id="e1c07-170">Igen</span><span class="sxs-lookup"><span data-stu-id="e1c07-170">Yes</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="e1c07-171">Hány könyvelési felosztás (kiterjesztett ár, áfa, költségek stb.) van egy-egy számlasornál?</span><span class="sxs-lookup"><span data-stu-id="e1c07-171">How many accounting distributions (extended price, sales tax, charges, and so on) are there for an invoice line?</span></span> <span data-ttu-id="e1c07-172">Ismételten alkalmazza a 80-20-as szabályt.</span><span class="sxs-lookup"><span data-stu-id="e1c07-172">Again, apply the 80-20 rule.</span></span></td>
<td><span data-ttu-id="e1c07-173">Kiterjesztett ár: 2 áfa: 0 költség: 0</span><span class="sxs-lookup"><span data-stu-id="e1c07-173">Extended price: 2 Sales tax: 0 Charges: 0</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="e1c07-174">A számlák szintén rendelkeznek könyvelési felosztásokkal a számla fejlécében?</span><span class="sxs-lookup"><span data-stu-id="e1c07-174">Do the invoices also have accounting distributions on the invoice header?</span></span> <span data-ttu-id="e1c07-175">Ha igen, e könyvelési felosztásoknak rendelkezésre kell állniuk a készüléken?</span><span class="sxs-lookup"><span data-stu-id="e1c07-175">If so, should these accounting distributions be available on the device?</span></span></td>
<td><span data-ttu-id="e1c07-176">Nincs használatban</span><span class="sxs-lookup"><span data-stu-id="e1c07-176">Not used</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="e1c07-177">A felhasználók látni szeretnék a számlához tartozó mellékleteket az eszközön?</span><span class="sxs-lookup"><span data-stu-id="e1c07-177">Will users want to see attachments for the invoice on the device?</span></span></td>
<td><span data-ttu-id="e1c07-178">Igen</span><span class="sxs-lookup"><span data-stu-id="e1c07-178">Yes</span></span></td>
</tr>
</tbody>
</table>

### <a name="create-the-workspace"></a><span data-ttu-id="e1c07-179">Munkaterület létrehozása</span><span class="sxs-lookup"><span data-stu-id="e1c07-179">Create the workspace</span></span>

1.  <span data-ttu-id="e1c07-180">A böngészőben nyissa meg a Finance and Operations rendszert, és jelentkezzen be.</span><span class="sxs-lookup"><span data-stu-id="e1c07-180">In a browser, open Finance and Operations, and sign in.</span></span>
2.  <span data-ttu-id="e1c07-181">Miután bejelentkezett, fűzze hozzá a **&mode=mobile** karakterláncot az URL-címhez az alábbi példa alapján, és frissítse az oldalt: https://&lt;sajaturl&gt;/?cmp=usmf&mi=DefaultDashboard **&mode=mobile**</span><span class="sxs-lookup"><span data-stu-id="e1c07-181">After you’ve signed in, append **&mode=mobile** to the URL as shown in the following example, and refresh the page: https://&lt;yoururl&gt;/?cmp=usmf&mi=DefaultDashboard **&mode=mobile**</span></span>
3.  <span data-ttu-id="e1c07-182">Kattintson a **Beállítások** (fogaskerék) gombra az oldal jobb felső sarkában, majd kattintson a **Mobilalkalmazás** elemre.</span><span class="sxs-lookup"><span data-stu-id="e1c07-182">Click the **Settings** (gear) button in the upper right of the page, and then click **Mobile app**.</span></span> <span data-ttu-id="e1c07-183">Megjelenik a mobilalkalmazás tervezője és a Feladatrögzítő.</span><span class="sxs-lookup"><span data-stu-id="e1c07-183">The mobile app designer must show up just as Task recorder shows up.</span></span>
4.  <span data-ttu-id="e1c07-184">Kattintson a **Hozzáadás** elemre új munkaterület létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="e1c07-184">Click **Add** to create a new workspace.</span></span> <span data-ttu-id="e1c07-185">Ebben a példában adja a munkaterületnek a **Jóváhagyásaim** nevet.</span><span class="sxs-lookup"><span data-stu-id="e1c07-185">For this example, name the workspace **My approvals**.</span></span>
5.  <span data-ttu-id="e1c07-186">Adjon meg leírást.</span><span class="sxs-lookup"><span data-stu-id="e1c07-186">Enter a description.</span></span>
6.  <span data-ttu-id="e1c07-187">Válasszon színt a munkaterületnek.</span><span class="sxs-lookup"><span data-stu-id="e1c07-187">Select a workspace color.</span></span> <span data-ttu-id="e1c07-188">A munkaterület színe adja a munkaterülethez tartozó mobilfelület általános stílusát.</span><span class="sxs-lookup"><span data-stu-id="e1c07-188">The workspace color will be used for the overall style of the mobile experience for this workspace.</span></span>
7.  <span data-ttu-id="e1c07-189">Válasszon ikont a munkaterülethez.</span><span class="sxs-lookup"><span data-stu-id="e1c07-189">Select an icon for the workspace.</span></span>
8.  <span data-ttu-id="e1c07-190">Kattintson a **Kész** gombra.</span><span class="sxs-lookup"><span data-stu-id="e1c07-190">Click **Done**</span></span>
9.  <span data-ttu-id="e1c07-191">A **Munkaterület közzététele** gombra kattintva mentse a módosításokat.</span><span class="sxs-lookup"><span data-stu-id="e1c07-191">Click **Publish workspace** to save the changes</span></span>

### <a name="vendor-invoices-assigned-to-me"></a><span data-ttu-id="e1c07-192">Hozzám rendelt szállítói számlák</span><span class="sxs-lookup"><span data-stu-id="e1c07-192">Vendor invoices assigned to me</span></span>

<span data-ttu-id="e1c07-193">Az első mobiloldal, amelyet meg kell terveznie, a véleményezésre a felhasználóhoz rendelt számlák listája.</span><span class="sxs-lookup"><span data-stu-id="e1c07-193">The first mobile page that you should design is the list of invoices that are assigned to the user for review.</span></span> <span data-ttu-id="e1c07-194">A mobillap megtervezéséhez használja a Finance and Operations **VendMobileInvoiceAssignedToMeListPage** lapját.</span><span class="sxs-lookup"><span data-stu-id="e1c07-194">To design this mobile page, use the **VendMobileInvoiceAssignedToMeListPage** page in Finance and Operations.</span></span> <span data-ttu-id="e1c07-195">Az eljárás végrehajtása előtt győződjön meg arról, hogy legalább egy szállítói számla Önhöz van rendelve véleményezésre, és hogy a számlasor két felosztást tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="e1c07-195">Before you complete this procedure, make sure that at least one vendor invoice is assigned to you for review, and that the invoice line has two distributions.</span></span> <span data-ttu-id="e1c07-196">Ez a beállítás megfelel a jelen forgatókönyv követelményeinek.</span><span class="sxs-lookup"><span data-stu-id="e1c07-196">This setup meets the requirements for this scenario.</span></span>

1.  <span data-ttu-id="e1c07-197">A Finance and Operations URL-jében cserélje le a menüelem nevét arra, hogy **VendMobileInvoiceAssignedToMeListPage**, és így megnyílik a **Hozzám rendelt függőben levő szállítói számlák** listaoldal mobilváltozata a **Kötelezettségek** modulban.</span><span class="sxs-lookup"><span data-stu-id="e1c07-197">In the Finance and Operations URL, replace the name of the menu item with **VendMobileInvoiceAssignedToMeListPage** to open the mobile version of the **Pending vendor invoices assigned to me** list page in the **Accounts payable** module.</span></span> <span data-ttu-id="e1c07-198">A rendszerben Önhöz hozzárendelt számlák számától függően a lapon megjelennek az érintett számlák.</span><span class="sxs-lookup"><span data-stu-id="e1c07-198">Depending on the number of invoices that you have in your system assigned to you, this page will show those invoices.</span></span> <span data-ttu-id="e1c07-199">Adott számla megkereséséhez használja a bal oldali szűrőt.</span><span class="sxs-lookup"><span data-stu-id="e1c07-199">To find a specific invoice, you can use the filter on the left.</span></span> <span data-ttu-id="e1c07-200">Ebben a példában viszont nincs szükségünk konkrét számlára.</span><span class="sxs-lookup"><span data-stu-id="e1c07-200">However, we don’t require a specific invoice for this example.</span></span> <span data-ttu-id="e1c07-201">Csak arra van szükségünk, hogy legyen néhány Önhöz rendelt számla, ami lehetővé teszi a mobillap megtervezését.</span><span class="sxs-lookup"><span data-stu-id="e1c07-201">We just require some invoice assigned to you which is going to allow you to design the mobile page.</span></span> <span data-ttu-id="e1c07-202">A rendelkezésre álló új oldalakat kifejezetten a szállítói számlákhoz kapcsolódó mobilforgatókönyvek kidolgozásához alakítottuk ki.</span><span class="sxs-lookup"><span data-stu-id="e1c07-202">The new pages that are available have been designed specifically for developing mobile scenarios for vendor invoice.</span></span> <span data-ttu-id="e1c07-203">Ezért ezeket az oldalakat kell használnia.</span><span class="sxs-lookup"><span data-stu-id="e1c07-203">Therefore, you must use these pages.</span></span> <span data-ttu-id="e1c07-204">Az URL-nek a következő URL-re kell hasonlítania, és miután megadta, meg kell jelennie az ábrán látható oldalnak: https://&lt;sajatURL&gt;/?cmp=usmf&mi **=VendMobileInvoiceAssignedToMeListPage**&mode=mobile [![Hozzám rendelt függőben lévő szállítói számlák oldal](./media/mobile-invoice-approvals01-1024x281.png)](./media/mobile-invoice-approvals01.png)</span><span class="sxs-lookup"><span data-stu-id="e1c07-204">The URL should resemble the following URL, and after you enter it, the page that is shown in the illustration must appear: https://&lt;yourURL&gt;/?cmp=usmf&mi=**VendMobileInvoiceAssignedToMeListPage**&mode=mobile [![Pending vendor invoices assigned to me page](./media/mobile-invoice-approvals01-1024x281.png)](./media/mobile-invoice-approvals01.png)</span></span>
2.  <span data-ttu-id="e1c07-205">Kattintson a **Beállítások** (fogaskerék) gombra az oldal jobb felső sarkában, majd kattintson a **Mobilalkalmazás** elemre</span><span class="sxs-lookup"><span data-stu-id="e1c07-205">Click the **Settings** (gear) button in the upper right of the page, and then click **Mobile app**</span></span>
3.  <span data-ttu-id="e1c07-206">Válassza ki a munkaterületet, és kattintson a **Szerkesztés** elemre</span><span class="sxs-lookup"><span data-stu-id="e1c07-206">Select your workspace and click **Edit**</span></span>
4.  <span data-ttu-id="e1c07-207">Kattintson az **Oldal hozzáadása** elemre az első mobiloldal létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="e1c07-207">Click **Add page** to create the first mobile page.</span></span>
5.  <span data-ttu-id="e1c07-208">Adjon meg egy nevet, például **Saját szállítói számlák**, és egy leírást, például **Véleményezésre hozzám rendelt szállítói számlák**.</span><span class="sxs-lookup"><span data-stu-id="e1c07-208">Enter a name, such as **My vendor invoices**, and a description, such as **Vendor invoices assigned to me for review**.</span></span>
6.  <span data-ttu-id="e1c07-209">Kattintson a **Kész** gombra.</span><span class="sxs-lookup"><span data-stu-id="e1c07-209">Click **Done**.</span></span>
7.  <span data-ttu-id="e1c07-210">A mobiltervezőben a **Mezők** fülön kattintson a **Mezők kijelölése** elemre.</span><span class="sxs-lookup"><span data-stu-id="e1c07-210">In the mobile designer, on the **Fields** tab, click **Select fields**.</span></span> <span data-ttu-id="e1c07-211">A listalapon látható oszlopoknak az alábbi ábrához kell hasonlítaniuk.</span><span class="sxs-lookup"><span data-stu-id="e1c07-211">The columns on the list page must resemble the following illustration.</span></span> <span data-ttu-id="e1c07-212">[![Hozzám rendelt függőben lévő szállítói számlák oldalának oszlopai](./media/mobile-invoice-approvals02-1024x117.png)](./media/mobile-invoice-approvals02.png)</span><span class="sxs-lookup"><span data-stu-id="e1c07-212">[![Columns on the Pending vendor invoices assigned to me page](./media/mobile-invoice-approvals02-1024x117.png)](./media/mobile-invoice-approvals02.png)</span></span>
8.  <span data-ttu-id="e1c07-213">A listaoldalról adja hozzá a szükséges oszlopokat, amelyeket a felhasználók látni fognak a mobiloldalon.</span><span class="sxs-lookup"><span data-stu-id="e1c07-213">Add the required columns from the list page that must be shown to the users in the mobile page.</span></span> <span data-ttu-id="e1c07-214">A rendelés, amelyhez hozzáadja őket, az a rendelés, amelyben a mezők megjelennek a végfelhasználó számára.</span><span class="sxs-lookup"><span data-stu-id="e1c07-214">The order in which you add is the order in which the fields will be displayed to the end user.</span></span> <span data-ttu-id="e1c07-215">A mezők sorrendjének megváltoztatása csak az összes mező újbóli kijelölésével lehetséges.</span><span class="sxs-lookup"><span data-stu-id="e1c07-215">The only way to change the ordering of the fields will be by re-selecting all the fields.</span></span> <span data-ttu-id="e1c07-216">A példánkban szereplő követelmények alapján a következő nyolc mező szükséges.</span><span class="sxs-lookup"><span data-stu-id="e1c07-216">Based on the requirements for this scenario, the following eight fields are required.</span></span> <span data-ttu-id="e1c07-217">Azonban egyes felhasználók úgy vélhetik, hogy nyolc mező mobileszközön túl sok információt jelent.</span><span class="sxs-lookup"><span data-stu-id="e1c07-217">However, some users might consider eight fields too much information to have on a mobile device.</span></span> <span data-ttu-id="e1c07-218">Ezért csak a legfontosabb mezőket mutatjuk a mobillista-nézetben.</span><span class="sxs-lookup"><span data-stu-id="e1c07-218">Therefore, we will show only the most important fields in the mobile list view.</span></span> <span data-ttu-id="e1c07-219">A fennmaradó mezők a részletes nézetben jelennek meg, amelyet később fogunk megtervezni.</span><span class="sxs-lookup"><span data-stu-id="e1c07-219">The remaining fields will appear in the details view that we will design later.</span></span> <span data-ttu-id="e1c07-220">Egyelőre a következő mezőket adjuk hozzá.</span><span class="sxs-lookup"><span data-stu-id="e1c07-220">For now, we will add the following fields.</span></span> <span data-ttu-id="e1c07-221">Kattintson ezekben az oszlopokban a plusz jelre (**+**) a mobiloldalhoz való hozzáadáshoz.</span><span class="sxs-lookup"><span data-stu-id="e1c07-221">Click the plus sign (**+**) in these columns to add to the mobile page.</span></span>
    - <span data-ttu-id="e1c07-222">Szállító neve</span><span class="sxs-lookup"><span data-stu-id="e1c07-222">Vendor name</span></span>
    - <span data-ttu-id="e1c07-223">Számla összege</span><span class="sxs-lookup"><span data-stu-id="e1c07-223">Invoice total</span></span>
    - <span data-ttu-id="e1c07-224">Számlafogadó</span><span class="sxs-lookup"><span data-stu-id="e1c07-224">Invoice account</span></span>
    - <span data-ttu-id="e1c07-225">Számla száma</span><span class="sxs-lookup"><span data-stu-id="e1c07-225">Invoice number</span></span>
    - <span data-ttu-id="e1c07-226">Számla dátuma</span><span class="sxs-lookup"><span data-stu-id="e1c07-226">Invoice date</span></span>

    <span data-ttu-id="e1c07-227">A mezők felvétele után a mobiloldalnak az alábbi ábrához kell hasonlítania.</span><span class="sxs-lookup"><span data-stu-id="e1c07-227">After the fields are added, the mobile page must resemble the following illustration.</span></span> 
    <span data-ttu-id="e1c07-228">[![Az oldal mezők hozzáadása után](./media/mobile-invoice-approvals03.png)](./media/mobile-invoice-approvals03.png)</span><span class="sxs-lookup"><span data-stu-id="e1c07-228">[![Page after fields are added](./media/mobile-invoice-approvals03.png)](./media/mobile-invoice-approvals03.png)</span></span>
9.  <span data-ttu-id="e1c07-229">Most a következő oszlopokat is hozzá kell adnia, hogy később engedélyezni lehessen munkafolyamat-műveleteket.</span><span class="sxs-lookup"><span data-stu-id="e1c07-229">You must also add the following columns now, so that we can enable workflow actions later.</span></span>
    - <span data-ttu-id="e1c07-230">Befejezett feladat megjelenítése</span><span class="sxs-lookup"><span data-stu-id="e1c07-230">Show complete task</span></span>
    - <span data-ttu-id="e1c07-231">Delegált feladat megjelenítése</span><span class="sxs-lookup"><span data-stu-id="e1c07-231">Show delegate task</span></span>
    - <span data-ttu-id="e1c07-232">Visszahívási feladat megjelenítése</span><span class="sxs-lookup"><span data-stu-id="e1c07-232">Show recall task</span></span>
    - <span data-ttu-id="e1c07-233">Elutasítási feladat megjelenítése</span><span class="sxs-lookup"><span data-stu-id="e1c07-233">Show reject task</span></span>
    - <span data-ttu-id="e1c07-234">Kérésteljesítési feladat megjelenítése</span><span class="sxs-lookup"><span data-stu-id="e1c07-234">Show request completion task</span></span>
    - <span data-ttu-id="e1c07-235">Újraküldési feladat megjelenítése</span><span class="sxs-lookup"><span data-stu-id="e1c07-235">Show resubmit task</span></span>

10. <span data-ttu-id="e1c07-236">Kattintson a **Kész** elemre a szerkesztés módból való kilépéshez.</span><span class="sxs-lookup"><span data-stu-id="e1c07-236">Click **Done** to exit edit mode.</span></span>
11. <span data-ttu-id="e1c07-237">Kattintson a **Vissza**, majd a **Kész** elemre a munkaterületről való kilépéshez.</span><span class="sxs-lookup"><span data-stu-id="e1c07-237">Click **Back** and then **Done** to exit the workspace</span></span>
12. <span data-ttu-id="e1c07-238">A **Munkaterület közzététele** gombra kattintva mentse el a munkáját.</span><span class="sxs-lookup"><span data-stu-id="e1c07-238">Click **Publish workspace** to save your work.</span></span>
13. <span data-ttu-id="e1c07-239">Engedélyezze a **Számla végösszegének megjelenítése a függő szállítói számlák listájában** funkciót a kötelezettségek paraméterei képernyő **Számla** részében.</span><span class="sxs-lookup"><span data-stu-id="e1c07-239">Enable **Display invoice total on pending vendor invoices list** in accounts payable parameters form under **Invoice**.</span></span> <span data-ttu-id="e1c07-240">Vegye figyelembe, hogy ezen paraméter engedélyezésével a rendszer kiszámítja a számlaösszegeket, és ezek megjelennek meg a függőben lévő szállítói számlák listaoldalán.</span><span class="sxs-lookup"><span data-stu-id="e1c07-240">Note that, only by enabling this parameter, invoice totals will be calculated to be displayed on the pending vendor invoices list page.</span></span> <span data-ttu-id="e1c07-241">Ezt az új képességet az előre szükséges 3208224-es gyorsjavítás biztosítja.</span><span class="sxs-lookup"><span data-stu-id="e1c07-241">This is a new capability as part of the pre-requisite hot fix 3208224.</span></span>

### <a name="vendor-invoice-details"></a><span data-ttu-id="e1c07-242">Szállítói számla részletei</span><span class="sxs-lookup"><span data-stu-id="e1c07-242">Vendor invoice details</span></span>

<span data-ttu-id="e1c07-243">A számla részletei lap mobilra való megtervezéséhez használja a Finance and Operations **VendMobileInvoiceHeaderDetails** oldalát.</span><span class="sxs-lookup"><span data-stu-id="e1c07-243">To design the invoice details page for mobile, use the **VendMobileInvoiceHeaderDetails** page in Finance and Operations.</span></span> <span data-ttu-id="e1c07-244">Fontos megjegyezni, hogy a rendszerben található számlák számától függően ezen a lapon a legrégebbi számla (az első létrehozott számla) jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="e1c07-244">Note that, depending on the number of invoices that you have in your system, this page shows the oldest invoice (the invoice that was created first).</span></span> <span data-ttu-id="e1c07-245">Adott számla megkereséséhez használja a bal oldali szűrőt.</span><span class="sxs-lookup"><span data-stu-id="e1c07-245">To find a specific invoice, you can use the filter on the left.</span></span> <span data-ttu-id="e1c07-246">Ebben a példában viszont nincs szükségünk konkrét számlára.</span><span class="sxs-lookup"><span data-stu-id="e1c07-246">However, we don’t require a specific invoice for this example.</span></span> <span data-ttu-id="e1c07-247">Csak némi számlaadatra van szükség ahhoz, hogy meg tudjuk tervezni a mobilos oldalt.</span><span class="sxs-lookup"><span data-stu-id="e1c07-247">We just require some invoice data so that we can design the mobile page.</span></span> <span data-ttu-id="e1c07-248">[![Munkafolyamat oldal](./media/mobile-invoice-approvals04-1024x425.png)](./media/mobile-invoice-approvals04.png)</span><span class="sxs-lookup"><span data-stu-id="e1c07-248">[![Workflow page](./media/mobile-invoice-approvals04-1024x425.png)](./media/mobile-invoice-approvals04.png)</span></span>

1. <span data-ttu-id="e1c07-249">A Finance and Operations URL-jében cserélje ki a menüelem nevét a **VendMobileInvoiceHeaderDetails** karakterláncra a képernyő megnyitásához</span><span class="sxs-lookup"><span data-stu-id="e1c07-249">In the Finance and Operations URL, replace the name of the menu item with **VendMobileInvoiceHeaderDetails** to open the form</span></span>
2. <span data-ttu-id="e1c07-250">Nyissa meg a mobiltervezőt a **Beállítások** (fogaskerék) gombbal.</span><span class="sxs-lookup"><span data-stu-id="e1c07-250">Open the mobile designer from the **Settings** (gear) button.</span></span>
3. <span data-ttu-id="e1c07-251">Kattintson a **Szerkesztés** gombra a munkaterület szerkesztési üzemmódjának elindításához.</span><span class="sxs-lookup"><span data-stu-id="e1c07-251">Click the **Edit** button to start edit mode in the workspace.</span></span>
4. <span data-ttu-id="e1c07-252">Válassza ki a korábban létrehozott **Saját szállítói számlák** oldalt, majd kattintson a **Szerkesztés** elemre.</span><span class="sxs-lookup"><span data-stu-id="e1c07-252">Select the **My vendor invoices** page that you created earlier, and then click **Edit**.</span></span>
5. <span data-ttu-id="e1c07-253">A **Mezők** lapon kattintson a **Rács** oszlop fejlécére.</span><span class="sxs-lookup"><span data-stu-id="e1c07-253">On the **Fields** tab, click the **Grid** column heading.</span></span>
6. <span data-ttu-id="e1c07-254">Kattintson a **Tulajdonságok &gt; Oldal hozzáadása** elemre.</span><span class="sxs-lookup"><span data-stu-id="e1c07-254">Click **Properties &gt; Add page**.</span></span> <span data-ttu-id="e1c07-255">**Megjegyzés:** amikor a **Rács** fejlécre kattint, és hozzáad egy oldalt, a részletek oldallal való kapcsolat automatikusan létrejön.</span><span class="sxs-lookup"><span data-stu-id="e1c07-255">**Note:** When you click the **Grid** heading and add a page, the relationship with the details page is established automatically.</span></span>
7. <span data-ttu-id="e1c07-256">Adja meg a lap címét, például: **Számla részletei**, és egy leírást, például: **Számlafejléc és sor részleteinek megtekintése**.</span><span class="sxs-lookup"><span data-stu-id="e1c07-256">Enter a page title, such as **Invoice details**, and a description, such as **View invoice header and line details**.</span></span>
8. <span data-ttu-id="e1c07-257">Kattintson a **Mezők kijelölése** elemre.</span><span class="sxs-lookup"><span data-stu-id="e1c07-257">Click **Select fields**.</span></span> <span data-ttu-id="e1c07-258">Ne feledje, hogy a rendelés, amelyhez hozzáadja őket, az a rendelés, amelyben a mezők megjelennek a végfelhasználó számára.</span><span class="sxs-lookup"><span data-stu-id="e1c07-258">Note that, the order in which you add is the order in which the fields will be displayed to the end user.</span></span> <span data-ttu-id="e1c07-259">A mezők sorrendjének megváltoztatása csak az összes mező újbóli kijelölésével lehetséges.</span><span class="sxs-lookup"><span data-stu-id="e1c07-259">The only way to change the ordering of the fields will be by re-selecting all the fields.</span></span> 
9. <span data-ttu-id="e1c07-260">Adja hozzá a példánkban szereplő követelmények alapján a következő mezőket a fejlécből:</span><span class="sxs-lookup"><span data-stu-id="e1c07-260">Add the following fields from the header, based on the requirements for this scenario:</span></span>
   - <span data-ttu-id="e1c07-261">Szállító neve</span><span class="sxs-lookup"><span data-stu-id="e1c07-261">Vendor name</span></span>
   - <span data-ttu-id="e1c07-262">Számla összege</span><span class="sxs-lookup"><span data-stu-id="e1c07-262">Invoice total</span></span>
   - <span data-ttu-id="e1c07-263">Számlafogadó</span><span class="sxs-lookup"><span data-stu-id="e1c07-263">Invoice account</span></span>
   - <span data-ttu-id="e1c07-264">Számla száma</span><span class="sxs-lookup"><span data-stu-id="e1c07-264">Invoice number</span></span>
   - <span data-ttu-id="e1c07-265">Számla dátuma</span><span class="sxs-lookup"><span data-stu-id="e1c07-265">Invoice date</span></span>
   - <span data-ttu-id="e1c07-266">Számla leírása</span><span class="sxs-lookup"><span data-stu-id="e1c07-266">Invoice description</span></span>
   - <span data-ttu-id="e1c07-267">Esedékes</span><span class="sxs-lookup"><span data-stu-id="e1c07-267">Due date</span></span>
   - <span data-ttu-id="e1c07-268">Számla pénzneme</span><span class="sxs-lookup"><span data-stu-id="e1c07-268">Invoice currency</span></span>

10. <span data-ttu-id="e1c07-269">Az oldalon szereplő sorrácsból adja hozzá a következő mezőket:</span><span class="sxs-lookup"><span data-stu-id="e1c07-269">Add the following fields from the lines grid on the page:</span></span>
    - <span data-ttu-id="e1c07-270">Beszerzési kategória</span><span class="sxs-lookup"><span data-stu-id="e1c07-270">Procurement category</span></span>
    - <span data-ttu-id="e1c07-271">Mennyiség</span><span class="sxs-lookup"><span data-stu-id="e1c07-271">Quantity</span></span>
    - <span data-ttu-id="e1c07-272">Egységár</span><span class="sxs-lookup"><span data-stu-id="e1c07-272">Unit price</span></span>
    - <span data-ttu-id="e1c07-273">Sor nettó összege</span><span class="sxs-lookup"><span data-stu-id="e1c07-273">Line net amount</span></span>
    - <span data-ttu-id="e1c07-274">1099-es összeg</span><span class="sxs-lookup"><span data-stu-id="e1c07-274">1099 amount</span></span>

11. <span data-ttu-id="e1c07-275">Miután az előző két lépésből az összes mezőt hozzáadta, kattintson a **Kész** elemre.</span><span class="sxs-lookup"><span data-stu-id="e1c07-275">After all the fields from the previous two steps have been added, click **Done**.</span></span> <span data-ttu-id="e1c07-276">Az oldalnak az alábbi ábrához kell hasonlítania.</span><span class="sxs-lookup"><span data-stu-id="e1c07-276">The page must resemble the following illustration.</span></span>
    <span data-ttu-id="e1c07-277">[![Az oldal mezők hozzáadása után](./media/mobile-invoice-approvals05.png)](./media/mobile-invoice-approvals05.png)</span><span class="sxs-lookup"><span data-stu-id="e1c07-277">[![Page after fields are added](./media/mobile-invoice-approvals05.png)](./media/mobile-invoice-approvals05.png)</span></span>
12. <span data-ttu-id="e1c07-278">Kattintson a **Kész** elemre a szerkesztés módból való kilépéshez.</span><span class="sxs-lookup"><span data-stu-id="e1c07-278">Click **Done** to exit edit mode.</span></span>
13. <span data-ttu-id="e1c07-279">Kattintson a **Vissza**, majd a **Kész** elemre a munkaterületről való kilépéshez.</span><span class="sxs-lookup"><span data-stu-id="e1c07-279">Click **Back** and then **Done** to exit the workspace</span></span>
14. <span data-ttu-id="e1c07-280">A **Munkaterület közzététele** gombra kattintva mentse el a munkáját</span><span class="sxs-lookup"><span data-stu-id="e1c07-280">Click **Publish workspace** to save your work</span></span>

### <a name="workflow-actions"></a><span data-ttu-id="e1c07-281">Munkafolyamat-műveletek</span><span class="sxs-lookup"><span data-stu-id="e1c07-281">Workflow actions</span></span>

<span data-ttu-id="e1c07-282">Munkafolyamat-műveletek hozzáadásához használja a Finance and Operations **VendMobileInvoiceHeaderDetails** oldalát.</span><span class="sxs-lookup"><span data-stu-id="e1c07-282">To add workflow actions, use the **VendMobileInvoiceHeaderDetails** page in Finance and Operations.</span></span> <span data-ttu-id="e1c07-283">Az oldal megnyitásához cserélje ki a menüpont nevét az URL-címben, mint korábban.</span><span class="sxs-lookup"><span data-stu-id="e1c07-283">To open this page, replace the name of the menu item in the URL, as you did earlier.</span></span> <span data-ttu-id="e1c07-284">Ezután nyissa meg a mobiltervezőt a **Beállítások** (fogaskerék) gombbal.</span><span class="sxs-lookup"><span data-stu-id="e1c07-284">Then open the mobile designer from the **Settings** (gear) button.</span></span> <span data-ttu-id="e1c07-285">Kövesse az alábbi lépéseket munkafolyamat-műveletek hozzáadásához a részletek oldalon.</span><span class="sxs-lookup"><span data-stu-id="e1c07-285">Follow these steps to add workflow actions on the details page.</span></span> <span data-ttu-id="e1c07-286">Olyan Önhöz rendelt számlákkal kell rendelkeznie, amelyek olyan megfelelő állapotban vannak, ami elérhetővé teszi azon munkafolyamat-műveleteket, amelyekhez felületet kíván tervezni.</span><span class="sxs-lookup"><span data-stu-id="e1c07-286">You must have invoices assigned to you that are in the appropriate state to make the workflow actions available to you that you are going to design for.</span></span>

#### <a name="record-workflow-actions"></a><span data-ttu-id="e1c07-287">Munkafolyamat-műveletek rögzítése</span><span class="sxs-lookup"><span data-stu-id="e1c07-287">Record workflow actions</span></span>
1.  <span data-ttu-id="e1c07-288">Kattintson a **Szerkesztés** gombra a munkaterület szerkesztési üzemmódjának elindításához.</span><span class="sxs-lookup"><span data-stu-id="e1c07-288">Click the **Edit** button to start edit mode in the workspace.</span></span>
2.  <span data-ttu-id="e1c07-289">Válassza a korábban elkészített **Számla részletei** oldalt, majd kattintson a **Szerkesztés** elemre.</span><span class="sxs-lookup"><span data-stu-id="e1c07-289">Select the **Invoice details** page that you created earlier, and then click **Edit**.</span></span>
3.  <span data-ttu-id="e1c07-290">A **Műveletek** lapon kattintson a **Művelet hozzáadása** elemre.</span><span class="sxs-lookup"><span data-stu-id="e1c07-290">On the **Actions** tab, click **Add action**.</span></span>
4.  <span data-ttu-id="e1c07-291">Adjon meg egy műveletcímet, például **Jóváhagyás**, és egy leírást, például a **Számla jóváhagyása**.</span><span class="sxs-lookup"><span data-stu-id="e1c07-291">Enter an action title, such as **Approve**, and a description, such as **Approve invoice**.</span></span> <span data-ttu-id="e1c07-292">Fontos megjegyezni, hogy a művelet itt megadott címe lesz a művelet neve, amit a felhasználó a mobilalkalmazásban látni fog.</span><span class="sxs-lookup"><span data-stu-id="e1c07-292">Note that the action title that you enter here becomes the name of the action that is shown to the user in the mobile app.</span></span>
5.  <span data-ttu-id="e1c07-293">Kattintson a **Kész** gombra.</span><span class="sxs-lookup"><span data-stu-id="e1c07-293">Click **Done**.</span></span>
6.  <span data-ttu-id="e1c07-294">Kattintson a **Mezők kijelölése** elemre.</span><span class="sxs-lookup"><span data-stu-id="e1c07-294">Click **Select fields**.</span></span>
7.  <span data-ttu-id="e1c07-295">Menjen végig a munkafolyamaton a **VendMobileInvoiceHeaderDetails** oldalon, és végezze el a rögzíteni kívánt műveletet.</span><span class="sxs-lookup"><span data-stu-id="e1c07-295">Go through the workflow process on the **VendMobileInvoiceHeaderDetails** page, and complete the action that you wanted to record.</span></span> <span data-ttu-id="e1c07-296">Ügyeljen, hogy e folyamat során írjon be megjegyzéseket a munkafolyamathoz annak érdekében, hogy a megjegyzések mező is bekerüljön a mobilfelületre.</span><span class="sxs-lookup"><span data-stu-id="e1c07-296">Make sure that you enter workflow comments during this process, so that a comments field is also included in the mobile experience.</span></span>
8.  <span data-ttu-id="e1c07-297">A munkafolyamat-művelet futtatása után kattintson a **Kész** elemre a Mezőválasztás feladat elvégzéséhez.</span><span class="sxs-lookup"><span data-stu-id="e1c07-297">After the workflow action is run, click **Done** to complete the Select fields task.</span></span>
9.  <span data-ttu-id="e1c07-298">Kattintson a **Kész** elemre a szerkesztés módból való kilépéshez.</span><span class="sxs-lookup"><span data-stu-id="e1c07-298">Click **Done** to exit edit mode.</span></span>
10. <span data-ttu-id="e1c07-299">Kattintson a **Vissza**, majd a **Kész** elemre a munkaterületről való kilépéshez.</span><span class="sxs-lookup"><span data-stu-id="e1c07-299">Click **Back** and then **Done** to exit the workspace</span></span>
11. <span data-ttu-id="e1c07-300">A **Munkaterület közzététele** gombra kattintva mentse el a munkáját</span><span class="sxs-lookup"><span data-stu-id="e1c07-300">Click **Publish workspace** to save your work</span></span>
12. <span data-ttu-id="e1c07-301">Ismételje meg az előző lépéseket az összes szükséges munkafolyamat-művelet rögzítéséhez.</span><span class="sxs-lookup"><span data-stu-id="e1c07-301">Repeat the previous steps to record all the required workflow actions.</span></span> 

#### <a name="create-a-js-file"></a><span data-ttu-id="e1c07-302">.js fájl létrehozása</span><span class="sxs-lookup"><span data-stu-id="e1c07-302">Create a .js file</span></span>
1. <span data-ttu-id="e1c07-303">Nyissa meg a Jegyzettömböt vagy a Microsoft Visual Studio programot, és illessze be a következő kódot.</span><span class="sxs-lookup"><span data-stu-id="e1c07-303">Open Notepad or Microsoft Visual Studio, and paste the following code.</span></span> <span data-ttu-id="e1c07-304">Mentse a fájlt .js fájlként.</span><span class="sxs-lookup"><span data-stu-id="e1c07-304">Save the file as a .js file.</span></span> <span data-ttu-id="e1c07-305">Ez a kód a következőket hajtja végre:</span><span class="sxs-lookup"><span data-stu-id="e1c07-305">This code does the following:</span></span>
    - <span data-ttu-id="e1c07-306">Elrejti a korábban a mobil listaoldalon hozzáadott, a munkafolyamattal kapcsolatos további oszlopokat.</span><span class="sxs-lookup"><span data-stu-id="e1c07-306">It hides the extra workflow-related columns that we added earlier on the mobile list page.</span></span> <span data-ttu-id="e1c07-307">Ezeket az oszlopokat azért adtuk hozzá, hogy az alkalmazás összefüggésben rendelkezzen az információkkal, és meg tudjuk tenni a következő lépést.</span><span class="sxs-lookup"><span data-stu-id="e1c07-307">We added these columns so that the app has that information in context and can do the next step.</span></span>
    - <span data-ttu-id="e1c07-308">Az aktív munkafolyamat-lépés alapján logikát alkalmazva csak az érintett műveleteket jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="e1c07-308">Based on the workflow step that is active, it applies logic to show only those actions.</span></span>

> [!NOTE]
> <span data-ttu-id="e1c07-309">Az oldalak és más vezérlőelemek nevének a JS-kódban és a munkaterületen egyeznie kell.</span><span class="sxs-lookup"><span data-stu-id="e1c07-309">The name of the pages and other controls in the code must be the same as the names in the workspace.</span></span>

    function main(metadataService, dataService, cacheService, $q) {
           return {
               appInit: function (appMetadata) {
                   // Hide controls that need to be present, but not visible
                   metadataService.configureControl('My-vendor-invoices', 'ShowAccept', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowApprove', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowReject', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowDelegate', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowRequestChange', { hidden: true });
                 metadataService.configureControl('My-vendor-invoices', 'ShowRecall', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowComplete', { hidden: true });
               metadataService.configureControl('My-vendor-invoices', 'ShowResubmit', { hidden: true });
               },
               pageInit: function (pageMetadata, params) {
        if (pageMetadata.Name == 'Invoice-details') {
                       // Show/hide workflow actions based on workflow step
                       metadataService.configureAction('Accept', { visible: true });
                       metadataService.configureAction('Approve', { visible: true });
                       metadataService.configureAction('Reject', { visible: true });
                       metadataService.configureAction('Delegate', { visible: true });
                       metadataService.configureAction('Request-change', { visible: true });
                       metadataService.configureAction('Recall', { visible: true });
                       metadataService.configureAction('Complete', { visible: true });
                       metadataService.configureAction('Resubmit', { visible: true });

                       var entityContextParts = params.pageContext.split(':');
                       var data = dataService.getEntityData(entityContextParts[0], entityContextParts[1]);

                       var acceptControl = data.getPropertyValue('VendInvoiceInfoTable/showAccept');
                       var approveControl = data.getPropertyValue('VendInvoiceInfoTable/showApprove');
                       var rejectControl = data.getPropertyValue('VendInvoiceInfoTable/showReject');
                       var delegateControl = data.getPropertyValue('VendInvoiceInfoTable/showDelegate');
                       var requestChangeControl = data.getPropertyValue('VendInvoiceInfoTable/showRequestChange');
                       var recallControl = data.getPropertyValue('VendInvoiceInfoTable/showRecall');
                       var completeControl = data.getPropertyValue('VendInvoiceInfoTable/showComplete');
                       var resubmitControl = data.getPropertyValue('VendInvoiceInfoTable/showResubmit');

                       var showAcceptControl = Boolean(acceptControl == 1);
                       var showApproveControl = Boolean(approveControl == 1);
                       var showRejectControl = Boolean(rejectControl == 1);
                      var showDelegateControl = Boolean(delegateControl == 1);
                       var showRequestChangeControl = Boolean(requestChangeControl == 1);
                       var showRecallControl = Boolean(recallControl == 1);
                       var showCompleteControl = Boolean(completeControl == 1);
                       var showResubmitControl = Boolean(resubmitControl == 1);

                       metadataService.configureAction('Accept', { visible: showAcceptControl });
                       metadataService.configureAction('Approve', { visible: showApproveControl });
                       metadataService.configureAction('Reject', { visible: showRejectControl });
                       metadataService.configureAction('Delegate', { visible: showDelegateControl });
                       metadataService.configureAction('Request-change', { visible: showRequestChangeControl });
                       metadataService.configureAction('Recall', { visible: showRecallControl });
                       metadataService.configureAction('Complete', { visible: showCompleteControl });
                     metadataService.configureAction('Resubmit', { visible: showResubmitControl });
                   }
                 },
           };
        }

2.  <span data-ttu-id="e1c07-310">Töltse fel a kódfájlt a munkaterületre a **Logika** lap kiválasztásával</span><span class="sxs-lookup"><span data-stu-id="e1c07-310">Upload the code file to the workspace by selecting the **Logic** tab</span></span>
3.  <span data-ttu-id="e1c07-311">Kattintson a **Kész** elemre a szerkesztés módból való kilépéshez.</span><span class="sxs-lookup"><span data-stu-id="e1c07-311">Click **Done** to exit edit mode.</span></span>
4.  <span data-ttu-id="e1c07-312">Kattintson a **Vissza**, majd a **Kész** elemre a munkaterületről való kilépéshez.</span><span class="sxs-lookup"><span data-stu-id="e1c07-312">Click **Back** and then **Done** to exit the workspace</span></span>
5.  <span data-ttu-id="e1c07-313">A **Munkaterület közzététele** gombra kattintva mentse el a munkáját</span><span class="sxs-lookup"><span data-stu-id="e1c07-313">Click **Publish workspace** to save your work</span></span>

### <a name="vendor-invoice-attachments"></a><span data-ttu-id="e1c07-314">Szállítói számlamellékletek</span><span class="sxs-lookup"><span data-stu-id="e1c07-314">Vendor invoice attachments</span></span>

1. <span data-ttu-id="e1c07-315">Kattintson a **Beállítások** (fogaskerék) gombra az oldal jobb felső sarkában, majd kattintson a **Mobilalkalmazás** elemre</span><span class="sxs-lookup"><span data-stu-id="e1c07-315">Click the **Settings** (gear) button in the upper right of the page, and then click **Mobile app**</span></span>
2. <span data-ttu-id="e1c07-316">Kattintson a **Szerkesztés** gombra a munkaterület szerkesztési üzemmódjának elindításához.</span><span class="sxs-lookup"><span data-stu-id="e1c07-316">Click the **Edit** button to start edit mode in the workspace.</span></span>
3. <span data-ttu-id="e1c07-317">Válassza a korábban elkészített <strong>Számla részletei \*\*oldalt, majd kattintson a Szerkesztés \*\*</strong> elemre.</span><span class="sxs-lookup"><span data-stu-id="e1c07-317">Select the <strong>Invoice details \*\*page that you created earlier, and then click \*\*Edit</strong>.</span></span>
4. <span data-ttu-id="e1c07-318">Állítsa a **Dokumentumkezelés** lehetőséget **Igen** értékre, ahogy az lent látható.</span><span class="sxs-lookup"><span data-stu-id="e1c07-318">Set the **Document management** option to **Yes** as shown below.</span></span> <span data-ttu-id="e1c07-319">**Megjegyzés:** ha a mellékleteket nem muszáj megjeleníteni a mobileszközön, a beállítást az alapértelmezett **Nem** értéken hagyhatja.</span><span class="sxs-lookup"><span data-stu-id="e1c07-319">**Note:** If there are no requirements to show attachments on the mobile device, you can leave this option set to **No**, which is the default setting.</span></span>
   <span data-ttu-id="e1c07-320">![Dokumentumkezelés](./media/docmanagement-216x300.png)</span><span class="sxs-lookup"><span data-stu-id="e1c07-320">![Document management](./media/docmanagement-216x300.png)</span></span>
5. <span data-ttu-id="e1c07-321">Kattintson a **Kész** elemre a szerkesztés módból való kilépéshez.</span><span class="sxs-lookup"><span data-stu-id="e1c07-321">Click **Done** to exit edit mode.</span></span>
6. <span data-ttu-id="e1c07-322">Kattintson a **Vissza**, majd a **Kész** elemre a munkaterületről való kilépéshez.</span><span class="sxs-lookup"><span data-stu-id="e1c07-322">Click **Back** and then **Done** to exit the workspace</span></span>
7. <span data-ttu-id="e1c07-323">A **Munkaterület közzététele** gombra kattintva mentse el a munkáját</span><span class="sxs-lookup"><span data-stu-id="e1c07-323">Click **Publish workspace** to save your work</span></span>

### <a name="vendor-invoice-line-distributions"></a><span data-ttu-id="e1c07-324">Szállítói számlasorok felosztásai</span><span class="sxs-lookup"><span data-stu-id="e1c07-324">Vendor invoice line distributions</span></span>

<span data-ttu-id="e1c07-325">E forgatókönyv követelményei megerősítik, hogy csak sorszintű felosztások lesznek jelen, és hogy a számláknak mindig csak egy soruk lesz.</span><span class="sxs-lookup"><span data-stu-id="e1c07-325">The requirements for this scenario confirm that there will be only line-level distributions, and that an invoice will always have only one line.</span></span> <span data-ttu-id="e1c07-326">Mivel ez a forgatókönyv egyszerű, a felhasználói felületnek a mobileszközön szintén elég egyszerűnek kell lennie ahhoz, hogy a felhasználónak ne kelljen számos szinten végigásnia magát a felosztások megtekintéséhez.</span><span class="sxs-lookup"><span data-stu-id="e1c07-326">Because this scenario is simple, the user experience on the mobile device must also be simple enough that the user doesn’t have to drill down several levels to view the distributions.</span></span> <span data-ttu-id="e1c07-327">A szállítói számláknál a Finance and Operationsben az összes felosztás megjeleníthető a számlafejlécből.</span><span class="sxs-lookup"><span data-stu-id="e1c07-327">Vendor invoices in Finance and Operations include the option of showing all distributions from the invoice header.</span></span> <span data-ttu-id="e1c07-328">A mobilfelülethez erre a funkcióra van szükségünk.</span><span class="sxs-lookup"><span data-stu-id="e1c07-328">This experience is what we need for the mobile scenario.</span></span> <span data-ttu-id="e1c07-329">Ezért a **VendMobileInvoiceAllDistributionTree** lapot fogjuk használni a mobilfelület ezen részének megtervezéséhez.</span><span class="sxs-lookup"><span data-stu-id="e1c07-329">Therefore, we will use the **VendMobileInvoiceAllDistributionTree** page to design this part of the mobile scenario.</span></span> 

> [!NOTE] 
> <span data-ttu-id="e1c07-330">A követelmények ismerete segít eldönteni, melyik adott oldalt használjuk, és pontosan hogyan optimalizáljuk a mobil felhasználói élményt a felület megtervezése során.</span><span class="sxs-lookup"><span data-stu-id="e1c07-330">Knowing the requirements helps us decide which specific page to use and how exactly to optimize the mobile experience for the user when we design the scenario.</span></span> <span data-ttu-id="e1c07-331">A második forgatókönyv szerint másik oldalt fogunk használni a felosztások megjelenítésére, mivel ennek a forgatókönyvnek a követelményei eltérőek.</span><span class="sxs-lookup"><span data-stu-id="e1c07-331">In the second scenario, we will use a different page to show the distributions, because the requirements for that scenario differ.</span></span>

1.  <span data-ttu-id="e1c07-332">Az URL-ben cserélje ki a menüpont nevét, mint korábban.</span><span class="sxs-lookup"><span data-stu-id="e1c07-332">In the URL, replace the name of the menu item, as you did before.</span></span> <span data-ttu-id="e1c07-333">A megjelenő lapnak az alábbi ábrához kell hasonlítania.</span><span class="sxs-lookup"><span data-stu-id="e1c07-333">The page that appears should resemble the following illustration.</span></span>
<span data-ttu-id="e1c07-334">[![Összes eloszlás oldal](./media/mobile-invoice-approvals06.png)](./media/mobile-invoice-approvals06.png)</span><span class="sxs-lookup"><span data-stu-id="e1c07-334">[![All distributions page](./media/mobile-invoice-approvals06.png)](./media/mobile-invoice-approvals06.png)</span></span>
2.  <span data-ttu-id="e1c07-335">Nyissa meg a mobiltervezőt a **Beállítások** (fogaskerék) gombbal.</span><span class="sxs-lookup"><span data-stu-id="e1c07-335">Open the mobile designer from the **Settings** (gear) button.</span></span>
3.  <span data-ttu-id="e1c07-336">Kattintson a **Szerkesztés** gombra a munkaterület szerkesztési üzemmódjának elindításához.</span><span class="sxs-lookup"><span data-stu-id="e1c07-336">Click the **Edit** button to start edit mode in the workspace.</span></span> <span data-ttu-id="e1c07-337">**Megjegyzés:** látni fogja, hogy két új oldal jön létre automatikusan.</span><span class="sxs-lookup"><span data-stu-id="e1c07-337">**Note:** You will see that two new pages were created automatically.</span></span> <span data-ttu-id="e1c07-338">A rendszer ezeket az oldalakat azért hozza létre, mert az előző részben bekapcsolta a Dokumentumkezelést.</span><span class="sxs-lookup"><span data-stu-id="e1c07-338">The system creates these pages, because you turned on document management in the previous section.</span></span> <span data-ttu-id="e1c07-339">Ezeket az új oldalakat figyelmen kívül hagyhatja.</span><span class="sxs-lookup"><span data-stu-id="e1c07-339">You can ignore these new pages.</span></span>
4.  <span data-ttu-id="e1c07-340">Kattintson az **Oldal hozzáadása** elemre.</span><span class="sxs-lookup"><span data-stu-id="e1c07-340">Click **Add page**.</span></span>
5.  <span data-ttu-id="e1c07-341">Adja meg az oldal címét, például **Könyvelés megtekintése**, és egy leírást, például a **Számla könyvelésének megtekintése**.</span><span class="sxs-lookup"><span data-stu-id="e1c07-341">Enter a page title, such as **View accounting**, and a description, such as **View accounting for the invoice**.</span></span>
6.  <span data-ttu-id="e1c07-342">Kattintson a **Kész** gombra.</span><span class="sxs-lookup"><span data-stu-id="e1c07-342">Click **Done**.</span></span>
7.  <span data-ttu-id="e1c07-343">A **mezők** lapon kattintson a **Mezők kiválasztása** elemre, a felosztások lapon válassza a következő mezőket, és kattintson a **Kész** elemre:</span><span class="sxs-lookup"><span data-stu-id="e1c07-343">On the **Fields** tab, click **Select fields**, select the following fields from the distributions page, and then click **Done**:</span></span>
    1.  <span data-ttu-id="e1c07-344">Összeg</span><span class="sxs-lookup"><span data-stu-id="e1c07-344">Amount</span></span>
    2.  <span data-ttu-id="e1c07-345">Pénznem</span><span class="sxs-lookup"><span data-stu-id="e1c07-345">Currency</span></span>
    3.  <span data-ttu-id="e1c07-346">Főkönyvi számla</span><span class="sxs-lookup"><span data-stu-id="e1c07-346">Ledger account</span></span>

    > [!NOTE] 
    > <span data-ttu-id="e1c07-347">A **Leírás** oszlopot nem választottuk ki a felosztások rácsból, mert ebben az esetben a követelmények megerősítik, hogy a kiterjesztett ár az egyetlen összeg, amelyhez felosztások lesznek elérhetők.</span><span class="sxs-lookup"><span data-stu-id="e1c07-347">We didn’t select the **Description** column from the distributions grid, because the requirements for this scenario confirmed that the extended price is the only amount that there will be distributions for.</span></span> <span data-ttu-id="e1c07-348">Ezért a felhasználónak nem lesz másik mezőre szüksége ahhoz, hogy lássa, milyen típusú összegre vonatkozik a felosztás.</span><span class="sxs-lookup"><span data-stu-id="e1c07-348">Therefore, the user won’t require another field to determine the amount type that the distribution is for.</span></span> <span data-ttu-id="e1c07-349">A következő forgatókönyvben azonban **használni fogjuk** ezt az információt, mivel annak a forgatókönyvnek a követelményei azt mondják, hogy egyéb összegtípusokhoz (például áfához) is lesznek felosztások.</span><span class="sxs-lookup"><span data-stu-id="e1c07-349">However, in the next scenario, we **will** use this information, because the requirements for that scenario specify that other amount types have distributions (for example, sales tax).</span></span>
8.  <span data-ttu-id="e1c07-350">Kattintson a **Kész** elemre a szerkesztés módból való kilépéshez.</span><span class="sxs-lookup"><span data-stu-id="e1c07-350">Click **Done** to exit edit mode.</span></span>
9.  <span data-ttu-id="e1c07-351">Kattintson a **Vissza**, majd a **Kész** elemre a munkaterületről való kilépéshez.</span><span class="sxs-lookup"><span data-stu-id="e1c07-351">Click **Back** and then **Done** to exit the workspace</span></span>
10. <span data-ttu-id="e1c07-352">A **Munkaterület közzététele** gombra kattintva mentse el a munkáját</span><span class="sxs-lookup"><span data-stu-id="e1c07-352">Click **Publish workspace** to save your work</span></span>

> [!NOTE] 
> <span data-ttu-id="e1c07-353">A **Könyvelés megjelenítése** mobillap jelenleg nem hivatkozik az általunk eddig megtervezett egyik mobillapra sem.</span><span class="sxs-lookup"><span data-stu-id="e1c07-353">The **View accounting** mobile page isn’t currently linked to any of the mobile pages that we have designed so far.</span></span> <span data-ttu-id="e1c07-354">Mivel a felhasználónak a mobilkészüléken el kell tudnia navigálnia a **Könyvelés megtekintése** oldalra a **Számla részletei** oldalról, navigációs lehetőséget kell biztosítanunk a **Számla részletei** oldalról a **Könyvelés megtekintése** oldalra.</span><span class="sxs-lookup"><span data-stu-id="e1c07-354">Because the user should be able to navigate to the **View accounting** page from the **Invoice details** page on the mobile device, we must provide navigation from the **Invoice details** page to the **View accounting** page.</span></span> <span data-ttu-id="e1c07-355">Ezt a navigációs lehetőséget további logika használatával hozzuk létre JavaScript segítségével.</span><span class="sxs-lookup"><span data-stu-id="e1c07-355">We establish this navigation by using additional logic via JavaScript.</span></span>

1.  <span data-ttu-id="e1c07-356">Nyissa meg a korábban létrehozott .js fájlt, és adja hozzá a következő kódban kiemelt sorokat.</span><span class="sxs-lookup"><span data-stu-id="e1c07-356">Open the .js file that you created earlier, and add the lines that are highlighted in the following code.</span></span> <span data-ttu-id="e1c07-357">Ezt a kódot két dolgot tesz:</span><span class="sxs-lookup"><span data-stu-id="e1c07-357">This code does two things:</span></span>
    1.  <span data-ttu-id="e1c07-358">Ez segít garantálni, hogy a felhasználók közvetlenül a munkaterületről nem léphetnek a **Könyvelés megtekintése** oldalra.</span><span class="sxs-lookup"><span data-stu-id="e1c07-358">It helps guarantee that users can’t navigate directly from the workspace to the **View accounting** page.</span></span>
    2.  <span data-ttu-id="e1c07-359">Ez létrehoz egy navigációs vezérlőt a **Számla részletei** oldalról a **Könyvelés megtekintése** oldalra.</span><span class="sxs-lookup"><span data-stu-id="e1c07-359">It establishes a navigation control from the **Invoice details** page to the **View accounting** page.</span></span>

> [!NOTE] 
> <span data-ttu-id="e1c07-360">Az oldalak és más vezérlőelemek nevének a JS-kódban és a munkaterületen egyeznie kell.</span><span class="sxs-lookup"><span data-stu-id="e1c07-360">The name of the pages and other controls in the code must be the same as the names in the workspace.</span></span>

    function main(metadataService, dataService, cacheService, $q) {
           return {
               appInit: function (appMetadata) {
                   // Hide controls that need to be present, but not visible
                   metadataService.configureControl('My-vendor-invoices', 'ShowAccept', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowApprove', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowReject', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowDelegate', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowRequestChange', { hidden: true });
                 metadataService.configureControl('My-vendor-invoices', 'ShowRecall', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowComplete', { hidden: true });
               metadataService.configureControl('My-vendor-invoices', 'ShowResubmit', { hidden: true });
                   // Hide pages not applicable for root navigation
                   metadataService.hideNavigation('View-accounting');
                   //Link to view accounting
                   metadataService.addLink('Invoice-details', 'View-accounting', 'View-accounting-nav-control', 'View accounting', true);
               },
               pageInit: function (pageMetadata, params) {
        if (pageMetadata.Name == 'Invoice-details') {
                       // Show/hide workflow actions based on workflow step
                       metadataService.configureAction('Accept', { visible: true });
                       metadataService.configureAction('Approve', { visible: true });
                       metadataService.configureAction('Reject', { visible: true });
                       metadataService.configureAction('Delegate', { visible: true });
                       metadataService.configureAction('Request-change', { visible: true });
                       metadataService.configureAction('Recall', { visible: true });
                       metadataService.configureAction('Complete', { visible: true });
                       metadataService.configureAction('Resubmit', { visible: true });

                       var entityContextParts = params.pageContext.split(':');
                       var data = dataService.getEntityData(entityContextParts[0], entityContextParts[1]);

                       var acceptControl = data.getPropertyValue('VendInvoiceInfoTable/showAccept');
                       var approveControl = data.getPropertyValue('VendInvoiceInfoTable/showApprove');
                       var rejectControl = data.getPropertyValue('VendInvoiceInfoTable/showReject');
                       var delegateControl = data.getPropertyValue('VendInvoiceInfoTable/showDelegate');
                       var requestChangeControl = data.getPropertyValue('VendInvoiceInfoTable/showRequestChange');
                       var recallControl = data.getPropertyValue('VendInvoiceInfoTable/showRecall');
                       var completeControl = data.getPropertyValue('VendInvoiceInfoTable/showComplete');
                       var resubmitControl = data.getPropertyValue('VendInvoiceInfoTable/showResubmit');

                       var showAcceptControl = Boolean(acceptControl == 1);
                       var showApproveControl = Boolean(approveControl == 1);
                     var showRejectControl = Boolean(rejectControl == 1);
                       var showDelegateControl = Boolean(delegateControl == 1);
                       var showRequestChangeControl = Boolean(requestChangeControl == 1);
                       var showRecallControl = Boolean(recallControl == 1);
                       var showCompleteControl = Boolean(completeControl == 1);
                       var showResubmitControl = Boolean(resubmitControl == 1);

                       metadataService.configureAction('Accept', { visible: showAcceptControl });
                       metadataService.configureAction('Approve', { visible: showApproveControl });
                       metadataService.configureAction('Reject', { visible: showRejectControl });
                       metadataService.configureAction('Delegate', { visible: showDelegateControl });
                       metadataService.configureAction('Request-change', { visible: showRequestChangeControl });
                       metadataService.configureAction('Recall', { visible: showRecallControl });
                       metadataService.configureAction('Complete', { visible: showCompleteControl });
                       metadataService.configureAction('Resubmit', { visible: showResubmitControl });
        }
                 },
           };
        }

2.  <span data-ttu-id="e1c07-361">Az előző kód felülírásához töltse fel a kódfájlt a munkaterületre a **Logika** lap kiválasztásával</span><span class="sxs-lookup"><span data-stu-id="e1c07-361">Upload the code file to the workspace by selecting the **Logic** tab to overwrite the previous code</span></span>
3.  <span data-ttu-id="e1c07-362">Kattintson a **Kész** elemre a szerkesztés módból való kilépéshez.</span><span class="sxs-lookup"><span data-stu-id="e1c07-362">Click **Done** to exit edit mode.</span></span>
4.  <span data-ttu-id="e1c07-363">Kattintson a **Vissza**, majd a **Kész** elemre a munkaterületről való kilépéshez.</span><span class="sxs-lookup"><span data-stu-id="e1c07-363">Click **Back** and then **Done** to exit the workspace</span></span>
5.  <span data-ttu-id="e1c07-364">A **Munkaterület közzététele** gombra kattintva mentse el a munkáját</span><span class="sxs-lookup"><span data-stu-id="e1c07-364">Click **Publish workspace** to save your work</span></span>

### <a name="validation"></a><span data-ttu-id="e1c07-365">Ellenőrzés</span><span class="sxs-lookup"><span data-stu-id="e1c07-365">Validation</span></span>

<span data-ttu-id="e1c07-366">A mobilkészüléken nyissa meg az alkalmazást, és csatlakozzon saját Finance and Operations példányához.</span><span class="sxs-lookup"><span data-stu-id="e1c07-366">From your mobile device, open the app, and connect to your Finance and Operations instance.</span></span> <span data-ttu-id="e1c07-367">Ügyeljen, hogy abba a vállalatba jelentkezzen be, amelynél vannak szállítói számlák Önhöz rendelve véleményezésre.</span><span class="sxs-lookup"><span data-stu-id="e1c07-367">Make sure that you sign in to the company where vendor invoices are assigned to you for review.</span></span> <span data-ttu-id="e1c07-368">Ekkor elvileg el tudja elvégezni a következő műveleteket:</span><span class="sxs-lookup"><span data-stu-id="e1c07-368">You should be able to perform the following actions:</span></span>

-   <span data-ttu-id="e1c07-369">Nézze meg a **Jóváhagyásaim** munkaterület.</span><span class="sxs-lookup"><span data-stu-id="e1c07-369">See the **My approvals** workspace.</span></span>
-   <span data-ttu-id="e1c07-370">Jusson el a **Jóváhagyásaim** munkaterületre, és nézze meg a **Saját szállítói számlák** oldalt.</span><span class="sxs-lookup"><span data-stu-id="e1c07-370">Drill into the **My approvals** workspace and see the **My vendor invoices** page.</span></span>
-   <span data-ttu-id="e1c07-371">Jusson el a **Saját szállítói számlák** oldalra, és nézze meg az Önhöz hozzárendelt számlák listáját.</span><span class="sxs-lookup"><span data-stu-id="e1c07-371">Drill into the **My vendor invoices** page and see the list of invoices that are assigned to you.</span></span>
-   <span data-ttu-id="e1c07-372">Lépjen be az egyik számlába, és nézze meg a számla fejlécadatait és a sor részleteit.</span><span class="sxs-lookup"><span data-stu-id="e1c07-372">Drill into one of the invoices, and see the invoice header details and line details.</span></span>
-   <span data-ttu-id="e1c07-373">A részletek oldalon nézze meg a mellékletekre mutató hivatkozást, e hivatkozás segítségével lépjen a mellékletek listájára, és nézze meg a mellékleteket.</span><span class="sxs-lookup"><span data-stu-id="e1c07-373">On the details page, see a link to attachments, and use this link to navigate to the attachments list and view the attachments.</span></span>
-   <span data-ttu-id="e1c07-374">A részletek oldalon nézze meg a **Könyvelés megtekintése** oldalra mutató hivatkozást, e hivatkozás segítségével lépjen a felosztások oldalára, és nézze meg a felosztásokat.</span><span class="sxs-lookup"><span data-stu-id="e1c07-374">On the details page, see a link to the **View accounting** page, and use this link to navigate to the distributions page and view the distributions.</span></span>
-   <span data-ttu-id="e1c07-375">A részletek oldalon kattintson a **Műveletek** menüre a lap alján, és hajtsa végre a munkafolyamat-lépésre vonatkozó munkafolyamat-műveleteket.</span><span class="sxs-lookup"><span data-stu-id="e1c07-375">On the details page, click the **Actions** menu at the bottom, and perform workflow actions that are applicable to the workflow step.</span></span>

## <a name="designing-a-complex-invoice-approval-scenario-for-fabrikam"></a><span data-ttu-id="e1c07-376">Összetett számlajóváhagyási forgatókönyv tervezése a Gyár számára</span><span class="sxs-lookup"><span data-stu-id="e1c07-376">Designing a complex invoice approval scenario for Fabrikam</span></span>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e1c07-377">Változatattribútum</span><span class="sxs-lookup"><span data-stu-id="e1c07-377">Scenario attribute</span></span></th>
<th><span data-ttu-id="e1c07-378">Válasz</span><span class="sxs-lookup"><span data-stu-id="e1c07-378">Answer</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="e1c07-379">A számlafejléc mely mezőit szeretné a felhasználó látni a mobil felületen, és milyen sorrendben?</span><span class="sxs-lookup"><span data-stu-id="e1c07-379">What fields from the invoice header will the user want to see in the mobile experience, and in what order?</span></span></td>
<td><ol>
<li><span data-ttu-id="e1c07-380">Szállító neve</span><span class="sxs-lookup"><span data-stu-id="e1c07-380">Vendor name</span></span></li>
<li><span data-ttu-id="e1c07-381">Számlaösszeg</span><span class="sxs-lookup"><span data-stu-id="e1c07-381">Invoice amount</span></span></li>
<li><span data-ttu-id="e1c07-382">Számlafogadó</span><span class="sxs-lookup"><span data-stu-id="e1c07-382">Invoice account</span></span></li>
<li><span data-ttu-id="e1c07-383">Számla száma</span><span class="sxs-lookup"><span data-stu-id="e1c07-383">Invoice number</span></span></li>
<li><span data-ttu-id="e1c07-384">Számla dátuma</span><span class="sxs-lookup"><span data-stu-id="e1c07-384">Invoice date</span></span></li>
<li><span data-ttu-id="e1c07-385">Számla leírása</span><span class="sxs-lookup"><span data-stu-id="e1c07-385">Invoice description</span></span></li>
<li><span data-ttu-id="e1c07-386">Esedékes</span><span class="sxs-lookup"><span data-stu-id="e1c07-386">Due date</span></span></li>
<li><span data-ttu-id="e1c07-387">Számla pénzneme</span><span class="sxs-lookup"><span data-stu-id="e1c07-387">Invoice currency</span></span></li>
</ol></td>
</tr>
<tr class="even">
<td><span data-ttu-id="e1c07-388">A számlasorok mely mezőit szeretné a felhasználó látni a mobil felületen, és milyen sorrendben?</span><span class="sxs-lookup"><span data-stu-id="e1c07-388">What fields from the invoice lines will the user want to see in the mobile experience, and in what order?</span></span></td>
<td><ol>
<li><span data-ttu-id="e1c07-389">Beszerzési kategória</span><span class="sxs-lookup"><span data-stu-id="e1c07-389">Procurement category</span></span></li>
<li><span data-ttu-id="e1c07-390">Mennyiség</span><span class="sxs-lookup"><span data-stu-id="e1c07-390">Quantity</span></span></li>
<li><span data-ttu-id="e1c07-391">Egységár</span><span class="sxs-lookup"><span data-stu-id="e1c07-391">Unit price</span></span></li>
<li><span data-ttu-id="e1c07-392">Sor nettó összege</span><span class="sxs-lookup"><span data-stu-id="e1c07-392">Line net amount</span></span></li>
<li><span data-ttu-id="e1c07-393">1099-es összeg</span><span class="sxs-lookup"><span data-stu-id="e1c07-393">1099 amount</span></span></li>
</ol></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="e1c07-394">Hány számlasor van a számlán?</span><span class="sxs-lookup"><span data-stu-id="e1c07-394">How many invoice lines are there in an invoice?</span></span> <span data-ttu-id="e1c07-395">Itt alkalmazza a 80-20-as szabályt, és optimalizáljon 80%-ra.</span><span class="sxs-lookup"><span data-stu-id="e1c07-395">Apply the 80-20 rule here, and optimize for the 80 percent.</span></span></td>
<td><span data-ttu-id="e1c07-396">5</span><span class="sxs-lookup"><span data-stu-id="e1c07-396">5</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="e1c07-397">A felhasználók akarnak könyvelési felosztásokat (számlakódolást) látni a mobileszközön ellenőrzések során?</span><span class="sxs-lookup"><span data-stu-id="e1c07-397">Will users want to see accounting distributions (invoice coding) on the mobile device during reviews?</span></span></td>
<td><span data-ttu-id="e1c07-398">Igen</span><span class="sxs-lookup"><span data-stu-id="e1c07-398">Yes</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="e1c07-399">Hány könyvelési felosztás (kiterjesztett ár, áfa, költségek stb.) van egy-egy számlasornál?</span><span class="sxs-lookup"><span data-stu-id="e1c07-399">How many accounting distributions (extended price, sales tax, charges, and so on) are there for an invoice line?</span></span> <span data-ttu-id="e1c07-400">Ismételten alkalmazza a 80-20-as szabályt.</span><span class="sxs-lookup"><span data-stu-id="e1c07-400">Again, apply the 80-20 rule.</span></span></td>
<td><span data-ttu-id="e1c07-401">Kiterjesztett ár: 2 áfa: 2 költség: 2</span><span class="sxs-lookup"><span data-stu-id="e1c07-401">Extended price: 2 Sales tax: 2 Charges: 2</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="e1c07-402">A számlák szintén rendelkeznek könyvelési felosztásokkal a számla fejlécében?</span><span class="sxs-lookup"><span data-stu-id="e1c07-402">Do the invoices also have accounting distributions on the invoice header?</span></span> <span data-ttu-id="e1c07-403">Ha igen, e könyvelési felosztásoknak rendelkezésre kell állniuk a készüléken?</span><span class="sxs-lookup"><span data-stu-id="e1c07-403">If so, should these accounting distributions be available on the device?</span></span></td>
<td><span data-ttu-id="e1c07-404">Nincs használatban</span><span class="sxs-lookup"><span data-stu-id="e1c07-404">Not used</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="e1c07-405">A felhasználók látni szeretnék a számlához tartozó mellékleteket az eszközön?</span><span class="sxs-lookup"><span data-stu-id="e1c07-405">Will users want to see attachments for the invoice on the device?</span></span></td>
<td><span data-ttu-id="e1c07-406">Igen</span><span class="sxs-lookup"><span data-stu-id="e1c07-406">Yes</span></span></td>
</tr>
</tbody>
</table>

### <a name="next-steps"></a><span data-ttu-id="e1c07-407">További lépések</span><span class="sxs-lookup"><span data-stu-id="e1c07-407">Next steps</span></span>

<span data-ttu-id="e1c07-408">A következő változatok elvégezhetők az 1. forgatókönyvhöz a 2. forgatókönyv követelményei alapján.</span><span class="sxs-lookup"><span data-stu-id="e1c07-408">The following variations can be done for scenario 1, based on the requirements for scenario 2.</span></span> <span data-ttu-id="e1c07-409">Ez a szakasz a mobilalkalmazás felhasználói élményének fokozására használható.</span><span class="sxs-lookup"><span data-stu-id="e1c07-409">You can use this section to improve your mobile app experience.</span></span>

1.  <span data-ttu-id="e1c07-410">Mivel a 2. forgatókönyvben több számlasor szükséges, a terv következő módosításai segítenek a mobileszközön a felhasználói élmény optimalizálásában:</span><span class="sxs-lookup"><span data-stu-id="e1c07-410">Because more invoice lines are expected in scenario 2, the following changes to the design will help optimize the user experience on the mobile device:</span></span>
    1.  <span data-ttu-id="e1c07-411">Számlasorok a részletek oldalon történő megjelenítése helyett (mint az 1. forgatókönyvben), a felhasználók itt dönthetnek úgy, hogy a sorokat külön mobiloldalon tekintik meg.</span><span class="sxs-lookup"><span data-stu-id="e1c07-411">Instead of viewing invoice lines on the details page (as in scenario 1), users can choose to view lines on a separate mobile page.</span></span>
    2.  <span data-ttu-id="e1c07-412">Mivel ebben a forgatókönyvben több számlasor szükséges, ha a **VendMobileInvoiceAllDistributionTree** oldalt használjuk a felosztási oldal megtervezéséhez a mobilon (mint az 1. forgatókönyvnél), a felhasználó számára a sorok és a felosztások megfeleltetése nehéz feladat lehet.</span><span class="sxs-lookup"><span data-stu-id="e1c07-412">Because more than one invoice line is expected in this scenario, if the **VendMobileInvoiceAllDistributionTree** page is used to design the distributions page for mobile (as in scenario 1), it might be confusing for the user to correlate lines to distributions.</span></span> <span data-ttu-id="e1c07-413">Ezért használja a **VendMobileInvoiceLineDistributionTree** oldalt a felosztások oldalának megtervezéshez.</span><span class="sxs-lookup"><span data-stu-id="e1c07-413">Therefore, use the **VendMobileInvoiceLineDistributionTree** page to design the distributions page.</span></span>
    3.  <span data-ttu-id="e1c07-414">Ideális esetben ennél a forgatókönyvnél a felosztások egy számlasor kontextusában jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="e1c07-414">Ideally, the distributions should be shown in the context of an invoice line in this scenario.</span></span> <span data-ttu-id="e1c07-415">Ezért győződjön meg arról, hogy a felhasználó eljuthat a kívánt sorig a felosztások oldal megtekintéséhez.</span><span class="sxs-lookup"><span data-stu-id="e1c07-415">Therefore, make sure that the user can drill into a line to see the distributions page.</span></span> <span data-ttu-id="e1c07-416">Hivatkozzon az oldalra az útvonal létrehozásához, mint ahogyan a fejlécnél és a részletező oldalnál tette az 1. forgatókönyvben.</span><span class="sxs-lookup"><span data-stu-id="e1c07-416">Use the page link capability to establish the drill-through, just as you did for the header and details pages in scenario 1.</span></span>

2.  <span data-ttu-id="e1c07-417">Mivel a 2. forgatókönyvben egynél több összegtípus várható a felosztások között (áfa stb.), hasznos lesz megjeleníteni az összeg leírását.</span><span class="sxs-lookup"><span data-stu-id="e1c07-417">Because more than one amount type is expected on the distributions in scenario 2 (sales tax, charges, and so on), it will be useful to show the description of the amount type.</span></span> <span data-ttu-id="e1c07-418">(Ezt az információt az 1. esetben kihagytuk.)</span><span class="sxs-lookup"><span data-stu-id="e1c07-418">(We omitted this information in scenario 1.)</span></span>




