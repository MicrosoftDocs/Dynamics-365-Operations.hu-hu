---
title: A kezdeti vevői fizetési előrejelzési modell kiértékelése
description: Ez a témakör ismerteti azokat a lépéseket, amelyek segítségével jobban megértheti a vevői kifizetések előrejelzési modelljét, és kiértékelheti annak hatékonyságát.
author: ShivamPandey-msft
ms.date: 05/02/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-05-28
ms.dyn365.ops.version: AX 10.0.8
ms.openlocfilehash: fcdf276505cf58267a38e9d6174a155ad307653b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8847002"
---
# <a name="evaluate-the-initial-customer-payment-prediction-model"></a>A kezdeti vevői fizetési előrejelzési modell kiértékelése

[!include [banner](../includes/banner.md)]

Ez a cikk azt mutatja be, hogyan lehet kiértékelni egy előrejelzési modellt, miután bekapcsolta a Pénzügyi adatáttekintéseket, majd előállította és előállította az első modellt. Ez a cikk a vevői kifizetések előrejelzésére használható modelleket tartalmazza. Azokat a lépéseket mutatja be, amelyekkel megismerheti a vevői kifizetési előrejelzési modellt, és értékelheti annak hatékonyságát.

## <a name="getting-details-about-the-model"></a>A modell részleteinek megszerzése

A Pénzügyi információk **paraméterei oldalon,** a 365 Pénzügy Microsoft Dynamics **, a Modellek pontosságának javítása hivatkozás jelenik meg a pontossági** pontszám mellett.

[![Modell pontosságának javítása hivatkozás.](./media/prediction-model.png)](./media/prediction-model.png)

Ez a hivatkozás a következő lépésekkel kapcsolható AI Builder össze, ahol további tudnivalókat lehet ismerkedni az aktuális modellel, és lépéseket lehet tenni annak javítása érdekében. A következő ábrán egy megnyitott oldal látható.

[![AI Builder.](./media/what-to-predict.png)](./media/what-to-predict.png)

A megnyitott oldal az alábbi információt mutatja:

- A **Teljesítmény** szakaszban a modell teljesítményi osztálya biztosítja a modell minőségét. Erről az osztályról a dokumentáció [előrejelzési modell](/ai-builder/prediction-performance) teljesítményével kapcsolatban tartalmaz további AI Builder tájékoztatást.
- A **Legbefolyásosabb adat** szakasz bemutatja, hogy milyen fontos a különböző típusú adatok bevitele a modellhez. A lista és a megfelelő százalékok értékelésével meghatározhatja, hogy az adatok összhangban vannak-e a vállalattal és a piaccal kapcsolatos ismeretekkel.

    [![Teljesítmény és legbefolyásosabb adatszakaszok az előrejelzési modellhez.](./media/models.png)](./media/models.png)

- A **Teljesítmény** szakaszban válassza a **Részletek megjelenítése** lehetőséget, ha többet szeretne megtudni az osztályról és egyéb szempontokról. A következő ábrán a részletek azt mutatják, hogy a modell a javasoltnál kevesebb információt használ. A rendszer emiatt figyelmeztető üzenetet hozott létre.

    [![A modell teljesítményével kapcsolatos figyelmeztetések.](./media/details.png)](./media/details.png)

## <a name="digging-deeper"></a>Mélyebbre ásás

Bár a pontosság jól kiindulópontként szolgál egy modell értékeléséhez, és a teljesítmény-fokozat ad szempontot, AI Builder részletesebb mérőszámokat is biztosít, amelyek az értékeléshez használhatók. A részletek letöltéséhez kattintson a **Teljesítmény** szakaszban a három pont gombra (**...**) a **Modell használata** gombra, majd válassza ki a **Részletes metrikák letöltése** lehetőségre.

[![Részletes metrikák letöltése parancs.](./media/performance.png)](./media/performance.png)

A következő ábra bemutatja azt a formátumot, amelyen le lehet tölteni az adatokat.

[![Letöltött adatok formátuma.](./media/data-format.png)](./media/data-format.png)

Az eredmények mélyebb elemzéséhez egy jó kiindulási pontot kell áttekinteni a „zavartság-mátrix” metrikájában. Itt látható például az előző ábra ehhez a metrikához megjelenített adatai.

`{"name": "Confusion Matrix", "value": {"schema_type": "confusion_matrix", "schema_version": "1.0.0", "data": {"class_labels": ["0", "1", "2"], "matrix": [[71, 9, 21], [5, 0, 27], [2, 0, 45]]}}, "type": "dictionaryNumericalList", "isGlobalScore": false}`

