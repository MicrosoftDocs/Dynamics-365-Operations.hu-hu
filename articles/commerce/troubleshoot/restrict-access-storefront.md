---
title: Az üzlethez való hozzáférés korlátozása tesztelés vagy fejlesztés során
description: Ez a témakör leírja, hogyan korlátozhatja a hozzáférést a Microsoft Dynamics 365 Commerce-üzlethez belső tesztelés vagy fejlesztés során.
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
ms.openlocfilehash: 2cdf131048e0fac940475322294ed99e76c0a53b
ms.sourcegitcommit: 6c108be3378b365e6ec596a1a8666d59b758db25
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/12/2021
ms.locfileid: "5585361"
---
# <a name="restrict-access-to-a-storefront-during-testing-or-development"></a><span data-ttu-id="a6641-103">Az üzlethez való hozzáférés korlátozása tesztelés vagy fejlesztés során</span><span class="sxs-lookup"><span data-stu-id="a6641-103">Restrict access to a storefront during testing or development</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="a6641-104">Ez a témakör leírja, hogyan korlátozhatja a hozzáférést a Microsoft Dynamics 365 Commerce-üzlethez belső tesztelés vagy fejlesztés során.</span><span class="sxs-lookup"><span data-stu-id="a6641-104">This topic explains how to restrict access to a Microsoft Dynamics 365 Commerce storefront while internal testing or development is occurring.</span></span>

## <a name="description"></a><span data-ttu-id="a6641-105">Leírás</span><span class="sxs-lookup"><span data-stu-id="a6641-105">Description</span></span>

<span data-ttu-id="a6641-106">Belső tesztelés vagy aktív fejlesztés során érdemes korlátozni a webhelyhez való hozzáférést, hogy a külső felhasználók ne férjenek hozzá a közzétett üzletoldalakhoz.</span><span class="sxs-lookup"><span data-stu-id="a6641-106">During internal testing or active development, you might want to restrict access to your site to prevent external users from accessing the published storefront pages.</span></span>

## <a name="resolution"></a><span data-ttu-id="a6641-107">Felbontás</span><span class="sxs-lookup"><span data-stu-id="a6641-107">Resolution</span></span>

### <a name="set-up-azure-ad-b2c-by-using-standard-user-flows"></a><span data-ttu-id="a6641-108">Azure AD B2C beállítása szokásos felhasználói folyamatok használatával</span><span class="sxs-lookup"><span data-stu-id="a6641-108">Set up Azure AD B2C by using standard user flows</span></span>

<span data-ttu-id="a6641-109">Az Azure Active Directory B2C (Azure AD B2C) rendszer e-kereskedelmi webhelyhez való beállítását lásd: [B2C-bérlő beállítása a Commerce alkalmazásban](../set-up-b2c-tenant.md).</span><span class="sxs-lookup"><span data-stu-id="a6641-109">For information about how to configure Azure Active Directory B2C (Azure AD B2C) for your e-commerce site, see [Set up a B2C tenant in Commerce](../set-up-b2c-tenant.md).</span></span>

### <a name="restrict-user-access-to-storefront-pages-and-block-the-creation-of-new-users"></a><span data-ttu-id="a6641-110">Az üzletoldalak felhasználói elérésének korlátozása és új felhasználók létrehozásának blokkolása</span><span class="sxs-lookup"><span data-stu-id="a6641-110">Restrict user access to storefront pages and block the creation of new users</span></span>

<span data-ttu-id="a6641-111">A Commerce webhelyszerkesztőben a következő lépésekkel korlátozhatja a felhasználók hozzáférését az üzletoldalakhoz.</span><span class="sxs-lookup"><span data-stu-id="a6641-111">To restrict user access to storefront pages in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="a6641-112">Nyissa meg a webhelyét.</span><span class="sxs-lookup"><span data-stu-id="a6641-112">Go to your site.</span></span>
1. <span data-ttu-id="a6641-113">Válassza ki az **Oldalak** lehetőséget, majd válassza ki azt az oldalt, amelyre korlátozni kell a felhasználói hozzáférést.</span><span class="sxs-lookup"><span data-stu-id="a6641-113">Select **Pages**, and then select the page to restrict user access for.</span></span>
1. <span data-ttu-id="a6641-114">Válassza ki a modult vagy a részlethelyet, majd válassza a **Szerkesztés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a6641-114">Select the module or fragment slot, and then select **Edit**.</span></span>
1. <span data-ttu-id="a6641-115">A tulajdonságok ablaktáblában válassza a **Bejelentkezés szükséges?** jelölőnégyzetet, majd válassza a **Szerkesztés befejezése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a6641-115">In the properties pane, select **Requires sign-in?**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="a6641-116">Válassza a **Közzététel** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a6641-116">Select **Publish**.</span></span>

<span data-ttu-id="a6641-117">A következő lépések szerint tilthatja le új felhasználók létrehozását az Azure AD szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="a6641-117">To block the creation of new users in Azure AD, follow these steps.</span></span>

1. <span data-ttu-id="a6641-118">Lépjen ide: [Azure Portal](https://portal.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="a6641-118">Go to the [Azure portal](https://portal.azure.com/).</span></span>
1. <span data-ttu-id="a6641-119">Válassza ki a webhely elérése érdekében létrehozott Azure AD B2C-alkalmazást.</span><span class="sxs-lookup"><span data-stu-id="a6641-119">Select the Azure AD B2C application that you created for your site access.</span></span>
1. <span data-ttu-id="a6641-120">A bal oldali navigációs részben válassza ki a **Felhasználói folyamatok** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a6641-120">In the left navigation, select **User flows**.</span></span>
1. <span data-ttu-id="a6641-121">A **Felhasználói folyamatok** oldal tetején válassza az **Új felhasználói folyamat** elemet.</span><span class="sxs-lookup"><span data-stu-id="a6641-121">At the top of the **User Flows** page, select **New user flow**.</span></span>
1. <span data-ttu-id="a6641-122">A **Felhasználói folyamattípus kiválasztása** oldalon válassza az **Előzetes verzió** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a6641-122">On the **Select a user flow type** page, select **Preview**.</span></span>
1. <span data-ttu-id="a6641-123">A lap középső részén válassza ki a **v2 bejelentkezés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a6641-123">In the middle of the page, select **Sign in v2**.</span></span> <span data-ttu-id="a6641-124">Ezután a [B2C-bérlő beállítása a Commerce alkalmazásban](../set-up-b2c-tenant.md) fejezet lépéseit követve konfigurálhatja a folyamatot a webhelye általános felhasználói folyamataként az Azure AD B2C számára a tesztelés vagy fejlesztés során.</span><span class="sxs-lookup"><span data-stu-id="a6641-124">Then follow the steps in [Set up a B2C tenant in Commerce](../set-up-b2c-tenant.md) to configure the flow as your site's standard user flow for Azure AD B2C during testing or development.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a6641-125">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="a6641-125">Additional resources</span></span>

[<span data-ttu-id="a6641-126">B2C-bérlő beállítása a Commerce alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="a6641-126">Set up a B2C tenant in Commerce</span></span>](../set-up-b2c-tenant.md)

[<span data-ttu-id="a6641-127">Felhasználói bejelentkezéshez használt egyéni oldalak beállítása</span><span class="sxs-lookup"><span data-stu-id="a6641-127">Set up custom pages for user sign-ins</span></span>](../custom-pages-user-logins.md)
