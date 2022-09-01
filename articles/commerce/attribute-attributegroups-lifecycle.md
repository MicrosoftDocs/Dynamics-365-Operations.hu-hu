---
title: Attribútumok és attribútumcsoportok kezelése
description: Ez a témakör leírja, hogyan kell kezelni a termékek és jellemzőik leírására vonatkozó attribútumokat és attribútumcsoportokat Microsoft Dynamics 365 Commerce.
author: ashishmsft
ms.date: 08/31/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2018-03-30
ms.openlocfilehash: aad448ea733aabdff3dc4438dcb682d49e0665c0
ms.sourcegitcommit: 09d4805aea6d148de47c8ca38d8244bbce9786ce
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/31/2022
ms.locfileid: "9386972"
---
# <a name="manage-attributes-and-attribute-groups"></a>Attribútumok és attribútumcsoportok kezelése

[!include [banner](includes/banner.md)]

Ez a témakör leírja, hogyan kell kezelni a termékek és jellemzőik leírására vonatkozó attribútumokat és attribútumcsoportokat Microsoft Dynamics 365 Commerce.

*Az attribútumok* segítségével le lehet írni a termékeket és azok jellemzőit a felhasználó által definiált mezők segítségével. Ilyen lehet például a memória mérete, a merevlemez kapacitása és az Energia Megfelelés.

Az attribútumok különböző Commerce entitásokhoz, például termékkategóriákhoz és csatornákhoz, társíthatók, és megadhatók hozzájuk alapértelmezett értékek. Amikor attribútumok termékkategóriákhoz vagy csatornákhoz vannak társítva, a termékek öröklik ezeket az attribútumokat és az alapértelmezett értékeiket. Az alapértelmezett attribútumértékek felülbírálhatók az egyes termékek szintjén, a csatorna szintjén vagy egy katalógusban.

Például egy tipikus televízió terméknek a következő attribútumai lehetnek.

| Kategória   | Attribútum           | Megengedett értékek                        | Alapértelmezett érték |
|------------|---------------------|-------------------------------------------|---------------|
| TV és videó | Márka               | Bármilyen érvényes márkaérték                     | Nincs          |
| TV         | Képernyőméret         | 20–85 hüvelyk                              | 55 hüvelyk     |
|            | Függőleges felbontás | 4K (2160p), TELJES OT (1080p) vagy 720p | 4K (2160p)    |
|            | Képernyő-frissítési gyakoriság | 60hz, 120hz vagy 240hz                     | 60hz          |
|            | HDMI-bemenetek         | 0–10                                      | 3             |

## <a name="attributes-and-attribute-types"></a>Attribútumok és attribútumtípusok

Az attribútumok az *attribútumtípusokon* alapulnak. Az attribútumtípus azonosítja az egy adott attribútumhoz be írható adatok típusát. A Commerce rendszer a következő attribútumtípusokat támogatja:

- **Pénznem** – Ez a típus egy pénznemértékeket támogat. Lehet kötött (vagyis támogathat egy értéktartományt) vagy nyitva is hagyható.
- **DateTime** – Ez a típus a dátum és idő értékeket támogatja Lehet kötött, vagy nyitva is hagyható.
- **Decimal** – Ez a típus egy numerikus értéket támogat, amely tizedesjegyeket tartalmaz. Mértékegységet is támogat. Lehet kötött, vagy nyitva is hagyható.
- **Itenger** – Ez a típus egy numerikus értékeket támogat. Mértékegységet is támogat. Lehet kötött, vagy nyitva is hagyható.
- **Text** – Ez a típus egy szöveges értéket támogat. A Rögzített lista beállítás engedélyezése esetén **a** lehetséges értékek egy előre definiált készletét is támogatja.
- **Boolean** – Ez a típus egy bináris értéket támogat (**igaz** vagy **hamis**).
- **Hivatkozás** – Ez a típus más jellemzőkre hivatkozik.

> [!NOTE]
> Az Azure [keresési index](/rest/api/searchservice/data-type-map-for-indexers-in-azure-search) korlátozásai miatt **a** felhőalapú keresési tapasztalatok nem támogatják a Tizedes attribútumtípust. Az Azure keresési szolgáltatás nem **támogatja a Tizedes** **attribútumtípusok Edm.Double** target index mezőtípusra történő konvertálását, mert ez az átalakítás csökkenti a pontosságot.

