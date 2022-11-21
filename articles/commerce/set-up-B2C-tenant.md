---
title: B2C-bérlő beállítása a Commerce-ben
description: Ez a témakör azt Azure Active Directory ismerteti, hogyan lehet beállítani a felhasználók által használt (Azure AD B2C) bérlőket a felhasználói webhely hitelesítésére Microsoft Dynamics 365 Commerce.
author: BrianShook
ms.date: 11/15/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2020-02-13
ms.openlocfilehash: 3421dd3d67198a99ac236a56cbb4f300cb591a03
ms.sourcegitcommit: 774f8f97a0b14cf1199bd1802178ccf536a25ade
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/17/2022
ms.locfileid: "9785137"
---
# <a name="set-up-a-b2c-tenant-in-commerce"></a>B2C-bérlő beállítása a Commerce-ben

[!include [banner](includes/banner.md)]

Ez a témakör azt Azure Active Directory ismerteti, hogyan lehet beállítani a felhasználók által használt (Azure AD B2C) bérlőket a felhasználói webhely hitelesítésére Dynamics 365 Commerce.

A Dynamics 365 Commerce az Azure AD B2C protokollt használja a felhasználók hitelesítő adatainak és hitelesítési folyamatainak támogatásához. A felhasználó ezeket a folyamatokat feliratkozhat, bejelentkezhet és alaphelyzetbe állíthatja jelszavát. Az Azure AD B2C érzékeny természetű felhasználói hitelesítési adatokat, például a felhasználónevet és a jelszót tárolja. A B2C-bérlőben a felhasználói rekordja a B2C helyi fiók rekordját vagy a B2C társadalmi identitásszolgáltatói rekordját fogja tárolni. Ezek a B2C rekordoknak a vevői rekordra mutatnak vissza a Commerce környezetben.

> [!WARNING] 
> Az Azure AD B2C megszünteti a régi (örökölt) felhasználói folyamatokat 2021. augusztus 1-jéig. Ezért érdemes megterveznie a felhasználói folyamatai áttelepítését az új, ajánlott verzióba. Az új verzió funkcióparitást és új funkciókat biztosít. A Commerce 10.0.15-ös vagy újabb verziójának modulkönyvtárát az ajánlott B2C felhasználói folyamatokkal kell használni. További információért lásd: [Felhasználói folyamatok az Azure Active Directory B2C-ben](/azure/active-directory-b2c/user-flow-overview).
 
 > [!NOTE]
 > A kereskedelmi értékelési környezetek egy előre betöltött Azure AD B2C bérlővel érkeznek demonstrációs célokra. Az értékelési környezetek esetén nincs szükség saját Azure AD B2C-bérlő betöltésére az alábbi lépésekkel.

> [!TIP]
> A Azure AD azonosítóvédelemmel és a feltételes hozzáféréssel tovább védheti webhelyének felhasználóit, és növelheti a Azure AD B2C bérlőinek biztonságát. A Azure AD B2C Premium P1 és Premium P2 bérlők számára elérhető képességek áttekintéséhez lásd: [Identitásvédelem és feltételes hozzáférés a Azure AD B2C oldalon](/azure/active-directory-b2c/conditional-access-identity-protection-overview).

## <a name="dynamics-environment-prerequisites"></a>Dynamics-környezet előfeltételei

Mielőtt hozzákezd, győződjön meg arról, hogy a Dynamics 365 Commerce-környezet és az e-kereskedelmi csatorna a következő előfeltételeknek megfelelően van konfigurálva.

- Állítsa az **AllowNonymousAccess** pénztári műveletek értékét „1” értékre a Commerce központban:
    1. Ugrás a **POS-műveletekhez**.
    1. A műveleti rácsban kattintson a jobb gombbal, majd válassza a **Testreszabás** parancsot.
    1. Válassza a **Mező hozzáadása** lehetőséget.
    1. Az elérhető oszlopok listájában válassza az **AllowAnonymousAccess** oszlopot a hozzáadáshoz.
    1. Válassza ki a **Frissítés** lehetőséget.
    1. A **612** „Vevő hozzáadása” műveletnél módosítsa az **AllowAnonymousAccess** gombra az „1” lehetőséget.
    1. Futtassa az **1090 (Pénztárgépek)** feladatot.
- Állítsa a vevői számla számsorozatának **Manuális** attribútumát **Nem** értékre a Commerce központban:
    1. Lépjen a **Retail és Commerce \> Központ beállítása \> Paraméterek \> Kinnlevőségi paraméterek** menüpontra.
    1. Válassza a **Számsorozatok** elemet.
    1. A **Vevői számla** sorban kattintson duplán a **Számsorozatkód** értékre.
    1. A számsorozat **Általános** gyorslapján állítsa a **Manuális** beállítást **Nem** értékre.

A Dynamics 365 Commerce környezet telepítését követően ajánlott a [Kiindulási adatok inicializálása](enable-configure-retail-functionality.md) a környezetben.

## <a name="next-steps"></a>További lépések

A B2C-bérlő [Azure AD Commerce rendszerbeli beállításának folytatásához lépjen tovább egy meglévő B2C-bérlő létrehozásához vagy hivatkozásához az Azure-portálon](create-link-aad-b2c-tenant.md).

## <a name="additional-resources"></a>További erőforrások

[Meglévő B2C-bérlő Azure AD létrehozása vagy hivatkozása az Azure-portálon](create-link-aad-b2c-tenant.md)

[A B2C-alkalmazás létrehozása](create-b2c-app.md)

[Felhasználóifolyamat-irányelvek létrehozása](create-user-flow-policies.md)

[Közösségi identitásszolgáltatók hozzáadása (nem kötelező)](add-social-identity-providers.md)

[A Commerce Headquarters frissítése az új Azure AD B2C-adatokkal](update-hq-aad-b2c-info.md)

[A B2C-bérlő konfigurálása a Commerce webhelyszerkesztőben](config-b2c-tenant-site-builder.md)

[További B2C információk](additional-b2c-info.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
