---
title: Készpénzpozíció
description: Ez a témakör azt mutatja be, hogyan lehet a Pénzforgalmi előrejelzési funkció egy szervezet készpénzpozícióját egy adott időpontra megjósolni. Leírja a különböző időszakok előrejelzésének megjelenítésére használható beállításokat is.
author: ShivamPandey-msft
ms.date: 12/21/2021
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
ms.search.validFrom: 2019-11-06
ms.dyn365.ops.version: AX 10.0.8
ms.openlocfilehash: 6bb99084a2ffef067dd0d7158ecb5e57d6d97d75
ms.sourcegitcommit: c8dc60bb760553f166409c2e06dd2377f601c006
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/23/2021
ms.locfileid: "7945789"
---
# <a name="cash-position"></a>Készpénzpozíció

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

A készpénzpozíció a pénzforgalom előrejelzése, amely a közeljövőben várható. Ennek alapja a vevőktől érkező készpénz-befizetések leképezése, amelyek kifizetik a kinnlévő számlákat és rendeléseket, valamint a szállítóknak a beszerzési számlákra és rendeléseket is.

Amikor a rendszer vevői kifizetéseket jósol, a kifizetési előrejelzéseket a vevői kifizetési előrejelzés funkcióból veszi át. A kifizetési előrejelzések nélkül a vevői számla minden vevő számára történő kifizetéséhez szükséges átlagos időt kell használni a kifizetés dátumának kiszámításához. Kinnlévő vevői rendeléseknél a rendszer a számlázási dátumot a vevők által számlázott rendelési sorok átlagos számának alapján számítja ki. Ezt követően a számla dátumát használja a fizetési előrejelzési funkció bemenetként. A vevői kifizetési előrejelzés funkció minden rendelési sorhoz kiszámítja a fizetési dátumot. 

A kinnlévő számlák kifizetési dátumának becslése a kifizetési előrejelzések alapján úgy, hogy választ egy olyan dátumot, amely megfelel az előrejelzett gyűjtő valószínűsége alapján kapott kumulatív elosztási függvény ötvenedik percentilisének.

Hasonló megközelítést alkalmaz a szállítóknak történő kifizetések előrejelzésére. A rendszer minden szállítónál kiszámítja a szállítói számla kifizetéshez történő átalakításához szükséges átlagos időt. A napok számát ezután arra használják, hogy kiszámolják a kifizetés dátumát. A nyitott szállítói rendelések esetében a rendszer a számlázási dátumot úgy számolja ki, hogy figyelembe veszi, hogy hány nap szükséges a rendelési sorok számlára való átalakításához az egyes szállítóknál. A rendszer ezután kiszámítja a kifizetési dátumot minden szállítói számla kifizetéshez történő átalakítás átlagos idejének felhasználásával.

A **Készpénzpozíció** fül felső szakasza tartalmaz egy készpénzpozíció diagramot. Ez a grafikon bemutatja a pénzbevételeket és a kiáramlásokat, valamint hatásukat a teljes likviditási egyenlegre. A készpénzpozíció adatai napi, heti, havi vagy negyedéves időszakokban is megtekinthetők. Amikor kiválasztja a **Naponta** beállítást, megtekintheti a következő 21 napra vonatkozó előrejelzéseket. Amikor kiválasztja a **Heti** beállítást, megtekintheti a következő 20 hétre vonatkozó előrejelzéseket. Amikor kiválasztja a **Havi** beállítást, megtekintheti a következő 12 hónapra vonatkozó előrejelzéseket. Amikor kiválasztja a **Negyedéves** beállítást, megtekintheti a következő 12 negyedévre vonatkozó előrejelzéseket. Ha azt szeretné, hogy a képernyő tartalma a **Készpénzpozíció** fülön látható legyen, akkor elrejtheti a diagramot.

A **Készpénzpozíció** fül alsó részében talál részleteket a pozícióval, a készpénzáramlással, az előrejelzett kifizetésekkel és a bankfiókkal kapcsolatos részleteket.

- A **Készpénzpozíció** rácsban szereplő adatok három részből állnak: a likviditási fiókok listája, a készpénzforgalomban felépített dokumentumok listája, valamint a készpénzforgalmi kivezetéseket alkotó dokumentumok listája. A rács a készpénzforgalmi egyenlegeket is megjeleníti. Az első megjelenített időszak esetében a likviditási számlák egyenlege a nyitó egyenleg. A következő időszakok esetében a likviditási fiókok egyenlegeit a pénzbevételek hozzáadásával és az előző időszakokból származó pénzkiadások kivonása alapján számítja ki a program. Az egyenleget alkotó tranzakciók részleteinek megtekintéséhez válassza ki az **Egyenleg** hivatkozását.
- A **Készpénzforgalom** rács a pénzbevételeket, az időszakonként összesített pénzkiáramlásokat, valamint a likviditási fiókok egyenlegére gyakorolt hatásukat jeleníti meg. Az első időszak esetében a likviditási számlák egyenlege a nyitó egyenleg. A következő időszakok esetében a likviditási fiókok egyenlegeit a pénzbevételek hozzáadásával és az előző időszakokból származó pénzkiadások kivonása alapján számítja ki a program.
- Az **Előrejelzett banki egyenleg** rács jeleníti meg a várható pénzkiáramlás és azok likviditási számlákra gyakorolt hatását.
- A **Bankfiók** rács a várható pénzbe- és kiáramlások hatását jeleníti meg a banki egyenlegen.

A készpénzpozíció mentéséhez és szerkesztéséhez hozzon létre egy pillanatképet. További tájékoztatás a pillanatképekkel kapcsolatban itt találhat: [Pillnatképek – áttekintés](payment-snapshots.md).

## <a name="details-of-the-cash-position-capability"></a>A készpénzpozíció képességének részletei 

A Készpénz pozíció funkció a következő funkciókat tartalmazza. 

- A készpénzpozíció funkció a rendszerben meglévő dokumentumokon alapuló cashflow-t, valamint a külső rendszerekből importált készpénzbeáramlási és kiáramlási sorokat mutatja.
- Segítségével egyszerű a pénzforgalmi adatok külső rendszerekből Dynamics 365 Finance-be történő integrálása. A készpénzpozíció az adatimportálási-exportálási keretrendszert is használhatja. Ez a keretrendszer megkönnyíti az Excel OData-val történő integrációt. Több forrásból származó adatokat is kombinálhat egy átfogó készpénzpozíciós megoldás létrehozásához.
- Intelligens készpénzpozíciót vezet be. A készpénzpozíció az ügyfél fizetési viselkedése alapján jön létre, hogy megjósolja, mikor számíthat a vállalat készpénz megérkezésére a számlájukra.
- Vevői rendelések és számlák esetében a vevői fizetési előrejelzés AI funkciója határozza meg az előző vevői fizetési viselkedést, amikor egy rendelést vagy számlát fizetnek.
- Szállítói rendelések és számlák esetében a szállítás és a számla közötti átlagos időt, valamint szállítónkénti számla kifizetését használjuk annak meghatározására, hogy mikor fizetnek ki egy szállítói rendelést vagy számlát, így pontosabbak lesznek a kiáramlások.

Ez pontosabb képet ad a pénzforgalomról a kincstárnok múltbeli fizetési viselkedése alapján. 

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
