---
title: "Attribútumok és attribútumcsoportok"
description: "Ez a témakör azt írja le, hogyan lehet attribútumok segítségével egy terméket és a jellemzőit leírni a felhasználó által definiált mezőkben."
author: ashishmsft
manager: AnnBe
ms.date: 04/28/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2018-03-30
ms.dyn365.ops.version: Application pdate 5, AX 8.0
ms.translationtype: HT
ms.sourcegitcommit: 190d0b59ad2e232b33b3c0d1700cbaf95c45aeca
ms.openlocfilehash: 76b78a898a619f1bc7faa4749e5380a0ccfef527
ms.contentlocale: hu-hu
ms.lasthandoff: 01/04/2019

---

# <a name="attributes-and-attribute-groups"></a>Attribútumok és attribútumcsoportok

[!include [banner](includes/banner.md)]

Az *Attribútumok* lehetővé teszik a termék és a jellemzői további leírását felhasználó által definiált mezőkkel (például **Memória mérete**, **Merevlemez kapacitása**, **Energy Star kompatibilis** és így tovább). A Microsoft Dynamics 365 for Finance and Operations esetében az attribútumok különböző Retail entitásokhoz, például termékkategóriákhoz és kiskereskedelmi csatornákhoz, társíthatók, és megadhatók hozzájuk alapértelmezett értékek. A termékek ezután öröklik az attribútumokat és a hozzájuk tartozó alapértelmezett értékeket, amikor társítják őket egy termékkategóriához vagy kiskereskedelmi csatornához. Az alapértelmezett értékek felülírhatók az egyes termékek szintjén, a kiskereskedelmi csatorna szintjén vagy a kiskereskedelmi kategóriában.

Például egy tipikus televízió terméknek a következő attribútumai lehetnek.

