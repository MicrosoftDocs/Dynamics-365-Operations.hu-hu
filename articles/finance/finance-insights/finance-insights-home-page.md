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
ms.openlocfilehash: 2f04ef1a0de815596f629fede25a247c58e026f4
ms.sourcegitcommit: c5f2cba3c2b0758e536eeaaa40506659a53085e1
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/12/2022
ms.locfileid: "9643877"
---
# <a name="finance-insights-home-page"></a>A Finance Insights kezdőlapja

[!include [banner](../includes/banner.md)]

A pénzügyi információk konfigurálható és extensible megoldásokat kínálnak, amelyek segítségével intelligens módon előre jelezhető a vállalat pénzforgaloma, várható, hogy mikor kap fizetést a kinnlevőségekért, és olyan költségvetési javaslatot generál, amely gyorsíthatja a költségvetés-folyamot. Ezek a funkciók intelligens gépi oktatási sablonokat használnak a modellek ön által használt felhasználásával (például egy külső féltől származó adatok, például egy iroda felhasználói jelentési információi). Ezek az intelligens képességek a döntéshozásról nyújtanak tájékoztatást, és segítséget nyújtanak annak érdekében, hogy hatékonyan reagáljanak a jelenlegi és várható üzleti problémákra. Ön felelős minden adatért, amely a Pénzügyi információkkal együtt (vagy ezek kimenetei alapján) használatos.

> [!NOTE]
> A pénzügyi információk rendelkezésre állnak az Amerikai Egyesült Államokban, Kanadában, az Egyesült Királyságban, Az Európa, Ázsia csendes-óceáni, Japánban, Ausztráliában és Új-Zélandban való telepítéshez. A Microsoft fokozatosan adja hozzá a további régiók támogatását.

## <a name="prerequisites"></a>Előfeltételek

Ez a szakasz a Pénzügyi elemzések használatának követelményeit sorolja fel. Ahol csak lehetséges, további információforrásokra mutató hivatkozásokat adnak meg.

### <a name="system-requirements"></a>Rendszerkövetelmények

A 2. szintű környezet (többdobozos) szükséges a Finance Insights előzetes verziójának megtekintéséhez. A környezetekkel kapcsolatos háttérbeli tudnivalókat lásd: [Környezet tervezése](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).

### <a name="version-requirements"></a>Verziókövetelmények

Ez a cikk a Microsoft Dynamics 365 Pénzügy 10.0.21-es és újabb verziójára vonatkozik.

### <a name="license-requirements"></a>Licenckövetelmények

A pénzügyi információk hiteleket AI Builder felhasználva pénzügyi előrejelzéseket hoznak létre. Ehhez az összes szükséges licenc a bérlői licenchez tartozik. A Dynamics 365 Pénzügy minden bérlője minden hónapban 20 000 AI Builder jóváírást biztosít. Ha az üzleti igényekhez további jóváírások szükségesek, közvetlenül a vállalattól lehet őket beszerezni AI Builder.

### <a name="historical-data-requirements"></a>Korábbi adatokra vonatkozó követelmények

Legalább egy év értékű vevői számlákra van szükség a gépi tanulási modell megfelelő betanításához, amelyet a Vevői fizetési előrejelzések funkcióhoz használnak. A pénzforgalmi előrejelzésekhez három év előzményadat ajánlott. Az intelligens költségvetési javaslatokhoz három évnyi múltbeli költségvetés és/vagy tény használata ajánlott.

## <a name="configure-finance-insights"></a>A Finance Insights konfigurálása

A Pénzügyi információk használata előtt el kell végrehajtania a konfigurációs lépéseket. A Pénzügyi elemzések konfigurálásáról a [Konfiguráció a pénzügyi elemzésekhez](configure-for-fin-insites.md) című témakörben talál további információt.

## <a name="create-a-data-integrator-project"></a>Adatintegrációs projekt létrehozása

Létre kell hoznia egy adatintegrátor projektet, hogy a gépi oktatási modell által generált adatok át tudjanak lenni a Dynamics 365 Pénzügybe. A projekt létrehozásának lépéseit az [Adatintegrációs projekt létrehozása](create-data-integrate-project.md) című témakörben találja.

## <a name="enable-finance-insights-capabilities"></a>Pénzügyi elemzési funkciók engedélyezése

Miután elvégezte a konfigurációs lépéseket, és beállította a bemutató adatokat, be kell kapcsolnia és be kell állítania minden használni kívánt funkciót: vevői fizetési előrejelzéseket, pénzforgalmi előrejelzéseket és költségvetési javaslatokat.