### <a name="set-up-attribute-types"></a>Attribútumtípusok beállítása

Az attribútumtípusok beállításának lépéseit a példa műveletében kell követni.

1. Kereskedelmi vezetőként jelentkezzen be a Commerce Headquartersbe.
1. Ugrás a Termékinformáció-kezelés **beállítási \> kategóriáihoz \> és attribútumtípusaihoz \>**
1. A Műveleti ablaktáblán kattintson az **Új** elemre.
1. Az Attribútumtípus **neve mezőbe** írja be a **Zsák típust**.
1. A **Típus** mezőben válassza ki az **Szöveg** lehetőséget.
1. A Rögzített **lista beállítása** Igen **beállításra**.
1. Az Értékek **gyors** oldalon válassza a Hozzáadás **lehetőséget**.
1. Az új sor Érték mezőjébe **írja** be a **Satzati értéket**.
1. Adjon hozzá öt további sort. Mindegyik értékmezőbe írjon be egy másik értéket: Megfelelő érték,44,44,666 **·** **·** **·** **, Üzenetkezelő** vagy **Stb.** **·**
1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.
1. A Műveleti ablaktáblán kattintson az **Új** elemre.
1. Az Attribútumtípus **neve mezőben** adja meg a **napgép márkanevét**.
1. A **Típus** mezőben válassza ki az **Szöveg** lehetőséget.
1. A Rögzített **lista beállítása** Igen **beállításra**.
1. Az Értékek **gyors** oldalon válassza a Hozzáadás **lehetőséget**.
1. Az új sor Érték mezőjébe **írja** be **a Tilt mezőt**.
1. Adjon hozzá két további sort. Mindegyik érték **mezőjébe** írjon be egy másik értéket: **Aviator vagy** **Mezőbe**.
1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.

![Attribútumtípusok lap.](media/AttributeType_2022Series.png)

### <a name="set-up-an-attribute"></a>Attribútum beállítása

Attribútum beállításának lépéseit a példa eljárásában kell követni.

1. Kereskedelmi vezetőként jelentkezzen be a Commerce Headquartersbe.
1. Ugrás a Termékinformáció-kezelés **beállítási \>\> kategóriáihoz és attribútumaihoz \>**
1. A Műveleti ablaktáblán kattintson az **Új** elemre.
1. A Név **mezőben** adja meg **a Zsák típusa mezőt**.
1. Az Attribútumtípus **mezőben** válassza ki a Zsák **típust**.
1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.

![Attribútumok lap.](media/Attribute_2022Series.png)

## <a name="attribute-metadata"></a>Attribútum metaadatai

Az *Attribútum-metaadatok* beállítások megadását teszi lehetővé annak a megadásához, hogy az attribútumok termékenként hogyan működjenek. Megadhatja például, hogy szükség van-e attribútumokra, hogy használhatóak-e keresésekhez, illetve szűrőként.

Termékek esetén az attribútummetaadat-beállítások a csatorna szintjén felülbírálhatók.

Az attribútum attribútumlapja **számos**, az attribútum-metaadatokkal kapcsolatos beállítással áll kapcsolatban. Ha **például** **·** **a Lehet szűkítési beállítás Igen beállítást választja a Commerce-csatornák** Attribútum-metaadatainál, akkor az attribútum a termékek finomítása vagy szűrése érdekében megjelenik a keresési eredmények és a kategória tallózási lapjain. Ahhoz, hogy egy attribútumot finomíthatóként konfigurálni tudja, először ki kell választania a Szűrőbeállításokat a munkaablakban, **és** meg kell erősítenie az attribútum szűrőbeállítását.

## <a name="filter-settings-for-attributes"></a>Attribútumok szűrési beállításai

Az attribútumok szűrőbeállításai segítségével meghatározhatja, hogy hogyan jelennek meg az attribútumszűrők a pénztárnál (POS). Egy attribútum szűrőbeállításainak eléréséhez válassza a Szűrőbeállítások lehetőséget **az attribútum attribútumainak lapján, a munkaablakban** **.**

A **Szűrőbeállítások** lap a következő mezőket tartalmazza:

