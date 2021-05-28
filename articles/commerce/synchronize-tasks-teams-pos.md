---
title: Feladatkezelés szinkronizálása a Microsoft Teams és a Dynamics 365 Commerce-pénztár között
description: Ez a témakör azt ismerteti, hogyan kell szinkronizálni a feladatkezelést a Microsoft Teams és a Dynamics 365 Commerce pénztár (POS) között.
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
ms.openlocfilehash: 74d53a850113c83979fba6baa4ff3c3e5d9ca02d
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/11/2021
ms.locfileid: "6020627"
---
# <a name="synchronize-task-management-between-microsoft-teams-and-dynamics-365-commerce-pos"></a>Feladatkezelés szinkronizálása a Microsoft Teams és a Dynamics 365 Commerce-pénztár között

[!include [banner](includes/banner.md)]

Ez a témakör azt ismerteti, hogyan kell szinkronizálni a feladatkezelést a Microsoft Teams és a Dynamics 365 Commerce pénztár (POS) között.

A Teams integráció egyik fő célja a feladatkezelés szinkronizálása a pénztáralkalmazás és a Teams között. Ily módon az üzlet alkalmazottai a pénztáralkalmazást vagy a Teams alkalmazást használhatja feladatok kezelésére, és nem kell másik alkalmazásra váltani.

Mivel a Tervező a Teamsben található feladatok adattára, kapcsolatnak kell lennie a Teams és a Dynamics 365 Commerce között. Ez a hivatkozás egy adott üzletcsoporthoz megadott tervazonosító alapján jött létre.

A következő eljárások be mutatják, hogyan lehet beállítani a feladatkezelés szinkronizálását a pénztár- és a Teams-alkalmazások között.

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

## <a name="link-pos-and-teams-for-task-management"></a>A pénztár és a Teams összekapcsolása feladatkezeléshez

Ha a pénztárt és a Microsoft Teams alkalmazásokat feladatkezeléshez össze szeretné kapcsolni a Commerce központban, kövesse az alábbi lépéseket.

1. Lépjen ide: **Kiskereskedelem és kereskedelem \> Feladatkezelés \> Feladatok integrációja a Microsoft Teams szolgáltatással**.
1. A műveleti ablaktáblán válassza a **Szerkesztés** lehetőséget.
1. Állíts a **Feladatkezelés-integráció engedélyezése** elemet **Igen** értékre.
1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.
1. A Műveleti ablaktáblán kattintson a **Feladatkezelés beállítása** elemre. Értesítést kell kapnia, amely azt jelzi, hogy egy **Teams kiépítése** nevű kötegelt feladat létrehozása történik.
1. Menjen a **Rendszerfelügyelet \> Lekérdezések \> Kötegelt feladatok** ponthoz, és keresse meg azt a legutóbbi feladatot, amely a **Teams-kiépítés** leírását tartalmazza. Várjon, amíg a feladat be nem fejeződik.
1. A **1070-es CDX-feladat** futtatásával tegye közzé a tervazonosítót és az üzlet hivatkozásait a Retail Server kiszolgálón.

## <a name="additional-resources"></a>További erőforrások

[A Dynamics 365 Commerce és a Microsoft Teams integrációjának áttekintése](commerce-teams-integration.md)

[A Dynamics 365 Commerce és a Microsoft Teams integrációjának engedélyezése](enable-teams-integration.md)

[Microsoft Teams kiépítése a Dynamics 365 Commerce rendszerből](provision-teams-from-commerce.md)

[Felhasználói szerepkörök kezelése a Microsoft Teams alkalmazásban](manage-user-roles-teams.md)

[Üzletek és csapatok leképezése, ha már vannak csapatok a Microsoft Teams alkalmazásban](map-stores-existing-teams.md)

[Dynamics 365 Commerce és Microsoft Teams integrációja – GYIK](teams-integration-faq.md)
