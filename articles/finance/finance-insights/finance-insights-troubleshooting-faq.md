---
title: A Finance Insights beállítási problémáinak elhárítása
description: Ez a cikk felsorolja azokat a problémákat, amelyek a pénzügyi információkhoz való képességek használata során fordulhatnak elő. Ezenkívül bemutatja a problémák megoldását is.
author: panolte
ms.date: 02/11/2022
ms.topic: article
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
ms.author: panolte
ms.search.validFrom: 2021-08-20
ms.dyn365.ops.version: AX 10.0.20
ms.openlocfilehash: 331c714663d212471b72f1558e6183452ef7f394
ms.sourcegitcommit: adadbc6e355e2ad68a1f6af26a1be1f89dc8eec6
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/22/2022
ms.locfileid: "9573172"
---
# <a name="troubleshoot-finance-insights-setup-issues"></a>A Finance Insights beállítási problémáinak elhárítása

[!include [banner](../includes/banner.md)]

Ez a cikk felsorolja azokat a problémákat, amelyek a pénzügyi információkhoz való képességek használata során fordulhatnak elő. Ezenkívül bemutatja a problémák megoldását is.

## <a name="symptom-why-cant-i-map-the-customer-payment-insights-data-integration-template-destination-column"></a>Tünet: Miért nem lehet leképezni a Vevői kifizetések információk adatintegrációs sablonjának céloszlopát?

### <a name="resolution"></a>Megoldás

Előfordulhat, hogy egy korábbi verzióhoz készült sablont használ. A 10.0.17-es verzió kiadása előtt az előzetes verziót használó vevők az **Ügyfél fizetési információk eredményei (CDS – Fin and Ops)** adatintegrációs (DI) sablont konfigurálták a **Fizetési előrejelzés eredménye (előzetes verzió)** entitással. A 10.0.17-es és újabb verzióra történő frissítés után az **Ügyfelek fizetési információinak eredményei (CDS – Fin and Ops 10.0.17 és újabb)** DI sablonját kell használnia a megfeleltetés befejezéséhez. Lehet, hogy nem tudja leképezni a DI sablon céloszlopát mindaddig, amíg az adatkezelési entitások listája frissül, és a **Fizetési előrejelzés eredménye** entitás meg nem jelenik benne. Az entitáslista frissítésére Microsoft Dynamics és a fizetési előrejelzés eredményének a megjelenítése érdekében a 365 Pénzügy Dataverse és (korábban Common Data Service\[CDS\] admin portal) lépéseit is végre kell végrehajtania.

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

## <a name="symptom-when-i-try-to-open-ai-builder-by-using-the-links-on-the-customer-payment-predictions-setup-page-why-do-i-receive-the-following-error-message-sorry-theres-been-a-disconnect"></a>Tünet: AI Builder Amikor a Vevői kifizetések előrejelzése beállítási lapon található hivatkozásokkal próbál meg megnyílni, miért jelenik meg a következő hibaüzenet: "Sajnáljuk, de megszakadt a kapcsolat"?

### <a name="resolution"></a>Megoldás

A Dynamics 365 Pénzügy felhasználói fióknak kell lennie a környezetben, és annak a Microsoft Power Apps felhasználói fióknak a Rendszer szabó szerepkörével kell lennie. A Microsoft Power Apps rendszergazda létrehozhatja a felhasználói fiókot, és hozzárendelheti a szerepkört. Ezután a megfelelő felhasználói fiók <https://make.preview.powerapps.com/> használatával bejelentkezhet, majd újra megpróbálkodhat a hivatkozásokkal.

## <a name="symptom-why-doesnt-the-cash-forecast-tab-in-the-cash-flow-forecast-workspace-show-any-data"></a>Tünet: Miért nem mutat adatokat a Pénzforgalmi előrejelzés munkaterület Készpénzforgalmi-előrejelzés lapja?

### <a name="resolution"></a>Megoldás

