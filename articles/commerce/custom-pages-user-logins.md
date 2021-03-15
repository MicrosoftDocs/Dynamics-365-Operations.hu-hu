---
title: Felhasználói bejelentkezéshez használt egyéni lapok beállítása
description: Ez a témakör azt mutatja be, hogyan lehet egyéni lapokat létrehozni a Microsoft Dynamics 365 Commerce alkalmazásban, amelyek az Azure Active Directory (Azure AD) cég és ügyfél (B2C) közötti bérlők felhasználóinak személyre szabott bejelentkezésit kezelik.
author: brianshook
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: a55da9683c43ac75109fd256e481b02a4d565914
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4970078"
---
# <a name="set-up-custom-pages-for-user-sign-ins"></a>Felhasználói bejelentkezéshez használt egyéni oldalak beállítása


[!include [banner](includes/banner.md)]

Ez a témakör azt mutatja be, hogyan lehet egyéni lapokat létrehozni a Microsoft Dynamics 365 Commerce alkalmazásban, amelyek az Azure Active Directory (Azure AD) cég és ügyfél (B2C) közötti bérlők felhasználóinak személyre szabott bejelentkezésit kezelik.

## <a name="overview"></a>Áttekintés

A Dynamics 365 Commerce alkalmazásban létrehozott egyéni lapok felhasználói bejelentkezési folyamatok kezelésére való beállításához be kell állítania azokat a Azure AD-szabályokat, amelyekre a Commerce-környezetben hivatkozni fognak. A „Regisztráció és bejelentkezés”, „Profilszerkesztés” és „Új jelszó létrehozása” Azure AD B2C irányelveket az Azure AD B2C alkalmazás használatával állíthatja be. Az Azure AD B2C bérlő és az irányelvnevek később hivatkozhatók a létesítési folyamat során, amelyet a Commerce-környezetben, Microsoft Dynamics Lifecycle Services (LCS) használatával végeznek.

Az egyéni Commerce-lapok a bejelentkezés, a regisztráció, a számlaprofil szerkesztése vagy az új jelszó beállítására szolgáló modul használatával hozhatók létre. Az ilyen egyéni lapokhoz közzétett lap URL-címeit az Azure AD B2C házirend-konfigurációi között kell megadni az Azure-portálon.

## <a name="set-up-b2c-policies"></a>B2C irányelvek beállítása

Miután beállította az Azure AD B2C-bérlőt, és társította a Commerce-környezethez, kattintson az **Azure AD B2C**-lapra az Azure-portálon, majd a menüben az **Irányelvek** alatt válassza a **Felhasználói folyamatok (házirendek)** parancsot.

![Felhasználói folyamatok (irányelvek) parancs a menüben](./media/B2C_CustomPage_PoliciesMenu.png)

Most konfigurálhatja a „Regisztráció és bejelentkezés”, „Profilszerkesztés” és „Új jelszó létrehozása” felhasználói bejelentkezési folyamatokat.

### <a name="configure-the-sign-up-and-sign-in-policy"></a>A „Regisztráció és bejelentkezés” irányelv konfigurálása

A „Regisztráció és bejelentkezés” irányelv konfigurálásához kövesse az alábbi lépéseket.

1. Válassza ki az **Új felhasználói folyamat** lehetőséget, majd az **Ajánlott** lapon válassza ki a **Regisztráció és bejelentkezés** irányelvet.
1. Adja meg az irányelv nevét (például **B2C\_1\_SignInSignUp**).
1. Az **Identitásszolgáltatók** szakaszban válassza ki az irányelvhez használandó identitásszolgáltatókat. Legalább az **E-mailes feliratkozás** lehetőséget be kell jelölni.
1. Az **Attribútum összegyűjtése** oszlopban jelölje be az **E-mail-cím**, az **Utónév** és a **Vezetéknév** jelölőnégyzetét.
1. A **Visszatérítési igény** oszlopban válassza ki az **E-mail-címek**, **Utónév**, **Identitásszolgáltató**, **Vezetéknév** és **Felhasználó objektumazonosítója** jelölőnégyzeteket.

    ![Kiválasztott attribútumok és igények](./media/B2C_SignInSignUp_Attributes.png)

1. Az irányelv létrehozásához kattintson az **OK** lehetőségre.
1. Kattintson duplán az új irányelv nevére, majd a navigációs ablakban válassza ki a **Tulajdonságok** lehetőséget.
1. Adja meg a **Oldalelrendezés JavaScript általi érvényesítésének engedélyezése (előnézet)** lehetőség esetében a **Be** értéket.

    ![Az új irányelv Tulajdonságok lapja](./media/B2C_SignInSignUp_EnableJavascript.png)

