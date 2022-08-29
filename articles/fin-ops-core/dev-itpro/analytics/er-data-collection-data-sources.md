---
title: Adatgyűjtési adatforrások használata elektronikus jelentési formátumokban
description: Ez a cikk bemutatja, hogy hogyan használhatók az ADATGYŰJTÉSi adatforrások az Elektronikus jelentés (ER) formátumokban.
author: kfend
ms.date: 08/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2021-01-01
ms.dyn365.ops.version: AX 10.0.16
ms.custom: 58771
ms.assetid: ''
ms.search.form: EROperationDesigner
ms.openlocfilehash: 221cefc1880cdd88a952140424daf24975a575aa
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9286179"
---
# <a name="use-data-collection-data-sources-in-electronic-reporting-formats"></a>Adatgyűjtési adatforrások használata elektronikus jelentési formátumokban

[!include [banner](../includes/banner.md)]

Az Elektronikus jelentéskészítési [(ER)](general-electronic-reporting.md) keretrendszer Művelettervezője segítségével konfigurálhatja egy ER-megoldás formátumösszetevőjét, amely a kimenő dokumentumok különböző formátumokban történő előállítására használható. A konfigurált formátumkomponens hierarchikus szerkezete különböző típusú formátumelemekből áll. Ezek a formátumelemek a létrejövő dokumentumok kitöltéséhez használhatók a szükséges információval, futásidőben. Alapértelmezés szerint egy ER-formátum futtatásakor a formátumelemek ugyanabban a sorrendben futnak le, ahogyan a formátumhierarchiában szerepelnek: egyenként, felülről lefelé.

Amikor az ER egy kötést tartalmazó formátumelemet futtat, a kötés képlete fut le, és a formátumelem hozzáadja az értéket a generált dokumentumhoz. A kötés például átadhatja egy adatmodell-mező értékét egy formátumelemnek. A DATA COLLECTION adatforrást úgy konfigurálhatja, hogy futásidőben összegyűjtse az adatmodell mezőinek értékeit, értékösszegzést végezzen, és egy generált dokumentumot töltsön fel az összegyűjtött értékekkel. Ha ezt a megközelítést szeretné használni, módosítsa a kezdeti kötést úgy, hogy a konfigurált DATA COLLECTION adatforrást használja az adatmodell mező értékének átadására egy formátumelemhez. Az értékek DATA COLLECTION adatforráson keresztül történő továbbításával összegyűjtheti a szükséges adatokat a további felhasználás céljából.

A DATA COLLECTION adatforrás konfigurálásakor adja meg az adatforrásban kezelendő értéktípust. Az értékek gyűjtéséhez jelenleg a következő [adattípusok](er-formula-supported-data-types-primitive.md) támogatottak:

- Logikai
- Dátum
- DateTime
- GUID
- Int64
- Egész
- Valós
- Sztring
- Idő

A DATA COLLECTION adatforrás `Collect(Value)` módszerével értéket adhat át egy adatforrásnak gyűjtésre. Ebben a módszerben a `Value` argumentum vagy egy konstans, vagy a megfelelő adattípusú adatforrásmező érvényes elérési útvonala.

