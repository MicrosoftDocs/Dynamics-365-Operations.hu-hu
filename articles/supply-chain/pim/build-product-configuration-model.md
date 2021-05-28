---
title: Termékkonfiguráció áttekintése
description: A speciális követelmények kielégítése érdekében a termék konfigurálásához szükséges egyre helyett a vállalkozások-, mind az egyéni üzleti kapcsolatok, a kivétel a szabály.
author: cvocph
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PCProductConfigurationModelDetails, ConfigPartOf
audience: Application User
ms.reviewer: kamaybac
ms.custom: 75083
ms.assetid: f08072b8-cb0b-43aa-9509-f5ec32caecd9
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7d37b1c8ed23bf93f0480c76e10b8aaed86fe2a2
ms.sourcegitcommit: 51cad1ce3ed44ebf7eb9bdf553ee2df4c1f03135
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/10/2021
ms.locfileid: "6015977"
---
# <a name="product-configuration-overview"></a>Termékkonfiguráció áttekintése

[!include [banner](../includes/banner.md)]

A speciális követelmények kielégítése érdekében a termék konfigurálásához szükséges egyre helyett a vállalkozások-, mind az egyéni üzleti kapcsolatok, a kivétel a szabály.

Egy gyártó vállalat, amely konfigurálása rendelésre helyzet kezelésére alkalmas van általában gondosan nagyobb ügyfelek igényeinek lehetőséget. Ezenkívül rakodási késztermékek helyett általános összetevők formájában félkész termék, a gyártó csökkentheti a kapcsolt tőke a készletbe.  

Egy rendelésre beállítása-beállítást a raktárra gyártás beállításaiból sikeres áthelyezési szükséges a termékszerkezetek gondos elemzésének, termék családjai és componentization azonosítása. Részek számának csökkentésével lehetséges, és a folyamatban lévő áruk a lehető legkevesebb, nagyon fontos a termék interfészek tudomásul, és ő tervezi újrahasznosításának tartozó.  

Nincsenek több termék konfigurációs modellezési elvek, például a dimenzión alapuló szabály alapú, és a megszorításon alapuló modellezési. Tanulmányok a megszorításon alapuló módszerre egyéb modellezési elvek összehasonlítva körülbelül 50%-kal csökkentheti modellek kód sorok számának megjelenítése. Ezért ez a módszer csökkentheti a tulajdonosi (TCO) teljes költségét. Az X++ kódon alapuló szabályalapú modellről a megszorításokon alapuló modellre való átéréssel már nincs szüksége fejlesztői licencre a termékmodellek karbantartásához.

## <a name="product-configuration"></a>Termékkonfiguráció

A iparosítási időszak árú kiváló minőségű és a szolgáltatás-multimédiás termékek előállításában nagy teljesítmények vezetett. A nagyságrendi teszik lehetővé beszerezni autók, televízió, háztartási és egyéb áruk, hogy többsége figyelembe kell venni a mindennapi élettartam fontos szerepet a iparosodott világ legtöbb felhasználó számára.  

Számos termék váltak árucikkek, mint a fordult elő kell megkülönböztetni őket. A gyártók azonnali választ, ez a kérdés az egyes termékekhez változatainak létrehozására került, hogy vevők több alternatíva. A stratégia illetéktelenek előrejelzési kihívásokra és Készletköltség és eladatlan termékek elavuljanak amiatt növekedését vezetett.  

A rendelésre konfigurálása szemléletmódot elfogadásával gyárt lehetőségük közben csökkentése vagy megszüntetése elavult készletcikkek egyedi termékek vevői igény kielégítése érdekében. A raktárra gyártási szemléletmódot úgy lehet egy rendelésre konfigurálása szemléletmódot, egy azonnali kérdés merül fel, hogy esetén rövid átfutási idők szükségességét képest alacsony készletszintek kell egyenlíteni.  

Itt a sikeres kulcsa gondosan elemezheti a termék portfólió, és keresse meg a szolgáltatások és a folyamatok szokásokat. Az célja, hogy ugyanazzal a műszerrel által előállított, és minden változatának használt általános összetevők azonosítása.  

