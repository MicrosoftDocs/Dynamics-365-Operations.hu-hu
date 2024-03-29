---
title: Commerce-katalógusok létrehozása B2B webhelyekhez
description: Ez a témakör azt ismerteti, hogyan lehet kereskedelmi katalógusokat létrehozni a Microsoft Dynamics 365 Commerce vállalathoz tartozó (B2B) webhelyek számára.
author: ashishmsft
ms.date: 07/11/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2022-02-28
ms.openlocfilehash: 7d4ed3e2a76924c2c3c0ba55e21ba648e8da7b76
ms.sourcegitcommit: d1491362421bf2fcf72a81dc2dc2d13d3b98122b
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/11/2022
ms.locfileid: "9136826"
---
# <a name="create-commerce-catalogs-for-b2b-sites"></a>Commerce-katalógusok létrehozása B2B webhelyekhez

[!include [banner](includes/banner.md)]

Ez a témakör azt ismerteti, hogyan lehet kereskedelmi termékkatalógusokat létrehozni a Microsoft Dynamics 365 Commerce vállalathoz tartozó (B2B) webhelyek számára. A B2B webhelyek commerce katalógusai gyakran feltett kérdésekre adott válaszokkal [kapcsolatban lásd a Commerce Catalogs for B2B FAQ (Gyakori kérdések) című témakört](catalogs-b2b-sites-FAQ.md).

> [!NOTE]
> Ez a cikk a Dynamics 365 Commerce 10.0.27-es és későbbi verziókra vonatkozik.

A Commerce katalógusok segítségével azonosíthatja a B2B online áruházakban kínálni kívánt termékeket. Katalógus létrehozása esetén azonosítja azokat az online áruházakat, amelyekben a termékek felkínálják, hozzáadja a szerepelni kívánt termékeket, és árusítási részletek hozzáadásával javítja a termék kínálatát. Minden B2B online áruházhoz több katalógust is létrehozhat, amint azt az alábbi ábra mutatja.

![Kereskedelmi termékkatalógusok előnézete](./media/Commerce_Catalogs.png)

A kereskedelmi termékkatalógusokkal a következő információkat lehet meghatározni:

- **Katalógustípus** – az érték konfigurálása **B2B típusként**. Megadhatja a B2B katalógusspecifikus tulajdonságokat, például a navigációs hierarchiát, a vevőhierarchiát és a katalógus attribútum-metaadatait. 
- **Katalógusspecifikus navigációs hierarchia** – a szervezetek egyedi kategóriastruktúrát hozhatnak létre az adott katalógushoz.
- **Katalógusspecifikus attribútum-metaadatok** – az attribútumok egy termék részletes adatait tartalmazzák. Ha attribútumokat rendel a navigációs hierarchia egy kategóriájához, az adott kategóriához rendelt termékek szintjén meghatározhatja az attribútumok értékeit. A szervezetek ezután a következő feladatokat fejezheti be:

    - Katalógusspecifikus attribútumértékek meghatározása.
    - Az attribútumok láthatóságának szabályozása katalógusszinten.
    - Az adott katalógushoz tartozó finomítók kiválasztása.

