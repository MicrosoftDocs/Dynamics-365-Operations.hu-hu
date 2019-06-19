---
title: Hűség áttekintése
description: Ez a témakör leírja a hűséggel kapcsolatos képességeket a Microsoft Dynamics 365 for Retail programban és a kapcsolódó beállítási lépéseket, amelyekkel a kereskedők könnyen elindíthatják hűségprogramjukat.
author: scott-tucker
manager: AnnBe
ms.date: 03/08/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
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
ms.openlocfilehash: 94f8cf5b5753c530c42327e251a2102b876c1c8a
ms.sourcegitcommit: e2fb0846fcc6298050a0ec82c302e5eb5254e0b5
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/27/2019
ms.locfileid: "1606872"
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
| 1050 (hűségadatok)           | Futtassa ezt a folyamatot a hűségkonfigurációs adatok Dynamics 365 for Retail programból a kiskereskedelmi üzletbe történő küldésére. Tanácsos lehet ütemezni a művelet végrehajtásához gyakran úgy, hogy a hűséges adatátvitel összes áruházhoz. | Elosztási ütemezés |
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
    
- A kiskereskedők generálhatnak hűségkártyaszámokat a csatornákban. A 2018 októberi frissítés előtt kiskereskedők fizikai hűségkártyákat használhattak vagy bizonyos egyedi vevőadatok, például telefonszám használatával hűségkártyákat generálhattak. Ahhoz, hogy a hűségkártyák generálása engedélyezve legyen kiskereskedelmi kapcsolja be a **Hűségkártyaszám létrehozása** lehetőséget az üzlethez társított funkcióprofilban. Online csatornák esetében a kiskereskedők használható a hűségkártyák kiadásához a vevőknek az IssueLoyaltyCard API-t használhatják. Kiskereskedők vagy megadhatnak hűségkártyaszámot az API-nak a hűségkártya létrehozásához vagy a rendszer a Dynamics 365 for Retail programban beállított hűségkártya-számsorozatot használja. Azonban ha nincs a számsorozat, és a kiskereskedő nem biztosít az API hívása közben a hűségkártyaszámot, egy hibaüzenet jelenik meg.

    ![Hűségkártya létrehozása](./media/Generate%20loyalty%20card.png "Hűségkártyaszám automatikus létrehozása")

- Megszerzett és beváltott hűségpontok most mentve van mindegyik tranzakciónál és értékesítési rendeléshez az értékesítési sorral szemben, hogy ugyanaz az összeg téríthető vissza vagy vehető vissza a teljes vagy részleges visszaküldés esetén. Ezenkívül a pontok láthatósága az értékesítési sor szintjén a hívásközponti felhasználóknak, lehetőséget biztosít azzal kapcsolatos kérések megválaszolására, hogy az egyes sorokhoz kapcsolódóan hány pont került megszerzésre vagy beváltásra. Ezen módosítás előtt hűségpontok mindig újra kiszámításra kerültek visszaküldés esetén, ennek eredménye eltérő összeg volt az eredetihez képest, a ha keresési vagy beváltási szabályok megváltoztak, illetve a hívásközpont felhasználói sem látták a pontok részletezését. A pontok a **Kártyatranzakciók** alatt tekinthetők meg az egyes hűségkártyák képernyőjén. Ahhoz, hogy ezt a funkciót engedélyezze. kapcsolja be a **Hűségpontok feladása értékesítési soronként** konfigurációt a **Megosztott kiskereskedelmi paraméterek** \> **Általános** lapon.

    > [!NOTE]
    > Fokozottan ajénljuk a funkció bekapcsolását annak érdekében, hogy biztosítani lehessen, hogy a megfelelő mennyiségű pont legyen visszatérítve vagy levonva a vevőtől visszaküldés esetén.

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

