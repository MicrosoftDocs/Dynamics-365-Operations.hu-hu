---
title: Eszközkezelés mobil munkaterület beállítása
description: Ez a témakör leírja, hogyan lehet beállítani a Microsoftot és a Pénzügy Dynamics 365 Supply Chain Management és műveletek (Dynamics 365) mobilalkalmazást egy eszközkezelési mobileszköz-munkaterület futtatására, amely a dolgozók számára eszközkezelési feladatok elvégzésére használható.
author: johanhoffmann
ms.date: 01/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-12-22
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: ef4e6bf2ae59adb05c7d4aacc3f5675a5adcafc9
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/29/2022
ms.locfileid: "9070053"
---
# <a name="set-up-the-asset-management-mobile-workspace"></a>Eszközkezelés mobil munkaterület beállítása

[!include [banner](../includes/banner.md)]

Ez a Dynamics 365 Supply Chain Management **témakör leírja, hogyan lehet beállítani a Microsoftot és a Pénzügy** és műveletek (Dynamics 365) mobilalkalmazást egy eszközkezelési mobileszköz-munkaterület futtatására, amely a dolgozók számára eszközkezelési feladatok elvégzésére használható.

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

Ahhoz, hogy elérhetővé tegye az eszközkezelési funkciókat a Pénzügy és műveletek (Dynamics 365) mobilalkalmazásban, **közzé kell tennie az Eszközkezelés mobileszköz-munkaterületét**.

1. A Supply Chain Management szolgáltatásban válassza a **Beállítások** gombot (a jobb felső sarkában látható fogaskerekek szimbólumát), majd válassza a menüben a **Mobilalkalmazás** lehetőséget.
1. A **Mobilalkalmazás-kezelés** párbeszédpanelen keresse meg az **Eszközkezelés** csempét. Ha azt a szöveget tartalmazza, hogy "Metaadatok között - nincs közzétéve", akkor a munkaterület még nincs közzétéve. Ha a "Metaadatok között - közzétett" szöveget tartalmazza, a munkaterület már közzé van téve, és a művelet hátralévő részét kihagyhatja.

    ![Mobilalkalmazás párbeszédpanel kezelése.](media/mobile-workspaces.png "Mobilalkalmazás párbeszédpanel kezelése")

1. Válassza az **Eszközkezelés** csempét, majd az eszköztár **Közzététel** gombját. Néhány másodperc múlva értesítést kell kapnia arról, hogy sikeresen megtörtént a munkaterület közzététele. Ezenkívül a csempe szövegének a "Metaadatok között – közzétéve" szövegre kell váltania.

## <a name="install-and-set-up-the-finance-and-operations-dynamics-365-mobile-app"></a>A Pénzügy és műveletek (Dynamics 365) mobilalkalmazás telepítése és beállítása

1. Ha mobileszközére telepítenie **kell a Microsoft Pénzügy és műveletek (Dynamics 365)** alkalmazást, kattintson a következő alkalmazásüzletek egyikére:

    - [Google Android eszközök esetében](https://go.microsoft.com/fwlink/?linkid=850662)
    - [Apple IOS eszközök esetében](https://go.microsoft.com/fwlink/?linkid=850663)

1. A Pénzügy és műveletek (Dynamics 365) alkalmazás megnyitása. A bejelentkezési oldalnak meg kell jelenni. A **Bejelentkezés** mezőben adja meg a saját Supply Chain Management URL-címét, vagy válassza ki a közelmúltbeli URL-címet a **Közelmúltbeli környezetek** listában, majd koppintson a **Csatlakozás** gombra.

    ![Bejelentkezési oldal.](media/mobile-app-sign-in.png "Bejelentkezési oldal")

1. Ha a program kéri a kapcsolat megerősítését, jelölje be a **Megértettem** jelölőnégyzetet, majd koppintson a **Csatlakozás** gombra.
1. A **Fiókválasztó** oldalon Microsoft-fiókjával jelentkezhet be a mobilalkalmazásba.

    Megjelenik a **Munkaterületek** oldal. Felsorolja a saját Supply Chain Management példánya által közzétett összes mobil munkaterületet.

    ![Munkaterületek listája.](media/mobile-app-workspaces.png "Munkaterületek listája")

1. Ha módosítania kell a jogi személyt (vállalatot), kattintson a bal felső sarkában látható Menü gombra (néha hamburgernek vagy a hamburgergombnak is nevezik), majd válassza a **Vállalat módosítása** lehetőséget.

    ![A jogi személy módosítása.](media/mobile-app-change-comp.png "A jogi személy módosítása")

1. Válassza ki a **Munkaterületek** lapon azt a munkaterületet, amelyet használni szeretne a megnyitásához.

    ![Eszközkezelési mobil munkaterület.](media/mobile-app-asset-workspace.png "Eszközkezelési mobil munkaterület")

## <a name="work-with-the-asset-management-mobile-workspace"></a>Eszközkezelés mobil munkaterület használata

Az **Eszközkezelés** mobil munkaterület használatával kapcsolatos további tudnivalókat lásd az [Eszközkezelés mobil munkaterület használata](asset-management-mobile-workspace.md) oldalt.

A Pénzügy és műveletek (Dynamics 365) mobilalkalmazással [kapcsolatos további tudnivalókat lásd a Mobilalkalmazás kezdőlapján](../../fin-ops-core/dev-itpro/mobile-apps/Mobile-app-home-page.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
