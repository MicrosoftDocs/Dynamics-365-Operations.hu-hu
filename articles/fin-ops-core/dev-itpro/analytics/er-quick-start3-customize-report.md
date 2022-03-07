---
title: Elektronikus jelentéskészítési konfigurációk testreszabása elektronikus bizonylat előállításához
description: Ez a témakör azt mutatja be, hogyan lehet testreszabni a Microsoft által biztosított elektronikus jelentéskészítési (ER) konfigurációkat, amelyekkel egyedi elektronikus dokumentumok generálhatók.
author: NickSelin
manager: AnnBe
ms.date: 10/21/2020
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
ms.openlocfilehash: 2a0cc308e2e3c7f42295a6170c4f709a835c5c84
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/09/2021
ms.locfileid: "5566126"
---
# <a name="customize-electronic-reporting-configurations-to-generate-an-electronic-document"></a>Elektronikus jelentéskészítési konfigurációk testreszabása elektronikus bizonylat előállításához

[!include[banner](../includes/banner.md)]

Az [elektronikus jelentéskészítési (ER) keretrendszer](general-electronic-reporting.md) segítségével feltöltheti a Microsoft által a Microsoft Dynamics 365 Finance példányában biztosított ER-[konfigurációkat](general-electronic-reporting.md#Configuration). Ily módon a Microsoft által biztosított konfigurációk az elektronikus Ügyfélszámlák (e-számlák) létrehozásához használt ER-megoldásként szolgálhatnak. Ez az ER-megoldás az egyéni ER-megoldások az egyéni adatbázismezők eléréséhez való konfigurációjára használható, és olyan e-számlák létrehozására, amelyek megfelelnek a megadott követelményeknek, anélkül, hogy szerkeszteni kellene a forráskódot.

## <a name="overview"></a>Áttekintés

Az ebben a témakörben szereplő példa esetében meg kell adnia egy szövetségi adóazonosító kódot új egyéni attribútumként minden olyan Ügyfélnek, akinek elektronikusan számláz. Éppen ezért a jelenleg használt számla szerkezetét testre kellszabni egy olyan új elem hozzáadásával, amelyet minden létrehozott e-számlán ki kell tölteni az áfakód alapján.

Az ebben a témakörben ismertetett eljárások azt mutatják be, hogy a Rendszergazda, az Elektronikus jelentéskészítési fejlesztő vagy az Elektronikus jelentéskészítési funkcionális tanácsadói szerepkörével rendelkező felhasználó hogyan hajthatja végre a következő feladatokat a Finance példányban:

- [ER-paraméterek minimális csoportjának konfigurálása, amely az ER-keretrendszer elindításához szükséges](#ConfigureER).
- [A standard ER-konfigurációk kezdeti verzióinak importálása, amelyek meg vannak adva az e-számla létrehozásához](#ImportERConfigurations1).
- [Kinnlevőségek paraméterek konfigurálása a standard ER-konfigurációk használatbavételéhez](#ConfigureAR1).
- [Jogi személy paramétereinek konfiguálása az ügyfeleknek való számlázáshoz](#ConfigureLE).
- [Ügyfélrekord előkészítése az elektronikus számlázáshoz](#ConfigureCustomer1).
- [Ügyfélszámla hozzáadása, feladása és elküldése a szabványos ER-konfigurációk segítségével](#ProcessInvoice1).
- [Egyéni adatbázismező hozzáadása a ügyfelekhez tartozó Szövetségi adóazonosító kód kezeléséhez](#AddCustomField).
- [A ER-metaadatok frissítésa az ER-modell-leképezési tervezőre vonatkozó adatbázis-módosítások engedélyezéséhez](#RefreshERMetadata).
- [Az egyéni ER-konfigurációk tervezése az új áfakódot tartalmazó e-számlák létrehozásához](#DesignCustomERConfigurations).
- [Kinnlevőségek paraméterek konfigurálása az egyéni ER-konfigurációk használatbavételéhez](#ConfigureAR2).
- [Ügyfélrekord frissítése az elektronikus számlázáshoz](#ConfigureCustomer2).
- [Ügyfélszámla hozzáadása, feladása és elküldése az egyéni ER-konfigurációk segítségével](#ProcessInvoice2).
- [A standard ER-konfigurációk új verzióinak importálása, amelyek meg vannak adva az e-számla létrehozásához](#ImportERConfigurations2).
- [A standard ER-konfigurációk új verzióira vonatkozó módosítások elfogadása az egyéni ER-konfigurációkban](#RebaseCustomERConfigurations).
- [Ügyfélszámla hozzáadása, feladása és elküldése az egyéni ER-konfigurációk új verziói segítségével](#ProcessInvoice3).

Ezen eljárások mindegyikét a **DEMF** vállalatban hajthatja végre.

## <a name="configure-the-er-framework"></a><a name="ConfigureER"></a>ER-keretrendszer konfigurálása

Elektronikus jelentések funkcióival foglalkozó tanácsadó vagy Elektronikus jelentések fejlesztője szerepkörrel rendelkező felhasználóként konfigurálnia kell az ER-paraméterek minimális csoportját. Ezt követően elkezdheti használni az ER keretrendszerét az e-számlák előállítására használt, az ER-megoldásban használt normál konfigurációk egyéni verzióinak tervezéséhez.

### <a name="configure-er-parameters"></a>ER-paraméterek konfigurálása

1. Ugorjon a **Szervezeti adminisztráció** \> **Munkaterületek** \> **Elektronikus jelentés** pontra.
2. A **Lokalizációs konfigurációk** oldalon, a **Kapcsolódó hivatkozások** szakaszban, válassza az **Elektronikus jelentéskészítés paraméterei** elemet.
3. Az **Elektronikus jelentéskészítési paraméterek** oldalon, az **Általános** lapon a **Tervezői mód engedélyezése** lehetőséget állítsa **Igen** értékre.
4. Válassza a **mellékletek** lap **konfigurációk** mezőjének **fájl** pontját.
5. A **Feladatarchívum**, **Ideiglenes**, **Alap** és **Egyebek** mezőkben válassza a **Fájl** típust.

Az ER-paraméterekkel kapcsolatos további tudnivalókat lásd: [ER-keretrendszer konfigurálása](electronic-reporting-er-configure-parameters.md).

### <a name="activate-an-er-configuration-provider"></a>ER-konfigurációszolgáltató aktiválása

Minden hozzáadott ER-konfigurációt egy ER-konfigurációszolgáltató által birtokoltként kell megjelölni. Erre a célra az **Elektronikus jelentéskészítés** munkaterületen aktiválható ER-konfigurációszolgáltató használatos. Éppen ezért aktiválnia kell egy ER-konfigurációszolgáltatót az **Elektronikus jelentéskészítés** munkaterületen, mielőtt elkezdené az ER-konfigurációk hozzáadását vagy szerkesztését.

> [!NOTE]
> Csak az ER-konfiguráció tulajdonosa szerkesztheti. Éppen ezért aktiválnia kell a megfelelő ER-konfigurációszolgáltatót az **Elektronikus jelentéskészítés** munkaterületen, mielőtt elkezdené az ER-konfigurációk hozzáadását vagy szerkesztését.

#### <a name="review-the-list-of-er-configuration-providers"></a>Az ER-konfigurációszolgáltatók listájának áttekintése

1. Ugorjon a **Szervezeti adminisztráció** \> **Munkaterületek** \> **Elektronikus jelentés** pontra.
2. A **Lokalizációs konfigurációk** oldalon, a **Kapcsolódó hivatkozások** szakaszban, válassza a **Konfigurációszolgáltatók** elemet.
3. A **Konfigurációszolgáltatók tábla** oldalon minden szolgáltatói rekordnak egyedi neve és URL-címe van. Tekintse át az oldal tartalmát. Ha a már létezik a **Litware, Inc.** (`https://www.litware.com`) rekordja, hagyja ki a következő eljárást: [Új ER-konfigurációszolgáltató hozzáadása](#AddProvider).

#### <a name="add-a-new-er-configuration-provider"></a><a id="AddProvider"></a>Új ER-konfigurációszolgáltató hozzáadása

1. Ugorjon a **Szervezeti adminisztráció** \> **Munkaterületek** \> **Elektronikus jelentés** pontra.
2. A **Lokalizációs konfigurációk** oldalon, a **Kapcsolódó hivatkozások** szakaszban, válassza a **Konfigurációszolgáltatók** elemet.
3. A **Konfigurációszolgáltatók** oldalon válassza az **Új** elemet.
4. A **Név** mezőbe írja be a következőt: **Litware, Inc.**.
5. Az **Internetcím** mezőben adja meg a következőt: `https://www.litware.com`.
6. Válassza a **Mentés** lehetőséget.

#### <a name="activate-an-er-configuration-provider"></a>ER-konfigurációszolgáltató aktiválása

1. Ugorjon a **Szervezeti adminisztráció** \> **Munkaterületek** \> **Elektronikus jelentés** pontra.
2. A **Lokalizációs konfigurációk** oldalon, a **Konfigurációszolgáltatók** szakaszban válassza ki a **Litware, Inc.** csempét, majd válassza a **Beállítás aktívként** lehetőséget.

További információért az ER-konfigurációszolgáltatókkal kapcsolatban tekintse át a [Konfigurációszolgáltatók létrehozása és megjelölése aktívként](tasks/er-configuration-provider-mark-it-active-2016-11.md) eljárást.

## <a name="import-the-initial-versions-of-standard-er-configurations"></a><a name="ImportERConfigurations1"></a>A szabvány ER-konfigurációk kezdeti verzióinak importálása

Ha a szabvány ER-konfigurációkat a Finance jelenlegi példányához szeretné hozzáadni, importálnia kell azokat az adott példányhoz konfigurált ER [adattárból](general-electronic-reporting.md#Repository).

1. Ugorjon a **Szervezeti adminisztráció** \> **Munkaterületek** \> **Elektronikus jelentés** pontra.
2. A **Lokalizációs konfigurációk** oldalon, a **Konfigurációszolgáltatók** szakaszban válassza ki a **Microsoft** csempét, majd válassza ki az **Adattárak** lehetőséget a Microsoft szolgáltatóhoz tartozó adattárak listájának megtekintéséhez.
3. A **Konfigurációs adattárak** lapon válassza ki a **Globális** típusú adattárat, majd válassza a **Megnyitás** lehetőséget. Ha a rendszer felkéri a hitelesítésre a Regulatory Configuration Service szolgáltatáshoz való kapcsolódáshoz, kövesse a hitelesítési utasításokat.
4. A **Konfigurációs adattárak** oldalon, a bal oldali panel konfigurációs fájában válassza ki a **Peppol értékesítési számla** formátumkonfigurációt.
5. Válassza ki a **Verziók** gyorslap **11.2.2.** verzióját.
6. Válassza az **Importálás** lehetőséget a kiválasztott verzióglobális adattárból történő letöltéséhez.

![Konfigurációk tárháza oldal](./media/er-quick-start3-import-solution1.png)

> [!TIP]
> Ha nem sikerül elérnie a [globális adattárat](er-download-configurations-global-repo.md), akkor lehetősége van ehelyett [letölteni konfigurációkat](download-electronic-reporting-configuration-lcs.md) a Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásból.

### <a name="review-the-imported-er-configurations"></a>Importált ER-konfigurációk áttekintése

1. Ugorjon a **Szervezeti adminisztráció** \> **Munkaterületek** \> **Elektronikus jelentés** pontra.
2. A **Lokalizációs konfigurációk** oldalon, a **Konfigurációk** szakaszban, válassza ki a **Jelentéskészítési konfiguráció** csempét.
3. A **Konfigurációk** lapon bontsa ki a **Konfigurációs összetevők** gyorslapot.
4. A bal oldali konfigurációs fában bontsa ki a **számla modell** elemet, majd bontsa ki a **UBL értékesítési számla** lehetőséget.

Figyelje meg, hogy a kiválasztott **Peppol értékesítési számla** ER-formátumon kívül más szükséges ER-konfigurációk importálása is megtörtént. Mivel az ER-konfigurációk új verziói folyamatosan megjelennek a globális tárházban és az LCS-ben, hogy a megfelelő megoldások megfeleljenek az új követelményeknek, a szükséges [adatmodell](general-electronic-reporting.md#data-model-and-model-mapping-components)konfigurációnak és ennek [modell-leképezési](general-electronic-reporting.md#data-model-and-model-mapping-components) konfigurációinak legújabb verziói importálásra kerültek.

![Konfigurációk oldala](./media/er-quick-start3-imported-solution1a.png)

Ha szimulálni szeretné, hogy milyen állapotban lennének az ER-konfigurációk az aktuális Finance példányban, ha importálta volna a **Peppol értékesítési számla** ER-formátum **11.2.2** verzióját a múltban (például 2019. augusztus 7-én), kövesse az alábbi lépéseket.

- A művelet ablaktáblán válassza a **Törlés** parancsot, ha törölni szeretné az összes olyan ER-konfigurációt, amelyet a 2019. augusztus 7. után közzétettek. Csak a **Számlamodell**, **Számlamodell-leképezés** (eredetileg **Ügyfélszámla-modell leképezése** néven), **UBL értékesítési számla** és **Peppol értékesítési számla** konfigurációk maradjanak.
- A maradék is ER-konfigurációk esetében a **Verziók** gyorslapon válassza a **Törlés** parancsot, ha törölni szeretné az összes olyan verziót, amely a 2019. augusztus 7. után lett közzétéve.

Ezután győződjön meg arról, hogy a konfigurációs fában a következő ER-konfigurációk érhetők el:

- **Számlamodell** az ER-adatmodell konfigurációját (eredetileg a **Ügyfélszámla modellje** néven):

    - A 11-es verzió tartalmazza az [adatmodell](general-electronic-reporting.md#data-model-and-model-mapping-components) ER-összetevő 10-es verzióját, amely a számlázó üzleti tartomány adatstruktúráját jelzi. Ezt az ER-konfigurációt importálták a **Peppol értékesítési számla** ER-formátum elődjeként, amelyet importálásra kijelöltek.
    - Az 50-es verzió tartalmazza az adatmodell ER-összetevő 31-es verzióját. Ezt az ER-konfigurációt a rendszer a **Számlamodell-leképezés** ER-modell-leképezési konfiguráció 2019. augusztus 7-ei verziója elődjeként importálta.

    ![A számlamodell ER-adatmodell konfigurációja a Konfigurációk oldalon](./media/er-quick-start3-imported-solution1b1.png)

    > [!TIP]
    > Ha nem látja ezt az adatmodell 50-es verzióját, nyissa meg a globális tárházat, és importálja a **Számlamodell-leképezés** ER-konfiguráció 50.19-es verzióját.

- **Számlamodell-leképezés** az ER-amodell-leképezési konfigurációját (eredetileg a **Ügyfélszámla modell-leképezése** néven):

    - Az 50.19-es verzió importálása a **Számlamodell** ER-adatmodell-konfiguráció 50-es verziójának legújabb megvalósításaként történt. A program két [modell-leképezés](general-electronic-reporting.md#data-model-and-model-mapping-components) ER-összetevőt tartalmaz, amely leírja, hogy az adatmodell milyen módon van kitöltve a futásidejű alkalmazási adatokkal.

    ![A számlamodell-leképezés ER-adatmodell-leképezési konfigurációja a Konfigurációk oldalon](./media/er-quick-start3-imported-solution1b2.png)

    > [!TIP]
    > Ha nem látja ezt a modell-leképezés 50.19-es verzióját, nyissa meg a globális tárházat, és importálja a **Számlamodell-leképezés** ER-konfiguráció 50.19-es verzióját.

- **UBL értékesítési számla** ER-formátumkonfigurációja:

    - A 11.2-es verzió tartalmazza a [formátum](general-electronic-reporting.md#FormatComponentOutbound) és formátumleképezés ER-összetevőit. A formátum összetevő meghatározza a jelentés elrendezését. A formátumleképezési összetevő tartalmazza a modell-adatforrást, és meghatározza, hogy a jelentés elrendezését milyen módon kell kitölteni ennek az adatforrásnak a használatával futásidőben. Ezt az ER-formátumot a rendszer úgy konfigurálta, hogy e-számlákat Universal Business Language (UBL) formátumban hozzon létre. Ezt importálták a **Peppol értékesítési számla** ER-formátum fölérendelt elemeként, amelyet importálásra kijelöltek.

- **Peppol értékesítési számla** ER-formátumkonfigurációja:

    - A 11.2.2-es verzió tartalmazza a formátum és formátum-leképezés ER-összetevőit, amelyeket konfiguráltak az e-számlák Pan-European Public Procurement OnLine (PEPPOL) formátumban való létrehozására.

    ![A Peppol értékesítési számla ER-formátumkonfigurációja a Konfigurációk oldalon](./media/er-quick-start3-imported-solution1b3.png)

## <a name="configure-the-accounts-receivable-parameters"></a><a name="ConfigureAR1"></a>A Kinnlevőségek paraméterei konfigurálása

1. Lépjen a **Kinnlevőségek** \> **Beállítások** \> **Kinnlevőségek paraméterei** pontra.
2. Az **elektronikus dokumentumok** lapon az **elektronikus jelentéskészítés** gyorslapján, az **értékesítési és Szabadszöveges számla** mezőben válassza ki a **Peppol értékesítési számlát**.
3. Válassza a **Mentés** lehetőséget.

![A Kinnlevőségek paraméterei lap elektronikus dokumentumok lapja](./media/er-quick-start3-configure-ar1.png)

## <a name="configure-the-legal-entity-parameters"></a><a name="ConfigureLE"></a>A jogi személy paramétereinek konfigurálása

1. Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Szervezetek** \> **Jogi személyek**.
2. A kiválasztott **DEMF** vállalat esetében a **bankszámla adatai** gyorslap **útvonalszám** mezőjébe írja be a **1234** értéket.
3. Válassza a **Mentés** lehetőséget.
4. Zárja be a **Jogi személyek** képernyőt.

## <a name="prepare-a-customer-record"></a><a name="ConfigureCustomer1"></a>Ügyfélrekord előkészítése

1. Ugorjon a **Kinnlevőségek** \> **Ügyfelek** \> **Minden Ügyfél** pontra.
2. Az **Összes Ügyfél** lapon válassza a **de-014** Ügyfélszámla hivatkozását.

### <a name="add-a-customer-contact"></a>Ügyfél-kapcsolattartó hozzáadása

1. Ugorjon a **Kinnlevőségek** \> **Ügyfelek** \> **Minden Ügyfél** pontra.
2. A Műveleti ablaktáblán az **Ügyfél** lapján a **Partnerek** csoportban válassza a **Kapcsolattartók** lehetőséget.
3. Válassza a **kapcsolattartók hozzáadása** lehetőséget.
4. A **Kapcsolattartók** oldal **Utónév** mezőjében nyissa meg a keresést, válassza **Adam Carter** nevét, majd válassza a **Kiválasztás** elemet a keresésé bezárásához.
5. Válassza a **Mentés** lehetőséget.
6. Zárja be a **Kapcsolattartók** képernyőt.

### <a name="define-a-primary-contact"></a>Elsődleges kapcsolattartó definiálása

1. Ugorjon a **Kinnlevőségek** \> **Ügyfelek** \> **Minden Ügyfél** pontra.
2. Az **Értékesítési demográfiai adatok** gyorslapon az **Elsődleges kapcsolattartó** mezőben válassza az **Adam Carter** nevet.

### <a name="set-the-e-invoicing-option"></a>Az e-számlázás beállítás beállítása

1. Ugorjon a **Kinnlevőségek** \> **Ügyfelek** \> **Minden Ügyfél** pontra.
2. A **számla és a teljesítés** gyorslapon állítsuk be az **eInvoice** beállítást **Igen** értékre.
3. Válassza a **Mentés** lehetőséget.
4. Zárja be az **összes ügyfél** lapot.

## <a name="process-a-customer-invoice-by-using-the-standard-er-configurations"></a><a name="ProcessInvoice1"></a>Ügyfélszámla feldolgozása a szabványos ER-konfigurációk segítségével

Most már használhatja azokat a szabványos ER-konfigurációkat, amelyeket a szabadszöveges számlának a Ügyfélnek történő elektronikus küldése céljából importált.

### <a name="add-a-new-invoice"></a>Új számla hozzáadása

1. Válassza a következőt **Kinnlevőségek** \> **Számlák** \> **Kizárólag szabadszöveges számlák**.
2. A **Szabadszöveges számla** lapon válassza az **új** elemet.
3. A **Szabadszöveges számla fejléce** gyorslap **Ügyfélszámla** mezőjében válassza a **de-014** értéket.
4. A **számlasorok** gyorslapon automatikusan hozzáadásra kerül egy számlasor. Ezen a soron állítsa be a következő mezőket:

    - A **Leírás** mezőben adja meg a **Jegyzetfüzet** értéket.
    - A **Fő számla** mezőben válassza a **401100** lehetőséget.
    - Írjon be **1000** értéket az **Egységár** mezőbe.

5. Válassza a **Mentés** lehetőséget.

![Szabadszöveges számla oldal](./media/er-quick-start3-add-invoice.png)

További tájékoztatás: [Szabadszöveges számla létrehozása](../../../finance/accounts-receivable/create-free-text-invoice-new.md).

### <a name="post-a-new-invoice"></a>Új számla közzététele

1. Válassza a következőt **Kinnlevőségek** \> **Számlák** \> **Kizárólag szabadszöveges számlák**.
2. A **Szabadszöveges számla** lapon válassza a művelet ablaktábla **Feladás** elemét.
3. A **Szabadszöveges számla feladása** párbeszédpanelen kattintson az **OK** gombra.

![Szabadszöveges számla részletei oldal](./media/er-quick-start3-post-invoice.png)

### <a name="send-a-posted-invoice"></a>Feladott számla küldése

1. Válassza a következőt **Kinnlevőségek** \> **Számlák** \> **Kizárólag szabadszöveges számlák**.
2. Válassza ki a **Szabadszöveges számla** lapot a művelet ablaktábláján, a **dokumentum** csoportban válassza a **Küldés** \> **Eredeti**.

    ![Az eredeti számla előnézetének megtekintése](./media/er-quick-start3-send-invoice.png)

3. Zárja be a **Szabadszöveges számla** képernyőt.

### <a name="analyze-a-generated-e-invoice"></a>Elkészített e-számla elemzése

1. Lépjen a **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Elektronikus jelentéskészítési feladatok** menüpontba.
2. Az **elektronikus jelentéskészítési feladatok** lapon válassza ki azt a kezdeti rekordot, amelynél a feladatnak leírása **eInvoice XML-fájl elküldése**.
3. Válassza ki a **Fájlok megjelenítése** elemet a létrejövő fájlok listájának eléréséhez.

    ![Elektronikus jelentéskészítési feladatai oldal](./media/er-quick-start3-jobs-list.png)

4. Válassza a **Megnyitás** elemet az imént létrehozott e-számla XML-fájl letöltéséhez.
5. Az e-számla XML-fájljának elemzése. Figyelje meg, hogy az ügyfél adózási sémáját jelenleg a **schemeID** és **schemeAgencyID** XML attribútumok jelzik. Azt is észreveheti, hogy a **cbc:CustomizationID** XML-elem jelenleg a következő szöveget tartalmazza: `urn:www.cenbii.eu:transaction:biicoretrdm010:ver1.0:# urn:www.peppol.eu:bis:peppol5a:ver1.0`.

    ![A létrejövő e-számla XML-fájljának előnézete](./media/er-quick-start3-e-invoice1.png)

## <a name="add-a-custom-database-field"></a><a name="AddCustomField"></a>Egyéni adatbázismező hozzáadása

Az [egyéni mező](../../fin-ops/get-started/user-defined-fields.md)  funkció az aktuális Finance példány következő testreszabásainak végrehajtásához használható:

- Új egyéni adatbázismező hozzáadásával testreszabhatja az adatbázis-struktúrát, amely minden Ügyfélhez egy Szövetségi adóazonosító kódot tárol.
- A **Ügyfél** lap testreszabása olyan új adatbeviteli mező hozzáadásával, amely az áfakód értékének megadására használható az új egyéni adatbázismezőben.

A Testreszabás végrehajtásához hajtsa végre az alábbi lépéseket.

1. Ugorjon a **Kinnlevőségek** \> **Ügyfelek** \> **Minden Ügyfél** pontra.
2. Az **Összes Ügyfél** lapon válassza a **de-014** Ügyfélszámla hivatkozását.
3. Az **általános** gyorslapon kattintson a jobb gombbal a **nyelv** mező alatti üres területre , majd válassza a **személyre szabás: UpperGroup** elemet.

    Az **Általános** gyorslap tartalma ki van emelve, és megjelenik a **személyre szabás** menü.

4. Válassza a **Személyre szabás** menü **mező hozzáadása** pontját.
5. Az **Oszlopok hozzáadása** párbeszédpanelen jelölje be az **új mező létrehozása** jelölőnégyzetet.
6. Válassza ki az **új mező létrehozása** párbeszédpanel **tábla neve** mezőjében a **Ügyfelek** elemet.
7. A **Név előtagja** mezőbe írja be a következőt: **FederalTaxID**.

    > [!NOTE]
    > A program az egész mezőnevet automatikusan **FederalTaxID\_Custom** néven határozta meg.

8. A **Címke** mezőbe írja a **Federal** értéket.
9. A **Típus** mezőben válassza ki az **Szöveg** lehetőséget.
10. Adja meg a **20** értéket a **Hossz** mezőben.
11. Válassza a **Mentés** lehetőséget.
12. A megjelenő üzenetablakban válassza az **Igen** lehetőséget, ha meg szeretné erősíteni az új **FederalTaxID** mezőbejegyzés létrehozását a **Ügyfelek** táblához.
13. Válassza ki a **Beszúrás** lehetőséget a <a name="insert_custom_field"></a>**FederalTaxID\_Custom** mező jelenlegi oldalhoz való hozzáadásához.

    ![Összes ügyfél oldal](./media/er-quick-start3-create-new-field.gif)

14. Zárja be az **összes ügyfél** lapot.

## <a name="refresh-the-er-metadata"></a><a name="RefreshERMetadata"></a>A ER-metaadatok frissítése

Frissítenie kell az ER-metaadatokat, hogy a hozzáadott egyéni mező [láthatóvá](electronic-reporting-er-configure-parameters.md#frequently-asked-questions) váljon az ER-modell-leképezés tervezőjében.

1. Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Táblahivatkozások újraépítése**.
2. Az **adatmodell frissítése** párbeszédpanelen kattintson az **OK** gombra.

## <a name="design-the-custom-er-configurations"></a><a name="DesignCustomERConfigurations"></a>Egyéni ER-konfigurációk tervezése

A Microsoft által biztosított ER-konfigurációk segítségével megtervezheti a saját egyéni ER-konfigurációját, hogy az új áfakódot tartalmazó e-számlákat hozza létre.

### <a name="customize-the-data-model-configuration"></a>Az adatmodell konfigurációjának testreszabása

Az elektronikus jelentéskészítési funkcionális tanácsadó szerepkörében felhasználóként megtervezheti az egyéni ER-adatmodellt.

#### <a name="add-a-custom-data-model-configuration"></a>Egyéni adatmodell-konfiguráció hozzáadása

1. Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**.
2. A **Konfigurációk** oldalon, a bal oldali panelen található konfigurációk fájában válassza a **Ügyfél számlamodell** elemet.
3. A Műveleti ablaktáblán kattintson a **Konfiguráció létrehozása** elemre.
4. A legördülő párbeszédpanel **új** mezőjében válassza a **Származtatás innen: Vevői számlamodell, Microsoft** elemet annak jelzésére, hogy az új egyéni ER-adatmodell konfigurációjának az ER-adatmodellel kapcsolatos konfiguráción kell alapulnia.
5. A **Név** mezőben írja be a **Számlamodell (Litware)** szöveget.
6. Az új ER-konfiguráció hozzáadásához válassza a **Konfiguráció létrehozása** elemet.

Ezután az ER-adatmodell-tervező használatával szerkesztheti a **Számlamodell (Litware)** ER-konfiguráció 50.1-es verzióját **Piszkozat** [állapotban](general-electronic-reporting.md#component-versioning).

![Az ER-konfiguráció 50.1.-es verziója a Konfigurációk oldalon](./media/er-quick-start3-added-custom-model.png)

#### <a name="configure-a-custom-data-model"></a>Egyéni adatmodell konfigurálása

A Szövetségi adóazonosító kód értékének megadásához egy új mező hozzáadásával módosítania kell az egyéni adatmodellt. Ez a kód a vevői adatoknak az a része, amely minden olyan ER-formátumnál szerepel, amely ezt az adatmodellt fogja használni adatforrásként.

1. A **Konfigurációk** oldalon, a bal oldali panelen található konfigurációk fájában válassza a **Számlamodell (Litware)** elemet.
2. A **Verziók** gyorslapon válassza ki a kijelölt ER-adatmodell-konfiguráció **50.1**-es verzióját **Piszkozat** állapotban.
3. A műveleti ablaktáblán válassza ki a kiválasztott konfigurációs verzió **tervezőjét**.
4. Az **adatmodell-tervező** lap adatmodell fastruktúrájában válassza ki az **Ügyféladatok (Ügyfél)** elemet.
5. Válassza az **Új** lehetőséget.
6. A legördülő párbeszédpanel **új csomópont a következőként** mezőjében fogadja el az alapértelmezett értéket, az **aktív csomópont alárendelt eleme**.
7. A **Név** mezőbe írja be a következőt: **FederalTaxID\_Litware**.
8. A **elemtípus** mezőben fogadja el az alapértelmezett értéket, a **karakterláncot**.
9. Válassza a **Hozzáadás** parancsot, majd válassza a **Mentés** elemet.

    ![Adatmodell-tervező oldal](./media/er-quick-start3-add-data-model-field.png)

    > [!NOTE]
    > A **címke** és a **Leírás** mező az új mező célját írja le. Ezeket a mezőket több nyelven is kitöltheti. További tudnivalókért lásd: [Többnyelvű jelentések tervezése elektronikus jelentéskészítésben (ER)](er-design-multilingual-reports.md).

10. Zárja be az **Adatmodell-tervező** oldalt.

#### <a name="complete-a-custom-data-model-configuration"></a>Egyéni adatmodell-konfiguráció befejezése

Be kell [fejeznie](general-electronic-reporting.md#component-versioning) a munkát az egyéni ER-adatmodell konfigurációjának 50.1-es verziójával annak érdekében, hogy elérhetővé váljon és így hozzáadhassa a többi egyéni ER-konfigurációt is.

1. Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**.
2. A **Konfigurációk** oldalon, a bal oldali panelen található konfigurációk fájában bontsa ki a **Számlamodell** elemet, majd válassza a **Számlamodell (Litware)** lehetőséget.
3. Válassza a **Verziók** gyorslap **Állapot módosítása** \> **Befejezés** elemét, majd kattintson az **OK** gombra.

Az 50.1-es verzió állapota a **Piszkozat** értékről a **Befejezett** értékre módosul , és a verzió írásvédett lesz. Az új, szerkeszthető verzió (50.2) **Piszkozat** állapottal kerül hozzáadásra. Ennek a verziónak a használatával további változtatásokat hajthat végre a saját egyéni ER-adatmodell-konfigurációban.

![A 50.1 verzió a konfigurációk oldalon fejeződött be](./media/er-quick-start3-completed-custom-model1.png)

### <a name="customize-the-model-mapping-configuration"></a>A modell-leképezési konfiguráció testreszabása

Az elektronikus jelentéskészítési fejlesztő szerepkörében felhasználóként megtervezheti az egyéni ER-modell leképezését.

#### <a name="add-a-custom-model-mapping-configuration"></a>Egyéni modell-leképezési konfiguráció hozzáadása

1. Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**.
2. A **Konfigurációk** oldalon, a bal oldali panelen található konfigurációk fájában bontsa ki a **Ügyfélszámlamodell** elemet, majd válassza a **Ügyfélszámlamodell leképezése** lehetőséget.
3. A Műveleti ablaktáblán kattintson a **Konfiguráció létrehozása** elemre.
4. A legördülő párbeszédpanel **új** mezőjében válassza a **Származtatás innen: Vevői számlamodell leképezése, Microsoft** elemet annak jelzésére, hogy az új egyéni ER-modell leképezési konfigurációjának az ER-modell-leképezéssel kapcsolatos konfiguráción kell alapulnia.
5. A **Név** mezőben írja be a **Számlamodell-leképezés (Litware)** szöveget.
6. A **cél modell** mezőben válassza ki a **számlamodell (Litware)**.

    > [!IMPORTANT]
    > Ez a lépés rendkívül fontos. Ha kihagyja, akkor nem fogja tudni használni az egyéni adatmodellt a konfigurált modell-hozzárendelésben.

7. Az új ER-konfiguráció hozzáadásához válassza a **Konfiguráció létrehozása** elemet.

![Az egyéni modell-leképezési konfiguráció hozzáadása a Konfigurációk oldalon](./media/er-quick-start3-adding-custom-mapping.png)

#### <a name="configure-a-custom-model-mapping"></a>Egyéni modell-leképezés konfigurálása

Módosítania kell az egyéni modell hozzárendelését, és meg kell adnia, hogy az egyéni adatmodell egyéni **FederalTaxID\_Litware** mezőjét a rendszer milyen módon töltse ki az alkalmazási adatokkal futásidőben.

1. Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**.
2. A **Konfigurációk** oldalon, a bal oldali panelen található konfigurációk fájában bontsa ki a **Ügyfélszámlamodell** \> **Ügyfélszámlamodell-leképezés** elemet, majd válassza a **Számlamodell leképezése (Litware)** lehetőséget.
3. A Műveleti ablaktáblán kattintson a **Tervező** elemre.
4. A **Modell leképezése adatforráshoz** oldalon válassza a **Ügyfélszámla** leképezést.

    ![Modell hozzárendelése adatforráshoz lap](./media/er-quick-start3-select-customer-mapping.png)

5. Válassza a **Tervező** lehetőséget.
6. A **Modell-leképezéstervező** oldal **Adatforrások** panelén bontsa ki a **CustInvoiceJour** adatforrást, amely a **CustInvoiceJour** alkalmazástáblát jelzi.
7. A **CustInvoiceJour** részben bontsa ki a **kapcsolatok** elemet, és tekintse át a **CustInvoiceJour tábla** több-egyben (N:1) típusú kapcsolatainak listáját.
8. A **CustInvoiceJour** \> **Kapcsolatok** területen bontsa ki a **vevők (CustTable)** elemet a **vevők (CustTable)** tábla mezőinek és kapcsolatainak eléréséhez.
9. Válassza ki az **FederalTaxID\_Egyéni** adatforrásmezőt, amelyet [korábban](#insert_custom_field) végrehajtott.
10. Az **adatmodell** ablaktáblán bontsa ki a **vevők adatait (vevő)** elemet, és válassza ki a **FederalTaxID\_Litware** adatmodell mezőt.
11. Válassza a **Bind** elemet.

    ![Modell-leképezés tervező oldal](./media/er-quick-start3-customize-model-mapping.gif)

12. Válassza a **Mentés** lehetőséget.
13. Zárja be a **Modell-hozzárendelési tervező** lapot.
14. Zárja be a **Modell hozzárendelése adatforráshoz** lapot.

#### <a name="complete-a-custom-model-mapping-configuration"></a>Egyéni modell-leképezési konfiguráció befejezése

Az egyéni ER-modell-hozzárendelési konfiguráció 50.19.1-es verziójával végzett munkát [be kell fejeznie](general-electronic-reporting.md#component-versioning) annak érdekében, hogy elérhető legyen a használatra.

1. Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**.
2. A **Konfigurációk** oldalon, a bal oldali panelen található konfigurációk fájában bontsa ki a **Ügyfélszámlamodell** \> **Ügyfélszámlamodell-leképezés** elemet, majd válassza a **Számlamodell leképezése (Litware)** lehetőséget.
3. Válassza a **Verziók** gyorslap **Állapot módosítása** \> **Befejezés** elemét, majd kattintson az **OK** gombra.

Az 50.19.1-es verzió állapota a **Piszkozat** értékről a **Befejezett** értékre módosul , és a verzió írásvédett lesz. Az új, szerkeszthető verzió (50.19.2) **Piszkozat** állapottal kerül hozzáadásra. Ennek a verziónak a használatával további változtatásokat hajthat végre a saját egyéni ER-modell-leképezési konfigurációban.

![A 50.19.1 verzió a konfigurációk oldalon fejeződött be](./media/er-quick-start3-completed-custom-mapping1.png)

> [!NOTE]
> A támogatott konfigurációs [életciklus](general-electronic-reporting-manage-configuration-lifecycle.md) nem fedi le az adatbázis-módosítások életciklusát. Ha az aktuális Finance példány **Számlamodell-leképezés (Litware)** konfiguráció 50.19.1 verzióját exportálja, és szeretne egy másik példányt importálni, ami nem tartalmazza az egyéni **FederalTaxID\_Custom** mezőt a **CustTable** táblában, kivétel történik. A kivétel azt határozza meg, hogy az importált ER konfiguráció nem kompatibilis a célként megadott Finance példány metaadataival.

### <a name="customize-the-format-configuration"></a>Formátumkonfiguráció testreszabása

Az elektronikus jelentéskészítési funkcionális tanácsadó szerepkörében felhasználóként megtervezheti az egyéni ER-formátumot.

#### <a name="add-a-custom-format-configuration"></a>Egyéni formátumkonfiguráció hozzáadása

1. Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**.
2. A **Konfigurációk** oldalon, a bal oldali panelen található konfigurációk fájában bontsa ki a **Ügyfélszámlamodell** \> **UBL értékesítési számla** elemet, majd válassza a **Peppol értékesítési számla** lehetőséget.
3. A Műveleti ablaktáblán kattintson a **Konfiguráció létrehozása** elemre.
4. A legördülő párbeszédpanel **új** mezőjében válassza a **Származtatás innen: Peppol értékesítési számla, Microsoft** elemet annak jelzésére, hogy az egyéni ER-formátum konfigurációjának az ER-formátummal kapcsolatos konfiguráción kell alapulnia.
5. A **Név** mezőben írja be a **Peppol értékesítési számla (Litware)** szöveget.
6. Az **adatmodell** mezőben válassza ki a **Számlázási modell (Litware)** elemet az Egyéni adatmodell és a modell-hozzárendelési összetevők használatához.

    > [!NOTE]
    > Ez a lépés rendkívül fontos. Ha kihagyja, akkor nem fogja tudni használni az egyéni adatmodellt a konfigurált formátumban.

7. Az **Adatmodell** mezőben válassza ki a **InvoiceCustomer** gyökérdefiníciót.
8. Az új ER-konfiguráció hozzáadásához válassza a **Konfiguráció létrehozása** elemet.

![Az egyéni formátumkonfiguráció hozzáadása a Konfigurációk oldalon](./media/er-quick-start3-adding-custom-format.png)

Ezután az ER-művelettervező használatával szerkesztheti a **Peppol értékesítési számla (Litware)** ER-konfiguráció 11.2.2.1-es verzióját **Piszkozat** [állapotban](general-electronic-reporting.md#component-versioning).

![Az ER-konfiguráció 11.2.2.1.-es verziója a Konfigurációk oldalon](./media/er-quick-start3-added-custom-format.png)

#### <a name="configure-a-custom-format"></a>Egyéni formátum konfigurálása

Az egyéni formátumot úgy kell módosítani, hogy egy új fájlformátumot ad hozzá, amely kitölti egy számlázott vevő Szövetségi adóazonosító kódja értékét.

1. Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**.
2. A **Konfigurációk** oldalon, a bal oldali panelen található konfigurációk fájában bontsa ki a **Ügyfélszámlamodell** \> **UBL értékesítési számla** \> **Peppol értékesítési számla** elemet, majd válassza a **Peppol értékesítési számla (Litware)** lehetőséget.
3. A Műveleti ablaktáblán kattintson a **Tervező** elemre.
4. A formátumfában bontsa ki a **XMLHeader** \> **számla** \> **cac:AccountingCustomerParty** \> **cac:Party** \> **cac:PartyTaxScheme** \> **cac:TaxScheme** elemet, és válassza ki a **cbc:ID** értéket.
5. Válassza a **Hozzáadás** parancsot, majd válassza az **XML** \> **Attribútum** elemet.
6. Írja be az **Összetevő-tulajdonság** párbeszédpanel **Név** mezőjébe ezt: **FederalTaxID**.
7. Az **OK** gombra kattintva hozzáadhat egy új formátumbeli elemet egy új **FederalTaxID** XML-attribútum létrehozásához egy létrehozott XML-fájlban.
8. A formátumfában az **XMLHeader** \> **Számla** \> **cac:AccountingCustomerParty** \> **cac:Party** \> **cac:PartyTaxScheme** \> **cac:TaxScheme** \> **cbc:ID** részben válassza a **FederalTaxID** elemet.
9. Válassza a **Feljebb** lehetőséget.

![Új formátumelem a Formátumtervező oldalon](./media/er-quick-start3-customized-format.png)

#### <a name="configure-a-custom-format-mapping"></a>Egyéni formátumleképezés konfigurálása

1. A **Formátumtervező** oldal **Leképezések** lapján bontsa ki a **Modell** típusú **Számla** adatforrását.
2. Bontsa ki a **számla** területen a **vevői adatok (vevő)** elemet, és válassza ki a **FederalTaxID\_Litware** elemet.
3. Válassza a **Bind** elemet.

    ![Formátumtervező oldal](./media/er-quick-start3-customized-format-mapping.png)

4. Válassza ki a **Modell** típus **Számla** adatforrást, majd válassza a **Szerkesztés** parancsot.
5. Válassza ki a **verzió** mezőben az Egyéni adatmodell **1**-es verzióját, majd kattintson az **OK** gombra.
6. Válassza a **Mentés** lehetőséget.
7. Zárja be a **Formátumtervező** lapot.

#### <a name="complete-a-custom-format-configuration"></a>Egyéni formátumkonfiguráció végrehajtása

Az egyéni ER-formátum-konfiguráció 11.2.2.1-es verziójával végzett munkát [be kell fejeznie](general-electronic-reporting.md#component-versioning) annak érdekében, hogy elérhető legyen a használatra.

1. Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**.
2. A **Konfigurációk** oldalon, a bal oldali panelen található konfigurációk fájában bontsa ki a **Ügyfélszámlamodell** \> **UBL értékesítési számla** \> **Peppol értékesítési számla** elemet, majd válassza a **Peppol értékesítési számla (Litware)** lehetőséget.
3. Válassza a **Verziók** gyorslap **Állapot módosítása** \> **Befejezés** elemét, majd kattintson az **OK** gombra.

Az 11.2.2.1-es verzió állapota a **Piszkozat** értékről a **Befejezett** értékre módosul , és a verzió írásvédett lesz. Az új, szerkeszthető verzió (11.2.2.2) **Piszkozat** állapottal kerül hozzáadásra. Ennek a verziónak a használatával további változtatásokat hajthat végre a saját egyéni ER-formátumkonfigurációjában.

![A 11.2.2.1 verzió a konfigurációk oldalon fejeződött be](./media/er-quick-start3-completed-custom-format1.png)

## <a name="configure-the-accounts-receivable-parameters-to-start-to-use-custom-er-configurations"></a><a name="ConfigureAR2"></a>Kinnlevőségek paraméterek konfigurálása az egyéni ER-konfigurációk használatbavételéhez.

1. Lépjen a **Kinnlevőségek** \> **Beállítások** \> **Kinnlevőségek paraméterei** pontra.
2. Az **elektronikus dokumentumok** lapon az **elektronikus jelentéskészítés** gyorslapján, az **értékesítési és Szabadszöveges számla** mezőben válassza ki a **Peppol értékesítési számla (Litware)** elemet.
3. Válassza a **Mentés** lehetőséget.

![A Kinnlevőségek paraméterei lap elektronikus dokumentumok lapja, elektronikus jelentéskészítés gyorslap](./media/er-quick-start3-configure-ar2.png)

## <a name="update-a-customer-record-by-adding-a-federal-tax-identification-code"></a><a name="ConfigureCustomer2"></a>Vevői rekord frissítése a Szövetségi adóazonosító kód hozzáadásával

1. Ugorjon a **Kinnlevőségek** \> **Ügyfelek** \> **Minden Ügyfél** pontra.
2. Az **Összes Ügyfél** lapon válassza a **de-014** Ügyfélszámla hivatkozását.
3. Írja be az **általános** gyorslapon a **Szövetségi adóazonosító** mezőbe a következőt: **LITWARE-6789**.
4. Válassza a **Mentés** lehetőséget.

    ![DE-014 ügyfél adatai oldal](./media/er-quick-start3-added-tax-id-value.png)

5. Zárja be az **összes ügyfél** lapot.

## <a name="process-a-customer-invoice-by-using-custom-er-configurations"></a><a name="ProcessInvoice2"></a>Vevői számla feldolgozása az egyéni ER-konfigurációk segítségével

### <a name="select-and-send-a-posted-invoice"></a>Feladott számla kiválasztása és elküldése

1. Válassza a következőt **Kinnlevőségek** \> **Számlák** \> **Kizárólag szabadszöveges számlák**.
2. A **Szabadszöveges számla** lapon válassza ki azt a számlát, amelyet korábban hozzáadott és feladott.
3. A műveleti panel **Dokumentum** csoportjában válassza a **Küldés** \> **Eredeti** lehetőséget.
4. Zárja be a **Szabadszöveges számla** képernyőt.

### <a name="analyze-a-generated-e-invoice"></a>Elkészített e-számla elemzése

1. Lépjen a **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Elektronikus jelentéskészítési feladatok** menüpontba.
2. Az **elektronikus jelentéskészítési feladatok** lapon válassza ki azt a legutóbbi rekordot, amelynél a feladatnak leírása **eInvoice XML-fájl elküldése**.
3. Válassza ki a **Fájlok megjelenítése** elemet a létrejövő fájlok listájának eléréséhez.
4. Válassza a **Megnyitás** elemet az imént létrehozott e-számla XML-fájl letöltéséhez.
5. Az e-számla XML-fájljának elemzése. Figyelje meg, hogy a testreszabással összhangban a vevői adózási séma tartalmazza az egyéni **FederalTaxID** XML-attribútumot a **schemeID** és a **schemeAgencyID** XML-attribútumokon kívül. Ennek az új XML-attribútumnak az értékét a **LITWARE-6789** Szövetségi adóazonosító határozza meg, amelyet a program számlázott vevőhöz rögzített.

    ![A létrejövő e-számla XML-fájljának előnézete a testreszabásokkal](./media/er-quick-start3-e-invoice2.png)

## <a name="import-the-latest-versions-of-standard-er-configurations"></a><a name="ImportERConfigurations2"></a>A szabvány ER-konfigurációk legutóbbi verzióinak importálása

Ha azt szeretné, hogy a Finance példány alapértelmezett ER-konfigurációi [naprakészek legyenek](general-electronic-reporting-manage-configuration-lifecycle.md), akkor az új verziókat importálnia kell, amikor elérhetővé válik az adott példányhoz konfigurált ER-[adattárban](general-electronic-reporting.md#Repository).

1. Ugorjon a **Szervezeti adminisztráció** \> **Munkaterületek** \> **Elektronikus jelentés** pontra.
2. A **Lokalizációs konfigurációk** oldalon, a **Konfigurációszolgáltatók** szakaszban válassza ki a **Microsoft** csempét, majd válassza ki az **Adattárak** lehetőséget a Microsoft szolgáltatóhoz tartozó adattárak listájának megtekintéséhez.
3. A **Konfigurációs adattárak** lapon válassza ki a **Globális** típusú adattárat, majd válassza a **Megnyitás** lehetőséget. Ha a rendszer felkéri a hitelesítésre a Regulatory Configuration Service szolgáltatáshoz való kapcsolódáshoz, kövesse a hitelesítési utasításokat.
4. A **Konfigurációs adattárak** oldalon, a bal oldali panel konfigurációs fájában válassza ki a **Peppol értékesítési számla** formátumkonfigurációt.
5. A **Verziók** gyorslapon válassza ki a kijelölt ER- formátumkonfiguráció **32.6.7**-es verzióját, amely a PEPPOL BIS 3 formátumú vevői elektronikus számlák támogatására lett kiadva. További tájékoztatás: [KB4490320](https://support.microsoft.com/help/4490320/an-update-for-european-union-to-support-export-of-customers-electronic).
6. Kattintson az **Importálás** lehetőségre a kiválasztott verzió Globális tárból a jelenlegi Finance and Operations példányba történő letöltéséhez.

![A konfigurációs tárház lapon kiválasztott verzió 32.6.7](./media/er-quick-start3-import-solution2.png)

Ha további tájékoztatást szeretne arról, hogyan lehet automatizálni ezt a folyamatot, akkor olvassa el [az ER-konfigurációk frissített verzióinak importálása](er-download-updated-versions-global-repo.md) című témakört.

### <a name="review-the-imported-er-configurations"></a>Importált ER-konfigurációk áttekintése

1. Ugorjon a **Szervezeti adminisztráció** \> **Munkaterületek** \> **Elektronikus jelentés** pontra.
2. A **Lokalizációs konfigurációk** oldalon, a **Konfigurációk** szakaszban, válassza ki a **Jelentéskészítési konfiguráció** csempét.
3. Bontsa ki a **Konfigurációs összetevők** gyorslapot.
4. A bal oldali ablak konfigurációs fáján bontsa ki a **Számlamodell** lehetőséget. Figyelje meg, hogy a **Vevői számla modelljének** neve **Számlamodell** névre módosult az egyik importált ER-adatmodell-konfigurációban.
5. A bal oldali ablak konfigurációs fáján bontsa ki a **Számlamodell-leképezés** lehetőséget. Figyelje meg, hogy a **Vevői számla modelljének leképezése** neve **Számlamodell-leképezés** névre módosult az egyik importált ER-modell-leképezési konfigurációban.
6. Bontsa ki: **UBL értékesítési számla** \> **Peppol értékesítési számla**.

Figyelje meg, hogy a kiválasztott **Peppol értékesítési számla** ER-formátumon kívül más szükséges ER-konfigurációk legújabb verziójának importálása is megtörtént. Mivel az ER-konfigurációk új verziói folyamatosan megjelennek a globális tárházban és az LCS-ben, hogy a megfelelő ER-megoldások megfeleljenek az új követelményeknek, a szükséges adatmodellkonfigurációnak és ennek modell-leképezési konfigurációinak legújabb verziói importálásra kerültek.

Győződjön meg arról, hogy a konfigurációs fában a következő ER-konfigurációk érhetők el:

- **Számlamodell** ER adatmodellkonfiguráció:

    - A 206-os (vagy újabb) verzió tartalmazza az adatmodell ER-összetevő 24-es (vagy újabb) verzióját, amely a számlázó üzleti tartomány adatstruktúráját jelzi. Ezt az ER-konfigurációt a rendszer a legújabb elérhető **Számlamodell-leképezés** ER-modell-leképezési konfiguráció elődjeként importálta.

    ![A 206-os verzió a konfigurációk oldalon fejeződött be](./media/er-quick-start3-imported-solution2b1.png)

- **Számlamodell-leképezés** ER -modell-leképezési konfiguráció:

    - Az 206.132-es (vagy újabb) verzió importálása a **Számlamodell** ER-adatmodell-konfiguráció 206-es verziójának legújabb megvalósításaként történt. A program számos modell-leképezés ER-összetevőt tartalmaz, amely leírja, hogy az adatmodell milyen módon van kitöltve a futásidejű alkalmazási adatokkal.

    ![A 206.132-os verzió a konfigurációk oldalon fejeződött be](./media/er-quick-start3-imported-solution2b2.png)

- **UBL értékesítési számla** ER-formátumkonfigurációja:

    - A 32.6-es verzió tartalmazza a formátum és formátumleképezés ER-összetevőit. A formátum összetevő meghatározza a jelentés elrendezését. A formátumleképezési összetevő tartalmazza a modell-adatforrást, és meghatározza, hogy a jelentés elrendezését milyen módon kell kitölteni ennek az adatforrásnak a használatával futásidőben. Ezt az ER-formátumot a rendszer úgy konfigurálta, hogy e-számlákat UBL formátumban hozzon létre. Ezt importálták a **Peppol értékesítési számla** ER-formátum fölérendelt elemeként, amelyet importálásra kijelöltek.

- **Peppol értékesítési számla** ER-formátumkonfigurációja:

    - A 32.6.7-es verzió tartalmazza a formátum és formátum-leképezés ER-összetevőit, amelyeket konfiguráltak az e-számlák PEPPOL formátumban való létrehozására.

    ![A 32.6.7-os verzió a konfigurációk oldalon fejeződött be](./media/er-quick-start3-imported-solution2b3.png)

## <a name="adopt-the-changes-to-the-new-standard-er-configurations-in-your-custom-er-configurations"></a><a name="RebaseCustomERConfigurations"></a>A standard ER-konfigurációk új verzióira vonatkozó módosítások elfogadása az egyéni ER-konfigurációkban

### <a name="adopt-your-custom-er-data-model"></a>Egyéni ER-adatmodell elfogadása

1. Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**.
2. A **Konfigurációk** oldalon, a bal oldali panelen található konfigurációk fájában bontsa ki a **Számlamodell** elemet, majd válassza a **Számlamodell (Litware)** lehetőséget.
3. A **Verziók** gyorslapon a kijelölt ER-adatmodell-konfiguráció **50.2**-es verziójának Piszkozat verziójához válassza az **Új alap** elemet.
4. A **cél verziószáma** mezőben hagyja jóvá az alao ER-adatmodell-konfiguráció **206**-os verziót, majd válassza az **OK** gombot .

    Az egyéni ER-adatmodell konfigurációjának piszkozatverziója újraszámozva **50.2**-ről **206.2**-re, így jelezheti, hogy a rendszer most az alapadat-modell konfigurációjának legutóbbi verziójában (206) szereplő módosításokkal összevont testreszabást tartalmazza.

    > [!NOTE]
    > Az új alap művelet visszafordítható. Ha az új alapra helyezést vissza szeretné vonni, válassza ki a **Számlamodell (Litware)** modell **50.1**-es verzióját a **Verziók** gyorslapon, majd válassza ki a **Verzió beszerzése** elemet. A 206.2-es verziót ezután a rendszer **50.2**-esként számozza fel, és az 50.2-es piszkozat verzió tartalma megegyezik a 50.1-es verzió tartalmával.

5. Válassza a **Verziók** gyorslap **Állapot módosítása** \> **Befejezés** elemét, majd kattintson az **OK** gombra.

Az 206.2-es verzió állapota a **Piszkozat** értékről a **Befejezett** értékre módosul , és a verzió írásvédett lesz. Az új, szerkeszthető verzió (206.3) **Piszkozat** állapottal kerül hozzáadásra. Ennek a verziónak a használatával további változtatásokat hajthat végre a saját egyéni ER-adatmodell-konfigurációban.

![A 206.2 verzió a konfigurációk oldalon fejeződött be](./media/er-quick-start3-completed-custom-model2.png)

### <a name="adopt-your-custom-er-model-mapping"></a>Egyéni ER-modell-leképezés elfogadása

1. Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**.
2. A **Konfigurációk** oldalon, a bal oldali panelen található konfigurációk fájában bontsa ki a **Számlamodell** \> **Számlamodell-leképezés** elemet, majd válassza a **Számlamodell leképezése (Litware)** lehetőséget.
3. A **Verziók** gyorslapon a kijelölt ER-modell-leképezési konfiguráció **50.19.2**-es verziójának Piszkozat verziójához válassza az **Új alap** elemet.
4. A **cél verziószáma** mezőben hagyja jóvá az alap ER-modell-leképezési konfiguráció **206.132**-os verziót, majd válassza az **OK** gombot .

    Az egyéni ER-modell-leképezési konfigurációjának piszkozatverziója újraszámozva **50.19.2**-ről **206.132.2**-re, így jelezheti, hogy a rendszer most az ER-modell-leképezési konfigurációjának legutóbbi verziójában (206.132) szereplő módosításokkal összevont testreszabást tartalmazza.

    Észreveheti, hogy a rendszer bizonyos új alap ütközéseket észlelt. Most manuálisan kell megoldania ezeket az ütközéseket.

    ![Ütközési üzenet új alapja a konfigurációk oldalon](./media/er-quick-start3-rebase-conflicts-model-mapping1.png)

5. A műveleti ablaktáblán válassza a **tervező** elemet, majd a hozzárendelések listáján válassza ki a **Vevői számlát**.
6. Minden egyes új alap ütközésnél válassza a **saját érték megtartása** beállítást, mert minden említett összetevőnél meg kell őriznie az egyéni adatmodell verziószámát.

    ![Az új alap ütközések a modell-leképezés tervező oldalán](./media/er-quick-start3-rebase-conflicts-model-mapping2.png)

7. Válassza a **Mentés** lehetőséget, majd zárja be a **Modell-leképezés tervező** oldalt.
8. A hozzárendelések listáján válassza ki a **projektszámlát**.
9. Minden egyes új alap ütközésnél válassza a **saját érték megtartása** beállítást, mert minden említett összetevőnél meg kell őriznie az egyéni adatmodell verziószámát.
10. Válassza a **Mentés** lehetőséget, majd zárja be a **Modell-leképezések** oldalt.

    > [!NOTE]
    > Az új alap művelet visszafordítható. Ha az új alapra helyezést vissza szeretné vonni, válassza ki a **Számlamodell-leképezés (Litware)** modell-leképezés **50.19.1**-es verzióját a **Verziók** gyorslapon, majd válassza ki a **Verzió beszerzése** elemet. A 206.132.2-es verziót ezután a rendszer **50.19.2**-esként számozza fel, és az 50.19.2-es piszkozat verzió tartalma megegyezik a 50.19.1-es verzió tartalmával.

11. Válassza a **Verziók** gyorslap **Állapot módosítása** \> **Befejezés** elemét, majd kattintson az **OK** gombra.

Az 206.132.2-es verzió állapota a **Piszkozat** értékről a **Befejezett** értékre módosul , és a verzió írásvédett lesz. Az új, szerkeszthető verzió (206.132.3) **Piszkozat** állapottal kerül hozzáadásra. Ennek a verziónak a használatával további változtatásokat hajthat végre a saját egyéni ER-modell-leképezési konfigurációban.

![A 206.132.2 verzió a konfigurációk oldalon fejeződött be](./media/er-quick-start3-completed-custom-mapping2.png)

### <a name="adopt-your-custom-er-format"></a>Egyéni ER-formátum elfogadása

1. Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**.
2. A **Konfigurációk** oldalon, a bal oldali panelen található konfigurációk fájában bontsa ki a **Számlamodell** \> **UBL értékesítési számla** \> **Peppol értékesítési számla** elemet, majd válassza a **Peppol értékesítési számla (Litware)** lehetőséget.
3. A **Verziók** gyorslapon a kijelölt ER-formátumkonfiguráció **11.2.2.2**-es verziójának Piszkozat verziójához válassza az **Új alap** elemet.
4. A **cél** verziómezőben hagyja jóvá az alap ER-formátumkonfiguráció **32.6.7**-os verziót, majd válassza az **OK** gombot .

    Az egyéni ER-formátum konfigurációjának piszkozatverziója újraszámozva **11.2.2.2**-ről **32.6.7.2**-re, így jelezheti, hogy a rendszer most az ER-formátumkonfigurációjának legutóbbi verziójában (32.6.7) szereplő módosításokkal összevont testreszabást tartalmazza.

    Észreveheti, hogy a rendszer bizonyos új alap ütközéseket észlelt. Most manuálisan kell megoldania ezeket az ütközéseket.

5. A Műveleti ablaktáblán kattintson a **Tervező** elemre.
6. Minden egyes új alap ütközésnél válassza a **saját érték megtartása** beállítást, mert minden említett összetevőnél meg kell őriznie az egyéni adatmodell verziószámát.
7. Válassza a **Mentés** lehetőséget.
8. A **Leképezés** lapon válassza a **Számla** adatforrást a **Modell** típusnál, majd válassza a **Szerkesztés** parancsot.
9. Válassza ki a **verzió** mezőben az Egyéni adatmodell **2**-es verzióját, majd kattintson az **OK** gombra.
10. Válassza a **Mentés** lehetőséget.

    > [!NOTE]
    > Az új alap művelet visszafordítható. Ha az új alapra helyezést vissza szeretné vonni, válassza ki a **Peppol értékesítési számla (Litware)** formátum **11.2.2.1**-es verzióját a **Verziók** gyorslapon, majd válassza ki a **Verzió beszerzése** elemet. A 32.6.7.2-es verziót ezután a rendszer **11.2.2.2**-esként számozza fel, és az 11.2.2.2-es piszkozat verzió tartalma megegyezik a 11.2.2.1-es verzió tartalmával.

11. Zárja be a **Formátumtervező** lapot.
12. Válassza a **Verziók** gyorslap **Állapot módosítása** \> **Befejezés** elemét, majd kattintson az **OK** gombra.

Az 32.6.7.2-es verzió állapota a **Piszkozat** értékről a **Befejezett** értékre módosul , és a verzió írásvédett lesz. Az új, szerkeszthető verzió (32.6.7.3) **Piszkozat** állapottal kerül hozzáadásra. Ennek a verziónak a használatával további változtatásokat hajthat végre a saját egyéni ER-formátumkonfigurációjában.

![A 32.6.7.2 verzió a konfigurációk oldalon fejeződött be](./media/er-quick-start3-completed-custom-format2.png)

## <a name="process-a-customer-invoice-by-using-new-versions-of-the-custom-er-configurations"></a><a name="ProcessInvoice3"></a>Vevői számla feldolgozása az egyéni ER-konfigurációk új verziói segítségével

### <a name="select-and-send-a-posted-invoice"></a>Feladott számla kiválasztása és elküldése

1. Válassza a következőt **Kinnlevőségek** \> **Számlák** \> **Kizárólag szabadszöveges számlák**.
2. A **Szabadszöveges számla** lapon válassza ki azt a számlát, amelyet korábban hozzáadott és feladott.
3. A műveleti panel **Dokumentum** csoportjában válassza a **Küldés** \> **Eredeti** lehetőséget.

    > [!NOTE] 
    > Mivel most már két verziója van az **Peppol értékesítési számla (Litware)** ER-formátum konfigurációban, és egyik verzió sem rendelkezik [hatályos dátummal](general-electronic-reporting.md#component-date-effectivity), a legutolsó verzió az e-számla előállítására szolgál.

4. Zárja be a **Szabadszöveges számla** képernyőt.

### <a name="analyze-a-generated-e-invoice"></a>Elkészített e-számla elemzése

1. Lépjen a **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Elektronikus jelentéskészítési feladatok** menüpontba.
2. Az **elektronikus jelentéskészítési feladatok** lapon válassza ki azt a legutóbbi rekordot, amelynél a feladatnak leírása **eInvoice XML-fájl elküldése**.
3. Válassza ki a **Fájlok megjelenítése** elemet a létrejövő fájlok listájának eléréséhez.
4. Válassza a **Megnyitás** elemet az imént létrehozott e-számla XML-fájl letöltéséhez.
5. Az e-számla XML-fájljának elemzése. Figyelje meg, hogy a testreszabással összhangban a vevői adózási séma tartalmazza az egyéni **FederalTaxID** XML-attribútumot a **schemeID** és a **schemeAgencyID** XML-attribútumokon kívül. Ezenkívül mivel az alap **UBL értékesítési számla** formátum új verziójának módosításai egyesítve lettek a testreszabással, a **cbc:CustomizationID** XML-elem szövege módosult `urn:www.cenbii.eu:transaction:biicoretrdm010:ver1.0:# urn:www.peppol.eu:bis:peppol5a:ver1.0` értékről `urn:cen.eu:en16931:2017#compliant#urn:fdc:peppol.eu:2017:poacc:billing:3.0` értékre.

    ![A létrejövő e-számla XML-fájljának előnézete a testreszabásokkal](./media/er-quick-start3-e-invoice3.png)

## <a name="additional-resources"></a>További erőforrások

- [Elektronikus jelentések áttekintése](general-electronic-reporting.md)
- [ER-konfigurációk letöltése a Lifecycle Services szolgáltatásból](download-electronic-reporting-configuration-lcs.md)
- [ER-konfigurációk letöltése a konfigurációs szolgáltatás globális tárából](er-download-configurations-global-repo.md)
- [Szabadszöveges számla létrehozása](https://docs.microsoft.com/dynamics365/finance/accounts-receivable/create-free-text-invoice-new)
- [Egyéni mezők létrehozása és használata](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/user-defined-fields)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]