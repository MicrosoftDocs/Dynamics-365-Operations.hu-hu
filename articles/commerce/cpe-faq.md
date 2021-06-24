---
title: Dynamics 365 Commerce értékelési környezet GYIK
description: Ez a témakör válaszokat ad a Microsoft Dynamics 365 Commerce értékelési környezettel kapcsolatos gyakori kérdésekre.
author: v-chgri
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2019-12-10
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: a0c6f82432a4786f23f12122f3806c3b96a05c8f
ms.sourcegitcommit: 74e47075eab2b0b28f82b0d57f439719847ecb01
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/07/2021
ms.locfileid: "6193594"
---
# <a name="dynamics-365-commerce-evaluation-environment-faq"></a><span data-ttu-id="0893e-103">Dynamics 365 Commerce értékelési környezet GYIK</span><span class="sxs-lookup"><span data-stu-id="0893e-103">Dynamics 365 Commerce evaluation environment FAQ</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="0893e-104">Ez a témakör válaszokat ad a Microsoft Dynamics 365 Commerce értékelési környezettel kapcsolatos gyakori kérdésekre.</span><span class="sxs-lookup"><span data-stu-id="0893e-104">This topic provides answers to frequently asked questions about the Microsoft Dynamics 365 Commerce evaluation environment.</span></span>

<span data-ttu-id="0893e-105">**Használható a Commerce értékelési környezet e-kereskedelmi áruházként a jelenleg Retail alkalmazást megvalósító ügyfeleink esetében?**</span><span class="sxs-lookup"><span data-stu-id="0893e-105">**Can we use the Commerce evaluation environment as an e-Commerce storefront for customers that currently implement Retail?**</span></span>

<span data-ttu-id="0893e-106">Szám</span><span class="sxs-lookup"><span data-stu-id="0893e-106">No.</span></span> <span data-ttu-id="0893e-107">A Commerce értékelési környezet csak az értékelésre szolgál.</span><span class="sxs-lookup"><span data-stu-id="0893e-107">The Commerce evaluation environment is only for evaluation.</span></span> <span data-ttu-id="0893e-108">Ha a Retail alkalmazást megvalósító ügyfél számára igényel környezetet, forduljon a Microsofthoz.</span><span class="sxs-lookup"><span data-stu-id="0893e-108">If you require an environment for a customer that implements Retail, contact Microsoft.</span></span>

<span data-ttu-id="0893e-109">**Használható a Commerce értékelési környezet egy Retail alkalmazást megvalósító meglévő alkalmazáson/környezeten az e-kereskedelmi funkciók megvalósítására?**</span><span class="sxs-lookup"><span data-stu-id="0893e-109">**Can the Commerce evaluation environment be used to provision the e-Commerce features on top of an existing application/environment that implements Retail?**</span></span>

<span data-ttu-id="0893e-110">Nem (többnyire).</span><span class="sxs-lookup"><span data-stu-id="0893e-110">No (mostly).</span></span> <span data-ttu-id="0893e-111">A Commerce értékelési összetevők csak olyan környezetekben érhetők el, amelyek megfelelnek az előfeltételekben és a létesítési útmutatóban megadott konfigurációknak.</span><span class="sxs-lookup"><span data-stu-id="0893e-111">The Commerce evaluation components are available only to environments that match the configurations that are specified in the prerequisites and provisioning guide.</span></span> <span data-ttu-id="0893e-112">Ezenkívül a szükséges alapszintű demóadatok nem lesznek elérhetők olyan környezetekben, amelyeknek a kezdeti kiadása korábbi, mint a 10.0.8.</span><span class="sxs-lookup"><span data-stu-id="0893e-112">Additionally, the required base demo data won't be available in environments that were deployed with an initial release that is earlier than 10.0.8.</span></span> 

<span data-ttu-id="0893e-113">**Milyen költségeket von maga után a Commerce értékelési környezet telepítése a Microsoft Azure alkalmazáson a Microsoft Dynamics Lifecycle Services (LCS) segítségével?**</span><span class="sxs-lookup"><span data-stu-id="0893e-113">**What costs are involved in deploying the Commerce evaluation environment on Microsoft Azure via Microsoft Dynamics Lifecycle Services (LCS)?**</span></span>

