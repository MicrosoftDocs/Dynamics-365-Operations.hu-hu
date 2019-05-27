---
title: Anyaghelyettesítés a gyártásban
description: Ez a témakör leírja, hogyan helyettesítsen anyagokat a termelési folyamat során.
author: johanhoffmann
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdBOM
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 70171
ms.assetid: ce3b11ef-550e-49b7-8942-2607c2ec3c5c
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 461b717acafb5ccf37acae23a1564069cea6828a
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1543445"
---
# <a name="material-substitution-in-manufacturing"></a>Anyaghelyettesítés a gyártásban

[!include [banner](../includes/banner.md)]

Ez a témakör leírja, hogyan helyettesítsen anyagokat a termelési folyamat során. 

Három mód van az anyagok helyettesítésére a termelési folyamat során:

-   Dátum szerint, amikor egy anyag helyettesítésre kerül egy másik által egy adott dátum után
-   Az alaptervezés során, amikor egy anyag egy receptúrában helyettesítésre kerül egy másik anyaggal, mert nincs készleten
-   A termelés során, mert egy anyag váratlanul elfogyott a készletről és egy másik anyaggal kerül helyettesítésre

## <a name="substituting-material-by-date"></a>Anyag helyettesítése dátum szerint
Fontolja meg a következő esetet: Egy gép, amelyet a vállalat gyárt tartalmat egy alkatrészt, amely két hónapon le fog járni a szállító katalógusában. A lejárati dátumtól kezdődően a szállító ajánlani fog egy új alkatrészt, amely képes a régi alkatrész helyettesítésére. Az érvényességi időkkel kezdődően és azokkal bezáróan beállíthatóak az anyagjegyzék (AJ) sorok. Ebben a példában beállítja, hogy a régi alkatrészt lejárjon a lejárati idő megadásával a **Záró dátum** mezőben. Ezután az anyagjegyzékben beállítja az új, helyettesítő alkatrészt, hogy érvényes legyen a régi alkatrész lejárata utáni naptól. Hogy ezt megtegye adja meg a kezdődátumot a **Nyitó dátum** mezőben.

## <a name="substituting-material-by-planning"></a>Anyag helyettesítése tervezés szerint
Tervezés során csak akkor helyettesíthet anyagokat, amikor receptúrákat használ, anyagjegyzék esetén nem. Fontolja meg a következő esetet: Egy élelmiszergyártó vállalat egy mártást készít egy olyan receptúrából, amely 20 alapanyaggal rendelkezik. Egy alapanyag a receptúrában helyettesíthető egy vagy két más alapanyaggal. Azonban amiért ez a két alapanyag drágább az előnyben részesített alapanyagnál, ezért csak akkor alkalmazunk helyettesítést, ha az előnyben részesített alapanyag nincs készleten. A helyettesíthető anyag neve A, amíg a két helyettesítő anyag neve B és C. A tervezés szerinti anyaghelyettesítés irányítása a receptúrasorokban található **Tervcsoport** és **Prioritás** mezőkkel történik. Ebben a példában Ön három anyaghoz hoz létre anyagjegyzék-sorokat és társítja a receptúrasorokat ugyanazon tervcsoporttal. Ebben a beállításban az A anyag receptúrasora rendelkezik a legmagasabb prioritással (legalacsonyabb szám), a C anyag receptúra sora rendelkezik a legalacsonyabb prioritással, a B anyag prioritása pedig a két másik sor prioritása közötti értéket vesz fel. Ha igénnyel rendelkezik a befejezett cikkhez, akkor az alaptervezés először meghatározza, hogy fedezhető az A anyag iránti igény. Ha az igény nem fedezhető, akkor az alaptervezés megvizsgálja a B és C anyagokat, a prioritás sorrendjében. Ha a B anyag készleten van, akkor felhasználásra kerül, miután egy kötegrendelést megerősítettek a receptúrához. Ha egyik anyag sincs készleten, akkor az alaptervezés létrehoz egy tervezett rendelést az A anyaghoz **Megjegyzés:** Amikor beállítja a receptúrasorokat egy tervcsoportban, akkor csak a legmagasabb prioritású anyagon ajánlott mennyiséget megadni. Ez a mennyiség lesz felhasználva, hogy kiszámítsa a tervben szereplő összes anyag igényét, még azokét az anyagokét is, amelyek alacsonyabb prioritással rendelkeznek. Nem tud megadni más mennyiségeket az alacsonyabb prioritású cikkeken a tervcsoportban.

## <a name="substituting-material-during-production"></a>Anyag helyettesítése a termelés során
Fontolja meg a következő példát: Egy fémlemez-darabra van szükség egy hegesztési művelethez. A művelet során egy raktári dolgozó tájékoztatja a gépkezelőt, hogy a lemez nincs készleten. Azonban döntés született róla, hogy a lemez helyettesíthető egy lemezzel, ami kissé vastagabb. Ilyen módon a művelet lezárható. Anyag hozzáadható egy anyagjegyzékhez egy nyílt termelési rendelés esetén. Ha a termelési rendelés állapota **Elindítva**, akkor a felhasználók felszólítást kapnak, hogy becsüljék újra a rendelést, amikor hozzáadnak egy új cikket a termelési anyagjegyzékhez. Miután az anyagot hozzáadták létrehozható egy új kitárolási lista az új cikkhez. Nem kell hozzáadni az új anyagot a termelési anyagjegyzékhez. Ehelyett hozzáadhatja közvetlenül a termelés kitárolási listájához. Majd amikor a kitárolási listát feladják a rendszer hozzáadja az anyagot a termelési anyagjegyzékhez.



