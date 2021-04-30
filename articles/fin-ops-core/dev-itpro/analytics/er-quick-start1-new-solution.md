---
title: Új ER-megoldás tervezése egyéni jelentés nyomtatásához
description: Ez a témakör azt mutatja be, hogyan tervezhető elektronikus jelentési megoldás (ER) egyéni jelentés nyomtatásához.
author: NickSelin
ms.date: 08/10/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERParameters, ERDataModelDesigner, ERModelMappingTable, ERModelMappingDesigner, EROperationDesigner, ERVendorTable
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6a3e0e4a8389fdd6580f66004d86ef4b1980dd9f
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/13/2021
ms.locfileid: "5891793"
---
# <a name="design-a-new-er-solution-to-print-a-custom-report"></a>Új ER-megoldás tervezése egyéni jelentés nyomtatásához

[!include[banner](../includes/banner.md)]

A következő lépések áttekintik, hogy a Rendszergazda, az Elektronikus jelentések fejlesztője vagy az Elektronikus jelentések funkcionális konzulense szerepkörű felhasználók hogyan konfigurálhatják az ER-keretrendszer paramétereit, hogyan tervezhetik meg az új ER-megoldásokhoz szükséges ER-konfigurációkat az adott üzleti tartományok adatainak eléréséhez, illetve hogyan hozhatnak létre egyéni jelentést Microsoft Office-formátumban. Ezeket a lépéseket a **USMF** vállalatban hajthatja végre.

