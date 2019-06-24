---
title: Vevői munkafolyamat
description: Ez a témakör a vevői munkafolyamattal kapcsolatban tartalmaz információkat. A munkafolyamat segítségével módosíthat a vevőre vonatkozó specifikus mezőket, és jóváhagyásra küldheti ezeket a módosításokat, mielőtt hozzáadásra kerülnének a vevőhöz.
author: mikefalkner
manager: aolson
ms.date: 08/24/2018
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Customer
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mikefalkner
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: 1b0e1621b256e6bbb42f97134b87dd65fa146193
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1554874"
---
# <a name="customer-workflow"></a>Vevői munkafolyamat

[!include [banner](../includes/banner.md)]

A vevői munkafolyamatot hozzáadtuk a Microsoft Dynamics 365 for Finance and Operations 8.0.4 verzióhoz. A munkafolyamat segítségével módosíthatja a vevőre vonatkozó specifikus mezőket, és jóváhagyásra küldheti ezeket a módosításokat, mielőtt hozzáadásra kerülnének a vevőhöz.

## <a name="set-up-the-customer-workflow"></a>Vevői munkafolyamat beállítása

A vevői munkafolyamat funkció használata előtt engedélyeznie kell azt.

1. Lépjen a **Kinnlevőségek \> Beállítások \> Kinnlevőségek paraméterei** pontra.
2. A funkció engedélyezéséhez állítsa az **Általános** lapon belül a **Vevői jóváhagyás** gyorslapon a **Vevői jóváhagyások engedélyezése** beállítást **Igen** értékre.
3. Az **Adatentitás viselkedése** mezőben válassza azt a viselkedést, amelyet az adatentitás az adatok importálásakor alkalmazzon:

    - **Módosítások engedélyezése jóváhagyás nélkül** – Egy entitás módosíthatja a vevői rekordot anélkül, hogy a munkafolyamaton keresztül kellene vinnie.
    - **Módosítások elutasítása** – A vevő rekordot nem lehet módosítani. Az importálás sikertelen lesz a munkafolyamat számára engedélyezett mezőkre vonatkozóan.
    - **Módosítási javaslatok létrehozása** – Minden mező módosítható, kivéve azok, amelyek a munkafolyamat számára engedélyezve vannak. Az ilyen mezőkbe bevitt értékek javasolt módosításként kerülnek hozzáadásra a vevőhöz, a munkafolyamat pedig automatikus elindul.

4. A vevői mezők listájában jelölje be az **Engedélyezés** jelölőnégyzetet minden olyan mező esetében, amelyeket jóvá kell hagyni, mielőtt véglegesíteni lehet a módosításokat.
5. Lépjen a **Kinnlevőségek \> Beállítások \> Kinnlevőségek munkafolyamatai** pontra.
6. Válassza az **Új** lehetőséget.
7. Válassza a **Javasolt vevői módosítások munkafolyamata** elemet. 
8. Állítsa be a munkafolyamatot úgy, hogy megfeleljen a jóváhagyási folyamatnak. A **Munkafolyamat-jóváhagyás javasolt vevői módosítások esetén** munkafolyamat jóváhagyási eleme alkalmazza a módosításokat a vevőre vonatkozóan.

## <a name="change-customer-information-and-submit-the-changes-to-the-workflow"></a>Vevőadatok módosítása és a módosítások elküldése a munkafolyamatba

Ha egy olyan mezőt változtat, amely engedélyezve van a munkafolyamat számára, a **Javasolt módosítások** oldal jelenik meg. Ez az oldal megmutatja a mező eredeti értékét és az újonnan megadott értéket. A megváltoztatott mező értéke visszaáll az eredeti értékre. Az oldalon egy állapotüzenet tájékoztatja arról, hogy a módosításokat még nem küldte el.

Minden alkalommal, amikor olyan mezőt módosít, amely a munkafolyamat számára engedélyezve van, a mező hozzáadásra kerül a javasolt módosítások listájához. Egy mező javasolt értékének elvetése érdekében használja a listában a mező mellett található **Elvetés** gombot. Az összes módosítás elvetése érdekében válassza az oldal alján található **Összes elvetése** gombot. Az oldal bezárásához kattintson az **Ok** lehetőségre.

Amennyiben legalább egy javasolt módosítással rendelkezik, két további menü jelenik meg a Műveletpanelen: a **Javasolt módosítások** és a **Munkafolyamat**.

1. A **Javasolt módosítások** oldal megnyitásához válassza a **Javasolt módosítások** menüt, és tekintse át a módosításokat.
2. A módosítások munkafolyamatba történő elküldéséhez válassza a **Munkafolyamat \> Elküldés** lehetőséget.

    Az oldalon látható állapot a következőre változik: **Jóváhagyásra váró módosítások**.

A munkafolyamat a Finance and Operations szolgáltatás szokásos munkafolyamatát követi. A jóváhagyót a rendszer a **Vevő** oldalra irányítja, ahol áttekintheti a **Javasolt módosítások** oldalon található módosításokat, majd a munkafolyamat jóváhagyásához kiválaszthatja a **Munkafolyamat \> Jóváhagyás** lehetőséget. Miután minden jóváhagyás befejeződött, a mezők a javasolt értékekre frissülnek.
