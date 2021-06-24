---
title: Regulatory Configuration Service
description: Ez a témakör áttekintést nyújt a Regulatory Configuration Service (RCS) lehetőségeiről, és bemutatja a szolgáltatáshoz való hozzáférést.
author: JaneA07
ms.date: 06/04/2021
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
ms.openlocfilehash: 7f946988f124c814452e1774c700d5c7354f39b0
ms.sourcegitcommit: 60afcd85b3b5b9e5e8981ebbb57c0161cf05e54b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/09/2021
ms.locfileid: "6216562"
---
# <a name="regulatory-configuration-service"></a><span data-ttu-id="a1d91-103">Regulatory Configuration Service</span><span class="sxs-lookup"><span data-stu-id="a1d91-103">Regulatory Configuration Service</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a1d91-104">A Regulatory Configuration Service (RCS) önálló tervezői és életciklus-kezelési szolgáltatás a kódmentes/alacsony kódú globalizációs funkciókhoz.</span><span class="sxs-lookup"><span data-stu-id="a1d91-104">Regulatory Configuration Service (RCS) is a standalone designer and lifecycle management service for no-code/low-code globalization functionality.</span></span> <span data-ttu-id="a1d91-105">Az RCS lehetővé teszi, hogy a globalizációs felek bővítsék és testreszabják az adózás, az e-számlázás, a hatósági jelentések, a bank és az üzleti dokumentumok globalizációs területeit, anélkül, hogy a fejlesztőket be kell vonni.</span><span class="sxs-lookup"><span data-stu-id="a1d91-105">RCS lets globalization stakeholders extend and customize key globalization areas of tax, e-invoicing, regulatory reporting, banking, and business documents without having to involve developers.</span></span> <span data-ttu-id="a1d91-106">Ez a kódmentes/alacsony kódú globalizációs megközelítés a létrehozáshoz vagy a kiterjesztéshez egyszerűbbé, gyorsabbá és költség hatékonyabbá teszi a globalizációt.</span><span class="sxs-lookup"><span data-stu-id="a1d91-106">This no-code/low-code globalization approach makes globalization easier, faster, and more cost effective to create or extend.</span></span>

<span data-ttu-id="a1d91-107">Az RCS a következő funkciókat kínálja:</span><span class="sxs-lookup"><span data-stu-id="a1d91-107">RCS provides the following capabilities:</span></span>

- <span data-ttu-id="a1d91-108">Az elektronikus jelentés (ER) által biztosított összes funkció támogatása.</span><span class="sxs-lookup"><span data-stu-id="a1d91-108">Support for all functionality that is provided by Electronic reporting (ER).</span></span>
- <span data-ttu-id="a1d91-109">Előfeltétele az új globalizációs mikroszolgáltatások konfigurálásának.</span><span class="sxs-lookup"><span data-stu-id="a1d91-109">A prerequisite to configure new globalization microservices.</span></span>
- <span data-ttu-id="a1d91-110">Elektronikus számlázás támogatása.</span><span class="sxs-lookup"><span data-stu-id="a1d91-110">Support for Electronic Invoicing.</span></span> <span data-ttu-id="a1d91-111">További tájékoztatásért lásd: [Elektronikus számlázás](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-finance/electronic-invoicing-add-on-dynamics-365-ga).</span><span class="sxs-lookup"><span data-stu-id="a1d91-111">For more information, see [Electronic Invoicing](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-finance/electronic-invoicing-add-on-dynamics-365-ga).</span></span>
- <span data-ttu-id="a1d91-112">Támogatja az adószámítást.</span><span class="sxs-lookup"><span data-stu-id="a1d91-112">Supports for Tax Calculation.</span></span> <span data-ttu-id="a1d91-113">További információ: [Adószolgáltatás](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-finance/tax-service-preview).</span><span class="sxs-lookup"><span data-stu-id="a1d91-113">For more information, see [Tax service](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-finance/tax-service-preview).</span></span>
- <span data-ttu-id="a1d91-114">A globalizációs funkció új funkcióinak támogatása, amely egyszerűbbé teszi a többösszetevős funkciók életciklus-kezelését, és további lehetőségeket biztosít a műveletek konfigurálása és a funkcióparaméterek beállítása során.</span><span class="sxs-lookup"><span data-stu-id="a1d91-114">Support for new globalization feature functionality that simplifies the lifecycle management of multi-component features and provides extra capability to configure actions and set up feature parameters.</span></span> <span data-ttu-id="a1d91-115">A további tudnivalókat lásd: [Regulatory Configuration Service – egyszerűsített globalizációs funkciókezelés a globalizációs szolgáltatásoknál](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-finance/regulatory-configuration-service-simplified-globalization-feature-management-globalization-services).</span><span class="sxs-lookup"><span data-stu-id="a1d91-115">For more information, see [Regulatory Configuration Service – simplified globalization feature management for globalization services](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-finance/regulatory-configuration-service-simplified-globalization-feature-management-globalization-services).</span></span>
- <span data-ttu-id="a1d91-116">Az egyéni konfigurációk központosított közzétételének, tárolásának és megosztásának támogatása a globális tárházban a konfigurálás egyszerűsítése érdekében, a Microsoft Dynamics Lifecycle Services (LCS) használata nélkül.</span><span class="sxs-lookup"><span data-stu-id="a1d91-116">Support for centralized publication, storage, and sharing of custom configurations in the Global repository to simplify configuration management without requiring the use of Microsoft Dynamics Lifecycle Services (LCS).</span></span>

