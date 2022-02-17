---
title: A Finance Insights kezdőlapja
description: A Pénzügyi információk konfigurálható és bővíthető modelleket biztosít, amelyek segítségével pontosan és intelligensen előrejelezheti a vállalat pénzforgalmát, előrejelezheti, hogy mikor kapja meg a fennmaradó kinnlévőségek kifizetését, és létrehoz egy költségvetési javaslatot, amely felgyorsíthatja a költségvetési folyamatot. Ezek a funkciók intelligens gépi tanulási modelleken alapulnak.
author: ShivamPandey-msft
ms.date: 01/27/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.custom:
- "14151"
- intro-internal
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-07-20
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 05b0de8b0104238a33f006234d4a0e8ba9fcdb2a
ms.sourcegitcommit: 7893ffb081c36838f110fadf29a183f9bdb72dd3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/02/2022
ms.locfileid: "8087293"
---
# <a name="finance-insights-home-page"></a>A Finance Insights kezdőlapja

[!include [banner](../includes/banner.md)]

A Finance Insights konfigurálható és bővíthető megoldásokat kínál, amelyek segítségével intelligensen megjósolhatja vállalata pénzforgalmát, megjósolhatja, hogy mikor kaphat kifizetést a fennálló követeléseiért, és olyan költségvetési javaslatot készíthet, amely felgyorsíthatja a költségvetési folyamatot. Ezek a funkciók intelligens gépi tanulási sablonokat használnak a modellek felépítéséhez az Ön által megadott adatok (beleértve egy harmadik féltől származó adatok, például egy iroda fogyasztói jelentési információi) felhasználásával. Ezek az intelligens képességek tájékoztatják a döntéshozatalt, és segítenek abban, hogy hatékonyan reagáljon a jelenlegi és várható üzleti kihívásokra. Ön felelős minden olyan adatért, amelyet a Finance insightokkal együtt használnak fel, vagy azokból kiadnak.

> [!NOTE]
> A Finance Insights az Amerikai Egyesült Államokban, Kanadában, az Egyesült Királyságban, Európában, Ázsia-csendes-óceáni térségben, Japánban, Ausztráliában és Új-Zélandon telepíthető. A Microsoft fokozatosan adja hozzá a további régiók támogatását.

## <a name="prerequisites"></a>Előfeltételek

Ez a szakasz a Pénzügyi elemzések használatának követelményeit sorolja fel. Ahol csak lehetséges, további információforrásokra mutató hivatkozásokat adnak meg.

### <a name="system-requirements"></a>Rendszerkövetelmények

A 2. szintű környezet (többdobozos) szükséges a Finance Insights előzetes verziójának megtekintéséhez. A környezetekkel kapcsolatos háttérbeli tudnivalókat lásd: [Környezet tervezése](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).

### <a name="version-requirements"></a>Verziókövetelmények

Ez a témakör a Microsoftra vonatkozik Dynamics 365 Finance 10.0.21 és újabb verzió.

### <a name="license-requirements"></a>Licenckövetelmények

Pénzügyi betekintések felhasználása AI Builder hitelek pénzügyi előrejelzések készítéséhez. Az ehhez szükséges összes licencet a bérlői licenc tartalmazza. Minden egyes Dynamics 365 Finance bérlőt biztosítanak 20.000 AI Builder kredit minden hónapban. Ha az üzleti igényekhez további hitelekre van szükség, azokat közvetlenül a webhelyről vásárolhatja meg AI Builder.

### <a name="historical-data-requirements"></a>Korábbi adatokra vonatkozó követelmények

Legalább egy év értékű vevői számlákra van szükség a gépi tanulási modell megfelelő betanításához, amelyet a Vevői fizetési előrejelzések funkcióhoz használnak. A cash flow-előrejelzésekhez három év múltbeli adatok javasoltak. Az intelligens költségvetési javaslatokhoz három éves múltbeli költségvetés és/vagy tényleges adatok javasoltak.

## <a name="configure-finance-insights"></a>A Finance Insights konfigurálása

A Finance Insights használatához végre kell hajtania a konfigurációs lépéseket. A Pénzügyi elemzések konfigurálásáról a [Konfiguráció a pénzügyi elemzésekhez](configure-for-fin-insites.md) című témakörben talál további információt.

## <a name="create-a-data-integrator-project"></a>Adatintegrációs projekt létrehozása

Létre kell hoznia egy adatintegrációs projektet, hogy a gépi tanulási modell által létrehozott adatok befolyhassanak a Dynamics 365 Finance-ba. A projekt létrehozásának lépéseit az [Adatintegrációs projekt létrehozása](create-data-integrate-project.md) című témakörben találja.

## <a name="enable-finance-insights-capabilities"></a>Pénzügyi elemzési funkciók engedélyezése

Miután elvégezte a konfigurációs lépéseket, és beállította a bemutató adatokat, be kell kapcsolnia és be kell állítania minden használni kívánt funkciót: vevői fizetési előrejelzéseket, pénzforgalmi előrejelzéseket és költségvetési javaslatokat.

