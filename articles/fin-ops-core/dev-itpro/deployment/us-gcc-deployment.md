---
title: Dynamics 365 Finance és Dynamics 365 Supply Chain Management az USA kormányzati közösségi felhőjében (GCC)
description: Ez a témakör tájékoztatást nyújt a Microsoft Dynamics 365 amerikai kormányzat termékei, amelyek elérhetőek a minősített kormányzati és magánszervezetek számára.
author: hasaid
ms.date: 11/12/2021
ms.topic: article
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: hasaid
ms.search.validFrom: 2021-11-09
ms.openlocfilehash: 0c8b88e5d190f6dc9beb9342909d1e489d4af10b
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/31/2022
ms.locfileid: "8062286"
---
# <a name="dynamics-365-finance-and-dynamics-365-supply-chain-management-in-us-government-community-cloud-gcc"></a>Dynamics 365 Finance és Dynamics 365 Supply Chain Management az USA kormányzati közösségi felhőjében (GCC)

[!include [banner](../includes/banner.md)]



Válassza ki Microsoft Dynamics 365 Egyesült Államok (USA) Kormányzati termékek elérhetők a minősített kormányzati és magánszervezetek számára. Ezek az entitások a következő típusokra korlátozódnak:

- Az Egyesült Államok szövetségi, állami, helyi, törzsi és területi kormányzati szervei
- Magánszemélyek, amelyek a Dynamics 365 US Government szolgáltatást használják arra, hogy megoldásokat kínáljanak kormányzati szerveknek vagy a felhőközösség minősített tagjainak
- A kormányzati szabályozás hatálya alá tartozó ügyféladatokkal rendelkező magánszemélyek, és a Dynamics 365 US Government a megfelelő szolgáltatás a szabályozási követelmények teljesítéséhez

További információkért lásd [Dynamics 365 US Government](/power-platform/admin/microsoft-dynamics-365-government).

## <a name="onboarding"></a>Onboarding

A bevezetési projekt kezdeti bevezetésének befejezéséhez Microsoft Dynamics Lifecycle Services (LCS), kövesse az utasításokat [Egy megvalósítási projekt fedélzetén](../../../fin-ops-core/fin-ops/imp-lifecycle/onboard.md). Azonban ne használja a nyilvános LCS-re mutató hivatkozást, amely az utasításokban található. Ehelyett használja a következő URL-t az LCS megnyitásához a US Government Community Cloud (GCC) számára:<https://gov.lcs.microsoftdynamics.us>.

