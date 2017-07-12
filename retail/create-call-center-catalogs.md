---
title: "Új hívásközpont létrehozása"
description: "Ez a cikk egy áttekintést nyújt a telefonos ügyfélszolgálathoz tartozó katalógus létrehozásának folyamatáról."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: annbe
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 16212
ms.assetid: c9d1b9df-82e8-4b3a-a13c-166df8b9718e
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: Human Translation
ms.sourcegitcommit: 59b51840c05fe649cf322bfa64737a321728a5aa
ms.openlocfilehash: 28aaa84c11a897b895b2a106ca5f0cd6168997b2
ms.contentlocale: hu-hu
ms.lasthandoff: 06/20/2017

---

# <a name="create-a-call-center-catalog"></a>Új hívásközpont létrehozása

[!include[banner](includes/banner.md)]


Ez a cikk egy áttekintést nyújt a telefonos ügyfélszolgálathoz tartozó katalógus létrehozásának folyamatáról. 

Az ügyfélszolgálaton használhatja a termékkatalógusokat a termékek azonosításához, amelyet a vevőknek szeretne árusítani. Az ügyfélszolgálatok általában nyomtatott katalógusokat használnak. A nyomtatott katalógusok tervezése és gyártása a Microsoft Dynamics 365 for Retail rendszeren kívül történik. Azonban a katalógus digitális formáját létrehozhatja és tárolhatja ugyanazon oldalakkal, amelyeket az online kiskereskedelmi katalógusok beállítására használ. Katalógus létrehozása előtt állítsa be a termék szortimenteket a rendszerben, és a szortimenteket rendelje hozzá egy ügyfélszolgálathoz. Majd adja hozzá a termékeket a katalógushoz a termékek kijelölésével a szortimentekből. Miután a termékeket hozzáadta a katalógushoz, és a katalógus befejeződött, ellenőriznie kell a katalógust, az adatok igazolásához. Ezután küldje el a katalógust ellenőrzésre és jóváhagyásra. Jóváhagyás után a katalógus közzétehető. Az ügyfélszolgálati katalógus létrehozásakor, megnézheti a katalógusadatok pillanatképét abban az időpontban, amikor a katalógus közzétele történik. A pillanatkép-funkció segítségével elérheti a katalógus egy adott verzióját, még akkor is, ha a katalógus később módosul és frissül. Az ügyfélszolgálati katalógusokat is be lehet állítani, hogy az alábbi választható szolgáltatásokat tartalmazzák.

-   **Forráskódok** – Kódok, amelyek az egyes katalógusokra kapott vevői válaszok nyomon követésére használatosak.
-   **Szabadszöveges termékek** – Termékek, amelyek a vevői rendelésben extra díjak nélkül szerepelnek. Ezek a termékek hozzáadódnak a rendeléshez automatikusan a katalógus forráskódjának a rendelésbe történő bevitelekor.
-   **Parancsfájlok** – Szövegek, amelyeket az ügyfélszolgálat dolgozó olvas a vevőnek, egy értékesítési rendelés létrehozásakor. Parancsfájlok tartalmazhatnak üdvözletet vagy beszerzési javaslatokat.
-   **Upsell vagy párhuzamosan értékesített cikkek** - elemek, amelyeket meg javaslatként egy adott termék a rendeléshez történő hozzáadásakor.

Ezek a beállítások a katalógus jóváhagyása és közzététele előtt be kell állítani.

## <a name="prerequisites"></a>Előfeltételek
Mielőtt hozzálátna, a következő eljárásoknak készen kell lenniük:

-   Állítsa be a termékeket és a termék szortimenteket.
-   Kereskedelmi termékek beállítása.
-   Szortiment beállítása.
-   Ügyfélszolgálat létrehozása.
-   Állítsa be a hívásközpont paramétereit:
-   Ügyfélszolgálat hozzáadása a szervezeti hierarchiához.
-   Szervezeti hierarchia létrehozása vagy módosítása.

## <a name="create-a-catalog"></a>Katalógus létrehozása
Először hozza létre a katalógust, adja a katalógushoz a kívánt termékeket, majd ellenőrizze és frissítse a termékattribútumokat.

## <a name="validate-the-catalog"></a>Katalógus érvényesítése
A katalógus beállításának befejezése után le kell futtatni az ellenőrzési folyamatot. Ez a folyamat ellenőrzi, hogy a csatornaattribútumokhoz és termékattribútumokhoz szükséges adat teljes és érvényes, és, hogy a katalógus közzétehető.

## <a name="submit-the-catalog-for-review-and-approval"></a>A beszerzési katalógus elküldése jóváhagyásra
A katalógust az érvényesítést követően elküldheti ellenőrzésre és jóváhagyásra. A katalógust közzététel előtt jóvá kell hagyni. A munkafolyamat konfigurálható úgy, hogy a katalógusok automatikusan legyenek jóváhagyva, és úgy is, hogy manuális jóváhagyást igényeljenek.

## <a name="optional-add-source-codes-free-products-and-scripts"></a>Választható: Forráskódok, ingyenes termékek és a parancsprogramok hozzáadása
A következő elemeket hívás center katalógushoz is megadhat. Ezeket a funkciókat nem kötelező beállítani.

-   Míg mások nyomtatott katalógusok **Forráskódok** segítségével nyomon követheti a vevő választ melyik katalógusokban. Forráskódok gyakran egy katalógus hátoldalán vannak nyomtatva, és akkor kerülnek be az értékesítési rendelésbe, amikor a vevő leadja a rendelést. Forráskód a katalógushoz való hozzáadásához először létre kell hoznia egy célpiacot. A célpiac általában hozzá van rendelve egy saját tulajdonú vagy bérelt levelezési listához.
-   **Ingyenes termékek** esetén szereplő akciós cikkek díjmentesen a vevői rendeléshez a katalógus hivatkozik.
-   **Parancsfájlok** vezet a dolgozó interakciók vevők összefüggésben a katalógust vagy a katalógus belül használható.

## <a name="publish-the-catalog"></a>Katalógus közzététele
A katalógus ügyfélszolgálat részére történő közzétételével véglegesíti a termékkel kapcsolatos információt a katalógusban. A közzététel azt is jelzi, hogy a katalógus kész további műveletekre, amelyeket szeretne végezni, például egy nyomtatott katalógus létrehozása. Ha például egy nyomtatott katalógus is létrehozhat. A katalógusokat manuálisan, vagy kötegfolyamat segítségével ütemezés alapján is közzéteheti. A katalógust a közzététel előtt ellenőrizni kell, és jóvá kell hagyni. Ha módosítani szeretné a katalógust a közzétételt követően, visszavonhatja a katalógust, és majd tegye közzé újra.




