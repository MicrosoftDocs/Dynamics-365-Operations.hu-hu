---
title: Pénzügyi információk kezdőlapja (előzetes verzió)
description: A Pénzügyi információk konfigurálható és bővíthető modelleket biztosít, amelyek segítségével pontosan és intelligensen előrejelezheti a vállalat pénzforgalmát, előrejelezheti, hogy mikor kapja meg a fennmaradó kinnlévőségek kifizetését, és létrehoz egy költségvetési javaslatot, amely felgyorsíthatja a költségvetési folyamatot. Ezek a funkciók intelligens gépi tanulási modelleken alapulnak.
author: ShivamPandey-msft
ms.date: 06/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-07-20
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 9d7eca35d6e5ce8f434f923fef69a6d13a8ac1b3
ms.sourcegitcommit: c9f55e64416d0bbedfdadafb00e4181921ad0f37
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/15/2021
ms.locfileid: "6261910"
---
# <a name="finance-insights-home-page-preview"></a>Pénzügyi információk kezdőlapja (előzetes verzió)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

A Pénzügyi információk konfigurálható és bővíthető modelleket biztosít, amelyek segítségével pontosan és intelligensen előrejelezheti a vállalat pénzforgalmát, előrejelezheti, hogy mikor kapja meg a fennmaradó kinnlévőségek kifizetését, és létrehoz egy költségvetési javaslatot, amely felgyorsíthatja a költségvetési folyamatot. Ezek a funkciók intelligens gépi tanulási modelleken alapulnak. Amikor ezeket az új képességeket kombinálják a szállítói kifizetések és beszedések automatizálásával, gazdag és intelligens pénzügyi rendszert biztosítanak, amely ösztönzi a döntéshozatalt, és segít a jelenlegi és várható üzleti kihívások hatékony megválaszolásában.

A Finance Insights előzetes verzió az Amerikai Egyesült Államokban, Európában és az Egyesült Királyságban is elérhető a próbaverzió telepítéshez. A Microsoft fokozatosan adja hozzá a további régiók támogatását.

