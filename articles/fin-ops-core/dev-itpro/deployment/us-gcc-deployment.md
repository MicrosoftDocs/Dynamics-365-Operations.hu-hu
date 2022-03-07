---
title: Dynamics 365 Finance és az Egyesült Egyesült Államokkal és az Egyesült Dynamics 365 Supply Chain Management Államokkal közös felhőben (GCC)
description: Ez a témakör a minősített kormányzati és magán jogi személyek számára elérhető 365 egyesült államoki kormányzati termékről nyújt Microsoft Dynamics tájékoztatást.
author: hasaid
ms.date: 11/12/2021
ms.topic: article
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: hasaid
ms.search.validFrom: 2021-11-09
ms.openlocfilehash: 17702ada5bf75a44652e194c2555a83e76e7a36b
ms.sourcegitcommit: 9f8da0ae3dcf3861e8ece2c2df4f693490563d5e
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/16/2021
ms.locfileid: "7817467"
---
# <a name="dynamics-365-finance-and-dynamics-365-supply-chain-management-in-us-government-community-cloud-gcc"></a>Dynamics 365 Finance és az Egyesült Egyesült Államokkal és az Egyesült Dynamics 365 Supply Chain Management Államokkal közös felhőben (GCC)

[!include [banner](../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

A 365-ös (egyesült államokbeli) kormányzati termékek a minősített kormányzati és magán jogi személyek számára Microsoft Dynamics érhetők el. Ezek az entitások csak a következő típusokra korlátozódnak:

- Usa szövetségi, állami, helyi, törzsi és területi kormányzati szervek
- A Dynamics 365 Egyesült Államokkal rendelkező magánentitások, amelyek a kormányzati entitásoknak vagy a felhőalapú közösség minősített tagjainak nyújtják a megoldásokat.
- A kormányzati szabályozás alá tartozó vevői adatokkal érintett magánjellegű entitások, és a jogszabályok követelményeinek megfelelő Szolgáltatás a Dynamics 365 egyesült állam lesz.

A további tudnivalókat lásd: [Dynamics 365 US Government](/power-platform/admin/microsoft-dynamics-365-government).

## <a name="onboarding"></a>Onboarding

A Lifecycle Services (LCS) egy megvalósítási projekt kezdeti telepítésének befejezéséhez kövesse a Microsoft Dynamics "Onboard" (A bevezetési) projektben található [utasításokat](../../../fin-ops-core/fin-ops/imp-lifecycle/onboard.md). Ne használja azonban a hivatkozást az útmutatásban megadott nyilvános LCS-fájlra. Ehelyett a következő URL-cím használatával nyissa meg az LCS-t az Egyesült Államok kormányzati közösségi felhőjéhez (GCC):<https://gov.lcs.microsoftdynamics.us>.

A kezdeti berakodási művelet befejezése után kövesse a Project onboarding szakaszban található [...](../lifecycle-services/project-onboarding.md) utasításokat. Ismét használja az [LCS-t GCC-ként](https://gov.lcs.microsoftdynamics.us) a nyilvános LCS helyett.

## <a name="environment-deployment"></a>Környezet telepítése

Miután befejezte a projekt továbbkozását, áttekintheti az LCS további, a [Lifecycle Services (LCS) alkalmazások vevőkkel kapcsolatos Finance and Operations](../../../fin-ops-core/dev-itpro/lifecycle-services/lcs-works-lcs.md) funkcióit. Ezután lépjen tovább a környezet telepítésére.

- A Microsoft által kezelt környezetek LCS-en keresztüli telepítéséhez kövesse az alkalmazások vevőinek [lifecycle Services (LCS) Finance and Operations](../../../fin-ops-core/dev-itpro/lifecycle-services/lcs-works-lcs.md#new-deployment-experience) útmutatóját.
- A felhőben tárolt környezetek esetén lásd a Fejlesztői környezetek telepítése [és elérése.](../../../fin-ops-core/dev-itpro/dev-tools/access-instances.md) Az egyesült államokbeli lifecycle Services-projektekre vonatkozó Azure erőforrás-kezelő on-boarding folyamatának befejezéseként az Erőforrás-kezelő továbbjelző folyamatot is be kell [...](arm-onbarding-us-goverment.md) fejeznie.

> [!NOTE]
> Az egyesült államokbeli LCS-projektek esetében csak az Azure-kormányspecifikus Azure-előfizetések támogatottak.

## <a name="features-that-arent-available"></a>Nem elérhető funkciók

Egyes szolgáltatások nem érhetők el a GCC-telepítéshez, vagy nem lesznek elérhetők a Dynamics 365 rendszer használata során a GCC-ben. A szolgáltatások Azure DevOps például nem érhetők el a GCC-ben. A létesítményben és a Azure DevOps nyilvános Azure DevOps szolgáltatásokban azonban használhatók. A funkciók elérhetőségére vonatkozó részletes tudnivalókat lásd az Üzleti alkalmazások egyesült államok kormányzati [funkciók rendelkezésre állása](https://aka.ms/BAPFunctionalParity) oldalon.

## <a name="frequently-asked-questions"></a>Gyakori kérdések

### <a name="are-dynamics-365-finance-and-dynamics-365-supply-chain-management-supported-in-gcc-high"></a>Használhatók Dynamics 365 Finance Dynamics 365 Supply Chain Management és támogatottak a GCC-High ?

Nem. Dynamics 365 Finance és Dynamics 365 Supply Chain Management csak GCC-kben támogatottak.

### <a name="can-i-use-public-azure-devops-with-finance-and-supply-chain-management-in-gcc"></a>Használható a nyilvános és Azure DevOps az ellátásilánc-kezelés a GCC-ben?

A nyilvános szolgáltatásokat akkor használhatja, ha nem rendelkezik a Azure DevOps FEDRAMP (Federal Risk and Authorization Management Program) által hitelesített megoldás követelményeivel. Másik lehetőségként használhatja a Azure DevOps Kiszolgálót is.

### <a name="can-i-deploy-a-cloud-hosted-environment-tier-1-development-environment-on-an-azure-commercial-subscription"></a>Telepíthet a felhőben tárolt Tier-1 fejlesztői környezetet Azure kereskedelmi előfizetésre?

Nem. A GCC LCS szolgáltatásban Azure Government előfizetéssel kell telepíteni egy felhőben tárolt [...](https://gov.lcs.microsoftdynamics.us) környezetet.

### <a name="what-can-i-do-if-i-need-a-package-from-the-shared-asset-library-but-it-isnt-available-in-lcs-for-gcc"></a>Mit lehet tenni, ha a Megosztott eszköz tára egy csomagjára van szükség, de nem érhető el a GCC LCS-ben?

Ugyanazt a csomagot a megosztott eszköztárból töltheti le [a nyilvános LCS-fájlban.](https://lcs.dynamics.com) Másik lehetőségként partnerével letöltheti a csomagot.

### <a name="is-the-code-upgrade-tool-available-in-gcc"></a>Elérhető a kódfrissítési eszköz a GCC-ben?

Nem, a kódfrissítési eszköz jelenleg nem érhető el a GCC-ben. A nyilvános LCS-kben azonban létrehozhat egy potenciális vevői projektet, [...](https://lcs.dynamics.com) és használhatja a kódfrissítési eszközt. A potenciális vevők projektjeiben nem lehet környezeteket telepíteni.

### <a name="can-my-partner-open-a-support-ticket-on-my-behalf"></a>A partner megnyithat egy támogató jegyet a nevében?

Igen. Ha azonban a partner nem GCC-személyazonosságot használ, a támogatási jegy a nyilvános támogatási várólistára kerül. Javasoljuk, hogy az LCS-ben a vevő GCC-jogosultsága segítségével nyissa meg a támogatási jegyeket.

## <a name="see-also"></a>Lásd még

- [Dynamics 365 Egyesült Állam -](/power-platform/admin/microsoft-dynamics-365-government)
- [Üzleti alkalmazások - USA kormányzati funkciók](https://aka.ms/BAPFunctionalParity) elérhetősége.
- [Lifecycle Services (LCS) használati útmutató](../../../fin-ops-core/dev-itpro/lifecycle-services/lcs-user-guide.md)
- [Felhőbeli telepítés áttekintése](../../../fin-ops-core/dev-itpro/deployment/cloud-deployment-overview.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
