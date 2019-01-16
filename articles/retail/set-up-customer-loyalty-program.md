---
title: "Hűség áttekintése"
description: "Ez a témakör leírja a hűséggel kapcsolatos képességeket a Microsoft Dynamics 365 for Retail programban és a kapcsolódó beállítási lépéseket, amelyekkel a kereskedők könnyen elindíthatják hűségprogramjukat."
author: scott-tucker
manager: AnnBe
ms.date: 10/24/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailLoyaltyPrograms, RetailPriceDiscGroup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 16201
ms.assetid: f79559d2-bc2d-4f0b-a938-e7a61524ed80
ms.search.region: global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 190d0b59ad2e232b33b3c0d1700cbaf95c45aeca
ms.openlocfilehash: 09d4e46694e89b648981352f64da4a43ab1522e1
ms.contentlocale: hu-hu
ms.lasthandoff: 01/04/2019

---

# <a name="loyalty-overview"></a>Hűség áttekintése

[!include [banner](includes/banner.md)]

A hűségprogramok segíthetnek a vevő hűségének növelésében azáltal, hogy megjutalmazzák a vevőket, ha kapcsolatba lépnek a kereskedő márkájával. A Microsoft Dynamics 365 for Retail programban be lehet állítani olyan egyszerű vagy összetett hűségprogramokat, melyek jogi személyi státusszal rendelkező bármilyen kiskereskedelmi csatornára alkalmazhatók. Ez a témakör leírja a hűséggel kapcsolatos képességeket a Microsoft Dynamics 365 for Retail programban és a kapcsolódó beállítási lépéseket, amelyekkel a kereskedők könnyen elindíthatják hűségprogramjukat.

A hűségprogram beállíthatja, hogy a következőket tartalmazza:

- Állítsa be annak a jutalomnak a típusát, amit hűségprogramjaiban használ és kövesse nyomon a részvételt a hűségprogramban.
- A hűségprogramokat úgy állítsa be, hogy azok a különböző Ön által ajánlott jutalomösztönzőket megfelelően képviseljék. Hűségprogram-szinteket adhat meg, hogy nagyobb ösztönzést és jutalmat nyújthasson azoknak az ügyfeleknek, akik gyakrabban vásárolnak vagy több pénzt költenek üzleteiben.
- Adjon meg jogosultsági szabályokat azon tevékenységek megadásához, melyeket az ügyfélnek teljesítenie kell ahhoz, hogy jogosulttá váljon a jutalomra. Megadhat beváltási szabályokat is annak meghatározása céljából, hogy mikor és hogyan válthat be az ügyfél jutalmat.
- Bármely hűségprogramjaiban részt vevő kiskereskedelmi csatornából kibocsáthat hűségkártyát, majd társítsa a hűségkártyát egy vagy több olyan hűségprogramhoz, melyben az ügyfél részt vehet. Vevőrekordot is csatolhat hűségkártyához, ezáltal lehetővé téve az ügyfélnek, hogy több kártyán gyűjthesse hűségpontjait és beválthassa azokat.
- Manuálisan rendezze a hűségkártyákat vagy vigye át a hűségpontegyenleget egyik kártyáról a másikra ügyfél befogadása vagy jutalmazására céljából.

## <a name="setting-up-loyalty-programs"></a>Hűségprogramok beállítása

Néhány összetevőt be kell állítania ahhoz, hogy a Dynamics 365 for Retail hűségprogram funkcióját engedélyezhesse. A következő ábra bemutatja a hűségprogram összetevőit és azok egymással való kapcsolódását.

![Hűség beállítási folyamata](./media/loyaltyprocess.gif "A Hűség komponensei és azok kapcsolata egymással")

## <a name="loyalty-components"></a>Hűségelemek beállítása

A következő táblázat minden egyes összetevőt és azok hűségkártyarendszerben használt helyét ismerteti.