> [!NOTE]
> Az irányelv neve teljes hivatkozással jelenik meg a Commerce-környezetben. (A **B2C\_1\_** előtag szerepelni fog a hivatkozásban.) Az irányelveket a létrehozásuk után nem lehet átnevezni. Ha a Commerce-környezet egy meglévő irányelvét cseréli le, akkor törölheti az eredeti irányelvet, és összeállíthat egy azonos nevű új irányelvet. Ha a környezetet már létre lett hozva, akkor alternatív megoldásként egy szolgáltatási kérelem útján elküldheti az új irányelv nevét.

Az egyéni lapok összeállítását követően visszatérhet az irányelvhez, és befejezheti a beállítását. Most zárja be az irányelvet, hogy visszatérjen az Azure-portál **Felhasználói folyamatok (irányelvek)** lapjára.

### <a name="configure-the-profile-editing-policy"></a>A „Profilszerkesztés” irányelv konfigurálása

A „Profilszerkesztés” irányelv konfigurálásához kövesse az alábbi lépéseket.

1. Válassza ki az **Új felhasználói folyamat** lehetőséget, majd az **Ajánlott** lapon válassza ki a **Profilszerkesztés** irányelvet.
1. Adja meg az irányelv nevét (például **B2C\_1\_EditProfile**).
1. Az **Identitásszolgáltatók** szakaszban válassza ki az irányelvhez használandó identitásszolgáltatókat. Legalább a **Bejelentkezés helyi fiókkal** lehetőséget ki kell választani.
1. Az **Attribútum összegyűjtése** oszlopban jelölje be az **E-mail-címek** és a **Vezetéknév** jelölőnégyzetét.
1. A **Visszatérítési igény** oszlopban válassza ki az **E-mail-címek**, **Utónév**, **Identitásszolgáltató**, **Vezetéknév** és **Felhasználó objektumazonosítója** jelölőnégyzeteket.
1. Az irányelv létrehozásához kattintson az **OK** lehetőségre.
1. Kattintson duplán az új irányelv nevére, majd a navigációs ablakban válassza ki a **Tulajdonságok** lehetőséget.
1. Adja meg a **Oldalelrendezés JavaScript általi érvényesítésének engedélyezése (előnézet)** lehetőség esetében a **Be** értéket.

Az egyéni lapok összeállítását követően visszatérhet az irányelvhez, és befejezheti a beállítását. Most zárja be az irányelvet, hogy visszatérjen az Azure-portál **Felhasználói folyamatok (irányelvek)** lapjára.

### <a name="configure-the-password-reset-policy"></a>Az „Új jelszó létrehozása” irányelv konfigurálása

Az „Új jelszó létrehozása” irányelv konfigurálásához kövesse az alábbi lépéseket.

1. Válassza ki az **Új felhasználói folyamat** lehetőséget, majd az **Előnézet** lapon válassza ki az **Új jelszó létrehozása v1.1** irányelvet.

    ![Az Előnézet lapon kiválasztott Új jelszó létrehozása v1.1 irányelv](./media/B2C_ForgetPassword_Menu.png)

1. Adja meg az irányelv nevét (például **B2C\_1\_ForgetPassword**).
1. Az **Identitásszolgáltatók** szakaszban válassza az **Új jelszó beállítása e-mail-cím használatával** lehetőséget.
1. A **Visszatérítési igény** oszlopban válassza ki az **E-mail-címek**, **Utónév**, **Vezetéknév** és **Felhasználó objektumazonosítója** jelölőnégyzeteket.

    ![Kijelölt igények](./media/B2C_ForgetPassword_Attributes.png)

1. Az irányelv létrehozásához kattintson az **OK** lehetőségre.
1. Kattintson duplán az új irányelv nevére, majd a navigációs ablakban válassza ki a **Tulajdonságok** lehetőséget.
1. Adja meg a **Oldalelrendezés JavaScript általi érvényesítésének engedélyezése (előnézet)** lehetőség esetében a **Be** értéket.

Az egyéni lapok összeállítását követően visszatérhet az irányelvhez, és befejezheti a beállítását. Most zárja be az irányelvet, hogy visszatérjen az Azure-portál **Felhasználói folyamatok (irányelvek)** lapjára.

## <a name="build-the-custom-pages"></a>Egyéni lapok létrehozása

Az egyéni lapoknak a felhasználói bejelentkezések kezelésére történő létrehozásához hajtsa végre az alábbi lépéseket.

