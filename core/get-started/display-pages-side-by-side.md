---
title: "Oldalak párhuzamos megjelenítése a Megnyitás új ablakban ikon használatával"
description: "Ez a cikk ismerteti, hogy hogyan jeleníthet meg lapokat egymás mellett a Microsoft Dynamics 365 for Operations rendszerben."
author: aneesmsft
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 17611
ms.assetid: fc589d76-3927-4486-ab83-e86b9b47ba2c
ms.search.region: Global
ms.author: aneesa
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: e29d436560590e844e92180a6d1e2ad53d019662
ms.contentlocale: hu-hu
ms.lasthandoff: 04/25/2017


---

# <a name="display-pages-side-by-side-using-the-open-in-new-window-icon"></a>Oldalak párhuzamos megjelenítése a Megnyitás új ablakban ikon használatával

[!include[banner](../includes/banner.md)]


Ez a cikk ismerteti, hogy hogyan jeleníthet meg lapokat egymás mellett a Microsoft Dynamics 365 for Operations rendszerben.

A Microsoft Dynamics 365 for Operations rendszer segít a feladatok hatékony végrehajtásában. Bizonyos esetekben előfordulhat, hogy több oldalt akar párhuzamosan megjeleníteni, a feladat gyors végrehajtásához. Például szeretne érvényesíteni vagy hozzáadni sorokat egyszerre több naplóhoz. Általában ehhez folyamatosan váltani kell a lap, ami megjeleníti a naplókat, valamint egy másik lap között, ami megjeleníti a sorokat az adott naplóhoz. Azonban a **Megnyitás új ablakban** funkció lehetővé teszi, hogy ezen lapokat párhuzamosan jelenítse meg, ezzel gyorsítva az elvégzendő feladatot. A fenti példánál maradva, a sorok megtekintése közben rákattinthat a **Megnyitás új ablakban** ikonra. [![open-in-new-window-icon](./media/open-in-new-window-icon.png)](./media/open-in-new-window-icon.png) A **Megnyitás új ablakban** ikonra kattintva a sorokat tartalmazó lap egy új, felugró böngészőben nyílik meg, majd az eredeti böngészőt visszairányítja az előzményekben arra a lapra, ami a naplók listáját tartalmazza. Ezután a két oldalt párhuzamosan jelenítheti meg. Ha befejezte egy napló megtekintését, megváltoztathatja a kiválasztott naplót a naplókat listázó oldalon. Ezután a sorokat megjelenítő felugró ablak automatikusan az újonnan kiválasztott napló sorait jeleníti majd meg. [![pages-show-side-by-side](./media/pages-show-side-by-side.png)](./media/pages-show-side-by-side.png) A dinamikus csatolás és frissítés az oldal biztonságáért felelős adatok közötti kapcsolat miatt történik. Ha a rendszer nem ismeri az adatok közötti kapcsolatot, az előugró ablak nem fog automatikusan frissülni az eredeti ablakban történt változás után. Néhány lapnak több nézete is van, mint például a Rács nézet, a Fejléc nézet, vagy a Részletek nézet. A **Megnyitás új ablakban** ikon hatására az egész lap egy új böngészőben nyílik meg. Emiatt nem lehet párhuzamosan megjeleníteni ugyan annak a lapnak két különböző nézetét a **Megnyitás új ablakban** szolgáltatás segítségével. Azonban a legtöbb ilyen oldal rendelkezik egy navigációs listával, aminek a segítségével válthat a rekordok között, egy hasonló eredményt elérve. A **Megnyitás új ablakban** funkció használata előtt a böngészőjében engedélyeznie kell a felugró ablakokat a Dynamics 365 for Operations rendszer weblapján. Például engedélyezheti a felugró ablakokat a „\*.dynamics.com” helyről. A **Megnyitás új ablakban** funkció csak akkor elérhető, ha több, mint egy oldal van megnyitva az ablakban. A felugró ablakok is automatikusan bezárulnak, ha nincs több megnyitható lap (ha az ablak utolsó lapja is bezárásra kerül). A Dynamics 365 for Operations rendszer bezárja a megnyitott lapokat is, ha Ön az alkalmazás egy másik részére navigál. Ezért ha van egy megnyitott felugró ablak, és Ön az alkalmazáson belül egy másik területre navigál, a felugró ablak automatikusan bezárul, mert az ablakon belüli lapokat a rendszer automatikusan bezárta. Az előugró ablak felső sora arról a vállalatról tartalmaz információt, amiben a lap meg lett nyitva, és csak olvasható. A felugró ablak a Dynamics 365 for Operations rendszer fő böngésző ablakára támaszkodik. Ha a fő ablak bezárásra kerül, vagy frissítve lesz, az összes felugró ablak csak olvasható állapotba kerül. Ez azt jelenti, hogy ezután is megtekintheti az információkat ezekben az ablakokban, de nem lesz képes módosítani azokat.




