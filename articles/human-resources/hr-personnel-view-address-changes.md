---
title: A cím változásainak megtekintése és kezelése
description: Ez a témakör azt mutatja be, hogyan lehet megtekinteni és kezelni a cím változásait a Dynamics 365 Human Resources rendszerben.
author: andreabichsel
manager: tfehr
ms.date: 08/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 269074
ms.assetid: 426c6127-42ee-4163-8dd0-b2867f95581d
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-08-07
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 27324b7705fe37ab00e169e8ea05c7768f32b120
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/17/2021
ms.locfileid: "5467337"
---
# <a name="view-and-manage-address-changes"></a>A cím változásainak megtekintése és kezelése

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Ez a témakör bemutatja, hogyan lehet megtekinteni és kezelni a cím változásait az Alkalmazotti önkiszolgáló rendszer **Személyi részletek szerkesztése** oldalán, illetve a **Dolgozó** részleteit tartalmazó oldalon a Dynamics 365 Human Resources rendszerben.

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

1. Válassza ki az **Alkalmazotti önkiszolgáló rendszer** csempét a kezdőlapon.

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

3. Válassza ki a dolgozót, majd kattintson az **Címek** gombra.

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

A HR munkatársai a **Személyzetkezelés** munkaterületen megtekinthetik és nyomon követik a címeket. A cím változásainak megtekintéséhez nyissa meg a **Személyzetkezelés** csempét a **Kezdőlapon**. A cím változása a jobb felső sarokban lévő csempén látható. A **Címváltozások** rész fölött látható, hogy hányszor módosult a cím az **Emberi erőforrások paraméterei** oldalon megadott számú nap alatt. 

Amikor kiválasztja a **Címváltozások** csempét, egy új lapon megjelennek az esetleges címváltozások részletei. Lehetősége van arra, hogy a jobb felső sarokban lévő **Jövőbeli címváltozásokkal** kiválasztásával megjelenítse a jövőbeli dátumú címváltozásokat.

> [!NOTE]
> Ha figyelmeztetést vagy e-mailt szeretne kapni ezekről a címváltozásokról, akkor létrehozhat egy új riasztási szabályt a Művelet panel **Beállítások** lapján. További információ a riasztási szabályokról: [Figyelmeztetési szabályok létrehozása](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/create-alerts).<br><br>

> Ha munkafolyamatot kíván konfigurálni a címváltozásokhoz, akkor a riasztási szabály **Külső küldés** beállításának kiválasztása után használhatja a Power Automate szolgáltatást az üzleti esemény aktiválásra és a munkafolyamat konfigurálására. További tájékoztatás: [Figyelmeztetések üzleti eseményekként](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/create-alerts#alerts-as-business-events).


[!INCLUDE[footer-include](../includes/footer-banner.md)]