A kezdeti betanítás befejezése után kövesse az utasításokat [Projektbevezetés](../lifecycle-services/project-onboarding.md). Még egyszer használd [LCS a GCC számára](https://gov.lcs.microsoftdynamics.us) nyilvános LCS helyett.

## <a name="environment-deployment"></a>Környezeti telepítés

Miután befejezte a projekt bevezetését, áttekintheti az LCS további lehetőségeit, amelyek leírása a következő helyen található: [Lifecycle Services (LCS) a Finance and Operations alkalmazások ügyfelei számára](../../../fin-ops-core/dev-itpro/lifecycle-services/lcs-works-lcs.md). Ezután folytassa a környezeti telepítéssel.

- A Microsoft által felügyelt környezetek LCS-n keresztüli üzembe helyezéséhez kövesse az alábbi utasításokat [Lifecycle Services (LCS) a Finance and Operations alkalmazások ügyfelei számára](../../../fin-ops-core/dev-itpro/lifecycle-services/lcs-works-lcs.md#new-deployment-experience).
- A felhő által üzemeltetett környezetekhez lásd [Fejlesztői környezetek telepítése és elérése](../../../fin-ops-core/dev-itpro/dev-tools/access-instances.md). Ezenkívül be kell fejeznie a Resource Manager-beépítési folyamatot a csatlakozási szoftverekhez, a leírás szerint [Végezze el az Azure Resource Manager bevezetési folyamatát az Egyesült Államok kormányzati életciklus-szolgáltatási projektjeihez](arm-onbarding-us-goverment.md).

> [!NOTE]
> Az Egyesült Államok kormányzati LCS-projektjei esetében csak az Azure Government-specifikus Azure-előfizetések támogatottak.

## <a name="features-that-arent-available"></a>Nem elérhető funkciók

Egyes funkciók nem lesznek telepíthetők a GCC-ben, vagy nem lesznek használhatók a Dynamics 365-tel a GCC-ben. Például,Azure DevOps A szolgáltatások nem lesznek elérhetők az GCC-ben. Azonban a helyszínen Azure DevOps vagy nyilvános Azure DevOps szolgáltatásokat lehet igénybe venni. A funkciók elérhetőségével kapcsolatos részletes információkért lásd: [Üzleti alkalmazások US kormányzati funkciók elérhetősége](https://aka.ms/BAPFunctionalParity).

## <a name="frequently-asked-questions"></a>Gyakori kérdések

### <a name="are-dynamics-365-finance-and-dynamics-365-supply-chain-management-supported-in-gcc-high"></a>Vannak Dynamics 365 Finance és Dynamics 365 Supply Chain Management támogatja a GCC-Hig?

Nem. Dynamics 365 Finance és Dynamics 365 Supply Chain Management csak a GCC támogatja.

### <a name="can-i-use-public-azure-devops-with-finance-and-supply-chain-management-in-gcc"></a>Használhatom nyilvános Azure DevOps pénzügyi és ellátási lánc menedzsmenttel az ÖET-ben?

Igen, használhatod nyilvánosan Azure DevOps szolgáltatásokat, ha nem rendelkezik követelményekkel a Szövetségi Kockázat- és Jogosultságkezelési Program (FEDRAMP) által tanúsított megoldással szemben. Alternatív megoldásként használhatja Azure DevOps Szerver.

### <a name="can-i-deploy-a-cloud-hosted-environment-tier-1-development-environment-on-an-azure-commercial-subscription"></a>Telepíthetek felhőalapú környezetet, Tier-1 fejlesztői környezetet egy kereskedelmi Azure-előfizetésen?

Nem. Ban ben [LCS a GCC számára](https://gov.lcs.microsoftdynamics.us), az Azure Government-előfizetést kell használnia egy felhőalapú környezet üzembe helyezéséhez.

### <a name="what-can-i-do-if-i-need-a-package-from-the-shared-asset-library-but-it-isnt-available-in-lcs-for-gcc"></a>Mit tehetek, ha szükségem van egy csomagra a Megosztott eszköztárból, de az nem érhető el az LCS for GCC-ben?

Ugyanezt a csomagot letöltheti a Megosztott eszközök könyvtárából [nyilvános LCS](https://lcs.dynamics.com). Alternatív megoldásként partnere segíthet a csomag letöltésében.

### <a name="is-the-code-upgrade-tool-available-in-gcc"></a>Elérhető a kódfrissítő eszköz a GCC-ben?

Nem, a kódfrissítő eszköz jelenleg nem érhető el a GCC-ben. Létrehozhat azonban potenciális projektet [nyilvános LCS](https://lcs.dynamics.com) és használja a kódfrissítő eszközt. Vegye figyelembe, hogy a potenciális projektekben nem tud majd környezeteket telepíteni.

### <a name="can-my-partner-open-a-support-ticket-on-my-behalf"></a>Nyithat-e a partnerem támogatási jegyet a nevemben?

Igen. Ha azonban partnere nem GCC-azonosítót használ, a támogatási jegy a nyilvános támogatási sorba kerül. Javasoljuk, hogy az ügyfél GCC-jogosultságát használja az LCS-ben a támogatási jegyek megnyitásához.

## <a name="see-also"></a>Lásd még

- [Dynamics 365 US Government](/power-platform/admin/microsoft-dynamics-365-government)
- [Üzleti alkalmazások US kormányzati funkciók elérhetősége](https://aka.ms/BAPFunctionalParity).
- [Lifecycle Services (LCS) használati útmutató](../../../fin-ops-core/dev-itpro/lifecycle-services/lcs-user-guide.md)
- [Felhőbeli telepítés áttekintése](../../../fin-ops-core/dev-itpro/deployment/cloud-deployment-overview.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
