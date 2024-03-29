---
title: Mozgó átlag
description: A mozgó átlag örökös költségszámítási módszer, amely az átlag elven alapul, ahol a készletkiadások költségei nem módosulnak, ha a beszerzési költség változik. A különbség tőkésített, és arányos számításon alapul. A fennmaradó összeg kiadásként van könyvelve.
author: JennySong-SH
ms.date: 08/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventModelGroup
audience: Application User
ms.reviewer: kamaybac
ms.custom: 65531
ms.assetid: dfd10099-8f7f-44b1-917e-df37c2fe8773
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yanansong
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0be72c8ba3c123300be83513531d2f805dc8f5e3
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/03/2022
ms.locfileid: "8676103"
---
# <a name="moving-average"></a>Mozgó átlag

[!include [banner](../includes/banner.md)]

A mozgó átlag örökös költségszámítási módszer, amely az átlag elven alapul, ahol a készletkiadások költségei nem módosulnak, ha a beszerzési költség változik. A különbség tőkésített, és arányos számításon alapul. A fennmaradó összeg kiadásként van könyvelve.

Mozgó átlag használatakor a készletkiegyenlítések és a készletjelölés nem támogatott. A készletzárás nem befolyásolja a készletmodell-csoportként mozgó átlaggal rendelkező termékeket, és nem hoz létre kiegyenlítéseket a tranzakciók között.

A következő előfeltételeknek kell megfelelni, ha a mozgó átlagköltség módszert alkalmazza költségszámításkor.

1. A **Cikkmodell-csoportok** lapon állítson be egy olyan cikkmodell csoportot, amely esetében a **Mozgó átlag** opció van beállítva a **Készletmodell** mezőben.

    > [!NOTE]
    > Alapértelmezés szerint, amikor a **Mozgó átlag** opció van kiválasztva, a **Tényleges készlet feladása** és a **Pénzügyi készlet feladása** mezők is be lesznek jelölve.

1. A **Feladás** lapon rendeljen hozzá számlákat az **Árkülönbség a mozgó átlag** elemhez. Használja az **Árkülönbség a mozgó átlaghoz** számlát, ha a költséget arányosan kell elszámolni. Ez a következő két esetben fordul elő:
    - A beszerzési elismervényen és a beszerzési számlán található költségek között különbség van, valamint az aktuális készletben szereplő mennyiség és az eredeti készletmennyiség eltérése miatt.
    - A tranzakciók negatívról nulla értékre hozzák a készletet, és a tranzakció költsége és az aktuális mozgóátlag költsége között eltérés van.

1. A **Feladás** lapon rendeljen számlákat az **Árkülönbség a mozgó átlaghoz** elemhez a **Készlet** lapon. Az **Árértékelés a mozgó átlaghoz** számlát akkor használja, ha egy termék mozgóátlag-költségét egy új egységárhoz szeretné igazítani.

1. A **Kiadott termékek** oldalon rendelje hozzá a mozgó átlag cikkmodell csoportját a termékhez.

    > [!NOTE]
    > A készlet zárása folyamat csak a könyvelési időszakot zárja le. Nem befolyásolja azon termékeket, amelyekhez mozgó átlag van hozzárendelve cikkmodell csoportként.

## <a name="convert-to-the-moving-average-costing-method"></a>Mozgó átlag költségképzési módra konvertálás

A termékeket át lehet konvertálni, hogy a mozgó átlag készletértékelési módszer legyen használva. Az ilyen típusú átváltás általában az aktuális év utolsó hónapjában történik, miután az aktuális év utolsó hónapja lezárásra került. Ez a termék aktuális költségszámítási modelljének használatával hajtható végre. Az átlag- vagy standardköltségen alapuló költségszámítási módszert lecserélheti egy mozgó átlagon alapuló módszerre.

Amennyiben az átlag- vagy standardköltségen alapuló költségszámítási módszert lecseréli egy mozgó átlagon alapuló módszerre, a következő feladatokat kell végrehajtania:

1. Hajtsa végre a szükséges módosításokat, hogy a készletmennyiségek és -értékek 0-ra (nullára) csökkenjenek.
1. Ha a készletérték és -mennyiség 0 (nulla), akkor módosítsa a cikkmodell csoportot mozgó átlagra.
1. Végezze el a szükséges módosításokat, hogy a mennyiségek és értékek a készletnek megfelelők legyenek.

A Készletértékelés módja mozgó átlagról nem változtatható a következő lehetőségekre: First in, First out (FIFO), Last in, First out (LIFO), súlyozott átlag módok.

> [!NOTE]
> Amennyiben standard költségszámításról súlyozott módra kíván váltani, azt manuálisan kell elvégezni.

