---
title: Termékajánlatok a POS esetében
description: Ez a témakör leírja a termék ajánlásainak használatát a pénztári eszközön (POS).
author: bebeale
manager: AnnBe
ms.date: 10/01/19
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 259664
ms.assetid: 5dd8db08-cd96-4f7e-9e65-b05ca815d580
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: c78fc1f2f1bb08d01828a8b71ad5d3c16ad31b86
ms.sourcegitcommit: 5b53bdafa5cb9a1279576bfece0452a50383b122
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/01/2019
ms.locfileid: "2278380"
---
# <a name="product-recommendations-on-pos"></a>Termékajánlatok a POS esetében

[!include [banner](includes/banner.md)]

A termék ajánlásai egy átalakító üzleti alkalmazás, amely az összes kiskereskedelmi területen átível a gazdag, vonzó és testreszabott termék-felfedezési élmények létrehozásához. Ha a POS rendszerhez szeretné végrehajtani ezt a funkciót, [akkor kövesse a lépéseket a POS-eszközökkel kapcsolatos javaslatok hozzáadásához.](add-recommendations-control-pos-screen.md) 

A termék ajánlásaival kapcsolatos további tudnivalókat lásd a [termék ajánlásainak áttekintése című témakörben.](../commerce/product-recommendations.md) 

## <a name="scenarios"></a>Esetek

Az alábbi POS-esetekben engedélyezettek a termékajánlások. A felhő POS vagy a modern POS (MPOS) esetében állnak rendelkezésre.

1. A **Termékadatok kezelése** oldalon:

    - • Ha az üzlet alkalmazottja megnyitja valamelyik **Termékadatok** oldalt, amikor az előző tranzakciókat nézi meg különböző csatornákat lefedve, az ajánlások szolgáltatás további elemeket javasol, amelyek várhatóan együtt fognak megvásárolni.

    [![Javaslatok a Termék részletei oldalon](./media/proddetails.png)](./media/proddetails.png)

2. A **Tranzakció** oldalon:

    - • Az ajánlási motor a kosárban lévő, gyakran együttesen vásárolt cikkek teljes listája alapján javasolja a cikkek elemeit.

    > [!NOTE]
    > Javaslatok megjelenítéséhez a **Tranzakció** lapon a kiskereskedőnek frissítenie kell a képernyő-elrendezést a Dynamics 365 for Retail rendszerben. Az **Ajánlások** vezérlőt rá kell húzni a **Tranzakció** oldalra.

    [![Javaslatok a Tranzakció oldalon](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)

## <a name="configure-dynamics-365-retail-to-enable-pos-recommendations"></a>A Dynamics 365 Retail konfigurálása pénztárjavaslatok engedélyezéséhez

A termékajánlások beállításához kövesse az alábbi lépéseket:

1. Győződjön meg arról, hogy a szolgáltatás frissítve lett a **10.0.6 build számára.**
2. Kövesse a [termékajánlások](../commerce/enable-product-recommendations.md) a saját vállalkozása számára történő engedélyezésének utasításait.
3. Választható lehetőség: Javaslatok megjelenítéséhez a tranzakciók képernyőn, menjen a **Képernyőelrendezés** lehetőséghez, válassza ki a képernyőelrendezést, indítsa el a **Képernyő-elrendezés tervezőjét**, majd helyezze az **ajánlások** vezérlőjét oda, ahová szükséges.
4. Keresse fel a **Kiskereskedelmi paraméterek** elemet, válassza **Gépi tanulás** elemet, jelölje be az **Igen** lehetőséget **POS-ajánlások engedélyezése** alatt.
5. A javaslatok megtekintéséhez a POS-on, futtassa az **1110** globális konfigurációs feladatot. A POS képernyő-elrendezés tervezőjén végzett módosítások megjelenítéséhez futtassa az **1070** csatorna konfigurációs feladatot.



## <a name="troubleshoot-issues-where-you-have-product-recommendations-already-enabled"></a>Már engedélyezett termékajánlások esetében problémák elhárítása

- Keresse meg a **Kiskereskedelmi paraméterek** \> **Ajánlási lista** \> **Termékajánlások letiltása** elemet, és futtassa a **Globális konfiguráció feladat \[9999\]** elemet. 
- Ha az **Ajánlások vezérlőelem** hozzá van adva a tranzakcióképernyőhöz a **Képernyő-elrendezés tervezője** használatával, távolítsa el azt is.
- További tájékoztatásért tekintse meg: [Javaslatok GYIK](../commerce/faq-recommendations.md).

## <a name="additional-resources"></a>További erőforrások

[Ajánlások vezérlő hozzáadása egy POS-eszköz tranzakció lapján](add-recommendations-control-pos-screen.md)
[Termékajánlatok áttekintése](../commerce/product-recommendations.md)
[Termékajánlatok engedélyezése](../commerce/enable-product-recommendations.md) 
