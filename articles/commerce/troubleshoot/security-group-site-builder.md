---
title: Nem konfigurálható biztonsági csoport a Commerce webhelyszerkesztő számára a kezdeti telepítés során
description: Ez a cikk olyan hibaelhárítási útmutatást tartalmaz, amely segítséget nyújt abban az esetben, ha a Commerce webhelyszerkesztő Microsoft Azure Active Directory (Azure AD) biztonsági csoportja nem jelenik meg beállításként, amikor az új e-commerce bérlő első telepítésekor létrehozza az e-commerce Microsoft Dynamics összetevőket a Lifecycle Services (LCS) alkalmazásban.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: shajain
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.custom: ''
ms.assetid: ''
ms.search.industry: Retail
ms.openlocfilehash: 7098c853c262fd7e0d48231634b232eef71c2b8d
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9292000"
---
# <a name="cant-configure-a-security-group-for-commerce-site-builder-during-initial-deployment"></a>Nem konfigurálható biztonsági csoport a Commerce webhelyszerkesztő számára a kezdeti telepítés során

[!include [banner](../../includes/banner.md)]

Ez a cikk olyan hibaelhárítási útmutatást tartalmaz, amely segítséget nyújt abban az esetben, ha a Commerce webhelyszerkesztő Microsoft Azure Active Directory (Azure AD) biztonsági csoportja nem jelenik meg beállításként, amikor az új e-commerce bérlő első telepítésekor létrehozza az e-commerce Microsoft Dynamics összetevőket a Lifecycle Services (LCS) alkalmazásban.

## <a name="description"></a>Leírás

Amikor az e-kereskedelmi összetevőket a Commerce webhelyszerkesztő összetevőt tartalmazó új e-kereskedelmi bérlő telepítés részeként hozza létre, az Azure AD biztonsági csoport nem jelenik meg lehetőségként a párbeszédpanelen.

## <a name="resolution"></a>Felbontás

### <a name="provision-the-e-commerce-site-with-a-user-in-the-correct-tenant"></a>Az e-kereskedelmi webhely telepítése a megfelelő bérlőben található felhasználóval

1. Lépjen ide: [Azure Portal](https://portal.azure.com/).
1. Azon bérlőnél, akinek az e-kereskedelmi webhelyére vonatkozó LCS-projektet létesítették, kövesse az [Alapcsoport létrehozása és tagok hozzáadása az Azure Active Directory segítségével](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal) pontban leírt utasításokat.
1. Lépejen az [LCS](https://lcs.dynamics.com/) oldalára, és jelentkezzen be egy olyan fiók használatával, amely ugyanazt a bérlőt használja, mint a most létrehozott Azure AD biztonsági csoport. A fióknak hozzáféréssel kell rendelkeznie az Azure AD biztonsági csoport megtekintéséhez.
1. A beállításoknak megfelelően konfigurálhatja az e-kereskedelmi webhelyet. Az e-kereskedelmi összetevők telepítésekor a biztonsági csoportnak lehetőségként kell megjelennie a párbeszédpanelen.

> [!NOTE]
> Annak érdekében, hogy a párbeszédpanel mezője fel legyen töltve a biztonsági csoportok listájával, válassza az **Enter** gombot a létrehozott Azure AD biztonsági csoport nevének beírása után. A keresési eredmények felsorolják azokat az Azure AD biztonsági csoportokat, amelyek a keresési szöveggel kezdődnek, és amelyekhez a felhasználónak hozzáférése van. Rövidebb keresési kifejezés használatával bővebb keresési eredményeket elérhet.

## <a name="additional-resources"></a>További erőforrások

[Alapcsoport létrehozása és tagok hozzáadása az Azure Active Directory segítségével](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)

[Új e-kereskedelmi bérlő telepítése](../deploy-ecommerce-site.md)
