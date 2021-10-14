---
title: Bejövő hajóutak és szállítókonténerek útjainak követése
description: Ez a témakör bemutatja, hogy hogyan lehet nyomon követni a hajóutak és a szállítókonténerek útjának előrehaladását a Bejövő nyomon követés lapon.
author: sherry-zheng
ms.date: 01/13/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ITMContainerActivityTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-01-13
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 67ee22af7a73c18d4f77018fedf5a89f0777774d
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/29/2021
ms.locfileid: "7580768"
---
# <a name="track-inbound-voyages-and-shipping-container-journeys"></a>Bejövő hajóutak és szállítókonténerek útjainak követése

[!include [banner](../../includes/banner.md)]

A **Bejövő nyomon követés** lapon követhető a hajóutak és a szállítókonténerek útjának előrehaladása. Minden út és utazás *tevékenység* szerint le van bontva, mindegyiknek saját sora van az oldalon. A lapon becsült dátumokat és tényleges dátumokat lehet megtekinteni és megadni tevékenység szerint.

A [Követési vezérlőközpont](delivery-information-setup.md#tracking-control-center) beállításaitól függően ezek a tevékenységek általában automatikusan a végső célnál történő partraszállítás becsült dátumát mutatják. A beállítástól függően a végső dátum általában a beszerzési rendelés sorában frissíti a szállítási dátumot vagy a visszaigazolt dátumot. Átmozgatásirendelés-soroknál beállíthatja, hogy a rendszer frissítse a bevételezési dátumot.

A **Bejövő követés** oldal megnyitásához nyissa meg a **Partraszállítási költség \> Követés \> Bejövő követés** részt.

## <a name="filter-the-activities-list"></a>A tevékenységek listájának szűrése

A **Bejövő követés** lap tetején található **Hajóút** és **Szállítókonténer** mezőkkel szűrheti az oldalt, hogy csak a kiválasztott hajóúthoz és/vagy szállítókonténerhez tartozó tevékenységeket jelenítse meg.

## <a name="update-tracking-information"></a>Nyomonkövetési adatok frissítése

Hajóút vagy út ütemezésének frissítéséhez adja meg az első tevékenység kezdő dátumát. A utolsó tevékenység becsült záró dátuma ezután frissül. A [Követési vezérlőközpontban](delivery-information-setup.md#tracking-control-center) az egyes szakasz- és utazássablonok beállításai határozzák meg a becsült átfutási időket. A becsült befejezési dátumok a tevékenység kezdő dátumától számított átfutási időt használják. Ezután, amikor a tényleges záró dátum rögzítésre kerül, a következő tevékenység kezdő dátuma is az előző tevékenység tényleges záró dátumának megfelelő dátumra módosul. A tényleges átfutási idő frissül, így összehasonlítást és elemzést lehet végezni. A **Megjegyzés** mezőben további megjegyzések is beírhatók.

A rácson végzett tevékenységek sorrendjét a megfelelő útsablonban a szakaszok sorrendje határozza meg. Ha a csatolt utak szakaszainak sorrendje megváltozik, a követési vezérlő is megváltozik.

Ha minden tárolóhoz frissíteni szeretné a dátumokat, válassza a **Kezdő dátum frissítése** vagy a **Tényleges záró dátum frissítése** lehetőséget a Művelet panelen. Alternatív megoldásként a szállítmányban konténerenként is megadhatja a dátumokat. Ez a megközelítés nagyobb rugalmasságot tesz lehetővé, mivel a konténereket többutas környezetben is fel lehet osztani.

## <a name="buttons-on-the-action-pane"></a>A Művelet panel gombjai

A **Bejövő követés** oldal Művelet paneljén található gombokkal lehet kezelni a bejövő hajóutakat és utakat. A következő táblázat az elérhető gombokat írja le:

| Gomb | Leírás |
|---|---|
| Szerkesztés | Hajóút vagy konténerút szerkesztése. |
| Új | Új hajóút vagy konténerút létrehozása. |
| Eltávolítás | Kiválasztott hajóút vagy konténerút törlése. |
| Kezdő dátum frissítése | Egy tevékenység kezdő dátumának frissítése a hajóúton található összes konténer esetében. Ha egy meghatározott tevékenység vagy útszakasz kezdő dátumát frissítik, akkor az azt követő becsült kezdő dátumok frissítése a megadott átfutási idő alapján történik. |
| Tényleges záró dátum frissítése | Egy tevékenység záró dátumának frissítése a hajóúton található összes konténer esetében. Ha egy meghatározott tevékenység vagy útszakasz záró dátumát frissítik, akkor az azt követő tevékenységek becsült frissítése a megadott átfutási idő alapján történik. |
| Tevékenységek hozzáadása | Tevékenység manuális hozzáadása egy hajóúthoz. Felvehet például egy fertőtlenítés tevékenységet. A kiegészítés hatására megváltozhat a hajó vagy hajóút áruinak visszaigazolt szállítási dátuma. Ha egy tevékenységet hozzáadnak az úthoz, akkor a becsült napok nem kerülnek megadásra, amíg meg nem frissül az utazás szakaszának kezdő dátuma. |

## <a name="information-and-settings-on-the-overview-tab"></a>Az Áttekintés lapon található információk és beállítások

Az **Áttekintés** lap az oldal tetején kiválasztott hajóúthoz és/vagy szállítókonténerhez tartozó összes tevékenység listáját jeleníti meg. Az alábbi táblázat bemutatja az egyes tevékenységekhez rendelkezésre álló mezőket.

| Mező | Leírás |
|---|---|
| Szakasz | A tevékenység szakaszazonosítója, az útsablonban meghatározottak szerint. |
| Szállítás módja | A tevékenység várt szállítási módja. |
| Tevékenység | Ez a mező általában azonosítja a tevékenységhez társított munkát vagy feladatot. Jellemző például a *Hajózás* és a *Vámvizsgálat*. |
| Leírás | A tevékenység hosszabb leírása. |
| Kezdés dátuma | A mező kezdetben a tevékenység becsült kezdő dátumát mutatja. Az előző tevékenység tényleges záró dátumának bevitele után azonban a tényleges kezdő dátum látható. Ez a mező az átfutási idő alapján a becsült záró dátum meghatározására használható. |
| Becsült záró dátum | A mező értékének számítása a kezdő dátum és az átfutási idő alapján történik. Általában nem szerkeszti közvetlenül az értéket. |
| Tényleges befejezési dátum | A felhasználónak a tevékenység megtörténte után a lehető leghamarabb frissítenie kell ezt a mezőt. Ezután frissül a tényleges átfutási idő. |
| Becsült napok száma | A tevékenység elvégzéséhez szükséges becsült idő (napban megadva). |
| Tényleges napok száma | A tevékenység elvégzéséhez szükséges tényleges idő (napban megadva). |
| Bankjegy | Ebben a mezőben egyéb megjegyzéseket és adatokat adhat meg a tevékenységről. |

## <a name="information-and-settings-on-the-general-tab"></a>Az Általános lapon található információk és beállítások

Az **Általános** lap az **Áttekintés** lapon kijelölt szakasz adatait jeleníti meg. Bár az **Áttekintés** lapon megjelenő információk egy részét megismétli, a kiválasztott szakaszra vonatkozó további információkat is tartalmaz.
