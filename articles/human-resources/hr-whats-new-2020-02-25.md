---
title: Új vagy módosult elemek a Dynamics 365 Human Resources szolgáltatásban (2020. február 25.)
description: Ez a cikk a Microsoft Dynamics 365 Human Resources új vagy módosított szolgáltatásait írja le a 2020. február 25-i kiadásban.
author: andreabichsel
manager: tfehr
ms.date: 02/25/2020
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
ms.author: jaredha
ms.search.validFrom: 2020-02-25
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 4faecb83518f3ef8af825872abc2a6ffb94162fc
ms.sourcegitcommit: f8bac7ca2803913fd236adbc3806259a17a110f4
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/06/2021
ms.locfileid: "5128022"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-february-25-2020"></a>Új vagy módosult elemek a Dynamics 365 Human Resources szolgáltatásban (2020. február 25.)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Ez a cikk a Dynamics 365 Human Resources szolgáltatásban található új vagy módosított funkciókat írja le. A változtatások a 8.1.2927-es buildszámra vonatkoznak. A néhány fejlécben látható, zárójelben lévő számok az LCS támogatási számaira vonatkoznak referenciaképpen.

## <a name="enable-case-management-navigation-and-data-management-framework-dmf-entity-414754"></a>Az Esetkezelési navigáció és az adatkezelési keretrendszer (DMF) entitás engedélyezése (414754)

Ez az előzetes funkció további navigálást tesz lehetővé az esetkezelési esetekhez. Ezt az előnézeti funkciót engedélyezheti a **Szolgáltatások kezelése** munkaterületen. Ezek a menüelemek a **Megfelelés** munkaterületen jelennek meg a Dynamics 365 Human Resources alkalmazásban. Ezzel a módosítással a Humán erőforrások hozzáférhet:

- Az összes eset
- Saját esetek
- Saját nyitott esetek
- Saját késedelmes esetek
- Munkafolyamat révén hozzám rendelt esetek

Ezekkel az új esetnézetekkel együtt az **Eset részletei** DMF entitás is elérhetővé vált.

## <a name="enable-relationship-definitions-in-global-address-bbook-414762"></a>Kapcsolati definíciók engedélyezése a globális címtárban (414762)

A kapcsolatok most engedélyezve vannak a globális címjegyzékben. Az eheti kiadás előtt a **Kapcsolat** adatterület minden rendszer által definiált kapcsolatot megjelenített. Immár a kapcsolatokat a globális címjegyzék lapon definiálhatja.

## <a name="a-position-can-be-removed-when-active-compensation-records-exist-for-the-position-414568"></a>A beosztás eltávolítható, ha a beosztáshoz aktív kompenzációs rekordok léteznek (414568)

Ezzel a módosítással figyelmeztetés jelenik meg, amikor egy beosztást megkísérel törölni, és egy dolgozónak aktív kompenzációs rekordja van ehhez a beosztáshoz. Ha ez történik, akkor a beosztás eltávolítása előtt frissíteni kell az alkalmazott fix kompenzációs rekordját.

## <a name="performance-review-workflow-occasionally-adds-sign-offs-from-people-who-are-not-part-of-the-process-414171"></a>A teljesítmény-felülvizsgálati munkafolyamat időnként hozzáadja nyugtázási műveleteket olyan személyektől, akik nem részei a folyamatnak (414171)

Ez a módosítás javítja azt a hibát, amelynél a rendszer további jóváhagyási résztvevőket ad hozzá a teljesítmény-ellenőrzéshez.

## <a name="worker-position-assignment-not-created-in-dataverse-when-selected-on-the-new-worker-dialog-413479"></a>A dolgozói beosztás társítása nem lett létrehozva a Dataverse alkalmazásban, amikor ki lett választva az új dolgozó párbeszédpanelén (413479)

Ez a módosítás javítja azt a hibát, amikor új dolgozót vesz fel, és az új belépőt egy beosztáshoz rendeli hozzá az **Új dolgozó** párbeszédpanelen. Immár beosztás-hozzárendelés tükröződik a Dataverse szolgáltatásban is.

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

Az elkövetkezendő hetekben ezek az entitásmódosítások minden környezetben elérhetők lesznek. A legújabb Dataverse megoldás manuális telepítése a Human Resourcesbe:

1.  Ugorjon a [Power Platform Adminisztrációs központba](https://admin.powerplatform.microsoft.com).

2.  Válassza a **Környezetek** lehetőséget.

3.  Keresse meg a frissíteni kívánt környezetet. Ennek meg kell egyeznie a **Környezet nevével** a **Common Data Service információk** szakaszban a Human Resources **Névjegy** képernyőjén.

4.  A környezet adatainak megtekintéséhez válassza ki a környezetet.

5.  Válassza ki a **Megoldások kezelése** elemet a felső műveletsávból. A rendszer egy új böngészőablakot nyit meg, és megnyitja a **Dynamics 365 felügyeleti központot** a környezete kontextusában.

6.  A **Megoldás** listán válassza a **Dynamics 365 Human Resources horgony** elemet.

7.  Válassza a **Frissítés** parancsot a legújabb megoldás alkalmazásához.

## <a name="in-preview"></a>Előnézetben

A következő előzetes funkciók érhetők el 2020. február 3-tól váltak elérhetővé:

- **Szabadság és távollét előzetes funkciói** – További tudnivalók: [Szabadság és távollét előzetes funkciói](hr-leave-and-absence-overview.md?leave-and-absence-preview-features).

- **Juttatáskezelés előzetes funkciói** – További tudnivalók, beleértve az ismert problémákat: [Juttatáskezelés – áttekintése](hr-benefits-management-overview.md).

## <a name="see-also"></a>Lásd még

[Új vagy módosult elemek a Human Resources szolgáltatásban](hr-admin-whats-new.md)</br>
[A Dynamics 365 Human Resources 2019 második kiadási hullámának áttekintése](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Rendelés frissítése](hr-admin-setup-update-process.md)</br>
[Szolgáltatások kezelése](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]