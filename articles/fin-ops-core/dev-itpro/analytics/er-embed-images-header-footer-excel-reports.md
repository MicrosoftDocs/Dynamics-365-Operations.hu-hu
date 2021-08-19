---
title: ER-formátum megtervezése az oldalfejlécben vagy láblécben beágyazott képeket tartalmazó Excel-formátumú jelentés létrehozásához
description: Ez a témakör bemutatja az Elektronikus jelentéskészítés (ER) olyan üzleti dokumentumok létrehozásához való használatát, amelyekben az oldalfejlécekbe és láblécekbe képek és alakzatok vannak beágyazva.
author: NickSelin
ms.date: 06/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EROperationDesigner, ERParameters
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2021-06-01
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 1115be8c33eeaf16c1a533e63b31d87b0fc5f68d6469ff075428f72ac146b2f4
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6746635"
---
# <a name="design-an-er-format-to-generate-a-report-in-excel-format-with-embedded-images-in-page-headers-or-footers"></a>ER-formátum megtervezése az oldalfejlécben vagy láblécben beágyazott képeket tartalmazó Excel-formátumú jelentés létrehozásához

[!include[banner](../includes/banner.md)]

Ez a témakör azt mutatja be, hogy a Rendszergazda vagy az Elektronikus jelentéskészítési szakterületi konzulens szerepkörű felhasználók hogyan hajthatják végre ezeket a feladatokat:

