---
title: Új vagy módosult elemek a Dynamics 365 Talent (2019. április 30.) szolgáltatásban
description: Ez a témakör a Microsoft Dynamics 365 Talent új vagy módosított szolgáltatásait írja le.
author: Darinkramer
manager: AnnBe
ms.date: 04/30/2019
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
ms.search.validFrom: 2019-04-30
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 2539baba84bffeb21d351cc307191eea3e940515
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/17/2020
ms.locfileid: "4528195"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-april-30-2019"></a>Új vagy módosult elemek a Dynamics 365 Talent (2019. április 30.) szolgáltatásban

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Ez a témakör a Microsoft Dynamics 365 Talent új vagy módosított szolgáltatásait írja le.

## <a name="changes-in-attract"></a>Változások az Attract-ben

A kiadás a Dynamics 365 Talent: Attract apró hibáinak javításait is tartalmazza.

## <a name="changes-in-onboard"></a>Változások az Onboard alkalmazásban

A kiadás a Dynamics 365 Talent: Onboard apró hibáinak javításait is tartalmazza.

## <a name="changes-in-core-hr"></a>A Core HR módosításai

A szakaszban ismertetett módosítások a 8.1.2270-ös buildre vonatkoznak. A néhány fejlécben látható, zárójelben lévő számok az Microsoft Dynamics Lifecycle Services (LCS) támogatási számaira vonatkoznak.

### <a name="provide-feedback"></a>Visszajelzés küldése

A visszajelzések küldésének lehetősége a Talent **Súgó** menüjében (**?**) található. Ez a menü a következő erőforrások elérését teszi lehetővé:

- Visszajelzés
- Súgó
- Első lépések
- Támogatás
- Ötletek
- Névjegy

### <a name="improvements-to-the-user-interface-for-duplicate-employee-detection"></a>A felhasználói felület fejlesztései az ismétlődő alkalmazottak észleléséhez

Ennek a módosításnak a következtében a program a név mezők beállításakor észleli az ismétlődéseket, és az állapotjelző az észlelt ismétlődések számát mutatja. A megadott hivatkozás egy olyan lapot nyit meg, ahol megadhatja, hogy az ismétlődések egyikét kell-e használni. Az adatbevitel megzavarása elkerülése érdekében az ismétlődéseket tartalmazó lap nem nyílik meg automatikusan. A lap megnyitásához ki kell választania a hivatkozást.

### <a name="common-data-service-entity-support-for-custom-fields"></a>Common Data Service entitás-támogatás egyéni mezőkhöz

A heti kiadásban a következő entitások már támogatják az egyéni mezőket: Foglalkoztatás, Juttatás típusa és Fizetési ciklus.

### <a name="an-error-occurs-when-an-off-boarding-checklist-is-assigned-299877"></a>Hiba történik a kilépési ellenőrzőlista hozzárendelésekor (299877).

A módosítás javítja azt a hibaüzenetet, amely akkor jelenik meg, amikor a kiléptetési ellenőrzőlista a felmondási folyamaton kívül van hozzárendelve.

### <a name="the-exited-workers-link-opens-the-wrong-worker-309939"></a>A kilépett dolgozók hivatkozása nem a megfelelő dolgozót nyitja meg (309939).

Ez a módosítás javítja azt a hibát, amely akkor fordul elő, amikor egy alkalmazottat újra felvesz egy másik jogi személytől, és megpróbál az alkalmazotthoz lépni a kilépett dolgozók listájáról.

### <a name="the-employee-self-service-compensation-card-doesnt-show-summary-values-when-advanced-security-is-turned-on-315231"></a>Az alkalmazotti önkiszolgáló kompenzációs kártya nem jeleníti meg az összesítő értékeket, amikor a speciális biztonság be van kapcsolva (315231).

A módosítás javítja azt a hibát, amely a speciális kompenzációs biztonság használatakor jelentkezik. Ha a speciális biztonság be van kapcsolva, akkor az alkalmazotti önkiszolgáló rendszer az alkalmazottak és a vezetők összesített kompenzációs összegeit is megjeleníti. A módosítás előtt az összesítő értékek 0 (nulla) értékként jelentek meg.

### <a name="if-a-position-without-a-title-is-created-in-common-data-service-no-position-is-created-in-talent-314562"></a>Ha cím nélküli beosztást hoznak létre a Common Data Service megoldásban, a Talentben nem jön létre beosztás (314562)

A heti módosítások korrigálnak egy olyan problémát, amely akkor fordul elő, amikor beosztásokat hoznak létre a Common Data Service megoldásban, de nem adnak meg címet.

### <a name="error-message-in-performance-journal-entries-in-employee-self-service-314134"></a>Hiba történt az alkalmazotti önkiszolgáló rendszer teljesítménynapló-bejegyzéseiben (314134) .

Ez a módosítás javítja azt a hibát, amely akkor fordul elő, amikor a teljesítmény-célkitűzéseket csatol az alkalmazotti önkiszolgáló teljesítménynapló-bejegyzéseihez.

## <a name="in-preview"></a>Előnézetben

### <a name="allow-reason-codes-to-be-specified-on-leave-types"></a>Okkódok megadásának engedélyezése a szabadságtípusoknál

A szervezeteknek kiegészítő információkra lehet szüksége a szabadságkérelmekkel kapcsolatban. Immár megadhat okkódokat egy adott távolléttípushoz, és megengedheti az alkalmazottak számára okkód választását szabadságkérelmükhöz.

### <a name="require-reason-codes-for-specific-leave-types-on-time-off-requests"></a>Okkódok kérése adott szabadságtípusokhoz a távollétkérelmek során

Előfordulhat, hogy a szervezetek okkódok beállítását kérik, bizonyos távolléttípusokhoz, amikor a munkavállalók távolléti kérelmeket nyújtanak be. Ez a követelmény a vállalat szabályzata vagy a törvényi követelmények miatt állhat fenn. Immár meghatározhatja, mely szabadságtípusokhoz szükséges okkód, és alkalmazottaktól megkövetelheti okkód megadását a szabadságtípushoz a távollétkérelmekhez.

### <a name="provide-a-leave-and-absence-transaction-list-for-hr"></a>Egy szabadság és a távolléti tranzakciólista átadása a HR-nek

Az alkalmazotti szabadidő követésének képessége és a szabadidő kiszámításának ismerete azon túl. hogy segít a személyzeti osztálynak (HR) alkalmazott kérdések megválaszolásában, pontos szabadságmegítéléseket biztosít a munkavállalóknak. HR új nézetet kap a tranzakciókhoz (támogatások, könyvelések, helyesbítések és kérelmek) így a HR munkatársai láthatják az egyenlegek okait.

## <a name="coming-soon"></a>Hamarosan

### <a name="email-support-for-alerts"></a>E-mailek támogatása figyelmeztetésekhez

A Finance and Operations 26-ös platformfrissítésben a felhasználók létrehozhatnak figyelmeztetési szabályokat, amely automatikusan értesítő e-maileket küldenek, a kapcsolattartóknak, ha egy esemény kezdeményezi az értesítést.
