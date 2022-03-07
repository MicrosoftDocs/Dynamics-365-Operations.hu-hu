---
title: Szállítói munkafolyamat
description: Módosítsa a szállító adatait és egy munkafolyamattal hagyja jóvá.
author: mikefalkner
ms.date: 08/24/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: Vendor
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: 8f4fc24153842b2a108b13835e56e70177d7b53842cb15ea17f172da21ddc10d
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6777168"
---
# <a name="vendor-workflow"></a>Szállítói munkafolyamat

[!include [banner](../includes/banner.md)]

A szállító munkafolyamat használata esetén az egyes mezőkön végrehajtott módosítások el lesznek küldve a munkafolyamathoz jóváhagyásra, mielőtt hozzáadásra kerülnek a szállítóhoz.

## <a name="set-up-the-vendor-workflow"></a>Szállítói munkafolyamat beállítása

A munkafolyamat használatához előbb aktiválni kell azt.

1. Ugorjon a **Kötelezettségek \> Beállítás \> Kötelezettségek paraméterei pontra**.
2. Az **Általános** lapon, a **Szállítói jóváhagyás** gyorslapon állítsa a **Feladatrögzítés engedélyezése** beállítást **Igen** értékre.
3. Az **Adatentitás működése** mezőben, válassza ki az adatok importálásakor használandó viselkedést:

    - **Módosítások engedélyezése jóváhagyás nélkül** – Az adatentitás lehet frissítheti a szállítórekordot a munkafolyamat-feldolgozása nélkül.
    - **Módosítások elvetése** – Nem módosíthatók a szállítói rekordok. Az importálás sikertelen lesz azokhoz a mezőkhöz, amelyek engedélyezve vannak ehhez a munkafolyamathoz.
    - **Módosítási javaslatok létrehozása** – Minden mező meg fog változni a munkafolyamathoz engedélyezett mezők kivételével. Ezen a mezők új értékei hozzá lesznek adva a szállítóhoz javasolt módosításokként, és a munkafolyamat automatikusan elindul.

4. A szállítói mezők listájában jelölje be az **Engedélyezése** jelölőnégyzetet minden mezőhöz, amelyet a módosítás előtt jóvá kell hagyni.
5. Ugorjon a **Kötelezettségek \> Beállítás \> Kötelezettségekkel kapcsolatos munkafolyamatok** pontra.
6. **Új** kiválasztása.
7. Válassza a **A javasolt szállítói módosítások munkafolyamata** lehetőséget. 
8. A munkafolyamatot állítsa be úgy, hogy megfeleljen a jóváhagyási folyamatának. A **Javasolt szállítói módosításhoz tartozó munkafolyamat-jóváhagyás** munkafolyamat-jóváhagyási elem alkalmazza a módosításokat szállítóhoz.

## <a name="change-vendor-information-and-submit-the-changes-to-the-workflow"></a>A szállító adatainak módosítása és a módosításokat elküldése a munkafolyamatnak

Ha módosít egy mezőt, amely engedélyezve van, a munkafolyamathoz, a **Javasolt módosítások** lap jelenik meg. Ez az oldal megmutatja a mező eredeti értékét és az újonnan megadott értéket. A mezőt, amely a módosított vissza lett állítva az eredeti értékre. Egy állapotüzenet is mutatja, hogy a módosítások még nem lettek beküldve. 

Minden alkalommal, amikor módosít egy mezőt, amely engedélyezve van a munkafolyamathoz, az a mező hozzáadódik **Javasolt módosítások** oldalon található listához. A mezőhöz a javasolt érték elvetéséhez, használja az **Elvetés** gombot a listában található mező mellett. Az összes változtatás elvetéséhez használja az **Összes változtatás elvetése** gombot az oldal alján. Válassza az **OK** lehetőséget az oldal bezárásához.

Legalább egy javasolt módosítás után, két további lap jelenik meg a műveleti panelen: **Javasolt módosítások** és **Munkafolyamat**.

1. Válassza a **Javasolt módosítások** elemet a **Javasolt módosítások** lap megnyitásához, és ellenőrizze a módosításait.
2. Válassza a **Munkafolyamat \> Beküldés lehetőséget, hogy beküldje a módosításokat a munkafolyamathoz**.

    Az oldalon látható állapot a következőre változik: **Jóváhagyásra váró módosítások**.

A munkafolyamat a normál munkafolyamatot követi. A jóváhagyót a rendszer a **Szállító** oldalra irányítja, ahol áttekintheti a **Javasolt módosítások** oldalon található módosításokat, majd a munkafolyamat jóváhagyásához kiválaszthatja a **Munkafolyamat \> Jóváhagyás** lehetőséget. Miután minden jóváhagyás befejeződött, a mezők a javasolt értékekre frissülnek.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]