| Összetevő                                        | Leírás | Ahol használható |
|--------------------------------------------------|-------------|-----------------|
| Kedvezmények beállítása (előfeltétel)                  | Állítsa be a hűséges vevőknek kínált kedvezményeket. Például: minden ruházati termékből 5 százalék kedvezmény. | A kedvezményeket hozzá kell adni az árcsoportokhoz, hogy a hűségprogramba bekerüljenek. Az árcsoportok hűségprogramokhoz és hűségszintekhez vannak hozzárendelve. |
| Árcsoportok beállítása (előfeltétel)               | Az árcsoportok kiskereskedelmi termékek árainak és engedményeinek létrehozására és kezelésére használhatók. Úgy állítsa be árcsoportjait, hogy azok tartalmazzák azokat a kedvezményeket, melyek hűségprogramjaiban érvényesek. | Az árcsoportok hűségprogramjaihoz és hűségszintjeihez vannak hozzárendelve. |
| Csatornák beállítása (előfeltétel)                   | A kiskereskedelmi csatornák a hűségprogramokban részt vevő üzletek, így lehetnek például valódi boltok, online áruházak vagy telefonos ügyfélszolgálatok is. Be kell állítania kiskereskedelmi csatornáit, mielőtt hűségprogramokat rendelne hozzájuk. | Kiskereskedelmi csatornát akkor rendel hozzá egy hűségprogramhoz, ha a kiskereskedelmi csatorna részt vesz a hűségprogramban. |
| Hűségprogram fizetési módjának beállítása (előfeltétel) | A hűségkártyák pénztárban való használata és a hűségpontok hűségprogramban való beváltása előtt be kell állítania egy fizetési módot a programhoz. A hűségprogram fizetési módját is hozzá kell adnia a kiskereskedelmi csatornához, hogy a vásárlók be tudják váltani hűségpontjaikat termékvásárlásra. | Állítsa be a hűségprogram típusának fizetési módját, ezután rendelje hozzá a hűségprogram fizetési módját a hűségprogramban részt vevő kiskereskedelmi csatornákhoz. |
| Időszakok beállítása                            | A dátumintervallumokkal rugalmasan beállíthatja azt az időszakot, amelyre a hűségszintek vonatkoznak. Dátumintervallumok segítségével megadhatja, hogy a mennyi vevő maradhat, egy réteg vagy az ügyfél mennyi időt van ahhoz, hogy a réteg egy tevékenység teljesítéséhez. | A dátumintervallumok csak akkor alkalmazhatók, ha hűségprogramjában szinteket használ. Kiválasztja a programszintekre vonatkozó időszakot, valamint a programszintszabályokra vonatkozó időszakot is. |
| Hűségpontok beállítása                             | A hűségpontok olyan típusú jutalmat jelentenek, amelyet vevőinek kíván nyújtani. A hűségpontok lehetnek beválthatók vagy nem beválthatók. A beváltható hűségpontok termékekre válthatók. A nem beváltható hűségpontok vagy nyomon követési célokra szolgálnak, vagy a vevő ezzel juthat tovább a hűségprogram következő szintjére. | A hűségpontokra a szintszabályozás hivatkozik, és azt a célt szolgálják, hogy a vevőt egy adott szintre eljuttassák. A hűségpontokra a hűségprogramok jogosultsági és beváltási szabályrendszere is hivatkozik. A jogosultsági szabályrendszerben megadja, hogy egy vevő milyen jutalmat kaphat egy bizonyos tevékenységért. A beváltási szabályrendszerben megadja, hogy a vevő milyen jutalmat válthat be. |
| Hűségprogramok beállítása                          | A hűségprogramok képezik a különböző felajánlható hűséglehetőségek magvát. Minden egyes hűségprogramhoz nullától számos lépcsőig terjedő hűségszint rendelhető hozzá. A kedvezmények, árcsoportok vagy a program szintjén vagy a hűségszint szintjén vannak hozzárendelve a hűségprogramokhoz. | Hűségprogramjaihoz hűségterveket rendel hozzá. Hűségprogramjaihoz hűségkártyákat rendel hozzá, a hűségkártyák pedig vevőkhöz rendelhetők hozzá. A kiskereskedelmi csatornák a hűségtervekhez rendelt hűségprogramokban vesznek részt. Bármely, hűségkártyával rendelkező vevő részt vehet olyan hűségprogramokban, amelyek hozzá vannak rendelve a kártyához. |
| Hűségszintek és szintszabályok beállítása              | A hűségszintek olyan választható szintek, melyeket hűségprogramjaihoz adhat meg. Minden, hűségprogramban részt vevő ügyfél részére beállíthat alapkedvezményt és jutalmat, valamint további kedvezményeket és jutalmakat is beállíthat olyan ügyfeleknek, akik már jogosulttá váltak a program különböző szintjeire. Minden egyes hűségszintre állíthat be olyan szabályokat, amelyek teljesülése esetén a vevő jogosulttá válik az adott szintre. Megadhatja, hogy a vevő mennyi ideig maradhat az adott szinten azt követően, hogy elérte azt. | A hűségszintek és a hűségszint-szabályrendszerek a hűségprogramokban kerülnek meghatározásra. Ha nem hoz létre hűségszintet, minden, a hűségprogramban részt vevő jogosulttá válik arra a kedvezményre, amelyet a hűségprogram árcsoportjában adott meg. Ha meghatároz hűségszinteket, akkor felállíthatja a hűségprogram hűségszintjeinek jogosultsági és beváltási szabályait is. |
| Hűségprogramok beállítása                           | A hűségtervek meghatározzák a kiválasztott hűségprogramokra vonatkozó jogosultsági és beváltási szabályokat. A hűségtervhez kiskereskedelmi csatornákat társít annak céljából, hogy megadhassa, mely hűségprogram, jogosultsági vagy beváltási szabály vonatkozik mely kiskereskedelmi üzletre. | A hűségterv a hűségprogramhoz és a kiskereskedelmi csatornákhoz kerül hozzárendelésre. Több hűségtervet rendelhet ugyanahhoz a hűségprogramhoz, és több hűségtervet rendelhet több kiskereskedelmi csatornához. |
| Hűségkártyák beállítása                             | A hűségkártya felhatalmazza birtokosát arra, hogy részt vegyen olyan hűségprogramokban, amelyek hozzá vannak rendelve a kártyához. A hűségkártyák kiállíthatók névtelenül, vagy hozzárendelhetők egy adott vevőhöz. Megtekintheti az egy adott kártyához tartozó hűségtranzakciókat, továbbá megtekintheti a kártyán már felhalmozott hűségpontok kimutatását is. Minden kiskereskedelmi csatornából bocsáthat ki hűségkártyát. A hűségkártya kézi beállítására is van lehetőség egy vevő másik szinthez történő rendelése, hűségpontok hozzáadása vagy hűségkártya pontegyenlegének másik kártyára történő átvitele céljából. | Hűségprogramokat rendel hűségkártyához. |

