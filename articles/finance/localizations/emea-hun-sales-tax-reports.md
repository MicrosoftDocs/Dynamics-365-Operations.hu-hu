---
title: Áfajelentések Magyarországról
description: Ez a témakör az áfabevallásra vonatkozó információkkal és a tételes áfakimutatás-jelentésekkel kapcsolatos információkat tartalmazza
author: anasyash
ms.date: 11/19/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 12641
ms.search.region: Hungary
ms.author: roschlom
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 5ffe6ee54e7503b58046c9123878247147a10407
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5815009"
---
# <a name="sales-tax-reports-for-hungary"></a>Áfajelentések Magyarországról

[!include [banner](../includes/banner.md)]

Ez a témakör az **áfabevallásra vonatkozó információkkal** és a **tételes áfakimutatás-jelentésekkel** kapcsolatos információkat tartalmazza. Ezeket a Microsoft Excel jelentéseket létrehozhatja, és ezekkel létrehozhatja az adóhatóságnak benyújtandó hozzáadottérték-adó (ÁFA) bevallásait.

- **Áfabevallásra vonatkozó információk** – Ez a jelentés az áfairány (áfakövetelés, fizetendő áfa vagy használati adó) és áfakód szerint csoportosított számlák listáját tartalmazza. Az egyes áfairányok és áfakódok esetében a jelentés tartalmazza a teljes áfaösszeget és a teljes bruttó számlaösszeget is.
- **Tételes áfabevallás** – Ez a jelentés tartalmazza a számlák teljes számát, az ellenoldali felek (partnerek) teljes számát, a teljes áfaalapot és az alábbi táblázatban szereplő egyes cikkek teljes áfaösszegét.

  | **Cikkszám** | **A benne foglalt tranzakciók**            |
  |-----------------|-----------------------------------------------|
  | 01              | Értékesítési számlák                                |
  | 02              | Jóváírás értékesítési rendelései                      |
  | 04              | Beszerzési számlák                            |
  | 05              | Jóváírás értékesítési rendelései                   |
  | 06              | Beszerzési számlák, amelyek nem haladják meg a korlátot |

Ez a jelentés az egyes partnerekre vonatkozóan is tartalmazza ugyanazokat az információkat, valamint az egyes cikkek számláinak listáját.

## <a name="setup"></a>Beállítás

