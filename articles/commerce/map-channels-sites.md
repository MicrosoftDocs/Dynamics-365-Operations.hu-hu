---
title: Csatornák leképezése e-kereskedelmi webhelyekhez
description: Ez a témakör néhány olyan Microsoft Dynamics 365 Commerce gyakori csatorna-hozzárendelési helyzetet ismertet, amelyek a legtöbb egyéb üzleti követelmény esetén külön is használhatók.
author: samjarawan
ms.date: 05/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 94c43df26e8d6e55a5b6d459b65066d5873e1063
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8902763"
---
# <a name="map-channels-to-e-commerce-sites"></a>Csatornák leképezése e-kereskedelmi webhelyekhez

Ez a témakör néhány olyan Microsoft Dynamics 365 Commerce gyakori csatorna-hozzárendelési helyzetet ismertet, amelyek a legtöbb egyéb üzleti követelmény esetén külön is használhatók.

Dynamics 365 Commerce A <a0/10/[...](#channels)<a2/1><a2/1><a2/<a2/5><a3/ számos üzleti helyzetet támogat az online csatornák megfeleltetéséhez, amelyekben beállított termékek, [árak és engedmények halmaza található a vevőknek szóló e-commerce](#e-commerce-sites) webhely tapasztalatokkal.

Ez a cikk a következő helyzetekre terjed ki:

- **Egy nyelven keresztüli csatorna, amely egyetlen e-commerce webhelyet tapasztalatokkal rendelkezik.** Ilyen helyzet lehet például egyetlen, az egyesült államoki piachoz beállított márkahely.
- **Többnyelvű csatorna, amely egyetlen honosított webhely-tapasztalatokkal rendelkezik.** Ilyen helyzet lehet például egyetlen, Kanadában francia és angol nyelvű támogatással konfigurált márkahely. Ebben az esetben a különböző nyelveket kiválasztó felhasználók ugyanazt a webhely-tapasztalatot tapasztalják, de az egyes felhasználók által választott nyelvre vannak honosva.
- **Több nyelven keresztül használt csatorna, amely nyelvenként eltérő webhely-tapasztalatokkal rendelkezik.** Ilyen helyzet lehet például egyetlen, Kanadában francia és angol nyelvű támogatással konfigurált márkahely. Ebben az esetben az egyes nyelvekhez egyedi tapasztalatokat lehet használni a webhelyen.
- **Több csatorna (egyszintű és/vagy több nyelven), amelyek egyetlen honosított webhely-tapasztalatokkal rendelkeznek.** Ez az eset lehet például egyetlen Ausztrália és Új-Zéland számára konfigurált márkahely. Ebben az esetben mindkét ország ugyanazokkal a webhelyekkel rendelkezik angol nyelven, de mindegyik ország eltérő termékekkel, pénznemekkel, árakkal, engedményekkel és szállítási módokkal van konfigurálva.
- **Több olyan csatorna (egyszintű és/vagy többszintű), amelyek csatornánként eltérő webhely-tapasztalatokkal rendelkeznek.** Ez a helyzet lehet például egyetlen, Ausztrália, Kanada és Németország számára több nyelven konfigurált márkahely is. Ebben az esetben minden ország egyedi webhely-tapasztalatokkal rendelkezik, és különböző termékekkel, pénznemekkel, árakkal, engedményekkel és szállítási módokkal van konfigurálva.

## <a name="channels"></a>Csatornák

A csatornák (más néven online áruházak és online csatornák) az online e-commerce rendszer egy olyan üzletét képviselik, amely a termékek, az árképzés, az engedmények, a nyelvek, a fizetési módok, a szállítási módok, a teljesítési központ és az online tapasztalat egyéb aspektusainak megfeleltethető az e-commerce ügyfelek számára. A csatornák létrehozása és kezelése a Commerce Headquarters szolgáltatásban, és egy jogi személyhez van [hozzárendelve](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json#legal-entities). A jogi személy általában egyetlen országban van, ahol a csatorna adóbevallást igényel, és csak egyetlen pénznemben konfigurálható.

További tájékoztatás a csatornákról: Csatorna [áttekintése](channels-overview.md). További tájékoztatás az online csatornák létrehozásáról: [Online csatorna beállítása](channel-setup-online.md).

A Commerce Headquarters következő példa illusztrálja azokat az alapértelmezett online Dynamics 365 Commerce csatornákat, amelyek akkor vannak telepítve, ha a bemutatóadat-beállítás ki van választva.

![A Commerce Headquarters alapértelmezett bemutatóadat-csatornái](media/channel-mapping-1.png)

## <a name="e-commerce-sites"></a>E-commerce webhelyek

Az e-commerce webhely webhelylapok halmazát tartalmazza, amelyek használatával a vevők böngészéshez és vásárláshoz használhatók. Az e-commerce webhelyeket a Commerce Webhelyszerkesztő kezeli.

A webhelyszerkesztőben található webhelyek létrehozásáról és kezeléséhez szükséges további tudnivalókat lásd [az E-commerce webhely áttekintésében](online-store-overview.md).

## <a name="common-channel-mapping-scenarios"></a>Gyakori csatorna-hozzárendelési esetek

Dynamics 365 Commerce A <a0/<a0/<a2/<a2/5><a2/ A csatorna-hozzárendelési esetek az összes lehetséges csatorna-hozzárendelési eset egy részkészletét jelentik. Útmutatóként szolgálnak, hogy segítséget kínálnak az egyedi üzleti esetek tervezéséhez. A Kalandorbolt kitalált árutárát Dynamics 365 Commerce, amely a bemutatóadatokkal együtt szerepel, példaként használja minden egyes helyzethez.

### <a name="single-language-channel-that-has-a-single-e-commerce-site-experience"></a>Egy nyelven keresztüli csatorna, amely egységes e-commerce webhely tapasztalatokkal rendelkezik.

A legtöbb esetben egyetlen csatorna egyetlen piaci értékesítésre használt nyelvre használható. Erre egy példa a Kalandorbolt online áruház, amely csak az egyesült államokbeli piac számára van beállítva.

A következő példa bemutatja a Commerce Headquarters egy csatorna-konfigurációját. Ebben a konfigurációban az online csatorna csak egy nyelvet (en-us **), egyetlen pénznemet (** **USD**) és egyetlen üzleti entitást (**usrt**) támogat, amely adóbevallásra használható.

![A Commerce Headquarters kiemelést adott a Kalandorbolt online áruház jogi személyének, pénznemének és nyelvének értékeihez.](media/channel-mapping-3.png)

A webhelyszerkesztő egyetlen e-commerce webhelyének megfeleltetheti az egyetlen online csatornát. Az új webhely létrehozásáról és csatornára való leképezésről a [cikk](#map-a-channel-to-a-site-in-site-builder) Webhelyszerkesztő szakaszának Webhelyre leképezés című fejezete nyújt tájékoztatást.

### <a name="multi-language-channel-that-has-a-single-localized-site-experience"></a>Többnyelvű csatorna, amely egyetlen honosított webhely-tapasztalatokkal rendelkezik.

Ebben az esetben egy csatorna több nyelvet is támogat. Ennek megfelelően a terméknevek, leírások és attribútumok honosítottuk a Commerce Headquarters szolgáltatásban. A teljes honosított webhely-tapasztalat érdekében a Commerce webhelyszerkesztőben a webhelyen található marketingtartalmak is honosizálhatóak.

Ennek az esetnek az az korlátozása, hogy egyetlen csatornát csak egy pénznemben, egy jogi személyben és egy termék- és árhalmazban lehet konfigurálni. Ez a konfiguráció a legmegfelelőbb olyan országokban, amelyekben egyetlen pénznem és több nyelv van (például Kanada, ahol az angol és a francia nyelveket), egyetlen jogi személyt, valamint egyetlen termék- és árkészletet tartalmaznak.

A csatornák minden nyelvét be lehet állítani a saját tartománynevével. Például a tartomány `www.adventure-works.ca` konfigurálható a kanadai angol verzióhoz, `www.adventure-works-fr.ca` a tartomány pedig a kanadai verzióhoz. Másik lehetőségként a csatornák különböző nyelveket is be lehet állítani egyetlen tartományban, majd mindegyik nyelvhez más-más elérési utat lehet használni. Például a `www.adventure-works.ca` tartomány konfigurálható a kanadai angol verzióhoz, `www.adventure-works.ca/fr` és az elérési út a kanadai verzióban is használható. [A földrajzi](geo-detection-redirection.md) észlelési funkció lehetővé teszi a felhasználók automatikus átirányítását a megfelelő helyre, a felhasználó helye alapján.

A vevők számára a [nyelvek](#add-and-configure-the-site-picker-module) közötti manuális váltásról a cikk Webhelyválasztó modul hozzáadása és konfigurálása című részében olvashat tájékoztatást. A honosított lapok [és a darabkák testreszabását a Több csatornát és nyelveket is elérhető webhelytartalom kezelése című rész tartalmaz](#manage-site-content-that-has-multiple-channels-and-languages).

### <a name="multi-language-channel-that-has-a-different-site-experience-per-language"></a>Többnyelvű csatorna, amely nyelvenként eltérő webhely-tapasztalatokkal rendelkezik

Olyan helyzeteket érdemes használni, ahol egy csatorna több nyelvet támogat, de minden nyelven teljesen eltérő webhely-tapasztalat jelenik meg. Ennek az esetnek az alkalmazása ajánlott megoldás az oldalváltozatok [egyetlen](#implement-page-variants-for-each-language) webhelyen való használata.

Egy másik módszer, ha a webhelyszerkesztő minden nyelvére új e-commerce webhelyet hoz létre, majd mindegyik helyet egyetlen online csatornára és nyelvre leképezi. Az eredmény egyetlen online csatorna lesz, amely több e-commerce webhelyhez van hozzárendelve, és mindegyik nyelvre egy. Ehhez a több telephelyes módszerhez különleges felügyeleti erőforrásokra van szükség, mivel a webhelyszerkesztőben egynél több telephelyet kell kezelni.

### <a name="multiple-channels-single-language-andor-multi-language-that-have-a-single-localized-site-experience"></a>Több csatorna (egyszintű és/vagy több nyelven), amelyek egyetlen honosított webhely-tapasztalatokkal rendelkeznek.

Egy márkanév hely esetén előfordulhat, hogy régiónként több online csatorna szükséges különböző pénznem, termékhalmaz és árkészlet támogatásához az egyes csatornákon belül. Például a Kalandorpiac webhelynek lehet egy online csatornája a kanadai piac számára, amely több nyelvre is van stb., az egyesült államokbeli piac csatornájára, és egy német piac csatornájára, amely egy nyelvet is rendelkezik. Ebben az esetben minden online csatorna egy régióspecifikus jogi személyhez lesz konfigurálva, és ezekhez a termékekhez ugyanazok a termékek lehetnek beállítva, mint a többi csatorna termékei, a termékek egy részhalmaza vagy más termékhalmaz. Minden csatorna saját árakkal rendelkezik a régió pénznemében, adóiban, engedményeiben és szállítási módjaiban.

Ebben az esetben minden egyes piac saját tartománynevekkel konfigurálható. A tartomány például `www.adventure-works.com` az Egyesült Államok piacára, `www.adventure-works.de` a tartomány pedig a német piachoz konfigurálható. Azt is be lehet állítani, hogy az egyes piacok másik útvonalat használjanak. Például a tartomány konfigurálható `www.adventure-works.com` az egyesült államok piacára, `www.adventure-works.com/de` és aztán az útvonal használható a német piac számára. [A földrajzi észlelési](geo-detection-redirection.md) funkció lehetővé teszi a felhasználók régiójuktól függően a megfelelő helyre való automatikus átirányítását is.

Előfordulhat az is, hogy a webhelyen egy legördülő listát szeretne létrehozni, amely lehetővé teszi a felhasználók számára, hogy manuálisan váltson egy adott piacra. A további tudnivalókat [lásd](#add-and-configure-the-site-picker-module) a cikk Webhelyválasztó modul hozzáadása és konfigurálása című részében.

Ha további tájékoztatást tartalmaz arról, hogyan lehet egy webhelyen több csatornát konfigurálni, [tekintse meg az e-commerce webhely több csatornának konfigurálása című fejezetét](#configure-multiple-channels-on-an-e-commerce-site).

### <a name="multiple-channels-single-language-andor-multi-language-that-have-a-different-site-experience-per-channel"></a>Több csatorna (egy nyelvet és/vagy több nyelvet) tartalmaz, amelyek csatornánként eltérő webhely-tapasztalatokkal rendelkeznek.

Előfordulhat, hogy egy márka számára több csatornát szeretne különböző régiókban, és előfordulhat, hogy az egyes régióknak más a webhelye. Ezt az esetet kétféle módszerrel lehet alkalmazni:

- Lapváltozatok [használata](#implement-page-variants-for-each-language).
- A Webhelyszerkesztő minden online csatornáján külön webhelyet kell beállítani, majd az egyes webhelyeket egy másik online csatornára és nyelvre kell leképezni. Ez a módszer különleges felügyeleti erőforrásokat igényel, mivel a webhelyszerkesztőben egynél több telephelyet kell kezelni.

## <a name="cross-channel-sharing"></a>Csatornák közötti megosztás

A csatornák közötti megosztás hasznos, mert egyetlen webhelyen több csatorna is megoszthat tartalmat. Például egy olyan kiskereskedő, akinek több márkaneve és üzlete van, amelyet egyetlen weboldal fog össze, megoszthatja a tartalmat néhány vagy az összes üzlet között. A megosztott tartalomba beletartoznak a feltételek és feltételek oldalait, a fizetési feltételeket, a szállítási módokat, valamint a gyakran feltett kérdéseket (FAQ). További információ a csatornákon [keresztüli megosztás engedélyezése és használata.](cross-channel-sharing.md)

## <a name="map-a-channel-to-a-site-in-site-builder"></a>Csatorna leképezés egy webhelyre a Webhelyszerkesztőben

A különböző online csatornákon keresztül történő webhely-létrehozásra és -konfigurálásra többféle módszer létezik.

### <a name="create-a-new-site"></a>Új bolt létrehozása

Ha egy teljesen új webhelyet **hoz** létre a Webhelyszerkesztőben, kattintson a Helyek listaoldalra **, és válassza az Új webhelyet**. Ezután a megjelenő Új **webhely** párbeszédpanelen kiválaszthatja a webhely alapértelmezett online csatornáját és nyelvét, amint azt az alábbi példa mutatja.

![Új csatorna létrehozása a webhelyszerkesztőben](media/channel-mapping-4.png)

Az így létrehozott webhely üres lesz, és nem tartalmaz webhelyoldalakat (például honlapot, kategóriaoldalakat és termékoldalakat).

További információért lásd: [E-kereskedelmi webhely létrehozása](create-ecommerce-site.md).

### <a name="create-a-new-site-by-using-the-site-copy-operation"></a>Új webhely létrehozása a hely másolási műveletének használatával

Ahelyett, hogy az előző szakaszban leírtak szerint egy teljesen új, üres helyet hozna létre, jobb megoldás, ha a Commerce modultárában található kezdőwebhelyek egy példányát indítják el, például a Gyár vagy a Kalandortár webhelyet.

Meglévő webhely másolásához kattintson **a** Webhelyszerkesztő Sites listaoldalára, és válassza a Webhely másolása **lehetőséget**. Ezután a Megjelenő Webhely másolása **párbeszédpanelen** kiválaszthatja a forráshelyet, és megadhatja a célhely nevét.

Ezen a ponton még nem lehet kiválasztani a webhely alapértelmezett online csatornáját és nyelvét. Ezeket a tulajdonságokat azonban a hely másolási műveletének befejezése után is beállíthatja. Amikor először kiválasztja a **webhelyet** a Webhelyszerkesztő Webhelylista lapján, **megjelenik** a Webhely beállítása párbeszédpanel, ahol kiválaszthatja az alapértelmezett csatornát és nyelvet.

A webhely másolási műveletére vonatkozó további információ: [E-commerce webhely másolása](copy-ecommerce-site.md).

### <a name="manage-an-existing-site-channel"></a>Meglévő webhelycsatorna kezelése

Miután a webhely konfigurálva van egy csatornával, **\>** a csatorna kezelhető és frissítható a Webhely-beállítási csatornák webhelyszerkesztő kijelölt telephelyén belül, amint azt az alábbi példa is mutatja.

![A csatorna-hozzárendelés kezelése a webhelyszerkesztőben](media/channel-mapping-7.png)

## <a name="support-multiple-sites-in-a-single-tenant"></a>Több hely támogatása egy bérlőben

Számos márkanév hely egy bérlőben együtt tud maradni. A következő példa bemutatja három különböző márkanévvel ábrázolt telephelyet (Kalandor gyár, Kalandor vállalkozás és Gyár), amelyek mindegyikét egy másik online csatornához lehet hozzárendelni.

![Helylista a Webhelyszerkesztőben.](media/channel-mapping-8.png)

## <a name="configure-a-single-domain-name-with-paths-for-multiple-sites"></a>Egyetlen tartománynév konfigurálása több hely elérési útvonalával

Egy tartománynév több helyhez is használható, elérési utak pedig különböző helyek és nyelvek elválaszthatja őket. A tartomány például `www.mycompany.com` két különböző e-kereskedelmi helyhez van konfigurálva: egy a Gyárhoz, és egy a Kalandor gyárhoz. Ebben az esetben az alapértelmezett elérési út (`www.mycompany.com` más néven üres elérési út) használható a Gyár telephelyén, `www.mycompany.com/adventureworks` és egy másik (például) elérési út is használható a Kalandorcsomóhelyhez. Egy másik lehetőség az egyéni elérési út (`www.mycompany.com/fabrikam` például) használata a Gyár webhely alapértelmezett elérési útja helyett.

Másik lehetőségként minden helyhez (például és ) más tartománynév `www.adventure-works.com` is használható`www.fabrikam.com`. Az elérési utak ezután több nyelvhez és régióhoz is használhatók (`www.adventure-works.com/fr-ca` például Kanadában, Franciaországban).

## <a name="configure-multiple-languages-on-a-site"></a>Több nyelv beállítása egy webhelyen

Az e-commerce webhely nyelveket a **Webhely-beállítási csatornák webhelyszerkesztője segítségével lehet beállítani \>**. A következő példa szerint az egyes nyelvek az elérési út területi beállításainak megfelelően vannak konfigurálva, így minden nyelvhez egyedi URL-cím készült.

![A webhelyen beállított több nyelv.](media/channel-mapping-10.png)

Ha új csatornanyelvet szeretne hozzáadni, kattintson a Webhely-beállítások **\> – Csatornák** elemre, és válassza ki a csatornahivatkozást. A jobb oldali ablakban **válassza a Területi beállítás hozzáadása lehetőséget a** hozzáadni kívánt csatorna és területi beállítás kiválasztásához. Ezután adja meg a kiválasztott csatornához használni kívánt elérési utat.

### <a name="add-and-configure-the-site-picker-module"></a>A webhelyválasztó modul hozzáadása és konfigurálása

Miután beállította a több nyelvet és csatornát használó webhelyet, előfordulhat, hogy egy nyelvi választót szeretne hozzáadni a webhely oldalfejlécéhez, hogy a felhasználók manuálisan kiválasztják a nyelvüket vagy az országukat. A modultár [fejlécmodulja](author-header-module.md) beépített támogatást nyújt a felhasználóknak arra, hogy a webhelyválasztó modul segítségével kiválasztsák a [nyelvet](site-selector.md). A helyválasztó modul a fejlécrészletben hozzáadható a fejlécmodulhoz.

A webhelyválasztó modul [hozzáadásáról és konfigurálásról a Webhelyválasztó modulban található további tájékoztatás](site-selector.md).

### <a name="implement-page-variants-for-each-language"></a>Oldalváltozatok megvalósítása minden nyelvhez

Ebben az esetben csak egy csatorna van, de több nyelv is van. Ha egy oldalváltozatot hoz létre, akkor a kiválasztott nyelv alapján módosíthatja a lap megjelenését. Ezután honosított tartalmat adhat hozzá a változathoz.

Ha meg van nyitva egy lap a webhelyszerkesztőben, és a jobb felső oldalon az aktuális csatornát és nyelvet ábrázoló hivatkozást választja, megjelenik egy csatorna- és nyelvválasztó, amint azt az alábbi példa mutatja. Ha az aktuális nyelven felül szeretné bírálni az oldalt, válasszon másik területi beállításokat, majd válassza a Módosítás **lehetőséget**. A csatorna akkor is [megváltoztatható, ha olyan webhelyet kezelő, amely több csatornát és nyelvet tartalmaz](#manage-site-content-that has-multiple-channels-and-languages).

![A lap nyelvének módosítása a webhelyszerkesztőben](media/channel-mapping-14.png)

Ha még nincs létrehozva a kiválasztott oldal vagy részlet változata, figyelmeztető üzenet jelenik meg, amint azt az alábbi példa mutatja. Ebben az esetben válassza ki az oldalváltozat **létrehozása** hivatkozást az üzenet szövegében. A megjelenő párbeszédpanelen olyan lehetőségek jelennek meg, amelyek segítségével akár egy meglévő változat másolatával kezdődni lehet, vagy egy sablon alapján teljesen új lapot lehet létrehozni.

![Rákérdezés a lapváltozat létrehozására a webhelyszerkesztőben](media/channel-mapping-16.png)

Ha nem hoz létre változatot, akkor az eredeti lap megjelenik, és a Commerce Headquarters alkalmazásból származó modul-karakterláncok és termékinformációk megfelelő nyelvét jeleníti meg. Ha azonban az alapértelmezett lapmodulban meg van adva közvetlenül szöveg, például oldalcím vagy más marketingtartalom, az adott szöveghez kapcsolódó karakterláncok az eredeti nyelven maradnak.

Az egyes oldalak és részletek manuális létrehozása helyett exportálhatja az egyes adatokat egy XML-honosítási fájlformátumba (XLIFF), amely ezután el is küldhető honosításra. Az egyes XLIFF-változatok honosított változataként importálhatók. Ha egy XLIFF-fájlt egy lapról vagy a helyszerkesztő egy részletének a fájljára vagy egy XLIFF-fájlt egy lapra vagy részletbe importál, válassza a **honosítást** a parancssorban. Ezután válassza az **Export XLIFF vagy** az **Import XLIFF lehetőséget**, amint azt az alábbi példa mutatja.

![Lap vagy részlet importálása vagy exportálása XLIFF formátumban.](media/channel-mapping-18.png)

## <a name="manage-site-content-that-has-multiple-channels-and-languages"></a>Több csatornát és nyelvet is tartalmazó webhely tartalmának kezelése

Olyan webhely, amely több csatornával és/vagy nyelvvel rendelkezik, az egyes oldalak egyedi változatát tárolja, és a csatorna és a nyelv egyes kombinációira külön darabot tartalmaz. Ez a viselkedés lehetővé teszi, hogy a lapváltozatok honosított adatokat tartalmazzanak, ugyanakkor rugalmasan módosítják az egyes változatok megjelenését és működését.

A lapváltozatok alkalmazásával kapcsolatos tudnivalókat [lásd a](#implement-page-variants-for-each-language) cikk egyes nyelvi változatok megvalósítása című részében.

## <a name="configure-multiple-channels-on-an-e-commerce-site"></a>Több csatorna konfigurálása e-commerce webhelyen

A webhelyszerkesztőben új csatornákat adhat hozzá egy e-commerce **\>** **webhelyhez, ha a Webhely-beállítási csatornák elemre, és a Csatorna hozzáadása lehetőséget választja.** Ezután a Megjelenő Csatorna **hozzáadása** párbeszédpanelen kiválaszthatja az online csatornát és az alapértelmezett területi beállításokat.

## <a name="additional-resources"></a>További erőforrások

[Csatornák áttekintése](channels-overview.md)

[Online csatorna beállítása](channel-setup-online.md)

[Szervezetek és szervezeti hierarchiák áttekintése](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md)

[Földrajzi észlelés és átirányítás beállítása](geo-detection-redirection.md)

[Csatornaközi megosztás engedélyezése és használata](cross-channel-sharing.md)

[E-kereskedelmi webhely létrehozása](create-ecommerce-site.md)

[E-kereskedelmi webhely másolása](copy-ecommerce-site.md)

[Webhelyválasztó modul](site-selector.md)
