---
title: Adatok importálása manuálisan kiválasztott fájlokból kötegelt módban
description: Ez a témakör bemutatja, hogyan importálhat adatokat a manuálisan kiválasztott fájlokból kötegelt módban.
author: NickSelin
ms.date: 01/07/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERImportFormatSourceTable, ERWorkspace
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2022-01-01
ms.dyn365.ops.version: Release 10.0.25
ms.openlocfilehash: 8615b5a0623fd696c64f4ec03e481a2bcb16c0ac
ms.sourcegitcommit: 89655f832e722cefbf796a95db10c25784cc2e8e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/31/2022
ms.locfileid: "8075746"
---
# <a name="import-data-from-manually-selected-files-in-batch-mode"></a>Adatok importálása manuálisan kiválasztott fájlokból kötegelt módban

[!include[banner](../includes/banner.md)]
[!include[banner](../includes/preview-banner.md)]

Használatához a [Elektronikus jelentéstétel (ER)](general-electronic-reporting.md) keretrendszerben, hogy adatokat importálhasson a manuálisan kiválasztott bejövő fájlokból kötegelt módban, konfiguráljon egy ER-t [formátum](er-overview-components.md#format-component) amely támogatja az importálást. Ezután futtassa a [modell leképezés](er-overview-components.md#model-mapping-component) a **A rendeltetési helyre** típus, amely ezt a formátumot használja adatforrásként. Adatok importálásához tallózással keresse meg az importálni kívánt fájlt, és válassza ki manuálisan. 

Az új ER-képesség, amely támogatja az adatimportálást kötegelt módban, lehetővé teszi ennek a folyamatnak a felügyelet nélküli konfigurálását. Az ER konfigurációk segítségével adatimportálást hajthat végre egy új kötegelt feladat ütemezésével az ER felhasználói felületről (UI).

Ez a témakör bemutatja, hogyan lehet befejezni az adatok importálását egy manuálisan kiválasztott fájlból kötegelt módban. A példákban a szállítói tranzakciók üzleti adatokként szerepelnek. A példák lépései a **USMF** vállalat. Nincs szükség kódolásra.

## <a name="prerequisites"></a>Előfeltételek

A jelen témakörben szereplő példák elvégzéséhez a következő hozzáférésekkel kell rendelkeznie:

- Az alábbi szerepek egyike:

    - Elektronikus jelentések fejlesztője
    - Elektronikus jelentések funkcióival foglalkozó konzulens
    - Rendszergazda

- ER formátum és modell konfigurációk 1099 fizetéshez

### <a name="create-the-required-er-configurations"></a>Hozza létre a szükséges ER-konfigurációkat

A szükséges ER-konfigurációk létrehozásához és egyéb előfeltételek megszerzéséhez kövesse az alábbi lépések egyikét:

- Játssza le az **Elektronikus jelentéskészítés – adatok importálása Microsoft Excel-fájlból** feladat-útmutatókat, amelyek a **7.5.4.3 Informatikai szolgáltatások/megoldások összetevőinek beszerzése/kifejlesztése (10677)** üzleti folyamat részei. Ezek a feladatútmutatók elmagyarázzák Önnek a szállítói tranzakciókat interaktívan importáló ER-konfigurációk tervezésének és használatának folyamatát.Microsoft Excel fájlokat. További tudnivalókért lásd: [Bejövő dokumentumok elemzése Excel formátumban](parse-incoming-documents-excel.md).
- Egészítse ki a példákat [Adatimportálás konfigurálása innen SharePoint](er-configure-data-import-sharepoint.md). Ezek a példák elmagyarázzák Önnek az olyan ER-konfigurációk tervezésének és használatának folyamatát, amelyek interaktívan importálják a szállítói tranzakciókat az Excel-fájlokból, amelyek egy SharePoint mappát.

### <a name="download-the-required-er-configurations"></a>Töltse le a szükséges ER-konfigurációkat

1. Töltse le a következő ER-konfigurációkat, és mentse őket helyileg.

    | Tartalom leírása | Fájl |
    |---------------------|------|
    | **1099 Fizetési modell** ER adatmodell konfigurációja | [1099model.xml](https://download.microsoft.com/download/b/d/9/bd9e8373-d558-4ab8-aa9b-31981adc97ea/1099model.xml) |
    | **Szállítói tranzakciók importálásához (Excel)** ER formátum konfiguráció | [1099format-import-from-excel.xml](https://download.microsoft.com/download/b/3/8/b38faf0a-fbaf-4e9e-84c2-dedae7464880/1099format-import-from-excel.xml) |

2. Használja a [Betöltés XML fájlból](er-defer-sequence-element.md#import-the-sample-er-configurations) ER lehetőség a letöltött ER-konfigurációk importálásához a példányodba Dynamics 365 Finance a következő sorrendben:

    1. ER-adatmodell konfigurációja
    2. ER-formátum konfigurációja

### <a name="download-the-required-excel-files"></a>Töltse le a szükséges Excel fájlokat

- Töltse le az alábbi mintaadatkészletet, és mentse el helyileg.

    | Tartalom leírása | Fájl |
    |---------------------|------|
    | Bejövő **1099import-data.xlsx** fájl, amely mintaadatokat tartalmaz az importáláshoz | [1099import-data.xlsx](https://download.microsoft.com/download/f/f/4/ff4dbce9-8364-4391-adee-877945ff01f7/1099import-data.xlsx) |

### <a name="review-the-prerequisites"></a>Tekintse át az előfeltételeket

1. Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**.
2. A **Konfigurációk** oldalon tekintse át az előkészített ER-megoldást az adatimportáláshoz kötegelt módban.
3. Tekintse át a **Szállítói tranzakciók importálásához (Excel)** formátum konfiguráció.

    - Ennek a konfigurációnak a formátumkomponense egy bejövő Excel-fájl elemzésére szolgál.
    - Ennek a konfigurációnak a modellleképezési összetevője az alapadatmodell kitöltésére szolgál az elemzett Excel-fájlból származó adatok felhasználásával.

    ![ER formátum konfiguráció az adatok kötegelt módban történő importálásához az ER UI-ról.](./media/er-configure-data-import-batch-configurations-1.png)

4. Tekintse át a **1099 Fizetési modell** adatmodell konfigurációja.

    - Ennek a konfigurációnak a modellkomponense annak az adatmodellnek a struktúráját képviseli, amely a futó ER-összetevők közötti adatok továbbítására szolgál.
    - Ennek a konfigurációnak a modellleképezési összetevője adatok lekérésére szolgál a végrehajtott formátumkomponensből, majd frissíti az alkalmazástáblázatokat.

    ![ER adatmodell konfigurációja adatok kötegelt módban történő importálásához az ER UI-ról.](./media/er-configure-data-import-batch-configurations-2.png)

5. Nyissa meg a **1099import-data.xlsx** fájlt az Excelben.

    ![Minta Excel-fájl adatokkal a kötegelt módban történő importáláshoz.](./media/er-configure-data-import-batch-excel-content.png)

## <a name="enable-batch-data-import-for-er-from-the-ui"></a>Engedélyezze a kötegelt adatimportálást az ER számára a felhasználói felületről

1. Válassza a **Rendszerfelügyelet** \> **Munkaterületek** \> **Funkciókezelés** elemet.
2. Ban,-ben **Funkciókezelés** munkaterületen válassza ki a **Futtassa a manuálisan feltöltött dokumentumok kötegelt ER-importálását** funkciót, majd válassza ki **Engedélyezze most**.

## <a name="import-data-from-manually-selected-excel-files"></a>Adatok importálása manuálisan kiválasztott Excel-fájlokból

1. Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**.
2. A **Konfigurációk** oldalon válassza ki a **1099 Fizetési modell** adatmodell konfigurációja.
3. A **Konfigurációs összetevők** FastTab, válassza ki a **1099 kézi tranzakció importálásához** link.
4. A **Modell-adatforrás-leképezés** oldal, a **1099 kézi tranzakció importálásához** a modellleképezés előre ki van választva. Válassza a **Futtatás** parancsot.
5. A **Paraméterek** lapon válassza ki **Tallózás**. Keresse meg és válassza ki a **1099import-data.xlsx** fájlt, majd válassza ki **rendben**.
6. Ban,-ben **Adja meg az utalvány azonosítóját** mezőbe írja be **V-00001**.
7. A **Fuss a háttérben** lapon állítsa be a **Kötegelt feldolgozás** opciót **Igen**.

    Vegyük észre, hogy a **Feladatleírás** mező értékre van állítva **Modell leképezés futtatása „1099 kézi tranzakciók importálásához”, konfiguráció „1099 fizetési modell”**. Ez az érték azt jelzi, hogy a kiválasztott modellleképezés végrehajtása új kötegelt feladatként lesz ütemezve.

    ![A kötegelt adatimportálás részleteinek megadása az Elektronikus jelentés paraméterei párbeszédpanelen.](./media/er-configure-data-import-batch-execution-parameters.png)

8. Válassza ki az **OK** lehetőséget. Egy üzenet értesíti, hogy egy új kötegelt feladat ütemezése megtörtént.

    ![Üzenet egy új ütemezett kötegelt feladatról a Modell adatforráshoz leképezési oldalon.](./media/er-configure-data-import-batch-scheduled-job-info.png)

## <a name="review-the-data-import-results-on-the-batch-job-page"></a>Tekintse át az adatimportálási eredményeket a Kötegelt feladat oldalon

1. Lépjen az **Általános** \> **Lekérdezések** \> **Kötegelt feladatok** \> **Saját kötegelt feladatok** pontra.
2. A **Kötegelt munka** oldalon, szűrje ki a kötegelt feladatok listáját az ütemezett köteg megkereséséhez, majd jelölje ki.
3. Válaszd ki a **Munkaazonosító** link a munka részleteinek megtekintéséhez.
4. A **Kötegelt feladatok** FastTab, válassza ki **Napló**.

    ![Napló gomb a Kötegelt munka oldalon.](./media/er-configure-data-import-batch-scheduled-job-record.png)

5. Tekintse át a végrehajtás részleteit.

    ![Az ütemezett kötegelt feladat végrehajtási naplója a Kötegfeladat oldalon.](./media/er-configure-data-import-batch-scheduled-job-log.png)

## <a name="change-the-data-import-parameters"></a>Módosítsa az adatimportálási paramétereket

Miután a köteg ütemezése megtörtént, és még nem futott le, módosíthatja az ütemezett adatimportálás paramétereit.

1. Lépjen az **Általános** \> **Lekérdezések** \> **Kötegelt feladatok** \> **Saját kötegelt feladatok** pontra.
2. A **Kötegelt munka** oldalon, szűrje ki a kötegelt feladatok listáját az ütemezett köteg megkereséséhez, majd jelölje ki.
3. Válassza az **Állapot módosítása** lehetőséget.
4. Ban,-ben **Válasszon új állapotot** párbeszédpanelen válassza ki **Tartsa vissza**, majd válassza ki **rendben**.
5. Válaszd ki a **Munkaazonosító** link a munka adatainak eléréséhez.
6. A **Kötegelt feladatok** FastTab, válassza ki **Paraméterek**.
7. Ban,-ben **Elektronikus jelentés paraméterei** párbeszédpanelen kövesse az alábbi lépéseket:

    1. Válassza ki **Tallózás** az adatimportálás alternatív fájljának kiválasztásához.
    2. Válassza ki **Adja meg az utalvány azonosítóját** szállítói tranzakciók importálásához szükséges bizonylatszám módosításához.

        ![Az ütemezett kötegelt feladat adatimportálási paramétereinek módosítása az Elektronikus jelentés paraméterei párbeszédpanelen.](./media/er-configure-data-import-batch-scheduled-job-parameters.png)

    3. Válassza ki az **OK** lehetőséget.

8. Győződjön meg arról, hogy a köteg továbbra is ki van választva, majd válassza ki **Állapotváltozás** újra.
9. Ban,-ben **Válasszon új állapotot** párbeszédpanelen válassza ki **Várakozás**, majd válassza ki **rendben**.

## <a name="review-the-data-import-results-on-the-er-source-page"></a>Tekintse át az adatimportálási eredményeket az ER forrásoldalán

1. Menj **Szervezeti adminisztráció** \> **Elektronikus jelentéstétel** \> **Elektronikus jelentési forrás**.
2. Válaszd ki a **Szállítói tranzakciók importálásához (Excel)** az adatimportálás során automatikusan létrejött rekord.

    ![Rekord a Szállítói tranzakciók importálásához (Excel) konfigurációhoz az Elektronikus jelentésforrás oldalon.](./media/er-configure-data-import-batch-files-source-1.png)

3. Válassza ki **A források fájlállapotai**.
4. A **Fájlok** és **Az importálási formátum forrásnaplói** FastTabs, tekintse át az importálás részleteit.
5. A **Fájlok** FastTab, válassza ki a rekordot. Figyelje meg, hogy az importált fájl ehhez a rekordhoz van csatolva.

    ![A rekordhoz csatolt importált fájl a források fájlállapotai oldalon.](./media/er-configure-data-import-batch-files-source-2.png)

6. Válassza ki **Mellékletek** az importált fájl áttekintésére.

    ![Importált fájl a Dokumentumnézet oldalon.](./media/er-configure-data-import-batch-files-source-3.png)

    > [!TIP]
    > A mellékletek megtartásához az ER keretrendszer olyan dokumentumtípust használ, amely a [készlet](electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents) a jelenlegi cég számára **Mások** az ER paraméterek mezőjében.

## <a name="review-the-data-import-results-on-the-vendor-settlement-for-1099s-page"></a>Tekintse át az adatimportálási eredményeket a Szállítói elszámolás az 1099s oldalon

1. Menj **Kötelezett számlák** \> **Időszakos feladatok** \> **Adó 1099** \> **Eladói elszámolás 1099-ért**.
2. Ban,-ben **Dátumtól** mezőbe írja be **2017.12.31** (2017. december 31.).
3. Válassza ki **Manuális 1099 tranzakció**.

    ![Importált szállítói tranzakciók az Adó 1099-tranzakciók oldalon.](./media/er-configure-data-import-batch-imported-data.png)

## <a name="additional-resources"></a>További erőforrások

[Elektronikus jelentések áttekintése](general-electronic-reporting.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
