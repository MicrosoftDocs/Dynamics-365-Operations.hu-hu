---
title: Feladatkezelés konfigurálása
description: Ez a témakör azt mutatja be, hogyan kell konfigurálni a feladatkezelési szolgáltatást a Microsoft Dynamics 365 Commerce alkalmazásban.
author: gvrmohanreddy
manager: annbe
ms.date: 02/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: gmohanv
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: e880305d02fd9f10464fe3f65a2774a44da258c6
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "5006235"
---
# <a name="configure-task-management"></a>Feladatkezelés konfigurálása

[!include [banner](includes/banner.md)]

Ez a témakör azt mutatja be, hogyan kell konfigurálni a feladatkezelési szolgáltatást a Microsoft Dynamics 365 Commerce alkalmazásban.

## <a name="overview"></a>Áttekintés

Mielőtt a Dynamics 365 Commerce alkalmazásban vezetők és az alkalmazottak használhatják a Commerce feladatkezelési funkcióit, konfigurálni kell a feladatkezelést. A konfigurálás lépései között szerepelnek a vezetők és az alkalmazottak engedélyei, az engedélyek elosztása a pénztári (POS) kliensekhez, a pénztári értesítések beállítása, valamint a **Feladatok** csempéjének konfigurálása egy pénztári alkalmazás kezdőlapján.

## <a name="configure-permissions-for-store-managers"></a>Engedélyek konfigurálása az üzletvezetők számára

Minden dolgozó egy adott üzletben megtekintheti az üzlethez rendelt összes feladatot. A hozzájuk társított feladatok állapotát is frissíteni tudják. Azonban a szereplők, mint például az üzletvezetők számára feladatkezelési jogosultság szükséges az üzlethez rendelt feladatok kezeléséhez és az egyfunkciós feladatok létrehozásához.

A következő lépésekkel konfigurálhatja az üzletvezetők feladatkezelési engedélyeit.

1. Nyissa meg a következőt: **Retail és Commerce \> Alkalmazottak \> Engedélycsoportok**.
1. Jelöljön ki egy adott jogosultsági csoportot (például **Vezető**), majd válassza a **Szerkesztés** parancsot.
1. Az **Engedélyek** gyorslapon állítsa be a **Feladatkezelés engedélyezése** beállítást **Igen** értékre.
1. Az **Értesítések** gyorslapon adja hozzá a **Feladatkezelés** műveletet, és adjon meg egy értéket a **Megjelenítési sorrend** mezőben. Írja be például a **2** értéket, ha a **Rendelés teljesítése** művelethez már tartozik **Megjelenítési sorrend** érték – az **1**.
    
> [!NOTE]
> Ha egy nem vezető személynek a pénztárban rendelkeznie kell feladatkezelési engedélyekkel akkor engedélyt adhat ennek a személynek. Azt is megteheti, hogy létrehoz egy új jogosultsági csoportot a nem vezetőknek, és beállítja a **Feladatkezelés engedélyezése** beállítást **Igen** értékre.

A következő ábra megmutatja, hogyan konfigurálhatja az üzletvezetők feladatkezelési engedélyeit.

![Az üzletvezetők feladatkezelési engedélyeinek konfigurálása](media/HQ-POS-Tasks-Notifications-User-Permission.png)

## <a name="configure-permissions-for-employees"></a>Alkalmazottak engedélyeinek konfigurálása

Az alkalmazottaknak rendelkezniük kell a feladatlisták létrehozásához szükséges engedélyekkel, a hozzárendelési feltételek kezelésével és bármely feladatlista ismétlődésének beállításával kapcsolatos engedélyekkel. Az engedélyek konfigurálásához az alkalmazottakat a **Retail feladatkezelő** szerepkörhöz kell rendelni.

Egy munkavállaló engedélyeinek konfigurálásához kövesse az alábbi lépéseket.