Az előzetes verziójú funkciók csak 2. szintű tesztkörnyezetekben szabad bekapcsolni. A tesztkörnyezetben létrehozott telepítési és mesterséges intelligencia-modellek (AI)nem telepíthetők át éles környezetbe. További információ: [A Microsoft Dynamics 365 előzetes verziók kiegészítő használati feltételei](/dynamics365/legal/supp-dynamics365-preview#:~:text=Supplemental%20Terms%20of%20Use%20for%20Microsoft%20Dynamics%20365,%28governing%20your%20use%20of%20Microsoft%20Dynamics%20365%20Online%29.).

> [!NOTE]
> Ezt a funkciót előnézeti funkciókként kínálják fel. Előnézeti funkcióként a kapott gépi oktatási modelleket nem szabad az üzleti döntések vagy a költségvetési javaslatok befolyásolása érdekében használni. A funkció használatát a [Kiegészítő használati feltételek](https://go.microsoft.com/fwlink/?linkid=2105274)szabályozzák.

## <a name="prerequisites"></a>Előfeltételek

Ez a szakasz a Pénzügyi elemzések használatának követelményeit sorolja fel. Ahol csak lehetséges, további információforrásokra mutató hivatkozásokat adnak meg.

### <a name="legal-requirements"></a>Jogi követelmények

Az előzetes verzióra való jelentkezéshez töltse ki a [Pénzügyi elemzési adatok előzetes verzió a Dynamics 365 Finance-hez megállapodás](https://forms.office.com/FormsPro/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR56j8lZs0FdAvwT75_WNFyxUM1c0Uzc1RFpaU1RVTEwxVTNWUERPRThUSy4u) űrlapot.

### <a name="system-requirements"></a>Rendszerkövetelmények

A 2. szintű tesztkörnyezet (többdobozos) szükséges a pénzügyi elemzések előzetes verziójának megtekintéséhez. A környezetekkel kapcsolatos háttérbeli tudnivalókat lásd: [Környezet tervezése](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).

### <a name="version-requirements"></a>Verziókövetelmények

Ez a dokumentum a Finance and Operations-alkalmazások 10.0.11-es verziójára (35-ös platformfrissítés) és újabb verziókra vonatkozik.

### <a name="historical-data-requirements"></a>Korábbi adatokra vonatkozó követelmények

Legalább egy év értékű vevői számlákra van szükség a gépi tanulási modell megfelelő betanításához, amelyet a Vevői fizetési előrejelzések funkcióhoz használnak.

Mintaadatok érhetők el a(z) Contoso bemutató adatkészlettel rendelkező bemutatórendszerekhez.

### <a name="role-and-permission-requirements"></a>Szerepkör- és engedélykövetelmények

A Microsoft Dynamics 365 Finance, Microsoft Dynamics, Lifecycle Services (LCS), Power Apps, és az Azure módosulni fog. Ezekben a környezetekben megfelelő engedélyekre van szükség. Íme néhány példa a jövőbeli változásokra:

- Új környezet jön létre a Microsoft Power Platformban.
- Az Azure-ban létrejön egy tárfiók, kulcstartó és alkalmazás.
- Az Active Directory bérlői rendszergazdájának engedélyeznie kell az AI Builder alkalmazást a Data Lake eléréséhez.
- A funkció be lesz kapcsolva a Dynamics 365 rendszerben.

Az erőforrások létrehozásának és kezelésének ismerete az Azure-ban, Microsoft Dataverse-ben, és LCS-ben hasznos lesz a folyamat befejezésekor.

## <a name="configure-finance-insights"></a>Pénzügyi információk konfigurálása

A Pénzügyi információk használatához végre kell hajtson néhány konfigurációs lépést. További információ a Finance Insights konfigurálásáról:
  - A 10.0.19-es verzióig: [Konfiguráció a Finance Insights alkalmazáshoz – 10.0.19 verzióig](configure-for-fin-insites.md).
  - A 10.0.20-as és újabb verziók esetén: [A Finance Insights (előzetes verzió) konfigurálása – 10.0.20-as és újabb verziók](configure-for-fin-insites-PubPrvw.md).

## <a name="create-a-data-integrator-project"></a>Adatintegrációs projekt létrehozása

Létre kell hoznia egy adatintegrációs projektet, hogy a gépi tanulási modell által létrehozott adatok befolyhassanak a Dynamics 365 Finance-ba. A projekt létrehozásának lépéseit az [Adatintegrációs projekt létrehozása](create-data-integrate-project.md) című témakörben találja.

## <a name="enable-finance-insights-capabilities"></a>Pénzügyi elemzési funkciók engedélyezése

Miután elvégezte a konfigurációs lépéseket, és beállította a bemutató adatokat, be kell kapcsolnia és be kell állítania minden használni kívánt funkciót: vevői fizetési előrejelzéseket, pénzforgalmi előrejelzéseket és költségvetési javaslatokat.

### <a name="enable-customer-payment-predictions"></a>Vevői fizetési előrejelzések engedélyezése
Ha bemutatóadatokat használ az ügyfelek fizetési előrejelzéseinek teszteléséhez, előfordulhat, hogy további bemutatóadatokat kell importálnia az AI-modell sikeres létrehozásához. 

Az ügyfelek fizetési előrejelzéseinek engedélyezéséhez végre kell hajtani egy sor lépést egy olyan gépi tanulási modell létrehozásához, amely a szervezet adataival a szervezet adatai alapján előrejelzéseket készít arról, hogy az ügyfelek valószínűleg mikor fizetnek ki kinnlévő számlákat, és mikor kell fizetnek ki bizonyos számlákat. További információkért és a végrehajtandó konkrét lépésekért olvassa el a [Vevői fizetési előrejelzések engedélyezése](enable-cust-paymnt-prediction.md) című témakört. 

### <a name="enable-cash-flow-forecasting"></a>Pénzforgalmi előrejelzés engedélyezése
A pénzforgalmi előrejelzés engedélyezéséhez végre kell hajtson egy sor lépést egy olyan gépi tanulási modell létrehozásához, amely a szervezet adatait használja pénzforgalmi előrejelzések létrehozásához. További információkért és a végrehajtandó konkrét lépésekért olvassa el a [Pénzforgalmi előrejelzések engedélyezése](enable-cash-flow-forecasting.md) című témakört.

### <a name="enable-budget-proposals"></a>Költségvetési javaslatok engedélyezése

A Költségvetési javaslatok funkció egy gépi tanulási modellt és a szervezet előzményadatait használja a költségvetési javaslat létrehozásához. A létrehozott javaslat segítségével elindíthatja a manuális folyamatoknál hatásosabb és hatékonyabb költségvetés-kezelési folyamatot. A funkció engedélyezéséhez szükséges konkrét lépéseket a [Költségvetési javaslatok engedélyezése](enable-budget-proposal.md) című témakörben talál. 

## <a name="using-finance-insights-features"></a>A Finance Insights funkcióinak használata

### <a name="using-customer-payment-predictions"></a>Vevői fizetési előrejelzések használata

Az intelligens pénzforgalmi előrejelzés a meglévő pénzforgalmi előrejelzési funkciókra épül a Dynamics 365 Finance-ben. A meglévő képesség áttekintéséhez olvassa el a [Pénzforgalmi előrejelzés](../cash-bank-management/cash-flow-forecasting.md) című témakört.

- Ha meg szeretné tudni, hogy az Ügyfél fizetési előrejelzései hogyan biztosíthatják a begyűjtési tevékenységek proaktív használatához szükséges információkat, olvassa el az [Ügyfél fizetési előrejelzések használata](use-customer-payment-predictions.md) című témakört.
- A funkció használatának megkezdése után, az előrejelzési modell hatékonyságának kiértékelésében hasznos információkkal kapcsolatban további tájékoztatást a [Kezdeti vevői fizetési előrejelzési modell kiértékelése](evaluate-payment-prediction.md) szakaszban talál.
- Az előrejelzés létrehozásához és ezáltal a hatékonyság növeléséhez használt adatok módosításához az[ Előrejelzési modell javítása](improve-model.md) című témakörben talál tájékoztatást.

Az AI-előrejelzési modellek eredményeivel kapcsolatos további információt a [Gépi tanulási modellek eredményei](confusion-matrix.md) részben talál.

### <a name="using-cash-flow-forecasts"></a>Pénzforgalmi előrejelzés használata

A Pénzforgalmi előrejelzés funkció segítségével pontosabban megbecsülheti készpénzpozícióját. 

- A Pénzforgalmi előrejelzések új képességeiről a [Pénzforgalmi előrejelzés](cash-flow-forecast-intro.md) című témakörben olvashat.
- A pénzforgalmi előrejelzésben szereplő külső adatok importálásáról a [Külső adatok használata a pénzforgalmi előrejelzésekben](external-data-in-cash-flow.md) című témakörben olvashat. 
- Ha tudni szeretné, hogyan használható a rövid távú pénzforgalom az AI-modell használatával, olvassa el a [Készpénzpozíció](cash-position.md) című témakört.
- A pénzforgalmi pozíciók és a pénzforgalmi előrejelzések pillanatképként való mentésével, valamint a pillanatképek tényleges adatokkal való összehasonlításáról a [Pillanatképek áttekintése](payment-snapshots.md) című témakörben olvashat.

### <a name="using-budget-proposal"></a>Költségvetési javaslatok használata

A költségvetés létrehozásának felgyorsításáról a [Költségvetési javaslatok](budget-proposals.md) című témakörben talál további információt. 

## <a name="feedback-and-support"></a>Visszajelzés és támogatás

Kérjük, küldjön egy e-mailt az [Ügyfél fizetési elemzés (előzetes verzió)](mailto:fiap@microsoft.com) címre, ha visszajelzést szeretne adni, vagy támogatásra van szüksége.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