## <a name="loyalty-processes"></a>Hűségprogram-folyamatok

A következő táblázat leírja a folyamatok, amelyeket el kell végezni a hűséges konfigurációk és adatokat küldhet az üzletekben és a Hűségkártyás tranzakciók listájának lekérése az üzletben.

| Feldolgozás neve                         | Leírás | Lapnév |
|--------------------------------------|-------------|-----------|
| 1050 (hűségadatok)           | Futtassa ezt a folyamatot a hűségkonfigurációs adatok Microsoft Dynamics 365 for Retail programból a kiskereskedelmi üzletbe történő küldésére. Tanácsos lehet ütemezni a művelet végrehajtásához gyakran úgy, hogy a hűséges adatátvitel összes áruházhoz. | Elosztási ütemezés |
| Hűségprogramok feldolgozása              | Futtassa ezt a folyamatot a hűségtervek hozzájuk tartozó kiskereskedelmi adatokkal való társításához. Ezt a folyamatot kötegelt folyamatként való ütemezéssel lehet futtatni. Ha módosítja a hűséges konfigurációs adatok, például a hűségprogramok hűségprogramok és a hűségpontok futtatnia kell ezt a folyamatot. | Hűségprogramok feldolgozása |
| Offline hűségtranzakciók feldolgozása | Futtassa ezt a folyamatot a hűségkártyák kapcsolat nélküli feldolgozott tranzakciókat is tartalmazó frissítéséhez. Ezt az eljárást csak akkor kell alkalmazni, ha az **Offline pontszerzés** jelölőnégyzet be van jelölve a **Megosztott kiskereskedelmi paraméterek** oldalon, így offline is lehet jutalompontokat szerezni. | Offline hűségtranzakciók feldolgozása |
| Hűségkártyarétegek frissítése            | Futtassa ezt a folyamatot a vevő jogosultsági szintjének a hűségprogram szintszabályai ellenében történő értékeléséhez és a vevő szintállapotának frissítéséhez. Erre a folyamatra csak akkor van szükség, ha módosítja a hűségprogramok szintszabályait és a frissített szabályokat a már kibocsátott hűségkártyákra visszamenőlegesen kívánja alkalmazni. Ezt a folyamatot kötegelt folyamatként vagy egyes kártyákra futtatható. | Hűségkártyarétegek frissítése |

