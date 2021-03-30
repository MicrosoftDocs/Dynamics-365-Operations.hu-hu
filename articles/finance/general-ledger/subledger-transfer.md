---
title: Részfőkönyv átvitele a főkönyvbe
description: Ez a témakör azt mutatja be, hogy a Microsoft Dynamics 365 Finance milyen funkciókat tartalmaz a részfőkönyv főkönyvbe történő átmozgatási folyamatához kapcsolódóan.
author: roschlom
manager: AnnBe
ms.date: 09/09/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
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
ms.openlocfilehash: aec68b9389ee2ef28e8119087392ac5f18ec5dd2
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5204785"
---
# <a name="subledger-transfer-to-the-general-ledger"></a>Részfőkönyv átvitele a főkönyvbe

[!include [banner](../includes/banner.md)]

Ez a témakör a Microsoft Dynamics 365 Finance azon képességeit mutatja be, amelyek a főkönyvi naplóbejegyzések kötegek átviteléhez szükséges szabályokhoz kapcsolódnak.

A 8.1 verzióban a módosítások lehetővé teszik azon szabályok átmozgatását, amelyek felváltották a **Szinkron** opciót. További információért lásd: [Eltávolított vagy elavult funkciók a Finance and Operations esetében](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/deprecated-features?toc=/dynamics365/finance/toc.json#finance-and-operations-81-with-platform-update-20).

A következő lehetőségek érhetők el a részfőkönyvi kötegek átviteléhez. 

 - Aszinkron – ez a beállítás azonnal ütemezni fogja a részfőkönyvi könyvelési tételek átvitelét a főkönyvbe. A program rögzíti a főkönyvi bizonylatot, mihelyt az erőforrások szabadon feldolgozhatják ezt a kérelmet a kiszolgálón. 

- Ütemezett köteg – ezzel a beállítással hozzáadja a főkönyv feldolgozási várólistájába átvitt olyan részkönyv-könyvelési tételeket, amelyeknél a program feldolgozza a tételeket a beérkezett sorrendben. A program rögzíti a főkönyvi bizonylatot abban az ütemezett időben, amikor az erőforrások szabadon feldolgozhatják ezt a kötegelt feladatot a kiszolgálón. 
 
A 10.0.8-as verzióban az Aszinkron beállítás teljesítményének javítását végezték. Ez a funkció engedélyezve van a **Részfőkönyv átvitele a főkönyv teljesítményoptimalizálása érdekében** szolgáltatásnévvel. 
 
Ez a funkció javítja az adatoknak a részfőkönyvből a főkönyvbe történő átvitelét. Ez lehetővé teszi a folyamat hatékonyabb kezelését, és az átmozgatásra kisebb tranzakciók halmazait csoportosítja. Ez lehetővé teszi a kötegelt kiszolgáló hatékonyabb használatát. Ez a funkció megköveteli, hogy a kötegfájlt be legyen állítva, online legyen és működjön ahhoz, hogy az Aszinkron átviteli beállítás működjön. 


[!INCLUDE[footer-include](../../includes/footer-banner.md)]