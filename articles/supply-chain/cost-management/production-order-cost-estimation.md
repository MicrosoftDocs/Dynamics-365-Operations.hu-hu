---
title: Termelési rendelés költségbecslése
description: A cikk a termelési költségbecsléssel kapcsolatos információkról nyújt tájékoztatást. A termelési költségbecslések az előrevetített anyag- és kapacitásfelhasználás költségeivel kapcsolatos információkról nyújt információkat, amelyek a cikkek tervezett rendelésben megadott mennyiségeinek termelésekor merülnek fel.
author: JennySong-SH
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BOMCalcTrans, InventCostTrans, ProdCalcTrans, ProdTableJour, ProdTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: 80633
ms.assetid: b4625d10-c852-4fda-b718-79df458de0d4
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yanansong
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ac658b49109a3fb3f987cf30bfa0b62bbff3d1c2
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/03/2022
ms.locfileid: "8672262"
---
# <a name="production-order-cost-estimation"></a>Termelési rendelés költségbecslése

[!include [banner](../includes/banner.md)]

A cikk a termelési költségbecsléssel kapcsolatos információkról nyújt tájékoztatást. A termelési költségbecslések az előrevetített anyag- és kapacitásfelhasználás költségeivel kapcsolatos információkról nyújt információkat, amelyek a cikkek tervezett rendelésben megadott mennyiségeinek termelésekor merülnek fel. 

Miután létrehozta a termelési rendelés, meg kell becsülnie a termelési költségeik. A cél a cikk és a termelési ütemezésre vonatkozó útvonal-felhasználás megbecslése, mert ezek a becslések képezik a későbbi ütemezés és a termelési folyamatok alapját.

## <a name="production-cost-estimation"></a>Termelés költségbecslése
A termelési költségek becslései a következő adatokon alapulnak:

-   A termelési rendelés mennyisége
-   A termelési anyagjegyzékek (BOM) összetevői
-   Az útvonalműveletek a termelési útvonalon
-   Az összetevőkre és műveletekre vonatkozó közvetett költségek
-   Aktív költségek adatai a kiszámításának dátumaként

Ha a termelési anyagjegyzékben egy álsor cikk szerepel, a számítások jelzik az álsor összetevőit és útvonalműveleteit. Alkalmazhat feladatbecslést a becsült költségek újraszámítására annak érdekében, hogy azok frissített adatokat tükrözzenek. Például a frissített adat lehet a termelési rendelésben szereplő mennyiségre vonatkozó változó, a termelési anyagjegyzék összetevő, a termelési útvonal útvonalműveleteiben szereplő termelési útvonal, az összetevőkre és műveletekre vonatkozó közvetett költség vagy az újraszámítási dátumként megjelenő aktív költség adat. A becsültköltség-számítások a költség + árrés módszeren alapuló termelési cikk eladási árát is javasolják. A becsültköltség-számítások igény szerint vonatkozhatnak hivatkozási rendelésekre is, amelyek a termelési rendeléshez kapcsolódó többi termelési rendeléseket tükrözik.

## <a name="view-the-estimated-costs"></a>A becsült költségek megtekintése
Becslés futtatása után megtekintheti az eredményeket az **Árkalkuláció** lapon. A becslés következő értékeket számítja ki:

-   **Termelési költség** – A termelési költség a becslés legfelső sora. Megjeleníti a termelési rendelés lefuttatásának teljes költségét és a termelés teljes eladási árát. Ez az érték a becslésben szereplő összes költségsor összege.
-   **Útvonal vagy erőforrás költségek** – Az Útvonal vagy az erőforrás költségek a termelési műveletek költségei. Az elemek költségét, csak úgy mint a beállítási időt, a lefutási időt és a többletköltséget tartalmazzák.
-   **Anyagköltségek** – Az Anyagköltségek a cikkek előállításához szükséges anyagjegyzék-összetevők költségei és árai. Ezeket a költségeket korábban létrehozták és rögzítették a rendszerben.

## <a name="other-uses-of-cost-estimation"></a>A költségbecslések egyéb felhasználási területei
A Költségbecslés a következő adatokat is tartalmazza:

-   Megalapozott árajánlatok
-   A rendelés nyereségességére vonatkozó becslések
-   Becslések a nyersanyag-felhasználásra vonatkozóan.
-   A korábbi termelésekből származó költségadatok összehasonlítása
-   Költségvetési és előrejelzési adatok.
-   Az adott költségszint fenntartásához szükséges termelési mennyiség becslései.






[!INCLUDE[footer-include](../../includes/footer-banner.md)]