A termékkonfigurációs szolgáltatáskészlet tartalmaz a felhasználói felület a termékmodell szerkezetéhez konfigurációs, és azokat is, amelynek nem fordítható deklaratív megszorítás szintaxist áttekintését nyújtó. Ezért vállalatokat, amelyeket szeretne egy konfigurációs gyakorlat támogatást megkezdéséhez könnyebben. Az alábbi szakaszok leírják, mint egy terméktervező már nem szükséges az egy termékkonfigurációs modell összeállítása, tesztelni és azt az értékesítési szervezet kiadás fejlesztő támogatásához.

## <a name="building-a-product-configuration-model"></a>Termékkonfigurációs modell építése

Nincsenek több olyan módon, hogy egy felhasználó hajthatja végre egy termékkonfigurációs modell létrehozásához. Egy lehetőség egy szekvenciális folyamat kövesse először az összes a hivatkozási adatok létrehozása, például alaptermékek egyedi termékek és üzemi erőforrások, és ezután összetevők, az anyagjegyzék (AJ) sorai, az útvonalműveletek és más elemeket, a termékkonfigurációs modell együtt. Azt is megteheti választani lehet a több ismétlődő megközelítés először létrehoz a modell és a hivatkozási adatok szükség szerint.

### <a name="components"></a>Összetevők

A termékkonfigurációs modell egy vagy több összetevő keresztül alösszetevő kapcsolatokkal együtt kötött áll. Összetevők egyszer határozzák meg, és fel lehet használni többször szereplő egy vagy több termékkonfigurációs modellek. Az összetevők a termékkonfigurációs modell fő épület mennyiségű, és szinte az összes modellel kapcsolatos információk megtekintése a kapcsolódó őket.

### <a name="attributes"></a>Attribútumok

Minden egyes összetevő rendelkezik egy vagy több attribútum, amelyek azonosítják annak tulajdonságait. Ezek a következők milyen felhasználók fogja választani a konfigurálás során. Attribútumok közötti összetevők, mind a belüli összetevő kapcsolatok megszorítások vagy számítások keresztül szabályozhatja. Anyagjegyzéksorok alkalmazott feltételek keresztül az attribútumok áll a konfigurált termék fizikai részeket meghatározására használható. Attribútum ezenkívül az AJ-sor tulajdonságának leképezés mechanizmusa keresztül szabályozhatja. Hasonló funkciót tartalmaz, az útvonalműveletek vonatkozó belefoglalási és a tulajdonság beállításait.

>[!NOTE]
> Az attribútumtípusok létrehozásakor ne hozzon létre magas számú értéket az attribútumtípus tartományhoz. Ez lassulást okozhat termékkonfigurátorban.

### <a name="expression-constraints"></a>Kifejezésmegszorítás

A megszorításon alapuló termékkonfigurációs modell használatát, az azt jelenti, hogy korlátozások léteznek, amikor a felhasználó kiválasztja a különböző attribútumok értékeit. Ilyen korlátozások kifejezés megszorítások, a nyelvet OML (optimalizálási modellező) használatával is megvalósíthatók. Másik lehetőségként korlátozás táblamegszorítás formájában is megvalósíthatók.

### <a name="table-constraints"></a>Táblamegszorítások

A táblázatok megszorításai felhasználó által definiáltak vagy rendszer definiáltak is lehetnek.  

A felhasználó által a felhasználó által definiált táblamegszorítás épül fel. A felhasználó választja ki, amely megadja annak a táblának az oszlopok Attribútumtípusok kombinációja, és ezután beírja az értékeket a tartományok, a kijelölt attribútum típusú alakítson ki a sorokat a táblamegszorításban.  

Rendszer által definiált táblamegszorítás referenciaként használandó tábla kiválasztása, és kiválasztja az ebből a táblából alakítson ki az oszlopokat a megszorításban szereplő mezők határozzák meg. A táblamegszorítás sorai a Supply Chain Management tábla a sorokat, amelyek a jelenlegi konfiguráció időpontban.  

Táblamegszorítás egy termékkonfigurációs modell a Táblamegszorítás oszlopai hivatkozásoknak a táblamegszorítás definíciójának és a modellben a megfelelő attribútumokat tartalmazza.

### <a name="calculations"></a>Számítások

