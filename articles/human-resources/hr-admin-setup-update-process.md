---
title: Rendelés frissítése
description: A Microsoft Dynamics 365 Human Resources teljes mértékben „szoftver szolgáltatásként” (SaaS) elven működik, amely folyamatos, érintés nélküli szolgáltatásfrissítéseket és platformmódosításokat tartalmaz.
author: twheeloc
ms.date: 12/01/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SystemAdministrationWorkspaceForm
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-27
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 197b3c5717494ab3c80a57cda337a9021293bf73
ms.sourcegitcommit: 68efa7b89273d04484566cbe14d3533a8fd4ee53
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/02/2022
ms.locfileid: "9819296"
---
# <a name="update-process"></a>Rendelés frissítése

_**Érvényes:**  Emberi erőforrások a különálló infrastruktúrán_ 

> [!NOTE]
> 2022 júliusa óta nem lehet új emberi erőforrások környezeteket létesítni a különálló emberi erőforrások infrastruktúrájára, Microsoft Dynamics és nem lehet új Lifecycle Services -projekteket létrehozni rajta. A vevők az emberi erőforrások környezetét telepítheti a pénzügyi és a műveleti infrastruktúrára. A további tudnivalókat lásd [az Emberi erőforrások biztosítása a pénzügyi és a műveleti infrastruktúra területén](hr-admin-setup-provision-fo.md).

> [!IMPORTANT]
> A pénzügyek és műveletek alkalmazás-infrastruktúrájának frissítési és gyorsjavítási folyamata különbözik az Emberi erőforrások önálló frissítési és gyorsjavítási folyamattól. A frissítési folyamattal kapcsolatos további tudnivalókat [lásd: Folyamat a pénzügyek és műveletek legújabb frissítéséhez való áthelyezéshez](../fin-ops-core/dev-itpro/migration-upgrade/upgrade-latest-update.md). A gyorsjavításokkal kapcsolatos további tudnivalókat [lásd A frissítések letöltése a Lifecycle Services (LCS) alkalmazásból](/fin-ops-core/dev-itpro/migration-upgrade/download-hotfix-lcs.md). 

A Microsoft Dynamics 365 Human Resources teljes mértékben „szoftver szolgáltatásként” (SaaS) elven működik, amely folyamatos, érintés nélküli szolgáltatásfrissítéseket tartalmaz. Ezek a frissítések olyan alkalmazás-és platformmódosításokat tartalmaznak, amelyek kritikus fontosságú javításokat biztosítanak a szolgáltatáshoz, többek között szabályozói frissítéseket.

## <a name="update-policy"></a>Frissítési irányelv

