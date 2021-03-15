---
title: Azonnali feltöltés
description: Ez a témakör leírja, hogyan lehet az azonnali feltöltés segítségével feltölteni a készletet, ha egy helyutasításnak nem sikerül készletet felosztania.
author: Mirzaab
manager: tfehr
ms.date: 03/15/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLocDirTable, WHSReplenishmentTemplates
audience: Application User
ms.reviewer: kamaybac
ms.custom: 1705903
ms.assetid: 427e01b3-4968-4cff-9b85-1717530f72e4
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: 6e2919c003d1dc67b988345260b2747364752222
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "5004777"
---
# <a name="immediate-replenishment"></a>Azonnali feltöltés

[!include [banner](../includes/banner.md)]

Az azonnali feltöltés segítségével azonnal fel lehet tölteni a készletet, ha egy helyutasítási sornak nem sikerül készletet felosztania. A feltöltés a helyutasítás beállításai közötti egyetlen soron alapul. Ha a készlet nem aktuális készlet, a sor által meghatározott mértékegységben, az adott mértékegység feltöltése azonnal megtörténik.

Az azonnali feltöltés mód alternatívát jelent ahhoz a módszerhez képest, ahol a készlet felosztásának alapját a helyutasítás több sora adja, és ahol az igény össze van foglalva a felosztás végén, és a feltöltés azon mértékegység szerint történik, amely a helyutasítás utolsó sorában van meghatározva.

Az azonnali feltöltés előnyei, hogy a feltöltés a megadott egységekre korlátozható, és a mennyiség meghatározott helyekre irányítható.

## <a name="business-scenario"></a>Üzleti eset

Például tegyük fel, hogy van egy raktár, amely külön kitárolási területekkel rendelkezik a „doboz” és az „mindegyik” mértékegységekhez. A kitárolási folyamatot optimalizálni szeretnénk a lehető legnagyobb számú doboz kitárolásával, majd a doboznál kevesebb maradék mennyiség a „mindegyik” területen bonyolított kitárolásával.

Ebben az esetben az azonnali feltöltést is használhatja. A helyutasításban beállíthat azonnali feltöltést a dobozokhoz, így az igényfeltöltés használatára azonnal sor kerül, amint hiány van az igényelt mennyiség kitárolásához használható dobozokból. Ezzel a módszerrel optimalizálhatja a kitárolási folyamat úgy, hogy kitárolás a lehető legmagasabb számú dobozt foglalja magában. Az azonnali feltöltési biztosítja a dobozok feltöltését, az igényt nem kell továbbadni úgy, hogy a mennyiségek kitárolására a „mindegyik” mértékegységben kerüljön sor. Ez azt jelenti, hogy csak az eleve a „mindegyik” mértékegységben kitárolandó mennyiség (azaz a doboznál kisebb mennyiség) kitárolása fog a „mindegyik” területen zajlani. Ha a „doboz” területen hiány jelentkezik, a lehető legtöbb doboz kitárolható a teljes igényből. A fennmaradó mennyiség kitárolása a „mindegyik” területről történik.

## <a name="where-it-applies"></a>Alkalmazási kör

Az azonnali feltöltés használatos hullám-végrehajtásnál, ha a felosztás sikertelen egy olyan helyutasítás sorművelete esetén, amelyhez feltöltési sablon van beállítva.

## <a name="set-up-immediate-replenishment"></a>Azonnali feltöltés beállítása

- Lépjen a **Raktárkezelés** \> **Beállítás** \> **Helyutasítások** elemre, majd a **Sorok** lapon az **Azonnali feltöltési sablon** listában válasszon feltöltési sablont a hullámigényhez.

A feltöltési sablon alkalmazásra kerül, ha a helyutasítás sorának nem sikerül erre a célra kijelöltt mértékegységet lefoglalni.

## <a name="troubleshooting"></a>Hibaelhárítás

Ha egy helyutasítási sornál azonnali feltöltés van kijelölve, de nem jön létre feltöltési munka, amikor az adott helyutasítási sorhoz igényfeltöltési sablont használ, két fő okot kell megvizsgálni:

- Győződjön meg arról, hogy az alkalmazott igényfeltöltési sablon be van állítva a megfelelő, **Feltöltési** típusú helysablonok és erőforrás-sablonokat használatára.
- Győződjön meg arról, hogy van elegendő aktuális készlet azon helyeken, ahol az igényfeltöltési sablonnak aktuális készletet keres a feltöltéshez.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]