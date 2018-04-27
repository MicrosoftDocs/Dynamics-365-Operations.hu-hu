---
title: "Termékazonosítók"
description: "Ez a témakör a különféle típusú termékazonosítókkal kapcsolatban tartalmaz tájékoztatást, és bemutatja, hogyan adhat hozzá termékazonosítókat a termékadataihoz."
auhor: cvocph
manager: AnnBe
ms.date: 03/23/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResProductEntityIdentifierCode
audience: Application User, IT Pro
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: conradv
ms.dyn365.ops.version: 7.3
ms.search.validFrom: 2017-12-31
ms.translationtype: HT
ms.sourcegitcommit: 19cc8f92b5bb6d9ddfdc77785e48de17ed005703
ms.openlocfilehash: afd542a652abdf6e45c83a6097dc8f0d36efa905
ms.contentlocale: hu-hu
ms.lasthandoff: 03/23/2018

---

# <a name="product-identifiers"></a>Termékazonosítók 

[!INCLUDE [banner](../includes/banner.md)]

Ez a témakör a különféle típusú termékazonosítókkal kapcsolatban tartalmaz tájékoztatást, és bemutatja, hogyan adhat hozzá termékazonosítókat a termékadataihoz.

Amikor az üzemben vagy a raktárban dolgozik termékekkel a Microsoft Dynamics ERP vagy a Microsoft Dynamics CRM alkalmazásban, a termékek és a termékváltozatok helyes azonosítási stratégiájával kell rendelkeznie.

## <a name="unique-product-numberproduct-id"></a>Egyedi termékszámot/termékazonosító

A Microsoft Dynamics 365 for Finance and Operations rendszerben a termék elsődleges azonosítója a termékszám (azaz az egyedi termékazonosító). Ezt a számot automatikusan létre lehet hozni egy számsorozat alapján, vagy manuálisan társítható egy termékhez. Termékváltozatokhoz a számokat a termékek elnevezési rendszerének sablonja segítségével lehet meghatározni.

Sok esetben a termékszámot eredetileg nem a Finance and Operations rendszerben hozták létre. Ehelyett egy termékciklus-kezelő (PLM) vagy termékadatkezelő (PDM) rendszerben található termékhez kapcsolódik. Ebben az esetben adatentitások használhatók a termékek és a termékváltozatok importálására. A Finance and Operations ezután a számokat az összes műveletben használja.

A Finance and Operations implementációjakor különös figyelmet kell fordítani a termékszámokkal kapcsolatos stratégiára. A jó számozási rendszer javítja a logisztikai folyamatokat, és segít elkerülni a hibákat. A jó termékazonosító legfeljebb 15 karaktert tartalmaz. Ideális esetben kevesebb, mint 10 karakter, és legfeljebb öt besoroló karaktert tartalmaz. Keresési nevek segítségével gyors kereséseket engedélyezhet. A keresési név egy további név, amely egy termék osztályozását képviseli.

A Common Data Service (CDS) használatakor a Finance and Operations termékszám egyben a CDS termékszáma is lesz. A termékváltozatok a CDS-be külön termékként szinkronizálódnak.

## <a name="item-number-and-product-dimensions"></a>Cikkszám és termékdimenziók

A cikkszám az adott jogi személy által használt termékazonosító érték. A cikkszám ideális esetben azonos a termékszámmal. Ha az elnevezési rendszer jogi személyenként eltérő, nehezen követhető lesz a termék az egész ellátási láncon belül, és megterhelő újracímkézési és hivatkozási folyamatokat kell bevezetni. A régebbi verziókkal (azaz a Microsoft Dynamics AX 2009 és korábbi verziói) való kompatibilitás érdekében megőriztük ezt a modellt. Javasoljuk azonban, hogy szüntesse meg a jogi személyek egyéni azonosítóit, amikor csak lehetséges, és helyette az egyedi termékszámot használja elsődleges azonosítóként.

