---
title: "Főkönyvi felosztási szabályok"
description: "Ez a cikk a főkönyvi felosztási szabályokkal kapcsolatos információkat tartalmaz. Leírja az ezen felosztási szabályok különböző összetevőit, és a hozzájuk használható felosztási módszereket."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerAllocation, LedgerAllocationBasisRule, LedgerAllocationRequest, LedgerAllocationRule
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 15402
ms.assetid: 8147e148-7c11-45ef-95c6-f9889a875b54
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 87b98811dabb6a8593cd4a75ad9c5a028f653867
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="ledger-allocation-rules"></a>Főkönyvi felosztási szabályok

[!include[banner](../includes/banner.md)]


Ez a cikk a főkönyvi felosztási szabályokkal kapcsolatos információkat tartalmaz. Leírja az ezen felosztási szabályok különböző összetevőit, és a hozzájuk használható felosztási módszereket.

Főkönyvi felosztási szabályok segítségével automatikusan kiszámítsa és a felosztási naplók és főkönyvi egyenlegek vagy rögzített összegek felosztásának számlabejegyzések létrehozása. Felosztási módszert is lehet, változó vagy állandó. Az alábbi felosztási módok Főkönyvi felosztási szabályok használható:

-   **Alap** – a változó módszert használják, ha a felosztás attól függ, a tényleges főkönyvi egyenleg, a szűrési feltételek alapján. Például a vállalat hirdetési kiadásait feloszthatja az egyes részlegeknek az összes értékesítéshez képest produkált értékesítésének arányában.
-   **Rögzített százalék** és **Fix súly** – közvetlenül a szabályhoz meghatározott ezeknek a módszereknek a felosztási százalék vagy súlya. Ha például hirdetési költségek lehet felosztani osztály kap a hirdetési kiadások 70 százalékát, és B osztály kap 30 százalékát.
-   **Egyenlő** – Ez a módszer elosztja a összeg egyenlő minden definiált célja. Például célok meg vannak adva a szervezeti egység és B osztály, hirdetési kiadások lehet hozzárendelni úgy, osztály, mind a "B" osztály kapja meg a hirdetési kiadások 50%-át.

Ha egy felosztási szabályhoz az Alap felosztási módszer tartozik, létre kell hoznia egy külön szabályt a főkönyvi felosztás alapjához is. A „Felosztási kérés feldolgozása” lehetővé teszi, hogy a felhasználók folyamat-a Főkönyvi felosztási szabály feldolgozása, és a létrejövő felosztási napló bejegyzéseinek megtekintése, vagy fel, vagy a számított felosztás törlése előtt.

## <a name="components-of-ledger-allocation-rules"></a>Felosztási szabályok összetevői
Minden felosztási szabály négy elsődleges összetevőből áll: általános, forrás, cél, és az ellenszámla. További alkatrészek, a Főkönyvi felosztási szabályok adatbázisok szükség, ha az Alap az elosztási módszert használja. Minden egyes összetevő egy kritikus fontosságú eleme szeretné feldolgozni a felosztásokat szükséges információt tartalmaz.

-   **Általános** – Az általános összetevő a felhasználó által megadott beállításokat jelenti, többek között a felosztási módszert, a vállalatközi szabálybeállításokat, illetve a szabály aktív vagy nem aktív állapotát.
-   **Forrás** – ezt az összetevőt, akkor a felhasználó megadhatja a felosztás forrásadatait. A felosztás alapulhat főkönyvi egyenlegeken (**Adatforrás** = **Főkönyv**) vagy rögzített összegeken (**Adatforrás** = **Rögzített érték**). Ha **Adatforrás** értéke **Főkönyvi**, forrás szűrési feltételeket meg kell adni a Főkönyvi felosztási szabály (például a hirdetési költségek).
-   **Cél** – A cél határozza meg, hogy a felosztási számítás eredményét hogyan kell elosztani a cél felosztási sorai között. Például lehet az egyes részlegekhez tartozó cél soronként.
-   **Ellenoldal** – ezt az összetevőt határozza meg, hogyan fő számlák és dimenziók érdekében meg kell határozni az ellenoldali bejegyzéseket, amelyek kiegyenlítik a cél bejegyzései. Ezek a bejegyzések általában a forrás oldalán megadott számlák/dimenziók helyében állnak. Ha **Adatforrás** értéke **Rögzített érték**, a **Forrás** lehetőség nem használható.
-   **Főkönyvi felosztási alap szabályok** – ezek szabályok saját forrás szűrési feltételek meghatározása, hogy mely főkönyvi egyenlegek használandó felosztási (például a bevétel szerinti beosztásokról) használja. Egy felosztási alapszabály több felosztási szabállyal együtt is használható.





