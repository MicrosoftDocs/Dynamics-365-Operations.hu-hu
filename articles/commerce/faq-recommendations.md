---
title: Termékajánlatok GYIK-je
description: Ez a témakör a termékajánlások vagy azok eredményeivel kapcsolatos problémák elhárításához használható folyamatokkal és eszközökkel kapcsolatban tartalmaz tájékoztatást.
author: bebeale
manager: AnnBe
ms.date: 10/1/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: ''
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, Core, Operations
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 7951f92ef68a7a782f2874d7b73d7e45eba0afba
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/01/2020
ms.locfileid: "3003027"
---
# <a name="product-recommendations-faq"></a>Termékajánlatok GYIK-je


[!include [banner](includes/banner.md)]

Ez a témakör a [termékajánlások](product-recommendations.md) vagy azok eredményeivel kapcsolatos problémák elhárításához használható folyamatokkal és eszközökkel kapcsolatban tartalmaz tájékoztatást.

## <a name="best-practices"></a>Gyakorlati tanácsok
Nagyon fontos az alaptermék és változatai fogalmának hasznosítása. Egy adott szülő alaptermék változatainak ésszerű csoportosítása segít a listaalgoritmusoknak és a szolgáltatásnak a jobb modellek létrehozásában. A szolgáltatás ezenkívül a termék egyetlen példányát is kiszolgálhatja ahelyett, hogy egy listára helyezné az összes közeli kapcsolatban álló változatot. Ha minden szorosan kapcsolódó változat szerepel egy listán, akkor hibás vagy ismétlődő eredmények léphetnek fel.

## <a name="why-are-products-missing-from-my-recommendation-lists"></a>Miért hiányoznak a termékek a saját ajánlási listáimról?

Jellemzően, ha egy cikk hiányzik egy termékajánlási listáról, akkor termékkonfigurációs probléma állhat fenn. Előfordulhat például, hogy hibás a termék kezdési vagy befejezési dátuma, a dimenziót rosszul van konfigurálva, vagy a termék nem a megfelelő csatornaszortimentben található stb.

Ha egy mesterséges intelligencia-gép tanuláson (AI-ML) alapuló ajánlási listából hiányzik egy elem, előfordulhat, hogy az elem nem felel meg az ajánlási lista feltételeinek, vagy nem rendelkezik elegendő vásárlási tranzakcióval, hogy az ajánlási lista megjelenítse.

Javasoljuk, hogy ellenőrizze ezeket a lépéseket:
1. **Ellenőrizze, hogy engedélyezve vannak-e a termékajánlások a központban.** Ha további információt szeretne a szolgáltatás bekapcsolásáról, tekintse meg a következőt: [Termékajánlatok engedélyezése](enable-product-recommendations.md).
1. **Győződjön meg róla, hogy a legfontosabb terméktulajdonságok be vannak állítva.** A termékszortimenteket például **Tartalmazza** értékre kell beállítani.
1. **Az szortimentbe újonnan felvett termékek esetében akár 3 órát is igénybe vehet, hogy a termék megjelenjen az új listában.**
1. **Ha egy termék még nem jelenik meg a Népszerű, Legnépszerűbb, Másoknak ez is tetszett vagy a Gyakran együtt vásárolt részben, akkor előfordulhat, hogy a termék nem rendelkezik elég tranzakcióval.** Ebben az esetben megvárhatja a további tranzakciókat, frissítheti az alapértelmezett ajánlási lista paramétereit, vagy manuális beavatkozással módosíthatja az ajánlási terméklista találatait. Az ajánlási paraméterekkel kapcsolatos további tudnivalókért tekintse meg a következőt: [AI-ML-alapú termékajánlási találatok kezelése](modify-product-recommendation-results.md).
1. **Győződjön meg róla, hogy a termék megfelel a lista ajánlási feltételeinek.** A termékajánlási paraméterekkel kapcsolatos további tudnivalókért tekintse meg a következőt: [AI-ML-alapú termékajánlási találatok kezelése](modify-product-recommendation-results.md).

## <a name="how-can-i-prevent-poor-recommendation-results-from-being-returned"></a>Hogyan lehet megakadályozni, hogy a rendszer rossz minőségű ajánlási találatokat adjon vissza?

