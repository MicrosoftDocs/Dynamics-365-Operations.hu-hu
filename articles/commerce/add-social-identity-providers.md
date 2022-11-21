---
title: Társadalombiztosítási szolgáltatók hozzáadása
description: Ez a témakör azt ismerteti, hogyan lehet a portálhoz hozzáadni a társadalombiztosítási szolgáltatókat Microsoft Azure.
author: BrianShook
ms.date: 11/15/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2020-02-13
ms.openlocfilehash: 5596097a5484acafda54adcfffa68fb59c8fbc65
ms.sourcegitcommit: 774f8f97a0b14cf1199bd1802178ccf536a25ade
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/17/2022
ms.locfileid: "9785812"
---
# <a name="add-social-identity-providers"></a>Társadalombiztosítási szolgáltatók hozzáadása

[!include [banner](includes/banner.md)]

Ez a témakör azt ismerteti, hogyan lehet a portálhoz hozzáadni a társadalombiztosítási szolgáltatókat Microsoft Azure.

A közösségi identitásszolgáltatók lehetővé teszik a felhasználók számára a saját közösségi fiókjaik hitelesítéshez történő használatát. A Dynamics 365 Commerce alkalmazásban a közösségi identitásszolgáltató hozzáadása opcionális. 

Ha a társadalombiztosítási szolgáltató hitelesítése nincs hozzáadva, akkor Azure Active Directory az alapértelmezett (Azure AD) B2C-profilok lesznek a felhasználói alap fő profiljai. A felhasználók kiválasztják a saját felhasználónevüket (az előnyben részesített e-mail címüket), és beállíthatnak egy jelszót. Az Azure AD B2C a felhasználókat közvetlenül hitelesíti. 

Ha a közösségi identitásszolgáltatói hitelesítés hozzá van adva, és a felhasználó a felajánlott közösségi identitásszolgáltatók egyikét választja, akkor is létrejön egy entitás az Azure AD B2C-bérlőn. Az Azure AD B2C ezt követően hitelesíteni fogja a felhasználó hitelesítő adatait a közösségi identitásszolgáltatóval.

> [!NOTE]
> Az identitásszolgáltató egy rekordot hoz létre a B2C-bérlőben, de a helyi fiókoktól eltérő formában, mivel egy külső identitásszolgáltató hivatkozását hívja meg a hitelesítéséhez. A felhasználó ugyanazt az e-mail címet használhatja több közösségi identitásszolgáltató esetében is ami azt jelenti, hogy a hitelesítéshez használt e-mail-felhasználónév nem biztos, hogy egyedi a bérlő számára. Az Azure AD B2C csak azt kényszeríti, hogy a B2C helyi fiókokban rendelkezzenek egyedi e-mail-címmel rendelkeznek.

A közösségi identitásszolgáltató hitelesítéshez történő hozzáadásához el kell látogatnia az identitásportálra és egy identitásszolgáltatói alkalmazást kell beállítania az Azure AD B2C dokumentációja utasításai alapján. A dokumentációra mutató hivatkozások listáját alább találja.

- [Amazon](/azure/active-directory-b2c/active-directory-b2c-setup-amzn-app)
- [Azure AD (egy bérlő)](/azure/active-directory-b2c/active-directory-b2c-setup-oidc-azure-active-directory)
- [Microsoft-fiók](/azure/active-directory-b2c/active-directory-b2c-setup-msa-app)
- [Facebook](/azure/active-directory-b2c/active-directory-b2c-setup-fb-app)
- [GitHub](/azure/active-directory-b2c/active-directory-b2c-setup-github-app)
- [Google](/azure/active-directory-b2c/active-directory-b2c-setup-goog-app)
- [LinkedIn](/azure/active-directory-b2c/active-directory-b2c-setup-li-app)
- [OpenID Connect](/azure/active-directory-b2c/active-directory-b2c-setup-oidc-idp)
- [Twitter](/azure/active-directory-b2c/active-directory-b2c-setup-twitter-app)

### <a name="add-and-set-up-a-social-identity-provider"></a>Közösségi identitásszolgáltató hozzáadása és beállítása

> [!NOTE]
> A társadalombiztosítási szolgáltatók hozzáadása nem kötelező lépés a vállalkozások közötti (B2C) bérlők beállításában Microsoft Dynamics 365 Commerce.

