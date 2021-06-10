---
title: Mérnöki változatok és mérnöki termékkategóriák
description: Ez a témakör a mérnöki verziók fogalmával kapcsolatban tartalmaz tájékoztatást. A mérnöki verziók gondoskodnak arról, hogy a termék különböző állapotai, valamint az adatok folyamatos és egyértelműek legyenek, és hogy megjeleníthetők legyenek a rendszerben.
author: t-benebo
ms.date: 09/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EngChgLookupDynastring, EngChgProductVersionNumberRule, EngChgEcmProductRoute, EngChgEcmRequestProducts, EngChgEcmProductRoute, EngChgEcmProductPreview,EngChgEcmProductBOMItemIdLookup, EngChgEcmProductBOMConsistOf, EngChgEcmProductCreate, EngChgEcmProductLookup, EngChgProductVersionPrCompany, ngChgProductTypeLookup, EngChgProductType, EngChgProductItemPart, EngChgProductItem, EngChgEcmCategory, EngChgEcmBomDesignerEditBom, EngChgEcmBomDesigner, EngChgEcmBOMCopyDialog
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 3509763c03ecc0e847c72828d14b172401df75b0
ms.sourcegitcommit: 588f8343aaa654309d2ff735fd437dba6acd9d46
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/28/2021
ms.locfileid: "6115145"
---
# <a name="engineering-versions-and-engineering-product-categories"></a>Mérnöki változatok és mérnöki termékkategóriák

[!include [banner](../includes/banner.md)]

A mérnöki termékek a termék életciklusa során több okból is fejlődnek. Előfordulhat például, hogy a termék szervizelhetőségét javító változtatásokat vezetnek be, módosítanak egy összetevőt módosítani, mert a szállító már nem kínálja, reagálnak új információkra, vagy kijavítanak hibákat a kezdeti kialakításban. Számos oka lehet annak, hogy ezeket a változtatásokat egy folyamatban lévő termék részeként kell tárolni úgy, hogy a korábbi adatok felülírása ne történjen meg. Az alábbiakban látható néhány ilyen ok:

- Nyomon szeretné követni a terméket, ahogy gyártásra és leszállításra került a vevőkhöz az előző életciklus-állapotokban.
- A módosítások jóváhagyása és alkalmazása előtt szüksége van egy átfutási időre.
- Minden változtatáshoz egy időbélyegzőt szeretne létrehozni, és azt szeretné, hogy a korábban gyártott termékeket egymástól elkülönítve lehessen kézbesíteni.

A *mérnöki verziók* gondoskodnak arról, hogy a termék különböző állapotai, valamint az adatok folyamatos és egyértelműek legyenek, és hogy megjeleníthetők legyenek a rendszerben. Ez a koncepció segít a konzisztencia fenntartásában, az anyagjegyzék (AJ) lezárásában a termeléshez, kiküszöbölve a változékonyságot, és könnyen azonosíthatóvá téve a módosításokat.

Általában a *kivitel és funkció illeszkedése* szabály határozza meg, hogy a módosításhoz új termék, új verzió vagy meglévő verzió frissítése szükséges-e. A szabály nevében mindhárom kifejezés egy alkatrész egy adott aspektusára utal, amely segít a mérnököknek az alkatrészek és az igények megfelelő egyeztetésében. A kivitel és funkció illeszkedése szabály növeli a tervezési változtatások rugalmasságát, mivel minimális dokumentációra és tervezési költségre van szükség egy alkatrész módosításához, feltéve, hogy a termék illeszkedése, kivitele és funkciója megmarad.

