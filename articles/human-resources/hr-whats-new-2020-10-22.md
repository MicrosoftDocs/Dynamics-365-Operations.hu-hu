---
title: Új vagy módosult elemek a Dynamics 365 Human Resources szolgáltatásban (2020. október 22.)
description: Ez a témakör olyan funkciókat ismertet, amelyek vagy újak, vagy módosulnak a Microsoftban Dynamics 365 Human Resources 2020. október 22-én.
author: jcart1106
ms.date: 10/22/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2020-10-20
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d58c8d5eab86779a764cee5a3ee8ca17ade471de
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8862801"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-october-22-2020"></a>Új vagy módosult elemek a Dynamics 365 Human Resources szolgáltatásban (2020. október 22.)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



Ez a témakör az új, módosított vagy hamarosan érkező funkciókat írja le Dynamics 365 Human Resources. A frissítési folyamattal és ütemezéssel kapcsolatos további tudnivalókért lásd: [Frissítési folyamat](hr-admin-setup-update-process.md).

További tájékoztatás az új szolgáltatásokról és a nyilvános megjelenési dátumokról: [A Dynamics 365 Human Resources 2020. második kiadási hullámának áttekintése](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>Ebben a verzióban

Ez a kiadás az alábbi új funkciókat és hibajavításokat tartalmazza. A változtatások a 8.1.3680-es buildszámra vonatkoznak.

### <a name="new-features"></a>Új funkciók

Az alábbi funkciók általában a következő verzióval lesznek elérhetők.

| Funkció | Kiadási terv | Dokumentáció |
| --- | --- | --- |
| 10.0.14(38) platformfrissítés | -- | [A Pénzügy és műveletek alkalmazások 10.0.14-es verziójának platformfrissítései (2020. november)](../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-14.md) |
| Szervezeti és személyzeti felügyeleti munkafolyamat-tapasztalatok továbbfejlesztései | [Szervezeti és személyzeti felügyeleti munkafolyamat-tapasztalatok továbbfejlesztései](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/organization-personnel-management-workflow-experience-enhancements) | [Konfigurációs beállítás a hozzám rendelt munkaelemek lista pozicionálásához](./hr-whats-new-2020-09-03.md#configuration-option-to-position-work-items-assigned-to-me-list-477004) |


### <a name="bug-fixes"></a>Hibajavítások

Ez a kiadás az alábbi hibajavításokat tartalmazza.

> [!NOTE]
> Célunk, hogy a lehető leghamarabb eljuttassuk Önhöz ezeket az információkat. A cikk első közzététele után frissíthet egy hibajavítást, amely a javításokat tartalmazza a buildben.

| Kiadás száma| Probléma  | Leírás|
| --- | --- | --- |
| 437922 | Az FMLA órák importálása a DMF entitás segítségével írásvédettségi hibát eredményez. | A FMLA entitáshoz tartozó órák importálása a FMLA óra entitás használatával nem sikerült. Hozzáadtunk némi logikát, és biztosítjuk, hogy az importált órák száma nem haladja meg az eset hátralévő idejét. |
| 512019 | Helytelen **Utolsó átvitt** mennyiség. | A **Szabadság** lapon az **Adott dátumtól** érték módosítása a következő pénzügyi időszak első napjára helytelen **Utolsó átvitt** mennyiséget jelenít meg az **Éves szabadság** típusra. Most már a megfelelő összeget jeleníti meg. |
| 458639 | A **Dolgozó kapcsolattartói** entitás nem támogatja a módosításkövetési módot. | Frissítettük a **Dolgozói kapcsolattartók** entitást, hogy a saját adatbázis (BYOD) forgatókönyveit is használni tudja.|
| 505347 | A betanításkezelők elküldhetnek egy szabadságkérelmet egy alkalmazottnak, ha engedélyezték a Korszerű dolgozó funkciót. | A HR-segéd és a HR-vezető kivételével a szerepkörök nem nyújthatnak be szabadságkérelmeket az alkalmazottak számára. |
| 513490 | Juttatáskezelések naplózása: naplózás hozzáadása a lefedettségi opció nélküli tervekhez. | Engedélyeztók az eredmények naplózását a **lefedettségi opció nélküli tervekhez**. Most már megjelennek a **Feldolgozás eredménye** táblázatban, és helyes a sorrendjük a képernyő felső részén. |
| 517021 | Nem lehet egynél több tervet ugyanazzal a **Tervtípus** kóddal kiválasztani, ha a **Tervtípushoz** egyetlen beléptetés van típusonként. | Megváltoztattuk azoknak a terveknek a korlátozását, amelyeknél csak egy beléptetés engedélyezett. A korlátozások most a **Tervtípuskód** helyett a **Tervtípus** szinten találhatók. Ez a módosítás lehetővé teszi a HSA és az FSA – mindkettő ugyanolyan típusú – tervezését, de külön **Tervtípuskódot** adhat nekik. Így egyszerre mindkettőt kiválaszthatja ugyanarra a beléptetési időszakra is. |
| 444791 | Nem tekinthető meg a kompenzáció az Alkalmazotti önkiszolgáló szolgáltatásban, ha a kompenzációs tervben bekapcsolták a **Hozzáférés korlátozását**. | Az Alkalmazotti önkiszolgáló **Kompenzáció** kártyáján az aktuális kompenzáció összege és a százalékos érték növelése 0, ha az alkalmazottat egy olyan tervbe léptették be, amely **korlátozza a hozzáférést**, és meghatározott szerepkörökhöz rendelték. Megoldottuk a problémát, így az alkalmazott és a vezető bármikor megtekintheti saját maga és a nekik közvetlenül jelentést tevők kompenzációs adatait. |
| 457542 | A tanfolyami részletek frissítése a tanfolyam lezárása után nem módosítja a tanfolyamo résztvevő alkalmazottra vonatkozó ugyanazon adatokat. | Az alkalmazotti adatok most már megfelelően frissülnek, amikor egy tanfolyami részletet módosítanak egy tanfolyam lezárása és újbóli megnyitása után. |
| 515342 | Nem szúrhatók be adatok a **CDSLeaveRequestDetailEntity** segítségével. A vállalat nem található, vagy nem létezik. | Most már beszúrhatók adatok a **CDSLeaveRequestDetailEntity** segítségével. |
| 514743 | Hiba az **E-mail-paraméter** űrlapon a Microsoft Exchange használata során. | A „Fájlok betöltése vagy összeállítása sikertelen...” üzenet az **E-mail paraméterek** oldalon látható, amikor az e-mail-szolgáltató beállítása **Árfolyam**. Ez a javítás azt is lehetővé teszi, hogy az **E-mail-paraméterek** lap töltése és mentése a várakozásnak megfelelően történjen. |


## <a name="in-preview"></a>Előnézetben

Az alábbi új funkciók előzetes verzióban érhetők el. A funkciók be- vagy kikapcsolásával kapcsolatos további információkért lásd a [Szolgáltatások kezelése](hr-admin-manage-features.md) című témakört.

| Funkció | Kiadási terv | Dokumentáció |
| --- | --- | --- |
| Human Resources alkalmazás a Microsoft Teams alkalmazásban | [Alkalmazott szabadsági és távolléti élménye a Microsoft Teams rendszerben](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) | [Human Resources alkalmazás a Teamsben](./hr-admin-teams-leave-app.md)<br>[Szabadságkérelmek kezelése a Teamsben](hr-teams-leave-app.md) |
| Továbbfejlesztett munkafolyamat-kérelmek és -jóváhagyások | [Szervezeti és személyzeti felügyeleti munkafolyamat-tapasztalatok továbbfejlesztései](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/organization-personnel-management-workflow-experience-enhancements) | [Konfigurációs beállítás a hozzám rendelt munkaelemek lista pozicionálásához](./hr-whats-new-2020-09-03.md#configuration-option-to-position-work-items-assigned-to-me-list-477004) |
| A Dataverse for Human Resources számára elérhető virtuális entitások | [Alapvető Dynamics 365 Human Resources-adatok kibontása a Dataverse szolgáltatásban](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/expand-dynamics-365-human-resources-core-data-common-data-service) | [Dataverse-virtuális entitások konfigurálása](hr-admin-integration-common-data-service-virtual-entities.md) |
| Integráció a LinkedIn Talent Hub szolgáltatással | [Integráció a LinkedIn Talent Hub szolgáltatással](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/integration-linkedin-talent-hub) | [Integráció a LinkedIn Talent Hub szolgáltatással](./hr-admin-integration-linkedin.md) |
| Egyéni hivatkozások a vezetői önkiszolgáló rendszerben | [Egyéni hivatkozások a vezetői önkiszolgáló rendszerben](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/custom-links-manager-self-service) | [Egyéni hivatkozások a vezetői önkiszolgáló rendszerben](./hr-employee-manager-self-service-custom-links.md) |

## <a name="coming-soon"></a>Hamarosan

A tervezett szolgáltatások és az ütemezett kiadások teljes listája az alábbi témakörben olvasható: [A Dynamics 365 Human Resources 2020. második kiadási hullámának áttekintése](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/).


## <a name="see-also"></a>Lásd még

[Újdonságok vagy változások a Human Resources szolgáltatásban](hr-admin-whats-new.md)</br>
[A Dynamics 365 Human Resources 2020. második kiadási hullámának áttekintése](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/)</br>
[Rendelés frissítése](hr-admin-setup-update-process.md)</br>
[Szolgáltatások kezelése](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]