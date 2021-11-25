---
title: A Finance Insights beállítási problémáinak elhárítása
description: Ez a témakör a Finance Insights funkciók használata során előforduló problémákat sorolja fel. Ezenkívül bemutatja a problémák megoldását is.
author: panolte
ms.date: 11/03/2021
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
ms.search.validFrom: 2021-08-20
ms.dyn365.ops.version: AX 10.0.20
ms.openlocfilehash: f3cac30a66ff3a74a7f67c11dd9fa14af79d10af
ms.sourcegitcommit: 03fa7556840aa59f825697f6f9edeb58ea673fca
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/04/2021
ms.locfileid: "7752617"
---
# <a name="troubleshoot-finance-insights-setup-issues"></a>A Finance Insights beállítási problémáinak elhárítása

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Ez a témakör a Finance Insights funkciók használata során előforduló problémákat sorolja fel. Ezenkívül bemutatja a problémák megoldását is.

## <a name="symptom-why-cant-i-map-the-customer-payment-insights-data-integration-template-destination-column"></a>Tünet: Miért nem lehet leképezni a Vevői kifizetések információk adatintegrációs sablonjának céloszlopát?

### <a name="resolution"></a>Megoldás

Előfordulhat, hogy egy korábbi verzióhoz készült sablont használ. A 10.0.17-es verzió kiadása előtt az előzetes verziót használó vevők az **Ügyfél fizetési információk eredményei (CDS – Fin and Ops)** adatintegrációs (DI) sablont konfigurálták a **Fizetési előrejelzés eredménye (előzetes verzió)** entitással. A 10.0.17-es és újabb verzióra történő frissítés után az **Ügyfelek fizetési információinak eredményei (CDS – Fin and Ops 10.0.17 és újabb)** DI sablonját kell használnia a megfeleltetés befejezéséhez. Lehet, hogy nem tudja leképezni a DI sablon céloszlopát mindaddig, amíg az adatkezelési entitások listája frissül, és a **Fizetési előrejelzés eredménye** entitás meg nem jelenik benne. Az entitáslista frissítésééhez és a fizetési előrejelzés eredményének a megjelenítése érdekében a Microsoft Dynamics 365 Finance és a Dataverse (korábban Common Data Service \[ CDS\] rendszergazdai portál) lépéseit is végre kell hajtania.

### <a name="in-finance"></a>A Finance-ben

A frissítés után kövesse a Finance-ben ezeket a lépéseket.

1. Ugrás a **Rendszerfelügyelet \> Munkaterületek \> Adatkezelés** elemre.
2. Az **Adatkezelés** munkaterületen válassza az **Keretrendszer-paraméterek** csempét.
3. Az **Adatimportálási és-exportálási keretrendszer paraméterei** oldalon válassza az **Entitás beállításai** elemet, majd válassza az **Entitáslista frissítése** lehetőséget.
4. Zárja be az **Adatimportálási és-exportálási keretrendszer paraméterei** oldalt.
5. Az **Adatkezelés** munkaterületen válassza az **Adatentitások** csempét.
6. Keressen "Kifizetés előrejelzésének eredménye" kifejezésre. Győződjön meg róla, hogy a **Fizetés-előrejelzésének eredménye** entitása nem az előzetes verziójú. Az előnézeti verzió neve az (előzetes verzió) kifejezésre végződik. Ha az entitásnak csak az előnézeti verziója látható, forduljon a Microsoft támogatási szolgálatához.

### <a name="in-dataverse"></a>Itt: Dataverse

Az alábbi lépések szerint frissítheti az adatintegrációs projekteket a [Power Platform felügyeleti központban](https://admin.powerplatform.microsoft.com/environments).

1. Ha a Finance Insights előnézeti verzióját használja, távolítsa el a **Vevői kifizetési információk eredményei (CDS – Fin Ops)** sablonhoz társított DI projektet.
2. Hajtsa végre az [Adatentregrátor projekt létrehozása](create-data-integrate-project.md) rész lépéseit. Használja a **ügyfelek fizetési információinak eredményei (CDS – Fin and Ops 10.0.17 vagy újabb)** sablont.

## <a name="symptom-when-i-try-to-open-ai-builder-by-using-the-links-on-the-customer-payment-predictions-setup-page-why-do-i-receive-the-following-error-message-sorry-theres-been-a-disconnect"></a>Tünet: Amikor a Vevői kifizetések előrejelzése beállítási lapon található hivatkozásokkal szeretnék megnyitni az AI Buildert, miért jelenik meg a következő hibaüzenet: "Sajnáljuk, de megszakadt a kapcsolat"?

### <a name="resolution"></a>Megoldás

Dynamics 365 Finance A felhasználónak felhasználói fiókkal kell lennie a környezetnek, és annak a felhasználói fióknak a Rendszer Microsoft Power Apps szabó szerepkörével kell lennie. A Microsoft Power Apps rendszergazda létrehozhatja a felhasználói fiókot, és hozzárendelheti a szerepkört. Ezután a megfelelő felhasználói fiók használatával <https://make.preview.powerapps.com/> bejelentkezhet, majd újra megpróbálkodhat a hivatkozásokkal.

## <a name="symptom-why-doesnt-the-cash-forecast-tab-in-the-cash-flow-forecast-workspace-show-any-data"></a>Tünet: Miért nem mutat adatokat a Pénzforgalmi előrejelzés munkaterület Készpénzforgalmi-előrejelzés lapja?

### <a name="resolution"></a>Megoldás

Be kell állítani és engedélyezni kell a Pénzforgalom és bankkezelés pénzforgalmi előrejelzési funkcióját, valamint a Finance Insights pénzforgalmi előrejelezési funkcióját, hogy az adatok megfelelően megjelenjenek a **Pénzforgalmi előrejelzés** munkaterületén.

Először állítsa be és engedélyezze a pénzforgalmi előrejelzési és a likviditási számlákat. További információkért lásd: [Pénzforgalmi előrejelzés](../cash-bank-management/cash-flow-forecasting.md). Ha ez a beállítás elkészült, de a várt eredmények nem láthatóak, a további tudnivalókat lásd a [Pénzforgalmi előrejelzés beállításainak hibaelhárítása](../cash-bank-management/cash-flow-forecasting-tsg.md) témakörben.

Ezután győződjön meg arról, hogy a Finance Insights (**Készpénz- és bankkezelés \> Beállítások \> Finance Insights \> Pénzforgalmi előrejelzések**) funkció engedélyezve van, és hogy befejeződött az AI-modell képzése. Ha a képzés még nem fejeződött be, az **Előrejelzés most** lehetőséget választva elindítható a modell betanítási folyamata.