- **Név** – Alapértelmezés szerint a mező értéke az attribútum neve. Ez az érték azonban módosítható.
- **Megjelenítési beállítás** – A következő beállítások közül választhat:

    - **Egyetlen érték** – Ez a lehetőség a következő attribútumtípusokhoz érhető el: **logikai**, **pénznem**, **decimális**, **egész** és **szöveg**. A terméklistaoldalakon, például a kategória tallózása és a termékkeresés eredményoldalán csak egy értéket lehet kiválasztani a finomítók számára.
    - **Többértékű** – Ez a lehetőség a következő attribútumtípusokhoz érhető el: **pénznem**, **decimális**, **egész** és **szöveg**. Lehetővé teszi a finomításhoz az ügyfélen az attribútumhoz több érték beállítását.

- **Megjelenítés szabályozása** – A következő beállítások közül választhat:

    - **Lista** – ez a beállítás minden attribútumtípusnál elérhető.
    - **Tartomány** – Ez a lehetőség a következő attribútumtípusokhoz érhető el: **pénznem**, **decimális** és **egész**.
    - **Csúszka** – Ez a lehetőség a következő attribútumtípusokhoz érhető el: **pénznem**, **decimális** és **egész**.
    - **Csúszka sávokkal** – Ez a lehetőség a következő attribútumtípusokhoz érhető el: **pénznem**, **decimális** és **egész**.

- **Küszöbérték** – A beállítás akkor szükséges, ha a **Tartomány** lehetőséget választotta a megjelenítés szabályozási típusának. Elválasztóként a pontosvessző (;) használatával definiálhat értékeket.

    Például egész szám attribútumtípusú zsáktérfogattribútum esetén **a** **·** **küszöbérték 10; 20; 50; 100; 200; 500; 100; 100; 1000; 1000; 5000**. Ebben az esetben a pénztár a következő tartományokat jeleníti meg. Az eredménykészletben nem szerepel terméktartományok halványan jelennek meg.

    - Kevesebb mint 10
    - 10–20
    - 20–50
    - 50–100
    - 100–200
    - 200–500
    - 500 vagy több

Az attribútumok szűrőbeállításai csak a termékattribútumokra vonatkoznak, a termékkeresés és a kategória tallózásának szűkítésére használhatók. Nem vonatkoznak sem vevőkeresésre, sem rendeléskeresésre, bár ugyanazok az attribútumok felhasználhatók a vevői és rendelési adatok további bővítőihez.

Az alapértelmezett Commerce modulokban a kijelző vezérlőszűrő-beállításaihoz (például Tartomány **,** **Elemre**, és Oszlopokkal stb.**·** **) nincs elérhető a dobozon kívül használható támogatás.** **A** Range és **a Hozzáférhető** beállítások továbbra is támogatottak a POS-megoldásoknál, míg a Bar barokkal beállítás örökölt online áruházakra vonatkozik, **·** SharePoint és továbbra is elérhetők maradnak külső fél integrációja és egyéni helyzetek számára.

Javasoljuk **·** **·**, hogy a testreszabható attribútumok Szöveg típusúak, ahol engedélyezve van a Rögzített lista beállítás, és a lista kezelhető maradjon (legfeljebb 100–200 egyedi érték). Ha egy finomítónak 1000 vagy több egyedi értéke lesz, **akkor célszerűbb olyan Szöveg** **típusú** attribútumot használni, ahol a Rögzített lista beállítás nincs engedélyezve.

Az attribútumnevekhez és azok értékeihez kritikus fontosságúak a fordítások. A Rögzített **lista** **·** **beállítást engedélyező Szöveg típusú attribútumok esetén az Attribútumtípus alatt definiálni lehet az attribútumértékek fordítását.** Minden más attribútumtípushoz definiálni lehet fordításokat az attribútumértékeket definiáló lapon. Például egy Szöveg **típusú** attribútumnál megadhatja az **attribútum attribútumainak lapján az alapértelmezett érték fordítását**. Ha azonban termékszinten felülbírálja az alapértelmezett értéket, **a** termék termékattribútum-lapján megadhatja az attribútum fordítását.

Miután az attribútumot át lehet definiálhatóként megjelölni egy csatornánál, nem szabad frissíteni az attribútumtípust. Ellenkező esetben a termékadatok közzétételét fogja befolyásolni a keresési indexben. Ehelyett javasoljuk, hogy hozzon létre egy új attribútumot egy új típusú finomítóhoz, és távolítsa el az előző attribútumot a többi attribútumcsoportból.

