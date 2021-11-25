---
title: A cím változásainak megtekintése és kezelése
description: Ez a témakör azt mutatja be, hogyan lehet megtekinteni és kezelni a cím változásait a Dynamics 365 Human Resources rendszerben.
author: twheeloc
ms.date: 10/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 269074
ms.assetid: 426c6127-42ee-4163-8dd0-b2867f95581d
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-08-07
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: ed7ddb192b338f6373e8b53be710c961d918921f
ms.sourcegitcommit: e91a1797192fd9bc4048b445bb5c1ad5d333d87d
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/01/2021
ms.locfileid: "7728833"
---
# <a name="view-and-manage-address-changes"></a>A cím változásainak megtekintése és kezelése

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Ez a témakör bemutatja, hogy hogyan lehet megtekinteni és kezelni a címváltozásokat a Személyes adatok szerkesztése lapon (amelyet az Alkalmazott önkiszolgáló munkaterületén nyit meg) vagy a Dolgozó részletei **·** **·** **·** lapról Dynamics 365 Human Resources.

Számos szervezet azt szeretné, hogy az alkalmazottak saját maguk, saját felületen kezelhessék saját személyes adataikat. Engedélyezheti a felhasználóknak, hogy frissítsék a címüket az **Alkalmazotti önkiszolgáló rendszer** munkaterületén. Ezt követően a változásokat a **Személyzetkezelés** munkaterületen követheti nyomon. A funkció használatához meg kell adnia, hogy hány napig kívánja megtekinteni a változásokat az **Emberierőforrás-paraméterek** oldalon.

## <a name="configure-address-change-parameters"></a>A cím módosítására vonatkozó paraméterek konfigurálása

A következő lépésekkel konfigurálhatja, hogy hány napig legyenek láthatók a cím módosításai a **Személyzetkezelés** munkaterületen:

1. A navigációs panelen válassza ki a **Személyzetkezelés** lehetőséget.
2. Válassza a **Hivatkozások** lehetőséget.
3. Válassza az **Emberi erőforrások paramétereinek konfigurálása** lehetőséget.
4. A **Napok száma** mezőben, a **Címváltozás** területen, adja meg, hogy hány napig legyenek láthatók a címváltozások a **Személyzetkezelés** munkaterületen.
5. Zárja be a lapot.

## <a name="create-or-change-an-employee-address"></a>Alkalmazott címének létrehozása vagy módosítása

Az alkalmazottak frissíthetik a saját címüket az **Alkalmazotti önkiszolgáló rendszer** munkaterületén. Cím létrehozásához vagy módosításához kövesse az alábbi lépéseket:

1. Válassza az **Alkalmazott – önkiszolgáló** szolgáltatás csempe lehetőséget a **·** Kezdőlapon.
2. Válassza a **Személyes adatok szerkesztése** elemet.
3. Cím hozzáadásához kattintson a **Hozzáadás** gombra. Meglévő cím frissítéséhez jelölje ki a címet a listában, majd válassza a **Szerkesztés** lehetőséget.
4. Adja meg a **nevet vagy a leírást**.
5. Válassza ki a **Cél** legördülő mezőt, majd válassza ki a cím típusát.
6. Írja be az **Ország/régió** nevét.
7. Írja be az **Irányítószám** értékét.
8. Adja meg az **Utcát**.
9. Írja be a **Várost**, az **Államot** és a **Megyét**. Ezeket a mezőket a rendszer általában automatikusan beállítja az **Irányítószám** mező alapján.
10. Lehetőség van az **Elsődleges** mező kiválasztására, amely elsődleges címet jelez. Csak egy címet lehet elsődlegesként megjelölni. Ha egy másik cím már meg van jelölve elsődleges címként, meg kell erősítenie, hogy a megadott címet szeretné elsődlegesként használni.
11. Lehetőség van a **Privát** mező kiválasztására, amely privát címet jelez. Csak azok a felhasználók tekinthetik meg ezt a címet, akiknél kifejezetten engedélyezve van a privát címek megtekintése.
12. Válassza ki az **OK** lehetőséget.

## <a name="create-or-change-a-worker-address"></a>Dolgozó címének létrehozása vagy módosítása

