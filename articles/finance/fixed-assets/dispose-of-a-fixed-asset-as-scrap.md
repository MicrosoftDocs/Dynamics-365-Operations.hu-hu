---
title: Tárgyi eszközök kivezetése selejtként
description: Ez a témakör azt mutatja be, hogyan lehet kiküszöbölni a tranzakciókat olyan tárgyi eszközök esetében, amelyek selejtként kerültek kivezetésre.
author: moaamer
ms.date: 08/14/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2019-08-14
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: 413847d350ca6b2bdd6153a598ea5b3f34a33818
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5826275"
---
# <a name="dispose-of-a-fixed-asset-as-scrap"></a>Tárgyi eszközök kivezetése selejtként

[!include [banner](../includes/banner.md)]

Ez a témakör azt mutatja be, hogyan lehet kiküszöbölni a tranzakciókat olyan tárgyi eszközök esetében, amelyek selejtként kerültek kivezetésre. Az eltávolítható tranzakciótípusok között szerepelnek egy eszköz beszerzési és felhalmozott értékcsökkenési tranzakciói, valamint egyéb tárgyieszköz-tranzakciói. Ezeknek a tranzakcióknak a felszámolása érinti a mérlegszámlákat, például a beszerzések helyesbítését, az értékcsökkenés kiigazítását, az átértékelést, a felértékelési és a leírási számlákat.

| Tranzakció                                         | Tartozás (Dr.) | Jóváírás (Cr.) |
|-----------------------------------------------------|-------------|--------------|
| Dr. Halmozott értékcsökkenés                        | X           |              |
| Cr. Tárgyi eszközök nyeresége/vesztesége                          |             | X            |
| Dr. Tárgyi eszközök nyeresége/vesztesége                          | X           |              |
| Cr. Tárgyieszköz-beszerzés számlája                 |             | X            |
| Dr. Tárgyi eszközök nyeresége/vesztesége (nettó könyv szerinti érték \[NKÉ\]) | X           |              |
| Cr. Tárgyi eszközök nyeresége/vesztesége (NKÉ)                    |             | X            |

> [!NOTE]
> Javasoljuk, hogy szorosan működjön együtt a pénzügyi vezetőjével (CFO) vagy kontrollerével, hogy azonosítsa az egyes tranzakciótípusok helyes számláit az egyes tranzakciótípusokhoz, és azt is ellenőrizzék, hogy a selejtezési folyamat és az általa létrehozott tranzakciók megfelelően frissítik azokat a számlákat.

A tárgyi eszköz selejtezése előtt létre kell hoznia azokat a főkönyvi számlákat, amelyek a tárgyi eszköz beszerzési értékéhez, az aktuális évi értékcsökkenéshez, az előző évek értékcsökkenéséhez és az eszköz NKÉ-jéhez tartoznak. A tárgyieszköz-tranzakciók típusai a **Tárgyi eszközök feladási profiljai** lapon láthatók. Nyissa meg a **Tárgyi eszközök \> Beállítások \> Tárgyieszköz-feladási profilok** menüt, majd a **Selejtezés** gyorslapon válassza ki a **Selejt** lehetőséget a rács fölötti mezőben. A következő ábra a tárgyieszköz-tranzakciótípusok listáját mutatja a **Tárgyieszköz-feladási profilok** oldalon.


[![Eszköz selejtezése selejtként, 1. ábra](./media/Fixed_asset_Disposal_scrap_scenario_1.png)](./media/Fixed_asset_Disposal_scrap_scenario_1.png)

A következő példában a tárgyi eszköz a 2018. január 1-én került beszerzésre, és azt 2019 március 31-én selejtezték le.

- **Beszerzési ár:** 24 000,00 amerikai dollár (USD)
- **Hasznos élettartam:** Két év
- **Avultatási mód:** Lineáris, élettartam szerinti értékcsökkenés
- **Értékcsökkenés összege:** 1000,00 USD havonta

A tárgyi eszköz NKÉ-je következő képlet segítségével számítható ki:

Nettó könyv szerinti érték = Beszerzési ár – értékcsökkenés

Ebben a példában a tárgyi eszköz beszerzése és avultatása 15 hónapig, 2018 januárjától 2019 márciusáig tartott. Ennek megfelelően az eszköz NKÉ-je 9000,00 USD (24 000,00 USD – 15 000,00 USD).

[![Tárgyi eszköz avultatása példa](./media/Fixed_asset_Disposal_scrap_scenario_2.png)](./media/Fixed_asset_Disposal_scrap_scenario_2.png)


A kivezetési napló létrehozásához nyissa meg a **Tárgyi eszközök \> Naplóbejegyzések \> Tárgyi eszközök naplója** lehetőséget, majd a műveleti ablaktáblán válassza a **Sorok** lehetőséget. Válassza a **Kivezetés – selejt** lehetőséget, majd válassza ki a tárgyi eszköz azonosítóját. Az eszköz teljes mértékű kivezetéséhez ne írjon be értéket **Terhelés** vagy a **Jóváírás** mezőbe.

[![Tárgyi eszközök naplója](./media/Fixed_asset_Disposal_scrap_scenario_3.png)](./media/Fixed_asset_Disposal_scrap_scenario_3.png)

A tárgyi eszközök kivezetési tranzakciója a következő módon módosítja a tárgyi eszköz könyvének mezőértékeit:

- Az **Egyenleg** szakaszban az **Állapot** mező a **selejtezettre** módosul.
- A **Kiadás** szakaszban a **Kivezetés dátuma** mező az eszköz selejtezésének dátumát adja meg.

[![Tárgyieszköz-napló részletei](./media/Fixed_asset_Disposal_scrap_scenario_4.png)](./media/Fixed_asset_Disposal_scrap_scenario_4.png)

A következő ábra a tárgyi eszköz egyenlegét jeleníti meg.

[![Tárgyieszköz egyenleg](./media/Fixed_asset_Disposal_scrap_scenario_5.png)](./media/Fixed_asset_Disposal_scrap_scenario_5.png)

A következő ábrán egy feladott bizonylat látható.

[![Nettó könyv szerinti érték](./media/Fixed_asset_Disposal_scrap_scenario_6.png)](./media/Fixed_asset_Disposal_scrap_scenario_6.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]