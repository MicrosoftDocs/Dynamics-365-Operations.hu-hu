---
title: Új vagy módosult elemek a Dynamics 365 Human Resources szolgáltatásban (2020. március 10.)
description: Ez a cikk a Microsoft Dynamics 365 Human Resources új vagy módosított funkcióit írja le.
author: Darinkramer
manager: AnnBe
ms.date: 03/10/2020
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
ms.search.validFrom: 2020-03-10
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 1843095c41428d377341154c9f2140085831e770
ms.sourcegitcommit: bd9ff0d28718d535356ffbe1cffaaf60310dd430
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/13/2020
ms.locfileid: "3555254"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-march-10-2020"></a>Új vagy módosult elemek a Dynamics 365 Human Resources szolgáltatásban (2020. március 10.)

Ez a cikk a Dynamics 365 Human Resources szolgáltatásban található új vagy módosított funkciókat írja le. A változtatások a 8.1.2985-es buildszámra vonatkoznak. A néhány fejlécben látható, zárójelben lévő számok az LCS támogatási számaira vonatkoznak referenciaképpen.

## <a name="cant-access-skill-gap-analysis-report-394460"></a>Nem érhető el a hiányelemzés jelentése (394460)

A Dynamics 365 Human Resources nem támogatja ezt a jelentést. Az SSRS-jelentés kinyomtatásához tartozó menüelem el lett távolítva.

## <a name="incorrect-message-accessing-the-getting-started-page-417950"></a>Nem megfelelő üzenet az Első lépések lap eléréséhez (417950)

Ezzel a módosítással a biztonság elrejti ezt a menüelemet, ha nincs hozzáférése az űrlaphoz.

## <a name="streamlined-task-maintenance-for-employees-380538"></a>Az alkalmazottak racionalizált karbantartása (380538)

A dolgozói feladatok karbantartása képernyő felsorolja az alkalmazottak összes feladatát a felvételi, kiléptetési, áthelyezési és üzleti folyamatokra kiterjedve. Törölheti, ismételten hozzárendelheti vagy frissítheti a feladatok állapotát.

Példa: Benjamin Martin a juttatások adminisztrátora. Az alkalmazotti beléptetés során Benjamin számára feladatok jönnek létre, hogy az új alkalmazott juttatásának kiválasztását vizsgálja felül. Benjaminnak vannak múltbéli befejezett feladatait és jövőbeni elvégzendő feladatai. Benjamin úgy dönt, hogy elhagyja a vállalatot, így a feladatait vagy újra hozzá kell rendelni, vagy el kell távolítani. A feladat karbantartása képernyő (a **Dolgozó** képernyő művelet ablaktábláján) lehetővé teszi Benjamin összes feladatának újbóli hozzárendelését egy másik dolgozóhoz, vagy azok eltávolítását.  

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
| Új **Beosztás** entitás | <ul><li>**Beosztás** hozzáadva</li></ul> Az új **Beosztás** entitást a Common Data Service tartalmazza, de jelenleg a **Munkakör** vagy **Munka** entitások nem hivatkoznak rá. |

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

A következő előzetes funkciók érhetők el 2020. február 3-tól:

- **Szabadság és távollét előzetes funkciói** – További tudnivalók: [Szabadság és távollét előzetes funkciói](hr-leave-and-absence-overview.md?leave-and-absence-preview-features).

- **Juttatáskezelés előzetes funkciói** – További tudnivalók, beleértve az ismert problémákat: [Juttatáskezelés – áttekintése](hr-benefits-management-overview.md).

## <a name="coming-soon"></a>Hamarosan

### <a name="platform-update-33"></a>Platform update 33

- Teljes oldalas alkalmazások (előzetes) – Ez az előzetes funkció, amely a mentett nézetek funkció engedélyezését megköveteli lehetővé teszi a Power Apps, és a külső féltől származó alkalmazások teljes képernyős élményként történő hozzáadását az irányítópultokhoz.

- Mentett nézetek (előzetes) – Ez az előzetes funkció engedélyezi a mentett nézeteket, amely a személyre szabási alrendszer fontos továbbfejlesztése. Ez a funkció lehetővé teszi a felhasználóknak, hogy oldalanként több névvel ellátott személyreszabási készletet adjanak meg. A nézeteket a biztonsági szerepkörökbe is közzé lehet tenni.

- Optimalizált „egyike a következőknek” szűrési élmény-ez a funkció elérhetővé teszi az optimalizált „egyike a következőknek” szűrési élményt, amely megkönnyíti több szűrőérték megadását, egy egyszerűbb mechanizmust kínál egy egyes vagy az összes szűrőérték eltávolításához, és egy kompakt és intuitív megjelenítést biztosít a szűrőbeállításokhoz.

- Javasolt mezők – A felhasználóknak gyakran kell mezőket felvenniük egy rácsba vagy egy lapra. Ez nehéz lehet ennyire sok rendelkezésre álló mezővel. Egy nagyméretű listán történő keresés helyett ez a funkció lehetővé teszi a rendszer számára, hogy megjelenítsen egy ajánlott mezőkészletet a hasonló helyzetekben a leggyakrabban használtak alapján.

- Alapértelmezett beragadó műveletek a rácsokban – Ez a funkció biztosítja, hogy a rács alapértelmezett művelete egy rács egy meghatározott oszlopához kapcsolódjon, függetlenül attól, hogy az adott oszlopot áthelyezték vagy elrejtették-e.

## <a name="see-also"></a>Lásd még

[Új vagy módosult elemek a Human Resources szolgáltatásban](hr-admin-whats-new.md)</br>
[A Dynamics 365 Human Resources 2019 második kiadási hullámának áttekintése](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Rendelés frissítése](hr-admin-setup-update-process.md)</br>
[Szolgáltatások kezelése](hr-admin-manage-features.md)