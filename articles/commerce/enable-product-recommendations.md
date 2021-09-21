---
title: Termékajánlatok engedélyezése
description: Ez a témakör azt mutatja be, hogyan lehet olyan termékjavaslatokat létrehozni, amelyek a Microsoft Dynamics 365 Commerce-felhasználók számára elérhető mesterséges intelligencia gépi tanulás (AI-ML) technológián alapulnak.
author: bebeale
ms.date: 08/31/2021
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 4a7be82b3a40aba621693f080ff41767fdaea474
ms.sourcegitcommit: 98061a5d096ff4b9078d1849e2ce6dd7116408d1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/01/2021
ms.locfileid: "7466316"
---
# <a name="enable-product-recommendations"></a>Termékajánlatok engedélyezése

[!include [banner](includes/banner.md)]

Ez a témakör azt mutatja be, hogyan lehet olyan termékjavaslatokat létrehozni, amelyek a Microsoft Dynamics 365 Commerce-felhasználók számára elérhető mesterséges intelligencia gépi tanulás (AI-ML) technológián alapulnak. A termékajánlási listákkal kapcsolatos további tudnivalókat lásd: [Termékajánlások áttekintése](product-recommendations.md).

## <a name="recommendations-pre-check"></a>Javaslatok előzetes ellenőrzése

1. Győződjön meg róla, hogy érvényes Dynamics 365 Commerce ajánlatok licenccel rendelkezik.
1. Győződjön meg arról, hogy az entitástár kapcsolódik egy vevő által birtokolt Azure Data Lake Storage Gen2-fiókhoz. További információ: [Győződjön meg róla, hogy az Azure Data Lake Storage-t megvásárolták és sikeresen hitelesítették a környezetben](enable-ADLS-environment.md).
1. Győződjön meg róla, hogy az Azure AD identitáskonfiguráció tartalmaz egy Ajánlási bejegyzést. A művelet végrehajtásával kapcsolatos további információk az alábbiakban láthatók.
1. Győződjön meg arról, hogy az entitástár napi frissítése be lett ütemezve a Azure Data Lake Storage Gen2-höz. A további tudnivalókat lásd: [Győződjön meg róla, hogy az entitástár frissítés automatizált](../fin-ops-core/dev-itpro/data-entities/entity-store-data-lake.md).
1. Engedélyezze a RetailSale-mértékeket az entitástárhoz. A folyamat beállításával kapcsolatos további tudnivalókat lásd: [Intézkedések használata](/dynamics365/ai/customer-insights/pm-measures).

A fenti lépések befejezése után készen áll az ajánlások engedélyezésére.

## <a name="azure-ad-identity-configuration"></a>Azure AD identitáskonfiguráció

Ezt a lépést csak az olyan vevőknek kötelező megadni, akik szolgáltatott infrastruktúra (IaaS) konfigurációt futtatnak. Az Azure AD identitáskonfiguráció automatikus a Azure Service Fabric-ben futó vevők esetében, de ajánlott ellenőrizni, hogy a beállítás az elvárásoknak megfelelően van-e konfigurálva.

### <a name="setup"></a>Beállítás

1. A Commerce központban keresse meg az **Azure Active Directory alkalmazások** oldalt.
1. Ellenőrizze, hogy létezik-e bejegyzés a következőhöz: **RecommendationSystemApplication-1**. Ha nem létezik bejegyzés, hozzon létre egyet a következő információk alapján:

    - **Ügyfél-azonosító**: d37b07e8-dd1c-4514-835d-8b918e6f9727
    - **Név**: RecommendationSystemApplication-1
    - **Felhasználói azonosító**: RetailServiceAccount

1. Mentés és a képernyő bezárása. 

## <a name="turn-on-recommendations"></a>Termékjavaslatok bekapcsolása

A termékajánlások bekapcsolásához kövesse az alábbi lépéseket.

1. A Commerce Headquarters alkalmazásban keressen rá a **Szolgáltatások kezelése** lehetőségre.
1. Válassza a **Mind** lehetőséget, ha meg szeretné tekinteni a rendelkezésre álló szolgáltatások listáját. 
1. A Keresés mezőbe írja be az **Ajánlatok** kifejezést.
1. Válassza ki a **Termékajánlatok** funkciót.
1. A **Termékajánlatok** tulajdonságok ablaktáblán válassza az **Engedélyezés most** lehetőséget.

![Javaslatok bekapcsolása.](./media/FeatureManagement_Recommendations.PNG)

> [!NOTE]
> - A fenti eljárás elindítja a termékjavaslati listák létrehozásának folyamatát. A listák elérhetővé tételéhez akár több óra szükséges lehet, és a pénztárban (POS) vagy a Dynamics 365 Commerce szolgáltatásban lehet megtekinteni.
> - Ez a konfiguráció nem engedélyezi az ajánlások minden funkcióját. A speciális funkciókat, például a személyre szabott ajánlásokat, a "hasonló szettek vásárlása" és a "hasonló leírású termékek vásárlása" ajánlásokat dedikált funkciókezelési bejegyzések vezérlik. A Commerce központ ezen funkcióinak engedélyezésével kapcsolatos tudnivalókat lásd: [Személyre szabott ajánlatok engedélyezése](personalized-recommendations.md), [„Hasonló szettek vásárlása” javaslatok engedélyezése](shop-similar-looks.md) és [„Hasonló leírású termékek vásárlása” javaslatok engedélyezése](shop-similar-description.md).

## <a name="configure-recommendation-list-parameters"></a>A javaslati lista paramétereinek konfigurálása

Alapértelmezés szerint az AI-ML-alapú termékjavaslati lista javasolt értékeket tartalmaz. Az alapértelmezett javasolt értékek módosíthatók, hogy megfeleljenek az Ön vállalatának. Az alapértelmezett paraméterek módosításával kapcsolatos további tudnivalókat az [AI-ML-alapú termékajánlás eredményeinek kezelése](modify-product-recommendation-results.md) témakörben talál.

## <a name="include-recommendations-in-e-commerce-experiences"></a>Ajánlatok felvétele az e-kereskedelmi tapasztalatokba

Miután engedélyezte az ajánlatokat a Commerce központ számára, az ajánlatok eredményeinek megjelenítésére használt Commerce-modulok készen állnak az e-kereskedelmi tapasztalatok konfigurálára. További információ: [Termékgyűjtemény-modulok](product-collection-module-overview.md).

## <a name="show-recommendations-on-pos-devices"></a>Javaslatok megjelenítése pénztáreszközökön

Miután engedélyezte az ajánlatokat a Commerce központban, hozzá kell adnia az ajánlatok panelt a pénztár vezérlése képernyőhöz az elrendezés eszközzel. A folyamattal kapcsolatos további tudnivalókat lásd: [Ajánlások hozzáadása egy a POS-eszközök tranzakció lapjának vezérléséhez](add-recommendations-control-pos-screen.md). 

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



[!INCLUDE[footer-include](../includes/footer-banner.md)]
