---
title: A Human Resources kiépítése a pénzügyi és az műveleti infrastruktúrában
description: Ez a cikk bemutatja, hogy hogyan lehet új termelési környezetet létesítni a Microsoft számára a pénzügyi Dynamics 365 Human Resources és műveleti infrastruktúra területén.
author: twheeloc
ms.date: 01/07/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SystemAdministrationWorkspaceForm
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 2fd8176d16178ecc4ba667e5937f2cec2e0af2c3
ms.sourcegitcommit: bd3b55e1af28e592c97b540de1e87cd8ba9c35a8
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/03/2022
ms.locfileid: "9221592"
---
# <a name="provision-human-resources-in-the-finance-and-operations-infrastructure"></a>A Human Resources kiépítése a pénzügyi és az műveleti infrastruktúrában

_**Érvényes:** Emberi erőforrások a pénzügy és az üzemeltetés alkalmazás-infrastruktúra területén_ 

> [!NOTE]
> 2022 júliusa óta nem lehet új emberi erőforrások környezeteket létesítni a különálló emberi erőforrások infrastruktúrájára, Microsoft Dynamics és nem lehet új Lifecycle Services -projekteket létrehozni rajta. A vevők az emberi erőforrások környezetét telepítheti a pénzügyi és a műveleti infrastruktúrára.

Ez a cikk bemutatja, hogy hogyan lehet új termelési környezetet létesítni a Microsoft számára a pénzügyi Dynamics 365 Human Resources és műveleti infrastruktúra területén.

## <a name="prerequisites"></a>Előfeltételek

Mielőtt új környezetet létesítenének, a következő előfeltételeknek meg kell jelennie:

