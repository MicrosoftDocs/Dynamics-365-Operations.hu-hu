---
title: Termékajánlatok engedélyezése
description: Ez a cikk bemutatja, hogy hogyan lehet a vevők számára elérhetővé tenni olyan termékajánlásokat, amelyek a visszaható intelligencia – gépi tanuláson (AI-FOG) alapulnak Microsoft Dynamics 365 Commerce.
author: bebeale
ms.date: 09/08/2022
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
ms.openlocfilehash: fc1b43fa70e6652d38b1141e2d93cf323f70a756
ms.sourcegitcommit: f88273627ba105ede27f28fe67ccec2d7f78261c
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/09/2022
ms.locfileid: "9460021"
---
# <a name="enable-product-recommendations"></a>Termékajánlatok engedélyezése

[!include [banner](includes/banner.md)]

Ez a cikk bemutatja, hogy hogyan lehet a vevők számára elérhetővé tenni olyan termékajánlásokat, amelyek a visszaható intelligencia – gépi tanuláson (AI-FOG) alapulnak Microsoft Dynamics 365 Commerce. A termékajánlási listákkal kapcsolatos további tudnivalókat lásd: [Termékajánlások áttekintése](product-recommendations.md).

## <a name="recommendations-pre-check"></a>Javaslatok előzetes ellenőrzése

1. Győződjön meg róla, hogy érvényes Dynamics 365 Commerce ajánlatok licenccel rendelkezik.
1. Győződjön meg arról, hogy az entitástár kapcsolódik egy vevő által birtokolt Azure Data Lake Storage Gen2-fiókhoz. További információ: [Győződjön meg róla, hogy az Azure Data Lake Storage-t megvásárolták és sikeresen hitelesítették a környezetben](enable-ADLS-environment.md).
1. Győződjön meg róla, hogy az Azure AD identitáskonfiguráció tartalmaz egy Ajánlási bejegyzést. A művelet végrehajtásával kapcsolatos további információk az alábbiakban láthatók.
1. Győződjön meg arról, hogy az entitástár napi frissítése be lett ütemezve a Azure Data Lake Storage Gen2-höz. A további tudnivalókat lásd: [Győződjön meg róla, hogy az entitástár frissítés automatizált](../fin-ops-core/dev-itpro/data-entities/entity-store-data-lake.md).
1. Engedélyezze a RetailSale-mértékeket az entitástárhoz. A folyamat beállításával kapcsolatos további tudnivalókat lásd: [Intézkedések használata](/dynamics365/ai/customer-insights/pm-measures).
1. Győződjön meg arról, hogy a környezetben konfigurálva vannak az aktuálisan támogatott régiók kiszolgáló és régiói a következők szerint:

    - **Támogatott érintett régiók:** EU/US/CA/AU.
    - **Támogatott kiszolgáló régiók:** USA/CA/AU. Ha a kiszolgáló régió nem felel meg a meglévő támogatott régiók egyikének, az ajánlások szolgáltatás a legközelebb támogatott kiszolgáló régiót választja.

A fenti lépések befejezése után készen áll az ajánlások engedélyezésére.

> [!NOTE]
> Van egy ismert probléma, ahol az ajánlások nem jelennek meg a következő lépések után. Ezt a problémát az adatáramlási problémák okozják a környezetben. Ha a környezetben nem mutatja az ajánlási eredményeket, konfigurálja az ajánlások szolgáltatásának alternatív adatait úgy, [hogy az ajánlásokhoz egy alternatív adatfolyamot hoz létre](set-up-alternate-data-flow.md). Ezekhez a lépésekhez azure rendszergazdai jogosultsággal kell rendelkeznie. Ha segítségre van szüksége, forduljon a FastTrack képviselőjhez.

## <a name="azure-ad-identity-configuration"></a>Azure AD identitáskonfiguráció

Ez a lépés csak akkor szükséges, ha a vevők szolgáltatáskonfigurációként (IaaS) futtatnak egy infrastruktúrát. Azure AD az identitás konfigurációja automatikus a Azure Service Fabric futó vevők esetében, de javasoljuk, hogy ellenőrizze, hogy a beállítás a várt módon van-e beállítva.

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

[Alternatív adatfolyam beállítása ajánlásokhoz](set-up-alternate-data-flow.md)

[Személyre szabott ajánlatok engedélyezése](personalized-recommendations.md)

[„Hasonló szettek vásárlása” javaslatok engedélyezése](shop-similar-looks.md)

[Személyre szabott termékajánlatok kikapcsolása](personalization-gdpr.md)

[Termékajánlások hozzáadása a pénztárnál](product.md)

[Ajánlatok hozzáadása a tranzakciós képernyőhöz](add-recommendations-control-pos-screen.md)

[AI-ML ajánlások eredményeinek helyesbítése](modify-product-recommendation-results.md)

[Válogatott ajánlások manuális létrehozása](create-editorial-recommendation-lists.md)

[Ajánlások létrehozása bemutató adatokkal](product-recommendations-demo-data.md)

[Termékajánlatok GYIK-je](faq-recommendations.md)




[!INCLUDE[footer-include](../includes/footer-banner.md)]
