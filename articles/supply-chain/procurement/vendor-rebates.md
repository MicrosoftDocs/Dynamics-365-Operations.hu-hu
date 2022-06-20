---
title: Szállítói visszatérítések
description: Ez a témakör áttekintést nyújt a szállítói visszatérítések végrehajtása során leggyakrabban elvégezni kívánt feladatokról. A szállítói visszatérítések segítséget nyújtanak a vállalatoknak szállító visszatérítési programjuk könnyebb kezelésében úgy, hogy automatizálják a megszerzett visszatérítések felügyeletéhez, nyomon követéséhez és igényléséhez szükséges feladatokat.
author: GalynaFedorova
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TAMVendRebateAgreement
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: gfedorova
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 2012
ms.openlocfilehash: 789a58af40595cbb72d55d598510c43315aead2b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8890799"
---
# <a name="vendor-rebates"></a>Szállítói visszatérítések

[!include [banner](../includes/banner.md)]

A szállítói visszatérítések segítséget nyújtanak a vállalatoknak szállító visszatérítési programjuk könnyebb kezelésében úgy, hogy automatizálják a megszerzett visszatérítések felügyeletéhez, nyomon követéséhez és igényléséhez szükséges feladatokat.

Ez a témakör áttekintést nyújt a szállítói visszatérítések végrehajtása során leggyakrabban elvégezni kívánt feladatokról. Az áttekintés a következő feladatokat foglalja magában:

- Visszatérítési megállapodás részleteinek áttekintése.
- Visszatérítéseket lehetővé tevő rendelések azonosítása és a visszatérítési igények létrehozása.
- Igények ellenőrzése és jóváhagyása.

## <a name="audience-and-purpose"></a>Célközönség és cél

A jelen cikk információi a vállalati vállalatok üzleti döntéshozóinak, például beszerzési vezető, pénzügyi igazgató és főkönyvelési vezető beosztásban, valamint főkönyvelési vezetőnek szántak, akik a következő felelősségi köröket vállalják:

- Szállítói árak, engedmények és visszatérítési megállapodások megtárgyalása.
- A személyzet felügyelete, amely feldolgozza a visszatérítési igényeket, és beszedi a kifizetéseket.
- Készlet rendelése a legjobb lehetséges áron.

Az ezen beosztásokban dolgozó személyek különféle módokat keresnek céljaik elérésére. Íme néhány példa:

- Rugalmasan alkalmazni különböző típusú szállítói promóciós programokat és visszatérítési feltételeket.
- A promóció teljesítményének figyeléséhez és az igények feldolgozásához kapcsolódó adminisztratív terhek és hibák csökkentése.
- Pénzforgalmi előrejelzések javítása a jövőbeni bevételek elhatárolása révén.
- Összegszerű alap biztosítása a szállítókkal folytatott, visszatérítésekkel kapcsolatos folyamatban lévő és jövőbeli tárgyalásokhoz.

## <a name="review-details-of-a-vendor-rebate-agreement"></a>Szállítói visszatérítési megállapodás részleteinek áttekintése.

A szállítói visszatérítési megállapodásban egy szállítóval kötött szerződési rekordot jelent, amely rögzíti azon egyeztetett feltételeket, amelyek alapján a vállalat előzetesen lefektetett beszerzési célok elérése alapján pénzjutalomra jogosult. A szállítói visszatérítési megállapodások rögzítése a **Visszatérítési megállapodások** oldalon történik.

A **szállítói visszatérítési megállapodások** oldal megnyitásához válassza a **Beszerzés és forrás** &gt; **Szállítói visszatérítések** &gt; **Visszatérítési megállapodások** elemet.

![Beszerzési szerződés.](media/purchase-agreement.PNG)

A **Szállítói visszatérítési megállapodások** lapon megtekintheti az adott szállítói szerződés egyeztetett feltételeinek részleteit.

A megállapodás fejléce mutatja az általános feltételeket, amelyek alapján a vállalat visszatérítésekre jogosult. A fejléc adatai tulajdonképpen azt szabják meg, hogy a szállító visszatérítést biztosít, amikor egy adott termék vásárlásai elérnek egy adott mennyiséget. A fejlécen a visszatérítés beállításaként megadható a mértékegység és a számítás dátumának típusa.

