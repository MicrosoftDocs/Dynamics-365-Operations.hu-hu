---
title: Új vagy módosult elemek a Dynamics 365 Human Resources szolgáltatásban (2021. március 22.)
description: Ez a témakör a Microsoft Dynamics 365 Human Resources új vagy módosított szolgáltatásait írja le a 2021. március 22-i kiadásban.
author: marcelbf
ms.date: 03/22/2021
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
ms.search.validFrom: 2021-03-22
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 383f4dcf315c46534cce93da469a8818f690c45c
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/18/2021
ms.locfileid: "6056492"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-march-22-2021"></a>Új vagy módosult elemek a Dynamics 365 Human Resources szolgáltatásban (2021. március 22.)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Ez a témakör a Dynamics 365 Human Resources új, módosított vagy nemsokára várható szolgáltatásait írja le.

A frissítési folyamattal és ütemezéssel kapcsolatos további tudnivalókért lásd: [Frissítési folyamat](hr-admin-setup-update-process.md).

További tájékoztatás az új szolgáltatásokról és a nyilvános megjelenési dátumokról: [A Dynamics 365 Human Resources 2021. második kiadási hullámának áttekintése](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>Ebben a verzióban

Ez a kiadás az alábbi új funkciókat és hibajavításokat tartalmazza. A változtatások a 8.1.4049-es buildszámra vonatkoznak.

### <a name="new-features"></a>Új funkciók

Az alábbi funkciók általában a következő verzióval lesznek elérhetők.

| Funkció | Kiadási terv | Dokumentáció |
| --- | --- | --- |
| Lehetőség az elakadt kötegelt feladatok érvénytelenítésének és alaphelyzetbe állításának kényszerítésére (560976) | NA | [Beragadt kötegelt feladatok alaphelyzetbe állítása](./hr-admin-troubleshooting-batch-execution.md) |
| Kisebb felhasználói felületi frissítések az új Juttatási terv létrehozásához (419941) | NA | [Juttatási konstrukció létrehozása](hr-benefits-plans-setup.md) |

### <a name="bug-fixes"></a>Hibajavítások

Ez a kiadás az alábbi hibajavításokat tartalmazza.

> [!NOTE]
> Célunk, hogy a lehető leghamarabb eljuttassuk Önhöz ezeket az információkat. Előfordulhat, hogy a jelen témakört frissítjök olyan hibajavításokkal, amelyek annak első közzététele után léptek életbe.

| Kiadás száma | Kiadás |  Leírás |
| --- | --- | --- |
| 554239 | A **BusinessProcessTaskAssignment** táblához kapcsolódó entitások teljesítménybeli fejlesztései | A **BusinessProcessTaskAssignment** táblához kapcsolódó entitások teljesítményének javítása, javasolt indexek hozzáadásával a táblához. |
| 566061 | V2 entitás tartalékkódjának eltávolítása az éjszakai szinkronizálásból | A V2 tartalékkód eltávolítva az éjszakai Dataverse szinkronizálásból. A tartalék már nem szükséges, és megakadályozza, hogy a szűrt szinkronizálás a várt módon működjön. A módosítás növeli a Dataverse adatszinkronizálás konzisztenciáját. |
| 538024 | Dolgozói juttatási programok > A kijelentkezéskor megjelenő hiba eltávolítása | Kijavítottuk a hibát, miközben eltávolítottuk a Juttatási csomag kijelentkezési lehetőségét a Dolgozói juttatások űrlapról. |
| 557965 | **Juttatások** munkaterület: Az **Aktív életesemények** hivatkozásának mindig láthatónak kell lennie a **Hivatkozások** szakaszban | Kijavítottuk azt a hibát, amely miatt az **Aktív életesemények** hivatkozás látható volt a **Hivatkozások** szakaszban, de hiba történt, miközben megpróbált navigálni hibát adott, ha az **(Előzetes verzió) Juttatások kezelése munkaterület** szolgáltatás nem volt engedélyezve. A munkaterület engedélyezéséről további információt a [Juttatások kezelése munkaterület](hr-benefits-management-workspace.md) részben talál. |
| 556672 | Nem lehet feldolgozni egy megszűntetett munkavállaló időbeli elhatárolását, ha a **Korszerűsített alkalmazotti belépés** engedélyezve van a Szolgáltatáskezelésben | A szabadság- és távolléti tervek elhatárolási lehetősége a **További beállítások** szakaszhoz lett hozzáadva a **Munkaelőzmények** alatt, ha az **Egyszerűsített munkavállalói beléptetés** engedélyezve van a funkciókezelésben. |
| 562656 | A **SysRecordChangeLogValidTimeState** menüpontot biztonsági jogosultsággal és a **SystemExternalBasicMaintain** biztonsági feladat kiterjesztésében kell szerepeltetni | A nem rendszergazdai szerepkörökből hiányzott a **Módosítás megtekintése** gomb a dátumkezelő űrlapokon. |
| 505989 | Életesemények feldolgozása: A jogosultság változása a felhasznált időpont miatt nem megfelelően lett feldolgozva | Kijavítottuk azt a problémát, amely miatt a jogosultsági feldolgozás változása a pozíció kezdési dátumtól függött, és nem csak az aktuális pozíciótól. |
| 562286 | A dolgozó munkaviszonyának megszüntetése több frissítést küld a Dataverse felé | Amikor egy dolgozót munkaviszonya megszűnik, egynél több frissítési műveletet küld a Dataverse felé, ami két frissítési értesítést eredményez ugyanehhez a módosításhoz. Ez több eseményindítót is okozhat, ha egy Power Automate folyamat úgy van konfigurálva, hogy a műveletből induljon. |
| 527340 | "Nem reprezentatív DateTime" hiba jelenik meg a szabadság- és távolléti regisztrációk megnyitásakor | Szabadság- és távollét regisztráció kiválasztásakor a hiba már nem jelenik meg. |
| 561663 | Várakozási idő időközének növelése fürtépítéshez | Az infrastruktúra stabilitásának javítása és konzisztencia kiépítése a fürt kiépítésének frissítésével. |
| 486129 | Nem szerkeszthető egyéni mezők a **Pozíciók > Módosítások kezelése** elemben | Kijavítottuk azt a problémát, amely miatt az egyéni mezők nem szerkeszthetők a **Beosztások** **Módosítások kezelése** lapon. |

## <a name="in-preview"></a>Előnézetben

Az alábbi új funkciók előzetes verzióban érhetők el. A funkciók be- vagy kikapcsolásával kapcsolatos további információkért lásd a [Szolgáltatások kezelése](hr-admin-manage-features.md) című témakört.

| Funkció | Kiadási terv | Dokumentáció |
| --- | --- | --- |
| Juttatáskezelési munkaterület | [Juttatáskezelési munkaterület (előzetes verzió)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [Juttatáskezelési munkaterület](hr-benefits-management-workspace.md) |
| Az alkalmazottak korlátozása az üzleti kapcsolattartók részleteinek szerkesztése elől | [Az alkalmazottak korlátozása az üzleti kapcsolattartók részleteinek szerkesztése elől](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/restrict-employees-editing-business-contact-details) | [Személyes adatok szerkesztésének korlátozása](hr-employee-self-service-restrict-editing.md)|

## <a name="coming-soon"></a>Hamarosan

| Funkció | Részletek |
| --- | --- |
| A vezető által az alkalmazottakhoz megadott szakértelmet egy munkafolyamat automatikusan jóváhagyhatja | Hamarosan. |

A tervezett funkciók és az ütemezett kiadásaik teljes listáját lásd: [A Dynamics 365 Human Resources 2021. első kiadási hullámának áttekintése](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="see-also"></a>Lásd még

[Újdonságok és változások a Human Resources szolgáltatásban](hr-admin-whats-new.md)</br>
[A Dynamics 365 Human Resources 2021. első kiadási hullámának áttekintése](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)</br>
[Rendelés frissítése](hr-admin-setup-update-process.md)</br>
[Szolgáltatások kezelése](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]