A cím a **Személyzetkezelés** munkaterületen frissíthető. Cím létrehozásához vagy módosításához kövesse az alábbi lépéseket:

1. A **Személyzetkezelés** munkaterületen válassza a **Hivatkozások**, majd a **Dolgozók** elemet.
2. Válassza ki a dolgozót, majd kattintson az **Címek** gombra.
3. Cím hozzáadásához kattintson a **Hozzáadás** gombra. Meglévő cím frissítéséhez jelölje ki a címet a listában, majd válassza a **Szerkesztés** lehetőséget.
4. Adja meg a **nevet vagy a leírást**.
5. Válassza ki a **Cél** legördülő mezőt, majd válassza ki a cím típusát.
6. Írja be az **Ország/régió** nevét.
7. Írja be az **Irányítószám** értékét.
8. Adja meg az **Utcát**.
9. Írja be a **Várost**, az **Államot** és a **Megyét**. Ezeket a mezőket a rendszer általában automatikusan beállítja az **Irányítószám** mező alapján.
10. Lehetőség van az **Elsődleges** mező kiválasztására, amely elsődleges címet jelez. Csak egy címet lehet elsődlegesként megjelölni. Ha egy másik cím már meg van jelölve elsődleges címként, meg kell erősítenie, hogy a megadott címet szeretné elsődlegesként használni.
11. Lehetőség van a **Privát** mező kiválasztására, amely privát címet jelez. Csak azok a felhasználók tekinthetik meg ezt a címet, akiknél kifejezetten engedélyezve van a privát címek megtekintése.
12. Válassza ki az **OK** lehetőséget.
 
## <a name="create-a-future-change-for-an-address"></a>Cím jövőbeli módosításának megadása

Bizonyos esetekben előfordulhat, hogy valamikor a jövőben szeretné módosítani a címet. Ez például akkor lehet hasznos, ha egy alkalmazott a következő hónap 15-én költözik.

1. Nyissa meg a **Címek kezelése** oldalt az egyik címrács **További beállítások > Speciális** elemére kattintva.
2. Válassza ki az **Új** lehetőséget egy új cím létrehozásához.
3. Adja meg a cím részleteit.
4. Lépjen az **Általános** gyorslapra.
5. Az **Érvényesség dátuma** mezőben válassza ki azt a dátumot, amikor az új cím érvénybe lép.
6. A **Lejárat dátuma** mezőben kiválaszthatja, hogy a cím mikortól nem lesz érvényes.
7. Zárja be a lapokat.

## <a name="view-and-monitor-address-changes"></a>A cím változásainak megtekintése és nyomon követése

A HR munkatársai a **Személyzetkezelés** munkaterületen megtekinthetik és nyomon követik a címeket. A címváltozások megtekintéséhez jelölje be a **Személyzetkezelés** csempe a **·** Kezdőlapon. A címváltozások a jobb felső sarkában lévő csempeen jelennek meg. A címváltozások feletti szám azt jelzi, hogy hány címváltozás történt az Emberi erőforrások paraméterei lapon megadott napok **·** száma **·** alatt. 

Amikor kiválasztja a **Címváltozások** csempét, egy új lapon megjelennek az esetleges címváltozások részletei. Lehetősége van arra, hogy a jobb felső sarokban lévő **Jövőbeli címváltozásokkal** kiválasztásával megjelenítse a jövőbeli dátumú címváltozásokat.

> [!NOTE]
> Ha figyelmeztetést vagy e-mailt szeretne kapni ezekről a címváltozásokról, akkor létrehozhat egy új riasztási szabályt a Művelet panel **Beállítások** lapján. További információ a riasztási szabályokról: [Figyelmeztetési szabályok létrehozása](../fin-ops-core/fin-ops/get-started/create-alerts.md).
>
> Ha munkafolyamatot kíván konfigurálni a címváltozásokhoz, akkor a riasztási szabály **Külső küldés** beállításának kiválasztása után használhatja a Power Automate szolgáltatást az üzleti esemény aktiválásra és a munkafolyamat konfigurálására. További tájékoztatás: [Figyelmeztetések üzleti eseményekként](../fin-ops-core/fin-ops/get-started/create-alerts.md#alerts-as-business-events).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