- Az [Elektronikus jelentéskészítési (ER)](general-electronic-reporting.md) keretrendszer paramétereinek konfigurálása.
- A Microsoft által [biztosított](general-electronic-reporting.md#Provider) [ER-konfigurációk](general-electronic-reporting.md#Configuration) importálása [szabadszöveges számlák](../../../finance/accounts-receivable/create-free-text-invoice-new.md) előállításához Microsoft Excel-formátumú [sablon](er-fillable-excel.md#excel-file-component) alapján.
- A Microsoft által biztosított szabvány ER-formátumú konfiguráció [egyéni (származtatott)](general-electronic-reporting.md#building-a-format-selecting-another-format-as-a-base-customization) verziójának létrehozása.
- Az egyéni ER-formátum konfigurációjának módosítása úgy, hogy olyan szabadszöveges számlajelentést generáljon, amelynek láblécében a vállalati embléma képe szerepel.

A jelen témakörben szereplő eljárások az **USMF** vállalatnál végezhetők el. Nincs szükség kódolásra. Mielőtt belekezdene, a következő fájlt is le kell töltenie, illetve mentenie kell.

| Leírás        | Fájlnév |
|--------------------|-----------|
| Vállalati embléma képe | [Company logo.png](https://download.microsoft.com/download/8/2/e/82e6bd81-caac-4e9a-bfce-1392ce7c8616/Companylogo.png) |

## <a name="content"></a>Tartalom

- [A jogi személy konfigurálása](#ConfigureLegalEntity)
- [ER-keretrendszer konfigurálása](#ConfigureFramework)

    - [ER-paraméterek konfigurálása](#ConfigureParameters)
    - [ER-konfigurációszolgáltató aktiválása](#ActivateProvider)

        - [Az ER-konfigurációszolgáltatók listájának áttekintése](#ReviewProvidersList)
        - [Új ER-konfigurációszolgáltató hozzáadása](#AddProvider)
        - [Az új ER-konfigurációszolgáltató aktiválása](#ActivateAddedProvider)

- [A szabvány ER-formátumkonfigurációk importálása](#ImportERSolution1)

    - [A szabvány ER-konfigurációk importálása](#ImportERFormat)
    - [Importált ER-konfigurációk áttekintése](#ReviewImportedERSolution)

- [Szabadszöveges számla nyomtatása a szabványos ER-formátum használatával](#PrintInvoice1)

    - [Nyomtatáskezelés beállítása](#ConfigurePrintManagement1)
    - [Szabadszöveges számla nyomtatása](#ProcessInvoice1)

- [A szabvány ER-formátum testreszabása](#CustomizeProvidedFormat)

    - [Egyéni formátum létrehozása](#DeriveProvidedFormat)
    - [Egyéni formátum szerkesztése](#ConfigureDerivedFormat)
    - [Egyéni formátum megjelölése futtathatóként](#MarkFormatRunnable)

- [Szabadszöveges számla nyomtatása egyéni ER-formátum használatával](#PrintInvoice2)

    - [Nyomtatáskezelés beállítása](#ConfigurePrintManagement2)
    - [Szabadszöveges számla nyomtatása](#ProcessInvoice2)

- [További erőforrások](#References)

## <a name="configure-the-legal-entity"></a><a id="ConfigureLegalEntity"></a>A jogi személy konfigurálása

1. Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Szervezetek** \> **Jogi személyek**.
2. A **Jogi személyek** lap **Vállalati emblémakép jelentése** gyorslapján válassza a **Módosítás** lehetőséget.
3. A **Feltöltendő képfájl kiválasztása** párbeszédpanelen válassza a **Tallózás** lehetőséget, majd válassza ki a korábban letöltött **Company logo.png** fájlt.
4. Válassza a **Mentés** lehetőséget, majd zárja be a **Jogi személyel** oldalt.

![Vállalati embléma képe kiválasztva a Jogi személyek lapon.](./media/er-embed-images-header-footer-excel-reports-company-logo-image.png)

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
> Az ER-konfigurációkat csak a konfiguráció tulajdonosa szerkesztheti. Aktiválnia kell a megfelelő ER-konfigurációszolgáltatót az **Elektronikus jelentéskészítés** munkaterületen, mielőtt elkezdené az ER-konfigurációk szerkesztését.

#### <a name="review-the-list-of-er-configuration-providers"></a><a id="ReviewProvidersList"></a>Az ER-konfigurációszolgáltatók listájának áttekintése

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

#### <a name="activate-the-new-er-configuration-provider"></a><a id="ActivateAddedProvider"></a>Az új ER-konfigurációszolgáltató aktiválása

1. Ugorjon a **Szervezeti adminisztráció** \> **Munkaterületek** \> **Elektronikus jelentés** pontra.
2. A **Lokalizációs konfigurációk** oldalon, a **Konfigurációszolgáltatók** szakaszban válassza ki a **Litware, Inc.** csempét, majd válassza a **Beállítás aktívként** lehetőséget.

További információért az ER-konfigurációszolgáltatókkal kapcsolatban tekintse át a [Konfigurációszolgáltatók létrehozása és megjelölése aktívként](tasks/er-configuration-provider-mark-it-active-2016-11.md) eljárást.

## <a name="import-the-standard-er-format-configurations"></a><a id="ImportERSolution1"></a>A szabvány ER-formátumkonfigurációk importálása

### <a name="import-the-standard-er-configurations"></a><a id="ImportERFormat"></a>A szabvány ER-konfigurációk importálása

Ha a standard ER-konfigurációkat a Dynamics 365 Finance jelenlegi példányához szeretné hozzáadni, importálnia kell őket az adott példányhoz konfigurált [ER-adattárból](general-electronic-reporting.md#Repository).

1. Ugorjon a **Szervezeti adminisztráció** \> **Munkaterületek** \> **Elektronikus jelentés** pontra.
2. A **Lokalizációs konfigurációk** oldalon, a **Konfigurációszolgáltatók** szakaszban válassza ki a **Microsoft** csempét, majd válassza ki az **Adattárak** lehetőséget a **Microsoft** szolgáltatóhoz tartozó adattárak listájának megtekintéséhez.
3. A **Konfigurációs adattárak** lapon válassza ki a **Globális** típusú adattárat, majd válassza a **Megnyitás** lehetőséget. Ha a rendszer felkéri a hitelesítésre a [Regulatory Configuration Service](../../../finance/localizations/rcs-overview.md) szolgáltatáshoz való kapcsolódáshoz, kövesse a hitelesítési utasításokat.
4. A **Konfigurációs adattárak** oldalon, a bal oldali panel konfigurációs fájában válassza ki a **Szabadszöveges számla (Excel)** formátumkonfigurációt.
5. A **Verziók** gyorslapon válassza ki a kijelölt ER-formátumkonfiguráció legújabb (például **240.112**-es) verzióját.
6. Kattintson az **Importálás** lehetőségre a kiválasztott verzió Globális tárból a jelenlegi Finance and Operations példányba történő letöltéséhez.

![A standard ER-konfigurációk importálása a Konfigurációk tárháza oldalon.](./media/er-embed-images-header-footer-excel-reports-import-solution.png)

> [!TIP]
> Ha nem sikerül elérnie a [globális adattárat](er-download-configurations-global-repo.md), akkor lehetősége van ehelyett [letölteni konfigurációkat](download-electronic-reporting-configuration-lcs.md) a Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásból.

### <a name="review-the-imported-er-configurations"></a><a id="ReviewImportedERSolution"></a>Importált ER-konfigurációk áttekintése

1. Ugorjon a **Szervezeti adminisztráció** \> **Munkaterületek** \> **Elektronikus jelentés** pontra.
2. A **Lokalizációs konfigurációk** oldalon, a **Konfigurációk** szakaszban, válassza ki a **Jelentéskészítési konfiguráció** csempét.
3. A **Konfigurációk** oldalon, a bal oldali panelen található konfigurációk fájában bontsa ki a **Számlamodell** elemet.
4. A kiválasztott **Szabadszöveges számla (Excel)** ER-formátumon kívül más szükséges ER-konfigurációk importálása is megtörtént. Győződjön meg arról, hogy a konfigurációs fában a következő ER-konfigurációk érhetők el:

    - **Számlamodell** – Ez a konfiguráció tartalmazza az [adatmodell](general-electronic-reporting.md#data-model-and-model-mapping-components) ER-összetevőt, amely a számlázási üzleti tartomány adatstruktúráját jelöli.
    - **Számlamodell leképezése** – Ez a konfiguráció tartalmazza a [modell-leképezés](general-electronic-reporting.md#data-model-and-model-mapping-components) összetevőt, amely leírja, hogy az adatmodell milyen módon van kitöltve az alkalmazási adatokkal futási időben.
    - **Szabadszöveges számla (Excel)** – ez a konfiguráció tartalmazza a [formátumra](general-electronic-reporting.md#FormatComponentOutbound) és formátum-hozzárendelésre vonatkozó ER-összetevőket. A formátum-összetevő egy Excel-formátumú sablon alapján határozza meg a jelentéselrendezést. A formátumleképezési összetevő tartalmazza a modell-adatforrást, és meghatározza, hogy a jelentés elrendezését milyen módon kell kitölteni ennek az adatforrásnak a használatával futásidőben.

![Importált ER-konfigurációk a Konfigurációk oldalon.](./media/er-embed-images-header-footer-excel-reports-imported-solution.png)

## <a name="print-a-free-text-invoice-by-using-the-standard-er-format"></a><a id="PrintInvoice1"></a>Szabadszöveges számla nyomtatása a szabványos ER-formátum használatával

### <a name="set-up-print-management"></a><a id="ConfigurePrintManagement1"></a>Nyomtatáskezelés beállítása

1. Válassza a következőt **Kinnlevőségek** \> **Számlák** \> **Kizárólag szabadszöveges számlák**.
2. Válassza ki a **Szabadszöveges számla** oldalon az **FTI-00000002** számlát, majd a Művelet panel **Számla** lapjának **Nyomtatáskezelés** csoportjában válassza a **Nyomtatáskezelés** lehetőséget.
3. A **Nyomtatáskezelés beállítása** oldalon, a bal oldali fában bontsa ki a **Modul – Kinnlevőségek \> Dokumentumok \> Szabadszöveges számla** ágat, majd válassza ki az **Eredeti \<Default\>** elemet.
4. A **Jelentésformátum** mezőben válassza ki a **Szabadszöveges számla (Excel)** lehetőséget.
5. Az **Esc** billentyű lenyomásával hagyja el a **Nyomtatáskezelés beállítása** oldalt, és térjen vissza a **Szabadszöveges számla** oldalra.

![Standard ER-formátumú szabadszöveges számla nyomtatáskezelési beállításai a Nyomtatáskezelés beállítása oldalon.](./media/er-embed-images-header-footer-excel-reports-print-management.png)

### <a name="print-a-free-text-invoice"></a><a id="ProcessInvoice1"></a>Szabadszöveges számla nyomtatása

1. Győződjön meg róla, hogy a **Szabadszöveges számla** oldalon még mindig ki van jelölve az **FTI-00000002** számla, majd a Művelet panel **Számla** lapjának **Dokumentum** csoportjában válassza a **Nyomtatás** \> **Kiválasztott** lehetőséget.
2. Töltse le a létrehozott számlát Excel-formátumban, és nyissa meg az előnézetét.
3. Figyelje meg, hogy a megadott ER-formátum Excel-sablonjának szerkezetével összhangban a létrehozott számla lábléce tartalmazza az aktuális oldalszámra és a jelentés teljes oldalszámára vonatkozó adatokat.

![Előállított szabadszöveges számla.](./media/er-embed-images-header-footer-excel-reports-print-invoice1.gif)

## <a name="customize-the-standard-er-format"></a><a id="CustomizeProvidedFormat"></a>A szabvány ER-formátum testreszabása

Az ebben a szakaszban szereplő példában a Microsoft által biztosított ER-konfigurációk segítségével szabadszöveges számlát hozhat létre Excel-formátumban. Hozzá kell adnia azonban egy testreszabást, amellyel a vállalati embléma képét elhelyezi a létrehozott számlák láblécében.

Ebben az esetben a Litware, Inc. képviselőjeként létre kell hozni (származtatni kell) egy olyan új ER-formátumkonfigurációt, amely a Microsoft által biztosított **Szabadszöveges számla (Excel)** konfiguráción alapul.

### <a name="create-a-custom-format"></a><a id="DeriveProvidedFormat"></a>Egyéni formátum létrehozása

1. Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**.
2. A **Konfigurációk** oldalon, a bal oldali panelen található konfigurációs fában bontsa ki a **Számlamodell** elemet, majd válassza a **Szabadszöveges számla (Excel)** lehetőséget. A Litware, Inc. ennek az ER-formátumkonfigurációnak az importált verzióját (például a **240.112-es** verziót) fogja használni az egyéni verzió alapjaként.
3. A **Konfiguráció létrehozása** kiválasztásával megnyithatja a legördülő párbeszédablakot. A párbeszédablak segítségével új konfigurációt hozhat létre az egyéni fizetési formátumra vonatkozóan.
4. Az **Új** mezőcsoportban válassza ki a **Származtatás innen: Szabadszöveges számla (Excel), Microsoft** lehetőséget.
5. A **Név** mezőben adja meg a **Szabadszöveges számla (Excel) – egyéni** értéket.
6. Válassza a **Konfiguráció létrehozása** lehetőséget.

![Egyéni fizetési formátum konfigurációjának létrehozása a Konfiguráció létrehozása legördülő párbeszédpanelen.](./media/er-embed-images-header-footer-excel-reports-add-derived-format.png)

Létrejön a **Szabadszöveges számla (Excel) – egyéni** ER-formátum 240.112.1-es verziója. Ez a verzió **Piszkozat** [állapottal](general-electronic-reporting.md#component-versioning) rendelkezik, és szerkeszthető. Az egyéni ER-formátum jelenlegi tartalma megegyezik a Microsoft által biztosított formátum tartalmával.

![Az ER-formátum konfigurációjának új verziója a Konfigurációk oldalon létrehozva.](./media/er-embed-images-header-footer-excel-reports-derived-format-configuration1.png)

### <a name="edit-the-custom-format"></a><a id="ConfigureDerivedFormat"></a>Egyéni formátum szerkesztése

Állítsa be az egyéni formátumot úgy, hogy a vállalati embléma képe bekerüljön a jelentés minden lapjának láblécébe.

1. Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**.
2. A **Konfigurációk** oldalon, a bal oldali panelen található konfigurációs fában bontsa ki a **Fizetési modell** elemet, majd válassza a **Szabadszöveges számla (Excel) – egyéni** lehetőséget.
3. A **Verziók** gyorslapon válassza ki a kijelölt konfiguráció **240.112.1**-es verzióját.
4. Válassza a **Tervező** lehetőséget.
5. A **Formátumtervező** oldalon válassza a **Részletek megjelenítése** lehetőséget, ha további tájékoztatást szeretne látni a formátumelemekről.
6. Bontsa ki és tekintése át a következő elemeket:

    - **Excel** típusú **Szabadszöveges számla** elem. Ezzel az elemmel számla generálható Excel-munkafüzet formátumban.
    - **Lap** típusú **Szabadszöveges számla \\ Számla** elem. Ezzel az elemmel lehet létrehozni munkalapot a létrehozott Excel-munkafüzetben.
    - **Lábléc** típusú **Szabadszöveges számla \\ Számla \\ Lábléc** elem. Ezzel az elemmel lehet kitölteni a számla láblécét.

7. Válassza ki **a Szabadszöveges számla \\ Számla \\ Lábléc** elemet.

    ![Lábléc elem az ER-művelettervezőben.](./media/er-embed-images-header-footer-excel-reports-derived-format0.png)

    > [!NOTE]
    > A létrehozott számlák minden lábléce tartalmazza az aktuális oldalszámmal és a jelentés teljes oldalszámával kapcsolatos adatokat. Amint látható, a **Szabadszöveges számla \\ Számla \\ Lábléc** elem nem tartalmaz gyermekelemeket. Emiatt a használt Excel-sablon úgy van beállítva, hogy minden jelentés láblécének középén lapozási adatokat jelenítsen meg.

8. Válassza a **Hozzáadás** lehetőséget, majd válassza ki a hozzáadni kívánt formátumelem **Excel \\ Kép** típusát:

    1. Az **Igazítás** mezőben válassza a **Jobbra** lehetőséget.
    2. A **Magasság méretezése** mezőben válassza a **Relatív** lehetőséget.
    3. A **Százalékos méretezés** mezőbe írja be a **70** értéket.
    4. Válassza ki az **OK** lehetőséget.

        > [!NOTE]
        > Az **Excel \\ Kép** elem segítségével vállalati emblémaképet lehet hozzáadni, és a lábléc jobb oldalára lehet igazítani.

    ![A Kép elem tulajdonságai az Összetevő tulajdonságai párbeszédpanelen.](./media/er-embed-images-header-footer-excel-reports-derived-format1.png)

9. A bal oldali formátumszerkezeti fában válassza ki az előbb hozzáadott **Kép** elemet, majd a **Leképezés** lapon bontsa ki a **modell** adatforrását.
10. Bontsa ki a **model.Payment** \> **model.InvoiceBase\> model.InvoiceBase.CompanyInfo** modellt, majd válassza ki a **model.InvoiceBase.CompanyInfo.Logo** adatforrásmezőt. A [Tároló](er-formula-supported-data-types-composite.md#container) típus adatforrásmezője a vállalati emblémát médiatartalomként teszi elérhetővé.
11. Válassza a **Bind** elemet. A **Kép** formátumelem most a **model.InvoiceBase.CompanyInfo.Logo** adatforrásmezőhöz van kötve. Következésképpen futásidőben a rendszer a létrehozott számlák láblécére egy vállalati emblémaképet helyez.

    ![Az ER-művelettervező model.InvoiceBase.CompanyInfo.Logo adatforrásmezőjéhez kötött képformátumelem.](./media/er-embed-images-header-footer-excel-reports-derived-format2.png)

12. Válassza a **Mentés** lehetőséget, majd zárja be a **Tervező** oldalt.

### <a name="mark-the-custom-format-as-runnable"></a><a id="MarkFormatRunnable"></a>Egyéni formátum megjelölése futtathatóként

Mivel az egyéni formátum első verzióját már létrehozta, és az a **Piszkozat** állapottal rendelkezik, tesztelés céljából futtathatja a formátumot. A jelentés futtatásához a szállítói kifizetést az egyéni ER-formátumra hivatkozó fizetési mód használatával dolgozza fel. Alapértelmezésben, amikor egy ER-formátumot hív meg az alkalmazásból, csak a **Befejeződött** vagy **Megosztott** állapotú verziókat [veszi figyelembe](general-electronic-reporting.md#component-versioning) a rendszer. Ez a viselkedés segít megakadályozni a befejezetlen konstrukciókkal rendelkező ER-formátumok használatát. A teszt futtatásakor azonban kényszerítheti az alkalmazást egy **Piszkozat** állapottal rendelkező ER-formátumverzió használatára. Ily módon módosíthatja az aktuális formátum verziószámát, ha bármilyen módosítás szükséges. További információ: [Alkalmazhatóság](electronic-reporting-destinations.md#applicability).

Ha egy ER-formátum piszkozat verzióját kívánja használni, ennek kifejezett módon be kell jelölnie az ER-formátumot.

1. Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**.
2. A **Konfigurációk** oldal műveleti ablaktábláján, a **Konfigurációk** lapon, a **Speciális beállítások** csoportban válassza a **Felhasználói paraméterek** lehetőséget.
3. A **Felhasználói paraméterek** párbeszédpanelen állítsa a **Futtatási beállítások** beállítását **Igen** értékre, majd kattintson az **OK** gombra.
4. Válassza a **Szerkesztés** lehetőséget a jelenlegi oldal szerkeszthetővé tételéhez, majd a bal oldali panelen található konfigurációs fában válassza ki a **Szabadszöveges számla (Excel) – egyéni** lehetőséget.
5. Állítsa a **Piszkozat futtatása** beállítást **Igen** lehetőségre.

![Az egyéni formátum megjelölése futtathatóként a Konfigurációk lapon.](./media/er-embed-images-header-footer-excel-reports-derived-format-configuration2.png)

## <a name="print-a-free-text-invoice-by-using-the-custom-er-format"></a><a id="PrintInvoice2"></a>Szabadszöveges számla nyomtatása egyéni ER-formátum használatával

### <a name="set-up-print-management"></a><a id="ConfigurePrintManagement2"></a>Nyomtatáskezelés beállítása

1. Válassza a következőt **Kinnlevőségek** \> **Számlák** \> **Kizárólag szabadszöveges számlák**.
2. Válassza ki a **Szabadszöveges számla** oldalon az **FTI-00000002** számlát, majd a Művelet panel **Számla** lapjának **Nyomtatáskezelés** csoportjában válassza a **Nyomtatáskezelés** lehetőséget.
3. A **Nyomtatáskezelés beállítása** oldalon, a bal oldali fában bontsa ki a **Modul – Kinnlevőségek** \> **Dokumentumok** \> **Szabadszöveges számla** ágat, majd válassza ki az **Eredeti** **\<Default\>** elemet.
4. A **Jelentésformátum** mezőben válassza ki a **Szabadszöveges számla (Excel) – egyéni** lehetőséget.
5. Az **Esc** billentyű lenyomásával hagyja el a **Nyomtatáskezelés beállítása** oldalt, és térjen vissza a **Szabadszöveges számla** oldalra.

### <a name="print-a-free-text-invoice"></a><a id="ProcessInvoice2"></a>Szabadszöveges számla nyomtatása

1. Győződjön meg róla, hogy a **Szabadszöveges számla** oldalon még mindig ki van jelölve az **FTI-00000002** számla, majd a Művelet panel **Számla** lapjának **Dokumentum** csoportjában válassza a **Nyomtatás** \> **Kiválasztott** lehetőséget.
2. Töltse le a létrehozott számlát Excel-formátumban, és nyissa meg az előnézetét.
3. Ne feledje, hogy az egyéni ER-formátum szerkezetével összhangban a létrehozott számla lábléce tartalmaz egy vállalati emblémaképet, valamint megjeleníti a jelentés lapozási információit.

![Létrehozott szabadszöveges számla az oldal láblécében a vállalati emblémaképpel.](./media/er-embed-images-header-footer-excel-reports-print-invoice2.gif)

## <a name="additional-resources"></a><a id="References"></a>További erőforrások

- [Tervezzen konfigurációkat a kimenő dokumentumok Excel-formátumban történő létrehozásához](er-fillable-excel.md)
- [Beágyazott képek és alakzatok az ER-rel generált dokumentumokban](electronic-reporting-embed-images-shapes.md)
