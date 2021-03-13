---
title: Eszközkezelés mobil munkaterület beállítása
description: Ez a témakör azt mutatja be, hogyan lehet beállítani a Microsoft Dynamics 365 Supply Chain Management és a Finance and Operations (Dynamics 365) mobilalkalmazást egy eszközkezelési mobil munkaterület futtatására, amely a dolgozók számára az eszközkezelési feladatok elvégzésére használható.
author: johanhoffmann
manager: tfehr
ms.date: 01/15/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-12-22
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 9c2410c50b5d289792e2cc364674e1e093653590
ms.sourcegitcommit: 995c678b4715be267f1f97148902a6b3dde3bcab
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/20/2021
ms.locfileid: "5033211"
---
# <a name="set-up-the-asset-management-mobile-workspace"></a>Eszközkezelés mobil munkaterület beállítása

[!include [banner](../includes/banner.md)]

Ez a témakör azt mutatja be, hogyan lehet beállítani a Microsoft Dynamics 365 Supply Chain Management és a Finance and Operations (Dynamics 365) mobilalkalmazást egy **Eszközkezelési** mobil munkaterület futtatására, amely a dolgozók számára az eszközkezelési feladatok elvégzésére használható.

## <a name="set-up-maintenance-worker-users-in-supply-chain-management"></a>Karbantartási dolgozói felhasználók beállítása a Supply Chain Management szolgáltatásban

Az alábbi lépéseket kell követni minden olyan felhasználó számára, akinek hozzá kell férni az **Eszközkezelés** mobil munkaterülethez.

1. A Supply Chain Management szolgáltatásban ugorjon az **Emberi erőforrások \> Dolgozók** elemre, és győződjön meg róla, hogy létezik dolgozórekord a beállítani kívánt felhasználóhoz. Hozzon létre igény szerint egy új dolgozói rekordot.
1. Ugorjon az **Eszközkezelés \> Beállítás \> Dolgozók \> Dolgozók** elemre, és győződjön meg róla, hogy az előző lépésben azonosított (vagy létrehozott) dolgozórekord egy karbantartási dolgozói rekordhoz van leképezve. Szükség szerint hozzon létre egy új karbantartási dolgozói rekordot, és állítsa a **Dolgozó** mezőt az előző lépésből származó dolgozórekordra.
1. Ugorjon az **Eszközkezelés \> Beállítás \> Dolgozók \> Karbantartási dolgozói csoportok** elemre, és győződjön meg róla, hogy az előző lépésben azonosított (vagy létrehozott) karbantartási dolgozói rekord egy karbantartási dolgozói csoporthoz van leképezve.
1. Ugorjon a **Rendszerfelügyelet \> Felhasználók** elemre.
1. Válassza ki a releváns felhasználót a rácsban.
1. A **Felhasználói adatok** gyorslapon állítsa a **Személy** mezőt arra a dolgozói fiókra, amelyet szeretne hozzárendelni az aktuális felhasználói fiókhoz. Ennek a dolgozói fióknak az 1. lépésben azonosított (vagy létrehozott) dolgozói rekordnak kell lennie, amely a 2. lépésben egy karbantartási dolgozói rekordhoz van leképezve.

> [!NOTE]
> A felhasználói engedélyek és a biztonsági szerepkörök úgy alkalmazandók az **Eszközkezelés** mobil munkaterület funkcióira, ahogyan a Supply Chain Management felhasználói felületének funkcióira. Emiatt minden felhasználónak, aki úgy van beállítva, hogy hozzáférjen az **Eszközkezelés** mobil munkaterülethez, olyan biztonsági szerepkörökkel kell rendelkeznie, amelyek a hasonló műveleteknek közvetlenül a Supply Chain Managementben való közvetlen végrehajtásához szükségesek.

## <a name="publish-the-asset-management-mobile-workspace"></a>Eszközkezelés mobil munkaterület közzététele

Ahhoz, hogy elérhetővé tegye az eszközkezelési funkciókat a Finance and Operations (Dynamics 365) mobilalkalmazásban, közzé kell tennie az **Eszközkezelés** mobil munkaterületet.

