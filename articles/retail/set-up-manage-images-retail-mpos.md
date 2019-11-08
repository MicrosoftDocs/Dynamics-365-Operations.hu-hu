---
title: Képek beállítása és kezelése a Retail Modern POS (MPOS) esetében
description: Ez a cikk ismerteti a Retail Modern POS (MPOS) rendszerben megjelenő különböző entitások számára a képek beállításának és kezelésének lépéseit.
author: athinesh99
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailChannelProfile, RetailMediaGallery, RetailImages,
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 52851
ms.assetid: 5c21385e-64e0-4091-98fa-6a662eb33010
ms.search.region: global
ms.search.industry: Retail
ms.author: athinesh
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 1776220766984339c7c289f7b55252fb0c0bb2a8
ms.sourcegitcommit: d37fb09101c30858bcb975931b3d8f947d72017b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/10/2019
ms.locfileid: "2570656"
---
# <a name="set-up-and-manage-images-for-retail-modern-pos-mpos"></a>Képek beállítása és kezelése a Retail Modern POS (MPOS) esetében

[!include [banner](includes/banner.md)]

Ez a cikk ismerteti a Retail Modern POS (MPOS) rendszerben megjelenő különböző entitások számára a képek beállításának és kezelésének lépéseit.

## <a name="setting-up-the-media-base-url-and-defining-media-templates-to-configure-the-format-for-image-urls"></a>A média alap URL-cím létrehozása és médiasablonok meghatározása a kép-URL-ek formátumának konfigurálásához.

A képeket, amelyek megjelennek a Retail Modern POS (MPOS) a Retail rendszeren kívül kell szolgáltatni. Általában egy tartalomkezelési rendszer, a tartalomkézbesítési hálózat (CDN) vagy médiaszerver tárolja őket. Ezután a MPOS lekérdezi és kijelzi a képeket a megfelelő entitások, például termékek és katalógusok számára, a cél URL-cím elérésével. Ezen külsőleg tárolt képek lekéréséhez az MPOS a képek helyes URL-formátumát igényli. A képekhez a megfelelő URL-t a **Média alap URL-cím** érték a csatornaprofilban való beállításával és a **Médiasablon definiálása** funkció használatával állíthatja be az entitások számára. Az entitások alcsoportjainál felül is írhatja a szabvány szerinti URL formátumot a **Szerkesztés az Excel programban** funkció használatával.

> [!IMPORTANT]
> A Retail jelenlegi verziójában már nem állíthatja be az URL-formátumot a **Kép** XML attribútum használatával az MPOS számára az **Alapértelmezett** entitások attribútum-csoportjában. Ha ismeri a Microsoft Dynamics AX 2012 R3-at, és már használja a Dynamics 365 Retail jelenlegi verzióját, ellenőrizze, hogy mindig az új **Médiasablon definiálása** funkciót használja a képek beállításához. Ne használja vagy módosítsa a **Kép** attribútumot az entitások **Alapértelmezett** attribútumcsoportjában, beleértve a termékeket is. A képek **Alapértelmezett** attribútum-csoportjában közvetlenül elvégzett módosítások nem fognak megjelenni. Ez a beállítás nem lesz használható a jövőbeli programverzióban.

Az alábbi eljárásokban a képek példaként a Katalógus entitásnál vannak beállítva. Ezen eljárások segítségével garantálhatja, hogy a megfelelő képelérési út legyen implicit módon beállítva az összes katalóguskép számára, amelyek közös útvonalat használnak. Például ha kívülről állított be egy médiakiszolgálót vagy CDN-t, és szeretné, hogy a képek MPOS-ben jelenjenek meg az egy adott áruháznál, a **Média sablon definiálása** funkció segítségével beállíthatja az elérési utat, amelyen keresztül az MPOS elérheti és beolvashatja a képeket.

> [!NOTE]
> Ebben a bemutató adatpéldában a médiakiszolgáló a Retail szerverre van telepítve. Azonban a Dynamics 365 Retail rendszeren kívül bárhova telepítheti.

### <a name="set-up-the-media-base-url-for-a-channel"></a>A média alap URL-cím beállítása egy csatornához

1. Nyissa meg a Retail HQ-portált.
2. Kattintson a **Kiskereskedelem** &gt; **Csatorna beállítása** &gt; **Csatornaprofilok** lehetőségekre.

    [![Navigáció](./media/channel-profile1.png)](./media/channel-profile1.png)

