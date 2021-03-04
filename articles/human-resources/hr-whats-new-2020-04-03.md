---
title: Új vagy módosult elemek a Dynamics 365 Human Resources (2020. április 3.) szolgáltatásban
description: Ez a cikk a Microsoft Dynamics 365 Human Resources új vagy módosított szolgáltatásait írja le a 2020. április 3-i kiadásban.
author: Darinkramer
manager: AnnBe
ms.date: 04/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2020-04-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 8f5d7ab996e0d27f763cd4c3c51e9a2c923d909b
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/17/2020
ms.locfileid: "4526786"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-april-3-2020"></a>Új vagy módosult elemek a Dynamics 365 Human Resources (2020. április 3.) szolgáltatásban

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Ez a cikk a Dynamics 365 Human Resources szolgáltatásban található új vagy módosított funkciókat írja le. A változtatások a 8.1.3111-es buildszámra vonatkoznak. A néhány fejlécben látható, zárójelben lévő számok tájékoztatásként a Lifecycle Services (LCS) támogatási számaira vonatkoznak.

## <a name="features-that-are-generally-available-the-week-of-april-6"></a>Az április 6-ikai héttől általánosan elérhető szolgáltatások

- **Szabadság és távollét funkciói** – További tudnivalókat lásd: [Szabadság és a távollét áttekintése](hr-leave-and-absence-overview.md).

- **Juttatáskezelési funkciók** – A további tudnivalókat lásd: [Juttatások kezelésének áttekintése](hr-benefits-management-overview.md).

## <a name="human-resources-environment-limits-are-now-based-on-updated-licensing-394595"></a>A Human Resources környezeti korlátai jelenleg frissített licencelésen alapulnak (394595)