1. A Supply Chain Management szolgáltatásban válassza a **Beállítások** gombot (a jobb felső sarkában látható fogaskerekek szimbólumát), majd válassza a menüben a **Mobilalkalmazás** lehetőséget.
1. A **Mobilalkalmazás-kezelés** párbeszédpanelen keresse meg az **Eszközkezelés** csempét. Ha azt a szöveget tartalmazza, hogy "Metaadatok között - nincs közzétéve", akkor a munkaterület még nincs közzétéve. Ha a "Metaadatok között - közzétett" szöveget tartalmazza, a munkaterület már közzé van téve, és a művelet hátralévő részét kihagyhatja.

    ![Mobilalkalmazás párbeszédpanel kezelése](media/mobile-workspaces.png "Mobilalkalmazás párbeszédpanel kezelése")

1. Válassza az **Eszközkezelés** csempét, majd az eszköztár **Közzététel** gombját. Néhány másodperc múlva értesítést kell kapnia arról, hogy sikeresen megtörtént a munkaterület közzététele. Ezenkívül a csempe szövegének a "Metaadatok között – közzétéve" szövegre kell váltania.

## <a name="install-and-set-up-the-finance-and-operations-dynamics-365-mobile-app"></a>A Finance and Operations (Dynamics 365) mobilalkalmazás telepítése és beállítása

1. Ha mobileszközére telepítenie kell a **Microsoft Finance and Operations (Dynamics 365)** alkalmazást, ugorjon a következő alkalmazásáruházak egyikére:

    - [Google Android eszközök esetében](https://go.microsoft.com/fwlink/?linkid=850662)
    - [Apple IOS eszközök esetében](https://go.microsoft.com/fwlink/?linkid=850663)

1. Nyissa meg Finance and Operations (Dynamics 365) alkalmazást. A bejelentkezési oldalnak meg kell jelenni. A **Bejelentkezés** mezőben adja meg a saját Supply Chain Management URL-címét, vagy válassza ki a közelmúltbeli URL-címet a **Közelmúltbeli környezetek** listában, majd koppintson a **Csatlakozás** gombra.

    ![Bejelentkezési oldal](media/mobile-app-sign-in.png "Bejelentkezési oldal")

1. Ha a program kéri a kapcsolat megerősítését, jelölje be a **Megértettem** jelölőnégyzetet, majd koppintson a **Csatlakozás** gombra.
1. A **Fiókválasztó** oldalon Microsoft-fiókjával jelentkezhet be a mobilalkalmazásba.

    Megjelenik a **Munkaterületek** oldal. Felsorolja a saját Supply Chain Management példánya által közzétett összes mobil munkaterületet.

    ![Munkaterületek listája](media/mobile-app-workspaces.png "Munkaterületek listája")

1. Ha módosítania kell a jogi személyt (vállalatot), kattintson a bal felső sarkában látható Menü gombra (néha hamburgernek vagy a hamburgergombnak is nevezik), majd válassza a **Vállalat módosítása** lehetőséget.

    ![A jogi személy módosítása](media/mobile-app-change-comp.png "A jogi személy módosítása")

1. Válassza ki a **Munkaterületek** lapon azt a munkaterületet, amelyet használni szeretne a megnyitásához.

    ![Eszközkezelési mobil munkaterület](media/mobile-app-asset-workspace.png "Eszközkezelési mobil munkaterület")

## <a name="work-with-the-asset-management-mobile-workspace"></a>Eszközkezelés mobil munkaterület használata

Az **Eszközkezelés** mobil munkaterület használatával kapcsolatos további tudnivalókat lásd az [Eszközkezelés mobil munkaterület használata](asset-management-mobile-workspace.md) oldalt.

A Finance and Operations (Dynamics 365) mobilalkalmazással kapcsolatos további tudnivalókat lásd: [Mobilalkalmazás kezdőlapja](../../fin-ops-core/dev-itpro/mobile-apps/Mobile-app-home-page.md).