## <a name="loyalty-enhancements"></a>Hűség fejlesztései

A Retail új hűség funkcióval rendelkezik a 2018 októberi kiadás részeként. Az új fejlesztéseket mindegyikének magyarázata az alábbiakban található.

- A korábbi kiadásokban a hűségprogram részeként kiskereskedők szerinti különböző kereseti és beváltási szabályokat hozhattak létre szintek szerint, hogy eltérően jutalmazzák a különböző szintű ügyfeleket. A kiskereskedők mostantól használhatják a „fiókok” funkciót a kereseti és beváltási szabályok részeként, így bizonyos vevőcsoportok tartozhatnak egy szinthez, mégis eltérő jutalmazásban részesülhetnek. Így nem szükséges további szintek létrehozása.
    
    > [!NOTE]
    > A hűségprogram belül a kereseti szabályok kiegészítő jellegűek. Például ha olyan szabályt hoz létre, amely szerint az arany szintű tagok minden egyes amerikai dollár után 10 pontot kapnak, és létrehoz egy szabályt, amely szerint a „veterán” fiók 5 pont jutalomban részesül minden egyes amerikai dollár, egy veterán, aki tagja is arany szintnek is 15 pontot pontot kap egy dollár után, mivel a vevő mindkét sorra jogosult.. Azonban ha veterán vevő nem volt arany szint tagja, akkor 5 pontot kapna minden egyes dollár után. A csatornák változásainak érvényesítéséhez, futtassa a **Hűségprogramok feldolgozása** és az **1050** (hűségadatok) feladatokat.
    
    ![Kereset fiók alapján](./media/Affiliation%20based%20earning.png "Keresetek fiók alapján")

- A kiskereskedők sokszor speciális árakat alkalmaznak vevők adott csoportja számára, akikre nem szeretnék alkalmazni a hűségprogramot. Például nagykereskedők vagy munkavállalók, akik speciális árképzésben részesülnek, de hűségpontokat nem kapnak. Gyakran a „fiókok” szolgálnak arra, hogy az ilyen vevőcsoportok speciális árképzésben részesüljenek. Bizonyos vevőcsoportok kizárásához a hűségpontok megkereséséből a kiskereskedő egy vagy több fiókot is megadhat a hűségprogram **Kizárt fiókok** részében. Ezzel a módszerrel kizárt fiókokhoz tartozó vevők már meglévő hűséges tagok, így nem kapnak hűségpontokat a vásárlásaik után. A csatornák változásainak érvényesítéséhez, futtassa a **Hűségprogramok feldolgozása** és az **1050** (hűségadatok) feladatokat.

    ![Kizárt fiókok](./media/Excluded%20affiliations.png "Fiókok kizárása hűségpontok szerzéséből")
    
- A kiskereskedők generálhatnak hűségkártyaszámokat a csatornákban. A 2018 októberi frissítés előtt kiskereskedők fizikai hűségkártyákat használhattak vagy bizonyos egyedi vevőadatok, például telefonszám használatával hűségkártyákat generálhattak. Ahhoz, hogy a hűségkártyák generálása engedélyezve legyen kiskereskedelmi kapcsolja be a **Hűségkártyaszám létrehozása** lehetőséget az üzlethez társított funkcióprofilban. Online csatornák esetében a kiskereskedők használható a hűségkártyák kiadásához a vevőknek az IssueLoyaltyCard API-t használhatják. Kiskereskedők vagy megadhatnak hűségkártyaszámot az API-nak a hűségkártya létrehozásához vagy a rendszer a Dynamics 365 for Retailben beállított hűségkártya-számsorozatot használja. Azonban ha nincs a számsorozat, és a kiskereskedő nem biztosít az API hívása közben a hűségkártyaszámot, egy hibaüzenet jelenik meg.

    ![Hűségkártya létrehozása](./media/Generate%20loyalty%20card.png "Hűségkártyaszám automatikus létrehozása")

