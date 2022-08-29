---
title: Áfabevallás (Dánia)
description: Ez a témakör azt ismerteti, hogyan lehet beállítani és létrehozni egy áfa-előlegbevallást Dániára.
author: AdamTrukawka
ms.date: 03/10/2022
ms.topic: article
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: atrukawk
ms.search.validFrom: ''
ms.openlocfilehash: a47b2b98d86daf50876c783f879362ec1addb579
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9272140"
---
# <a name="vat-declaration-denmark"></a>Áfabevallás (Dánia)

[!include [banner](../includes/banner.md)]

Ez a cikk bemutatja, hogyan lehet beállítani a dán áfabevallást, és előnézeti nézetet látni a dokumentumban Microsoft Excel.

A jelentés automatikus létrehozásához először hozzon létre elég áfakódot ahhoz, hogy az előleg áfabevallásán minden egyes mezőben külön áfakönyvelés legyen. Ezenkívül az előzetes áfabevallás elektronikus jelentéskészítési (ER) formátumának alkalmazásspecifikus paramétereiben társítsa a forgalmiadó-kódokat az áfabevalláson szereplő mezők keresésének eredményével.

Dánia esetében be kell állítani a Jelentés **mezőkeresést**. Az alkalmazásspecifikus paraméterek beállításával kapcsolatos további [tudnivalókat](#set-up-application-specific-parameters) lásd a Cikk áfabevallási mezők alkalmazásspecifikus paramétereinek beállítása című részében.

Az alábbi táblázatban a "Keresési eredmény" oszlop az áfabevallási formátumban egy adott áfabevallási sorhoz előre konfigurált keresési eredményt mutatja. Ezen információk segítségével helyesen társíthatja az áfakódokat a keresési eredményhez, majd az áfabevallás sorához.

### <a name="vat-declaration-overview"></a>Áfabevallás áttekintése

A dán áfabevallás a következő adatokat tartalmazza.

**VAT-fizetendő**

| Leírás                                                  | Adóalap/adó összege | Keresési eredmény/összesen                                                                                                                                                                                                                                                                                                                          |
|--------------------------------------------------------------|---------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Kimeneti áfa                                                   | Adó összege          | **OutputVAT**</br> **DomesticVATUseTax** (jelentés a "Bejövő áfa" mezőben is)                                                                                                                                                                                                                                                                       |
| Áruk áfása stb. Külföldi vásárlás                           | Adó összege          | **BeszerzésGoodsAbroad**</br>**PurchaseGoodsAbroadUseTax** (az "Input VAT" mezőben is jelentve)</br>**PurchaseGoodsEU** (Az adóalap jelentése az "A mező - árubeszerzés")</br>**PurchaseGoodsUSETax** (Az adó összegét az "Bemeneti áfa" mezőben is jelentik. Az adóalap jelentése az "A mező - árubeszerzés" mezőben található.                   |
| A külföldön beszerzett szolgáltatások áfája, amelyek a fordított adózás alá tartoznak | Adó összege          | **PurchaseServicesAbroad**</br> **PurchaseServicesAbroadUseTax** (jelentés az "Input VAT" mezőben is)</br>**PurchaseServicesEU** (Az adóalap jelentése az "A mező - szolgáltatásbeszerzés")</br>**PurchaseServicesUSETax** (az adó összegét az "Bemeneti áfa" mezőben is jelentik. Az adóalap jelentése az "A mező - szolgáltatásbeszerzés" alatt található. |
| Kötelezettségek összesen                                                | Adó összege          | Az előző három mező összege                                                                                                                                                                                                                                                                                                            |

**Levonások**

| Leírás                                                                               | Adóalap/adó összege | Keresési eredmény/összesen                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
|-------------------------------------------------------------------------------------------|---------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Bemeneti áfa                                                                                 | Adó összege          | **InputVAT**</br> **DomesticVATUseTax** (jelentés az "Output VAT" mezőben is)</br>**PurchaseGoodsAbroadUseTax** (jelentés az "Áruk áfával stb.) Beszerzett külföldi" mező)</br>**PurchaseServicesAbroadUseTax** (a fordított fizetés hatálya alá tartozó külföldi szolgáltatások áfáról is jelentve)</br>**PurchaseGoodsUSETax** (jelentés az "Áruk áfával stb.) Beszerzett külföldi" mező)</br> **PurchaseServicesUSETax (jelentése a** fordított fizetés hatálya alá tartozó külföldi szolgáltatások áfával kapcsolatos jelentése) |
| Kőolajjal és palackos gázzal összefüggő adó                                                                  | Adó összege          | **OilGasDuty**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| Földgázzal és városi gázzal összefüggő adó                                                             | Adó összege          | **Natural TownGasDuty**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| Széndioxid-kibocsátással összefüggő adó                                                                               | Adó összege          | **2019. év 201**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| CO2Duty                                                                                   | Adó összege          | **CO2Duty**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| Vízdíj                                                                              | Adó összege          | **Vízfeltöltés**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| Összes levonás                                                                          | Adó összege          | Az előző hat mező összege                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| Teljes adóösszeg (pozitív összeg = kifizetés, negatív összeg = visszatérítés fogadása) | Adó összege          | "Teljes kötelezettség" – "Összes levonás"                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |

**Kiegészítő információ**

| Leírás                                                                                                                                                                                                                                | Adóalap/adó összege | Keresési eredmény/összesen                             |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------|-------------------------------------------------|
| A mező - árubeszerzés. Az Európai Unióon belüli árubeszerzések áfát nem adó értéke.                                                                                                                                                   | Adóalap            | **PurchaseGoodsEU PurchaseGoodsUSETax**       |
| A mező - szolgáltatásbeszerzés. Az Európai Unióon belüli szolgáltatásbeszerzések áfát nem adó értéke.                                                                                                                                             | Adóalap            | **PurchaseServicesEU PurchaseServicesEUUseTax** |
| B mező - áruellátás - jelentés az "EU-értékesítés áfa nélkül"/DK VIES számára. Az Európai Unióon belüli áruellátás áfa nélküli értéke                                                                                                           | Adóalap            | **SalesGoodsEU**                                |
| B mező - értékesítések - nem jelentve az "EU-értékesítések áfa nélkül"/DK VIES számára. Bizonyos Közösségen belüli szállítások, például a telepítés, az összeállítás, a távolságértékesítés és a nem adóköteles személyeknek való új szállítási eszközök áfa nélküli értéke. | Adóalap            | **SalesInstallationAssemblyEtcEU**              |
| B mező - szolgáltatásellátás. Az európai uniós szolgáltatásértékesítések áfa nélküli értékét, amelynek a vevő fordított áfa fizetésére kötelezett, jelenteni kell az "EU-értékesítés áfa nélkül"/DK VIES részére.                          | Adóalap            | **SalesServicesEU**                             |
| C-rovat - egyéb kellékek Más áruk és szolgáltatások forgalmi adó nélkül, Dánia területén, más EU-tagállamnak, illetve harmadik országoknak vagy harmadik területeknek nyújtott értéke.                                     | Adóalap            | **EgyébSuppliesWithoutVAT**                     |

#### <a name="purchase-reverse-charge-vat"></a>Beszerzési fordított adó áfa

Ha úgy konfigurálja az áfakódokat, hogy a használati adó használatával feladják a bejövő fordított adók áfáját, társítsa az áfakódokat a Jelentés mezőkeresés **keresési eredményéhez**, amely a névben szerepel a "UseTax" kifejezés.

Másik lehetőségként két külön áfakódot is konfigurálhat: egyet az esedékes áfa, egyet pedig az áfa levonásához. Ezután társítsa az egyes kódokat a Jelentés mezőkeresés megfelelő keresési **eredményeihez**.

Például a **közösségen belüli adóköteles beszerzések esetén az** **UT_S_EU áfakódot hozzá kell állítani a forgalmi adóhoz, és azt társítani kell a Jelentés mező keresésének PurchaseGoodsUSETax** **keresési eredményéhez**. Ebben az esetben az **áfakódot UT_S_EU** adóösszegek megjelennek az "Áruk áfával stb. Vásárolt külföldi termékek" és "Bemeneti áfa" mezők. Az adóalapok az "A doboz - árubeszerzés" szövegben jelennek meg.

Másik lehetőségként két áfakódot is konfigurálhat:

- **VAT_S_EU**, amelynek -25 százalékos adókulcs-értéke van
- **InVAT_S_EU**, amelynek 25 százalékos adókulcs-értéke van

Ezt követően a jelentés mezőkeresési eredményeihez **a** következő módon társítja a kódokat:

- A **VAT_S_EU** társítása **a PurchaseGoodsEU** keresési eredményhez.
- A **InVAT_S_EU** társítása **a InputVAT** keresési eredményéhez.

Ebben az esetben az áfakódot **VAT_S_EU** az "Áruk áfára stb. is tükrözik. Beszerzett külföldi áru" rovat és "A doboz - árubeszerzés" Az áfakódot InVAT_S_EU **az** "Bemeneti áfa" mezőben jelennek meg.

A fordított áfa beállításával kapcsolatos további tudnivalókat lásd: [Fordított költségek](emea-reverse-charge.md).

## <a name="configure-system-parameters"></a>Rendszerparaméterek konfigurálása

Áfabevallás létrehozásához konfigurálnia kell az áfaszámot.

1. Nyissa meg a következőt: **Szervezetek adminisztrációja** > **Szervezetek** > **Jogi személyek**.
2. Válassza ki a jogi személyt, majd válassza ki a Regisztrációkhoz **való jogokat**.
3. Válassza ki vagy hozza létre a címet Dániában, **majd** válassza a Gyorstára regisztrációs azonosító **gyorsét**.
4. A Regisztráció **típusa mezőben** válassza ki azt a regisztrációtípust, amely a Dániában van elkönyvelve, **és** amely az áfaazonosító-regisztrációs kategóriát használja.
5. A Regisztrációs **szám mezőbe** írja be az adószámot.
6. Az Általános **lap** Hatályos **mezőjébe** írja be azt a dátumot, amikor a szám hatályba lép.

A regisztrációs kategóriák és a regisztrációtípusok beállításának további tudnivalókat lásd [: Regisztráció-forgalmi adatok](emea-registration-ids.md).

## <a name="set-up-a-vat-declaration-preview-for-denmark"></a>Áfabevallás előnézetének beállítása Dániában

### <a name="import-er-configurations"></a>ER-konfigurációk importálása

Az Elektronikus jelentés **munkaterület megnyitása** és az **áfabevallási Excel (DK) ER-formátum importálása**.

További információért lásd: [ER-konfigurációk letöltése a Konfigurációs szolgáltatás globális tárolójából](../../fin-ops-core/dev-itpro/analytics/er-download-configurations-global-repo.md).

### <a name="set-up-application-specific-parameters-for-vat-declaration-fields"></a><a name="set-up-application-specific-parameters"></a> Alkalmazásspecifikus paraméterek beállítása az áfabevallási mezőkhöz

> [!NOTE]
> Javasoljuk, hogy engedélyezze az **Alkalmazásspecifikus paraméterek használata az elektronikus jelentéskészítési formátumok előző verzióiból** funkciót a **Szolgáltatáskezelés** munkaterületen. Ha ez a funkció engedélyezve van, akkor az ER-formátum korábbi verziójához beállított paraméterek automatikusan alkalmazhatók ugyanannak a formátumnak a későbbi verzióira is. Ha ez a funkció nincs engedélyezve, akkor explicit módon konfigurálnia kell az alkalmazásspecifikus paramétereket az egyes formátumverziókhoz. Az **Alkalmazásspecifikus paraméterek használata az elektronikus jelentéskészítési formátumok előző verzióiból** funkció a **Szolgáltatáskezelés** munkaterületen a Finance 10.0.23 verziójától érhető el. Az egyes jogi személyek ER-formátumának paramétereinek beállítását lásd: [Az ER-formátum paramétereinek beállítása jogi személyenként](../../fin-ops-core/dev-itpro/analytics/er-app-specific-parameters-set-up.md).

Áfabevallás automatikus létrehozásához társítsa az áfakódokat az alkalmazásban, és keresse meg az eredményeket az ER konfigurációban.

A következő lépések szerint adhatja meg, hogy mely áfakódok generálják az áfabevallás mezőit.

1. Menjen a Munkaterületek **elektronikus** > **jelentési szolgáltatásba**, és válassza ki a Jelentéskészítési **konfigurációkat**.
2. Válassza ki az áfabevallás **Excel-konfigurációját**, majd **a Konfigurációk \> alkalmazásspecifikus paramétereinek beállításait**.
3. Az Alkalmazásspecifikus **paraméterek lapon**, **a** Keresések gyorslapon válassza a Jelentés **mező keresését**.
4. A Feltételek **gyorscsoporton** állítsa be a következő mezőket az áfakódok és a jelentésmezők társítása érdekében.

    | Mező                  | Leírás                                                                                                                                                                                                                                                                                                          |
    |------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | Keresési eredmény          | A jelentésmező értékének kiválasztása. Az értékekről és az [áfabevallási sorokhoz való hozzárendelésükről a cikk korábbi, áfabevallási áttekintő](#vat-declaration-overview) szakaszában olvashat bővebben.                                                                                               |
    | Adókód               | A jelentésmezőhöz társítani kívánt áfakód kiválasztása. A kiválasztott áfakódot használják a feladott adótranzakciók a megfelelő bevallás mezőben lesznek összegyűjtve. Javasoljuk, hogy az áfakódokat úgy válassza el, hogy egy áfakód csak egy bevallásmezőben generáljon összegeket. |
    | Tranzakcióosztályozó | Ha a bevallás meghatározásához elegendő áfakódot hozott létre, válassza **\* a Nem üres lehetőséget\***. Ha nem létrehozott elég áfakódot ahhoz, hogy egy áfakód csak egy bevallásmezőben generáljon összegeket, akkor be lehet állítani egy tranzakcióosztályozót. A következő tranzakcióosztályozók érhetők el:</br>-   **Beszerzés**</br>-   **PurchaseExempt** (adómentes beszerzés)</br>-   **PurchaseReverseCharge** (beszerzés fordított áfafizetésből visszakövethető adója)</br>-   **Értékesítés**</br>-   **SalesExempt** (adómentes értékesítés)</br>-   **SalesReverseCharge** (a beszerzés fordított vagy fordított áfafizetésből fizetendő adója)</br>-   **Az adó használata.** </br>Minden tranzakcióosztályozónál elérhető a jóváírás osztályozója is. Például az egyik osztályozó a **PurchaseCreditNote** (beszerzési jóváírás).</br>Mindenképpen hozzon létre két sort mindegyik áfakódhoz: egyet a tranzakcióosztályozó értékével, és egyet a jóváírási érték tranzakcióosztályozóval. |


    > [!NOTE]
    > Minden áfakód társítása a keresési eredményekhez. Ha az áfakódok nem generálnak értékeket az áfabevalláson, társítsa őket az **Egyéb** keresés eredményhez.

    ![Alkalmazásspecifikus paraméterek oldal.](media/7db74920fad66a0db7fad60758698cc0.png)


5. Az Állam **mezőben** módosítsa az értéket " **Befejezve" értékre**.

### <a name="set-up-the-vat-reporting-format-for-preview-amounts-in-excel"></a>Áfabevallási formátum beállítása az összegek excelben való megtekintéséhez

1. A Funkciókezelés **munkaterületen** keresse meg és válassza ki az áfabevallék-formátum **jelentéseit.** Funkció a listában, majd válassza az Engedélyezés **lehetőséget**.
2. Ugrás a Főkönyv **beállítása** > **főkönyvi** > **paraméterekhez**.
3. Az Áfanyilatkozat-formátum **·** **·** **·** **hozzárendelése mező Áfabeállítások gyorslapján válassza ki az áfabevallási Excel (DK)** ER formátumot.

   Ez a formátum a kiegyenlítési időszak áfajelentésének **futtatásakor kerül nyomtatásra**. Akkor is kinyomtatja, ha **az** Áfakifizetések **lapon** a Nyomtatás lehetőséget választja.

4. Az Adóhatóság **lapon** válassza ki az adóhatóságot, majd a **Jelentés elrendezése** mezőben válassza az Alapértelmezett **beállítást**.

Ha az áfabevallást [több](emea-reporting-for-multiple-vat-registrations.md) áfaregisztrációval rendelkező jogi személynél konfigurálja, kövesse az alábbi lépéseket.

1. Ugrás a Főkönyv **beállítása** \> **főkönyvi** \> **paraméterekhez.**
2. Az Áfa **lap** **Országok/** **régiók gyorslapján, a DNK** **sorában válassza az Áfabevallási Excel (DK)** ER formátumot.

## <a name="set-up-electronic-messages"></a>Elektronikus üzenetek beállítása

### <a name="download-and-import-the-data-package-that-has-example-settings-for-electronic-messages"></a>Az elektronikus üzenetekhez példaként megadott adatcsomag letöltése és importálása

Az adatcsomag olyan elektronikus üzenet-beállításokat tartalmaz, amelyek az áfabevallás Excel programban való előnézetének megtekintésére használhatók. Ezek a beállítások bővíthetők, de létrehozható egy saját beállítás is. Az elektronikus üzenetkezelés alkalmazásával és a saját beállítások beállításával kapcsolatos további tudnivalókat lásd: [Elektronikus üzenetkezelés](../general-ledger/electronic-messaging.md).

1. A [Microsoft Dynamics Lifecycle Services (LCS)](https://lcs.dynamics.com/v2)**megosztott** eszköztárában válassza ki eszköztípusként az Adatcsomagot, **majd töltse le a DK-áfabevallási csomagot.** A letöltött fájl neve DK áfabevallási **csomag.zip**.
2. Válassza az Importálás lehetőséget **a Pénzügy eszköz Adatkezelés** **munkaterületén**.
3. Az Importálás **gyorscsoport** Csoportnév **mezőjébe** írja be a feladat nevét.
4. A **Kiválasztott entitások** gyorslapon válassza a **Fájl hozzáadása** elemet.
5. A Fájl **hozzáadása párbeszédpanelen győződjön meg róla,** **·** **·** **hogy a Forrásadatok formátuma mező csomag, válassza a Feltöltés és hozzáadás lehetőséget, majd válassza ki a korábban letöltött zip-fájlt.**
6. Válassza **Bezárás** lehetőséget.
7. Az adatentitások feltöltése után a műveleti ablaktáblán válassza az **Importálás** elemet.
8. Ugrás az **Adókeresések** > **és jelentések** > **·** > **elektronikus** üzenetekhez és az Importált elektronikus üzenetek feldolgozásának ellenőrzéséről (**DK-áfabevallás**).

### <a name="configure-electronic-messages"></a>Elektronikus üzenetek konfigurálása

1. Ugrás az **Adóbeállítás** > **–** > **Elektronikus üzenetek –** > **Rekordok feltöltése műveletekhez**
2. Válassza ki a DK Áfa-visszacsatlott **rekordok feltöltése sorát**, majd válassza a **Lekérdezés szerkesztése lehetőséget**.
3. A szűrő használatával megadhatja a jelentésben szerepeletni kívánt kiegyenlítési időszakokat.
4. Ha más bevallásban kell jelentenie más kiegyenlítési időszakok adótranzakcióit, hozzon létre egy új Rekord feltöltése műveletet, és válassza ki a **megfelelő** kiegyenlítési időszakokat.

## <a name="preview-the-vat-declaration-in-excel"></a>Áfabevallás előnézete az Excel programban

### <a name="preview-the-vat-declaration-in-excel-from-the-report-sales-tax-for-settlement-period-periodic-task"></a><a name="preview-vat-excel"></a> Áfabevallás előnézete az Excel programban a forgalmi adó jelentésből a kiegyenlítési időszak ismétlődő feladatának megtekintéséhez

1. Ugrás az Adó – **Időszakos** > **feladatok** > **– Bevallás** > **– Áfajelentés** > **- áfa a kiegyenlítési időszakra**
2. A Kiegyenlítési **időszak mezőben** válasszon ki egy értéket.
3. Az Áfafizetés **verziószáma** mezőben válasszon a következő értékek közül:

    - **Eredeti**: Jelentés készítése az eredeti áfafizetés vagy az áfafizetés generálása előtti áfatranzakciókról.
    - **Korrekciók**: Jelentés készítése az adott időszakra vonatkozó összes ezt követő áfakifizetés áfatranzakcióiról.
    - **Összlista**: Jelentés készítése az adott időszak összes áfatranzakcióiról, az eredeti és az összes javítással együtt.

4. A Kezdő **dátum mezőben** válassza ki a jelentési időszak kezdő dátumát.
5. Válassza az **OK** gombra, és tekintse át az Excel-jelentést.

### <a name="settle-and-post-sales-tax"></a>Áfa kiegyenlítése és feladása

1. Ugrás az Adó – **Időszakos feladatokhoz** > **– Áfabevallások** > **áfafizetése** > **és áfa feladása** > **·**
2. A Kiegyenlítési **időszak mezőben** válasszon ki egy értéket.
3. Az Áfafizetés **verziószáma** mezőben válasszon a következő értékek közül:

    - **Eredeti**: a kiegyenlítési időszak eredeti áfafizetésének létrehozása.
    - **Legutóbbi korrekciók**: Helyesbítő áfakifizetés generálása a kifizetési időszak eredeti áfafizetésének létrehozása után.

4. A Kezdő **dátum mezőben** válassza ki a jelentési időszak kezdő dátumát.
5. Válassza ki az **OK** lehetőséget.

### <a name="preview-the-vat-declaration-in-excel-from-a-sales-tax-payment"></a>Áfabevallás előnézete az Excel programban egy áfafizetésből

1. Menjen az Adó **-** > **és jelentésjelentések** > **az Áfakifizetések** > **lekérdezéshez**, és válasszon egy áfafizetési sort.
2. Válassza a **Jelentés nyomtatása**, majd az **OK gombra való lehetőséget**.
3. Ellenőrizze a kiválasztott áfafizetési sorhoz létrehozott Excel-fájlt.

> [!NOTE]
> A jelentés csak az áfafizetés kiválasztott sorában jön létre. Ha például javító nyilatkozatot kell létrehoznia, amely az időszak összes korrekcióját tartalmazza, vagy egy olyan pótnyilatkozatot, amely az eredeti adatokat és az összes javítást tartalmazza, **a** Jelentés – áfajelentés a kiegyenlítési időszak ismétlődő feladatára.

## <a name="generate-a-vat-declaration-from-electronic-messages"></a>Áfabevallás létrehozása elektronikus üzenetekből

Amikor elektronikus üzenetekkel generálja a jelentést, adóadatokat gyűjthet több jogi személytől. A további tudnivalókat [lásd a](#run-vat-declaration) cikk több jogi személyhez című szakaszának Áfabevallás futtatása című részében.

A következő eljárás az LCS megosztott eszköztárából korábban importált elektronikus üzenetek feldolgozási példáját alkalmazza.

1. Ugrás az Adó-lekérdezések **\> és jelentések \> elektronikus üzenetekhez \>**
2. Válassza ki a bal oldali ablakban a **DK-áfabevallást**.
3. Az Üzenetek **gyorspanelen** válassza az Új **lehetőséget**, majd **a Futtatás feldolgozása párbeszédpanelen** válassza az **OK gombra.**
4. Válassza ki a létrehozott üzenetsort, adjon meg leírást, majd adja meg a nyilatkozat kezdő és záró dátumát.

   > [!NOTE]
   > Az 5–7. lépés nem kötelező.

5. Nem kötelező: Az Üzenetek gyors **oldalon** válassza az **Adatok** gyűjtése gombra, majd válassza az **OK gombra.** A program hozzáadja a korábban létrehozott áfafizetéseket az üzenethez. A további tudnivalókat lásd [a](#settle-and-post-sales-tax) cikk korábbi, Az áfafizetés és áfa feladás szakaszában. Ha kihagyja ezt a lépést, akkor is létrehozhat áfabevallást **a** **Bevallás** párbeszédpanel Adóbevallás verziómezője segítségével.
6. Nem kötelező: Az Üzenet –**cikkek** gyors oldalon ellenőrizze a feldolgozásra átvitt áfafizetéseket. Alapértelmezés szerint a kijelölt időszak minden olyan áfafizetése szerepel, amely nem szerepelt ugyanannak a feldolgozásnak más üzenetében.
7. Választható: Válassza az **eredeti dokumentumot** az áfakifizetések ellenőrzéshez, **vagy válassza a Törlés** lehetőséget, ha ki szeretné zárni az áfafizetéseket a feldolgozásból. Ha kihagyja ezt a lépést, akkor is létrehozhat áfabevallást **a** **Bevallás** párbeszédpanel Adóbevallás verziómezője segítségével.
8. Az Üzenetek **gyorsjelentésen** válassza a Frissítés **állapot beállítását**. A Frissítés állapota párbeszédpanelen **válassza a** **Generálra kész lehetőséget, majd kattintson az** OK gombra **.** Győződjön meg róla, hogy az üzenet állapota Kész **állapotra változott.**
9. Válassza a **Jelentés létrehozása lehetőséget**. Az áfabevallási összegek előzetes megtekintéséhez **válassza** **az** Előnézet jelentés lehetőséget a Futtatás párbeszédpanelen, majd **kattintson az OK gombra.**
10. Az Elektronikus **jelentés**[paraméterei párbeszédpanelen állítsa be a mezőket az Ebben a cikk korábbi részében, az Áfabevallás előnézete excelben](#preview-vat-excel) funkcióban leírtak szerint, **majd válassza az OK gombra**.
11. Válassza a **lap** jobb felső sarkában a Mellékletek gombot (papír clip-szimbólum), **majd** a Megnyitás gombra kattintva nyissa meg a fájlt. Tekintse át az összegeket az Excel-dokumentumban.

## <a name="run-a-vat-declaration-for-multiple-legal-entities"></a><a name="run-vat-declaration"></a> Áfabevallás futtatása több jogi személyhez

Ha a formátumokat használni kívánt egy jogi személycsoport áfabevallásának jelentéséhez, először be kell állítania az összes kötelező jogi személy áfakódja ER-formátumára vonatkozó alkalmazásspecifikus paramétereit.

### <a name="set-up-electronic-messages-to-collect-tax-data-from-several-legal-entities"></a>Elektronikus üzenetek beállítása különböző jogi személyektől származó adóadatok összegyűjtésére

A következő lépések szerint beállíthatja az elektronikus üzeneteket több jogi személytől származó adatok gyűjtésére.

1. Ugrás a **Munkaterületek** > **funkciókezelésre**
2. Keresse meg és válassza **ki** a listában a Több vállalatot átfedő lekérdezéseket a rekordműveletek feltöltése funkcióhoz, majd válassza az **Engedélyezés lehetőséget**.
3. Ugrás az **Adóbeállítás** > **–** > **Elektronikus üzenetek –** > **Rekordok feltöltése műveletekhez**
4. A Rekordok **feltöltése műveletlapon** válassza ki **az Áfa-feltöltési rekordok sorát**.

   Az Adatforrások **beállítási rácsában** elérhető egy új **Vállalat** mező. Meglévő rekordok esetén ez a mező az aktuális jogi személy azonosítóját mutatja.

5. A DataSources **beállítási rácsában** adjon hozzá egy sort minden további jogi személyhez, amely részt fog venni a jelentésen. Minden új sornál állítsa be a következő mezőket.

    | Mező                  | Leírás                                                                                                                   |
    |------------------------|-------------------------------------------------------------------------------------------------------------------------------|
    | Név                   | Adjon meg egy értéket, amely alapján jobban megértheti, hogy honnan származik ez a rekord. Megadhatja például az **1. leányvállalat áfafizetését**. |
    | Üzenetelem típusa      | Áfa-visszaáru **kiválasztása**. Ez az érték az egyetlen olyan érték, amely minden rekord számára elérhető.                                    |
    | Számla típusa           | Az összes **kijelölése**.                                                                                                               |
    | Fő tábla neve      | TaxReportVoucher **megadása** minden rekordhoz.                                                                             |
    | Dokumentumszám mező  | Bizonylat **megadása** minden rekordhoz.                                                                                      |
    | Dokumentumdátum mező    | A **TransDate megadása** minden rekordhoz.                                                                                    |
    | Dokumentumszámla mező | TaxPeriod **megadása** minden rekordhoz.                                                                                    |
    | Vállalat                | Válassza ki a jogi személy azonosítóját.                                                                                            |
    | Felhasználó lekérdezése             | A lekérdezés szerkesztése lehetőség kiválasztásával automatikusan be van jelölve ez **a jelölőnégyzet**.                                 |

6. Minden új sornál válassza **a Lekérdezés** szerkesztése lehetőséget, és adjon meg egy kapcsolódó kiegyenlítési időszakot a **sor** Vállalat mezőjében megadott jogi személyhez.

Ha a beállítás befejeződött, **·** **az** Elektronikus üzenetek lapon található Adatgyűjtés funkció a megadott jogi személyektől gyűjt áfafizetéseket.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
