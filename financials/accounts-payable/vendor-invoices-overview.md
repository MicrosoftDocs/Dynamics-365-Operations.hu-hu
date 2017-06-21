---
title: "Szállítói számlák áttekintése"
description: "Ez a cikk a szállítói számlákkal kapcsolatos általános információkat tartalmazza. A szállítói számlák a bevételezett termékekért és szolgáltatásokért cserébe igényelt kifizetés kérelmei. A szállítói számlák vonatkozhatnak már folyamatban lévő szolgáltatásokra, vagy bizonyos termékek és szolgáltatások esetén beszerzési rendeléseken is alapulhatnak."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 13971
ms.assetid: 0ec4dbc0-2eeb-423b-8592-4b5d37e559d3
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 16ff8ebb0e620f45c4d290ee5076d5505abf3436
ms.contentlocale: hu-hu
ms.lasthandoff: 05/25/2017


---

# <a name="vendor-invoices-overview"></a>Szállítói számlák áttekintése

[!include[banner](../includes/banner.md)]


Ez a cikk a szállítói számlákkal kapcsolatos általános információkat tartalmazza. A szállítói számlák a bevételezett termékekért és szolgáltatásokért cserébe igényelt kifizetés kérelmei. A szállítói számlák vonatkozhatnak már folyamatban lévő szolgáltatásokra, vagy bizonyos termékek és szolgáltatások esetén beszerzési rendeléseken is alapulhatnak. 

<a name="vendor-invoices"></a>Szállítói számlák
---------------

A beszerzési rendelés szállítói számlája egy olyan számla, amit a szállítóval egyeztetett beszerzési rendelés alapján termékek vagy szolgáltatások kézbesítésekor jön létre. A szállítói számla fejlécet, valamint a cikkekre vagy szolgáltatásokra vonatkozó egy vagy több sort tartalmaz. A szállítói számlával a ciklus beszerzési rendelésből termékbevételezésre és szállítói számlára léphet tovább. 

Annak ellenére, hogy néhány szállítói számla beszerzési rendeléshez kapcsolódik a szállítói számlák tartalmazhatnak olyan sorokat is, amelyek nem tartoznak beszerzési rendeléssorokhoz. Olyan szállítói számlákat is létrehozhat, amelyek nincsenek hozzárendelve egyetlen beszerzési rendeléshez sem. Ezek a szállítói számlák jelenthetnek folyamatban lévő szolgáltatásokat, például segédprogram számlát, amelyek nem rendelkeznek hivatkozással a beszerzési rendeléshez hozzáadáskor. 

Számos módja van a szállítói számla bevitelének:

-   A szállítói számlajegyzék használatával gyorsan adhat meg számlákat amelyek nem rendelkeznek hivatkozással egy beszerzési rendeléshez, így elhatárolhatja a kiadást. Szállítói számla jóváhagyási napló használatával kiválaszthat számlákat és feladhatja azokat a szállítói egyenlegbe a könyvelt összeg sztornírozásához.
-   A szállítói számlanapló használatával gyorsan megadhat egy lépésben számlákat amelyek nem hivatkoznak a beszerzési rendelésre.
-   A szállítói gyűjtőszámlával a szállítói számlajegyzékkel gyorsan megadhat számlákat a költség elhatárolásához. Megnyithatja a kapcsolódó beszerzési rendeléseket később a számla kiadási számlára történő feladásához.
-   A **Nyitott szállítói számlák** és a **Függőben lévő szállítói számlák** lapok lehetővé teszik a szállítói számlák létrehozását a visszaigazolt beszerzési rendelésekből.

Az alábbi vitafórumon további információkat tudhat meg a **Nyitott szállítói számlák** vagy a **Függőben lévő szállítói számlák** oldalak használatáról, ha szállítói számlát szeretne létrehozni egy beszerzési rendelésből.

## <a name="understanding-invoice-line-quantities"></a>Számlasor mennyiségek ismertetése
Ha szállítói számlát egy kapcsolódó beszerzési rendelésből nyit meg, akkor számlasorok jönnek létre a beszerzési rendelésből. Alapértelmezés szerint a termékbevételezési mennyiségből származik. Azonban a következő alapértelmezett viselkedések bármelyikét használhatja:

