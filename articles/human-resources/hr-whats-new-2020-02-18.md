---
title: Új vagy módosult elemek a Dynamics 365 Human Resources szolgáltatásban (2020. február 18.)
description: Ez a cikk a Microsoft Dynamics 365 Human Resources új vagy módosított szolgáltatásait írja le a 2020. február 18-i kiadásban.
author: andreabichsel
ms.date: 02/18/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-02-18
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 6c28d0dc76195cc0aedc132f348a229af0421c43
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5790428"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-february-18-2020"></a>Új vagy módosult elemek a Dynamics 365 Human Resources szolgáltatásban (2020. február 18.)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Ez a cikk a Dynamics 365 Human Resources szolgáltatásban található új vagy módosított funkciókat írja le. A változtatások a 8.1.2903-es buildszámra vonatkoznak. A néhány fejlécben látható, zárójelben lévő számok az LCS támogatási számaira vonatkoznak referenciaképpen.

## <a name="platform-update-32"></a>32-as platformfrissítés 

A 32-es platform-frissítés már elérhető. A további tudnivalókat lásd: [Újdonságok és módosítások a Finance and Operations-alkalmazások 32-as platformfrissítéséhez (2020. február)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-update-32).

## <a name="search-values-are-remembered-when-changing-view-options-in-streamlined-employee-form-383833"></a>A program a keresési értékeket az egyszerűsített alkalmazotti űrlap nézetbeállításainak módosításakor emlékszik (383833).

Az új **Dolgozó** képernyő most emlékszik a keresési értékekre, amikor megváltoztatja a nézet beállításait, és alkalmazza a változtatásokat.

## <a name="compensation-management-summary-tiles-in-preview-feature-redirect-to-wrong-form-401861"></a>Kompenzációkezelés összesítése csempék az előzetes funkcióban a rossz űrlapra irányítanak (401861)

A fix és változó kompenzációs kezelési csempék most a megfelelő rekordokat jelenítik meg az új **Dolgozó** képernyőn. Csak az egyszerűsített dolgozói űrlap előzetes funkciójára vonatkozik. Ezt az előnézeti funkciót engedélyezheti a **szolgáltatások kezelése** modulban. További információért lásd: [Funkciók kezelése](hr-admin-manage-features.md).

## <a name="empty-status-field-for-some-leave-request-records-in-dataverse-414915"></a>Üres állapotmező látható a Dataverse szolgáltatás néhány távollétkérelmi rekordjánál (414915)

A módosítással javul a Dataverse egyik hibája, amikor a távollétkérelem **Állapot** mezőjének beállítása **Felülvizsgálat**. Dataverse most az állapotot tükrözi.

## <a name="skill-gap-analysis-only-possible-for-assigned-job-411390"></a>A szakértelem hiányelemzése csak hozzárendelt feladatnál lehetséges (411390)

Most már végrehajthatja a Human Resources szolgáltatásban meghatározott bármely feladat szakértelmi hiányelemzését.

## <a name="system-currency-doesnt-sync-from-dataverse-to-human-resources-in-new-environments-418011"></a>A rendszerpénznem nem szinkronizál a Dataverse szolgáltatásból a Human Resources szolgáltatásba új környezetekben (418011)

A rendszerpénznem most már szinkronizálhat a Dataverse szolgáltatásból a Human Resources szolgáltatásba.

## <a name="in-preview"></a>Előnézetben

- [Szabadság és távollét előzetes funkciói](hr-leave-and-absence-overview.md?leave-and-absence-preview-features)

- [Juttatáskezelés előzetes funkciói](hr-benefits-management-overview.md)

## <a name="coming-soon"></a>Hamarosan

### <a name="updated-dataverse-solution"></a>Dataverse megoldás frissítve

Az új Dataverse megoldás hamarosan a következő változtatásokkal érhető el:

| Leírás | Visszajáró |
| ----------------------------------------- | --- |
| **Feladat/pozíció** entitás módosításai | **Kompenzációs régió** hozzáadása</br>**Pénzügyi dimenziók** hozzáadása |
| **Dolgozó** entitás módosításai | **Névsorrend** hozzáadása</br>**Otthonról dolgozik** hozzáadása</br>**Nyelv** hozzáadása</br>**Szolgálati idő dátuma** hozzáadása</br>**Évforduló dátuma** hozzáadása</br>**Eredeti felvételi dátum** hozzáadása |
| **Foglalkoztatás** entitás módosításai | **Pénzügyi dimenziók** hozzáadása</br>**Felmondás oka** hozzáadása</br>**Megszűnés dátuma** az **Áttérési dátumtól** átnevezve</br>**Próbaidős dátum** hozzáadása |
| **Dolgozó címe** entitás módosításai | **Utca és házszám** hozzáadása</br>**1. címsor**, **2. címsor** és **3. címsor** megjelölve megszűnésre |
| Új változó kompenzációs beállítási entitások | **Változó kompenzációs konstrukció típusa**</br>**Változó kompenzációs konstrukció**</br>**Kilépési szabályok**</br>**Változó kompenzációs konstrukció szintje** |
| Új **Dolgozói naptár – foglalkoztatás** entitás | **Munkanaptár-entitás** hozzáadva |
| Új **Bérlista szerinti beosztás részletei** entitás | **Bérlista szerinti beosztás** részletei |
| Új **Beosztás** entitás | **Beosztás** hozzáadása Az új **Cím** entitást a Human Resources és a Dataverse közötti szinkronizálási folyamatában fog szerepelni. Kezdetben nem lesz hivatkozva a **Beosztás** vagy a **Feladat** entitásból. |

## <a name="see-also"></a>Lásd még

[Új vagy módosult elemek a Human Resources szolgáltatásban](hr-admin-whats-new.md)</br>
[A Dynamics 365 Human Resources 2019 második kiadási hullámának áttekintése](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Rendelés frissítése](hr-admin-setup-update-process.md)</br>
[Szolgáltatások kezelése](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]