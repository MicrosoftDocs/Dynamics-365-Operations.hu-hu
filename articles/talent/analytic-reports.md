---
title: Analitikus jelentések használata a toborzási folyamattal kapcsolatos információk érdekében
description: Ez a témakör az Attract analitikus jelentéseiről szól
author: fewatson
manager: AnnBe
ms.date: 04/30/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: fewatson
ms.search.validFrom: 2019-04-30
ms.dyn365.ops.version: Talent April 2019 update
ms.openlocfilehash: 33ed6072a9ad99144fb96ad19389a57461324f71
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/07/2019
ms.locfileid: "1516560"
---
# <a name="use-analytic-reports-for-hiring-process-insights"></a>Analitikus jelentések használata a toborzási folyamattal kapcsolatos információk érdekében

Az Attract analitikus jelentései egy beépített (OOTB) megoldást biztosítanak a felvételi folyamat háttérinformációihoz. A rendelkezésre álló funkciók a következők:

- **Álláselemzés** – Kattintson egy állás **Elemzés** lapjára, és megtekintheti az állás pályázójára vonatkozó mutatókat.
- **Elemzési központ:** Kattintson a bal oldali navigációs menüben az **Elemzés** pontra az állások összesített mutatóiért.
- **Felhasználói szintű biztonság:** A jelentésekhez való hozzáférést az Attract [szerepköre](security-attract.md) és az állás résztvevőjének szerepköre szabályozza.
- **Keresztszűrés:** A jelentésen belül a vizuális elemekre kattintva megtekinthet további mutatókat a kijelölt adat szerint szűrve.

>[!NOTE] 
>- Ez a funkció jelenleg [előzetes verzióban](access-preview-feature.md) elérhető. Ha ki szeretné próbálni, rendelkeznie kell az [**Átfogó felvételi bővítménnyel**](attract-comprehensive-hiring.md).
>- Az összes nyilvános előzetes jelentés angolul jelenik meg.
>- A jelentések 3 óránként frissülnek. A jelentés felső részén található a legutóbbi frissítési idő (a helyi időzónában). A frissítési idők becsült értékek, és a régióban használt adatmennyiségtől és erőforrás-terheléstől is függenek.

## <a name="job-analytics"></a>Állással kapcsolatos elemzések

Az Álláselemzési jelentések pillanatképet biztosítanak egy állás felvételi folyamatáról.  A fő mutatók a következők:

- Aktív pályázók fokozat szerint
- Pályázó forrása
- Pályázó típusa (belső vagy külső)

## <a name="analytics-hub"></a>Elemzési központ

Az Elemzési központ jelentések aggregálják az állások adatait, és így kimutatják a felvételi folyamat trendjeit. A program két beépített jelentést tartalmaz: a prognózis összegzése és a tölcsérelemzés.

### <a name="pipeline-summary"></a>Értékesítési prognózis összegzése

A prognózisösszesítő jelentés összesíti a nyitott állások adatait. A fő mutatók a következők:

- Bármely állás pályázói fokozat szerint
- Pályázó forrása
- Nyitott állások a szolgálati idő szintje szerint

### <a name="funnel-analysis"></a>Tölcsérelemzés

A tölcsérelemzési jelentés összesíti a betöltöttként lezárt állások adatait. A fő mutatók a következők:

- Felvétel időpontja
- Konverziós mutatók (rámutatáskor)
- Ajánlat elfogadási rátája

Megjegyzés: A felvételi jelentés legpontosabb időpontjának érdekében javasoljuk, hogy használja az [Ajánlatkezelés](offer-setup.md) funkciót, amely az Átfogó felvételi bővítmény részeként elérhető.

>[!TIP] 
>További információért vigye az egérmutatót a vizuális elemek fölé. Például ha egérre rámutat az **Aktív pályázók** elemre, a vizuális elemek megmutatják a fokozaton töltött napok átlagos számát. Ezen információk elemzése kritikus fontosságú információkat nyújthat a felvétel idejének lecsökkentéséhez, és lehetővé teszi, hogy a toborzók olyan módszerekre koncentráljanak, amelyek lecsökkentik az egyes fokozatokon töltött időt.

## <a name="user-specific-security"></a>Felhasználóspecifikus biztonság

Az Attract-jelentések Rendszergazda, Minden olvasása, Toborzó és Felvételi vezető [szerepkörrel](security-attract.md) rendelkezők számára hozzáférhetők. A nem hozzárendelt felhasználók nem férhetnek hozzá a elemzési jelentés oldalaihoz (az Állás elemzése és az Elemzési központ oldalakhoz).

Az Álláselemzés jelentések a kiválasztott állás adatait jelenítik meg. Az Elemzési központ a felhasználó által megtekinthető összes állásra vonatkozóan összesítve jelenti az adatokat. A felhasználók, akik az Állások oldalon megtekinthetik a Saját állások és az Összes állás lapot, ugyanazt látják az Elemzési központban.

## <a name="cross-filter"></a>Keresztszűrés

A Power BI egyik nagyszerű funkciója az a mód, ahogy a jelentés oldalának összes vizuális eleme összeköttetésben van. Ha kijelöl egy adatpontot az egyik vizális elemen, az oldalon található összes másik vizuális elem módosul, amely tartalmazza az adatot, a kiválasztás alapján. További információt és példát a [Hogyan végeznek a vizuális elemek keresztszűrést egy Power BI-jelentésben](https://docs.microsoft.com/en-us/power-bi/consumer/end-user-interactions) részben talál.

## <a name="export-to-excel"></a>Exportálás az Excel programba

Ha meg szeretné tekinteni a jelentések adatait az Excel programban, kattintson a vizuális elem beállítások menüpontjára (három pont), és válassza a **Háttéradatok exportálása** lehetőséget. Az exportált adatok szűrve kerülnek exportálásra, az Attract szolgáltatásban érvényes felhasználói engedélyek figyelembe vételével. A további információkért lásd: [Adatok exportálása vizualizációból](https://docs.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-export-data).
