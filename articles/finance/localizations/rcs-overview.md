---
title: Regulatory Configuration Service
description: Ez a témakör áttekintést nyújt a Regulatory Configuration Service (RCS) lehetőségeiről, és bemutatja a szolgáltatáshoz való hozzáférést.
author: JaneA07
ms.date: 04/07/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RCS, Regulatory Configuration Services, Localization
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-02-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 1eeac7217290e0583fcecdf5b4b5b9153d266240
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/11/2021
ms.locfileid: "6019394"
---
# <a name="regulatory-configuration-service"></a><span data-ttu-id="bd4c0-103">Regulatory Configuration Service</span><span class="sxs-lookup"><span data-stu-id="bd4c0-103">Regulatory Configuration Service</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="bd4c0-104">A Regulatory Configuration Service (RCS) önálló tervezői és életciklus-kezelési szolgáltatás a kódmentes/alacsony kódú globalizációs funkciókhoz.</span><span class="sxs-lookup"><span data-stu-id="bd4c0-104">Regulatory Configuration Service (RCS) is a standalone designer and lifecycle management service for no-code/low-code globalization functionality.</span></span> <span data-ttu-id="bd4c0-105">Az RCS lehetővé teszi, hogy a globalizációs felek bővítsék és testreszabják az adózás, az e-számlázás, a hatósági jelentések, a bank és az üzleti dokumentumok globalizációs területeit, anélkül, hogy a fejlesztőket be kell vonni.</span><span class="sxs-lookup"><span data-stu-id="bd4c0-105">RCS lets globalization stakeholders extend and customize key globalization areas of tax, e-invoicing, regulatory reporting, banking, and business documents without having to involve developers.</span></span> <span data-ttu-id="bd4c0-106">Ez a kódmentes/alacsony kódú globalizációs megközelítés a létrehozáshoz vagy a kiterjesztéshez egyszerűbbé, gyorsabbá és költség hatékonyabbá teszi a globalizációt.</span><span class="sxs-lookup"><span data-stu-id="bd4c0-106">This no-code/low-code globalization approach makes globalization easier, faster, and more cost effective to create or extend.</span></span>

<span data-ttu-id="bd4c0-107">Az RCS a következő funkciókat kínálja:</span><span class="sxs-lookup"><span data-stu-id="bd4c0-107">RCS provides the following capabilities:</span></span>