- Az **Illeszkedés** az alkatrész vagy funkció azon képességét teszi, hogy csatlakozzon, kapcsolódjon, vagy összeállítható legyen egy szerelvény egy másik funkciójával vagy részével. Az illeszkedés lehetővé teszi, hogy az alkatrész megfeleljen a szükséges szerelési tűrésnek, hogy hasznos lehessen.
- A **kivitel** egy alkatrész vagy szerelvény jellemzőire vonatkozik, például a külső méretre, a súlyra, a méretre és a vizuális megjelenésre. A kivitel az a szempont, amelyet a leginkább befolyásolnak a mérnök esztétikai döntései. Ez magában foglalja a burkolatot, a vázat és a vezérlőpanelt, amelyek válnak a termék „kifelé” mutató arculatává válnak.
- A **funkció** olyan feltétel, amely akkor teljesül, ha az alkatrész hatékonyan és megbízhatóan hajtja végre a megadott célját. Egy elektronikai termékben például a funkció függhet a használt szilárdtest-összetevőktől, valamint a szoftvertől vagy a belső vezérlőprogramtól. Gyakran a kiválasztott ház jellemzőitől is függhet. A két leggyakoribb oka annak, hogy egy ház nem felel meg a funkció kritériumának, az a rosszul elhelyezett vagy rosszul méretezett portok, és a félrevezető vagy hiányzó címkézés. 

## <a name="engineering-versions"></a>Tervezési verziók

A mérnöki termékek használatakor minden termék rendelkezik legalább egy mérnöki verzióval. A kezdeti mérnöki verzió automatikusan létrejön, amikor létrehoz egy mérnöki terméket. Minden egyes mérnöki verzió tárolja a mérnöki szempontból releváns adatokat, amelyek az adott verzióra jellemzők. Íme néhány példa az ilyen adatokra:

- A verziószám és az előző verziószám (ha van ilyen)
- A tényleges kezdő és a tényleges záró dátumok
- A termékverzió aktív állapota, amely azt jelzi, hogy a verzió kiadható és felhasználható-e a tranzakciókban (További információ: [Termékkészenlét](product-readiness.md).)
- A terméket létrehozó és birtokló mérnöki vállalat (A mérnöki vállalatokkal és az operatív vállalatokkal kapcsolatos további tudnivalókat lásd a [Mérnöki vállalatok és az adatok tulajdonlásának szabályai](engineering-org-data-ownership-rules.md) részben.)
- Kapcsolódó mérnöki dokumentumok, például összeállítási kézikönyv, felhasználói utasítások, képek és hivatkozások
- A mérnöki attribútumok (További információ: [Mérnöki attribútumok és mérnöki attribútumok keresése](engineering-attributes-and-search.md).)
- Anyagjegyzék tervezési termékekhez
- Folyamatszerű gyártással előállított termékekhez használatos képletek
- A mérnöki útvonalak

Ezeket az adatokat egy meglévő verzión frissítheti, vagy létrehozhat egy új verziót egy *mérnöki módosítási rendelés* használatával. (További információ: [A mérnöki termékek módosításának kezelése](engineering-change-management.md).) Ha egy termék új verzióját hozza létre, a rendszer az összes műszaki szempontból releváns adatot átmásolja az adott új verzióra. Ezután módosíthatja az új verzió adatait. Ily módon nyomon követheti az egyes egymást követő verziók konkrét adatait. Az egymást követő mérnöki verziók közötti különbségek összehasonlításához vizsgálja meg a mérnöki módosítási rendelést, amely tartalmazza az összes változást jelző módosítástípusokat.

Mint azt említettük, a kezdeti mérnöki verzió automatikusan létrejön, amikor létrehoz egy mérnöki terméket. Ennek a verziónak a verziószáma a termék mérnöki kategóriájában meghatározott verziószámszabályt követi. A következő verzióra való áttéréshez a terméket sorként kell hozzáadnia egy mérnöki módosítási rendeléshez, és a **Hatás** mezőt *Új verzió* értékre kell állítania. A mérnöki módosítási rendelés tartalmazza az aktuális verzióról a következő verzióra történő módosítás részleteit.

