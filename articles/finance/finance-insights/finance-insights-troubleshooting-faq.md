---
title: A Finance Insights beállítási problémáinak elhárítása
description: Ez a témakör a Finance Insights funkciók használata során előforduló problémákat sorolja fel. Ezenkívül bemutatja a problémák megoldását is.
author: panolte
ms.date: 01/29/2022
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
ms.openlocfilehash: f77cddfdab22bef8af7f62d49723e330c4f13261
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/31/2022
ms.locfileid: "8064866"
---
# <a name="troubleshoot-finance-insights-setup-issues"></a>A Finance Insights beállítási problémáinak elhárítása

[!include [banner](../includes/banner.md)]

Ez a témakör a Finance Insights funkciók használata során előforduló problémákat sorolja fel. Ezenkívül bemutatja a problémák megoldását is.

## <a name="symptom-why-cant-i-map-the-customer-payment-insights-data-integration-template-destination-column"></a>Tünet: Miért nem lehet leképezni a Vevői kifizetések információk adatintegrációs sablonjának céloszlopát?

### <a name="resolution"></a>Megoldás

Előfordulhat, hogy egy korábbi verzióhoz készült sablont használ. A 10.0.17-es verzió kiadása előtt az előzetes verziót használó vevők az **Ügyfél fizetési információk eredményei (CDS – Fin and Ops)** adatintegrációs (DI) sablont konfigurálták a **Fizetési előrejelzés eredménye (előzetes verzió)** entitással. A 10.0.17-es és újabb verzióra történő frissítés után az **Ügyfelek fizetési információinak eredményei (CDS – Fin and Ops 10.0.17 és újabb)** DI sablonját kell használnia a megfeleltetés befejezéséhez. Lehet, hogy nem tudja leképezni a DI sablon céloszlopát mindaddig, amíg az adatkezelési entitások listája frissül, és a **Fizetési előrejelzés eredménye** entitás meg nem jelenik benne. Az entitáslista frissítésééhez és a fizetési előrejelzés eredményének a megjelenítése érdekében a Microsoft Dynamics 365 Finance és a Dataverse (korábban Common Data Service \[CDS\] rendszergazdai portál) lépéseit is végre kell hajtania.

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

## <a name="symptom-when-i-try-to-open-ai-builder-by-using-the-links-on-the-customer-payment-predictions-setup-page-why-do-i-receive-the-following-error-message-sorry-theres-been-a-disconnect"></a>Tünet: Amikor megpróbálom kinyitni AI Builder az Ügyfél fizetési előrejelzései beállítási oldalon található hivatkozások használatával miért kapom a következő hibaüzenetet: "Sajnáljuk, megszakadt a kapcsolat"?

### <a name="resolution"></a>Megoldás

Dynamics 365 Finance a felhasználóknak rendelkezniük kell a Microsoft Power Apps felhasználói fiók a környezethez, és ennek a felhasználói fióknak rendelkeznie kell a Rendszer-testreszabó szerepkörrel. A Microsoft Power Apps rendszergazda létrehozhatja a felhasználói fiókot és hozzárendelheti a szerepkört. Ezután mehet a<https://make.preview.powerapps.com/>, jelentkezzen be a felhasználói fiókkal, és próbálja meg újra a hivatkozásokat.

## <a name="symptom-why-doesnt-the-cash-forecast-tab-in-the-cash-flow-forecast-workspace-show-any-data"></a>Tünet: Miért nem mutat adatokat a Pénzforgalmi előrejelzés munkaterület Készpénzforgalmi-előrejelzés lapja?

### <a name="resolution"></a>Megoldás

Be kell állítani és engedélyezni kell a Pénzforgalom és bankkezelés pénzforgalmi előrejelzési funkcióját, valamint a Finance Insights pénzforgalmi előrejelezési funkcióját, hogy az adatok megfelelően megjelenjenek a **Pénzforgalmi előrejelzés** munkaterületén.

Először állítsa be és engedélyezze a pénzforgalmi előrejelzési és a likviditási számlákat. További információkért lásd: [Pénzforgalmi előrejelzés](../cash-bank-management/cash-flow-forecasting.md). Ha ez a beállítás elkészült, de a várt eredmények nem láthatóak, a további tudnivalókat lásd a [Pénzforgalmi előrejelzés beállításainak hibaelhárítása](../cash-bank-management/cash-flow-forecasting-tsg.md) témakörben.

Ezután győződjön meg arról, hogy a Finance Insights (**Készpénz- és bankkezelés \> Beállítások \> Finance Insights \> Pénzforgalmi előrejelzések**) funkció engedélyezve van, és hogy befejeződött az AI-modell képzése. Ha a képzés még nem fejeződött be, az **Előrejelzés most** lehetőséget választva elindítható a modell betanítási folyamata.

