---
title: ER-formátum módosítása egyéni elektronikus dokumentum generálásához
description: Ez a témakör azt mutatja be, hogyan lehet módosítani a Microsoft által biztosított elektronikus jelentéskészítési (ER) formátumot, hogy az egyedi elektronikus dokumentumot generáljon.
author: NickSelin
manager: AnnBe
ms.date: 06/22/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERParameters, ERDataModelDesigner, ERModelMappingTable, ERModelMappingDesigner, EROperationDesigner, ERVendorTable
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 220314
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 67763b29744c4262249ef1ec04e7df490b31fe5b
ms.sourcegitcommit: 1e6a7b50596eaf9d965e0155f3f2c50f7f50747e
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/22/2020
ms.locfileid: "3498097"
---
# <a name="adjust-an-er-format-to-generate-a-custom-electronic-document"></a>ER-formátum módosítása egyéni elektronikus dokumentum generálásához

[!include[banner](../includes/banner.md)]

Az ebben a témakörben ismertetett eljárások azt mutatják be, hogy a Rendszergazda vagy az Elektronikus jelentéskészítési funkció tanácsadói szerepkörével rendelkező felhasználó hogyan hajthatja végre ezeket a feladatokat:

- Az [Elektronikus jelentéskészítési (ER) keretrendszer](general-electronic-reporting.md) paramétereinek konfigurálása.
- A Microsoft által biztosított és a [szállítói kifizetések](../../../finance/cash-bank-management/tasks/vendor-payment-overview.md) feldolgozása során a fizetési fájlok előállításához használt ER-konfigurációk importálása.
- A Microsoft által biztosított szabvány ER-formátum konfiguráció egyéni verziójának létrehozása.
- Az egyéni ER-formátum konfigurációjának módosítása, hogy olyan kifizetési fájlokat generáljon, amelyek megfelelnek egy adott bank követelményeinek.
- A szabvány ER-formátum konfigurációnak az egyéni ER-formátum konfigurációban végzett módosításainak adoptálása.

A **GBSI** vállalatban valamennyi következő eljárást végrehajthatja. Nincs szükség kódolásra.

