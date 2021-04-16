---
title: Munkafolyamat-elemek
description: A témakör ismerteti a munkafolyamat különböző összetevőit.
author: ChrisGarty
ms.date: 11/03/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 56441
ms.assetid: de740262-6ffd-42b9-a325-540eae5cec94
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 20f320e84d5faaf964585f30581d24996131031c
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5747151"
---
# <a name="workflow-elements"></a>Munkafolyamat-elemek

[!include [banner](../includes/banner.md)]

A témakör ismerteti a munkafolyamat különböző összetevőit.

Egy munkafolyamat elemekből áll. A következő részek az elemek összes típusát.

## <a name="tasks"></a>Feladatok

A *feladat* egy olyan munkaegység, amelyet el kell végezni. Kétféle típusú feladat adható hozzá egy munkafolyamathoz: manuális feladatok és automatizált feladatok.

### <a name="manual-task"></a>Kézi feladat

A *manuális feladat* egy olyan munkaegység, amelyet a hozzárendelt felhasználónak kell elvégeznie. Például egy költségjelentési munkafolyamat tartalmazhat manuális feladatokat, amelyeknél a hozzárendelt felhasználóknak a következő műveleteket kell végrehajtaniuk:

- Tekintse át a költségjelentésekkel együtt leadott nyugtákat.
- Hívja az alkalmazott felettesét.

### <a name="automated-task"></a>Automatizált feladat

Egy *automatizált feladat* egy olyan munkaegység, amelyet a rendszernek kell elvégeznie. Nincs szükség emberi beavatkozásra Például egy értékesítési jelentéshez tartozó munkafolyamat tartalmazhat automatizált feladatokat, amelyeknél a rendszernek a következő műveleteket kell végrehajtania:

- Hitelkeret-ellenőrzés végrehajtása.
- Vevőrekord létrehozása a vevő számára, ha nem létezik még ilyen rekord.

## <a name="approval-processes"></a>Jóváhagyási folyamatok

A *jóváhagyási folyamat* egy több lépésből álló folyamat. Az egyes jóváhagyási lépésekkel a felhasználó a következő műveleteket végezheti el:

- A dokumentum jóváhagyása
- A dokumentum elutasítása
- A dokumentum módosításának kérése
- A dokumentum másik felhasználóhoz rendelése jóváhagyásra.

## <a name="line-item-workflow-elements"></a>Sortétel munkafolyamatának elemei

Munkafolyamat létrehozható dokumentumok vagy a sorban szereplő cikkek egy dokumentumban való feldolgozásához. Például létrehozott jóváhagyási munkafolyamatot időnyilvántartásokhoz. (Erre a munkafolyamatra *dokumentum-munkafolyamat* néven fogunk hivatkozni.) Lehetőség van *egy sortétel-munkafolyamat* elem hozzáadásához a dokumentum-munkafolyamathoz. A sortétel-elem futtatásakor a rendszer a dokumentumon szereplő minden sortételt elküld feldolgozásra. Lehet, hogy az azonos sortétel-munkafolyamattal akarja feldolgoztatni a sorban szereplő cikkeket, vagy egy másik sortétel-munkafolyamattal szeretné feldolgoztatni a sorban szereplő cikkeket. Tegyük fel, hogy az alkalmazott elküldött egy időnyilvántartást, amely hasonlít az alábbi ábrára.

![Munkafolyamat sortételekkel](./media/workflow_lineitemworkflow.gif)

Ebben az esetben szükség lehet a következő sortétel-munkafolyamatok létrehozására:

- **Sortétel-munkafolyamat 1** – A munkafolyamat segítségével az 1111 projektazonosítójú sortételeket lehet feldolgozni.
- **Sortétel-munkafolyamat 2** – A munkafolyamat segítségével a 2222 projektazonosítójú sortételeket lehet feldolgozni.
- **Sortétel-munkafolyamat 3** – A munkafolyamat segítségével a 3333 projektazonosítójú sortételeket lehet feldolgozni.

## <a name="flow-control-elements"></a>Vezérési folyamat elemei

A következő elemek lehetővé teszik, hogy olyan munkafolyamatokat tervezzen, amelyek másodlagos ágakkal vagy egyszerre futó ágakkal rendelkeznek.

### <a name="manual-decision"></a>Manuális döntés

A *manuális döntés* egy olyan pont, ahol a munkafolyamat két ágra válik szét. A felhasználónak végre kell hajtania a döntést, és ez a döntés határozza meg, hogy a benyújtott dokumentum feldolgozásához melyik ágat kell követni.

### <a name="conditional-decision"></a>Feltételes döntés

A *feltételes döntés* is egy olyan pont, ahol a munkafolyamat két ágra válik szét. Azonban itt a rendszer dönt, hogy a benyújtott dokumentum feldolgozásához melyik ágat kell követni. Ahhoz, hogy ezt a döntést meghozza, a rendszer kiértékeli a dokumentumot, hogy meghatározza, hogy az megfelel-e meghatározott feltételeknek.

### <a name="parallel-activity"></a>Párhuzamos tevékenység

A *párhuzamos tevékenység* egy olyan munkafolyamat-elem, amely két vagy több, egy időben futó munkafolyamatágat foglal magában.

### <a name="subworkflow"></a>Almunkafolyamat

Az *almunkafolyamat* egy olyan munkafolyamat, amely egy másik munkafolyamat kontextusán belül megy végbe.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]