1. Nyissa meg a következőt: **Retail és Commerce \> Alkalmazottak \> Felhasználók**.
1. Válasszon egy alkalmazottat.
1. A **Felhasználó szerepkörei** gyorslapon válassza a **Szerepkörök hozzárendelése** elemet.
1. A **Szerepkörök társítása a felhasználóhoz** párbeszédpanelen válassza ki a **Retail feladatkezelő** szerepkört, majd kattintsonaz **OK** gombra.

## <a name="distribute-permissions-to-pos-clients"></a>Jogosultságok elosztása a POS-ügyfeleknek

Mielőtt az alkalmazottak felhasználhatnák a POS-ügyfeleket, az engedélyeket meg kell osztani és szinkronizálni kell ezekhez az ügyfelekhez.

Az engedélyek terjesztéséhez a POS-ügyfelekhez hajtsa végre az alábbi lépéseket.

1. Ugorjon a **Kiskereskedelem és kereskedelem \> Kiskereskedelem és kereskedelem informatika \> Elosztási ütemezés** pontra.
1. Válassza ki az **1060** (**Személyzet**) elosztási ütemezést, majd válassza a **Futtatás most** parancsot.
1. Válassza ki az **1070** (**Csatorna konfigurációja**) elosztási ütemezést, majd válassza a **Futtatás most** parancsot.

## <a name="configure-pos-notifications-for-tasks"></a>POS-értesítések konfigurálása a feladatokhoz

A Feladatkezelést úgy kell konfigurálni, hogy a POS-alkalmazásban az értesítések elérhetők legyenek.

A POS-értesítések konfigurálásához a feladatokhoz kövesse az alábbi lépéseket.

1. Lépjen a **Retail és Commerce \> Csatornabeállítás \> Pénztárbeállítás \> Pénztár \> Pénztárműveletek** lehetőségre.
1. Keresse meg az **1400** műveletet (**Feladatkezelés**), és jelölje be az **Értesítések engedélyezése** jelölőnégyzetet.

A következő ábra a **Feladatkezelő** műveletet jeleníti meg a **Pénztári műveletek** lapon.

![Feladatkezelő működése a POS-műveletek lapon](media/HQ-POS-Tasks-Notifications.png)

A POS-értesítések konfigurálásával kapcsolatos további tudnivalókat lásd: [Rendelési értesítések megjelenítése a pénztárnál (POS)](notifications-pos.md).

## <a name="configure-the-tasks-tile-on-a-pos-application-home-page"></a>A Feladatok csempe konfigurálása a Pénztáralkalmazás kezdőlapján

Mielőtt egy Pénztáralkalmazás kezdőlapján beállítja a **Feladatok** csempéjét:, lásd: [Képernyő-elrendezések a pénztár (POS) számára](pos-screen-layouts.md), ahol megtudhatja, hogy hogyan lehet beállítani és új gombokat hozzáadni a pénztár képernyő elrendezéséhez.

A **Feladatok** csempe konfigurálásához a Pénztáralkalmazás kezdőlapján kövesse az alábbi lépéseket,

1. Lépjen a **Retail és Commerce \> Csatornabeállítás \> Pénztárbeállítás \> Pénztár \> Képernyő-elrendezések** lehetőségre.
1. Válasszon ki egy képernyő-elrendezést, válasszon egy elrendezési méretet, majd válassza ki egy gombrácsot.
1. A **Gombrácsok** gyorslapján a kiválasztott gombrács szerkesztéséhez válassza a **Tervező** elemet.
1. Adjon hozzá egy **Feladatok** csempét a Kezdőlap megfelelő szakaszához.

A következő ábra a pénztár kezdőlapján található **Feladatok** csempére mutat be egy példát.

![A Feladatok mozaikja a pénztár kezdőlapján](media/POS-home-screen-tasks-button-image.png)

## <a name="additional-resources"></a>További erőforrások

[Feladatkezelés – áttekintés](task-mgmt-overview.md)

[Feladatlisták létrehozása és feladatok hozzáadása](task-mgmt-create-lists.md)

[Feladatlisták hozzárendelése áruházakhoz vagy alkalmazottakhoz](task-mgmt-assign-lists.md)

[Feladatkezelés a pénztárban](task-mgmt-POS.md)
