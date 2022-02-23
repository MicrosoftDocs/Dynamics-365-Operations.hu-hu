---
title: Új vagy módosult elemek a Dynamics 365 Human Resources szolgáltatásban (2020. február 12.)
description: Ez a cikk a Microsoft Dynamics 365 Human Resources új vagy módosított szolgáltatásait írja le a 2020. február 12-i kiadásban.
author: Darinkramer
manager: AnnBe
ms.date: 02/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2020-02-07
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: b89e022441f69825d9c9c56ecdbca2e09e461b9e
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/17/2020
ms.locfileid: "4526888"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-february-12-2020"></a>Új vagy módosult elemek a Dynamics 365 Human Resources szolgáltatásban (2020. február 12.)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Ez a cikk a Dynamics 365 Human Resources szolgáltatásban található új vagy módosított funkciókat írja le. A változtatások az 8.1.2867-ös buildszámra vonatkoznak. A néhány fejlécben látható, zárójelben lévő számok az Microsoft Dynamics Lifecycle Services (LCS) támogatási számaira vonatkoznak.

## <a name="existing-entities-compfixedempls-and-hcmpersonimage-should-be-accessible-from-odata-414178"></a>A meglévő entitásoknak – CompFixedEmpls és HcmPersonImage – elérhetőnek kell lennie a OData szolgáltatásból (414178).

A heti kiadással a **CompFixedEmpls** és a **HcmPersonImage** az OData szolgáltatáson keresztül nyilványos és elérhető.

## <a name="delete-employment-from-common-data-service-doesnt-work-when-employment-details-arent-active-403193"></a>A foglalkoztatás törlése a Common Data Service szolgáltatásból nem működik, ha a foglalkoztatás adatai nem aktívak (403193)

Ez a változtatás most lehetővé teszi a foglalkoztatás törlését a Common Data Service szolgáltatással, ha nem léteznek aktív foglalkoztatási adatok.

## <a name="course-registration-workflow-changes-status-to-complete-and-errors-after-second-approval-409749"></a>A tanfolyam-regisztrációs munkafolyamat állapota befejeződöttre módosul, és hibát jelez a második jóváhagyás után (409749)

A tanfolyam-regisztráció munkafolyamata frissítve lett több jóváhagyó engedélyezése esetén.

## <a name="in-preview"></a>Előnézetben

A következő előzetes funkciók érhetők el 2020. február 3-tól:

- **Szabadság és távollét előzetes funkciói** – További tudnivalók: [Szabadság és távollét előzetes funkciói](hr-leave-and-absence-overview.md?leave-and-absence-preview-features).

- **Juttatáskezelés előzetes funkciói** – További tudnivalók, beleértve az ismert problémákat: [Juttatáskezelés – áttekintése](hr-benefits-management-overview.md).

## <a name="coming-soon"></a>Hamarosan

### <a name="platform-update-32"></a>32-as platformfrissítés 

A 32-es platformfrissítés hamarosan elérhető lesz. [További tudnivalók a 32-es platformfrissítésről:](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-update-32).

### <a name="updated-common-data-service-solution"></a>Common Data Service megoldás frissítve

Az új Common Data Service megoldás hamarosan a következő változtatásokkal érhető el:

| Leírás | Visszajáró |
| ----------------------------------------- | --- |
| **Feladat/pozíció** entitás módosításai | **Kompenzációs régió** hozzáadása</br>**Pénzügyi dimenziók** hozzáadása |
| **Dolgozó** entitás módosításai | **Névsorrend** hozzáadása</br>**Otthonról dolgozik** hozzáadása</br>**Nyelv** hozzáadása</br>**Szolgálati idő dátuma** hozzáadása</br>**Évforduló dátuma** hozzáadása</br>**Eredeti felvételi dátum** hozzáadása |
| **Foglalkoztatás** entitás módosításai | **Pénzügyi dimenziók** hozzáadása</br>**Felmondás oka** hozzáadása</br>**Megszűnés dátuma** az **Áttérési dátumtól** átnevezve</br>**Próbaidős dátum** hozzáadása |
| **Dolgozó címe** entitás módosításai | **Utca és házszám** hozzáadása</br>**1. címsor**, **2. címsor** és **3. címsor** megjelölve megszűnésre |
| Új változó kompenzációs beállítási entitások | **Változó kompenzációs konstrukció típusa**</br>**Változó kompenzációs konstrukció**</br>**Kilépési szabályok**</br>**Változó kompenzációs konstrukció szintje** |
| Új **Dolgozói naptár – foglalkoztatás** entitás | **Munkanaptár-entitás** hozzáadva |
| Új **Bérlista szerinti beosztás részletei** entitás | **Bérlista szerinti beosztás** részletei |
| Új **Beosztás** entitás | **Beosztás** hozzáadása Az új **Cím** entitást a Human Resources és a Common Data Service közötti szinkronizálási folyamatában fog szerepelni. Kezdetben nem lesz hivatkozva a **Beosztás** vagy a **Feladat** entitásból. |

## <a name="see-also"></a>Lásd még

[Új vagy módosult elemek a Human Resources szolgáltatásban](hr-admin-whats-new.md)</br>
[A Dynamics 365 Human Resources 2019 második kiadási hullámának áttekintése](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Rendelés frissítése](hr-admin-setup-update-process.md)</br>
[Szolgáltatások kezelése](hr-admin-manage-features.md)