---
title: Új vagy módosult elemek a Dynamics 365 Talent (2019. április 9.) szolgáltatásban
description: Ez a témakör a Microsoft Dynamics 365 Talent új vagy módosított szolgáltatásait írja le.
author: Darinkramer
manager: AnnBe
ms.date: 04/09/2019
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
ms.search.validFrom: 2019-04-09
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 0a4d4de6cf28e24d1265395d6440df85edf71a0d
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/06/2019
ms.locfileid: "2897856"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-april-9-2019"></a>Új vagy módosult elemek a Dynamics 365 Talent (2019. április 9.) szolgáltatásban

Ez a témakör a Dynamics 365 Talent új vagy módosított szolgáltatásait írja le.

## <a name="changes-in-attract"></a>Változások az Attract-ben

### <a name="lifecycle-services-lcs-integration-with-report-a-problem"></a>Lifecycle Services (LCS) integráció „probléma jelentésével”
Attract és Onboard megoldásokban a végfelhasználók által naplózott problémák a probléma jelentése szolgáltatással automatikusan támogatási problémákat hoznak létre az ügyfél LCS projektjében. Az adminisztrátorok ezt követően besorolhatják a problémákat, majd elküldhetik azokat a Microsoftnak, amikor szükséges. Ez megfelel annak, ahogy a Core HR kezeli a végfelhasználói támogatási problémákat.

### <a name="relevance-search"></a>Relevanciakeresés
A tehetségállományokban adott szakértelmek, nevek és tanulmányi hátterek alapján kereshet a teljese jelölti adatbázisban. Nem kell többé megadnia, hogy melyik részében szeretne keresni a jelentkező profiljának. Az Attract a teljes profilban keres, és az összes találatot kiemeli. Az Attract keres minden olyan dokumentumban, amely elérhető a jelöthöz, és intelligens módon osztályozza a keresési eredményeket. Ezenkívül az eredményeket szűrheti, forrás szerint vagy az alapján, hogy ezüstérmesek-e. További tudnivalókért lásd: [Keresése és megtekintése a jelölt profiloknak](https://docs.microsoft.com/dynamics365/unified-operations/talent/attract-talent-pools#search-and-view-candidate-profiles).

### <a name="prospect-recommendations"></a>Potenciális jelöltekre vonatkozó javaslatok
Az Attract segít elindítani a keresést egy munkához amint aktiválja azt, azáltal, hogy intelligens jelöltajánlásokat kínál a vállalat jelöltadatbázisából. Az ajánlások tartalmazzák a szakértelemre oktatásra vonatkozó adatokat, amikor a releváns potenciális jelöltek között keres. Ezek a javaslatok megjelennek a **Potenciális jelöltek** lapon egy állás alatt, ha engedélyezi a az állás felvételi folyamata során. További információ: [Potenciális jelöltekre vonatkozó javaslatok](https://docs.microsoft.com/dynamics365/unified-operations/talent/intelligent-recommendations#prospect-recommendations).

### <a name="interviewer-availability-statuses"></a>Interjúkészítők elérhetőségének állapota
Az interjúütemezők hamarosan megtekinthetik a **Házon kívül, máshol dolgozik** állapotokat az interjúztatókhoz, így olyan időpontokat ütemezhetnek, amelyek jobban megfelelnek az interjúztatóknak.

### <a name="candidate-interview-experience-save-calendar-invites"></a>Pályázó interjúélmény: Naptármeghívók mentése
Pályázók mostantól letölthetik és telepíthetik az interjú eseményeket személyes naptárjukba a pályázónak küldött összegző e-mailhez csatolt .ics fájl segítségével.

## <a name="changes-in-onboard"></a>Változások az Onboard alkalmazásban

### <a name="lifecycle-services-lcs-integration-with-report-a-problem"></a>Lifecycle Services (LCS) integráció probléma jelentésével
Attract és Onboard megoldásokban a végfelhasználók által naplózott problémák a probléma jelentése szolgáltatással automatikusan támogatási problémákat hoznak létre az ügyfél LCS projektjében. Az adminisztrátorok ezt követően besorolhatják a problémákat, majd elküldhetik azokat a Microsoftnak, amikor szükséges. Ez megfelel annak, ahogy a Core HR kezeli a végfelhasználói támogatási problémákat.

## <a name="changes-in-core-hr"></a>A Core HR módosításai
A szakaszban ismertetett módosítások a 8.1.2225-ös buildre vonatkoznak.

### <a name="percent-of-basis-variable-plans-load-incorrect-amount"></a>A változó konstrukciók alapszázaléka betöltésekor helytelen összeg jelenik meg
Az eheti kiadási javít egy problémát a változó kompenzációk betöltése során az alapkonstrukciók használatával.
 
### <a name="date-picker-on-last-day-worked-doesnt-work-correctly"></a>Az utolsó munkában töltött nap dátumválasztója nem működik megfelelően
Ezt a módosítást megoldja a problémát: Ha a felhasználó szerkeszti a **Munkaviszony megszűnésének dátuma** elemet, és a naptárvezérlővel választja ki a dátumot egy nap hozzáadódik a kijelöléshez.

###  <a name="limit-personnel-action-types-by-the-action-taken"></a>Személyzeti művelettípusok korlátozása végrehajtott művelet szerint
Ez a módosítás korlátozza a művelettípusokat, amely akkor jelennek meg, amikor a bizonyos műveletek végrehajtása történik. Például, ha új beosztásra szükség, csak a beosztásműveletek jelennek meg a műveletek választására szolgáló listában. Korábban mind az új és szerkesztési műveletek is megjelentek. 

### <a name="transferring-an-employee-with-compensation-in-a-second-legal-entity"></a>Az alkalmazott átvitele kompenzációval egy második jogi személyhez
Ez a kiadás lehetővé teszi, hogy a kompenzáció egy második jogi személynél fejeződjön be vállalatok közötti átvitel esetén.

### <a name="unable-to-select-compensation-for-a-future-employment-during-a-transfer"></a>Nem lehet kijelölni egy jövőbeli munkaviszonyhoz a kompenzációt az átvitel során
Egy alkalmazott átvitele során egy új jogi személyhez, most beállíthat kompenzációt az új jogi személyhez az átviteli folyamat során.

### <a name="user-isnt-able-to-assign-compensation-during-position-assignment"></a>A felhasználó nem tud kompenzációt hozzárendelni egy beosztás-hozzárendelés során
Új beosztásra vonatkozó megbízás hozzáadása immár lehetővé teszi a fix kompenzációs rekordok beállítását. 

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

###  <a name="email-support-for-alerts"></a>E-mailek támogatása figyelmeztetésekhez
A Finance and Operations 25-ös platformfrissítésében a felhasználók létrehozhatnak figyelmeztetési szabályokat, amely automatikusan értesítő e-maileket küldenek, a kapcsolattartóknak, ha egy esemény kezdeményezi az értesítést. 
