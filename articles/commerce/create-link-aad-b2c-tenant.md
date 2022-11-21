---
title: Meglévő B2C-bérlő Azure AD létrehozása vagy hivatkozása az Azure-portálon
description: Ez a témakör azt Azure Active Directory ismerteti, hogyan lehet a portálon létező (Azure AD) vállalat-felhasználó (B2C) bérlőt létrehozni, illetve hivatkozással összekapcsolni Microsoft Azure.
author: BrianShook
ms.date: 11/15/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2020-02-13
ms.openlocfilehash: 0aa12387f00ffc3dd10688c6385c7952f089ab12
ms.sourcegitcommit: 774f8f97a0b14cf1199bd1802178ccf536a25ade
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/17/2022
ms.locfileid: "9785816"
---
# <a name="create-or-link-to-an-existing-azure-ad-b2c-tenant-in-the-azure-portal"></a>Meglévő B2C-bérlő Azure AD létrehozása vagy hivatkozása az Azure-portálon

[!include [banner](includes/banner.md)]

Ez a témakör azt ismerteti, hogyan lehet létrehozni és hivatkozni a Azure Active Directory portál egy (Azure AD) vállalat és felhasználó között (B2C) bérlőre Microsoft Azure. A további tudnivalókat lásd [: Azure Active Directory B2C bérlő létrehozása](/azure/active-directory-b2c/tutorial-create-tenant).

A következő lépések szerint hozhatja Azure AD létre az Azure-portálon meglévő B2C-bérlőt, illetve hivatkozását.

1. Jelentkezzen be az [Azure portálra](https://portal.azure.com/).
1. Válassza az Azure Portal menü **Erőforrás létrehozása** pontját. Ügyeljen arra, hogy a Commerce környezethez kapcsolt előfizetést és könyvtárat használja.

    ![Erőforrás létrehozása az Azure-portálon.](./media/B2CImage_1.png)

1. Nyissa meg az **Identitás \> Azure Active Directory B2C** elemet.
1. A **AAD B2C-bérlő létrehozása vagy hivatkozás egy meglévő bérlőre az Azure Portal webhelyen** lapon, használja vállalat igényeinek leginkább megfelelő alábbi lehetőséget:

    - **Új B2C bérlő létrehozása Azure AD: Ezzel a** Azure AD beállítással új B2C-bérlőt hozhat létre.
        1. Válassza az **Új Azure AD B2C-bérlő létrehozása** lehetőséget.
        1. A **Szervezet neve** területen írja be a szervezet nevét.
        1. A **Kezdeti tartománynév** mezőbe írja be a kezdeti tartománynevet.
        1. Az **Ország vagy régió** helyen válassza ki az országot vagy régiót.
        1. Válassza a **Létrehozás** lehetőséget a bérlő létrehozásához.

     ![Új Azure AD-bérlő létrehozása.](./media/B2CImage_2.png)

     - **Meglévő Azure AD B2C-bérlő csatolása a saját Azure előfizetésemhez**: Akkor használja ezt a lehetőséget, ha már van egy Azure AD B2C bérlője, amelyhez csatolni kívánja.
        1. Válassza ki a **Meglévő Azure AD B2C bérlő csatolása saját Azure előfizetéshez** lehetőséget.
        1. Az **Azure AD B2C bérlő** esetében válassza ki a megfelelő B2C-bérlőt. Ha a kiválasztási mezőben a „Nem jogosult B2C-bérlők találhatók” üzenet jelenik meg, akkor nem rendelkezik jogosult B2C Bérlővel, és újat kell létrehoznia.
        1. Az **Erőforráscsoport** helyen válassza az **Új létrehozása** lehetőséget. Írja be annak a csoportnak a **Nevét**, amely a bérlőt fogja tartalmazni, válassza ki az **Erőforráscsoport helyét** ,majd válassza a **Létrehozás** parancsot.

    ![Válassza ki a Meglévő Azure AD B2C bérlő csatolása saját Azure előfizetéshez lehetőséget.](./media/B2CImage_3.png)

1. Miután létrehozta az új Azure AD B2C könyvtárat (ez néhány percet is igénybe vehet), az új könyvtárra mutató hivatkozás megjelenik az irányítópulton. Ez a link közvetlenül az „Üdvözli az Azure Active Directory B2C” oldalra mutat.

    ![Csatolás az új könyvtárhoz Azure AD](./media/B2CImage_4.png)

> [!NOTE]
> Ha több előfizetése van a Azure-fiókján belül, vagy a B2C-bérlőt egy aktív előfizetés csatolása nélkül állította be, akkor egy **Hibaelhárítási** banner fogja arra kérni hogy a bérlőt egy előfizetéshez kapcsolja. Válassza ki a hibaelhárítási üzenetet, majd kövesse az utasításokat az előfizetési probléma megoldásához.

A következő kép egy Azure AD B2C **Hibaelhárítási** bannert mutat be.

![Figyelmeztetés, amely azt mutatja, hogy könyvtárának nincs aktív előfizetése.](./media/B2CImage_5.png)

## <a name="next-steps"></a>További lépések

A B2C-bérlő Commerce alkalmazásban való beállításának folytatásához folytassa [a B2C-alkalmazás létrehozásához](create-b2c-app.md).

## <a name="additional-resources"></a>További erőforrások

[B2C-bérlő beállítása a Commerce alkalmazásban](set-up-b2c-tenant.md)

[A B2C-alkalmazás létrehozása](create-b2c-app.md)

[Felhasználóifolyamat-irányelvek létrehozása](create-user-flow-policies.md)

[Közösségi identitásszolgáltatók hozzáadása (nem kötelező)](add-social-identity-providers.md)

[A Commerce Headquarters frissítése az új Azure AD B2C-adatokkal](update-hq-aad-b2c-info.md)

[A B2C-bérlő konfigurálása a Commerce webhelyszerkesztőben](config-b2c-tenant-site-builder.md)

[További B2C információk](additional-b2c-info.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
