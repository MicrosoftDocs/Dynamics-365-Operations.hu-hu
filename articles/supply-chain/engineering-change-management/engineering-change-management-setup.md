---
title: Közös értékek létrehozása a mérnöki módosításkezeléshez
description: Ez a témakör azt ismerteti, hogyan hozhat létre közös értékeket, amelyeket a mérnöki módosításkezelés különböző részeinek paramétereihez használnak.
author: t-benebo
ms.date: 09/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EngChgProductParameters, EngChgEcmSeverityTable, EngChgEcmSeverityRuleSet, EngChgEcmSeverityLookup,EngChgEcmSeverityChart,EngChgEcmRequestSeverityChart,EngChgEcmPriorityTable, EngChgEcmPriorityLookup, EngChgEcmPriorityChart, EngChgEcmMaterialDisposition, EngChgEcmEH
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 65f86fc488fe25cd4b093461088134fd7ad0c45ca569cd8f751314f1f5d88b6c
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6753300"
---
# <a name="establish-common-values-for-engineering-change-management"></a>Közös értékek létrehozása a mérnöki módosításkezeléshez

[!include [banner](../includes/banner.md)]

A műszaki módosításkezelés beállításakor több értékgyűjteményt kell létrehoznia, amelyek a felhasználói felület (UI) más részeiben található legördülő listák kitöltésére szolgálnak. Ezeket az értékeket az Ön által előállított terméktípusok és az adott üzleti igények szerint kell megadnia.

## <a name="engineering-change-categories"></a>Tervezési módosítás kategóriái

A mérnöki módosítási kategóriák segítségével rendszerezheti a mérnöki módosítási rendeléseket, hogy könnyebben kezelhetők és áttekinthetők legyenek. Hasznos lehet például egy munkafolyamat beállítása, ahol a kategóriától függően egy adott részlegnek át kell tekintenie a javasolt módosításokat. Ezért a mérnöki módosítási rendelés tartalmaz egy **Kategória** mezőt.

A vállalatnál használt műszaki módosítási kategóriák gyűjteményének létrehozásához nyissa meg a **Mérnöki módosításkezelés \> Beállítás \> Mérnöki módosításkezelés \> Mérnöki módosítási kategóriák** elemet. Ezután a művelet panel gombjaival értékeket adhat hozzá, távolíthat el és szerkeszthet, és a megjelenő legördülő listákban való megjelenésük sorrendjébe rendezheti őket.

## <a name="engineering-change-priorities"></a>Tervezési módosítás prioritásai

A mérnöki módosítási prioritásokkal jelezheti a mérnöki módosítási rendelés fontosságát vagy sürgősségét. Ezek segítségével nyomon követheti a mérnöki módosítási rendelés fontosságát, így könnyen azonosíthatja, hogy mely rendeléseket kell először feldolgozni, és milyen gyorsan.

A vállalatnál használt műszaki módosítási prioritások gyűjteményének létrehozásához nyissa meg a **Mérnöki módosításkezelés \> Beállítás \> Mérnöki módosításkezelés \> Mérnöki módosítási prioritások** elemet. Ezután a művelet panel gombjaival értékeket adhat hozzá, távolíthat el és szerkeszthet, és a megjelenő legördülő listákban való megjelenésük sorrendjébe rendezheti őket.

## <a name="engineering-change-reasons"></a>Tervezési módosítás okai

A műszaki módosítás okai jelzik a módosítási rendelés módosításának okát vagy jellegét.

A vállalatnál használt műszaki módosítási okok gyűjteményének létrehozásához nyissa meg a **Mérnöki módosításkezelés \> Beállítás \> Mérnöki módosításkezelés \> Mérnöki módosítási okok** elemet. Ezután a művelet panel gombjaival értékeket adhat hozzá, távolíthat el és szerkeszthet, és a megjelenő legördülő listákban való megjelenésük sorrendjébe rendezheti őket.

## <a name="material-disposal-codes"></a>Anyaggal kapcsolatos intézkedési kódok

Az anyagártalmatlanítási kódokat a késztermékekben használt anyagok vagy olyan alkatrészek kategorizálására használhatja, amelyeket meghatározott módon kell ártalmatlanítani, vagy valamilyen kezelést igényelnek, mielőtt hozzáadhatók a szokásos hulladékhoz. Amikor hozzáad egy releváns terméket egy műszaki módosítási rendeléshez, a módosítás részleteinek részeként hozzárendelhet egy ártalmatlanítási kódot.

A vállalatnál használt anyagártalmatlanítási kódok gyűjteményének létrehozásához nyissa meg a **Mérnöki módosításkezelés \> Beállítás \> Mérnöki módosításkezelés \> Anyagártalmatlanítási kódok** elemet. Ezután a művelet panel gombjaival értékeket adhat hozzá, távolíthat el és szerkeszthet, és a megjelenő legördülő listákban való megjelenésük sorrendjébe rendezheti őket.

## <a name="received-customer-approval"></a>Megszerzett ügyféljóváhagyás

Ha egy adott vevőnek tervez termékeket, a tervezést és a specifikációkat gyakran ellenőrizni kell, mielőtt a termék készen állna. A **Beérkezett vevői jóváhagyás** mezőben megadhatja, hogy a vevő jóváhagyási folyamatában hol tart a termék, és/vagy hogy a jóváhagyás megérkezett-e.

