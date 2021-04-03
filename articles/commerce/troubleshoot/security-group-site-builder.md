---
title: Nem konfigurálható biztonsági csoport a Commerce webhelyszerkesztő számára a kezdeti telepítés során
description: Ez a témakör olyan hibaelhárítási útmutatást tartalmaz, amely segítséget nyújt abban az esetben, ha a Commerce webhelyszerkesztő Microsoft Azure Active Directory (Azure AD) biztonsági csoportja nem jelenik meg lehetőségként, amikor az új e-kereskedelmi bérlő első telepítésekor létrehozza az e-kereskedelmi összetevőket a Microsoft Dynamics Lifecycle Services (LCS) alkalmazásban.
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
ms.author: shajain
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 36ea43e19f395e3914d3eda1a9b8f5487b0926c5
ms.sourcegitcommit: 6c108be3378b365e6ec596a1a8666d59b758db25
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/12/2021
ms.locfileid: "5585360"
---
# <a name="cant-configure-a-security-group-for-commerce-site-builder-during-initial-deployment"></a>Nem konfigurálható biztonsági csoport a Commerce webhelyszerkesztő számára a kezdeti telepítés során

[!include [banner](../../includes/banner.md)]

Ez a témakör olyan hibaelhárítási útmutatást tartalmaz, amely segítséget nyújt abban az esetben, ha a Commerce webhelyszerkesztő Microsoft Azure Active Directory (Azure AD) biztonsági csoportja nem jelenik meg lehetőségként, amikor az új e-kereskedelmi bérlő első telepítésekor létrehozza az e-kereskedelmi összetevőket a Microsoft Dynamics Lifecycle Services (LCS) alkalmazásban.

## <a name="description"></a>Leírás

Amikor az e-kereskedelmi összetevőket a Commerce webhelyszerkesztő összetevőt tartalmazó új e-kereskedelmi bérlő telepítés részeként hozza létre, az Azure AD biztonsági csoport nem jelenik meg lehetőségként a párbeszédpanelen.

## <a name="resolution"></a>Felbontás

### <a name="provision-the-e-commerce-site-with-a-user-in-the-correct-tenant"></a>Az e-kereskedelmi webhely telepítése a megfelelő bérlőben található felhasználóval

1. Lépjen ide: [Azure Portal](https://portal.azure.com/).
1. Azon bérlőnél, akinek az e-kereskedelmi webhelyére vonatkozó LCS-projektet létesítették, kövesse az [Alapcsoport létrehozása és tagok hozzáadása az Azure Active Directory segítségével](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal) pontban leírt utasításokat.
1. Lépejen az [LCS](https://lcs.dynamics.com/) oldalára, és jelentkezzen be egy olyan fiók használatával, amely ugyanazt a bérlőt használja, mint a most létrehozott Azure AD biztonsági csoport. A fióknak hozzáféréssel kell rendelkeznie az Azure AD biztonsági csoport megtekintéséhez.
1. A beállításoknak megfelelően konfigurálhatja az e-kereskedelmi webhelyet. Az e-kereskedelmi összetevők telepítésekor a biztonsági csoportnak lehetőségként kell megjelennie a párbeszédpanelen.

> [!NOTE]
> Annak érdekében, hogy a párbeszédpanel mezője fel legyen töltve a biztonsági csoportok listájával, válassza az **Enter** gombot a létrehozott Azure AD biztonsági csoport nevének beírása után. A keresési eredmények felsorolják azokat az Azure AD biztonsági csoportokat, amelyek a keresési szöveggel kezdődnek, és amelyekhez a felhasználónak hozzáférése van. Rövidebb keresési kifejezés használatával bővebb keresési eredményeket elérhet.

## <a name="additional-resources"></a>További erőforrások

[Alapcsoport létrehozása és tagok hozzáadása az Azure Active Directory segítségével](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)

[Új e-kereskedelmi bérlő telepítése](../deploy-ecommerce-site.md)
