---
title: Új vagy módosult elemek a Dynamics 365 Human Resources szolgáltatásban (2021. január 28.)
description: Ez a témakör olyan funkciókat ismertet, amelyek vagy újak, vagy módosulnak a Microsoftban Dynamics 365 Human Resources 2021. január 28-án.
author: marcelbf
ms.date: 01/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-01-28
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 46bbda21c3eb2b32030b93afc2a40785c22b124e
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8909759"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-january-28-2021"></a>Új vagy módosult elemek a Dynamics 365 Human Resources szolgáltatásban (2021. január 28.)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Ez a témakör az új, módosított vagy hamarosan érkező funkciókat írja le Dynamics 365 Human Resources.

A frissítési folyamattal és ütemezéssel kapcsolatos további tudnivalókért lásd: [Frissítési folyamat](hr-admin-setup-update-process.md).

További tájékoztatás az új szolgáltatásokról és a nyilvános megjelenési dátumokról: [A Dynamics 365 Human Resources 2021. második kiadási hullámának áttekintése](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>Ebben a verzióban

Ez a kiadás az alábbi új funkciókat és hibajavításokat tartalmazza. A változtatások a 8.1.3906-es buildszámra vonatkoznak.

### <a name="new-features"></a>Új funkciók

Az alábbi funkciók általában a következő verzióval lesznek elérhetők.

| Funkció | Kiadási terv | Dokumentáció |
| --- | --- | --- |
| A Juttatási okkódok integrálása a **Személyzet kezelése** munkaterületen | -- | [Okkódok beállítása](hr-benefits-setup-reason-codes.md) |

### <a name="bug-fixes"></a>Hibajavítások

Ez a kiadás az alábbi hibajavításokat tartalmazza.

> [!NOTE]
> Célunk, hogy a lehető leghamarabb eljuttassuk Önhöz ezeket az információkat. A cikk első közzététele után frissíthet egy hibajavítást, amely a javításokat tartalmazza a buildben.


| Kiadás száma | Probléma |  Leírás |
| --- | --- | --- |
| 539456 | A naptár a szabadságtípust jeleníti meg rámutatáskor, ha a **Csak távollét megjelenítése részletek nélkül** paraméter van engedélyezve. | Ha a **Csak távollét megjelenítése részletek nélkül** beállítás engedélyezve van, a kérelem dátuma rámutatáskor megjelenik. |
| 528907 | A jogi személyhez alkalmazotti szerepkörben való hozzáférés megadása azt eredményezi, hogy a vezetők nem látják az alkalmazotti szabadság és távollét egyensúlyával kapcsolatos tevékenységeket az Alkalmazotti önkiszolgáló rendszer **Saját csoport** területén. |Ezen lehetőség beállításával a vezetők továbbra is láthatják a szabadság és távollét egyensúlyával kapcsolatos tevékenységeket. |
| 526280 | Engedélyhiba lépett fel a HcmWorkerEntity, a HcmEmployeeEntity és a HcmContractorEntity esetében. | A nem rendszergazdai szerepkörbe sorolt felhasználók a NationalityCountryRegion mezőbe engedélyhiba miatt nem exportálták a felsorolt entitásokat. A felhasználóknak a következő jogosultságokra lesz szükségük az adatok exportálására: HcmWorkerEntityMaintain, HcmWorkerEntityView, HcmEmployeeEntityMaintain, HcmEmployeeEntityMaintain, HcmEmployeeEntityView, HcmContractorEntityMaintain és HCMContractorEntityView. |
| 542147 | A **Bankszámlaszám** és az **Útvonalszám** mezők kötelezőek, ha az Alkalmazotti önkiszolgáló rendszeren keresztül adja hozzá a bankszámlát. | Javítottuk azt a hibát, amely miatt az alkalmazottaknak ki kellett tölteniük a **Bankszámlaszám** és a **Útvonalszám** mezőket a bankszámla részleteinek hozzáadásakor. Ezek a mezők már nem kötelezőek az új bankszámlaadatok mentésekor. |
| 543641 | Az elektronikus jelentésen nem jelenik meg az irányítószám. | Kijavított hiba: az irányítószám nem jelent meg az ACA-jelentésben az L és Q közötti fedezeti kódok esetén. |
| 545402 | Adja meg a UserBranding.js fájl útvonalváltozását a 404-es hibák eltávolításához. | A felhasználóknak a konzolon már nem kell 404-es hibát látniuk. |

## <a name="in-preview"></a>Előnézetben   

Az alábbi új funkciók előzetes verzióban érhetők el. A funkciók be- vagy kikapcsolásával kapcsolatos további információkért lásd a [Szolgáltatások kezelése](hr-admin-manage-features.md) című témakört.

| Funkció | Kiadási terv | Dokumentáció |
| --- | --- | --- |
| Human Resources alkalmazás a Microsoft Teams alkalmazásban | [Alkalmazott szabadsági és távolléti élménye a Microsoft Teams rendszerben](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) | [Human Resources alkalmazás a Teamsben](./hr-admin-teams-leave-app.md)<br>[Szabadságkérelmek kezelése a Teamsben](hr-teams-leave-app.md) |
| Szabadságok vállalatközi nézete vezetőknek | [Munkavállalói szabadságok vállalatközi nézete vezetőknek](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/cross-company-view-employee-leave-managers) | [Szabadság és távollét paramétereinek konfigurálása](./hr-leave-and-absence-parameters.md) |

## <a name="coming-soon"></a>Hamarosan

| Funkció | Részletek |
| --- | --- |
| Juttatási regisztrációk e-mailben való visszaigazolása | Ezzel a funkcióval visszaigazoló e-mailt küldhet az alkalmazottaknak, amikor kijelentkeznek a juttatások regisztrációs szolgáltatásából a Munkavállalói önkiszolgáló rendszerben. Ez a funkció február 1-jén lesz elérhető. További információ: [Juttatáskezelési paraméterek konfigurálása vállalatonként](hr-benefits-setup-parameters-per-company.md). |
| A vezető által az alkalmazottakhoz megadott szakértelmet egy munkafolyamat automatikusan jóváhagyhatja | Hamarosan. |

A tervezett funkciók és az ütemezett kiadásaik teljes listáját lásd: [A Dynamics 365 Human Resources 2021. első kiadási hullámának áttekintése](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="terminology-updates-for-microsoft-dataverse"></a>Terminológiai frissítések a Microsoft Dataverse számára

2020 novemberétől a Common Data Service szolgáltatás új neve: [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). A további tudnivalókat lásd a [hivatalos közleményben](https://powerapps.microsoft.com/blog/reshape-the-future-of-work-with-microsoft-dataverse-for-teams-now-generally-available/) a Power Apps blogon. Ezzel a névváltozással együtt a Dataverse terminológiája is részben frissült. Például az *entitás* mostantól *tábla*, a *mező* pedig *oszlop*. A további tudnivalókat lásd: [Terminológia frissítései](/powerapps/maker/data-platform/data-platform-intro#terminology-updates).

Ebben a kiadásban a Dynamics 365 Human Resources rendszer Dataverse-integrációjával kapcsolatos terminológiáját frissítettük az alkalmazás egészében, hogy tükrözze ezeket a változásokat. Például a **Common Data Service-integráció** űrlapjának neve most **Microsoft Dataverse-integráció**.

A Dynamics 365 Human Resources rendszer Microsoft Dataverse rendszerrel történő integrációjával kapcsolatos további tudnivalókat lásd: [A Microsoft Dataverse-integráció konfigurálása](./hr-admin-integration-common-data-service.md) és [Microsoft Dataverse virtuális táblák konfigurálása](./hr-admin-integration-common-data-service-virtual-entities.md).

## <a name="see-also"></a>Lásd még

[Újdonságok és változások a Human Resources szolgáltatásban](hr-admin-whats-new.md)</br>
[A Dynamics 365 Human Resources 2021. első kiadási hullámának áttekintése](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)</br>
[Rendelés frissítése](hr-admin-setup-update-process.md)</br>
[Szolgáltatások kezelése](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]