Egy közösségi identitásszolgáltató hozzáadásához és beállításához hajtsa végre az alábbi lépéseket.  

1. Az Azure portálon menjen az **Identitásszolgáltató** részre.
1. Válassza a **Hozzáadás** lehetőséget. Megjelenik az **Identitásszolgáltató** hozzáadása képernyő.
1. A **Név** csoportban adja meg a bejelentkezési képernyőn a felhasználók számára megjelenítendő nevet.
1. Az **Identitásszolgáltatótípusa** területen válasszon ki egy identitásszolgáltatót a listából.
1. Válassza ki az **OK** lehetőséget.
1. Válassza az **Identitásszolgáltató beállítása** lehetőséget, hogy elérje a **Közösségi identitásszolgáltató beállítása** képernyőt.
1. Az **Ügyfélazonosító** területen írja be az ügyfél azonosítóját, amelyet az identitásszolgáltató alkalmazás-beállításaiban kapott.
1. A **Titkos ügyfélkód** területen írja be aza titkos ügyfélkódot, amelyet az identitásszolgáltató alkalmazás-beállításaiban kapott.
1. Felhasználói folyamat csatolása a bejelentkezési/bejelentkezési irányelvekhez:
1. Nyissa meg az **Azure AD B2C – Felhasználói folyamatok (házirendek) \> {az Ön regisztrációs házirendje} \> Identitásszolgáltatók** lehetőséget.
1. A bejelentkezési/bejelentkezési felhasználói folyamat irányelvének csatolásához válassza ki a fiókhoz beállított összes identitásszolgáltatót. A folyamatok teszteléséhez jelölje be a Felhasználói **folyamat** futtatása minden egyes identitásszolgáltatóhoz. Egy új lap megjeleníti a bejelentkezési oldalt, amely az új azonosítószolgáltató kiválasztási négyzetét jeleníti meg.

A következő képen példákat talál az **Identitásszolgáltató hozzáadása** és az **Identitiásszolgáltató beállítása** képernyőkre az Azure AD B2C-ben.

![Közösségi identitásszolgáltató hozzáadása az alkalmazásához.](./media/B2CImage_14.png)

A következő képen egy példa látható arra, hogyan lehet kiválasztani az identitásszolgáltatót az Azure AD B2C **Identitásszolgáltatók** lapján.

![Válassza ki az egyes közösségi identitásszolgáltatókat, hogy engedélyezze azokat házirendjéhez.](./media/B2CImage_16.png)

A következő kép egy példát mutat be egy alapértelmezett bejelentkezési képernyőre, amely a közösségi identitásszolgáltató bejelentkezési gombját jeleníti meg.

> [!NOTE]
> Ha a Commerce alkalmazásban létrehozott egyéni oldalakat szeretné használni a felhasználói folyamatokhoz, a közösségi identitásszolgáltatók gombjait a Commerce modultár bővíthetőségi funkcióival kell hozzáadni. Továbbá, amikor az alkalmazásokat egy adott közösségi identitásszolgáltatónál állítja be, bizonyos esetekben az URL- vagy konfigurációs sztringekben megkülönböztethetik a kis- és nagybetűket. További információt a közösségi identitásszolgáltató csatlakozási utasításaiban talál.
 
![Példa az alapértelmezett bejelentkezési képernyőre, melyen látható a közösségi identitásszolgáltató bejelentkezési gombja.](./media/B2CImage_17.png)

## <a name="next-steps"></a>További lépések

A B2C bérlő beállításának folytatásához folytassa a Commerce [Headquarters frissítését az új Azure AD B2C-adatokkal](update-hq-aad-b2c-info.md).

## <a name="additional-resources"></a>További erőforrások

[B2C-bérlő beállítása a Commerce alkalmazásban](set-up-b2c-tenant.md)

[Meglévő B2C-bérlő Azure AD létrehozása vagy hivatkozása az Azure-portálon](create-link-aad-b2c-tenant.md)

[A B2C-alkalmazás létrehozása](create-b2c-app.md)

[Felhasználóifolyamat-irányelvek létrehozása](create-user-flow-policies.md)

[A Commerce Headquarters frissítése az új Azure AD B2C-adatokkal](update-hq-aad-b2c-info.md)

[A B2C-bérlő konfigurálása a Commerce webhelyszerkesztőben](config-b2c-tenant-site-builder.md)

[További B2C információk](additional-b2c-info.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
