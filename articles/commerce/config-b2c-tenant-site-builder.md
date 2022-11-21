---
title: A B2C-bérlő konfigurálása a Commerce webhelyszerkesztőben
description: Ez a témakör azt ismerteti, hogyan kell konfigurálni a vállalat-felhasználó (B2C) bérlőt a webhelyszerkesztőben Microsoft Dynamics 365 Commerce.
author: BrianShook
ms.date: 11/15/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2020-02-13
ms.openlocfilehash: 181edf1570f1a9d071a7fae38ff9d73ff3c068fa
ms.sourcegitcommit: 774f8f97a0b14cf1199bd1802178ccf536a25ade
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/17/2022
ms.locfileid: "9785820"
---
# <a name="configure-your-b2c-tenant-in-commerce-site-builder"></a>A B2C-bérlő konfigurálása a Commerce webhelyszerkesztőben

[!include [banner](includes/banner.md)]

Ez a témakör azt ismerteti, hogyan kell konfigurálni a vállalat-felhasználó (B2C) bérlőt a webhelyszerkesztőben Microsoft Dynamics 365 Commerce.

A Azure AD B2C-bérlő beállításainak megadása után konfigurálni kell a B2C-bérlőt a Commerce webhelyszerkesztőben. A konfigurálás lépései közül az egyik a B2C alkalmazás adatainak összegyűjtése az Azure portálról, a B2C alkalmazás adatainak megadása webhelykészítőben, majd a B2C alkalmazás társítása a webhelyéhez és a csatornájához.

### <a name="collect-the-required-application-information"></a>A szükséges alkalmazásadatok összegyűjtése

A szükséges alkalmazásadatok összegyűjtéséhez kövesse az alábbi lépéseket.

1. Az Azure-portálon menjen a **\>Azure AD B2C – alkalmazásregisztrációk webhelyre**.
1. Válassza ki az alkalmazást, majd a bal oldali navigációs ablakban válassza **az Áttekintés** lehetőséget az alkalmazás részletes adataihoz.
1. Az alkalmazásazonosító-hivatkozásból **gyűjtse** össze a B2C-bérlőben létrehozott B2C-alkalmazás azonosítóját. Ezt a későbbiekben a webhelykészítőben **Ügyfél GUID-ként** lesz megadva.
1. Válassza az **Átirányítási URL-címeket**, és gyűjtse össze a webhelyéhez látható válasz URL-címet (a válasz URL-címét a beállításkor adja meg).
1. Ugrás a **B2C \>Azure AD kezdőlaphoz – felhasználói folyamatok**, majd az egyes felhasználói folyamati irányelvek teljes nevének összegyűjtése.

Az alábbi kép egy példát **Azure AD mutat be a B2C – alkalmazásregisztrációk áttekintő** lapra.

![Azure AD B2C - Az alkalmazásregisztrációk áttekintő lapja a kijelölt alkalmazásazonosítóval (ügyfél)](./media/ClientGUID_Application_AzurePortal.png)

A következő kép egy példát mutat be a felhasználói folyamatokra az **Azure AD B2C – felhasználói folyamatok (házirendek)** oldalon.

![A B2C házirendfolyamatok neveinek összegyűjtése.](./media/B2CImage_22.png)

### <a name="enter-your-azure-ad-b2c-tenant-application-information-into-commerce"></a>Adja meg a Azure AD B2C bérlő alkalmazásával kapcsolatos adatokat a Commerce rendszerből.

Meg kell adnia a Azure AD B2C bérlő adatait a Commerce oldalkészítő számára, mielőtt a B2C bérlőt a webhelyéhez/webhelyeihez társítja.

A B2C Azure AD bérlőalkalmazási információinak a Commerce alkalmazásba való felvételéhez kövesse ezeket a lépéseket.