3. A csatornaprofilban, amelyet az üzlet az MPOS-nél használ, frissítse a **Média alap URL-cím** mezőt a médiakiszolgáló vagy a CDN alap URL-címére. Az alap URL-cím az URL-cím első része, amely a különböző entitások esetében az összes képmappánál ugyanaz.

    [![Csatornaprofilok oldal](./media/channel-profile2.png)](./media/channel-profile2.png)

### <a name="define-the-media-template-for-an-entity"></a>A médiasablon meghatározása egy entitáshoz

1. Kattintson a **Kiskereskedelem** &gt; **Katalóguskezelés** &gt; **Katalógusképek** lehetőségekre.
2. A **Katalógusképek** oldalon kattintson a Műveleti ablakra, majd **Médiasablon definiálása** lehetőségre. A **Médiasablon definiálása** párbeszédpanelen, az **Entitás** mezőben a **Katalógus** legyen az alapértelmezett beállítás.
3. A **Média elérési útja** gyorslapon írja be a fennmaradó útvonalat a kép helyéhez. A média elérési útvonala a **LanguageID** lehetőséget támogatja változóként. Például a bemutató adatok esetében létrehozhat egy **Katalógusok** mappát az összes katalóguskép számára a média alap URL-címe alatt a médiaszerverhez (`https://testax3ret.cloud.test.dynamics.com/RetailServer/MediaServer`). Minden egyes nyelvhez felállíthat egy mappát, például en-US vagy fr-FR, és minden mappába bemásolhatja a megfelelő képeket. Ha nem rendelkezik a különböző képekkel a különböző nyelvekhez, akkor kihagyhatja a **LanguageID** változót a mappastruktúrából, és mutathat közvetlenül a katalógusok mappára, amely tartalmazza a katalógusképeket.

    > [!NOTE]
    > A Retail jelenlegi verziója a **{LanguageId}** tokent a Katalógus, Termék és a Kategória entitások esetében támogatja. (A jelenlegi szabvány alapján a **{LanguageID}** token nem támogatott a Vevő és Dolgozó entitások esetében, ez a Microsoft Dynamics AX 6.x. óta van érvényben)

4. Képek esetén a fájlnév formátuma katalógus nevébe van véglegesen kódolva, és nem lehet módosítani. Ezért úgy nevezze át a képeket, hogy azok megfelelő katalógusnévvel rendelkezzenek, ezzel garantálva, hogy az MPOS megfelelően kezeli azokat.
5. A **Fájlkiterjesztés** mezőben válassza ki a várható fájlkiterjesztést, a képek típusától függően. Például a bemutatóadatokhoz a katalógusképek a .jpg kiterjesztéssel vannak beállítva. (A képfájlokat azért is átnevezhetik, hogy legyen katalógusnevük.)
6. Kattintson az **OK** gombra.
7. Annak ellenőrzésére, hogy helyesen mentette-e a médiasablont a képek számára, a **Katalógusképek** lapon kattintson újra a **Médiasablon definiálása** lehetőségre. A sablon ellenőrzéséhez anélkül, hogy bezárná a **Médiasablon definiálása** párbeszédpanelt, a **Kép-URL-címek generálása az Excelbe** gyorslapot használja. Ellenőrizze a kép URL-címének megjelenését, és győződjön meg róla, hogy az URL-cím megfelel a sablon szabványának, amelyet korábban említettünk. A **Médiasablon definiálása** párbeszédpanel implicit módon beállította a képelérési útvonalat az összes katalóguskép számára, amelyek ezt a közös URL-címet használják. Ez az URL-cím az összes katalógusképre vonatkozik, kivéve, ha a felül vannak írva. A kép elérési útjának első része a média alap URL-címből származik, melyet a csatornaprofilban adott meg. Az elérési út fennmaradó része a médiasablonban megadott útvonalból származik. A két rész együttesen adja ki a kép helyének teljes URL-jét. Például egy katalógus a bemutató adatok között a Fabrikam Base Catalog nevet kapta. Emiatt a kép neve Fabrikam Base Catalog.jpg kell, hogy legyen, hogy a sablonban konfigurált katalógusnevet és a .jpg fájlkiterjesztést használjuk. Ebben az esetben az összefűzés után az URL-cím: `https://testax3ret.cloud.test.dynamics.com/RetailServer/MediaServer/Catalogs/en-US/Fabrikam Base Catalog.jpg`.
8. Futtassa le a szinkronizálási feladatokat, hogy az új sablon a csatorna-adatbázisba kerüljön, hogy az MPOS használhassa a sablont a képek eléréséhez.
9. A katalógusképek médiasablonjának frissítéséhez a csatorna oldalon ügyeljen arra, hogy futtassa a **Katalógusfeladat 1150** opciót a **Kiskereskedelmi IT** &gt; **Elosztási ütemezés** opciókból.

    [![Médiasablon párbeszédpanel meghatározása](./media/catalog1.png)](./media/catalog1.png)