- [ER-keretrendszer konfigurálása](#ConfigureFramework)

    - [ER-paraméterek konfigurálása](#ConfigureParameters)
    - [ER-konfigurációszolgáltató aktiválása](#ActivateProvider)

        - [Az ER-konfigurációszolgáltatók listájának áttekintése](#ReviewProvidersList)
        - [Új ER-konfigurációszolgáltató hozzáadása](#AddProvider)
        - [ER-konfigurációszolgáltató aktiválása](#ActivateAddedProvider)

- [Tartományspecifikus adatmodell kialakítása](#DesignModel)

    - [Új adatmodell-konfiguráció importálása](#ImportDataModel)
    - [Új adatmodell-konfiguráció létrehozása](#DesignDataModel)

        - [Az adatmodell elnevezése](#NameDataModel)
        - [Adatmodell mezőinek hozzáadása](#FieldsEntry)
        - [Az adatmodell kialakításának befejezése](#CompleteDataModel)

- [Modell-leképezés tervezése a konfigurált adatmodellhez](#DesignMapping)

    - [Új modell-leképezési konfiguráció importálása](#ImportModelMapping)
    - [Új modell-leképezési konfiguráció létrehozása](#CreateModelMapping)

        - [Új modell-leképezési összetevő tervezése](#DesignMappingComponent)
        - [Adatforrások hozzáadása alkalmazástáblák eléréséhez](#AddMmDataSource1)
        - [Adatforrások hozzáadása alkalmazásfelsorolások eléréséhez](#AddMmDataSource2)
        - [ER-címkék hozzáadása adott nyelvű jelentés létrehozásához](#AddMmLabels)
        - [Adatforrás hozzáadása a felsorolási értékek és a szöveges érték összehasonlításakor kapott eredmények átalakításához](#AddMmDataSource3)
        - [Adatforrások kötése az adatmodell mezőihez](#AddMmBindings1)
        - [A modell-leképezés kialakításának befejezése](#CompleteModelMapping)

- [Sablon tervezése egyéni jelentésekhez](#DesignReportTemplate)
- [Formátum tervezése](#DesignFormat)

    - [Megtervezett formátumkonfiguráció importálása](#FormatImport)
    - [Új formátumkonfiguráció létrehozása](#FormatCreate)

        - [Jelentéssablon importálása](#ImportReportTemplate)
        - [Formátum konfigurálása](#ConfigureFormat)
        - [Adatkötés definiálása a jelentés címéhez](#DefineFormatBindings)
        - [A modell adatforrásának ellenőrzése](#ReviewModelDataSource)
        - [Formátum-összetevők összekötése az adatforrás mezőivel](#BindFormatElements)

    - [Megtervezett formátum futtatása az ER-ből](#RunFormatFromER)

- [Megtervezett formátum finomhangolása](#TuneFormat)

    - [Formátum módosítása a létrehozott dokumentumok nevének módosításához](#ModifyToChangeName)
    - [Formátum módosítása a kérdések sorrendjének módosításához](#ModifyToOrder)
    - [Módosított formátum futtatása az ER-ből](#RunFormatFromER2)
    - [A formátum kialakításának befejezése](#CompleteFormat)

- [Alkalmazás-összetevők fejlesztése a megtervezett jelentés meghívásához](#DevelopCustomCode)

    - [Forráskód módosítása](#ModifySourceCode)

        - [Adatszerződés-osztály hozzáadása](#DataContractClass)
        - [UI-készítő osztály hozzáadása](#UIBuilderClass)
        - [Adatszolgáltató-osztály hozzáadása](#DataProviderClass)
        - [Címkéket tartalmazó fájlok hozzáadása](#LabelsFile)
        - [Jelentésszolgáltatási osztály hozzáadása](#ServiceClass)
        - [Jelentésvezérlő osztály hozzáadása](#ControllerClass)
        - [Menüelem hozzáadása](#MenuItem)
        - [Menüelem hozzáadása a menükhöz](#Menu)
        - [Visual Studio-projekt készítése](#BuildVSProject)

    - [Formátum futtatása az alkalmazásból](#RunFormatFromApp)

- [Megtervezett ER-megoldás finomhangolása](#TuneSolution)

    - [Modell-hozzárendelés módosítása](#ModifyModelMapping)

        - [Adatforrások hozzáadása adatszerződési objektum eléréséhez](#AddDataSource1)
        - [Adatforrások hozzáadása az ER-formátum leképezési rekordjaihoz való hozzáféréshez](#AddDataSource2)
        - [Adatforrások hozzáadása a futó ER-formátum formátumleképezési rekordjaihoz való hozzáféréshez](#AddDataSource3)
        - [Futó ER-formátum nevének megadása az adatmodellben](#AddBinding)
        - [A modell-leképezés kialakításának befejezése](#CompleteModelMapping2)

    - [Formátum módosítása](#ModifyFormat)

        - [Új formátumelem hozzáadása](#AddFormatElement)
        - [Hozzáadott formátumelem kötése](#BindAddedFormatElement)
        - [A formátum kialakításának befejezése](#CompleteFormat2)

    - [Formátum futtatása az alkalmazásból](#RunFormatFromApp2)
    - [Formátum futtatása az ER-ből](#RunFormatFromER3)
    - [Formátum célhelyének konfigurálása a képernyőn látható előzetes verzióból](#ConfigureDestination)
    - [Formátum futtatása az alkalmazásból PDF-dokumentumként történő előzetes verzió készítéséhez](#RunFormatFromApp3)

- [További erőforrások](#References)

Ebben a példában új ER-megoldást hoz létre a [Kérdőív](../../../human-resources/hr-learning-questionnaires.md) modulhoz. Ezzel az új ER-megoldással jelentést tervezhet úgy, hogy Microsoft Excel-munkalapot használ sablonként. Ezt követően létrehozhatja a **Kérdőív** jelentést Excel- vagy PDF-formátumban, valamint elkészítheti a meglévő SQL Server Reporting Services- (SSRS) jelentéseket. Az új jelentést igény szerint módosíthatja később. Nincs szükség kódolásra.

1. A meglévő jelentés futtatásához lépjen a **Kérdőív** \> **Tervezés** \> **Kérdőívek jelentése** részre.

    ![A Kérdőívek jelentése menüelem kiválasztása a Kérdőív modulban a meglévő SSRS-jelentés futtatásához](./media/er-quick-start1-application-menu-origin.png)

2. A **Kérdőívek jelentése** párbeszédpanelen adja meg a kiválasztási feltételeket. Alkalmazzon egy szűrőt, hogy a jelentés csak a **SBCCrsExam** kérdőívet tartalmazza.

    ![A kiválasztási feltételek megadása a Kérdőívek jelentése párbeszédpanelen](./media/er-quick-start1-ssrs-report-dialog.png)

A következő ábrán az **SBCCrsExam** kérdőívhez SSRS-jelentés létrehozott változata látható.

![Létrehozott SSRS-jelentés](./media/er-quick-start1-ssrs-report.png)

## <a name="configure-the-er-framework"></a><a name="ConfigureFramework"></a>ER-keretrendszer konfigurálása

Elektronikus jelentések fejlesztője szerepkörű felhasználóként konfigurálnia kell a minimálisan szükséges ER-paraméterek készletét, mielőtt új ER-megoldás tervezéséhez kezdené használni az ER-keretrendszert.

### <a name="configure-er-parameters"></a><a name="ConfigureParameters"></a>ER-paraméterek konfigurálása

1. Ugorjon a **Szervezeti adminisztráció** \> **Munkaterületek** \> **Elektronikus jelentés** pontra.
2. Az **Elektronikus jelentéskészítés** munkaterületen kattintson az **Elektronikus jelentések paraméterei** hivatkozására.
3. Az **Elektronikus jelentéskészítési paraméterek** oldalon, az **Általános** lapon a **Tervezői mód engedélyezése** lehetőséget állítsa **Igen** értékre.
4. A **Mellékletek** lapon állítsa be a következő paramétereket:

    - A **Konfigurációk** mezőben állítsa be a **Fájl** értéket az **USMF** vállalathoz.
    - A **Feladatarchívum**, **Ideiglenes**, **Alap** és **Egyebek** mezőkben adja meg a **Fájl** típust.

Az ER-paraméterekkel kapcsolatos további tudnivalókat lásd: [ER-keretrendszer konfigurálása](electronic-reporting-er-configure-parameters.md).

### <a name="activate-an-er-configuration-provider"></a><a name="ActivateProvider"></a>ER-konfigurációszolgáltató aktiválása

Minden ER-konfigurációt egy ER-konfigurációszolgáltató által birtokoltként kell megjelölni. Ennek megfelelően aktiválnia kell egy ER-konfigurációszolgáltatót az **Elektronikus jelentéskészítés** munkaterületen, mielőtt megkezdené az ER-konfigurációk hozzáadását vagy szerkesztését.

> [!NOTE]
> Csak az ER-konfiguráció tulajdonosa szerkesztheti. Éppen ezért aktiválnia kell a megfelelő ER-konfigurációszolgáltatót az **Elektronikus jelentéskészítés** munkaterületen, mielőtt elkezdené az ER-konfigurációk hozzáadását vagy szerkesztését.

#### <a name="review-the-list-of-er-configuration-providers"></a><a name="ReviewProvidersList"></a>Az ER-konfigurációszolgáltatók listájának áttekintése

1. Ugorjon a **Szervezeti adminisztráció** \> **Munkaterületek** \> **Elektronikus jelentés** pontra.
2. Az **Elektronikus jelentéskészítés** munkaterületen, a **Kapcsolódó hivatkozások** szakaszban, válassza a **Konfigurációszolgáltatók** elemet.
3. A **Konfigurációszolgáltatók** oldalon minden konfigurációszolgáltatói rekordnak egyedi neve és URL-címe van. Tekintse át az oldal tartalmát. Ha a már létezik a **Litware, Inc.** (`https://www.litware.com`) rekordja, hagyja ki a következő eljárást: [Új ER-konfigurációszolgáltató hozzáadása](#ActivateProvider).

#### <a name="add-a-new-er-configuration-provider"></a><a name="AddProvider"></a>Új ER-konfigurációszolgáltató hozzáadása

1. A **Konfigurációszolgáltatók** oldalon válassza az **Új** elemet.
2. A **Név** mezőbe írja be a következőt: **Litware, Inc.**.
3. Az **Internetcím** mezőben adja meg a következőt: `https://www.litware.com`.
4. Válassza a **Mentés** lehetőséget.

#### <a name="activate-an-er-configuration-provider"></a><a name="ActivateAddedProvider"></a>ER-konfigurációszolgáltató aktiválása

1. Ugorjon a **Szervezeti adminisztráció** \> **Munkaterületek** \> **Elektronikus jelentés** pontra.
2. Az **Elektronikus jelentés** munkaterületen válassza ki a **Litware, Inc.** konfigurációszolgáltatót.
3. Válassza ki az **Aktív beállítása** elemet.

További információért az ER-konfigurációszolgáltatókkal kapcsolatban tekintse át a [Konfigurációszolgáltatók létrehozása és megjelölése aktívként](tasks/er-configuration-provider-mark-it-active-2016-11.md) eljárást.

## <a name="design-a-domain-specific-data-model"></a><a name="DesignModel"></a>Tartományspecifikus adatmodell kialakítása

Létre kell hoznia egy olyan új ER-konfigurációt, amely tartalmaz egy [adatmodell](general-electronic-reporting.md#data-model-and-model-mapping-components) összetevőt a **Kérdőív** üzleti tartományhoz. Ez az adatmodell lesz az adatforrás, amikor megtervezi az ER-formátumot a **Kérdőív** jelentés létrehozásához.

Az [Új adatmodell-konfiguráció importálása](#ImportDataModel) szakasz lépéseivel importálhatja a szükséges adatmodellt a megadott XML-fájlból. Egy másik megoldás, hogy az [Új adatmodell-konfiguráció létrehozása](#DesignDataModel) szakasz lépéseit követve az alapoktól kezdve tervezi meg az adatmodellt.

### <a name="import-a-new-data-model-configuration"></a><a name="ImportDataModel"></a>Új adatmodell-konfiguráció importálása

1. Töltse le a [Questionnaires model.version.1.xml](https://go.microsoft.com/fwlink/?linkid=851448) fájlt, és mentse a helyi számítógépen.
2. Ugorjon a **Szervezeti adminisztráció** \> **Munkaterületek** \> **Elektronikus jelentés** pontra.
3. Az **Elektronikus jelentéskészítés** munkaterületen válassza ki a **Jelentéskészítési konfiguráció** lehetőséget.
4. A Műveleti ablaktáblában válassza az **Átváltás** \> **Betöltés XML-fájlból** elemet.
5. Kattintson a **Tallózás** elemre, majd keresse meg és válassza ki a **Questionnaires model.version.1.xml** fájlt.
6. A konfiguráció importálásához kattintson az **OK** gombra.

A folytatáshoz ugorja át a következő eljárást: [Új adatmodell-konfiguráció létrehozása](#DesignDataModel).

### <a name="create-a-new-data-model-configuration"></a><a name="DesignDataModel"></a>Új adatmodell-konfiguráció létrehozása

1. Ugorjon a **Szervezeti adminisztráció** \> **Munkaterületek** \> **Elektronikus jelentés** pontra.
2. Az **Elektronikus jelentéskészítés** munkaterületen válassza ki a **Jelentéskészítési konfiguráció** lehetőséget.
3. Válassza a **Konfiguráció létrehozása** lehetőséget.
4. Írja be a legördülő párbeszédpanel **Név** mezőjébe ezt: **Kérdőív modellje**.
5. A konfiguráció létrehozása válassza a **Konfiguráció létrehozása** elemet.

#### <a name="name-the-data-model"></a><a name="NameDataModel"></a>Az adatmodell elnevezése

1. A **Konfigurációk** oldalon, a konfigurációk fastruktúrájában válassza a **Kérdőív modellje** lehetőséget.
2. Válassza a **Tervező** lehetőséget.
3. Az **Adatmodell-tervező** oldal **Általános** gyorslapján írja be a **Név** mezőbe a <a name="DataModeName"></a>**Kérdőívek** szót.

#### <a name="add-new-data-model-fields"></a><a name="FieldsEntry"></a>Új adatmodellmezők hozzáadása

1. Az **Adatmodell-tervező** oldalon válassza az **Új** elemet.
2. Az adatmodell csomópontjainak hozzáadására szolgáló legördülő párbeszédpanelen hajtsa végre az alábbi lépéseket:

    1. Az új csomópont típusaként adja meg a **Modellgyökér** lehetőséget.
    2. A **Név** mezőbe írja be a <a name="RootDefinitionName"></a>**Gyökér** szót.
    3. Új csomópont hozzáadásához kattintson a **Hozzáadás** lehetőségre.

    Ez a gyökérleíró biztosít majd adatokat a **Kérdőív** jelentéshez. Egy adatmodellhez több leíró is tartozhat. Mindegyik leíró meghatározható egy adott ER-jelentésformátumhoz, hogy meg lehessen határozni a jelentés létrehozásához szükséges adatokat.

3. Válassza ismét az **Új** lehetőséget, majd az adatmodell csomópontjainak hozzáadására szolgáló legördülő párbeszédpanelen hajtsa végre az alábbi lépéseket:

    1. Az új csomópont típusaként válassza az **Aktív csomópont gyermeke** lehetőséget.
    2. A **Név** mezőbe írja be a **CompanyName** szót.
    3. A **Cikktípus** mezőben válassza ki a **Karakterlánc** lehetőséget.
    4. Új mező hozzáadásához kattintson a **Hozzáadás** lehetőségre.

    Ez a mező szükséges, hogy át lehessen adni az aktuális vállalat nevét az olyan ER-jelentéseknek, amelyek ezt az adatmodellt használják adatforrásként.

4. Válassza ismét az **Új** lehetőséget, majd az adatmodell csomópontjainak hozzáadására szolgáló legördülő párbeszédpanelen hajtsa végre az alábbi lépéseket:

    1. Az új csomópont típusaként válassza az **Aktív csomópont gyermeke** lehetőséget.
    2. A **Név** mezőbe írja be a **Kérdőív** szót.
    3. A **Cikktípus** mezőben válassza ki a **Rekordlista** lehetőséget.
    4. Új mező hozzáadásához kattintson a **Hozzáadás** lehetőségre.

    Ez a mező adja majd át a kérdőívek listáját az olyan ER-jelentéseknek, amelyek ezt az adatmodellt használják adatforrásként.

5. Válassza ki a **Kérdőív** csomópontot.
6. Hasonló módon adja hozzá a szerkeszthető adatmodell kötelező mezőit, amíg a következő adatmodell-struktúrát nem kapja.

    | Mező elérési útja                                                    | Adattípus   | Mező megnevezése/visszaadott érték |
    |---------------------------------------------------------------|-------------|----------------------------------|
    | Gyökér                                                          |             | A kérdőív adatainak kérésére szolgáló hivatkozási pont. |
    | Root\\CompanyName                                             | Karakterlánc      | Az aktuális vállalat neve. |
    | Root\\ExecutionContext                                        | Rögzítés      | Formátum-végrehajtás részletei. |
    | Root\\ExecutionContext\\FormatName                            | Karakterlánc      | Az éppen futtatott ER-formátum neve. |
    | Root\\Questionnaire                                           | Rekordlista | A kérdőívek listája |
    | Root\\Questionnaire\\Active                                   | Karakterlánc      | Az aktuális kérdőív állapota. |
    | Root\\Questionnaire\\Code                                     | Karakterlánc      | Az aktuális kérdőív kódja. |
    | Root\\Questionnaire\\Description                              | Karakterlánc      | Az aktuális kérdőív leírása. |
    | Root\\Questionnaire\\QuestionnaireType                        | Karakterlánc      | Az aktuális kérdőív típusa. |
    | Root\\Questionnaire\\QuestionOrder                            | Karakterlánc      | Az aktuális kérdőív numerikus sorrendje. |
    | Root\\Questionnaire\\ResultsGroup                             | Rögzítés      | Az aktuális kérdőív eredményparaméterei. |
    | Root\\Questionnaire\\ResultsGroup\\Code                       | Karakterlánc      | Az aktuális eredménycsoport azonosítókódja. |
    | Root\\Questionnaire\\ResultsGroup\\Description                | Karakterlánc      | Az aktuális eredménycsoport leírása. |
    | Root\\Questionnaire\\ResultsGroup\\MaxNumberOfPoints          | Valós        | A maximálisan megszerezhető pontok száma. |
    | Root\\Questionnaire\\Question                                 | Rekordlista | Az aktuális kérdőív kérdéseinek listája. |
    | Root\\Questionnaire\\Question\\CollectionSequenceNumber       | Egész     | Az aktuális válaszok gyűjteményének sorszáma. |
    | Root\\Questionnaire\\Question\\Id                             | Karakterlánc      | Az aktuális kérdés azonosítókódja. |
    | Root\\Questionnaire\\Question\\MustBeCompleted                | Karakterlánc      | Jelölő, amely azt jelzi, hogy az aktuális kérdést meg kell-e válaszolni. |
    | Root\\Questionnaire\\Question\\PrimaryQuestion                | Karakterlánc      | Jelölő, amely azt jelzi, hogy az aktuális kérdés elsődleges-e. |
    | Root\\Questionnaire\\Question\\SequenceNumber                 | Egész     | Az aktuális kérdés sorszáma. |
    | Root\\Questionnaire\\Question\\Text                           | Karakterlánc      | Az aktuális kérdés szövege. |
    | Root\\Questionnaire\\Question\\Answer                         | Rekordlista | Az aktuális kérdés válaszainak listája. |
    | Root\\Questionnaire\\Question\\Answer\\CorrectAnswer          | Karakterlánc      | Jelölő, amely azt jelzi, hogy az aktuális válasz helyes-e. |
    | Root\\Questionnaire\\Question\\Answer\\Points                 | Valós        | Az aktuális válasz kiválasztása alkalmával kapott pontok. |
    | Root\\Questionnaire\\Question\\Answer\\SequenceNumber         | Egész     | Az aktuális válasz sorszáma. |
    | Root\\Questionnaire\\Question\\Answer\\Text                   | Karakterlánc      | Az aktuális válasz szövege. |

    A következő ábra a befejezett szerkeszthető adatmodellt mutatja az **Adatmodell-tervező** oldalon.

    ![Konfigurált adatmodell az ER adatmodell-tervezőjében](./media/er-quick-start1-model2.png)

7. Mentse el a módosításokat.
8. Zárja be az **Adatmodell-tervező** oldalt.

#### <a name="complete-the-design-of-the-data-model"></a><a name="CompleteDataModel"></a>Az adatmodell kialakításának befejezése

1. Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**.
2. A **Konfigurációk** oldalon, a konfigurációk fastruktúrájában válassza a **Kérdőív modellje** lehetőséget.
3. A **Verziók** gyorslapon válassza ki azt a konfigurációverziót, amelynek az állapota **Piszkozat**.
4. Válassza az **Állapot módosítása** \> **Teljes** lehetőséget.

A konfiguráció 1. verziójának állapota **Piszkozatról** **Befejezett** értékre módosul. Az 1. verzió a későbbiekben már nem módosítható. Ez a verzió tartalmazza a konfigurált adatmodellt, és a többi ER-konfiguráció alapjaként használható. A konfiguráció 2. változata létrejön **Piszkozat** állapottal. Ezt a verziót a **Kérdőív** adatmodell módosításával szerkesztheti.

![A szerkeszthető ER-konfiguráció verziói a Konfigurációk oldalon](./media/er-quick-start1-model-configuration.png)

További információ az ER-konfigurációk verziószámozásáról: [Elektronikus jelentéskészítés (ER) áttekintése](general-electronic-reporting.md#component-versioning).

> [!NOTE]
> A konfigurált adatmodell a **Kérdőív** üzleti terület absztrakt ábrázolása, és nem tartalmaz konkrét, Microsoft Dynamics 365 Finance-specifikus összetevőket.

## <a name="design-a-model-mapping-for-the-configured-data-model"></a><a name="DesignMapping"></a>Modell-leképezés tervezése a konfigurált adatmodellhez

Elektronikus jelentések fejlesztője szerepkörű felhasználóként létre kell hoznia egy olyan új ER-konfigurációt, amely [modell-leképezési](general-electronic-reporting.md#data-model-and-model-mapping-components) összetevőt tartalmaz a **Kérdőív** adatmodellhez. Mivel ez az összetevő a Finance konfigurált adatmodelljét valósítja, Finance-specifikus. A modell-hozzárendelési összetevőt úgy kell konfigurálni, hogy megadja azokat az alkalmazásobjektumokat, amelyeket a futásidőben használni kell a konfigurált adatmodell alkalmazásadatokkal való feltöltéséhez. Ennek a feladatnak a végrehajtásához ismernie kell a **Kérdőív** üzleti terület adatszerkezetét megvalósítási részleteit a Finance rendszerben.

Az alábbi [Új modell-leképezési konfiguráció importálása](#ImportModelMapping) szakasz lépéseivel importálhatja a szükséges modell-leképezési konfigurációt a megadott XML-fájlból. Egy másik megoldás, hogy az [Új modell-leképezés létrehozása](#CreateModelMapping) szakasz lépéseit követve az alapoktól kezdve tervezi meg a modell-leképezést.

### <a name="import-a-new-model-mapping-configuration"></a><a name="ImportModelMapping"></a>Új modell-leképezési konfiguráció importálása

1. Töltse le a [Questionnaires mapping.version.1.1.xml](https://go.microsoft.com/fwlink/?linkid=851448) fájlt, és mentse a helyi számítógépen.
2. Ugorjon a **Szervezeti adminisztráció** \> **Munkaterületek** \> **Elektronikus jelentés** pontra.
3. Az **Elektronikus jelentéskészítés** munkaterületen válassza ki a **Jelentéskészítési konfiguráció** lehetőséget.
4. A Műveleti ablaktáblában válassza az **Átváltás** \> **Betöltés XML-fájlból** elemet.
5. Kattintson a **Tallózás** elemre, majd keresse meg és válassza ki a **Questionnaires mapping.version.1.1.xml** fájlt.
6. A konfiguráció importálásához kattintson az **OK** gombra.

A folytatáshoz ugorja át a következő eljárást: [Új modell-leképezési konfiguráció létrehozása](#CreateModelMapping).

### <a name="create-a-new-model-mapping-configuration"></a><a name="CreateModelMapping"></a>Új modell-leképezési konfiguráció létrehozása

1. Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**.
2. A **Konfigurációk** oldalon, a konfigurációk fastruktúrájában válassza a **Kérdőív modellje** lehetőséget.
3. Válassza a **Konfiguráció létrehozása** lehetőséget.
4. A legördülő párbeszédpanelen hajtsa végre a következő lépéseket:

    1. Az **Új** mezőben válassza az **Adatmodell kérdőívein alapuló modell-leképezés** lehetőséget.
    2. A **Név** mezőbe írja be **Kérdőív leképezése** szöveget.
    3. Az **Adatmodell definíciója** mezőben válassza ki a **Gyökér** definíciót.
    4. A konfiguráció létrehozása válassza a **Konfiguráció létrehozása** elemet.

#### <a name="design-a-new-model-mapping-component"></a><a name="DesignMappingComponent"></a>Új modell-leképezési összetevő tervezése

1. A **Konfigurációk** oldalon, a konfigurációk fastruktúrájában válassza a **Kérdőív leképezése** lehetőséget.
2. Válassza ki a **Tervezőt** a leképezések listájának megnyitásához.
3. Válassza azt a **Kérdőívek leképezése** leképezést, amelyet a rendszer automatikusan hozzáadott a **Gyökér** definícióhoz.
4. A kiválasztott hozzárendelés konfigurálásához válassza ki a **Tervező** lehetőséget.

A rendszer automatikusan hozzáad egy új leképezést a **Gyökér** definícióhoz. Ez a leképezés a **Modellhez** irányt használja. Ezért ez a hozzárendelés használható az adatmodell szükséges adatokkal való feltöltéséhez.

#### <a name="add-data-sources-to-access-application-tables"></a><a name="AddMmDataSource1"></a>Adatforrások hozzáadása alkalmazástáblák eléréséhez

Az adatforrásokat konfigurálni kell, hogy elérjék a kérdőív részleteit tartalmazó alkalmazástáblákat.

1. A **Modell-leképezés tervező** oldal **Adatforrástípusok** paneljén válassza a **Dynamics 365 for Operations\\Táblarekordok** lehetőséget.
2. Adjon hozzá egy olyan új adatforrást, amely a KMCollection tábla elérésére szolgál. A táblában minden rekord egyetlen kérdőívhez tartozik:

    1. Az **Adatforrás** panelen válassza a **Gyökér hozzáadása** elemet.
    2. A párbeszédpanel **Név** mezőjébe írja be a **Kérdőív** kifejezést.
    3. A **Tábla** mezőbe írja be a **KMCollection** szót.
    4. Állítsa a **Lekérdezés kérése** beállítást **Igen** értékre. Ezt követően futásidőben ehhez a táblához megadhatja a [szűrési](../../fin-ops/get-started/advanced-filtering-query-options.md) beállításokat a rendszerlekérdezés párbeszédpanelen.
    5. Az új adatforrás hozzáadásához kattintson az **OK** gombra.

3. Az **Adatforrástípusok** panelen válassza a **Dynamics 365 for Operations\\Táblarekordok** lehetőséget.
4. Adjon hozzá egy olyan új adatforrást, amely a KMQuestion tábla elérésére szolgál. A táblában minden rekord a kérdőív egyetlen kérdéséhez tartozik:

    1. Az **Adatforrás** panelen válassza a **Gyökér hozzáadása** elemet.
    2. A párbeszédpanel **Név** mezőjébe írja be a **Kérdés** kifejezést.
    3. A **Tábla** mezőbe írja be a **KMQuestion** szót.
    4. Az új adatforrás hozzáadásához kattintson az **OK** gombra.

5. Az **Adatforrástípusok** panelen válassza a **Dynamics 365 for Operations\\Táblarekordok** lehetőséget.
6. Adjon hozzá egy olyan új adatforrást, amely a KMAnswer tábla elérésére szolgál. A táblában minden rekord a kérdőív adott kérdésének egyetlen válaszához tartozik:

    1. Az **Adatforrás** panelen válassza a **Gyökér hozzáadása** elemet.
    2. A **Név** mezőbe írja be a **Válasz** szót.
    3. A **Tábla** mezőbe írja be a **KMAnswer** szót.
    4. Az új adatforrás hozzáadásához kattintson az **OK** gombra.

7. Az **Adatforrástípusok** panelen válassza a **Függvények\\Számított mező** lehetőséget.
8. Adjon hozzá egy olyan új számított mezőt, amelyet a KMQuestionResultGroup tábla rekordjainak elérésére fog használni a szülő KMCollection tábla összes rekordjából:

    1. Az **Adatforrások** panelen válassza a **Kérdőív** elemet.
    2. Válassza a **Hozzáadás** lehetőséget.
    3. A párbeszédpanel **Név** mezőjébe írja be a következőt: **\$ResultGroup**.
    4. Válassza a **Képlet szerkesztése** elemet.
    5. Az [ER-receptúraszerkesztő](general-electronic-reporting-formula-designer.md) **Receptúra** mezőjében adja meg a **FIRSTORNULL(\@.'\<Relations'.KMQuestionResultGroup)** képletet a KMCollection és a KMQuestionResultGroup tábla közötti egy-a-többhöz kapcsolat [elérési útjának](er-formula-language.md#paths) használatához.
    6. Válassza a **Mentés** gombot, majd zárja be a receptúraszerkesztőt.
    7. Az új számított mező hozzáadásához kattintson az **OK** gombra.

9. Az **Adatforrástípusok** panelen válassza a **Függvények\\Számított mező** lehetőséget.
10. Adjon hozzá egy olyan új számított mezőt, amelyet a KMQuestion tábla kérdésrekordjainak elérésére fog használni a szülő KMCollectionQuestion tábla összes rekordjából:

    1. Az **Adatforrások** panelen válassza a **Kérdőív** elemet.
    2. Bontsa ki a KMCollection tábla egy-a-többhöz kapcsolatait tartalmazó **\<Kapcsolatok** csomópontot.
    3. Válassza ki a kapcsolódó **KMCollectionQuestion** táblát, majd a **Hozzáadás** elemet.
    4. A párbeszédpanel **Név** mezőjébe írja be a **\$Kérdés** kifejezést.
    5. Válassza a **Képlet szerkesztése** elemet.
    6. A receptúraszerkesztő **Receptúra** mezőjébe írja be a **FIRSTORNULL (FILTER(Question, Question.kmQuestionId = \@.kmQuestionId))** képletet a megfelelő kérdésrekordok KMQuestion táblából való visszaadásához.
    7. Válassza a **Mentés** gombot, majd zárja be a receptúraszerkesztőt.
    8. Az új számított mező hozzáadásához kattintson az **OK** gombra.

11. Az **Adatforrástípusok** panelen válassza a **Függvények\\Számított mező** lehetőséget.
12. Adjon hozzá egy olyan új számított mezőt, amelyet a KMAnswer tábla válaszrekordjainak elérésére fog használni a szülő KMQuestion tábla összes rekordjából:

    1. Az **Adatforrások** panelen válassza a **Questionnaire.\<Relations.KMCollectionQuestion.\$Question**, majd a **Hozzáadás** lehetőséget.
    2. A párbeszédpanel **Név** mezőjébe írja be a **\$Válasz** kifejezést.
    3. Válassza a **Képlet szerkesztése** elemet.
    4. A receptúraszerkesztő **Receptúra** mezőjébe írja be a **FILTER (Answer, Answer.kmAnswerCollectionId = \@.kmAnswerCollectionId)** képletet a megfelelő válaszrekordok KMAnswer táblából való visszaadásához.
    5. Válassza a **Mentés** gombot, majd zárja be a receptúraszerkesztőt.
    6. Az új számított mező hozzáadásához kattintson az **OK** gombra.

13. Az **Adatforrástípusok** panelen válassza a **Dynamics 365 for Operations\\Tábla** lehetőséget.
14. Adjon hozzá egy olyan új adatforrást, amely a CompanyInfo tábla metódusaihoz való hozzáférésre szolgál majd. Ügyeljen arra, hogy a tábla **find()** metódusa olyan rekordot ad vissza, amely az aktuális Finance-példánynak azt a vállalatát jelöli, amelynek a környezetében megtörtént ennek a hozzárendelésnek a meghívása.

    1. Az **Adatforrás** panelen válassza a **Gyökér hozzáadása** elemet.
    2. A párbeszédpanel **Név** mezőjébe írja be a **CompanyInfo** kifejezést.
    3. A **Tábla** mezőbe írja be a **CompanyInfo** szót.
    4. Az új adatforrás hozzáadásához kattintson az **OK** gombra.

#### <a name="add-data-sources-to-access-application-enumerations"></a><a name="AddMmDataSource2"></a>Adatforrások hozzáadása alkalmazásfelsorolások eléréséhez

Az alkalmazásfelsorolások eléréséhez és az alkalmazásfelsorolások értékének az alkalmazástáblákban lévő **Felsorolás** típusú mezők értékének való összevetéséhez adatforrásokat kell konfigurálni. Az adatmodell megfelelő mezőinek kitöltéséhez az összehasonlítás eredményét kell használni.

1. A **Modell-leképezés tervező** oldal **Adatforrástípusok** paneljén válassza a **Dynamics 365 for Operations\\Felsorolás** lehetőséget.
2. Adjon hozzá egy olyan új adatforrást, amely az **EnumAppNoYes** felsorolás értékeihez való hozzáférésre szolgál majd:

    1. Az **Adatforrás** panelen válassza a **Gyökér hozzáadása** elemet.
    2. A párbeszédpanel **Név** mezőjébe írja be az **EnumAppNoYes** kifejezést.
    3. A **Felsorolás** mezőbe írja be a **NoYes** kifejezést.
    4. Az új adatforrás hozzáadásához kattintson az **OK** gombra.

3. Az **Adatforrástípusok** panelen válassza a **Dynamics 365 for Operations\\Felsorolás** lehetőséget.
4. Adjon hozzá egy olyan új adatforrást, amely a **KMCollectionQuestionMode** felsorolás értékeihez való hozzáférésre szolgál majd:

    1. Az **Adatforrás** panelen válassza a **Gyökér hozzáadása** elemet.
    2. A párbeszédpanel **Név** mezőjébe írja be az **EnumAppQuestionOrder** kifejezést.
    3. A **Felsorolás** mezőbe írja be a **KMCollectionQuestionMode** kifejezést.
    4. Az új adatforrás hozzáadásához kattintson az **OK** gombra.

#### <a name="add-er-labels-to-generate-a-report-in-a-specified-language"></a><a name="AddMmLabels"></a>ER-címkék hozzáadása adott nyelvű jelentés létrehozásához

Ha bizonyos adatforrásokat úgy szeretne konfigurálni, hogy olyan értékeket adjanak vissza, amelyek a modell-leképezés hívásának kontextusában meghatározott nyelvtől függenek, hozzáadhat ER-címkéket.

1. A **Modell-hozzárendelési tervező** oldal **Adatforrások** paneljén válassza a **Válasz**, majd a **Szerkesztés** lehetőséget.
2. Aktiválja a **Címke** mezőt.
3. Válassza a **Fordítás** elemet.
4. A **Szöveg fordítása** párbeszédpanelen hajtsa végre a következő lépéseket:

    1. A **Címkeazonosító** mezőbe írja a **PositiveAnswer** értéket.
    2. A **Szöveg az alapértelmezett nyelven** mezőben adja meg az **Igen** értéket.
    3. Válassza a **Fordítás** elemet.
    4. A **Címkeazonosító** mezőbe írja a **NegativeAnswer** értéket.
    5. A **Szöveg az alapértelmezett nyelven** mezőben adja meg a **Nem** értéket.
    6. Válassza a **Fordítás** elemet.

5. Zárja be a **Szöveg fordítása** párbeszédpanelt.
6. Válassza a **Mégse** lehetőséget.

![ER-címkék hozzáadása szerkeszthető modell-leképezéshez](./media/er-quick-start1-adding-labels.png)

Eddig csak az alapértelmezett nyelvhez vett fel ER-címkéket. További információ az ER-címkék más nyelvekre való lefordításáról: [Többnyelvű jelentések tervezése](er-design-multilingual-reports.md).

#### <a name="add-a-data-source-to-transform-the-results-of-comparing-enumeration-values-to-a-text-value"></a><a name="AddMmDataSource3"></a>Adatforrás hozzáadása a felsorolási értékek és a szöveges érték összehasonlításakor kapott eredmények átalakításához

Mivel a különböző forrásokhoz többször át kell alakítani a felsorolás értékeinek és a szövegértékek összevetése során kapott eredményeket, célszerű ezt a logikát egyetlen adatforrásként konfigurálni. Ha azonban ezt az adatforrást újra fel szeretné használni, akkor paraméteres adatforrásként kell konfigurálnia. További információ [A Számított mező típusának ER-adatforrásaihoz tartozó paraméteres hívások támogatása](er-calculated-field-type.md).

1. A **Modell-leképezés tervező** oldal **Adatforrástípusok** paneljén válassza az **Általános\\Üres tároló** lehetőséget.
2. Adja hozzá egy új tároló adatforrását:

    1. Az **Adatforrás** panelen válassza a **Gyökér hozzáadása** elemet.
    2. A párbeszédpanel **Név** mezőjébe írja be a **Segítő** kifejezést.
    3. Az új tároló adatforrás hozzáadásához kattintson az **OK** gombra.

3. Az **Adatforrástípusok** panelen válassza a **Függvények\\Számított mező** lehetőséget.
4. Adjon hozzá új adatforrást:

    1. Válassza az **Adatforrások** ablaktábla **Segítő** elemét.
    2. Válassza a **Hozzáadás** lehetőséget.
    3. A párbeszédpanel **Név** mezőjébe írja be a **NoYesEnumToString** kifejezést.
    4. Válassza a **Képlet szerkesztése** elemet.
    5. A receptúraszerkesztőben válassza a **Paraméterek** lehetőséget.
    6. A konfigurált kifejezés paramétereinek megadásához kövesse az alábbi lépéseket:

        1. Válassza az **Új** lehetőséget.
        2. A párbeszédpanel **Név** mezőjébe írja be az **Argumentum** kifejezést.
        3. A **Típus** mezőben válassza ki a **Logikai** adattípust.
        4. Válassza ki az **OK** lehetőséget.

    7. A **Receptúra** mezőbe írja be az **IF (Argument = true, \@"GER\_LABEL:PositiveAnswer", \@"GER\_LABEL:NegativeAnswer")** képletet a megfelelő ER-címke szövegének visszaadásához. Ez a végrehajtási környezet nyelvétől, illetve a megadott paraméter értékétől függ.
    8. Válassza a **Mentés** gombot, majd zárja be a receptúraszerkesztőt.
    9. Az új adatforrás hozzáadásához kattintson az **OK** gombra.

![Konfigurált modell-leképezés az ER modell-leképezésének tervezőjében](./media/er-quick-start1-added-data-sources.png)

#### <a name="bind-data-sources-to-data-model-fields"></a><a name="AddMmBindings1"></a>Adatforrások kötése az adatmodell mezőihez

Ha meg szeretné adni, hogy az adatmodell hogyan legyen feltöltve az alkalmazás adataival, akkor az adatmodell mezőihez kell kötnie a konfigurált adatforrásokat.

1. A **Modell-leképezés tervező** oldal **Adatmodell** paneljén válassza a **CompanyName** lehetőséget.
2. Az **Adatforrások** panelen bontsa ki a **CompanyInfo** részt, majd kövesse az alábbi lépéseket:

    1. Bontsa ki a **CompanyInfo.find()** csomópontot, amely a CompanyInfo tábla **find()** metódusát jelzi.
    2. Válassza ki a **CompanyInfo.find().Name** lehetőséget.
    3. Annak a vállalatnak a nevének a kitöltéséhez, amelynek a környezetében meg szeretné hívni a konfigurált modell-leképezést a futásidőben, válassza a **Kötés** lehetőséget.

3. Az **Adatmodell** panelen válassza a **Kérdőív** elemet.
4. Az **Adatforrások** panelen válassza a **Kérdőív** lehetőséget, majd a kérdőív rekordjainak kitöltéséhez válassza a **Kötés** lehetőséget.
5. Az **Adatmodell** panelen bontsa ki a **Kérdőív** részt, majd kövesse az alábbi lépéseket:

    1. Az **Adatmodell** panelen válassza az **Aktív** elemet.
    2. Az **Adatmodell** panelen válassza a **Szerkesztés** elemet.
    3. A **Receptúra** mezőbe írja be a **Helper.NoYesEnumToString (\@.Active = EnumAppNoYes.Yes)** képletet a felsorolási értékek összehasonlításának szöveg- és nyelvfüggő eredményeinek kitöltéséhez.

6. Az alábbi eredmény eléréséig folytassa az adatforrások adatmodell-mezőkhöz kötését ugyanezen a módon.

    | Mező elérési útja                                              | Adattípus   | Művelet | Kötési kifejezés |
    |---------------------------------------------------------|-------------|--------|--------------------|
    | CompanyName                                             | Karakterlánc      | Kötés   | CompanyInfo.'find()'.Name |
    | Kérdőív                                           | Rekordlista | Kötés   | Kérdőív |
    | Questionnaire\\Active                                   | Karakterlánc      | Szerkesztés   | Helper.NoYesEnumToString(\@.active = EnumAppNoYes.Yes) |
    | Questionnaire\\Code                                     | Karakterlánc      | Kötés   | \@.kmCollectionId |
    | Questionnaire\\Description                              | Karakterlánc      | Kötés   | \@.Description |
    | Questionnaire\\QuestionnaireType                        | Karakterlánc      | Kötés   | \@.'&gt;Relations'.kmCollectionTypeId.Description |
    | Questionnaire\\QuestionOrder                            | Karakterlánc      | Szerkesztés   | CASE (\@.questionMode,<br>EnumAppQuestionOrder.Conditional, "Feltételes",<br>EnumAppQuestionOrder.Random, "Véletlenszerű (százalékos arány a kérdőívben)",<br>EnumAppQuestionOrder.RandomGroup, "Véletlenszerű (százalékos arány az eredménycsoportokban)",<br>EnumAppQuestionOrder.Sequence, "Egymás utáni",<br>"") |
    | Questionnaire\\ResultsGroup                             | Rögzítés      |        | |
    | Questionnaire\\ResultsGroup\\Code                       | Karakterlánc      | Kötés   | \@.'\$ResultGroup'.kmQuestionResultGroupId |
    | Questionnaire\\ResultsGroup\\Description                | Karakterlánc      | Kötés   | \@.'\$ResultGroup'.description |
    | Questionnaire\\ResultsGroup\\MaxNumberOfPoints          | Valós        | Kötés   | \@.'\$ResultGroup'.maxPoint |
    | Questionnaire\\Question                                 | Rekordlista | Kötés   | \@.'&lt;Relations'.KMCollectionQuestion |
    | Questionnaire\\Question\\CollectionSequenceNumber       | Egész     | Kötés   | \@.answerCollectionSequenceNumber |
    | Questionnaire\\Question\\Id                             | Karakterlánc      | Kötés   | \@.kmQuestionId |
    | Questionnaire\\Question\\MustBeCompleted                | Karakterlánc      | Szerkesztés   | Helper.NoYesEnumToString(\@.mandatory = EnumAppNoYes.Yes) |
    | Questionnaire\\Question\\PrimaryQuestion                | Karakterlánc      | Kötés   | \@.parentQuestionId |
    | Questionnaire\\Question\\SequenceNumber                 | Egész     | Kötés   | \@.SequenceNumber |
    | Questionnaire\\Question\\Text                           | Karakterlánc      | Kötés   | \@.'\$Question'.text |
    | Questionnaire\\Question\\Answer                         | Rekordlista | Kötés   | \@.'\$Question'.'\$Answer' |
    | Questionnaire\\Question\\Answer\\CorrectAnswer          | Karakterlánc      | Szerkesztés   | Helper.NoYesEnumToString(\@.correctAnswer = EnumAppNoYes.Yes) |
    | Questionnaire\\Question\\Answer\\Points                 | Valós        | Kötés   | \@.point |
    | Questionnaire\\Question\\Answer\\SequenceNumber         | Egész     | Kötés   | \@.sequenceNumber |
    | Questionnaire\\Question\\Answer\\Text                   | Karakterlánc      | Kötés   | \@.text |

    A következő ábra a **Modell-leképezés tervező** oldal konfigurált modell-leképezésének végleges állapotát mutatja.

    ![Teljesen konfigurált modell-leképezés az ER modell-leképezésének tervezőjében](./media/er-quick-start1-mapping2.png)

7. Mentse el a módosításokat.
8. Zárja be a **Modell-hozzárendelési tervező** lapot.

#### <a name="complete-the-design-of-the-model-mapping"></a><a name="CompleteModelMapping"></a>A modell-leképezés kialakításának befejezése

1. Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**.
2. A **Konfigurációk** oldalon, a konfigurációk fastruktúrájában válassza a **Kérdőív leképezése** lehetőséget.
3. A **Verziók** gyorslapon válassza ki azt a konfigurációverziót, amelynek az állapota **Piszkozat**.
4. Válassza az **Állapot módosítása** \> **Teljes** lehetőséget.

A konfiguráció 1.1. verziójának állapota **Piszkozatról** **Befejezett** értékre módosul. Az 1.1. verzió a későbbiekben már nem módosítható. Ez a verzió tartalmazza a konfigurált modell-leképezést, és a többi ER-konfiguráció alapjaként használható. A konfiguráció 1.2. változata létrejön **Piszkozat** állapottal. Ezt a verziót a **Kérdőív leképezése** konfiguráció módosításával szerkesztheti.

![A szerkeszthető ER-konfiguráció verziói a Konfigurációk oldalon](./media/er-quick-start1-mapping-configuration.png)

> [!NOTE]
> A konfigurált modell-leképezés a **Kérdőív** üzleti területet képviselő absztrakt adatmodell Finance-specifikus megvalósítása.

## <a name="design-a-template-for-a-custom-report"></a><a name="DesignReportTemplate"></a>Sablon tervezése egyéni jelentésekhez

Az ER keretrendszer előre definiált sablonok használatával készít jelentéseket Microsoft Office-formátumban (Excel-munkafüzetek vagy Word-dokumentumok). A szükséges jelentés létrehozása során a program a konfigurált adatfolyamnak megfelelően kitölti a szükséges adatokkal a sablont. Ennek megfelelően először egy sablont kell terveznie a saját egyéni jelentéséhez. Ezt a sablont Excel-munkafüzetként kell megtervezni; a szerkezet képezi le az egyéni jelentés elrendezését. Minden olyan Excel-tételt meg kell neveznie, amelyet fel szeretne tölteni a szükséges adatokkal.

1. Töltse le a [Questionnaires report template.xslx](https://go.microsoft.com/fwlink/?linkid=851448) fájlt, és mentse a helyi számítógépen.
2. Nyissa meg a fájlt az Excel programban, és tekintse át a munkafüzet struktúráját.

Ahogy a következő ábrán látható, a letöltött sablon úgy lett kialakítva, hogy olyan konkrét kérdőíveket lehessen vele kinyomtatni, amelyek tartalmazzák a kérdőív kérdéseit és a megfelelő válaszokat.

![Excel-sablon a megadott kérdőívek nyomtatásához](./media/er-quick-start1-template-layout.png)

A sablonhoz Excel-neveket adtunk a kérdőív részleteinek kitöltéséhez. Az Excel-neveket a Névkezelővel ellenőrizheti.

![A megadott Excel-sablonban lévő Excel-nevek ellenőrzése a Névkezelővel](./media/er-quick-start1-template-names.png)

A jelentés címkéit angol nyelvű rögzített szövegként adtuk hozzá. A jelentés címkéit olyan új Excel-nevekre cserélheti, amelyek az ER-formátum [címkéivel](#AddMmLabels) töltik ki nyelvtől függő szöveggel a címkéket (ahogy a konfigurált modell-leképezés nyelvtől függő kifejezései esetében is tette). Ebben az esetben az ER-címkéket szerkeszthető ER-formátumban kell megadni.

A következő ábrán látható egyéni jelentés fejléce úgy lett megadva, hogy az Excel számára engedélyezze a lapozást.

![Egyéni jelentés fejléce a megadott Excel-sablonban](./media/er-quick-start1-template-header.png)

## <a name="design-a-format"></a><a name="DesignFormat"></a>Formátum tervezése

Elektronikus jelentéskészítési funkció tanácsadója szerepkörű felhasználóként Önnek kell olyan új ER-konfigurációt létrehoznia, amely tartalmaz [formátum](general-electronic-reporting.md#FormatComponentOutbound) összetevőt. A formátum összetevőt úgy kell konfigurálni, hogy megadhatja, hogy a program milyen módon töltse ki a futásidőben a jelentés sablonját a szükséges adatokkal.

A [Megtervezett formátumkonfiguráció importálása](#FormatImport) szakasz lépéseivel importálhatja a szükséges formátumot a megadott XML-fájlból. Egy másik megoldás, hogy az [Új formátumkonfiguráció létrehozása](#FormatCreate) szakasz lépéseit követve az alapoktól kezdve tervezi meg a formátumot.

### <a name="import-a-designed-format-configuration"></a><a name="FormatImport"></a>Megtervezett formátumkonfiguráció importálása

1. Töltse le a [Questionnaires format.version.1.1.xml](https://go.microsoft.com/fwlink/?linkid=851448) fájlt, és mentse a helyi számítógépen.
2. Ugorjon a **Szervezeti adminisztráció** \> **Munkaterületek** \> **Elektronikus jelentés** pontra.
3. Az **Elektronikus jelentéskészítés** munkaterületen válassza ki a **Jelentéskészítési konfiguráció** lehetőséget.
4. A Művelet ablaktáblában válassza az **Átváltás** \> **Betöltés XML-fájlból** elemet.
5. Kattintson a **Tallózás** elemre, majd keresse meg és válassza ki a **Questionnaires format.version.1.1.xml** fájlt.
6. A konfiguráció importálásához kattintson az **OK** gombra.

A folytatáshoz ugorja át a következő eljárást: [Új formátumkonfiguráció létrehozása](#FormatCreate).

### <a name="create-a-new-format-configuration"></a><a name="FormatCreate"></a>Új formátumkonfiguráció létrehozása
 
1. Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**.
2. A **Konfigurációk** oldalon, a konfigurációk fastruktúrájában válassza a **Kérdőív modellje** lehetőséget.
3. Válassza a **Konfiguráció létrehozása** lehetőséget.
4. A legördülő párbeszédpanelen hajtsa végre a következő lépéseket:

    1. Az **Új** mezőben válassza az **Adatmodell kérdőívein alapuló formátum** lehetőséget.
    2. A **Név** mezőbe írja be a **Jelentés a kérdőívről** szöveget.
    3. Az **Adatmodell-verzió** mezőben válassza az **1** értéket.

        > [!NOTE]
        > - Ha kiválasztja az alap adatmodell egy adott verzióját, akkor az adatmodell megfelelő verziójának struktúrája jelenik meg mint a létrehozott formátumú **Modell** adatforrás szerkezete.
        > - Ez a mező üresen maradhat. Ebben az esetben az adatmodell **Piszkozat** verziójának a szerkezete jelenik meg mint a létrehozott formátumú **Modell** adatforrás szerkezete. Ezután a modell módosítható, és a módosítások azonnal megtekinthetők az Ön által használt formátumban. Ez a módszer hatékonyabbá teheti az ER-megoldás kialakítását, amikor az adatmodell, a modell-leképezés és a formátum konfigurálása egyidejűleg történik.
        > - Ha az alap adatmodelljéből egy adott verziót választja ki, akkor később, amikor szerkeszteni kezd egy formátumot, válthat a **Piszkozat** verzió használatára.

    4. Az **Adatmodell definíciója** mezőben válassza ki a **Gyökér** definíciót.

5. A konfiguráció létrehozása válassza a **Konfiguráció létrehozása** elemet.

#### <a name="import-a-report-template"></a><a name="ImportReportTemplate"></a>Jelentéssablon importálása

1. A **Konfigurációk** oldalon, a konfigurációk fastruktúrájában válassza a **Jelentés a kérdőívről** lehetőséget.
2. Egy egyéni formátum konfigurálásához válassza ki a **Tervező** lehetőséget.
3. A **Formátumtervező** oldal Művelet Paneljén válassza az **Importálás** \> **Importálás a Microsoft Excel programból** lehetőséget.
4. A párbeszédpanelen hajtsa végre a következő lépéseket:

    1. Válassza a **Sablon hozzáadása** lehetőséget.
    2. Keresse meg és válassza ki a helyileg mentett **Questionnaires report template.xslx** fájlt, és válassza a **Megnyitás** lehetőséget.
    3. A sablon importálásához kattintson az **OK** gombra.

    ![Jelentéssablon importálása](./media/er-quick-start1-template-import.png)

Az **Excel\\File** formátumelemet a rendszer automatikusan hozzáadja gyökérelemként a szerkeszthető formátumhoz. Ezenkívül vagy az **Excel\\Range**, vagy a **Excel\\Cell** formátumelemet automatikusan hozzáadja az importált sablon valamennyi felismert Excel-nevéhez. A **Sztring** elembe beágyazott **Excel\\Header** formátumot a rendszer automatikusan hozzáadja, hogy lehessen látni az importált sablon fejlécbeállításait.

![Formátumstruktúra, amely tartalmazza az automatikusan hozzáadott elemeket az ER-művelet tervezőjében](./media/er-quick-start1-template-import2.png)

#### <a name="configure-a-format"></a><a name="ConfigureFormat"></a>Formátum konfigurálása

1. A **Formátumtervező** oldal formátumfájában válassza ki az **Excel** gyökérelemet.
2. Az oldal jobb oldalán lévő **Formátum** lap **Név** mezőjébe írja be a <a name="AddFormatRootElement"></a>**Jelentés** kifejezést.
3. A **Nyelvi preferencia** mezőben válassza ki a **Felhasználói preferencia** lehetőséget a jelentés felhasználó által preferált nyelven történő futtatásához.
4. A **Kulturális preferencia** mezőben válassza ki a **Felhasználói preferencia** lehetőséget a jelentés felhasználó által preferált kultúra használatával történő futtatásához.

    További információ a nyelvi és kulturális környezet ER-folyamathoz történő megadásáról: [Többnyelvű jelentések tervezése](er-design-multilingual-reports.md).

    ![A tervezett jelentés nyelvi és kulturális beállításainak konfigurálása az ER-művelettervezőben](./media/er-quick-start1-template-format-structure1.png)

5. A formátumfában bontsa ki a gyökércsomópontot, majd válassza ki a **ResultsGroup** lehetőséget.
6. A **Formátum** lap **Replikációs irány** mezőjében válassza a **Nem replikál** lehetőséget, mert egy kérdőív esetében nem várható több eredménycsoport.

    ![A replikálási irány meghatározása a Tartomány formátumelemhez az ER-művelettervezőben](./media/er-quick-start1-template-format-structure2.png)

7. Válassza a **Mentés** lehetőséget.

#### <a name="define-the-data-binding-for-a-report-title"></a><a name="DefineFormatBindings"></a>Adatkötés definiálása a jelentés címéhez

Az olyan formátumelemekhez, amelyek a létrehozott jelentések címének kitöltésére szolgálnak, meg kell határozni adatkötést.

1. A **Formátumtervező** oldal **Leképezés** lapjának jobb oldalán válassza a **Report\\ReportTitle** elemet.
2. Válassza a **Képlet szerkesztése** elemet.
3. A receptúraszerkesztőben válassza a **Fordítás** lehetőséget.
4. A **Szöveg fordítása** párbeszédpanelen hajtsa végre a következő lépéseket:

    1. A **Címkeazonosító** mezőbe írja a **ReportTitle** értéket.
    2. A **Szöveg az alapértelmezett nyelven** mezőben adja meg: **Kérdőívek jelentése**.
    3. Válassza a **Fordítás**, majd a **Mentés** elemet.
    4. A **Fordítás** lehetőség kiválasztásával zárja be a **Szöveg fordítása** párbeszédpanelt.

5. Zárja be a receptúraszerkesztőt.

    ![A kötés konfigurálása a létrehozott jelentés címének kitöltéséhez](./media/er-quick-start1-add-report-title-label.png)

Ezzel a technikával az aktuális sablon sablonnyelvtől függő összes további címke elkészíthető. Ha további információt szeretne arról, hogyan egy adott ER-konfiguráció hozzáadott címkéi hogyan fordíthatók le az összes támogatott nyelvre, tekintse át a [Többnyelvű jelentések tervezése](er-design-multilingual-reports.md) részt.

#### <a name="review-model-data-source"></a><a name="ReviewModelDataSource"></a>A modell adatforrásának ellenőrzése

1. A **Formátumtervező** oldal **Leképezés** lapján válassza ki a <a name="ModelDSName"></a>**modell** adatforrást, amely ennek az ER-formátumnak az alap adatmodelljét jelzi.
2. Válassza ki a **Szerkesztés** opciót.
3. Tekintse át az **Adatforrás-tulajdonságok** párbeszédpanelen lévő adatokat. Ez az adatforrás jelöli a **Kérdőívek** adatmodell-összetevő 1. verzióját, amely a **Kérdőívek modell** ER-konfigurációjában található.

![A modelladatforrás tulajdonságai az ER-művelettervezőben](./media/er-quick-start1-model-data-source.png)

#### <a name="bind-format-elements-to-data-source-fields"></a><a name="BindFormatElements"></a>Formátum-összetevők összekötése az adatforrás mezőivel

Ha meg szeretné adni, hogyan történjen egy sablon kitöltése a futásidőben, akkor a megfelelő Excel-nevekhez társított minden formátumelemet kötni kell e formátum adatforrásának egy adott mezőjéhez.

1. A **Formátumtervező** oldal formátumfájában válassza ki a **Report\\CompanyName** formátumelemet.
2. A **Leképezés** lapon válassza ki a **Sztring** típus **model.CompanyName** adatforrásmezőjét.
3. Ha meg szeretné adni egy vállalat nevét a sablonban, válassza a **Kötés** lehetőséget.
4. A formátumfában válassza ki a **Report\\Questionnaire** elemet.
5. A **Leképezés** lapon válassza ki a **Rekordlista** típus **model.Questionnaire** adatforrásmezőjét.
6. Válassza a **Bind** elemet.
7. A formátumelemek további részleteinek megtekintéséhez válassza a **Részletek megjelenítése** lehetőséget.

    A **Kérdőív** tartomány formátumeleme vertikálisan replikáltként van konfigurálva. Amikor **Rekordlista** típusú adatforráshoz kötik, a program megismétli az Excel-sablon megfelelő **Kérdőív** tartományát a kötésben lévő adatforrás minden rekordjánál.
 
    ![A Kérdőív tartomány formátumelemének kötése a megfelelő Rekord lista adatforrásaihoz az ER-művelettervezőben](./media/er-quick-start1-bindings1.png)

    Mivel az Excel-sablon **Kérdőív** tartományának definiálása az 5–14. sor között történik, ezeket a sorokat a rendszer minden jelentett kérdőívnél megismétli.

    ![Az Excel-sablon olyan sorai, amelyek egy létrehozott jelentésben a Rekord lista adatforrásainak valamennyi rekordjához megismétlődnek](./media/er-quick-start1-template-questionnaire-range.png)

8. A fennmaradó formátumelemekhez konfiguráljon hasonló kötéseket, a következő táblázatban leírt módon.

    > [!NOTE]
    > Ebben a táblában az „Adatforrás elérési útja” oszlopban szereplő információ azt feltételezi, hogy a [relatív elérési út](relative-path-data-bindings-er-models-format.md) ER-funkció be van kapcsolva.

    | Formátumelem elérési útja                                      | Adatforrás elérési útja |
    |----------------------------------------------------------|------------------|
    | Excel\\ReportTitle                                       | **\@"GER\_LABEL:ReportTitle"** |
    | Excel\\CompanyName                                       | **model.CompanyName** |
    | Excel\\Questionnaire                                     | **model.Questionnaire** |
    | Excel\\Questionnaire\\Active                             | **\@.Active**, ahol a **\@** a **model.Questionnaire** |
    | Excel\\Questionnaire\\Code                               | **\@.Code** |
    | Excel\\Questionnaire\\Description                        | **\@.Description** |
    | Excel\\Questionnaire\\QuestionnaireType                  | **\@.QuestionnaireType** |
    | Excel\\Questionnaire\\QuestionOrder                      | **\@.QuestionOrder** |
    | Excel\\Questionnaire\\ResultsGroup\\Code\_               | **\@.ResultsGroup.Code** |
    | Excel\\Questionnaire\\ResultsGroup\\Description\_        | **\@.ResultsGroup.Description** |
    | Excel\\Questionnaire\\ResultsGroup\\MaxNumberOfPoints    | **\@.ResultsGroup.MaxNumberOfPoint** |
    | Excel\\Questionnaire\\Question                           | **\@.Question** |
    | Excel\\Questionnaire\\Question\\CollectionSequenceNumber | **\@.CollectionSequenceNumber**, ahol a **\@** a **model.Questionnaire.Question** |
    | Excel\\Questionnaire\\Question\\Id                       | **\@.Id** |
    | Excel\\Questionnaire\\Question\\MustBeCompleted          | **\@.MustBeCompleted** |
    | Excel\\Questionnaire\\Question\\PrimaryQuestion          | **\@.PrimaryQuestion** |
    | Excel\\Questionnaire\\Question\\SequenceNumber           | **\@.SequenceNumber** |
    | Excel\\Questionnaire\\Question\\Text                     | **\@.Text** |
    | Excel\\Questionnaire\\Question\\Answer                   | **\@.Answer** |
    | Excel\\Questionnaire\\Question\\Answer\\CorrectAnswer    | **\@.CorrectAnswer**, ahol a **\@** a **model.Questionnaire.Answer** |
    | Excel\\Questionnaire\\Question\\Answer\\Points           | **\@.Points** |
    | Excel\\Questionnaire\\Question\\Answer\\Text             | **\@.Text** |

9. Amikor elkészült, válassza a **Mentés** elemet.

A következő ábra a **Formátumtervező** oldal konfigurált adatkötéseinek végleges állapotát mutatja.

![Konfigurált adatkötések az ER-művelettervezőben](./media/er-quick-start1-bindings2.png)

> [!IMPORTANT]
> A megadott adatforrások és kötések egész gyűjteménye a konfigurált formátum formátumleképezési összetevőjét jelöli. A rendszer ezt a formátumleképezést hívja meg, amikor Ön futtatja konfigurált formátumot jelentések létrehozásához.

### <a name="run-a-designed-format-from-er"></a><a name="RunFormatFromER"></a>Megtervezett formátum futtatása az ER-ből

Most tesztelési célra futtathat egy tervezett formátumot a **Konfigurációk** oldalon.

1. Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**.
2. A **Konfiguráció** oldalon, a konfigurációk bal oldali panelen található fájában bontsa ki a **Kérdőív modellje** elemet, majd válassza a **Jelentés a kérdőívről** lehetőséget.
3. Válassza ki a **Tervező** lehetőséget a **Piszkozat** állapotú formátumverzióhoz.
4. A **Formátumtervező** oldalon válassza a **Futtatás** elemet.
5. Az **ER-paraméterek** párbeszédpanelén lévő **Belefoglalandó rekordok** gyorslapon adja meg a szűrőfeltételeket, hogy a rendszer csak az **SBCCrsExam** kérdőívet szerepeltesse.
6. A szűrési beállítás megerősítéséhez kattintson az **OK** lehetőségre.
7. A jelentés futtatásához válassza az **OK** lehetőséget.
8. Tekintse át a létrehozott jelentést.

[Alapértelmezés szerint](electronic-reporting-destinations.md#default-behavior) a létrejövő jelentések letölthető Excel-fájlként jelennek meg. A következő képeken a létrejövő Excel-formátumú jelentés két oldala látható.

![A létrejövő Excel-formátumú jelentés példája, 1. oldal](./media/er-quick-start1-report1a.png)

![A létrejövő Excel-formátumú jelentés példája, 2. oldal](./media/er-quick-start1-report1b.png)

## <a name="tune-a-designed-format"></a><a name="TuneFormat"></a>Megtervezett formátum finomhangolása

### <a name="modify-a-format-to-change-the-name-of-a-generated-document"></a><a name="ModifyToChangeName"></a>Formátum módosítása a létrehozott dokumentumok nevének módosításához

Alapértelmezés szerint a létrehozott dokumentumok elnevezése az aktuális felhasználó aliasával történik. A formátum módosításával ezt a viselkedést módosíthatja, hogy a létrejövő dokumentumok elnevezése az Ön által megadott egyéni logika alapján történjen. A létrejövő dokumentumok neve például az aktuális munkamenet dátumán és időpontján és a jelentés címén alapulhat.

1. A **Formátumtervező** lapon válassza a **Jelentés** gyökérelemet.
2. Válassza a **Leképezés** lap **Fájlnév szerkesztése** elemét.
3. A **Receptúra** mezőbe írja be a **CONCATENATE (\@"GER\_LABEL:ReportTitle", " - ", DATETIMEFORMAT(SESSIONNOW(), "yyyy-MM-dd hh-mm-ss"))** képletet.
4. Válassza a **Mentés** gombot, majd zárja be a receptúraszerkesztőt.
5. Válassza a **Mentés** lehetőséget.

### <a name="modify-a-format-to-change-the-order-of-questions"></a><a name="ModifyToOrder"></a>Formátum módosítása a kérdések sorrendjének módosításához

A kérdések nem megfelelő sorrendben vannak a létrejövő jelentésekben. A sorrendet a formátum módosításával lehet módosítani.

1. A **Formátumtervező** lapon válassza a **Jelentés** gyökérelemet.
2. A **Leképezés** lapon lévő formátumfán bontsa ki a **Report\\Questionnaire\\Question** részt.

    ![A Tartomány típus Kérdés formátumeleme az ER-művelettervezőben](./media/er-quick-start1-bindings3.png)

3. A **Leképezés** lapon válassza a **model.Questionnaire** lehetőséget.
4. Válassza a **Hozzáadás** \> **Functions\\Calculated field** lehetőséget, majd a **Név** mezőben adja meg, hogy **OrderedQuestions**.
5. Válassza a **Képlet szerkesztése** elemet.
6. A receptúraszerkesztőben a **Receptúra** mezőbe írja be az **ORDERBY (model.Questionnaire.Question, model.Questionnaire.Question.SequenceNumber)** képletet az aktuális kérdőív kérdéslistájának sorszám szerint történő rendezéséhez.
7. Válassza a **Mentés** gombot, majd zárja be a receptúraszerkesztőt.
8. Az új számított mező bejegyzésének befejezéséhez kattintson az **OK** gombra.
9. A **Leképezés** lapon válassza a **model.Questionnaire.OrderedQuestions** lehetőséget.
10. A formátumokat megjelenítő fán válassza az **Excel\\Questionnaire\\Question** lehetőséget.
11. Válassza a **Kötés** lehetőséget, majd győződjön meg arról, hogy az aktuális **model.Questionnaire.Questions** elérési utat a rendszer az új **model.Questionnaire.OrderedQuestions** elérési útra cserélte a beágyazott elemek összes kötésében.
12. Válassza a **Mentés** lehetőséget.

![A Kérdés formátumú elem kötése a konfigurált OrderedQuestions-adatforráshoz az ER-művelettervezőben](./media/er-quick-start1-bindings4.png)

### <a name="run-a-modified-format-from-er"></a><a name="RunFormatFromER2"></a>Módosított formátum futtatása az ER-ből

Most már futtathat módosított formátumokat tesztelési célból az ER-keretrendszerből.

1. A **Formátumtervező** oldalon válassza a **Futtatás** elemet.
2. Az **ER-paraméterek** párbeszédpanelén lévő **Belefoglalandó rekordok** gyorslapon adja meg a szűrőfeltételeket, hogy a rendszer csak az **SBCCrsExam** kérdőívet szerepeltesse.
3. A szűrési beállítás megerősítéséhez kattintson az **OK** lehetőségre.
4. A jelentés futtatásához válassza az **OK** lehetőséget.
5. Tekintse át a létrehozott jelentést.

A következő képen egy olyan Excel-formátumú létrehozott jelentés látható, amelyen helyes sorrendben vannak a kérdések.

![Excel-formátumú létrehozott jelentés, amely helyes sorrendbe rendezett kérdéseket tartalmaz](./media/er-quick-start1-report2.png)

### <a name="complete-the-format-design"></a><a name="CompleteFormat"></a>A formátum kialakításának befejezése

1. Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**.
2. A **Konfigurációk** oldalon, a konfigurációk bal oldali panelen található fájában bontsa ki a **Kérdőív modellje** elemet, majd válassza a **Jelentés a kérdőívről** lehetőséget.
3. A **Verziók** gyorslapon válassza ki azt a konfigurációverziót, amelynek az állapota **Piszkozat**.
4. Válassza az **Állapot módosítása** \> **Teljes** lehetőséget.

A konfiguráció 1.1. verziójának állapota **Piszkozatról** **Befejezett** értékre módosul. Az 1.1. verzió a későbbiekben már nem módosítható. Ez a verzió a konfigurált formátumot tartalmazza, és egyéni jelentés nyomtatására is használható. A konfiguráció 1.2. változata létrejön **Piszkozat** állapottal. Ezt a verziót a **Kérdőív** jelentés formátumának módosításával szerkesztheti.

![A szerkeszthető ER-konfiguráció verziói a Konfigurációk oldalon](./media/er-quick-start1-format-configuration.png)

> [!NOTE]
> A konfigurált formátum az Ön kialakítása a **Kérdőív** jelentéshez, és nincs kapcsolata Finance-specifikus összetevőkkel.

## <a name="develop-application-artefacts-to-call-the-designed-report"></a><a name="DevelopCustomCode"></a>Alkalmazás-összetevők fejlesztése a megtervezett jelentés meghívásához

Rendszergazda szerepkörű felhasználóként új logikát kell kidolgoznia, hogy a konfigurált ER-formátumot meg lehessen hívni az alkalmazás felhasználói felületéről (UI) az egyéni jelentés létrehozásához. Az ER jelenleg nem rendelkezik ilyen típusú logika konfigurálásához használható funkciókkal. Ennek megfelelően ehhez műszaki erőfeszítésre van szükség. 

Az új logika kidolgozásához telepítenie kell egy olyan topológiát, amely támogatja a folyamatos buildet. A további tudnivalókért lásd: [A folyamatos build- és tesztautomatizálást támogató topológiák telepítése](../perf-test/continuous-build-test-automation.md). Ezen topológia fejlesztői környezetéhez való hozzáféréssel is kell rendelkezzen. További információ az elérhető ER API-ról: [Elektronikus jelentéskészítési keretrendszer API](er-apis-app73.md).

### <a name="modify-source-code"></a><a name="ModifySourceCode"></a>Forráskód módosítása

#### <a name="add-a-data-contract-class"></a><a name="DataContractClass"></a>Adatszerződés-osztály hozzáadása

Adja hozzá az új **QuestionnairesErReportContract** osztályt a Microsoft Visual Studio-projekthez, és írjon egy olyan kódot, amely meghatározza, hogy melyik adatszerződést kell használni a konfigurált ER-formátum futtatásához.

```xpp
/// <summary>
///     This class is the data contract class for the <c>QuestionnairesErReportDP</c> class.
/// </summary>
/// <remarks>
///    This is the data contract class for the Questionnaires ER report.
/// </remarks>
[
    DataContractAttribute,
    SysOperationContractProcessingAttribute(classStr(QuestionnairesErReportUIBuilder))
    ]
    public class QuestionnairesErReportContract extends ERFormatMappingRunBaseContract implements SysOperationValidatable
{
    ERFormatMappingId formatMapping;

    /// <summary>
    ///    Validates the report parameters.
    /// </summary>
    /// <returns>
    ///    true if no errors; otherwise, false.
    /// </returns>
    public boolean validate()
    {
        boolean ret = true;
        if (!formatMapping)
        {
            ret = checkFailed(strFmt("@SYS26332", new SysDictType(extendedTypeNum(ERFormatMappingId)).label()));
        }
        return ret;
    }
    [
        DataMemberAttribute('FormatMapping'),
        SysOperationLabelAttribute(literalstr("@ElectronicReporting:FormatMapping")),
        SysOperationHelpTextAttribute(literalstr("@ElectronicReporting:FormatMapping"))
    ]
    public ERFormatMappingId parmFormatMapping(ERFormatMappingId _formatMapping = formatMapping)
    {
        formatMapping = _formatMapping;
        return formatMapping;
    }
}
```

#### <a name="add-a-ui-builder-class"></a><a name="UIBuilderClass"></a>UI-készítő osztály hozzáadása

Adja hozzá az új **QuestionnairesErReportUIBuilder** osztályt a Visual Studio-projekthez, és írjon egy kódot, amely olyan futásidejű párbeszédpanelt hoz létre, amellyel megkereshető a futtatandó ER-formátum formátum-hozzárendelési azonosítója. A megadott kód csak olyan ER-formátumokat keres, amelyek az **Adatmodell** típus olyan adatforrását tartalmazzák, amely a **[Kérdőívek](#DataModeName)** adatmodellre a **[Gyökér](#RootDefinitionName)** definícióval hivatkozik.

> [!NOTE]
> Egy másik lehetőség, hogy az ER-formátumok szűréséhez ER-integrációs pontokat használ. További információ: [API a formátumleképezési keresés megjelenítéséhez](er-apis-app10-0-11.md#api-to-show-a-format-mapping-lookup).

```xpp
/// <summary>
/// The UIBuilder class for Questionnaires ER report
/// </summary>
class QuestionnairesErReportUIBuilder extends SysOperationAutomaticUIBuilder
{
    public const str ERQuestionnairesModel = 'Questionnaires';
    public const str ERQuestionnairesDataContainer = 'Root';

    /// <summary>
    /// Action after build of the dialog UI.
    /// </summary>
    public void postBuild()
    {
        DialogField formatMapping;
        super();
        formatMapping = this.bindInfo().getDialogField(this.dataContractObject(),
            methodStr(QuestionnairesErReportContract, parmFormatMapping));
        formatMapping.registerOverrideMethod(
            methodStr(FormReferenceControl, lookupReference),
            methodStr(QuestionnairesErReportUIBuilder, formatMappingLookup),
            this);
    }

    /// <summary>
    /// Performs the lookup form for format mapping.
    /// </summary>
    /// <param name="_referenceGroupControl">
    /// The control to perform lookup form.
    /// </param>
    public void formatMappingLookup(FormReferenceControl _referenceGroupControl)
    {
        ERObjectsFactory::createFormatMappingTableLookupForControlAndModel(
            _referenceGroupControl,
            ERQuestionnairesModel,
            ERQuestionnairesDataContainer).performFormLookup();
    }
}
```

#### <a name="add-a-data-provider-class"></a><a name="DataProviderClass"></a>Adatszolgáltató-osztály hozzáadása

Adja hozzá az új **QuestionnairesErReportDP** osztályt a Microsoft Visual Studio-projekthez, és írjon egy olyan kódot, amely megadja, hogy melyik adatszolgáltatót kell használni a konfigurált ER-formátum futtatásához. A megadott kód csak ennek az adatszolgáltatónak az adatszerződését tartalmazza.

```xpp
/// <summary>
/// Data provider class for Questionnaires ER report.
/// </summary>
public class QuestionnairesErReportDP
{
    QuestionnairesErReportContract contract;
    public static QuestionnairesErReportDP construct()
    {
        QuestionnairesErReportDP  dataProvider;
        dataProvider = new QuestionnairesErReportDP();
        return dataProvider;
    }
}
```

#### <a name="add-a-labels-file"></a><a name="LabelsFile"></a>Címkéket tartalmazó fájlok hozzáadása

Adja hozzá az új **QuestionnairesErReportLabels\_en-US** címkék fájlját a Visual Studio-projekthez, és határozza meg a következő címkéket az új felhasználói felületi erőforrásokhoz:

- A **\@QuestionnairesReport** címke olyan új menüelemhez, amely amerikai angol nyelven (en-US) tartalmazza a következő szöveget: **Kérdőívek jelentése (ER használatával)**
- A **\@QuestionnairesReportBatchJobDescription** címke kötegelt feladatcímekhez, ha a kiválasztott ER-formátumot kötegelt feladatként ütemezték végrehajtásra

#### <a name="add-a-report-service-class"></a><a name="ServiceClass"></a>Jelentésszolgáltatási osztály hozzáadása

Adja hozzá az új **QuestionnairesErReportService** osztályt a Visual Studio-projekthez, és írjon egy olyan kódot, amely meghív egy ER-formátumot, meghatározza formátumleképezési azonosítóként, majd egy adatszerződést biztosít paraméterként.

```xpp
using Microsoft.Dynamics365.LocalizationFramework;
/// <summary>
/// The electronic reporting service class for Questionnaires ER report
/// </summary>
class QuestionnairesErReportService extends SysOperationServiceBase
{
    public const str ERModelDataSourceName = 'model';
    public const str DefaultExportedFileName = 'Questionnaires report';
    public const str ParametersDataSourceName = 'RunTimeParameters';

    /// <summary>
    /// Generates report by using Electronic reporting framework
    /// </summary>
    /// <param name = "_contract">The Questionnaires report contract</param>
    public void generateReportByGER(QuestionnairesErReportContract _contract)
    {
        ERFormatMappingId formatMappingId;
        QuestionnairesErReportDP  dataProvider;
        dataProvider = QuestionnairesErReportDP::construct();
        formatMappingId = _contract.parmFormatMapping();
        if (formatMappingId)
        {
            try
            {
                ERIModelDefinitionParamsAction parameters = new ERModelDefinitionParamsUIActionComposite()
                    .add(new ERModelDefinitionObjectParameterAction(ERModelDataSourceName, ParametersDataSourceName, _contract, true));

                // Call ER to generate the report.
                ERIFormatMappingRun formatMappingRun = ERObjectsFactory::createFormatMappingRunByFormatMappingId(formatMappingId, DefaultExportedFileName);
                if (formatMappingRun.parmShowPromptDialog(true))
                {
                    formatMappingRun.withParameter(parameters);
                    formatMappingRun.withFileDestination(_contract.getFileDestination());
                    formatMappingRun.run();
                }
            }
            catch
            {
                // An error occurred while exporting data.
                error("@SYP4861341");
            }
        }
        else
        {
            // There is no data available.
            info("@SYS300117");
        }
    }
}
```

Amikor az alkalmazás adatait futtató ER-formátumot kell használnia, konfigurálnia kell az **Adatmodell** típus adatforrását a formátumleképezésben. Ez az adatforrás egyetlen gyökérdefiníció használatával utal a megadott adatmodell meghatározott részére. Az ER-formátum a futtatáskor ezt az adatforrást hívja meg, hogy elérje az adott modellhez és gyökérdefinícióhoz konfigurált megfelelő ER-modell-leképezést.

A forráskódban esetlegesen előkészített és az adatszerződés részeként tárolt összes adat átadható a futó ER-formátumnak az ilyen típusú ER-modell-leképezések használatával. Az ER-modell-leképezésben konfigurálni kell egy olyan **Objektum** típusú adatforrást, amely a **[QuestionnairesErReportContract](#DataContractClass)** osztályra hivatkozik. A modell-leképezések azonosításához meg kell adnia egy olyan adatforrást, amely ezt a modell-leképezést hívja meg. A megadott kódban ezt az adatforrást az az **ERModelDataSourceName** konstans határozza meg, amely a **[modell](#ModelDSName)** értékkel rendelkezik. Ha meg szeretné állapítani, hogy melyik adatforrás használatával történik a modell-leképezésben lévő adatszerződés elérhetővé tétele, meg kell adnia egy adatforrásnevet. A megadott kódban ezt a nevet az a **ParametersDataSourceName** konstans határozza meg, amely a <a name="DataContractDSName"></a>**RunTimeParameters** értékkel rendelkezik.

> [!NOTE]
> Az új környezetekben előfordulhat, hogy frissíteni kell az ER-metaadatokat, hogy az ilyen típusú osztály elérhető legyen az ER-modell-leképezés tervezőjében. További információ: [ER-keretrendszer konfigurálása](electronic-reporting-er-configure-parameters.md#frequently-asked-questions).

#### <a name="add-a-report-controller-class"></a><a name="ControllerClass"></a>Jelentésvezérlő osztály hozzáadása

Adja hozzá az új **QuestionnairesErReportController** osztályt a Visual Studio-projekthez, és írjon egy olyan kódot, amely (igény szerint) vagy szinkron vagy kötegelt módban futtat egy ER-formátumot azon a párbeszédpanelen, amely a megadott **QuestionnairesErReportUIBuilder** osztály logikájára épül.

```xpp
/// <summary>
/// The controller for Questionnaires ER report
/// </summary>
class QuestionnairesErReportController extends ERFormatMappingRunBaseController
{
    /// <summary>
    /// The main entrance of the controller
    /// </summary>
    /// <param name = "args">The arguments</param>
    public static void main(Args args)
    {
        QuestionnairesErReportController operation;
        operation = new QuestionnairesErReportController(
            classStr(QuestionnairesErReportService),
            methodStr(QuestionnairesErReportService, generateReportByGER),
            SysOperationExecutionMode::Synchronous);
        operation.startOperation();
    }

    /// <summary>
    /// Gets caption of the dialog.
    /// </summary>
    /// <returns>Caption of the dialog</returns>
    public ClassDescription defaultCaption()
    {
        ClassDescription batchDescription;
        batchDescription = "Questionnaires report (powered by ER)";
        return batchDescription;
    }
}
```

#### <a name="add-a-menu-item"></a><a name="MenuItem"></a>Menüelem hozzáadása

Adja hozzá az új **QuestionnairesErReport** menüelemet a Visual Studio-projekthez. Az **Objektum** tulajdonságában ez a menüelem a **QuestionnairesErReportController** osztályra hivatkozik, és az ER-formátumok kiválasztásához és futtatásához szükséges felhasználói engedély meghatározásához használatos. A **Címke** tulajdonságban ez a menüelem a korábban létrehozott **\@QuestionnairesReport** címkére hivatkozik, hogy megfelelő szöveg jelenjen meg az alkalmazás kezelőfelületén.

#### <a name="add-a-menu-item-to-a-menu"></a><a name="Menu"></a>Menüelem hozzáadása a menükhöz

Adja hozzá a meglévő **KM** menüt a Visual Studio-projekthez. Ehhez a menühöz fel kell vennie egy új **QuestionnairesErReport** elemet a **Kimenet** típusból. Ennek az elemnek az előző szakaszban leírt **QuestionnairesErReport** menüelemre kell hivatkoznia.

#### <a name="build-a-visual-studio-project"></a><a name="BuildVSProject"></a>Visual Studio-projekt készítése

Készítse el a felhasználók számára új menüelemet elérhetővé tevő projektet.

### <a name="run-a-format-from-the-application"></a><a name="RunFormatFromApp"></a>Formátum futtatása az alkalmazásból

1. Lépjen a **Kérdőív** \> **Tervezés** \> **Kérdőívek jelentése (ER használatával)** részre.

    ![A Kérdőívek jelentése (ER használatával) menüelem kiválasztása a Kérdőív modulban a konfigurált ER-formátum futtatásához](./media/er-quick-start1-application-menu-modified.png)

2. A párbeszédpanel **Formátum leképezése** mezőjében válassza a **Kérdőívek jelentése** lehetőséget.
3. Válassza ki az **OK** lehetőséget.
4. Az **Elektronikus jelentés paraméterei** párbeszédpanelén lévő **Belefoglalandó rekordok** gyorslapon adja meg a szűrőfeltételeket, hogy a rendszer csak az **SBCCrsExam** kérdőívet szerepeltesse.
5. A szűrési beállítás megerősítéséhez kattintson az **OK** lehetőségre.
6. A jelentés futtatásához válassza az **OK** lehetőséget.

    ![A kiválasztási feltételek megadása az Elektronikus jelentés párbeszédpanelen](./media/er-quick-start1-report-run-dialog-page.png)

7. Tekintse át a létrehozott jelentést.

## <a name="tune-a-designed-er-solution"></a><a name="TuneSolution"></a>Megtervezett ER-megoldás finomhangolása

A konfigurált ER megoldást módosíthatja úgy, hogy azt az adatszolgáltató osztályt használja, amellyel Ön elérhetővé tette a futó ER-formátum részleteit, így a létrehozott jelentésben lévő ER-formátum nevét adja meg.

### <a name="modify-a-model-mapping"></a><a name="ModifyModelMapping"></a>Modell-hozzárendelés módosítása

#### <a name="add-data-sources-to-access-a-data-contract-object"></a><a name="AddDataSource1"></a>Adatforrások hozzáadása adatszerződési objektum eléréséhez

1. Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**.
2. A **Konfigurációk** oldalon, a konfigurációk bal oldali panelen található fájában bontsa ki a **Kérdőív modellje** elemet, majd válassza a **Kérdőív leképezése** lehetőséget.
3. A **Tervező** lehetőség kiválasztásával nyissa meg a **Modell leképezése adatforráshoz** oldalt.
4. A **Tervező** lehetőség kiválasztásával nyissa meg a kiválasztott leképezést a modell-leképezés tervezőjében.
5. A **Modell-leképezés tervező** oldal **Adatforrástípusok** paneljén válassza a **Dynamics 365 for Operations\\Objektum** lehetőséget.
6. Az **Adatforrás** panelen válassza a **Gyökér hozzáadása** elemet.
7. A párbeszédpanel **Név** mezőjébe írja be a **[RunTimeParameters](#DataContractDSName)** **QuestionnairesErReportService** osztály forráskódjában meghatározott értékét.
8. Az **Osztály** mezőbe írja be a korábban kódolt **[QuestionnairesErReportContract](#DataContractClass)** értéket.
9. Válassza ki az **OK** lehetőséget.
10. Bontsa ki a **RunTimeParameters** részt.

A hozzáadott adatforrás információt tartalmaz a futó ER-formátumleképezés rekordazonosítójáról.

![Hozzáadott adatforrás az ER-modell-leképezés tervezőjében](./media/er-quick-start1-mapping3.png)

#### <a name="add-a-data-source-to-access-er-format-mapping-records"></a><a name="AddDataSource2"></a>Adatforrások hozzáadása az ER-formátum leképezési rekordjaihoz való hozzáféréshez

Folytassa a kiválasztott modell-leképezés szerkesztését: adjon hozzá adatforrást az ER-formátum-leképezési rekordok eléréséhez.

1. A **Modell-leképezés tervező** oldal **Adatforrástípusok** paneljén válassza a **Dynamics 365 for Operations\\Táblarekordok** lehetőséget.
2. Az **Adatforrás** panelen válassza a **Gyökér hozzáadása** elemet.
3. A párbeszédpanel **Név** mezőjébe írja be az **ER1** kifejezést.
4. A **Tábla** mezőbe írja be a **ERFormatMappingTable** kifejezést.
5. Válassza ki az **OK** lehetőséget.

#### <a name="add-a-data-source-to-access-a-format-mapping-record-of-a-running-er-format"></a><a name="AddDataSource3"></a>Adatforrások hozzáadása a futó ER-formátum formátumleképezési rekordjaihoz való hozzáféréshez

Folytassa a kiválasztott modell-leképezés szerkesztését: adjon hozzá adatforrást a futó ER-formátum formátumleképezési rekordjának eléréséhez.

1. A **Modell-leképezés tervező** oldal **Adatforrástípusok** paneljén válassza a **Functions\\Calculated field** lehetőséget.
2. Az **Adatforrás** panelen válassza a **Gyökér hozzáadása** elemet.
3. A párbeszédpanel **Név** mezőjébe írja be az **ER2** kifejezést.
4. Válassza a **Képlet szerkesztése** elemet.
5. A receptúraszerkesztő **Receptúra** mezőjébe írja be a **FIRSTORNULL (FILTER(ER1, ER1.RecId = RunTimeParameters.parmFormatMapping))** képletet.
6. Válassza a **Mentés** gombot, majd zárja be a receptúraszerkesztőt.
7. Válassza ki az **OK** lehetőséget.

#### <a name="enter-the-name-of-the-running-er-format-in-the-data-model"></a><a name="AddBinding"></a>Futó ER-formátum nevének megadása az adatmodellben

Folytassa a kiválasztott modell-leképezés szerkesztését, hogy megadhassa az adatmodellben megadott futó ER-formátum nevét.

1. A **Modell-leképezés tervező** oldal **Adatmodell** paneljén bontsa ki az **ExecutionContext** részt, és válassza az **ExecutionContext\\FormatName** lehetőséget.
2. Az **Adatmodell** panelen válassza a **Szerkesztés** lehetőséget a kiválasztott adatmodell mezőjéhez tartozó adatkötések konfigurálásához.
3. A receptúraszerkesztő **Receptúra** mezőjébe írja be a **FIRSTORNULL (ER2.'\>Relations'.Format).Name** képletet.
4. Válassza a **Mentés** gombot, majd zárja be a receptúraszerkesztőt.

Mivel a **FormatName** mezőt használta, a konfigurált modell-leképezés megjeleníti egy olyan ER-formátum nevét, amely ezt a modellt hívja meg a végrehajtás során.

![Az adatmodell mezőjének kötése az ER-modell-leképezés tervezőjében hozzáadott adatforrás metódusához](./media/er-quick-start1-mapping4.png)

#### <a name="complete-the-design-of-the-model-mapping"></a><a name="CompleteModelMapping2"></a>A modell-leképezés kialakításának befejezése

1. A **Modell-leképezés tervező** oldalon válassza a **Mentés** elemet.
2. Zárja be a lapot.
3. Zárja be a Modell-leképezések oldalt.
4. Ellenőrizze, hogy a **Konfigurációk** oldalon, a konfigurációkat tartalmazó fában a **Kérdőív leképezése** konfiguráció továbbra is be van jelölve. Ezután a **Verziók** gyorslapon válassza ki azt a konfigurációverziót, amelynek az állapota **Piszkozat**.
5. Válassza az **Állapot módosítása** \> **Teljes** lehetőséget.

A konfiguráció 1.2. verziójának állapota **Piszkozatról** **Befejezett** értékre módosul. Az 1.2. verzió a későbbiekben már nem módosítható. Ez a verzió tartalmazza a konfigurált modell-leképezést, és a többi ER-konfiguráció alapjaként használható. A konfiguráció 1.3. változata létrejön **Piszkozat** állapottal. Ezt a verziót a **Kérdőív** modell-leképezés módosításával szerkesztheti.

### <a name="modify-a-format"></a><a name="ModifyFormat"></a>Formátum módosítása

A konfigurált ER-formátum módosítható úgy, hogy a neve megjelenjen az ER-formátum futtatásakor létrehozott jelentés élőlábában.

#### <a name="add-a-new-format-element"></a><a name="AddFormatElement"></a>Új formátumelem hozzáadása

1. Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**.
2. A **Konfigurációk** oldalon, a konfigurációk bal oldali panelen található fájában bontsa ki a **Kérdőív modellje** elemet, majd válassza a **Jelentés a kérdőívről** lehetőséget.
3. Válassza a **Tervező** lehetőséget.
4. A **Formátumtervező** lapon válassza a **Jelentés** gyökérelemet.
5. A **Hozzáadás** lehetőséggel új beágyazott formátumelemet vehet fel a kiválasztott **Jelentés** gyökérelemhez.
6. Válassza az **Excel\\Footer** lehetőséget.
7. A **Név** mezőbe írja be a **Lábléc** szót.
8. Válassza a **Jelentés\Lábléc**, majd a **Hozzáadás** lehetőséget.
9. Válassza a **Text\\String** lehetőséget.

#### <a name="bind-the-added-format-element"></a><a name="BindAddedFormatElement"></a>Hozzáadott formátumelem kötése

1. A **Formátumtervező** oldal **Leképezés** lapján, a formátumok fájában válassza az aktív **Footer\\String** elemnél a **Receptúra szerkesztése** lehetőséget.
2. A receptúraszerkesztő **Receptúra** mezőjébe írja be a **CONCATENATE ("\&C\&10", FORMAT("Generated by'\%1' ER solution", model.ExecutionContext.FormatName))** képletet.
3. Válassza a **Mentés** gombot, majd zárja be a receptúraszerkesztőt.
4. Válassza a **Mentés** lehetőséget.

A konfigurált formátum már módosult, így a rendszer a létrehozott jelentés láblécébe írja be a nevét, a **Footer\\String** elem használatával.

![A Lábléc formátumelem hozzáadása a konfigurált formátumhoz az ER-művelettervezőben](./media/er-quick-start1-template-format-structure3.png)

#### <a name="complete-the-format-design"></a><a name="CompleteFormat2"></a>A formátum kialakításának befejezése

1. Zárja be a **Formátumtervező** lapot.
2. Ellenőrizze, hogy a **Konfigurációk** oldalon, a konfigurációkat tartalmazó fában a **Jelentés a kérdőívről** konfiguráció továbbra is be van jelölve. Ezután a **Verziók** gyorslapon válassza ki azt a konfigurációverziót, amelynek az állapota **Piszkozat**.
3. Válassza az **Állapot módosítása** \> **Teljes** lehetőséget.

A konfiguráció 1.2. verziójának állapota **Piszkozatról** **Befejezett** értékre módosul. Az 1.2. verzió a későbbiekben már nem módosítható. Ez a verzió tartalmazza a konfigurált formátumot, és a többi ER-konfiguráció alapjaként használható. A konfiguráció 1.3. változata létrejön **Piszkozat** állapottal. Ezt a verziót a **Kérdőív** jelentés módosításával szerkesztheti.

### <a name="run-a-format-from-the-application"></a><a name="RunFormatFromApp2"></a>Formátum futtatása az alkalmazásból

1. Lépjen a **Kérdőív** \> **Tervezés** \> **Kérdőívek jelentése (ER használatával)** részre.
2. A párbeszédpanel **Formátum leképezése** mezőjében válassza a **Kérdőívek jelentése** lehetőséget.
3. Válassza ki az **OK** lehetőséget.
4. Az **ER-paraméterek** párbeszédpanelén lévő **Belefoglalandó rekordok** gyorslapon adja meg a szűrőfeltételeket, hogy a rendszer csak az **SBCCrsExam** kérdőívet szerepeltesse.
5. A szűrési beállítás megerősítéséhez kattintson az **OK** lehetőségre.
6. A jelentés futtatásához válassza az **OK** lehetőséget.
7. Tekintse meg a létrehozott jelentést Excel-formátumban.

Figyelje meg, hogy a létrehozott jelentés lábléce a létrehozásához használt ER-formátum nevét tartalmazza.

![A létrehozott jelentés Excel-formátumban](./media/er-quick-start1-report4.png)

### <a name="run-a-format-from-er"></a><a name="RunFormatFromER3"></a>Formátum futtatása az ER-ből

1. Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**.
2. A **Konfigurációk** oldalon, a konfigurációk bal oldali panelen található fájában bontsa ki a **Kérdőív modellje** elemet, majd válassza a **Jelentés a kérdőívről** lehetőséget.
3. A Műveleti ablaktáblán kattintson a **Futtatás** elemre.
4. Az **Elektronikus jelentés paraméterei** párbeszédpanelén lévő **Belefoglalandó rekordok** gyorslapon adja meg a szűrőfeltételeket, hogy a rendszer csak az **SBCCrsExam** kérdőívet szerepeltesse.
5. A szűrési beállítás megerősítéséhez kattintson az **OK** lehetőségre.
6. A jelentés futtatásához válassza az **OK** lehetőséget.
7. Tekintse meg a létrehozott jelentést Excel-formátumban.

Figyelje meg, hogy a létrehozott jelentés lábléce nem tartalmazza a létrehozásához használt ER-formátum nevét, mivel az adatszerződési objektum nem lett átadva a futó modell-leképezésnek, amikor azt meghívta az ER-ből futtatott ER-formátum.

### <a name="configure-a-format-destination-for-on-screen-preview"></a><a name="ConfigureDestination"></a>Formátum célhelyének konfigurálása a képernyőn látható előzetes verzióból

1. Ugorjon a **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Elektronikus jelentéskészítési cél** részre.
2. Az **Elektronikus jelentéskészítési cél** oldalon adjon meg egy célrekordot a konfigurált **Jelentés a kérdőívről** ER-formátumhoz.
3. A **Fájl célja** gyorslapon állítsa be a **Képernyő** [célt](er-destination-type-screen.md) ahhoz a **Jelentés** formátum-összetevőhöz, amelyet [hozzáadott](#AddFormatRootElement) a konfigurált **Jelentés a kérdőívről** ER-formátum gyökérelemeként.
4. A **PDF-konverzió beállításai** gyorslapon konfigurálja a célhelyet a jelentés **Fekvő** tájolást használó [PDF-formátumra](electronic-reporting-destinations.md#OutputConversionToPDF) történő konvertálásához.

![Az egyéni Képernyő cél konfigurálása az ER-formátumhoz az Elektronikus jelentéskészítés célja oldalon](./media/er-quick-start1-destination.png)

### <a name="run-a-format-from-the-application-to-preview-it-as-a-pdf-document"></a><a name="RunFormatFromApp3"></a>Formátum futtatása az alkalmazásból PDF-dokumentumként történő előzetes verzió készítéséhez

1. Lépjen a **Kérdőív** \> **Tervezés** \> **Kérdőívek jelentése (ER használatával)** részre.
2. A párbeszédpanel **Formátum leképezése** mezőjében válassza a **Kérdőívek jelentése** lehetőséget.
3. Válassza ki az **OK** lehetőséget.
4. Az **Elektronikus jelentés paraméterei** párbeszédpanelén lévő **Belefoglalandó rekordok** gyorslapon adja meg a szűrőfeltételeket, hogy a rendszer csak az **SBCCrsExam** kérdőívet szerepeltesse.
5. A szűrési beállítás megerősítéséhez kattintson az **OK** lehetőségre.

    A **Célok** gyorslapon figyelje meg, hogy a **Kimenet** mező értéke **Képernyő**. Ha módosítani szeretné a konfigurált célt, válassza a **Módosítás** lehetőséget.

    ![ER-jelentés konfigurált cél módosítását lehetővé tevő párbeszédpanelje futásidőben](./media/er-quick-start1-run-settings.png)

6. A jelentés futtatásához válassza az **OK** lehetőséget.
7. Tekintse meg a létrehozott jelentést PDF-formátumban.

    ![A létrehozott PDF-formátumú jelentés képernyőn látható előnézete](./media/er-quick-start1-preview-PDF.png)

## <a name="additional-resources"></a><a name="References"></a>További erőforrások

- [Elektronikus jelentések áttekintése](general-electronic-reporting.md)
- [Elektronikus jelentéskészítés képletének nyelve](er-formula-language.md)
- [Többnyelvű jelentések tervezése](er-design-multilingual-reports.md)
- [Elektronikus jelentéskészítési keretrendszer API](er-apis-app73.md)
- [A CASE függvény](er-functions-logical-case.md)
- [A CONCATENATE függvény](er-functions-text-concatenate.md)
- [A DATETIMEFORMAT függvény](er-functions-datetime-datetimeformat.md)
- [A FILTER függvény](er-functions-list-filter.md)
- [A FIRSTORNULL függvény](er-functions-list-firstornull.md)
- [A FORMAT függvény](er-functions-text-format.md)
- [Az IF függvény](er-functions-logical-if.md)
- [Az ORDERBY függvény](er-functions-list-orderby.md)
- [A SESSIONNOW függvény](er-functions-datetime-sessionnow.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]