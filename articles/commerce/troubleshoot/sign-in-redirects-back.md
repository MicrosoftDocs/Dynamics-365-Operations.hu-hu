---
title: Bejelentkezési hivatkozás egy e-kereskedelmi webhelyre irányít át
description: Ez a témakör olyan hibaelhárítási útmutatást tartalmaz, amely segítséget nyújt abban az esetben, ha egy bejelentkezési hivatkozás a bejelentkezési oldalra való ugrás helyett az e-kereskedelmi webhelyre irányít vissza.
author: Reza-Assadi
manager: AnnBe
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 36f10c9f68570a6c67da6b4b6e4155f4634f633a
ms.sourcegitcommit: 6c108be3378b365e6ec596a1a8666d59b758db25
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/12/2021
ms.locfileid: "5585349"
---
# <a name="sign-in-link-redirects-back-to-an-e-commerce-site"></a><span data-ttu-id="d6ba4-103">Bejelentkezési hivatkozás egy e-kereskedelmi webhelyre irányít át</span><span class="sxs-lookup"><span data-stu-id="d6ba4-103">Sign-in link redirects back to an e-commerce site</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="d6ba4-104">Ez a témakör olyan hibaelhárítási útmutatást tartalmaz, amely segítséget nyújt abban az esetben, ha egy bejelentkezési hivatkozás a bejelentkezési oldalra való ugrás helyett az e-kereskedelmi webhelyre irányít vissza.</span><span class="sxs-lookup"><span data-stu-id="d6ba4-104">This topic provides troubleshooting guidance that can help when a sign-in link redirects back to the e-commerce site instead of going to the sign-in page.</span></span>

## <a name="description"></a><span data-ttu-id="d6ba4-105">Leírás</span><span class="sxs-lookup"><span data-stu-id="d6ba4-105">Description</span></span>

<span data-ttu-id="d6ba4-106">Miután konfigurált egy új Microsoft Azure Active Directory B2C (Azure AD B2C) bérlőt a Commerce webhelyszerkesztőben, a **Bejelentkezés** hivatkozást kiválasztó felhasználókat a rendszer úgy irányítja vissza a fő e-kereskdelmi kezdőlapra, hogy nem lép tovább a bejelentkezési oldalra.</span><span class="sxs-lookup"><span data-stu-id="d6ba4-106">After you configure a new Microsoft Azure Active Directory B2C (Azure AD B2C) tenant in Commerce site builder, users who select the **Sign in** link are redirected back to the main e-commerce landing page without going to the sign-in page.</span></span>

## <a name="resolution"></a><span data-ttu-id="d6ba4-107">Felbontás</span><span class="sxs-lookup"><span data-stu-id="d6ba4-107">Resolution</span></span>

### <a name="confirm-that-the-reply-url-is-correctly-configured-in-the-azure-ad-b2c-application"></a><span data-ttu-id="d6ba4-108">Győződjön meg arról, hogy a válasz URL helyesen legyen konfigurálva az Azure AD B2C alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="d6ba4-108">Confirm that the reply URL is correctly configured in the Azure AD B2C application</span></span>

<span data-ttu-id="d6ba4-109">Kövesse az alábbi lépéseket, hogy meggyőződjön arról, hogy a válasz URL helyesen legyen konfigurálva az Azure AD B2C alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="d6ba4-109">To confirm that the reply URL is correctly configured in the Azure AD B2C application, follow these steps.</span></span>

1. <span data-ttu-id="d6ba4-110">Lépjen ide: [Azure Portal](https://portal.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="d6ba4-110">Go to the [Azure portal](https://portal.azure.com/).</span></span>
1. <span data-ttu-id="d6ba4-111">Válassza ki a webhely elérése érdekében létrehozott Azure AD B2C-alkalmazást.</span><span class="sxs-lookup"><span data-stu-id="d6ba4-111">Select the Azure AD B2C application that you created for your site access.</span></span>
1. <span data-ttu-id="d6ba4-112">Válassza ki az Azure AD B2C beállítása során létrehozott alkalmazást.</span><span class="sxs-lookup"><span data-stu-id="d6ba4-112">Select the application that you created during the Azure AD B2C setup.</span></span>
1. <span data-ttu-id="d6ba4-113">A **Válasz URL** pontban győződjön meg arról, hogy a lista a webhely tartományának URL-címét és az e-kereskedelem által generált URL-címet is tartalmazza, amint azt az alábbi ábra mutatja.</span><span class="sxs-lookup"><span data-stu-id="d6ba4-113">Under **Reply URL**, make sure that the list includes entries for both the site domain URL and the e-commerce-generated URL, as shown in the example in the following illustration.</span></span>

    ![Azure AD B2C válasz URL bejegyzései](media/aad-b2c-reply-url.jpg)

> [!NOTE]
> <span data-ttu-id="d6ba4-115">A webhelytartomány URL-címének és az e-kereskedelem által generált URL-címnek egyaránt érvényes URL-formátummal kell rendelkeznie, amely nem tartalmaz vezető vagy záró perjeleket.</span><span class="sxs-lookup"><span data-stu-id="d6ba4-115">Both the site domain URL and the e-commerce-generated URL must be in a valid URL format that doesn't include leading or trailing slashes.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d6ba4-116">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="d6ba4-116">Additional resources</span></span>

[<span data-ttu-id="d6ba4-117">Webalkalmazás regisztrálása az Azure Active Directory B2C alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="d6ba4-117">Register a web application in Azure Active Directory B2C</span></span>](https://docs.microsoft.com/azure/active-directory-b2c/tutorial-register-applications?tabs=app-reg-ga#register-a-web-application)

[<span data-ttu-id="d6ba4-118">B2C-bérlő beállítása a Commerce alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="d6ba4-118">Set up a B2C tenant in Commerce</span></span>](../set-up-b2c-tenant.md)
