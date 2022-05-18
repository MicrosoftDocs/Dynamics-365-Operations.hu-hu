---
title: Küszöbérték és kivételi küszöbérték
description: Ez a témakör a Forrásnál levont adó (TDS) küszöbértékét és kivételi küszöbértékeit írja le.
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 7fa7d871fdf25f29b003a68cacd9fc0d487dce5b
ms.sourcegitcommit: 631d2cea52590af15f208e9af584446e85540fcf
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/07/2022
ms.locfileid: "8726016"
---
# <a name="threshold-limit-and-exception-threshold-limit"></a>Küszöbérték és kivételi küszöbérték

[!include [banner](../includes/banner.md)]

Ez a témakör a Forrásnál levont adó (TDS) küszöbértékét és kivételi küszöbértékeit írja le. A számlákra és kifizetésekre vonatkozó TDS-t mindig az **Adóelőleg-összetevők** oldalon a TDS-adóösszetevőkre meghatározott küszöbérték és kivételi küszöbérték figyelembevételével számítják ki. A TDS-adóösszetevők a TDS-adókódjaihoz vannak csatolva, amelyek a TDS-adócsoportok részét képezik. A TDS-adócsoportok a szállítókhoz és az ügyfelekhez vannak csatolva, hogy a TDS-t számla- vagy fizetés szintjén számítsák ki.

A TDS kiszámítása akkor történik, ha egy adott TDS-csoporttal egy szállítónál feladott tranzakció vagy kumulatív tranzakció összege meghaladja az **Adóelőleg-összetevők** lapon megadott értékhatárt. A TDS-t addig nem számítják ki, amíg a kumulált tranzakcióösszeg nem haladja meg a megadott küszöbértéket.

Ha egy TDS-összetevőre vonatkozó küszöbértékkel együtt kivételi küszöbértéket határoznak meg, a TDS-t akkor számítják ki, ha egy adott tranzakció összege meghaladja a kivételi küszöbértéket, még akkor is, ha a kumulált tranzakció összege nem haladja meg a meghatározott küszöbértéket.

### <a name="example"></a>Példa
A TDS nevű adóösszetevő a Vállalkozó nevű TDS adócsoporthoz van beállítva és csatolva. A küszöbértéket 50 000-ben, a kivételi küszöbértéket pedig 20 000-ben határozták meg a TDS-adóösszetevő esetében. A TDS-csoport alvállalkozója az 1. szállító alapértelmezett TDS-csoportjaként van definiálva.

A 001-es beszerzési számla az 1-es szállítónak 10 000 értékben kerül feladásra. A TDS-t azért nem számítják ki a számlára, mert a számla összege nem lépte át az küszöbértéket vagy a kivételi küszöbértéket. A 002-es beszerzési számla az 1-es szállítónak 25 000 értékben kerül feladásra. A TDS-t ki lesz számítva a számlára, mert a számla összege átlépte kivételi küszöbértéket. A 003-as beszerzési számla az 1-es szállítónak 20 000 értékben kerül feladásra. A TDS-t azért számítják ki a számlára, mert a szállító számára kiállított három számla teljes számlaösszege átlépte a küszöbértéket. A TDS kiszámítása minden olyan számlára történik, amelyet annak a szállítónak állítanak ki, amelyre a TDS-t korábban nem számították ki. Ezért a TDS-t 30 000-hez számítják, ami a 001-es és 003-as számla teljes számlaösszege.

A küszöbérték és a kivételi küszöbérték nincs figyelembe véve a TDS-számításhoz, ha a **Küszöbérték figyelmen kívül hagyása** jelölőnégyzet be van jelölve a TDS adókódokhoz a TDS-csoportban, amely mellékelve van a tranzakcióhoz. A küszöbértéket nem használják a TDS-csoport TDS-adókódjaiban, amelyekhez a **Küszöbérték figyelmen kívül hagyása** jelölőnégyzet be van jelölve.

Ha a **Küszöbérték figyelmen kívül hagyása** jelölőnégyzetet egy adott TDS-csoporthoz kiválasztják egyes számlákhoz, de nem az adott szállító/vevő számára létrehozott egyéb számlákhoz van kiválasztva, a TDS kiszámítása anélkül, hogy figyelmen kívül hagyná a néhány számla küszöbértékét, figyelembe véve az összes olyan számlán szereplő összegösszeget, amelyre a TDS-t korábban nem számították ki.

A küszöbérték például 25000. A következő számlák lettek kiállítva az A szállítónak.

- Számla 1 – 20 000 – ( A **küszöbérték figyelmen kívül hagyása** jelölőnégyzete nincs kiválasztva): A TDS nincs számítva.

- Számla 2 – 4000 – (A **küszöbérték figyelmen kívül hagyása** jelölőnégyzet nincs kiválasztva): A TDS 4000-hez van számítva.

- 2. számla – 3000 – (A **Küszöbérték figyelmen kívül hagyása** jelölőnégyzet nincs kiválasztva): A TDS a számla összesített összegéhez, azaz 27 000 (20 000+4000+3000) ki van számítva, mert túllépte az értékhatárt. A TDS-t azon számlák kumulált összegére számítják, amelyekhez a TDS-t korábban nem számították ki, azaz 23 000 (20 000+3000).