### <a name="enable-customer-payment-predictions"></a>Vevői fizetési előrejelzések engedélyezése
Ha bemutatóadatokat használ az ügyfelek fizetési előrejelzéseinek teszteléséhez, előfordulhat, hogy további bemutatóadatokat kell importálnia az AI-modell sikeres létrehozásához. 

Az Ügyfél fizetési előrejelzéseinek engedélyezéséhez lépések sorozatát kell végrehajtania egy olyan gépi tanulási modell felépítéséhez, amely a szervezet adatait használja fel arra vonatkozóan, hogy az ügyfelek várhatóan mikor fizetik ki a fennálló számlákat, és mikor fizetnek ki bizonyos számlákat. További információkért és a végrehajtandó konkrét lépésekért olvassa el a [Vevői fizetési előrejelzések engedélyezése](enable-cust-paymnt-prediction.md) című témakört. 

### <a name="enable-cash-flow-forecasting"></a>Pénzforgalmi előrejelzés engedélyezése
A pénzforgalmi előrejelzés engedélyezéséhez végre kell hajtson egy sor lépést egy olyan gépi tanulási modell létrehozásához, amely a szervezet adatait használja pénzforgalmi előrejelzések létrehozásához. További információkért és a végrehajtandó konkrét lépésekért olvassa el a [Pénzforgalmi előrejelzések engedélyezése](enable-cash-flow-forecasting.md) című témakört.

### <a name="enable-budget-proposals"></a>Költségvetési javaslatok engedélyezése

A Költségvetési javaslatok funkció egy gépi tanulási modellt és a szervezet előzményadatait használja a költségvetési javaslat létrehozásához. A létrehozott javaslat segítségével elindíthatja a manuális folyamatoknál hatásosabb és hatékonyabb költségvetés-kezelési folyamatot. A funkció engedélyezésének konkrét lépéseiért lásd: [Költségvetési javaslatok engedélyezése](enable-budget-proposal.md). 

## <a name="using-finance-insights-features"></a>A Finance Insights funkcióinak használata

### <a name="using-customer-payment-predictions"></a>Vevői fizetési előrejelzések használata

- Ha meg szeretné tudni, hogy az Ügyfél fizetési előrejelzései hogyan biztosíthatják a beszedési tevékenységek proaktív megkezdéséhez szükséges információkat, lásd: [Használja az Ügyfél fizetési előrejelzéseit](use-customer-payment-predictions.md).
- A funkció használatának megkezdése után, az előrejelzési modell hatékonyságának kiértékelésében hasznos információkkal kapcsolatban további tájékoztatást a [Kezdeti vevői fizetési előrejelzési modell kiértékelése](evaluate-payment-prediction.md) szakaszban talál.
- Az előrejelzés létrehozásához és ezáltal a hatékonyság növeléséhez használt adatok módosításához az[ Előrejelzési modell javítása](improve-model.md) című témakörben talál tájékoztatást.
- Az AI-előrejelzési modellek eredményeivel kapcsolatos további információt a [Gépi tanulási modellek eredményei](confusion-matrix.md) részben talál.

### <a name="using-cash-flow-forecasts"></a>Pénzforgalmi előrejelzés használata

A Pénzforgalmi előrejelzés funkció segítségével pontosabban megbecsülheti készpénzpozícióját. Az intelligens cash flow-előrejelzés a meglévő cash flow-előrejelzési funkcióra épül Dynamics 365 Finance. A meglévő képesség áttekintéséhez olvassa el a [Pénzforgalmi előrejelzés](../cash-bank-management/cash-flow-forecasting.md) című témakört.

- Ha többet szeretne megtudni a Cash flow-előrejelzések új lehetőségeiről, lásd: [Cash flow előrejelzés](cash-flow-forecast-intro.md).
- A pénzforgalmi előrejelzésben szereplő külső adatok importálásáról a [Külső adatok használata a pénzforgalmi előrejelzésekben](external-data-in-cash-flow.md) című témakörben olvashat. 
- Ha tudni szeretné, hogyan használható a rövid távú pénzforgalom az AI-modell használatával, olvassa el a [Készpénzpozíció](cash-position.md) című témakört.
- A pénzforgalmi pozíciók és a pénzforgalmi előrejelzések pillanatképként való mentésével, valamint a pillanatképek tényleges adatokkal való összehasonlításáról a [Pillanatképek áttekintése](payment-snapshots.md) című témakörben olvashat.

### <a name="using-budget-proposal"></a>Költségvetési javaslatok használata

A költségvetés létrehozásának felgyorsításáról a [Költségvetési javaslatok](budget-proposals.md) című témakörben talál további információt. 

## <a name="feedback-and-support"></a>Visszajelzés és támogatás

Ha szeretne visszajelzést adni, vagy támogatásra van szüksége, küldjön e-mailt a következő címre: [Pénzügyi betekintések](mailto:fiap@microsoft.com).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