A frissítések rendszeres ütemben jelennek meg minden környezethez. A Human Resources támogatását a [Microsoft Lifecycle irányelv](https://support.microsoft.com/hub/4095338/microsoft-lifecycle-policy) szabályozza, amely egységes és kiszámítható útmutatást nyújt a termék elérhetőségével kapcsolatos támogatásról.

## <a name="release-cadence"></a>A kiadások ütemezése 

A Human Resources szolgáltatás frissítései automatikusan alkalmazva vannak az összes környezetre. A Human Resources szolgáltatáshoz kétféle kiadást biztosítunk:

- **Szolgáltatásfrissítések**: A szolgáltatásfrissítések a megfelelő platformfrissítéseket tartalmazzák a kiadvakor. A kivétel alapú frissítések mellett rendszeres szolgáltatásfrissítések is sorra állnak a Dynamics 365 Pénzügyi platform általános elérhetőségének frissítéseit követően. A platformfrissítésekkel kapcsolatos további tudnivalókat [lásd a Platformfrissítések újdonságai és módosulásai.](../fin-ops-core/dev-itpro/get-started/whats-new-home-page.md) A frissítéseknek több régióra is ki van ásva a globális összesítésük. A frissítésekkel kapcsolatos további tudnivalókat [lásd a Újdonságok és a Módosítások újdonságok Dynamics 365 Human Resources](hr-admin-whats-new.md) oldalon.

- A **Dataverse megoldás frissítései**: Ezek frissítések kb. hat hetente jelennek meg, szükség szerint. Új entitásokat tartalmaz, valamint a Dataverse meglévő entitásainak módosításait. Ezek a frissítések kéthetes frissítésekkel azonos régiókba adták ki őket, és az összes adatforráson keresztüli replikálás körülbelül hat hétig tart. A megoldások frissítései követhetik a kétheti szolgáltatásfrissítéseket, de nem feltétlenül.

> [!NOTE]
> A megoldásfrissítések az összes adatközpontban elérhetők a kiadásuk után. Ha nem szeretné megvárni a frissítések automatikus replikálását, manuálisan is alkalmazhatja azokat bármilyen környezetben, bármelyik adatközpontban.

Szükség esetén az Emberi erőforrások a következő típusú javításokat biztosítják:

- **Javítás (gyorsjavítás)**: Olyan hibajavítások, amelyek a kétheti szolgáltatásfrissítési kiadásokkal vagy azoktól külön jelennek meg

- **Vészhelyzeti javítás**: Proaktív és reaktív gyorsjavítások, amelyek különállóak, csak a konfiguráció vagy csak a kód módosításait tartalmazzál az élő webhelyek hibáinak megoldásához, és a kétheti szolgáltatásfrissítésektől függetlenül is megjelenhetnek

A kiadások felülvizsgálata, tesztelése és ellenőrzése belső környezetben történik. A buildek jóváhagyása után következik a termelési környezetben történő felhasználásuk.

## <a name="communications"></a>Kommunikációk

A következő helyeken tudhatja meg, hogy milyen munkák vannak folyamatban a Human Resources szolgáltatással kapcsolatban, és mit adtunk már ki:

- [Dynamics 365 Human Resources ütemterv](https://dynamics.microsoft.com/roadmap/human-resources/)

- [Dynamics 365 programverzióra vonatkozó kiadási tervek](/dynamics365/release-plans/)

- [Új vagy módosult elemek a Dynamics 365 Human Resources szolgáltatásban](hr-admin-whats-new.md)

- [Megoldáskereső a Lifecycle Servicesben (LCS)](../fin-ops-core/dev-itpro/lifecycle-services/issue-search-lcs.md) (csak a platformmal kapcsolatos hibák esetében)

- [Human Resources blog](https://community.dynamics.com/365/talent/b/dynamics365fortalent)

- [Human Resources Yammer-közössége](https://www.yammer.com/dynamicsaxfeedbackprograms/#/threads/inGroup?type=in_group&feedId=10542230)

## <a name="preview-features-in-a-sandbox-environment"></a>Előzetes funkciók tesztkörnyezetben

Az előzetes funkciókat tesztkörnyezetben ellenőrizheti, mielőtt engedélyezné azokat a termelési környezetben. Az új funkciók engedélyezésével kapcsolatos további tudnivalókat lásd: [Funkciókezelés áttekintése](../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

Minden új funkció megmarad előzetes verzióban legalább 30 napig, és általában 30-60 napig. A főbb funkciók általában az előzetes időszakot követően minden év októberében és áprilisában érhetők el. Amint az új funkciókat a **Funkciókezelés** munkaterületen látja, be lehet kapcsolni őket. Előfordulhat, hogy egyes funkciók alapértelmezés szerint be vannak kapcsolva.

Időnként egy szerves funkció alapértelmezésben be van kapcsolva, de nem kapcsolható ki (például a Funkciókezelési munkaterület).

Ha egy szolgáltatás általában elérhető, előfordulhat, hogy a működési környezetben be van kapcsolva vagy ki van kapcsolva. A **funkciókezelés** munkaterület jelzi, hogy egy előzetes funkció mikor válik kötelezővé. Ez a dátum általában október 1. vagy április 1., hogy a féléves kiadási tervekkel összehangolják. Nem kapcsolhatja ki a kötelező funkciókat. Amíg nem válik kötelezővé, bármely környezetben ki- és bekapcsolhatja a funkciót.

Kifejezetten ajánljuk, hogy tesztkörnyezetben vagy próbakörnyezetben tekintse meg ezeket a funkciókat. A legjobb megoldás az, ha másolatot készít a jelenlegi termelési környezetről vagy adatbázisról egy tesztkörnyezetbe, hogy az adataival próbálhassa ki az új szolgáltatásokat.

A teszt környezet létesítésével kapcsolatos további tudnivalókat lásd: [Létesítés a Human Resources szolgáltatásban](hr-admin-setup-provision.md). A tesztkörnyezet eltávolításának ismertetését lásd: [Példány eltávolítása](hr-admin-setup-remove-instance.md#remove-a-test-drive-environment). 

## <a name="report-bugs"></a>Hibák jelentése

Az előzetes funkciók tesztelésekor vagy az új képességek kipróbálásakor előfordulhat, hogy olyan elemeket talál, amelyek nem a várt módon működnek. A hibákat a [Microsoft Dynamics 365 ügyfélszolgálatának jelentheti](https://dynamics.microsoft.com/support/).

## <a name="see-also"></a>Lásd még

[Dynamics 365 és Power Platform programverzióra vonatkozó kiadási tervek](/dynamics365/release-plans)</br>
[Új vagy módosult elemek a Dynamics 365 Human Resources szolgáltatásban](hr-admin-whats-new.md)</br>
[A szoftver életciklusára vonatkozó irányelv](../fin-ops-core/dev-itpro/migration-upgrade/versions-update-policy.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
