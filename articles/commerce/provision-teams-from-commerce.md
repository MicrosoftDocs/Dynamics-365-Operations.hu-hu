---
title: Microsoft Teams kiépítése a Dynamics 365 Commerce rendszerből
description: Ez a témakör azt ismerteti, hogyan lehet szervezeti Microsoft Teams adatokat használni a következőből:Dynamics 365 Commerce
author: gvrmohanreddy
ms.date: 03/31/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-01-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 3dc9d0f20ec251f0908dda0017adaaeac1b43856
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8868935"
---
# <a name="provision-microsoft-teams-from-dynamics-365-commerce"></a>Microsoft Teams kiépítése a Dynamics 365 Commerce rendszerből

[!include [banner](includes/banner.md)]

Ez a témakör azt ismerteti, hogyan lehet szervezeti Microsoft Teams adatokat használni a következőből:Dynamics 365 Commerce

A Dynamics 365 Commerce segítségével könnyen kiépíthető a Teams, ha még nem állított be itt csapatokat a kiskereskedelmi áruházai számára. Ha kihasználja a Commerce rendszerből származó, a Teamsben használni kívánt, jól definiált információkat, az segíthet üzlete alkalmazottainak a Teams használatának megkezdésében. Ezen információk közé tartozik a szervezeti hierarchia, az üzletnevek, az alkalmazotti adatok és az Azure Active Directory (Azure AD) fiókok. 

A Teams létesítés folyamatának két lépése van:

1. A Teamsben hozzon létre egy-egy csapatot minden kiskereskedelmi üzlethez, és adja hozzá az üzlet dolgozóit a megfelelő csapat tagjaiként. Ha egy alkalmazott több kiskereskedelmi üzlethez is társítva van, a csoporttagság ezt a tényt fogja tükrözni. A Teams feladatainak közzétételét segítő, regionális vezetőket tagként tartalmazó kommunikációs csoport jön létre.
1. Töltse fel a szervezeti hierarchiát a Commerce rendszerből a Teamsbe.

## <a name="provision-teams-in-commerce-headquarters"></a>Teams kiépítése a Commerce központi felületén

A Microsoft Teams kiépítése előtt végezze el ezeket a feladatokat:

- Erősítse meg, hogy minden regionális vezető kommunikációs vezetői minősítést kapott.
- Ellenőrizze, hogy minden üzletvezető és dolgozó Azure-fiókja hozzá van társítva az adott vezető vagy dolgozó munkavégzői rekordjához a Commerce központi felületén.

A Teams kiépítéséhez a Commerce központi felületén kövesse az alábbi lépéseket.

1. Lépjen a **Retail és Commerce \> Csatorna beállítása \> Microsoft Teams integrációs konfiguráció** elemre.
1. A Művelet panelen válassza a **Csapatok kiépítése** lehetőséget. Létrejön egy **Csapatok kiépítése** nevű kötegelt feladat.
1. Menjen a **Rendszerfelügyelet \> Lekérdezések \> Kötegelt feladatok** ponthoz, és keresse meg azt a legutóbbi feladatot, amely a **Teams-kiépítés** leírását tartalmazza. Várjon, amíg a feladat be nem fejeződik.

> [!TIP]
> Ha a regionális vezetők, üzletvezetők és áruházi dolgozók egyike sem lett Teams-licenccel társítva, a következő hibaüzenet jelenhet meg: „Nem sikerült beolvasni az alkalmazható SKU-kategóriákat a felhasználóhoz.” A probléma megoldásához válassza a **Csoportok és tagok szinkronizálása** lehetőséget a Művelet panelen.

<!-- ![Dynamics 365 Commerce - Teams integration configuration.](media/D365-Commerce-Microsoft-Teams-Configuration_with_disclaimer.png)-->

## <a name="validate-teams-provisioning-in-the-teams-admin-center"></a>A Teams kiépítésének ellenőrzése a Teams felügyeleti központjában

A Microsoft Teams felügyeleti központban a Microsoft Teams-kiépítés ellenőrzéshez kövesse az alábbi lépéseket.
    