- A 8.1.3, kiadásban engedélyeztük a „fizetés hűséggel” beállítást a hívásközpont csatornán. A beállítás engedélyezéséhez hozzon létre hűségkártya fizetőeszköz-típust és társítsa a hívásközponttal. 

    > [!NOTE]
    > Mivel a hűségalapú kifizetések mint kártyás fizetésként vannak beállítva, ki kell válasszon egy kártyát a **Kártyabeállítások** oldalon. 

    ![Hűségkártya beállításai](./media/LoyaltyCardSetup.png "Hűségkártya beállításai")

    Ezen beállítást követően a vevők beválthatják hűségpontjaikat a hívásközpontban. Ezenkívül tovább javítjuk az ügyfélélményt a „Hűségpontokkal fedezett összeg” megjelenítésével hogy a hívásközpont felhasználóinak ne kelljen egy másik képernyőre ugorniuk a hűségpontok egyenlegének megtekintéséhez.

- Számos kiskereskedő hűségpontokat csak értékesítési tranzakciók alapján ad, de több ügyfélcentrikus kiskereskedő szeretné, ha bármilyen a márkával kapcsolatos tevékenységért adhatnának pontot. Ha például szeretnék jutalmazni egy online kérdőív kitöltését, üzlet meglátogatását a kereskedő Facebook-oldalának kedvelését, a tweetelést a kereskedővel kapcsolatosan stb. Ehhez a kiskereskedő bármennyi „Más tevékenységtípust” határozhat meg, és ezek a tevékenységekhez a kereseti szabályokat definiálhat. Van továbbá egy Retail Server kitett API "PostNonTransactionalActivityLoyaltyPoints", amely meghívható, ha a tevékenység nem azonosított amely hűségpontokat kellene adjon az ügyfélnek. Ez az API hűségkártya-azonosítót, csatornaazonosítót és egyéb tevékenységazonosító vár, hogy megtalálható legyen a jutalmazandó vevő, és a tevékenységhez tartozó kereseti szabály azonosítható legyen. 

    A nem tranzakciós tevékenységekhez tartozó pontok odaítélésének általában két fő lépése van:

    - Annak meghatározása, hogy olyan tevékenység végrehajtása történt, amelynek jutalmazottnak kell lennie.
    - Jutalmazás a megfelelő pontokkal.

    Az első lépés a Microsoft Dynamics 365 for Retail rendszeren kívül történik, például a márkával kapcsolatos tweet vagy a márka kedvelése a Facebookon. A tevékenységhez felismerését követően a kiskereskedők meghívhatják a fent említett Retail server API-t, és valós időben adhatnak hűségpontokat. Ilyen esetekben nincs szükség ellenőrzési lépésre, mivel tevékenység történt, és a megfelelő pontokat meg kell adni. Vannak azonban oylan esetek, ahol a kiskereskedő szeretne pontok odaítélése előtt a rekordokat áttekinteni. Például a kiskereskedő létrehozott egy workshopot az üzletben, amelyre az ügyfelek feliratkozhatnak az elektronikus kereskedelem webhelyen vagy bármilyen más eseményregisztrációs alkalmazásban. Azonban csak a részvevő vevőknek járnak hűségpontok. Az ilyen esetekhez a 10,0 verzióban bevezettünk egy **Kiskereskedelmi hűség egyéb tevékenységtípus sorok** entitást. Az adatentitás lehetővé teszi, hogy a kiskereskedő használja adatok importálására/exportálására szolgáló keretrendszert (DIXF) vagy az OData API-t, így rögzítheti a tevékenységet, amelyek után a vevők hűségpontokat kell kapjanak. Az adatentitás a tevékenységeket a **Hűségsorok egyéb tevékenységekhez** nevű naplóban tárolja, amely ellenőrzési és módosítási célokra használható. Az adatok ellenőrzését követően az informatikai felhasználó manuálisan feladhatja tevékenység sorokat vagy futtathatja a **Más tevékenységtípus hűségsorok feldolgozása** nevű feladatot, amely feladja az összes fel nem adott tevékenységsort és megadja a pontokat az ügyfeleknek a kereseti szabályok alapján. A fenti esetben az eseményregisztrációs alkalmazás meghívta OData API-t a vevői adatok küldéséhez a Dynamics 365 for Retail rendszerbe. Informatikai felhasználó azonban csak azon vevőkhöz tehet közzé tevékenységsorokat, akik részt vettek a workshopon, és törölheti a tevékenységsorokat más ügyfelektől. 

    > [!NOTE]
    > Jelenleg a rendszer megköveteli a felhasználóktól, hogy állítsanak be egy számsorozatot az "egyéb tevékenységtípusokhoz", de ez nem lesz szükséges lépés a jövőbeli kiadásokban. Számsorozat beállításához kattintson a **Megosztott kiskereskedelmi paraméterek** \> **Számsorozatok** lehetőségre, és válasszon ki egy számsorozatot a **Hűséghez kapcsolódó egyéb tevékenységtípus azonosítója** elemhez.

