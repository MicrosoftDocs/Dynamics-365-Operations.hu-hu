---
title: Importálás manuálisan kiválasztott fájlokból kötegelt módban
description: Ez a cikk bemutatja, hogy hogyan importálhat adatokat manuálisan kiválasztott fájlokból kötegelt módban.
author: kfend
ms.date: 01/07/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2022-01-01
ms.dyn365.ops.version: Release 10.0.25
ms.custom: 220314
ms.assetid: ''
ms.search.form: ERSolutionTable, ERImportFormatSourceTable, ERWorkspace
ms.openlocfilehash: 21a2ab5f0eb07dda92baf9cc04ee36caeff8b4ec
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9288228"
---
# <a name="import-data-from-manually-selected-files-in-batch-mode"></a>Importálás manuálisan kiválasztott fájlokból kötegelt módban

[!include[banner](../includes/banner.md)]
[!include[banner](../includes/preview-banner.md)]

Ha az elektronikus jelentési [(ER)](general-electronic-reporting.md) keretrendszert használni kell a manuálisan kiválasztott bejövő fájlok adatainak kötegelt módban történő importálására, konfigurálja az importálást támogató ER-formátumot [...](er-overview-components.md#format-component). Ezután az adott [formátumot](er-overview-components.md#model-mapping-component)**adatforrásként** használó céltípus modellleképezésének futtatása. Az adatok importálása során tallózással keresse meg az importálni kívánt fájlt, majd válassza ki manuálisan. 

Az új ER-képesség, amely kötegelt módban támogatja az adatok importálását, lehetővé teszi a folyamat felügyelet nélküliként történő konfigurálését. Az ER-konfigurációk használatával lehet adatimportációt végezni egy új kötegelt feladatnak az ER felhasználói felületről történő ütemezésével.

Ez a cikk bemutatja, hogyan lehet kötegelt módban elvégezni a manuálisan kiválasztott fájlokból történő adatimportadatokat. A példákban a szállítói tranzakciók üzleti adatokként szerepelnek. A példák lépéseit az **USMF vállalatnál lehet** végrehajtani. Nincs szükség kódolásra.

## <a name="prerequisites"></a>Előfeltételek

Az ebben a példában olvasható példák csak a következő hozzáféréssel egészek ki:

- A következő szerepkörök egyike:

    - Elektronikus jelentések fejlesztője
    - Elektronikus jelentések funkcióival foglalkozó konzulens
    - Rendszergazda

- ER-formátum és modellkonfigurációk 1099-es kifizetésekhez

### <a name="create-the-required-er-configurations"></a>A szükséges ER-konfigurációk létrehozása

A szükséges ER-konfigurációk létrehozásához és más előfeltételek beszerzéséhez hajtsa végre a következő lépések valamelyikét:

- Játssza le az **Elektronikus jelentéskészítés – adatok importálása Microsoft Excel-fájlból** feladat-útmutatókat, amelyek a **7.5.4.3 Informatikai szolgáltatások/megoldások összetevőinek beszerzése/kifejlesztése (10677)** üzleti folyamat részei. A feladat útmutatója a szállítói tranzakciók fájlokból történő interaktív importálását lehetővé tő ER-konfigurációk tervezésének és használatának folyamatát ismerteti Microsoft Excel. További tudnivalókért lásd: [Bejövő dokumentumok elemzése Excel formátumban](parse-incoming-documents-excel.md).
- Töltse ki a példákat az Adatok importálásának [konfigurálása innen történő konfigurálása során SharePoint](er-configure-data-import-sharepoint.md). A példák bemutatják az ER-konfigurációk tervezését és használatát, amelyek interaktív módon importálnak szállítói tranzakciókat az Excel-fájlokból, amelyek egy mappában vannak tárolva SharePoint.

### <a name="download-the-required-er-configurations"></a>A szükséges ER-konfigurációk letöltése

1. Töltse le a következő ER-konfigurációkat, majd mentse azokat helyben.

    | Tartalom leírása | Fájl |
    |---------------------|------|
    | **1099-es fizetési modell** ER adatmodell-konfigurációja | [1099model.xml](https://download.microsoft.com/download/b/d/9/bd9e8373-d558-4ab8-aa9b-31981adc97ea/1099model.xml) |
    | **Szállítói tranzakciók (Excel) ER-formátum-konfigurációjának** importálására | [1099format-import-from-excel.xml](https://download.microsoft.com/download/b/3/8/b38faf0a-fbaf-4e9e-84c2-dedae7464880/1099format-import-from-excel.xml) |

2. A következő sorrendben [importálhatja](er-defer-sequence-element.md#import-the-sample-er-configurations) a letöltött ER-konfigurációkat az Ön Dynamics 365 Pénzügy példányába az XML-fájlból – ER beállítással:

    1. ER-adatmodell konfigurációja
    2. ER-formátum konfigurációja

### <a name="download-the-required-excel-files"></a>A szükséges Excel-fájlok letöltése

- Töltse le és mentse helyileg a következő minta-adathalmazt.

    | Tartalom leírása | Fájl |
    |---------------------|------|
    | **Bejövő 1099import-data.xlsx** fájl, amely az importáláshoz szükséges mintaadatokat tartalmazza. | [1099import-data.xlsx](https://download.microsoft.com/download/f/f/4/ff4dbce9-8364-4391-adee-877945ff01f7/1099import-data.xlsx) |

### <a name="review-the-prerequisites"></a>Az előfeltételek áttekintése

1. Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**.
2. A Konfigurációk **lapon** ellenőrizze az előkészített ER-megoldást az adatimporthoz kötegelt módban.
3. **Ellenőrizze a Szállítói tranzakciók importálása (Excel) formátum konfigurációját**.

    - A konfiguráció formátumösszetevője egy bejövő Excel-fájl elemzési formátuma.
    - A konfiguráció modellleképezési összetevője az alapadatmodell kitöltésére használható az elemezett Excel-fájl adatai alapján.

    ![ER formátumkonfiguráció az adatok kötegelt módban, az ER felhasználói felületről történő importáláshoz.](./media/er-configure-data-import-batch-configurations-1.png)

4. Tekintse át az **1099-es fizetési modell adatmodell-konfigurációját**.

    - A konfiguráció modellösszetevőja annak az adatmodellnek a szerkezetét ábrázolja, amely az adatoknak az ER-összetevők futtatása között való továbbzére használatos.
    - A konfiguráció modell-hozzárendelési összetevőjét használja a program a végrehajtott formátumösszetevő adatainak le lekérdezésére, majd az alkalmazástáblák frissítésére.

    ![ER adatmodell-konfiguráció adatok kötegelt módban történő importálására az ER felhasználói felületről.](./media/er-configure-data-import-batch-configurations-2.png)

5. **Az 1099import-data.xlsx fájl** megnyitása az Excel programban.

    ![Minta Excel-fájl, amely kötegelt módban importálható adatokat tartalmaz.](./media/er-configure-data-import-batch-excel-content.png)

## <a name="enable-batch-data-import-for-er-from-the-ui"></a>Kötegelt adatok felhasználói felületről történő importálásának engedélyezése az ER számára

1. Válassza a **Rendszerfelügyelet** \> **Munkaterületek** \> **Funkciókezelés** elemet.
2. A Funkciókezelés **munkaterületen** jelölje be a Kötegelt funkcióban a manuálisan **feltöltött dokumentumok ER-importálásának** futtatását, majd az **Engedélyezés lehetőséget**.

## <a name="import-data-from-manually-selected-excel-files"></a>Adatok importálása manuálisan kijelölt Excel-fájlokból

1. Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**.
2. A Konfigurációk **lapon** válassza **ki az 1099-es fizetési modell adatmodell-konfigurációját**.
3. A Konfigurációs **összetevők** gyors oldalon válassza a **For 1099 manuális tranzakciók importálása hivatkozást**.
4. A Modell és **adatforrás megfeleltetése** lapon **a 1099-es** manuális tranzakciók importmodell-hozzárendelése előzetesen be van jelölve. Válassza a **Futtatás** parancsot.
5. A Paraméterek **lapon** válassza a Tallózás **lehetőséget**. Keresse meg és válassza ki az **1099import-data.xlsx** fájlt, majd válassza az **OK gombra.**
6. A Bizonylatazonosító **beírása** mezőbe írja be a **V-00001 azonosítót**.
7. A háttérben **futó futtatás lapon** állítsa **a Kötegelt feldolgozás** beállítást Igen **beállításra**.

    A feladat leírásmezője **a** **"1099-es manuális tranzakciók importálása esetén" modellmegfeleltetés Futtatása beállításra van beállítva (konfiguráció: "1099-es fizetési modell"**. Ez az érték azt jelzi, hogy a kiválasztott modellleképezés végrehajtása új kötegelt feladatként lesz ütemezve.

    ![Az Adatok kötegelt módban történő importálásának részleteinek megadása az Elektronikus jelentés paraméterei párbeszédpanelen.](./media/er-configure-data-import-batch-execution-parameters.png)

8. Válassza ki az **OK** lehetőséget. Egy üzenet jelzi, hogy egy új kötegelt feladatot ütemeztek.

    ![Üzenet a Modell adatforrás-hozzárendelési lapon található új ütemezett kötegelt feladatról.](./media/er-configure-data-import-batch-scheduled-job-info.png)

## <a name="review-the-data-import-results-on-the-batch-job-page"></a>Tekintse át az adatok importálásának eredményeit a Kötegelt feladat lapon.

1. Lépjen az **Általános** \> **Lekérdezések** \> **Kötegelt feladatok** \> **Saját kötegelt feladatok** pontra.
2. A Kötegelt **feladat lapon** szűrje a kötegelt feladatok listáját, hogy megkeresse az ütemezett köteget, majd válassza ki.
3. A feladat **részleteinek ellenőrzéshez** válassza ki a Feladatazonosító hivatkozást.
4. Válassza a **Napló lehetőséget** a Kötegfeladatok **gyorslapon**.

    ![Eseménynapló gomb a Kötegelt feladat lapon.](./media/er-configure-data-import-batch-scheduled-job-record.png)

5. Tekintse át a végrehajtás részleteit.

    ![Az ütemezett kötegelt feladat végrehajtási naplója a Kötegelt feladat lapon.](./media/er-configure-data-import-batch-scheduled-job-log.png)

## <a name="change-the-data-import-parameters"></a>Az adatimportfájl-importálási paraméterek módosítása

A köteg ütemezése után, és bár még nem futtatták, az ütemezett adatimportáltak paramétereit módosíthatja.

1. Lépjen az **Általános** \> **Lekérdezések** \> **Kötegelt feladatok** \> **Saját kötegelt feladatok** pontra.
2. A Kötegelt **feladat lapon** szűrje a kötegelt feladatok listáját, hogy megkeresse az ütemezett köteget, majd válassza ki.
3. Válassza az **Állapot módosítása** lehetőséget.
4. Az Új állapot **kiválasztása párbeszédpanelen válassza a** **Visszatartás lehetőséget, majd kattintson az** OK **gombra**.
5. A feladat **részleteinek eléréséhez** válassza ki a Feladatazonosító hivatkozást.
6. A Kötegelt feladatok **gyorslapon** válassza ki a **paramétereket**.
7. Az Elektronikus jelentés **paraméterei** párbeszédpanelen hajtsa végre a következő lépéseket:

    1. Válassza a **Tallózás** lehetőséget az adatimport másodlagos fájl kiválasztásához.
    2. Válassza **ki a Bizonylatazonosító beírása** lehetőséget a szállítói tranzakciók importálásának bizonylatszámának a módosításahoz.

        ![Az ütemezett kötegelt feladat adatimportálta paramétereinek módosítása az Elektronikus jelentés paraméterei párbeszédpanelen.](./media/er-configure-data-import-batch-scheduled-job-parameters.png)

    3. Válassza ki az **OK** lehetőséget.

8. Győződjön meg róla, hogy a köteg ki van választva, majd válassza újra az Állapot **módosítása** lehetőséget.
9. Az Új állapot kiválasztása párbeszédpanelen **válassza a Várakozás** **lehetőséget, majd kattintson az** OK gombra **.**

## <a name="review-the-data-import-results-on-the-er-source-page"></a>Az adatok importálási eredményeinek áttekintése az ER forrásoldalon

1. Ugrás a Szervezet **felügyelete** \> **Elektronikus jelentéskészítés elektronikus jelentési** \> **forrásának**
2. A szállítói **tranzakciók importálása (Excel)** rekord kiválasztása, amely automatikusan jött létre az adatok importálása során.

    ![Rekord a szállítók tranzakcióinak (Excel) importálására az Elektronikus jelentés forrásoldalán.](./media/er-configure-data-import-batch-files-source-1.png)

3. Válassza ki **a fájlok államát a forrásokhoz**.
4. Tekintse át **az** importálás részleteit **a** FastTabs importálási formátum Fájl- és forrásnaplóiban.
5. A Fájlok **gyors** oldalon válassza ki a rekordot. Az importált fájl ehhez a rekordhoz van csatolva.

    ![A forrásoldalhoz a rekordhoz csatolt importált fájl.](./media/er-configure-data-import-batch-files-source-2.png)

6. Válassza ki **a mellékleteket** az importált fájl ellenőrzéshez.

    ![Importált fájl a Dokumentum nézet oldalon.](./media/er-configure-data-import-batch-files-source-3.png)

    > [!TIP]
    > A mellékletek megtartására [az](electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents)**ER** keretrendszer egy olyan dokumentumtípust használ, amely az aktuális vállalathoz van beállítva az ER-paraméterek Egyebek mezőjében.

## <a name="review-the-data-import-results-on-the-vendor-settlement-for-1099s-page"></a>A Szállítói kiegyenlítések – 1099s lap adatimport adatainak importálási eredményeinek áttekintése

1. Ugrás a **Kötelezettségek**\> – **Időszakos feladatok adó** \> **- 1099-es szállítói** \> **kiegyenlítés az 1099-es jelentéshez.**
2. Írja **be** **a 2017. december 31. 12-ét (2017**. december 31.).
3. Válassza ki **a manuális 1099-es tranzakciókat**.

    ![Importált szállítói tranzakciók az 1099-es adótranzakciók oldalon.](./media/er-configure-data-import-batch-imported-data.png)

## <a name="additional-resources"></a>További erőforrások

[Elektronikus jelentések áttekintése](general-electronic-reporting.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