Ezenkívül egy termékváltozat nem azonosítható egyedileg cikkszámmal. Mindig a cikkszám és az alapterméknél megadott összes termékdimenzió kombinációjára van szükség. Ez a követelmény kényelmetlenné válhat, és lelassíthatja az azonosító folyamatokat. Ebből az okból is, azt ajánljuk, hogy inkább használja az egyedi termékszámot a cikkszám helyett, amikor csak lehetséges.

Sok oldal még mindig a cikkszámot és a termékdimenziókat tartalmazza elsődleges azonosítóként. A termékszámok azonban használhatók kereséshez. Az **Értékesítés és marketing** &gt; **Beállítás** &gt; **Keresés** &gt; **Keresési paraméterek** pontban módosíthatja a keresést úgy, hogy elsődleges keresési stratégiaként termékszámokat használjon a cikkszámok helyett. Ha a **Kikeresés engedélyezése termékek kereséséhez** lehetőséget **Igen** értékre állítja, a kikeresés nemcsak az alapterméket, hanem a termékváltozatokat is meg fogja jeleníteni. További információk: [Termékek és termékváltozatok keresése a rendelésbevitel során](search-products-product-variants.md)

Emellett képes lesz keresni és szűrni a termékszámra, a terméknévre és -leírásra, valamint a termékváltozat termékdimenziós azonosítóira. Amikor kiválaszt egy változatot, kiválasztódik a kapcsolódó cikkszám, és az összes cikkdimenzió-azonosító. Emiatt könnyebben lehet megkeresni és kiválasztani a megfelelő változatot. Ez a beállítás különösen ajánlott, ha a termékek elsődleges azonosítójaként a termékváltozatokat és az egyedi termékszámokat használja. Kivétel a divatáru iparág lehet, ahol az üzleti folyamatok gyakran kötelezővé teszik az alap kiválasztását egy változat kiválasztása előtt. Gondosan értékelni kell ezt a lehetőséget, mielőtt megvalósítaná számozási rendszerét.

## <a name="product-name-and-description"></a>Terméknév és -leírás

A termék neve és leírása a termék olvasható azonosítója, és bármilyen nyelven karban lehet tartani. A Finance and Operations kliens alapértelmezés szerint minden termékinformációt az alapértelmezett vállalati nyelven jelenít meg, nem a felhasználó nyelvén. Azonban a rendszer a lefordított termékneveket és leírásokat használja az ügyfelekkel és a gyártókkal való minden kommunikáció során. A fordítások a vevői és szállítói számlák nyelvkódján alapulnak.

Termékváltozatokhoz a termék nevét a termékek elnevezési rendszerének sablonja segítségével lehet létrehozni. Mivel nincs olyan követelmény, hogy a terméknevek egyediek legyenek, több olyan terméket is találhat, amelyek azonos névvel rendelkeznek.

## <a name="product-and-item-search-names"></a>Termék- és cikk-keresési nevek

A Finance and Operations másodlagos keresési nevet kínál a termékekhez és a cikkekhez is (bevezetett termékek). A keresési névnek nem kell egyedinek lennie, és a termék vagy termékváltozat létrehozása után módosítani lehet. Azt ajánljuk, hogy a név keresését a termékek kategóriák szerinti keresésére használja. A keresési nevek gyors kereséseket tesznek lehetővé, különösen az értékesítési és beszerzési folyamatoknál.

A keresési név is tartalmazhat vevői vagy szállítói termékazonosítót, vagy valamilyen más külső termékazonosítót, ha ez a külső azonosító egy termék elsődleges keresési feltétele.

## <a name="external-product-identifiers-customer-and-vendor-identifiers"></a>Külső termékazonosítók (vevői és szállítói azonosítók)

Kiadott termékekhez karbantarthatja a cikkszámokat, a cikkek nevét és a cikkek leírását, amelyeket a vevő vagy szállító használ. A hivatkozások megjelennek a külső dokumentumokon, például az értékesítési rendeléseken, a beszerzési rendeléseken, a csomagjegyzékeken és számlákon. A Finance and Operations jelenlegi verziójában a külső hivatkozások nem szerepelnek az alapvető műveleti oldalakon. Az egyetlen kivétel a szállító cikkszáma. Ez a szám a **Termékinformációk** párbeszédpanelen jelenik meg, ha egy alapértelmezett szállító meg van adva a kiadott termékhez.