<span data-ttu-id="0893e-114">Egy hagyományos Dynamics 365 Finance/Dynamics 365 Supply Chain Management/Dynamics 365 Commerce központ demókörnyezete (virtuális gép \[VM\]) fog megjelenni az Azure-előfizetésében.</span><span class="sxs-lookup"><span data-stu-id="0893e-114">A traditional Dynamics 365 Finance/Dynamics 365 Supply Chain Management/Dynamics 365 Commerce headquarters demo environment (virtual machine \[VM\]) will be hosted in your Azure subscription.</span></span> <span data-ttu-id="0893e-115">Az [Azure árkalkulátorral](https://azure.microsoft.com/pricing/calculator/) megbecsülheti ezt a költséget.</span><span class="sxs-lookup"><span data-stu-id="0893e-115">You can use the [Azure pricing calculator](https://azure.microsoft.com/pricing/calculator/) to estimate this cost.</span></span>

<span data-ttu-id="0893e-116">Más összetevők, például a Commerce Scale Unit, a Commerce webhelyépítő és az e-commerce webhely szoftverként, valamint a Microsoft által működtetett „szoftver szolgáltatásként” (SaaS) formájában elérhetővé válik.</span><span class="sxs-lookup"><span data-stu-id="0893e-116">Other components such as Commerce Scale Unit, Commerce site builder, and your e-Commerce site will be available as software as a service (SaaS) and hosted by Microsoft.</span></span>

<span data-ttu-id="0893e-117">**Jelenleg az Azure mely földrajzi régiói támogatottak a Commerce értékelési környezete esetében?**</span><span class="sxs-lookup"><span data-stu-id="0893e-117">**Which Azure geographies are currently supported for the Commerce evaluation environment?**</span></span>

<span data-ttu-id="0893e-118">A Commerce értékelési környezet csak Észak-Amerika területén telepíthető.</span><span class="sxs-lookup"><span data-stu-id="0893e-118">The Commerce evaluation environment can be deployed only in the North America geography.</span></span>

<span data-ttu-id="0893e-119">**Létezik letölthető virtuális merevlemez (VHD), amely rendelkezik a teljes OneBox virtuális számítógép (VM) opcióval?**</span><span class="sxs-lookup"><span data-stu-id="0893e-119">**Is there a downloadable virtual hard disk (VHD) that has the complete OneBox virtual machine (VM) option?**</span></span>

<span data-ttu-id="0893e-120">A Dynamics 365 Commerce és a Commerce Scale Unit teljes mértékben „szoftver szolgáltatásként” (SaaS) elven működnek, és a felhőben tároltak.</span><span class="sxs-lookup"><span data-stu-id="0893e-120">Dynamics 365 Commerce and Commerce Scale Unit are completely software as a service (SaaS) and must be cloud-hosted.</span></span>

<span data-ttu-id="0893e-121">**Meddig használható a Commerce értékelési környezet?**</span><span class="sxs-lookup"><span data-stu-id="0893e-121">**How long can the Commerce evaluation environment be used?**</span></span>

<span data-ttu-id="0893e-122">A Commerce értékelési környezet 30 napos határidőt tartalmaz attól a naptól számítva, amikor a SaaS-összetevők, például a Commerce Scale Unit, a Commerce webhelyépítő és az e-kereskedelmi webhely létesítése megtörtént.</span><span class="sxs-lookup"><span data-stu-id="0893e-122">The Commerce evaluation environment has a 30-day time limit from the date when SaaS components such as Commerce Scale Unit, Commerce site builder, and your e-Commerce site are provisioned.</span></span>

<span data-ttu-id="0893e-123">**Meghosszabbítható a Commerce értékelési környezet időkorlátja?**</span><span class="sxs-lookup"><span data-stu-id="0893e-123">**Can I extend the time limit for my Commerce evaluation environment?**</span></span>

<span data-ttu-id="0893e-124">A határidő meghosszabbítása inkább kivétel a szabályra, és eseti alapon hoznak döntést róla.</span><span class="sxs-lookup"><span data-stu-id="0893e-124">Extension of the time limit is an exception to the norm and is considered on a case-by-case basis.</span></span> <span data-ttu-id="0893e-125">Segítségért forduljon a Microsoft-partnere kapcsolattartójához.</span><span class="sxs-lookup"><span data-stu-id="0893e-125">You should reach out to your Microsoft partner contact for assistance.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0893e-126">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="0893e-126">Additional resources</span></span>

[<span data-ttu-id="0893e-127">Dynamics 365 Commerce értékelési környezet áttekintése</span><span class="sxs-lookup"><span data-stu-id="0893e-127">Dynamics 365 Commerce evaluation environment overview</span></span>](cpe-overview.md)

[<span data-ttu-id="0893e-128">Dynamics 365 Commerce értékelési környezet kiépítése</span><span class="sxs-lookup"><span data-stu-id="0893e-128">Provision a Dynamics 365 Commerce evaluation environment</span></span>](provisioning-guide.md)

[<span data-ttu-id="0893e-129">Dynamics 365 Commerce értékelési környezet konfigurálása</span><span class="sxs-lookup"><span data-stu-id="0893e-129">Configure a Dynamics 365 Commerce evaluation environment</span></span>](cpe-post-provisioning.md)

[<span data-ttu-id="0893e-130">BOPIS konfigurálása Dynamics 365 Commerce értékelési környezetben</span><span class="sxs-lookup"><span data-stu-id="0893e-130">Configure BOPIS in a Dynamics 365 Commerce evaluation environment</span></span>](cpe-bopis.md)

[<span data-ttu-id="0893e-131">Dynamics 365 Commerce értékelési környezet választható funkcióinak konfigurálása</span><span class="sxs-lookup"><span data-stu-id="0893e-131">Configure optional features for a Dynamics 365 Commerce evaluation environment</span></span>](cpe-optional-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]