A DATA COLLECTION adatforrás `Result` tulajdonságával elérheti az összegyűjtött értékek listáját. Ez a tulajdonság egy [rekordlistát](er-formula-supported-data-types-composite.md#record-list) ad vissza. A rekordlista rekordjai tartalmazzák a `Value` mezőt, amellyel elérheti az összegyűjtött értékeket.

Alapértelmezés szerint a DATA COLLECTION adatforrás csak egyedi értékeket gyűjt.

Az összes érték összegyűjtéséhez állítsa a konfigurált ADATGYŰJTÉS adatforrás **Összes érték összegyűjtése** mezőjét **Igenre**. Ha az **Összes érték összegyűjtése** mezőt **Igenre** állítja, a `Sum(Flag)` paraméterezett tulajdonság elérhetővé válik. Ezzel a tulajdonsággal megkaphatja az összes jelenleg gyűjtött érték teljes összegét. Ebben a tulajdonságban a `Flag` argumentum egy [Boolean](er-formula-supported-data-types-primitive.md#boolean) érték, amely azt jelzi, hogy a teljes értéket vissza kell-e állítani.

- A **Hamis** érték megadásakor az összegzés a korábban gyűjtött összegből folytatódik.
- Ha az **Igaz** értéket adja meg, akkor új összegzés indul.

Az összegzéshez jelenleg a következő adattípusok támogatottak:

- Int64
- Egész
- Valós

Ha többet szeretne megtudni erről a funkcióról, töltse ki az alábbi példát.

## <a name="example-configure-an-er-format-to-do-counting-and-summing-by-using-a-data-collection-data-source"></a>Példa: ER-formátum konfigurálása számoláshoz és összegzéshez DATA COLLECTION adatforrás használatával

Ez a példa azt mutatja be, hogy a Rendszergazda vagy az Elektronikus jelentéskészítési funkcionális tanácsadó szerepkörben lévő felhasználó hogyan konfigurálhat egy ER-formátumot, amely rendelkezik egy ADATGYŰJTÉS adatforrással, amelyet a futó összegek kiszámítására és az összesített értékek összegyűjtésére használnak.

Az ebben a példában alkalmazott eljárások az USMF Microsoft Dynamics vállalatnál, a 365 Pénzügyben használhatja.

### <a name="upload-and-use-the-provided-er-solution"></a>Töltse fel és használja a megadott ER megoldást

1. [Minta ER-konfigurációk importálása](er-defer-sequence-element.md#import-the-sample-er-configurations).
2. [Konfigurációszolgáltató aktiválása](er-defer-sequence-element.md#activate-a-configurations-provider).
3. [Tekintse át az importált modell leképezését.](er-defer-sequence-element.md#review-the-imported-model-mapping)
4. [Tekintse át az importált formátumot](er-defer-sequence-element.md#review-the-imported-format).
5. [Importált formátum futtatása](er-defer-sequence-element.md#run-the-imported-format).

### <a name="run-the-format-of-the-provided-er-solution"></a>A megadott ER megoldás formátumának futtatása

1. A **Formátumtervező** oldalon válassza a **Futtatás** elemet.
2. Az **Elektronikus jelentési paraméterek** párbeszédablakban válassza az **OK** lehetőséget.
3. Töltse le és ellenőrizze a webböngészőből a felkínált fájlt.

    ![Letöltött fájl, amely a kezdeti formátum végrehajtásának eredményeit tartalmazza](./media/er-data-collection-data-sources-01.png)

### <a name="modify-the-format-of-the-er-solution-to-calculate-the-running-tax-total"></a>Módosítsa az ER megoldás formátumát a futó adóösszeg kiszámításához

Ha a tranzakciók mennyisége sokkal nagyobb, mint a jelenlegi példában szereplő mennyiség, az összegzéshez szükséges idő megnövekedhet, és teljesítményproblémákat okozhat. A formátum beállításainak megváltoztatásával segíthet megelőzni ezeket a teljesítményproblémákat. Mivel hozzáfér az adóértékekhez, hogy azokat a generált jelentésbe felvegye, ezt az információt újra felhasználhatja az adóértékek összegzéséhez.

1. A **Formátum tervező** lapon a **Hozzáadás** lapon válassza a **Gyökér hozzáadása** lehetőséget.
2. Az **Adatforrás hozzáadása** párbeszédpanelen válassza a **Funkciók** \> **Adatgyűjtés** lehetőséget.
3. Az **„Adatgyűjtés” adatforrás tulajdonságai** párbeszédpanelen kövesse az alábbi lépéseket:

    1. A **Név** mezőbe írja be a **CollectedTaxValues** értéket.
    2. A **Cikktípus** mezőben válassza ki a **Valós** lehetőséget.
    3. Az **Összes érték összegyűjtése** mezőben válassza az **Igen** lehetőséget.
    4. Válassza ki az **OK** lehetőséget.

4. Válassza ki a **Jelentés\\sorok\\Rekord\\Adómérték** numerikus formátum elemet.

    > [!NOTE]
    > Jelenleg a `@.Value` kötés van beállítva ehhez az elemhez. Ezért a generált dokumentumot a `model.Data.List.Value` mezőből származó adóértékekkel kell kitölteni.

5. Válassza a **Képlet szerkesztése** elemet.
6. A **Képlettervező** oldalon kövesse az alábbi lépéseket:

    1. A **Képlet** mezőben helyettesítse a `@.Value` értéket a `CollectedTaxValues.Collect(@.Value)` értékkel.
    2. Mentse el a módosításokat, és zárja be az oldalt.

    > [!NOTE]
    > Az új kötés ugyanazokat az adóértékeket adja át a generált dokumentumnak. Ezek az értékek azonban a **CollectedTaxValues** adatforrásban is összegyűjtésre kerülnek.

7. Válassza ki a **Report\\Lines\\Record\\RunningTotal** numeric format elemet.
8. Válassza a **Képlet szerkesztése** elemet.
9. A **Képlettervező** oldalon kövesse az alábbi lépéseket:

    1. A **Képlet** mezőbe írja be a `CollectedTaxValues.Sum(false)` értéket.
    2. Mentse el a módosításokat, és zárja be az oldalt.

    > [!NOTE]
    > Az új kötés átadja a generált dokumentumnak a már megadott adóértékek teljes összegét.

    ![A formátum tervező lapon frissített kötésekkel rendelkező numerikus elemek](./media/er-data-collection-data-sources-02.png)

10. Válassza a **Mentés** parancsot, majd válassza a **Futtatás** elemet.
11. Az **Elektronikus jelentési paraméterek** párbeszédablakban válassza az **OK** lehetőséget.
12. Töltse le és ellenőrizze a webböngészőből a felkínált fájlt.

    ![Letöltött fájl, amely a módosított formátum végrehajtásának eredményeit tartalmazza](./media/er-data-collection-data-sources-03.png)

### <a name="modify-the-format-to-evaluate-the-list-of-collected-tax-values"></a>Módosítsa a formátumot a beszedett adóértékek listájának kiértékeléséhez

1. A **Formátum tervező** lapon a **Formátum** lapon válassza a **Jelentés\\Sorok\\Rekord\\RunningTotal** numerikus formátum elemet, majd kövesse az alábbi lépéseket:

    1. A **Numerikus típus** mezőben változtassa meg az értéket **Valósról** **Egész számra**.
    2. A **Numerikus formátum** mezőben változtassa meg az értéket **F2-ről** **F0-ra**.

3. Válassza a **Hozzárendelés** lapon a **Képlet szerkesztése** lehetőséget.
4. A **Képlettervező** oldalon kövesse az alábbi lépéseket:

    1. A **Képlet** mezőbe írja be a `COUNT(CollectedTaxValues.Result)` értéket.
    2. Mentse el a módosításokat, és zárja be az oldalt.

    > [!NOTE]
    > Az új kötés átadja a generált dokumentumnak a listában szereplő rekordok számát, ahol az adóértékeket gyűjtik.

5. Válassza a **Mentés** parancsot, majd válassza a **Futtatás** elemet.
6. Az **Elektronikus jelentési paraméterek** párbeszédablakban válassza az **OK** lehetőséget.
7. Töltse le és ellenőrizze a webböngészőből a felkínált fájlt.

    ![Letöltött fájl, amely egy másik módosított formátumú végrehajtás eredményeit tartalmazza](./media/er-data-collection-data-sources-04.png)

## <a name="frequently-asked-questions"></a>Gyakori kérdések

### <a name="if-i-have-to-calculate-running-totals-and-collect-data-what-is-the-difference-between-using-a-data-collection-data-source-and-using-the-built-in-data-collection-functions"></a>Ha futó összegeket kell kiszámítanom és adatokat gyűjtenem, mi a különbség a DATA COLLECTION adatforrás és a beépített DATA COLLECTION funkciók használata között?

Mind a DATA COLLECTION adatforrás, mind a beépített [DATA COLLECTION](er-functions-category-data-collection.md) funkciók használhatók adatgyűjtésre, összegzésre és számolásra a generált kimenő dokumentumnak átadott információk alapján. Amikor azonban megpróbálja eldönteni, hogy melyik technikát használja, a következő pontokat kell figyelembe vennie.

| Adatforrás | Beépített funkciók |
|-------------| ------------------ |
| Csak az értékeket gyűjtik be. | <p>A megnevezett értékeket gyűjtik. Ezért az értékek különálló csoportjaira is kiszámíthatók összegek.</p><p>Ezen kívül a csoportok listaként is kivonhatók.</p><p>Szöveges értékek is gyűjthetők.</p> |
| Az egyedi értékek automatikusan összegyűjtésre kerülnek. | Az összegyűjtött értékekből az egyedi értékek listájának kivonásához további beállításokra van szükség. |
| A teljesítmény az összegyűjtött értékek mennyiségétől függ. | A gyakorlatban a teljesítmény nem függ az összegyűjtött értékek mennyiségétől. |
| Ez a technika minden típusú kimenő dokumentum esetében működik. | Ez a technika csak szöveges és XML dokumentumok esetében működik. |

## <a name="additional-resources"></a>További erőforrások

- [Számláláshoz és összegzéshez használt formátum konfigurálása](./tasks/er-format-counting-summing-1.md)
- [A szekvenciaelemek végrehajtásának elhalasztása az ER-formátumokban](er-defer-sequence-element.md#Example)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