A külső termékazonosítók kiadott termék, kiadott termékváltozat, vevő vagy vevőcsoport, szállító vagy szállítócsoport szerint tarthatók karban.

A **Kiadott termékek** oldalon hajtsa végre az alábbi műveletek valamelyikét.

- Vevőknél az **Eladás** lapon a **Kapcsolódó információk** csoportban válassza **Külső cikkleírás** elemet.
- Szállítóknál a **Beszerzés** lapon a **Kapcsolódó információk** csoportban válassza **Külső cikkleírás** elemet.

A **Külső cikkleírások** lapon társítani lehet a vevő vagy szállító cikkszámát a kiadott termékhez. A társítást minden jogi személyhez el kell végezni. Az alábbi adatok rögzítésére van lehetőség: A Finance and Operations aktuális verziójában sajnos kissé félrevezetők a címkék. Ezek a címkék azonban jövőbeli verzióban megváltozhatnak.

| Mező | Megfelelő vevőadatok | Megfelelő szállítói adatok |
|-------|------------------------------------|----------------------------------|
| Külső cikkszám | A vevői cikkszám | A szállító cikkszáma |
| Leírás | A vevő által a cikkhez társított név | A szállító által a cikkhez társított név |
| Külső cikkszöveg | A vevő cikkleírása | A cikk szállítói leírása |

Ha sok vevő vagy szállító használja ugyanazokatat a cikkszámokat (például beszerzési társulás vagy egy kiskereskedelmi csoport esetében), létrehozhat olyan vevői vagy szállítói csoportokat, amelyek egyszerűsítik a külső termékinformációk karbantartását.

- Vevőcsoportokhoz lépjen az **Értékesítés** &gt; **Beállítás** &gt; **Cikkek** &gt; **Külső cikkleírás** elemre a csoportok és a kapcsolódó cikkszámok létrehozásához és karbantartásához. Vevők társításához egy csoporthoz, kattintson a **Kinnlevőségek** &gt; **Vevők** &gt; **Minden vevő** elemre, majd az **Értékesítési rendelés alapértelmezései** gyorslapon adjon meg egy értéket a **Cikk - vevőcsoport** mezőben.
- Szállítócsoportokhoz lépjen a **Beszerzés és forrás** &gt; **Beállítás** &gt; **Külső cikkleírási csoport** elemre a csoportok és a kapcsolódó cikkszámok létrehozásához és karbantartásához. Szállító társításához egy csoporthoz, kattintson a **Kötelezettségek** &gt; **Szállítók** &gt; **Minden szállító** elemre, majd az **Beszerzési rendelés alapértelmezései** gyorslapon adjon meg egy értéket a **Cikk - szállítócsoport** mezőben.
 
## <a name="bar-codes"></a>Vonalkódok

Ha vonalkód-leolvasót szeretne használni a termékek azonosítására, a termékazonosítónak meg kell felelnie a használt vonalkódszabvány követelményeinek. Ezért a vonalkódok általában nem a nyers termékszámot tartalmazzák, hanem egy olyan számot, amelyik kifejezetten a kiválasztott vonalkódtechnológiához jön létre. Vonalkódtípusonként több vonalkód tartható karban. Még azonos vonalkódot is társíthat több termékhez, és kiválaszthatja a tényleges aktív társítást a vonalkód beolvasásakor.

A vonalkódok meghatározása előtt meghatározhat egy vagy több vonalkód-beállítást. A vonalkód-beállítások segítségével ellenőrizhető, hogy a vonalkódok követik-e a szükséges útmutatásokat, és így hatékonyan nyomtathatók és olvashatók be. Adott termékmennyiségekhez speciális vonalkódokat is karbantarthat.

Azt ajánljuk, hogy a vonalkód-beállítást használja a nemzetközi cikkszám (EAN) vagy a globális kereskedelmi cikkszám (GTIN) kódok karbantartására.

A vonalkódok karbantartásához a **Kiadott termékek** oldalon, a **Készletkezelés** lapon, a **Raktár** csoportban, válassza **Vonalkódok lehetőséget**.