Az attribútumok alapján való keresés támogatott, de az eredmények beolvasása csak a keresési szavak pontos egyezését jelenti. Például egy **Anyag** **attribútum értéke Cashmere attribútum**. Ha egy vevő a "Készpénz" **kifejezésre keres, akkor a program nem fog beolvasni olyan** termékeket, amelyek anyagát készpénzmemószerként kell beolvasni. Ha viszont a vevő a "Cashmere", "Pépé" vagy "Cashmere És" termékeket keresi, **amelyek anyagát cashmere** anyagként olvassa be a program.

### <a name="additional-attribute-metadata-options"></a>További attribútum-metaadatok beállításai

> [!NOTE]
> Ezek az attribútum-metaadat-beállítások csak SharePoint az örökölt online áruházakra és külső integrációkra vonatkoznak. Ezekről az attribútumok metaadat-beállításairól [SharePoint a Server 2013 keresési sémájának áttekintése nyújt további tájékoztatást](/SharePoint/search/search-schema-overview).

Az Attribútumok lapon a következő további attribútum-metaadat-beállítások **is** elérhetők:

- Kereshető
- Beolvasható
- Lekérdezhető
- Rendezhető
- Kis- és nagybetűk, illetve formázás figyelmen kívül hagyása
- Teljes egyezés

Ezek a beállítások eredetileg az SharePoint örökölt online áruházak keresési funkcióinak javítására szolgáltak. Nem feltétlenül vonatkoznak a Commerce e-commerce webhelyekre és POS-terminálokra. Mivel a fej nélküli integráció továbbra is támogatott, ezek a beállítások a Commerce szoftverfejlesztői csomag (SDK) segítségével exportálható attribútum-metaadatok exportálásához is elérhetők. A Commerce SDK segítségével lehet termékeket egyéni, optimalizált külső keresési indexbe tenni. Így biztos lehet benne, hogy csak az indexelni szükséges attribútumok indexelnek.

## <a name="attribute-groups"></a>Attribútumcsoportok

Az *attribútumcsoport* segítségével csoportosítható egy termékkonfigurációs modell egy összetevő vagy részösszetevő egyedi attribútumai. Több attribútumcsoportba is felvehet egy attribútumot. Az attribútumcsoportok segíthetik a felhasználókat a termékek konfigurálásában, mert a különböző kiválasztások rendezve jelennek meg az adott környezetben. Az attribútumcsoportokat hozzárendelheti a csatornákhoz vagy a kategóriákhoz. Az attribútumcsoport attribútumainak alapértelmezett értékeit is be lehet állítani.

![Attribútumcsoportok lap.](media/AttributeGroup_2022Series.png)

### <a name="create-an-attribute-group"></a>Attribútumcsoport létrehozása

Attribútumcsoport létrehozásához kövesse az alábbi lépéseket a példában.

1. Kereskedelmi vezetőként jelentkezzen be a Commerce Headquartersbe.
1. Ugrás a Termékinformáció-kezelés **beállítási \> kategóriáihoz \> és attribútumcsoporthoz \>**
1. Hozzon létre egy olyan attribútumcsoportot, amely inget **tartalmaz**.
1. Adja hozzá a következő attribútumokat: **CleaningMethod,Type** **·**, **Collection** és **Design**.

> [!NOTE]
> Az attribútumcsoport attribútumcsoportja attribútumainak megjelenítési sorrendje nincs hatással a finomítók sorrendjére a keresési és kategória tallózási eredményei között. Ezek csak a "rendelésattribútumok" esetre alkalmazhatók.

### <a name="assign-attribute-groups-to-categories"></a>Attribútumcsoportok társítása kategóriákhoz

A következő típusú kategóriahierarchiákban egy vagy több attribútumcsoport társítható kategória-csomópontokhoz:

- Kereskedelmi termékhierarchia
- Csatorna navigációs kategóriájának hierarchiája
- Kiegészítő termékkategória hierarchiája

Ha a termékeket attribútumcsoportokba sorolja, akkor öröklik az attribútumcsoportokban található attribútumokat.

![Termékattribútum-csoportok gyorslapja a Commerce termékhierarchia oldalon](media/AGRetailProdHierarchy_2022Series.png)