1. Jelentkezzen be rendszergazdaként a saját környezetéhez tartozó Commerce oldalkészítőbe.
1. A bal oldali navigációs panelen válassza a **Bérlőbeállítások** elemet a kibontáshoz.
1. A Bérlő **beállításai csoportban** válassza a Webhely hitelesítésének **beállításait**. 
1. Válassza a Kezelés lehetőséget a Webhely **hitelesítési** profiljai melletti fő **ablakban**. (Ha a bérlő megjelenik a webhely hitelesítési profiljainak listáján, azt már egy rendszergazda hozzáadta. Győződjön meg róla, hogy az alábbi 6. lépésben lévő cikkek megegyeznek a B2C beállításokban tervezett cikkekkel. Új profilt a Azure AD B2C hasonló bérlők vagy pályázatok segítségével is létre lehet hozni, hogy kisebb különbségeket is figyelembe tudjanak venni, például eltérő felhasználói irányelv-azonosítókat.
1. Válassza a **Webhely hitelesítési profiljának hozzáadása lehetőséget**.
1. A megjelenő képernyőn adja meg a következő szükséges elemeket a B2C bérlő és az alkalmazás értékeit használva. A nem kötelező mezők (a csillag nélküliek) üresen maradhatnak.

    - **Alkalmazás neve**: A B2C alkalmazás neve (például „Fabrikam B2C”).
    - **Bérlő neve**: A B2C bérlője neve (például használja a „fabrikam” beállítást, ha a B2C-bérlőnek a tartomány „fabrikam.onmicrosoft.com” néven jelenik meg). 
    - **Felejtse el a jelszót házirend azonosító**: A felejtse el a jelszót felhasználóifolyamat házirend azonosítója „B2C_1_PasswordReset”.
    - **Bejelentkezési irányelv azonosítója**: A regisztráció és a bejelentkezés felhasználói folyamatának irányelvazonosítója, például "B2C_1_signup_signin".
    - **Ügyfél GUID**: A B2C alkalmazás azonosítója: (például „22290eb2-c52e-42e9-8b35-a2b0a3bcb9e6” B2C).
    - **Profilirányelv azonosítója**: A profilszerkesztő felhasználói folyamatazonosító, például „B2C_1A_ProfileEdit”.

1. Válassza ki az **OK** lehetőséget. Ekkor megjelenik a B2C alkalmazásának neve a listán.
1. A változtatások mentéséhez válassza a **Mentés** elemet.

A Bejelentkezési **név egyéni tartomány választható mezőjét** csak akkor kell használni, ha egyéni tartományt ad meg a Azure AD B2C bérlő számára. A Bejelentkezési tartomány mező használatával **kapcsolatos** további részleteket és szempontokat lásd a [További B2C-információkban](additional-b2c-info.md).

### <a name="associate-the-b2c-application-to-your-site-and-channel"></a>A B2C alkalmazás társítása a webhelyéhez és a csatornához

> [!WARNING]
> - Ha webhelye már B2C alkalmazáshoz van társítva, a másik B2C alkalmazásra történő módosítás eltávolítja a korábban a környezetben már feliratkozott felhasználók számára létrehozott aktuális hivatkozásokat. Módosítás eseténe az aktuálisan hozzárendelt B2C alkalmazáshoz társított hitelesítő adatok nem lesznek elérhetők a felhasználók számára. 
> - Csak akkor frissítse a B2C alkalmazást, ha első alkalommal szeretné bejelenni a csatorna B2C-alkalmazását, vagy ha szeretné, hogy a felhasználók újra regisztrálják az új B2C-alkalmazást erre a csatornára. A csatornáknak a B2C alkalmazásokkal történő társítása során legyen körültekintő, valamint az alkalmazásoknevét egyértelműen adja meg. Ha egy csatorna nincs egy B2C alkalmazáshoz van társítva az alábbi lépésekben, akkor a program a webhelyébe bejelentkező felhasználókat belépteti az **alapértelmezett** B2C alkalmazásba a **Bérlői beállítások \> B2C beállítások** helyen található B2C alkalmazások listáján.

A B2C alkalmazás társításához a webhelyéhez és a csatornához kövesse az alábbi lépéseket.

1. Nyissa meg a webhelyét a Commerce webhelykészítőben.
1. A bal oldali navigációs panelen válassza a **Webhelybeállítások** elemet a kibontáshoz.
1. A **Webhely beállításai** alatt válassza ki a **Csatornák** elemet.
1. Válassza ki a **Csatorna** elem alatti fő ablakban válassza ki a csatornáját.
1. A jobb oldali csatornatulajdonságok ablaktáblán válassza ki a B2C-alkalmazás nevét a **B2C-alkalmazás** kiválasztása legördülő menüből.
1. Válassza a **Bezárás** parancsot, majd válassza a **Mentés és közzététel** parancsot.

## <a name="next-steps"></a>További lépések

A B2C [bérlő beállításának folytatásához lépjen tovább a B2C további adataira](additional-b2c-info.md).

## <a name="additional-resources"></a>További erőforrások

[B2C-bérlő beállítása a Commerce alkalmazásban](set-up-b2c-tenant.md)

[Meglévő B2C-bérlő Azure AD létrehozása vagy hivatkozása az Azure-portálon](create-link-aad-b2c-tenant.md)

[A B2C-alkalmazás létrehozása](create-b2c-app.md)

[Felhasználóifolyamat-irányelvek létrehozása](create-user-flow-policies.md)

[Közösségi identitásszolgáltatók hozzáadása (nem kötelező)](add-social-identity-providers.md)

[A Commerce Headquarters frissítése az új Azure AD B2C-adatokkal](update-hq-aad-b2c-info.md)

[További B2C információk](additional-b2c-info.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
