---
title: Termékajánlatok engedélyezése
description: Ez a témakör azt mutatja be, hogyan lehet olyan termékjavaslatokat létrehozni, amelyek a Microsoft Dynamics 365 Commerce-felhasználók számára elérhető mesterséges intelligencia gépi tanulás (AI-ML) technológián alapulnak.
author: bebeale
manager: AnnBe
ms.date: 08/18/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 59c83409ede5e006ddf030d396934eeb6cd8df76
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "5010124"
---
# <a name="enable-product-recommendations"></a>Termékajánlatok engedélyezése

[!include [banner](includes/banner.md)]

Ez a témakör azt mutatja be, hogyan lehet olyan termékjavaslatokat létrehozni, amelyek a Microsoft Dynamics 365 Commerce-felhasználók számára elérhető mesterséges intelligencia gépi tanulás (AI-ML) technológián alapulnak. A termékajánlási listákkal kapcsolatos további tudnivalókat lásd: [Termékajánlások áttekintése](product-recommendations.md).

## <a name="recommendations-pre-check"></a>Javaslatok előzetes ellenőrzése

Az engedélyezés előtt felhívjuk figyelmét, hogy a termékjavaslatok csak azok számára a Commerce-ügyfelek számára támogatott, akik a tárhelyüket áttelepítették, és az Azure Data Lake Storage felhasználói. 

Az ajánlások engedélyezése előtt engedélyeznie kell a következő konfigurációkat a háttérirodában:

1. Győződjön meg róla, hogy a Azure Data Lake Storage-t megvásárolták és sikeresen hitelesítették a környezetben. További információ: [Győződjön meg róla, hogy az Azure Data Lake Storage-t megvásárolták és sikeresen hitelesítették a környezetben](enable-ADLS-environment.md).
2. Győződjön meg róla, hogy az entitástár frissítés automatizált. A további tudnivalókat lásd: [Győződjön meg róla, hogy az entitástár frissítés automatizált](../fin-ops-core/dev-itpro/data-entities/entity-store-data-lake.md).
3. Győződjön meg róla, hogy az Azure AD identitáskonfiguráció tartalmaz egy Ajánlási bejegyzést. A művelet végrehajtásával kapcsolatos további információk az alábbiakban láthatók.

Ezenkívül győződjön meg arról, hogy a RetailSale-mértékek engedélyezve vannak. A beállítással kapcsolatos további tudnivalókat lásd: [Intézkedések használata](https://docs.microsoft.com/dynamics365/ai/customer-insights/pm-measures).

## <a name="azure-ad-identity-configuration"></a>Azure AD identitáskonfiguráció

Ezt a lépést kötelező megadni az összes olyan vevőnek, aki infrastruktúra szolgáltatásként (IaaS) konfigurációt futtat. A Service Fabric (SF) modulban futó vevők esetében ennek a lépésnek automatikusnak kell lennie, és javasoljuk, hogy ellenőrizze, hogy ez a beállítás a várakozásoknak megfelelően van-e konfigurálva.

### <a name="setup"></a>Beállítás

1. Keresse meg az **Azure Active Directory alkalmazások** lapot a háttér-irodában.
2. Ellenőrizze, hogy létezik-e bejegyzés a következőhöz: „RecommendationSystemApplication-1”.

Ha a bejegyzés nem létezik, adjon hozzá egy új bejegyzést a következő adatokkal:

- **Ügyfélazonosító** - d37b07e8-dd1c-4514-835d-8b918e6f9727
- **Név** – RecommendationSystemApplication-1
- **Felhasználói azonosító** – RetailServiceAccount

Mentés és a képernyő bezárása. 

## <a name="turn-on-recommendations"></a>Termékjavaslatok bekapcsolása

A termékajánlások bekapcsolásához kövesse az alábbi lépéseket.

1. A Commerce Headquarters alkalmazásban keressen rá a **Szolgáltatások kezelése** lehetőségre.
1. Válassza a **Mind** lehetőséget, ha meg szeretné tekinteni a rendelkezésre álló szolgáltatások listáját. 
1. A Keresés mezőbe írja be az **Ajánlatok** kifejezést.
1. Válassza ki a **Termékajánlatok** funkciót.
1. A **Termékajánlatok** tulajdonságok ablaktáblán válassza az **Engedélyezés most** lehetőséget.

![Termékjavaslatok bekapcsolása](./media/FeatureManagement_Recommendations.PNG)

> [!NOTE]
> Ez az eljárás elindítja a termékjavaslati listák létrehozásának folyamatát. A listák elérhetővé tételéhez akár több óra szükséges lehet, és a pénztárban (POS) vagy a Dynamics 365 Commerce szolgáltatásban lehet megtekinteni.

## <a name="configure-recommendation-list-parameters"></a>A javaslati lista paramétereinek konfigurálása

Alapértelmezés szerint az AI-ML-alapú termékjavaslati lista javasolt értékeket tartalmaz. Az alapértelmezett javasolt értékek módosíthatók, hogy megfeleljenek az Ön vállalatának. Az alapértelmezett paraméterek módosításával kapcsolatos további tudnivalókat az [AI-ML-alapú termékajánlás eredményeinek kezelése](modify-product-recommendation-results.md) témakörben talál.

## <a name="show-recommendations-on-pos-devices"></a>Javaslatok megjelenítése pénztáreszközökön

Miután engedélyezte a javaslatokat a Commerce háttérirodában, hozzá kell adnia a javaslatok panelt a vezérlő pénztárképernyőhöz az elrendezés eszközzel. A folyamattal kapcsolatos további tudnivalókat lásd: [Ajánlások hozzáadása egy a POS-eszközök tranzakció lapjának vezérléséhez](add-recommendations-control-pos-screen.md). 

## <a name="enable-personalized-recommendations"></a>Személyre szabott ajánlatok engedélyezése

A Dynamics 365 Commerce programban a kiskereskedők a személyre szabott termékajánlatokat (más néven személyre szabásokat) tehetnek elérhetővé. Ily módon a személyre szabott ajánlások belefoglalhatók az online felhasználói élménybe és a pénztárba. Ha be van kapcsolva a személyre szabási funkció, akkor a rendszer társíthatja a felhasználó beszerzési és termékinformációit az egyéni ajánlások előállításához.

Ha további tájékoztatást szeretne a személyre szabott ajánlásokról, lásd: [Személyre szabott ajánlatok engedélyezése](personalized-recommendations.md).

## <a name="additional-resources"></a>További erőforrások

[Termékajánlatok áttekintése](product-recommendations.md)

[Az Azure Data Lake Storage engedélyezése a Dynamics 365 Commerce környezetben](enable-adls-environment.md)

[Személyre szabott ajánlatok engedélyezése](personalized-recommendations.md)

[A hasonlóak megvásárlására vonatkozó javaslatok engedélyezése](shop-similar-looks.md)

[Személyre szabott termékajánlatok kikapcsolása](personalization-gdpr.md)

[Termékajánlások hozzáadása a pénztárnál](product.md)

[Ajánlatok hozzáadása a tranzakciós képernyőhöz](add-recommendations-control-pos-screen.md)

[AI-ML ajánlások eredményeinek helyesbítése](modify-product-recommendation-results.md)

[Válogatott ajánlások manuális létrehozása](create-editorial-recommendation-lists.md)

[Ajánlások létrehozása bemutató adatokkal](product-recommendations-demo-data.md)

[Termékajánlatok GYIK-je](faq-recommendations.md)

