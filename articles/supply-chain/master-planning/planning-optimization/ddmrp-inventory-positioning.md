---
title: Készlet pozicionakciója
description: Ez a cikk a stratégiai készletelrendezéssel kapcsolatban tartalmaz tájékoztatást, amelynek része az ellátási láncban található összeszerkeszedő pontok azonosítása, ahol az átfutási idők tömörítését és az ellátási láncban való összeszorzását lehetővé telő aktuális készletet lehet felépíteni.
author: t-benebo
ms.date: 06/30/2022
ms.topic: article
ms.search.form: ReqGroup, EcoResProductDetailsExtended
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2022-06-30
ms.dyn365.ops.version: 10.0.28
ms.openlocfilehash: bec36b5b51b937782afdb78d7009a58dcd0942f0
ms.sourcegitcommit: 529fc10074b06f4c4dc52f2b4dc1f159c36e8dbc
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/22/2022
ms.locfileid: "9186585"
---
# <a name="inventory-positioning"></a>Készlet pozicionakciója

[!include [banner](../../includes/banner.md)]
[!INCLUDE [preview-banner](../../includes/preview-banner.md)]

A stratégiai készlet pozicionzása az ellátási láncban a felépítési pontok azonosítását foglalja magában, amelyeken fel lehet építeni az aktuális készletet. Ez a megközelítés elsősorban az átfutási idők tömörítését és az átfutási idők felhasználhatók az ellátási láncban. Ezzel enyhíthető a "hatása", mivel az igény változhatósága nem elég az ellátási láncon lefelé. (Az *ingadozás* azt jelenti, hogy a kiskereskedelmi szintű igények kis ingadozásai növekvő ingadozásokat okozhatnak a nagykereskedelem, a terjesztő, a gyártó és a nyersanyag-szállítói szinteken.)

A készlet pozicionálta az igényvezérelt anyagok erőforrás-tervezésének első lépését.

## <a name="inventory-positioning-for-manufacturing"></a>Készlet pozicionakciója gyártáshoz

Ez a szakasz egy olyan példát mutat be, amely bemutatja, hogyan lehet készlet pozicionakciókat hozni egy tipikus termék gyártásához. A többszörösen megjelenő anyagjegyzék többszintű, mint azt az alábbi ábra mutatja.

![Példa többszintű anyagjegyzékre egy jól megfelelő termék esetén.](media/ddmrp-bom-example.png "Példa többszintű anyagjegyzékre egy visszaható termékhez")

### <a name="choose-your-decoupling-points"></a>Válassza ki a függetlenítési pontokat.

Ha azt választja, hogy hová tegye a lecsatolási pontokat, akkor feltételként vegye figyelembe az anyagjegyzékben az egyes cikkek összes következő aspektusát:

- Külső változhatóság
- Készletáttétel és rugalmasság
- Kritikus művelet védelme
- Vevői tűréshatár (idő)
- Értékesítési rendelés láthatósági horizontja
- Piaci potenciális átfutási idő

A példa példában a következő okokból lehet az első összecsukópontot *a* megfelelő számlázási pontként be tenni:

- Nehéz forrásként használni az anyagokat, amelyek a veszélyes anyagjegyzékek hoz használatosak, és az elérhetőség is veszélyes. Ebből következően *teljesül a* külső változhatósági feltétel.
- A gyártott váltókat több különböző formára és méretre lehet kivágni, hogy más, gyártott termékekhez is egyedi lapkák készítsenek, a műanyagok mellett. Ennek megfelelően teljesül *a készletáttételi és a rugalmassági* feltétel.

Ezt követően a következő összecsomópontot az *anyagcsomagra* lehet tenni, ez egy előre levágott anyag. Erre a pontra azért lehet választani, mert csak egy anyag vágási gépe van. Ennek megfelelően teljesül *a kritikus művelet-védelmi* feltétel.

