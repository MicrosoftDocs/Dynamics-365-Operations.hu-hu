---
title: Felhasználóifolyamat-irányelvek létrehozása
description: Ez a témakör azt ismerteti, hogyan lehet felhasználói folyamat irányelveket létrehozni a portálon Microsoft Azure.
author: BrianShook
ms.date: 11/15/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2020-02-13
ms.openlocfilehash: 91b9d99dfd8c3d100ca197aa499ca86799bbffc8
ms.sourcegitcommit: 774f8f97a0b14cf1199bd1802178ccf536a25ade
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/17/2022
ms.locfileid: "9785817"
---
# <a name="create-user-flow-policies"></a>Felhasználóifolyamat-irányelvek létrehozása

[!include [banner](includes/banner.md)]

Ez a témakör azt ismerteti, hogyan lehet felhasználói folyamat irányelveket létrehozni a portálon Microsoft Azure.

A felhasználói folyamatok az üzleti Azure Active Directory folyamatok (Azure AD B2C) irányelvei a biztonságos bejelentkezéshez, regisztrációhoz, profil szerkesztéséhez és a jelszóval kapcsolatos felhasználói tapasztalatok feledéséhez valók. A Dynamics 365 Commerce ezeket a folyamatokat a házirendműveletek elvégzéséhez használja az interakcióhoz az Azure AD B2C-bérlővel. Ha egy felhasználó ezekkel a házirendekkel kommunikál, Azure AD akkor a program átirányítja őket a B2C bérlőhöz, hogy végrehajtsa a műveleteket.

Az Azure AD B2C három alapvető felhasználói folyamatot kínál:
- Feliratkozás és bejelentkezés
- Profil szerkesztése
- Új jelszó létrehozása

Választhat, hogy a Azure AD B2C által biztosított alapértelmezett felhasználói folyamatokat használja-e, amelyek a Azure AD B2C által tárolt lapot jelenítik meg. Másik megoldásként HTML-lapot is létrehozhat, amellyel szabályozhatja a felhasználói folyamatok megjelenését és érzetét. 

A felhasználói irányelvek oldalainak Dynamics 365 Commerce alkalmazásban létrehozott oldalakkal való testreszabásáról lásd: [Felhasználói bejelentkezéshez használt egyéni lapok beállítása](custom-pages-user-logins.md). A további tudnivalókat lásd [a Felhasználói tapasztalatok testreszabása a Azure Active Directory B2C-ben](/azure/active-directory-b2c/tutorial-customize-ui).

### <a name="create-a-sign-up-and-sign-in-user-flow-policy"></a>Felhasználói folyamatra vonatkozó bejelentkezési irányelv létrehozása

A következő lépések szerint hozzon létre egy bejelentkezési és bejelentkezési felhasználói folyamatra vonatkozó házirendet.

1. Az Azure Portal modul bal oldali navigációs ablakában válassza ki a **Felhasználói folyamatok (házirendek)** elemet.
1. Az **Azure AD B2C – Felhasználói folyamatok (házirendek)** lapon válassza az **Új felhasználói folyamat** elemet.
1. Válassza ki a **Regisztráció és bejelentkezés** irányelvet, majd válassza az **Ajánlott** verziót.
1. A **Név** mezőbe írja be a házirend nevét. Ez a név azután jelenik meg, hogy a portál hozzárendel egy előtagot (például „B2C_1_”).
1. Válassza **az E-mailben** való regisztrációt az **Identitásszolgáltató területen a Helyi** számlák **szakaszban**. A Commerce rendszer leggyakrabban az e-mail hitelesítést használja. Ha a társadalombiztosítási szolgáltató hitelesítését is használja, akkor most is kiválaszthatja azokat.
1. A **Többlépcsős hitelesítés** területen válassza ki a vállalat számára a megfelelő lehetőséget. 
1. A **Felhasználói attribútumok és igények** területen válassza ki az attribútumok gyűjtését vagy igénylések visszaküldését szükség szerint. Válassza a **Több megjelenítése...** lehetőséget az attribútumok és a jogcímbeállítások teljes listájának bemutatja. A Commerce a következő alapértelmezett beállításokat igényli:

    | **Attribútum összegyűjtése** | **Igény visszaküldése** |
    | ---------------------- | ----------------- |
    | E-mail cím          | E-mail-címek   |
    | Utónév             | Utónév        |
    |                        | Identitásszolgáltató |
    | Vezetéknév                | Vezetéknév           |
    |                        | Felhasználó objektumazonosítója  |

1. Válassza a **Létrehozása** lehetőséget.

