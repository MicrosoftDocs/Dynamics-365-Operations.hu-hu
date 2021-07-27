---
title: Egy végrehajtott ER formátum hibakeresési adatforrásai az adatfolyam elemzéséhez és átalakításához
description: Ez a témakör azt mutatja be, hogyan lehet hibakeresést végezni egy végrehajtott ER-formátum adatforrásaiból, hogy jobban megérthesse a konfigurált adatáramlást és átalakítást.
author: NickSelin
ms.date: 04/22/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, EROperationDesigner
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-04-01
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: 86551cfeda1e4204c91b0534cda563012191e25c
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/06/2021
ms.locfileid: "6348116"
---
# <a name="debug-data-sources-of-an-executed-er-format-to-analyze-data-flow-and-transformation"></a>Egy végrehajtott ER formátum hibakeresési adatforrásai az adatfolyam elemzéséhez és átalakításához

[!include[banner](../includes/banner.md)]

[!include[banner](../includes/preview-banner.md)]

Amikor egy elektronikus jelentéskészítési (ER) megoldást [konfigurál](tasks/er-format-configuration-2016-11.md) kimenő dokumentumok létrehozásához meghatározhatja azt a módszert, amellyel a rendszer adatokat kérhet le az alkalmazásból, majd a létrehozott kimeneti fájlba illesztheti őket. Ha hatékonyabbá szeretné tenni az ER-megoldás életciklus-támogatását, a megoldásnak egy ER [adatmodellből](general-electronic-reporting.md#DataModelComponent) és annak [leképezési](general-electronic-reporting.md#ModelMappingComponent) összetevőiből kell állnia , valamint egy ER [formátumból](general-electronic-reporting.md#FormatComponentOutbound) és annak leképezési összetevőiből, így a modell-leképezés alkalmazásspecifikus legyen, míg a többi komponens alkalmazásól független maradjon. Emiatt ER számos összetevő [hatással lehet](general-electronic-reporting.md#FormatComponentOutbound) az adatok beviteli folyamatára a létrejövő kimenetben.

Előfordulhat, hogy a létrejövő kimenet adatai eltérően jelennek meg az alkalmazás adatbázisában szereplő ugyanezen adatoktól. Ezekben az esetekben meg kell határozni, hogy melyik ER-összetevő felelős az adatok átalakításáért. Az ER-adatforrás-hibakereső funkció jelentősen csökkenti a vizsgálathoz szükséges időt és költségeket. Az ER-formátum végrehajtását félbeszakíthatja, és megnyithatja az adatforrás-hibakereső felületét. Itt böngészhet az elérhető adatforrások között, és kiválaszthat egy egyedi adatforrást a végrehajtáshoz. Ez a manuális végrehajtás egy ER-formátum tényleges futtatásakor szimulálja az adatforrás végrehajtását. Az eredmény olyan oldalon jelenik meg, ahol elemezni lehet a kapott adatokat.

Ha be kívánja kapcsolni az adatforrás hibakeresési funkcióját, állítsa be az **Adatok hibakeresésének engedélyezése a formátum futtatása során** lehetőséget **Igen** értékre az ER felhasználói paraméterei. Ezt követően elindíthatja az adatforrás hibakeresését, miközben a kimenő dokumentumok létrehozásához futtat egy ER-formátumot. A **Hibakeresés indítása** lehetőséggel is elindíthatja az adatforrás hibakeresését egy ER-formátumhoz, amely konfigurálva van az [ER művelettervezőben](./tasks/er-format-configuration-2016-11.md#design-the-format-of-an-electronic-document).

Ez a témakör a végrehajtható ER formátumokhoz tartozó adatforrás-hibakeresés kezdeményezéséhez tartalmaz útmutatást. Bemutatja, hogy az adatok hogyan segítenek az adatáramlás és az adatok átalakítások megértésében. Az ebben a témakörben szereplő példák a szállítói kifizetések feldolgozásának üzleti folyamatát használják.

## <a name="limitations"></a>Korlátozások

Az adatforrás-hibakereső használható a kimenő dokumentumok létrehozásához futtatott, ER formátumokban használt adatforrások adatainak eléréséhez. Nem használható a bejövő dokumentumok elemzésére szolgál ER-formátumok adatforrásainak hibakeresésére.

A következő ER-formátum beállítások nem érhetők el az adatforrások hibakereséséhez:

- Formátumalakítások
- Formátum és leképezés ellenőrzési szabályai
- Kifejezések engedélyezése
- A memóriában tárolt adatgyűjtés részletei

## <a name="prerequisites"></a>Előfeltételek

- A jelen témakörben szereplő példák végrehajtásához hozzáféréssel kell rendelkeznie a következő [szerepkörök](../sysadmin/tasks/assign-users-security-roles.md) egyikéhez:

    - Elektronikus jelentések fejlesztője
    - Elektronikus jelentések funkcióival foglalkozó konzulens
    - Rendszergazda

- A vállalatot **DEMF** értékre kell beállítani.

- Kövesse a témakör [1. függelékének](#appendix1) lépéseit a Microsoft ER-megoldás szállítói kifizetések feldolgozásához szükséges összetevőinek letöltéséhez.
- Kövesse a témakör [2. függelékének](#appendix2) lépéseit a szállítói kifizetések feldolgozásához szükséges Kötelezettségek előkészítéséhez az Ön által letöltött ER-megoldás segítségével.

## <a name="process-a-vendor-payment-to-get-a-payment-file"></a>Szállítói kifizetések feldolgozása kifizetési fájl beszerzéséhez

1. A szállítói kifizetések feldolgozásához kövesse a témakör [3. függelékének](#appendix3) lépéseit.

    ![Szállítói kifizetések feldolgozása folyamatban.](./media/er-data-debugger-process-payment.png)

2. Töltse le és mentse a zip-fájlt a helyi számítógépére.
3. Bontsa ki az **ISO20022 Credit transfer.xml** fizetési fájlt a zip-fájlból.
4. A kibontott kifizetési fájlt nyissa meg az XML-fájlmegjelenítő segítségével.

    A fizetési fájlban a szállító bankszámlájának nemzetközi bankszámlaszám-kódja (IBAN) nem tartalmaz szóközöket. Ennek megfelelően különbözik a **Bankszámlák** lapon [megadott](#enteredIBANcode) értéktől.

    ![IBAN-kód szóközök nélkül.](./media/er-data-debugger-payment-file.png)

    Az ER adatforrás-hibakeresővel megtudhatja, hogy a rendszer melyik összetevőjét használja az IBAN-kód szóközeinek törlésére.

## <a name="turn-on-data-source-debugging"></a>Adatforrás hibakeresésének bekapcsolása

1. Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**.
2. A **Konfigurációk** oldal műveleti ablaktábláján, a **Konfigurációk** lapon, a **Speciális beállítások** csoportban válassza a **Felhasználói paraméterek** lehetőséget.
3. Az **Adatok hibakeresésének engedélyezése a formátum futtatása során** lehetőséget állítsa **Igen** értékre.

    > [!NOTE]
    > Ez a paraméter a felhasználó- és a vállalatspecifikus.

    ![A Felhasználói paraméterek párbeszédablak.](./media/er-data-debugger-user-parameters.png)

## <a name="process-a-vendor-payment-for-debugging"></a>Szállítói fizetés feldolgozása hibakereséshez

1. A szállítói kifizetések feldolgozásához kövesse a témakör [3. függelékének](#appendix3) lépéseit.
2. Az üzenetablakban válassza az **Igen** lehetőséget annak megerősítéséhez, hogy szeretné megszakítani a szállítói kifizetések feldolgozását, és ehelyett elindítani az adatforrás hibakeresését az **Adatforrások hibakeresése** oldalon.

    ![Megerősítő üzenet mezője.](./media/er-data-debugger-start-debugging.png)

## <a name="debug-data-sources-that-are-used-in-payment-processing"></a>A fizetés feldolgozásakor használt adatforrások hibakeresése

### <a name="debug-the-model-mapping"></a>A modell-leképezés hibakeresése

1. A Műveleti panel **Adatforrások hibakeresése** válassza ki a **Modell-leképezés** lehetőséget a hibakeresés elindításához ebből az ER-összetevőből.
2. A bal oldali adatforrás ablaktáblán válassza ki a **\$notSentTransactions** adatforrást, majd válassza az **Összes rekord beolvasása** parancsot.

    Kiválaszthatja az **1 rekord beolvasása**, a **10 rekord beolvasása**, **100 rekord beolvasása** illetve az **Összes rekord beolvasása** a kiválasztott adatforrás megfelelő számú rekordja beolvasásának a kényszerítéséhez. Ily módon szimulálható az adatforrás elérése a futó ER-formátumból.

3. A jobb oldali adatpanelen válassza az **Összes kibontása** elemet.

    Láthatja, hogy a **Rekordlista** típusú adatforrás egyetlen rekordot tartalmaz.

4. Bontsa ki a **\$notSentTransactions** adatforrást, és válassza ki a beágyazott **vendBankAccountInTransactionCompany ()** metódust.
5. Bontsa ki a **vendBankAccountInTransactionCompany()** metódust, és válassza ki a beágyazott **IBAN** mezőt.
6. Válassza ki az **Érték beolvasása** lehetőséget.

    Az **Érték beolvasása** lehetőség kiválasztásával kényszerítheti a kiválasztott adatforrás kiválasztott mezőjének értékének beolvasását. Ily módon szimulálható ezen mező elérése a futó ER-formátumból.

7. Válassza az **Összes kibontása** elemet.

    ![Az IBAN-mező értéke a modell-leképezésben.](./media/er-data-debugger-debugging-model-mapping.png)

    Látható, hogy a modell-leképezés nem felelős a levágott szóközökért, mivel a szállítói bankszámlához visszaküldött IBAN-kód szóközöket tartalmaz. Ennek megfelelően folytatnia kell az adatforrás hibakeresését.

### <a name="debug-the-format-mapping"></a>A Formátum-leképezés hibakeresése

1. A Műveleti panel **Adatforrások hibakeresése** lapján válassza ki a **Formátumleképezés** lehetőséget a hibakeresés folytatásához ebből az ER-összetevőből.
2. Válassza ki a **\$PaymentByDebtor** adatforrást, majd válassza az **Összes rekord beolvasása** parancsot.
3. A **\$PaymentByDebtor** kibontása.
4. Bontsa ki a **\$PaymentByDebtor.Lines** elemet, majd válassza az **Összes rekord beolvasása** parancsot.
5. Bontsa ki a **\$PaymentByDebtor.Lines.CreditorAccount** elemet.
6. Bontsa ki a **\$PaymentByDebtor.Lines.CreditorAccount.Identification** elemet, majd válassza a **\$PaymentByDebtor.Lines.CreditorAccount.Identification.IBAN** lehetőséget.
7. Válassza ki az **Érték beolvasása** lehetőséget.
8. Válassza az **Összes kibontása** elemet.

    ![Az IBAN-mező értéke a formátumleképezésben.](./media/er-data-debugger-debugging-format-mapping.png)

    Látható, hogy a formátumleképezés adatforrásai nem felelősek a levágott szóközökért, mivel a szállítói bankszámlához visszaküldött IBAN-kód szóközöket tartalmaz. Ennek megfelelően folytatnia kell az adatforrás hibakeresését.

### <a name="debug-the-format"></a>A formátum hibakeresése

1. A Műveleti panel **Adatforrások hibakeresése** lapján válassza ki a **Formátum** lehetőséget a hibakeresés folytatásához ebből az ER-összetevőből.
2. A formátumelemek kibontásával válassza ki az **ISO20022CTReports** \> **XMLHeader** \> **Document** \> **CstmrCdtTrfInitn** \> **PmtInf** elemet, majd válassza ki az **Összes rekord beolvasása** lehetőséget.
3. A formátumelemek kibontásával válassza ki az **ISO20022CTReports** \> **XMLHeader** \> **Document** \> **CstmrCdtTrfInitn** \> **PmtInf** \> **CdtTrfTxInf**, majd válassza az **Összes rekord beolvasása** lehetőséget.
4. A formátumelemek kibontásával válassza ki az **ISO20022CTReports** \> **XMLHeader** \> **Document** \> **CstmrCdtTrfInitn** \> **PmtInf** \> **CdtTrfTxInf** \> **CdtrAcct** \> **Id** \> **IBAN** \> **BankIBAN** elemeket, majd válassz az **Érték lekérése** lehetőséget.
5. Válassza az **Összes kibontása** elemet.

    ![Az IBAN-mező értéke a formátumban.](./media/er-data-debugger-debugging-format.png)

   Látható, hogy a formátumkapcsolás nem felelős a levágott szóközökért, mivel a szállítói bankszámlához visszaküldött IBAN-kód szóközöket tartalmaz. Ennélfogva a **BankIBAN** elem úgy van beállítva, hogy olyan formátumátalakítást használjon, amely törli a szóközöket.

6. Zárja be az adatforrás-hibakeresőt.

### <a name="review-the-format-transformations"></a>A formátum-átalakítások áttekintése

1. Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**.
2. A **Konfigurációk** lapon válassza ki a **Kifizetési modell** \> **ISO20022 jóváírás-átutalás** lehetőséget.
3. Válassza ki a **Tervezőt**, majd az elemelek kibontásával válassza ki a **Dokumentum** \> **CstmrCdtTrfInitn** \> **PmtInf** \> **CdtTrfTxInf** \> **CdtrAcct** \> **Id** \> **IBAN** \> **BankIBAN** lehetőséget.

    ![A BankIBAN elem a Formátumtervező oldalon.](./media/er-data-debugger-referred-transformation.png)

    Amint látható, a **BankIBAN** elem úgy van beállítva, hogy a **nem alfanumerikus elemek eltávolítása** átalakítást használja.

4. Válassza ki az **Átalakítások** lapot.

    ![A BankIBAN elem Átalakítások lapja.](./media/er-data-debugger-transformation.png)

    Amint látható, a **nem alfanumerikus elemek eltávolítása** van beállítva, hogy olyan kifejezést használjon, amely eltávolítja a szóközöket a megadott karaktersorozatból.

## <a name="start-to-debug-in-the-operation-designer"></a>Hibaelhárítás indítása a művelettervezőben

Ha olyan vázlatverziót konfigurál az ER-formátumból, amely közvetlenül a Művelettervezőből futtatható, akkor az adatforrás-hibakeresőt a Műveleti ablaktáblán a **Hibakeresés indítása** elem kiválasztásával érheti el.

![Hibakeresés indítása gomb a Formátumtervező oldalán.](./media/er-data-debugger-run-from-designer.png)

A szerkesztés alatt álló ER formátum leképezési és fomrátum komponensei érhetők el a hibakereséshez.

## <a name="start-to-debug-in-the-model-mapping-designer"></a>Hibaelhárítás indítása a Modelleképezés-tervezőben

Ha olyan ER modell-leképezést konfigurál, amely a **Modell-leképezés** oldalról futtatható akkor az adatforrás-hibakeresőt a Műveleti ablaktáblán a **Hibakeresés indítása** elem kiválasztásával érheti el.

![Hibakeresés indítása gomb a Modell-leképezés-tervező oldalán.](./media/er-data-debugger-run-from-designer-mapping.png)

A szerkesztés alatt álló ER-leképezés modell-leképezési összetevője elérhető a hibakereséshez.

## <a name="appendix-1-get-an-er-solution"></a><a name="appendix1"></a>1. függelék: ER-megoldás lekérése

### <a name="download-an-er-solution"></a>Egy ER-megoldás letöltése

Ha ER-megoldást szeretne használni egy elektronikus fizetési fájl generálásához egy feldolgozás alatt álló szállítói kifizetéshez akkor [letöltheti](download-electronic-reporting-configuration-lcs.md) az **ISO20022 átutalás** ER fizetési formátumot, amely a Microsoft Dynamics Lifecycle Services (LCS) megosztott Közös eszközök könyvtárából vagy a Globális adattárból tölthető le.

![Az ER fizetési formátum importálása a Konfigurációk tárháza oldalon.](./media/er-data-debugger-import-from-repo.png)

A kiválasztott ER-formátumon kívül a következő [konfigurációkat](general-electronic-reporting.md#Configuration) automatikusan importálni kell a Microsoft Dynamics 365 Finance példányba az **ISO20022-átutalás** ER-megoldás részeként:

- **Fizetési modell** [ER adatmodellkonfiguráció](general-electronic-reporting.md#DataModelComponent)
- **ISO20022 átutalás** [ER formátumkonfiguráció](general-electronic-reporting.md#FormatComponentOutbound)
- **Fizetési modell hozzárendelése 1611** [ER modell leképezésének konfigurációja](general-electronic-reporting.md#ModelMappingComponent)
- **Fizetési modell hozzárendelése célhelyhez ISO20022** ER modell leképezésének konfigurációja

Ezeket a konfigurációkat az ER keretrendszer **Konfiguráció** lapján lehet megtekinteni (**Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**).

![A Konfigurációk oldalon importált konfigurációk.](./media/er-data-debugger-configurations.png)

Ha a konfigurációs fából hiányzik a korábban felsorolt konfigurációk valamelyike, akkoe manuálisan le kell tölteni őket a LCS megosztott eszköz könyvtárából, ugyan úgy, ahogy letöltötte az **ISO20022 átutalás** ER fizetési formátumot.

### <a name="analyze-the-downloaded-er-solution"></a>A letöltött ER-megoldás elemzése

#### <a name="review-the-model-mapping"></a>A modell-leképezés áttekintése

1. Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**.
2. Válassza a **Fizetési modell** \> **Kifizetési modell leképezés 1611** lehetőséget.
3. Válassza a **Tervező** lehetőséget.
4. Válassza ki a **Fizetési modell-leképezés ISO20022 CT** leképezésrekordot.
5. Válassza ki a **Tervezőt** elemet, majd tekintse át a megnyitott modell-leképezést.

    Figyelje meg, hogy az adatmodell **Fizetések** mezője a **\$notSentTransactions** adatforráshoz van kapcsolva, amely a feldolgozás alatt álló szállítói kifizetési sorok listáját adja vissza.

    ![Kifizetések mező a Modell-leképezés tervező lapján.](./media/er-data-debugger-model-mapping.png)

#### <a name="review-the-format-mapping"></a>A formátumleképezés áttekintése

1. Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**.
2. Válassza ki a **Kifizetési modell** \> **ISO20022 átutalás** lehetőséget.
3. Válassza a **Tervező** lehetőséget.
4. A **Leképezés** lapon tekintse át a megnyitott formátumleképezést.

    Figyelje meg, hogy a **Dokumentum** \> **CstmrCdtTrfInitn** \> **PmtInf** eleme a **ISO20022CTReports** \> **XMLHeader** fájlnak a **\$PaymentByDebtor** adatforráshoz van kapcsolva, amely úgy van konfigurálva, hogy az adatmodell **Fizetések** mezőjének rekordjait csoportosítsa.

    ![A PmtInf elem a Formátumtervező oldalon.](./media/er-data-debugger-format-mapping.png)

#### <a name="review-the-format"></a>A formátum áttekintése

1. Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**.
2. Válassza ki a **Kifizetési modell** \> **ISO20022 átutalás** lehetőséget.
3. Válassza ki a **Tervezőt** elemet, majd tekintse át a megnyitott formátumot.

    Figyelje meg, hogy a **Dokumentum** \> **CstmrCdtTrfInitn** \> **PmtInf** \> **CdtTrfTxInf** \> **CdtrAcct** \> **Id** \> **IBAN** \> **BankIBAN** alatt található formátumelem úgy van konfigurálva, hogy megadja a szállítói számla IBAN-kódját a fizetési fájlba.

    ![A BankIBAN elem a Formátumtervező oldalon.](./media/er-data-debugger-format.png)

## <a name="appendix-2-configure-accounts-payable"></a><a name="appendix2"></a>2. melléklet: Kötelezettségek konfigurálása

### <a name="modify-a-vendor-property"></a>Szállítói tulajdonság módosítása

1. Nyissa meg a következőt: **Kötelezettségek** \> **Szállítók** \> **Minden szállító**.
2. Válassza ki a **DE-01002** szállítót és ezt követően a Műveleti paneé **Szállító** lapján, a **Beállítás** csoportban válassza a **Bankszámlák** elemet.
3. Az **Azonosítás** gyorslap **IBAN** mezőjébe, <a name="enteredIBANcode"></a>írja be a **GB33 BUKB 2020 1555 5555 55** értéket.
4. Válassza a **Mentés** lehetőséget.

![IBAN mező beállítva a Szállítói bankszámlák lapon.](./media/er-data-debugger-iban.png)

### <a name="set-up-a-method-of-payment"></a>Egy fizetési mód beállítása

1. Nyissa meg a következőt: **Kötelezettségek** \> **Kifizetés beállítása** \> **Fizetési módok**.
2. Válassza ki a **SEPA CT** fizetési módot.
3. Állítsa a **Fájlformátumok** gyorslap **Fájlformátumok** szakaszán az **Általános elektronikus exportformátum** beállítását **Igen** értékre.
4. Az **Exportálási formátum konfigurálása** mezőben válassza ki az **ISO20022-átutalás** ER-formátumot.
5. Válassza a **Mentés** lehetőséget.

![Fájlformátum beállításai a Fizetési módok lapon.](./media/er-data-debugger-payment-method.png)

### <a name="add-a-vendor-payment"></a>Szállítói kifizetés hozzáadása

1. Ugorjon a **Kötelezettségek** \> **Fizetések** \> **Szállítói kifizetés naplója** lehetőségre.
2. Adjon hozzá egy új kifizetési naplót.
3. Válassza ki a **Sorok** lehetőséget, és adjon hozzá egy új fizetési sort.
4. Válassza a **DE-01002** szállítót a **Számla** mezőben.
5. Adjon meg egy értéket a **Terhelés** mezőben.
6. A **Fizetési mód** mezőben válassza a **SEPA CT** lehetőséget.
7. Válassza a **Mentés** lehetőséget.

![A szállítói kifizetés hozzáadva a Szállítói fizetések lapon.](./media/er-data-debugger-payment-journal.png)

## <a name="appendix-3-process-a-vendor-payment"></a><a name="appendix3"></a>3. melléklet: Egy szállítói fizetés feldolgozása

1. Ugorjon a **Kötelezettségek** \> **Fizetések** \> **Szállítói kifizetés naplója** lehetőségre.
2. A **Szállítói fizetési napló** lapon válassza ki a korábban létrehozott fizetési naplót, majd válassza ki a **Sorok** lehetőséget.
3. Válassza ki a kifizetési sort, majd válassza a **Kifizetési állapota** \> **Nincs** elemet.
4. **Kifizetések létrehozása** kiválasztása.
5. A **Fizetési mód** mezőben válassza a **SEPA CT** lehetőséget.
6. A **Bankszámla** mezőben válassza a **DEMF OPER** lehetőséget.
7. A **Kifizetések létrehozása** párbeszédpanelen válassza az **OK** lehetőséget.
8. Az **Elektronikus jelentési paraméterek** párbeszédablakban válassza az **OK** lehetőséget.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]