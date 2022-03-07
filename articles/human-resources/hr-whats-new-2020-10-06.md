---
title: Új vagy módosult elemek a Dynamics 365 Human Resources szolgáltatásban (2020. október 6.)
description: Ez a témakör a Microsoft Dynamics 365 Human Resources új vagy módosított szolgáltatásait írja le a 2020. október 6-i kiadásban.
author: jcart1106
ms.date: 10/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2020-10-06
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: ac64218e48d2713b91af1541f94083aef3f815a2
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/31/2022
ms.locfileid: "8062979"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-october-6-2020"></a>Új vagy módosult elemek a Dynamics 365 Human Resources szolgáltatásban (2020. október 6.)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



Ez a témakör a Dynamics 365 Human Resources új, módosított vagy nemsokára várható szolgáltatásait írja le. A frissítési folyamattal és ütemezéssel kapcsolatos további tudnivalókért lásd: [Frissítési folyamat](hr-admin-setup-update-process.md).

További tájékoztatás az új szolgáltatásokról és a nyilvános megjelenési dátumokról: [A Dynamics 365 Human Resources 2020. második kiadási hullámának áttekintése](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>Ebben a verzióban

Ez a kiadás az alábbi új funkciókat és hibajavításokat tartalmazza. A változtatások a 8.1.3636-es buildszámra vonatkoznak.

### <a name="new-features"></a>Új funkciók

Az alábbi funkció általában a következő verzióval lesz elérhető.

| Funkció | Kiadási terv | Dokumentáció |
| --- | --- | --- |
| További betekintés a szabadságnaptárakba | [További betekintés biztosítása a szabadságnaptár nézetekbe](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/provide-additional-insight-leave-calendar-views) | [Csapat- és vállalati naptár megtekintése](hr-employee-self-service-calendar.md) |

### <a name="bug-fixes"></a>Hibajavítások

Ez a kiadás az alábbi hibajavításokat tartalmazza.

>[!NOTE]
> Célunk, hogy a lehető leghamarabb eljuttassuk Önhöz ezeket az információkat. Előfordulhat, hogy a jelen témakör frissítései olyan hibajavításokat is tartalmazhatnak, amelyek annak első közzététele után léptek életbe.

| Kiadás száma | Kiadás | Leírás |
| --- | --- | --- |
| 448806 | Az **Alapértelmezett azonosítótípus** a HCM-paraméterekbe **RecID** típusként exportálódik | A Human Resources paraméterek entitás ezne módosítása hozzáad egy újabb oszlopot, amely az **Alapértelmezett azonosítótípust** jeleníti meg. |
| 492923 | A feladathoz kapcsolódó felvételeket a rendszer nem menti a Lifecycle Services (LCS) szolgáltatásba | A feladatrögzítések most már menthetők az LCS rendszerben. |
| 429950 | A rögzített kompenzáció helytelenül jár le a beosztás módosításakor | Amikor egy dolgozó beosztását a **Dolgozó áthelyezése** lapon módosítják, egy nappal a beosztás vége előttre be kell állítani a legutolsó kompenzációs dátumot. A kompenzáció záró dátuma most már megegyezik a beosztás záró dátumával. |
| 467214 | A **Bérezéses elemzés** lehetőség csak akkor jelenik meg, ha a **fizetési díjalap átalakításának neve** beállítása **Évente** | A bérezéses fizetési díjalapok, amelyek neve nem **Évente**, nem szerepelnek a kompenzációs elemzésekben. Ezzel a frissítéssel a kompenzációs elemzések minden fizetési díjalap átalakítását figyelembe veszik. A jelentések **Órabér** vagy **Bérezéses** lebontásban történő futtatásakor a **Fizetés** szűrő tartalmaz minden olyan fizetési díjalapot, amely az órabértől eltérő időszakot használ. Az **Órabér** szűrőben csak az **óránkénti** fizetési díjalapok szerepelnek. |
| 482464 | Az **Értékelések** megtekintésekor a **Részletek** nézet nem változik rácsnézetre a szűrő alkalmazása után | A szűrő alkalmazása után az értékelésrács a várt módon jelenik meg. |
| 483184 | A Human Resources nem hozza létre az eltávozást ha a **Szabadság regisztrációja** rekordban **Szintalapként** a **Módosított kezdési időpontot** választja |A **Módosított kezdési időpont** mezőt a program kitölti és felhasználja a szabadságok létrehozásakor.  |
| 509731 | A jövőben elbocsátott dolgozók szabadságkérelmei hibát okoznak, ha a megszűnés dátuma utánra kérnek szabadságot | A sazbadságkérelmeket most már be lehet nyújtani olyan alkalmazottakhoz, akik rendelkeznek jövőbeli megszűnési dátummal, feltéve, hogy a kérelem a felmondási dátum előttre szól. |
| 510716 | A kompenzációs elemzések a férfi és női alkalmazottakat egyaránt tartalmazzák a **Férfiak átlagos óránkénti fizetése** mezőben | A kompenzációs elemzések esetében a **Férfiak átlagos óránkénti fizetése** a **Jövedelmek demográfiai elemzése** részben a női átlagos fizetést is tartalmazza. Most már csak a férfiak fizetését tartalmazza. |
| 511348 | Az önkiszolgáló juttatásfizetés kizárólag a mai naptól a juttatási időszak végéig érvényes juttatási terveket jeleníti meg | A lejárt juttatási tervek megjelennek az alkalmazottak előtt a **Juttatások regisztrálása** oldalon. Ez a hibajavítás eltávolítja ezeket a terveket. |
| 512706 | Az alábbi mezők csak olvashatók:<ul><li>BenefitPlanEmployeeEntity</li><li>EnrollmentConfirmed</li><li>EnrollmentConfirmedBy</li><li>EnrollmentConfirmedDateTime | A dimenziók részleteinek **Hozzáadás** és **Eltávolítás** gombjait a rendszer a művelet befejezése után hibásan engedélyezte. A **Beosztás műveleti – részletek** lap ezen frissítésével a művelet befejezése után a mezők többé nem szerkeszthetők. |

## <a name="in-preview"></a>Előnézetben

Az alábbi új funkciók előzetes verzióban érhetők el. A funkciók be- vagy kikapcsolásával kapcsolatos további információkért lásd a [Szolgáltatások kezelése](hr-admin-manage-features.md) című témakört.

| Funkció | Kiadási terv | Dokumentáció |
| --- | --- | --- |
| Human Resources alkalmazás a Microsoft Teams alkalmazásban | [Alkalmazott szabadsági és távolléti élménye a Microsoft Teams rendszerben](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) | [Human Resources alkalmazás a Teamsben](./hr-admin-teams-leave-app.md)<br>[Szabadságkérelmek kezelése a Teamsben](hr-teams-leave-app.md) |
| Továbbfejlesztett munkafolyamat-kérelmek és -jóváhagyások | [Szervezeti és személyzeti felügyeleti munkafolyamat-tapasztalatok továbbfejlesztései](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/organization-personnel-management-workflow-experience-enhancements) | [Konfigurációs beállítás a hozzám rendelt munkaelemek lista pozicionálásához](./hr-whats-new-2020-09-03.md#configuration-option-to-position-work-items-assigned-to-me-list-477004) |
| A Dataverse for Human Resources számára elérhető virtuális entitások | [Alapvető Dynamics 365 Human Resources-adatok kibontása a Dataverse szolgáltatásban](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/expand-dynamics-365-human-resources-core-data-common-data-service) | [Dataverse-virtuális entitások konfigurálása](hr-admin-integration-common-data-service-virtual-entities.md) |

## <a name="coming-soon"></a>Hamarosan

A következő új funkciókat jövőbeli kiadásokra ütemeztük:

- **Ellenőrzőlista entitások a Dataverse szolgáltatásban**: az Előkészítés, Felszámolás, Áthelyezések és Üzleti folyamatok hamarosan elérhetők lesznek a Dataverse alkalmazásban.

- **Juttatáskezelési okkódok**: A juttatáskezelés okkódjai hamarosan kombinálva lesznek a Human Resources meglévő okkódjaival. Ha a Juttatások kezelése modulban több, mint 15 karakterből álló okkódok szerepelnek, akkor az Juttatások kezelése **Okkódok** űrlapján az okkódot maximum 15 karakter hosszúra kell módosítania. Miután frissítette a nevet, az okkód a Személyzetkezelés modul meglévő okkódok képernyőjén fog megjelenni. Ez a változtatás a jövőben elérhető lesz, és nem fogja befolyásolni a meglévő funkciókat.

- **Egyéni hivatkozások a vezetői önkiszolgáló rendszerben**: a vezetők támogatásának céljára a vezetői önkiszolgáló szolgáltatás képességei bővülnek. Lehetővé tesszük, hogy egyéni hivatkozásokat adjon hozzá a **Saját csoport** lapon. Ez a funkció hasonló az Alkalmazotti önkiszolgáló **Saját adatok** lapján található egyéni hivatkozások szolgáltatáshoz. További tájékoztatás: [Egyéni hivatkozások a vezetői önkiszolgáló szolgáltatásban](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/custom-links-manager-self-service).

A tervezett szolgáltatások és az ütemezett kiadások teljes listája az alábbi témakörben olvasható: [A Dynamics 365 Human Resources 2019. második kiadási hullámának áttekintése](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/).

## <a name="additional-resources"></a>További erőforrások

[Újdonságok vagy változások a Human Resources szolgáltatásban](hr-admin-whats-new.md)</br>
[A Dynamics 365 Human Resources 2020. második kiadási hullámának áttekintése](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/)</br>
[Rendelés frissítése](hr-admin-setup-update-process.md)</br>
[Szolgáltatások kezelése](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]