Be kell állítani és engedélyezni kell a Pénzforgalom és bankkezelés pénzforgalmi előrejelzési funkcióját, valamint a Finance Insights pénzforgalmi előrejelezési funkcióját, hogy az adatok megfelelően megjelenjenek a **Pénzforgalmi előrejelzés** munkaterületén.

Először állítsa be és engedélyezze a pénzforgalmi előrejelzési és a likviditási számlákat. További információkért lásd: [Pénzforgalmi előrejelzés](../cash-bank-management/cash-flow-forecasting.md). Ha ez a beállítás elkészült, de a várt eredmények nem láthatóak, a további tudnivalókat lásd a [Pénzforgalmi előrejelzés beállításainak hibaelhárítása](../cash-bank-management/cash-flow-forecasting-tsg.md) témakörben.

Ezután győződjön meg arról, hogy a Finance Insights (**Készpénz- és bankkezelés \> Beállítások \> Finance Insights \> Pénzforgalmi előrejelzések**) funkció engedélyezve van, és hogy befejeződött az AI-modell képzése. Ha a képzés még nem fejeződött be, az **Előrejelzés most** lehetőséget választva elindítható a modell betanítási folyamata.

## <a name="symptom-why-isnt-the-install-a-new-add-in-button-visible-in-microsoft-dynamics-lifecycle-services"></a>Tünet: Miért nem látható az Új bővítmény Microsoft Dynamics telepítése gomb a Lifecycle Services szolgáltatásban?

### <a name="resolution"></a>Megoldás

Először ellenőrizze, hogy **a** **Környezetkezelő vagy a** Projekttulajdonos szerepkör hozzá van-e **rendelve a Lifecycle Services (LCS) Projekt biztonsági szerepkör** Microsoft Dynamics mezőjében a bejelentkezett felhasználóhoz. Az új bővítmények telepítéséhez a projekt egyik biztonsági szerepköre szükséges.

Ha a megfelelő projektbiztonsági szerepkör van hozzárendelve, lehet, **hogy frissítenie kell a böngészőablakot, hogy az Új bővítmény telepítése gomb látható** legyen.

## <a name="symptom-the-finance-insights-add-in-doesnt-seem-to-be-installing-why-is-that"></a>Tünet: A Pénzügyi információk bővítmény nem úgy látszik, hogy telepítve van. Mi az?

### <a name="resolution"></a>Megoldás

A következő lépéseknek el kellett volna fejeződni.

- Ellenőrizze, hogy rendelkezik-e **·** **rendszergazdai** és rendszer szabó hozzáféréssel a Power Portal admin center alkalmazásban.
- Győződjön meg róla, hogy a bővítményt telepítő felhasználóhoz dynamics 365 pénzügyi vagy azzal egyenértékű licenc van alkalmazva.
- Győződjön meg róla, hogy a következő Azure AD alkalmazás regisztrálva van a következőben Azure AD: 

    | Alkalmazás                  | Alkalmazás azonosítója           |
    | ---------------------------- | ---------------- |
    | Microsoft Dynamics ERP mikroszolgáltatások CDS | 703e2651-d3fc-48f5-942c-74274233dba8 | 
  
    Ha ellenőrizni kell, hogy a pályázat be van-e Azure AD jegyezve, jelölje be az Összes **pályázat listát**. A további tudnivalókat lásd a Vállalati [alkalmazások megtekintése.](/azure/active-directory/manage-apps/view-applications-portal)
  
    Ha az alkalmazás nincs regisztrálva a alkalmazásban Azure AD, forduljon a támogatási szolgálathoz.

## <a name="symptom-error-we-didnt-find-any-data-for-the-selected-filter-range-please-select-a-different-filter-range-and-try-again"></a>Tünet: Hiba: "Nem található adat a kiválasztott szűrőtartományhoz. Válasszon másik szűrőtartományt, majd próbálkozzon újra." 

### <a name="resolution"></a>Megoldás