1. Nyissa meg a webhelyét a Commerce létrehozási eszközökben.
1. Állítsa össze a következő öt sablont és öt lapot:

    - A **Bejelentkezés** sablont és a bejelentkezési modult használó lapot.
    - A **Regisztráció** sablont és a regisztrációs modult használó lapot.
    - Az **Új jelszó beállítása** sablont és az új jelszó beállítás modult használó lapot.
    - Az **Új jelszó megerősítése** sablont és az új jelszó megerősítése modult használó lapot.
    - A **Profilszerkesztés** sablont és a fiókprofil-szerkesztő modult használó lapot

A lapok összeállítása során kövesse az alábbi irányelveket:

- Minden lap vagy modul esetében használja az üzleti szükségleteinek legmegfelelőbb elrendezést és stílust.
- Tegye közzé az összes lapot és URL-t, amelyet az Azure AD B2C beállításban használni kell.
- Miután közzétette a lapokat és az URL-címeket, gyűjtse össze az URL-eket, amelyeket az Azure AD B2C irányelv-konfigurációkhoz használni kell. A **?preloadscripts=true** utótagot a program minden URL-címhez hozzáadja, amikor használatban van.

> [!IMPORTANT]
> Ne használja újra az olyan univerzális fejléceket és lábléceket, amelyek relatív hivatkozásokkal rendelkeznek. Ezeket a lapokat a rendszer az Azure AD B2C tartományban tárolja, amikor használatban vannak, ezért csak abszolút URL-címeket szabad használni minden hivatkozáshoz.

## <a name="configure-azure-ad-b2c-policies-with-custom-page-information"></a>Az Azure AD B2C irányelvek beállítása egyénilap-információkkal 

Az Azure-portálon térjen vissza az **Azure AD B2C** lapra, majd a menüben az **Irányelvek** alatt válassza a **Felhasználói folyamatok (irányelvek)** lehetőséget.

### <a name="update-the-sign-up-and-sign-in-policy-with-custom-page-information"></a>A „Regisztráció és bejelentkezés” irányelv frissítése az egyéni lap információival

A „Regisztráció és bejelentkezés” irányelvnek az egyéni lap információival való frissítéséhez tegye a következőket.

1. A korábban konfigurált **Regisztráció és bejelentkezés** irányelv navigációs ablakában válassza ki a **Lapelrendezések** elemet.
1. Válassza ki az **Egyesített bejelentkezési vagy regisztrációs lap** elrendezést.
1. Az **Egyéni laptartalom használata** lehetőséget állítsa be **Igen** értékre.
1. Írja be a teljes bejelentkezési URL-t az **Egyéni lap URI** mezőbe. Foglalja bele a **?preloadscripts=true** utótagot. Például írja be, hogy ``www.<my domain>.com/sign-in?preloadscripts=true``.
1. A **Lapelrendezés verziója (előnézet)** mezőben válassza ki a **1.2.0** értéket.
1. Válassza ki a **Helyi fiók regisztrációs lapja** elrendezést.
1. Az **Egyéni laptartalom használata** lehetőséget állítsa be **Igen** értékre.
1. Írja be a teljes bejelentkezési URL-t az **Egyéni lap URI** mezőbe. Foglalja bele a **?preloadscripts=true** utótagot. Például írja be, hogy ``www.<my domain>.com/sign-up?preloadscripts=true``.
1. A **Lapelrendezés verziója (előnézet)** mezőben válassza ki a **1.2.0** értéket.
1. A **Felhasználói attribútumok** szakaszban hajtsa végre a következő lépéseket:

    1. Az **E-mail-cím**, **Utónév** és **Vezetéknév** attribútumok esetében válassza a **Nem** értéket az **Ellenőrzés szükséges** mezőben.
    1. Az **Utónév** és **Vezetéknév** attribútumok esetében válassza a **Nem** értéket az **Opcionális** mezőben.

    ![A Helyi fiók regisztrációs lap irányelvének konfigurálása](./media/B2C_SignUp_PageURLConfig.png)

### <a name="update-the-profile-editing-policy-with-custom-page-information"></a>A „Profilszerkesztés” irányelv frissítése az egyéni lap információival

A „Profilszerkesztés” irányelvnek az egyéni lap információival való frissítéséhez tegye a következőket.