1. A [Microsoft Dynamics Lifecycle Services (LCS)](https://lcs.dynamics.com/V2) szolgáltatásban, a Közös eszközök könyvtárából töltse le a legfrissebb verzióit a következő Elektronikus jelentéskészítési (ER) konfigurációkat a jelentésformátumhoz:

   * **Áfabevallás adatai Tételes Excel formátum (HU)**
   * **Forgalmi adó bevallás információ, jelentésformátum (HU)**

    További tudnivalókért lásd: [Az elektronikus jelentési beállítások letöltése a Lifecycle Services rendszerből](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).

2. Menjen a **Főkönyv** \> **Főkönyv beállítás** \> **Főkönyv paraméterei** pontra.
3. Az **Áfa** fül **Áfakimutatás** gyorslapján állítsa a **Tételes áfakimutatás nyomtatásának engedélyezése** beállítást **Igen** értékre az **Áfabevallás adatai tételes Excel formátum (HU) ER-formátum használatához és a Tételes áfakimutatás jelentés létrehozása** használatához.

   Másik lehetőségként állítsa a **Nem** értékre az **Áfabevallás információ, jelentésformátum (HU) ER-formátumának használatához, és az Áfabevallással kapcsolatos információ létrehozásának** jelentéséhez.

4. Ha a **Tételes áfakimutatás nyomtatása lehetőséget Igen** értékre állítja, a **Tételes áfakimutatás-korlát (HUF)** mezőben adja meg az összegkorlátot magyar forintban (HUF). Ez a mező határozza meg, hogy mely számlatranzakciók szerepeljenek a **Tételes áfakimutatás** jelentésben. Minden olyan számla, amelynek áfaösszege meghaladja ennek a mezőnek az értékét, szerepelni fog.

## <a name="generate-and-export-the-sales-tax-declaration-information-report-or-itemized-vat-statement-report"></a>Az áfabevallás-információs jelentés vagy a Tételes áfakimutatás jelentés létrehozása és exportálása

### <a name="generate-and-print-vat-reporting"></a><a name= "generateandprintvatreporting"></a>Áfajelentés létrehozása és nyomtatása

1. Nyissa meg **Adó** \> **Időszakos feladatok** \> **Áfajelentés** lehetőséget.
2. Az **Áfajelentés** lap felső részén állítsa be a **Dátum** és **Kiegyenlítési időszak** mezőket. A rács az áfajelentéshez rendelkezésre álló kiegyenlítési időszakokat jeleníti meg.

    ![Áfabevallási oldal](media/HU-sales-tax-reports-1.png)

3. Válassza ki a kívánt kiegyenlítési időszak sorát, majd válassza a **Jelentés létrehozása** lehetőséget.
4. Az **Áfabevallásra vonatkozó információk** párbeszédpanelen a következő mezőket állítsa be.

    | **Mező**      | **Leírás**                                                                                                                                                                                                                              |
    |----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | Jóváhagyás       | Az áfajelentés jóváhagyásához állítsa ezt a beállítást **Igen** értékre.              |
    | Importadóval   | Állítsa ezt a beállítást **Igen** értékre, hogy az áfatranzakciók szerepeljenek a kiegyenlítési jelentésen.                                                                                                                                                                              |
    | Fájl létrehozása     | Állítsa ezt a beállítást **Igen** értékre ahhoz, hogy létrehozzon egy exportfájlt a **Tételes áfakimutatás-jelentéshez**.                                                                                                                                                                       |
    | Futtatási mód | Válassza ki azt a pénznemet, amelyben az összegek megjelennek a jelentésben: </br>- **Összegek a vállalat pénznemében a könyveléshez**: A könyvelési pénznemben lévő értékek megjelenítése. </br>- **Összegek a vállalat pénznemében az áfajelentéshez**: Az áfakód pénznemében lévő értékek megjelenítése. </br>- **Összegek eredeti pénznemben**: A tranzakció pénznemében lévő értékek megjelenítése.                                                                                                                                                                                                       |

5. Válassza ki az **OK** lehetőséget. A lap alsó részén lévő rácsban létrejön egy sor, amely az áfajelentési adatokat tartalmaz. Ezenkívül létrejön egy zip-archívum, amely tartalmazza a jelentést.
6. Tekintse át a létrehozott sorban lévő adatokat.

    | **Mező**      | **Leírás**                                                                                                                                                                                                                              |
    |----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | Engedélyezve       | A bejelölt jelölőnégyzet azt jelzi, hogy az áfajelentés el lett fogadva. Ennek a jelölőnégyzetnek a beállítása az **Áfabevallással kapcsolatos adatok** párbeszédpanel **Jóváhagyás** mezőjéből kerül át.                                             |
    | Időszak kezdete   | A jelentési időszak kezdő dátuma.                                                                                                                                                                                                      |
    | Időszak vége     | A jelentési időszak záró dátuma.                                                                                                                                                                                                        |
    | Jelentés dátuma | A jelentés létrehozásának dátuma.                                                                                                                                                                                                       |
    | Importadó        | A bejelölt jelölőnégyzet azt jelzi, hogy a feldolgozás során belefoglalták az áfatranzakciókat. Ennek a jelölőnégyzetnek a beállítása az **Áfabevallással kapcsolatos adatok** párbeszédpanel **Importadó belefoglalása** mezőjéből kerül át. |

### <a name="reprint-a-generated-report"></a>Létrehozott jelentés újranyomtatása

1. Az **Áfa-jelentés** lapon válassza a **Jelentés** nyomtatása lehetőséget a létrehozott áfajelentés nyomtatásához.
2. Az **Áfabevallással kapcsolatos adatok** párbeszédpanelen állítsa be a **Jóváhagyás**, a **Külkereskedelem belefoglalása**, a **Fájl létrehozása**, és a **Futtatási mód** mezőket az előző szakaszban leírtak szerint.
3. Válassza ki az **OK** lehetőséget. Tekintse át a létrehozott zip-archívumot, amely tartalmazza a jelentést.

### <a name="re-create-the-report-for-a-period"></a>A jelentés újbóli létrehozása egy időszakra

1. Az **Áfa-jelentés** lapon válassza az **Időszak megszakítása** lehetőséget, ha törölni szeretné a **Jóváhagyás** jelölőnégyzetet az előző jelentésből.
2. Válassza az **Időszak törlése** lehetőséget a lap alsó részén lévő, korábban létrehozott sor törléséhez.
3. Válassza a **Jelentés létrehozása** lehetőséget, és az [Áfajelentés készítése és nyomtatása](#generateandprintvatreporting) szakasz utasításait követve hozzon létre egy új sort az **Áfajelentés** lap alsó részén.

## <a name="example"></a>Példa

Ez a példa a **DEMF** jogi személyben elvégezhető.

### <a name="setup"></a>Beállítás

1. Nyissa meg az **Adó** \> **Közvetett adók** \> **Áfa** \> **Áfakódok** lehetőséget, és állítsa be a következő három áfakódot.

    | **Áfakód** | **Százalék** | **Leírás**                                                                       |
    |--------------------|----------------|---------------------------------------------------------------------------------------|
    | VAT27              | 27             | A belföldi értékesítés 27 százaléka.                                               |
    | InVAT27            | 27             | A belföldi vásárlások 27 százaléka.                                           |
    | EU18               | 18             | Unión belüli vásárlás 18 százaléka, ahol az **Importadó** lehetőség **Igen** értékre van állítva. |

2.  Menjen az **Adó** \> **Beállítás** \> **Áfa** \> **Adómentességi szám** lehetőségre, és válassza az **Új** lehetőséget a következő két sor létrehozásához.

    | **Ország/régió** | **Adómentességi szám** |
    |--------------------|-----------------------|
    | HUN                | HU11651273            |
    | HUN                | HU34532985            |

### <a name="create-and-post-customer-transactions"></a>Vevőtranzakciók létrehozása és feladása

1. Menjen a **Kinnlevőségek** \> **Vevők** \> **Minden vevő** lehetőségre, és válassza ki a **DE-010** vevőt.
2. A **Cím** gyorslapon állítsa be a **HUN** értéket országként, majd a **Számla és szállítás** gyorslapon állítsa az **Adómentességi szám** mezőt **HU11651273** értékre.
3. Válassza a **Mentés** lehetőséget.
4. Menjen a **Kinnlevőségek** \> **Rendelésel** \> **Minden értékesítési rendelés** lehetőségre, majd hozza létre a következő rendelést, és egy számlát.

    | **Dátum**        | **Vevő** | **Nettó összeg** | **Áfaösszeg** | **Áfakód** |
    |-----------------|--------------|----------------|----------------|--------------------|
    | 2020. január 1. | DE - 010       | 800.00         | 216.00         | VAT27              |

5. Javítási jóváírás létrehozása a rendeléshez. Jelölje ki a létrehozott rendelést, majd válassza az **Eladás \> Létrehozás \> Jóváírás** lehetőséget. A következő két új sor kerül hozzáadásra.

    | **Dátum**        | **Vevő** | **Nettó összeg** | **Áfaösszeg** | **Áfakód** |
    |-----------------|--------------|----------------|----------------|--------------------|
    | 2020. január 2. | DE - 010       | \-800,00.       | \-216,00.       | VAT27              |
    | 2020. január 2. | DE - 010       | 800.00         | 216.00         | VAT27              |

6. Módosítsa a második sorban szereplő összeget az alábbi táblázatban látható módon.

    | **Dátum**        | **Vevő** | **Nettó összeg** | **Áfaösszeg** | **Áfakód** |
    |-----------------|--------------|----------------|----------------|--------------------|
    | 2020. január 2. | DE - 010       | \-800,00.       | \-216,00.       | VAT27              |
    | 2020. január 2. | DE - 010       | **1,000.00**   | **270.00**     | VAT27              |

   > [!NOTE] 
   > Ha manuálisan hoz létre jóváírást az **Eladás \> Létrehozás \> Jóváírás** létrehozása lehetőség kiválasztása helyett (például negatív összegű szabadszöveges számlát hoz létre), a jóváírás megjelenik a 01-es cikkben (eladási számlák), és negatív összeggel rendelkezik.

### <a name="create-and-post-vendor-transactions"></a>Szállítótranzakciók létrehozása és feladása

1. Menjen a **Kötelezettségek** \> **Szállítók** \> **Minden szállító** lehetőséget, és válassza ki a **DE-001** szállítót.
2. A **Cím** gyorslapon állítsa be a **HUN** értéket országként, majd a **Számla és szállítás** gyorslapon állítsa az **Adómentességi szám** mezőt **HU34532985** értékre.
3. Válassza a **Mentés** gombot, és zárja be az oldalt.
4. **DE-01001** szállító kiválasztása.
5. A **Cím** gyorslapon ellenőrizze, hogy a **DEU** érték van-e beállítva országként, majd a **Számla és szállítás** gyorslapon állítsa az **Adómentességi szám** mezőt **DE192873939** értékre.

6. Nyissa meg a **Kötelezettségek \> Számlák \> Számlanapló** lehetőséget, hozza létre a következő két számlát, majd könyvelje őket.

    | **Dátum**        | **Szállító** | **Nettó összeg** | **Áfaösszeg** | **Áfakód** |
    |-----------------|------------|----------------|----------------|--------------------|
    | 2020. január 1. | DE - 001     | 1,500          | 405            | InVAT27            |
    | 2020. január 1. | DE - 01001   | 1,100          | 198            | EU18               |

   > [!NOTE] 
   > Ha manuálisan hoz létre jóváírást az **Beszerzés \> Létrehozás \> Jóváírás** létrehozása lehetőség kiválasztása helyett (például negatív összegű szállítói számlát hoz létre), a jóváírás megjelenik a 04-es cikkben (beszerzési számlák), és negatív összeggel rendelkezik.

### <a name="generate-and-print-the-sales-tax-declaration-information-report"></a>Az áfabevallás adatai jelentés létrehozása és nyomtatása

1. Menjen a **Főkönyv** \> **Főkönyv beállítás** \> **Főkönyv paraméterei** pontra.
2. Az **Áfa** fül **Áfakimutatás** gyorslapján győződjön meg arról, hogy a **Tételes áfakimutatás nyomtatásának engedélyezése** beállítás **Nem** értékre van állítva.
3. Nyissa meg az **Adó \> Időszakos feladatok \> Áfajelentés lehetőséget.**
4. Válassza a következő sort.

    | **Kifizetési időszak** | **Kezdő dátum** | **Záró dátum** |
    |-----------------------|---------------|-------------|
    | Hé                   | 2020.01.01.      | 2020.01.31   |

5. Válassza a **Jelentés létrehozása** lehetőséget.
6. Az **Áfabevallással kapcsolatos információ** párbeszédpanelen állítsa az **Importadó belefoglalása** beállítást **Igen** értékre.
7. Kattintson az **OK** gombra, és tekintse át a [létrehozott jelentést](https://mbs.microsoft.com/files/customer/AX/Downloads/Taxupdates/SalesTaxDeclarationInformation.xlsx).

### <a name="generate-and-print-the-itemized-vat-statement-report"></a>Tételes áfabevallási jelentés létrehozása és nyomtatása

1. Menjen a **Főkönyv** \> **Főkönyv beállítás** \> **Főkönyv paraméterei** pontra.
2. Az **Áfa** fül **Áfakimutatás** gyorslapján állítsa be a **Tételes áfakimutatás nyomtatásának engedélyezése** beállítás **Igen** lehetőséget.
3. Válassza a **Mentés** lehetőséget.
4. Nyissa meg az **Adó \> Időszakos feladatok \> Áfajelentés lehetőséget.**
5. Válassza a következő sort.

    | **Kifizetési időszak** | **Kezdő dátum** | **Záró dátum** |
    |-----------------------|---------------|-------------|
    | Hé                   | 2020.01.01.      | 2020.01.31   |

6. Válassza az **Időszak törlése** lehetőséget, majd a **Jelentés létrehozása** lehetőséget.
7. Az **Áfabevallással kapcsolatos információ** párbeszédpanelen állítsa az **Importadó belefoglalása** beállítást **Igen** értékre.
8. Kattintson az **OK** gombra, és tekintse át a [létrehozott jelentést](https://mbs.microsoft.com/files/customer/AX/Downloads/Taxupdates/ItemizedVATStatement.xlsx).

A **Tételes áfakimutatás** jelentés a következő adatokat tartalmazza:

- A **0065A-01-05** szakasz tartalmaz egy táblázatot, amely az összegeket cikkenként jeleníti meg.

    | &nbsp; |     &nbsp;          | Partnerek száma | Számlák száma | Áfaalap | VAT-összeg |
    |--------|---------------------|--------------------|--------------------|----------|------------|
    | 102.   | Összesen 00 – 01. sor | 1                  | 1                  | 800.00   | 216.00     |
    | 103.   | Összesen 00 – 02. sor | 1                  | 1                  | 200.00   | 54.00      |
    |        | 102+103 sorok       | 1                  | 2                  | 1,000.00 | 270.00     |
    | 105.   | Összesen 00 – 04. sor | 2                  | 2                  | 2,600.00 | 405.00     |
    | 106.   | Összesen 00 – 05. sor | 0                  | 0                  | 0,00     | 0,00       |
    | 107.   | Összesen 00 – 06. sor | 0                  | 0                  | 0,00     | 0,00       |
    |        | 105+106+107 sorok   | 2                  | 2                  | 2,600.00 | 405.00     |

Ebben a táblában a 102-es sor tartalmazza az értékesítési rendelést, a 103-as sor az értékesítési rendelés jóváírását, a 105-ös sor pedig két szállítói számlát.
A többi szakasz az egyes partnerekre vonatkozóan is tartalmazza ugyanazokat az információkat, valamint az egyes cikkek számláinak listáját.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]