Az ajánlási listák esetében a találatok előállításához nagy mennyiségű tranzakcióra van szükség. Ezért fontos, hogy a felhasználók teljes körű múltbeli tranzakcióadatokat adjanak meg.

Ezenkívül a tranzakciókkal nem rendelkező vagy kevés tranzakcióval rendelkező termékek általában nem rendelkeznek **Másoknak ez is tetszett** vagy **Gyakran együtt vásárolt** találatokkal, és nem szerepelnek a **Népszerű** vagy **Legnépszerűbb** javaslati listában. Ez a helyzet gyakran előfordulhat nagyon új termékek esetében, illetve olyan régi termékek esetében, amelyeknél kis számú vásárlás történt. A népszerű új cikkek könnyedén leküzdik ezt a problémát.

Javasoljuk, hogy kövesse ezeket a lépéseket:
1. **Győződjön meg róla, hogy a termék megfelel a lista ajánlási feltételeinek.** A termékajánlási paraméterekkel kapcsolatos további tudnivalókért tekintse meg a következőt: AI-ML-alapú termékajánlási találatok módosítása.
1. **Ha a termék új, akkor érdemes módosítani egy ajánlási listát, amíg a termék több tranzakcióval nem rendelkezik.** Az ajánlási lista találatainak módosításával kapcsolatos további tudnivalókért tekintse meg a következőt: [AI-ML-alapú termékajánlási találatok kezelése](modify-product-recommendation-results.md).


- **Győződjön meg róla, hogy a termék megfelel a lista ajánlási feltételeinek.** A termékajánlási paraméterekkel kapcsolatos további tudnivalókért tekintse meg a következőt: [AI-ML-alapú termékajánlási találatok kezelése](modify-product-recommendation-results.md).
- **Ha a termék új, akkor érdemes módosítani egy ajánlási listát, amíg a termék több tranzakcióval nem rendelkezik**. Az ajánlási lista találatainak módosításával kapcsolatos további tudnivalókért tekintse meg a következőt: [AI-ML-alapú termékajánlási találatok kezelése](modify-product-recommendation-results.md).

## <a name="can-i-remove-a-product-but-still-see-it-in-the-store"></a>Eltávolíthatok egy terméket, és továbbra is láthatom az áruházban?

Lehetőség van az üzleti szükségletek felmerülése esetén az algoritmus alapján generált listák módosítására. Ha azonban egy terméket eltávolítanak egy ajánlási listából, a termék továbbra is megtalálható lesz az áruházban. A termékajánlások találatainak módosításával kapcsolatos további tudnivalókért tekintse meg a következőt: [AI-ML-alapú termékajánlási találatok kezelése](modify-product-recommendation-results.md).

Ha blokkolni kell egy cikket, hogy ne legyen megtalálható az áruházban, módosítania kell a **Cikkszortimentek** beállítást **Kihagyás** értékre.

## <a name="how-do-i-add-a-list-to-an-e-commerce-page"></a>Hogyan lehet listát hozzáadni az e-kereskedelmi oldalhoz?

A termékajánlási lapoknak az e-kereskedelmi webhelyhez történő hozzáadásával kapcsolatos további tudnivalókat lásd: [Termékajánlások listájának hozzáadása lapokhoz](add-reco-list-to-page.md).

## <a name="how-do-i-enable-recommendations-on-pos"></a>Hogyan engedélyezhetők ajánlások a POS-en?

A termékajánlások engedélyezése után hozzá kell adnia az ajánlások panelt a POS vezérlése képernyőhöz. Lásd [a funkció dokumentációját](https://docs.microsoft.com/en-us/dynamics365/unified-operations/retail/add-recommendations-control-pos-screen), amelyben további tájékoztatás található arról, hogy hogyan lehet hozzáadni az ajánlások panelt a POS-eszköz elrendezéséhez.

## <a name="additional-resources"></a>További erőforrások

[Termékajánlatok áttekintése](product-recommendations.md)

[Termékajánlatok engedélyezése](enable-product-recommendations.md)

[AI-ML-alapú termékajánlás eredményeinek kezelése](modify-product-recommendation-results.md)
