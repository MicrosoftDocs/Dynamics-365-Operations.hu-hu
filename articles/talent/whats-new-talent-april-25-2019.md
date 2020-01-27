---
title: Új vagy módosult elemek a Dynamics 365 Talent (2019. április 23.) szolgáltatásban
description: Ez a témakör a Microsoft Dynamics 365 Talent új vagy módosított szolgáltatásait írja le.
author: Darinkramer
manager: AnnBe
ms.date: 04/23/2019
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
ms.search.validFrom: 2019-04-23
ms.dyn365.ops.version: Talent
ms.openlocfilehash: cbafea9063844dd3f19e5828ab37632e04591f18
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/06/2019
ms.locfileid: "2897894"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-april-23-2019"></a>Új vagy módosult elemek a Dynamics 365 Talent (2019. április 23.) szolgáltatásban

Ez a témakör a Dynamics 365 Talent új vagy módosított szolgáltatásait írja le.

## <a name="changes-in-attract"></a>Változások az Attract-ben
A kiadás a Dynamics 365 Talent: Attract apró hibáinak javításait is tartalmazza.

## <a name="changes-in-onboard"></a>Változások az Onboard alkalmazásban
A kiadás a Dynamics 365 Talent: Onboard apró hibáinak javításait is tartalmazza.

## <a name="changes-in-core-hr"></a>A Core HR módosításai
A szakaszban ismertetett módosítások a 8.1.2253-ös buildre vonatkoznak. A fejlécekben látható, zárójelben lévő számok a Lifecycle Services (LCS) támogatási számaira vonatkoznak.

### <a name="common-data-service-entity-support-for-custom-fields"></a>Common Data Service entitás-támogatás egyéni mezőkhöz
A heti kiadástól a következő entitások támogatják a egyéni mezőket: Kompenzációs szint, Juttatási lehetőség, Szakértelem típusa és Kompenzációs régió.

### <a name="additional-odata-entities-302992"></a>További OData-entitások (302992)
A következő entitások immár támogatottak az OData-n belül: Dolgozó szakmai tapasztalata és Dolgozó végzettsége.
   
### <a name="performance-journal-attachments-for-managers-and-employees-308248"></a>Teljesítménynapló-mellékletek vezetőkhöz és alkalmazottakhoz (308248)
Ebben a kiadásban a teljesítménymutatók létrehozásakor és frissítésekor a mellékletek immár a vezetők és az alkalmazottak számára is elérhetők.

### <a name="employee-rehire-flag-always-available-310047"></a>Alkalmazott-újrafelvételi jelző mindig elérhető (310047)
Az alkalmazott-újrafelvételi lehetőség már elérhető a megszűnési folyamaton kívüli frissítéshez. 

### <a name="cannot-change-the-name-of-my-payment-method-308815"></a>A **Saját fizetési időszak** neve nem módosítható (308815)
A személyre szabás engedélyezve lett a **Saját fizetési mód** címkéjének módosításához az Alkalmazotti önkiszolgáló szolgáltatásban.

### <a name="financial-dimensions-against-a-position-cant-be-deleted-293908"></a>A beosztással szemben fennálló pénzügyi dimenziók nem törölhetők (293908)
A pénzügyi dimenziók most már eltávolíthatók, amikor módosítást kérnek egy meglévő beosztáshoz és a pénzügyi dimenzió vállalaton kívüli határaihoz. 

### <a name="customer-is-unable-to-publish-back-data-into-talent-when-opening-the-data-from-excel-302955"></a>A ügyfél nem tud visszaküldeni adatokat a Talentbe, amikor Excel alkalmazásból nyit meg adatokat (302955).
Ez a módosítás javítja a kapcsolódó táblák használatakor tapasztalható közzétételi problémákat.

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
## <a name="known-issues"></a>Ismert problémák

### <a name="email-support-for-alerts"></a>E-mailek támogatása figyelmeztetésekhez
A Finance and Operations 26-ös platformfrissítésében a felhasználók létrehozhatnak figyelmeztetési szabályokat, amely automatikusan értesítő e-maileket küldenek, a kapcsolattartóknak, ha egy esemény kezdeményezi az értesítést.