A vállalatnál használt beérkezett vevői jóváhagyási értékek gyűjteményének létrehozásához nyissa meg a **Mérnöki módosításkezelés \> Beállítás \> Mérnöki módosításkezelés \> Beérkezett vevői jóváhagyás** elemet. Ezután a művelet panel gombjaival értékeket adhat hozzá, távolíthat el és szerkeszthet, és a megjelenő legördülő listákban való megjelenésük sorrendjébe rendezheti őket.

## <a name="engineering-change--environmental-health-and-safety-codes"></a>Műszaki módosítások – Környezetvédelmi, egészségvédelmi és biztonsági kódok

Ha a termék gyártása során bármilyen szabványos környezetvédelmi és biztonsági előírást, illetve vállalatspecifikus előírást vagy eljárást figyelembe kell venni, akkor a környezetvédelmi és biztonsági kódok segítségével meghatározhatja azokat. A műszaki módosítási rendelésben az érintett termék részleteinek szerkesztése közben jelezheti, hogy mely kódok vonatkoznak a termék gyártására.

A vállalatnál használt egészségügyi és biztonsági értékek gyűjteményének létrehozásához nyissa meg a **Mérnöki módosításkezelés \> Beállítás \> Mérnöki módosításkezelés \> Környezetvédelmi, egészségvédelmi és biztonsági kódok** elemet. Ezután a művelet panel gombjaival értékeket adhat hozzá, távolíthat el és szerkeszthet, és a megjelenő legördülő listákban való megjelenésük sorrendjébe rendezheti őket.

## <a name="engineering-change-severities"></a>Tervezési módosítás súlyosságai

A műszaki módosítási súlyosságok segítségével jelezheti a műszaki módosítási rendelésben lévő termékekre gyakorolt hatás szintjét.

A vállalatnál használt műszaki módosítási súlyosságok gyűjteményének létrehozásához nyissa meg a **Mérnöki módosításkezelés \> Beállítás \> Mérnöki módosításkezelés \> Mérnöki módosítási súlyosságok** elemet. Ezután a művelet panel gombjaival értékeket adhat hozzá, távolíthat el és szerkeszthet, és a megjelenő legördülő listákban való megjelenésük sorrendjébe rendezheti őket.

Olyan szabályokat hozhat létre, amelyek minden egyes létrehozott súlyossági szintre vonatkoznak. A szabályok hozzárendeléséről a következő szakaszban talál további információt.

## <a name="engineering-change-severity-rule-sets"></a>Tervezési módosítás súlyossági szabálykészletei

A mérnöki módosítások súlyossági szabálykészletei segítségével olyan szabálycsoportot hozhat létre, amelynek segítségével az érintett termékek módosítási típusa alapján automatikusan kiszámíthatja a módosítási rendelés súlyosságát. A súlyossági szabályok használatához nyissa meg a **Mérnöki módosításkezelési paraméterek** oldalt, és állítsa a **Súlyossági szabályt** mezőt *Számítás* vagy *Automatikus számítás* értékre.

Amikor a rendszer kiértékeli a súlyosságot, a szabályokat abban a sorrendben dolgozza fel, ahogyan azok az oldalon megjelennek, fentről lefelé. Ahhoz, hogy egy szabályt ki lehessen választani, és a prioritását létre lehessen hozni, a szabálykészlet összes szabályának teljesülnie kell.

Az egyes meghatározott módosítási súlyossági szintekre vonatkozó szabályok beállításához nyissa meg a **Mérnöki változáskezelés \> Beállítás \> Mérnöki változáskezelés \> Mérnöki változások súlyossági szabálykészletei** menüpontot. Majd tegye a következők egyikét.

- Új szabálykészlet létrehozásához válassza az **Új** lehetőséget a Művelet ablakon, majd állítsa be a mezőket a szakasz további részében leírtak szerint.
- Meglévő szabálykészlet szerkesztéséhez jelölje ki azt a listapanelen, válassza a Művelet ablak **Szerkesztés** parancsát, majd állítsa be a mezőket a szakasz későbbi részében leírtak szerint.
- Meglévő szabálykészlet törléséhez jelölje ki azt a listapanelen, majd válassza a **Törlés** lehetőséget a Művelet panelen.
- A szabálykészletek listájának átrendezéséhez jelöljön ki egy szabálykészletet a listapanelen, majd a műveleti panel **Fel** és **Le** gombjaival helyezze át azt.

Állítsa be a következő mezőt minden egyes szabálykészletnél:

- **Súlyosság** – Válassza ki a súlyossági szintet, amelyhez szabályokat szeretne megállapítani. A **Mérnöki változás súlyosságai** oldalon hozhatja létre és nevezheti el a szinteket. (A további tudnivalókat lásd a korábbi szakaszban.)

A **Szabályok** gyorslap gombjaival hozzáadhat vagy eltávolíthat szabályokat az aktuális súlyossági beállításra vonatkozóan. Minden szabályhoz található egy **Szabályok** mező és egy **Név** mező. A szabályokat a rendszer határozza meg, és jelzik, hogy a termék milyen típusú módosításokkal rendelkezhet. A név jelzi a módosítási típust.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]