Végül érdemes az utolsó összecsomópontot a befejezett jó cikkhez tenni. Ezt a pontot akkor választhatja, ha nagyon alacsony a *vevői* tűréshatára az értékesítésnél, *és* mivel az értékesítési rendelés láthatósági horizontja meglehetősen rövid. Ezért gondoskodni szeretne arról, hogy az aktuális készlet megfeleljen a bejövő rendeléseknek. Magasabb árat is be lehet állítani, ha az átfutási időt ilyen rövid ideig tartjuk, *és ezt jelenti a piaci potenciális átfutási idő feltétele*.

Az elemzés alapján a következő ábra azt mutatja be, hogy hogyan fog kinézni a 4000 anyagjegyzék. A sárga készletszimbólumokkal lehet kiemelni a hivatkozási pontokat.

![Példa anyagjegyzék a kiemelt pontokkal.](media/ddmrp-bom-decoupling-example.png "Példa anyagjegyzék a kiemelt pontokkal")

### <a name="calculate-your-decoupled-lead-time"></a>A leselepkedő átfutási idő kiszámítása

Ez a szakasz bemutatja, hogy hogyan lehet kiszámítani az új átfutási időket a pontbevallást követően.

Az előző részben elindított példa példaként illusztrált példában az átfutási idők szürke mezőkben jelennek meg az egyes anyagjegyzék-összetevők bal felső részén. A piros szerkezetű mezők az összesített átfutási időt (az anyagjegyzék egyes szintjeinél leghosszabb átfutási idők összegét) hajtó cikkeket jelölik. Ez az átfutási idő 21 nap a nullától kezdve.

![Példa anyagjegyzék átfutási idővel.](media/ddmrp-bom-lead-times-example.png "Példa anyagjegyzék átfutási idővel")

Ha viszont alkalmazza a korábban kiválasztott pontokat, akkor a lecsatolt cikkek mindig készleten lesznek. Ezért az átfutási idő 0 (nulla). A termelés új átfutási ideje most már csak öt nap: két nap a szál megvásárlása, és három nap a termeléshez. Ennek az átfutási időnek az neve *az összetolt átfutási idő*.

![Példa a lesiklott átfutási időre.](media/ddmrp-bom-decoupled-lead-time-example.png "Példa a lesiklott átfutási időre")

## <a name="strategic-inventory-positioning-in-a-retail-model"></a>Stratégiai készlet pozicionása kiskereskedelmi modellben

Mivel a kiskereskedők csak befejezett termékeket készleteznek, az AJ nem kiadás. A kiskereskedők azonban továbbra is használhatják a DDMRP-t, ha az elosztási hálózat tárolási helyei alapján stratégiai készlethelyeket és pufferszinteket ad meg.

Az alábbi ábra egy olyan vállalat példáját mutatja be, amely egy terjesztési központtal rendelkezik Iba és Atlantában, Atlantában és Atlantában.

![Pontok modellezése a kiskereskedelmi modellben található hely alapján](media/ddmrp-retail-decoupl-points-example.png "Pontok modellezése a hely alapján egy kiskereskedelmi modellben")

Előfordulhat, hogy úgy dönt, hogy egy kerettermék elosztási központ és üzletek közötti áthelyezésének ideje sérti a vevő tűréshatárát, mivel a vevők azt várják, hogy a *keret* készleten legyen a látogatáskor. Ebben az esetben mindhárom üzletben be kell állítania a keretcikkhez egy szűrési pontot. Minden üzletnek eltérő pufferszintje lesz az átfutási időktől, az igénymintáktól stb. függően.

## <a name="implement-inventory-positioning-in-dynamics-365-supply-chain-management"></a>Készlet pozicionálja a következő helyen: Dynamics 365 Supply Chain Management

Ez a szakasz bemutatja, hogyan lehet megvalósítani a készlet pozicioning stratégiáit a Microsoftnál Dynamics 365 Supply Chain Management.

### <a name="set-up-item-coverage-groups-that-create-decoupling-points"></a>Összefedő pontokat létrehozási cikkfedezeti csoportok beállítása

A cikkek olyan fedezeti pontokká válnak, amelyek egy Olyan fedezeti csoporthoz tartoznak, amely **a** *Fedezeti pont fedezeti kódértékkel van beállítva.* Ezért a DDMRP beállításának első lépése annak eldöntésében, hogy mely fedezetcsoportokat kell megvalósítanának a DDMRP stratégiához, majd ezeket a lépéseket követve hozza létre őket.