- <span data-ttu-id="bd4c0-108">Az elektronikus jelentés (ER) által biztosított összes funkció támogatása.</span><span class="sxs-lookup"><span data-stu-id="bd4c0-108">Support for all functionality that is provided by Electronic reporting (ER).</span></span>
- <span data-ttu-id="bd4c0-109">Előfeltétele az új globalizációs mikroszolgáltatások konfigurálásának.</span><span class="sxs-lookup"><span data-stu-id="bd4c0-109">A prerequisite to configure new globalization microservices.</span></span>
- <span data-ttu-id="bd4c0-110">Elektronikus számlázás támogatása.</span><span class="sxs-lookup"><span data-stu-id="bd4c0-110">Support for Electronic Invoicing.</span></span> <span data-ttu-id="bd4c0-111">További tájékoztatásért lásd: [Elektronikus számlázás](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-finance/electronic-invoicing-add-on-dynamics-365-ga).</span><span class="sxs-lookup"><span data-stu-id="bd4c0-111">For more information, see [Electronic Invoicing](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-finance/electronic-invoicing-add-on-dynamics-365-ga).</span></span>
- <span data-ttu-id="bd4c0-112">Támogatja az adószámítást.</span><span class="sxs-lookup"><span data-stu-id="bd4c0-112">Supports for Tax Calculation.</span></span> <span data-ttu-id="bd4c0-113">További információ: [Adószolgáltatás](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-finance/tax-service-preview).</span><span class="sxs-lookup"><span data-stu-id="bd4c0-113">For more information, see [Tax service](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-finance/tax-service-preview).</span></span>
- <span data-ttu-id="bd4c0-114">A globalizációs funkció új funkcióinak támogatása, amely egyszerűbbé teszi a többösszetevős funkciók életciklus-kezelését, és további lehetőségeket biztosít a műveletek konfigurálása és a funkcióparaméterek beállítása során.</span><span class="sxs-lookup"><span data-stu-id="bd4c0-114">Support for new globalization feature functionality that simplifies the lifecycle management of multi-component features and provides extra capability to configure actions and set up feature parameters.</span></span> <span data-ttu-id="bd4c0-115">A további tudnivalókat lásd: [Regulatory Configuration Service – egyszerűsített globalizációs funkciókezelés a globalizációs szolgáltatásoknál](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-finance/regulatory-configuration-service-simplified-globalization-feature-management-globalization-services).</span><span class="sxs-lookup"><span data-stu-id="bd4c0-115">For more information, see [Regulatory Configuration Service – simplified globalization feature management for globalization services](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-finance/regulatory-configuration-service-simplified-globalization-feature-management-globalization-services).</span></span>
- <span data-ttu-id="bd4c0-116">Az egyéni konfigurációk központosított közzétételének, tárolásának és megosztásának támogatása a globális tárházban a konfigurálás egyszerűsítése érdekében, a Microsoft Dynamics Lifecycle Services (LCS) használata nélkül.</span><span class="sxs-lookup"><span data-stu-id="bd4c0-116">Support for centralized publication, storage, and sharing of custom configurations in the Global repository to simplify configuration management without requiring the use of Microsoft Dynamics Lifecycle Services (LCS).</span></span>

## <a name="access-rcs"></a><span data-ttu-id="bd4c0-117">RCS-hozzáférés</span><span class="sxs-lookup"><span data-stu-id="bd4c0-117">Access RCS</span></span>

