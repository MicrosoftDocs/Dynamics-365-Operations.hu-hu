---
title: Beszerzési cXML fejlesztései
description: A Beszerzési cXML-fejlesztések funkció a meglévő külső katalógus funkcióra, a PunchOut-funkcióra épül, amely a beszerzési igénylésekhez használatos.
author: Henrikan
ms.date: 08/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatCXMLParameters, CatCXMLPurchRequest
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2020-08-03
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 210d92b9fd962708b141b79f3634f142cca9787a
ms.sourcegitcommit: 8cb031501a2b2505443599aabffcfece50e01263
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/09/2021
ms.locfileid: "7777767"
---
# <a name="purchasing-cxml-enhancements"></a>Beszerzési cXML fejlesztései

[!include [banner](../includes/banner.md)]

A _Beszerzési cXML-fejlesztések_ funkció a [meglévő külső katalógus funkcióra](set-up-external-catalog-for-punchout.md), a PunchOut-funkcióra épül, amely a beszerzési igénylésekhez használatos. Ez a meglévő funkció neve _PunchOut_. Bár a beszerzési rendelés nem kell, hogy a beszerzési igényléstől származzon, a beszerzési rendelésen szereplő szállító és a beszerzési rendelés dokumentumának küldéséhez használt paraméterek között kapcsolat kell legyen.

## <a name="turn-on-the-purchasing-cxml-enhancements-feature"></a>A beszerzési cXML-fejlesztések funkció bekapcsolása

A funkció bekapcsolásához nyissa meg a **[Funkciókezelés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)** lapot, és keressen rá a *Beszerzési cXML fejlesztései* kifejezésre. Válassza ki a bekapcsolni kívánt funkciót, majd a részletek ablaktáblán válassza az **Engedélyezés most** lehetőséget a bekapcsolásához. (Az Ellátásilánc-kezelés 10.0.21-es verziója alapértelmezés szerint be van kapcsolva.)

A funkció bekapcsolását követően konfigurálnia kell a beállításokat a következő három területen:

- **[cXML-paraméterek](#cxml-parameters)** – ezeket a beállításokat a beszerzési rendelések küldéséhez szükséges globális paraméterek beállítására használhatja.
- **[Szállító beállítása](#vendor-setup)** – Ha az összes szállítóhoz létrehozott összes új beszerzési rendeléshez alapértelmezésként a commerce EXtensible Markup Language (cXML) nyelvet kell használni, akkor a szállítónál a **beszerzési rendelés küldését cXML-en keresztól** beállítást állítsa _Igen_ értékre.
- **[Külső katalógusok](#external-catalog-setup)** – Az új **Rendeléstulajdonságok** beállításokkal határozza meg a beszerzési rendelési dokumentum formátumát, valamint azt, hogy hogyan történik az elküldése.

A következő ábra összefoglalja ezt a konfigurációt.

![A cXML-funkciók beállítására szolgáló területek.](media/cxml-settings-areas.png "A cXML-funkciók beállítására szolgáló területek")

Ezenkívül be kell állítania a [Beszerzési rendelési kérelem kötegelt feladatot](#po-batch). Ez a kötegelt feladat a visszaigazolt beszerzési rendelések küldéséhez használatos.

## <a name="set-up-global-cxml-parameters"></a><a name="cxml-parameters"></a> Globális cXML-paraméterek beállítása

A **cXML-paraméterek** oldal használatával elvégezhet néhány globális beállítást, amelyek a beszerzési rendelések küldésének funkcionalitására vonatkoznak.

![cXML-paraméterek oldal.](media/cxml-parameters.png "cXML-paraméterek oldal")

Nyissa meg a **Beszerzési és forrás \> Beállítások \> cXML-kezelése \> cXML-paraméterek** menüpontot, és állítsa be a következő paramétereket:

- **cXML teszt mód** – Ez a globális paraméter hatással van arra, hogy a beszerzési rendelések fizikailag milyen módon legyenek elküldve a kötegelt feladattól. Válasszon a következő értékek közül:

    - **Teszt** – Ebben a módban a kötegelt feladat futhatja, és létrejön az üzenet XML-dokumentuma, de az nem lesz elküldve. Helyette a program a beszerzési rendelésre vonatkozó kérelmet menti ellenőrzési célból. Ez a mód akkor hasznos, ha a kezdeti implementációnál tart, és látni szeretné, hogy hogyan kell megadni az adatokat a cXML-üzenetben. Lehetséges, hogy mintaüzeneteket is szeretne létrehozni amelyeket el lehet küldeni a szállítóknak kezdeti ellenőrzésre.
    - **Élő** – Ebben a módban a funkció a [külső katalógus beállításai](#external-catalog-setup) alapján ténylegesen továbbítja a dokumentumokat a szállítónak.

- **Beszerzési kérelem frissítéseinek küldése** –Ezt a beállítást *Igen* értékre állítva a beszerzési rendelésekhez frissítési üzeneteket küldhet. A *Nem* értékre állítással megakadályozhatja az üzenet elküldését. A legtöbb szállító azt szeretné, ha nem érkeznének frissítési üzenetek. Ehelyett inkább azt szeretnék, hogy az ügyfelek telefonon vagy e-mailben vegyék fel velük a kapcsolatot, ha egy beszerzési rendelést módosítani szükséges. Ez a paraméter egy globális paraméter, és nem adható meg felülbírálás a külső katalógusban az egyes szállítókhoz. A beszerzési rendelés frissítettként lesz megjelölve, ha a beszerzési rendeléshez második visszaigazolását ad fel, de az első visszaigazolást már elküldték, és a szállító visszaigazolta. Ha van második visszaigazolás, de az első visszaigazolás nem lett elküldve, akkor a rendszer új dokumentumként kezeli a második visszaigazolást. Egy beszerzési rendelést tetszőleges számú alkalommal megerősítheti, amíg el nem küld egy visszaigazolást. A következő visszaigazolást frissítési üzenetként kezeli a rendszer.
- **Beszerzési kérelem törlésének küldése** –Ezt a beállítást *Igen* értékre állítva a beszerzési rendelésekhez törlési üzeneteket küldhet. A *Nem* értékre állítással megakadályozhatja az üzenet elküldését. A legtöbb szállító azt szeretné, ha nem érkeznének törlési üzenetek. Ehelyett inkább azt szeretnék, hogy az ügyfelek telefonon vagy e-mailben vegyék fel velük a kapcsolatot, ha egy beszerzési rendelés nem szándékosan lett küldve. Ez a paraméter egy globális paraméter, és nem adható meg felülbírálás a külső katalógusban az egyes szállítókhoz. A beszerzési rendelés töröltnek lesz megjelölve, ha érvényteleníti a beszerzési rendelést a Supply Chain Management alkalmazásban.
- **Archívumfájl** – Adja meg a fájl elérési útját, amelybe exportálni szeretné az archivált cXML dokumentumokat. Az elérési út akkor használatos, amikor futtatja a véglegesen töröl funkciót a **Beszerzési rendelési kérelem** lapon.
- **Utca sor maximális karakterszáma** – Adja meg, hogy legfeljebb hány karakter használható a cXML dokumentumban az utcacímekhez. Ez a globális paraméter az összes szállítót érinti, ha a külső katalógus tulajdonságainál nincs megadva felülbírálás.

## <a name="set-up-vendor-purchase-orders-to-use-cxml"></a><a name="vendor-setup"></a> Szállítói beszerzési rendelések beállítása cXML használatára

Minden alkalommal, amikor megerősít egy beszerzési rendelést, amelynél a **beszerzési rendelés küldése cXML-en keresztül** beállítás értéke _Igen_, a rendszer automatikusan létrehozza a cXML üzenetet, és leszállítja az adott beszerzési rendeléshez társított szállítónak. A beszerzési rendelésekhez kétféle módszerrel lehet szabályozni ezt a beállítást:

- Ha azt szeretné beállítani, hogy a szállító automatikusan cXML-t használjon az igénylésből létrehozott összes új beszerzési rendeléshez, nyissa meg a **Beszerzés és forrás \> Szállítók \> Összes szállító** lehetőséget , majd válasszon ki, vagy hozzon létre egy szállítót a részletek lapjának megnyitásához. Ezt követően a **Beszerzési rendelés alapértelmezései** gyorslapján állítsa a **Beszerzési rendelés küldése cXML-en keresztül** lehetőséget _Igen_ értékre. Ha a cXML a nem **igénylésből** létrejövő új beszerzési rendelésekhez is automatikusan használni kell , akkor az **ENABLEMANUALPO** rendelési tulajdonságot is _Igaz_ értékre kell állítani a kapcsolódó külső katalógus esetében, a témakör [A rendelés tulajdonságainak beállítása](#set-order-properties) című későbbi részében leírtak szerint.
- Az egyes beszerzési rendelések esetében nyissa meg a **Beszerzési és forrás \> Beszerzési rendelések \> Összes beszerzési rendelés** lehetőséget, és válassza ki vagy hozzon létre egy beszerzési rendelést a részletek lapjának megnyitásához. Váltson át a **Fejléc** nézetre, majd a **Beállítás** gyorslapon a **Beszerzési rendelés küldése cXML-en keresztül** beállítást kötelezőre.

![Szállítói beszerzési rendelések alapértelmezett beállításai.](media/cxml-order-defaults.png "Szállítói beszerzési rendelések alapértelmezett beállításai")

## <a name="set-up-an-external-catalog-to-use-cxml"></a><a name="external-catalog-setup"></a> Külső szállítói katalógus beállítása cXML használatára

A **Külső katalógusok** lapon mindegyik katalógushoz be lehet állítani a PunchOut funkciót és a beszerzési rendelések küldésének funkcióját. A megfelelő beállítások megkereséséhez nyissa meg a **Beszerzési és forrás \> Katalógusok \> Külső katalógusok lehetőséget**. Kezdje úgy , hogy [minden katalógust a megszokott módon állít be](set-up-external-catalog-for-punchout.md). Ez a folyamat tartalmazza egy szállító hozzárendelését, azon kategóriák beállítását, amelynél a szállító számára engedélyezett az ellátás, illetve a katalógus aktiválását. Ezután konfigurálja a szakaszban ismertetett további beállításokat.

> [!NOTE]
> Amikor egy cXML keresztül küldendő beszerzési rendelést erősít meg, a rendszer megkeresi a beszerzési rendeléshez társított szállítót, majd megkeresi az adott szállítóhoz társított első aktív külső katalógust. A rendszer ezután a külső katalógus beállításait használja a beszerzési rendelés elküldéséhez. Ha több külső katalógus van beállítva, akkor a rendszer csak az első megtalált külső katalógust használja, amely a beszerzési rendelésen szereplő szállító alapján. Ezért azt ajánljuk, hogy csak egy külső katalógust hozzon létre mindegyik szállítóhoz.

![Külső katalógus beállításai.](media/cxml-supplier-catalog.png "Külső katalógus beállításai")

### <a name="set-the-punchout-protocol-type"></a>A PunchOut-protokoll típusának megadása

A **Külső katalógusok** lap **Általános** gyorslapján állítsa a **Punchout-protokolltípus** mezőt _cXML_ értékre. Ez a lehetőség csak akkor érhető el, ha egy partner kibővítette a funkcionalitást, és a bővítményben további beállításokat biztosít.

Ha a PunchOuthoz tartozó katalógust is használja, akkor [be kell állítania az üzenet formátumát](set-up-external-catalog-for-punchout.md) is. Az üzenet formátuma a szállítóval való kapcsolat létrehozására szolgál az igénylésből származó PunchOut-tranzakcióban. Beszerzési rendelés elküldésekor a program a rendelés tulajdonságait használja a szállítóval való kapcsolat létrehozásához.

### <a name="set-the-order-properties"></a><a name="set-order-properties"></a> A rendelés tulajdonságainak beállítása

A _Beszerzési cXML fejlesztései_ funkció hozzáadja az új **Rendelési tulajdonságok** gyorslapot a külső katalógusokhoz. Ez a gyorslap egy rácsot biztosít, ahol megadhatja a rendelés tulajdonságait. Emellett egy eszköztárat is tartalmaz. Ez az eszköztár a következő három gombot tartalmazza, amelyek segítségével kezelhetők a rendelési tulajdonságok:

- **Alapértelmezett tulajdonságok** – Új katalógus beállításakor jelölje be ezt a jelölőnégyzetet, ha a rácshoz előre definiált, gyakran használt tulajdonságok gyűjteményét szeretne hozzáadni.
- **Új** – Új tulajdonság hozzáadása a rácshoz.
- **Törlés** – Az aktuálisan kiválasztott tulajdonság törlése a rácsból. Ha véletlenül töröl egy alapértelmezett tulajdonságot, akkor az **Alapértelmezett tulajdonságok** beállításával visszaállíthatja az összes hiányzó tulajdonságot.

Minden alkalommal, amikor egy vagy több tulajdonságot hozzáad a rácshoz, a jobb oldali oszlopban adja meg a kívánt értékeiket.

Az alapértelmezett tulajdonságokat a következőképpen lehet használni:

- **BUYER\_ COOKIE** – Ezt a nyomon követési mezőt a vállalatra vonatkozó konkrét információk jelzésére lehet használni. Hacsak nem rendelkezik a szállítóval megállapodással a tulajdonság használatáról, akkor a beszerzési rendelés elküldésekor nem hordoz sok jelentést. Ezért egy egyszerű értéket kell megadni.
- **DELIVERTO** – Amikor a szállítási cím szerepel a dokumentumban a beszerzési rendelésből, a **Figyelmeztető információ** mező szolgál a **DeliverTo** mező beállítására az XML-üzenetben. Ha azt szeretné, hogy ez az érték legyen kérelmező neve, és a beszerzési rendelés fejlécében beállítja a kérelmező mezőt, akkor adja meg az ehhez a tulajdonsághoz tartozó _REQUESTER_ értéket, hogy a kérelmező neve szerepeljen az XML **DeliverTo** mezőjében. Ebben az esetben a használt elsődleges e-mail cím és telefonszám a megrendelő helyett a kérelmezőből lesz használva.
- **DEPLOYMENTMODE** – Ezt a tulajdonságot a szállító által megköveteltként állíthatja be. Az értékek általában _PRODUCTION_ vagy _TEST_. Az értéket a szállítóval folytatott kommunikáció alapján állítsa be. A programnak általában egyeznie kell a **ORDERCHECKURL** érték mögötti szándékolt rendszerrel, amelyet a szállító teszt- vagy termelési rendszerként jelez.
- **FIXEDBILLADDRESSID** – Ha be van állítva az XML-üzenet **addressID** mezője, akkor a rendszer észleli az ezen a címen megadott helyet. Ha a szállítónak küldött azonosító érték eltér a cím helyén lévő értéktől valamilyen oknál fogva, akkor az itt megadott érték megadásával kényszerítheti a felülírást. A feltételezés az, hogy csak egy címet fog használni a szállítónál, és a cím be van állítva a szállítói rendszerben. A számlázási cím a jogi személynek a Supply Chain Management alkalmazásban megadott elsődleges számlázási címe.
- **FIXEDSHIPADDRESSID** – Ha be van állítva az XML-üzenet **addressID** mezője, akkor a rendszer észleli az ezen a címen megadott helyet. Ha a szállítónak küldött azonosító érték eltér a cím helyén lévő értéktől valamilyen oknál fogva, akkor az itt megadott érték megadásával kényszerítheti a felülírást. A feltételezés az, hogy csak egy címet fog használni a szállítónál, és a cím be van állítva a szállítói rendszerben. A szállítási cím a beszerzési rendelés fejlécében megadott cím. A legtöbb szállító csak fejléc-címeket fogad el, nem pedig sorcímeket. Annak ellenére, hogy az XML-címben szerepelnek mezők sorcímeihez, fejléccímre lesznek állítva.
- **FROM\_ DOMAIN** – Adja meg a beszerzési rendelési dokumentumok küldéséhez használt értéket. Ezt az értéket a szállító biztosítja.
- **FROM\_ IDENTITY** – Adja meg a beszerzési rendelési dokumentumok küldéséhez használt értéket. Ezt az értéket a szállító biztosítja.
- **ORDERCHECKURL** – Adja meg az URL-címet, amelyre továbbítani szeretné a beszerzési rendelési dokumentumokat. Ez az URL-cím a `https://` előtaggal kezdődik, és a szállító biztosítja.
- **PAYLOAD\_ ID** – Adjon meg egy előtagot a rakomány azonosítója számára, az aktuális szállítónál érvényes üzleti folyamatokhoz szükséges módon.
- **SENDER\_ DOMAIN** – Adja meg a beszerzési rendelési dokumentumok küldéséhez használt értéket. Ezt az értéket a szállító biztosítja.
- **SENDER\_ IDENTITY** – Adja meg a beszerzési rendelési dokumentumok küldéséhez használt értéket. Ezt az értéket a szállító biztosítja.
- **SHARED\_ SECRET** – Adja meg a beszerzési rendelési dokumentumok küldéséhez használt értéket. Ezt az értéket a szállító biztosítja.
- **STREETLENGTH** – Adja meg azt a számot, amely azt jelzi, hogy a szállító maximálisan hány karaktert fogad el az utcanév értékének. Ha meg van adva egy érték, akkor felülbírálja a **cXML paraméterek** lapon megadott értéket. A rendszer eltávolítja a sortöréseket és a szóközöket, és megpróbálja a Supply Chain Management alkalmazásban alapértelmezett címet az itt megadott számú karakterhez igazítani. A program csonkolja a további karaktereket.
- **TO\_ DOMAIN** – Adja meg a beszerzési rendelési dokumentumok küldéséhez használt értéket. Ezt az értéket a szállító biztosítja.
- **TO\_ IDENTITY** – Adja meg a beszerzési rendelési dokumentumok küldéséhez használt értéket. Ezt az értéket a szállító biztosítja.
- **USERAGENT** – Adjon meg egy értéket a használt rendszer meghatározásához. Például írja be, hogy _Dynamics 365 Supply Chain Management_.
- **VERSION** – Adja meg a cXML verziószámát, ha a szállító ezt az információt kéri. Az alapértelmezett verzió *1.2.008*. Ez a verzió stabil, és a legtöbb szállító elfogadja.
- **RESPONSETEXT** – Adja meg azt a saját szöveget, amelyet a szállítónak a cXML-válasz üzenetbe történő visszaküldéséhez elvár. Ily módon a rendszer képes megjelölni az üzenetet a _Nyugtázott_ értékkel. Ha a válasz nem egyezik meg a normál szöveggel vagy az itt megadott vevő szövegével, akkor a kérést a program _Hibaként_ jelöli meg.
- **RESPONSETEXTSUB** – Ezt a tulajdonságot állítsa _IGAZ_ értékre ha a szállítói válasz szövegében a **RESPONSETEXT** mezőben megadott értékekre kívánja keresni. Előfordulhat például, hogy a szállító hosszú karakterláncot ad vissza, amely a válaszban az „OK” értéket tartalmazza. Ebben az esetben megadhatja az _OK_ értéket a **RESPONSETEXT** mezőben és a **RESPONSETESTSUB** tulajdonságot _IGAZ_ értékre állítva az „OK” kifejezésre bárhol kereshet a válaszban. Ezt követően a rendelést _Nyugtázott_ értékre lehet állítani.
- **CONTENTTYPE** – Egy tipikus katalógus-beállításban nem kell beállítani ezt a tulajdonságot. Ha egy beszerzési rendelés elküldésekor a 500-as kiszolgálóhibát kap a szállító rendszerétől, akkor a tesztelést a tulajdonság _HAMIS_ értékre állításával végezheti el. Ez az érték megváltoztatja a webes kérelem beállítását, és lehetővé teheti, hogy bizonyos platformokra elküldjék az üzenetet.
- **ENABLEHEADERS** – Ezt a tulajdonságot állítsa _IGAZ_ értékre, ha a beszerzési rendeléssel együtt a fejléceket is el kell küldeni. Ezt a tulajdonságot csak akkor kell megadni, ha a szállító igényli. Ha _IGAZ_ értékűre állítja ezt a tulajdonságot , adja meg a szállító által biztosított neveken alapuló további egyéni tulajdonságokat, és adja hozzájuk a _H\__ előtagot. Ilyan például a **H\_ USERID**, **H\_ PASSWORD**, **H\_ RECEIVERID**, and **H\_ ACTIONREQUEST**. A következő egyéni tulajdonságok szerepelnek az alapértelmezett tulajdonságok között:

    - **H\_ USERID** – Ha a kereskedelmi partner azt szeretné, hogya a beszerzési rendelés elküldéséhez szükséges URL-cím részeként egy felhasználói azonosítót küldjön, itt adja meg az értéket.
    - **H\_ USERID** – Ha a kereskedelmi partner azt szeretné, hogya a beszerzési rendelés elküldéséhez szükséges URL-cím részeként egy jelszót is küldjön, itt adja meg az értéket.

- **ENABLEMANUALPO** – Ha ez a tulajdonság _IGAZ_ értékre van állítva, akkor, amikor a felhasználók manuálisan hoznak létre beszerzési rendeléseket (azaz amikor nem egy igénylésből indulnak ki), akkor ezek a beszerzési rendelések öröklik a szállítóhoz tartozó **Beszerzési rendelés küldése cXML-en keresztül** beállítás értékeit. Ha ez a tulajdonság nincs megadva, vagy _HAMIS_ értékre van állítva, akkor a beszerzési rendelés fejlécében a program nem állítja be a **Beszerzési rendelés küldése cXML-en keresztül** lehetőséget a beszerzési rendelések fejlécében. Az igénylésből létrehozott beszerzési rendelések esetében a **Beszerzési rendelés küldése cXML-en keresztül** beállítás mindig a szállítótól lesz örökölve, a tulajdonság beállításától függetlenül. További tudnivalókért lásd a [Szállítói beszerzési rendelések beállítása cXML használatára](#vendor-setup) című részt, a témakör korábbi részében.
- **PUNCHOUTPOONLY** – Ha ez a tulajdonság _IGAZ_ értékre van állítva, akkor csak a PunchOut folyamatból létrehozott beszerzési igénylési sorok esetében lesz beállítva a **Beszerzési rendelés küldése cXML-en keresztül** beállítás a beszerzési rendelés fejlécében. Ezenkívül a beszerzési rendelési sor típusa a beszerzési rendelés minden soránál _Külső katalóguscikk_ kell legyen. Ellenkező esetben a cXML beszerzési rendelés nem hozható létre.
- **PUNCHOUTSHIPTO** – Ha ez a tulajdonság _IGAZ_ értékre van állítva, akkor a rendszer a jogi személy alapértelmezett címét adja hozzá a PunchOut-beállítás kérelemüzenethez, amikor a felhasználó megnyit egy külső katalógust. Ezt a címet **ShipTo** címként adja hozzá a program. A szállítók a **ShipTo** cím használatával jelenítik meg a vállalat helyétől függő árképzést.
- **TRACEPUNCHOUT** – Ezt a tulajdonságot akkor kell _IGAZ_ értékre állítani, ha hibaüzenet jelenik meg, amikor megpróbál egy külső katalógust böngészni az igénylésből. A nyomon követési adatok kitöltése a Supply Chain Management és a szállítói webhely között elküldött **PunchOutSetupRequest** és **PunchOutResponse** üzenetekben történik. Ezt az információt a **cXML-kosárüzenet-napló** lapon tekintheti meg , amelyet a **Külső katalógus beállítása** lapján nyithat meg a problémás szállítói katalógushoz. Ezt a tulajdonságot csak akkor kell _IGAZ_ értékűre kell állítania , ha a hibakeresést végzi, mivel minden PunchOUt művelethez nagy terhelés generál az adatbázisban. A további tudnivalókat lásd a [A cXML kosár-üzenetek naplójának megtekintése a külső katalógus PunchOut esetében](#message-log) című részében, a témakörben később.
- **REPLACENEWLINE** – Állítsa ezt a tulajdonságot _IGAZ_ értékre, ha problémája van, mivel a szállítói rendszer olyan **PunchOutResponse** üzenetet küld, amely sortörés (\\ n) karaktereket tartalmaz. Ez a hiba akkor fordulhat elő, ha a szállítói üzeneteket köztes szoftver vagy beszerzési központ útján elemzik. Ha problémája van egy új szállítói beállítással, a **TRACEPUNCHOUT** tulajdonságot _IGAZ_ értékre kell állítani, hogy megtekintse a **PunchOutResponse** üzenetet, és meghatározza, hogy az XML-címkék sortörési karakterekkel fel vannak-e bontva.
- **POCOMMENTS** – Ezt a tulajdonságot állítsa _IGAZ_ értékre , ha azt szeretné, hogy a cXML dokumentum tartalmazzon megjegyzéseket, amelyek mellékelve vannak a beszerzési rendeléshez a Supply Chain Management alkalmazásban. A melléklet szövege a beszerzési rendelési üzenet fejlécében szereplő megjegyzések között szerepel. Ha további tájékoztatást szeretne arról, hogy a rendszer hogyan választja ki és dolgozza fel ezeket a mellékleteket, tekintse meg ebben a témakörben a [Megjegyzések csatolása egy beszerzési rendelés](#attach-po-notes) című szakaszt.
- **VENDCOMMENTS** – Ezt a tulajdonságot állítsa _IGAZ_ értékre , ha azt szeretné, hogy a cXML dokumentum tartalmazzon megjegyzéseket, amelyek mellékelve vannak a beszerzési rendeléshez a Supply Chain Management alkalmazásban. A melléklet szövege a beszerzési rendelési üzenet fejlécében szereplő megjegyzések között szerepel. Ha további tájékoztatást szeretne arról, hogy a rendszer hogyan választja ki és dolgozza fel ezeket a mellékleteket, tekintse meg a [Megjegyzések csatolása egy beszerzési rendelés](#attach-po-notes) című szakaszt.
- **CLEANAMP** – ezt a tulajdonságot akkor állítsa _IGAZ_ értékre , ha hibaüzenet jelenik meg, amikor egy szállítóhoz megpróbál PunchOut-ot küldeni, és a szállító visszatérési URL-címe helytelenül kódolt és jeleket tartalmaz (\&).
- **PUNCHOUTTZ** – Ezt a tulajdonságot akkor állítsa _IGEN_ értékre, ha a szállító, amellyel dolgozik a Nemzetközi Szabványügyi Szervezet (ISO) 8601 szabványát használja, a PunchOut-kérelem dátumának és időpontjának konkrét érvényesítéséhez. A Supply Chain Management az egyezményes világidő (UTC) dátumát használja a **PunchOutSetupRequest** üzenetben. Ezért ha a tulajdonságot _IGAZ_ értékűre állítja , akkor a *+00:00* hozzá lesz adva a dátum-és időformátumhoz.
- **WMSADDRESSID** – Állítsa ezt a tulajdonságot _IGAZ_ értékre állítása a beszerzési rendelés fejlécében szereplő raktári számnak a szállítónak küldött beszerzési rendelési kérelemben **addressID** értékként való használatára a **ShipTo** címben. Ha a **FIXEDSHIPADDRESSID** tulajdonsághoz megad értéket, az az érték felülírja ezt az értéket. Éppen ezért az egyik tulajdonságot kell használni az **addressID** érték beállításához a dokumentum **ShipTo** címében.
- **PUNCHOUTSHIPTOUSER** – Ez a tulajdonság együtt működik a **PUNCHOUTSHIPTO** tulajdonsággal. Ha a **PUNCHOUTSHIPTO** _IGAZ_ értékre van állítva, akkor a program a jogi személy címét veszi fel. Ha a **PUNCHOUTSHIPTOUSER** _IGAZ_ értékre van állítva, akkor a program a PunchOut felhasználó elsődleges címét használja a jogi személy címének helyett.

### <a name="activate-the-external-catalog"></a>A külső katalógus aktiválása

Ha befejezte az összes tulajdonság beállítását és a külső katalógus egyéb beállításainak konfigurálását, térjen vissza a **Külső katalógusok** lap **Általános** gyorslapára , és állítsa be az **Aktív** beállítást *Igen* értékre.

### <a name="attach-notes-to-a-purchase-order"></a><a name="attach-po-notes"></a> Megjegyzések csatolása beszerzési rendeléshez

Amint azt a [Rendelés tulajdonságainak beállítása](#set-order-properties) szakasz említi , ha azt szeretné, hogy a leszállított cXML tartalmazza a megfelelő beszerzési rendeléshez és/vagy szállítói rekordhoz csatolt megjegyzések szövegét, akkor a külső katalógus beállításaiban a **POCOMMENTS** és/vagy a **VENDCOMMENTS** tulajdonságot is _IGAZ_ értékre állíthatja. Ez a szakasz részletesen bemutatja, hogy a rendszer hogyan választja és dolgozza fel ezeket a mellékleteket, ha használja őket.

A rendszer által keresett megjegyzések típusának beállításához nyissa meg a **Beszerzés és forrás \> Beállítás \> Képernyők a \> Képernyőbeállítások** lehetőséget. Ezután a **Beszerzési rendelés** lapon állítsa be a **Belefoglalandó dokumentumtípus** mezőt arra a megjegyzéstípusra, amelynek hozzáadását lehetővé szeretné tenni. Csak szöveget tartalmazó megjegyzések szerepelnek, a dokumentumok mellékletei nem.

![Képernyőbeállítás lap.](media/cxml-form-setup.png "Képernyőbeállítás lap")

A mellékletek csak akkor lesznek társítva a beszerzési rendeléshez, ha a **Típus** mező értéke a **Belefoglalandó dokumentumtípus** mezőben kiválasztott értékre van állítva , és ha a **Korlátozás** mező a _Külső_ értékre van állítva. Egy beszerzési rendelés mellékleteinek létrehozásához, megtekintéséhez vagy szerkesztéséhez nyissa meg a **Beszerzés és forrás \> Összes beszerzési rendelés** menüpontot, válasszon ki vagy hozzon létre egy beszerzési rendelést, majd válassza ki a **Mellékletek** gombot (gemkapocs szimbólum) a jobb felső sarokban.

![Csatolt melléklet, amely be van állítva a szállítónak való elküldésre.](media/cxml-note-to-vendor.png "Csatolt melléklet, amely be van állítva a szállítónak való elküldésre")

## <a name="view-the-cxml-cart-message-log-for-external-catalog-punchout"></a><a name="message-log"></a> A cXML-kosárüzenetek naplójának megtekintése a külső katalógus PunchOut-hoz

Ha a egy külső katalógushoz a **PunchOut-protokoltípus** értékét _cXML_ értékre állítja be , akkor a rendszer rögzíti a szállítóktól érkező kosarak üzenetnaplóját. Ez a napló a hibaelhárításhoz és egyéb adatcélokhoz használható.

Ha meg szeretné nyitni a külső katalógus naplóját, válassza ki a megfelelő katalógust, majd a művelet ablaktáblán válassza ki a **cXML kosár-üzenetek naplója** lehetőséget. A **cXML-kosár üzenetnapló** lap felsorolja a visszaküldött kossarakat, a kosarakhoz kapcsolódó XML-t, és a sorokat, amelyek a kapcsolódó beszerzési rendelésen lettek létrehozva.

![cXML kosár üzenet-napló lapja.](media/cxml-cart-message-log.png "cXML kosár üzenet-napló lapja")

## <a name="set-the-extrinsic-elements-for-external-catalog-punchout"></a>A külső katalógus PunchOut külső elemeinek megadása

Ha a **Punchout-protokoll típusa** mezőt *cXML* értékre állítja egy külső katalógushoz egyéni külső elemeket adhat hozzá, amelyek a megfelelő helyre lesznek beillesztve a kérelem XML-üzenetébe.

A külső összetevők külső katalógusba történő felvételéhez hajtsa végre az alábbi lépéseket.

1. Ugorjon a **Beszerzés és forrás \> Katalógusok \> Külső katalógusok** pontra.
1. Válassza ki a kívánt katalógust.
1. Válassza az **Üzenet formátuma** gyorslap **Külső elemek** szakaszának **Hozzáadás** parancsát , és adjon hozzá a rácshoz egy sort minden egyes szerepeltetni kívánt külső elemhez. Állítsa be a következő mezőket minden egyes sornál:

    - **Név** – Adjon meg egy nevet az elemnek. Ez az érték lesz az egyes sorokban létrehozott **Külső** XML-elem **név** attribútumának értéke. Általában a szállítóval együttesen kell megegyeznie a külső elem nevéről.
    - **Érték** – Válassza ki az elem értékét. Ez az érték lesz az egyes sorokban létrehozott XML-elem értéke. A következő értékek állnak rendelkezésre:

        - **Felhasználónév** – A PunchOut műveletet elvégző felhasználó neve. Ez a név a Supply Chain Management bejelentkezési neve.
        - **Felhasználó e-mail-címe** – A PunchOut műveletet elvégző felhasználó e-mail-címe. Ez a cím az a cím, amelyet a felhasználó a **Felhasználó beállításai** lap **Fiók** lapján állított be.
        - **Véletlen érték** – Egyedi, véletlen értéket használjon.
        - **Felhasználó teljes neve** – A külső katalógushoz hozzáférő felhasználóhoz társított kapcsolattartó teljes nevét használja.
        - **Keresztnév** – A külső katalógushoz hozzáférő felhasználóhoz társított kapcsolattartó keresztnevét használja.
        - **Utónévtnév** – A külső katalógushoz hozzáférő felhasználóhoz társított kapcsolattartó utónevét használja.
        - **Telefonszám** – A külső katalógushoz hozzáférő felhasználóhoz társított kapcsolattartó elsődleges telefonszámát használja.

![Külső elem beállításai.](media/cxml-extrinsics.png "Külső elem beállításai")

A felhasználó vagy adminisztrátor nem fogja látni a külső elemeket, mert nincsenek hozzáadva, amíg a felhasználó nem végzi el a PunchOut műveletet. A program automatikusan beszúrja a **BuyerCookie** és a **BrowserFromPost** elemek közé a cXML-beállítási üzenetbe. Ezért nem kell manuálisan beállítania azokat az XML-fájlban, amikor beállítja a külső katalógust.

![Az XML-hez hozzáadott külső elemek.](media/cxml-extrinsics-xml.png "Az XML-hez hozzáadott külső elemek")

## <a name="create-and-process-a-purchase-order"></a><a name="create-po"></a> Beszerzési rendelés létrehozása és feldolgozása

Ha egy szállítóhoz beszerzési rendelést hoz létre, akkor a szállítótól örökli a **Beszerzési rendelés küldése cXML-en keresztül** beállítást. A beállítás azonban a beszerzési rendelés **Fejléc** nézetének **Beállítás** gyorslapján továbbra is elérhető, így később szükség szerint módosítható.

![A cXML használatára beállított beszerzési rendelés.](media/cxml-purchase-order.png "A cXML használatára beállított beszerzési rendelés")

Amikor beszerzési rendelést hoz létre egy PunchOut-folyamatból származó beszerzési igénylésből, akkor az összes szükséges soradatot kitölti a rendszer. Ezután a beszerzési rendelés sorait manuálisan is hozzáadhatja, illetve más beszerzési rendelésekből másolhatja. Győződjön meg róla, hogy az összes szükséges mezőt beállítsa. Ezek a kötelező mezők tartalmazzák a külső hivatkozási számot, amely a cXML-üzenetben használt szállítói szám.

![Példa külső hivatkozási számra.](media/cxml-line-details.png "Példa külső hivatkozási számra")

Ha befejezte a beszerzési rendelés összes adatának kitöltését, mindenképpen erősítse meg azt. A program csak a beszerzési rendelés visszaigazolása esetén küld üzenetet. Egy beszerzési rendelés megerősítéséhez a Műveleti ablaktáblán, a **Beszerzés** lapon a **Műveletek** csoportban kattintson a **Megerősítés** elemre a beszerzési rendelés megerősítéséhez. 

A beszerzési rendelés visszaigazolása után a visszaigazolás állapotát a **Beszerzési rendelések visszaigazolása** naplóban lehet megtekinteni. A Műveleti ablaktáblán, a **Beszerzés** lapon a **Naplók** csoportban kattintson a **Beszerzési rendelés visszaigazolások** elemre.

Minden beszerzési rendeléshez tartozhat több visszaigazolás is. Minden visszaigazolást növekményes számmal kell jelölni. A következő ábrán a beszerzési rendelés száma *00000275*, és a visszaigazolásé *00000275-1*. Ez a sorszámozás az Supply Chain Management funkciókat tükrözi, ahol a beszerzési rendelés módosításait, és ennek megfelelően a szállító számára küldendő cXML-üzenet típusát a megerősítés alapján lehet azonosítani. Ahogy az ábra mutatja, hogy a **Beszerzési rendelés visszaigazolása** lap tartalmazza a **Rendelés küldési állapota** és a **Rendelési kérelem szállítói állapota** mezőket is. Ha további tájékoztatást szeretne kapni a lapon megjelenő különböző állapotértékekről, tekintse meg a témakör későbbi, [Beszerzési rendelési kérelmek figyelése](#monitor-po-requests) című szakaszát.

![Beszerzési rendelések visszaigazolása lap.](media/cxml-po-confirmations.png "Beszerzési rendelések visszaigazolása lap")

A dokumentummal kapcsolatos további információk megtekintéséhez válassza ki a rács fölötti a **Beszerzési rendelési kérelem** elemet.

A **beszerzési rendelési kérelem** lap két rácsot tartalmaz. A lap felső részén lévő rácsnak egy rekordja van mindegyik küldésre megjelölt beszerzési rendeléshez. Előfordulhat, hogy a lap alsó részén található **Beszerzési rendelési kérelmek előzményei** lap rácsa több rekordot tartalmaz a kiválasztott beszerzési rendeléshez, hogy jelezze az egyes visszaigazolások állapotát. A következő ábra azt mutatja a 00000275 beszerzési rendelést a felső rácsban és a 00000275-1 dokumentumot **Beszerzési rendelési kérelmek előzményei** lap rácsában.

![Beszerzési rendelési kérelem lap.](media/cxml-po-request.png "Beszerzési rendelési kérelem lap")

Ha a kötegelt feladat be van állítva, és fut, akkor a program elküldi a dokumentumot. A dokumentum elküldését követően megtekintheti az állapot változását. A következő ábrán a **Rendelés küldési állapota** mező _Elküldve_ értékre van állítva. A **rendelési kérelem szállítójának állapota** mező értéke _Nyugtázva_, így jelezve, hogy a szállító megkapta a dokumentumot, és képes volt olvasni és tárolni a rendszerben. A **Beszerzési rendelés előzményei** lap rácsa a dokumentum elküldésének időpontját jeleníti meg. Ha további tájékoztatást szeretne kapni a lapon megjelenő különböző állapotértékekről, tekintse meg a [Beszerzési rendelési kérelmek figyelése](#monitor-po-requests) című szakaszt.

![Állapotüzenetek a beszerzési rendelési kérelem lapon.](media/cxml-po-request-2.png "Állapotüzenetek a beszerzési rendelési kérelem lapon")

## <a name="schedule-the-purchase-order-request-batch-job"></a><a name="po-batch"></a> A beszerzési rendelési kérelem kötegelt feladatának ütemezése

Ha aktiválni szeretné a kötegelt feladatot a beszerzési rendelési kérelmek küldéséhez, nyissa meg a **Beszerzési és forrás \> Beállítás \> cXML-kezelés \> Beszerzési rendelés** lehetőséget majd kattintson a művelet ablaktábla **Beszerzési rendelési kérelem** lapján a **Köteg** csoportban válassza a **Feladat beküldése** elemet, és nyissa meg a **Beszerzési kérelem előkészítése és küldése** párbeszédpanelét. Ezen a párbeszédpanelen beállíthatja az ismétlődést, ugyanúgy, ahogy a Supply Chain Management kötegelt feladataihoz. Válasszon egy intervallumot a rendelési mennyiség alapján. Annak ellenére, hogy percenként is futtathatja a kötegelt feladatot, valószínűleg érdemes a kötegelt feladatokat a munkanap során elküldeni a rendelésfogadási ablakokban, amelyek megfelelnek a szállító napirendjének.

Például a szállítónak van egy szabályzata, amely azt jelzi, hogy az délután 1 óráig beérkezett rendelések aznap kerülnek leszállításra. Ebben az esetben érdemes, lehet reggel néhányszor futtatnia a köteget, hogy kommunikálja a leadott rendeléseit. A fennmaradó rendelések elküldése a következő napon történik. Ez a döntés pusztán üzleti döntés. Áttekintheti, és ennek megfelelően beállíthatja a paramétereket.

A folyamat megkeresi a *Várakozik* állapotú beszerzési rendelési kérelmeket. Ha egy rendelést azonnal el kell küldenie egy szállítónak, akkor kiválaszthatja a **Feladat beküldése** és a **Kötegelt feldolgozás** beállítását *Nem* értékre állíthatja.

## <a name="monitor-purchase-order-requests"></a><a name="monitor-po-requests"></a> Beszerzési rendelési kérelmek figyelése

### <a name="view-the-status-of-a-purchase-order"></a>A beszerzési rendelés állapotának megtekintése

Amikor a cXML keresztül küldendő rendeléseket visszaigazolják, azok _Várakozik_ állapotba kerülnek. Amint azt a [Beszerzési rendelés létrehozása és feldolgozása](#create-po) című szakaszban már ismertettük, a Beszerzési rendelési kérelem lapon megtekintheti a beszerzési rendelés állapotát. Minden beszerzési rendelési kérelem több állapotból eggyel rendelkezhet, attól függően, hogy milyen paramétereket és adatokat tartalmaz. Ez a szakasz a különböző állapottípusokat és azok lehetséges értékeit írja le. Ezek az információk a problémák kezelését és a beszerzési rendelések állapotának megértését segítik.

![Beszerzési rendelés állapota a beszerzési rendelési kérelem lapon.](media/cxml-monitor-po-request.png "Beszerzési rendelés állapota a beszerzési rendelési kérelem lapon")

A **Beszerzési rendelési kérelem** lap felső részén lévő rács a következő állapotokat jelenítheti meg:

- **Rendelés küldési állapota** – Ez a mező a következő értékeket veheti fel:

    - **Várakozás** – A dokumentum elküldésére vár.
    - **Elküldve** – A dokumentum el lett küldve.
    - **Leállítva** – a dokumentum elküldése előtt _Leállított_ értékkel lett megjelölve. (Dokumentum _Leállítva_ értékkel megjelöléséhez a, a **Beszerzési igénylés** lap műveleti paneljén válassza a **Leállítás** parancsot.)
    - **Archív** – a dokumentum már el lett távolítva. (A dokumentum végleges törléséhez **Beszerzési igénylés** lap műveleti paneljén válassza a **Véglegesen töröl** parancsot.)

- **Rendelési kérelem szállítói állapota** – Ez a mező a következő értékeket veheti fel:

    - **Várakozás** – A dokumentum elküldésére vár.
    - **Nyugtázva** – A dokumentumot fogadottként nyugtázta a szállító. A lap alsó részén látható **Válasz XML** lap kiválasztásával megtekintheti a szállító által visszaküldött részletes XML-üzenetet.
    - **Hiba** – A dokumentumot a program elküldte a szállítónak, de hiba történt. A hibaüzenet a lap alsó részén látható **Válasz XML** lap kiválasztásával tekintheti meg.

A **Beszerzési rendelési kérelmek előzményei** rácsa a **Beszerzési rendelési kérelem** lap alján a következő értékeket jelenítheti meg:

- **Rendelési kérelem típusa** – Ez a mező a következő értékeket veheti fel:

    - **Új** – A sor a beszerzési rendelés visszaigazolása után azonnal újként van megjelölve.
    - **Frissítés** – Ha a szállító már elküldte és nyugtázta a visszaigazolást, a következő visszaigazolás _Frissítésként_ lesz megjelölve. A frissítéseket csak akkor küldi el a rendszer, ha a **Beszerzési kérelem frissítéseinek küldése** beállítás *Igen* értékre van állítva a [globális cXML paraméterek](#cxml-parameters) között.
    - **Törlés** – Ha a szállító már elküldte és nyugtázta a visszaigazolást, de a beszerzési rendelés érvénytelenítve van, akkor a rendszer a várakozó visszaigazolást _Törlés_ értékkel jelöli meg. A törléseket csak akkor küldi el a rendszer, ha a **Beszerzési kérelem törlésének küldése** beállítás *Igen* értékre van állítva a [globális cXML paraméterek](#cxml-parameters) között.

- **Kérelem időpontja** – A rendelés-visszaigazolás létrehozásának időpontja. Összehasonlíthatja a kérelem időpontját a rendelési állapot idejével, és meghatározhatja a visszaigazolás és a szállítói nyugtázás közötti időt.
- **Rendelés küldési állapota** – Ez a mező ugyanaz, mint a lap felső részén található **Rendelés küldési állapota** mező. Ez itt meg van ismételve, hogy könnyebben megtekinthesse az állapotot a visszaigazolás szintjén. Ha a **Rendelési kérelem típusa** mező az *Új* értékre van állítva , és a beszerzési rendelést a visszaigazolás elküldése előtt újra megerősítik, a **Rendelés küldési állapota** mező értéke *Archív*.
- **Rendelés állapotának időpontja** – Az az időpont, amikor a beszerzési rendelés előzményrekordját utoljára frissítették. (A frissítések tartalmazzák az állapot változásait.)
- **Rendelési kérelem szállítói állapota** – Ez a mező ugyanaz, mint a lap felső részén található **Rendelési kérelem szállítói állapota** mező. Ez itt meg van ismételve, hogy könnyebben megtekinthesse az állapotot a visszaigazolás szintjén.
- **Újraküldési idő** – Az az időpont, amikor újra beküldték a rekordot.
- **Újraküldések száma** – Az a szám, ahányszor a rekordot újra beküldték. A magas szám több hibát jelez, így jelezheti az ön adatbeállításaival vagy a szállító adatbeállításaival kapcsolatos problémákat.

### <a name="view-the-xml-for-a-purchase-order-request-message"></a>A beszerzési rendelési kérelmek XML-jének megtekintése

A beszerzési rendelési kérelem üzenet XML-jének megtekintéséhez válassza a **Beszerzési rendelési kérelem** lap alján látható **XML-szöveg kérése** lapot. Az ezen a lapon található információk a teszt vagy a hibaellenőrzés során hasznosak lehetnek. Az adatok könnyebb olvashatósága érdekében formázott üzenetként tekinthető meg. Másolja a lap tartalmát egy szövegfájlba, majd tekintse meg egy XML-szerkesztőben.

![XML-szöveg kérése lap.](media/cxml-request-xml-text.png "XML-szöveg kérése lap")

### <a name="view-the-details-of-the-vendor-response"></a>A szállítói válasz részleteinek megtekintése

Ha meg szeretné tekinteni a szállító visszaigazolásának vagy a hibaüzenetnek a tartalmát, válassza ki a **Válasz XML** lapot a **Beszerzési rendelési kérelem** lapjának alján.

![Válasz XML lap.](media/cxml-response-xml.png "Válasz XML lap")

## <a name="additional-resources"></a>További erőforrások

- [Külső katalógus beállítása a PunchOut e-beszerzés számára](set-up-external-catalog-for-punchout.md)
- [Külső katalógus használatának engedélyezése a PunchOut e-beszerzés számára](use-external-catalogs-for-punchout.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]