1. Manjen az **Alaptervezés \> Beállítás \> Fedezet \> Fedezeti csoportok** menübe.
1. Fedezeti csoport létrehozásához válassza **a munkaablak Új** lehetőséget.
1. Adja meg a fedezeti csoportot azonosító adatokat, majd válassza ki a használni kívánt naptárat.
1. Az Általános **lapon** állítsa **a Fedezeti kód** *mezőt a4/11/33. pontra*. Ez a beállítás azt jelenti, hogy a DDMRP rendszer az ehhez a fedezeti csoporthoz tartozó összes cikkre vonatkozó szűrési pontként kezeli. Ez a művelet a csoport minden DDMRP beállítását is engedélyezi, amint azt az eljárás későbbi leírása ismerteti.
1. **·** **A DDMRP** paraméterek szakasz Egyéb lapján állítsa be a következő mezőket:

    - **Átfutási** idő tényezője – adjon meg egy tényezőt (0 és 1 közötti decimális értékkel), amely meghatározza az átfutási idő hatását az ebben a fedezeti csoportban található cikkek minimális és maximális készletszintének kiszámításakor. Általában minél hosszabb az átfutási idő egy cikknél, annál alacsonyabb lesz az átfutási idő tényezője. Az alacsonyabb átfutásiidő-tényező alacsonyabb minimális és maximális készletszintet hoz létre, ezért kisebb és ritkább rendeléseket okoz. A DDMRP módszertan 0,20 és 0,40 közötti értéket javasol a hosszú átfutási idővel értékelt cikkekhez, a közepes átfutási idővel értékelt cikkekhez 0,41 és 0,60, a rövid átfutási idővel értékelt cikkekhez pedig 0,61 és 1,00 közötti értéket. További információ a pufferprofilban [és a szintekben található](ddmrp-buffer-profile-and-levels.md).
    - **Változósági tényező** – adjon meg egy tényezőt (0 és 1 közötti decimális értékkel) annak szabályozására, hogy milyen hatással legyen a változó igény az ebbe a fedezeti csoportba tartozik cikkek minimális készletszintjének a kiszámításakor. Általános szabály, hogy minél több változóra van igény egy cikknél, annál nagyobb változó tényezőnek kell lennie. A nagyobb variability tényező magasabb minimális készletszintet hoz létre. A DDMRP módszertan 0,00 és 0,40 közötti értéket javasol az olyan cikkeknél, amelyek kis változhatóságúak, 0,41 és 0,60 közötti cikkeket, a nagy változságú cikkeknél pedig 0,61 és 1,00 közötti értéket. További információ a pufferprofilban [és a szintekben található](ddmrp-buffer-profile-and-levels.md).
    - **Minimális, maximális és újrarendelési pontidőszak** – adja meg, hogy milyen gyakran kell a pufferértékeket számítani (*napi* vagy *heti*).

