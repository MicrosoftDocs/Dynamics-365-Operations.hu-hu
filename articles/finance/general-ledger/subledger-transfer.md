---
title: Részfőkönyv átvitele a főkönyvbe
description: Ez a témakör azt mutatja be, hogy a milyen funkciók kapcsolódnak a részfőkönyv főkönyvbe történő átmozgatási folyamatához kapcsolódóan.
author: rcarlson
ms.date: 07/20/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalSetup, LedgerJournalTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2020-01-18
ms.dyn365.ops.version: AX 10.0.8
ms.openlocfilehash: 03c04a5eb8b544b582019ddd204382900b162d952842c901f69ed4a853bd8183
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6716645"
---
# <a name="subledger-transfer-to-the-general-ledger"></a>Részfőkönyv átvitele a főkönyvbe

[!include [banner](../includes/banner.md)]

Ez a témakör azokat a képességeket mutatja be, amelyek a főkönyvi naplóbejegyzések kötegek átviteléhez szükséges szabályokhoz kapcsolódnak.

A 8.1 verzióban a módosítások lehetővé teszik azon szabályok átmozgatását, amelyek felváltották a **Szinkron** opciót. További információért lásd: [Eltávolított vagy elavult funkciók a Finance and Operations esetében](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md?toc=%2fdynamics365%2ffinance%2ftoc.json#finance-and-operations-81-with-platform-update-20).

A következő lehetőségek érhetők el a részfőkönyvi kötegek átviteléhez:

- **Aszinkron** – Azonnal ütemezni fogja a részfőkönyvi könyvelési tételek átvitelét a főkönyvbe. A program rögzíti a főkönyvi bizonylatot, mihelyt az erőforrások elérhetők a kérelem feldolgozásához a kiszolgálón.
- **Ütemezett köteg** – A részfőkönyv könyvelési bejegyzései, amelyek átvitele szükséges hozzá lesznek adva a főkönyv feldolgozási várólistához. A várólistán lévő rekordok feldolgozása érkezési sorrendben történik. Az egyes főkönyvi bizonylatok frissítik a számlákat ütemezett időben, amikor az erőforrások elérhetők kötegelt feladat feldolgozásához a kiszolgálón.

A 10.0.8-as verzióban az **Aszinkron** beállítás teljesítményének javítását végezték. Ez a funkció engedélyezve van a **Részfőkönyv átvitele a főkönyv teljesítményoptimalizálása érdekében** szolgáltatásnévvel.

Az analitikusnapló kötegek aszinkron átvitelére vonatkozó funkcióval javítható az analitikus naplóból a főkönyvbe történő adatátvitel. A kisebb tranzakciók csoportosítása és a tranzakciók csoportokban való átvitele segítségével a funkció hatékonyabban dolgozza fel a tranzakciókat. A tranzakciók csoportosítása esetén a kötegkiszolgáló erőforrásainak használata hatékonyabb lehet.

Az analitikaiszámla-kötegek aszinkron átvitelhez szükséges, hogy a kötegszerver be legyen állítva, legyen online és működjön. Ellenkező esetben az **Aszinkron** átviteli beállítás nem működik.

A köteg szintjén végzett hatékonysági változás egy ismétlődő kötegelt feladatot használ a rendszerben található összes jogi személyhez. Futásidőben egy új kötegelt feladat jön létre a még nem átvitt szükséges rekordok feldolgozásához. A több beállítást a rendszerfelügyelet **Folyamatautomatizálás** lapján lehet szabályozni. Ezen a lapon módosíthatja a háttérfolyamatot, módosíthatja a gyakoriságot, és meghatározhat egy szüneteltetési időszakot.

A folyamatautomatizálás beállításával kapcsolatos további tudnivalókat lásd: [Folyamatautomatizálás](../../fin-ops-core/dev-itpro/sysadmin/process-automation.md).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
