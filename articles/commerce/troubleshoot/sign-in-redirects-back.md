---
title: Bejelentkezési hivatkozás egy e-kereskedelmi webhelyre irányít át
description: Ez a témakör olyan hibaelhárítási útmutatást tartalmaz, amely segítséget nyújt abban az esetben, ha egy bejelentkezési hivatkozás a bejelentkezési oldalra való ugrás helyett az e-kereskedelmi webhelyre irányít vissza.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
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
ms.openlocfilehash: 94afc339bd156d26c5057c1e401d707aa7d517a041493659a40c7b69ad4d377a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6715284"
---
# <a name="sign-in-link-redirects-back-to-an-e-commerce-site"></a>Bejelentkezési hivatkozás egy e-kereskedelmi webhelyre irányít át

[!include [banner](../../includes/banner.md)]

Ez a témakör olyan hibaelhárítási útmutatást tartalmaz, amely segítséget nyújt abban az esetben, ha egy bejelentkezési hivatkozás a bejelentkezési oldalra való ugrás helyett az e-kereskedelmi webhelyre irányít vissza.

## <a name="description"></a>Leírás

Miután konfigurált egy új Microsoft Azure Active Directory B2C (Azure AD B2C) bérlőt a Commerce webhelyszerkesztőben, a **Bejelentkezés** hivatkozást kiválasztó felhasználókat a rendszer úgy irányítja vissza a fő e-kereskdelmi kezdőlapra, hogy nem lép tovább a bejelentkezési oldalra.

## <a name="resolution"></a>Felbontás

### <a name="confirm-that-the-reply-url-is-correctly-configured-in-the-azure-ad-b2c-application"></a>Győződjön meg arról, hogy a válasz URL helyesen legyen konfigurálva az Azure AD B2C alkalmazásban

Kövesse az alábbi lépéseket, hogy meggyőződjön arról, hogy a válasz URL helyesen legyen konfigurálva az Azure AD B2C alkalmazásban.

1. Lépjen ide: [Azure Portal](https://portal.azure.com/).
1. Válassza ki a webhely elérése érdekében létrehozott Azure AD B2C-alkalmazást.
1. Válassza ki az Azure AD B2C beállítása során létrehozott alkalmazást.
1. A **Válasz URL** pontban győződjön meg arról, hogy a lista a webhely tartományának URL-címét és az e-kereskedelem által generált URL-címet is tartalmazza, amint azt az alábbi ábra mutatja.

    ![Azure AD B2C válasz URL bejegyzései.](media/aad-b2c-reply-url.jpg)

> [!NOTE]
> A webhelytartomány URL-címének és az e-kereskedelem által generált URL-címnek egyaránt érvényes URL-formátummal kell rendelkeznie, amely nem tartalmaz vezető vagy záró perjeleket.

## <a name="additional-resources"></a>További erőforrások

[Webalkalmazás regisztrálása az Azure Active Directory B2C alkalmazásban](/azure/active-directory-b2c/tutorial-register-applications?tabs=app-reg-ga#register-a-web-application)

[B2C-bérlő beállítása a Commerce alkalmazásban](../set-up-b2c-tenant.md)