- Az **Áttekintés** lapon, ha a **Cikk-kóddal** rendelkező sorok *táblázat* értékre vannak állítva egy cikk meghatározásához, akkor a megállapodás arra az adott cikkre vonatkozik. Ha van olyan sor, amelyben a **Cikk-kód** *Csoport* vagy *Összes* értékre van állítva a cikkek megadásához, akkor a szállítói visszatérítési megállapodás külön-külön lesz feldolgozva az cikkódnak megfelelő elemenként, nem a cikkódnak megfelelő összes elemre vonatkozóan.

- Az **Általános** lapon a **Visszatérítés mértékegysége** mezőben határozhatja meg, hogy egy adott mértékegység feltétele legyen-e a beszerzési rendelési sornak a visszatérítési igényre való jogosultsághoz.

    - **Konvertálás** – a beszerzési rendelési sor szállítói visszatérítésre jogosult a visszatérítési megállapodás szerint. A visszatérítést attól függetlenül megkapja, hogy, a sorban milyen mértékegység van alkalmazva.
    - **Pontos egyezés** – a visszatérítéshez a beszerzési soron ugyanannak a mértékegységnek kell szerepelnie, amely a szerződésben elő van írva.

- Az **Általános** lapon a **Számítás dátumának típusa** mezőben válassza ki azt a dátumot, amely azt határozza meg, hogy a beszerzés a visszatérítési megállapodás érvényességi időszakán belül történik-e.

    - **Létrehozva** – a beszerzési rendelés létrehozási dátumának használata.
    - **Kért kiszállítás** – a kért kiszállítási dátum használata.

A szerződési sorokban részletesebben megadhatja a szállítói visszatérítési megállapodást.

- A **Beszerzések összesítési időszaka** mezőben be lehet állítani a visszatérítési igény kiszámítását. Az összeg beállítható időszaktól (hét, hónap, év, élettartam vagy egy egyéni időszak) függően. A **Számla** érték azt jelzi, hogy a visszatérítési igény meghatározására minden alkalommal sor kerül, amikor egy beszerzési rendelési sor számlázása megtörténik.
- A **Forrás:** mezőben megadhatja a visszatérítés kiszámításának alapját.

    - **Bruttó** – a visszatérítést a rendszer a cikk bruttó ára alapján számítja ki.
    - **Nettó** – a visszatérítést a rendzser a cikk nettó ára alapján (az egyéb engedmények alkalmazása után maradó ár) számítja ki.

- A **Visszatérítési program elhatárolása** és a **Visszatérítési program költségszámlája** mezőkben adja meg a jóváhagyás és a feldolgozás közötti közbenső szakaszban az elhatárolt visszatérítési összegek fogadására használt számlaszámokat.
- Ha a **Jóváhagyás szükséges** beállítás **Igen** értékre van állítva, a visszatérítési igényt annak elhatárolása vagy kifizetése előtt jóvá kell hagyni.
- A **Visszatérítéssor törésének típusa** mezőben a visszatérítések számításához használt módszer látható.

    - **Mennyiség** – a visszatérítések mennyiségalapúak.
    - **Összeg** – a visszatérítések összegalapúak.

- A **Sorok** gyorslapon látható, hogyan állíthatók be különböző visszatérítések megadásához használt mennyiségi rétegek. Például az előző példában a **Kezdő érték** és a **Záró érték** mezők mutatják, hogy a 10 és 19 egység közötti termékmennyiség egységenkénti 15 USD visszatérítésre jogosít.

    > [!NOTE]
    > A **Kezdő érték** érték tartalmazza a határértéket, a **Záró érték** érték pedig nem. Például a **Visszatérítéssor törésének típusa** mező értéke **Mennyiség**, és Ön **1**-et ad meg a **Kezdő érték** mezőben és **3**-at a **Záró érték** mezőben. Ebben az esetben a visszatérítési összeg egy vagy két cikk beszerzése esetén érvényes, de nem három cikk beszerzése esetén.

