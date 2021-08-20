---
title: Új vagy módosult elemek a Dynamics 365 Human Resources szolgáltatásban 2021. május 3-án
description: Ez a témakör a Microsoft Dynamics 365 Human Resources új vagy módosított szolgáltatásait írja le a 2021. május 3-i kiadásban.
author: marcelbf
ms.date: 05/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-05-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 1bfbfabc8ba9c41dfd02c205755042f82387f5e09c88722e2503316bc1cf5feb
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6770360"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-may-3-2021"></a>Új vagy módosult elemek a Dynamics 365 Human Resources szolgáltatásban 2021. május 3-án

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Ez a témakör a Dynamics 365 Human Resources új, módosított vagy nemsokára várható szolgáltatásait írja le.

A frissítési folyamattal és ütemezéssel kapcsolatos további tudnivalókért lásd: [Frissítési folyamat](hr-admin-setup-update-process.md).

További tájékoztatás az új szolgáltatásokról és a nyilvános megjelenési dátumokról: [A Dynamics 365 Human Resources 2021. második kiadási hullámának áttekintése](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>Ebben a verzióban

Ez a kiadás az alábbi új funkciókat és hibajavításokat tartalmazza. A változtatások a 8.1.4140-es buildszámra vonatkoznak.

### <a name="new-features"></a>Új funkciók

Az alábbi funkciók általában a következő verzióval lesznek elérhetők.

| Funkció | Kiadási terv | Dokumentáció |
| --- | --- | --- |
| Információs sáv hozzáadása az életesemények létrehozásakor. | - | Az életesemények létrehozásakor az információs sáv a létrehozott életesemény típusát jelző üzenetet jelenít meg.

### <a name="bug-fixes"></a>Hibajavítások

Ez a kiadás az alábbi hibajavításokat tartalmazza.

> [!NOTE]
> Célunk, hogy a lehető leghamarabb eljuttassuk Önhöz ezeket az információkat. Előfordulhat, hogy a jelen témakört frissítjök olyan hibajavításokkal, amelyek annak első közzététele után léptek életbe.

| Kiadás száma | Kiadás |  Leírás |
| --- | --- | --- |
| 559312 |  A szint nem jelenik meg, amikor fix kompenzációs konstrukciót hoz létre egy alkalmazott számára. |  Ha időzóna-eltérés van a felhasználó időzónája és a vállalat időzónája között, akkor a feladathoz megadott kompenzációs szintet nem sikerült beolvasni. A lekérdezés UTC-idő alapján lett frissítve a beolvasásra. |
| 573676  | Nem lehet új időszakot hozzáadni a **Juttatási terv** űrlapon. | A képernyő frissítése után a **Juttatási tervek** **Időszak** gyorslapja alatt elérhető **Új** gomb engedélyezve lesz. |

## <a name="in-preview"></a>Előnézetben

Az alábbi új funkciók előzetes verzióban érhetők el. A funkciók be- vagy kikapcsolásával kapcsolatos további információkért lásd a [Szolgáltatások kezelése](hr-admin-manage-features.md) című témakört.

| Funkció | Kiadási terv | Dokumentáció |
| --- | --- | --- |
| Juttatáskezelési munkaterület | [Juttatáskezelési munkaterület (előzetes verzió)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [Juttatáskezelési munkaterület](hr-benefits-management-workspace.md) |
| Szabadság és távollét munkafolyamat-élmény javításai | [Szabadság és távollét munkafolyamat-élmény javításai](https://go.microsoft.com/fwlink/?linkid=2147528) | [Távollét kérelmezése](hr-employee-self-service-request-time-off.md)|
| Egyszerűsített bérintegrációs (Bérintegrációs API-k) engedélyezése | [Egyszerűsített integráció engedélyezése a bérszolgáltatókkal](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-simplified-integration-payroll-providers) | [Bérlista-integrációs API](hr-admin-integration-payroll-api-introduction.md)|
| Szabadságelhatárolási tranzakció auditálása | - | [Szabadságelhatárolási tranzakció auditálása](hr-leave-and-absence-accrue.md)|

## <a name="coming-soon"></a>Hamarosan

| Funkció | Részletek |
| --- | --- |
| Platform frissítése erre: 10.0.18 (42) | A 10.0.18-es verziófrissítés az ütemezés szerint a szolgáltatáskiadással, 2021. május 17-én indul el. További tájékoztatás: [Platform-frissítések az Finance and Operations alkalmazások 10.0.18 verziójához (2021. május)](/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-18). |
| Egyéni mező támogatása a Juttatások kezelése jogosultsági szabályokban  | [Egyéni mezőtámogatás a jogosultságok feldolgozásához](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/custom-field-support-eligibility-processing) |

A tervezett funkciók és az ütemezett kiadásaik teljes listáját lásd: [A Dynamics 365 Human Resources 2021. első kiadási hullámának áttekintése](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="see-also"></a>Lásd még

[Újdonságok és változások a Human Resources szolgáltatásban](hr-admin-whats-new.md)</br>
[A Dynamics 365 Human Resources 2021. első kiadási hullámának áttekintése](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)</br>
[Rendelés frissítése](hr-admin-setup-update-process.md)</br>
[Szolgáltatások kezelése](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