Ha a Commerce termékhierarchia kategóriáihoz attribútumcsoportokat szeretne hozzárendelni, kövesse az alábbi példa lépéseit.

1. Kereskedelmi vezetőként jelentkezzen be a Commerce Headquartersbe.
1. Ugorjon a **Kiskereskedelem és kereskedelem \> Termékek és kategóriák \> Kereskedelmi termékhierarchia** lehetőségre.
1. Válassza ki **a divatház** navigációs hierarchiáját.
1. A **Menskategóriában** válassza **a Kategóriát**, **·** **majd a Gyorstribútum-csoportok termékattribútum-csoportokban adjon hozzá egy attribútumcsoportot, amely a Férfi attribútumok neve**.
1. Jelölje be a **Divatnapszemüvegek** kategóriát, és ellenőrizze az új attribútumokat a **Divatnapszemüvegek** attribútumcsoportban az **Attribútumok megtekintése** kiválasztásával. Az attribútumcsoportnak meg kell jelenítenie az új **Lencsealakzat** és **Napszemüvegmárka** attribútumokat.
1. Válassza ki **a Kategóriát**, és ellenőrizze **a Férfi** **attribútumcsoport attribútumainak megfelelő attribútumokat az Attribútumok megtekintése lehetőség választásával**. Az attribútumcsoportban meg kell jelenítenie a **Férfiövmárka**, az **Öv anyaga** és az **Öv mérete** attribútumoknak.

Ugyanez az alapvető eljárás használható attribútumcsoportoknak a csatorna-navigációs kategóriahierarchia és a kiegészítő termékkategória-hierarchia kategóriáihoz való hozzárendelésére is. A 2. lépésben azonban használja az alábbi elérési utak egyikét attól a hierarchiától függően, amelyekhez attribútumcsoportokat szeretne hozzárendelni:

- **Csatornanavigációs kategóriahierarchia: Ugrás** **a kiskereskedelmi és kereskedelmi \> kategóriákra és a termékkezelési \> csatorna navigációs kategóriáira**.
- **Kiegészítő termékkategória-hierarchia: Ugrás** a kiskereskedelmi **és kereskedelmi \> kategóriákhoz és a termékkezelés \> kiegészítő termékkategóriáihoz**.

> [!NOTE]
> Győződjön meg arról, hogy egy kategóriahierarchiában csak a Termékattribútum-csoportok gyorscsoporthoz társít attribútumcsoportokat, **nem** pedig a **Kategóriaattribútum**-értékek gyors oldalon. Ha az attribútumok megjelennek a Kategóriaattribútum-értékek **gyorspanelen**, válassza a **Munkaablak Kategóriahierarchia** szerkesztése lehetőséget. Ezután a Kategóriaattribútum-csoportok **gyors** oldalon jelölje ki a kategória-csomópontokat, és válassza az Eltávolítás **lehetőséget**. Kategória szerint nem lehet bekérni az attribútumokat a Commerce Scale Unit segítségével.

## <a name="identify-viewable-and-refinable-attributes-for-commerce-channels-for-the-default-product-collection"></a>Az alapértelmezett termékgyűjtemény commerce csatornáiban megtekinthető és testreszabható attribútumok azonosítása

Miután a különböző attribútumcsoportokat társította a különböző hierarchiák kategóriáihoz (Commerce termékhierarchia vagy csatornanavigációs kategóriák), és a kategória-társítás alapján mindegyik termékhez meghatározott attribútumértékeket adott meg, **engedélyeznie** kell az Attribútum megjelenítése a csatornajelzőn attribútumot, hogy ezek az attribútumok megtekinthetők legyen egy adott csatornában.

1. Nyissa meg a következőt: **Kiskereskedelem és kereskedelem \> Csatorna beállítása \> Csatornakategóriák és termékattribútumok**.
1. Válassza ki **az attribútum metaadatainak** beállítása, majd válasszon egy attribútumot a bal oldali navigációs ablakban.
1. A csatorna **termékattribútumainak** gyorscsoportján (**nem** pedig a Kategóriaattribútumok gyorsattribútumoknál) **·** **állítsa** az Attribútum megjelenítése a csatornán beállítás Igen beállítást, hogy az attribútum megtekinthető legyen.
1. Ha azt szeretné, hogy az attribútum is finomítható legyen, **állítsa Igen beállításra a Lehet finomhangolható** **beállítást**.

