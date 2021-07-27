---
title: Pénzforgalmi előrejelzés (előzetes verzió)
description: Ez a témakör a Pénzforgalmi előrejelzési képességet mutatja be.
author: ShivamPandey-msft
ms.date: 06/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom:
- "14151"
- intro-internal
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-05-19
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 3f16c8471123969443af52ff9bed7fc017b8e9c2
ms.sourcegitcommit: 92ff867a06ed977268ffaa6cc5e58b9dc95306bd
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/03/2021
ms.locfileid: "6339215"
---
# <a name="cash-flow-forecast-preview"></a>Pénzforgalmi előrejelzés (előzetes verzió)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

A pénzforgalom kritikus fontosságú minden üzleti tevékenységhez. Még a nyereséges vállalatok is szembesülnek a fizetésképtelenséggel, ha nem tartják fenn a pénzforgalmat, amivel meg tudnak felelni az azonnali igényeknek. A pénzforgalmi előrejelzések pénzforgalmi előrejelzési képessége segít a vállalatoknak a pénzforgalmi egyenleg hatékony nyomon követésében és kezelésében. Ez a funkció a gépi tanulást használja a vállalatok számára, hogy a korábbinál pontosabban előrejelzést nyújtson a pénzforgalomhoz. Ezenkívül segítséget nyújt a menedzsereknek a lehetőségek optimalizálása érdekében, hogy az aktuális készpénzpozíció kontextusában optimalizálják a lehetőségeket. 

A legtöbb vállalatnál a pénzforgalom kezelése és a pénzforgalmi előrejelzések futtatása unalmas, ismétlődő és manuális művelet. A legtöbb vállalat a különböző komplexitású Microsoft Excel-megoldásokra támaszkodik. A pénzforgalom pontos előrejelzésének kihívásai a következők:

- Az adatok nem érhetők el a döntéshozók számára, mert több helyen elszórtan találhatók, többek között a következők: 
  - A könyvelés vagy a vállalati erőforrástervezési rendszer
  - Pénzügyi tervezési szoftver
  - Excel
  - További szoftveralkalmazások 
- Az előrejelzés alapja a belső tudás, amely az egyes tartományokon vagy osztályokon belül a „silókban” található.
- A Pénzforgalmi előrejelzés pontosságának mérése a pénzeszközök felfrissítését követően bizonytalan és nehézkes.
    
## <a name="details-of-the-cash-flow-forecasts-capability"></a>A pénzforgalmi előrejelzések funkcióval kapcsolatos részletek
A Pénzforgalmi előrejelzések funkció a következő lehetőségeket tartalmazza. 

- Segítségével egyszerű a pénzforgalmi adatok külső rendszerekből Dynamics 365 Finance-be történő integrálása. A pénzforgalmi előrejelzések az adatimport, -export keretrendszer használatára is használhatók. Ez a keretrendszer megkönnyíti az Excel OData-val történő integrációt. Egy átfogó pénzforgalmi megoldást több forrásból származó adatok egyesítésével is lehet létrehozni. 

- Intelligens készpénzpozíciót vezet be. A készpénzpozíció létrehozása a vevői fizetési mód alapján történik, amely azt jelzi, hogy a vállalat mikorra várhatja a számlájára a bejövő összeget. A fizető szállítók múltbeli feladatainak elemzésével azt is megjósolhatja, hogy a jövőbeli számlákat és rendeléseket valószínűleg mikor fizetik ki. 

- Bemutatja az intelligens pénzforgalmi előrejelzést a hosszú távú előrejelzésekhez, az idősor előrejelzést használva az AI Builder automatizált integrációján keresztül.

- Lehetőséget nyújt bizonyos pénzforgalmi helyzetek vagy előrejelzések mentésére, szerkesztésére, majd az előrejelzési teljesítmény tényleges pénzügyekkel való egyszerű összehasonlítására és mérésére.

- A mi lenne, ha elemzést engedélyezi a pillanatkép összehasonlításon keresztül. Létrehozhat például több pillanatképet, amely optimista, pesszimista vagy a pénzforgalom leginkább valósághű nézeteit jeleníti meg, majd összevetheti és megtekintheti a különbségeket.

- Lehetőséget nyújt a pénzforgalmi előrejelzések több pénznemben történő megtekintésére jogi személyek között, valamint a bankszámlához kapcsolódó pénzforgalom szűrésére és megtekintésére. 

- A pénzügyi dimenziókkal kapcsolatos bankszámlák szűrését és megjelenítését teszi lehetővé.

A pénzforgalom-előrejelzési funkció segíti a szervezetet, hogy az unalmas, összetett, mégis ismétlődő pénzforgalmi előrejelzést egyszerű, automatizált folyamatra alakítsa át a Dynamics 365 Finance-ben. A pénzforgalmi előrejelzések leginkább unalmas aspektusainak automatizálása lehetővé teszi a kritikus döntések meghozatalát a kívánt üzleti eredmények eléréséhez.

## <a name="setting-up-dimensions-for-cash-flow-forecasting"></a>A Pénzforgalmi előrejelzés dimenzióinak beállítása
A **Pénzforgalmi előrejelzés beállítása** lap egy új lapján beállíthatja, hogy milyen pénzügyi dimenziókat kell használni a **Pénzforgalmi előrejelzés** munkaterületen végzett szűréshez. Ez a lap csak akkor jelenik meg, ha engedélyezve van a Pénzforgalmi előrejelzések funkció. 

A **Dimenziók** fülön válassza ki a szűréshez használni kívánt dimenziók listáját, és a nyilakkal helyezze át őket a jobb oldali oszlopba. A pénzforgalmi előrejelzések adatainak szűréséhez csak két dimenzió választható ki. 

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