1. Az Egyéb **lap** Átlagos napi használati **területén** állítsa be a következő mezőket:

    - **Átlagos napi felhasználás alapja** – válassza ki, hogy mely időszakokon alapuljön az átlagos napi felhasználás (ADU) számítása. Válasszon a következő értékek közül:

        - *Elmúlt* – csak az **Elmúlt időszak (nap) mezőben megadott napok számában korábbi használatba van** adva. Az ADU számítása úgy történik, hogy a számítási időszakban a cikk összigényét elosztja a számítási időszak napjainak számán (készletegységben).
        - *Előre* – csak az előre jelzett jövőbeli felhasználást (és az előrejelzéseket is) nézze meg a Előre jelzett időszak (nap) **mezőben** megadott napok számában. Az ADU számítása úgy történik, hogy a számítási időszakban a cikk összigényét elosztja a számítási időszak napjainak számán (készletegységben). 
        - *Összeolvasva* – a múltba és a jövőbe is belevetve. Az Elmúlt időszak **(nap) mező,** az Előrehozott időszak (nap) **mező** és a párolási beállítások mind érvényesek. 

            *Súlyozott ADU* = (\[*múltbeli* súlyozási × *az ADU*\] + \[*előrehozott* súlyozás × *ADU*\]) ÷ (*múltbeli súlyozású* + *előre súlyozás*)

    - **Elmúlt időszak (napok)** – adja meg, hogy hány elmúlt napot (a mai napot is beleértve) kell a rendszernek figyelembe vennie, amikor kiszámítja az ebbe a fedezeti csoportba tartozik cikkek ADU-ját. Ez a beállítás csak akkor érvényes, ha **·** *a* mezőn alapuló átlagos napi használati érték Past vagy *Blended* beállítású.
    - **Előrei időszak (napok)** – adja meg, hogy hány jövőbeli napot (a mai naptól a megadott napig) kell a rendszernek figyelembe vennie, amikor kiszámítja az ebbe a fedezeti csoportba tartozik cikkek ADU-ját. Ez a beállítás csak akkor érvényes, ha **a mezőn alapuló átlagos napi használat beállítása** Előre vagy *Összeolvasva* *.*
    - **Az elmúlt időszak relatív** súlya a napi súlyozott átlaghoz – adja meg a súlyt (százalékban) az elmúlt időszakra a súlyozott ADU számítása során. Ez a beállítás csak akkor érvényes, ha **a** mezőn alapuló átlagos napi használat beállítása *Blended*.
    - **Az előrehozott időszak** relatív súlya a napi súlyozott átlaghoz – adja meg a súlyt (százalékban) az előrehozott időszakra a összetolt ADU számítása során. Ez a beállítás csak akkor érvényes, ha **a** mezőn alapuló átlagos napi használat beállítása *Blended*.

1. Az összes többi lap és mező részletes beállításainak megadása, amelyek az ehhez a fedezeti csoporthoz kapcsolt cikkek követelményeinek kiszámításához használatosak.

### <a name="set-an-item-as-a-decoupling-point"></a>Cikk beállítása lecsatolási pontként

A következő lépések szerint állíthatja be a cikkeket az összesítő pontként.

1. Kattintson a **Termékinformációk kezelése \> Termékek \> Kiadott termékek** lehetőségre.
1. Keresse meg és válassza ki azt a kiadott cikket, amely a DDMRP számára van beállítva.
1. A Munkaablak Terv lapján **válassza** a Cikkfedezet **lehetőséget**.
1. Előfordulhat, **hogy a Cikkfedezet** lapon már több cikkfedezeti rekord szerepel, amelyek a tárolási és termékdimenziók különböző kombinációira vonatkoznak. Kiválaszthatja azt a meglévő cikkfedezeti rekordot, amely azokra a dimenziókra vonatkozik, amelyekhez létre szeretne hozni egy újrafedő pontokat. Másik lehetőségként az Új **elemet** választja a munkaablakban új cikkfedezeti rekord létrehozásához.
1. A szokásos cikkfedezeti rekord beállítása. Legalább meg kell adnia azt a helyet és raktárt, ahol a felcsatolási pont érvényes lesz.
1. Amíg a megfelelő rekord ki van választva, válassza az Általános **lapot**.
1. Jelölje be a **Megadott beállítások használata** jelölőnégyzetet.
1. A Fedezetcsoport **mező** beállítása fedezeti csoportra, amely a kiegészítő pontok létrehozására van beállítva (az előző szakaszban leírtak szerint).
1. A cikk konfigurálva van egy szűrési pontként. A DDMRP általában itt olyan beállításokat is konfigurál, amelyek hatással vannak a pufferméretekre és az újrarendelési mennyiségre. Ezt a konfigurációt azonban később is befejezheti. A beállításokkal kapcsolatos további tudnivalókat [lásd: Pufferek beállítása egy összecsukópontos cikkhez](ddmrp-buffer-profile-and-levels.md#set-up-buffers).

> [!NOTE]
> Ha olyan cikkeket kell tervezni, amelyek nem pontokat tartalmaznak, kövesse ugyanezeket a lépéseket az általános anyagkövetelmény-tervezés (MRP) használata során.
