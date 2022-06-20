---
title: Dynamics 365 Pénzügy, Ellátásilánc-kezelés és Commerce – Az Egyesült Államokkal kapcsolatos közösségi felhő (GCC)
description: Ez a cikk a Microsoft Dynamics minősített kormányzati és magán jogi személyek számára elérhető 365 egyesült államoki kormányzati termékről nyújt tájékoztatást.
author: hasaid
ms.date: 11/12/2021
ms.topic: article
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: hasaid
ms.search.validFrom: 2021-11-09
ms.openlocfilehash: 90e64fec512307af209ace128d5897475de7aee5
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8867273"
---
# <a name="dynamics-365-finance-supply-chain-management-and-commerce-in-us-government-community-cloud-gcc"></a>Dynamics 365 Pénzügy, Ellátásilánc-kezelés és Commerce – Az Egyesült Államokkal kapcsolatos közösségi felhő (GCC)

[!include [banner](../includes/banner.md)]



A Microsoft Dynamics 365-ös (egyesült államokbeli) kormányzati termékek a minősített kormányzati és magán jogi személyek számára érhetők el. Ezek az entitások csak a következő típusokra korlátozódnak:

- Usa szövetségi, állami, helyi, törzsi és területi kormányzati szervek
- A Dynamics 365 Egyesült Államokkal rendelkező magánentitások, amelyek a kormányzati entitásoknak vagy a felhőalapú közösség minősített tagjainak nyújtják a megoldásokat.
- A kormányzati szabályozás alá tartozó vevői adatokkal érintett magánjellegű entitások, és a jogszabályok követelményeinek megfelelő Szolgáltatás a Dynamics 365 egyesült állam lesz.

A további tudnivalókat lásd: [Dynamics 365 US Government](/power-platform/admin/microsoft-dynamics-365-government).

## <a name="onboarding"></a>Onboarding

Microsoft Dynamics A Lifecycle Services (LCS [) egy megvalósítási projekt kezdeti telepítésének befejezéséhez kövesse a "Onboard" (A bevezetési) projektben található utasításokat](../../../fin-ops-core/fin-ops/imp-lifecycle/onboard.md). Ne használja azonban a hivatkozást az útmutatásban megadott nyilvános LCS-fájlra. Ehelyett a következő URL-cím használatával nyissa meg az LCS-t az Egyesült Államok kormányzati közösségi felhőjéhez (GCC):<https://gov.lcs.microsoftdynamics.us>.