Számítások felelnek meg az egy termékkonfigurációs modell aritmetikai műveletek végrehajtására szolgáló eljárás. Számítás meghatározható, például egy meghatározott adatra nyersanyag vagy csiszoló művelet feldolgozási idő hosszát. Számítások elengedhetetlenek, és minden után elérhetővé válik a számítási kifejezésben szereplő termékattribútum-értékeinek a célattribútum értékének beállítása.

### <a name="subcomponents"></a>Részösszetevők

A részösszetevők a termékkonfigurációs modell fastruktúráját tükrözik. Minden egyes alösszetevő kapcsolat hivatkozást, amelynek beállítása megszorításon alapuló konfiguráció változat konfigurációs technológia alaptermékhez kötelező megadni.

### <a name="user-requirements"></a>Felhasználói követelmények

Felhasználói követelmény részletes összetevőinek tartozik. Az egyetlen különbség, hogy egy felhasználói követelmény alaptermék nem kötött. Ez a különbség a gyakorlati hatása, hogy minden olyan anyagjegyzéksorok vagy útvonalművelet definiált felhasználói követelmény keretében gyűjti össze a szülő komponensszerkezet Anyagjegyzék vagy útvonal. Ez a viselkedés a látszólagos Anyagjegyzék működése hasonlít.

### <a name="bom-lines"></a>Anyagjegyzéksorok

Minden egyes összetevő gyártási Anyagjegyzékében azonosítására anyagjegyzéksorok jelennek meg. Anyagjegyzéksor hivatkoznia kell a cikk, és az összes cikk tulajdonság megváltoztathatók egy rögzített értékre állítani, vagy attribútum rendelve.

### <a name="route-operations"></a>Útvonalműveletek

Útvonalműveletek bekerülnek a termelési útvonal azonosítása. Útvonalművelet hivatkoznia kell a meghatározott művelethez, és az összes művelet tulajdonság beállítható egy rögzített értéket. Erőforrás-igényű kivételével az összes tulajdonság az attribútum értéke helyett rendelhetők.

## <a name="validating-and-testing-a-product-configuration-model"></a>Termékkonfigurációs modell létrehozása és beállítása

A termékkonfigurációs modell ellenőrzése a modellben több szinten történhet, és ezért tudja fedezni a különböző hatókörök. A legalacsonyabb szint egy egyetlen Kifejezésmegszorítás szolgál. Ebben az esetben a ellenőrzési általában végzi a termék-tervező segítségével a kifejezés szintaxisának helyességét.  

Ehhez hasonlóan a feltételt a AJ-sor vagy egy útvonalművelet önmagában érvényesíthető.  

Az a felhasználó által definiált táblamegszorítás definíciója ellenőrzési is elvégezhető. Ebben az esetben a felhasználó ellenőrizheti, hogy a megadott az egyes mezők értékei a megfelelő típusú attribútum a tartományon belül.  

Végül a teljes termékkonfigurációs modell ellenőrzése a teljes szintaxisának helyességét, és hogy az összes elnevezéshez, illetve a modellezési szabályok betartásáról ellenőrzési végezhető el.

### <a name="testing"></a>Tesztelés

A modell tesztelése hasonlít egy tényleges konfigurációs munkamenet futtatására. A felhasználó végigmehet a konfigurációs lapokon, és ellenőrizheti, hogy a szerkezeti modell támogatja-e a konfigurálási folyamatot. A felhasználó ellenőrizni tudja, hogy helyesen-e a termékattribútum-értékeit, és az attribútumok leírása végigvezeti a felhasználót, jelölje be a megfelelő értékeket az, hogy. Végül a vizsgálati munkamenet befejezése után a rendszer megpróbálja létrehozni az Anyagjegyzék és az útvonal, amely megfelel a kiválasztott termékattribútum-értékeit, és egy hibaüzenet jeleníti meg, ha bármilyen hiba történne.

### <a name="the-configuration-page"></a>Konfiguráció oldal

Kattintva válthat az összetevők között, **Következő**, vagy kattintson a konfigurációs termékmodellfa fókuszt meg összetevő.

## <a name="finalizing-a-model-for-configuration"></a>Egy modell konfigurációjának véglegesítése

