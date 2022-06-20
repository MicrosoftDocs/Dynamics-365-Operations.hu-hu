---
title: Vonalkód-adatforrások használata vonalkód-képek létrehozásához
description: Ez a cikk bemutatja, hogy hogyan lehet vonalkód-adatforrásokat használni vonalkód-képek létrehozásához.
author: NickSelin
ms.date: 10/21/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERModelMappingDesigner, EROperationDesigner
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: Version 10.0.13
ms.openlocfilehash: c8e755b664656a1a10672a990dc581969f6a7b80
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8880312"
---
# <a name="use-barcode-data-sources-to-generate-bar-code-images"></a>Vonalkód-adatforrások használata vonalkód-képek létrehozásához

[!include[banner](../includes/banner.md)]

Az Elektronikus jelentési [(ER)](general-electronic-reporting.md) keretrendszer használatával ER-formátumösszetevők tervezhetők, amelyek futtatásával a szükséges elektronikus és nyomtatható kimenő dokumentumok generálhatók. A kimenő dokumentumok Microsoft Office formátumba történő előállításához meg kell adni a jelentés elrendezését egy Microsoft Excel dokumentummal vagy egy Microsoft Word dokumentummal a jelentés sablonjaként. Az [ER-műveleti tervező ](general-electronic-reporting.md#building-a-format-that-uses-a-data-model-as-a-base) segítségével egy Excel- vagy Word-dokumentumot csatolhat egy ER-formátumhoz. A csatolt sablonban a következő névvel ellátott elemek vannak társítva a konfigurált formátum-összetevő elemeihez:

- Tartalmi vezérlőelemek a Word programban
- Névvel ellátott lapok, tartományok, cellák, alakzatok és képek az Excel programban

Ezek a névvel ellátott elemek helyőrzőként használatosak a létrejövő dokumentumban megadott adatoknál, amikor az ER-formátum fut. Az ER-formátumösszetevők az adatforrásokhoz vannak kötve. Ezek az adatforrások határozzák meg, hogy milyen adatok szerepeljenek a létrejövő dokumentumokban futásidőben. További információkért lásd: [Beágyazott képek és alakzatok az ER-rel generált dokumentumokban](electronic-reporting-embed-images-shapes.md)

Az ER most már támogatja a **Vonalkód** adatforrástípust. Ebből következően a megadott szöveg vonalkódját képviselő kép generálható. Ha beállít egy ER-formátumot, akkor a **Vonalkód** típusú adatforrásokat a vonalkódképek előállítására is megadhatja. Ezt követően ezeket a képeket hozzáadhatja a létrejövő üzleti dokumentumokhoz, például rendelésekhez, számlákhoz, szállítólevelekhez és számlákhoz. A különféle címkékhez, például termék és polc címkékhez, csomagolási és levélcímkékhez is hozzáadhatók.

A következő helyőrzők használhatók a jelentéskészítő sablonokban a vonalkódképek megadásához:

- [Kép](/office/client-developer/word/content-controls-in-word) tartalmi vezérlőelem a Word programhoz
- [Kép](https://support.office.com/article/insert-pictures-3c51edf4-22e1-460a-b372-9329a8724344) objektum az Excel programban

A **Vonalkód** típusú adatforrás használatával a következő formátumokban lehet vonalkódokat generálni:

- Egydimenziós vonalkódok:

    - Codabar
    - Code 39
    - Code 93
    - Code 128
    - EAN-8
    - EAN-13
    - ITF-14
    - Intelligens e-mail
    - MSI
    - Plessey
    - PDF417
    - UPC-A
    - UPC-E

- Kétdimenziós vonalkódok:

    - Aztec
    - Adatmátrix
    - QR-kód

**Vonalkód** adatforrás konfigurálásakor megadhatók a lemezképek létrehozásához használt speciális renderelési paraméterek:

- **Szélesség** – Adja meg a vonalkód szélességét képpontban. A **0** (nulla) érték azt jelzi, hogy az alapértelmezett szélességet használja a program. A jelentés a különböző formátumokra változhat.
- **Magasság** – Adja meg a vonalkód magasságát képpontban. A **0** (nulla) érték azt jelzi, hogy az alapértelmezett magasságot használja a program. A jelentés a különböző formátumokra változhat.
- **Margó** – Adja meg a vonalkód margójának méretét képpontban. A margó a vonalkód mindkét oldalán látható terület, amelyet tisztán kell tartani (csendes zóna). A **0** (nulla) érték azt jelzi, hogy az alapértelmezett margót használja a program. A jelentés a különböző formátumokra változhat.
- **Kimeneti tartalom** – Az érték **Igen** értékre állítása olyan vonalkódkép létrehozásához, amely a kódolt információt szövegként tartalmazza. Az alapértelmezett érték a **Nem**.
- **Kódolás** – Adja meg, hogy milyen típusú karaktereket kódol a program a létrehozott vonalkódképben. Alapértelmezés szerint az **UTF-8** kódolást használja a program.

> [!IMPORTANT]
> Amikor új **Vonalkód** adatforrást ad hozzá, azt egy másik elem (konténer) alá kell helyeznie beágyazott elemként.
>
> Amikor egy **Vonalkód** adatforrást egy cella elemhez köt egy formátumban, és a cella elem vagy egy Word tartalmi vezérlőelemet vagy egy Excel-képet képvisel, akkor az adatforrás egy olyan funkcióként jelenik meg a kötésben, amely egyetlen, **karakterlánc** típusú paraméterrel rendelkezik. Ennek a paraméternek a használatával meg kell határoznia, hogy milyen szöveget kell a vonalkód-lemezképbe átalakítani, és mit kell kiolvasni a létrehozott vonalkódot beolvasásakor.

A funkcióval kapcsolatos további tudnivalókat az alábbi példában olvashatja.

## <a name="example-generate-a-payment-check-that-contains-a-bar-code-that-encodes-the-payable-amount"></a>Példa: Egy olyan vonalkódot tartalmazó kifizetési csekk előállítása, amely kódolja a kötelezettség összegét

Ez a példa azt mutatja be, hogy a **Rendszergazda** vagy az **Elektronikus jelentéskészítési funkció konzulens** szerepkörében egy felhasználó beállíthat egy olyan ER-formátumot, amely vonalkódot tartalmazó Excel-formátumú kimenő dokumentum előállítására szolgál. Az alábbiakban egy áttekintés olvasható a szóban forgó lépésekről.

1. [Teljesítse az előfeltételeket](#ExamplePrerequisites).
2. [Konfigurációszolgáltató aktiválása](#ExampleProvider).
3. [A nyújtott ER-megoldás importálása](#ExampleImportSolution).
4. [Kifizetési csekk előállítása](#ExampleGenerateCheque).
5. [A létrehozott kifizetés csekk ellenőrzése](#ExampleReviewGeneratedCheque).
6. [A megadott ER-megoldás formátumának módosítása](#ExampleModifyFormat).

    1. [Új csekksablon alkalmazása](#ExampleModifyFormatApplyTemplate).
    2. [Új vonalkód adatforrás hozzáadása](#ExampleModifyFormatAddDataSource).
    3. [Új formátumelem kötése](#ExampleModifyFormatBindFormatElement).
    4. [A módosított verzió elérhetővé tétele tesztfuttatásra](#ExampleModifyFormatMakeVersionAvailable).

        1. [Töltse ki a módosított formátum verziószámát](#CompleteToRun).
        2. [A piszkozat verziójának elérhetővé tétele használatra](#MarkToRun).

7. [Kifizetési csekk előállítása](#ExampleGenerateCheque2).
8. [A létrejövő csekk átalakítása PDF-formátumra](#ExampleConvertToPDF).

Ebben a példában a megadott ER-megoldást kell konfigurálni a kifizetési csekkek létrehozásához. Ez a megoldás olyan kifizetési csekkeket hoz létre, amelyeknél a fizetendő összeg számként és szövegként van írva. Ezt az ER-megoldást akkor fogja módosítani, ha a csekk tartalmaz egy olyan felállított vonalkódot is, amelyben a fizetendő összeg kódolva van, és a vonalkódos lapolvasó használatával olvasható.

A lépéseket az **USMF** vállalatnál lehet végrehajtani a Microsoft Dynamics 365 Pénzügyben.

### <a name="complete-the-prerequisites"></a><a name="ExamplePrerequisites"></a>Teljesítse az előfeltételeket

A jelen példa végrehajtásához hozzáféréssel kell rendelkeznie az USMF vállalathoz a Finance megoldásban a következő szerepkörök egyikéhez:

- Elektronikus jelentések funkcióival foglalkozó konzulens
- Rendszergazda

Ha még nem fejeződött [be a példa az ER-cikk segítségével generált dokumentumok képek és alakok beágyazása részen, töltse le az ER-minta](electronic-reporting-embed-images-shapes.md) megoldás alábbi konfigurációit.

| Tartalom leírása         | Fájlnév                   |
|-----------------------------|-----------------------------|
| ER-adatmodell konfigurációja | [Model for cheques.xml](https://download.microsoft.com/download/6/e/a/6ea166fd-1382-4fdb-8dcb-0f13379f9c8e/Modelforcheques.xml)      |
| ER-formátum konfigurációja     | [Cheques printing format.xml](https://download.microsoft.com/download/1/7/c/17c301e3-c4ee-4886-ae75-440fcc002c8c/Chequesprintingformat.xml) |

Ezenkívül töltse le a következő Excel-fájlt, amely tartalmazza a megadott ER-megoldás módosított sablonját.

| Tartalom leírása | Fájlnév                 |
|---------------------|---------------------------|
| Jelentéssablon     | [Check template Excel.xlsx](https://download.microsoft.com/download/3/b/d/3bd3b944-da8f-43b4-8533-3c1292a4c3ef/CheckTemplateExcel.xlsx) |

### <a name="activate-a-configuration-provider"></a><a name="ExampleProvider"></a>Konfigurációszolgáltató aktiválása

1. Ugorjon a **Szervezeti adminisztráció** \> **Munkaterületek** \> **Elektronikus jelentés** pontra.
2. Győződjön meg róla, hogy a **Honosítási konfigurációk** lap **Konfigurációs szolgáltatók** szakaszában a **Litware, Inc.** [konfigurációs szolgáltatója](general-electronic-reporting.md#Provider) szerepel a listán, és aktívként van megjelölve. Ha nem szerepel a listán, vagy ha nem aktívként van megjelölve, kövesse a Konfigurációszolgáltató létrehozása lépést, [és jelölje meg aktív cikkként](tasks/er-configuration-provider-mark-it-active-2016-11.md).

![Mintavállalat beállítása aktívként a Lokalizációs konfigurációk oldalon.](./media/er-barcode-data-source-active-provider.png)

### <a name="import-the-provided-er-solution"></a><a name="ExampleImportSolution"></a>A nyújtott ER-megoldás importálása

1. Ugorjon a **Szervezeti adminisztráció** \> **Munkaterületek** \> **Elektronikus jelentés** pontra.
2. A **Lokalizációs konfigurációk** oldalon, a **Konfigurációk** szakaszban, válassza ki a **Jelentéskészítési konfiguráció** csempét.
3. A **Konfigurációk** oldalon, ha nem érhető el a **Model for cheques** konfiguráció a konfigurációs fában, importálja az ER-adatmodell konfigurációját a következő lépésekkel:

    1. A Műveleti ablaktáblában válassza az **Átváltás** \> **Betöltés XML-fájlból** elemet.
    2. Válassza a **Tallózás** elemet a párbeszédpanelen, keresse meg és válassza ki a **Model for cheques.xml** fájlt, majd kattintson az **OK** gombra.

4. Ha nem érhető el a **Cheques printing format** konfiguráció a konfigurációs fában, importálja az ER-formátum konfigurációját a következő lépésekkel:

    1. A Műveleti ablaktáblában válassza az **Átváltás** \> **Betöltés XML-fájlból** elemet.
    2. Válassza a **Tallózás** elemet a párbeszédpanelen, keresse meg és válassza ki a **Cheques printing format.xml** fájlt, majd kattintson az **OK** gombra.

5. A konfigurációs fában bontsa ki ezt: **Model for cheques**.
6. Tekintse át a konfigurációs fában importált ER-konfigurációk listáját.

### <a name="generate-a-payment-check"></a><a name="ExampleGenerateCheque"></a>Kifizetési csekk előállítása

1. Menjen a **Készpénz és bankkezelés** \> **Bankszámlák** \> **Bankszámlák** menüpontra.
2. A **Bankszámlák** lapon válassza ki az **USMF OPER** fiókot.
3. A bankszámla részletei oldal műveleti ablaktábláján, a **Beállítás** lapon, az **Elrendezés** csoportban válassza ki az **Ellenőrzés** lehetőséget.
4. Az **Elrendezés ellenőrzése** lapon válassza a **Szerkesztés** parancsot.
5. Adja meg az **Általános** gyorslap **Általános elektronikus export formátum** beállítását **Igen** értékre.
6. Az **Exportálási formátum konfigurálása** mezőben válassza ki a **Csekkek nyomtatási formátuma** korábban importált ER-formátumot.
7. A Művelet ablaktáblán válassza ki a **Nyomtatási tesz** elemet.
8. A párbeszédpanelen állítsa az **Átruházható csekkformátum** beállítását **Igen** értékre, majd kattintson az **OK** gombra.

    ![Elrendezés ellenőrzése – teszt párbeszédpanel nyomtatása.](./media/er-barcode-data-source-check-layout.png)

### <a name="review-the-generated-payment-check"></a><a name="ExampleReviewGeneratedCheque"></a>A létrehozott kifizetés csekk ellenőrzése

- A létrejövő csekk megnyitása az Excel programban.
2. Tekintse át a létrehozott csekket.

    ![A létrejött fizetési csekk az Excel programban.](./media/er-barcode-data-source-cheque1.png)

### <a name="modify-the-format-of-the-provided-er-solution"></a><a name="ExampleModifyFormat"></a>A megadott ER-megoldás formátumának módosítása

#### <a name="apply-a-new-check-template"></a><a name="ExampleModifyFormatApplyTemplate"></a>Új csekksablon alkalmazása

Az Excel asztali alkalmazással megnyithatja a korábban importált **Cheque template Excel.xlsx** fájlt. Figyelje meg, hogy ez a sablon különbözik a fizetési csekk előállításához használt sablontól a megadott ER-megoldásban. Ezenkívül tartalmaz egy **AmountBarcode** elemet a vonalkódképhez.

![AmountBarcode elem az Excel-sablonban.](./media/er-barcode-data-source-cheque2.png)

Most módosítania kell az ER-megoldást, majd [újra alkalmaznia kell](modify-electronic-reporting-format-reapply-excel-template.md) a módosított sablont.

1. Ugorjon a **Szervezeti adminisztráció** \> **Munkaterületek** \> **Elektronikus jelentés** pontra.
2. A **Lokalizációs konfigurációk** oldalon, a **Konfigurációk** szakaszban, válassza ki a **Jelentéskészítési konfiguráció** csempét.
3. A **Konfigurációk** lapon, a konfigurációs fában, bontsa ki a **Modell csekkekhez** elemet, majd válassza a **Csekkek nyomtatása formátum** elemet.
4. A Műveleti ablaktáblán kattintson a **Tervező** elemre.
5. Az ER műveleti tervezőben válassza ki az oldal jobb oldalán található **Leképezés** lapot, majd a bal oldali formátum ablaktáblán válassza a **Kibontás/összecsukás** parancsot.
6. Figyelje meg, hogy minden cellaformázás-elem kötődik a megfelelő adatforrásokhoz.

    ![A cellaformázás elemek kötése az ER műveletek tervezője adatforrásaihoz.](./media/er-barcode-data-source-cells-bound.png)

7. Válassza ki a **Formátum** lapot az oldal jobb oldalán.
8. A műveleti ablaktáblán válassza ki a három pontot (**...**), majd válassza az **Importálás** elemet.
9. Az **Importálás** csoportban válassza a **Frissítés az Excel programból** elemet, majd válassza a **Sablon frissítése** parancsot.
10. A párbeszédpanelen tallózással keresse meg a számítógépre mentett **Cheque template Excel.xlsx** fájlt, majd válassza ki, majd az **OK** gombra kattintva erősítse meg, hogy a kiválasztott sablont kell alkalmazni.
11. Válassza ki az oldal jobb oldalán található **Leképezés** lapot, majd a bal oldali formátum ablaktáblán válassza a **Kibontás/összecsukás** parancsot.
12. Figyelje meg, hogy az **AmountBarcode** cellaelem hozzá van rendelve a formátumhoz. Ez az elem ahhoz az **AmountBarcode** elemhez van társítva, amely a módosított Excel-sablonhoz a vonalkód-kép helyőrzőként lett hozzáadva.

    ![Az AmountBarcode cellaelem hozzáadva a formátumhoz az ER műveletek tervezőjében.](./media/er-barcode-data-source-cell-added.png)

#### <a name="add-a-new-barcode-data-source"></a><a name="ExampleModifyFormatAddDataSource"></a>Új vonalkód adatforrás hozzáadása

Ezután **Vonalkód** típusú új adatforrást kell hozzáadnia.

1. Ezután az ER műveleti tervezőben, a **Leképezés** lapon, amely az oldal jobb oldalán található, válassza ki az adatforrás **nyomtatását**.
2. Válassza a **Hozzáadás** parancsot, majd a **Funkciók** csoportban válassza ki a **Vonalkód** adatforrástípust.

    ![A vonalkód adatforrástípusának kiválasztása.](./media/er-barcode-data-source-add.png)

3. A párbeszédpanel **Név** mezőjébe írja be a **vonalkód** kifejezést.
4. A **Vonalkód formátuma** elemnél válassza a **Code 128** lehetőséget.
5. Írja be a **500** értéket a **Szélesség** mezőbe.
6. Válassza ki az **OK** lehetőséget.

    ![Adatforrás-tulajdonságok párbeszédpanel.](./media/er-barcode-data-source-add2.png)

#### <a name="bind-a-new-format-element"></a><a name="ExampleModifyFormatBindFormatElement"></a>Új formátumelem kötése

Ezután az új formátum elemet kötelező hozzákötni az imént hozzáadott adatforráshoz.

1. Ezután az ER műveleti tervezőben, a **Leképezés** lapon, amely az oldal jobb oldalán található, válassza ki az adatforrás **nyomtatás\\vonalkód** lehetőségét.
2. A bal oldali formátum fa ablakában Válassza ki az **AmountBarcode** cella elemét, majd válassza a **Kötés** elemet.
3. A Műveleti ablaktáblán kattintson a **Részletek megjelenítése** elemre.
4. Figyelje meg, hogy mivel a **Vonalkód** adatforrás egy olyan funkcióként jelenik meg a kötésben, amely egyetlen paramétert tartalmaz, a kötött formátumú elem neve automatikusan a paraméter argumentumaként szerepel.

    ![A vonalkód adatforrás adatai az ER-műveleti tervezőben.](./media/er-barcode-data-source-bind1.png)

5. A kötés módosításához válassza a **Receptúra szerkesztése** parancsot.

    Nem szeretné, hogy a cella elem nevének visszaadása történjen. Ennek megfelelően konfigurálnia kell egy kifejezést, amely az aktuális csekk fizetendő összegét tartalmazó szöveget adja vissza. Mivel a szülő **ChequeLines** tartomány a **model.cheques** adatforráshoz van kötve, az aktuális csekk fizetendő összege a **model.cheques.attributes.amount** mezőjében érhető el a **Tényleges** adattípusnak.

6. A **Receptúra** mezőbe írja be ezt: **print.barcode(NUMBERFORMAT(@.attributes.amount, "F2"))**.
7. Válassza a **Mentés** lehetőséget, majd zárja be az [ER receptúratervezőt](general-electronic-reporting-formula-designer.md).
8. Figyelje meg, hogy a kötés módosult.

    ![Helyesbített kötés az ER-műveleti tervezőben.](./media/er-barcode-data-source-bind2.png)

9. Válassza a **Mentés** lehetőséget, majd zárja be az ER műveleti tervezőt.

#### <a name="make-the-modified-version-available-for-test-runs"></a><a name="ExampleModifyFormatMakeVersionAvailable"></a>A módosított verzió elérhetővé tétele tesztfuttatásra

Alapértelmezésként a program csak a **teljesített** és a **megosztott** állapotú verziókat használja az ER-formátum futtatásakor.

Ha véglegesített a módosításokat, befejezheti a munkát az aktuális piszkozat verzióval, és elérhetővé teheti a változtatásokat használatra. A következő témakörben található további tájékoztatás: [Töltse ki a módosított formátum verziószámát](#CompleteToRun).

Ha folytatni kívánja az aktuális piszkozat verzió használatát, de a csekkek létrehozásához használnia kell, akkor explicit módon meg kell adnia, hogy a formátum piszkozat verzióját szeretné használni a végrehajtáshoz. További tájékoztatás a következő témakörben olvasható: [A piszkozat verziójának elérhetővé tétele használatra](#MarkToRun).

##### <a name="complete-the-modified-format-version"></a><a name="CompleteToRun"></a>Töltse ki a módosított formátum verziószámát

1. Ugorjon a **Szervezeti adminisztráció** \> **Munkaterületek** \> **Elektronikus jelentés** pontra.
2. A **Lokalizációs konfigurációk** oldalon, a **Konfigurációk** szakaszban, válassza ki a **Jelentéskészítési konfiguráció** csempét.
3. A **Konfigurációk** lapon, a konfigurációs fában, bontsa ki a **Modell csekkekhez** elemet, majd válassza a **Csekkek nyomtatása formátum** elemet.
4. A **Verziók** gyorslapon válassza ki azt a rekordot, amelynek állapota **piszkozat**.
5. Válassza ki az **Állapot módosítása** elemet, majd kattintson a **Befejezés** gombra.
6. Kattintson az párbeszédpanelen az **OK** gombra.

Az aktuális verzió állapota a **Piszkozat** értékről a **Befejezett** értékre módosul, és létrejön egy új, **Piszkozat** állapotú verzió. Az új piszkozat verzióra további változtatásokat alkalmazhat.

##### <a name="make-the-draft-version-available-for-use"></a><a name="MarkToRun"></a>A piszkozat verziójának elérhetővé tétele használatra

1. Ugorjon a **Szervezeti adminisztráció** \> **Munkaterületek** \> **Elektronikus jelentés** pontra.
2. A **Lokalizációs konfigurációk** oldalon, a **Konfigurációk** szakaszban, válassza ki a **Jelentéskészítési konfiguráció** csempét.
3. A **Konfigurációk** oldal műveleti ablaktábláján, a **Konfigurációk** lapon, a **Speciális beállítások** csoportban válassza a **Felhasználói paraméterek** lehetőséget.
4. A párbeszédpanelen állítsa az **Futtatási beállítás** beállítását **Igen** értékre, majd kattintson az **OK** gombra.
5. A konfigurációs fában, bontsa ki a **Modell csekkekhez** elemet, majd válassza a **Csekkek nyomtatása formátum** elemet.
6. Állítsa a **Piszkozat futtatása** beállítást **Igen** lehetőségre.
7. Válassza a **Mentés** lehetőséget.

A kijelölt formátum piszkozata használatra elérhető megjelölést kap a kiválasztott formátum futtatásakor.

### <a name="generate-a-payment-check"></a><a name="ExampleGenerateCheque2"></a>Kifizetési csekk előállítása

1. Menjen a **Készpénz és bankkezelés** \> **Bankszámlák** \> **Bankszámlák** menüpontra.
2. A **Bankszámlák** lapon válassza ki az **USMF OPER** fiókot.
3. A bankszámla részletei oldal műveleti ablaktábláján, a **Beállítás** lapon, az **Elrendezés** csoportban válassza ki az **Ellenőrzés** lehetőséget.
4. Válassza ki a **Csekk elrendezés** lap művelet ablaktábláján a **Teszt nyomtatása** lehetőséget.
5. A párbeszédpanelen állítsa az **Átruházható csekkformátum** beállítását **Igen** értékre.
6. Válassza ki az **OK** lehetőséget.
7. Tekintse át a létrehozott csekket. Figyelje meg, hogy a rendszer vonalkódot hoz létre, amely kódolja a csekk fizetendő összegét.

    ![Vonalkódos fizetési csekk létrehozása az Excel alkalmazásban.](./media/er-barcode-data-source-cheque3.png)

> [!IMPORTANT]
> Kivétel akkor történik, ha a **Vonalkód** adatforrás argumentuma nem felel meg a vonalkód-formátumára vonatkozó megfelelő követelményeknek. Ha például a **Vonalkód** adatforrás egy [EAN-8](https://wikipedia.org/wiki/EAN-8) vonalkódot hoz létre a megadott szöveghez, akkor a program kivételt eredményez, ha a szöveg hossza meghaladja a 7 karaktert.

### <a name="convert-the-generated-check-to-a-pdf"></a><a name="ExampleConvertToPDF"></a>A létrejövő csekk átalakítása PDF-formátumra

Amint azt a Nyomtatható [FTI képernyők](er-generate-printable-fti-forms.md#finland) létrehozása cikk ismerteti, különleges betűtípussal lehet vonalkódokat előállítani a generált dokumentumokban. Ebben az esetben előfordulhat, hogy a létrejövő dokumentum további átalakítása függhet az átalakítási környezetben található betűtípustól. Ha például a dokumentumot PDF-formátumra próbálja meg átalakítani, vagy egy olyan környezetben tekinti meg, ahol hiányzik a betűtípus, akkor a vonalkódok nem fognak helyesen megjeleníteni.

Ha azonban a **Vonalkód** adatforrást használja a vonalkódok létrehozásához, akkor az ilyen vonalkódok renderelése nem függ semmilyen betűtípustól. Ezért a vonalkódokat tartalmazó dokumentumokat egyszerűen konvertálhatja PDF-formátumba. A következő ábra egy olyan generált fizetési csekk előnézetét jeleníti meg, amely PDF-fájllá lett [konvertálva](electronic-reporting-destinations.md#OutputConversionToPDF) a konfigurált ER [cél](electronic-reporting-destinations.md) beállításai alapján.

![A kifizetési csekk PDF-fájljának előnézete.](./media/er-barcode-data-source-cheque4.png)

## <a name="limitations"></a>Korlátozások

> [!NOTE]
> A létrehozott vonalkódok néhány típusa rögzített méretarányú. Ennek a viselkedésnek akkor van jelentősége, ha be van kapcsolva az **EPPlus könyvtár használatának engedélyezése az elektronikus jelentési keretrendszerben** funkció az Excel-dokumentumokkal végzett munkához az ER-ben. Ebben az esetben a kép zárolt méretarányú helyőrzőbe kerül. Ezért ha egy sablonban egy helyőrző mérete megfelel egy megadott kép arányának, akkor elképzelhető, a létrejövő dokumentumban egy valódi kép átméretezhető lehet a szükséges méretarányt fenntartásához. Ha meg szeretné akadályozni, hogy a kép átméretezése megtörténjen, használjon egy olyan helyőrzőt, amelynek megfelelő a méretaránya.

## <a name="additional-resources"></a>További erőforrások

- [Elektronikus jelentések áttekintése](general-electronic-reporting.md)
- [Elektronikus jelentéskészítés céljai](electronic-reporting-destinations.md)
- [Elektronikus jelentéskészítés képletének nyelve](er-formula-language.md)
- [NUMBERFORMAT függvény](er-functions-text-numberformat.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