- [ER-keretrendszer konfigurálása](#ConfigureFramework)

    - [ER-paraméterek konfigurálása](#ConfigureParameters)
    - [ER-konfigurációszolgáltató aktiválása](#ActivateProvider)

        - [Az ER-konfigurációszolgáltatók listájának áttekintése](#ReviewProvidersList)
        - [Új ER-konfigurációszolgáltató hozzáadása](#ActivateProvider)
        - [ER-konfigurációszolgáltató aktiválása](#ActivateAddedProvider)

- [A szabvány ER-formátumkonfigurációk importálása](#ImportERSolution1)

    - [A szabvány ER-konfigurációk importálása](#ImportERFormat1)
    - [Importált ER-konfigurációk áttekintése](#ReviewImportedERSolution)

- [Szállítói fizetés előkészítése feldolgozásra](#PrepareVendorPayment)

    - [Banki információ hozzáadása egy szállítói fiókhoz](#AddBankAccount)
    - [Szállítói kifizetés bevitele](#EnterVendorPayment)

- [Szállítói kifizetés feldolgozása a szabvány ER-formátum használatával](#ProcessVendorPayment1)

    - [Elektronikus fizetési mód beállítása](#ConfigureMethodOfPayment1)
    - [Szállítói kifizetés feldolgozása](#ProcessPayment1)

- [A szabvány ER-formátum testreszabása](#CustomizeProvidedFormat)

    - [Egyéni formátum létrehozása](#DeriveProvidedFormat)
    - [Egyéni formátum szerkesztése](#ConfigureDerivedFormat)
    - [Egyéni formátum megjelölése futtathatóként](#MarkFormatRunnable)

- [Szállítói kifizetés feldolgozása az egyéni ER-formátum használatával](#ProcessVendorPayment2)

    - [Elektronikus fizetési mód beállítása](#ConfigureMethodOfPayment2)
    - [Szállítói kifizetés feldolgozása](#ProcessPayment2)

- [A szabvány ER-formátumkonfigurációk új verzióinak importálása](#ImportERSolution2)

    - [A szabvány ER-konfigurációk új verzióinak importálása](#ImportERFormat2)
    - [Importált ER-formátumkonfigurációk áttekintése](#ReviewImportedERFormat)

- [Az importált formátum új verziójában szereplő módosítások adoptálása egy egyéni formátumban](#AdoptNewBaseVersion)

    - [Egyéni formátum aktuális tervezet változatának befejezése](#CompleteDerivedFormat)
    - [Egyéni formátum alapjának áthelyezése új alapverzióra](#RebaseDerivedFormat)
    - [Szállítói kifizetés feldolgozása egy új alapra helyezett ER-formátum használatával](#ProcessPayment3)

- [További erőforrások](#References)

## <a name="configure-the-er-framework"></a><a id="ConfigureFramework"></a>ER-keretrendszer konfigurálása

Az Elektronikus jelentéskészítési funkció tanácsadó szerepkörében lévő felhasználóként konfigurálnia kell a minimálisan szükséges ER-paraméterek készletét, mielőtt elkezdené használni az ER-keretrendszert a szabványos formátum egyéni verziójának tervezéséhez.

### <a name="configure-er-parameters"></a><a id="ConfigureParameters"></a>ER-paraméterek konfigurálása

1. Ugorjon a **Szervezeti adminisztráció** \> **Munkaterületek** \> **Elektronikus jelentés** pontra.
2. A **Lokalizációs konfigurációk** oldalon, a **Kapcsolódó hivatkozások** szakaszban, válassza az **Elektronikus jelentéskészítés paraméterei** elemet.
3. Az **Elektronikus jelentéskészítési paraméterek** oldalon, az **Általános** lapon a **Tervezői mód engedélyezése** lehetőséget állítsa **Igen** értékre.
4. A **Mellékletek** lapon állítsa be a következő paramétereket:

    - A **Konfigurációk** mezőben válassza ki a **Fájl** típust az **USMF** vállalat esetében.
    - A **Feladatarchívum**, **Ideiglenes**, **Alap** és **Egyebek** mezőkben válassza a **Fájl** típust.

Az ER-paraméterekkel kapcsolatos további tudnivalókat lásd: [ER-keretrendszer konfigurálása](electronic-reporting-er-configure-parameters.md).

### <a name="activate-an-er-configuration-provider"></a><a id="ActivateProvider"></a>ER-konfigurációszolgáltató aktiválása

Minden hozzáadott ER-konfigurációt egy ER-konfigurációszolgáltató által birtokoltként kell megjelölni. Erre a célra az **Elektronikus jelentéskészítés** munkaterületen aktiválható ER-konfigurációszolgáltató használatos. Éppen ezért aktiválnia kell egy ER-konfigurációszolgáltatót az **Elektronikus jelentéskészítés** munkaterületen, mielőtt elkezdené az ER-konfigurációk hozzáadását vagy szerkesztését.

> [!NOTE]
> Csak az ER-konfiguráció tulajdonosa szerkesztheti. Éppen ezért aktiválnia kell a megfelelő ER-konfigurációszolgáltatót az **Elektronikus jelentéskészítés** munkaterületen, mielőtt elkezdené az ER-konfigurációk hozzáadását vagy szerkesztését.

#### <a name="review-the-list-of-er-configuration-providers"></a><a id="ReviewProvidersList"></a>Az ER-konfigurációszolgáltatók listájának áttekintése

1. Ugorjon a **Szervezeti adminisztráció** \> **Munkaterületek** \> **Elektronikus jelentés** pontra.
2. A **Lokalizációs konfigurációk** oldalon, a **Kapcsolódó hivatkozások** szakaszban, válassza a **Konfigurációszolgáltatók** elemet.
3. A **Konfigurációszolgáltatók tábla** oldalon minden szolgáltatói rekordnak egyedi neve és URL-címe van. Tekintse át az oldal tartalmát. Ha a már létezik a **Litware, Inc.** (`https://www.litware.com`) rekordja, hagyja ki a következő eljárást: [Új ER-konfigurációszolgáltató hozzáadása](#ActivateProvider).

#### <a name="add-a-new-er-configuration-provider"></a><a id="ActivateProvider"></a>Új ER-konfigurációszolgáltató hozzáadása

1. Ugorjon a **Szervezeti adminisztráció** \> **Munkaterületek** \> **Elektronikus jelentés** pontra.
2. A **Lokalizációs konfigurációk** oldalon, a **Kapcsolódó hivatkozások** szakaszban, válassza a **Konfigurációszolgáltatók** elemet.
3. A **Konfigurációszolgáltatók** oldalon válassza az **Új** elemet.
4. A **Név** mezőbe írja be a következőt: **Litware, Inc.**.
5. Az **Internetcím** mezőben adja meg a következőt: `https://www.litware.com`.
6. Válassza a **Mentés** lehetőséget.

#### <a name="activate-an-er-configuration-provider"></a><a id="ActivateAddedProvider"></a>ER-konfigurációszolgáltató aktiválása

1. Ugorjon a **Szervezeti adminisztráció** \> **Munkaterületek** \> **Elektronikus jelentés** pontra.
2. A **Lokalizációs konfigurációk** oldalon, a **Konfigurációszolgáltatók** szakaszban válassza ki a **Litware, Inc.** csempét, majd válassza a **Beállítás aktívként** lehetőséget.

További információért az ER-konfigurációszolgáltatókkal kapcsolatban tekintse át a [Konfigurációszolgáltatók létrehozása és megjelölése aktívként](tasks/er-configuration-provider-mark-it-active-2016-11.md) eljárást.

## <a name="import-the-standard-er-format-configurations"></a><a id="ImportERSolution1"></a>A szabvány ER-formátumkonfigurációk importálása

### <a name="import-the-standard-er-configurations"></a><a id="ImportERFormat1"></a>A szabvány ER-konfigurációk importálása

Ha a szabvány ER-konfigurációkat a Microsoft Dynamics 365 Finance jelenlegi példányához szeretné hozzáadni, importálnia kell azokat az adott példányhoz konfigurált ER [adattárból](general-electronic-reporting.md#Repository).

1. Ugorjon a **Szervezeti adminisztráció** \> **Munkaterületek** \> **Elektronikus jelentés** pontra.
2. A **Lokalizációs konfigurációk** oldalon, a **Konfigurációszolgáltatók** szakaszban válassza ki a **Microsoft** csempét, majd válassza ki az **Adattárak** lehetőséget a Microsoft szolgáltatóhoz tartozó adattárak listájának megtekintéséhez.
3. A **Konfigurációs adattárak** lapon válassza ki a **Globális** típusú adattárat, majd válassza a **Megnyitás** lehetőséget. Ha a rendszer felkéri a hitelesítésre a Regulatory Configuration Service szolgáltatáshoz való kapcsolódáshoz, kövesse a hitelesítési utasításokat.
4. A **Konfigurációs adattárak** oldalon, a bal oldali panel konfigurációs fájában válassza ki a **BACS (UK)** formátumkonfigurációt.
5. A **Verziók** gyorslapon válassza ki a kijelölt ER-formátumkonfiguráció **1.1**-es verzióját.
6. Kattintson az **Importálás** lehetőségre a kiválasztott verzió Globális tárból a jelenlegi Finance and Operations példányba történő letöltéséhez.

![Konfigurációk tárháza oldal](./media/er-quick-start2-import-solution1.png)

> [!TIP]
> Ha nem sikerül elérnie a [globális adattárat](er-download-configurations-global-repo.md), akkor lehetősége van ehelyett [letölteni konfigurációkat](download-electronic-reporting-configuration-lcs.md) a Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásból.

### <a name="review-the-imported-er-configurations"></a><a id="ReviewImportedERSolution"></a>Importált ER-konfigurációk áttekintése

1. Ugorjon a **Szervezeti adminisztráció** \> **Munkaterületek** \> **Elektronikus jelentés** pontra.
2. A **Lokalizációs konfigurációk** oldalon, a **Konfigurációk** szakaszban, válassza ki a **Jelentéskészítési konfiguráció** csempét.
3. A **Konfigurációk** oldalon, a bal oldali panelen található konfigurációk fájában bontsa ki a **Fizetési modell** elemet.
4. Figyelje meg, hogy a kiválasztott **BACS (UK)** ER-formátumon kívül más szükséges ER-konfigurációk importálása is megtörtént. Győződjön meg arról, hogy a konfigurációs fában a következő ER-konfigurációk érhetők el:

    - **Fizetési modell** – Ez a konfiguráció tartalmazza az [adatmodell](general-electronic-reporting.md#data-model-and-model-mapping-components) ER-összetevőt, amely a fizetési üzleti tartomány adatstruktúráját jelöli.
    - **Kifizetési modell leképezés 1611** – Ez a konfiguráció tartalmazza a [modell-leképezés](general-electronic-reporting.md#data-model-and-model-mapping-components) összetevőt, amely leírja, hogy az adatmodell milyen módon van kitöltve az alkalmazási adatokkal futási időben.
    - **BACS (UK)** – Ez a konfiguráció tartalmazza az ER-összetevők [formátum](general-electronic-reporting.md#FormatComponentOutbound) és formátumleképezés ER-összetevőit. A formátum összetevő meghatározza a jelentés elrendezését. A formátumleképezési összetevő tartalmazza a modell-adatforrást, és meghatározza, hogy a jelentés elrendezését milyen módon kell kitölteni ennek az adatforrásnak a használatával futásidőben.

![Konfigurációk oldala](./media/er-quick-start2-imported-solution1.png)

## <a name="prepare-a-vendor-payment-for-processing"></a><a id="PrepareVendorPayment"></a>Szállítói fizetés előkészítése feldolgozásra

### <a name="add-bank-information-for-a-vendor-account"></a><a id="AddBankAccount"></a>Banki információ hozzáadása egy szállítói fiókhoz

Hozzá kell adni banki információkat egy szállítói számlához, amelyre egy regisztrált fizetésben hivatkoznak.

1. Nyissa meg a következőt: **Kötelezettségek** \> **Szállítók** \> **Minden szállító**.
2. Válassza ki a **Minden szállító** oldalt, válassza ki a **GB_SI_000001** szállítói számlát, majd a Művelet panelen, a **Szállító** lap **Beállítás** csoportjában válassza ki a **Bankszámlák** lehetőséget.
3. A **Szállítói bankszámlák** oldalon válassza az **Új** parancsot, majd adja meg a következő adatokat:

    1. A **Bankszámla** mezőben adja meg a **GBP OPER** lehetőséget.
    2. A **Bankcsoportok** mezőben válassza ki a **BankGBP** elemet.
    3. A **Bankszámlaszám** mezőben adja meg a **202015** lehetőséget.
    4. A **SWIFT-kód** mezőben adja meg a <a id="DefineSWIFTCode"></a>**CHASDEFXXXX** értéket.
    5. Az **IBAN** mezőben adja meg a **GB33BUKB20201555555555** értéket.
    6. Az **Útvonalszám** mezőben tartsa meg az <a id="DefineRoutingNumber"></a>**123456** alapértelmezett értéket.

    ![Szállítói bankszámlák oldal](./media/er-quick-start2-bank-account.png)

4. Válassza a **Mentés** lehetőséget.
5. Zárja be a lapot.
6. A **Minden szállító** lapon nyissa meg a **GB_SI_000001** szállítói számlát.
7. Ha szükséges, a szállítói részletek oldalon válassza a **Szerkesztés** parancsot az oldal szerkeszthetővé tételéhez.
8. A **Fizetés** gyorslap **Bankszámla** mezőjében válassza ki a **GBP OPER** elemet.

    ![Szállító részletei oldal](./media/er-quick-start2-bank-account-reference.png)

9. Válassza a **Mentés** lehetőséget.
10. Zárja be a lapot.

### <a name="enter-a-vendor-payment"></a><a id="EnterVendorPayment"></a>Szállítói kifizetés bevitele

Új szállítói kifizetés megadásához a [fizetési javaslatot](https://docs.microsoft.com/dynamics365/finance/accounts-payable/create-vendor-payments-payment-proposal) kell használnia.

1. Ugorjon a **Kötelezettségek** \> **Fizetések** \> **Szállítói kifizetés naplója** lehetőségre.
2. A **Szállító kifizetési naplója** oldalon válassza az **Új** elemet.
3. A **Név** mezőbe válassza a **VendPay** lehetőséget.
4. **Sorok** kiválasztása.
5. Válassza a **Kifizetési javaslat** \> **Fizetési javaslat létrehozása** elemet.
6. A **Szállítói fizetési javaslat** párbeszédpanelen konfigurálja azokat a feltételeket, amelyek csak az **GB_SI_000001** szállítói számlához tartozó rekordok szűréséhez szükségesek, majd kattintson az **OK** gombra.
7. Válassza ki a **00000007_Inv** számlához tartozó sort, majd válassza a **Kifizetés létrehozása** lehetőséget.

    ![Szállítói fizetési javaslatok párbeszédpanel](./media/er-quick-start2-payment-proposal.png)

8. Győződjön meg róla, hogy a megadott fizetés az **Elektronikus** fizetési mód használatára van beállítva.

    ![Szállítói kifizetések oldala](./media/er-quick-start2-payment-line.png)

## <a name="process-a-vendor-payment-by-using-the-standard-er-format"></a><a id="ProcessVendorPayment1"></a>Szállítói kifizetés feldolgozása a szabvány ER-formátum használatával

### <a name="set-up-the-electronic-payment-method"></a><a id="ConfigureMethodOfPayment1"></a>Elektronikus fizetési mód beállítása

Az elektronikus fizetési módot úgy kell konfigurálni, hogy az az importált ER-formátum konfigurációját használja.

1. Nyissa meg a következőt: **Kötelezettségek** \> **Kifizetés beállítása** \> **Fizetési módok**.
2. A **Fizetési módok – szállítók** oldalon válassza ki az **Elektronikus** fizetési módot a bal oldali ablaktáblán.
3. Válassza ki a **Szerkesztés** opciót.
4. Adja meg a **Fájlformátumok** gyorslap **Általános elektronikus export formátum** beállítását**Igen** értékre.
5. Az **Exportálási formátum konfigurálása** mezőben válassza ki az **BACS (UK)** formátumkonfigurációt.

    ![Fizetési módok - szállítók oldal](./media/er-quick-start2-method-of-payment1.png)

6. Válassza a **Mentés** lehetőséget.

### <a name="process-a-vendor-payment"></a><a id="ProcessPayment1"></a>Szállítói kifizetés feldolgozása

1. Ugorjon a **Kötelezettségek** \> **Fizetések** \> **Szállítói kifizetés naplója** lehetőségre.
2. A **Szállítói fizetési napló** lapon válassza ki a korábban hozzáadott fizetési naplót, majd válassza ki a **Sorok** lehetőséget.
3. A **Szállítói kifizetések** oldalon válassza a **Kifizetések létrehozása** elemet.
4. A **Kifizetések létrehozása** párbeszédpanelen adja meg a következő adatokat:

    - A **Fizetési mód** mezőben válassza az **Elektronikus** lehetőséget.
    - A **Bankszámla** mezőben válassza a **GBSI OPER** lehetőséget.

5. Válassza ki az **OK** lehetőséget.
6. Az **Elektronikus jelentések paraméterei** párbeszédpanelen állítsa a **Nyomtatási vezérlő jelentés** beállítását **Igen** értékre, majd válassza az **OK** gombot.

    ![Elektronikus jelentés paraméterei – párbeszédoldal](./media/er-quick-start2-payment-dialog1.png)

    > [!NOTE]
    > A kifizetési fájlon kívül ellenőrzési jelentés is létrehozható.

7. Töltse le a zip-fájlt, majd csomagolja ki belőle a következő fájlokat:

    - Az ellenőrzési jelentést Excel-formátumban
    - A fizetési fájl TXT-formátumban

        Figyelje meg, hogy a megadott ER-formátum [struktúrájával](#PositionRoutingNumber) összhangban a létrehozott fájl kifizetési sora a konfigurált bankszámlához [megadott](#DefineRoutingNumber) útválasztási számmal kezdődik.

        ![Fizetési fájl TXT-formátum](./media/er-quick-start2-payment-file1.png)

## <a name="customize-the-standard-er-format"></a><a id="CustomizeProvidedFormat"></a>A szabvány ER-formátum testreszabása

Az ebben a részben megjelenő példa esetében a Microsoft által biztosított ER-konfigurációkat kell használni a BACS formátumú szállítói kifizetési fájlok létrehozásához, de a megfelelő testreszabással kell ellátni őket egy adott bank követelményeinek támogatásához. Azt is szeretné, hogy a saját egyéni formátuma frissíthető legyen, ha elérhetővé válnak az ER-konfigurációk új verziói. A frissítést azonban a lehető legalacsonyabb költséggel szeretné elvégezni.

Ebben az esetben a Litware, Inc. képviselőjeként létre kell hozni (származtatni) egy új ER-formátumkonfigurációt a **BACS (UK)** Microsoft által megadott konfiguráció alapján.

### <a name="create-a-custom-format"></a><a id="DeriveProvidedFormat"></a>Egyéni formátum létrehozása

1. Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**.
2. A **Konfigurációk** oldalon, a bal oldali panelen található konfigurációk fájában bontsa ki a **Fizetési modell** elemet, majd válassza a **BACS (UK)** lehetőséget. A Litware, Inc. ennek az ER-formátumkonfigurációnak az 1.1-es verzióját fogja használni az egyéni verzió alapjaként.
3. A **Konfiguráció létrehozása** kiválasztásával megnyithatja a legördülő párbeszédablakot. A párbeszédablak segítségével új konfigurációt hozhat létre az egyéni fizetési formátumra vonatkozóan.
4. Az **Új** mezőcsoportban válassza ki a **Származtatás innen: BACS (UK), Microsoft** lehetőséget.
5. A **Név** mezőbe írja be a következőt: **BACS (UK egyéni)**.

    ![Konfiguráció létrehozása legördülő párbeszédpanel](./media/er-quick-start2-add-derived-format.png)

6. Válassza a **Konfiguráció létrehozása** lehetőséget.

A **BACS (UK egyéni)** ER-formátum konfigurációjának 1.1.1-es verziója jön létre. Ez a verzió **Piszkozat** [állapottal](general-electronic-reporting.md#component-versioning) rendelkezik, és szerkeszthető. Az egyéni ER-formátum jelenlegi tartalma megegyezik a Microsoft által biztosított formátum tartalmával.

![Konfigurációk oldala](./media/er-quick-start2-derived-format-configuration1.png)

### <a name="edit-a-custom-format"></a><a id="ConfigureDerivedFormat"></a>Egyéni formátum szerkesztése

Az egyéni formátumot úgy kell konfigurálni, hogy megfeleljen a bankspecifikus követelményeknek. Előfordulhat például, hogy a bank előírja, hogy a létrejövő kifizetési fájlok között szerepel egy olyan Society for Worldwide Interbank Financial Telecommunication (SWIFT) kód, amelyhez a feldolgozott szállítói kifizetésben az ügynök szerepkör van hozzárendelve. A SWIFT-kódok olyan nemzetközi banki kódok, amelyek világszerte meghatározott bankokat határoznak meg. Más néven banki azonosító kódoknak (BIC) nevezik őket. A SWIFT-kódnak 11 karakter hosszúnak kell lennie, és meg kell adni a létrehozott kifizetési fájlok minden fizetési sora kezdetén.

1. Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**.
2. A **Konfigurációk** oldalon, a bal oldali panelen található konfigurációk fájában bontsa ki a **Fizetési modell** elemet, majd válassza a **BACS (UK egyéni)** lehetőséget.
3. A **Verziók** gyorslapon válassza ki a kijelölt konfiguráció **1.1.1**-es verzióját.
4. Válassza a **Tervező** lehetőséget.
5. A **Formátumtervező** oldalon válassza a **Részletek megjelenítése** lehetőséget, ha további tájékoztatást szeretne látni a formátumelemekről.
6. Bontsa ki és tekintése át a következő elemeket:

    - A **Mappa** típusú **BACSReportsFolder** elemet. Ez az elem a ZIP formátumú kimenet létrehozásához használatos.
    - A **Fájl** típusú **fájl** elemet. Ez az elem a TXT formátumú kifizetési fájl létrehozásához használatos.
    - A **Sorozat** típusú **tranzakciók** elemet. Ez az elem a kifizetési fájl egyszeres kifizetési sorának létrehozásához használatos.
    - A **Sorozat** típusú **tranzakció** elemet. Ez az elem az egyszeres kifizetési sor egyes mezőinek létrehozásához használatos.

7. Válassza ki a **tranzakció** elemet.

    ![Tranzakció elem az ER-művelettervezőben](./media/er-quick-start2-derived-format0.png)

    > [!NOTE]
    > A megadott jelentés úgy van beállítva, hogy <a id="PositionRoutingNumber"></a>minden kifizetési sor a banki regisztrációs útválasztási kezdődjön. Erre a célra a **vendBankRouteNum** formátumelem használatos. 

8. Válassza a **Hozzáadás** lehetőséget, majd válassza ki a hozzáadni kívánt formátumelem **Szöveg\\Karakterlánc** típusát:

    1. A **Név** mezőbe írja be a következőt: **vendBankSWIFT**.
    2. Adja meg a **11** értéket a **Minimális hossz** mezőben.
    3. Adja meg a **11** értéket a **Maximális hossz** mezőben.
    4. Válassza ki az **OK** lehetőséget.

    > [!NOTE]
    > A **vendBankSWIFT** elem a létrejövő fájlokban a szállítói bank SWIFT-kódjának megadására szolgál.

9. Válassza ki a **vendBankSWIFT** elemet a formátumstruktúra fájában.
10. Válassza **Mozgatás felfelé** lehetőséget a kiválasztott formátumelem egy szinttel feljebb helyezéséhez. Ismételje meg ezt a lépést addig, amíg a **vendBankSWIFT** elem a <a id="PositionSWIFTCode"></a>szülő **tranzakció** elem alatti első elem lesz.

    ![VendBankSWIFT, mint a tranzakció alatti első elem az ER-művelettervezőben](./media/er-quick-start2-derived-format1.png)

11. Miközben a **vendBankSWIFT** még mindig ki van választva a szerkezeti fában, válassza ki a **Leképezés** lapot, majd bontsa ki a **modell** adatforrást.
12. Bontsa ki a **model.Payment** \> **model.Payment.CreditorAgent** elemet, majd válassza a **model.Payment.CreditorAgent.BICFI** adatforrásmezőt. Ez az adatforrásmező kiteszi annak a szállítói banknak a SWIFT-kódját, amely a feldolgozott szállítói kifizetésben szereplő ügynöki szerepkörhöz van rendelve.
13. Válassza a **Bind** elemet. A **vendBankSWIFT** formátumelem most a **model.Payment.CreditorAgent.BICFI** adatforrásmezőhöz van kötve, így a rendszer a létrejövő kifizetési fájlokban rögzíti a SWIFT-kódokat.

    ![Az ER-művelettervező model.Payment.CreditorAgent.BICFI adatforrásmezőjéhez kötött vendBankSWIFT formátumelem](./media/er-quick-start2-derived-format2.png)

14. Válassza a **Mentés** lehetőséget.
15. Zárja be a tervezőoldalt.

### <a name="mark-a-custom-format-as-runnable"></a><a id="MarkFormatRunnable"></a>Egyéni formátum megjelölése futtathatóként

Miután létrehozta az egyéni formátum első verzióját, és az a **Piszkozat** állapottal rendelkezik, tesztelés céljából futtathatja azt. A jelentés futtatásához a szállítói kifizetést az egyéni ER-formátumra hivatkozó fizetési mód használatával kell feldolgoznia. Alapértelmezésben, amikor egy ER-formátumot hív meg az alkalmazásból, csak a **Befejeződött** vagy **Megosztott** állapotú verziókat [veszi figyelembe](general-electronic-reporting.md#component-versioning) a rendszer. Ez a viselkedés segít megakadályozni a befejezetlen konstrukciókkal rendelkező ER-formátumok használatát. A teszt futtatásakor azonban kényszerítheti az alkalmazást egy **Piszkozat** állapottal rendelkező ER-formátumverzió használatára. Ily módon módosíthatja az aktuális formátum verziószámát, ha bármilyen módosítás szükséges. További információ: [Alkalmazhatóság](electronic-reporting-destinations.md#applicability).

Ha egy ER-formátum piszkozat verzióját kívánja használni, ennek kifejezett módon be kell jelölnie az ER-formátumot.

1. Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**.
2. A **Konfigurációk** oldal műveleti ablaktábláján, a **Konfigurációk** lapon, a **Speciális beállítások** csoportban válassza a **Felhasználói paraméterek** lehetőséget.
3. A **Felhasználói paraméterek** párbeszédpanelen állítsa a **Futtatási beállítások** beállítását **Igen** értékre, majd kattintson az **OK** gombra.
4. Ha szükséges, a **Szerkesztés** gombbal az aktuális lapot szerkeszthetőre állíthatja.
5. A bal oldali ablak konfigurációs fáján válassza a **BACS (UK custom)** lehetőséget.
6. Állítsa a **Piszkozat futtatása** beállítást **Igen** lehetőségre.

    ![Piszkozat futtatása beállítás a Konfigurációk lapon](./media/er-quick-start2-derived-format-configuration2.png)

## <a name="process-a-vendor-payment-by-using-the-custom-er-format"></a><a id="ProcessVendorPayment2"></a>Szállítói kifizetés feldolgozása az egyéni ER-formátum használatával

### <a name="set-up-the-electronic-payment-method"></a><a id="ConfigureMethodOfPayment2"></a>Elektronikus fizetési mód beállítása

Az elektronikus fizetési módot úgy kell konfigurálni, hogy a rendszer a szállítói kifizetéseket a saját egyéni ER-formátumával dolgozza fel.

1. Nyissa meg a következőt: **Kötelezettségek** \> **Kifizetés beállítása** \> **Fizetési módok**.
2. A **Fizetési módok – szállítók** oldalon válassza ki az **Elektronikus** fizetési módot a bal oldali ablaktáblán.
3. Válassza ki a **Szerkesztés** opciót.
4. Adja meg a **Fájlformátum** gyorslap **Általános elektronikus export formátum** beállítását **Igen** értékre.
5. Az **Exportálási formátum konfigurálása** mezőben válassza ki az **BACS (UK egyéni)** formátumkonfigurációt.

    ![Fizetési módok - szállítók oldal](./media/er-quick-start2-method-of-payment2.png)

6. Válassza a **Mentés** lehetőséget.

### <a name="process-a-vendor-payment"></a><a id="ProcessPayment2"></a>Szállítói kifizetés feldolgozása

1. Ugorjon a **Kötelezettségek** \> **Fizetések** \> **Szállítói kifizetés naplója** lehetőségre.
2. A **Szállítói fizetési napló** lapon válassza ki a korábban létrehozott fizetési naplót.
3. **Sorok** kiválasztása.
4. A **Szállítói kifizetések** oldalon, a rács felett válassza a **Kifizetési állapot** \> **Nincs** lehetőséget.
5. Válassza a **Fizetés létrehozása** lehetőséget.
6. A **Kifizetések létrehozása** párbeszédpanelen adja meg a következő adatokat:

    - A **Fizetési mód** mezőben válassza az **Elektronikus** lehetőséget.
    - A **Bankszámla** mezőben válassza a **GBSI OPER** lehetőséget.

7. Válassza ki az **OK** lehetőséget.
8. Az **Elektronikus jelentések paraméterei** párbeszédpanelen állítsa a **Nyomtatási vezérlő jelentés** beállítását **Igen** értékre, majd válassza az **OK** gombot.

    > [!NOTE]
    > A kifizetési fájlon kívül csak ellenőrzési jelentést hozhat létre.

9. Töltse le a zip-fájlt, majd csomagolja ki belőle a következő fájlokat:

    - Az ellenőrzési jelentést Excel-formátumban
    - A fizetési fájl TXT-formátumban

        Figyelje meg, hogy az egyéni ER-formátum struktúrájával összhangban a létrehozott fájl kifizetési sora most azzal a SWIFT-kóddal [kezdődik](#PositionSWIFTCode), amelyet azon szállító bankszámláján [rögzítettek](#DefineSWIFTCode), amelynek a kifizetését már feldolgozták.

        ![Fizetési fájl TXT-formátum](./media/er-quick-start2-payment-file2.png)

## <a name="import-new-versions-of-the-standard-er-format-configurations"></a><a id="ImportERSolution2"></a>A szabvány ER-formátumkonfigurációk új verzióinak importálása

Az ebben a részben megjelenő példa esetében értesítést kap a Tudásbázis következő cikkéről: [KB3763330](https://fix.lcs.dynamics.com/Issue/Details?kb=3182046). Ez a tájékoztatás tájékoztatja a **BACS (UK)** Microsoft által közzétett ER-formátum új verziójáról. Az ellenőrzési jelentésen kívül ez az új verzió lehetővé teszi a felhasználók számára a kifizetési bizonylatokról szóló jelentés és a részvételi megjegyzés jelentés létrehozását a szállítói kifizetések feldolgozásakor. Hasznos lehet ennek a funkciónak a használata.

### <a name="import-new-versions-of-the-standard-er-configurations"></a><a id="ImportERFormat2"></a>A szabvány ER-konfigurációk új verzióinak importálása

Ha az ER-konfigurációk új verzióit szeretné hozzáadni az aktuális Finance-példányhoz, importálnia kell azokat a konfigurált ER-[adattárból](general-electronic-reporting.md#Repository).

1. Ugorjon a **Szervezeti adminisztráció** \> **Munkaterületek** \> **Elektronikus jelentés** pontra.
2. A **Lokalizációs konfigurációk** oldalon, a **Konfigurációszolgáltatók** szakaszban válassza ki a **Microsoft** csempét, majd válassza ki az **Adattárak** lehetőséget a Microsoft szolgáltatóhoz tartozó adattárak listájának megtekintéséhez.
3. A **Konfigurációs adattárak** lapon válassza ki a **Globális** típusú adattárat, majd válassza a **Megnyitás** lehetőséget. Ha a rendszer felkéri a hitelesítésre a Regulatory Configuration Service szolgáltatáshoz való kapcsolódáshoz, kövesse a hitelesítési utasításokat.
4. A **Konfigurációs adattárak** oldalon, a bal oldali panel konfigurációs fájában válassza ki a **BACS (UK)** formátumkonfigurációt.
5. A **Verziók** gyorslapon válassza ki a kijelölt ER-formátumkonfiguráció **3.3**-es verzióját.
6. Kattintson az **Importálás** lehetőségre a kiválasztott verzió Globális tárból a jelenlegi Finance and Operations példányba történő letöltéséhez.

![Konfigurációk tárháza oldal](./media/er-quick-start2-import-solution2.png)

> [!TIP]
> Ha nem sikerül elérnie a [globális adattárat](er-download-configurations-global-repo.md), akkor lehetősége van ehelyett [letölteni konfigurációkat](download-electronic-reporting-configuration-lcs.md) a Lifecycle Services (LCS) szolgáltatásból.

### <a name="review-the-imported-er-format-configurations"></a><a id="ReviewImportedERFormat"></a>Importált ER-formátumkonfigurációk áttekintése

1. Ugorjon a **Szervezeti adminisztráció** \> **Munkaterületek** \> **Elektronikus jelentés** pontra.
2. A **Lokalizációs konfigurációk** oldalon, a **Konfigurációk** szakaszban, válassza ki a **Jelentéskészítési konfiguráció** csempét.
3. A **Konfigurációk** oldalon, a bal oldali panelen található konfigurációk fájában bontsa ki a **Fizetési modell** elemet, majd válassza a **BACS (UK)** lehetőséget.
4. Válassza ki a **Verziók** gyorslap **3.3.** verzióját.
5. Válassza a **Tervező** lehetőséget.
6. A **Formátumtervező** oldalon bontsa ki a **BACSReportsFolder** formátumelemet.
7.  Figyelje meg, hogy a 3.3-as verzió tartalmazza a **PaymentAdviceReport** formátumelemet, amely a szállítói kifizetések feldolgozásakor a kifizetési bizonylatokról szóló jelentés létrehozásához használatos.

    ![PaymentAdviceReport formátumelem az ER-művelettervezőben](./media/er-quick-start2-imported-solution2.png)

8. Zárja be a tervezőoldalt.

## <a name="adopt-the-changes-in-the-new-version-of-an-imported-format-in-a-custom-format"></a><a id="AdoptNewBaseVersion"></a>Az importált formátum új verziójában szereplő módosítások adoptálása egy egyéni formátumban

### <a name="complete-the-current-draft-version-of-a-custom-format"></a><a id="CompleteDerivedFormat"></a>Egyéni formátum aktuális tervezet változatának befejezése

Ha meg szeretné tartani az egyéni formátum jelenlegi állapotát, fejezze be az 1.1.1-es verziót úgy, hogy az állapotát a **Piszkozat** értékről **Befejezett** értékre módosítja.

1. Ugorjon a **Szervezeti adminisztráció** \> **Munkaterületek** \> **Elektronikus jelentés** pontra.
2. A **Lokalizációs konfigurációk** oldalon, a **Konfigurációk** szakaszban, válassza ki a **Jelentéskészítési konfiguráció** csempét.
3. A **Konfigurációk** oldalon, a bal oldali panelen található konfigurációk fájában bontsa ki a **Fizetési modell** elemet, majd a **BACS (UK)** eleme, és válassza a **BACS (UK egyéni)** lehetőséget.
4. Válassza a **Verziók** gyorslap **Állapot módosítása** \> **Befejezés** elemét, majd kattintson az **OK** gombra.

Az 1.1.1-es verzió állapota a **Piszkozat** értékről a **Befejezett** értékre módosul , és a verzió írásvédett lesz. Az új, szerkeszthető verzió (1.1.2) **Piszkozat** állapottal kerül hozzáadásra. Ennek a verziónak a használatával további változtatásokat hajthat végre a saját egyéni ER-formátumában.

### <a name="rebase-a-custom-format-to-a-new-base-version"></a><a id="RebaseDerivedFormat"></a>Egyéni formátum alapjának áthelyezése új alapverzióra

A 3.3-as verziójú **BACS (UK)** formátum új funkcióinak a testreszabásában történő használatához módosítania kell a **BACS (UK egyéni)** egyéni konfiguráció alapkonfigurációját. Ennek a folyamatnak a neve [új alap](general-electronic-reporting.md#upgrading-a-format-selecting-a-new-version-of-base-format-rebase) megadása. Használja az új 3.3-as verziót a **BACS (UK)** 1.1-es verziója helyett.

1. Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**.
2. A **Konfigurációk** oldalon, a bal oldali panelen található konfigurációk fájában bontsa ki a **Fizetési modell** elemet, majd válassza a **BACS (UK egyéni)** lehetőséget.
3. A **Verziók** gyorslapon válassza az **1.1.2** verziót, majd válassza az **Új alap** lehetőséget.
4. Válassza az **Új alap** párbeszédpanelt **Cél verzió** mezőben, válassza az alapkonfiguráció **3.3** verzióját, és alkalmazza azt új alapként, valamint használja a konfiguráció frissítésére.

    ![Új alap párbeszédpanel](./media/er-quick-start2-rebase1.png)

5. Válassza ki az **OK** lehetőséget.
6. Figyelje meg, hogy a piszkozat verziójának száma **1.1.2**-ről **3.3.2**-re módosult az alapverzió változásainak megfelelően.

    A rendszer bizonyos ütközéseket észlelt az egyéni verzió és az új alapverzió egyesítésekor, mivel néhány formátummódosítást nem lehet automatikusan egyesíteni.

    ![Új alapra helyezett konfiguráció ütközésekkel a Konfigurációk oldalon](./media/er-quick-start2-rebase2.png)

    Ha ütközések merülnek fel, akkor azokat manuálisan kell megoldani a formátumtervező programban.

7. Válassza ki a **Verziók** gyorslap **3.3.2.** verzióját.
8. Válassza a **Tervező** lehetőséget.
9. A **Formátumtervező** lap **Részletek** gyorslapján jelöljön ki egy új alap ütközési rekordot, majd válassza az **Alapérték alkalmazása** lehetőséget.

    ![Új alap ütközési rekord az ER-művelettervezőben](./media/er-quick-start2-rebase3.png)

10. Válassza a **Mentés** lehetőséget.

    Az új alap ütközési rekordnak ezután többé nem kellene megjelennie **Részletek** gyorslapon.

    ![Feloldott ütközés az ER-művelettervezőben](./media/er-quick-start2-rebase4.png)

    > [!NOTE]
    > Az ütközést úgy oldotta fel, hogy megerősítette, hogy az alapmodell 3. verzióját kell használni ebben az ER-formátumban.

11. Bontsa ki a **BACSReportsFolder** \> **fájl** \> **tranzakciók** \> **tranzakció** elemet.
12. A **Feltérképezés** lapon figyelje meg, hogy az egyéni ER-formátumának 3.3.2-es verziója tartalmazza mind a testreszabását (a **vendBankSWIFT** formátumelemet és annak kötését), valamint a Microsoft által biztosított alap ER-formátum 3.3-as verziójának új funkcionalitását (a **PaymentAdviceReport** formátumú elem a beágyazott elemekkel és a konfigurált kötésekkel együtt). Csak néhány egérkattintással adoptálta az új alapverzió módosításait, egyesítve azokat a testreszabásával.

    ![Egyesített formátum az ER-művelettervezőben](./media/er-quick-start2-rebase5.png)

13. Zárja be a tervezőoldalt.

> [!NOTE]
> Az új alap művelet visszafordítható. Ha az új alapra helyezést vissza szeretné vonni, válassza ki a **BACS (UK egyéni)** formátum **1.1.1**-es verzióját a **Verziók** gyorslapon, majd válassza ki a **Verzió beszerzése** elemet. A 3.3.2-es verziót ezután a rendszer 1.1.2-esként számozza fel, és az 1.1.2-es piszkozat verzió tartalma megegyezik a 1.1.1-es verzió tartalmával.

### <a name="process-a-vendor-payment-by-using-a-rebased-er-format"></a><a id="ProcessPayment3"></a>Szállítói kifizetés feldolgozása egy új alapra helyezett ER-formátum használatával

1. Ugorjon a **Kötelezettségek** \> **Fizetések** \> **Szállítói kifizetés naplója** lehetőségre.
2. A **Szállítói fizetési napló** lapon válassza ki a korábban létrehozott fizetési naplót.
3. **Sorok** kiválasztása.
4. A **Szállítói kifizetések** oldalon, a rács felett válassza a **Kifizetési állapot** \> **Nincs** lehetőséget.
5. Válassza a **Fizetés létrehozása** lehetőséget.
6. A **Kifizetések létrehozása** párbeszédpanelen adja meg a következő adatokat:

    - A **Fizetési mód** mezőben válassza az **Elektronikus** lehetőséget.
    - A **Bankszámla** mezőben válassza a **GBSI OPER** lehetőséget.

7. Válassza ki az **OK** lehetőséget.
8. Az **Elektronikus jelentés paraméterei** párbeszédpanelen adja meg a következő adatokat:

    - Állítsa az **Ellenőrzési jelentés nyomtatása** opciót **Igen** értékre.
    - Állítsa az **Kifizetési bizonylat nyomtatása** opciót **Igen** értékre.

    ![Elektronikus jelentés paraméterei – párbeszédablak](./media/er-quick-start2-payment-dialog2.png)

    > [!NOTE]
    > A kifizetési fájlon kívül már az ellenőrzési jelentés és a kifizetési bizonylat jelentés is létrehozható.

9. Válassza ki az **OK** lehetőséget.
10. Töltse le a zip-fájlt, majd csomagolja ki belőle a következő fájlokat:

    - Az ellenőrzési jelentést Excel-formátumban
    - Az kifizetési bizonylat jelentést Excel-formátumban

        ![Kifizetési bizonylat jelentést Excel-formátumban](./media/er-quick-start2-payment-advice-report.png)

    - A fizetési fájl TXT-formátumban

        Figyelje meg, hogy a létrehozott fájl kifizetési sora azzal a SWIFT-kóddal kezdődik, amelyet azon szállító bankszámláján rögzítettek, amelynek a kifizetését már feldolgozták.

        ![Fizetési fájl TXT-formátum](./media/er-quick-start2-payment-file3.png)

## <a name="additional-resources"></a><a id="References"></a>További erőforrások

- [Elektronikus jelentések áttekintése](general-electronic-reporting.md)
- [ER-konfigurációk letöltése a Lifecycle Services szolgáltatásból](download-electronic-reporting-configuration-lcs.md)
- [ER-konfigurációk letöltése a konfigurációs szolgáltatás globális tárából](er-download-configurations-global-repo.md)