## <a name="access-rcs"></a><span data-ttu-id="a1d91-117">RCS-hozzáférés</span><span class="sxs-lookup"><span data-stu-id="a1d91-117">Access RCS</span></span>

<span data-ttu-id="a1d91-118">Az RCS szolgáltatásra a [Regulatory Configuration Service](https://marketing.configure.global.dynamics.com/) lapon regisztrálhat, illetve bejelentkezhet oda.</span><span class="sxs-lookup"><span data-stu-id="a1d91-118">You can sign up for or sign in to RCS from the [Regulatory Configuration Service page](https://marketing.configure.global.dynamics.com/).</span></span>

![RCS feliratkozás és bejelentkezés](media/202103_RCS%20Marketing%20page_updated_1.jpg)

<span data-ttu-id="a1d91-120">A **Regulatory Configuration Service** oldalon ellenőrizze és fogadja el a szolgáltatás használatára vonatkozó kiegészítő feltételeket, majd válasszon a következő gombok közül:</span><span class="sxs-lookup"><span data-stu-id="a1d91-120">On the **Regulatory Configuration Service** page, review and accept the supplemental terms and conditions for use of the service, and then select one of the following buttons:</span></span>

- <span data-ttu-id="a1d91-121">**Regisztrálja magát**, ha első alkalommal használja a szolgáltatást, és egy üzleti e-mail-címet használ a szervezet számára szolgáltatási környezet nyújtásához.</span><span class="sxs-lookup"><span data-stu-id="a1d91-121">**Sign up** if you're a first-time user of the service, and you're using a business email address to provision your organization a service environment</span></span>
- <span data-ttu-id="a1d91-122">**Jelentkezzen be**, ha korábban már regisztrált a szolgáltatásra, és szeretné elérni a szervezeti környezetet.</span><span class="sxs-lookup"><span data-stu-id="a1d91-122">**Sign in** if you've previously signed up for the service, and you want to access your organization environment</span></span>

## <a name="regional-availability"></a><span data-ttu-id="a1d91-123">Regionális elérhetőség</span><span class="sxs-lookup"><span data-stu-id="a1d91-123">Regional availability</span></span>

<span data-ttu-id="a1d91-124">Az RCS általában a következő régiókban érhető el:</span><span class="sxs-lookup"><span data-stu-id="a1d91-124">RCS is generally available in the following regions:</span></span>

- <span data-ttu-id="a1d91-125">Amerikai Egyesült Államok</span><span class="sxs-lookup"><span data-stu-id="a1d91-125">United States</span></span>
- <span data-ttu-id="a1d91-126">India</span><span class="sxs-lookup"><span data-stu-id="a1d91-126">India</span></span>
- <span data-ttu-id="a1d91-127">Franciaország</span><span class="sxs-lookup"><span data-stu-id="a1d91-127">France</span></span>
- <span data-ttu-id="a1d91-128">Európa</span><span class="sxs-lookup"><span data-stu-id="a1d91-128">Europe</span></span>

<span data-ttu-id="a1d91-129">A régiók teljes listájáért lásd: [Dynamics 365 és Power Platform: Elérhetőség, adatok helye, nyelv és honosítás](https://aka.ms/dynamics_365_international_availability_deck).</span><span class="sxs-lookup"><span data-stu-id="a1d91-129">For a complete list of regions, see [Dynamics 365 and Power Platform: Availability, data location, language, and localization](https://aka.ms/dynamics_365_international_availability_deck).</span></span>

## <a name="rcs-default-company"></a><span data-ttu-id="a1d91-130">RCS alapértelmezett vállalat</span><span class="sxs-lookup"><span data-stu-id="a1d91-130">RCS default company</span></span>

<span data-ttu-id="a1d91-131">Az RCS által használt időtervezési funkciók az összes vállalat között meg vannak osztva.</span><span class="sxs-lookup"><span data-stu-id="a1d91-131">Design time functionality that is used in RCS is shared across all companies.</span></span> <span data-ttu-id="a1d91-132">Nincsenek vállalatspecifikus funkciók.</span><span class="sxs-lookup"><span data-stu-id="a1d91-132">There is no company-specific functionality.</span></span> <span data-ttu-id="a1d91-133">Ezért javasoljuk, hogy az RCS-környezetben egy vállalatot, a **DAT** vállalatot használja.</span><span class="sxs-lookup"><span data-stu-id="a1d91-133">Therefore, we recommend that you use one company, **DAT**, with your RCS environment.</span></span>

<span data-ttu-id="a1d91-134">Bizonyos helyzetekben azonban érdemes az ER-formátumokat egy adott jogi személyhez kapcsolódó paraméterekkel használni.</span><span class="sxs-lookup"><span data-stu-id="a1d91-134">However, in some scenarios, you might want to make ER formats use parameters that are related to a specific legal entity.</span></span> <span data-ttu-id="a1d91-135">Csak ilyen esetben érdemes az alapértelmezett vállalatváltót használni.</span><span class="sxs-lookup"><span data-stu-id="a1d91-135">In these scenarios only, you should use the default company switcher.</span></span> <span data-ttu-id="a1d91-136">Például lásd: [ER-formátum konfigurálása a jogi személyenként meghatározott paraméterek használatára](../../fin-ops-core/dev-itpro/analytics/er-app-specific-parameters-configure-format.md).</span><span class="sxs-lookup"><span data-stu-id="a1d91-136">For an example, see [Configure ER format to use parameters that are specified per legal entity](../../fin-ops-core/dev-itpro/analytics/er-app-specific-parameters-configure-format.md).</span></span>

## <a name="related-rcs-documentation"></a><span data-ttu-id="a1d91-137">Kapcsolódó RCS-dokumentáció</span><span class="sxs-lookup"><span data-stu-id="a1d91-137">Related RCS documentation</span></span>

<span data-ttu-id="a1d91-138">A következő témakörökben bővebben olvashat a kapcsolódó összetevőkről:</span><span class="sxs-lookup"><span data-stu-id="a1d91-138">For more information about related components, see the following topics:</span></span>

- <span data-ttu-id="a1d91-139">**RCS:**</span><span class="sxs-lookup"><span data-stu-id="a1d91-139">**RCS:**</span></span>

    - [<span data-ttu-id="a1d91-140">Hozzon létre ER-konfigurációkat a RCS-ben, és töltse fel őket a globális tárházba</span><span class="sxs-lookup"><span data-stu-id="a1d91-140">Create ER configurations in RCS and upload them to the Global repository</span></span>](rcs-global-repo-upload.md)

- <span data-ttu-id="a1d91-141">**Globális adattár:**</span><span class="sxs-lookup"><span data-stu-id="a1d91-141">**Global repository:**</span></span>

    - [<span data-ttu-id="a1d91-142">ER-konfiguráció létrehozása és feltöltés a globális adattárba</span><span class="sxs-lookup"><span data-stu-id="a1d91-142">Create ER configuration & upload to Global repo</span></span>](rcs-global-repo-upload.md)
    - [<span data-ttu-id="a1d91-143">Konfiguráció megosztása a globális adattárban</span><span class="sxs-lookup"><span data-stu-id="a1d91-143">Share configuration in Global repo</span></span>](rcs-global-repo-share-configuration.md)
    - [<span data-ttu-id="a1d91-144">Továbbfejlesztett szűrés a globális adattárban</span><span class="sxs-lookup"><span data-stu-id="a1d91-144">Enhanced filtering in Global repo</span></span>](enhanced-filtering-global-repo.md)
    - [<span data-ttu-id="a1d91-145">ER-konfigurációk letöltése a globális adattárból</span><span class="sxs-lookup"><span data-stu-id="a1d91-145">Download ER configurations from the Global repository</span></span>](../../fin-ops-core/dev-itpro/analytics/er-download-configurations-global-repo.md)
    - [<span data-ttu-id="a1d91-146">Konfigurációk megszüntetése a globális adattárban</span><span class="sxs-lookup"><span data-stu-id="a1d91-146">Discontinuing configurations in Global repo</span></span>](discontinuing-configurations-rcs-global-repo.md)
    - [<span data-ttu-id="a1d91-147">Regulatory Configuration Service (RCS) – Lifecycle Services (LCS) tárhely kivezetése</span><span class="sxs-lookup"><span data-stu-id="a1d91-147">Regulatory Configuration Service (RCS) – Lifecycle Services (LCS) storage deprecation</span></span>](rcs-lcs-repo-dep-faq.md)

- <span data-ttu-id="a1d91-148">**Globalizációs funkciók:**</span><span class="sxs-lookup"><span data-stu-id="a1d91-148">**Globalization feature:**</span></span>

    - [<span data-ttu-id="a1d91-149">Regulatory Configuration Service (RCS) – Globalizációs jellemzők</span><span class="sxs-lookup"><span data-stu-id="a1d91-149">Regulatory Configuration Service (RCS) - Globalization feature</span></span>](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-finance/regulatory-configuration-service-simplified-globalization-feature-management-globalization-services)


## <a name="troubleshooting-rcs-sign-up"></a><span data-ttu-id="a1d91-150">RCS feliratkozás hibaelhárítása</span><span class="sxs-lookup"><span data-stu-id="a1d91-150">Troubleshooting RCS sign-up</span></span>

<span data-ttu-id="a1d91-151">Ha a szolgáltatási oldalról regisztrál RCS-re, akkor a következő, az Azure Active Directory (Azure AD) szolgáltatással kapcsolatos probléma merülhet fel.</span><span class="sxs-lookup"><span data-stu-id="a1d91-151">When you sign up for RCS from the service page, you might encounter an issue that is related to Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="a1d91-152">A kapott hibaüzenet azt jelzi, hogy az RCS regisztrációja jelenleg ki van kapcsolva, és be kell kapcsolni, mielőtt befejezheti a regisztrációt.</span><span class="sxs-lookup"><span data-stu-id="a1d91-152">The error message that you receive indicates that sign-up for RCS is currently turned off and must be turned on before you can complete the sign-up process.</span></span>

![RCS -regisztráció hibaüzenete](media/01_RCSSignUpError.jpg)

<span data-ttu-id="a1d91-154">A probléma oka az, hogy blokkolva van az ad hoc előfizetés regisztrációja, ezért az `AllowAdHocSubscriptions` tulajdonságot engedélyezni kell a bérlőben.</span><span class="sxs-lookup"><span data-stu-id="a1d91-154">The issue occurs because you're blocked from signing up for ad-hoc subscriptions, and the `AllowAdHocSubscriptions` property must be enabled in your tenant.</span></span> 

- <span data-ttu-id="a1d91-155">Ha az IT részleg kezeli a szervezet Azure-bérlőit, vegye fel a kapcsolatot az osztállyal, és jelentse a problémát.</span><span class="sxs-lookup"><span data-stu-id="a1d91-155">If your IT department manages your organization's Azure tenants, contact that department to report the issue.</span></span>
- <span data-ttu-id="a1d91-156">Ha Ön felelős az Azure-bérlők kezeléséért, a problémákat javíthatja a [Mi az Önálló Azure Active Directory-regisztráció](/azure/active-directory/enterprise-users/directory-self-service-signup#how-do-i-control-self-service-settings) rész lépéseivel.</span><span class="sxs-lookup"><span data-stu-id="a1d91-156">If you're responsible for managing your Azure tenants, you can fix the issues by following the steps in [What is self-service sign-up for Azure Active Directory](/azure/active-directory/enterprise-users/directory-self-service-signup#how-do-i-control-self-service-settings).</span></span>
