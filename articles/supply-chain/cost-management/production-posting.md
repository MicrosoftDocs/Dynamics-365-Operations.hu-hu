---
title: Termelés feladása
description: Ez a cikk a termelési folyamat feladásainak különböző típusáról nyújt tájékoztatást.
author: JennySong-SH
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventItemGroup, ProjCategory, WrkCtrResourceGroup, WrkCtrTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 54591
ms.assetid: 0917fe64-f643-46ae-98ff-5013b266a067
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yanansong
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 41c5026f862f64fb0de86dbae23316593d058be9
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/03/2022
ms.locfileid: "8672234"
---
# <a name="production-posting"></a>Termelés feladása

[!include [banner](../includes/banner.md)]

Ez a cikk a termelési folyamat feladásainak különböző típusáról nyújt tájékoztatást.

A termelés feladási tevékenységei az alábbi részekben ismertetett termelési folyamatokat követik.

## <a name="material-consumption"></a>Anyagfelhasználás
A termelési kitárolásilista-napló feladásakor az anyagokat a termelés során felhasználtként regisztrálják. Ez a folyamat kiadási tranzakciókat hoz létre, amelyek az aktuális készletet csökkentik. A termelési paraméterek között megadhatja, hogy a folyamatban lévő nyersanyagok (folyamatban lévő munka \[WIP\]) értéke feladásra kerüljön-e a főkönyvbe. A folyamatban levő (WIP) nyersanyagok értéke ezután egy külön e célra fenntartott kitárolásilista-számlára és egy kitárolásilista-ellenszámlára kerül feladásra.

## <a name="time-consumption"></a>Időfelhasználás
Az az idő, amelyet az alkalmazottak a termelési feladatokra fordítanak, szintén rögzítésre kerül az útvonalkártya-naplóban vagy a feladatkártya-naplóban. Ezen naplók feladásakor a rendszer feldolgozza a folyamatban lévő erőforrások főkönyvi könyvelését egy erre a célra kijelölt számlára. Ez a feladás a termelési rendeléssel töltött idő értékét képviseli. A termelési rendelés befejezettként való regisztrációja után a folyamatban lévő munka számlái kiegyenlítésre kerülnek.

## <a name="reporting-finished-goods-and-error-quantities"></a>Késztermékek és hibás mennyiségek jelentése
Amikor a termelési rendelést készként jelentik, a befejezett késztermék mennyisége frissül a készletben egy készrejelentési napló által. Amennyiben folyamatban lévő munkán (WIP) alapuló könyvelést használ, amelyet a termelési paraméterek között állíthat be, egy főkönyvi napló jön létre a folyamatban lévő munka számlák egyenlegének csökkentésére és a késztermékek készletének növelésére. A napló a termékhez meghatározott elszámolóárat használja.

## <a name="ending-the-production-order"></a>A termelési rendelések befejezése
A megtermelt mennyiség tényleges költségeinek kiszámítása még a termelési rendelés befejezése előtt megtörténik. Minden becsült anyag-, munka- és többletköltséget sztorníroz a program, és a tényleges költségeket vezeti be a helyükre. A befejezett cikk teljes költsége tartozik tételként jelenik meg a Bevételezési számlán és követelésként a készlet Kiadási számláján. Ha a **Záró feladat** jelölőnégyzetet bejelöli a költségszámítás futtatásakor, a termelési rendelés a **Befejezett** állapotra vált. Ez az állapot meggátolja, hogy bármilyen további költséget véletlenül feladjanak egy már elkészült termelési rendeléshez. Megadhatja, hogy a jelentések részeként készként jelentett hibamennyiségek értékét a készként jelentett jók mennyiségéhez kell felosztani. Alternatív megoldásként beállíthatja, hogy a hibás mennyiségek értékét egy e célra felállított selejtszámlára kelljen feladni.

## <a name="controlling-the-level-of-ledger-posting"></a>A főkönyvi feladás szintjének vezérlése
A **Gyártásvezérlési paraméterek** részen a **Főkönyvi feladás** mezőben állíthatja be a főkönyvi feladási szintet a termelési folyamatokra vonatkozóan. A következő értékek állnak rendelkezésre:

-   **Cikk és erőforrás** – a nyersanyagok és késztermékek cikkcsoportjára beállított főkönyvi számlák használata. A folyamatban lévő munka időfelhasználását a rendszer az útvonalműveletek erőforrásából vagy erőforráscsoportjából veszi.
-   **Cikk és kategória** – a nyersanyagok és késztermékek cikkcsoportjára beállított főkönyvi számlák használata. A folyamatban lévő munka időfelhasználását a rendszer az útvonalműveletekhez társított költségkategóriákból veszi.
-   **Termelési csoportok** – a termelési csoportokban a nyersanyagokra és időfelhasználásra beállított főkönyvi számlákat használja. A kiadott termékhez csatolja a termelési csoportokat, majd a rendelések létrehozásakor átmásolja ezeket a termelési rendelésre. A termelési rendelések feladása ezután a termelési rendeléshez társított termelési csoportokat követi.

**Megjegyzés:** Ha az elkészült cikk költségének kiszámításához a normál módszert használta, az a végső tranzakciókon is látható lesz. Ha különbség van a tényleges költségek és a normál módszerrel számított költségek között, azt a program feladja az eredményt mutató számlára.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]