A következő példák azt mutatják be, hogy milyen hatást fejt ki a mozgó átlagköltség módszer alkalmazása. Négy konfiguráció van:

- Beszerzési rendelés és az arányosan elkönyvelt költségek közötti eltérés
- Mozgó átlagtermék és készlethelyesbítés
- Mozgó átlag termeléssel
- Mozgó átlag visszadátumozott tranzakcióval

## <a name="purchase-order-and-proportionally-expensed-cost-difference"></a>Beszerzési rendelés és az arányosan elkönyvelt költségek közötti eltérés

Mozgó átlagot alkalmazva a termék költségét a beszerzési elismervény határozza meg. A beszerzési számlák feladásakor, ha a beszerzési elismervényen és a beszerzési számlán található költségek között eltérés mutatkozik, a különbség arányosan módosul a készleten lévő aktuális termékek szerint, valamint minden hátralévő költség is elszámolásra kerül.

Ebben a példában egy beszerzési rendelés egy adott költségen kerül létrehozásra és fogadására, de a beszerzési számla egy különböző költséggel kerül feladásra.

1. Hozzon létre egy beszerzési rendelést 2 mennyiséggel és 10,00 egységárral.
1. Hozzon létre egy beszerzési elismervényt a termékhez.
1. Hozzon létre egy értékesítési rendelést 1 mennyiséggel és 10,00 egységárral.
1. Hozzon létre egy számlát 2 mennyiséggel és 12,00 egységárral.

Az egységárban való eltérés (2,00) is feladásra kerül az Árkülönbség a mozgó átlag számlához a beszerzési számla feladásakor. Ennek az oka, hogy két termék került beszerzésre 20,00 áron. Az egyik termék 10,00 egységáron került értékesítésre. A beszerzési számla 12,00 egységárral és 2 mennyiséggel került könyvelésre. A termék egységára nem könyvelhető el 14,00 értékkel.

## <a name="moving-average-product-and-inventory-adjustment"></a>Mozgó átlagtermék és készlethelyesbítés

Ha egy termék mozgó átlagköltségét módosítani kell, a készlethelyesbítések a mai napra vonatkozóan engedélyezettek. Egy készlethelyesbítést nem lehet visszadátumozni egy termék mozgó átlagköltségének helyesbítéséhez. Nem lehet a költségforgalmat további tranzakciókon keresztül vezetni.

Ebben a példában módosul a mozgó átlagköltség egy termékre vonatkozóan.

1. Válassza ki azt a terméket, amelyre vonatkozóan módosítani kívánja a mozgó átlagköltséget. 

 > [!NOTE]
 > Az **Árátértékelés a mozgó átlaghoz** lap megvizsgálja a termékhez rendelkezésre álló készletet. A kiválasztott termék feladott mennyisége 1, a feladott értéke 12,00, a feladott egységköltsége 12,00, egységköltsége 12,00.
    
1. Frissítse az **Egységköltség** mezőt a következőre: 16,00. A rendszer kiszámítja a fennmaradó mezőket.
1. A kiigazítás feladásra kerül.

> [!NOTE]
> Csak a mai dátumig vonatkozóan lehet módosítani a mozgó átlagköltséget.

A **Lezárt bizonylatok** lapon megtekintheti az Önköltségi átértékelés a mozgó átlaghoz nevű számlára feladott 4,00 egységnyi korrekciót.

## <a name="moving-average-with-production"></a>Mozgó átlag termeléssel

A mozgó átlag támogatja a termelt cikkeket. Ha szeretné használni a mozgó átlagot termelési környezetben, válassza a **Becsült önköltségi ár használata** csúszkát a **Gyártásvezérlési paraméterek** lapon. Ez azt jelenti, hogy az aktuális anyagjegyzék-számítási ár helyett a becslés során számított önköltségi ár lesz használva.

## <a name="moving-average-with-a-backdated-transaction"></a>Mozgó átlag visszadátumozott tranzakcióval

A visszadátumozott tranzakciók hozzá lesznek rendelve az aktuális mozgó átlagköltséghez, és a termék tényleges mennyisége frissül, de ez nem befolyásolja a termék mozgó átlagárát. Az alábbi mozgó átlagos példában a mozgó átlagú termékhez egy visszadátumozott tranzakciót adunk fel.

1. Hozzon létre egy készlethelyesbítést a mozgó átlagú termékhez 1 mennyiséggel és 20,00 költséggel.
1. A termék készletezési tranzakcióelőzményének a következőhöz kell hasonlítania:
    - Egy 1 egységnyi, 16,00 költségű tranzakció január 15. feladási dátummal és január 15. tranzakciós dátummal.
    - Egy 1 egységnyi, 20,00 költségű készlethelyesbítés január 1. feladási dátummal és január 15. tranzakciós dátummal.
