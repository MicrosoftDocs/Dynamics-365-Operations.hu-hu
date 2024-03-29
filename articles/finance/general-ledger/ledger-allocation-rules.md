---
title: Főkönyvi felosztási szabályok
description: Ez a cikk a főkönyvi felosztási szabályokkal kapcsolatos információkat tartalmaz. Leírja az ezen felosztási szabályok különböző összetevőit, és a hozzájuk használható felosztási módszereket.
author: kweekley
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerAllocation, LedgerAllocationBasisRule, LedgerAllocationRequest, LedgerAllocationRule
audience: Application User
ms.reviewer: kfend
ms.custom: 15402
ms.assetid: 8147e148-7c11-45ef-95c6-f9889a875b54
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0691c65e6a499f713952070811cefaa7a213af7b
ms.sourcegitcommit: c364f50ea0ad50bac5c30724b6ce301d9574b653
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/18/2022
ms.locfileid: "9787553"
---
# <a name="ledger-allocation-rules"></a>Főkönyvi felosztási szabályok

[!include [banner](../includes/banner.md)]

Ez a cikk a főkönyvi felosztási szabályokkal kapcsolatos információkat tartalmaz. Leírja az ezen felosztási szabályok különböző összetevőit, és a hozzájuk használható felosztási módszereket.

Főkönyvi felosztási szabályok segítségével automatikusan kiszámítsa és a felosztási naplók és főkönyvi egyenlegek vagy rögzített összegek felosztásának számlabejegyzések létrehozása. Felosztási módszert is lehet, változó vagy állandó. A felosztás a tranzakció pénznemértékán alapul. Az idegen pénznemben történő nyereség/veszteség könyvelési tételek feladása például a könyvelési és jelentési pénznemösszegek korrigálásához történik. Ezek a bejegyzések nem vonatkoznak a felosztási szabályokra, mivel a tranzakció pénznemének értéke 0,00. Az alábbi felosztási módok Főkönyvi felosztási szabályok használható:

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






[!INCLUDE[footer-include](../../includes/footer-banner.md)]