Ellenőrizze az adat integrátor beállításait, és ellenőrizze, hogy a funkció a várt módon működik-e, és az adatok a Pénzügy programba való telepítésének AI Builder megfelelően működik-e.  
A további tudnivalókat lásd [: "Adatintegrációs projekt létrehozása"](../finance-insights/create-data-integrate-project.md).

## <a name="symptom-customer-payment-prediction-training-failed-and-the-ai-builder-error-states-prediction-should-have-only-2-distinct-outcome-values-to-train-the-model-map-to-two-outcomes-and-retrain-training-report-issue-isnotminrequireddistinctnonnullvalues"></a>Tünet: A vevői kifizetések előrejelzésére vonatkozó képzés AI Builder sikertelen volt, és a hibakódok azt jelezték: "Az előrejelzésnek csak két egyedi eredményértékkel kell lennie a modell képzésére. Leképezés két eredményre és átterhelésre", "Képzési jelentés kiállítása: IsNotMinRequiredDistinctNonLlValues".

### <a name="resolution"></a>Megoldás

Ez a hiba azt **jelzi**, hogy nincs elég múltbeli tranzakció az elmúlt évben, amelyek az egyes kategóriákat az időben, **·** **késedelmesen** és nagyon késő kategóriákban leírtnak írják le. A hiba megoldásához módosítsa a **Nagyon kései** tranzakciós időszakot. Ha a **Nagyon** kései tranzakciós időszak beállítása nem javítja ki a hibát, **akkor** a vevői fizetési előrejelzések nem használhatók a legjobb megoldásként, mivel az egyes kategóriák adataira van szükség képzési célokra.

Az időbeni, **·** **·** **·**[késedelmes és nagyon késedelmes kategóriák módosításával kapcsolatos további tudnivalókat lásd a Vevői kifizetések előrejelzésének engedélyezése.](../finance-insights/enable-cust-paymnt-prediction.md)

## <a name="symptom-model-training-failed"></a>Tünet: A modelledz<a2/<a

### <a name="resolution"></a>Megoldás

A **pénzforgalmi előrejelzési modell** képzéséhez olyan adatokra van szükség, amelyek 100 vagy több, egy évnél több tranzakciót tartalmaznak. Javasoljuk, hogy legalább két évnyi adatot és több mint 1000 tranzakciót tartalmaz.

A **Vevői kifizetések előrejelzése** funkcióhoz az előző hat-kilenc hónap alatt több mint 100 tranzakció szükséges. A tranzakciók szabadszöveges számlákat, értékesítési rendeléseket és vevői kifizetéseket tartalmazhatnak. Ezt az adatot el kell **terjeszteni** a Konfigurálás lapon megadott Időben, **·** **Késve és Nagyon késve** **beállítások** között.    

A **költségvetési javaslat** funkcióhoz legalább három év költségvetési vagy tényleges adat szükséges. Ez a megoldás az előrejelzésekben három-tíz évnyi adatot használ fel. Több mint három év jobb eredményt ad. Maga az adat akkor működik a legjobban, ha eltérések vannak az értékekben. Ha az adatok minden állandó adatot tartalmaznak, például bérletet, a képzés sikertelen lehet, mert az eltérés hiánya nem igényli az AI számára az összegek projektbehozát.

## <a name="symptom-error-message-states-that-the-table-with-name-msdyn_paypredpredictionresultentities-does-not-exist-the-remote-server-returned-an-error-404-not-found"></a>Tünet: A hibaüzenet azt jelezi, hogy nem létezik "Tábla a következő néven: "msdyn_paypredpredictionresultentities". A távoli kiszolgáló hibát adott vissza: (404) Nem található."

### <a name="resolution"></a>Megoldás

A környezet elérte az Adat –Szolgáltatási maximum táblakorlátot. A korlátról az **Exportálás az Azure-adatok**[áttekintésében található a közel valós idejű adatváltozások engedélyezése című részében található részletes tájékoztatás](../../fin-ops-core/dev-itpro/data-entities/Azure-Data-Lake-GA-version-overview.md).