Vegye figyelembe, hogy egy mérnöki termék egyszerre csak egy mérnöki változási rendelésben lehet. Ez a korlátozás biztosítja az adatok pontosságát, és segít elkerülni az átfedéseket vagy az ellentmondásos változásokat a termékben. Azt is vegye figyelembe, hogy a mérnöki módosítási rendelés **Fejléc** nézetének **Mérnök** mezőjében az a mérnök látható, aki felelős a változási rendelésért. Ha a mérnök a rendszerben definiált csapathoz tartozik, akkor a **Felelős** mező a csapat vezetőjét jeleníti meg.

## <a name="track-versions-in-transactions"></a>A tranzakciók verziójának nyomon követése

A mérnöki változáskezelés használatakor a terméktörzsadatok mindig egy vagy több mérnöki verziót tartalmaznak. A mérnöki termékek beállításában kiválaszthatja, hogy a mérnöki verzió része-e a *logisztikai tranzakcióknak* is. (További információkért lásd a [Mérnöki termékkategóriák beállítása](#product-category) szakaszt a témakör későbbi részében.) Ha a logisztikai hatás releváns, az termékenként és vállalatonként eltérő. Néha csak a termék legújabb verzióját használják. Ezért új verzió bevezetésekor az előző verzió már nem használható. Más esetekben az előző verzió szükséges a logisztikai tranzakciókban a következő kihívások leküzdéséhez:

- A logisztikai részlegnek egy termék két darabját kell szállítania egy vevőnek. Ebben az esetben el kell döntenie, hogy két különböző verziót kíván-e vagy engedélyez-e szállítani.
- Később kiderül, hogy probléma merül fel, ami egy adott változáshoz kapcsolódik. Ebben az esetben hasznos lehet pontosan meghatározni, hogy melyik verziót szállították az egyes rendelésekben.
- A vállalatok általában először a régi verziókat szeretnék szállítani, hogy kivonják őket a készletből. Különösen a kis volumenű termékek esetében ez a megközelítés gyakran kezelhető az új verzió hatályossági dátumainak meghatározásával, összevetve az előrejelzésekkel, hogy mikor fog kimerülni a régi verzió készlete. Néha azonban előfordulhat, hogy nem tudja ezt az összehasonlítást végezni, vagy túl magasnak tekintheti a készletszintű előrejelzések bizonytalanságát.

Az a döntés, hogy a verziók láthatóvá váljanak-e a készletben, olyan tényezőktől függ, mint például a korábban említettek, valamint a vállalati gyakorlattól és az egyes vállalatokra jellemző egyéb szempontoktól. Megadhatja a *mérnöki termékkategória* viselkedését. Ezután az adott kategóriából létrehozott összes termékre vonatkozik, minden olyan vállalatra, amelynek a terméket kiadták.

A logisztikai hatással lévő termékek esetében minden tranzakcióhoz meg kell adni a mérnöki verziót. Bár a rendszer a *legújabb aktív verziót* javasolja, választhat a vállalat számára elérhető összes aktív verzió közül. A logisztikai hatással nem rendelkező termékek esetében a tranzakciókhoz nincs megadva a mérnöki verzió. A rendszer azonban a legújabb aktív verziót használja. Ha például hozzáad egy terméket egy gyártási anyagjegyzékhez, a rendszer a legújabb verziót használja, és az alaptervezés futtatásakor a rendszer a legújabb verziót veszi alapul.

## <a name="set-up-engineering-product-categories"></a><a name="product-category"></a>Mérnöki termékkategóriák beállítása

A mérnöki termékkategória alapot biztosít egy adott mérnöki termék létrehozásához. Minden kategória alapértelmezett értékek és házirendek halmazát hozza létre. Ezért amikor létrehoz egy mérnöki terméket, először ki kell választania azt a kategóriát, amelyből létre szeretné hozni.

Vegye figyelembe, hogy egy új kategóriahierarchia-típus (*mérnöki termékhierarchia*) automatikusan be van állítva. A kategóriákat manuálisan is létrehozhatja a **Mérnöki változtatások kezelése \> Beállítás \> Mérnöki termékkategória részletei** részen.

Minden egyes mérnöki termékkategória létrehozza az adott kategória alapján létrehozott mérnöki termékek alapértelmezett viselkedését. Miután létrehozott egy mérnöki terméket, nem módosíthatja annak mérnöki termékkategóriáját. Ha azonban a helytelen kategóriát választja, törölheti a terméket, majd újra létrehozhatja azt.

Műszaki termékkategória létrehozásakor a következő beállításokat nem változtathatja meg:

- Mérnöki vállalat
- Terméktípus
- Termékaltípus
- Termékdimenzió-csoport
- Konfigurációs technológia
- Verziószám szabálya

Más beállítások örökölhetik a mérnöki termékkategóriához beállított alapértelmezett értékeket. A rendszerszabályok szerint azonban ezek az értékek módosíthatók.

A mérnöki termékkategóriák kezeléséhez lépjen a **Mérnöki változtatások kezelése \> Beállítás \> Mérnöki termékkategória részletei** részre. Majd tegye a következők egyikét.

- Új kategória létrehozásához válassza az **Új** lehetőséget a Művelet ablakon, majd állítsa be a mezőket az alábbi alszakaszokban leírtak szerint.
- Meglévő kategória szerkesztéséhez jelölje ki azt a listaablaktáblán, válassza a Művelet ablak **Szerkesztés** parancsát, majd állítsa be a mezőket az alábbi alszakaszokban leírtak szerint.
- Meglévő kategória törléséhez jelölje ki azt a listapanelen, majd válassza a **Törlés** lehetőséget a Művelet panelen.

### <a name="header"></a>Fejléc

Állítsa be a következő mezőket egy mérnöki termékkategória fejlécében.

| Mező | Leírás |
|---|---|
| Név | Adjon egy nevet a mérnöki termékkategóriának. |
| Mérnöki vállalat | Válassza ki azt a mérnöki vállalatot, ahol az ebben a mérnöki termékkategóriában található termékeket létrehozzák, és ahol azokat karbantartják. |

### <a name="details-fasttab"></a>Részletek gyorslap

Állítsa be a következő mezőket egy mérnöki termékkategória **Részletek** gyorslapján.

| Mező | Leírás |
|---|---|
| Terméktípus | Adja meg, hogy a kategória vonatkozik-e a termékekre vagy szolgáltatásokra. |
| Termelés típusa | Ez a mező csak akkor látható, ha engedélyezte a [receptúrák változásának kezelését](manage-formula-changes.md). Válassza ki azt a termelési típust, amelyre ez a tervezési termékkategória vonatkozik:<ul><li>**Tervezési cikk** – ezzel a tervezési kategóriával a tervezési cikkek receptúráinak változásai kezelhetők. A tervezési cikkek receptúrákat használnak. Hasonlítanak a receptúrás cikkekhez, de csak társ- és melléktermékek előállításához használatosak, késztermékekéhez nem. A receptúrák a folyamatszerű gyártás során használatosak.</li><li>**Anyagjegyzék** – ezzel a tervezési kategóriával az olyan tervezési termékek kezelhetők, amelyek nem használnak receptúrát, és jellemzően (de nem feltétlenül) anyagjegyzékeket tartalmaznak.</li><li>**Receptúra** – ezzel a tervezési kategóriával a befejezett termékek receptúráinak változásai kezelhetők. Ezek a cikkek majd rendelkeznek receptúrával, anyagjegyzékkel viszont nem. A receptúrák a folyamatszerű gyártás során használatosak.</li></ul> |
| Tényleges súly | Ez a beállítás csak akkor látható, ha engedélyezte a [receptúrák változásának kezelését](manage-formula-changes.md). Csak akkor érhető el, ha a **Termelés típusa** mező értéke *Tervezési cikk* vagy *Receptúra*. A beállításnál adja meg az *Igen* értéket, ha ezt a tervezési kategóriát a tényleges súly támogatását igénylő cikkek kezelésére szeretné használni. |
| A tranzakciók verziójának nyomon követése | Válassza ki, hogy a termék verzióját minden tranzakcióra rá kell-e bélyegezni (logisztikai hatás). Ha például nyomon követi a verziót a tranzakciókban, minden értékesítési rendelés megmutatja, hogy a termék melyik verzióját értékesítették az adott értékesítési rendelésben. Ha nem követi nyomon a verziót a tranzakciókban, az értékesítési rendelések nem jelenítik meg, hogy melyik verziót értékesítették. Ehelyett mindig a legújabb verziót jelenítik meg.<ul><li>Ha ez a beállítás *Igen*, akkor a termék alapterméke létrejön, és a termék minden verziója a *verzió* termékdimenziót használó változat lesz. A **Termék altípusa** mező automatikusan *Alaptermék* értékre van állítva, és a **Termékdimenzió csoport** mezőben ki kell választania egy termékdimenzió csoportot, ahol a *verzió* dimenzió aktív. Csak azok a termékdimenzió-csoportok jelennek meg, ahol a *verzió* aktív dimenzió. Új termékdimenzió-csoportokat a **Szerkesztés** gombra (ceruza szimbólum) kattintva hozhat létre.</li><li>Ha ez a beállítás *Nem*, a *verzió* termékdimenzió nem lesz használva. Ezután kiválaszthatja, hogy más dimenziókat használó terméket vagy alapterméket szeretne-e létrehozni.</li></ul><p>Ezt a beállítást gyakran használják olyan termékeknél, amelyek költségkülönbséggel rendelkeznek a verziók között, vagy olyan termékeknél, amelyeknél eltérő feltételek vonatkoznak a vevőre. Ezért fontos jelezni, hogy melyik verziót használták az egyes tranzakciókban.</p> |
| Termékaltípus | Válassza ki, hogy a kategóriában lesznek-e termékek vagy alaptermékek. Az alaptermékek esetében termékdimenziókat kell használni.
| Termékdimenzió-csoport | A **Tranzakciók verzióinak nyomon követése** beállítás segít kiválasztani a termék dimenziócsoportját. Ha megadta, hogy nyomon szeretné követni a verziót a tranzakciókban, akkor megjelennek azok a termékdimenzió-csoportok, ahol a *verzió* dimenziót használják. Egyébként csak azok a termékdimenzió-csoportok jelennek meg, ahol a *verzió* dimenzió nincs használatban. |
| Termékéletciklus-állapot létrehozáskor | Állítsa be az alapértelmezett termékéletciklus-állapotot, amellyel egy mérnöki terméknek az első létrehozásakor rendelkeznie kell. További információ: [Termékéletciklus-állapotok és tranzakciók](product-lifecycle-state-transactions.md). |
| Verziószám szabálya | Válassza ki a kategóriára vonatkozó verziószámszabályt:<ul><li>**Manuális** – Minden új verzió verziószámát ön választja ki.</li><li>**Automatikus** – A rendszer a megadott formátum alapján állítja be a verziószámot. A formátum beállításakor használjon egy számjelet (\#) egy számjegye és bármely más karakter esetében egy állandó érték ábrázolására. Ha például a *V-\#\#* formátumot adja meg, az első verzió „V-01”, a második verzió „V-02” lesz, és így tovább.</li><li>**Lista** – A rendszer a következő számot a megadott egyéni értékek előre meghatározott listájából veszi át.</li></ul> |
| Érvényesség kényszerítése | Adja meg, hogy a műszaki verziók érvényességi dátumainak összefüggőnek kell-e lenniük, vagy lehetnek hézagok és átfedések. Ez a beállítás befolyásolja, hogy hogyan használhatja az **Érvényesség kezdete** és az **Érvényesség vége** mezőket az egyes mérnöki verziókhoz, amelyekre a kategória érvényes.<ul><li>Ha ez a beállítás *Igen*, akkor minden verzióhoz meg kell adni egy **Érvényesség kezdete** értéket, és a verziók között sem átfedések, sem hézagok nem engedélyezettek. Az egyes mérnöki verziók dátumtartománya közvetlenül kapcsolódik az előző és a következő mérnöki verzióhoz, ha vannak ilyenek. Ebben a forgatókönyvben mindig a legújabb verziót használja a rendszer, a régebbi verziókat pedig már nem.</li><li>Ha ez a beállítás **Nem**, nincs korlátozás a mérnöki verziók érvényességi dátummezőire vonatkozóan, és az átfedések és a hézagok is megengedettek. Ebben a forgatókönyvben egyszerre több verzió is aktív lehet, és bármilyen aktív verzióval dolgozhat.</li></ul><p>Ez a beállítás a termékverzióhoz kapcsolódó anyagjegyzékekre és útvonalakra is hatással van. További információt a témakör [Anyagjegyzékek és útvonalak összekapcsolása a mérnöki verziókkal](#boms-routes) című szakaszában talál.</p> |
| Számszabály elnevezési rendszerének használata | Állítsa ezt a beállítást *Igen* értékre, ha engedélyezni szeretné a termékszámok számsorozatok, mérnöki attribútumnevek és értékek, valamint szöveges állandók szegmensként történő használatával való definiálására vonatkozó szabályokat. Szabályok létrehozásához vagy módosításához kattintson a **Szerkesztés** gombra. |
| Névszabály elnevezési rendszerének használata | Állítsa ezt a beállítást *Igen* értékre, ha engedélyezni szeretné a nevek mérnöki attribútumnevek, mérnöki attribútumértékek, valamint szöveges állandók szegmensként történő használatával való definiálására vonatkozó szabályokat. Szabályok létrehozásához vagy módosításához kattintson a **Szerkesztés** gombra. |
| Leírási szabály elnevezési rendszerének használata | Állítsa ezt a beállítást *Igen* értékre, ha engedélyezni szeretné a leírás mérnöki attribútumnevek, mérnöki attribútumértékek, valamint szöveges állandók szegmensként történő használatával való definiálására vonatkozó szabályokat. Szabályok létrehozásához vagy módosításához kattintson a **Szerkesztés** gombra. |

### <a name="attributes-fasttab"></a>Attribútumok gyorslap

Az **Attribútumok** gyorslapon lévő rács segítségével állítsa be az ebbe a kategóriába tartozó termékekre vonatkozó mérnöki jellemzőket. A mérnöki attribútumok létrehozásával kapcsolatos további információk: [Mérnöki attribútumok és mérnöki attribútumok keresése](engineering-attributes-and-search.md).

Az **Attribútumok** gyorslapon található gombokkal attribútumokat adhat hozzá, távolíthat el és rendezhet el a rácsban.

Ha módosítja egy mérnöki kategória attribútumainak kiválasztását, és már léteznek az adott kategórián alapuló termékek, el kell döntenie, hogy alkalmazza-e a módosításokat ezekre a termékekre. Ha azt szeretné, hogy a meglévő termékek tükrözzék a módosításokat, válassza a **Meglévő termékek frissítése** lehetőséget az **Attribútumok** gyorslapon.

A rácshoz hozzáadott minden egyes sorhoz állítsa be a következő mezőket.

| Mező | Leírás |
|---|---|
| Név | Válassza ki a hozzáadni kívánt attribútumot. |
| Érték | Válassza ki az attribútum alapértelmezett értékét. |
| Kötelező | *Logikai* típusú attribútumok esetén, ha ez a beállítás *Igen*, a felhasználóknak az attribútumot *Igen* értékre kell állítaniuk. Ha ez a beállítás *Nem*, a felhasználók az attribútumot *Igen* vagy *Nem* beállításra állíthatják. Más adattípusok esetén ennek a beállításnak a beállítása csak tájékoztató. |
| Kötegattribútum | Adja meg, hogy az attribútumot propagálni kell-e a kötegfunkción keresztül. |

### <a name="readiness-policy-fasttab"></a>Készenléti házirend gyorslap

A **Termékkészenléti házirend** mezőben válassza ki az ezen tervezési kategória alapján létrehozott termékekre alkalmazandó készenléti házirendet. További információ: [Termékkészenlét](product-readiness.md).

> [!NOTE]
> A **Termékkészenléti házirend** mező kissé eltérően működik, ha bekapcsolja a *Termék készenléti ellenőrzései* funkciót. (Ezzel a funkcióval a szokásos, \[nem tervezési\] termékekre vonatkozó vonatkozó készenléti házirendek alkalmazhatók.) További információ: [Készenléti házirendek hozzárendelése a szokásos és a tervezési termékekhez](product-readiness.md#assign-policy).

### <a name="release-policy-fasttab"></a>Kiadási házirend gyorslap

A **Termékkiadási házirend** mezőben választhatja ki az ebbe a kategóriába tartozó termékekre vonatkozó kiadási házirendet. További információért lásd: [Termékstruktúrák kiadása](release-product-structure.md)

## <a name="connect-boms-and-routes-to-engineering-versions"></a><a name="boms-routes"></a>Anyagjegyzékek és útvonalak összekapcsolása a mérnöki verziókkal

Az **Érvényesség kikényszerítése** beállítás fontos az anyagjegyzékek és az egyes mérnöki verziókhoz vezető útvonalak csatlakoztatásához. Termékenként több anyagjegyzéket vagy útvonalat csak akkor aktiválhat, ha az alábbi beállítások bármelyikében eltérés van:

- Termékdimenzió
- Mennyiség
- Hely
- Érvényességi dátumok

A mérnöki anyagjegyzékek és az útvonalak abból a mérnöki verzióból jönnek létre, ahol alkalmazzák őket. Ezeket a **Mérnöki vezérlésű** jelölőnégyzetben található jel alapján ismerheti fel. Ha mérnöki anyagjegyzékekkel és útvonalakkal dolgozik, általában nem különböző mennyiségek használatával tervezi meg őket. Emellett általában nem tervez helyenkénti anyagjegyzékeket. Emellett a mérnöki anyagjegyzékek és útvonalak esetében az érvényességi dátumok mindig a mérnöki verzióból származnak. Ezért egy mérnöki verzió, annak anyagjegyzéke és útvonala mind azonos érvényességi dátummal rendelkezik.

Olyan termékek esetében, ahol a *verzió* termékdimenzióját használja (a tranzakciókra gyakorolt logisztikai hatással együtt), a verzió hozzáadódik az anyagjegyzékekhez és az útvonalakhoz is. Ez a viselkedés segít megkülönböztetni az egymást követő verziók anyagjegyzékeit és útvonalait, függetlenül az **Érvényesség kikényszerítése** beállítástól.

Olyan termékek esetében, ahol nem a *verzió* termékdimenzióját használja (a tranzakciókra gyakorolt logisztikai hatás nélkül), a verzió nem adódik hozzá az anyagjegyzékekhez vagy az útvonalakhoz. Ezért nem lesz különbség az egymást követő verziók anyagjegyzékei és útvonalai között. Ebben az esetben erősen ajánlott az **Érvényesség kikényszerítése** beállítás *Igen* értékre való beállítása. Ily módon megakadályozhatja, hogy a mérnöki verziók átfedésben legyenek, és aktiválhatja az újabb verzió anyagjegyzékét és útvonalát anélkül, hogy először inaktiválná az előző verzió anyagjegyzékét és útvonalát. Ha ebben az esetben az **Érvényesség kikényszerítése** beállítást *Igen* értékre állítja, a legújabb verzió aktiválása előtt manuálisan inaktiválnia kell a régebbi verziók anyagjegyzékeit és útvonalait.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