### <a name="control-visibility-of-dimension-based-refiners-such-as-size-style-and-color"></a>A dimenzión alapuló finomítók (például méret, stílus és szín) láthatóságának szabályozása

A leggyakrabban a termékdimenziókat, például a méretet, a stílust és a színt használják. Ha ezeket a termékdimenziókat finomítóként szeretné elérhetővé tenni, attribútumcsoportot kell társítani a csatorna szintjén, amely hivatkozást tartalmaz egy olyan attribútumtípusra, amely automatikusan örökli az értékeket a termékdimenzió értékeiből.

A csatornakategóriák és **termékattribútumok lapján a jelzők frissítésével meghatározhatja, hogy a termékdimenziók megtekinthetők és testreszabhatóak** legyen. Válassza ki a gyökércsomópontot a navigációs ablakban, **·** **·** **·** **majd** a Csatorna termékattribútumok gyorslapon állítsa az Attribútum megjelenítése a csatornán lehetőséget Igen beállításra a Méret, **·** **Stílus és Szín** attribútumok esetén. Ha azt szeretné, hogy ezek az attribútumok is finomíthatók legyen, **·** **mindegyikhez állítsa a Lehet finomhangolható beállítás Igen** beállítást.

![A dimenziófinomítók attribútum-metaadatainak beállítása](./media/ProductDimensionRefinersMetadataSetup_2022Series.png)

Ha engedélyezni szeretné az attribútumokat úgy, hogy elérhetők a bemutatóadat-alapú Csatornán, kövesse az alábbi példa lépéseit.

1. Nyissa meg a következőt: **Kiskereskedelem és kereskedelem \> Csatorna beállítása \> Csatornakategóriák és termékattribútumok**.
1. Válassza ki a **Houston** csatornát.
1. Válassza a műveleti ablakban az **Attribútum-metaadatok beállítása** lehetőséget.
1. Válassza ki a **Divat** kategória-csomópont, majd a **Csatorna termékattribútumok** gyorslapon jelölje be az **Attribútum befoglalása** lehetőséget minden attribútumra.
1. Válassza ki a **Divatáru kiegészítők** kategória-csomópontot, válassza ki a **Divatnapszemüvegek** kategóriát, majd a **Csatorna termékattribútumok** gyorslapon jelölje be az **Attribútum befoglalása** lehetőséget minden attribútumra.
1. Válassza ki a **Férfiruházat** kategória-csomópontot, válassza ki a **Nadrágok** kategóriát, majd a **Csatorna termékattribútumok** gyorslapon jelölje be az **Attribútum befoglalása** lehetőséget minden attribútumra.
1. A tervezett attribútumok és finomítók attribútum-metaadatainak frissítése után mentse a módosításokat, **és** futtassa a Csatornafrissítések közzététele feladatot. Ezután a frissítések közzététele után a következő feladatokat kell futtatni: **1070** (**csatornakonfiguráció**), 1040 **(** **Termékek)** **és 1150** (**Katalógus).**

> [!NOTE]
> - Ha a vállalat megköveteli, hogy gyakran adjon hozzá vagy távolítson el termékeket a navigációs hierarchiából, vagy például a megjelenített rendelési értékek frissítését, új kategóriák hozzáadását és új attribútumcsoportokat adjon a kategóriákhoz, javasoljuk, **hogy** a Csatornafrissítések közzététele feladatot gyakori kötegelt feladatként futtassa. Másik lehetőségként **manuálisan** aktiválhatja a Csatornafrissítések közzététele feladatot, Commerce Data Exchange majd a következő (CDX-) feladatokat: **1070** (**csatornakonfiguráció**), **1040** (**Termékek**) **és 1150** (**Katalógus**).
> - Az **Öröklés** lehetőséggel megadhatja, hogy a csatorna örökölje az attribútumcsoportokat a szülő csatornától a hierarchiában. Ha az **Öröklés** lehetőséget **Igen** beállításra állítja, a gyermek csatornacsomópont örökli az összes attribútumcsoportot, az attribútumcsoportokban levő összes attribútummal együtt.
> - Ha a Művelet ablaktábla **Attribútum-metaadatok beállítása gombja nem érhető el, győződjön meg arról,** **·** **hogy az Általános gyorspanelen társítva van a csatornához navigációs hierarchia.**
> - Csatornaszinten (**·** **például** a csatornakategóriák és termékattribútumok lapján található Attribútumcsoportok) kivételével nem társíthat attribútumcsoportokat.
> - A Commerce rendszer 10.0.27-es verziójában a vevőspecifikus vállalat-vállalat (B2B) katalógusok támogatásának bevezetése után várhatóan az egyes B2B-katalógusok finomítóját és attribútumbeállítását azonosítsa az ebben a cikkben ismertetett módon.

