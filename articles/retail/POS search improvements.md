---
title: "Termék- és vevőkeresés a pénztárban"
description: "Ez a témakör áttekintést nyújt a Dynamics 365 for Retail termék- és vevőkeresési funkcióján végrehajtott fejlesztésekről."
author: shalabhjain
manager: AnnBe
ms.date: 08/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application user
ms.search.scope: Operations, Retail
ms.custom: 141393
ms.assetid: 
ms.search.region: Global
ms.search.industry: Retail
ms.author: shajain
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: Retail April 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 66859535ee118ffc04a847dfe6e8e0bae1cd9d6c
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="overview-of-product-and-customer-search-in-point-of-sale"></a>Termék- és vevőkeresés áttekintése a pénztárban

A modern pénztár (MPOS) és a felhőpénztár (CPOS) könnyen használható keresési funkciót biztosítanak, amellyel a bolti alkalmazottak gyorsan kereshetnek termékeket és vevőket. A keresési sáv mindig látható az MPOS és a CPOS tetején, így az alkalmazottak gyorsan megtalálhatják a termékeket és a vevőket.

Az alkalmazottak az aktuális üzlethez társított katalógusokban és szortimentekben, valamint a vállalat bármely más üzletéhez társított katalógusokban és szortimentekben kereshetnek termékeket. Ezért a pénztárosok értékesíthetnek és visszaküldhetnek az üzlet szortiment kívül eső termékeket. Ehhez hasonlóan az alkalmazottak kereshetnek a jelenlegi vagy a vállalat bármely más üzletével társított vevőkkel. Ezenkívül az alkalmazottak kereshetnek a fölérendelt szervezet bármely másik vállalatához társított vevőket.

## <a name="product-search"></a>Termékkeresés 

A termékek keresése alapértelmezés szerint az üzletszortiment alapján történik. Az ilyen típusú keresés *helyi termékkeresés* néven ismert. Azonban az alkalmazottak egyszerűen átválthatnak bármelyik az aktuális üzlethez társított katalógusra, illetve keresést végezhetnek másik üzletben. Az ilyen típusú keresés *távoli termékkeresés* néven ismert. A katalógus megváltoztatásához válassza a **Kategóriák** gombot a lap bal oldalán. A megjelenő ablak tetején válassza a **Katalógus módosítása** gombot, és a tallózáshoz válasszon a rendelkezésre álló katalógusok közül. A rendszer megkeresi a termékeket a kijelölt katalógusban.

A **Katalógus módosítása** oldalon az alkalmazottak egyszerűen kiválaszthatnak minden üzletet, illetve végezhetnek keresést termékekre minden üzletben.

![A katalógus módosítása](./media/Changecatalog.png "A katalógus módosítása")
 
A helyi termékkeresés a következő terméktulajdonságokon belül keres:

- Termékszám
- Termék neve
- Leírás
- Dimenziók
- Vonalkód
- Keresési név

### <a name="enhancements-to-local-product-searches"></a>Helyi termékkeresések továbbfejlesztése

A helyi termékkeresés élménye felhasználóbarátabbá vált. A következő fejlesztések történtek:

- A termék és vevő legördülő menük bekerültek a Keresés mezőbe, hogy az alkalmazottak választhassanak a **Termék** vagy a **Vevő** közül a keresés előtt. Alapértelmezés szerint a **Termék** van ki jelölve a következő ábrán látható módon.
- A több kulcsszavas keresésnél (például a keresési kifejezések használatával végzett keresésnél), a kiskereskedők beállíthatják, hogy a keresési találatok közé a bármelyik keresési feltételnek megfelelő találatok vagy csak az összes keresési feltételeknek megfelelő találatok kerüljenek-e be. Ez a beállítás a pénztári funkcióprofilban, a **Termékkeresés** nevű új csoportban érhető el. Az alapértelmezett beállítás **Bármelyik keresési kifejezés egyeztetése**. Ez a beállítás egyúttal az ajánlott beállítás is. Ha a **Bármelyik keresési kifejezés egyeztetése** beállítás van használva, az összes termék, amely részben vagy egészben megfelel legalább egy keresési feltételnek, megjelenik a találatok között, és a találatok automatikusan növekvő sorrendben vannak rendezve a legtöbb (teljes vagy részleges)egyező kulcsszóval rendelkező termékek szerint.

    Az **Az összes keresési kifejezés egyeztetése** beállítás csak a minden a keresési feltételnek (egészben vagy részlegesen) megfelelő termékeket adja vissza. Ez a beállítás akkor hasznos, ha a a terméknevek hosszúak, és az alkalmazottak csak korlátozott számú terméket akarnak látni a keresési eredmények között. Azonban az ilyen típusú keresésre két korlátozás vonatkozik:

    - A keresés az egyes terméktulajdonságok alapján történik. Például csak azokat a termékeket adja vissza, amelyeknél az összes keresett kulcsszó szerepel legalább egy terméktulajdonságnál.
    - A dimenziók között nincs keresés.