### <a name="enable-customer-payment-predictions"></a>Vevői fizetési előrejelzések engedélyezése
Ha bemutatóadatokat használ az ügyfelek fizetési előrejelzéseinek teszteléséhez, előfordulhat, hogy további bemutatóadatokat kell importálnia az AI-modell sikeres létrehozásához. 

A vevői kifizetések előrejelzésének engedélyezéséhez egy sor lépést kell végrehajtania egy gépi oktatási modell létrehozásához, amely a szervezet adatai alapján előrejelzéseket generál arról, hogy a vevők mikor várhatóan kifizetik a ki nem fizetett számlákat, és mikor várható az egyes számlák kifizetése. További információkért és a végrehajtandó konkrét lépésekért olvassa el a [Vevői fizetési előrejelzések engedélyezése](enable-cust-paymnt-prediction.md) című témakört. 

### <a name="enable-cash-flow-forecasting"></a>Pénzforgalmi előrejelzés engedélyezése
A pénzforgalmi előrejelzés engedélyezéséhez végre kell hajtson egy sor lépést egy olyan gépi tanulási modell létrehozásához, amely a szervezet adatait használja pénzforgalmi előrejelzések létrehozásához. További információkért és a végrehajtandó konkrét lépésekért olvassa el a [Pénzforgalmi előrejelzések engedélyezése](enable-cash-flow-forecasting.md) című témakört.

### <a name="enable-budget-proposals"></a>Költségvetési javaslatok engedélyezése

A Költségvetési javaslatok funkció egy gépi tanulási modellt és a szervezet előzményadatait használja a költségvetési javaslat létrehozásához. A létrehozott javaslat segítségével elindíthatja a manuális folyamatoknál hatásosabb és hatékonyabb költségvetés-kezelési folyamatot. A funkció engedélyezésének részletes lépéseit lásd A költségvetési [javaslatok engedélyezése](enable-budget-proposal.md). 

## <a name="using-finance-insights-features"></a>A Finance Insights funkcióinak használata

### <a name="using-customer-payment-predictions"></a>Vevői fizetési előrejelzések használata

- A Vevői kifizetések [előrejelzései segítségével a beszedési tevékenységek proaktív megkezdéséhez szükséges információkat tudni a Vevői kifizetések előrejelzésének használata](use-customer-payment-predictions.md).
- A funkció használatának megkezdése után, az előrejelzési modell hatékonyságának kiértékelésében hasznos információkkal kapcsolatban további tájékoztatást a [Kezdeti vevői fizetési előrejelzési modell kiértékelése](evaluate-payment-prediction.md) szakaszban talál.
- Az előrejelzés létrehozásához és ezáltal a hatékonyság növeléséhez használt adatok módosításához az[ Előrejelzési modell javítása](improve-model.md) című témakörben talál tájékoztatást.
- Az AI-előrejelzési modellek eredményeivel kapcsolatos további információt a [Gépi tanulási modellek eredményei](confusion-matrix.md) részben talál.

### <a name="using-cash-flow-forecasts"></a>Pénzforgalmi előrejelzés használata

A Pénzforgalmi előrejelzés funkció segítségével pontosabban megbecsülheti készpénzpozícióját. Az intelligens pénzforgalmi előrejelzés a Dynamics 365 Pénzügy meglévő pénzforgalmi előrejelzési funkcióin alapul. A meglévő képesség áttekintéséhez olvassa el a [Pénzforgalmi előrejelzés](../cash-bank-management/cash-flow-forecasting.md) című témakört.

- A pénzforgalmi előrejelzésekben új képességekre vonatkozó tudnivalókat lásd a [Pénzforgalmi előrejelzésben](cash-flow-forecast-intro.md).
- A pénzforgalmi előrejelzésben szereplő külső adatok importálásáról a [Külső adatok használata a pénzforgalmi előrejelzésekben](external-data-in-cash-flow.md) című témakörben olvashat. 
- Ha tudni szeretné, hogyan használható a rövid távú pénzforgalom az AI-modell használatával, olvassa el a [Készpénzpozíció](cash-position.md) című témakört.
- A pénzforgalmi pozíciók és a pénzforgalmi előrejelzések pillanatképként való mentésével, valamint a pillanatképek tényleges adatokkal való összehasonlításáról a [Pillanatképek áttekintése](payment-snapshots.md) című témakörben olvashat.

### <a name="using-budget-proposal"></a>Költségvetési javaslatok használata

A költségvetés létrehozásának felgyorsításáról a [Költségvetési javaslatok](budget-proposals.md) című témakörben talál további információt. 

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
