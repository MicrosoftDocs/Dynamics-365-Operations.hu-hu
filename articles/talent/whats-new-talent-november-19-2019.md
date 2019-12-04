---
title: Új vagy módosult elemek a Dynamics 365 Talent szolgáltatásban (2019. november 19.)
description: Ez a cikk a Microsoft Dynamics 365 Talent új vagy módosított funkcióit írja le.
author: Darinkramer
manager: AnnBe
ms.date: 11/19/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-11-19
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 6a26c0039b145f4b6a0940a60256ba7b6644a829
ms.sourcegitcommit: b95df4cea27d6a8f797e0bdd18952bec7dece4ad
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/22/2019
ms.locfileid: "2825002"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-november-19-2019"></a>Új vagy módosult elemek a Dynamics 365 Talent szolgáltatásban (2019. november 19.)

[!include [banner](includes/banner.md)]

Ez a cikk a Dynamics 365 Talent szolgáltatásban található új vagy módosított funkciókat írja le.

## <a name="changes-in-attract"></a>Változások az Attract-ben

A kiadás a Dynamics 365 Talent: Attract apró hibáinak javításait is tartalmazza.

## <a name="changes-in-onboard"></a>Változások az Onboard alkalmazásban

A kiadás a Dynamics 365 Talent: Onboard apró hibáinak javításait is tartalmazza.

## <a name="changes-in-core-hr"></a>A Core HR módosításai

A szakaszban ismertetett módosítások a 8.1.2621-ös buildre vonatkoznak. A néhány fejlécben látható, zárójelben lévő számok az Microsoft Dynamics Lifecycle Services (LCS) támogatási számaira vonatkoznak.

### <a name="platform-update-31-for-finance-and-operations-apps"></a>Platform update 31 a Finance and Operations alkalmazásokhoz

A további tudnivalókat lásd [Előzetes funkciók a Finance and Operations alkalmazások Platform update 31 verziójában (2020. január)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-update-31).

### <a name="feature-management-workspace-383856"></a>A Funkciókezelés munkaterület (383856)

A **Funkció-kezelés** munkaterülete az egyes kiadásokban kiadott funkciók listáját tartalmazza. Alapértelmezés szerint az új szolgáltatások ki vannak kapcsolva. A munkaterületen bekapcsolhatja a szolgáltatásokat, és megtekintheti a rájuk vonatkozó dokumentációt. A funkciókezeléssel kapcsolatos további tudnivalókat lásd [Funkciókezelés áttekintése](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview).

Minden új funkció megmarad előzetes verzióban legalább 30 napig, és általában 30-60 napig. A főbb funkciók általában az előzetes időszakot követően minden év októberében és áprilisában érhetők el. Amint az új funkciókat a **Funkciókezelés** munkaterületen látja, be lehet kapcsolni őket. Előfordulhat, hogy egyes funkciók alapértelmezés szerint be vannak kapcsolva.
 
Időnként egy szerves funkció alapértelmezésben be van kapcsolva, de nem kapcsolható ki (például a **Funkciókezelési** munkaterület).
 
Ha egy szolgáltatás általában elérhető, előfordulhat, hogy a működési környezetben be van kapcsolva vagy ki van kapcsolva. A **funkciókezelés** munkaterület jelzi, hogy egy előzetes funkció mikor válik kötelezővé. Ez a dátum általában október 1. vagy április 1., hogy a féléves kiadási tervekkel összehangolják. Nem kapcsolhatja ki a kötelező funkciókat. Amíg nem válik kötelezővé, bármely környezetben ki- és bekapcsolhatja a funkciót.

### <a name="message-appears-when-canceled-action-exists-for-a-position-382887"></a>Üzenet jelenik meg, ha a beosztáshoz érvénytelenített művelet található (382887)

A következő üzenet már nem jelenik meg, amikor kiválasztott egy beosztást, és a beosztáshoz csak egy érvénytelenített művelet áll rendelkezésre: **Egy hiányos művelet van folyamatban az xxxxxx beosztás esetében**.

### <a name="in-learning-analytics-the-course-type-and-status-display-incorrect-data-381151"></a>A Tanulási elemzésekben a Tanfolyam típusa és Állapot helytelen adatokat jelenít meg (381151)

Az eheti kiadással frissült a tanulási elemzés és már helyesen jeleníti meg a **Tanfolyam típusa** és **Állapot** értékét.

### <a name="personnel-number-should-display-in-the-new-worker-form-banner-383832"></a>A személyzeti számnak meg kell jelennie az Új dolgozó űrlap szalagcímében (383832)

Az **Új dolgozó** képernyőn a **Személyzeti szám** most már megjelenik a szalagcímben gyors hivatkozás érdekében.

### <a name="position-start-date-determines-the-job-record-to-use-when-retrieving-a-compensation-level-during-hire-350361"></a>A beosztás kezdő dátuma határozza meg a toborzás során a kompenzációs szint lekérésekor használandó állásrekordot (350361)

Ebben a kiadásban a **kompenzáció kezdő dátuma** határozza meg az új álláshoz rendelt szintet.

### <a name="custom-pick-list-fields-in-the-position-table-arent-synchronized-to-common-data-service-387503"></a>A beosztás tábla egyéni kitárolási lista mezői nem kerülnek szinkronizálásra a Common Data Service szolgáltatással (387503)

Ebben a kiadásban a kitárolási listaelemek szinkronizálása megtörténik a Common Data Service szolgáltatással.

### <a name="worker-address-entity-doesnt-synchronize-with-common-data-service-while-importing-new-data-349673"></a>A dolgozói cím entitás nem szinkronizálódik a Common Data Service szolgáltatással az új adatok importálásakor (349673)

A heti kiadásban a cím adatai szinkronizálva vannak a Common Data Service szolgáltatással az új adatok importálása közben.

## <a name="in-preview"></a>Előnézetben

### <a name="print-performance-reviews"></a>Teljesítményértékelések nyomtatása

Lásd [Teljesítményértékelések nyomtatása](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/print-performance-reviews) a Dynamics 365: 2019 release wave 2 tervben.
