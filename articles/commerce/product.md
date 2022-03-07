---
title: Termékajánlatok hozzáadása a pénztárnál
description: Ez a témakör leírja a termék ajánlásainak használatát a pénztári eszközön (POS).
author: bebeale
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailParameters
audience: Application User
ms.reviewer: josaw
ms.custom: 259664
ms.assetid: 5dd8db08-cd96-4f7e-9e65-b05ca815d580
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 29f502df7c158611df4eb2ddd5ac0e6bd6b4fe628113b2c544e33ba9c41cbcc7
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6763740"
---
# <a name="add-product-recommendations-on-pos"></a>Termékajánlatok hozzáadása a pénztárnál

[!include [banner](includes/banner.md)]

A termékajánlások egy átalakító üzleti alkalmazás, amely az összes kereskedelmi területen átível a gazdag, vonzó és testreszabott termék-felfedezési élmények létrehozásához. Ha a POS rendszerhez szeretné végrehajtani ezt a funkciót, [akkor kövesse a lépéseket a POS-eszközökkel kapcsolatos javaslatok hozzáadásához.](add-recommendations-control-pos-screen.md) 

A termék ajánlásaival kapcsolatos további tudnivalókat lásd a [termék ajánlásainak áttekintése című témakörben.](../commerce/product-recommendations.md) 

## <a name="scenarios"></a>Esetek

Az alábbi POS-esetekben engedélyezettek a termékajánlások. A felhő POS vagy a modern POS (MPOS) esetében állnak rendelkezésre.

1. A **Termékadatok kezelése** oldalon:

    - Ha az üzlet alkalmazottja megnyitja valamelyik **Termékadatok** oldalt, amikor az előző tranzakciókat nézi meg különböző csatornákon keresztül, az ajánlások szolgáltatás további elemeket javasol, amelyek várhatóan együtt fognak megvásárolni.

    [![Javaslatok a Termék részletei oldalon.](./media/proddetails.png)](./media/proddetails.png)

2. A **Tranzakció** oldalon:

    - Az ajánlási motor a kosárban lévő, gyakran együttesen vásárolt cikkek teljes listája alapján javasolja a cikkek elemeit.

    > [!NOTE]
    > Javaslatok megjelenítéséhez a **Tranzakció** lapon a kiskereskedőnek frissítenie kell a képernyő-elrendezést a Dynamics 365 Commerce rendszerben. Az **Ajánlások** vezérlőt rá kell húzni a **Tranzakció** oldalra.

    [![Javaslatok a Tranzakció oldalon.](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)

## <a name="configure-commerce-to-enable-pos-recommendations"></a>A Commerce konfigurálása pénztárjavaslatok engedélyezéséhez

A termékajánlások beállításához kövesse az alábbi lépéseket:

1. Győződjön meg arról, hogy a szolgáltatás frissítve lett a **10.0.6 build számára.**
2. Kövesse a [termékajánlások](../commerce/enable-product-recommendations.md) a saját vállalkozása számára történő engedélyezésének utasításait.
3. Választható lehetőség: Javaslatok megjelenítéséhez a tranzakciók képernyőn, menjen a **Képernyőelrendezés** lehetőséghez, válassza ki a képernyőelrendezést, indítsa el a **Képernyő-elrendezés tervezőjét**, majd helyezze az **ajánlások** vezérlőjét oda, ahová szükséges.
4. Keresse fel a **Commerce paraméterek** elemet, válassza **Gépi tanulás** elemet, jelölje be az **Igen** lehetőséget **POS-ajánlások engedélyezése** alatt.
5. A javaslatok megtekintéséhez a POS-on, futtassa az **1110** globális konfigurációs feladatot. A POS képernyő-elrendezés tervezőjén végzett módosítások megjelenítéséhez futtassa az **1070** csatorna konfigurációs feladatot.

## <a name="troubleshoot-issues-where-you-have-product-recommendations-already-enabled"></a>Már engedélyezett termékajánlások esetében problémák elhárítása

- Keresse meg a **Commerce paraméterek** \> **Ajánlási lista** \> **Termékajánlások letiltása** elemet, és futtassa a **Globális konfiguráció feladat \[9999\]** elemet. 
- Ha az **Ajánlások vezérlőelem** hozzá van adva a tranzakcióképernyőhöz a **Képernyő-elrendezés tervezője** használatával, távolítsa el azt is.
- További tájékoztatásért tekintse meg: [Termékjavaslatok GYIK](../commerce/faq-recommendations.md).

## <a name="additional-resources"></a>További erőforrások

[Termékajánlatok áttekintése](product-recommendations.md)

[Az Azure Data Lake Storage engedélyezése a Dynamics 365 Commerce környezetben](enable-adls-environment.md)

[Termékajánlatok engedélyezése](enable-product-recommendations.md)

[Személyre szabott ajánlatok engedélyezése](personalized-recommendations.md)

[Személyre szabott termékajánlatok kikapcsolása](personalization-gdpr.md)

[A hasonlóak megvásárlására vonatkozó javaslatok engedélyezése](shop-similar-looks.md)

[Ajánlatok hozzáadása a tranzakció képernyőjéhez](add-recommendations-control-pos-screen.md)

[AI-ML ajánlások eredményeinek helyesbítése](modify-product-recommendation-results.md)

[Válogatott ajánlások manuális létrehozása](create-editorial-recommendation-lists.md)

[Ajánlások létrehozása bemutató adatokkal](product-recommendations-demo-data.md)

[Termékajánlatok GYIK-je](faq-recommendations.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]