- Az emberi erőforrásokat egy felhőszolgáltató (CSP) vagy vállalati architektúra (EA) szerződés segítségével vásárolta meg. Ha olyan meglévő Dynamics 365-licenccel rendelkezik, amely már tartalmazza az Emberi erőforrások szolgáltatástervet, és nem tudja végrehajtani a cikk lépéseit, forduljon a Támogatási szolgálathoz.
- A globális rendszergazda bejelentkezett [Microsoft Dynamics a Lifecycle Services (LCS) szolgáltatásba,](https://lcs.dynamics.com) és létrehozott egy új pénzügyi és műveleti projektet.

## <a name="provision-a-human-resources-trial-environment"></a>Az Emberi erőforrások próbakörnyezetének kiépítése

> [!NOTE]
> 2022. április elején az Emberi erőforrások próbakörnyezete nem lesz elérhető a különálló alkalmazásban. A pénzügyi és műveletalkalmazások emberi erőforrásokkal kapcsolatos képességeinek kiértékelés iránt érdeklődő potenciális vevők az ingyenes 30 napos próbaidőszakot a bemutatóadatokkal együtt használhatják. A Dynamics 365 Pénzügy az emberi erőforrások azon képességeit fogja tartalmazni, amelyek a különálló alkalmazás egyesítése révén a pénzügyi infrastruktúra szolgáltatásokat fogják tartalmazni. A további tudnivalókat lásd az EMBERI-szolgáltatások [egyesítése és a vevőknek nyújtott képességek egyesítésével kapcsolatban](https://cloudblogs.microsoft.com/dynamics365/it/2021/09/15/merging-of-hr-offerings-brings-capabilities-together-for-customers). A Dynamics 365 Pénzügy teszteléssel kapcsolatos további tudnivalókat lásd a lépésenként [útmutatóban](../fin-ops-core/fin-ops/get-started/before-you-buy.md).

## <a name="plan-human-resources-environments"></a>A Human Resources-környezetek megtervezése

Az első Human Resources-környezet létrehozása előtt gondosan tervezze meg a projekt környezeti szükségleteit. Az Emberi erőforrások alap előfizetése két környezetben, egy termelési környezetben és egy alapértelmezett szabványos elfogadási tesztben (Box) található. A projekt összetettségétől függően lehetősége van további környezetek vásárlására a projekttevékenységek támogatása érdekében.

A további választható környezetek esetében a következő szempontokat kell figyelembe venni:

- **Adatáttelepítés** – az adatáttelepítési tevékenységek lehetővé teszik, hogy az üzenetdoboz-környezetet tesztelési célokra használja a projektben. Ha további környezete van, akkor az adatáttelepítési tevékenységek a tesztelés és a konfigurálás közben is folytathatók egy másik környezetben.
- **Integráció** – az integráció konfigurálása és tesztelése, amely lehet natív integráció vagy egyéni integráció, például a bérszámfejtés, a pályázók nyomon követési rendszereinek, vagy a juttatási rendszereknek és a szolgáltatóknak a integrációja.
- **Oktatás** – lehet, hogy külön környezetre van szükség, amely a képzési adatok készletével van konfigurálva, hogy az alkalmazottak képzéssel képezve leselkedve használják az új rendszert. 
- **Többfáziss projekt** – szükség lehet egy további környezetre a konfiguráció, az adatáttelepítés, a tesztelés és más tevékenységek támogatásához egy olyan projektfázisban, amely a projekt kezdeti indulása után van tervezve.
- **Fejlesztés** – a pénzügyi és műveleti infrastruktúra területén tovább bővítheti a megoldást, és saját testreszabásokat is kialakíthat. Minden fejlesztőnek saját fejlesztői környezetet kell használnia. A további tudnivalókat lásd [a Fejlesztői környezetek telepítése és elérése.](../fin-ops-core/dev-itpro/dev-tools/access-instances.md)
- **GOLD** – új telepítés esetén a leggyakoribb gyakorlat egy külön GOLD környezet használata, amely a konfigurációhoz és az adatáttelepítéshez eredeti marad. Ez a környezet a teljes megvalósításban használható más környezetek frissítésére. Ezzel hozza létre az új termelési környezetet, amely az alapkonfigurációt és az adatáttelepítést használja. Nem lehet éles környezetet telepíteni a pénzügyi és műveleti infrastruktúrára, amíg be nem fejeződött az éles készenlét. További tájékoztatás: Felkészülés [az élő élőre](../fin-ops-core/fin-ops/imp-lifecycle/prepare-go-live.md).

<!--NOTE: Need to come back and verify Tier-1 can be used and if a customer cannot purchase tier 3-5 need specific documentation about this.-->

> [!IMPORTANT]
> Ha figyelembe veszi a környezetet, a következő megközelítést javasoljuk:
>
> - Az alapértelmezett szabványos elfogadási teszt (korábbi nevén Üzenetbox) környezetben vagy más környezetben történő használat után további átvételt lehet eltolni az élő környezet előtt.
> - Részletes adatátváltási ellenőrzőlista tartani, amely tartalmazza azokat az adatcsomagokat, amelyek szükségesek a végső adatok éles környezetbe való áttelepítéséhez az éles adatátváltás során. Ez az ajánlás különösen akkor fontos, ha nincs külön GOLD környezete a konfigurációk tárolására.
> - Az alapértelmezett szabványos elfogadási teszt (korábbi nevénBox) vagy más, 2. szintű vagy magasabb szintű környezet használata tesztkörnyezetként a projektben. Ha további környezetek szükséges, a szervezet további költségek mellett is megvásárolhatja őket.

## <a name="create-an-lcs-project"></a>LCS-projekt létrehozása

Az LCS-nek a Human Resources kezelésére való használatához előbb egy LCS-projektet kell létrehozni. Ha az emberi erőforrások környezetét a pénzügyi és műveleti infrastruktúrába áttelepítése, új LCS-projektet kell létrehoznia a pénzügyi és műveleti alkalmazások számára. Ha már van LCS-projektje más pénzügyi és műveletalkalmazások számára, **engedélyezheti az Emberi erőforrások szolgáltatást a Funkciókezelés munkaterületen**. További tájékoztatás: [Funkciókezelés – áttekintés](../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

Amikor egy új vevő jelentkezik az Emberi erőforrások közé, az előfizetés tartalmaz egy implementáció projekt munkaterületét. Miután a vevő aktiválja a szolgáltatást, a bérlő rendszergazdájának a <https://lcs.dynamics.com> bérlői számlával kell bejelentkeznie. A projekt munkaterülete automatikusan létrejön a szervezet számára. A további tudnivalókat [lásd a Lifecycle Services (LCS) for Finance and Operations alkalmazások vevőinek](../fin-ops-core/dev-itpro/lifecycle-services/lcs-works-lcs.md).

> [!NOTE]
> A **sikeres** **·** Power Apps létesítés érdekében az Emberi erőforrások környezet építéséhez használt fiókot hozzá kell rendelni vagy a Rendszergazda szerepkörhöz, vagy a rendszer szabó szerepköréhez az emberi erőforrások környezethez társított környezetben. A biztonsági szerepkörök felhasználókhoz Microsoft Power Platform [való hozzárendelésének a beállításával kapcsolatos további tudnivalókat lásd: Felhasználóbiztonság konfigurálása az erőforrásokhoz](/power-platform/admin/database-security).

A környezetek telepítése előtt el kell kezdenie az LCS-projekt üzembe helyezését. A további tudnivalókat lásd [a Projekt hajóra való felhozatásnál](../fin-ops-core/dev-itpro/lifecycle-services/project-onboarding.md). Az LCS használatával kapcsolatos további tudnivalókat lásd [a Lifecycle Services (LCS) felhasználói útmutatóban](../fin-ops-core/dev-itpro/lifecycle-services/lcs-user-guide.md).

## <a name="deploy-human-resources-environments"></a>Az Emberi erőforrások környezetek telepítése

A felhőben a pénzügyi és műveletalkalmazások, többek között az Emberi erőforrások telepítése megköveteli, hogy megértsük a környezetet és az előfizetést, amelyre telepít, ki hajthat végre feladatokat, és milyen adatokat és testreszabásokat kell kezelnie. Új környezetek telepítésekor ajánlott egy szolgáltatásfiókot használni elnevezett felhasználó helyett. A környezetek pénzügyi és műveleti infrastruktúrára [való telepítésével kapcsolatos további tudnivalókat lásd a Felhőtelepítési áttekintésben](/fin-ops-core/dev-itpro/deployment/cloud-deployment-overview).

Ahhoz, hogy az Emberi erőforrások termelési környezetét a pénzügyi és a műveleti infrastruktúrára telepítve legyen, be kell fejeződnie az éles készenlét folyamatának. További tájékoztatás: Felkészülés [az élő élőre](../fin-ops-core/fin-ops/imp-lifecycle/prepare-go-live.md). Ez a folyamat tartalmazza az előfizetés becslését az LCS-be. További információ az Előfizetés [becslésében található](../fin-ops-core/dev-itpro/lifecycle-services/subscription-estimator.md).

## <a name="integrate-microsoft-power-platform-with-human-resources"></a>Integráció az Microsoft Power Platform Emberi erőforrásokkal

Microsoft Power Platform A <a0/&<a2/&ő rendszer a Dynamics 365-alkalmazásokhoz nyújt lehetőségeket a rendszergazdai Power Platform központon keresztül. Az emberi erőforrásokkal kapcsolatos adatok integrálhatók és bővíthetők a használatával Microsoft Power Platform. Az Emberi erőforrások integrálásával kapcsolatos tudnivalókat Microsoft Power Platform [Microsoft Power Platform lásd a Pénzügy és Műveletek alkalmazással való integrációval kapcsolatban](../fin-ops-core/dev-itpro/power-platform/overview.md).

## <a name="supported-geographies"></a>Támogatott földrajzi területek

Az Emberi erőforrások által [támogatott nyelvekről és földrajzi nyelvekről a Global by design: learn about countries and languages (az országok/régiók és a támogatott nyelvek) nyújt tájékoztatást](https://dynamics.microsoft.com/availability-reports/).

## <a name="grant-access-to-the-environment"></a>Hozzáférés biztosítása a környezethez

Alapértelmezés szerint a környezetet csak az a globális rendszergazda érheti el, aki létrehozta. Az alkalmazás további felhasználóinak kifejezett módon engedélyezni kell a hozzáférést. Fel kell vennie a felhasználókat, és hozzájuk kell rendelnie a megfelelő szerepköröket a Human Resources környezetben. További tudnivalókért lásd: [Új felhasználók létrehozása](/dynamics365/unified-operations/dev-itpro/sysadmin/tasks/create-new-users) és [Felhasználók hozzárendelése biztonsági szerepkörökhöz](/dynamics365/unified-operations/dev-itpro/sysadmin/tasks/assign-users-security-roles).

## <a name="additional-resources"></a>További erőforrások
Az LCS-kben a pénzügyekkel és a műveletekkel kapcsolatos projekteknek a következő erőforrások révén való használatával való használatával kapcsolatban további tudnivalókat lehet megindoklok:

- [Lifecycle Services-erőforrások](../fin-ops-core/dev-itpro/lifecycle-services/lcs.md)
- [Lifecycle Services (LCS) használati útmutató](../fin-ops-core/dev-itpro/lifecycle-services/lcs-user-guide.md)
- [Az önkiszolgáló központi telepítés áttekintése](../fin-ops-core/dev-itpro/deployment/infrastructure-stack.md)
- [Adatbázis-mozgási műveletek honlapja](../fin-ops-core/dev-itpro/database/dbmovement-operations.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
