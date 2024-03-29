---
title: Biztosra tervezett rendelések
description: Ez a cikk bemutatja a tervezett rendelések meg kell erősedelét. A tervezett rendelések a megerősítéskor tényleges beszerzési rendelésekké, átmozgatási rendelésekké vagy termelési rendelésekké válnak.
author: t-benebo
ms.date: 08/09/2022
ms.search.form: ReqTransPo, ReqTransFirmLog
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-04-22
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: c2e4294cb54e9ba41467f505e361d5ee45f1f27d
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/03/2022
ms.locfileid: "9740522"
---
# <a name="firm-planned-orders"></a>Biztosra tervezett rendelések

[!include [banner](../../includes/banner.md)]

A tervezett rendeléseket meg kell *erősíteni* (azaz ki kell adni) az alaptervezési folyamat részeként. A tervezett rendelések a megerősítéskor tényleges beszerzési rendelésekké, átmozgatási rendelésekké vagy termelési rendelésekké válnak. Ezek a rendelések ismertek *kiadott rendelésekként* vagy *nyitott rendelésként* is.

Háromféleképpen tudja biztosra tervezni a rendeléseket:

- **Manuális megerősítés** – Meghatározott tervezett rendelések kiválasztása egy listából, majd a folyamat manuális elindítása.
- **Automatikus megerősítés** – Határozzon meg egy alapértelmezett megerősítési időkorlátot a fedezetcsoportokhoz, egyedi cikkekhez, valamint a cikkek és alaptervek kombinációihoz. Ezt követően az alaptervezés futtatásakor a tervezett rendelések automatikusan meg lesznek erősítve, ha a rendelés dátuma a megerősítés adott időkorlátján belül van.
- **Lekérdezésalapú megerősítés** – Lekérdezés meghatározása a tulajdonságaik alapján tervezett rendelések kiválasztásához. Be lehet állítani egy kötegelt feladatot, amely a lekérdezés futtatását és az egyező rendeléseket rendszeres ütemezés szerint megerősíti.

Ez a témakör részletesen ismerteti az egyes metódusokat.

## <a name="enable-the-features-that-are-described-in-this-article"></a><a name="enable-features"></a> Az ebben a cikkben leírt funkciók engedélyezése

A legtöbb tervezett rendelési funkció a Microsoft minden alaptelepítésében elérhető Dynamics 365 Supply Chain Management. A jelen leírásban ismertetett funkciók egy része azonban csak akkor használható, ha be van kapcsolva a Funkciókezelés.

### <a name="turn-parallelized-firming-of-planned-orders-on-or-off"></a>Tervezett rendelések párhuzamos meg- és kikapcsolása

A párhuzamos megerősítés segít felgyorsítni a megerősítés folyamatot a több szálon keresztüli párhuzamosítás révén. Ez a megközelítés akkor lehet hasznos, ha sok tervezett rendelés meg van erősítve. Ennek a funkciónak a *használatához* be kell kapcsolva lennie a rendszer tervezett rendeléseket párhuzamos megrendelő funkciónak. 

Az Ellátásilánc-kezelés 10.0.21-es verziója szerint ez a funkció alapértelmezés szerint be van kapcsolva. A 10.0.25-ös ellátásilánc-kezelésben ez a funkció kötelező, és nem lehet kikapcsolni. Ha 10,0,25-ösnél régebbi verziót futtat, [akkor ezt a funkciót a Funkciókezelés](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)*funkcióval* kapcsolhatja be és kapcsolhatja ki, és a tervezett rendelések párhuzamos meg lehet erősítő szolgáltatását keresi.

### <a name="turn-planned-order-firming-with-filtering-on-or-off"></a>Tervezett rendelés-meg- és szűréssel való meg- és kikapcsolása

A tervezett rendelésmegerősítés szűréssel lehetővé teszi, hogy logikai feltételt határozzon meg a megerősíteni kívánt tervezett rendelések kiválasztásához. Megtekintheti azt is, hogy mely tervezett rendelések lettek kiválasztva, a háttérben futtathatja a folyamatot, és/vagy ütemezheti kötegelt feladatként.