1. Lépjen a [Teams felügyeleti központjába](https://admin.teams.microsoft.com/), és jelentkezzen be az e-kereskedelmi bérlő rendszergazdájaként.
1. A bal oldali navigációs panelen válassza a **Csapatok** lehetőséget a kibontásához, majd válassza a **Csapatok kezelése** lehetőséget.
1. Ellenőrizze, hogy minden Commerce kiskereskedelmi üzlethez létrehoztak-e egy csapatot.
1. Jelöljön ki egy csapatot, és győződjön meg arról, hogy az áruházi dolgozók tagként hozzá lettek adva.
1. A bal oldali navigációs ablakban válassza a **Felhasználók** lehetőséget, és ellenőrizze, hogy az összes áruház összes alkalmazottja felhasználóként hozzá lett-e adva.

Az alábbi ábra egy példát mutat be a **Csapatok kezelése** lapra a Teams felügyeleti központban.

![Példa a Csapatok kezelése lapra a Teams felügyeleti központban.](media/Teams-FLW-Admin-Teams.png)

## <a name="upload-a-commerce-organizational-hierarchy-to-teams"></a>Commerce szervezeti hierarchia feltöltése a Teamsbe
    
A Commerce szervezeti hierarchia a Microsoft Teams alkalmazásban használható tevékenységek közzétételére az összes vagy kijelölt, ugyanazt a hierarchiastruktúrát használó üzletben.

Ha fel szeretne tölteni egy Commerce szervezeti hierarchiát a Teamsbe, kövesse az alábbi lépéseket.
    
1. A Commerce központi felületén lépjen a **Retail és Commerce \> Csatornabeállítás \> Microsoft Teams-intergráció konfigurációja** elemre.
1. Válassza a **Célzási hierarchia letöltése** lehetőséget, majd a szervezeti hierarchia vesszővel elválasztott értékfájlja (CSV) letöltéséhez válassza a **Kiskereskedelmi üzletek régiónként** lehetőséget.
1. Telepítse a Microsoft Teams PowerShell modult a [Microsoft Teams PowerShell telepítése](/microsoftteams/teams-powershell-install) lépéseit követve.
1. Amikor a rendszer kéri a Teams PowerShell ablakban, jelentkezzen be az Azure AD-bérlő rendszergazdai fiókjával.
1. Kövesse a [Csoportcélzási hierarchia beállítása](/microsoftteams/set-up-your-team-hierarchy) lépéseit a célzási hierarchia CSV-fájljának feltöltéséhez.

## <a name="verify-that-the-organizational-hierarchy-was-uploaded-to-teams"></a>Annak ellenőrzése, hogy a szervezeti hierarchia fel van-e töltve a Teamsbe

Annak ellenőrzéséhez, hogy a szervezeti hierarchia fel van-e töltve a Microsoft Teams alkalmazásba, tegye a következőket.

1. Jelentkezzen be a Teamsbe kommunikációs vezetőként.
1. A bal oldali navigációs ablakban válassza a **Feladatok tervező szerint** lehetőséget.
1. A **Közzétett listák** lapon hozzon létre egy új listát, amely üres feladattal rendelkezik.
1. Válassza a **Közzététel** lehetőséget. A szervezeti hierarchiának meg kell jelennie a **Közzététel címzettjének kiválasztása** párbeszédpanelen, amint az az alábbi ábrán látható.

![Példa szervezeti hierarchiára a Közzététel címzettjének kiválasztása párbeszédpanelen.](media/Microsoft-teams-verify-org-hierarchy.png)

## <a name="additional-resources"></a>További erőforrások

[A Dynamics 365 Commerce és a Microsoft Teams integrációjának áttekintése](commerce-teams-integration.md)

[A Dynamics 365 Commerce és a Microsoft Teams integrációjának engedélyezése](enable-teams-integration.md)

[Feladatkezelés szinkronizálása a Microsoft Teams és a Dynamics 365 Commerce-pénztár között](synchronize-tasks-teams-pos.md)

[Felhasználói szerepkörök kezelése a Microsoft Teams alkalmazásban](manage-user-roles-teams.md)

[Üzletek és csapatok leképezése, ha már vannak csapatok a Microsoft Teams alkalmazásban](map-stores-existing-teams.md)

[Dynamics 365 Commerce és Microsoft Teams integrációja – GYIK](teams-integration-faq.md)