- A kiskereskedők a termékkeresést úgy is beállíthatják, hogy keresési javaslatok jelenjenek meg a terméknevek beírása közben. A funkció egy új beállítása a pénztári funkcióprofilban, a **Termékkeresés** nevű csoportban érhető el. A beállítás neve **Keresési javaslatok mutatása gépelés közben**. A funkció segítségével az alkalmazottak gyorsan megtalálhatják a terméket, amelyet keresnek, mivel nem kell manuálisan beírniuk a teljes nevét.
- A termékkeresési algoritmus mostantól a **Keresési név** terméktulajdonságban is keresi a keresési kifejezéseket.

![Termékjavaslatok](./media/Productsuggestions.png "Termékjavaslatok")

## <a name="customer-search"></a>Vevőkeresés

A vevőkereséssel különböző célokkal kereshetők vevők. Például lehet, hogy a pénztáros szeretné megnézni egy vevő kívánságlistáját vagy beszerzési előzményeit, vagy hozzá akarja adni a vevőt egy tranzakcióhoz. Több kulcsszavas keresés esetén a vevőkeresési algoritmus az összes olyan vevőt visszaadja, aki a keresett kulcsszavak bármelyikének megfelel. A legtöbb kulcsszónak megfelelő vevők azonban az eredmények tetején jelennek meg. Ez a viselkedés hasonló ahhoz, ahogy a többi keresési motor megjeleníti az eredményeket. Először a legtöbb keresett feltételnek megfelelő eredményeket jelenítik meg, utánuk pedig azokat az eredményeket, amelyek részben felelnek meg a kulcsszavaknak. Ez a viselkedés segítséget nyújt a pénztárosoknak az olyan helyzetekben, ahol a keresés során több kulcsszót használnak, de az egyik kulcsszóban helyesírási hiba található.

Alapértelmezés szerint a vevő keresése az üzlethez társított vevői címjegyzékekben történik. Az ilyen típusú keresés *helyi vevőkeresés* néven ismert. Azonban az alkalmazottak kereshetnek vevőt globálisan is. Más szavakkal kereshetnek a vállalat üzletei és az összes többi jogi személy között. Az ilyen típusú keresés *távoli vevőkeresés* néven ismert.

Globális kereséshez, az alkalmazottak választhatják az **Eredmények szűrése** gombot az oldal alján, majd a **Keresés az összes üzletben** paramétert a következő ábrán látható módon. Ebben az esetben nem csak a vevők szerepelnek a találatok között. Ehelyett a központ bármely címjegyzékében szereplő összes fél, típusától függetlenül, szintén megjelenik. Ezek a felek a dolgozók, a szállítók, kapcsolattartók és a versenytársak.

> [!NOTE]
> A távoli vevőkereséshez legalább négy karaktert meg kell adni, hogy legyen találat.

A távoli vevőkeresésnél a vevőkód nem jelenik meg a más jogi személyektől származó vevők esetében, mert a jelenlegi vállalatnál nem jött létre vevőkód ezekhez a felekhez. Ha azonban az alkalmazott megnyitja a vevő adatlapot, a rendszer automatikusan létrehozza a vevőkódot az adott félnek, és az üzlet vevői címjegyzékét is társítja a vevővel. Így a vevő a későbbiekben végzett helyi keresésekben is látható lesz.

![Globális vevőkeresés](./media/Globalcustomersearch.png "Globális vevőkeresés")

### <a name="enhancements-to-local-customer-searches"></a>Helyi vevőkeresések továbbfejlesztése

Helyi vevőkeresés segítségével az alkalmazottak gyorsan megtalálhatják a vevőket telefonszám alapján. Az alkalmazottaknak nem kell beírniuk a vevő telefonszámához hozzáadott esetleges speciális karaktereket, például szóközöket, kötőjeleket vagy zárójeleket. Annak ellenére, hogy a pénztárosok a telefonszámokat bármilyen formátumban tárolhatják (például tartalmazhatnak zárójeleket, kötőjeleket, szimbólumokat stb.), a vevők részleges telefonszám beírásával is kereshetők. Ha egy pénztáros speciális karaktereket alkalmazott a telefonszám megadásakor, más pénztárosok a vevőt a szám után megjelenő különleges karakterek beírásával találhatják meg. Ha például egy vevő telefonszámát **123-456-7890** formában rögzítették, a pénztáros kereshet a vevőre az **123**, **456**, **7890** vagy az **1234567890** beírásával, ill. a telefonszám első néhány számának részbeni megadásával.

