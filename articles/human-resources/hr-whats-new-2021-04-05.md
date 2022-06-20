---
title: Új vagy módosult elemek a Dynamics 365 Human Resources szolgáltatásban, 2021. április 5.
description: Ez a cikk a Microsoft Dynamics 365 Human Resources új vagy módosított szolgáltatásait írja le a 2021. április 5-i kiadásban.
author: marcelbf
ms.date: 04/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-04-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 1b8074877b8d2b2c05596406cbf2d98febd2e8cc
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8899527"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-april-5-2021"></a>Új vagy módosult elemek a Dynamics 365 Human Resources szolgáltatásban, 2021. április 5.

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Ez a témakör az új, módosított vagy hamarosan érkező funkciókat írja le Dynamics 365 Human Resources.

A frissítési folyamattal és ütemezéssel kapcsolatos további tudnivalókért lásd: [Frissítési folyamat](hr-admin-setup-update-process.md).

További tájékoztatás az új szolgáltatásokról és a nyilvános megjelenési dátumokról: [A Dynamics 365 Human Resources 2021. második kiadási hullámának áttekintése](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>Ebben a verzióban

Ez a kiadás az alábbi új funkciókat és hibajavításokat tartalmazza. A változtatások a 8.1.4074-es buildszámra vonatkoznak.

### <a name="new-features"></a>Új funkciók

Az alábbi funkciók általában a következő verzióval lesznek elérhetők.

| Funkció | Kiadási terv | Dokumentáció |
| --- | --- | --- |
| Az alkalmazottak korlátozása az üzleti kapcsolattartók részleteinek szerkesztése elől | [Az alkalmazottak korlátozása az üzleti kapcsolattartók részleteinek szerkesztése elől](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/restrict-employees-editing-business-contact-details) | [A személyes adatok szerkesztésének korlátozása](./hr-employee-self-service-restrict-editing.md)|

### <a name="bug-fixes"></a>Hibajavítások

Ez a kiadás az alábbi hibajavításokat tartalmazza.

> [!NOTE]
> Célunk, hogy a lehető leghamarabb eljuttassuk Önhöz ezeket az információkat. A cikk első közzététele után frissíthet egy hibajavítást, amely a javításokat tartalmazza a buildben.

| Kiadás száma | Probléma |  Leírás |
| --- | --- | --- |
| 550852 | A **Jóváhagyás** gomb nem érvényesíti az **Ellenőrzés** képernyőn beállított kötelező mezőket. | Ha az **Ellenőrzés** képernyőn kötelező mezőként beállít egy mezőt, és közzéteszi a módosításokat a vezetői szerepkörben, akkor a képernyő nem a várt módon ellenőrzi az érvényesítést. |
| 559564 | A fix kompenzáció módosításakor alkalmazott korábbi dolgozói műveletek hibát jeleznek a már kilépett felhasználóknál. | Egy kilépett alkalmazotti kompenzáció dolgozói művelete hibát jelez. Ha egy alkalmazott munkaviszonya megszűnik, akkor a felmondás előtti előléptetés dolgozói művelet hibát jelez. |
| 560074 | A foglalkoztatási kategória legördülő listája nem szűr a **Dolgozótípusra**, és nem jeleníti meg az alkalmazottak és alvállalkozók kategóriáit. | Az **Alkalmazott** képernyőn a **Foglalkoztatási kategória** legördülő lista az alkalmazott vagy az alvállalkozó kategóriáit mutatja az alkalmazott dolgozótípusa alapján. |
| 567388 | Az újonnan létrehozott alkalmazottak bizonyos adatai nem szinkronizálódnak azonnal a **cdm_worker** táblával itt: Dataverse. | Új alkalmazotti rekord létrehozásakor az új rekord szinkronizálva lesz a **cdm_worker** táblával itt: Dataverse, de nem minden tulajdonság szerepel a Dataverse rekordban. |
| 563837 | Azok a funkciók, amelyek nem érhetők el az Emberi erőforrások képernyőn. | Számos funkció, amely nem vonatkozik az Emberi erőforrásokra, a Funkciókezelésben jelenik meg. Ezek a funkciók már nem érhetők el az Emberi erőforrások által engedélyezhető funkciók listájáról. |

## <a name="in-preview"></a>Előnézetben

Az alábbi új funkciók előzetes verzióban érhetők el. A funkciók be- vagy kikapcsolásával kapcsolatos további információkért lásd a [Szolgáltatások kezelése](hr-admin-manage-features.md) című témakört.

| Funkció | Kiadási terv | Dokumentáció |
| --- | --- | --- |
| Juttatáskezelési munkaterület | [Juttatáskezelési munkaterület (előzetes verzió)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [Juttatáskezelési munkaterület](hr-benefits-management-workspace.md) |

## <a name="coming-soon"></a>Hamarosan

| Funkció | Részletek |
| --- | --- |
| A vezető által az alkalmazottakhoz megadott szakértelmet egy munkafolyamat automatikusan jóváhagyhatja | Hamarosan. |
| Platform frissítése erre: 10.0.17 (41) | A 10.0.17-es verziófrissítés az ütemezés szerint a következő kiadással, 2021. április 19-én indul el. A további tudnivalókat [lásd a Pénzügy és műveletek alkalmazások 10.0.17-es verziójának Platformfrissítései (2021. április)](../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-17.md). |

A tervezett funkciók és az ütemezett kiadásaik teljes listáját lásd: [A Dynamics 365 Human Resources 2021. első kiadási hullámának áttekintése](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="see-also"></a>Lásd még

[Újdonságok és változások a Human Resources szolgáltatásban](hr-admin-whats-new.md)</br>
[A Dynamics 365 Human Resources 2021. első kiadási hullámának áttekintése](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)</br>
[Rendelés frissítése](hr-admin-setup-update-process.md)</br>
[Szolgáltatások kezelése](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]