A termékkonfigurációs modell konfigurálása rendelésre esetekben használandó elkészül, ha létre kell hozni egy verziót. Azonban, amelyek a modellezési tapasztalat növelheti többféle lehetőség kínálkozik.

### <a name="user-interface"></a>Felhasználói felület

A konfigurációs Kezelőfelület egy vagy több alösszetevői az attribútumcsoportok bevezetésével módosítható. Ilyen lehet jelölje ki a meghatározott attribútumokkal közötti kapcsolatokat és a konfigurációs felhasználó azonosítása a fókuszban lévő termék.

### <a name="templates"></a>Sablonok

Egy vagy több konfigurációs sablonok konfigurálását fel lehet gyorsítani létrehozhatók. Azt is megteheti sablonokat is létrehozható elősegítése meghatározott attribútum kombinációja, például amikor meghatározott funkciók a termék eladási kampány szolgál.

### <a name="translations"></a>Fordítások

Az eladandó különböző országokban/régiókban alkalmazható, ha a konfigurációs Kezelőfelület megjelenő szövegeket fordítások is létrehozható. Ez a szöveg a nemcsak neve és a mezők leírása, hanem attribútum a szöveges értékeket tartalmazza.

### <a name="versions"></a>Verziók

A legutóbbi és legfontosabb lépés a véglegesítési folyamatban a termékkonfigurációs modell verzió létrehozásához. A verzió jeleníti meg az alapterméket, amelyen kiválaszthatók a rendelésen, vagy az ajánlati sor konfigurációs, és a termékkonfigurációs modell közötti kapcsolatot. Az anyagverziót az indítás és a használat előtt jóvá kell hagyni.

## <a name="extending-a-product-configuration-model-through-the-api"></a>A termékkonfigurációs modell az API-k kiterjesztése

Egy dedikált alkalmazási programozási felület (API), így a partnerek és egyéb fejlesztői licenccel rendelkező bővíthetők az egy termékkonfigurációs modell jellemzőinek hajtották végre. A fő cél egy olyan mechanizmus létrehozása, amely lehetővé teszi a meglévő Termékszerkesztőt használó partnerek és ügyfelek számára a Termékszerkesztő modelljeibe beágyazott kódok migrálását az API-ba. Ezzel a módszerrel azokat is át a modellek Termékszerkesztő a termék konfigurációja. Új partnerek és a vevők is is előnyös az API segítségével új termékkonfigurációs modellek kiterjeszteni.

Az API számos által megvalósított **PCAdaptor** osztályok, amelyek teszik elérhetővé a termékkonfigurációs modellek az adatszerkezet. A **PCAdaptor** osztály egy példányát létre kell hozni minden egyes modellhez, amely ki lesz terjesztve. A konfigurációs munkamenet befejezése után a rendszer ellenőrzi, hogy fut-e ezen osztály egy példánya, és hogy megtalálható-e.  

A következő API-folyamatábra a folyamatot ismerteti.  

[![Folyamatábra](./media/product_configuration_2.png)](./media/product_configuration_2.png)  

## <a name="configure-products"></a>Termékek konfigurálása

### <a name="configure-one-or-more-products"></a>Egy vagy több termék konfigurálása

A termékeket a következő helyekről konfigurálhatja:

- Értékesítésirendelés-sor
- Értékesítési ajánlat sora
- Beszerzésirendelés-sor
- Termelési rendelés sorai
- Cikkszükséglet-sort (projekt)

A konfiguráció az a célja, hogy hozzon létre egy külön változat a termék, amely megfelel a vevő követelménynek. Minden új konfiguráció jön létre a konfiguráció egyedi Azonosítóját. Ez az azonosító lehetővé teszi, hogy a készlet nyomon követése.

### <a name="multiple-sites-and-intercompany-considerations"></a>Többszörös helyek és a vállalatközi megfontolások

Ha a beállítás történik, a hely vagy akár egy vállalat, amely eltér a hely vagy vállalat, ahol a termelési sor fog kerülni, az Anyagjegyzék és az útvonal lesz kell létrehozni, és a szállító helyén a szállító vállalatnál. A termékváltozat vesznek részt az ellátási lánc minden vállalatban kiadja a rendszer.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]