- A **Munkafolyamat-jóváhagyási állapot** mezőben a **Jóváhagyva** érték azt jelzi, hogy a megállapodás alkalmazható azon beszerzési rendelésekre, amelyek megfelelnek a megállapodás feltételeinek.

## <a name="identify-orders-that-qualify-for-rebates-and-generate-rebate-claims"></a>Visszatérítéseket lehetővé tevő rendelések azonosítása és a visszatérítési igények létrehozása

Amikor egy olyan szállító kap beszerzési rendelést, amellyel a vállalatnak visszatérítési megállapodása van, a program azonosítja az esetleges jövőbeli szállítói fizetési jóváírásokat. Ha a beszerzési rendelések visszatérítésre jogosultak, visszatérítési igény jön létre minden rendelési sorhoz, amint a beszerzési számla feladása megtörtént. Ez folyamat automatikus. Később a várható visszatérítések áttekinthetők és látható ezen visszatérítések hatása a termék költségére és fedezeti mutatójára nézve.

### <a name="view-details-of-rebates-that-are-applied-to-a-purchase-order-line-per-the-vendor-rebate-agreement"></a>A szállítói visszatérítési megállapodás alapján a beszerzésirendelés-sorra alkalmazott visszatérítések részleteinek megtekintése

1. A **Beszerzési rendelés** oldalon válasszon ki egy rendeléssort, és válassza a **Beszerzésirendelés-sor** &gt; **Megtekintés** &gt; **Ár részletei** elemet.
2. Az **Ár részletei** oldalon válassza a **Visszatérítések** gyorslapot.

A visszatérítési információk az **Ár részletei** lap **Becsült haszonkulcs** részének **Szállítói visszatérítés** mezőjében is megjelennek.

> [!NOTE]
> A **Beszerzési és forrásparaméterek** oldalon az **Árak** lapon ellenőrizze, hogy az **Áradatok engedélyezése** a beállítás **Igen**-e. Ha a beállítás értéke **Nem**, nem lehet a visszatérítéseket megtekinteni.

## <a name="review-and-approve-claims"></a>Igények ellenőrzése és jóváhagyása

A létrehozott visszatérítési igények a szállítótól érkező várható jövőbeli kifizetéseket képviselik. Jóváírás a szállító részére történő végrehajtása előtt a szerződés tulajdonosa általában szeretné az igényeket áttekinteni és jóváhagyni. Megjegyzendő, hogy az igény állapota határozza meg, hogy a követelés készen áll-e a jóváhagyási folyamatra.

### <a name="the-status-of-claims-and-the-effect-on-the-approval-process"></a>Az igények állapota és hatása a jóváhagyási folyamatra

Igény létrehozásakor az állapot értéke **Számítandó**, ha a visszatérítés megadása halmozott alapon történik, illetve **Számított**, ha a visszatérítés megadása számlánként történik. Ha az igény állapota **Számítandó**, az igénynek egy számítási folyamaton kell átesnie, amely az Összesítés funkció kezel. Csak a **Számított** állapotú igények kerülhetnek be a jóváhagyási folyamatba.

> [!NOTE]
> Ha a **Jóváhagyás szükséges** beállítás értéke egy szállítói visszatérítési megállapodásban **Nem**, a létrehozott igények állapota  **Jóváhagyva** lesz. A jóváhagyás kötelező a halmozott adatok alapján biztosított igényeknél.

### <a name="approve-claims-and-view-postings-and-invoice-details"></a>Igények jóváhagyása, feladások és számlaadatok megtekintése

Az igények jóváhagyást követően feldolgozhatók a Kötelezettségek (A/P) részéről. A jóváírást (szállítói számla) a program a visszatérítési igénylés összegéhez automatikusan generálja. Az követel tétel ezután hozzáadható a szállítói egyenleghez, az A/P-csoport pedig felveheti a normál kiegyenlítési folyamatba.