A következő kép egy példa Azure AD a B2C regisztrációra és a bejelentkezési felhasználói folyamatra.

![A Regisztráció és bejelentkezés irányelv konfigurálása.](./media/B2CImage_11.png)

   
### <a name="create-a-profile-editing-user-flow-policy"></a>Profilszerkesztési felhasználóifolyamat-irányelv létrehozása

Profilszerkesztési felhasználóifolyamat-házirend konfigurálásához kövesse az alábbi lépéseket.

1. Az Azure Portal modul bal oldali navigációs ablakában válassza ki a **Felhasználói folyamatok (házirendek)** elemet.
1. Az **Azure AD B2C – Felhasználói folyamatok (házirendek)** lapon válassza az **Új felhasználói folyamat** elemet.
1. Válassza a **Profilszerkesztés** lehetőséget, majd az **Ajánlott** verziót.
1. A **Név** mezőbe adja meg a profilszerkesztési felhasználói folyamatot. Ez a név azután jelenik meg, hogy a portál hozzárendel egy előtagot (például „B2C_1_”).
1. Az **Identitásszolgáltató** területen a Helyi **számlák** területen válassza az **E-mail bejelentkezési azonosítót**.
1. A **Felhasználói attribútumok** alatt jelölje be az alábbi jelölőnégyzeteket:
    
    | **Attribútum összegyűjtése** | **Igény visszaküldése** |
    | ---------------------- | ----------------- |
    |                        | E-mail-címek   |
    | Utónév             | Utónév        |
    |                        | Identitásszolgáltató |
    | Vezetéknév                | Vezetéknév           |
    |                        | Felhasználó objektumazonosítója  |
    
1. Válassza a **Létrehozása** lehetőséget.

A következő kép egy példát mutat be a Azure AD B2C profilszerkesztő felhasználói folyamatára.

![Példa a Azure AD B2C profil szerkesztésére - felhasználói folyamat](./media/B2CImage_12.png)

### <a name="create-a-password-reset-user-flow-policy"></a>Egy jelszóvisszaállítás felhasználóifolyamat létrehozása

Jelszóvisszaállítás felhasználóifolyamat-házirend konfigurálásához kövesse az alábbi lépéseket.

1. Az Azure Portal modul bal oldali navigációs ablakában válassza ki a **Felhasználói folyamatok (házirendek)** elemet.
1. Az **Azure AD B2C – Felhasználói folyamatok (házirendek)** lapon válassza az **Új felhasználói folyamat** elemet.
1. Válassza az **Új jelszó kérése** lehetőséget, majd az **Ajánlott** verziót.
1. A **Név** mezőben adjon meg egy nevet a jelszóvisszaállítási felhasználói folyamat számára.
1. Az **Identitásszolgáltatók** alatt válassza az **Új jelszó beállítása e-mail-cím használatával** lehetőséget.
1. Válassza a **Létrehozása** lehetőséget.
1. A **Jelentkezési igények** alatt jelölje be az alábbi jelölőnégyzeteket:
    - **E-mail címek**
    - **Utónév**
    - **Vezetéknév**
    - **Felhasználó objektumazonosítója**
1. Válassza a **Létrehozása** lehetőséget.

A következő kép azt jelzi, hogy hol kell beállítani az **Új jelszó beállítása e-mail-cím használatával** funkciót az Azure AD B2C felhasználói folyamatában.

![A „Új jelszó beállítása e-mail-cím használatával” beállítása a Jelszóvisszaállítási-házirendben](./media/B2CImage_13.png)

## <a name="next-steps"></a>További lépések

Ha folytatni szeretne egy B2C bérlő beállítását a Commerceben, járjon el a Társadalombiztosítási [azonosító szolgáltatók hozzáadása pontra](add-social-identity-providers.md).

## <a name="additional-resources"></a>További erőforrások

[B2C-bérlő beállítása a Commerce alkalmazásban](set-up-b2c-tenant.md)

[Meglévő B2C-bérlő Azure AD létrehozása vagy hivatkozása az Azure-portálon](create-link-aad-b2c-tenant.md)

[A B2C-alkalmazás létrehozása](create-b2c-app.md)

[Közösségi identitásszolgáltatók hozzáadása (nem kötelező)](add-social-identity-providers.md)

[A Commerce Headquarters frissítése az új Azure AD B2C-adatokkal](update-hq-aad-b2c-info.md)

[A B2C-bérlő konfigurálása a Commerce webhelyszerkesztőben](config-b2c-tenant-site-builder.md)

[További B2C információk](additional-b2c-info.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
