---
title: Beszerzési igénylések
description: Ez a témakör azt ismerteti, hogyan támogatottak a beszerzési igénylések a tervezési optimalizálásban.
author: ChristianRytt
manager: tfehr
ms.date: 01/04/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2021-01-04
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 8075f8d7c3868c6d6012edbce17dbbb4749209ab
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4992344"
---
# <a name="purchase-requisitions"></a>Beszerzési igénylések

Az alaptervezés feltöltheti a jóváhagyott beszerzési igényléseket. A beszerzési igénylések fedezésére tehát a felhasználóknak nem kell munkafolyamatot használni a beszerzési igénylések létrehozásához. Ehelyett az alaptervezés fedezheti a beszerzési igényléseket. A funkciók miatt a beszerzési igénylések a kapcsolódó termék beállított **Tervezett rendelési típusától** függően beszerzési igénylést, átmozgatási rendelést vagy termelési rendelést is előállíthat.

## <a name="enable-master-plans-to-include-requisitions"></a>Alaptervek engedélyezése az igénylések belefoglalásához

Ha az igényléseket is figyelembe kell venni az alapterv fedezetszámítása során, kövesse ezeket a lépéseket.

1. Ugorjon az **Alaptervezés** \> **Beállítás** \> **Tervek** \> **Alaptervezések** lehetőségre.
1. Hozzon létre vagy válasszon egy alaptervet.
1. Az **Általános** gyorslapon állítsa az **Igénylések befoglalása** beállítást *Igen* értékre.
1. Ismételje meg a 2. és 3. lépést minden további olyan alaptervre, amelyben szerepeltetni szeretné az igényléseket.

## <a name="approved-requisitions-time-fence"></a>Jóváhagyott igénylések időkorlátja

A *jóváhagyott igénylések időkorlátja* meghatározza, hogy az alapterv mennyire visszamenőleg (napokban) fogja tartalmazni a jóváhagyott feltöltési igénylések iránti igényt. A jóváhagyott igénylések időkorlátját mind a fedezeti csoport szintjén, mind az alapterv szintjén be lehet állítani.

### <a name="set-the-approved-requisitions-time-fence-for-a-coverage-group"></a>A jóváhagyott igénylési időkorlát beállítása fedezeti csoporthoz

1. Ugorjon az **Alaptervezés** \> **Beállítás** \> **Fedezet** \> **Fedezeti csoportok** menübe.
1. Hozzon létre vagy válasszon ki egy fedezeti csoportot.
1. Állítsa a **Jóváhagyott igénylések időkorlátja (napok)** mezőt az **Egyéb** gyorslapon az időkorlátba belefoglalandó napok számára.
1. Ismételje meg a 2. és 3. lépést minden olyan további fedezetcsoportra, ahol be szeretné állítani a jóváhagyott igénylések időkorlátját.

### <a name="set-the-approved-requisitions-time-fence-for-individual-master-plans"></a>A jóváhagyott igénylések időkorlátjának beállítása egyedi alaptervekhez

Ha egy adott alaptervhez beállít egy jóváhagyott igénylési időkorlátot, akkor a beállítás felülbírálja az esetleges fedezeti csoportok időkorlát-beállítását.

1. Ugorjon az **Alaptervezés** \> **Beállítás** \> **Tervek** \> **Alaptervezések** lehetőségre.
1. Hozzon létre vagy válasszon egy alaptervet.
1. Állítsa a **Jóváhagyott igénylések időkorlátja (napok)** mezőt az **Időkorlát napokban** gyorslapon az időkorlátba belefoglalandó napok számára.
1. Ismételje meg a 2. és 3. lépést minden olyan további alaptervre, ahol be szeretné állítani a jóváhagyott igénylések időkorlátját.

> [!IMPORTANT]
> **Hamarosan:** A jóváhagyott igénylések időkorlátja még nem támogatott a tervezési optimalizálásban. Amíg nem válnak támogatottá, a rendszer figyelmen kívül hagyja a **Jóváhagyott igénylések időkorlátja (napok)** mezőbe beírt összes értéket.

## <a name="independent-supply-regardless-of-coverage-code"></a>Önálló készlet a fedezeti kódtól függetlenül

A beszerzési igényléseket mindig önálló tervezett rendelések fedezik, függetlenül a fedezeti kódtól. Ez a viselkedés gondoskodik a beszerzési igénylések és a feltöltési rendelések közötti egyértelmű nyomon követhetőségről és munkafolyamatokról.

### <a name="example-1"></a>1. példa

Egy termék úgy van beállítva, hogy a **Fedezeti kód** értéke *Min/max*. A következő készlet- és igénylési állapotokkal rendelkezik:

- Aktuális készletmennyiség = 10.
- Minimális készletmennyiség = 15.
- Maximális készletmennyiség = 20.
- Akár egy darabhoz is megadható beszerzési igénylés. A kért dátuma a mai.

Az alaptervezés futtatásakor két tervezett rendelés jön létre: egy a készlet maximális mennyiségre való feltöltéséhez szükséges 10 darabhoz és egy darab a beszerzési igénylés feltöltéséhez.

### <a name="example-2"></a>2. példa

Egy termék úgy van beállítva, hogy a **Fedezeti kód** értéke *Min/max*. A következő készlet- és igénylési állapotokkal rendelkezik:

- Aktuális készletmennyiség = 17.
- Minimális készletmennyiség = 15.
- Maximális készletmennyiség = 20.
- Akár egy darabhoz is megadható beszerzési igénylés. A kért dátuma a mai.

Az alaptervezés futtatásakor egy darabra vonatkozó tervezett rendelés jön létre a beszerzési igénylés feltöltéséhez.

### <a name="example-3"></a>3. példa

Egy termék úgy van beállítva, hogy **Időszak** értékű *Fedezetti kóddal* rendelkezik, és az időszak hossza hét nap. A következő készlet-, értékesítési és igénylési állapotokkal rendelkezik:

- Aktuális készletmennyiség = 0.
- Akár öt darabhoz is megadható értékesítési rendelés. A várható szállítási dátuma a maihoz képest plusz egy nap.
- Akár három darabhoz is megadható beszerzési igénylés. A kért dátuma a maihoz képest plusz három nap.

Az alaptervezés futtatásakor két tervezett rendelés jön létre: egy a beszerzési igénylés feltöltéséhez szükséges három darabhoz és egy az értékesítési igénylés öt darabjának feltöltéséhez.

> [!NOTE]
> Miután a beszerzési igényléshez rögzített tervezett rendelést megerősítik, a tervezőmotor megtartja az igénykövetést a beszerzési igényléshez. Ha a megerősített rendelésben később hiányzó mennyiséget találnak a beszerzési igénylés teljesítéséhez, a rendszer új tervezett rendelést hoz létre a különbözethez.

A beszerzési igénylésekkel kapcsolatos tudnivalókért lásd: [Beszerzési igénylés áttekintése](../../procurement/purchase-requisitions-overview.md).
