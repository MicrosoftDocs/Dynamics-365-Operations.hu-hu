---
title: További B2C információk
description: Ez a témakör további tájékoztatást tartalmaz arról, hogyan lehet beállítani a vállalat-felhasználó (B2C) bérlőt a következőben:Microsoft Dynamics 365 Commerce
author: BrianShook
ms.date: 11/14/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2020-02-13
ms.openlocfilehash: b60ef15544cd30c44968ee7a588a8a9fb08e8223
ms.sourcegitcommit: 774f8f97a0b14cf1199bd1802178ccf536a25ade
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/17/2022
ms.locfileid: "9785807"
---
# <a name="additional-b2c-information"></a>További B2C információk

[!include [banner](includes/banner.md)]

Ez a témakör további tájékoztatást tartalmaz arról, hogyan lehet beállítani a vállalat-felhasználó (B2C) bérlőt a következőben:Microsoft Dynamics 365 Commerce

### <a name="customer-migration"></a>Ügyfelek áttelepítése

Ha egy korábbi identitásszolgáltatói platformról szeretné áttelepíteni a vevői rekordokat, forduljon a Dynamics 365 Commerce csapathoz a vevői áttelepítéssel kapcsolatosa igényei áttelepítéséhez.

A vevői áttelepítéssel kapcsolatos további Azure AD B2C dokumentációkat lásd: [Felhasználók áttelepítése az Azure Active Directory B2C megoldásba](/azure/active-directory-b2c/active-directory-b2c-user-migration).

### <a name="custom-policies"></a>Egyéni házirendek

További tájékoztatás az Azure AD B2C által kínált interakciók és irányelvfolyamatok testreszabásával a B2C szabványos házirendjein túl, lásd: [Egyéni házirendek az Azure Active Directory B2C megoldásban](/azure/active-directory-b2c/active-directory-b2c-overview-custom). 

### <a name="secondary-admin"></a>Másodlagos adminisztrátor

Egy opcionális, másodlagos adminisztrátori fiók is hozzáadható a B2C bérlő **Felhasználók** szakaszához. Ez lehet egy közvetlen fiók vagy egy általános fiók. Ha egy csoport erőforrásai között egy fiókot meg kell osztania, akkor egy közös fiókot is létre lehet hozni. Az Azure AD B2C-ben tárolt adatok érzékenysége miatt egy közös fiókot a vállalat biztonsági eljárásai szerint gondosan nyomon kell követni.

### <a name="set-up-a-custom-sign-in-domain"></a>Egyéni bejelentkezési tartomány beállítása

Azure AD A B2C lehetővé teszi a B2C bérlő Azure AD egyéni bejelentkezési tartományának beállítását. Az útmutatásért lásd [egyéni tartományok engedélyezése a Azure Active Directory B2C számára](/azure/active-directory-b2c/custom-domain). 

Egyéni bejelentkezési tartomány használata esetén a tartományt meg kell adni a Commerce Webhelyszerkesztőben.

A webhelyszerkesztőben egyéni bejelentkezési tartományt a következő lépések szerint lehet megadni.

1. A Webhelyszerkesztő jobb felső sarkában válassza ki a hely kapcsolóját, majd válassza **a Helyek kezelése lehetőséget**.
1. A bal oldali navigációs ablakban válassza a Bérlő **beállításai \> webhely hitelesítésének beállítását**.
1. Válassza a **Kezelés lehetőséget a Webhely hitelesítési** profiljai **szakaszban**.
1. A jobboldali menüben **válassza** a Szerkesztés gombot (szimbólumot) annak a hely hitelesítési profilnak a mellett, amelybe egyéni tartományt szeretne megadni.
1. A Webhely hitelesítési **profiljának** szerkesztése **párbeszédpanel** Egyéni tartomány bejelentkezése területen adja meg az egyéni bejelentkezési tartományt (például " login.fabrikam.com").

> [!WARNING]
> Amikor a B2C bérlő egyéni tartományát frissíti, a módosítás hatással van a Azure AD bérlő által létrehozott token kibocsátójának adataira. A kibocsátó adatai ezután az egyéni tartományt tartalmazzák, nem pedig a B2C által biztosított Azure AD alapértelmezett tartományt. **A** Commerce Headquarters más kibocsátó konfigurációja (**Retail and Commerce \> Headquarters \>\>\>** beállítása – Megosztott kereskedelmi paraméterek – Azonosító szolgáltatók) módosítja a rendszer és a webhely felhasználói közötti kommunikációt, potenciálisan új vevőrekordot hoz létre, ha egy felhasználó az új kibocsátóval szemben hitelesítést kap. Az egyéni tartományváltozásokat Azure AD alaposan tesztelni kell, mielőtt élő B2C környezetben átváltanának az egyéni tartományra.

## <a name="additional-resources"></a>További erőforrások

[B2C-bérlő beállítása a Commerce alkalmazásban](set-up-b2c-tenant.md)

[Meglévő B2C-bérlő Azure AD létrehozása vagy hivatkozása az Azure-portálon](create-link-aad-b2c-tenant.md)

[A B2C-alkalmazás létrehozása](create-b2c-app.md)

[Felhasználóifolyamat-irányelvek létrehozása](create-user-flow-policies.md)

[Közösségi identitásszolgáltatók hozzáadása (nem kötelező)](add-social-identity-providers.md)

[A Commerce Headquarters frissítése az új Azure AD B2C-adatokkal](update-hq-aad-b2c-info.md)

[A B2C-bérlő konfigurálása a Commerce webhelyszerkesztőben](config-b2c-tenant-site-builder.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