1. A korábban konfigurált **Profilszerkesztés** irányelv navigációs ablakában válassza ki a **Lapelrendezések** elemet.
1. Válassza ki **Profilszerkesztés lap** elrendezést.
1. Az **Egyéni laptartalom használata** lehetőséget állítsa be **Igen** értékre.
1. Írja be a teljes profilszerkesztési URL-t az **Egyéni lap URI** mezőbe. Foglalja bele a **?preloadscripts=true** utótagot. Például írja be, hogy ``www.<my domain>.com/profile-edit?preloadscripts=true``.
1. A **Lapelrendezés verziója (előnézet)** mezőben válassza ki a **1.2.0** értéket.
1. A **Felhasználói attribútumok** szakaszban hajtsa végre a következő lépéseket:

    1. Az **E-mail-cím** és **Utónév** attribútumok esetében válassza a **Nem** értéket az **Ellenőrzés szükséges** mezőben.
    1. Az **Utónév** és **Vezetéknév** attribútumok esetében válassza a **Nem** értéket az **Opcionális** mezőben.

### <a name="update-the-password-reset-policy-with-custom-page-information"></a>Az „Új jelszó létrehozása” irányelv frissítése az egyéni lap információival

Az „Új jelszó létrehozása” irányelvnek az egyéni lap információival való frissítéséhez tegye a következőket.

1. A korábban konfigurált **Új jelszó létrehozása** irányelv navigációs ablakában válassza ki a **Lapelrendezések** elemet.
1. Válassza ki az **Új jelszó létrehozása lap** elrendezést.
1. Az **Egyéni laptartalom használata** lehetőséget állítsa be **Igen** értékre.
1. Írja be a teljes jelszóvisszaállítási URL-t az **Egyéni lap URI** mezőbe. Foglalja bele a **?preloadscripts=true** utótagot. Például írja be, hogy ``www.<my domain>.com/passwordreset?preloadscripts=true``.
1. A **Lapelrendezés verziója (előnézet)** mezőben válassza ki a **1.2.0** értéket.
1. Válassza ki a **Fiókellenőrzés lap** elrendezést.
1. Az **Egyéni laptartalom használata** lehetőséget állítsa be **Igen** értékre.
1. Írja be a teljes jelszóvisszaállítás-érvényesítési URL-t az **Egyéni lap URI** mezőbe. Foglalja bele a **?preloadscripts=true** utótagot. Például írja be, hogy ``www.<my domain>.com/passwordreset-verification?preloadscripts=true``.
1. A **Lapelrendezés verziója (előnézet)** mezőben válassza ki a **1.2.0** értéket.



## <a name="customize-default-text-strings-for-labels-and-descriptions"></a>Címkék és leírások alapértelmezett szöveges karakterláncainak testreszabása

A modulkönyvtárban a bejelentkezési modulok a címkék és leírások alapértelmezett szövegével kerülnek előre kitöltésre. Ezeket a karakterláncokat testreszabhatja a szoftverfejlesztői készletben (SDK) a bejelentkezési modul global.json fájljában található értékek frissítésével.

Az elfelejtett jelszó hivatkozásának alapértelmezett szövege például **Elfelejtette a jelszót?**. A következőkben látható ez az alapértelmezett szöveg a bejelentkezési oldalon.

![Alapértelmezett szöveg a bejelentkezési oldalon található elfelejtett jelszó hivatkozáshoz](./media/B2C_SignUp_ModuleFace.png)

A modulkönyvtár bejelentkezési moduljának global.json fájljában azonban szerkesztheti a szöveget az **Elfelejtett jelszó?** értékre, ahogy az a következő ábrán látható.

![Frissített hivatkozásszöveg a bejelentkezési modul global.json fájljában](./media/B2C_CustomizingStringsForModule.png)

A global.json fájl frissítése és a módosítások közzététele után az új hivatkozásszöveg megjelenik a bejelentkezési modulban, mind a Commerce, mind az éles bejelentkezési lapon.

## <a name="additional-resources"></a>További erőforrások

[Tartománynév konfigurálása](configure-your-domain-name.md)

[Új e-kereskedelmi bérlő telepítése](deploy-ecommerce-site.md)

[E-kereskedelmi webhely létrehozása](create-ecommerce-site.md)

[Dynamics 365 Commerce webhely társítása online csatornával](associate-site-online-store.md)

[Robots.txt fájlok kezelése](manage-robots-txt-files.md)

[URL-átirányítások tömeges feltöltése](upload-bulk-redirects.md)

[B2C-bérlő beállítása a Commerce-ben](set-up-B2C-tenant.md)

[Több B2C-bérlő konfigurálása egy Commerce környezetben](configure-multi-B2C-tenants.md)

[Tartalomkézbesítési hálózat (CDN) támogatásának hozzáadása](add-cdn-support.md)

[Helyalapú áruházészlelés engedélyezése](enable-store-detection.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]