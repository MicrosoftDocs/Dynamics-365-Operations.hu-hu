---
title: "Erőforrás-képességek"
description: "Ez a cikk az erőforrás képességeivel kapcsolatos információkról nyújt tájékoztatást. A képesség egy üzemi erőforrás képességét jelenti egy adott tevékenység végrehajtására. A cikk bemutatja, hogy hogyan használják a képességeket és a kapcsolódó fogalmakat (például a szakértelemszint és a prioritás) a megfelelő erőforrások kiválasztására egy tevékenységre vonatkozóan."
author: sorenva
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WrkCtrCapability, WrkCtrTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 29961
ms.assetid: 30e38233-2a64-4070-911f-8ffd78dd8281
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 29c42feec36f7fe1fc00918a8c24e42de8a6dda2
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="resource-capabilities"></a>Erőforrás-képességek

[!include[banner](../includes/banner.md)]


Ez a cikk az erőforrás képességeivel kapcsolatos információkról nyújt tájékoztatást. A képesség egy üzemi erőforrás képességét jelenti egy adott tevékenység végrehajtására. A cikk bemutatja, hogy hogyan használják a képességeket és a kapcsolódó fogalmakat (például a szakértelemszint és a prioritás) a megfelelő erőforrások kiválasztására egy tevékenységre vonatkozóan.

A képesség egy üzemi erőforrás képességét jelenti egy adott tevékenység végrehajtására. Egy műveleti erőforráshoz több képesség is rendelhető, és a képességek több erőforráshoz is hozzárendelhetők. Átmenetileg hozzárendelhet képességeket erőforrásokhoz, ehhez adjon meg kezdő és lejárati dátumot a képesség hozzárendelésekor. Amikor egy erőforráshoz lejár a képesség, akkor az erőforrást nem lehet ütemezni projekthez vagy termeléshez amihez szükséges az adott képesség. A lejárt képesség megújítható. Törölhet képességeket, feltéve ha azok nincsenek egy útvonal objektumkapcsolatán vagy egy aktív termelési rendelés termelési útvonalán. Legyen óvatos képességek törlésekor. Ehelyett fontolja meg a képességgel rendelkező erőforrások lejárati dátumának módosítását. Bármilyen típusú üzemi erőforráshoz rendelhetők hozzá képességek: eszköz, szállító, gép, emberi erőforrás, hely, illetve létesítmény.

## <a name="level"></a>Szint
Több erőforrás gyakran ugyanazzal a funkcionális képességgel rendelkezik de eltérő a szakértelmük szintje (pl. erősség, feldolgozási sebesség vagy pontosság). Ezért amikor egy forráshoz hozzárendel egy képességet megadhat a **Szint** számára egy értéket. A szint egy egyszerű számérték. Ha megadja, hogy egy képesség forrás szükséglet egy termelési útvonalhoz, akkor megadhatja a **Minimálisan szükséges szint** értékét a képességhez. Az ütemezési motor ezután csak olyan erőforrásokat választ ki amelyek rendelkeznek a szükséges képességgel, olyan szinten, ami megegyezik, vagy meghaladja a forrás szükségletben meghatározott szintet.

## <a name="priority"></a>Prioritás
Az azonos képességekkel rendelkező üzemi erőforrások prioritással hozzárendelhetőek. Ezután, ha több erőforrás van, ami eleget tesz az ütemezés követelményeinek a megkövetelt szinten, és szabad kapacitással rendelkeznek akkor az ütemezési motor tud választani ezen erőforrások közül. Ha a **Prioritás** van kiválasztva az **Ütemezési paraméterek** oldal **Elsődleges erőforrás kiválasztás**, mezőben, akkor az legmagasabb prioritású erőforrás (a **Prioritás** mezőben a legalacsonyabb számértékű) kerül kiválasztásra az ütemezéshez.