<span data-ttu-id="bd4c0-118">Az RCS szolgáltatásra a [Regulatory Configuration Service](https://marketing.configure.global.dynamics.com/) lapon regisztrálhat, illetve bejelentkezhet oda.</span><span class="sxs-lookup"><span data-stu-id="bd4c0-118">You can sign up for or sign in to RCS from the [Regulatory Configuration Service page](https://marketing.configure.global.dynamics.com/).</span></span>

![RCS feliratkozás és bejelentkezés](media/202103_RCS%20Marketing%20page_updated_1.jpg)

<span data-ttu-id="bd4c0-120">A **Regulatory Configuration Service** oldalon ellenőrizze és fogadja el a szolgáltatás használatára vonatkozó kiegészítő feltételeket, majd válasszon a következő gombok közül:</span><span class="sxs-lookup"><span data-stu-id="bd4c0-120">On the **Regulatory Configuration Service** page, review and accept the supplemental terms and conditions for use of the service, and then select one of the following buttons:</span></span>

- <span data-ttu-id="bd4c0-121">**Regisztrálja magát**, ha első alkalommal használja a szolgáltatást, és egy üzleti e-mail-címet használ a szervezet számára szolgáltatási környezet nyújtásához.</span><span class="sxs-lookup"><span data-stu-id="bd4c0-121">**Sign up** if you're a first-time user of the service, and you're using a business email address to provision your organization a service environment</span></span>
- <span data-ttu-id="bd4c0-122">**Jelentkezzen be**, ha korábban már regisztrált a szolgáltatásra, és szeretné elérni a szervezeti környezetet.</span><span class="sxs-lookup"><span data-stu-id="bd4c0-122">**Sign in** if you've previously signed up for the service, and you want to access your organization environment</span></span>

## <a name="regional-availability"></a><span data-ttu-id="bd4c0-123">Regionális elérhetőség</span><span class="sxs-lookup"><span data-stu-id="bd4c0-123">Regional availability</span></span>

<span data-ttu-id="bd4c0-124">Az RCS általában a következő régiókban érhető el:</span><span class="sxs-lookup"><span data-stu-id="bd4c0-124">RCS is generally available in the following regions:</span></span>

- <span data-ttu-id="bd4c0-125">Amerikai Egyesült Államok</span><span class="sxs-lookup"><span data-stu-id="bd4c0-125">United States</span></span>
- <span data-ttu-id="bd4c0-126">India</span><span class="sxs-lookup"><span data-stu-id="bd4c0-126">India</span></span>
- <span data-ttu-id="bd4c0-127">Franciaország</span><span class="sxs-lookup"><span data-stu-id="bd4c0-127">France</span></span>
- <span data-ttu-id="bd4c0-128">Európa</span><span class="sxs-lookup"><span data-stu-id="bd4c0-128">Europe</span></span>

<span data-ttu-id="bd4c0-129">A régiók teljes listájáért lásd: [Dynamics 365 és Power Platform: Elérhetőség, adatok helye, nyelv és honosítás](https://aka.ms/dynamics_365_international_availability_deck).</span><span class="sxs-lookup"><span data-stu-id="bd4c0-129">For a complete list of regions, see [Dynamics 365 and Power Platform: Availability, data location, language, and localization](https://aka.ms/dynamics_365_international_availability_deck).</span></span>

## <a name="related-rcs-documentation"></a><span data-ttu-id="bd4c0-130">Kapcsolódó RCS-dokumentáció</span><span class="sxs-lookup"><span data-stu-id="bd4c0-130">Related RCS documentation</span></span>

<span data-ttu-id="bd4c0-131">A következő dokumentációban bővebben olvashat a kapcsolódó összetevőkről:</span><span class="sxs-lookup"><span data-stu-id="bd4c0-131">For more information about related components, see the following documentation:</span></span>

- <span data-ttu-id="bd4c0-132">**Globális adattár:**</span><span class="sxs-lookup"><span data-stu-id="bd4c0-132">**Global repository:**</span></span>

    - [<span data-ttu-id="bd4c0-133">ER-konfiguráció létrehozása és feltöltés a globális adattárba</span><span class="sxs-lookup"><span data-stu-id="bd4c0-133">Create ER configuration & upload to Global repo</span></span>](rcs-global-repo-upload.md)
    - [<span data-ttu-id="bd4c0-134">Konfiguráció megosztása a globális adattárban</span><span class="sxs-lookup"><span data-stu-id="bd4c0-134">Share configuration in Global repo</span></span>](rcs-global-repo-share-configuration.md)
    - [<span data-ttu-id="bd4c0-135">Továbbfejlesztett szűrés a globális adattárban</span><span class="sxs-lookup"><span data-stu-id="bd4c0-135">Enhanced filtering in Global repo</span></span>](enhanced-filtering-global-repo.md)
    - [<span data-ttu-id="bd4c0-136">ER-konfigurációk letöltése a globális adattárból</span><span class="sxs-lookup"><span data-stu-id="bd4c0-136">Download ER configurations from the Global repository</span></span>](../../fin-ops-core/dev-itpro/analytics/er-download-configurations-global-repo.md)
    - [<span data-ttu-id="bd4c0-137">Konfigurációk megszüntetése a globális adattárban</span><span class="sxs-lookup"><span data-stu-id="bd4c0-137">Discontinuing configurations in Global repo</span></span>](discontinuing-configurations-rcs-global-repo.md)

- <span data-ttu-id="bd4c0-138">**Globalizációs funkciók:**</span><span class="sxs-lookup"><span data-stu-id="bd4c0-138">**Globalization feature:**</span></span>

    - [<span data-ttu-id="bd4c0-139">Regulatory Configuration Service (RCS) – Globalizációs jellemzők</span><span class="sxs-lookup"><span data-stu-id="bd4c0-139">Regulatory Configuration Service (RCS) - Globalization feature</span></span>](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-finance/regulatory-configuration-service-simplified-globalization-feature-management-globalization-services)