---
title: A felhasználó nem található az Attract vagy Onboard Személyválasztójában
description: Ez a témakör bemutatja, mi a teendő, amikor a felhasználók a vállalati példányában nem jelenik meg az Személyválasztóban Dynamics 365 Talent – Attract vagy Onboard alkalmazásokban.
author: andreabichsel
manager: AnnBe
ms.date: 01/22/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2019-01-22
ms.dyn365.ops.version: Talent
ms.openlocfilehash: d84dd9c22738a1b4fc5edb5331d4aa213b82facb
ms.sourcegitcommit: 75db3b75d35d27034f9b56e7119c9d0cb7666830
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/03/2019
ms.locfileid: "2551933"
---
# <a name="user-not-found-in-people-picker-in-attract-or-onboard"></a><span data-ttu-id="1c329-103">A felhasználó nem található az Attract vagy Onboard Személyválasztójában</span><span class="sxs-lookup"><span data-stu-id="1c329-103">User not found in People Picker in Attract or Onboard</span></span>
[!include [banner](includes/banner.md)]

## <a name="issue"></a><span data-ttu-id="1c329-104">Kibocsátás</span><span class="sxs-lookup"><span data-stu-id="1c329-104">Issue</span></span>

<span data-ttu-id="1c329-105">Egyes érvényes felhasználók a Microsoft Azure Active Directory (Azure AD) a bérlőnek nem jelennek meg a Személyválasztóban a név keresésekor a Dynamics 365 Talent: Attract vagy Dynamics 365 Talent: Onboard alkalmazásokban.</span><span class="sxs-lookup"><span data-stu-id="1c329-105">Certain valid users in Microsoft Azure Active Directory (Azure AD) for the tenant do not appear when searching for the name in the People Picker in Dynamics 365 Talent: Attract or Dynamics 365 Talent: Onboard.</span></span>

## <a name="cause"></a><span data-ttu-id="1c329-106">Ok</span><span class="sxs-lookup"><span data-stu-id="1c329-106">Cause</span></span>

<span data-ttu-id="1c329-107">Bizonyos felhasználótípusok jelenleg nem támogatottak az Attract és Onboard alkalmazásokban.</span><span class="sxs-lookup"><span data-stu-id="1c329-107">Certain user types are not currently supported in Attract and Onboard.</span></span> <span data-ttu-id="1c329-108">Győződjön meg róla, hogy a felhasználó nem egy Azure AD Business to Business (B2B) vendégfelhasználó.</span><span class="sxs-lookup"><span data-stu-id="1c329-108">Verify that the user is not an Azure AD Business to Business (B2B) guest user.</span></span> <span data-ttu-id="1c329-109">A „Felhasználó típusa” információk az Azure Active Directory lapon találhatók az Azure portálon.</span><span class="sxs-lookup"><span data-stu-id="1c329-109">"User Type" information can be found in the Azure Active Directory blade on the Azure portal.</span></span>

<span data-ttu-id="1c329-110">Az Azure B2B-vel kapcsolatos további tudnivalókat lásd: [Mi a vendég felhasználói hozzáférés az Azure Active Directory B2B-ben](https://docs.microsoft.com/azure/active-directory/b2b/what-is-b2b).</span><span class="sxs-lookup"><span data-stu-id="1c329-110">For more information about Azure B2B, see [What is guest user access in Azure Active Directory B2B](https://docs.microsoft.com/azure/active-directory/b2b/what-is-b2b).</span></span>

<span data-ttu-id="1c329-111">Nem B2B felhasználóknak bizonyos felhasználók esetében hiányos„Felhasználótípus” tulajdonság lehet a **Felhasználó** objektumban.</span><span class="sxs-lookup"><span data-stu-id="1c329-111">For non-B2B users, there are certain users who may have an incomplete "User Type" property on the **User** object.</span></span> <span data-ttu-id="1c329-112">Ez ellenőrizhető és javítható az Azure AD Powershell modul használatával.</span><span class="sxs-lookup"><span data-stu-id="1c329-112">This can be verified and fixed using the Azure AD Powershell module.</span></span> <span data-ttu-id="1c329-113">További tájékoztatást a következő témakörben talál: [Azure AD](https://docs.microsoft.com/powershell/module/azuread/?view=azureadps-2.0).</span><span class="sxs-lookup"><span data-stu-id="1c329-113">For more information, see [Azure AD](https://docs.microsoft.com/powershell/module/azuread/?view=azureadps-2.0).</span></span>

## <a name="resolution"></a><span data-ttu-id="1c329-114">Feloldás</span><span class="sxs-lookup"><span data-stu-id="1c329-114">Resolution</span></span>

<span data-ttu-id="1c329-115">A probléma megoldásához a következő lépések végrehajtásával szüksége lesz „Globális rendszergazda” engedélyekre za Azure Active Directory bérlőben vagy a **User.ReadWrite.All** engedélyekre.</span><span class="sxs-lookup"><span data-stu-id="1c329-115">To complete the following steps to resolve the issue, you will need to have "Global Administrator" permissions on the Azure Active Directory tenant or permissions for **User.ReadWrite.All**.</span></span>

<span data-ttu-id="1c329-116">A „Felhasználótípus" ellenőrzéséhez az érintett felhasználónál.</span><span class="sxs-lookup"><span data-stu-id="1c329-116">To verify the "User Type" for the affected user.</span></span>

```
PS C:\>Get-AzureADUser -ObjectId "testUpn@tenant.com"
```
<span data-ttu-id="1c329-117">A parancs a következő információkat adja vissza.</span><span class="sxs-lookup"><span data-stu-id="1c329-117">The command returns the following information.</span></span>
```
ObjectId                             DisplayName UserPrincipalName      UserType
--------                             ----------- -----------------      --------
5e8b0f4d-2cd4-4e17-9467-b0f6a5c0c4d0 New user    testUpn@tenant.com     
```
<span data-ttu-id="1c329-118">Jegyezze fel a felhasználó **Felhasználótípus** tulajdonságát.</span><span class="sxs-lookup"><span data-stu-id="1c329-118">Note the **UserType** property on the user.</span></span> <span data-ttu-id="1c329-119">Ha a **UserType** üres, például nem „Tag” vagy „Vendég”, frissítse a **UserType** mezőt a következő paranccsal.</span><span class="sxs-lookup"><span data-stu-id="1c329-119">If the **UserType** is blank, for example not "Member" or "Guest", update the **UserType** using the following command.</span></span>

```
PS C:\>Set-AzureADUser -ObjectId "testUpn@tenant.com" -UserType Member
```