- Megszerzett és beváltott hűségpontok most mentve van mindegyik tranzakciónál és értékesítési rendeléshez az értékesítési sorral szemben, hogy ugyanaz az összeg téríthető vissza vagy vehető vissza a teljes vagy részleges visszaküldés esetén. Ezenkívül a pontok láthatósága az értékesítési sor szintjén a hívásközponti felhasználóknak, lehetőséget biztosít azzal kapcsolatos kérések megválaszolására, hogy az egyes sorokhoz kapcsolódóan hány pont került megszerzésre vagy beváltásra. Ezen módosítás előtt hűségpontok mindig újra kiszámításra kerültek visszaküldés esetén, ennek eredménye eltérő összeg volt az eredetihez képest, a ha keresési vagy beváltási szabályok megváltoztak, illetve a hívásközpont felhasználói sem látták a pontok részletezését. A pontok a **Kártyatranzakciók** alatt tekinthetők meg az egyes hűségkártyák képernyőjén.    
- Az kereskedők minden egyes jutalomponthoz meghatározhatnak átruházási időszakot. Az átruházási időszak meghatározz az időszakot a megszerzett dátumtól kezdve, amely után a hűségpontok a vevők számára rendelkezésre állnak. A nem átruházott pontok a **Nem átruházott** pontok oszlopában tekintheti meg a **Hűségkártyák** oldalon. Ezenkívül kiskereskedők meghatározhatnak maximális hűségesprogram jutalompont határértéket hűségkártyánként. Ez a mező használatával lehet a hűségesprogram-csalások hatását csökkenteni. Ha elérte a maximális jutalom pontokat, a felhasználó nem szerezhet több pontot. A kereskedő dönthet úgy, hogy az ilyen kártyákat mindaddig letiltja, amíg a potenciális csalást kiviszgálják. Ha kiskereskedő csalást állapít meg, a kiskereskedő nem csak a blokkolhatja a hűségkártyát a vevő számára, de meg is jelölheti a vevőt zároltként. Ehhez állítsa a **Vevő letiltása hűségprogramba való regisztráció esetén** tulajdonságot **Igen** értékre a **Minden vevő** alatt a **Kiskereskedelem** gyorslapon. A zárolt vevők nem kaphatnak hűségkártyát bármelyik csatornán keresztül sem.

    ![Hűségpontok átruházása és a maximális megszerzett pont](./media/Vesting%20and%20maximum%20reward%20points.png "Az átruházás és maximális hűségpontok meghatározása")

- A fiókok használhatók speciális árképzés és engedmények nyújtására, de van néhány fiókok, amelyeket a kiskereskedők nem szeretnék, hogy ügyfeleik lássanak. Például a „Sokat költő vásárló” fiókot előfordulhat, hogy nem fogadnának jól bizonyos vevők. Ezenkívül vannak fiókokok, amelyeket nem kezelnhetnek az az üzletnek, például az alkalmazottak, mert nem szeretné, hogy a pénztárosok eldönthessék, hogy ki alkalmazott, így alkalmazotti alapú engedményeket adjanak. A kiskereskedők most kiválaszthatják a fiókokat, amelyeket el kell rejteni a kiskereskedelmi csatornákon. Az **Elrejtés a csatornákban** módon megjelölt fiókokat nem lehet megtekinteni, hozzáadni vagy eltávolítani a pénztárban. Azonban a fiókhoz társított árképzés és engedmények továbbra is alkalmazva lesznek a termékekre.

    ![Fiókok elrejtése](./media/Hide%20affiliations.png "Fiókok elrejtése a csatornákban")
    
- A Hívásközpont felhasználók mostantól több könnyen megkereshetnek ügyfeleket a hűségkártya-adatok használatával, és megkereshetik a vevő, hűségkártya és hűségkártya kártya tranzakciók lapjait a **Ügyfélszolgálat** oldalon.

    ![Ügyfélszolgálat](./media/Customer%20service.png "Hűségadatok keresése a vevőhöz")
    
- A hűségkártya sérülése esetén cserekártya kell hozható létre, és a meglévő pontok átvihetők az új kártyára. Ebben a verzióban a cserekártya-folyamat egyszerűbbé vált. Mindemellett a vásárlók elajándékozhatják hűségpontjaikat vagy azok egy részét barátaiknak és családjuknak Pontok átmozgatáskor pontkiigazítási bejegyzések készülnek minden hűségkártyához. A cserekártya és egyenlegátvitel funkciók a **Hűségkártyák** oldalon érhetők el.

    ![Csere és pontok átvitele](./media/Replace%20and%20transfer%20points.png "Hűségkártya cseréje vagy egyenleg átvitele")
    
