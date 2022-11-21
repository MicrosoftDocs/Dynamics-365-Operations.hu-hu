---
title: A Commerce központ frissítése az új Azure AD B2C adatokkal
description: Ez a témakör azt ismerteti, hogyan Microsoft Dynamics 365 Commerce frissítheti a központot az Azure Active Directory új (Azure AD) vállalat-felhasználó (B2C) adatokkal.
author: BrianShook
ms.date: 11/15/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2020-02-13
ms.openlocfilehash: c65949ff97182d2692319ac2af00e3ef35a79580
ms.sourcegitcommit: 774f8f97a0b14cf1199bd1802178ccf536a25ade
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/17/2022
ms.locfileid: "9785821"
---
# <a name="update-commerce-headquarters-with-the-new-azure-ad-b2c-information"></a>A Commerce központ frissítése az új Azure AD B2C adatokkal

[!include [banner](includes/banner.md)]

Ez a témakör azt ismerteti, hogyan Microsoft Dynamics 365 Commerce frissítheti a központot az Azure Active Directory új (Azure AD) vállalat-felhasználó (B2C) adatokkal.

Miután az Azure AD B2C létesítési lépések befejeződtek, az Azure AD B2C alkalmazást regisztrálni kell a Dynamics 365 Commerce környezetében.

Az új Azure AD B2C információval rendelkező központ frissítéséhez hajtsa végre az alábbi lépéseket.

1. A Commerce menüben nyissa meg a **Commerce megosztott paraméterei elemet**, és válassza ki a bal oldali menüben az **Identitásszolgáltatók** elemet.
1. Az **identitás-szolgáltatók** területen hajtsa végre a következő műveleteket:
    1. A Kibocsátó **mezőben** adja meg az azonosító szolgáltató kibocsátójának karakterláncát. A kibocsátó karakterlánc megkereshető az alábbi [, a központ beállításához szükséges kibocsátó karakterlánc bejedve](#obtain-issuer-string-for-headquarters-setup).
    1. A **Név** mezőbe írja be a kiállító rekordjának nevét.
    1. A **Típus** mezőbe írja be a **Azure AD B2C (id_token)** értéket.
1. A **Függő felek** területen, a fenti B2C identitásszolgáltató kiválasztása után tegye a következőket:
    1. **A ClientID mezőben** adja meg a B2C alkalmazásazonosítót, **amelyet** a B2C alkalmazás tulajdonságai oldalának Alkalmazásazonosító mezőiben talál.
    1. A **Típus** mezőbe írja be a **Nyilvános** kifejezést.
    1. A **Felhasználó típusa** mezőbe írja be az **Ügyfél** kifejezést.
1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.
1. A Commerce keresőmezőjében keressen rá az **Elosztási ütemezés** elemre
1. Az **Elosztási ütemezések** lap bal oldali navigációs menüjében válassza a **1110 globális konfiguráció** feladatot.
1. A műveleti ablaktáblán kattintson a **Futtatás most** elemre.

### <a name="obtain-issuer-string-for-headquarters-setup"></a>Kibocsátó karakterlánc beszerzése a központ beállításához

Az azonosító szolgáltató kibocsátójának karakterlánca az alábbi lépések szerint szerezhető be.

1. Az Azure Portal Azure AD B2C lapján keresse meg a **Regisztráció és bejelentkezés** felhasználói folyamatot.
1. Válassza a bal oldali navigációs menü **Oldalelrendezések** elemét, az **Elrendezés neve** alatt válassza az **Egyesített regisztrációs vagy bejelentkezési oldal** lehetőséget, majd a **Felhasználói folyamat futtatása** elemet.
1. Győződjön meg róla Azure AD, hogy az alkalmazás az fent létrehozott, a kívánt B2C-alkalmazásra van beállítva, majd válassza ki azt a felhasználói folyamathivatkozást, **·**``.../.well-known/openid-configuration?p=<B2CSIGN-INPOLICY>`` amely a Felhasználói folyamat fejlécének futtatása alatt látható. (Ne jelölje be **Felhasználói folyamat futtatása**.) Megjelenik egy új lap, amely megjeleníti a kibocsátó karakterlánc beszedése irányelv metaadatait.
1. A böngészőben megjelenített metaadatlapon másolja át az azonosító szolgáltató kibocsátójának karakterláncát (**a** kibocsátónak a "https://" karaktersel kezdődő, "/v2.0/") értékkel kezdődő értékét, amely a következő példához hasonlónak látszik.
   - ``https://login.fabrikam.com/011115c3-0113-4f43-b5e2-df01266e24ae/v2.0/``.
 
**VAGY**: Ha ugyanazt a metaadat-URL-címet manuálisan szeretné megépíteni, tegye meg a következő lépéseket.

1. Hozzon létre egy metaadat cím-URL-t a következő formátumban a B2C bérlő és irányelv használatával: ``https://<B2CTENANTNAME>.b2clogin.com/<B2CTENANTNAME>.onmicrosoft.com/v2.0/.well-known/openid-configuration?p=<B2CSIGN-INPOLICY>``
    - Példa: ``https://d365plc.b2clogin.com/d365plc.onmicrosoft.com/v2.0/.well-known/openid-configuration?p=B2C_1_signinup``
1. Adja meg a metaadatcím URL-jét a böngésző címsorába.
1. A metaadatokban másolja az identitásszolgáltató kiállítójának URL-címét (az **„issuer”** értékét).
    - Példa: ``https://login.fabrikam.com/011115c3-0113-4f43-b5e2-df01266e24ae/v2.0/``

## <a name="next-steps"></a>További lépések

Ha folytatnia kell a B2C bérlő beállítását a Commerce alkalmazásban, konfigurálja [a B2C bérlőt a Commerce webhelyszerkesztőben](config-b2c-tenant-site-builder.md).

## <a name="additional-resources"></a>További erőforrások

[B2C-bérlő beállítása a Commerce alkalmazásban](set-up-b2c-tenant.md)

[Meglévő B2C-bérlő Azure AD létrehozása vagy hivatkozása az Azure-portálon](create-link-aad-b2c-tenant.md)

[A B2C-alkalmazás létrehozása](create-b2c-app.md)

[Felhasználóifolyamat-irányelvek létrehozása](create-user-flow-policies.md)

[Közösségi identitásszolgáltatók hozzáadása (nem kötelező)](add-social-identity-providers.md)

[A B2C-bérlő konfigurálása a Commerce webhelyszerkesztőben](config-b2c-tenant-site-builder.md)

[További B2C információk](additional-b2c-info.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