A projektenként elérhető környezetek számának korlátozása az LCS szolgáltatásban megváltozott. Az előző korlát két környezet volt. Az LCS-ben a Human Resources megoldásban a termelési és teszt környezetek létrehozására vonatkozó korlátozás immár a frissített licencelésen alapul. Mostantól a megvásárolt licencek számától függően igény szerinti számban hozhat létre környezeteket egy-egy LCS-projekthez. A 2020. február 1-jén frissített új licencelés lehetővé teszi az ügyfelek számára, hogy további környezeteket vásároljanak. További tájékoztatás a licencelési követelményekről további környezetekhez: [Dynamics 365 licencelési útmutató](https://dynamics.microsoft.com/pricing/#HumanResources).
 
## <a name="error-when-trying-to-delete-a-questionnaire-428603"></a>Hiba egy kérdőív törlése közben (428603)

A heti frissítés javítja azt a hibát, amelyben egy kérdőív törlésekor a következő hiba jelent meg:

Nem kiegyensúlyozott XX++ TTSBEGIN/TTSCOMMI pár észlelhető.

## <a name="performance-journal-and-professional-certificates-security-issue-428499"></a>A Teljesítménynapló és a szakmai tanúsítványok biztonsági problémája (428499)

Ez a módosítás korlátozza mind a teljesítménymutatók, mind a szakmai tanúsítványok láthatóságát azon vállalatok alapján, amelyekhez hozzáféréssel rendelkeznek. 

## <a name="the-abbreviation-for-quebec-and-manitoba-387510"></a>Quebec és Manitoba rövidítése (387510)

A kezdő adatok frissítve lettek Manitoba és Quebec helyes rövidítésének megfelelően.

## <a name="new-entities-available-in-data-management-framework"></a>Új entitások érhetők el az Adatkezelő keretrendszerben

A következő entitások állnak rendelkezésre. Ha nem látja ezeket az entitásokat az entitások listában, akkor válassza az **Entitások frissítése** lehetőséget a **Keretrendszer paraméterei > Entitásbeállítások > Entitáslista frissítése helyen**.

 - Szabadsági és távolléti banki tranzakció V2
 - Szabadság és távollét bejegyzése V2
 - Szabadság- és távolléti terv szintje V2
 - Szabadság- és távolléti terv V2

## <a name="common-data-service-solution-is-now-available-with-the-following-changes"></a>A Common Data Service megoldás már elérhető a következő változtatásokkal:

| Leírás | Visszajáró |
| --- | --- |
| **Feladat/pozíció** entitás módosításai | <ul><li>**Kompenzációs régió** hozzáadása</li>|
| **Munkaköri dimenzió** entitás hozzáadva | <ul><li>**Pénzügyi dimenziók** hozzáadása</li>
| **Dolgozó** entitás módosításai | <ul><li>**Névsorrend** hozzáadása</li><li>**Otthonról dolgozik** hozzáadása</li><li>**Nyelv** hozzáadása</li><li>**Szolgálati idő dátuma** hozzáadása</li><li>**Évforduló dátuma** hozzáadása</li><li>**Eredeti felvételi dátum** hozzáadása</li></ul> |
| **Foglalkoztatás** entitás módosításai | <ul><li>**Pénzügyi dimenziók** hozzáadása</li><li>**Felmondás oka** hozzáadása</li><li>**Megszűnés dátuma** az **Áttérési dátumtól** átnevezve</li><li>**Próbaidős dátum** hozzáadása</li></ul> |
| **Dolgozó címe** entitás módosításai | <ul><li>**Utca és házszám** hozzáadása</li><li>**1. címsor**, **2. címsor** és **3. címsor** megjelölve megszűnésre</li></ul> |
| Új változó kompenzációs beállítási entitások | <ul><li>**Változó kompenzációs konstrukció típusa**</li><li>**Változó kompenzációs konstrukció**</li><li>**Kilépési szabályok**</li><li>**Változó kompenzációs konstrukció szintje**</li></ul> |
| Új **Dolgozói naptár – foglalkoztatás** entitás | <ul><li>**Munkanaptár-entitás** hozzáadva</li></ul> |
| Új **Bérlista szerinti beosztás részletei** entitás | <ul><li>**Bérlista szerinti beosztás** részletei</li></ul> |
| Új **Beosztás** entitás | <ul><li>**Beosztás** hozzáadva</li></ul>Az új **Beosztás** entitást a Common Data Service tartalmazza, de jelenleg a **Munkakör** vagy **Munka** entitások nem hivatkoznak rá. |

> [!NOTE]
> A beosztások és a foglalkoztatás pénzügyi dimenziói egyirányú integrációt biztosítanak a Human Resources és a Common Data Service közötti frissítésekhez. A pénzügyi dimenziók frissítései jelenleg nem szinkronizálnak a Common Data Service és a Human Resources között.

Az elkövetkezendő hetekben ezek az entitásmódosítások minden környezetben elérhetők lesznek. A legújabb Common Data Service megoldás manuális telepítése a Human Resourcesbe:

1.  Ugorjon a [Power Platform Adminisztrációs központba](https://admin.powerplatform.microsoft.com).

2.  Válassza a **Környezetek** lehetőséget.

3.  Keresse meg a frissíteni kívánt környezetet. A környezetnek meg kell egyeznie a **Környezet nevével** a **Common Data Service információk** szakaszban a Human Resources **Névjegy** képernyőjén.

4.  A környezet adatainak megtekintéséhez válassza ki a környezetet.

5.  Válassza ki a **Megoldások kezelése** elemet a felső műveletsávból. A rendszer egy új böngészőablakot nyit meg, és megnyitja a **Dynamics 365 felügyeleti központot** a környezete kontextusában.

6.  A **Megoldás** listán válassza a **Dynamics 365 Human Resources horgony** elemet.

7.  Válassza a **Frissítés** parancsot a legújabb megoldás alkalmazásához.

## <a name="in-preview"></a>Előnézetben

## <a name="leave-suspension"></a>Szabadság felfüggesztése

Egy alkalmazottra vonatkozóan felfüggesztheti a szabadságokat és a távollétet. A szabadság felfüggesztése kiválasztott távolléti típusoknál leállítja az elhatárolást. Ha a felfüggesztés a könyvelés feldolgozását követően következik be, akkor a szabadság felfüggesztése az alkalmazott szabadságának egyenlegéhez egy arányosan korrigált kiigazítást hoz majd létre. További információ: [Szabadság felfüggesztése](hr-leave-and-absence-suspend-leave.md).

## <a name="carry-forward-rules"></a>Átvitel szabályai

Megadhatja, hogy az átviteli szabadságtípust az átviteli egyenlegekhez, ahová az átviteli korrekciók ár lesznek helyezve. Ha például egy alkalmazott 10 napot visz át, akkor a 10 napnál más szabadság-típust is kiválaszthat. További tájékoztatás: [Szabadság és távolléti típusok konfigurálása](hr-leave-and-absence-types.md).

## <a name="coming-soon"></a>Hamarosan

## <a name="new-production-release-cadence"></a>Új termelési kiadás ütemezése

Áprilistól kezdődően a program a Human Resources kiadási ritmusa heti frissítésről a kétheti frissítésre módosul. A biztonságos telepítési gyakorlattal való összehangolás biztosításához és a szolgáltatásban a stabilitás és megbízhatóság magas színvonalának megőrzéséhez a szolgáltatás frissítései minden régióban két hetes ütemezésre váltanak. További tesztek és nyomon követések lesznek bevezetve a sikeres telepítés megerősítéséhez a folyamat minden egyes fázisában. A kiadás ritmusával kapcsolatos további tudnivalókat lásd: [Frissítési folyamat](hr-admin-setup-update-process.md).

## <a name="known-issues"></a>Ismert problémák

## <a name="employment-detail-entity"></a>Foglalkoztatás részletei entitás

A **Foglalkoztatási adatok** entitása frissítve lett a következő mezőkkel: **PayFrequency**, **Foglalkoztatási kategória azonosítója**, **Foglalkoztatási típus**, **EmploymentTypeID** és **Juttatás foglalkoztatási státusza**. Ezeknek a mezőknek a beállítási adatai a Funkciókezelésben engedélyezve vannak a juttatások kezeléséhez. Ne töltse ki vagy frissítse ezeket a mezőket a **Foglalkoztatás részletei** entitásban, mert ez hibákat fog eredményezni az importálás során.

## <a name="sharepoint-preview-doesnt-work-in-some-environments"></a>SharePoint előnézet nem használható bizonyos környezetekben

Ha egy, a SharePoint-ban tárolt dokumentum előnézete nem működik, próbálja meg a következő eljárást:

1. Ellenőrizze, hogy az Adminisztrátor felhasználói fiók rendelkezik-e a felhasználói rekordhoz társított e-mail-címmel. Ezt az információt a **Felhasználó** oldalon lehet megtekinteni. Ha nincs beállítva e-mail-cím, akkor az e-mail-címet és a szolgáltatót hozzá kell adnia az OData Excel-bővítménnyel. Alapértelmezés szerint az e-mail-cím nem szerepel az Excel-tervben. Szerkesztenie kell az Excel-tervet, minden mezőt fel kell venni, alkalmazni kell, majd frissíteni kell. Miután befejezte ezeket a lépéseket, frissítheti az adminisztrátori fiókot.

2. Miután az Adminisztrátor fiókhoz hozzá van rendelve egy e-mail-fiók, az Adminisztrátori hitelesítő adatokkal jelentkezzen be a Human Resources szolgáltatásokba.

3. A dokumentum előnézetének indításához nyisson meg egy mellékletet SharePoint-ban.

4. Jelentkezzen be egy másik olyan felhasználói fiókkal, amely hozzáférhet a mellékletekhez, és ellenőrizze, hogy az előnézet a várt módon működik-e.

## <a name="see-also"></a>Lásd még

[Új vagy módosult elemek a Human Resources szolgáltatásban](hr-admin-whats-new.md)</br>
[A Dynamics 365 Human Resources 2019 második kiadási hullámának áttekintése](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Rendelés frissítése](hr-admin-setup-update-process.md)</br>
[Szolgáltatások kezelése](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]