- Előfordulhat, hogy a kiskereskedők szeretnék rögzíteni egy adott csatorna hatékonyságát hogy egy hűségprogramba vegyenek fel vásárlókat. A hűségkártyák belépési forrása mostantól tárolva van, így a kiskereskedők jelentéseket futtathatnak ezeken az adatokon. A jogosultságok forrás automatikusan rögzítve van az összes a kiadott hűségkártyához a MPOS/CPOS vagy elektronikus kereskedelmi csatornákból. A back-office alkalmazásból kiadott hűségkártyák esetében a hívásközpont kiválaszthatja a megfelelő csatornát.
- A korábbi kiadásokban kiskereskedők az MPOS/CPOS rendszert használhatták a hűségpontok beváltásához a vevők számára az üzletben. Azonban azon kiadásokban a hűségpontok egyenlege hűségpontokban jelenik meg, így a pénztáros sikerült nem tekinthette meg a pénznemérték összegét, amely az aktuális tranzakció felé alkalmazható. A pénztáros a pontokat át kellett váltsa pénznembe mielőtt lehetséges lett volna a fizetés hűségpontokban. A jelenlegi verzióban sorok hozzáadása után a tranzakcióhoz a pénztáros láthatja, hogy mekkora összeget fedeznek a hűségpontok a jelenlegi tranzakcióból amely megkönnyíti hűségpontok vagy azok egy részének beváltását a tranzakcióhoz. Ezenkívül a pénztáros megtekintheti a következő 30 napban lejáró pontokat, így felülértékesítésre vagy keresztértékesítésre van lehetősége, hogy a vásárló elköltse a pontokat a tranzakció során..

    ![Hűségpontokkal fedezett összeg](./media/Points%20covered%20by%20loyalty%20balance.png "Hűségpontokkal fedezett összeg megjelenítése")

    ![Lejáró pontok](./media/Expiring%20points.png "Lejáró pontok megtekintése")
    
## <a name="upcoming-enhancements"></a>Várható fejlesztések

A következő funkciókra lesznek elérhetők a Dynamics 365 for Retail későbbi havi frissítéseiben.
    
- Vevők szeretnék megtekinteni hűségegyenlegük részleteit az ügyféllel találkozó csatornákon. Ehhez hasonlóan fontos a pénztárosok a vevő hűségpontokkal kapcsolatos előzményeinek megtekintése az MPOS/CPOS rendszerben, hogy gyorsan válaszolhassanak a vevők kérdéseire. Egy később érkező havi kiadásban a vevők és a pénztárosok megtekinthetik majd a hűségkártya-előzmények részleteit.
- Számos kiskereskedő hűségpontokat csak értékesítési tranzakciók alapján adhat, de több ügyfélcentrikus kiskereskedő szeretné, ha bármilyen a márkával kapcsolatos tevékenységért adhatnának pontot. Ha például szeretnék jutalmazni egy online kérdőív kitöltését, üzlet meglátogatását a kereskedő Facebook-oldalának kedvelését, a tweetelést a kereskedővel kapcsolatosan stb. A jövőben lehetőséget biztosítunk arra, hogy minden vevői tevékenység után lehessen hűségpontot adni. Ehhez a kiskereskedő "Más tevékenységtípust" határozhat meg, és ezek a tevékenységekhez a kereseti szabályokat definiálhat. Megjelenítünk egy Retail Server API-t, amely egy tevékenység azonosítása esetén meghívható, amelyek segítségével a kereseti szabályt használva adja meg a szükséges hűségpontokat.
- Ahhoz, hogy a valódi többcsatornás kiskereskedelmi élményt nyújthassanak, lehetővé tesszük a hűségpontok megszerzését beváltását minden csatorna között.
- Ingyenes vagy kedvezményes szállítás egyike az online vásárlásra motiváló tényezőknek. Ahhoz, hogy a szállítás promóciók beállítását tegyük lehetővé a kiskereskedők számára, egy új promóciótípust vezetünk be, ahol a kereskedő meghatározhat küszöbértékeket, melyek teljesülése esetén az ügyfél jogosulttá válik kedvezményes vagy ingyenes szállításra.

