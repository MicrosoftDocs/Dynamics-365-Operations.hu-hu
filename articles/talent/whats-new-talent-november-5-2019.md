---
title: Új vagy módosult elemek a Dynamics 365 Talent szolgáltatásban (2019. november 5.)
description: Ez a témakör a Microsoft Dynamics 365 Talent új vagy módosított szolgáltatásait írja le.
author: Darinkramer
manager: AnnBe
ms.date: 11/05/2019
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
ms.search.validFrom: 2019-11-05
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 48de07178acfaccf11e0a02b2848bf24e6ccc117
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/06/2019
ms.locfileid: "2896773"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-november-5-2019"></a>Új vagy módosult elemek a Dynamics 365 Talent szolgáltatásban (2019. november 5.)

Ez a témakör a Dynamics 365 Talent új vagy módosított szolgáltatásait írja le.

## <a name="changes-in-attract"></a>Változások az Attract-ben

A kiadás a Dynamics 365 Talent: Attract apró hibáinak javításait is tartalmazza.

## <a name="changes-in-onboard"></a>Változások az Onboard alkalmazásban

A kiadás a Dynamics 365 Talent: Onboard apró hibáinak javításait is tartalmazza.

## <a name="changes-in-core-hr"></a>A Core HR módosításai

A szakaszban ismertetett módosítások a 8.1.2598-ös buildre vonatkoznak. A néhány fejlécben látható, zárójelben lévő számok az Microsoft Dynamics Lifecycle Services (LCS) támogatási számaira vonatkoznak.

### <a name="copy-a-core-hr-instance"></a>Core HR példány másolása

A heti kiadásban az Microsoft Dynamics Lifecycle Services (LCS) szolgáltatással átmásolhat egy Microsoft Dynamics 365 Talent: Core HR adatbázist egy tesztkörnyezetbe. Ha van másik tesztkörnyezete, akkor abból a környezetből is másolható az adatbázis a célként kiválasztott tesztkörnyezetbe. További tájékoztatás:

- [Tágabb környezetkezelés](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/broader-environment-management) a Dynamics 365: 2019 Release Wave 2 tervben

- [Core HR-példány másolása](hr-copy-instance.md) a Talent dokumentációba

### <a name="common-data-service-integration-batch-jobs-arent-created-when-common-data-service-integration-is-enabled-388030"></a>Nem jönnek létre Common Data Service-integrációs kötegelt feladatok, amikor a Common Data Service-integráció engedélyezve van (388030)

A módosítással kötegelt feladatok jönnek létre a Common Data Service szolgáltatáshoz, amikor engedélyezve van az integráció.

### <a name="the-hcmpersonimageentity-doesnt-resize-the-person-image-when-uploaded-369469"></a>A HcmPersonImageEntity nem méretezi át a személy képét feltöltéskor (369469)

Ez a heti kiadás megváltoztatja a képek átméretezését a jobb teljesítmény érdekében, amikor az adatkezelésen keresztül importálják.

### <a name="a-positions-available-for-assignment-date-can-be-earlier-than-the-activation-date-340103"></a>A beosztás Elérhető hozzárendelésre dátuma az Aktiválási dátumnál korábbi lehet (340103)

Ezzel a módosítással megjelenik egy figyelmeztetés, ha olyan **Elérhetőség dátuma a hozzárendeléshez** dátumot választ ki, amely korábbi, mint a beosztás **Aktiválási dátuma**.

### <a name="cant-create-a-compensation-change-request-in-employee-self-service-for-step-based-plans-376872"></a>Nem hozható létre kompenzációs módosítási kérelem az Alkalmazotti önkiszolgáló szolgáltatásban a lépésalapú tervekhez (376872)

Ez a kiadás javítja azt a hibát, amely a kompenzáció módosítására vonatkozó kérelem alkalmazotti önkiszolgáló rendszeren keresztül való elküldése során merül fel lépésalapú tervek esetén. 

### <a name="reason-code-doesnt-sync-to-common-data-service-if-the-description-is-longer-than-30-characters-core-hr-allows-60-352682"></a>Az okkód nem szinkronizálódik a Common Data Service szolgáltatással, ha a leírás 30 karakternél hosszabb, a Core HR megengedett értéke 60 (352682)

ezzel a módosítással a 30 karakternél hosszabb okkódok frissítése is megtörténik a Common Data Service szolgáltatásban. A Common Data Service szolgáltatásban végrehajtott változtatások a Talent szolgáltatásban is megjelennek.

### <a name="address-integration-from-talent-to-finance-and-operations-351961"></a>Címek integrációja a Talent alkalmazásból a Finance and Operations szolgáltatásba (351961)

Ez a kiadás javít egy olyan problémát, amelynél a Talentben frissített címek nem frissültek a Finance and Operations szolgáltatásban. A rendszer most már frissíti a címblokkok módosításait.

## <a name="coming-soon"></a>Hamarosan

### <a name="print-performance-reviews"></a>Teljesítményértékelések nyomtatása

Lásd [Teljesítményértékelések nyomtatása](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/print-performance-reviews) a Dynamics 365: 2019 release wave 2 tervben.

### <a name="feature-management-workspace"></a>A Funkciókezelés munkaterület

Minden kiadásban új szolgáltatások és frissítések jelennek meg. A funkció-kezelési élmény olyan munkaterületet tartalmaz, amelyen megtekintheti az egyes kiadásokban elérhetővé tett szolgáltatások listáját. Alapértelmezés szerint az új szolgáltatások ki vannak kapcsolva. A munkaterületen bekapcsolhatja a szolgáltatásokat, és megtekintheti a rájuk vonatkozó dokumentációt.

További információ a szolgáltatások kezelésével kapcsolatos változásokról: [Funkciókezelés áttekintése](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview).
