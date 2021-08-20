---
title: Új vagy módosult elemek a Dynamics 365 Human Resources szolgáltatásban (2020. március 24.)
description: Ez a cikk a Microsoft Dynamics 365 Human Resources új vagy módosított szolgáltatásait írja le a 2020. március 24-i kiadásban.
author: andreabichsel
ms.date: 03/24/2020
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
ms.search.validFrom: 2020-03-24
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 64abc088ec1ec9bdf4d6f5ba175e420e495e770535c321b4dd9d266e1864d58e
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6751194"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-march-24-2020"></a>Új vagy módosult elemek a Dynamics 365 Human Resources szolgáltatásban (2020. március 24.)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Ez a cikk a Dynamics 365 Human Resources szolgáltatásban található új vagy módosított funkciókat írja le. A változtatások a 8.1.3073-es buildszámra vonatkoznak. A néhány fejlécben látható, zárójelben lévő számok tájékoztatásként a Lifecycle Services (LCS) támogatási számaira vonatkoznak.

## <a name="human-resources-environment-limits-are-now-based-on-updated-licensing-394595"></a>A Human Resources környezeti korlátai jelenleg frissített licencelésen alapulnak (394595)

A projektenként elérhető környezetek számának korlátozása a Lifecycle Services (LCS) szolgáltatásban megváltozott. Az előző korlát két környezet volt. Az LCS-ben a Human Resources megoldásban a termelési és teszt környezetek létrehozására vonatkozó korlátozás immár a frissített licencelésen alapul. Mostantól a megvásárolt licencek számától függően igény szerinti számban hozhat létre környezeteket egy-egy LCS-projekthez. A 2020. február 1-jén frissített új licencelés lehetővé teszi az ügyfelek számára, hogy további környezeteket vásároljanak. További tájékoztatás a licencelési követelményekről további környezetekhez: [Dynamics 365 licencelési útmutató](https://dynamics.microsoft.com/pricing/#HumanResources).

## <a name="platform-changes"></a>Platformok módosításai

- Teljes oldalas alkalmazások (előzetes) – Ez az előzetes funkció, amely a mentett nézetek funkció engedélyezését megköveteli lehetővé teszi a Power Apps, és a külső féltől származó alkalmazások teljes képernyős élményként történő hozzáadását az irányítópultokhoz.

- Mentett nézetek (előzetes) – Ez az előzetes funkció engedélyezi a mentett nézeteket, amely a személyre szabási alrendszer fontos továbbfejlesztését jelentik. Ez a funkció lehetővé teszi a felhasználóknak, hogy oldalanként több névvel ellátott személyreszabási készletet adjanak meg. A nézeteket a biztonsági szerepkörökbe is közzé lehet tenni.

- Optimalizált „egyike a következőknek” szűrési élmény-ez a funkció elérhetővé teszi az optimalizált „egyike a következőknek” szűrési élményt, amely megkönnyíti több szűrőérték megadását, egy egyszerűbb mechanizmust kínál egy egyes vagy az összes szűrőérték eltávolításához, és egy kompakt és intuitív megjelenítést biztosít a szűrőbeállításokhoz.

- Javasolt mezők – A felhasználóknak gyakran kell mezőket felvenniük egy rácsba vagy egy lapra. Ez nehéz lehet ennyire sok rendelkezésre álló mezővel. Egy nagyméretű listán történő keresés helyett ez a funkció lehetővé teszi a rendszer számára, hogy megjelenítsen egy ajánlott mezőkészletet a hasonló helyzetekben a leggyakrabban használtak alapján.

- Alapértelmezett beragadó műveletek a rácsokban – Ez a funkció biztosítja, hogy a rács alapértelmezett művelete egy rács egy meghatározott oszlopához kapcsolódjon, függetlenül attól, hogy az adott oszlopot áthelyezték vagy elrejtették-e.

## <a name="unable-to-adjust-leave-balance-for-a-plan-with-no-accruals-that-was-created-with-multiple-leave-type-feature-on-419635"></a>Nem lehet módosítani a szabadság egyenlegét olyan terv esetében, amelynek nincs könyvelése, és a „több szabadságtípus” funkcióval hoztak létre (419635)

A módosításnak köszönhetően immár módosíthatja az egyenlegeket azokhoz a szabadságtervekhez, amelyeket a Funkciókezelésben engedélyezett Több szabadságtípus (Előzetes) funkcióval hoztak létre.

## <a name="in-preview"></a>Előnézetben

A következő előzetes funkciók érhetők el 2020. február 3-tól váltak elérhetővé:

- **Szabadság és távollét előzetes funkciói** – További tudnivalók: [Szabadság és távollét előzetes funkciói](hr-leave-and-absence-overview.md?leave-and-absence-preview-features).

- **Juttatáskezelés előzetes funkciói** – További tudnivalók, beleértve az ismert problémákat: [Juttatáskezelés – áttekintése](hr-benefits-management-overview.md).

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

## <a name="new-production-release-cadence"></a>Új termelési kiadás ütemezése

Áprilistól kezdődően a program a Human Resources kiadási ritmusa heti frissítésről a kétheti frissítésre módosul. A biztonságos telepítési gyakorlattal való összehangolás biztosításához és a szolgáltatásban a stabilitás és megbízhatóság magas színvonalának megőrzéséhez a szolgáltatás frissítései minden régióban két hetes ütemezésre váltanak. További tesztek és nyomon követések lesznek bevezetve a sikeres telepítés megerősítéséhez a folyamat minden egyes fázisában. A kiadás ritmusával kapcsolatos további tudnivalókat lásd: [Frissítési folyamat](hr-admin-setup-update-process.md).

## <a name="known-issues"></a>Ismert problémák

## <a name="employment-detail-entity"></a>Foglalkoztatás részletei entitás

A **Foglalkoztatási adatok** entitása frissítve lett a következő mezőkkel: **PayFrequency**, **Foglalkoztatási kategória azonosítója**, **Foglalkoztatási típus**, **EmploymentTypeID** és **Juttatás foglalkoztatási státusza**. Ezeknek a mezőknek a beállítási adatai a Funkciókezelésben engedélyezve vannak a juttatások kezeléséhez. Ne töltse ki vagy frissítse ezeket a mezőket a **Foglalkoztatás részletei** entitásban, mert ez hibákat fog eredményezni az importálás során.

## <a name="see-also"></a>Lásd még

[Új vagy módosult elemek a Human Resources szolgáltatásban](hr-admin-whats-new.md)</br>
[A Dynamics 365 Human Resources 2019 második kiadási hullámának áttekintése](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Rendelés frissítése](hr-admin-setup-update-process.md)</br>
[Szolgáltatások kezelése](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]