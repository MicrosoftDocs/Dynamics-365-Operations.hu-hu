---
title: Dynamics 365 Commerce- és Microsoft Teams-integráció GYIK
description: Ez a témakör a Microsoft Dynamics 365 Commerce és a Microsoft Teams integrációjával kapcsolatos gyakori kérdésekre ad válaszokat.
author: gvrmohanreddy
manager: annbe
ms.date: 03/31/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-01-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: bf9aebb1c8ba7cf4fee3f0471a10872de1e23ce6
ms.sourcegitcommit: 34b478f175348d99df4f2f0c2f6c0c21b6b2660a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/16/2021
ms.locfileid: "5908856"
---
# <a name="dynamics-365-commerce-and-microsoft-teams-integration-faq"></a>Dynamics 365 Commerce- és Microsoft Teams-integráció GYIK

[!include [banner](includes/banner.md)]

Ez a témakör a Microsoft Dynamics 365 Commerce és a Microsoft Teams integrációjával kapcsolatos gyakori kérdésekre ad válaszokat.

### <a name="who-in-the-store-becomes-an-owner-of-a-team-while-provisioning-teams-from-commerce"></a>Az üzletben ki válik egy csapat tulajdonosvá a Teams Commerce rendszerből való létesítése alatt? 

A program minden üzletvezetőt automatikusan hozzáad a megfelelő csapatcsoporthoz, hogy végrehajtsa például egy saját csatorna hozzáadását és tagok hozzáadását vagy törlését. 

### <a name="how-do-i-assign-the-communications-manager-role-to-an-employee-in-commerce-headquarters"></a>Hogyan lehet a „kommunikációs vezető” szerepkört hozzárendelni a Commerce központi alkalmazotthoz? 

A kommunikációvezetők a Microsoft Teams szolgáltatásban feladatlisták létrehozására és közzétételére is képesek. A szervezetnek azokat az alkalmazottakat, akiknek kommunikációs vezetővé kell válniuk, hozzá kell rendelni a „kiskereskedelmi feladatkezelő” szerepkört a Commerce központban.

A következő lépések szerint rendelje hozzá a kiskereskedelmi feladatkezelő szerepkört egy alkalmazotthoz a Commerce központban.

1. Nyissa meg a következőt: **Retail és Commerce \> Alkalmazottak \> Felhasználók**.
1. Válasszon egy alkalmazottat.
1. A **Felhasználó szerepkörei** gyorslapon válassza a **Szerepkörök hozzárendelése** elemet.
1. A **Szerepkörök társítása a felhasználóhoz** párbeszédpanelen válassza ki a **Retail feladatkezelő** szerepkört, majd kattintsonaz **OK** gombra.

### <a name="how-do-i-make-a-specific-organization-hierarchy-available-to-upload-into-microsoft-teams"></a>Hogyan lehet egy adott szervezeti hierarchiát feltölthetővé tenni a Microsoft Teams szolgáltatásba?

A Commerce központban minden szervezeti hierarchia egy vagy több célhoz van társítva. Győződjön meg róla, hogy a hierarchiához, amelyet a Microsoft Teams szolgáltatásba ki szeretne építeni, társítva van a **Kiskereskedelmi jelentéskészítés**, ahogy a következő mintaképen látható. 

![Példa szervezeti hierarchia céljára a Commerce központ alkalmazásban](media/d365-commerce-organization-hierarchies-purpose.png)

### <a name="how-do-i-enable-retail-store-workers-to-sign-in-to-commerce-point-of-sale-pos-using-azure-active-directory-azure-ad"></a>Hogyan lehet engedélyezni a kiskereskedelmi üzlet dolgozóinak, hogy az Azure Active Directory (Azure AD) használatával jelentkezzenek be a Commerce pénztár (POS) alkalmazásba?

A Commerce pénztár bejelentkezési felületének az Azure AD hitelesítés használatára való konfigurálásával kapcsolatos további információkért lásd: [Azure Active Directory-hitelesítés engedélyezése pénztári bejelentkezéshez](aad-pos-logon.md).

### <a name="how-do-i-map-stores-and-corresponding-teams-in-commerce-headquarters-if-my-organization-has-already-created-teams-in-microsoft-teams"></a>Hogyan kell megfeleltetni az áruházakat és a megfelelő csapatokat a Commerce központon belül, ha a szervezetem már létrehozta a csapatokat a Microsoft Teams szolgáltatásban?

Ha vannak már létező csapatok, az üzletek és csapatok leképezésével kapcsolatos tudnivalókat lásd: [Üzletek és megfelelő csapatok leképezése, h a szervezetben már találhatók meglévő csapatok a Microsoft Teams szolgáltatásban](map-stores-existing-teams.md).

### <a name="how-do-i-clear-the-microsoft-graph-api-token-stored-in-the-session-storage"></a>Hogyan lehet törölni a munkamenet-tárolóban tárolt Microsoft Graph API-tokent?

A felhasználónak, aki a pénztárba (POS) Azure Active Directory (Azure AD) fiókkal jelentkezett be, ki kell jelentkeznie a pénztárból, vagy be kell zárnia az alkalmazást a munkamenet-tároló törléséhez. 

> [!TIP]
> A javasolt legjobb gyakorlat az, ha az üzlet dolgozóit mindig zárolják a POS terminált, vagy kijelentkeznek egy munkamenetből, amikor nem használják a terminált. 

### <a name="what-happens-if-a-store-doesnt-have-store-managers"></a>Mi történik, ha egy üzletnek nincs üzletvezetői?

Ha nincs vezető az üzletben, akkor nem jön létre csapatcsoport az üzlethez vagy a Teamsben. 

### <a name="what-happens-if-a-store-manager-leaves-the-company"></a>Mi történik, ha egy üzletvezető elhagyja a vállalatot?

Egy tulajdonos szerepkörrel rendelkező személy felvehet új üzletvezetőt a Commerce központban, és újra létesítheti a Teamst, hogy az új vezető a csoporthoz szükséges jogosultságokkal rendelkezzen a Teamsben. 

## <a name="additional-resources"></a>További erőforrások

[A Dynamics 365 Commerce és a Microsoft Teams integrációjának áttekintése](commerce-teams-integration.md)

[A Dynamics 365 Commerce és a Microsoft Teams integrációjának engedélyezése](enable-teams-integration.md)

[Microsoft Teams kiépítése a Dynamics 365 Commerce rendszerből](provision-teams-from-commerce.md)

[Feladatkezelés szinkronizálása a Microsoft Teams és a Dynamics 365 Commerce-pénztár között](synchronize-tasks-teams-pos.md)

[Felhasználói szerepkörök kezelése a Microsoft Teams alkalmazásban](manage-user-roles-teams.md)

[Üzletek és csapatok leképezése, ha már vannak csapatok a Microsoft Teams alkalmazásban](map-stores-existing-teams.md)
