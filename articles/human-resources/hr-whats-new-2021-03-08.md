---
title: Új vagy módosult elemek a Dynamics 365 Human Resources szolgáltatásban (2021. március 8.)
description: Ez a témakör a Microsoft Dynamics 365 Human Resources új vagy módosított szolgáltatásait írja le a 2021. március 8-i kiadásban.
author: marcelbf
manager: tfehr
ms.date: 03/08/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-03-08
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: c3cd69c86e8590951dd96da75d99bfee2855ac93
ms.sourcegitcommit: 75b432ce9019c81253eb6bd865db905701e28a26
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/11/2021
ms.locfileid: "5579403"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-march-08-2021"></a>Új vagy módosult elemek a Dynamics 365 Human Resources szolgáltatásban (2021. március 08.)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Ez a témakör a Dynamics 365 Human Resources új, módosított vagy nemsokára várható szolgáltatásait írja le.

A frissítési folyamattal és ütemezéssel kapcsolatos további tudnivalókért lásd: [Frissítési folyamat](hr-admin-setup-update-process.md).

További tájékoztatás az új szolgáltatásokról és a nyilvános megjelenési dátumokról: [A Dynamics 365 Human Resources 2021. második kiadási hullámának áttekintése](https://docs.microsoft.com/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>Ebben a verzióban

Ez a kiadás az alábbi új funkciókat és hibajavításokat tartalmazza. A változtatások a 8.1.4017-es buildszámra vonatkoznak.

### <a name="new-features"></a>Új funkciók

Az alábbi funkciók általában a következő verzióval lesznek elérhetők.

| Funkció | Kiadási terv | Dokumentáció |
| --- | --- | --- |
| Szabadságok vállalatközi nézete vezetőknek | [Munkavállalói szabadságok vállalatközi nézete vezetőknek](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/cross-company-view-employee-leave-managers) | [Szabadság és távollét paramétereinek konfigurálása](https://docs.microsoft.com/dynamics365/human-resources/hr-leave-and-absence-parameters) |

### <a name="bug-fixes"></a>Hibajavítások

Ez a kiadás az alábbi hibajavításokat tartalmazza.

> [!NOTE]
> Célunk, hogy a lehető leghamarabb eljuttassuk Önhöz ezeket az információkat. Előfordulhat, hogy a jelen témakört frissítjök olyan hibajavításokkal, amelyek annak első közzététele után léptek életbe.

| Kiadás száma | Kiadás |  Leírás |
| --- | --- | --- |
| 486611 | Távollét jelenik meg a szabadságnaptárban, amikor engedélyezve van a **Szabadság letiltása az összes naptárban** | Ha engedélyezve van a **Szabadság letiltása az összes naptárban** funkció, akkor már nem jelennek meg a szabadságadatok, amikor engedélyezve van a Szabadság és távollét naptár fejlesztései funkciót.|
| 508972 | A Szabadság és távollét banktranzakciós entitásból hiányzik a beléptetés ellenőrzése | A Szabadság és távollét banktranzakciós entitás használatakor a konstrukcióba nem regiszrtált alkalmazottak már nem importálhatók. |
| 554854 | Naptár frissítése az Alkalmazott entitás hibáiban, ha az alapértelmezett Jogi személy eltér a Felhasználói beállításokban | Ha a naptárt az Alkalmazott entitással frissíti egy alkalmazottnál, nem jelenik meg hiba, ha az alapértelmezett Jogi személy eltér a Felhasználói beállításokban. |
| 558347 | A „Nem hozható létre rekord az Űrlapkonfigurációkban (FormRunConfiguration)” üzenet megjelenik a kezdőoldal betöltésekor. | A személyre szabások miatt jelenik meg a „Nem hozható létre rekord az Űrlapkonfigurációkban (FormRunConfiguration)” üzenet a kezdőoldal betöltésekor. |
| 557327 | Juttatáskezelési munkaterület: A rács fölött megjelenik egy üres hely. | Javítottuk a felhasználói élménnyel kapcsolatos problémát, ahol nem szándékos hézag jelent meg a táblarács szegélyein a Juttatások munkaterületen. |
| 557334 | Juttatáskezelési munkaterület: Az **Időszak** kiválasztásának legördülő mezője csak az **Összegzés** lapon jelenjen meg | A Juttatások **Időszak** kiválasztása legördülő lista most csak akkor jelenik meg, ha az **Összesítő** lap aktív a Juttatások munkaterületen, nem pedig a **Folyamat eredménye** és a **Hivatkozások** szakaszban. |
| 557336 | Juttatáskezelési munkaterület: A **Kivett konstrukciókkal rendelkező beléptetés megnyitása** szöveg csonkolva van a csempenézetben | A csempenézetben módosítottuk a szöveget a következőre: **Kivett tervek... beléptetés megnyitása**, a szükséges környezet csonkításának elkerülése érdekében. |

## <a name="in-preview"></a>Előnézetben

Az alábbi új funkciók előzetes verzióban érhetők el. A funkciók be- vagy kikapcsolásával kapcsolatos további információkért lásd a [Szolgáltatások kezelése](hr-admin-manage-features.md) című témakört.

| Funkció | Kiadási terv | Dokumentáció |
| --- | --- | --- |
| Juttatáskezelési munkaterület | [Juttatáskezelési munkaterület (előzetes verzió)](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [Juttatáskezelési munkaterület](hr-benefits-management-workspace.md) |
| Az alkalmazottak korlátozása az üzleti kapcsolattartók részleteinek szerkesztése elől | [Az alkalmazottak korlátozása az üzleti kapcsolattartók részleteinek szerkesztése elől](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/restrict-employees-editing-business-contact-details) | [Személyes adatok szerkesztésének korlátozása](hr-employee-self-service-restrict-editing.md)|

## <a name="coming-soon"></a>Hamarosan

| Funkció | Részletek |
| --- | --- |
| A vezető által az alkalmazottakhoz megadott szakértelmet egy munkafolyamat automatikusan jóváhagyhatja | Hamarosan. |

A tervezett funkciók és az ütemezett kiadásaik teljes listáját lásd: [A Dynamics 365 Human Resources 2021. első kiadási hullámának áttekintése](https://docs.microsoft.com/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="see-also"></a>Lásd még

[Újdonságok és változások a Human Resources szolgáltatásban](hr-admin-whats-new.md)</br>
[A Dynamics 365 Human Resources 2021. első kiadási hullámának áttekintése](https://docs.microsoft.com/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)</br>
[Rendelés frissítése](hr-admin-setup-update-process.md)</br>
[Szolgáltatások kezelése](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
