---
title: Részfőkönyv átvitele a főkönyvbe
description: Ez a témakör a főkönyv a számba vevő átviteli folyamatához kapcsolódó funkciókat ismerteti.
author: RyanCCarlson2
ms.date: 12/08/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalSetup, LedgerJournalTable
audience: Application User
ms.reviewer: kfend
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: rcarlson
ms.search.validFrom: 2020-01-18
ms.dyn365.ops.version: AX 10.0.8
ms.openlocfilehash: 6d9b40409089e2050dc28c21040069107b766aa0
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8871246"
---
# <a name="subledger-transfer-to-the-general-ledger"></a>Részfőkönyv átvitele a főkönyvbe

[!include [banner](../includes/banner.md)]

Ez a témakör az adagotra vonatkozó naplóbejegyzések kötegeinek átvitelére vonatkozó szabályokkal kapcsolatos funkciókat ismerteti.

A 8.1 verzióban a módosítások lehetővé teszik azon szabályok átmozgatását, amelyek felváltották a **Szinkron** opciót. A további tudnivalókat [lásd a Pénzügyi és műveletek eltávolítva vagy elavult funkcióinál](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md?toc=%2fdynamics365%2ffinance%2ftoc.json#finance-and-operations-81-with-platform-update-20).

A következő lehetőségek érhetők el a részfőkönyvi kötegek átviteléhez:

- **Aszinkron** – Azonnal ütemezni fogja a részfőkönyvi könyvelési tételek átvitelét a főkönyvbe. A program rögzíti a főkönyvi bizonylatot, mihelyt az erőforrások elérhetők a kérelem feldolgozásához a kiszolgálón.
- **Ütemezett köteg** – A részfőkönyv könyvelési bejegyzései, amelyek átvitele szükséges hozzá lesznek adva a főkönyv feldolgozási várólistához. A várólistán lévő rekordok feldolgozása érkezési sorrendben történik. Az egyes főkönyvi bizonylatok frissítik a számlákat ütemezett időben, amikor az erőforrások elérhetők kötegelt feladat feldolgozásához a kiszolgálón.

A 10.0.8-as verzióban az **Aszinkron** beállítás teljesítményének javítását végezték. Ez a funkció engedélyezve van a **Részfőkönyv átvitele a főkönyv teljesítményoptimalizálása érdekében** szolgáltatásnévvel.

Az analitikusnapló kötegek aszinkron átvitelére vonatkozó funkcióval javítható az analitikus naplóból a főkönyvbe történő adatátvitel. A kisebb tranzakciók csoportosítása és a tranzakciók csoportokban való átvitele segítségével a funkció hatékonyabban dolgozza fel a tranzakciókat. A tranzakciók csoportosítása esetén a kötegkiszolgáló erőforrásainak használata hatékonyabb lehet.

Az aszinkron átvitelhez be kell állítani, online módon kell beállítani a kötegkiszolgálót, valamint be kell állítani az online munkát, mivel a kötegelt feladatok a kötegkiszolgálón történő azonnali végrehajtáshoz létrejönnek. Ha engedélyezve van **a** Főkönyv modulba történő adagotra vonatkozó teljesítményoptimalizálási funkció, engedélyezni kell a Folyamatautomatizálás rendszer kötegelt feladatot is, **·** **amely a Folyamatautomatizálás lekérdezési rendszer feladata**. További információért tekintse át a [Folyamat automatizálása](../../fin-ops-core/dev-itpro/sysadmin/process-automation.md) menüpontot.

A köteg szintjén végzett hatékonysági változás egy ismétlődő kötegelt feladatot használ a rendszerben található összes jogi személyhez. Futásidőben egy új kötegelt feladat jön létre a még nem átvitt szükséges rekordok feldolgozásához. A több beállítást a rendszerfelügyelet **Folyamatautomatizálás** lapján lehet szabályozni. Ezen a lapon módosíthatja a háttérfolyamatot, módosíthatja a gyakoriságot, és meghatározhat egy szüneteltetési időszakot.

A folyamatautomatizálás beállításával kapcsolatos további tudnivalókat lásd: [Folyamatautomatizálás](../../fin-ops-core/dev-itpro/sysadmin/process-automation.md).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
