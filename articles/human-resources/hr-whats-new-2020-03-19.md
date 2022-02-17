---
title: Új vagy módosult elemek a Dynamics 365 Human Resources szolgáltatásban (2020. március 19.)
description: Ez a cikk a Microsoft Dynamics 365 Human Resources új vagy módosított szolgáltatásait írja le a 2020. március 19-i kiadásban.
author: andreabichsel
ms.date: 03/19/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-03-19
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 0bea115ed111d1309e19631c1cc08fdbab0dca3f
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/31/2022
ms.locfileid: "8062034"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-march-19-2020"></a>Új vagy módosult elemek a Dynamics 365 Human Resources szolgáltatásban (2020. március 19.)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



Ez a cikk a Dynamics 365 Human Resources szolgáltatásban található új vagy módosított funkciókat írja le. A változtatások a 8.1.3014-es buildszámra vonatkoznak. A néhány fejlécben látható, zárójelben lévő számok tájékoztatásként a Lifecycle Services (LCS) támogatási számaira vonatkoznak.

## <a name="human-resources-environment-limits-are-now-based-on-updated-licensing-394595"></a>A Human Resources környezeti korlátai jelenleg frissített licencelésen alapulnak (394595)

A projektenként elérhető környezetek számának korlátozása a Lifecycle Services (LCS) szolgáltatásban megváltozott. Az előző korlát két környezet volt. Az LCS-ben a Human Resources megoldásban a termelési és teszt környezetek létrehozására vonatkozó korlátozás immár a frissített licencelésen alapul. Mostantól a megvásárolt licencek számától függően igény szerinti számban hozhat létre környezeteket egy-egy LCS-projekthez. A 2020. február 1-jén frissített új licencelés lehetővé teszi az ügyfelek számára, hogy további környezeteket vásároljanak. További tájékoztatás a licencelési követelményekről további környezetekhez: [Dynamics 365 licencelési útmutató](https://dynamics.microsoft.com/pricing/#HumanResources).

## <a name="provide-cross-company-viewing-of-compensation-data-for-employees-and-managers-403904"></a>A kompenzációs adatok vállalatszintű megtekintése az alkalmazottak és a vezetők számára (403904)

Ezt a funkciót a **Funkció kezelés** munkaterületen kapcsolhatja be. A további részletekért lásd: [Előzetes funkciók engedélyezése vagy letiltása](hr-admin-manage-features.md#enable-or-disable-preview-features).

Ha engedélyezi ezt a funkciót, a vezetők láthatják a közvetlen és közvetett beosztottak kompenzációját anélkül, hogy be kellene jelentkezniük a munkáltató vállalatba. A teljes kompenzációs előzmények elérhetők minden olyan bejelentkezett vállalatnál, amelyhez a vezető hozzáférhet. További tájékoztatás: [Alkalmazotti és vezetői önkiszolgálás áttekintése](hr-employee-manager-self-service-overview.md).

## <a name="enable-global-address-book-merge-functionality-427189"></a>Globális címjegyzék egyesítési funkcióinak engedélyezése (427189)

Immár egyesíthet dupla címjegyzék-bejegyzéseket, ha kiválasztja a dupla bejegyzéseket és az **Egyesítés** lehetőséget választja a **Globális címjegyzék** oldalon.

## <a name="unable-to-adjust-leave-balance-for-a-plan-with-no-accruals-that-was-created-with-the-multiple-leave-type-feature-on-419635"></a>Nem lehet módosítani a szabadság egyenlegét olyan terv esetében, amelynek nincs könyvelése, és a Több szabadságtípus funkcióval hoztak létre (419635)

Immár módosíthatja az egyenlegeket azokhoz a szabadságtervekhez, amelyeket a Funkciókezelésben engedélyezett **Több szabadságtípus** előzetes funkcióval hoztak létre.

## <a name="primary-position-field-in-the-workerpositionassignmententity-when-an-employee-is-terminated-420774"></a>Elsődleges beosztás mező a WorkerPositionAssignmentEntity entitásban, amikor egy alkalmazott munkaviszonya megszűnik (420774)

A megszüntetett munkaviszonnyal rendelkező alkalmazottak esetében a munkaviszony megszüntetésekor aktív elsődleges pozíció jelenik meg az entitásban. Az integrációk esetében már nem jön létre ismétlődő rekord az alkalmazott dolgozói pozíció-hozzárendeléséhez. 

## <a name="dataverse-solution-is-now-available-with-the-following-changes"></a>A Dataverse megoldás már elérhető a következő változtatásokkal:

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
| Új **Beosztás** entitás | <ul><li>**Beosztás** hozzáadva</li></ul>Az új **Beosztás** entitást a Dataverse tartalmazza, de jelenleg a **Munkakör** vagy **Munka** entitások nem hivatkoznak rá. |

> [!NOTE]
> A beosztások és a foglalkoztatás pénzügyi dimenziói egyirányú integrációt biztosítanak a Human Resources és a Dataverse közötti frissítésekhez. A pénzügyi dimenziók frissítései jelenleg nem szinkronizálnak a Dataverse és a Human Resources között.

Az elkövetkezendő hetekben ezek az entitásmódosítások minden környezetben elérhetők lesznek. A legújabb Dataverse megoldás manuális telepítése a Human Resourcesbe:

1.  Ugorjon a [Power Platform Adminisztrációs központba](https://admin.powerplatform.microsoft.com).

2.  Válassza a **Környezetek** lehetőséget.

3.  Keresse meg a frissíteni kívánt környezetet. A környezetnek meg kell egyeznie a **Környezet nevével** a **Common Data Service információk** szakaszban a Human Resources **Névjegy** képernyőjén.

4.  A környezet adatainak megtekintéséhez válassza ki a környezetet.

5.  Válassza ki a **Megoldások kezelése** elemet a felső műveletsávból. A rendszer egy új böngészőablakot nyit meg, és megnyitja a **Dynamics 365 felügyeleti központot** a környezete kontextusában.

6.  A **Megoldás** listán válassza a **Dynamics 365 Human Resources horgony** elemet.

7.  Válassza a **Frissítés** parancsot a legújabb megoldás alkalmazásához.

## <a name="sharepoint-preview-doesnt-work-in-some-environments"></a>SharePoint előnézet nem használható bizonyos környezetekben

Ha egy, a SharePoint-ban tárolt dokumentum előnézete nem működik, próbálja meg a következő eljárást:

1. Ellenőrizze, hogy az Adminisztrátor felhasználói fiók rendelkezik-e a felhasználói rekordhoz társított e-mail-címmel. Ezt az információt a **Felhasználó** oldalon lehet megtekinteni. Ha nincs beállítva e-mail-cím, akkor az e-mail-címet és a szolgáltatót hozzá kell adnia az OData Excel-bővítménnyel. Alapértelmezés szerint az e-mail-cím nem szerepel az Excel-tervben. Szerkesztenie kell az Excel-tervet, minden mezőt fel kell venni, alkalmazni kell, majd frissíteni kell. Miután befejezte ezeket a lépéseket, frissítheti az adminisztrátori fiókot.

2. Miután az Adminisztrátor fiókhoz hozzá van rendelve egy e-mail-fiók, az Adminisztrátori hitelesítő adatokkal jelentkezzen be a Human Resources szolgáltatásokba.

3. A dokumentum előnézetének indításához nyisson meg egy mellékletet SharePoint-ban.

4. Jelentkezzen be egy másik olyan felhasználói fiókkal, amely hozzáférhet a mellékletekhez, és ellenőrizze, hogy az előnézet a várt módon működik-e.

## <a name="coming-soon"></a>Hamarosan

### <a name="platform-update-33"></a>Platform update 33

- Teljes oldalas alkalmazások (előzetes) – Ez az előzetes funkció, amely a mentett nézetek funkció engedélyezését megköveteli lehetővé teszi a Power Apps, és a külső féltől származó alkalmazások teljes képernyős élményként történő hozzáadását az irányítópultokhoz.

- Mentett nézetek (előzetes) – Ez az előzetes funkció engedélyezi a mentett nézeteket, amely a személyre szabási alrendszer fontos továbbfejlesztését jelentik. Ez a funkció lehetővé teszi a felhasználóknak, hogy oldalanként több névvel ellátott személyreszabási készletet adjanak meg. A nézeteket a biztonsági szerepkörökbe is közzé lehet tenni.

- Optimalizált „egyike a következőknek” szűrési élmény-ez a funkció elérhetővé teszi az optimalizált „egyike a következőknek” szűrési élményt, amely megkönnyíti több szűrőérték megadását, egy egyszerűbb mechanizmust kínál egy egyes vagy az összes szűrőérték eltávolításához, és egy kompakt és intuitív megjelenítést biztosít a szűrőbeállításokhoz.

- Javasolt mezők – A felhasználóknak gyakran kell mezőket felvenniük egy rácsba vagy egy lapra. Ez nehéz lehet ennyire sok rendelkezésre álló mezővel. Egy nagyméretű listán történő keresés helyett ez a funkció lehetővé teszi a rendszer számára, hogy megjelenítsen egy ajánlott mezőkészletet a hasonló helyzetekben a leggyakrabban használtak alapján.

- Alapértelmezett beragadó műveletek a rácsokban – Ez a funkció biztosítja, hogy a rács alapértelmezett művelete egy rács egy meghatározott oszlopához kapcsolódjon, függetlenül attól, hogy az adott oszlopot áthelyezték vagy elrejtették-e.

## <a name="new-production-release-cadence"></a>Új termelési kiadás ütemezése

Áprilistól kezdődően a program a Human Resources kiadási ritmusa heti frissítésről a kétheti frissítésre módosul. Ez biztosítja a biztonságos telepítési gyakorlatoknak való megfelelést, valamint a szolgáltatás magas szintű stabilitásának és megbízhatóságának megtartását. További teszteket és nyomon követéseket vezetünk be a sikeres telepítés megerősítéséhez a folyamat minden egyes fázisában. A kiadás ritmusával kapcsolatos további tudnivalókat lásd: [Frissítési folyamat](hr-admin-setup-update-process.md).

## <a name="in-preview"></a>Előnézetben

A következő előzetes funkciók érhetők el 2020. február 3-tól:

- **Szabadság és távollét előzetes funkciói** – További tudnivalók: [Szabadság és távollét előzetes funkciói](hr-leave-and-absence-overview.md?leave-and-absence-preview-features).

- **Juttatáskezelés előzetes funkciói** – További tudnivalók, beleértve az ismert problémákat: [Juttatáskezelés – áttekintése](hr-benefits-management-overview.md).

## <a name="see-also"></a>Lásd még

[Új vagy módosult elemek a Human Resources szolgáltatásban](hr-admin-whats-new.md)</br>
[A Dynamics 365 Human Resources 2019 második kiadási hullámának áttekintése](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Rendelés frissítése](hr-admin-setup-update-process.md)</br>
[Szolgáltatások kezelése](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]