A funkció használatához be kell kapcsolva lennie a rendszeren. Az Ellátásilánc-kezelés 10.0.25-ös verziója szerint a funkció alapértelmezés szerint be van kapcsolva. Az Ellátásilánc-kezelés 10.0.29-es verziója szerint a funkció kötelező, és nem lehet kikapcsolni. Ha 10.0.29-esnél régebbi verziót futtat, *·*[akkor](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) a rendszergazdák be- vagy kikapcsolhatják ezt a funkciót, ha a Funkciókezelés munkaterületén keresi a Tervezett rendelés megingatása szűrési funkciót.

### <a name="turn-auto-firming-for-planning-optimization-on-or-off"></a>A tervezési optimalizálás automatikus automatizációs funkcióának be- és kikapcsolása

Az automatikus megerősítéssel a megerősítés időkorlátja alatt, az Alaptervezési folyamat részeként megerősítheti a tervezett rendeléseket. Az automatikus megerősítés mindig támogatott a Supply Chain Management szolgáltatásba beépített tervezőmotornál. Ahhoz azonban, hogy a tervezési optimalizálás is használni tudja, be kell kapcsolnia a funkciót.

Az Ellátásilánc-kezelés 10.0.21-es verziója szerint ez a funkció alapértelmezés szerint be van kapcsolva. A 10.0.29-es ellátásilánc-kezelésben ez a funkció kötelező, és nem lehet kikapcsolni. Ha 10,0,29-esnél régebbi verziót futtat, [...](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)*akkor* ezt a funkciót a Funkciókezelés funkcióval kapcsolhatja be és kapcsolhatja ki, és a tervezésoptimalizálási funkció automatikus biztosra keresésével kapcsolhatja be és kapcsolhatja ki.

## <a name="manually-firm-planned-orders"></a>Manuálisan biztosra tervezett rendelések

A rendelések manuális biztosra tervezése érdekében keresse meg és válassza ki azokat a tervezett rendeléseket, amelyeket meg kíván erősíteni, majd manuálisan indítsa el a megerősítési folyamatot.