Ezeket az adatokat a következő módon lehet kibontani.

| &nbsp;                   | Előrejelzés szerint Időben | Előrejelzés szerint Későn | Előrejelzés szerint Nagyon későn |
|--------------------------|-------------------|----------------|---------------------|
| Időben történő kifizetés   | **71**            | 0              | 21                  |
| Tényleges késedelmes fizetés      | 5                 | **0**          | 27                  |
| Tényleges nagyon késedelmes fizetés | 2                 | 0              | **45**              |

A zavartság mátrix megmutatja a kiválasztott vizsgálati adathalmaz eredményeit a képzési folyamatból. Mivel ezeket a lezárt számlákat nem használták fel a modell tanítására, jó teszteseteket mutatnak be a modellhez. Ezenkívül, mivel a számla tényleges állapota ismert, a modell teljesítménye is látható.

A legáltalánosabb tényleges érték az első dolog, ami a leggyakrabban keresendő. Annak ellenére, hogy ez az érték nem teljesen igazodik a teljes adathamazhoz, észszerű megközelítés. Ebben az esetben a **Tényleges időben történő fizetés** a 171 számlából a 92-re esik, és ez a leggyakrabb tényleges érték. Ezért ez jó kiindulás a modelljének. Ha csak megbecsülte, hogy az összes számla időben lesz fizetve, akkor 92-szer lenne igaza a 171-ből (azaz 54 százalékban).

Fontos, hogy megértse, mennyire kiegyensúlyozott az adathalmaza. Ebben az esetben 171-ból 92-t fizettek ki időben, 32-t későn, 47-et pedig nagyon későn. Ezek az értékek észszerűen kiegyensúlyozott adathalmazt jeleznek, mivel az egyes kategóriákban nem triviális eredmények szerepelnek. Az a helyzet, amikor az egyik állapotnak nagyon kevés eredménye van, így kihívást jelenthet egy gépi tanulási modell esetében.

A modell pontossága a teszt adathalmaz helyes előrejelzési számát jelzi. Ezek a helyes előrejelzések az előző példában félkövér betűvel szereplő értékek. Ebben az esetben az értékek 67,8 százalékban számítottak pontosan (= \[71 + 0 + 45\] ÷ 171). Ez az érték 14 százalékos javulást jelent a 54 százalékos kiinduló becsléshez képest, és a modell minőségének egy mutatója.

Ha jobban szemügyre veszi a zavartság-mátrixot, akkor észreveheti, hogy a modell jó munkát végez az idő- és a késedelmes számlakifizetések előrejelzésében. Azonban helytelen 32 számla esetében, amelyek ténylegesen későn lettek kifizetve (de nem túl késő). Ez az eredmény arra utal, hogy a modell további felfedezésére és javítására van szükség.

A modell teljesítményét a pontosságnál jobban képviselő szám az F1 makrópontszám. Ez a pontszám figyelembe veszi az egyes osztályzási állapotok eredményeit (időben, későn és nagyon későn). Itt látható például az előző ábra ehhez az „F1 makró”metrikához megjelenített adatai.

`{"name": "F1 Macro", "value": 0.4927170868347339, "type": "percentage", "isGlobalScore": false}`

Ebben az esetben az F1 makrópontszám körülbelül 49,3 százalékban azt jelzi, hogy a modell nem nyújt hatékony előrejelzéseket az egyes állapotok esetében, annak ellenére, hogy az általános pontosságpontszám úgy tűnik, meglehetősen magas.

## <a name="improving-the-model"></a>A modell javítása

Miután jobban megértette az első modell eredményeit, érdemes lehet javítani a modellt a jellemzőoszlopok hozzáadásával vagy eltávolításával, vagy az adatkészlet olyan részeinek szűrésével, amelyek nem támogatják a pontos előrejelzéseket. Zárja be AI Builder, majd indítsa **újra** a folyamatot a Dynamics 365 Pénzügy AI Builder modellhivatkozásával. Kísérletezhet a különböző jellemzőkkel anélkül, hogy befolyásolná a közzétett modellt. A közzétett modellt csak akkor befolyásolja, ha a **Közzététel** lehetőséget választja. Ne feledje, hogy a Dynamics 365 Pénzügy ön példánya egyetlen modellt használ. Ezért a közzététel előtt alaposan tekintse át az új modelleket.

## <a name="for-more-information"></a>További információ

Az előrejelzési modellek kiértékelésével kapcsolatos további információt a [Gépi tanulási modellek eredményei](confusion-matrix.md) részben talál

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
