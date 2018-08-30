---
title: "Termék- és vevőkeresés a pénztárban (POS)"
description: "Ez a témakör áttekintést nyújt a Microsoft Dynamics 365 for Retail termék- és vevőkeresési funkcióján végrehajtott fejlesztésekről."
author: ShalabhjainMSFT
manager: AnnBe
ms.date: 03/28/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application user
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 141393
ms.assetid: 
ms.search.region: Global
ms.search.industry: Retail
ms.author: shajain
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: Retail April 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 5098fb3339403b6f2779dfe3bb7ef5c4ca78051f
ms.openlocfilehash: 50b0cec27e343b3b6aba464a04c9883160ab263a
ms.contentlocale: hu-hu
ms.lasthandoff: 08/09/2018

---

# <a name="product-search-and-customer-search-in-the-point-of-sale-pos"></a>Termék- és vevőkeresés a pénztárban (POS)

[!include [banner](includes/banner.md)]

A modern pénztár (MPOS) és a felhőpénztár (CPOS) könnyen használható termék- és vevőkeresési funkciót biztosítanak. Mivel a keresési sáv mindig látható az MPOS és a CPOS ablakok tetején, így az alkalmazottak gyorsan megtalálhatják a termékeket és a vevőket.

Az alkalmazottak az aktuális üzlethez kapcsolódó szortimentekben és katalógusokban kereshetnek termékeket. Emelletta vállalatban található üzletekhez kapcsolódó szortimentekben és katalógusokban is kereshetnek. Ezért a pénztárosok értékesíthetnek és visszaküldhetnek az üzlet szortiment kívül eső termékeket. Ehhez hasonlóan az alkalmazottak kereshetnek a jelenlegi vagy a vállalat bármely más üzletével társított vevőket. Ezenkívül az alkalmazottak kereshetnek a fölérendelt szervezet bármely másik vállalatához társított vevőket.

## <a name="product-search"></a>Termékkeresés

A termékek keresése alapértelmezés szerint az üzletszortiment alapján történik. Az ilyen típusú keresés *helyi termékkeresés* néven ismert. Azonban az alkalmazottak egyszerűen átválthatnak bármelyik az aktuális üzlethez társított katalógusra, illetve keresést végezhetnek másik üzletben. Az ilyen típusú keresés *távoli termékkeresés* néven ismert. A katalógus megváltoztatásához válassza a **Kategóriák** gombot a lap bal oldalán. A megjelenő ablak tetején válassza a **Katalógus módosítása** gombot, és a tallózáshoz válasszon a rendelkezésre álló katalógusok közül. A rendszer megkeresi a termékeket a kijelölt katalógusban.

A **Katalógus módosítása** oldalon az alkalmazottak egyszerűen kiválaszthatnak minden üzletet, illetve végezhetnek keresést termékekre minden üzletben.

![A katalógus módosítása](./media/Changecatalog.png "A katalógus módosítása")
 
A helyi termékkeresés a következő terméktulajdonságokon belül történik:

- Termékszám
- Termék neve
- Leírás
- Dimenziók
- Vonalkód
- Keresési név

### <a name="enhancements-to-local-product-searches"></a>Helyi termékkeresések továbbfejlesztése

A helyi termékkeresés használata felhasználóbarátabbá vált. A következő fejlesztések történtek:

- A termék és vevő legördülő menük bekerültek a Keresés mezőbe, hogy az alkalmazottak választhassanak a **Termék** vagy a **Vevő** közül a keresés előtt. Alapértelmezés szerint a **Termék** van ki jelölve a következő ábrán látható módon.
- A több kulcsszavas keresésnél (például a keresési kifejezések használatával végzett keresésnél), a kiskereskedők beállíthatják, hogy a keresési találatok közé a *bármelyik* keresési feltételnek megfelelő találatok vagy csak az *összes* keresési feltételeknek megfelelő találatok kerüljenek-e be. Ez a beállítás a pénztári funkcióprofilban, a **Termékkeresés** nevű új csoportban érhető el. Az alapértelmezett beállítás **Bármelyik keresési kifejezés egyeztetése**. Ez a beállítás egyúttal az ajánlott beállítás is. A **Bármely keresési kifejezésnek megfelel** beállítás használatakor minden olyan termék megjelenik a találatok között, amely egy vagy több teljes vagy részleges keresési kifejezést tartalmaz. Ezeket az eredményeket a rendszer automatikusan sorrendbe rendezi azon olyan termékek növekvő sorrendjében, amelyeknél a legtöbb a kulcsszóegyezés (teljes vagy részleges).

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