- Jó ügyfélszolgálat és a vevők kérdéseinek hatékony megoldásához fontos,hogy a pénztárosok hozzáférjenek a teljes ügyfélprofilhoz. A 10.0 kiadásában és a kapcsolódó hűségkártya programot és a hűségkártya-előzmények részletei láthatók lesznek a POS-ben a pénztárosok számára.
- Ingyenes vagy kedvezményes szállítás egyike az online vásárlásra motiváló tényezőknek. Ahhoz, hogy a szállítás promóciók beállítását tegyük lehetővé a kiskereskedők számára, a 10.0 kiadásban egy új promóciótípust vezetünk be, amelynek neve „Szállítási küszöbérték kedvezmény” ahol a kereskedő meghatározhat küszöbértékeket, melyek teljesülése esetén az ügyfél jogosulttá válik kedvezményes vagy ingyenes szállításra. Ha például költsön 35 dollárt ingyenes „két napos szállításért” vagy „ingyenes két napos szállítás” minden hűségkártyás ügyfél számára. Ez a funkció az új Speciális automatikus költségek képességre épül. Tekintse át a [Speciális automatikus költségek dokumentációját](https://docs.microsoft.com/dynamics365/unified-operations/retail/omni-auto-charges). Ezeket a speciális automatikus költségeket engedélyezni kell a szállítási promóció működéséhez. Ezeket a **Vevői rendelések** lapon a **Kiskereskedelmi paraméterek** oldalon engedélyezhetők, és kapcsolja be a "Speciális automatikus díjak használata" konfigurációt. Mindemellett, mivel a kiskereskedő többféle díjat állíthat be, például a kezelési vagy a telepítési díjakat, a kiskereskedő meg kell adja hogy melyik költség minősül a szállítási költségnek. A szállítási engedmények csak a szállítási költségekre lesznek alkalmazva. Egy díj megadásához szállítási költségként menjen a **Költségkódok** képernyőre a **Kiskereskedelem** \> **Kiskereskedelmi informatika** \> **Csatorna beállítása** \> **Költségek** helyen és kapcsolja be a „Szállítási költség” jelölőnégyzetet a kívánt költségekhez. Most megnyithatja a **Kiskereskedelmi szállítási küszöbérték szerinti engedmény** képernyőt, és beállíthatja az engedményt.

    A termékengedményekhez hasonlóan ez az engedmény tiszteletben tartja az összes meglévő szokásos engedményképességet így ezek az engedmények korlátozhatók csak az utalványokra, így csak a utalványok rendelkező vevőket illetik meg ezek az engedmények. Ezek az engedmények támaszkodnak az Árcsoportok képességre az ilyen engedményekre való jogosultságának meghatározásához. Például a kiskereskedő kiválaszthatja, hogy csak az online csatornákon futtatja ezeket a promóciókat, és/vagy csak bizonyos ügyfélcsatornákon keresztül, például hűségkártyás vevők esetében. Miután a rendelési sorokat a megadott szállítási móddal elérik a megállapított küszöbértéket, akkor a szállítási engedmény alkalmazva lesz, és csökkenti a szállítási díjat, az engedmény beállítása alapján. 

    > [!NOTE]
    > Egyéb időszakos kedvezményekkel, például a mennyiségi, egyszerű, kombinációs küszöbérzék kedvezményekkel szemben a szállítási engedmény nem hoz létre engedménysorokat, a szállítási díjat hozzáfűzi a a költség leírásához.
