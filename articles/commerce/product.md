---
title: Termékajánlatok hozzáadása a pénztárnál
description: Ez a témakör a pénztári eszközökre vonatkozó termékajánlásokat ismerteti.
author: bebeale
ms.date: 09/08/2022
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
ms.openlocfilehash: 170e2bf18aefc79a796620818c7100ff8e6e689a
ms.sourcegitcommit: f88273627ba105ede27f28fe67ccec2d7f78261c
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/09/2022
ms.locfileid: "9460056"
---
# <a name="add-product-recommendations-on-pos"></a>Termékajánlatok hozzáadása a pénztárnál

[!include [banner](includes/banner.md)]

A termékajánlások egy átalakító üzleti alkalmazás, amely az összes kereskedelmi területen átível a gazdag, vonzó és testreszabott termék-felfedezési élmények létrehozásához. Ha a POS rendszerhez szeretné végrehajtani ezt a funkciót, [akkor kövesse a lépéseket a POS-eszközökkel kapcsolatos javaslatok hozzáadásához.](add-recommendations-control-pos-screen.md) 

A termék ajánlásaival kapcsolatos további tudnivalókat lásd a [termék ajánlásainak áttekintése című témakörben.](../commerce/product-recommendations.md) 

## <a name="scenarios"></a>Esetek

Az alábbi POS-esetekben engedélyezettek a termékajánlások. A felhő POS vagy a modern POS (MPOS) esetében állnak rendelkezésre.

1. A **Termékadatok kezelése** oldalon:

    - Ha egy üzlet felkeresi a Termék részletei lapot, amikor különböző csatornákon keresztül keresi a **korábbi** tranzakciókat, az ajánlások szolgáltatás további, várhatóan együtt beszerzett cikkeket javasol. A **szolgáltatáshoz** **használt** bővítményektől függően a kiskereskedők hasonló megjelenést és az Üzletekhez hasonló leírási ajánlásokat adhatnak a termékekhez, valamint a korábbi beszerzési előzményekkel kapcsolatos, személyre szabható ajánlásoknak is.

    [![Javaslatok a Termék részletei oldalon.](./media/proddetails.png)](./media/proddetails.png)

2. A **Tranzakció** oldalon:

    - Az ajánlási motor a kosárban lévő, gyakran együttesen vásárolt cikkek teljes listája alapján javasolja a cikkek elemeit.

    > [!NOTE]
    > Javaslatok megjelenítéséhez a **Tranzakció** lapon a kiskereskedőnek frissítenie kell a képernyő-elrendezést a Dynamics 365 Commerce rendszerben. Az **Ajánlások** vezérlőt rá kell húzni a **Tranzakció** oldalra.

    [![Javaslatok a Tranzakció oldalon.](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)

## <a name="configure-commerce-to-enable-pos-recommendations"></a>A Commerce konfigurálása pénztárjavaslatok engedélyezéséhez 

A termék ajánlásának beállításához erősítse meg, hogy befejezte a Commerce termék-ajánlások [létesítási folyamatát a termékajánlásokat engedélyező lépések segítségével](../commerce/enable-product-recommendations.md). Alapértelmezés szerint az ajánlások **mind** **a** Termék részletei lapon, mind a Vevő adatai lapon megjelennek, miután befejezte a létesítés lépéseit, és az adatok sikeresen megfőzöttek. 

## <a name="add-recommendations-to-the-transaction-screen"></a>Ajánlatok hozzáadása a tranzakció képernyőjéhez

1. Ha ajánlásokat szeretne hozzáadni a tranzakciós képernyőhöz, kövesse az [Ajánlások hozzáadása a tranzakciós képernyőhöz lépéseit](add-recommendations-control-pos-screen.md).
1. A POS képernyőelrendezés-tervezőben végzett módosítások tükrözéséhez futtassa **a 1070-es** csatorna-konfigurációs feladatot a Commerce Headquarters alkalmazáson.

> [!NOTE] 
> Ha a RecoMock vesszővel elválasztott értékeket (CSV) fájllal szeretné engedélyezni a POS-ajánlások engedélyezését, az elrendezéskezelő konfigurálása előtt telepítenie kell a CSV-fájlt Microsoft Dynamics a Lifecycle Services (LCS) eszköztárára. Ha a RecoMock CSV fájlt használja, akkor nem kell engedélyeznie az ajánlásokat. A CSV-fájl csak bemutató céljára érhető el. Ajánlott az olyan vevőknek vagy megoldástervezőknek, akik az ajánlási listák megjelenését bemutató jellegű megjelenési célokra is le szeretnék utánozni anélkül, hogy meg kellene vásárolniuk egy kiegészítő stock keeping unit (SKU) adatokat.

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