### <a name="enhancements-to-local-customer-search"></a>Helyi vevőkeresés továbbfejlesztése

A telefonszámon alapuló keresések egyszerűbbé váltak. Ezek a keresések most figyelmen kívül hagyják a különleges karaktereket, például a szóközöket, kötőjeleket és zárójeleket, amelyeket a vevő létrehozásakor esetleg hozzáadtak. Ezért a pénztárosoknak nem kell többé a telefonszámformátum miatt aggódniuk, amikor keresnek. Kereshetnek a vevők részleges telefonszámának beírásával is. Ha egy telefonszám különleges karaktereket tartalmaz, megtalálható a speciális karakterek után megjelenő számok keresésével is. Ha például egy vevő telefonszámát **123-456-7890** formában rögzítették, a pénztáros kereshet a vevőre az **123**, **456**, **7890** vagy az **1234567890** beírásával, ill. részlegesen a telefonszám első néhány számának részbeni megadásával.

A hagyományos vevőkeresés időigényes lehet, mivel több mező között keres. Ehelyett most a pénztárosok kereshetnek egyetlen egyéni tulajdonságra, például névre, e-mail-címre vagy telefonszámra. A vevőkeresési algoritmus által használt tulajdonságok együttes neve: *vevőkeresési feltételek*. A rendszergazda egyszerűen konfigurálhat egy vagy több kritériumot olyan rövidítésként, amelyek megjelennek a pénztárban. Mivel a keresés egyetlen feltétel korlátozódik, csak a releváns keresési eredmények jelennek meg, és a teljesítmény sokkal nagyobb, mint a szokásos vevő keresés teljesítménye. Az alábbi ábra mutatja a pénztár vevőkeresési rövidítéseit.

![Vevőkeresési rövidítések](./media/SearchShortcutsPOS.png "Vevőkeresési rövidítések")

Keresési keresési feltételek rövidítésekként történő beállításához a rendszergazda nyissa meg a **Kiskereskedelmi paraméterek** oldalt a Microsoft Dynamics 365 for Finance and Operations szolgáltatásban, majd a **Pénztári keresési feltételek** fülön válassza ki a feltételeket, amelyeket szeretne rövidítésekként megjeleníteni.

![Keresési rövidítések konfigurálása](./media/ConfigureShortcutsAX.png "Keresési rövidítések konfigurálása")

> [!NOTE]
> Ha túl sok rövidítést ad hozzá, a pénztár keresés sávjának legördülő menüje zsúfolttá fog válni, ami hatással lehet a keresés használhatóságára az alkalmazott számára. Javasoljuk, hogy csak annyi rövidítést adjon hozzá, amennyire szüksége van.

A **Megjelenítési sorrend** mező határozza meg, hogy melyik rövidítések jelennek meg a pénztárban. A látható feltételek alapból rendelkezésre álló tulajdonságok, amelyeket a vevőkeresési algoritmus a vevők keresésére használ. A partnerek azonban egyedi tulajdonságokat is hozzáadhatnak keresési rövidítésként. Ha egyéni tulajdonságokat kíván keresési rövidítésként hozzáadni, a rendszergazdának ki kell terjesztenie az ügyfélkeresési feltételekhez használt kiterjeszthető felsorolást (enum), majd meg kell jelölnie a partner egyedi tulajdonságait rövidítésekként. A partnerek felelősek azon kód megírásáért, amely találatokat biztosít, amikor amikor egyéni rövidítéseiket keresésekre használják.

> [!NOTE]
> Az egyéni tulajdonság, amelyet hozzáadnak a felsoroláshoz, nem befolyásolja a normál vevői keresési algoritmust. Más szóval a vevőkereső algoritmus nem keres az egyéni tulajdonságban. A felhasználók csak akkor használhatják az egyéni tulajdonságokat keresésre, ha az adott tulajdonság hozzá van adva rövidítésként, vagy ha az alapértelmezett keresési algoritmust felülbírálják.

