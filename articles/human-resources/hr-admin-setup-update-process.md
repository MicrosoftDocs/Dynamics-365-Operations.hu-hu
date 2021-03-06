---
title: Rendelés frissítése
description: A Microsoft Dynamics 365 Human Resources teljes mértékben „szoftver szolgáltatásként” (SaaS) elven működik, amely folyamatos, érintés nélküli szolgáltatásfrissítéseket és platformmódosításokat tartalmaz.
author: andreabichsel
ms.date: 09/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SystemAdministrationWorkspaceForm
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-27
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 2466c53885340991aeeb0a07af83517473b332b6
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/18/2021
ms.locfileid: "6053635"
---
# <a name="update-process"></a>Rendelés frissítése

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

A Microsoft Dynamics 365 Human Resources teljes mértékben „szoftver szolgáltatásként” (SaaS) elven működik, amely folyamatos, érintés nélküli szolgáltatásfrissítéseket tartalmaz. Ezek a frissítések olyan alkalmazás-és platformmódosításokat tartalmaznak, amelyek kritikus fontosságú javításokat biztosítanak a szolgáltatáshoz, többek között szabályozói frissítéseket.

## <a name="update-policy"></a>Frissítési irányelv

A frissítések rendszeres ütemben jelennek meg minden környezethez. A Human Resources támogatását a [Microsoft Lifecycle irányelv](https://support.microsoft.com/hub/4095338/microsoft-lifecycle-policy) szabályozza, amely egységes és kiszámítható útmutatást nyújt a termék elérhetőségével kapcsolatos támogatásról.

## <a name="release-cadence"></a>A kiadások ütemezése 

A Human Resources szolgáltatás frissítései automatikusan alkalmazva vannak az összes környezetre. A Human Resources szolgáltatáshoz kétféle kiadást biztosítunk:

- **Szolgáltatásfrissítések**: Hibajavításokat és új funkciókat tartalmazó frissítések kéthetente jelennek meg. A kiadott szolgáltatásfrissítések tartalmazzák a megfelelő platformfrissítéseket is. A platformfrissítéseinek kiadásainak ütemezésével kapcsolatos tájékoztatást lásd: [3. táblázat: Platformkiadások](../fin-ops-core/dev-itpro/migration-upgrade/versions-update-policy.md#table-3-platform-releases). A kétheti frissítések egy szakaszos, globális bevezetés keretében jelennek meg a régiókban. A kétheti frissítésekkel kapcsolatos további tudnivalókat lásd: [Újdonságok és változások: Dynamics 365 Human Resources](hr-admin-whats-new.md).

    Ha nincs eltérő értesítés, az összes támogatott adatközpont kéthetente frissül. A kéthetes frissítések között az Egyesült Államok, Ausztrália, Európa, az Egyesült Királyság, Ázsia és Kanada régiói szerepelnek. 

- A **Dataverse megoldás frissítései**: Ezek frissítések kb. hat hetente jelennek meg, szükség szerint. Új entitásokat tartalmaz, valamint a Dataverse meglévő entitásainak módosításait. Ezek a frissítések ugyanazon régiókba irányulnak, mint a kétheti frissítések, és kb. hat hetet vesz igénybe, hogy az összes adatközpontban megtörténjen a replikálásuk. A megoldások frissítései követhetik a kétheti szolgáltatásfrissítéseket, de nem feltétlenül.

> [!NOTE]
> A megoldásfrissítések az összes adatközpontban elérhetők a kiadásuk után. Ha nem szeretné megvárni a frissítések automatikus replikálását, manuálisan is alkalmazhatja azokat bármilyen környezetben, bármelyik adatközpontban.

Szükség esetén a Human Resources szolgáltatás a következő típusú javításokat is biztosítja:

- **Javítás (gyorsjavítás)**: Olyan hibajavítások, amelyek a kétheti szolgáltatásfrissítési kiadásokkal vagy azoktól külön jelennek meg

- **Vészhelyzeti javítás**: Proaktív és reaktív gyorsjavítások, amelyek különállóak, csak a konfiguráció vagy csak a kód módosításait tartalmazzál az élő webhelyek hibáinak megoldásához, és a kétheti szolgáltatásfrissítésektől függetlenül is megjelenhetnek

A kiadások felülvizsgálata, tesztelése és ellenőrzése belső környezetben történik. A buildek jóváhagyása után következik a termelési környezetben történő felhasználásuk.

## <a name="release-cadence-exceptions-in-2021"></a>Kiadási ütemezést érintő kivételek 2021-ban

A munkaszüneti napok figyelembe vételéhez a 2021. novemberi és decemberi kiadások ütemezése a következő:

- Novemberi kiadás: november 1. – november 14.
- Decemberi kiadás: November 29. – December 12.
 
A kéthetes kiadási ütemezés a szokásos módon fog folytatódni 2022. január 10-én.

## <a name="communications"></a>Tájékoztatás

A következő helyeken tudhatja meg, hogy milyen munkák vannak folyamatban a Human Resources szolgáltatással kapcsolatban, és mit adtunk már ki:

- [Dynamics 365 Human Resources ütemterv](https://dynamics.microsoft.com/roadmap/human-resources/)

- [Dynamics 365 programverzióra vonatkozó kiadási tervek](/dynamics365/release-plans/)

- [Új vagy módosult elemek a Dynamics 365 Human Resources szolgáltatásban](hr-admin-whats-new.md)

- [Megoldáskereső a Lifecycle Servicesben (LCS)](../fin-ops-core/dev-itpro/lifecycle-services/issue-search-lcs.md) (csak a platformmal kapcsolatos hibák esetében)

- [Human Resources blog](https://community.dynamics.com/365/talent/b/dynamics365fortalent)

- [Human Resources Yammer-közössége](https://www.yammer.com/dynamicsaxfeedbackprograms/#/threads/inGroup?type=in_group&feedId=10542230)

## <a name="preview-features-in-a-sandbox-environment"></a>Előzetes funkciók tesztkörnyezetben

Az előzetes funkciókat tesztkörnyezetben ellenőrizheti, mielőtt engedélyezné azokat a termelési környezetben. Az új funkciók engedélyezésével kapcsolatos további tudnivalókat lásd: [Funkciókezelés áttekintése](../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

Minden új funkció megmarad előzetes verzióban legalább 30 napig, és általában 30-60 napig. A főbb funkciók általában az előzetes időszakot követően minden év októberében és áprilisában érhetők el. Amint az új funkciókat a Funkciókezelés munkaterületen látja, be lehet kapcsolni őket. Előfordulhat, hogy egyes funkciók alapértelmezés szerint be vannak kapcsolva.

Időnként egy szerves funkció alapértelmezésben be van kapcsolva, de nem kapcsolható ki (például a Funkciókezelési munkaterület).

Ha egy szolgáltatás általában elérhető, előfordulhat, hogy a működési környezetben be van kapcsolva vagy ki van kapcsolva. A funkciókezelés munkaterület jelzi, hogy egy előzetes funkció mikor válik kötelezővé. Ez a dátum általában október 1. vagy április 1., hogy a féléves kiadási tervekkel összehangolják. Nem kapcsolhatja ki a kötelező funkciókat. Amíg nem válik kötelezővé, bármely környezetben ki- és bekapcsolhatja a funkciót.

Kifejezetten ajánljuk, hogy tesztkörnyezetben vagy próbakörnyezetben tekintse meg ezeket a funkciókat. A legjobb megoldás az, ha másolatot készít a jelenlegi termelési környezetről vagy adatbázisról egy tesztkörnyezetbe, hogy az adataival próbálhassa ki az új szolgáltatásokat.

A teszt környezet létesítésével kapcsolatos további tudnivalókat lásd: [Létesítés a Human Resources szolgáltatásban](hr-admin-setup-provision.md). A tesztkörnyezet eltávolításának ismertetését lásd: [Példány eltávolítása](hr-admin-setup-remove-instance.md#remove-a-test-drive-environment). 

## <a name="report-bugs"></a>Hibák jelentése

Az előzetes funkciók tesztelésekor vagy az új képességek kipróbálásakor előfordulhat, hogy olyan elemeket talál, amelyek nem a várt módon működnek. A hibákat a [Microsoft Dynamics 365 ügyfélszolgálatának jelentheti](https://dynamics.microsoft.com/support/).

## <a name="see-also"></a>Lásd még

[Dynamics 365 és Power Platform programverzióra vonatkozó kiadási tervek](/dynamics365/release-plans)</br>
[Új vagy módosult elemek a Dynamics 365 Human Resources szolgáltatásban](hr-admin-whats-new.md)</br>
[A szoftver életciklusára vonatkozó irányelv](../fin-ops-core/dev-itpro/migration-upgrade/versions-update-policy.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]