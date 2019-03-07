---
title: A felhasználó nem található az Attract vagy Onboard Személyválasztójában
description: Ez a témakör bemutatja, mi a teendő, amikor a felhasználók a vállalati példányában nem jelenik meg az Személyválasztóban Dynamics 365 for Talent Attract vagy Onboard alkalmazásokban.
author: ChrisChua
manager: AnnBe
ms.date: 01/22/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: chrichua
ms.search.validFrom: 2019-01-22
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 2d4a74ee2cc65153c1f9fdc1b42c2fc440d188d6
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "304744"
---
# <a name="azure-active-directory-users-not-found-in-people-picker"></a><span data-ttu-id="262fd-103">Azure Active Directory-felhasználók nem találhatók a Személyválasztó szolgáltatásban</span><span class="sxs-lookup"><span data-stu-id="262fd-103">Azure Active Directory users not found in People Picker</span></span>

[!include [banner](includes/banner.md)]

## <a name="issue"></a><span data-ttu-id="262fd-104">Kibocsátás</span><span class="sxs-lookup"><span data-stu-id="262fd-104">Issue</span></span>

<span data-ttu-id="262fd-105">Egyes érvényes felhasználók a Microsoft Azure Active Directory (Azure AD) a bérlőnek nem jelennek meg a Személyválasztóban a név keresésekor a Dynamics 365 for Talent Attract vagy Onboard alkalmazásokban.</span><span class="sxs-lookup"><span data-stu-id="262fd-105">Certain valid users in Microsoft Azure Active Directory (Azure AD) for the tenant do not appear when searching for the name in the People Picker in the Dynamics 365 for Talent Attract or Onboard applications.</span></span>

## <a name="cause"></a><span data-ttu-id="262fd-106">Ok</span><span class="sxs-lookup"><span data-stu-id="262fd-106">Cause</span></span>

<span data-ttu-id="262fd-107">Bizonyos felhasználótípusok jelenleg nem támogatottak a Attract és Onboard alkalmazásokban.</span><span class="sxs-lookup"><span data-stu-id="262fd-107">Certain user types are not currently supported in the Attract and Onboard applications.</span></span> <span data-ttu-id="262fd-108">Győződjön meg róla, hogy a felhasználó nem egy Azure AD Business to Business (B2B) vendégfelhasználó.</span><span class="sxs-lookup"><span data-stu-id="262fd-108">Verify that the user is not an Azure AD Business to Business (B2B) guest user.</span></span> <span data-ttu-id="262fd-109">A „Felhasználó típusa” információk az Azure Active Directory lapon találhatók az Azure portálon.</span><span class="sxs-lookup"><span data-stu-id="262fd-109">"User Type" information can be found in the Azure Active Directory blade on the Azure portal.</span></span>

<span data-ttu-id="262fd-110">Az Azure B2B-vel kapcsolatos további tudnivalókat lásd: [Mi a vendég felhasználói hozzáférés az Azure Active Directory B2B-ben](https://docs.microsoft.com/en-us/azure/active-directory/b2b/what-is-b2b).</span><span class="sxs-lookup"><span data-stu-id="262fd-110">For more information about Azure B2B, see [What is guest user access in Azure Active Directory B2B](https://docs.microsoft.com/en-us/azure/active-directory/b2b/what-is-b2b).</span></span>

<span data-ttu-id="262fd-111">Nem B2B felhasználóknak bizonyos felhasználók esetében hiányos„Felhasználótípus” tulajdonság lehet a **Felhasználó** objektumban.</span><span class="sxs-lookup"><span data-stu-id="262fd-111">For non-B2B users, there are certain users who may have an incomplete "User Type" property on the **User** object.</span></span> <span data-ttu-id="262fd-112">Ez ellenőrizhető és javítható az Azure AD Powershell modul használatával.</span><span class="sxs-lookup"><span data-stu-id="262fd-112">This can be verified and fixed using the Azure AD Powershell module.</span></span> <span data-ttu-id="262fd-113">További tájékoztatást a következő témakörben talál: [Azure AD](https://docs.microsoft.com/en-us/powershell/module/azuread/?view=azureadps-2.0).</span><span class="sxs-lookup"><span data-stu-id="262fd-113">For more information, see [Azure AD](https://docs.microsoft.com/en-us/powershell/module/azuread/?view=azureadps-2.0).</span></span>

## <a name="resolution"></a><span data-ttu-id="262fd-114">Feloldás</span><span class="sxs-lookup"><span data-stu-id="262fd-114">Resolution</span></span>

<span data-ttu-id="262fd-115">A probléma megoldásához a következő lépések végrehajtásával szüksége lesz „Globális rendszergazda” engedélyekre za Azure Active Directory bérlőben vagy a **User.ReadWrite.All** engedélyekre.</span><span class="sxs-lookup"><span data-stu-id="262fd-115">To complete the following steps to resolve the issue, you will need to have "Global Administrator" permissions on the Azure Active Directory tenant or permissions for **User.ReadWrite.All**.</span></span>

<span data-ttu-id="262fd-116">A „Felhasználótípus" ellenőrzéséhez az érintett felhasználónál.</span><span class="sxs-lookup"><span data-stu-id="262fd-116">To verify the "User Type" for the affected user.</span></span>

```
PS C:\>Get-AzureADUser -ObjectId "testUpn@tenant.com"
```
<span data-ttu-id="262fd-117">A parancs a következő információkat adja vissza.</span><span class="sxs-lookup"><span data-stu-id="262fd-117">The command returns the following information.</span></span>
```
ObjectId                             DisplayName UserPrincipalName      UserType
--------                             ----------- -----------------      --------
5e8b0f4d-2cd4-4e17-9467-b0f6a5c0c4d0 New user    testUpn@tenant.com     
```
<span data-ttu-id="262fd-118">Jegyezze fel a felhasználó **Felhasználótípus** tulajdonságát.</span><span class="sxs-lookup"><span data-stu-id="262fd-118">Note the **UserType** property on the user.</span></span> <span data-ttu-id="262fd-119">Ha a **UserType** üres, például nem „Tag” vagy „Vendég”, frissítse a **UserType** mezőt a következő paranccsal.</span><span class="sxs-lookup"><span data-stu-id="262fd-119">If the **UserType** is blank, for example not "Member" or "Guest", update the **UserType** using the following command.</span></span>

```
PS C:\>Set-AzureADUser -ObjectId "testUpn@tenant.com" -UserType Member
```