| Kategória   | Attribútum                | Megengedett értékek          | Alapértelmezett érték |
|------------|--------------------------|-----------------------------|---------------|
| TV és videó | Márka                    | Bármilyen érvényes márkaérték       | Nincs          |
| TV         | Képernyőméret              | 20–80 hüvelyk                | Nincs          |
|            | Függőleges felbontás      | 480i, 720p, 1080i vagy 1080p | 1080p         |
|            | Képernyő-frissítési gyakoriság      | 60hz, 120hz vagy 240hz       | 60hz          |
|            | HDMI-bemenetek              | 0–10                        | 3             |
|            | DVI-bemenetek               | 0–10                        | 1             |
|            | Kompozit bemenetek         | 0–10                        | 2             |
|            | Komponens bemenetek         | 0–10                        | 1             |
| LCD        | 3D Ready                 | Igen vagy Nem                   | Igen           |
|            | 3D Enabled               | Igen vagy Nem                   | Nincs            |
| Plazma     | Min. üzemhőmérséklet      | 32–110 fok              | 32            |
|            | Max. üzemhőmérséklet        | 32–110 fok              | 100           |
| Projektoros | Képcsőgarancia | 6, 12 vagy 18 hónap         | 12            |
|            | Képcsövek száma (\# képcső)   | 1–5                         | 3             |

## <a name="attributes-and-attribute-types"></a>Attribútumok és attribútumtípusok

Az attribútumok az *attribútumtípusokon* alapulnak. Az attribútumtípus az adott attribútumba bevihető adatok típusát azonosítja. A Finance and Operations jelenleg a következő attribútumtípusokat támogatja:

- **Pénznem** – Ez a típus egy pénznemértékeket támogat. Lehet kötött (vagyis támogathat egy értéktartományt) vagy nyitva is hagyható.
- **DateTime** – Ez a típus a dátum és idő értékeket támogatja Lehet kötött, vagy nyitva is hagyható.
- **Decimal** – Ez a típus egy numerikus értéket támogat, amely tizedesjegyeket tartalmaz. Mértékegységet is támogat. Lehet kötött, vagy nyitva is hagyható.
- **Itenger** – Ez a típus egy numerikus értékeket támogat. Mértékegységet is támogat. Lehet kötött, vagy nyitva is hagyható.
- **Text** – Ez a típus egy szöveges értéket támogat. Előre meghatározott, lehetséges értékcsoportokat is támogat (vagyis *felsorolás*).
- **Boolean** – Ez a típus egy bináris értéket támogat (**igaz** vagy **hamis**).
- **Hivatkozás** – Ez a típus más jellemzőkre hivatkozik.

### <a name="set-up-attribute-types-in-finance-and-operations"></a>Attribútumtípusok beállítása a Finance and Operations alkalmazásban

1. Jelentkezzen be a Finance and Operations háttérirodai ügyfelébe kiskereskedelmi termékkihelyezési vezetőként.
2. Ugorjon a következő útvonalra: **Termékinformációk kezelése** &gt; **Beállítás** &gt; **Kategóriák és attribútumok** &gt; **Attribútumtípusok**.
3. Hozzon létre két **Szöveg** típusú attribútumtípust, állítsa a **Rögzített lista** lehetőséget az **Igen** beállításra, majd adja hozzá az értékek listáját:

    - Egy attribútumtípust nevezzen el így: **Lencsealakzat**, és adja meg a következő értéket: **Ovális**, **Szögletes** és **Négyszög**.
    - A másik attribútumtípust nevezze el így: **Napszemüvegmárka**, és adja meg a következő értéket: **Ray ban**, **Aviator** és **Oakley**.

![Attribútumtípusok](media/AttributeType.png)

### <a name="set-up-an-attribute-in-finance-and-operations"></a>Attribútum beállítása a Finance and Operations alkalmazásban

1. Jelentkezzen be a háttérirodai ügyfélbe kiskereskedelmi termékkihelyezési vezetőként.
2. Ugorjon a következő útvonalra: **Termékinformációk kezelése** &gt; **Beállítás** &gt; **Kategóriák és attribútumok** &gt; **Attribútumok**.
3. Hozzon létre egy **Lencsék** nevű attribútum.
4. Állítsa az **Attribútumtípus** mezőt **Lencsealakzat** értékre.

![Attribútumok](media/Attribute.png)

## <a name="attribute-metadata"></a>Attribútum metaadatai

Az *Attribútum-metaadatok* beállítások megadását teszi lehetővé annak a megadásához, hogy az attribútumok termékenként hogyan működjenek. Megadhatja például, hogy szükség van-e attribútumokra, hogy használhatóak-e keresésekhez, illetve szűrőként.

Kiskereskedelmi termékek esetén az attribútummetaadat-beállítások a csatorna szintjén felülbírálhatók. Ezt a lehetőséget a témakör későbbi tárgyalja.

Megfigyelheti, hogy az **Attribútumok** lap tartalmazza a beállításokat, amelyek kapcsolódnak az attribútum-metaadatokhoz. Az **attribútum-metaadatok a POS számára** alatt egy **Szűkíthető** nevű lehetőség befolyásolja az attribútumértékek viselkedését a kiskereskedelmi pénztárban, vagy azt, hogy a rendszer hogyan kezeli ezeket az attribútumértékeket. Csak azok az attribútumok, amelyekre beállíthatja a **Szűkíthető** lehetőség **Igen** beállítását, jelennek meg a retail POS alkalmazásban termékek finomítására vagy szűrésére.

Az alábbiak a további attribútummetaadat-beállítások az **Attribútumok** lapon:

- Kereshető
- Beolvasható
- Lekérdezhető
- Rendezhető
- Több érték engedélyezése
- Kis- és nagybetűk, illetve formázás figyelmen kívül hagyása
- Teljes egyezés

Ezek a beállítások eredetileg az online kirakat keresési funkciójának javítására szolgáltak. Bár a Finance and Operations nem tartalmazza az online kirakatot alapértelmezetten, része az eCommerce Publishing szoftverfejlesztői készlet (SDK). Felhasználók használhatják az SDK-t termékek elhelyezésére tetszés szerinti keresési indexben. Annak ellenére, hogy a termékadatokat importálják, a vevőknek továbbra is meg kell tudniuk különböztetni a kereshető adatokat, a lekérdezhető adatokat és így tovább. Így össze lehet állítani egy optimális indexet annak a biztosítására, hogy csak azok az attribútumok lesznek indexelve, amelyeket *véleményük szerint* indexelni kell.

A fennmaradó lehetőségek céljával kapcsolatos további tudnivalókat lásd: [A SharePoint Server 2013 keresési sémájának áttekintése](https://technet.microsoft.com/library/jj219669.aspx).

## <a name="filter-settings-for-attributes"></a>Attribútumok szűrési beállításai

Az attribútumok szűrőbeállításaival határozható meg, hogyan jelennek meg a kiskereskedelmi pénztárban az attribútumok szűrői. Egy attribútum szűrőbeállításainak eléréséhez az **Attribútumok** lapon a Finance and Operations alkalmazásban válassza ki az attribútumot, majd a műveleti ablakban válassza a **Szűrőbeállítások** lehetőséget.

A **Szűrőmegjelenítési beállítások** lap tartalmazza a következő mezőket:

- **Név** – Alapértelmezés szerint a mező értéke az attribútum neve. Ez az érték azonban módosítható.
- **Megjelenítési beállítás** – A következő beállítások közül választhat:

    - **Egyetlen érték** – Ez a lehetőség a következő attribútumtípusokhoz érhető el: **logikai**, **pénznem**, **decimális**, **egész** és **szöveg**. Ez a beállítás lehetővé teszi az attribútumok finomítását egyetlen érték kiválasztásával az ügyfélprogramban.
    - **Többértékű** – Ez a lehetőség a következő attribútumtípusokhoz érhető el: **pénznem**, **decimális**, **egész** és **szöveg**. Ez a beállítás lehetővé teszi az attribútum finomítását több érték kiválasztásával az ügyfélprogramban.

- **Megjelenítés szabályozása** – A következő beállítások közül választhat:

    - **Lista** – Ez a beállítás minden attribútumtípushoz elérhető.
    - **Tartomány** – Ez a lehetőség a következő attribútumtípusokhoz érhető el: **pénznem**, **decimális** és **egész**.
    - **Csúszka** – Ez a lehetőség a következő attribútumtípusokhoz érhető el: **pénznem**, **decimális** és **egész**.
    - **Csúszka sávokkal** – Ez a lehetőség a következő attribútumtípusokhoz érhető el: **pénznem**, **decimális** és **egész**.

- **Küszöbérték** – A beállítás akkor szükséges, ha a **Tartomány** lehetőséget választotta a megjelenítés szabályozási típusának. Elválasztóként a pontosvessző (;) használatával definiálhat értékeket.

    Például a **Táskatérfogat** szűrőnél a küszöbérték lehet **10; 20. 50. 100. 200; 500; 1000; 5000**. Ebben az esetben a kiskereskedelmi pénztár a következő tartományokat jeleníti meg. A tartományok, amelyek nem rendelkeznek termékekkel az eredményben, inaktívvá válnak.

    - Kevesebb mint 10
    - 10–20
    - 20–50
    - 50–100
    - 100–200
    - 200–500
    - 500 vagy több

![Attribútumszűrő beállításai](media/AttributeFilterSettings.PNG)

## <a name="attribute-groups"></a>Attribútumcsoportok

Az attribútumok a definiálásuk után attribútumcsoportokhoz rendelhetők. A termékkonfigurációs modellben lévő összetevők és részösszetevők egyes attribútumainak csoportosítására egy *attribútumcsoport* szolgál. Több attribútumcsoportba is felvehet egy attribútumot. Az attribútumcsoportok segíthetik a felhasználókat a termékek konfigurálásában, mert a különböző kiválasztások rendezve jelennek meg az adott környezetben. Az attribútumcsoportokat hozzárendelheti a kiskereskedelmi csatornákhoz vagy a kiskereskedelmi kategóriákhoz.

Ezenfelül beállíthat alapértelmezett értékeket az attribútumokhoz, amelyek szerepelnek egy attribútumcsoportban. Például szín attribútum hozzáadása egy attribútumcsoporthoz, és a **kék** kiválasztása alapértelmezett attribútumértékeként. Ebben az esetben, amikor az attribútumcsoport hozzáadják egy kiskereskedelmi termékekhez, amelyik az egyik attribútumként a színt is tartalmazza, a **kék** jelenik meg a termék alapértelmezett színeként.

![Attribútumcsoportok](media/AttributeGroup.png)

### <a name="create-an-attribute-group"></a>Attribútumcsoport létrehozása

1. Jelentkezzen be a háttérirodai ügyfélbe kiskereskedelmi termékkihelyezési vezetőként.
2. Ugorjon a következő útvonalra: **Termékinformációk kezelése** &gt; **Beállítás** &gt; **Kategóriák és attribútumok** &gt; **Attribútumcsoportok**.
3. Hozzon létre egy **divatnapszemüvegek** nevű attribútumcsoport.
4. Adja hozzá a következő attribútumokat: **Lencsealakzat** és **Napszemüvegmárka**.

### <a name="assign-attribute-groups-to-retail-categories"></a>Attribútumcsoportok társítása kiskereskedelmi kategóriákhoz

Egy vagy több attribútumcsoport társítható a kategória-csomópontokkal a következő típusú kiskereskedelmikategória-hierarchiákban: kiskereskedelmi termékek hierarchiája, csatornák navigációs kategóriahierarchiája és kiegészítő termékek kategóriahierarchiája. Ezután, a kategorizálást követően, a termékek öröklik az attribútumcsoportba tartozó attribútumokat.

![Kiskereskedelmi termékek hierarchiája – Termékattribútum-csoportok](media/AGRetailProdHierarchy.PNG)

Kövesse az alábbi lépéseket attribútumcsoportok hozzárendeléséhez kategóriákhoz a kiskereskedelmi termékek hierarchiájában.

1. Jelentkezzen be a háttérirodai ügyfélbe kiskereskedelmi termékkihelyezési vezetőként.
2. Menjen ide: **Kiskereskedelem** &gt; **Kategória és termék kezelése** &gt; **Kiskereskedelmi termékek hierarchiája**.
3. Válassz a **Divat navigációs hierarchiája** elemet.
4. A **Férfiruházat** alatt jelölje be a **Nadrágok** kategóriát, majd a **Termékattribútum-csoportok** gyorslapon adja hozzá a **Férfiöv** nevű attribútumcsoportot.
5. Jelölje be a **Divatnapszemüvegek** kategóriát, és ellenőrizze az új attribútumokat a **Divatnapszemüvegek** attribútumcsoportban az **Attribútumok megtekintése** kiválasztásával.

    Az attribútumcsoportnak meg kell jelenítenie az új **Lencsealakzat** és **Napszemüvegmárka** attribútumokat.

6. A **Férfiruházat** alatt jelölje be a **Nadrágok** kategóriát, és ellenőrizze a **Férfiöv** attribútumcsoportot az **Attribútumok megtekintése** kiválasztásával.

    Az attribútumcsoportban meg kell jelenítenie a **Férfiövmárka**, az **Öv anyaga** és az **Öv mérete** attribútumoknak.

> [!NOTE]
> Ezzel az eljárással attribútumcsoportokat is hozzárendelhet a kategóriákhoz a csatorna navigációs kategóriahierarchiájában és a kiegészítő termékek kategóriahierarchiájában. A 2. lépésben használja a következő navigációs elérési utakat:
>
> - **Kiskereskedelem** &gt; **Kategória és termék kezelése** &gt; **Csatorna navigációs kategóriák**
> - **Kiskereskedelem** &gt; **Kategória és termék kezelése** &gt; **Kiegészítő termékkategóriák**.

### <a name="assign-attribute-groups-to-retail-stores"></a>Attribútumcsoportok hozzárendelése kiskereskedelmi boltokhoz

Egy vagy több attribútumcsoport társítható kiskereskedelmi üzlethez a kiskereskedelmi üzlet hierarchiában. A kategorizálást követően az adott kiskereskedelmi üzletekhez bővített termékek öröklik az attribútumcsoportba tartozó attribútumokat.

1. Jelentkezzen be a háttérirodai ügyfélbe kiskereskedelmi termékkihelyezési vezetőként.
2. Nyissa meg a következőt: **Kiskereskedelem** &gt; **Csatorna beállítása** &gt; **Csatornakategóriák és termékattribútumok**.
3. Attribútumcsoportok hozzárendelése a Houston csatornához:

    1. Válassza ki a **Houston** csatornát.
    2. Az **Attribútumcsoport** gyorslapon válassza a **Hozzáadás** elemet, majd a **Név** mezőben válassza ki ezt: **SharePointProvisionedProductAttributeGroup**.
    3. Válassza ismét a **Hozzáadás** elemet, és ezt követően a **Név** mezőben válassza ki a **Férfiöv** lehetőséget.
    4. Válassza ismét a **Hozzáadás** elemet, és ezt követően a **Név** mezőben válassza ki a **Divatnapszemüvegek** lehetőséget.

        > [!NOTE]
        > Egy beállítás lehetővé teszi annak a megadását, hogy ennek a csatornának örökölnie kell az attribútumcsoportokat a szülő csatornájától a hierarchiában. Ha az **Öröklés** lehetőséget **Igen** beállításra állítja, a gyermek csatornacsomópont örökli az összes attribútumcsoportot, az attribútumcsoportokban levő összes attribútummal együtt.

4. Az attribútumok engedélyezése, hogy elérhetők legyenek a Houston csatornában:

    1. Válassza a műveleti ablakban az **Attribútum-metaadatok beállítása** lehetőséget.
    2. Válassza ki a **Divat** kategória-csomópont, majd a **Csatorna termékattribútumok** gyorslapon jelölje be az **Attribútum befoglalása** lehetőséget minden attribútumra.
    3. Válassza ki a **Divatáru kiegészítők** kategória-csomópontot, válassza ki a **Divatnapszemüvegek** kategóriát, majd a **Csatorna termékattribútumok** gyorslapon jelölje be az **Attribútum befoglalása** lehetőséget minden attribútumra.
    4. Válassza ki a **Férfiruházat** kategória-csomópontot, válassza ki a **Nadrágok** kategóriát, majd a **Csatorna termékattribútumok** gyorslapon jelölje be az **Attribútum befoglalása** lehetőséget minden attribútumra.

![Csatornakategóriák és termékattribútumok – Attribútumcsoportok](media/CCPAttrGrp.png)

## <a name="overriding-attribute-values"></a>Attribútumértékek felülbírálása

Az attribútumok alapértelmezett értéke felülírható az egyedi termékek esetében a termékszinten. Az alapértelmezett érték is felülírható meghatározott katalógusokba tartozó egyedi termékek esetében, amelyek egy adott kiskereskedelmi csatornát céloznak meg.

### <a name="override-the-attribute-values-of-an-individual-product"></a>Az egyedi termékek attribútumértékeinek felülbírálása

1. Jelentkezzen be a háttérirodai ügyfélbe kiskereskedelmi termékkihelyezési vezetőként.
2. Menjen ide: **Kiskereskedelem** &gt; **Kategória és termék kezelése** &gt; **Felszabadított termékek kategóriák szerint**.
3. Válassza ki a **Divatáru** &gt; **Divatáru kiegészítők** &gt; **Divatnapszemüvegek** kategória-csomópontot.
4. Jelölje be a kívánt terméket a rácsban. Ezután a műveleti ablaktáblán a **Termék** lapon a **Beállítás** csoportban válassza a **Termékattribútumok** lehetőséget.
5. Jelöljön ki egy attribútumot a bal oldali ablakban, és frissítse az értékét a jobb oldali ablakban.

![Termékadatok lap – Termékattribútum-csoportok](media/ProdDetailsProdAttrValues.png)

### <a name="override-the-attribute-values-of-products-in-a-catalog"></a>A termékek attribútumértékeinek felülbírálása a katalógusban

1. Jelentkezzen be a háttérirodai ügyfélbe kiskereskedelmi termékkihelyezési vezetőként.
2. Menjen ide: **Kiskereskedelem** &gt; **Katalóguskezelés** &gt; **Minden katalógus**.
3. Válassza ki a **Fabrikam Base Catalog** katalógust.
4. Válassza ki a **Divatáru** &gt; **Divatáru kiegészítők** &gt; **Divatnapszemüvegek** kategória-csomópontot.
5. A **Termékek** gyorslapon jelölje be a szükséges terméket, és válassza ki az **Attribútumok** elemet a termékrács felett.
6. A következő gyorslapon frissítése a szükséges attribútumok értékeit:

    - Megosztott termékhez tartozó média
    - Megosztott termékattribútumok
    - Csatornamédia
    - Csatornatermék-attribútumok

    > [!NOTE]
    > Ha a megosztott termékhez tartozó média és a megosztott termékattribútumok létrehozása a Finance and Operations alkalmazásban jön létre, minden kiskereskedelmi termékre vonatkoznak.

![Katalógus-termékattribútum csoportok](media/CatalogProdAttrValues.png)

### <a name="override-the-attribute-values-of-products-in-a-channel"></a>A termékek attribútumértékeinek felülbírálása egy csatornában

1. Jelentkezzen be a háttérirodai ügyfélbe kiskereskedelmi termékkihelyezési vezetőként.
2. Nyissa meg a következőt: **Kiskereskedelem** &gt; **Csatorna beállítása** &gt; **Csatornakategóriák és termékattribútumok**.
3. Válassza ki a **Houston** csatornát.
4. A **Termékek** gyorslapon jelölje be a szükséges terméket, és válassza ki az **Attribútumok** elemet a termékrács felett.

    > [!NOTE]
    > Ha egy termék sem áll rendelkezésre, végezze el a kiválasztott termékek hozzáadását a **Hozzáadás** elemmel a **Termékek** gyorslapon, majd a szükséges terméket válassza ki a **Termékek hozzáadása** párbeszédpanelen.

5. A következő gyorslapon frissítése a szükséges attribútumok értékeit:

    - Megosztott termékhez tartozó média
    - Megosztott termékattribútumok
    - Csatornamédia
    - Csatornatermék-attribútumok

    > [!NOTE]
    > Ha a megosztott termékhez tartozó média és a megosztott termékattribútumok létrehozása a Finance and Operations alkalmazásban jön létre, minden kiskereskedelmi termékre vonatkoznak.