## <a name="override-attribute-values"></a>Attribútumértékek felülbírálása

Az attribútumok alapértelmezett értéke felülírható az egyedi termékek esetében a termékszinten. Ezek az egyes katalógusok egyes termékeire is felülbírálhatók, amelyek meghatározott csatornákra irányulnak.

### <a name="override-the-attribute-values-of-an-individual-product"></a>Az egyedi termékek attribútumértékeinek felülbírálása

Ha felül szeretné bírálni egy adott termék attribútumértékeit, kövesse az ebben a példában megadott lépéseket.

1. Kereskedelmi vezetőként jelentkezzen be a Commerce Headquartersbe.
1. Ugrás a **kiskereskedelmi és kereskedelmi \> kategóriákhoz és a termékkezelés \> kiadott termékeihez kategória szerint**.
1. Válassza ki **a Fashion \> Fashion Kiegészítők \> divatterveit**.
1. Jelölje be a kívánt terméket a rácsban. Ezután a műveleti ablaktáblán a **Termék** lapon a **Beállítás** csoportban válassza a **Termékattribútumok** lehetőséget.
1. Jelöljön ki egy attribútumot a bal oldali ablakban, és frissítse az értékét a jobb oldali ablakban.

![Termékattribútum-értékek lap.](media/ProdDetailsProdAttrValues_2022Series.png)

### <a name="override-the-attribute-values-of-all-products-in-a-catalog"></a>Katalógusban található összes termék attribútumértékének felülbírálása

Ha felül szeretné bírálni egy katalógus minden termékének attribútumértékeit, kövesse az ebben a példában megadott lépéseket.

1. Kereskedelmi vezetőként jelentkezzen be a Commerce Headquartersbe.
1. Ugrás a **Retail and Commerce \> Catalog management All \> katalógushoz**
1. Válassza ki a **Fabrikam Base Catalog** katalógust.
1. Válassza ki **a Fashion \> Fashion Kiegészítők \> divatterveit**.
1. A **Termékek** gyorslapon jelölje be a szükséges terméket, és válassza ki az **Attribútumok** elemet a termékrács felett.
1. A következő gyorslapon frissítése a szükséges attribútumok értékeit:

    - Megosztott termékhez tartozó média
    - Megosztott termékattribútumok
    - Csatornamédia
    - Csatornatermék-attribútumok

### <a name="override-the-attribute-values-of-all-products-in-a-channel"></a>A csatorna összes termékének attribútumértékének felülbírálása

Ha felül szeretné bírálni egy csatorna összes termékének attribútumértékeit, kövesse az ebben a példaként megadott lépéseket.

1. Kereskedelmi vezetőként jelentkezzen be a Commerce Headquartersbe.
1. Nyissa meg a következőt: **Kiskereskedelem és kereskedelem \> Csatorna beállítása \> Csatornakategóriák és termékattribútumok**.
1. Válassza ki a **Houston** csatornát.
1. A **Termékek** gyorslapon jelölje be a szükséges terméket, és válassza ki az **Attribútumok** elemet a termékrács felett.
1. Ha nem érhető el termék, válassza a **Hozzáadás** **gombra** a Termékek gyorspanelen, **majd válassza ki a szükséges termékeket a Termékek hozzáadása párbeszédpanelen.**
1. A következő gyorslapon frissítése a szükséges attribútumok értékeit:

    - Megosztott termékhez tartozó média
    - Megosztott termékattribútumok
    - Csatornamédia
    - Csatornatermék-attribútumok

### <a name="define-variant-specific-attribute-values-and-define-multiple-values-for-product-attributes"></a>Változatspecifikus attribútumértékek definiálása és több érték meghatározása a termékattribútumokhoz

