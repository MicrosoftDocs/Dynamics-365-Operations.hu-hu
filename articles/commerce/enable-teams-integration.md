---
title: A Dynamics 365 Commerce és a Microsoft Teams integrációjának engedélyezése
description: Ez a témakör a Microsoft Dynamics 365 Commerce és a Microsoft Teams integrációjának engedélyezését ismerteti.
author: gvrmohanreddy
ms.date: 03/31/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-01-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: eb0b8b419b302fbd0bc107bca22f8b26774ba3c7
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/11/2021
ms.locfileid: "6019835"
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
1. Másolja az **Alkalmazás (ügyfél) azonosítója** értékét a regisztrált alkalmazás **Áttekintés** lapjára. Ezt az értéket arra fogja használni, hogy lehetővé tegye a Teams integrációját a Commerce központi felületén.
1. Másolja a tanúsítvány értékét, amely az 1. lépésben, a [tanúsítvány hozzáadásakor](/azure/active-directory/develop/quickstart-register-app#add-a-certificate) lett megadva. A tanúsítvány nyilvános kulcsként vagy alkalmazáskulcsként is ismert. Ezt az értéket arra fogja használni, hogy lehetővé tegye a Teams integrációját a Commerce központi felületén.

A Teams integráció engedélyezéséhez a Commerce központi felületén kövesse az alábbi lépéseket.

1. Lépjen a **Retail és Commerce \> Csatorna beállítása \> Microsoft Teams integrációs konfiguráció** elemre.
1. A műveleti ablaktáblán válassza a **Szerkesztés** lehetőséget.
1. Állítsa a **Microsoft Teams-integráció engedélyezése** beállítást **Igen** lehetőségre.
1. Az **Alkalmazásazonosító** és **Alkalmazáskulcs** mezőkben adja meg a Teams alkalmazás Azure Portalon való regisztrálásakor kapott értékeket.
1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.

Az alábbi ábra egy példát mutat be a Teams integrációs konfigurációjáról a Commerce központi felületén.

![Teams-integráció konfigurációja a Commerce központi felületén](media/D365-Commerce-Microsoft-Teams-Configuration_with_disclaimer.png)

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