A kezdeti berakodási művelet befejezése után kövesse [a Project onboarding](../lifecycle-services/project-onboarding.md) szakaszban található utasításokat. Ismét használja az [LCS-t GCC-ként a nyilvános LCS](https://gov.lcs.microsoftdynamics.us) helyett.

## <a name="environment-deployment"></a>Környezet telepítése

Miután befejezte a projektbe való befektetést, áttekintheti az LCS [további lehetőségeit, amelyek a Lifecycle Services (LCS) for Finance and Operations alkalmazások vevőiben le vannak írva](../../../fin-ops-core/dev-itpro/lifecycle-services/lcs-works-lcs.md). Ezután lépjen tovább a környezet telepítésére.

- A Microsoft által kezelt környezetek LCS-en keresztüli telepítéséhez kövesse [a Lifecycle Services (LCS) for Finance and Operations alkalmazások vevőinek a Lifecycle Services (LCS) útmutatóját](../../../fin-ops-core/dev-itpro/lifecycle-services/lcs-works-lcs.md#new-deployment-experience).
- A felhőben tárolt környezetek esetén lásd [a Fejlesztői környezetek telepítése és elérése.](../../../fin-ops-core/dev-itpro/dev-tools/access-instances.md) Az egyesült [államokbeli lifecycle Services-projektekre vonatkozó Azure erőforrás-kezelő on-boarding folyamatának befejezéseként az Erőforrás-kezelő továbbjelző folyamatot is be kell fejeznie](arm-onbarding-us-goverment.md).

> [!NOTE]
> Az egyesült államokbeli LCS-projektek esetében csak az Azure-kormányspecifikus Azure-előfizetések támogatottak.

## <a name="features-that-arent-available"></a>Nem elérhető funkciók

Egyes szolgáltatások nem érhetők el a GCC-telepítéshez, vagy nem lesznek elérhetők a Dynamics 365 rendszer használata során a GCC-ben. A szolgáltatások például Azure DevOps nem érhetők el a GCC-ben. A létesítményben és a Azure DevOps nyilvános szolgáltatásokban Azure DevOps azonban használhatók. A funkciók elérhetőségére vonatkozó részletes tudnivalókat lásd az [Üzleti alkalmazások egyesült államok kormányzati funkciók rendelkezésre állása oldalon](https://aka.ms/BAPFunctionalParity).

## <a name="frequently-asked-questions"></a>Gyakori kérdések

### <a name="are-dynamics-365-finance-and-dynamics-365-supply-chain-management-supported-in-gcc-high"></a>Támogatott a Dynamics 365 Pénzügy és Dynamics 365 Supply Chain Management a GCC-High?

Nem. Dynamics 365 Pénzügy, és Dynamics 365 Supply Chain Management csak a GCC támogatja.

### <a name="can-i-use-public-azure-devops-with-finance-and-supply-chain-management-in-gcc"></a>Használható a nyilvános és az Azure DevOps ellátásilánc-kezelés a GCC-ben?

A nyilvános szolgáltatásokat akkor Azure DevOps használhatja, ha nem rendelkezik a FEDRAMP (Federal Risk and Authorization Management Program) által hitelesített megoldás követelményeivel. Másik lehetőségként használhatja a Kiszolgálót Azure DevOps is.

### <a name="can-i-deploy-a-cloud-hosted-environment-tier-1-development-environment-on-an-azure-commercial-subscription"></a>Telepíthet a felhőben tárolt Tier-1 fejlesztői környezetet Azure kereskedelmi előfizetésre?

Nem. A [GCC](https://gov.lcs.microsoftdynamics.us) LCS szolgáltatásban Azure Government előfizetéssel kell telepíteni egy felhőben tárolt környezetet.

### <a name="what-can-i-do-if-i-need-a-package-from-the-shared-asset-library-but-it-isnt-available-in-lcs-for-gcc"></a>Mit lehet tenni, ha a Megosztott eszköz tára egy csomagjára van szükség, de nem érhető el a GCC LCS-ben?

Ugyanazt a csomagot a megosztott eszköztárból töltheti le a nyilvános [LCS-fájlban](https://lcs.dynamics.com). Másik lehetőségként partnerével letöltheti a csomagot.

### <a name="is-the-code-upgrade-tool-available-in-gcc"></a>Elérhető a kódfrissítési eszköz a GCC-ben?

Nem, a kódfrissítési eszköz jelenleg nem érhető el a GCC-ben. A nyilvános LCS-kben [azonban](https://lcs.dynamics.com) létrehozhat egy potenciális vevői projektet, és használhatja a kódfrissítési eszközt. A potenciális vevők projektjeiben nem lehet környezeteket telepíteni.

### <a name="can-my-partner-open-a-support-ticket-on-my-behalf"></a>A partner megnyithat egy támogató jegyet a nevében?

Igen. Ha azonban a partner nem GCC-személyazonosságot használ, a támogatási jegy a nyilvános támogatási várólistára kerül. Javasoljuk, hogy az LCS-ben a vevő GCC-jogosultsága segítségével nyissa meg a támogatási jegyeket.

## <a name="see-also"></a>Lásd még

- [Dynamics 365 Egyesült Állam -](/power-platform/admin/microsoft-dynamics-365-government)
- [Üzleti alkalmazások - USA kormányzati funkciók elérhetősége](https://aka.ms/BAPFunctionalParity).
- [Lifecycle Services (LCS) használati útmutató](../../../fin-ops-core/dev-itpro/lifecycle-services/lcs-user-guide.md)
- [Felhőbeli telepítés áttekintése](../../../fin-ops-core/dev-itpro/deployment/cloud-deployment-overview.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
