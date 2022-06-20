---
title: Vevő fizetési információi (Előzetes)
description: Ez a témakör a fizetéselemzési képességeket írja le, amelyek segítséget nyújtanak az egyes vevők jellemző fizetési gyakorlatának megértésében. A funkció segítségével azonosíthatja azokat a körülményeket, amelyek indokolják a begyűjtési folyamatok korábbi megkezdését, mint amilyennel egyébként tett volna.
author: ShivamPandey-msft
ms.date: 11/06/2019
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom:
- "14151"
- intro-internal
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2019-11-06
ms.dyn365.ops.version: AX 10.0.8
ms.openlocfilehash: 54655d2b1cfb4b11f32842d4c3cff2f4d8e97ef5
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8856799"
---
# <a name="customer-payment-insights-preview"></a>Vevő fizetési információi (Előzetes)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Ez a témakör a fizetéselemzési képességeket írja le, amelyek segítséget nyújtanak az egyes vevők jellemző fizetési gyakorlatának megértésében. A funkció segítségével azonosíthatja azokat a körülményeket, amelyek indokolják a begyűjtési folyamatok korábbi megkezdését, mint amilyennel egyébként tett volna. 

## <a name="overview"></a>Áttekintés

Nehéz lehet megjósolni, hogy a vevők mikor fizetik ki a számláikat. A háttérinformációk hiánya kevésbé pontos pénzforgalmi előrejelzéseket eredményezhet, túl későn elinduló beszedési folyamatokat, valamint rendelések kiadását olyan vevőknek, akik elmulaszthatják a kifizetést. A Vevői kifizetés információk (előzetes verzió) segít a szervezetkenk megjósolni a vevői számla kifizetését.. Ez az információ segíthet a szervezeteknek olyan gyűjteménystratégiák létrehozásában, amelyek javítják az időben történő kifizetés valószínűségét. 

## <a name="predictions"></a>Előrejelzések

A kifizetési előrejelzések lehetővé teszik a szervezetek számára, hogy javítsák az üzleti folyamataikat, mivel így könnyebben azonosíthatják azokat a számlákat, amelyeket valószínűleg késve fizetnek, és hogy a megfelelő intézkedéseket megtegyék, hogy javítsák az idejüket az időben történő kifizetésre.

Egy gépi tanulási modellt alkalmaznak, amely a múltbeli számlákat, a kifizetéseket és a vevői adatokat használja fel, a vevői kifizetéssel kapcsolatos háttériformációk (előzetes verzió) pontosabban jósolja meg, ha a vevő mikor fizeti ki a kiegyenlítetlen számlát.

Minden nyitott számla esetében a Vevői fizetési háttérinformációk (előzetes verzió) három fizetési valószínűséget jósolhat meg:

-   Időben történő fizetés valószínűsége 
-   Késve történő fizetés valószínűsége
-   Nagyon késedelmesen történő fizetés valószínűsége

A vevői kifizetéssel kapcsolatos háttérinformációk (előzetes verzió) a várható kifizetések összesített megjelenítését is lehetővé teszi annak érdekében, hogy a szervezetek megértsék a három kategória egyikében a vevőtől elvárható teljes kifizetett összeget, az időben, későn és nagyon későn kategóriákban.

[![Kifizetési előrejelzések összesített nézete.](./media/graphic-payment-reports.png)](./media/graphic-payment-reports.png)

Ezenkívül minden számlához hozzárendeli a rendszer az időben való fizetés valószínűségét. Ha az időben való fizetés valószínűsége 50%-nál alacsonyabb, akkor a rendszer a számlát piros körrel jelöli meg, amellyel jelzi, hogy ezekre a számlákra a beszedés fokozott figyelme szükséges. 

[![Kifizetési valószínűségek listája.](./media/customer-pymnt-probability-list.png)](./media/customer-pymnt-probability-list.png)

A vevői kifizetésre vonatkozó háttérinformációk (előzetes verzió) környezeti információkat is nyújt az előrejelzés magyarázataként, például az előrejelzést leginkább befolyásoló tényezők, a vevővel folytatott üzleti kapcsolat aktuális állapota, valamint részletek a múltbéli vevői kifizetési viselkedésről. A beszedési folyamat számos vállalkozásban reaktív tevékenység volt; a beszedési folyamat addig nem kezdődik, amíg a számlák esedékessé nem válnak. 

A vevői kifizetésekkel kapcsolatos háttérinformációk (előzetes verzió) segítségével a vállalatok proaktívabban kezelhetik a beszedéseket. A programnak már nem kell megvárnia a beszedési folyamat elkezdéséhez, hogy a tranzakciók esedékessé váljanak. Helyette a fizetési előrejelzési képességgel meghatározhatja, hogy a proaktív beszedések javítják-e az időben történő fizetés valószínűségét. A kifizetés előrejelzése azt is lehetővé teszi a vállalatok számára, hogy rendelkezzenek a beszedési folyamat korai megkezdéséhez szükséges információkkal.

## <a name="methodology"></a>Módszertan

Az AI-megoldások fejlesztése és bevezetése nehéz. Adatszakértők, adott téma szakértői és mérnökök csapatára van szükség, akik egy hosszabb ideig dolgoznak egy használható AI-megoldás kialakításán, fejlesztésén, üzembe helyezésén és karbantartásán. Az AI-megoldások a Finance modulban egyszerűen telepíthetők és használhatók. A Microsoftra épülő AI-megoldások előzetes kicsomagolása a Pénzügyben AI Builder. Egy végfelhasználó egyetlen kattintással telepítheti az AI-megoldást, és elindíthatja az intelligens előrejelzések előnyeinek kihasználását. Ha egy szervezet nem elégedett az előrejelzések pontosságával, egy kiemelt felhasználó, szintén egy kattintással újra beléphet az AI Builder bővítmény gyakorlatába, majd kiválaszthatja vagy törölheti azon mezők kiválasztását, amiket az előrejelzések létrehozásához szeretne használni. Ha készen áll, betaníthatják és közzétehetik a módosításokat, és az újonnan kiképzett modellt a rendszer automatikusan felveszi az előrejelzésekhez a Finance szolgáltatásban.

## <a name="how-to-get-customer-payment-insights-preview"></a>Hogyan szerezhetem be a Vevői fizetéssel kapcsolatos háttérinformációk (előzetes verzió) szolgáltatást

Küldjön e-mailt a [Vevői kifizetéssel kapcsolatos háttérinformációk (előzetes verzió)](mailto:fiap@microsoft.com) számára, ha szeretné kipróbálni a Vevői kifizetéssel kapcsolatos háttérinformációk (előzetes verzió) szolgáltatást.

## <a name="privacy-notice"></a>Adatvédelmi nyilatkozat

Az előnézetek (1) kisebb adatvédelmi és biztonsági intézkedésekre lehetnek szükség, mint a Dynamics 365 Pénzügy és műveletek szolgáltatás, (2) nem szerepelnek a szolgáltatás szolgáltatásiszint-szerződésében, (3) nem szabad használni a személyes adatok vagy más olyan adatok feldolgozására, amelyekre jogi vagy jogszabályban előírt megfelelési követelmények vonatkoznak, és (4) korlátozottan támogatja.




[!INCLUDE[footer-include](../../includes/footer-banner.md)]