## <a name="gtin-codes"></a>GTIN-kódok

Az e-kereskedelemben elengedhetetlen, hogy minden fél közös nyelvet beszéljen, és a termékekre közös azonosítókkal hivatkozzon. Emiatt egyes ágazatok a [GTIN](https://www.gs1.org/id-keys/gtin) rendszerre támaszkodnak: ez egy globális cikkszámrendszer, amelyet a GS1 gondoz.

A Finance and Operations rendszerben azt ajánljuk, hogy a GTIN-t vonalkódként tartsa nyilván. Azonban a **Cikk – GTIN** oldalon is lehetőség van a karbantartására. Az oldal megnyitásához a **Kiadott termékek** oldalon, a **Készletkezelés** lapon, a **Raktár** csoportban, válassza a **GTIN-kódok** lehetőséget. Vegye figyelembe, hogy a GTIN nyilvántartása nem globális számként történik. Ehelyett megőrzése jogi személyenként történik.

A Finance and Operations rendszerben a raktári műveletekben a csomagolási változatok meghatározása adott mértékegységek meghatározásával történik. Például egy cikk lehet darabokban, hatos kötegekben, 18-as tálcákban vagy teljes raklapon tárolva. Ezen csomagolási változatok mindegyikére adott mértékegység kerül meghatározásra. Mivel a GTIN jellemzően egy termék csomagolási egységéhez kapcsolódik, a **Cikk – GTIN** oldalon termékenként és mértékegységenként több GTIN kódot tarthat fenn. Ugyanakkor nem használhatja ugyanazt a GTIN kódot egynél több alkalommal adott jogi személy különböző cikkeihez vagy termékváltozataihoz.

A **GTIN-kódok** karbantartásához a **Kiadott termékek** oldalon, a **Készletkezelés** lapon, a **Raktár** csoportban, válassza **GTIN** lehetőséget.

## <a name="external-codes"></a>Külső kódok

A Finance and Operations programban számos entitás számára adható meg külső kód. Például meghatározhat külső kódokat a termékek és kiadott termékek azonosításához. Ezek a külső kódok statisztikai kódok vagy adókódok társítására használhatók a kiadott termékekkel és kiadott termékváltozatokkal. A külső kódok meghatározása jogi személy és a kód típusa alapján történik. Jogi személy, kódtípus és táblahivatkozás szerint egyedinek kell lennie.

Sajnos nincs olyan szabványos funkció, amely lehetővé teszi a termékek keresését külső kódok szerint.

## <a name="data-entities-that-are-used-to-import-and-export-product-identifiers"></a>Termékazonosítók importálásához és exportálásához használt adatentitások

| Entitásnév | Importazonosítók | Exportazonosítók | Megjegyzések |
|-------------|--------------------|--------------------|----------|
| Termékek V2 | Termékszám, termék keresési neve, termék neve, termékleírás | Termékszám, termék keresési neve, termék neve, termékleírás | Az entitás beállításaitól és a termékszám számsorozatától függően a termékszám automatikusan létrehozható az importálás során. |
| Termékváltozatok | Termékszám, termék keresési neve, termék neve, termékleírás | Termékszám, termék keresési neve, termék neve, termékleírás | A terméknómenklatúra sablonjától függően a termékszám automatikusan létrehozható az importálás során. Azonban bármilyen egyedi termékszám importálható, és a termékszámnak nem kell a termékek elnevezési rendszerének sablonjának szerkezetét követnie. |
| Termékfordítások | Terméknév, termékleírás | Terméknév, termékleírás | Ez az entitás felülír minden nyelvet. Ne feledje, hogy ha egy jogi személy elsődleges nyelvének nevét vagy leírását felülírják, maga a termék neve és leírása is megváltozik. |
| Kiadott termékek V2 | Cikkszám, termékszáma, cikk keresési neve| Cikkszám, termékszám, cikk keresési neve, termék keresési neve, termék neve | Ez az entitás kihívást jelenthet, amikor új kiadott termékek létrehozása során számsorozatokat használnak. Mind a **Cikkszám** számsorozat, mind a **Termékszám** számsorozat hatással vannak. Azonban a **Cikkszám** számsor jogi személyenként érvényes,a **Termékszám** számsor pedig globális. Emiatt nem ajánlott, hogy a **Cikkszám** számsorozatot használja újonnan kiadott termékek telepítésekor. Természetesen ha az entitás meglévő termék kiadásához van használva, a termékszámot meg kell adni az entitásban. További információkhoz lásd a jelen témakör lásd „Termék- és cikkszámsorozatok” részét. |
| Kiadott termékváltozatok | Cikkszám, termékdimenziók, termékszám | Termékszám, termék keresési neve, termék neve, termékleírás, termékdimenziók | A **Termékváltozatok** entitáshoz hasonlóan ez az entitás használható új termékek létrehozására, amelyek vagy követik a termékek elnevezési rendszerének sablonját, vagy saját termékszámokat használnak a változathoz. |
| Vevőkhöz tartozó külső cikkleírás | Vevői cikkszám, vevői-cikk neve, vevő leírása, vevői számla | Vevői cikkszám, vevői-cikk neve, vevő leírása, vevői számla | A vevők egy csoportja (például egy vevőszövetség) egy csoportba vonható össze az **Külső cikkleírásokhoz tartozó vevőcsoportok** entitás segítségével. |
| Szállítókhoz tartozó külső cikkleírás | Szállító cikkszáma, szállító cikkneve, szállító leírása, szállítói számla | Szállító cikkszáma, szállító cikkneve, szállító leírása, szállítói számla | A szállítói egy csoportja (például egy szállítói szövetség vagy iparági szervezet) egy csoportba vonható össze az **Külső cikkleírásokhoz tartozó szállítócsoportok** entitás segítségével. |
| Cikkvonalkód | Vonalkód | Vonalkód | Vegye figyelembe, hogy importáláskor a célrendszerben meghatározott vonalkód-beállítást kell alkalmaznia. Az importált vonalkód-referenciák a vonalkód-beállítással összevetve lesznek érvényesítve, és el lesznek utasítva, ha a vonalkód nem egyezik meg a követelményekkel, amelyek a vonalkód-beállításokban vannak meghatározva. |
| Külső kódok a kiadott termékekhez | Külső kód | Külső kód, külső kódosztályok, cikkszám | A külső kódok jogi személy szerint rendeződnek. Importáláshoz egy meghatározott kódosztályra kell hivatkoznia. Kódosztályok importálására használja a **Külső kódosztályok a kiadott termékekhez** entitást. |
| A kiadott termékváltozatokhoz tartozó külső kódok | Külső kód | Külső kód, külső kódosztályok, cikkszám, termékdimenziók | A külső kódok jogi személy szerint rendeződnek. Importáláshoz egy meghatározott kódosztályra kell hivatkoznia. Kódosztályok importálására használja a **Külső kódosztályok a kiadott termékekhez** entitást. Ez az entitás a termékváltozatokra utal cikkszámát és termékdimenziók szerint. |
| Kiadott termékváltozatok külső kódjai termékszám-azonosító alapján | Külső kód | Külső kód, külső kódosztályok, termékszám | A külső kódok jogi személy szerint rendeződnek. Importáláshoz egy meghatározott kódosztályra kell hivatkoznia. Kódosztályok importálására használja a **Külső kódosztályok a kiadott termékekhez** entitást. Ez az entitás a termékváltozatokra utal a változat termékszáma szerint. (A következő nagyobb kiadásból) |
| GTIN | Nem alkalmazható | Nem alkalmazható | Jelenleg nincs olyan egyedi entitás, amelyet GTIN kódok importálására és exportálására használatos. Azt ajánljuk, hogy helyette használja a **Cikk vonalkódja** entitást. |
| Termékentitás Common Data Service azonosító entitása | Nem alkalmazható | Cikkszám, cikk keresési neve, termék keresési neve, szállítói cikkszám, vevői cikkszám, külső kódok, GTIN kódok, vonalkódok | Ez az entitás összesít minden azonosítót egy adatmodellben úgy, hogy egy illesztőfelület segítségével lehessen könnyedén exportálni az összes azonosítót, az összes kapcsolódó típusukkal együtt. Használja a **Termékentitás azonosító kód** entitást az azonosító kódok és leírások exportálásához. Használja a **Termékentitás azonosítójának hatóköre** entitást egy azonosító további hatóköradatainak exportálásához, például fél, jogi személy, mennyiség vagy egység. |

### <a name="product-and-item-number-sequences"></a>Termék- és cikkszámsorozatok

A Finance and Operations rendszerben két különböző számsorozat adható meg:

- A **Termékszám** számsorozat a globális termékszámhoz
- A **Cikkszám** számsorozata a cikkszámot jelenti, jogi személyenként

> [!NOTE]
> A cikkszámot külön azonosítóként csak akkor célszerű használni, ha áttelepít különböző jogi személyeket különböző forrásokból, amelyek különböző számozási rendszereket használtak. Mindig olyan termékazonosítót kell használnia, amely egyedi minden jogi személy között. Ennek megfelelően kell beállítani a **Kézi** lehetőséget **Igen** beállításra a **Cikkszám** számsorozat esetében. Ily módon a cikkszám követni fogja a termékszámot a létrehozás során. Ha a Finance and Operations nem az új termékszámok fő rendszere, állítsa a **Kézi** lehetőséget **Igen** értékre mind a **Cikkszám**, mind a **Termékszám** számsorozatoknál.

Ha a **Kiadott termék V2** entitást használja termékek létrehozásához, több beállítás van hatással arra, hogy hogyan történik a számsorozatok használata a termékszám és a cikkszám létrehozásához:

- A **Termékszám** számsorozat beállítása
- A **Cikkszám** számsorozat beállítása
- A cikkszám leképezése 
- A termékszám leképezése

Az alábbi táblázat az importálás és a kézi létrehozás eredményeinek áttekintését adja a számsorrend és a mező-hozzárendelési beállítások adott kombinációi esetében.

| Termékszám számsorozat | Cikkszám számsorozata | Cikkszám leképezése | Termékszám leképezése | Entitásimportálás eredménye | Manuális létrehozás eredménye | Összefoglalás |
|--------------------------------|-----------------------------|----------------------------|-------------------------------|-------------------------|----------------------------|-----------|
| Kézi = Nem | Kézi = Nem | Nincs megfeleltetés. | Nincs megfeleltetés. | A termékszámok a **Termékszám** számsorozatot használják. A cikkszámok a **Cikkszám** számsorozatot használják. | A termékszámok a **Termékszám** számsorozatot használják. A cikkszámok a **Cikkszám** számsorozatot használják. | Ezek a beállítások akkor használhatók, ha a termékekhez és a cikkekhez egy másik számra van szüksége. Azonban nem ajánlott, hogy különböző számokat használjon a cikkekhez és a termékekhez. |
| Kézi = Nem | Kézi = Igen | Automatikus létrehozás | Nincs megfeleltetés. | Mind a termékszámok, mind a cikkszámok a **Cikkszám** számsorozatot használják. | Mind a termékszámok, mind a cikkszámok a **Termékszám** számsorozatot használják. | Ezek a beállítások nem ajánlottak. Az importálás és a kézi létrehozás másképp működik. |
| Kézi = Nem | Kézi = Igen | Nincs megfeleltetés. | Nincs megfeleltetés. | Mind a termékszámok, mind a cikkszámok a **Termékszám** számsorozatot használják. | Mind a termékszámok, mind a cikkszámok a **Termékszám** számsorozatot használják. | Ezen beállítások használata akkor javasolt, ha a termékeknek konzisztens automatikus számozásuknak kellene lennie, függetlenül attól, hogy import- vagy kézi létrehozása használatos. |
| Kézi = Igen | Nem alkalmazható | Nem alkalmazható | Automatikus létrehozás | A következő hibaüzenetet kapja: „Number sequence can't be detected.” (Számsorozatot nem lehet észlelni.) | A **Cikkszám** számsorozat alapján | Ez a beállítás nem támogatott az importáláshoz. |

## <a name="product-entity-identifier-export-all-product-identifiers"></a>Termékentitás-azonosító (az összes termék azonosítójának exportálása)

A termékentitás-azonosítómodellt azért hozták létre, hogy a CDS 1.0 kiadását az összes azonosítóval létesíthessék, amelyeket egy termékre való hivatkozásként használnak. A feladat egyszerűsítése érdekében minden azonosító össze van gyűjtve egy globális azonosítótáblába, hogy egy modell szerint legyenek exportálhatók. Ne feledje, hogy a CDS ezen verziója nem használja a termékazonosítók modelljét. Emiatt a **Termékentitás közös adatokszolgáltatási azonosító entitás** entitás és ez a folyamat korlátozott gyakorlati haszonnal rendelkezik, és valószínűleg megváltozik a jövőben.

A termékazonosító tábla globális tábla, amelyet a rendszer a fő jogi személy összes hivatkozási táblájából tölt fel adatokkal, egy ismétlődő kötegelt feladat futtatásával. Választania kell egy jogi személy és egy termékkategória-hierarchiát a globális alaptermék-hatókör meghatározásához. A globális termékazonosító tábla létrehozása olyan termékekre korlátozódik, amelyek kibocsátása a kiválasztott jogi személy számára történik, és a termékhierarchiába tartozó olyan termékekre, amelyek a **Common Data Service** szerepkörben ki vannak választva a termékkategóriák hierarchiájában.

Ez a folyamat azt feltételezi, hogy a termék alapadatainak karbantartása elsősorban egy központi jogi személynél történik. (Azonban a jogi személy lehet egy virtuális jogi személy, amely csak a globális alapadatok karbantartására szolgál.)

Tegye a következőket a környezet konfigurálásához.

1. Válassza ki a kategóriahierarchiát a CDS-hez. A **Kategóriahierarchiához tartozó szerepkör társításai** oldalon, ha a hierarchia nincs társítva a **Közös adatszolgáltatás** szerepkörrel, létre kell hoznia egy új társítást. Válassza ki a **Közös adatszolgáltatás** szerepet, és ezután társítása azt a kategóriahierarchiát, amelyik azt a termékportfóliót képviseli, amelyet szinkronizálni kell a CDS-sel.
2. Válassza ki a jogi személyt a termék globális alapadataihoz. A **Termékinformáció-kezelési paraméterek** oldalon, a **Termékattribútumok** fülön válassza ki a fő vállalatot, ahol a termék- és cikkazonosítók karbantartása elsősorban történik.
3. Adja meg az exportálandó azonosító kódtípusokat és kódokat. Lépjen a **Termékinformációk kezelése** &gt; **Beállítás** &gt; **Termékazonosító kódok** elemre. Az azonosítókód-típusok létrehozásához jelölje be a **Kódok generálása**. A kiválasztott jogi személyben található azonosítók mindegyik típusához kódtípus-bejegyzés jön létre.

    Vegye figyelembe, hogy a vonalkódoknál, minden vonalkód-beállításhoz kódtípus jön létre. Külső kódok esetén minden külső kódosztályhoz kódtípus generálódik.

    Most már karbantarthatja a kódtípusok listáját. A kódot, a nevet és a leírást bármikor módosíthatja. A kódtípusok is törölhetők. A törölt kódtípusok nem használhatók fel a globális termékentitás-azonosító táblázatok kitöltésére.

4. Amikor befejezte a termékazonosító kódtípusok meghatározását, létrehozhatja az azonosítókat a globális táblában a **Termékentitás-azonosítók létrehozása** feladat elindításával a **Termékentitás azonosítókódok** lapon. A feladatot kötegelt módban kell futtatni. Ez a feladatot ismétlődő kötegelt feladatként kell beállítani úgy, hogy a tábla az új bejegyzések alapján legyen feltöltve.

Most már használhatók a **Termékentitás közös adatokszolgáltatási azonosító entitás**, a **Termékentitás azonosító kód** és a **Termékentitás azonosító hatókör** adatentitások az azonosítók exportálásához bármilyen célrendszerbe.

## <a name="related-topic"></a>Kapcsolódó témakör

[Termékek és termékváltozatok keresése a rendelésbevitel során](search-products-product-variants.md)