1. Válassza a **Beszerzés és forrás** &gt; **Szállítói visszatérítések** &gt; **Visszatérítési igények** elemet visszatérítési igény megnyitásához.
2. Zárja be a visszatérítési igényt.
3. Jelölje be az igényt, és ezután válassza a műveleti ablak **Jóváhagyás** elemét.
4. A kérelem lapon található a **Szállító** mezőben válassza ki a szállítót, amelyhez engedélyezett a visszatérítés fogadára, majd válassza az **OK** gombot.

    Egy visszatérítési könyvelési napló feladásra kerül a követelés összegével. Ez a feladás tartozik tételként kerül az Elhatárolt szállítói visszatérítés-követelések számlára a várt szállítói jóváírás alapján és követel tételként az ideiglenes Elhatárolt szállítói visszatérítés-kiegyenlítések számlára a várható nyereséget illetően.

    ![Üzenet.](media/message.png)

5. A visszatérítési listában válassza ki a sort, majd ezután a műveleti ablakban válassza a **Visszatérítési tranzakciók** elemet az elhatárolt visszatérítéshez tartozó naplókötegszám megjelenítéséhez és kikereséséhez.

    Az igények a normál A/P folyamatba való átviteléhez az A/P adminisztrátornak végre kell hajtania a visszatérítési igényt, amihez a Folyamat funkciót kell futtatni.

6. A műveleti ablaktáblán válassza a **Folyamat**, majd a **Szűrő** elemet. A **Szállítói számla** mező **Feltételek** mezőjében válassza ki a szállítót, amelynél visszatérítési igényt kíván feldolgozni, válassza ki a többi vonatkozó szűrőt, majd válassza az **OK** gombot.

    Az üzenetoszlopok és az, hogy az állapot **Kész** értékre vált, jelzik, hogy a következő eseményeket megtörténtek:

    - Az Elhatárolt visszatérítés könyvelési naplójának feladása sztornírozta az előző ideiglenes összegeket az elhatárolt követelések és költségszámlán.
    - A visszatérítési összegre létrejött egy szállítói számla (jóváírás).

        > [!NOTE]
        > A **Beszerzési és forrásparaméterek** oldal **Visszatérítési program** lapjának **Manuális számlafeladás** beállítása határozza meg, hogy egy szállítói számla feladása kézzel vagy automatikusan történik-e az igény feldolgozásának részeként.

    - A szállítói számla automatikus vagy manuális feladásakor a szállító Fizetési számláján követel, a Kapott engedmények számla pedig tartozik tétel jelenik meg.

        > [!NOTE] 
        > A Kapott engedmények számlaszám van megadva a beszerzési kategóriához, amely a visszatérítéshez a beszerzési számlasornál használatos. A beszerzési kategória pedig a **Beszerzési és forrásparaméterek** oldal **Visszatérítési program** lapján van megadva.

7. A visszatérítési listában válassza ki a sort, majd ezután a műveleti ablakban válassza a **Visszatérítési tranzakciók** elemet az elhatárolt visszatérítéshez tartozó naplókötegszám és szállítói számlaszám megjelenítéséhez és kikereséséhez.
8. Válassza ki a szállítói számlatranzakció sorát, majd a műveleti ablaktáblán válassza a **Szállítói számla** elemet. Ha a szállítói számla feladása megtörtént, a Számlanapló jelenik meg. Ellenkező esetben a szállítói számla jelenik meg függőben lévő szállítói számlaként, amely manuálisan történő feladást igényel.

    A számlasor megadja a szállítói számla részletes adatait a **Jutalékok és a visszatérítések** beszerzési kategóriához.

9. A **Minden szállító** oldalon válassza ki a szállítót, amelytől visszatérítést fog kapni, és a műveleti ablaktáblán válassza a **Tranzakciók** elemet. Keresse meg a számla sorát. A visszatérítési összeg hozzá lett adva a szállítói egyenleghez.

## <a name="summary"></a>Összegzés

A szállítói visszatérítések kezelésére szolgáló eljárásban több manuális nyomon követési feladat található, és ezek gyakran fárasztóak lehetnek. Ezeket a feladatokat automatizálva a szállítói visszatérítések kezelése segít navigálni a következő folyamatokban:

- Pontos visszatérítési igények létrehozása
- A várható kinnlevőségek és az ideiglenes nyereség elhatárolása a főkönyvben
- A szállítói egyenleg és az eredménykimutatás frissítése az esedékes engedménnyel


[!INCLUDE[footer-include](../../includes/footer-banner.md)]