---
title: Feladatkezelés szinkronizálása a Microsoft Teams és a Dynamics 365 Commerce-pénztár között
description: Ez a témakör leírja, hogyan kell szinkronizálni a feladatkezelést a Microsoft Teams Dynamics 365 Commerce pénztár és a pénztár között.
author: gvrmohanreddy
ms.date: 11/04/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-01-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: f339ae031f11ad850dab47f84bc9823cf6776e74
ms.sourcegitcommit: 9e2e54ff7d15aa51e58309da3eb52366328e199d
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/04/2022
ms.locfileid: "9746097"
---
# <a name="synchronize-task-management-between-microsoft-teams-and-dynamics-365-commerce-pos"></a>Feladatkezelés szinkronizálása a Microsoft Teams és a Dynamics 365 Commerce-pénztár között

[!include [banner](includes/banner.md)]

Ez a témakör leírja, hogyan kell szinkronizálni a feladatkezelést a Microsoft Teams Dynamics 365 Commerce pénztár és a pénztár között.

A Teams integráció egyik fő célja a feladatkezelés szinkronizálása a pénztáralkalmazás és a Teams között. Ily módon az üzlet alkalmazottai a pénztáralkalmazást vagy a Teams alkalmazást használhatja feladatok kezelésére, és nem kell másik alkalmazásra váltani.

Mivel a Tervező a Teamsben található feladatok adattára, kapcsolatnak kell lennie a Teams és a Dynamics 365 Commerce között. Ez a hivatkozás egy adott üzletcsoporthoz megadott tervazonosító alapján jött létre.

A következő eljárások be mutatják, hogyan lehet beállítani a feladatkezelés szinkronizálását a pénztár- és a Teams-alkalmazások között.

## <a name="link-pos-and-teams-for-task-management"></a>A pénztár és a Teams összekapcsolása feladatkezeléshez

Ha a pénztárt és a Microsoft Teams alkalmazásokat feladatkezeléshez össze szeretné kapcsolni a Commerce központban, kövesse az alábbi lépéseket.

> [!NOTE]
> Mielőtt megpróbálja integrálni a feladatkezelést a Teams alkalmazással, győződjön meg róla, hogy engedélyezte [Dynamics 365 Commerce és integrálta az integrációt Microsoft Teams](enable-teams-integration.md). 

1. Lépjen ide: **Kiskereskedelem és kereskedelem \> Feladatkezelés \> Feladatok integrációja a Microsoft Teams szolgáltatással**.
1. A műveleti ablaktáblán válassza a **Szerkesztés** lehetőséget.
1. Állíts a **Feladatkezelés-integráció engedélyezése** elemet **Igen** értékre.
1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.
1. A Műveleti ablaktáblán kattintson a **Feladatkezelés beállítása** elemre. Értesítést kell kapnia, **amely azt jelzi, hogy létrehoznak egy Teams-létesítő** nevű kötegelt feladatot.
1. Menjen a **Rendszerfelügyelet \> Lekérdezések \> Kötegelt feladatok** ponthoz, és keresse meg azt a legutóbbi feladatot, amely a **Teams-kiépítés** leírását tartalmazza. Várjon, amíg a feladat be nem fejeződik.
1. A **1070-es CDX-feladat** futtatásával tegye közzé a tervazonosítót és az üzlet hivatkozásait a Retail Server kiszolgálón.

## <a name="publish-a-test-task-list-in-teams"></a>Tesztfeladatlista közzététele a Teamsben

A következő eljárás feltételezi, hogy az üzletcsapatok első alkalommal használják a Microsoft Teams feladatkezelés integrációját a Commerce alkalmazással.

A tesztfeladatok listájának a Teamsben való közzétételéhez hajtsa végre ezeket a lépéseket.

1. Jelentkezzen be a Teamsbe kommunikációs vezetőként. A kommunikációs vezetők általában olyan felhasználók, akiknek a Commerce-ben **Területi vezetői** szerepkörük van.
1. A bal oldali navigációs ablakban válassza a **Feladatok tervező szerint** lehetőséget.
1. A **Közzétett listák** lapon válassza az **Új lista** lehetőséget a bal alsó részén, és nevezze el az új listát **Tesztfeladatlistának**.
1. Válassza a **Létrehozása** lehetőséget. Az új lista a **Vázlatok** alatt jelenik meg.
1. A **Feladat címe** részben adja az első feladatnak a **Teams-integráció tesztelése** címet. Ezután válassza a **Bevitel** lehetőséget.
1. A **Vázlatok** listán válassza ki a feladatlistát. Ezután válassza a  **Közzététel** lehetőséget a jobb felső sarokban.
1. A **Közzététel címzettjének kiválasztása** párbeszédpanelen, válassza ki azokat a csoportokat, amelyek megkapják a tesztfeladatok listáját.
1. Válassza a **Tovább** gombot a közzétételi terv áttekintéshez. Ha módosításokat kell végrehajtania, válassza a  **Vissza** lehetőséget. 
1. Válassza a **Megerősítés folytatáshoz** lehetőséget, majd válassza a **Közzététel** lehetőséget.
1. A közzététel befejeződése után a **Közzétett listák** lap tetején található üzenet jelzi, hogy sikeresen megtörtént-e a feladatlista kézbesítése.

További információkért lásd: [Feladatlisták közzététele a munka létrehozásához és követéséhez a szervezetben](https://support.microsoft.com/office/publish-task-lists-to-create-and-track-work-in-your-organization-095409b3-f5af-40aa-9f9e-339b54e705df).

> [!NOTE]
> Miután sikeresen megtörtént a feladatlista közzététele a Teamsben, a feladatok megjelennek a POS-terminálon. A POS-vezetőknek és pénztárosoknek ezután be kell Azure AD jelentkeznie a POS-be. A további tudnivalókat lásd [Azure Active Directory a POS-bejelentkezéshez való hitelesítés engedélyezése cikknél](aad-pos-logon.md). 

## <a name="additional-resources"></a>További erőforrások

[A Dynamics 365 Commerce és a Microsoft Teams integrációjának áttekintése](commerce-teams-integration.md)

[A Dynamics 365 Commerce és a Microsoft Teams integrációjának engedélyezése](enable-teams-integration.md)

[Microsoft Teams kiépítése a Dynamics 365 Commerce rendszerből](provision-teams-from-commerce.md)

[Felhasználói szerepkörök kezelése a Microsoft Teams alkalmazásban](manage-user-roles-teams.md)

[Üzletek és csapatok leképezése, ha már vannak csapatok a Microsoft Teams alkalmazásban](map-stores-existing-teams.md)

[Dynamics 365 Commerce és Microsoft Teams integrációja – GYIK](teams-integration-faq.md)
