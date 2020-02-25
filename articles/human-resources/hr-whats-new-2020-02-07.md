---
title: Új vagy módosult elemek a Dynamics 365 Human Resources szolgáltatásban (2020. február 7.)
description: Ez a cikk a Microsoft Dynamics 365 Human Resources új vagy módosított funkcióit írja le.
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
ms.openlocfilehash: 78043273fb98a12a8d33f7bb94ba8ad2e9fb49fb
ms.sourcegitcommit: 13c4a6f98ccce243d6befde90992aefcf562bdab
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/06/2020
ms.locfileid: "3029957"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-february-7-2020"></a>Új vagy módosult elemek a Dynamics 365 Human Resources szolgáltatásban (2020. február 7.)

Ez a cikk a Dynamics 365 Human Resources szolgáltatásban található új vagy módosított funkciókat írja le. A változtatások az 8.1.2835-ös buildszámra vonatkoznak. A néhány fejlécben látható, zárójelben lévő számok az Microsoft Dynamics Lifecycle Services (LCS) támogatási számaira vonatkoznak.

## <a name="learning-analytics-doesnt-show-the-course-if-the-classroom-is-blank-388289"></a>A tanulási elemzés nem jeleníti meg a tanfolyamot, ha a tanterem üres (388289)

A tanulási elemzés oldala most már megjeleníti a tanfolyamot, ha a tanterem üres.

## <a name="position-lookup-doesnt-take-the-time-zone-into-account-405344"></a>A pozíciók keresése nem veszi figyelembe az időzónát (405344)

A nyitott pozíciók keresése most már figyelembe veszi az időzónát annak ellenőrzésekor, hogy a pozíció nyitott-e.

## <a name="current-balance-analysis-view-doesnt-update-with-the-correct-current-leave-balance-after-submitting-time-off-requests-409756"></a>Az aktuális egyenleg elemzési nézete nem frissül a megfelelő aktuális szabadságegyenleggel a távollétre vonatkozó kérések elküldésekor (409756)

Az aktuális egyenleg most már tartalmazza az elküldött távolléti kéréseket.

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
| Új **Beosztás** entitás | **Beosztás** hozzáadása A rendszer figyelembe veszi az új **Beosztás** entitást a Human Resources és a Common Data Service szinkronizálásának folyamatában, de kezdetben nem lesz hivatkozás a **Feladat pozíciója** vagy a **Feladat** entitásból. |