A változatspecifikus attribútumértékek meghatározásához és a termékattribútumok több értékének meghatározásához kövesse az alábbi példa lépéseit.

1. Kereskedelmi vezetőként jelentkezzen be a Commerce Headquartersbe.
1. Nyissa meg a következőt: **Kiskereskedelem és kereskedelem \> Csatorna beállítása \> Csatornakategóriák és termékattribútumok**.
1. Válassza ki a **Houston** csatornát.
1. A Termékek **gyors** oldalon válassza ki a kívánt termékváltozatot, majd **válassza** ki a termékrács fölötti attribútumokat.
1. Ha nem érhető el termék, válassza **·** **a** Hozzáadás gombra a Termékek gyorspanelen, **majd válassza ki a szükséges termékváltozatokat a Termékek hozzáadása párbeszédpanelen.**
1. A következő gyorslapon frissítése a szükséges attribútumok értékeit:

    - Megosztott termékhez tartozó média
    - Megosztott termékattribútumok
    - Csatornamédia
    - Csatornatermék-attribútumok

#### <a name="example-of-variant-specific-attribute-configuration"></a>Példa változatspecifikus attribútumkonfigurációra
        
Ebben a példában **a P001-Master** termék egy három különböző változatból áll, **a** Futás, **a Variáns** **és aCipking** több tevékenységből áll. Minden egyes változatnál egyedileg meg szeretné határozni a **Tevékenység** attribútum értékét. A csatorna **csatornakategóriái** **és** termékattribútum-oldalának Termékek gyorslapján határozza meg a változatok Tevékenység attribútumértékét, **amint** az a következő táblázatban látható.

| Változat     | Tevékenységattribútum értéke |
|-------------|--------------------------|
| P001-Master | Sport                   |
| P001-1      | Fut                  |
| P001-2      | Járás                  |
| P001-3      | Trekking                 |

Ha egy felhasználó "gyártott" terméket keres, **a P001-Master** termék megjelenik a keresési eredmények között. **Ha** a Tevékenység attribútumot finomíthatóként állította be, **·** **akkor** a tevékenység finomítója csak a sportot fogja definiálható értékként felsorolni, **·** **mivel ez az érték a P001 alaptermék** szintjén lett meghatározva a Tevékenység attribútumhoz.

Alapértelmezés szerint a változatszintű attribútumok csak a termék részletező lapjain (PDP) használhatók. Ha egy PDP-hez kiválaszt egy adott termékváltozatot, a rendszer frissíti a PDP termékselőírásokat erre a változatra.

A finomítóknak a termékváltozat szintjén meghatározott attribútumértékek kiválasztásához meg kell határoznia egy attribútumot az alaptermék szintjén, **be** kell állítania a Több érték engedélyezése jelölőnégyzetet, **és az attribútumtípust Szöveg beállításra kell állítania**.

Ezután meg kell határoznia a termékváltozatok összes lehetséges értékét. Az ebben a példában használt tevékenységattribútumhoz tartozhat a Futás, **·** **·** **·** **Az Idő, Az időzónák, a Attribútumok,** a **Beleking** **, a Waterparts** **és aÉrték-tulajdonságok.** **·**

Miután meghatározta, hogy milyen változóattribútum-értékeknek kell lennie, a táraval elválasztott értékekkel határozhatja meg őket az alaptermék szintjén. A Tevékenység **attribútumhoz** az **alaptermék attribútumértékét Futás értékként határozhatja meg| | | Csak egy | | Víz | A (<a0/<a2**

Ezután mindegyik változathoz megadhatja az attribútumértékeket úgy, hogy vagy tára választja el az értékeket, vagy csak egy értéket ad meg. A Tevékenység **attribútumnál** egy adott termékváltozatot futásra lehet konfigurálni **| | Indulás**, **futás**, **futás| | Vízpartok** stb.

Miután meghatározta a változatattribútum értékeit, **·** **a** Munkaablak Csatornakategóriák és termékattribútumok lapján válassza a Csatornafrissítések közzététele lehetőséget, **majd futtassa a 1150-es**, **1040-es** **és 1070-es** feladatokat.

A feladatok befejezése és a keresési index frissítése után minden várt értéknek meg kell jelenni a keresési eredményekben és a kategória tallózási eredményeiben.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
