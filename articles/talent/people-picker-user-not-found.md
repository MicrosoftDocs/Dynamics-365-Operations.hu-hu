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
# <a name="azure-active-directory-users-not-found-in-people-picker"></a>Azure Active Directory-felhasználók nem találhatók a Személyválasztó szolgáltatásban

[!include [banner](includes/banner.md)]

## <a name="issue"></a>Kibocsátás

Egyes érvényes felhasználók a Microsoft Azure Active Directory (Azure AD) a bérlőnek nem jelennek meg a Személyválasztóban a név keresésekor a Dynamics 365 for Talent Attract vagy Onboard alkalmazásokban.

## <a name="cause"></a>Ok

Bizonyos felhasználótípusok jelenleg nem támogatottak a Attract és Onboard alkalmazásokban. Győződjön meg róla, hogy a felhasználó nem egy Azure AD Business to Business (B2B) vendégfelhasználó. A „Felhasználó típusa” információk az Azure Active Directory lapon találhatók az Azure portálon.

Az Azure B2B-vel kapcsolatos további tudnivalókat lásd: [Mi a vendég felhasználói hozzáférés az Azure Active Directory B2B-ben](https://docs.microsoft.com/en-us/azure/active-directory/b2b/what-is-b2b).

Nem B2B felhasználóknak bizonyos felhasználók esetében hiányos„Felhasználótípus” tulajdonság lehet a **Felhasználó** objektumban. Ez ellenőrizhető és javítható az Azure AD Powershell modul használatával. További tájékoztatást a következő témakörben talál: [Azure AD](https://docs.microsoft.com/en-us/powershell/module/azuread/?view=azureadps-2.0).

## <a name="resolution"></a>Feloldás

A probléma megoldásához a következő lépések végrehajtásával szüksége lesz „Globális rendszergazda” engedélyekre za Azure Active Directory bérlőben vagy a **User.ReadWrite.All** engedélyekre.

A „Felhasználótípus" ellenőrzéséhez az érintett felhasználónál.

```
PS C:\>Get-AzureADUser -ObjectId "testUpn@tenant.com"
```
A parancs a következő információkat adja vissza.
```
ObjectId                             DisplayName UserPrincipalName      UserType
--------                             ----------- -----------------      --------
5e8b0f4d-2cd4-4e17-9467-b0f6a5c0c4d0 New user    testUpn@tenant.com     
```
Jegyezze fel a felhasználó **Felhasználótípus** tulajdonságát. Ha a **UserType** üres, például nem „Tag” vagy „Vendég”, frissítse a **UserType** mezőt a következő paranccsal.

```
PS C:\>Set-AzureADUser -ObjectId "testUpn@tenant.com" -UserType Member
```