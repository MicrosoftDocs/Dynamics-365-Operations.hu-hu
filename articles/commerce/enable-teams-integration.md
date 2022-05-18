---
title: A Dynamics 365 Commerce és a Microsoft Teams integrációjának engedélyezése
description: Ez a témakör a Microsoft Dynamics 365 Commerce és a Microsoft Teams integrációjának engedélyezését ismerteti.
author: gvrmohanreddy
ms.date: 02/17/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-01-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: dfada577ab97fdb9912c22d2399529f934b25d54
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/04/2022
ms.locfileid: "8695734"
---
# <a name="enable-dynamics-365-commerce-and-microsoft-teams-integration"></a>A Dynamics 365 Commerce és a Microsoft Teams integrációjának engedélyezése

[!include [banner](includes/banner.md)]

Ez a témakör a Microsoft Dynamics 365 Commerce és a Microsoft Teams integrációjának engedélyezését ismerteti.

A Teams alkalmazást Dynamics 365 Commerce rendszerből származó információkkal információkkal szeretné kiépíteni, és szinkronizálni szeretné a kezelési funkciókat a Teams és a pénztár (POS) alkalmazás között, akkor engedélyeznie kell a Commerce központi felületének integrációs funkcióit.

> [!NOTE]
> Amikor engedélyezi a Teams integrációját, hozzájárul ahhoz, hogy adatait megossza a Teams alkalmazással. Előfordulhat, hogy a Teams alkalmazással megosztott adatok a Commerce-adatoktól eltérő országban találhatók, és eltérő megfelelőségi szabványok vonatkoznak rájuk. A további tudnivalókat lásd: [Microsoft megbízhatósági központ](https://www.microsoft.com/trust-center). A Microsoft adatvédelmi irányelveit a [Microsoft adatvédelmi nyilatkozatában](https://aka.ms/privacy) találja.

## <a name="enable-teams-integration"></a>A Teams-integráció engedélyezése

A Microsoft Teams és a Commerce integrációjának engedélyezése előtt regisztrálnia kell a Teams alkalmazást a bérlővel az Azure Portalon.

A Teams alkalmazásnak a bérlővel való regisztrálásához az Azure Portalon, kövesse az alábbi lépéseket.

1. A Teams alkalmazás Azure Portalon található bérlőjével történő regisztrálásához kövesse a következő lépéseit: [Rövid útmutató: Alkalmazások regisztrálása a Microsoft Identity platformmal](/azure/active-directory/develop/quickstart-register-app).
1. Az Alkalmazásregisztráció **lapon** válassza ki az előző lépésben létrehozott alkalmazást. Ezután a Hitelesítés lapon **válassza** a Platform **hozzáadása lehetőséget**.
1. A párbeszédpanelen válassza a Webes **lehetőséget**. Ezután az ÁtirányításI **URL-címek** mezőbe írja be az URL-címet **\<HQUrl\> az /oauth formátumban**. Csere **\<HQUrl\>** a Commerce Headquarters URL-címére (például `https://hxennugbjtweufmdeo385f47fadb6aa9a0aos.cloudax.int.dynamics.com/oauth`).
1. A regisztrált **alkalmazás** Áttekintés lapján másolja át **az alkalmazás (ügyfél) azonosítójának** értékét. Ezt az értéket meg kell adnia ahhoz, hogy a következő szakaszban engedélyezni tudja a Teams-integrációt a Commerce Headquarters szolgáltatásban.
1. Az ügyféltitk hozzáadásához [kövesse az Ügyféltitk](/azure/active-directory/develop/quickstart-register-app#add-a-client-secret) hozzáadása útmutatót. Ezután másolja át az **ügyfél Titkos érték** értékét. Ezt az értéket meg kell adnia ahhoz, hogy a következő szakaszban engedélyezni tudja a Teams-integrációt a Commerce Headquarters szolgáltatásban.
1. Válassza ki **az API-engedélyeket**, majd válassza az Engedély **hozzáadása lehetőséget**.
1. A Kérés **API-engedélyeinek** párbeszédpanelen válassza a Microsoft Graph **gombra,** válassza **a Delegált engedélyek lehetőséget,** **bontsa** ki a Csoportot, **válassza a Group.ReadWrite.All** lehetőséget, **majd válassza az Engedélyek hozzáadása lehetőséget**.
1. A Kérés **API-engedélyeinek** párbeszédpanelen válassza az Engedély hozzáadása lehetőséget, **jelölje** be a Microsoft Graph **gombra, válassza** **ki az alkalmazásengedélyeket,** **bontsa ki a Csoport gombra,** válassza a **Group.ReadWrite.All** lehetőséget, **majd válassza az Engedélyek hozzáadása lehetőséget.**
1. A Kérés **API-engedélyeinek** párbeszédpanelen válassza az Engedély **hozzáadása lehetőséget**. Keresse meg **és válassza ki a Saját szervezet által használt API-k** **Microsoft Teams lapon a Retail Service** szolgáltatást.
1. Válassza a Delegált engedélyeket **, bontsa ki** a Feladat **közzététele gombra, válassza** a TaskPublising.ReadWrite.All **lehetőséget,** majd válassza az Engedélyek hozzáadása lehetőséget **.** A további tudnivalókat lásd [az Ügyfélalkalmazás konfigurálása web API elérésére.](/azure/active-directory/develop/quickstart-configure-app-access-web-apis)

A Teams integráció engedélyezéséhez a Commerce központi felületén kövesse az alábbi lépéseket.

1. Lépjen a **Retail és Commerce \> Csatorna beállítása \> Microsoft Teams integrációs konfiguráció** elemre.
1. A műveleti ablaktáblán válassza a **Szerkesztés** lehetőséget.
1. Állítsa a **Microsoft Teams-integráció engedélyezése** beállítást **Igen** lehetőségre.
1. Az Alkalmazásazonosító **mezőben** adja **meg azt az alkalmazásazonosítót (ügyfél),** amelyet a Teams alkalmazásnak az Azure-portálon való regisztrációja során kapott.
1. Az Alkalmazás kulcsmezőben **adja** meg azt a Titkos értéket, amelyet akkor kapott, **amikor** az Azure-portálon hozzáadta az ügyféltitkot.
1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.

Az alábbi ábra egy példát mutat be a Teams integrációs konfigurációjáról a Commerce központi felületén.

![Teams-integráció konfigurációja a Commerce központi felületén.](media/D365-Commerce-Microsoft-Teams-Configuration_with_disclaimer.png)

## <a name="disable-teams-integration"></a>A Teams-integráció letiltása

A Microsoft Teams-integráció letiltásához a Commerce központi felületén kövesse az alábbi lépéseket.

1. Lépjen a **Retail és Commerce \> Csatorna beállítása \> Microsoft Teams integrációs konfiguráció** elemre.
1. A műveleti ablaktáblán válassza a **Szerkesztés** lehetőséget.
3. Állítsa a **Microsoft Teams-integráció engedélyezése** beállítást **Nem** lehetőségre.
4. Törölje az értékeket az **Alkalmazásazonosító** és az **Alkalmazáskulcs** mezőkből.
1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.

> [!NOTE]
> A Teams Commerce szolgáltatással való integrációjának letiltása után a POS-terminálok a továbbiakban nem jelenítik meg a Teams alkalmazásból közzétett feladatokat.

## <a name="additional-resources"></a>További erőforrások

[A Dynamics 365 Commerce és a Microsoft Teams integrációjának áttekintése](commerce-teams-integration.md)

[Microsoft Teams kiépítése a Dynamics 365 Commerce rendszerből](provision-teams-from-commerce.md)

[Feladatkezelés szinkronizálása a Microsoft Teams és a Dynamics 365 Commerce-pénztár között](synchronize-tasks-teams-pos.md)

[Felhasználói szerepkörök kezelése a Microsoft Teams alkalmazásban](manage-user-roles-teams.md)

[Üzletek és csapatok leképezése, ha már vannak csapatok a Microsoft Teams alkalmazásban](map-stores-existing-teams.md)

[Dynamics 365 Commerce és Microsoft Teams integrációja – GYIK](teams-integration-faq.md)
