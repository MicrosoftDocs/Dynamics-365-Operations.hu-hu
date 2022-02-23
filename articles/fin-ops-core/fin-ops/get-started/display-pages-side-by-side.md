---
title: Oldalak párhuzamos megjelenítése a Megnyitás új ablakban funkció használatával
description: Ez a cikk azt ismerteti, hogy miként jeleníthetők meg az oldalak egymás mellett.
author: aneesmsft
manager: AnnBe
ms.date: 11/20/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.custom: 17611
ms.assetid: fc589d76-3927-4486-ab83-e86b9b47ba2c
ms.search.region: Global
ms.author: aneesa
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 35ade352edf31fe895a9b9118a8ad7d5fe6c0bde
ms.sourcegitcommit: b112925c389a460a98c3401cc2c67df7091b066f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/19/2020
ms.locfileid: "4798403"
---
# <a name="show-pages-side-by-side-using-the-open-in-new-window-feature"></a>Oldalak párhuzamos megjelenítése a Megnyitás új ablakban funkció használatával

[!include [banner](../includes/banner.md)]

Ez a cikk azt ismerteti, hogy miként jeleníthetők meg az oldalak egymás mellett.

Előfordulhat, hogy több oldalt akar párhuzamosan megjeleníteni, a feladat gyors végrehajtásához. Például szeretne érvényesíteni vagy hozzáadni sorokat egyszerre több naplóhoz. Általában a sorok megadásához vagy ellenőrzéséhez egyszerre több naplóban folyamatosan váltani kell a lap, ami megjeleníti a naplókat, valamint egy másik lap között, ami megjeleníti a sorokat az adott naplóhoz. Azonban a **Megnyitás új ablakban** funkció lehetővé teszi, hogy ezen lapokat párhuzamosan jelenítse meg, ezzel gyorsítva az elvégzendő feladatot.

A fenti példánál maradva, a sorok megtekintése közben rákattinthat a **Megnyitás új ablakban** ikonra.

[![Kattintson a Megnyitás új ablakban ikonra.](./media/open-in-new-window-icon.png)](./media/open-in-new-window-icon.png)

A **Megnyitás új ablakban** ikonra kattintva a sorokat tartalmazó lap egy új, felugró böngészőben nyílik meg, majd az eredeti böngészőt visszairányítja az előzményekben arra a lapra, ami a naplók listáját tartalmazza. Ezután a két oldalt párhuzamosan jelenítheti meg. Egy napló megtekintése után megváltoztathatja a kiválasztott naplót a naplókat listázó oldalon. Ezután a sorokat megjelenítő felugró ablak automatikusan az újonnan kiválasztott napló sorait jeleníti majd meg.

[![A két oldalt párhuzamosan jelenítheti meg.](./media/pages-show-side-by-side.png)](./media/pages-show-side-by-side.png)

A dinamikus csatolás és frissítés az oldal biztonságáért felelős adatok közötti kapcsolat miatt történik. Ha a rendszer nem ismeri az adatok közötti kapcsolatot, az előugró ablak nem fog automatikusan frissülni az eredeti ablakban történt változás után.

Néhány lapnak több nézete is van, mint például a Rács nézet, a Fejléc nézet, vagy a Részletek nézet. A **Megnyitás új ablakban** ikon hatására az egész lap egy új böngészőben nyílik meg. Emiatt nem lehet párhuzamosan megjeleníteni ugyan annak a lapnak két különböző nézetét a **Megnyitás új ablakban** szolgáltatás segítségével. A legtöbb ilyen oldal rendelkezik egy navigációs listával, aminek a segítségével válthat a rekordok között, egy hasonló eredményt elérve.

A **Megnyitás új ablakban** funkció használata előtt a böngészőjében engedélyeznie kell a felugró ablakokat az oldalon. Például engedélyezheti a felugró ablakokat a „\*.dynamics.com” helyről.

A **Megnyitás új ablakban** funkció csak akkor elérhető, ha több, mint egy oldal van megnyitva az ablakban. A felugró ablakok is automatikusan bezárulnak, ha nincs több megnyitható lap (ha az ablak utolsó lapját is bezárta). A rendszer bezárja a megnyitott lapokat is, ha Ön az alkalmazás egy másik részére navigál. Ezért ha van egy megnyitott felugró ablak, és Ön az alkalmazáson belül egy másik területre navigál, a felugró ablak automatikusan bezárul, mert az ablakon belüli lapokat a rendszer automatikusan bezárta.

Az előugró ablak felső sora arról a vállalatról tartalmaz információt, amiben a lap meg lett nyitva, és csak olvasható. A felugró ablakok támaszkodnak még a fő böngészőablakra. Ha a fő ablak bezárásra kerül, vagy frissítve lesz, az összes felugró ablak csak olvasható állapotba kerül. Ha ez történik, ezután is megtekintheti az információkat ezekben az ablakokban, de nem lesz képes módosítani azokat.