## <a name="resource-requirements"></a>Erőforrásigények
Amikor egy termelési útvonalhoz forrás szükségleteket ad meg, akkor megadhat követelményként egy vagy több képességet. A termelésütemezés során a képességek, amelyek a forrás szükségletekben definiáltak a műveleti úton egyeztetve vannak az erőforrásokhoz definiált képességekkel. A képesség követelményeinek megfelelő források kiválasztásra kerülnek. Ha több erőforrás azonos funkcionális képességgel rendelkezik, de eltérő a szakértelmi szintjük (pl. erősség, feldolgozási sebesség vagy pontosság), akkor megadhat több képességet vagy használhatja a képességi szintet az erőforrás minősítésére. Egy példa:

-   Egy útvonalon a fúrási folyamat ideje 10 egység óránként, de maga a követelmény Fúrásként van definiálva.
-   Az M1 és M2 fúrógépek állnak rendelkezésre.
-   A Fúrási kapacitás az M1 és M2 géphez van hozzárendelve.
-   Az M1 gép óránként 2 egységet fúr, az M2 gép óránként 11 egységet.

Ebben a példában mindkét gépet ki lehet választani az ütemezési motorral, mert teljesítik az alapvető képességi követelményt (Fúrás). Azonban az M1 gép óránként csak két egységet tud fúrni. Amiatt, mert ez az érték sokkal kisebb, mint 10 egység óránként, ami meg van adva az útvonalon az M1 gép kiválasztása esetén termelési problémák adódnak. Erre a problémára kétféle megoldás van, amivel bizonyosan az M2 gépet választja ki helyette:

-   Hozzon létre két külön képességet: Alacsony és Magas sebességű fúrás. Határozza meg az Alacsony sebességű fúrást, egy olyan folyamatként aminek a folyamatideje egytől kilenc egység óránként. Határozza meg a Magas sebességű fúrást, egy olyan folyamatként aminek a folyamatideje 10-19 egység óránként. Majd rendelje hozzá az M1 gépet az Alacsony fúrási sebesség képességhez, és rendelje hozzá az M2 gépet a Magas fúrási sebesség képességhez. Végül módosítsa az erőforrás képesség követelményét a Magas sebességű fúrásnál. Az ütemezési motor ezután kiválasztja a megfelelő gépet (M2).
-   Használja a képességi szintet a Fúrási képesség minősítésére, ami a fúrógépekhez van rendelve. Adja meg, hogy az M1 gép rendelkezik-e a Fúrási képességgel 2.0 szinten, és hogy az M2 gép rendelkezik-e a Fúrási képességgel 11.0 szinten. Ezután adja meg, hogy 10.0 az ezen az úton szükséges Fúrási képesség. Az ütemezési motor ezután meghatározza, hogy csak az M2 gép tesz eleget a forrás szükségletnek.

## <a name="competencies-for-human-resources"></a>Emberi erőforrások kompetenciái
Ha **Emberi erőforrások** típusú üzemi erőforrással rendelkezik, amelyik az Emberi erőforrásoknál dolgozókhoz van rendelve, akkor kihasználhatja a dolgozók kompetenciáit amikor megadja az útvonal forrás szükségleteit. Más szóval is megadhat követelményeket bizonyos képességekhez, tanfolyamokhoz, tanúsítványokhoz vagy beosztásokhoz. Az ütemezési motor kiválaszthat forrásokat, amelyek dolgozókhoz vannak rendelve, a kiválasztás a dolgozók kompetenciái alapján történik. A kompetenciák az Emberi erőforrásoknál, nem pedig az **Erőforrások képességei** oldalon találhatók. Amikor képességeket, tanfolyamokat, képesítéseket vagy beosztásokat ad meg forrás szükségletekként, akkor a Humán erőforrások funkciót kell használni a rendszerben, és minden egyes erőforrást hozzá kell rendelnie a **Humán erőforrások** típusához a megfelelő dolgozónak. Ha a rendszerben az Emberi erőforrások funkciót használja, akkor megadhat képességeket az **Erőforrás-képességek** oldalon ami megjeleníti vagy duplikálja a Humán erőforrások kompetenciáit. Ugyanakkor az **Erőforrás-képességek** oldal nem tartalmaz funkciót amelyik szükséges a képességek, tanfolyamok, bizonyítványok vagy beosztások karbantartásához.




