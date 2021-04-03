---
title: Műveletfüggő ER-célok konfigurálása
description: Ez a témakör elmagyarázza, hogyan lehet beállítani műveletfüggő célhelyeket a kimenő dokumentumok létrehozásához konfigurált elektronikus jelentési (ER) formátumú fájlok MAPPA vagy FÁJL összetevőihez.
author: NickSelin
manager: AnnBe
ms.date: 02/09/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERFormatDestinationTable
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: f3055a27-717a-4c94-a912-f269a1288be6
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-12-01
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 80624e286fd1300b8de6fd8a7fc67c246cb3a41b
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/09/2021
ms.locfileid: "5569635"
---
# <a name="configure-action-dependent-er-destinations"></a>Műveletfüggő ER-célok konfigurálása

[!include [banner](../includes/banner.md)]

Beállíthat [célhelyeket](electronic-reporting-destinations.md) minden kimeneti összetevőjéhez (mappa vagy fájl) az [elektronikus jelentési (ER)](general-electronic-reporting.md) [formátum](general-electronic-reporting.md#FormatComponentOutbound) [konfigurációknak](general-electronic-reporting.md#Configuration), amelyek kimenő dokumentumok létrehozásához használtak. Azok a felhasználók, akik ilyen típusú ER-formátumot futtatnak, és megfelelő hozzáférési jogokkal rendelkeznek, futásidőben módosíthatják a konfigurált cél beállításait is.

A Microsoft Dynamics 365 Finance **10.0.17-es és újabb verzióiban** az ER-formátum futtatható egy olyan műveletkód [üzembe helyezése](er-apis-app10-0-17.md) által, amelyet a felhasználó az adott ER-formátum futtatásával hajt végre. Például a **Kinnlevőségek** modul Nyomtatáskezelési beállításainál választhat olyan ER-formátumot, amely konkrét üzleti dokumentumot, például szabadszöveges számlát generál. Ezután a számla előnézeti képe megtekinthető a **Nézet** lehetőséggel, illetve a **Nyomtatás** gombbal elküldheti egy nyomtatóra. Ha futásidőben felhasználói művelet van átállítva a futó ER-formátumhoz, eltérő ER-célokat lehet beállítani a különböző felhasználói műveletekhez. Ez a témakör leírja, hogyan kell konfigurálni az ER-célokat az ilyen típusú ER-formátumhoz.

## <a name="make-action-dependent-er-destinations-available"></a>Műveletfüggő ER-célok elérhetővé tétele

Az aktuális Finance példány műveletfüggő ER-céljának konfigurálásához és az [új](er-apis-app10-0-17.md) ER API engedélyezéséhez nyissa meg a [Szolgáltatáskezelés](../../fin-ops/get-started/feature-management/feature-management-overview.md#the-feature-management-workspace) munkaterületet, és kapcsolja be a **Különféle PM-műveletek funkcióhoz használt specifikus ER-célok konfigurálása** funkciót. Ha futásidőben konfigurált ER-célokat használ [adott](#reports-list-wave1) jelentésekhez, engedélyezze a **PM-jelentések kimenetét útvonalválasztása a felhasználói műveletspecifikus (1. hullám) ER-célok alapján**.

## <a name="configure-action-dependent-er-destinations"></a>Műveletfüggő ER-célok konfigurálása

Ha bekapcsolja a **Különféle PM-műveletek funkcióhoz használt specifikus ER-célok konfigurálása** funkciót, műveletfüggő ER-célokat konfigurálhat az **Elektronikus jelentési céloldal** **Fájlcél** gyorslapján. Minden egyes összetevőre felvehet egy rekordot, és engedélyezheti az egyes ER-célokat. Minden rekordhoz meg kell adnia, hogy milyen típusú dokumentumhoz kell alkalmazni a konfigurált ER-célokat. A **Dokumentumtípus** mezőben válassza a következő értékek egyikét:

- Az **Elektronikus** beállítással a konfigurált célokat alkalmazhatja, ha futásidőben nem ad meg felhasználói műveletkódot.
- A **Nyomtatáskezelés** beállítással a konfigurált célokat alkalmazhatja, ha futásidőben nem ad meg felhasználói műveletkódot.
- A **Bármely** mindig alkalmazhatja a konfigurált célokat, függetlenül attól, hogy futásidőben megad-e felhasználói műveletkódot.

Ha a **Nyomtatáskezelés** dokumentumtípust választja, meg kell adnia azokat a felhasználói műveleteket, amelyekre a konfigurált ER-célokat alkalmazni kell. A **Nyomtatáskezelés művelet** mezőben válassza a következő értékek egyikét:

- A **Megtekintés** beállítással a konfigurált célokat alkalmazhatja, ha futásidőben meg van adva a **Megtekintés** felhasználói művelet.
- A **Nyomtatás** beállítással a konfigurált célokat alkalmazhatja, ha futásidőben meg van adva a **Nyomtatás** felhasználói művelet.
- A **Küldés** beállítással a konfigurált célokat alkalmazhatja, ha futásidőben meg van adva a **Küldés** felhasználói művelet.

> [!NOTE]
> Egyetlen célrekordhoz több művelet is kiválasztható.

Ha a **Bármely** dokumentumtípust választja, a **Nyomtatáskezelési művelet** mezőben felhasználói műveletként automatikusan az **Automatikus kijelölés** van kiválasztva, és a következő viselkedés történik:

- Ha futásidőben nincs megadva felhasználói műveletkód, a rendszer az összes konfigurált ER-célt alkalmazza.
- Ha futásidőben felhasználói műveletkódot ad meg, a program egy adott művelethez előre meghatározott ER-célt alkalmaz, **tekintet nélkül arra, hogy engedélyezve van-e**:

    - Ha futásidőben meg van adva a **Megtekintés** műveletet, a rendszer a **Képernyő** ER-célt alkalmazza.
    - Ha futásidőben meg van adva a **Küldés** műveletet, a rendszer az **E-mail** ER-célt alkalmazza.
    - Ha futásidőben meg van adva a **Nyomtatás** műveletet, a rendszer a **Nyomtató** ER-célt alkalmazza.

A **Szabadszöveges számla (Excel)** ER-formátum használatával például a feladott [szabadszöveges számlát](https://docs.microsoft.com/dynamics365/finance/accounts-receivable/create-free-text-invoice-new) nyomtathatja ki. A generált dokumentumok útvonalának eléréséhez konfigurálnia kell az ER-célokat ehhez az ER-formátumhoz. Például előfordulhat, hogy konfigurálnia kell ezeket az ER-célokat, hogy a következő műveleteket hajtsa végre egy generált dokumentumon:

- A dokumentum archiválása, ha az ER-formátum fut, de nincs megadott műveletkódot (például a dokumentum elektronikus továbbítása esetén).
- A dokumentum előnézete a böngészőben, amikor a felhasználó végrehajtja a **Megtekintés** műveletet.
- A dokumentum archiválása és nyomtatása a **Nyomtatás** művelet végrehajtásakor.
- A dokumentum archiválása és elküldése e-mailben, kimenő e-mail mellékleteként, amikor a felhasználó végrehajtja a **Küldés** műveletet.

A következő ábra bemutatja, hogy hogyan lehet elérni ezt a konfigurált ER-célt egyedi célrekordok készleteként, amikor minden rekordot egy adott felhasználói művelethez konfigurálnak:

![Elektronikus jelentési céloldal, amely műveletfüggő célbeállításokkal rendelkezik egy ER-formátumhoz, ha minden célrekord konfigurálva van egy felhasználói művelethez.](./media/er-destination-action-dependent-01.png)

A következő ábra bemutatja, hogy hogyan lehet elérni ugyanazon alternatív módon konfigurált ER-célokat egyedi célrekordok készleteként, amikor minden rekordot egy adott célhoz konfigurálnak:

![Elektronikus jelentési céloldal, amely műveletfüggő célbeállításokkal rendelkezik egy ER-formátumhoz, ha minden célrekord konfigurálva van egy célhoz](./media/er-destination-action-dependent-01a.png)

> [!NOTE]
> Ha a futó ER-formátumhoz meg van adva egy műveletkódot, de az adott műveletkódhoz nincsenek beállítva célok, a program az [alapértelmezett](electronic-reporting-destinations.md#default-behavior) célviselkedést alkalmazza.

## <a name="change-action-dependent-er-destinations-at-runtime"></a>Műveletfüggő ER-célok módosítása futásidőben

Ha ER-formátumot futtat, és olyan felhasználók létesítenek felhasználói műveleteket, akik rendelkeznek a megfelelő [engedélyekkel](electronic-reporting-destinations.md#security-considerations) a konfigurált célbeállítások futásidőben való módosításához, megjelenik egy párbeszédpanel, amely lehetőséget ad a konfigurált célbeállítások módosítására. Ez a párbeszédpanel nem kötelező, és megjelenésének módja attól függ, hogy az ER-keretrendszer hogyan valósítja meg az ER-formátumot. Ha megjelenik ez a párbeszédpanel, a mezőben található ER-célok a megadott felhasználói műveletnek megfelelően lesznek engedélyezve.

A következő ábra az **Elektronikus jelentési formátum célokat** bemutató párbeszédpanel egy példáját mutatja be, amely a szabadszöveges számla [feladása](https://docs.microsoft.com/dynamics365/finance/accounts-receivable/create-free-text-invoice-new) esetén jelenik meg, és a **Szabadszöveges számla (Excel)** ER-formátumának futtatásával generálja ezt a dokumentumot, ha a **Nyomtató** művelet létesítve van, és az ER-célok erre a formátumra vannak konfigurálva, amint az ebben a témakörben korábban látható.

![Párbeszédpanel, amely lehetőséget ad a kezdetben konfigurált ER-célok megváltoztatására a futó ER-formátumhoz](./media/er-destination-action-dependent-02.gif)

> [!NOTE]
> Ha az ER-célokat a futó ER-formátum több összetevőjéhez konfigurálta, akkor a rendszer az ER-formátum minden konfigurált összetevőjét külön fel fog kínálni egy opciót.

## <a name="verify-the-provided-user-action"></a>A megadott felhasználói művelet ellenőrzése

Ellenőrizheti, hogy egy adott felhasználói művelet végrehajtásakor a futó ER-formátumhoz milyen felhasználói művelet van megadva, ha van ilyen. Ez az ellenőrzés akkor fontos, amikor műveletfüggő ER-célokat kell konfigurálnia, de nem biztos abban, hogy melyik felhasználói műveletkód van megadva, ha van ilyen. Amikor például elkezdi egy szabadszöveges számla feladását, és a **Számla nyomtatása** beállítást **Igen** beállításra állíthatja a **Szabadszöveges számla feladása** párbeszédpanelen, a **Nyomtatáskezelés cél használata** beállítást **Igen** vagy **Nem** beállításra állíthatja.

A következő lépések szerint ellenőrizze a megadott felhasználói műveletkódot.

1. Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**.
2. A **Konfigurációk** oldal műveleti ablaktábláján, a **Konfigurációk** lapon, a **Speciális beállítások** csoportban válassza a **Felhasználói paraméterek** lehetőséget.
3. A **Felhasználói paraméterek** párbeszédpanelen [állítsa](er-trace-reports-compare-baseline.md#configure-er-parameters-to-use-the-baseline-feature) a **Futtatás hibakeresési módban** az **Igen** értékre.
4. Felhasználói művelet végrehajtása ER-formátum futtatásával. Ne feledje, hogy az ER felhasználói paraméterek felhasználó- és vállalatspecifikusak.
5. Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk hibakeresési naplói**.
6. A **Konfiguráció hibakeresési naplói** lapon szűrje az ER futtatási naplóit, és keresse meg a futtatott ER-formátum naplóját.
7. Ellenőrizze a naplónak azokat a bejegyzéseit, amely a megadott felhasználói műveletkódot tartalmazó rekordot tartalmazzák, ha van művelet az ER-formátum futtatásához.

    ![Az elektronikus jelentési futtatási naplók lapja, amely az ER-formátumok szűrt futtatásához megadott felhasználói műveletkódról tartalmaz információkat.](./media/er-destination-action-dependent-03.png)

## <a name=""></a><a name="reports-list-wave1">Üzleti dokumentumok listája (1. hullám)</a>

Az üzleti dokumentumok következő listáját a következő funkció vezérli: **PM-jelentések kimenetének útvonalválasztása a felhasználói műveletspecifikus (1. hullám) ER-célok alapján**:

- Ügyfélszámla (szabadszöveges számla)
- Ügyfélszámla (értékesítési számla)
- Beszerzési rendelés
- Beszerzési rendelés beszerzési értesítője
- Értékesítési rendelés  visszaigazolása
- Kollekciók fizetésre felszólítás
- Vevő számlakivonata
- Kamatlevél
- Szállítói kifizetési bizonylat
- Ajánlatkérés

## <a name="additional-resources"></a>További erőforrások

[Elektronikus jelentéskészítés (ER) áttekintése](general-electronic-reporting.md)

[Elektronikus jelentéskészítés (ER) céljai](electronic-reporting-destinations.md)

[Elektronikus jelentési keretrendszer API módosításai az Application update 10.0.17 számára](er-apis-app10-0-17.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]