## <a name="previewing-an-image-from-the-entity-level"></a>Az entitás szintről kép előzetes megtekintése

1. Az entitás cikk oldalról HQ-ban megtekintheti a kép előnézetét, amely médiasablonból nyert URL-címet használja. Ebben a példában a nyissa meg a megfelelő katalógust, majd a Műveleti ablakban kattintson a **Média** &gt; **Képek** lehetőségekre. A legördülő lista segítségével válassza ki a különböző áruházakat, amelyek különböző csatornaprofilokkal rendelkezhetnek.
2. Egy implicit médiasablon szerkesztéséhez vagy eltávolításához vissza kell térnie a **Médiasablon definiálása** párbeszédpanelen a **Katalógusképek** lapra.
3. A **Hozzáadás** és az **Eltávolítás** gombok használatával manuálisan módosíthatja az adott képhez használt és az implicit sablonon alapuló útvonalat. További tájékoztatásért lásd a [Médiasablon felülírása entitáscikkekhez](#overwriting-the-media-template-for-entity-items) részt a jelen cikk későbbi részében.
4. Miután befejezte egy kép előnézetének megtekintését és a kívánt módosításokat, indítsa el az MPOS-folyamatot a megfelelő üzletnél, és nézze meg, hogy megjelennek-e katalógusképek.

    [![Képek párbeszédpanel](./media/catalog4.png)](./media/catalog4.png)

> [!NOTE]
> Ugyanezt az eljárást használhatja mind az öt támogatott entitás esetében: Dolgozó, Vevő, Katalógus, Kategória és Termékek. A „Katalógustermékek” (a katalógus szintjén beállított termékek) és a „Csatornatermékek” (a csatorna szintjén beállított termékek) a Termékek entitáshoz beállított médiasablont használják. A Termékek médiasablonhoz kiválaszthatja a termékenként megjelenítendő termékképek számát. Ezenfelül beállíthatja az alapértelmezett képet is egy adott termékhez. Ilyen módon elkerülheti az üres képek megjelenítését az MPOS-ben és meghatározhatja, hogy melyik kép legyen az alapértelmezett kép egy termék esetében. Az alábbi példában minden terméknek van öt képe, és az első kép van beállítva alapértelmezett képként. A termékváltozatokat a rendszer ugyanúgy kezeli, mint az alaptermékeket. A képfájl fájlnevének a termékszámon kell alapulnia. Néhány karaktert fel is old a rendszer, míg a fájlnév létrejön. Ezért célszerű ellenőrizni a fájlnevet a **Kép-URL-címek létrehozása az Excel számára** szakasz használatával. Lásd a [Felülírás az Excel Szerkesztés funkciójának használatával](#overwrite-by-using-edit-in-excel) szakaszt a cikk későbbi részében.

## <a name="synchronization-jobs-to-send-a-media-template-to-the-channel-side"></a>Szinkronizálási feladatok egy médiasablon a csatorna oldalra való küldéséhez

Az öt támogatott entitáshoz (Dolgozó, Vevő, Katalógus, Kategória és Termékek), amikor frissíti a **Médiasablon definiálása** párbeszédet egy kép beállításához, győződjön meg arról, hogy futtatja a Katalógus feladatot (1150) a **Kiskereskedelmi IT** &gt; **Elosztási ütemezés** útvonalról. Ez a feladat lehetővé teszi, hogy a frissített médiasablon szinkronizálódjon a csatornához, és hogy az MPOS használja. Miután a következő módosítások valamelyikét végrehajtotta, futtassa a Katalógus feladatot (1150):

- Ha frissíti a Katalóguskép médiasablont a **Katalógusképek** &gt; **Médiasablon definiálása** útvonalon.
- Ha frissíti az Alkalmazottkép médiasablont az **Alkalmazottképek** &gt; **Médiasablon definiálása** útvonalon.
- Ha frissíti a Vevőkép médiasablont a **Vevőkép** &gt; **Médiasablon definiálása** útvonalon.
- Ha frissíti a Termékkép médiasablont a **Katalógusképek** &gt; **Médiasablon definiálása** útvonalon.
- Ha frissíti a Kategóriakép médiasablont a **Kategóriaképek** &gt; **Médiasablon definiálása** útvonalon. A csatornát is közzé kell tennie.

## <a name="overwriting-the-media-template-for-entity-items"></a>A médiasablon felülírása az entitáscikkekhez

Az előző szakaszból tudjuk, hogy egy adott entitás médiasablonja csak egy közös elérési utat támogat. Ez az útvonal a konfigurált média alap URL-címén és a megadott média elérési útján alapszik. Azonban sok esetben a kiskereskedő különböző forrásokból szeretne képeket használni egy entitás cikkeinek egy részénél. Például egy üzlet a képek egyik katalógusára a self-hosted médiaszervert használja, de egy másik csoport esetében más CDN URL-eket használ. Az olyan kép-URL-ek felülírásához, amelyek az entitás szinten lévő entitásképekhez tartozó médiasablonon alapszanak, használhatja az Excelben a Szerkesztés és a Kézi szerkesztés funkciót az **Előnézet** oldalon.

### <a name="overwrite-by-using-edit-in-excel"></a>Felülírás az Excel Szerkesztés funkciójának használatával

1. Kattintson a **Kiskereskedelem** &gt; **Katalóguskezelés** &gt; **Katalógusképek** lehetőségekre.
2. A **Katalógusképek** oldalon kattintson a **Médiasablon definiálása** lehetőségre. A **Médiasablon definiálása** párbeszédpanelen, az **Entitás** mezőben a **Katalógus** legyen kiválasztva.
3. A **Média elérési útvonala** gyorslapon figyelje meg a kép helyét.
4. A **Kép-URL-címek létrehozása az Excel számára** gyorslapon kattintson **Létrehozás** lehetőségre.

    > [!IMPORTANT]
    > Ha megváltozik a médiasablon, rá kell kattintania **Létrehozás** opcióra, mielőtt használhatja a Szerkesztés funkciót az Excelben.

    Megjelenik a kép-URL-címek előnézete, amely az utolsó elmentett médiasablon alapján jött létre.

    [![Képek URL-címeinek létrehozása az Excel gyorslaphoz a Létrehozás kiválasztása után](./media/excel2.png)](./media/excel2.png)

    > [!NOTE]
    > Az Excel számára generált URL-címek a definiált médiasablon útvonalát és konvencióit használják. Ezek a szabályok tartalmazzák a fájlnevekre vonatkozó szabályokat. Az elvárás, hogy a fizikai képeket a Retail rendszeren kívül állította be, és a képek az URL-címeken keresztül érhetők el, melyeket a korábban definiált médiasablonból lehet beolvasni. Ezeket a beolvasott URL-eket az Excel Szerkesztés funkciójával írhatja fölül.

5. Kattintson a **Szerkesztés Excelben** lehetőségre.
6. Miután megnyitotta a Microsoft Excel munkalapot, kattintson a **Szerkesztés engedélyezése** lehetőségre, mikor kéri a program.
7. Mikor kéri a program, kattintson a **Bővítmény megbízható** lehetőségre a jobb oldali ablakban, és várjon a bővítmény telepítésének befejezéséig.

    [![A bővítmény megbízható](./media/excel4.jpg)](./media/excel4.jpg)

8. Ha megjelenik a bejelentkezés, adja meg a hitelesítési adatokat, amelyeket a központba való bejelentkezéshez használt.

    [![Bejelentkezési kérdés](./media/excel5.png)](./media/excel5.png)

9. Bejelentkezés után meg kell jelennie a kép-URL-címek listájának a különböző katalógus-bejegyzésekhez.
10. A különféle entitáscikkek kép-URL-jeinek szerkesztése, hozzáadása és eltávolítása.
11. Az összes entitásnál, kivéve a Termékeket, felülírhatja a kép-URL-címeket. Módosítsa a meglévő kép-URL-t, hogy az új elérési URL-t használja a rendszer a kép eléréséhez, és frissítse a fájlnevet a képfájl új fájlnevével. A fájlnévnek egyedinek kell lennie, hogy garantálja, hogy a rekord egyedi legyen.

    [![Kép-URL-címek felülírása az Excel programban](./media/excel6.jpg)](./media/excel6.jpg)

    > [!NOTE]
    > Ha kép-URL-eket ír felül a Termék entitások esetében az Excel Szerkesztés funkciójának használatával vagy az entitás cikkoldalon, az MPOS mindig az összes médiasablon kép-URL-t mutatja, együtt a felülírt kép-URL-ekkel.

12. Miután befejezte a módosításokat, kattintson a **Közzététel Excelben** lehetőségre egy új, explicit társítás létrehozása céljából.
13. Térjen vissza a HQ-hoz, majd kattintson az **OK** gombra.
14. Futtassa az entitás megfelelő szinkronizálási feladatait, és ellenőrizze az entitáslapon vagy az MPOS-ben az előnézetet.

#### <a name="creating-new-records"></a>Új jelentések létrehozása

Az Excel programban is létrehozhat új rekordokat. Azonban ügyeljen a helyes információk használatára. Például egy új katalógusbejegyzés létrehozásához győződjön meg arról, hogy a katalógus azonosítója és neve helyes, majd adnia kell egy egyedi fájlnevet. Az egyedi fájlnév nagyon fontos, mert az Excel-rekordok egyedisége a közzététele közben lesz megerősítve. Először másolja ki a részleteket abból a katalógusból, amelyhez új rekordot kíván létrehozni, és másolja a rekordot. Csak a fájlnevet és az URL-t kell frissítenie, mivel a többi adat ugyanaz lesz. Termék entitás cikkekhez illő új rekordok létrehozásához ugyanazt az alapvető eljárást kell használni. Az Excel-munkalapról másoljon ki egy létező rekordot annak a terméknek, amelyhez rekordot kíván létrehozni, majd cserélje ki a kép-URL-t és a fájlnevet. Győződjön meg arról, hogy a fájl neve egyedi.

#### <a name="deleting-an-existing-record"></a>Egy létező rekord törlése

Csak a felülírt kép-URL rekordok törölhetők. Miután törlődik egy kép és a szinkronizálás befejeződik, a kép nem fog megjelenni az **Előnézet** lapon vagy az MPOS-ben. A kép-URL rekordok, amelyek a médiasablonból származnak, nem törölhetők, mivel ezek a rekordok mindig, minden alkalommal a médiasablonból származnak.

### <a name="overwrite-from-the-entity-level-preview-page"></a>Felülírás az entitás szintű Előnézet oldalról

A Termékek kivételével minden entitás esetében a kép-URL-t egy adott entitásnál az entitáscikk szintjén írhatja felül, az **Előnézet** lapról. A Termékek esetében a „Katalógusban szereplő termékek” entitáslapot használhatja. Ez a példa bemutatja, hogyan lehet felülírni egy katalógusképet.

1. Kattintson a **Katalógusok** &gt; **Média** &gt; **Képek** opciókra, és válassza ki a frissítendő katalógusképet.
2. Kattintson a **Hozzáadás** lehetőségre, és írja be a kép-URL-t a médiasablon URL-jének felülírására.
3. Ha szeretné megjeleníteni ezt a képet az MPOS-ben a katalógushoz, akkor beállíthatja alapértelmezett képként.
4. Kattintson az **OK** gombra. A kép-URL frissül ehhez a katalógusképhez, és megjelenik az előnézet.

    [![URL frissítve az Új kép párbeszédablakban](./media/preview3.png)](./media/preview3.png)

5. Az összes felülírt kép-URL képi előnézetét megtekintheti a **Katalógusképek** galérialapon.

    [![Katalógusképek galérialapja](./media/preview-4.png)](./media/preview-4.png)

> [!NOTE]
> Jelenleg a galéria nem mutat előnézetet a médiasablon kép-URL-ekhez. A Katalógus, Dolgozó, Vevő és Kategória entitásokhoz, ha a felhasználó expliciten ezen az oldalon keresztül ad meg egy URL-t, ajánlott jelölni, hogy melyik kép az alapértelmezett, mert a Retail szerver kliensek csak egy képet mutatnak Katalógusonként, Vevőnként, Dolgozónként és Kategóriánként. Ha a felhasználó nem ad meg egy alapértelmezett képet, a rendszer határozza meg azt, és elküldi a Kiskereskedelmi szolgáltatás hívójára (MPOS vagy Elektronikus kereskedelem).

### <a name="overwrite-the-image-url-for-catalog-product-images-from-the-preview-page"></a>Felülírja a Katalógustermék képeinek kép-URL-címét az Előnézet oldalból.

A Katalógustermék képeinek kép-URL-jeinek felülírásához az **Előnézet** oldalt kell használni. Az Excel funkcióban nem használhatja a Szerkesztést.

1. Termékképek katalógusszinten való felülírásához jelölje be a katalógust, és válassza ki a terméket, amelynél felül kívánja írni a képet.
2. Kattintson az **Attribútumok** lehetőségre.
3. A következő oldalon válassza ki a **Kép** lehetőséget, majd kattintson a **Szerkesztés** lehetőségre. Az **Előnézet** lap csúszkás párbeszédpanelként jelenik meg.
4. Kattintson a **Hozzáadás** lehetőségre, majd írja felül a kép-URL-t egy új URL-címre.
5. Kattintson az **OK** gombra. Most az új kép az előnézeti képe jelenik meg, és ezt beállíthatja alapértelmezett képként.

    [![Kép előnézete az Új kép párbeszédablakban](./media/cat3.png)](./media/cat3.png)

> [!NOTE]
> A kategóriakép-társítás után közzé kell tennie a csatornát és le kell futtatnia a Csatornafeladatot, hogy a módosítások biztosan a csatorna-adatbázison legyenek közzétéve.

## <a name="setting-up-images-to-appear-in-offline-mode-for-mpos"></a>Képek beállítása az MPOS számára Kapcsolat nélküli módban való megjelenítéshez

Az MPOS-t futtathatja Online módban (ha az MPOS kapcsolódik a Retail szerverhez) vagy Offline üzemmódban (ha nincs Retail szerver vagy nincs hálózati kapcsolat, és a tranzakciók egy helyi offline adatbázisban tárolódnak). Ha az MPOS Offline módban fut, a külső képkiszolgálóról nem tudja elérni a képeket, hogy a Retai szerverről megjelenítse őket, mivel a Retail szerver nem kapcsolódik. Azonban továbbra is állíthat be a képeket, amelyek akkor jelennek meg, ha az MPOS Kapcsolat nélküli módban fut.

### <a name="set-up-product-images-to-appear-in-offline-mode-for-mpos"></a>Képek beállítása, amelyek az MPOS-ben Kapcsolat nélküli módban jelennek meg

A Kapcsolat nélküli módban használandó termékképek úgy állíthatók be, hogy a kívánt fizikai képeket feltölti az alap termékképhez.

1. Kattintson a **Termékinformációk kezelése** &gt; **Termékek** &gt; **Termékek** lehetőségekre.
2. Jelölje ki a terméket, amelyhez be kívánja állítani az offline képet.
3. Kattintson a **Szerkesztés** lehetőségre, majd kattintson a jobb oldali sarokban a nyílra a megfelelő ablak eléréséhez.
4. A **Termékkép** gyorslapon kattintson a **Kép módosítása** lehetőségre, és töltse fel a kiválasztott termékhez Offline módban használandó fizikai képet.
5. Mentés és a képernyő bezárása.
6. Miközben MPOS Online módban van, futtassa a Katalógusfeladatot a HQ-ban, hogy az adatok legalább egyszer el legyenek küldve az offline adatbázisba.
7. Tegye az MPOS-t Offline módba. Megjelenik az adott termékhez a feltöltött kép a HQ-ban.

    [![Termékkép offline módban](./media/offline1.png)](./media/offline1.png)

### <a name="set-up-catalog-category-employee-and-customer-images-to-appear-in-offline-mode-for-mpos"></a>Katalógus, kategória, alkalmazott és vevő képek beállítása az MPOS Kapcsolat nélküli módban való megjelenítésre

Katalógus, kategória, alkalmazott, és vevő képeket, amelyeket Kapcsolat nélküli módban kell használni, úgy lehet beállítani, hogy az adott kép elérési útvonalát hozzá kell adni a galériához, és a kiválasztott képet alapértelmezett képként kell beállítani a kiválasztott entitáshoz.

1. Menjen rá a katalógusra, majd a Műveleti panelen kattintson a **Média** &gt; **Képek** lehetőségekre.
2. Kövesse a lépéseket a [Felülírás az entitás szintű Előnézeti lapról](#overwrite-from-the-entity-level-preview-page) szakaszban, hogy külső URL-címet adhasson hozzá.
3. Jelölje be ezt a képet alapértelmezettként a katalógushoz úgy, hogy kipipálja a Kép jelölőnégyzetét a rácsban.
4. Futtassa le a Katalógusfeladatot. A kép most már az adott katalógushoz Kapcsolat nélküli képként lesz használatos az MPOS-ben.
5. A többi entitás esetében is hasonló folyamatot kövessen, például a Kategória, Alkalmazott és Vevő esetében.

    [![Offline kép](./media/offline2.png)](./media/offline2.png)