## <a name="symptom-why-isnt-the-install-a-new-add-in-button-visible-in-microsoft-dynamics-lifecycle-services"></a>Tünet: Miért nem jelenik meg az Új bővítmény telepítése gomb itt?Microsoft Dynamics Életciklus-szolgáltatások?

### <a name="resolution"></a>Megoldás

Először ellenőrizze, hogy a **Környezetvédelmi vezető** vagy **Projekt tulajdonos** szerepkör van hozzárendelve a bejelentkezett felhasználóhoz **Projekt biztonsági szerepkör** mező be Microsoft Dynamics Életciklus-szolgáltatások (LCS). Az új bővítmények telepítéséhez ezen projektbiztonsági szerepkörök valamelyikére van szükség.

Ha a megfelelő projektbiztonsági szerepkör van hozzárendelve Önhöz, előfordulhat, hogy frissítenie kell a böngészőablakot, hogy láthassa a **Telepítsen új bővítményt** gomb.

## <a name="symptom-the-finance-insights-add-in-doesnt-seem-to-be-installing-why-is-that"></a>Tünet: Úgy tűnik, hogy a Finance Insights bővítmény nem települ. Miert van az?

### <a name="resolution"></a>Megoldás

A következő lépéseket kellett volna végrehajtani.

- Ellenőrizze, hogy rendelkezik-e **Rendszergazda** és **Rendszer-testreszabó** elérheti a Power Portal adminisztrációs központjában.
- Ellenőrizze, hogy a Dynamics 365 Finance vagy azzal egyenértékű licenc vonatkozik a bővítményt telepítő felhasználóra.
- Ellenőrizze, hogy a következők Azure AD Az alkalmazás regisztrálva van Azure AD: 

  | Pályázat                  | Alkalmazás azonosítója           |
  | ---------------------------- | ---------------- |
  | Microsoft Dynamics ERP mikroszolgáltatások CDS | 703e2651-d3fc-48f5-942c-74274233dba8 | 
  
## <a name="symptom-error-we-didnt-find-any-data-for-the-selected-filter-range-please-select-a-different-filter-range-and-try-again"></a>Tünet: Hiba: "Nem találtunk adatokat a kiválasztott szűrőtartományhoz. Kérjük, válasszon másik szűrőtartományt, és próbálja újra." 

### <a name="resolution"></a>Megoldás

Ellenőrizze az adatintegrátor beállítását, és ellenőrizze, hogy a várt módon működik-e, és frissíti-e az adatokat AI Builder vissza a pénzügyekhez.  
További információkért lásd [Hozzon létre egy adatintegrációs projektet](../finance-insights/create-data-integrate-project.md).

## <a name="symptom-customer-payment-prediction-training-failed-and-the-ai-builder-error-states-prediction-should-have-only-2-distinct-outcome-values-to-train-the-model-map-to-two-outcomes-and-retrain-training-report-issue-isnotminrequireddistinctnonnullvalues"></a>Tünet: Az ügyfél fizetési előrejelzési képzése meghiúsult, és a AI Builder hibaüzenet: "Az előrejelzésnek csak 2 különböző kimeneti értékkel kell rendelkeznie a modell betanításához. Térképezze fel a két eredményt, és képezze újra, "Képzési jelentés probléma: IsNotMinRequiredDistinctNonNullValues".

### <a name="resolution"></a>Megoldás

Ez a hiba azt jelzi, hogy nincs elegendő olyan előzménytranzakció az elmúlt évben, amely a következőben leírt kategóriákat képviselné **Időben**, **·**, és **Nagyon későn** kategóriákat. A hiba megoldásához állítsa be a **Nagyon későn** tranzakciós időszak. Ha beállítja a **Nagyon későn** a tranzakciós időszak nem javítja a hibát, **Ügyfél fizetési előrejelzései** nem a legjobb megoldás, mivel minden kategória adataira van szükség edzési célokra.

Ha többet szeretne megtudni arról, hogyan állíthatja be a **Időben**, **·**, és **Nagyon későn** kategóriák, lásd [Ügyfélfizetési előrejelzések engedélyezése](../finance-insights/enable-cust-paymnt-prediction.md).

## <a name="symptom-model-training-failed"></a>Tünet: A modellképzés sikertelen volt

### <a name="resolution"></a>Megoldás

A **Cash flow előrejelzés** A modellképzéshez több mint egy évre kiterjedő, 100-nál is több tranzakciót tartalmazó adatokra van szükség. Ezeknek a tranzakcióknak ki kell hatniuk a likviditási számlákra, amelyek szerepelnek a cash flow-előrejelzési beállításban.

A **Ügyfél fizetési előrejelzései** az előrejelzések létrehozásához legalább 100 ügyfélszámla és fizetési tranzakció szükséges az elmúlt hat-kilenc hónapban.  
