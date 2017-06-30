---
title: Munkafolyamat-elemek
description: "A cikk ismerteti a munkafolyamat különböző összetevőit."
author: sericks007
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 56441
ms.assetid: de740262-6ffd-42b9-a325-540eae5cec94
ms.search.region: Global
ms.author: tjvass
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: a3a12080efcb138365c26981abd51222c51663ff
ms.contentlocale: hu-hu
ms.lasthandoff: 05/25/2017


---

# <a name="workflow-elements"></a>Munkafolyamat-elemek

[!include[banner](../includes/banner.md)]


A cikk ismerteti a munkafolyamat különböző összetevőit.

Egy munkafolyamat elemekből áll. A következő részek az elemek összes típusát.

## <a name="tasks"></a>Feladatok
A *feladat* egy olyan munkaegység, amelyet el kell végezni. Kétféle típusú feladat adható hozzá egy munkafolyamathoz: manuális feladatok és automatizált feladatok.

### <a name="manual-task"></a>Kézi feladat

A *manuális feladat* egy olyan munkaegység, amelyet a hozzárendelt felhasználónak kell elvégeznie. Például egy költségjelentési munkafolyamat tartalmazhat manuális feladatokat, amelyeknél a hozzárendelt felhasználóknak a következő műveleteket kell végrehajtaniuk:

-   Tekintse át a költségjelentésekkel együtt leadott nyugtákat.
-   Hívja az alkalmazott felettesét.

### <a name="automated-task"></a>Automatizált feladat

Egy *automatizált feladat* egy olyan munkaegység, amelyet a rendszernek kell elvégeznie. Nincs szükség emberi beavatkozásra Például egy értékesítési jelentéshez tartozó munkafolyamat tartalmazhat automatizált feladatokat, amelyeknél a rendszernek a következő műveleteket kell végrehajtania:

-   Hitelkeret-ellenőrzés végrehajtása.
-   Vevőrekord létrehozása a vevő számára, ha nem létezik még ilyen rekord.

## <a name="approval-processes"></a>Jóváhagyási folyamatok
A *jóváhagyási folyamat* egy több lépésből álló folyamat. Az egyes jóváhagyási lépésekkel a felhasználó a következő műveleteket végezheti el:

-   A dokumentum jóváhagyása
-   A dokumentum elutasítása
-   A dokumentum módosításának kérése
-   A dokumentum másik felhasználóhoz rendelése jóváhagyásra.

## <a name="lineitem-workflow-elements"></a>Sortétel munkafolyamatának elemei
Munkafolyamat létrehozható dokumentumok vagy a sorban szereplő cikkek egy dokumentumban való feldolgozásához. Például létrehozott jóváhagyási munkafolyamatot időnyilvántartásokhoz. (Erre a munkafolyamatra *dokumentum-munkafolyamat* néven fogunk hivatkozni.) Lehetőség van *egy sortétel-munkafolyamat* elem hozzáadásához a dokumentum-munkafolyamathoz. A sortétel-elem futtatásakor a rendszer a dokumentumon szereplő minden sortételt elküld feldolgozásra. Lehet, hogy az azonos sortétel-munkafolyamattal akarja feldolgoztatni a sorban szereplő cikkeket, vagy egy másik sortétel-munkafolyamattal szeretné feldolgoztatni a sorban szereplő cikkeket. Tegyük fel, hogy az alkalmazott elküldött egy időnyilvántartást, amely hasonlít az alábbi ábrára. ![Munkafolyamat sortételekkel](./media/workflow_lineitemworkflow.gif) Ebben az esetben szükség lehet, a következő sortétel-munkafolyamatok létrehozására:

-   **Sortétel-munkafolyamat 1** – A munkafolyamat segítségével az 1111 projektazonosítójú sortételeket lehet feldolgozni.
-   **Sortétel-munkafolyamat 2** – A munkafolyamat segítségével a 2222 projektazonosítójú sortételeket lehet feldolgozni.
-   **Sortétel-munkafolyamat 3** – A munkafolyamat segítségével a 3333 projektazonosítójú sortételeket lehet feldolgozni.

## <a name="flowcontrol-elements"></a>Vezérlési folyamat elemei
A következő elemek lehetővé teszik, hogy olyan munkafolyamatokat tervezzen, amelyek másodlagos ágakkal vagy egyszerre futó ágakkal rendelkeznek.

### <a name="manual-decision"></a>Manuális döntés

A *manuális döntés* egy olyan pont, ahol a munkafolyamat két ágra válik szét. A felhasználónak végre kell hajtania a döntést, és ez a döntés határozza meg, hogy a benyújtott dokumentum feldolgozásához melyik ágat kell követni.

### <a name="conditional-decision"></a>Feltételes döntés

A *feltételes döntés* is egy olyan pont, ahol a munkafolyamat két ágra válik szét. Azonban itt a rendszer dönt, hogy a benyújtott dokumentum feldolgozásához melyik ágat kell követni. Ahhoz, hogy ezt a döntést meghozza, a rendszer kiértékeli a dokumentumot, hogy meghatározza, hogy az megfelel-e meghatározott feltételeknek.

### <a name="parallel-activity"></a>Párhuzamos tevékenység

A *párhuzamos tevékenység* egy olyan munkafolyamat-elem, amely két vagy több, egy időben futó munkafolyamatágat foglal magában.

### <a name="subworkflow"></a>Almunkafolyamat

Az *almunkafolyamat* egy olyan munkafolyamat, amely egy másik munkafolyamat kontextusán belül megy végbe.




