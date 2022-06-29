---
title: Fel a költségszámla könyvelési elvbe
description: Ez a cikk áttekintést nyújt a költségszámla könyvelési elve alapján feladott cikkről.
author: rachel-profitt
ms.date: 05/02/2022
ms.topic: article
ms.search.form: InventPosting, InventItemGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: raprofit
ms.search.validFrom: 2022-05-02
ms.dyn365.ops.version: 10.0.27
ms.openlocfilehash: c03109baaa341b25af70840b791ddf04f692fb1a
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/15/2022
ms.locfileid: "9016565"
---
# <a name="post-to-charge-account-accounting-principle"></a>Fel a költségszámla könyvelési elvbe

A *feladás* a költségszámla könyvelési elvével lehetővé teszi a tényleges feladás és a pénzügyi feladás, a beszerzett cikkek közvetett költségei és a beszerzési rendelés költségei közötti egységár közötti eltérések elszámolását és egyszerű egyeztetését.

A Kötelezettségek költségkódok két konfigurációja a Költségkód **lapon** (**Kötelezettségek \>\> – Költségek beállítása – Költségkód**) a beszerzési rendelések miatt befolyásolhatja a készleteszköz-értékeléseket:

- Olyan **költségkódok** *·* **·** *esetén*, amelyekben a Tartozás típusa mező beállítása Cikk, és a Követel típus mező beállítása Főkönyvi számla, a költségkönyvelési számlaként kiválasztott főkönyvi számla készletváltozat-számlaként viselkedik.
- Olyan **költségkódok** *·* **·** *esetén, amelyekben a Tartozik típus mező beállítása Cikk, és a Követel típus mezőben a Vevő/* Szállító érték van beállítva, a költséget anyagköltségként, a cikk készlet variációs számláját használja a rendszer.

## <a name="european-special-accounting-rule"></a>Európai speciális könyvelési szabály

Európában gyakran használják *a számlakönyvelési alapelvet* a költségkönyvelésre való postán, hogy egy speciális könyvelési szabályt használjanak. Például az alábbi módszerek egyikét általában a készletváltozások figyelembe veszik:

- **Értékesítési költség módszer** – a szokásos készletfeladási profil konfigurációja támogatja ezt a módszert. A *költségszámla-könyvelési alapelvet* nem kötelező megadni.
- **Költség jellege módszer** – a kisebb szervezetek gyakran használják ezt a módszert. Ez általában a következő lépésekből áll:

    1. Az áruk és szolgáltatások a bevételezéskor teljesen költségként költségeket elszámolnak.
    2. Az időszak végén ciklikusan történik a számlálás.
    3. A mennyiség és érték manuális korrekcióját feladja a program a készletbe. (Az ellenszámla egy készlet variációs számlája, amely kiegyenlíti az 1. lépésben feladott költséget. Ebből következően a készletérték eltérése csak ezen a számlán látható.)

A *költségszámla feladása* elvvel teljesen automatizálható a két feladás. Ily módon eltávolíthatja az időszak végi manuális záró korrekció feladását.

## <a name="enable-the-post-to-charge-account-accounting-principle"></a>A költségszámla feladható könyvelési elvének engedélyezése

A költségszámla könyvelési *elvének engedélyezéséhez* kövesse ezeket a lépéseket.

1. Ugorjon a **Kötelezettségek \> Beállítás \> Kötelezettségek paraméterei pontra**.
2. A Számla **lap** **Számla** gyorslapján **állítsa** *a Feladás költségszámla főkönyvi beállítás Igen beállításra.*
3. Zárja be a lapot.

## <a name="prerequisites-and-recommended-parameters-for-the-post-to-charge-account-accounting-principle"></a>A költségszámla könyvelési elvének előfeltételei és javasolt paraméterei

Ha figyelembe veszi a beszerzési költségeket és a készlet variációit, a következő előfeltételeknek kell megfeleltetve lennie:

- A Kötelezettségek **paraméterei** lap **Számla** lapján (**Kötelezettségek \>\>** beállítása – Kötelezettségek paraméterei) **a** Főkönyvi Feladás költségszámlája beállításNál Igen beállítást kell *beállítani.*
- A Cikkmodellcsoportok **lapon** (**Költségkezelés \>\>** – Készletkönyvelési irányelvek beállítása – Cikkmodellcsoportok) minden olyan vonatkozó modellcsoport esetében igen beállítást kell beállítani, *amely* a beszerzési rendelésben szereplő cikkeket tartalmazza:

    - Tényleges készlet feladása
    - Pénzügyi készlet feladása
    - Kötelezettség elhatárolása termékbevételezéskor

- A Beszerzés **és** forrás **paraméterei** lap Szállítás lapján (**\>\>** Beszerzés és forrás beállítása – Beszerzés és forrás paraméterei) **·** *a Költségek létrehozása a termékbevételezéshez beállítást Igen beállításra kell állítani.*
- A Készlet **- és raktárkezelési** **paraméterek lap Készletkönyvelés lapján (** Készletkezelés beállítása **\> – Készlet- és raktárkezelési paraméterek \>)** **a** Szállítólevél főkönyvi feladása beállítást Igen beállításra kell állítani *.*
- A Feladás **lap** **·** (**\>\>\>** Készletkezelés beállítása – Feladás) lapján az összes vonatkozó cikkre vonatkozó fő számlákat az alábbi feladási típusokhoz kell megadni:

    - Beszerzési kiadás, nem számlázott
    - Termékre vonatkozó beszerzési kiadás
    - Készlet variációja

## <a name="example-scenario-1-change-in-unit-cost-price"></a>1. példa: Egység önköltségi árának módosítása

Ebben a példában a következő előfeltételek vannak:

- ELSŐKÉNT be, elsőként ki (FIFO) költségszámítási modell

Az alábbi eljárás bemutatja, hogy mi történik, ha módosítja az önköltségi egységárat egy beszerzési rendelésen.

1. Hozzon létre egy beszerzési rendelést, 1 mennyiséggel egy 100,00 egységárral.
2. Erősítse meg a beszerzési rendelést.
3. A beszerzési rendelés termékbevételezésének feladott bevételezése.
4. A termékbevételezés bizonylatának ellenőrzése. A következő táblázat egy mintabizonylatot mutat be.

    | Feladás típusa | Fő számla | Fő számla neve | Számla típusa | Tartozik/követel? | Elszámolási számla | Fizikai/pénzügyi? | Összeg |
    |---|---|---|---|---|---|---|---|
    | Beszerzés, készletváltozás | 600170 | Készlet variációs anyagai | Költség | Jóváírás | Nem | Tényleges | -100,00 |
    | Megvásárolt anyagok bevételezett költsége | 140100 | Anyagkészlet | Eszközök | Terhelés | Igen | Tényleges | 100.00 |
    | Beszerzési kiadás, nem számlázott | 600180 | Anyagbevételezések | Költség | Terhelés | Igen | Tényleges | 100.00 |
    | Beszerzés, elhatárolás | 200140 | Elhatárolt beszerzések | Kötelezettség | Jóváírás | Igen | Tényleges | -100,00 |

5. A beszerzési rendeléshez tartozó, 110,00 egységáron frissített számla feladható.
6. A számlán szereplő bizonylat ellenőrzése. A következő táblázat egy mintabizonylatot mutat be.

    | Feladás típusa | Fő számla | Fő számla neve | Számla típusa | Tartozik/követel? | Elszámolási számla | Fizikai/pénzügyi? | Összeg |
    |---|---|---|---|---|---|---|---|
    | Beszerzés, készletváltozás | 600170 | Készlet variációs anyagai | Költség | Jóváírás | Nem | Pénzügyi | -10,00 |
    | Megvásárolt anyagok bevételezett költsége | 140100 | Anyagkészlet | Eszközök | Terhelés | Igen | Pénzügyi | -100,00 |
    | Beszerzési kiadás, nem számlázott | 600180 | Anyagbevételezések | Költség | Terhelés | Igen | Pénzügyi | -100,00 |
    | Beszerzés, elhatárolás | 200140 | Elhatárolt beszerzések | Kötelezettség | Jóváírás | Igen | Pénzügyi | 100.00 |
    | Megvásárolt anyagok számlázott költsége | 140100 | Anyagkészlet | Eszközök | Terhelés | Nem | Pénzügyi | 110.00 |
    | Termékre vonatkozó beszerzési kiadás | 600180 | Anyagbevételezés | Költség | Jóváírás | Nem | Pénzügyi | 110.00 |
    | Szállítói egyenleg | 211000 | Kötelezettségek - kereskedelem | Kötelezettség | Jóváírás | Nem | Pénzügyi | -110.00 |

## <a name="example-2-charges-and-indirect-costs-on-the-purchase-order"></a>2. példa: Költségek és közvetett költségek a beszerzési rendelésen

Ebben a példában a következő előfeltételek vannak:

- FIFO költségszámítási modell
- **1. költségkód:** tartozik cikk és követel főkönyvi számla 10%-ot
- **2. költségkód:** tartozik cikk és követel vevő/szállító 10,00 arányban
- **Közvetett költség:** 2,00% hozzáadva a beszerzési árhoz

Az alábbi eljárás bemutatja, hogy mi történik, amikor a költségeket és a közvetett költségeket be kell foglalni a beszerzési rendelésbe.

1. Hozzon létre egy beszerzési rendelést, 1 mennyiséggel egy 100,00 egységárral.
2. Adjon meg egy 10 százalékos költségkódot, amely megterheli a cikket, és követel tételt könyvel a főkönyvbe.
3. Adjon meg egy költségkódot a 10,00 összeghez, amely megterheli a cikket, és követel tételt a vevőnek/szállítónak.
4. A költségek felosztása a beszerzésirendelés-sorokhoz.
5. Erősítse meg a beszerzési rendelést.
6. A beszerzési rendelés termékbevételezésének feladott bevételezése.
7. A termékbevételezés bizonylatának ellenőrzése. A következő táblázat egy mintabizonylatot mutat be.

    | Feladás típusa | Fő számla | Fő számla neve | Számla típusa | Tartozik/követel? | Elszámolási számla | Fizikai vagy pénzügyi | Összeg |
    |---|---|---|---|---|---|---|---|
    | Beszerzés, készletváltozás | 600170 | Készlet variációs anyagai | Költség | Jóváírás | Nem | Tényleges | -110.00 |
    | Felhasznált becsült közvetett költség | 600520 | Akkreált közvetett költségek | Költség | Jóváírás | Igen | Tényleges | -2.40 |
    | Beszerzés fuvardíja | 600120 | Fuvar- és szállítási költségek | Költség | Jóváírás | Nem | Tényleges | -10,00 |
    | Megvásárolt anyagok bevételezett költsége | 140100 | Anyagkészlet | Eszközök | Terhelés | Igen | Tényleges | 122.40 |
    | Beszerzési kiadás, nem számlázott | 600180 | Anyagbevételezések | Költség | Terhelés | Igen | Tényleges | 110.00 |
    | Beszerzés, elhatárolás | 200140 | Elhatárolt beszerzések | Kötelezettség | Jóváírás | Igen | Tényleges | -110.00 |

8. A beszerzési rendelés számlájának a feladott összege.
9. A számlán szereplő bizonylat ellenőrzése. A következő táblázat egy mintabizonylatot mutat be.

    | Feladás típusa | Fő számla | Fő számla neve | Számla típusa | Tartozik/követel? | Elszámolási számla | Fizikai/pénzügyi? | Összeg |
    |---|---|---|---|---|---|---|---|
    | Beszerzés, készletváltozás | 600170 | Készlet variációs anyagai | Költség | Jóváírás | Nem | Pénzügyi | 0,00 |
    | Felhasznált becsült közvetett költség | 600520 | Akkreált közvetett költségek | Költség | Terhelés | Igen | Pénzügyi | 2.40 |
    | Felhasznált közvetett költség | 600520 | Akkreált közvetett költségek | Költség | Terhelés | Nem | Pénzügyi | -2.40 |
    | Megvásárolt anyagok bevételezett költsége | 140100 | Anyagkészlet | Eszközök | Jóváírás | Igen | Pénzügyi | -110.00 |
    | Beszerzési kiadás, nem számlázott | 600180 | Anyagbevételezések | Költség | Jóváírás | Igen | Pénzügyi | -110.00 |
    | Beszerzés, elhatárolás | 200140 | Elhatárolt beszerzések | Kötelezettség | Terhelés | Igen | Pénzügyi | 110.00 |
    | Megvásárolt anyagok számlázott költsége | 140100 | Anyagkészlet | Eszközök | Terhelés | Nem | Pénzügyi | 110.00 |
    | Termékre vonatkozó beszerzési kiadás | 600180 | Anyagbevételezés | Költség | Jóváírás | Nem | Pénzügyi | 110.00 |
    | Szállítói egyenleg | 211000 | Kötelezettségek - kereskedelem | Kötelezettség | Jóváírás | Nem | Pénzügyi | -110.00 |
