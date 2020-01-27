---
title: Új vagy módosult elemek a Dynamics 365 Talent (2019. április 16.) szolgáltatásban
description: Ez a témakör a Microsoft Dynamics 365 Talent új vagy módosított szolgáltatásait írja le.
author: Darinkramer
manager: AnnBe
ms.date: 04/16/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-04-16
ms.dyn365.ops.version: Talent
ms.openlocfilehash: a37436eb15ee4c561d5d0c15c90e37815cb80860
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/06/2019
ms.locfileid: "2897925"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-april-16-2019"></a>Új vagy módosult elemek a Dynamics 365 Talent (2019. április 16.) szolgáltatásban

Ez a témakör a Dynamics 365 Talent új vagy módosított szolgáltatásait írja le.

## <a name="changes-in-attract"></a>Változások az Attract-ben

### <a name="process-auditing"></a>Folyamatok auditálása

Immár nyomon követheti a jelentkezők, álláslehetőségek vagy a pályázatok változásait a könyvvizsgálati feldolgozással. További tájékoztatás: [A toborzási adatok változásainak nyomon követése](process-auditing.md).

## <a name="changes-in-onboard"></a>Változások az Onboard alkalmazásban

A kiadás a Dynamics 365 Talent: Onboard apró hibáinak javításait is tartalmazza.

## <a name="changes-in-core-hr"></a>A Core HR módosításai

A szakaszban ismertetett módosítások a 8.1.2239-ös buildre vonatkoznak. A fejlécekben látható, zárójelben lévő számok a Lifecycle Services (LCS) támogatási számaira vonatkoznak.

### <a name="compensation-region-compensation-level-benefit-option-and-skill-type-entities-in-common-data-service-updated-to-include-customer-field-support"></a>Kompenzációs régió, kompenzációs szint, juttatási lehetőség és szakértelem típusa entitások frissülnek a Common Data Service megoldásban a vevői mező támogatásához

Ebben a kiadásban ezek a Common Data Service entitások frissítve lettek, hogy lehetséges legyen egyéni mezők hozzáadása a Talent: Core HR megoldásban.

### <a name="new-common-data-service-entity-support-for-compensation-vesting-rules-compensation-variable-plan-variable-compensation"></a>Új Common Data Service entitás-támogatás: Kompenzációs átruházási szabályok, Kompenzáció-változó konstrukció, Változó kompenzáció

Ebben a kiadásban a Kompenzációs átruházási szabályok, a Kompenzációs változó konstrukció és a változó kompenzáció entitások hozzá lettek adva a Common Data Service megoldáshoz. Ezek az entitások a Talent: Core HR megoldással hozzáadott egyéni mezőket is támogatják.

### <a name="powerbi-refresh-issues-314342"></a>PowerBI frissítési problémák (314342)

A módosítás korrigálja a PowerBI-jelentések megfelelő frissítésével kapcsolatos problémát.

### <a name="unable-to-click-directly-through-on-transition-tasks-in-employee-self-service-303309"></a>Nem lehet közvetlenül rákattintani az Alkalmazotti önkiszolgáló rendszerben az átváltási feladatok között (303309).

Ez a módosítás teszi lehetővé, hogy az alkalmazotti szerepkörrel rendelkező felhasználók kiválasszanak és frissítsenek átváltási feladatokat a Talent teendőlistájából.

### <a name="performance-feedback-email-message-updated-309615"></a>Teljesítmény-visszacsatolási e-mail üzenet frissítve (309615)

Ezzel a módosítással egy visszaigazoló üzenet jelenik meg, ha sikeresen elküldték a visszajelzéseket.

### <a name="missing-tables-in-word-template-308048"></a>Hiányzó táblázatok a Word-sablonban (308048)

Ezzel a módosítással, ha Word-sablon hoz létre az alkalmazottak és szakképzettségek adataival, csak a kiválasztott munkavállalóhoz tartozó szakképzettségek jelennek meg a Word dokumentumban.

### <a name="when-applying-an-offboarding-checklist-an-error-is-displayed-299877"></a>Egy kilépési ellenőrzőlista alkalmazásakor hiba jelenik meg. (299877)

A módosítás javítja azt a hibát, amikor a kilépési ellenőrzőlista alkalmazva van közvetlenül a dolgozó űrlapról.

## <a name="in-preview"></a>Előnézetben

### <a name="allow-reason-codes-to-be-specified-on-leave-types"></a>Okkódok megadásának engedélyezése a szabadságtípusoknál

A szervezeteknek kiegészítő információkra lehet szüksége a szabadságkérelmekkel kapcsolatban. Immár megadhat okkódokat egy adott távolléttípushoz, és engedélyezheti az alkalmazottak számára okkód választását szabadságkérelmükhöz.

### <a name="require-reason-codes-for-certain-leave-types-on-time-off-requests"></a>Okkódok kérése egy szabadságtípusokhoz a távollétkérelmek során

Előfordulhat, hogy a szervezetek okkódok beállítását kérik, bizonyos távolléttípusokhoz, amikor a munkavállalók távolléti kérelmet nyújtanak be. Ennek oka lehet a vállalat szabályzata vagy szabályozási követelmények. Immár meghatározhatja, mely szabadságtípusokhoz szükséges okkód, és alkalmazottaktól megkövetelheti okkód megadását a szabadságtípushoz a távollétkérelmekhez.

### <a name="provide-leave-and-absence-transaction-list-for-hr"></a>Szabadság és a távolléti tranzakciólista átadása a HR-nek

Az alkalmazotti szabadidő követése és a szabadidő kiszámításának ismerete azon túl. hogy segít a HR-nek alkalmazott kérdések megválaszolásában, pontos szabadságmegítéléseket biztosít a munkavállalóknak. HR új nézetet kap a tranzakciókhoz (támogatások, könyvelések, helyesbítések és kérelmek) így láthatja az egyenlegek okait.

## <a name="coming-soon"></a>Hamarosan

### <a name="improvements-to-the-user-interface-for-duplicate-employee-check"></a>A felhasználói felület fejlesztései az ismétlődő alkalmazottak ellenőrzéséhez

Ez a módosítással az ismétlődések észleli a program, amikor névmezőket ad meg, és egy állapot jelenik meg a talált ismétlődések számával. A hivatkozás kiválasztásával megnyithat egy új lapot, hogy megállapítsa, hogy használja-e az észlelt egyezést. Az adatbevitel megzavarása elkerülése érdekében az ismétlődéseket tartalmazó űrlap nem nyílik meg automatikusan.

### <a name="email-support-for-alerts"></a>E-mailek támogatása figyelmeztetésekhez

A Finance and Operations 25-ös platformfrissítésében a felhasználók létrehozhatnak figyelmeztetési szabályokat, amely automatikusan értesítő e-maileket küldenek, a kapcsolattartóknak, ha egy esemény kezdeményezi az értesítést.