1. Adja fel a helyesbítést.

A **Készlettranzakciók** lapon láthatja, hogy 4,00 egység 16,00 egységnyi kiadásként lett könyvelve a termék aktuális mozgóátlagaként. A múltra vonatkozóan is könyvelhet, de költségeltérés is könyvelve lesz kiadásként, így az nincs hatással a mozgó átlagköltségre.

## <a name="negative-inventory-balances"></a>Negatív készletegyenlegek

A tranzakciók eltérően kezelhetők attól függően, hogy az új aktuális készlet a tranzakció után negatív, nulla vagy pozitív.

### <a name="new-balance-is-negative-or-zero"></a>Az új egyenleg negatív vagy nulla

Ha az új készleten lévő mennyiség negatív vagy nulla, akkor a tranzakciót az aktuális átlagköltségek alapján kell elszámolni. Ha eltérés van a beszerzési ár és az aktuális átlagköltség között, akkor a mozgóátlag esetében a program feladja az **Árkülönbség a mozgó átlaghoz** elemhez.

### <a name="new-balance-is-positive"></a>Az új egyenleg pozitív

Ha az új aktuális készlet pozitív a tranzakció után, akkor a tranzakciót két részre osztja fel a program, és eltérő módon költségeli a következő táblázatban összegzett módon.

| Alkatrész | Leírás |
|---|---|
| Negatív és nulla közötti mennyiség | A készlet a cikk aktuális mozgóátlagos költségét használja, nem pedig a bevételezési mennyiség azon részének tranzakciós költségét, amely negatívról nullára növeli az aktuális egyenleget. Az eltérést a tranzakciós költség és az aktuális mozgóátlagos költség között fel lesz adva az **Árkülönbség a mozgó átlaghoz** elemhez. |
| Nulla és pozitív közötti mennyiség | A készlet a bevételezési mennyiség azon részére vonatkozó tranzakciós költséget használja, amely az aktuális egyenleget nulláról pozitív értékre növeli.                                                  |

## <a name="inventory-value-report"></a>Készletérték-jelentés

Jelen mozgó átlagos példában kinyomtatásra kerül a készletérték-jelentés, így segítve az aktuális mozgó átlag számításokat a termékre vonatkozóan. A készletérték-jelentést ki lehet nyomtatni a tranzakciók időrendi sorrendjében a költségekkel együtt, így segítve az aktuális mozgó átlag számításokat a termékre vonatkozóan. Ezen jelentésben szerepel a termékre vonatkozó mozgó átlagköltség. A **Készletérték-jelentések** párbeszédpanelen dátumintervallum lehetővé teszi, hogy kiválassza a **Tranzakció időpontja** vagy a **Feladási dátum** opciókat a jelentések rendezéséhez. A **Feladási dátum** beállítás a jelentés hagyományos nyomtatási módja. A **Tranzakció időpontja** lehetőség a tranzakció tényleges jelentési dátuma és a termék mozgó átlagköltségének tényleges frissítési ideje. Kinyomtathatja a Készletérték-jelentést a **Tranzakció ideje szerinti rendezés** lehetőség segítségével, ha a mozgó átlagköltséggel kapcsolatos számításokat az idő függvényében szeretné megtekinteni. A következő táblázatban láthatja azon termékre vonatkozó tranzakciókat, amelyhez a jelentés a **Tranzakció ideje szerinti rendezés** beállítás használatával lett kinyomtatva.

| Tranzakció időpontja | Dátum         | Tranzakció típusa           | Mennyiség | Összeg | Átlagos egységenkénti költség |
|------------------|--------------|----------------------------|----------|--------|-------------------|
|                  | Október 1.    | Nyitó egyenleg          | 0        | 0,00   | 0,00              |
| Október 8.        | Szeptember 28. | Visszadátumozott számla          | 1        | 16.00  | 16.00             |
| Október 3.        | Október 3.    | Beszerzési számla           | 2        | 20,00  | 12,00             |
| Október 5.        | Október 5.    | Értékesítési rendelés                | -1       | -10,00 | 13.00             |
| Október 7.        | Október 7.    | Beszerzési számla           |          | 2.00   | 14.00             |
| Október 8.        | Október 8.    | Átértékelés-átlag mozgatása |          | 4.00   | 16.00             |
|                  | október 31.   | Összesen                      | 2        | 32.00  | 16.00             |

> [!NOTE]
> A **Tranzakció ideje szerinti rendezés** lehetőséget alkalmazva nem tudja egyeztetni a főkönyvet a készlettel. A jelentést a **Feladási dátum** lehetőség használatával kell kinyomtatni.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]