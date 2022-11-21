---
title: B2C-pályázat létrehozása
description: Ez a témakör azt ismerteti, hogyan lehet a portálon vállalati felhasználói (B2C) alkalmazásokat Microsoft Azure létrehozni.
author: BrianShook
ms.date: 11/15/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2020-02-13
ms.openlocfilehash: d8956d51bac7bf2a162a370ae5ef1c7e7cdc1e2f
ms.sourcegitcommit: 774f8f97a0b14cf1199bd1802178ccf536a25ade
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/17/2022
ms.locfileid: "9785813"
---
# <a name="create-a-b2c-application"></a>B2C-pályázat létrehozása

[!include [banner](includes/banner.md)]

Ez a témakör azt ismerteti, hogyan lehet a portálon vállalati felhasználói (B2C) alkalmazásokat Microsoft Azure létrehozni.

Miután létrehozta a B2C bérlőt, létre kell hoznia egy B2C-alkalmazást Azure Active Directory az új (Azure AD) bérlőn belül, hogy kapcsolatba lépjen a Commerce alkalmazással.

A B2C alkalmazás létrehozásához kövesse az alábbi lépéseket.

1. Az Azure portálon válassza az **Alkalmazásregisztrációk** elemet, majd az **Új regisztráció** lehetőséget.
1. A **Név** mezőbe írja be a Azure AD B2C-alkalmazásnak adni kívánt nevet.
1. A **Támogatott fióktípusok** csoportban válassza a **Fiókok bármely identitásszolgáltatóban vagy szervezeti címtárban (felhasználók hitelesítéséhet a felhasználói folyamatokkal)**.
1. Az **Átirányítási URI** szolgáltatáshoz írja be a dedikált válasz URL-eket **Web** típusúként. A válasz URL-címekkel és a formázásukkal kapcsolatos információkért lásd: [Válasz URL-címek](#reply-urls) részt alább. Meg kell adni egy átirányítási URI-címet/válasz URL-címet Azure AD, amely lehetővé teszi a B2C rendszerből a webhelyre való átirányítást, amikor egy felhasználó hitelesíti magát. A válasz URL-címe hozzáadható a regisztrációs folyamat során, **illetve később is, ha a B2C** **alkalmazás Áttekintés szakaszában az "Átirányítás URI** **hozzáadása**" hivatkozásra kattint.
1. Az **Engedélyek** esetében válassza a **Rendszergazdai hozzájárulás biztosítása az OpenID-hoz és az offline hozzáférési engedélyezkhez** lehetőséget.
1. Válassza a **Regisztrálás** lehetőséget.
1. Válassza ki az újonnan létrehozott alkalmazást, és nyissa meg a Hitelesítés **menüt**. 
1. Ha meg van adva egy válasz URL-címe, **az Implicit támogatás és az áramlási** **folyamat mezőben válassza a Hozzáférési tokenek** **és az azonosítótokenek** lehetőséget az alkalmazás engedélyezéséhez, **majd válassza a Mentés lehetőséget**. Ha a regisztráció során nem lett megadva válasz URL-címe, **akkor ezen a lapon a Platform hozzáadása, a** **Webes** lehetőség kiválasztásával, majd az alkalmazás átirányítási URI-jének beírásával is hozzáadható. Ezt követően **a Implicit támogatás és áramlási** **folyamat szakasz elérhetővé válik a Hozzáférési tokenek és az azonosítótokenek** **beállításának kiválasztásához**.
1. Lépjen az Azure Portal **Áttekintés** menüjébe, és másolja be az **Alkalmazás (ügyfél) azonosítóját**. Jegyezze fel ezt az azonosítót a későbbi beállítási lépésekhez (később **Ügyfél GUID azonosítóként** hivatkoznak rá).

Az Azure AD B2C alkalmazásregisztrációiról további információt az [Azure Active Directory B2C új alkalmazásregisztrációs élménye](/azure/active-directory-b2c/app-registrations-training-guide) részben talál

### <a name="reply-urls"></a>Válasz URL-címek

A válasz URL-címek fontosak, mivel egy engedélyezési listát biztosítanak a visszajövő tartományokhoz, amikor a webhelye meghívja az Azure AD B2C-t a felhasználó hitelesítéséhez. Ez engedélyezi a hitelesített felhasználó visszaküldését abba a tartományba, ahonnan bejelentkeznek (a webhelye tartományába). 

A **Válasz URL** mezőben az **Azure AD B2c – Alkalmazások \> Új alkalmazás** képernyőjén a válasz URL-cím mezőben külön sorokat kell megadni a webhely-tartományához (ha a környezet létesítése megtörtént) és a Commerce által generált URL-címhez. Ezeknek az URL-címnek mindig érvényes URL-formátumot kell használniuk, és csak alap URL-címek lehetnek (nem lehetnek záró perjelek vagy elérési utak). Ezt követően az ``/_msdyn365/authresp`` karakterláncot a következő példáknak megfelelően kell hozzáfűzni az alap URL-címekhez.

- ``https://www.fabrikam.com/_msdyn365/authresp`` (A tartománynak teljesen meg kell egyeznie az e-kereskedelmi tartománnyal. Ha több tartománya van, akkor mindegyik tartományhoz hozzá kell adnia ezt az URL-címet.)
- ``https://fabrikam-prod.commerce.dynamics.com/_msdyn365/authresp``

## <a name="next-steps"></a>További lépések

A B2C bérlők Commerce rendszerből való beállításának folytatásához lépjen a felhasználói folyamat [irányelveinek létrehozására](create-user-flow-policies.md).

## <a name="additional-resources"></a>További erőforrások

[B2C-bérlő beállítása a Commerce alkalmazásban](set-up-b2c-tenant.md)

[Meglévő B2C-bérlő Azure AD létrehozása vagy hivatkozása az Azure-portálon](create-link-aad-b2c-tenant.md)

[Felhasználóifolyamat-irányelvek létrehozása](create-user-flow-policies.md)

[Közösségi identitásszolgáltatók hozzáadása (nem kötelező)](add-social-identity-providers.md)

[A Commerce Headquarters frissítése az új Azure AD B2C-adatokkal](update-hq-aad-b2c-info.md)

[A B2C-bérlő konfigurálása a Commerce webhelyszerkesztőben](config-b2c-tenant-site-builder.md)

[További B2C információk](additional-b2c-info.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