- **Csatornák** – a szervezetek egy katalógushoz több B2B online csatornát is társíthat. A katalógusok teljes terméktámogatása jelenleg csak a B2B online áruházakban érhető el.
- **Vevői hierarchiák** – egy adott B2B csatorna esetén a szervezetek egy adott katalógust elérhetővé tudnak tenni a kiválasztott B2B partnerek számára, az adott katalógushoz vevőhierarchiák társításával.
- **Árcsoportok** – az adott katalógusra jellemző árakat és promóciókat konfigurálhatja. Ez a képesség a B2B-csatorna katalógusának meghatározásának alapvető oka. A katalógusok árcsoportja lehetővé teszi a szervezetek számára, hogy termékeket tegyenek elérhetővé a tervezett B2B szervezetek számára, és alkalmazzák a preferált árképzést és engedményeket. A konfigurált katalógusból rendelést vásárló B2B vevők a Commerce B2B webhelyre való bejelentkezés után különleges árakat és promóciókat kaphatnak. Katalógusspecifikus árak konfigurálása **érdekében** **válassza** ki az Árcsoportokat a Katalógusok lapon, ha egy vagy több árcsoportot a katalógushoz csatol. A katalógusból vevői rendelés esetén a rendszer az azonos árcsoporthoz kapcsolt valamennyi kereskedelmi megállapodást, árkorrekció-naplót és speciális engedményt alkalmazza. (Az speciális engedmények közé tartoznak a küszöbérték-, mennyiség- és kombinációs engedmények.) Az árcsoportokkal kapcsolatos további tudnivalókat lásd: [Árcsoportok](price-management.md#price-groups).

> [!NOTE]
> Ez a funkció a Dynamics 365 Commerce 10.0.27-es verziótól indul. Ha katalógusspecifikus konfigurációkat, például navigációs hierarchiákat és vevők hierarchiáját szeretné konfigurálni a Commerce Headquarters alkalmazásban, **kattintson a Szolgáltatáskezelés** **\>\>** munkaterületének kezelése képernyőre, **engedélyezze több katalógus használatát a kiskereskedelmi csatornák szolgáltatásban,** majd futtassa a 1110 CDX-feladatot.**·** Ha engedélyezi ezt a funkciót, a Katalógusok lapon az összes, POS-üzletekhez **vagy hívásközponthoz használt katalógus katalógustípus = B2C** **lesz megjelölve**. Csak a katalógustípusként **megjelölt meglévő és új katalógusok – B2C** – vonatkoznak a POS-üzletekre és a hívásközpontra. 

## <a name="b2b-catalog-process-flow"></a>B2B katalógus folyamatábra

A katalógusok létrehozásának és feldolgozásának folyamata négy általános lépésből áll. Minden lépés részletesen le van ásva a következő szakaszban.

> [!NOTE]
> Mielőtt továbblép, győződjön meg róla, hogy a **katalógus katalógustípusként van megjelölve = B2B**.

1. **[Konfiguráció](#configure-the-catalog)**

    - A navigációs hierarchia társítása
    - Adja meg az érvényességi időt és a lejárati dátumokat, ha vannak ilyen dátumok.
    - Termékek hozzáadása és kategorizálása.
    - Árcsoportok társítása.
    - A B2B-szervezetekre jellemző vevői hierarchia társítása. 
    - Az alapértelmezett dimenzióattribútum-csoport társítása a finomítókhoz (például méret, stílus és szín).
    - Attribútum-metaadatok beállítása

1. **[Érvényesítés](#validate-the-catalog)** – ebben a lépésben olyan érvényesítési szabályokat futtat, amelyek meghatározott viselkedést érvényesítnek. Íme néhány példa:

    - Győződjön meg róla, hogy nincsenek nem kategorizált termékek.
    - Győződjön meg róla, hogy minden, az egyes csatornákhoz hozzárendelt cikk hozzá van társítva egy katalógushoz.

1. **[Jóváhagyás](#approve-the-catalog)**
1. **[Közzététel](#publish-the-catalog)**

## <a name="set-up-the-catalog"></a>Katalógus beállítása

Ennek a szakasznak az adatai alapján állíthatja be a katalógust.

### <a name="configure-the-catalog"></a>Katalógus konfigurálása

A Commerce Headquarters alkalmazás a **katalógus konfigurálása érdekében menjen a Retail and Commerce \> Catalogs \>** és a szortimentek összes katalógusára.

Új katalógus létrehozása után először társítani kell egy vagy több csatornához. A katalógus létrehozásakor csak a kiválasztott [csatorna szortimenthez](/dynamics365/unified-operations/retail/assortments) kapcsolt cikkeket lehet használni. Ha a katalógust egy vagy több csatornához szeretne társítani, **·** **válassza a Hozzáadás a Katalógusbeállítás lap Commerce csatornák** **gyorslapján** lehetőséget. Győződjön meg róla, hogy a katalógus katalógustípusként **van megjelölve = B2B**.

#### <a name="associate-the-navigation-hierarchy"></a>Navigációs hierarchia társítása

Ha termékeket szeretne hozzáadni egy katalógushoz, ki kell választania egy navigációs hierarchiát. A navigációs hierarchia támogatja a katalógus kategóriastruktúráját. Ki kell választania egy **navigációs hierarchiát, amely a Katalógusbeállítási lap Commerce-csatornák** **gyorslapján kiválasztott csatornákhoz van társítva**. Ha az egyes csatornákhoz **alapértelmezett navigációs hierarchiát társít, használja a Retail és Commerce \> Csatorna \> beállítása csatornakategóriákat és termékattribútumokat**.

#### <a name="specify-time-effective-and-expiration-dates"></a>Adja meg az érvényességi időt és a lejárati dátumokat.

Egy katalógus érvényességi és lejárati dátumának megadásához válassza ki a katalógushierarchia legfelső csomópontját, és térjen vissza a főkatalógus fejlécnézetéhez. Ezt követően állítsa be az **érvényességi** és a lejárati dátumokat az Általános gyorsététi oldalon.

#### <a name="add-and-categorize-products"></a>Termékek hozzáadása és kategorizálása

A katalógushoz hozzáadható termékek a Commerce Headquarters **alkalmazásba való felvétele érdekében a Retail and Commerce \> Catalogs és a Szortimentek \> Mind katalógusok gombra való ugrásával konfigurálhatók**. Ezután a Katalógusok lapon **válassza** a Termékek **hozzáadása lehetőséget**.

Másik lehetőségként jelöljön ki egy csomópontot a navigációs hierarchiában. Ezt követően a katalógus egy kategóriájához közvetlenül hozzá tudja adni a termékeket.

#### <a name="associate-price-groups"></a>Árcsoportok társítása

A katalógushoz hozzáadható termékek a Commerce Headquarters **alkalmazásba való felvétele érdekében a Retail and Commerce \> Catalogs és a Szortimentek \> Mind katalógusok gombra való ugrásával konfigurálhatók**. Ezután a Katalógusok lapon **válassza** a Termékek **hozzáadása lehetőséget**. 

Azok a termékek, amelyek a navigációs hierarchia gyökércsomópontból egy katalógushoz hozzáadva, a Termék hozzáadása a munkaablakban lehetőség választásával öröklik a kategóriákat, amennyiben a **katalógushoz** a forrás navigációs hierarchia is társítva van. A forrás navigációs hierarchiában végrehajtott kategóriák módosításai azonnal megjelennek a katalógusok között. A csatornák frissítéséhez újból közzé kell tennie a katalógusokat.

Másik lehetőségként kiválaszthat egy csomópontot a navigációs hierarchiában, és közvetlenül termékeket adhat hozzá a katalógus kiválasztott kategóriájához. 

Termékek hozzáadásakor az **Összes változat automatikus felvétele, ha csak** az alaptermék van kiválasztva, elérhetővé válik. Az összes változat felvételének megakadályozásához válasszon ki legalább egy változatot az alaptermékhez. 

> [!NOTE]
> Ha azt választja, hogy minden változat automatikusan szerepeljen nagy alaptermék-kiválasztásban, hosszabb feldolgozási időket is tapasztalhat. Nagy beállítások esetén azt ajánljuk, **hogy** a művelet kötegelt módban való futtatásához jelölje be az összes változatot a katalógusok oldalának műveleti ablakában. Ha a katalógusban csak az alaptermék szerepel, de egyetlen változat sem, előfordulhat, hogy a változatválasztó nem érhető el, amikor egy termék részletei lapra navigál. 

Katalógusspecifikus árak konfigurálása érdekében egy vagy több árcsoportot kell a katalógushoz kapcsolnia. Ha árcsoportokat társít egy katalógushoz a Commerce Headquarters segítségével, **akkor menjen a Retail and Commerce \> Catalogs and szortimentek \> Minden katalógusba**. Ezután válassza ki az **Árcsoportokat** **a Katalógusok lapon,** az **Árképzés csoportban**. Az ugyanabba az árcsoportba tartozó minden kereskedelmi megállapodás, árkorrekció-napló és speciális engedmény (küszöbérték, mennyiség és kombinációs engedmény) akkor lesz alkalmazva, amikor a vevő rendelést rendel a katalógusból.

Az árcsoportokkal kapcsolatos további tudnivalókat lásd: [Árcsoportok](price-management.md#price-groups).

> [!NOTE]
> Nem hozhat létre új árcsoportot a **Minden katalógus lapon**. Ehelyett az Összes árcsoport lapon **kell** létrehozni. Ezt követően társítva kell lennie a katalógushoz a Minden **katalógus lapon**.

#### <a name="associate-a-customer-hierarchy"></a>Vevőhierarchia társítása

A vevőhierarchiák Commerce Headquarters **szolgáltatásban való társítása a Retail and Commerce \> Catalogs és a Szortimentek \> Mind katalógusok részében található**. Ezután a Katalógusok lap **Vevői** hierarchiája **csoportjában** válassza a Hierarchiák hozzárendelése lehetőséget, **ha** egy vagy több vevőhierarchiát a katalógushoz szeretne hozzárendelni.

> [!NOTE]
> Nem hozhat létre új vevőhierarchiát **a Minden katalógus lapon**. Ehelyett a Vevői **hierarchiák lapról kell létrehozni**. Ezt követően társítva kell lennie a katalógushoz a Minden **katalógus lapon**.

#### <a name="associate-default-dimension-attribute-group-for-refiners-such-as-size-style-and-color"></a>Alapértelmezett dimenzióattribútum-csoport társítása a finomítókhoz (például méret, stílus és szín)

Ha társítani szeretné az alapértelmezett dimenzióattribútum-csoportot a finomítókhoz (például méret, stílus és szín) a Commerce Headquarters szolgáltatásban, **használja a Retail and Commerce \> Catalogs and szortimentek \> Minden katalógusát**. Ezután a Katalógusok lapon **, az Attribútumok csoportban** **válassza ki az Attribútumcsoportokat** **.**

#### <a name="set-attribute-metadata"></a>Attribútum-metaadatok beállítása

Az attribútum-metaadatok a Commerce Headquarters **alkalmazás Retail and Commerce \> Catalogs és Szortimentek \> Mind katalógusainak beállításával konfigurálhatók**. Ezután a Katalógusok **lapon**, az Attribútumok csoportban **válassza** az Attribútumok metaadatainak **beállítása lehetőséget**. A megtekinthető és testreszabható attribútumok kiválasztásához válasszon ki egy kategóriát a kapcsolódó katalógusspecifikus navigációs hierarchiában, **majd** válasszon egy attribútumot a Katalógus termékattribútumok csoportban. Ezután válassza az Attribútum **megjelenítése a csatornában lehetőséget**. Alapértelmezés szerint minden megtekinthető attribútum kereshető is. Ha igény szerint finomítani is kívánt attribútumokat, **válassza a Lehet finomítani**.

### <a name="validate-the-catalog"></a>Katalógus érvényesítése

Ahhoz, hogy új katalógust használjon, érvényesíteni kell és közzé kell tenni.

Katalógus érvényesítéséhez kövesse az alábbi lépéseket.

1. Az Összes **katalógus lap Katalógusok** lapján **található** Katalógusok **ellenőrzése** ellenőrzés futtatásához jelölje be **a** Katalógus érvényesítése lehetőséget. Ez a lépés kötelező. Ellenőrzi, hogy helyes-e a szükséges beállítás.
1. Az **ellenőrzés részleteinek** megtekintéséhez válassza az Eredmények megtekintése lehetőséget. Ha a rendszer hibákat talál, ki kell javítania az adatokat, majd újra futtatnia kell az ellenőrzést, amíg el nem halad.

> [!NOTE]
> Ha **a katalógus típusa = B2B**, az érvényesítés sikertelen lesz, ha pos-áruházakat vagy hívásközpontokat adott hozzá a katalógushoz. A B2B katalógusok csak B2B online csatornákhoz társíthatók. Az ellenőrzés akkor is sikertelen lesz, ha nincs hozzárendelve vevőhierarchia egy B2B-katalógushoz. 

### <a name="approve-the-catalog"></a>Katalógus jóváhagyása

A katalógus érvényesítése után jóvá kell hagyni azt.

A katalógus-jóváhagyási munkafolyamat az alábbi lépések szerint indítva indítva el a katalógust.

1. A Minden katalógus lap munkaablakában **válassza** a Munkafolyamat elküldése **lehetőséget \>**.
1. Menjen a **Retail and Commerce \> Headquarters beállításához \> a Commerce** munkafolyamatok segítségével, és állítsa be a lépéseket és a munkafolyamat jogosult felhasználóit. A munkafolyamat meghatározza azokat a lépéseket, amelyek szükségesek ahhoz, hogy a **katalógus Jóváhagyott állapotúra** kerül.

### <a name="publish-the-catalog"></a>Katalógus közzététele

Ha egy katalógus Jóváhagyott **állapotú**, **·** **a** Katalógusok menü Közzététel parancsával közzéteheti azt. Miután a katalógus közzétett **állapotban** van, felhasználható hívásközponti rendelésbevitelben és a katalógusfolyamatok elküldését. A katalógusokat saját kezűleg vagy kötegelt feldolgozással lehet közzétenni. A katalógushoz megadott hatályos dátum határozza meg, hogy a termékek mikor érhetők el az online áruházban. A megadott lejárati dátum határozza meg, hogy mikor távolítják el a termékeket az online áruházból.

> [!NOTE]
> A figyelmeztetéseket tartalmazó termékeket tartalmazó katalógusokat közzé lehet tenni. Ezek a termékek azonban nem jelennek meg az online áruházban.

## <a name="additional-resources"></a>További erőforrások

[Commerce-katalógusok B2B-testreszabásokra vonatkozó bővíthetőségi hatása](catalogs-b2b-sites-dev.md)

[Commerce-katalógusok B2B-hez – GYIK](catalogs-b2b-sites-FAQ.md)

[Katalógusválasztó modul](catalog-picker.md)