1. [Nyissa meg bármelyik tervezett rendelés listaoldalát](approved-planned-order.md#view-planned-orders).
1. A lista szűréséhez és rendezéséhez használja a **Szűrés** és **Tervezés** mezőt, illetve az oszlopfejléceket, így megtalálhatja a keresett tervezett rendeléseket.
1. A megerősíteni kívánt tervezett rendelés mellett jelölje be a jelölőnégyzetet. Ha meg szeretne erősíteni az oldalon jelenleg felsorolt összes tervezett rendelést (az alkalmazott szűrők alapján), akkor hagyja ki ezt a lépést.
1. A Műveleti ablak fülön válassza a következő gombok valamelyikét:

    - **Megerősítés** – Csak a kiválasztott tervezett rendeléseket erősítse meg.
    - **Az összes megerősítése** – Az oldalon jelenleg felsorolt összes tervezett rendelés megerősítése (az alkalmazott szűrők alapján), függetlenül attól, hogy a jelölőnégyzetek be vannak-e jelölve. Ez a beállítás akkor lehet hasznos, ha sok tervezett rendelést erősít meg.

1. A **Megerősítés** párbeszédpanel **Paraméterek** gyorslapján állítsa be a következő mezőket. (Ezen mezők közül sok az **Alaptervezés paraméterei** lap **Standard frissítés** fülről veszik az alapértelmezett értékeiket.)

    - **Jelölés frissítése** – Válassza ki a megerősített tervezett rendeléseknél alkalmazandó készletjelölési irányelvet.
    - **Hiba esetén a megerősítés leállítása** – Állítsa *Igen* értékre ezt a lehetőséget, ha az összes kiválasztott tervezett rendelés megerősítését meg szeretné állítani, ha hiba történik valamelyiknél. Ezt a beállítást *Nem* értékre kell állítani, ha a **Megerősítés párhuzamosítása** lehetőség *Igen* értékre van állítva.
    - **A firmizes** párhuzamos használata – [*·*](#enable-features) ez a beállítás csak akkor érhető el, ha a rendszer a tervezett rendelések párhuzamos firming funkciója be van kapcsolva, és ha két vagy több tervezett rendelést választott ki megingatásra. Állítsa *Igen* értékre, ha párhuzamosan szeretné futtatni a megerősítési folyamatokat. A párhuzamos megerősítés javíthatja a teljesítményt.
    - **Szálak száma** –[*·*](#enable-features) ez a beállítás csak akkor érhető el, ha a rendszernél be van kapcsolva a tervezett rendelések párhuzamos meggombolása funkció, **·** *és ha a Párhuzamosizálás beállítás Beállítása Igen.* Adja meg a megerősítési folyamat párhuzamosításához használt szálak számát. A beállítás alaptervezésben való használatával kapcsolatban az [Alaptervezés teljesítményének javítása](../master-planning-performance.md#number-of-threads) rész nyújt segítséget.

        > [!NOTE]
        > Ha a **Szálak száma** mezőt *0* (nulla) értékre állítja, azzal növeli az alaptervezés futási idejét. Ezért azt ajánljuk, hogy mindig 0-nál nagyobb értéket adjon meg ebben a mezőben.

    - **Szállítók szerinti csoportosítás** – Állítsa ezt a lehetőséget *Igen* értékre a megerősítés közbeni tervezett beszerzési rendelések csoportosítása és a szállítónként egy beszerzési rendelés létrehozása érdekében. Az a másik lehetőség, hogy minden tervezett rendeléshez létrehoz egy egysoros beszerezési rendelést.
    - **Csoportosítás beszerzői csoportok szerint** – Állítsa ezt a lehetőséget *Igen* értékre a tervezett beszerzési rendelések csoportosításához, és hozzon létre egy a szállítót és a beszerzői csoportot egyesítő beszerzési rendelést. Ez a beállítás csak akkor használható, ha a **Szállítók szerinti csoportosítás** lehetőség *Igen* értékre van állítva.
    - **Beszerzési szerződés szerinti csoportosítás** – Az *Igen* beállítással úgy csoportosíthatja a tervezett beszerzési rendeléseket, hogy ugyanaz a szállító szerepeljen rajtuk, mint a meglévő beszerzési szerződéseken, és beszerzési szerződésenként egy beszerzési rendelést hozhat létre. Ha a **Szállítók szerinti csoportosítás** engedélyezve van, ez a beállítás automatikusan engedélyezve van. A **Beszerzési szerződés szerinti csoportosítás** használatához a **Beszerzési szerződések keresése** beállításnál az *Igen* értéket kell megadni az **Alaptervezés paraméterei** oldalon.
    - **Csoportosítás időszak szerint** (a **Beszerzési rendelések** szakaszban) – Válassza ki azt az időszakot, amely szerint csoportosítani szeretné a tervezett beszerzési rendeléseket. Ez a beállítás csak akkor használható, ha be van jelölve a **Szállítók szerinti csoportosítás** opció is.
    - **Csoportosítás időszak szerint** (az **Átmozgatások** szakaszban) – Válassza ki azt az időszakot, amely szerint csoportosítani szeretné a tervezett átmozgatási rendeléseket. A rendelések a **Raktárból** és a **Raktárba** értékek alapján lesznek csoportosítva.

    > [!NOTE]
    > A "CSOPORTOSÍTÁS SZERINT" minden beállítás esetén a rendszer a tervezett rendeléseket a csoportosításból származó egyetlen beszerzési rendelés sorára alakítja át.

    ![Paraméterek gyorslap a Megerősítés párbeszédpanelben.](./media/manual-firming.png "Paraméterek gyorslap a Megerősítés párbeszédpanelben")

1. A **Futtatás a háttérben** gyorslapon úgy állítsa be a feladatot, hogy kötegelt módban fusson. A manuális megerősítésnél azonban nincs értelme ismétlődő ütemezést beállítani. A mezők ugyanúgy működnek, mint a Supply Chain Management más, [háttérben futó feladattípusai](../../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md). A manuális megerősítéshez azonban a kötegelt feladat csak az aktuálisan kiválasztott tervezett rendeléseket fogja feldolgozni. Nem fog feldolgozni olyan rendeléseket, amelyek megfelelnek a lapon aktuálisan alkalmazott szűrőknek.
1. Az **OK** gombra kattintva alkalmazza a beállításokat, és hozzon létre megerősített rendeléseket.

## <a name="auto-firm-planned-orders"></a>Automatikusan biztosra tervezett rendelések

Az automatikus megerősítéssel az Alaptervezési folyamat részeként megerősítheti a tervezett rendeléseket. Meghatározhat egy alapértelmezett megerősítési időkorlátot a fedezetcsoportokhoz, egyedi cikkekhez, valamint a cikkek és alaptervek kombinációihoz. Ezt követően az alaptervezés futtatásakor a tervezett rendelések automatikusan meg lesznek erősítve, ha a rendelés dátuma a megerősítés adott időkorlátján belül van. A tervezési optimalizálás és az elavult alaptervezési motor által létrehozott tervezett rendelések másképp kezelik a rendelés dátumát (azaz a kezdő dátumot).

> [!NOTE]
> A tervezett beszerzési rendelések automatikus megerősítése csak akkor lehetséges, ha a cikkek társítva vannak a szállítóhoz.
> 
> A megerősített származtatott rendelések (azaz alvállalkozói beszerzési rendelések) *Ellenőrzés alatt* állapottal jelennek meg, ha a változás követése be van kapcsolva.

> [!IMPORTANT]
> Mielőtt az ebben a szakaszban ismertetett funkció felhasználható lenne a tervezési optimalizálással, [*·*](#enable-features) a rendszernek be kell kapcsolva lennie a tervezési optimalizálási funkciónak az első részében ismertetett módon. Az automatikus tervezés mindig használható az elavult alaptervezési motorral.

### <a name="auto-firming-with-planning-optimization-vs-the-deprecated-master-planning-engine"></a>Automatikus firming a tervezési optimalizálással és az elavult alaptervezési motorral

A tervezési optimalizálás és az elavult alaptervezési motor egyaránt használható a tervezett rendelések automatikus automatizálására. Vannak azonban fontos eltérések. Például a tervezési optimalizálás a rendelésdátum (vagyis a kezdő dátum) alapján határozza meg, hogy mely tervezett rendeléseket kell meghatározni, míg az elavult alaptervezési motor a szükségletdátum (vagyis a záró dátum) alapján határozza meg. Az alábbi táblázat összegzi a különbségeket.

| Szolgáltatás | Tervezési optimalizálás | Elavult alaptervezési motor |
|---|---|---|
| **Kiindulási dátum** | Az automatikus megerősítés a rendelés dátuma (kezdő dátum) alapján történik. | Az automatikus megerősítés a követelmény dátuma (záró dátum) alapján történik. |
| **Átfutási idő** | Mivel a rendelés dátuma (kezdő dátum) indítja a megerősítést, nem kell figyelembe vennie az átfutási időt a megerősítési időkorlát részeként. | Ha biztosítani szeretné, hogy a rendelések időben meg legyenek erősítve, a megerősítés időtartamának hosszabbnak kell lennie, mint az átfutási idő. |
| **Rendelések az aktuális hétre** | Az összes olyan rendelés megerősítéséhez, amely az aktuális hét során kezdődik, a megerősítési időkorlátnak egy hétnek kell lennie. | Az összes olyan rendelés megerősítésének, amely az aktuális hét során kezdődik, a megerősítési időkorlátjának az átfutási idő plusz egy hétnek kell lennie. |

### <a name="set-up-auto-firming-and-the-firming-time-fence"></a>Automatikus megerősítés és a megerősítés időkorlátjának beállítása

Az automatikus megerősítés úgy kapcsolhatja be, hogy a megfelelő fedezeti beállításokhoz egy, a későbbiekben ismertetett automatikus megerősítési időkorlátot rendel. Ha a fedezeti beállításoknál nincs beállítva az automatikus megerősítés, vagy ha a tervezés egy bizonyos oldalról kezdődik, például egy kiadott termék **Nettó követelmény** lapjáról, akkor a program kihagyja az automatikus megerősítési folyamatot.

Az automatikus megerősítés csoportosítási és jelölési beállításai az **Alaptervezési paraméterek** oldal **Standard frissítés** lapján megadott értékeket veheti át.

Az automatikus megerősítés időkorlátját a megfelelő fedezeti beállításoknál megadott számú nap határozza meg. Az automatikus megerősítést bekapcsolni és a megerősítési időkorlátot szabályozni a következő módokon lehet:

- A fedezeti csoport alapértelmezett megerősítési időkorlátjának megadásához nyissa meg az **Alaptervezés \> Beállítás \> Fedezet \> Fedezeti csoportok**, és válasszon ki egy fedezeti csoportot. Ezután a **Egyéb** gyorslap **automatikus megerősítési időkorlátja (nap)** mezőjébe írja be a napok számát.
- Ha felül kell írni a fedezeti csoporthoz meghatározott, egy adott cikkhez megadott időkorlátot, akkor menjen a **Termékinformáció kezelése \> Kiadott termékek** lehetőségre. A Műveleti ablaktáblán válassza a **Tervezés** elemet, majd a **Cikkfedezet** lehetőséget. Az **Általános** lapon jelölje be az **Időkorlát felülbírálása** elemet, majd az **Automatikus megerősítés időkorlátja (nap)** mezőben adja meg a napok számát.
- Ha felül szeretné írni a fedezeti csoporthoz tartozó megerősítési időkorlátot és az adott alaptervezéshez tartozó cikkfedezetet, lépjen az **Alaptervezés \> Beállítás \> Alaptervek** pontra, és válasszon alaptervet. Ezután az **Időkorlát napokban** gyorslapon állítsa a **Megerősítés** lehetőséget *Igen* értékre, majd adja meg a napok számát.

Ha az összes korábban említett időkorlátot *0* (nulla) értékre állítja, az automatikus megerősítés ténylegesen le lesz tiltva a vonatkozó fedezett cikkeknél.

## <a name="firm-planned-orders-by-using-a-query"></a>Biztosra tervezett rendelések lekérdezés használatával

A lekérdezésalapú megerősítés lehetővé teszi a megerősítés előre meghatározott feltételek alapján történő tervezését. Az automatikus megerősítéstől eltérően a lekérdezésalapú megerősítés lehetővé teszi a rendelések különböző alkészleteinek automatikus, időben történő megerősítését. Ezenkívül a manuális és automatizált műveletek használatával is meg lehet erősíteni a különféle típusú tervezett rendeléseket. Megtekintheti azt is, hogy mely megerősített rendelések vannak kiválasztva a saját beállításai alapján. Ebből következően megerősítheti, hogy a választás megfelel-e az elvárásainak.

Az automatikus és a lekérdezésen alapuló megerősítésekkel kombinálhatja az automatikus megerősítéseket. Egy lekérdezésalapú megerősítési feladathoz például egy olyan előre hozott időkorlát tartozik, amely hosszabb, mint a megegyező automatikus megerősítési fedezett konfiguráció időkorlátja. Emiatt a lekérdezésalapú megerősítés az automatikus megerősítés előtt feldolgozhatja a tervezett rendeléseket. Ezt a viselkedést kihasználhatja, ha az egyes szállítók rendeléseit másképp ütemezi, mint a más szállítóktól származó hasonló termékek rendeléseit.

> [!IMPORTANT]
> Az ebben a részben [*·*](#enable-features) ismertetett funkció használata előtt a Tervezett rendelések szűrési funkcióját be kell kapcsolva a rendszeren a cikk elején ismertetettek szerint.

A rendelések lekérdezésen alapuló megerősítési folyamattal való biztosra tervezéséhez kövesse az alábbi lépéseket.

1. Menjen az **Alaptervezés \> Alaptervezés \> Futtatás \> Tervezett rendelés megerősítése** pontra.
1. Állítsa be az alapvető feldolgozási, jelölési és csoportosítási beállításokat a **Paraméterek** gyorspanel **Tervezett rendelés megerősítése** párbeszédpanelén. Ezek a lehetőségek pont úgy működnek, mint a **Megerősítés** párbeszédpanelen. (A leírásokat az előző szakaszban találja.) Ezután a **Terv** szakaszban állítsa be a **Tervezett rendelés megerősítése** egyedi mezőit:

    - **Terv** – Válassza ki azt az alaptervet, amelyet a jelen lekérdezés során talált tervezett rendeléseknél alkalmazni kell.
    - **Időkorlát napjainak megerősítése a jövőben** – Válassza ki, hogy az alaptervezés alapján a jövőben mennyire előretekintve kell számítani a különböző igényeket és egyéb szempontokat.
    - **Időkorlát napjainak megerősítése a múltban** – Válassza ki, hogy az alaptervezés alapján a múltban mennyire előretekintve kell számítani a különböző igényeket és egyéb szempontokat.

    ![Paraméterek gyorslap a Tervezett rendelés megerősítése párbeszédpanelben.](./media/planned-order-firming-main-1.png "Paraméterek gyorslap a Tervezett rendelés megerősítése párbeszédpanelben")

1. Annak megadásához, hogy mely rekordok szerepeljenek a rendelésben, válassza ki a **Szűrő** gombot a **Belefoglalandó rekordok** gyorslapon. Megjelenik egy standard lekérdezési párbeszédpanel, ahol meghatározhatja a kiválasztási feltételeket, a rendezési feltételeket és az illesztéseket. A mezők ugyanúgy működnek, mint a Supply Chain Management más lekérdezéstípusai. Az alábbi mezők írásvédettek, és a lekérdezéshez kapcsolódó értékeket is megmutatja.

    ![Belefoglalandó rekordok gyorslap a Tervezett rendelés megerősítése párbeszédpanelben.](./media/planned-order-firming-main-2.png "Belefoglalandó rekordok gyorslap a Tervezett rendelés megerősítése párbeszédpanelben")

1. Az **Előzetes verzió** kiválasztásával megtekintheti az eddig megadott beállításoknak megfelelő megerősített rendelés tartalmát. A tervezett rendelések listája megerősítése üzenetként fog megjelenni. Ezután a szükséges beállításokat addig módosíthatja, amíg az előzetes verzióban meg nem jelenik a megerősített rendelés.

    ![Példa a megerősített rendelés előzetes verziójára.](./media/planned-order-firming-preview.png "Példa a megerősített rendelés előzetes verziójára")

    > [!WARNING]
    > Ez a funkció a szűrési feltételeknek megfelelő összes tervezett rendelést meg fogja erősíteni. A tervezett rendelések nem kritikus megerősítése miatt több nem kívánt beszerzési, átmozgatási és termelési rendelést kell létrehozni. Mielőtt folytatja, mindig az **Előzetes verzió** gombra kattintva ellenőrizze a szerepeltetni kívánt rekordokat.

1. A **Futtatás a háttérben** gyorslapon úgy állítsa be a feladatot, hogy kötegelt módban fusson, és/vagy állítson be egy jelenlegi ütemezést. A mezők ugyanúgy működnek, mint a Supply Chain Management más, [háttérben futó feladattípusai](../../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md).
1. Az **OK** gombra kattintva alkalmazza a beállításokat, és hozzon létre megerősített rendeléseket.

## <a name="track-firmed-orders"></a>Megerősített rendelések követése

A meg nem erősített tervezett rendelések követéséhez hajtsa végre a következő lépéseket.

1. [Nyissa meg bármelyik tervezett rendelés listaoldalát](approved-planned-order.md#view-planned-orders).
1. Nyissa meg vagy válassza ki a követni kívánt tervezett rendelést.
1. A Művelet ablaktábla **Nézet** lapjának **Nézet** csoportjában válassza a **Megerősítési előzmények** elemet.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