-   **Most bevételezett mennyiség** – Használja részleges szállítmányokhoz ezt a lehetőséget. A **Mennyiség** mezőben az alapértelmezett érték a **Fogadás** mennyiség mezőjéből származik, a beszerzési rendelésből.
-   **Rendelt mennyiség** – Használja teljes szállítmányokhoz ezt a lehetőséget. A **Mennyiség** alapértelmezett értéke a beszerzési rendelés **Megrendelt** mennyiség mezőjéből származik.
-   **Regisztrált mennyiség** – Használja ezt a lehetőséget, ha a cikkhez regisztráció szükséges a megadott a **Cikkmodell csoportok** oldalon. A **Mennyiség** mezőben szereplő alapértelmezett érték a regisztrált fizikai módosítási mennyiség.
-   **Termékbevételezési mennyiség** – Akkor válassza, ha a rendelés már átesett termékbevételezésen. A **Mennyiség** mezőben szereplő alapértelmezett érték a termékbevételezéseken elérhető teljes mennyiség.
-   **Regisztrált mennyiség és szolgáltatások** – Akkor használja, ha az érkeztetési naplóban raktározott cikkek vagy a nem raktározott cikkek regisztrált mennyiségek. Ez a beállítás a szolgáltatásokat is tartalmazza, függetlenül attól, hogy regisztrálva vannak-e.

Ha a jogi személy számlaegyeztetést használ, akkor megtekintheti a mennyiségegyeztetés eredményeit a **Termékbevételezés mennyiségi egyeztetése** oszlopban. Használhatja az **Egyezetés részletei** menü parancsot is az **Ellenőrzés** fülön a mennyiségegyeztetés eredményeinek megtekintéséhez.

## <a name="adding-a-line-that-wasnt-on-the-purchase-order"></a>Új sor hozzáadása amely nem volt megnyitva a beszerzési rendelésen
Hozzáadhat új sorokat, amelyek nem voltak a szállítói számla beszerzési rendelésében. Ki kell választania egy cikkszámot vagy beszerzési kategóriát. Ezután hozzáadhatja mennyiségeket, árakat és összegeket a sorhoz. A sor csak az egyeztetési irányelvek számlaösszegeiben fog szerepelni.

## <a name="submitting-a-vendor-invoice-for-review"></a>Szállítói számla küldése ellenőrzésre
A szervezet használhat meghatározott munkafolyamatokat a szállítói számlák ellenőrzési eljárásához. A munkafolyamat előírhatja a számlafejléc, a számlasor vagy mindkettő ellenőrzését. A munkafolyamat vezérlőelemei a fejlécre vagy a sorra vonatkoznak, attól függően, hogy hol van a fókusz, amikor a vezérlőelemre kattint. A **Feladás** gomb helyett a **Küldés** gomb jelenik meg, amelyet használhat szállítói számla feladásához az ellenőrzési folyamat során.

## <a name="matching-vendor-invoices-to-product-receipts"></a>Szállítói számlák egyeztetése a termékbevételezésekkel
Megadhatja és mentheti a szállítói számlák adatait, és a számlasorokat egyeztetheti a termékbevételezési sorokkal. Részleges mennyiségeket is egyeztethet a soroknál. 

Szállítói számlát létrehozhat a termékbevételezési sorokban az adott napig bevételezett cikkek alapján akkor is, ha még nem érkezett meg egy meghatározott beszerzési rendelés összes cikke. Például ezt olyankor teheti meg, amikor egy szállító havonta egy számlát küld, amely a szállító által az adott hónapban kézbesített összes szállítást fedezi. Mindegyik termékbevételezés a beszerzési rendelésen szereplő cikkek egy-egy részleges vagy teljes szállításának felel meg. 

A számla feladásakor a **Számlahátralék** mennyisége minden cikkre vonatkozóan frissül a kiválasztott termékbevételezéseken fogadott mennyiségekkel. Ha a beszerzési rendelésen található összes cikknél 0 (nulla) a **Számlahátralék** és a **Fennmaradó szállítása** értéke, a beszerzési rendelés **Számlázott** állapotú lesz. Ha a számlához tartozó **Számlahátralék** mennyisége nem 0, akkor a beszerzési rendelés állapota változatlan marad, és további számlákat lehet hozzá rögzíteni.

Ez a lehetőség azt feltételezi, hogy legalább egy termékbevételezést feladtak a beszerzési rendeléshez. A szállítói számla ezeken a termékbevételezéseken alapul, és azok mennyiségeit tükrözi. A számla pénzügyi adatai a számla feladásakor megadott információkon alapulnak.

## <a name="working-with-multiple-invoices"></a>Több számla használata

Dolgozhat egyszerre több számlával, és fel is adhatja azokat egyszerre. Ha több számlát kell létrehoznia, akkor használja a **Függőben lévő szállítói számlák** oldalt. Ha több szállítói számlát kell feladni és nyomtatni, akkor használja a számla-jóváhagyási napló oldal.t Ha számla-jóváhagyási naplót használ, legalább egy termékbevételezést feladtak, és a beszerzési rendelés számláját fel kell adni a számlajegyzékbe. A számla pénzügyi adatai a számlajegyzékbe feladott számláról származnak.





