---
title: Nem konfigurálható biztonsági csoport a Commerce webhelyszerkesztő számára a kezdeti telepítés során
description: Ez a témakör olyan hibaelhárítási útmutatást tartalmaz, amely segítséget nyújt abban az esetben, ha a Commerce webhelyszerkesztő Microsoft Azure Active Directory (Azure AD) biztonsági csoportja nem jelenik meg lehetőségként, amikor az új e-kereskedelmi bérlő első telepítésekor létrehozza az e-kereskedelmi összetevőket a Microsoft Dynamics Lifecycle Services (LCS) alkalmazásban.
author: Reza-Assadi
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
ms.author: shajain
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: aa00e9331693600ced2f4ead399a0c005b77ad08
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5801507"
---
# <a name="cant-configure-a-security-group-for-commerce-site-builder-during-initial-deployment"></a><span data-ttu-id="fecc7-103">Nem konfigurálható biztonsági csoport a Commerce webhelyszerkesztő számára a kezdeti telepítés során</span><span class="sxs-lookup"><span data-stu-id="fecc7-103">Can't configure a security group for Commerce site builder during initial deployment</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="fecc7-104">Ez a témakör olyan hibaelhárítási útmutatást tartalmaz, amely segítséget nyújt abban az esetben, ha a Commerce webhelyszerkesztő Microsoft Azure Active Directory (Azure AD) biztonsági csoportja nem jelenik meg lehetőségként, amikor az új e-kereskedelmi bérlő első telepítésekor létrehozza az e-kereskedelmi összetevőket a Microsoft Dynamics Lifecycle Services (LCS) alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="fecc7-104">This topic provides troubleshooting guidance that can help when the Microsoft Azure Active Directory (Azure AD) security group for Commerce site builder doesn't appear as an option when you create e-commerce components in Microsoft Dynamics Lifecycle Services (LCS) during initial deployment of a new e-commerce tenant.</span></span>

## <a name="description"></a><span data-ttu-id="fecc7-105">Leírás</span><span class="sxs-lookup"><span data-stu-id="fecc7-105">Description</span></span>

<span data-ttu-id="fecc7-106">Amikor az e-kereskedelmi összetevőket a Commerce webhelyszerkesztő összetevőt tartalmazó új e-kereskedelmi bérlő telepítés részeként hozza létre, az Azure AD biztonsági csoport nem jelenik meg lehetőségként a párbeszédpanelen.</span><span class="sxs-lookup"><span data-stu-id="fecc7-106">When you create the e-commerce components as part of the process of deploying a new e-commerce tenant that includes the Commerce site builder component, the Azure AD security group doesn't appear as an option in the dialog box.</span></span>

## <a name="resolution"></a><span data-ttu-id="fecc7-107">Felbontás</span><span class="sxs-lookup"><span data-stu-id="fecc7-107">Resolution</span></span>

### <a name="provision-the-e-commerce-site-with-a-user-in-the-correct-tenant"></a><span data-ttu-id="fecc7-108">Az e-kereskedelmi webhely telepítése a megfelelő bérlőben található felhasználóval</span><span class="sxs-lookup"><span data-stu-id="fecc7-108">Provision the e-commerce site with a user in the correct tenant</span></span>

1. <span data-ttu-id="fecc7-109">Lépjen ide: [Azure Portal](https://portal.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="fecc7-109">Go to the [Azure portal](https://portal.azure.com/).</span></span>
1. <span data-ttu-id="fecc7-110">Azon bérlőnél, akinek az e-kereskedelmi webhelyére vonatkozó LCS-projektet létesítették, kövesse az [Alapcsoport létrehozása és tagok hozzáadása az Azure Active Directory segítségével](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal) pontban leírt utasításokat.</span><span class="sxs-lookup"><span data-stu-id="fecc7-110">Under the tenant that the LCS project for your e-commerce site was provisioned for, follow the instructions in [Create a basic group and add members using Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal).</span></span>
1. <span data-ttu-id="fecc7-111">Lépejen az [LCS](https://lcs.dynamics.com/) oldalára, és jelentkezzen be egy olyan fiók használatával, amely ugyanazt a bérlőt használja, mint a most létrehozott Azure AD biztonsági csoport.</span><span class="sxs-lookup"><span data-stu-id="fecc7-111">Go to [LCS](https://lcs.dynamics.com/), and sign in by using an account that shares the same tenant as the Azure AD security group that you just created.</span></span> <span data-ttu-id="fecc7-112">A fióknak hozzáféréssel kell rendelkeznie az Azure AD biztonsági csoport megtekintéséhez.</span><span class="sxs-lookup"><span data-stu-id="fecc7-112">The account must have access to view the Azure AD security group.</span></span>
1. <span data-ttu-id="fecc7-113">A beállításoknak megfelelően konfigurálhatja az e-kereskedelmi webhelyet.</span><span class="sxs-lookup"><span data-stu-id="fecc7-113">Complete the setup steps to configure the e-commerce site.</span></span> <span data-ttu-id="fecc7-114">Az e-kereskedelmi összetevők telepítésekor a biztonsági csoportnak lehetőségként kell megjelennie a párbeszédpanelen.</span><span class="sxs-lookup"><span data-stu-id="fecc7-114">When you provision the e-commerce components, the security group should now appear as an option in the dialog box.</span></span>

> [!NOTE]
> <span data-ttu-id="fecc7-115">Annak érdekében, hogy a párbeszédpanel mezője fel legyen töltve a biztonsági csoportok listájával, válassza az **Enter** gombot a létrehozott Azure AD biztonsági csoport nevének beírása után.</span><span class="sxs-lookup"><span data-stu-id="fecc7-115">To ensure that the field in the dialog box is filled with the list of security groups, you must select **Enter** after you enter the name of the Azure AD security group that you created.</span></span> <span data-ttu-id="fecc7-116">A keresési eredmények felsorolják azokat az Azure AD biztonsági csoportokat, amelyek a keresési szöveggel kezdődnek, és amelyekhez a felhasználónak hozzáférése van.</span><span class="sxs-lookup"><span data-stu-id="fecc7-116">The search results will list all the Azure AD security groups that start with the search text, and that the user has access to.</span></span> <span data-ttu-id="fecc7-117">Rövidebb keresési kifejezés használatával bővebb keresési eredményeket elérhet.</span><span class="sxs-lookup"><span data-stu-id="fecc7-117">You can use a shorter search term to allow for broader search results.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="fecc7-118">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="fecc7-118">Additional resources</span></span>

[<span data-ttu-id="fecc7-119">Alapcsoport létrehozása és tagok hozzáadása az Azure Active Directory segítségével</span><span class="sxs-lookup"><span data-stu-id="fecc7-119">Create a basic group and add members using Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)

[<span data-ttu-id="fecc7-120">Új e-kereskedelmi bérlő telepítése</span><span class="sxs-lookup"><span data-stu-id="fecc7-120">Deploy a new e-commerce tenant</span></span>](../deploy-ecommerce-site.md)
