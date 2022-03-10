---
title: Üzletidokumentum-kezelés – áttekintés
description: Ez a témakör azt mutatja be, hogyan lehet használni az ER-keretrendszer üzletidokumentum-kezelő funkcióját.
author: NickSelin
ms.date: 04/23/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: ERBDWorkspace, ERBDParameters, ERSecurityAccessEditor
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-08-01
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: faea9d4d9b3fc8f3f1474b6bb2a8dc31cdc22511
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2022
ms.locfileid: "7986251"
---
# <a name="business-document-management-overview"></a>Üzletidokumentum-kezelés – áttekintés

[!include [banner](../includes/banner.md)]

Az [elektronikus jelentési (ER)](general-electronic-reporting.md) keretrendszer a különböző országok/régiók jogi követelményeinek megfelelő formátumú elektronikus dokumentumok konfigurálását teszi lehetővé a Business felhasználói számára. A felhasználók definiálhatják az adatfolyamot, amely meghatározza, hogy milyen alkalmazásadatok kerüljenek a létrejövő dokumentumokba. Az ER keretrendszer előre definiált sablonok használatával készít kimenő dokumentumokat Microsoft Office formátumban (Excel-munkafüzetek vagy Word-dokumentumok). A sablonokat a program a szükséges adatokkal a konfigurált adatfolyammal tölti ki, miközben a szükséges dokumentumokat generálja. Minden konfigurált formátum közzétehető egy ER-megoldás részeként kimenő dokumentumok előállítása céljából. Ezt egy olyan ER formátumú konfiguráció képviseli, amely a különböző kimenő dokumentumok létrehozásához használható sablonokat tartalmazza. Az üzleti felhasználók ezt a keretrendszert használhatják a szükséges üzleti dokumentumok kezelésére.

**Az Üzleti dokumentumkezelés** az ER-keretrendszerre épül, és lehetővé teszi az üzleti felhasználók számára, hogy a szolgáltatások vagy a Microsoft 365 szolgáltatások vagy a megfelelő Microsoft Office asztali alkalmazások segítségével szerkesszék az üzleti dokumentumok sablonjait. Az üzleti dokumentumok szerkesztésével módosulhatnak az üzleti dokumentumok megjelenése, és a további adathelyőrzők a forráskód módosítása és az új telepítések nélkül is megadhatók. Az üzleti dokumentumok sablonjainak frissítéséhez nem szükséges az ER keretrendszer ismerete.

> [!NOTE]
> Ügyeljen arra, hogy az üzleti Dokumentumkezelés lehetővé teszi az üzleti dokumentumok (például rendelések, számlák stb.) előállításához használt sablonok módosítását. Amikor egy sablon módosult, és a rendszer egy új verziót publikált, ez a verzió lesz használva a szükséges üzleti dokumentumok létrehozásához. Az Üzleti dokumentumkezelés nem használható a már létrehozott üzleti dokumentumok módosításához.

## <a name="supported-deployments"></a>Támogatott telepítések

Az üzleti dokumentumkezelő funkció jelenleg csak felhő-telepítések esetén van bevezetve. Ha ez a funkció kritikus fontosságú egy helyszíni telepítéshez, tudassa velünk; adjon visszajelzést az [Ötletek](https://experience.dynamics.com/ideas/) webhelyen.

## <a name="supported-microsoft-office-applications"></a>Támogatott Microsoft Office-alkalmazások

Az Excel vagy Word formátumú sablonoknak a Microsoft Office asztali alkalmazások segítségével történő szerkesztéséhez az üzleti dokumentumkezelés használatával a Microsoft Office 2010 vagy újabb verziót kell telepítenie. Ez a felhőalapú és helyszíni telepítésű verziókban is támogatott

Ahhoz, hogy az üzleti dokumentumkezelést használni tudja az Excel- és Word-formátumokban használt sablonok alkalmazások használatával való szerkesztéséhez, az Microsoft 365 Microsoft 365 Office for the web-előfizetés szükséges. Ezt a felhőtelepítés támogatja.

## <a name="business-document-availability"></a>Üzleti dokumentum elérhetősége

Az októberi 2019 kiadásra tervezett összes jelentés teljes listája megtalálható a [Konfigurálható üzleti jelentések Word és Excel szoftverekben](/dynamics365-release-plan/2019wave2/dynamics365-finance-operations/configurable-business-documents-reporting-word-excel-pdf#feature-details) szakaszban.

Az októberi 2020 kiadásra tervezett összes jelentés teljes listája megtalálható a [Konfigurálható üzleti jelentések – Word-sablonok](/dynamics365-release-plan/2020wave1/dynamics365-finance/configurable-business-documents-word-templates) szakaszban.

A későbbi verziókban további jelentések válnak elérhetővé. A további jelentésekkel kapcsolatos különleges értesítések küldése külön történik. Az aktuálisan elérhető jelentések listájának áttekintéséről lásd: [ER-konfigurációk listája, amelyeket a Finance tartalmaz a konfigurálható üzleti dokumentumok támogatására](#list-of-configurations-cbd).

Ha további tájékoztatást szeretne erről a funkcióról, végezze el a példafeladatot ebben a témakörben.

## <a name="configure-er-parameters"></a>ER-paraméterek konfigurálása

Mivel az üzleti Dokumentumkezelés az ER-keretrendszerre épül, konfigurálnia kell az ER paramétereit az üzleti dokumentumkezelés használatának megkezdéséhez. Ehhez be kell állítania az ER-paramétereket az [Elektronikus jelentéskészítés (ER) keretrendszer konfigurálása](electronic-reporting-er-configure-parameters.md) témakörben leírtak szerint. Új konfigurációs szolgáltatókat is meg kell adni a [A konfigurációs szolgáltatók létrehozása és megjelölése aktívként](tasks/er-configuration-provider-mark-it-active-2016-11.md) szakaszban leírtak szerint.

![ER-munkaterület.](./media/BDM-Overview-ERSetting.png)

## <a name="import-er-solutions"></a>ER-megoldások importálása

A minta ER konfigurációk a következő példában használatosak:. Importálnia kell a Dynamics 365 Finance aktuális példányába azokat az ER konfigurációkat, amelyek az üzletidokumentum-kezelés használatával szerkeszthető üzletidokumentum-sablonokat tartalmazzák. A következő fájlok letöltésével, majd helyben történő tárolásával hajthatja végre ezt a műveletet.

**ER vevői számlázási mintamegoldása**

| Fájl                                      | Tartalom |
|-------------------------------------------|---------|
| Customer invoicing model.version.2.xml    | [ER-adatmodell konfigurációja](https://download.microsoft.com/download/b/f/a/bfa5cb52-e6e2-42bc-a4c0-77014a4c54e6/Customerinvoicingmodel.version.2.xml) |
| Customer FTI report (GER).version.2.3.xml | [Szabadszöveges számla ER-formátumkonfigurációija](https://download.microsoft.com/download/3/c/2/3c2e58f2-6e56-43d9-85ea-4c97252a108d/CustomerFTIreportGER.version.2.3.xml) |

**ER kifizetési csekkek mintája**

| Fájl                                     | Tartalom |
|------------------------------------------|---------|
| Model for cheques.version.10.xml         | [ER-adatmodell konfigurációja](https://download.microsoft.com/download/3/7/6/376cb0f6-181a-4895-a432-390ffca64162/Modelforcheques.version.10.xml) |
| Cheques printing format.version.10.9.xml | [Fizetési csekk ER formátumkonfigurációja](https://download.microsoft.com/download/6/d/6/6d61bfff-3d89-4377-9e34-2e3ee6d6df91/Chequesprintingformat.version.10.9.xml) |

**ER külföldi kereskedelmi megoldás mintája**

| Fájl                             | Tartalom |
|----------------------------------|---------|
| Intrastat model.version.1.xml    | [ER-adatmodell konfigurációja](https://download.microsoft.com/download/2/0/0/200d6ed1-eff8-48ec-ab75-175a4acf9714/Intrastatmodel.version.1.xml) |
| Intrastat report.version.1.9.xml | [Intrastat-ellenőrzési jelentés ER formátumának konfigurálása](https://download.microsoft.com/download/7/a/2/7a2a27c3-a8a5-42a1-9d04-f0a8e1ec1707/Intrastatreport.version.1.9.xml) |

A következő eljárással importálhatja az egyes fájlokat. Importálja az ER *adatmodell* konfigurációját az egyes elektronikus megoldásokhoz a fenti táblázat alapján, mielőtt importálná a kapcsolódó ER *formátumkonfigurációt*.

1. Nyissa meg a **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk** oldalt.
2. Válassza a **Csere** lehetőséget az oldal tetején.
3. Kattintson a **Betöltés XML-fájlból** lehetőségre.
4. A szükséges XML-fájl betöltéséhez kattintson a **Tallózás** gombra.
5. A konfiguráció importálásának jóváhagyásához kattintson az **OK** gombra.

![Konfigurációimportálást megerősítő ER-konfigurációk oldal.](./media/BDM-Overview-ERSolutions.png)

Azt is megteheti, hogy a hivatalosan közzétett ER formátumkonfigurációkat importálja a Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásból. Ennek az eljárásnak a végrehajtásához például importálni lehet a **Szabadszöveges számla (Excel)** ER formátumának konfigurációját. A program automatikusan importálja a megfelelő ER adatmodellt és az ER modell-leképezési konfigurációkat.

![Az LCS közös eszközök tárának tartalomoldala.](./media/BDM-Overview-SharedAssetLibrary.png)

Az ER-konfigurációk importálásával kapcsolatos további tudnivalókat lásd: [Elektronikus jelentéskészítési konfigurációk életciklusainak kezelése](general-electronic-reporting-manage-configuration-lifecycle.md).

## <a name="enable-business-document-management"></a>Az Üzletidokumentum-kezelés engedélyezése

Az Üzletidokumentum-kezelés elindításához meg kell nyitnia a **Funkciókezelés** munkaterületet , és engedélyeznie kell az **Üzletidokumentum-kezelés** funkciót.

A következő eljárással engedélyezheti az üzletidokumentum-kezelési funkciókat az összes jogi személy számára.

1. Nyissa meg a **Funkciókezelés** munkaterületet.
2. Az **Új** lapon válassza ki a **Üzletidokumentum-kezelés** funkciót a listából.
3. Válassza az **Engedélyezés most** lehetőséget a kiválasztott funkció bekapcsolásához.
4. Az új funkció eléréséhez frissítse a lapot.

> [!NOTE]
> További tájékoztatás az üzleti dokumentumkezelés új dokumentum felhasználói felületének használatáról: [Az új dokumentum felhasználói felület az üzleti Dokumentumkezelés modulban.](er-business-document-management-new-template-ui.md).

![A Funkciókezelés munkaterület.](./media/BDM-Overview-FMEnabling.png)

Az új funkciók aktiválásával kapcsolatos további tudnivalókat lásd [Funkciókezelés áttekintése](../../fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="configure-parameters"></a>Paraméterek konfigurálása

A következő szakaszokban található információk alapján beállíthatja az Üzletidokumentum-kezelés alapvető paramétereit.

### <a name="prerequisites-for-parameter-setup"></a>A paraméterek beállításának előfeltételei

Mielőtt beállíthatná az üzleti dokumentumok kezelését, be kell állítania a szükséges dokumentumtípust a dokumentumkezelési keretrendszerben. Ez a dokumentumtípus az Office-formátumokban (Excel és Word) használt dokumentumok ideiglenes tárolását határozza meg, amlyek sablonok az elektronikus jelentésekhez. Az ideiglenes tárolási sablon az Office asztali alkalmazások segítségével szerkeszthető.

Ehhez a dokumentum típushoz ki kell választani a következő attribútum-értékeket.

| Attribútum neve | Attribútumérték |
|----------------|-----------------|
| Osztály          | Fájl csatolása     |
| Csoport          | Fájl            |
| Helyszín       | SharePoint      |

A szükséges dokumentumkezelési paraméterek és dokumentumtípusok beállításával kapcsolatos tudnivalókat lásd: [Dokumentumkezelés konfigurálása.](../../fin-ops/organization-administration/configure-document-management.md).

![Dokumentumkezelés dokumentumtípusának beállítása.](./media/BDM-Overview-DMSetting.png)

### <a name="set-up-parameters"></a><a name="SetupBdmParameters"></a>Paraméterek beállítása

Az alapvető üzletidokumentum-paraméterek lapon beállíthatja az alapvető az **Üzleti dokumentumok paraméterei** oldalon állíthatók be. Csak meghatározott felhasználók férhetnek hozzá a laphoz. Ezek közé a következők tartoznak:

- A **Rendszergazda** szerepkörhöz hozzárendelt felhasználók.
- Azon felhasználók, akik olyan szerepkörhöz vannak hozzárendelve, amely **Az Üzleti dokumentumkezelés paraméterei** (AOT- **ERBDMaintainParameters**) helyen meghatározott feladatokat végezhet el.

A következő eljárással beállíthatja az összes jogi személy alapvető paramétereit.

1. Az **Üzleti dokumentum paraméterei** lapjához való hozzáféréssel rendelkező felhasználóként jelentkezzen be.
2. Nyissa meg a **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Üzleti dokumentumok kezelése** \> **Üzleti dokumentumok paraméterei** lapot.
3. Az **Üzleti dokumentum paraméterei** lap **Mellékletek** lapjának **SharePoint bizonylattípus** mezőjében határozza meg, hogy milyen dokumentumtípusban szeretné ideiglenesen tárolni az Office-formátumú sablonokat, amikor azok szerkesztése történik asztali Office alkalmazásokkal. 

> [!NOTE]
> Csak azok a dokumentumtípusok érhetők el ehhez a paraméterhez, amelyek egy SharePoint-hely használatával vannak konfigurálva.

![Üzleti dokumentumkezelés paramétereinek beállítása.](./media/BDM-Overview-BDMSetting.png)

A kiválasztott dokumentumtípus a vállalatspecifikus, és akkor használatos, ha a felhasználó az Üzleti dokumentumkezelés modulban dolgozik azon a vállalatnál, amelyhez a kiválasztott dokumentumtípus be van állítva. Ha a felhasználó az Üzleti dokumentumkezelés modulban egy másik vállalatnál dolgozik, ugyanez a dokumentumtípus lesz használva, ha nem lett ehhez a vállalathoz ilyen konfigurálva. Ha egy dokumentumtípus lett konfigurálva, akkor ez lesz használva a **SharePoint-dokumentumtípus** mezőben kiválasztott típus helyett.

> [!NOTE]
> A **SharePoint dokumentumtípus** paraméterrel egy SharePoint mappa határozható meg ideiglenes tárolóhelyként a Microsoft Excel vagy a Word használatával szerkeszthető sablonokhoz. Akkor kell beállítani ezt a paramétert, ha az Office asztali alkalmazásokat szeretné használni a sablonok szerkesztéséhez. A további tudnivalókat lásd [Sablon szerkesztése az Office asztali alkalmazásban](#EditInOfficeDesktopApp). Ha a sablont csak a funkció használatával tervezi módosítani, akkor ezt a paramétert üresen hagyhatja Microsoft 365. További tájékoztatás: [Sablon szerkezstése az Microsoft 365 megoldásban](#EditInOffice365).

## <a name="configure-access-permissions"></a>Hozzáférési engedélyek konfigurálása

Alapértelmezés szerint, amikor az üzleti dokumentumkezelő engedélyeihez való hozzáférés nincs engedélyezve, minden, az üzleti dokumentumkezelő munkaterülethez hozzáférő felhasználó látni fogja az alkalmazásban rendelkezésre álló összes megoldás-sablont. Az Üzletidokumentum-kezelés munkaterület csak azokat a sablonokat jeleníti meg, amelyek a elektronikus formátum konfigurációban vannak, és amelyeket egy **Üzleti dokumentumtípus** címkével vannak megjelölve.

![ER konfigurációs lap Üzleti dokumentumtípus címkével.](./media/BDM-Overview-ERFormatTags.png)

Az üzleti dokumentumok kezelése munkaterületen elérhető sablonok listája korlátozható hozzáférési engedélyek konfigurálásával. Ez akkor lehet fontos, ha a különböző sablonok a különböző üzleti tartományok számára (funkcionális területek) szükségesek üzleti dokumentumok előállítására, és engedélyezni szeretné, hogy az egyes felhasználók különböző sablonokhoz férjenek hozzá szerkesztés céljából az Üzleti dokumentumok kezelése munkaterületen.

Az üzleti dokumentumok kezelése hozzáférési engedélyeit a **Hozzáférési engedélyek konfigurátorában** lehet megadni. Csak a következő felhasználók férhetnek hozzá a laphoz:

- A **Rendszergazda szerepkörhöz** hozzárendelt felhasználók.
- A kötelezettség elvégzésére beállított egyéb szerepkörhöz hozzárendelt felhasználók, **Az üzleti dokumentumok sablonjainak szerkesztéséhez szükséges engedélyek konfigurálása** (AOT-név **ERBDTemplatesSecurity**).

A következő eljárással állíthatja be az üzletidokumentum-kezelési funkcióinak elérésével kapcsolatos engedélyeket az összes jogi személy számára.

1. A **Hozzáférési engedélyek konfigurátora** laphoz való hozzáféréssel rendelkező felhasználóként jelentkezzen be az alkalmazásba.
2. Nyissa meg a **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Üzleti dokumentumok kezelése** \> **Hozzáférési engedélyek kezelése** lapot.

    Figyeljen oda az értesítésre, miszerint hogy az Üzleti dokumentumkezelés modulhoz jelenleg nincs engedélyezve a hozzáférési engedélyek használata.

    ![Üzleti dokumentumkezelő hozzáférési engedélyeinek konfigurátora lap.](./media/BDM-Overview-TemplatesAccess1.png)

    Ezzel a beállítással minden olyan felhasználó, aki bármely, olyan biztonsági szerepkörhöz van hozzárendelve, amely az **Üzleti dokumentumoksablonok kezelése** (AOT név **ERBDManageTemplates**) feladat elvégzéséhez be van állítva, meg tudja nyitni az üzleti dokumentum kezelése munkaterületet, és szerkesztheti az alkalmazásban rendelkezésre álló sablonokat.

    A következő ábra bemutatja, hogy milyen lehetőségek érhetők el az Üzleti dokumentumkezelés munkaterületen a **Kinnlevőség-adminisztrátor** szerepkörhöz hozzárendelt felhasználók számára. Az aktuális hozzáférési jogosultságok beállításával a felhasználó szerkesztheti a különböző funkcionális területek üzleti dokumentumait, többek között a számlázást, a szabályozási jelentéseket és a kifizetéseket is.

    ![A Kinnlevőségek adminisztrátor üzletidokumentum-kezelő munkaterületének lapja.](./media/BDM-Overview-TemplatesForAlice1.png)

3. A **Hozzáférési engedélyek konfigurátora** lapon válassza a **Hozzáférési engedélyek beállítása** lehetőséget.
4. A **Sablonok szerkesztésére vonatkozó hozzáférési engedélyek beállításai** párbeszédpanelen kapcsolja be a **Konfigurált hozzáférési engedélyek alkalmazása** beállítást.
5. Az **OK** gombra kattintva győződjön meg arról, hogy engedélyezve vannak az Üzleti-dokumentumkezelés hozzáférési engedélyei.

    ![Üzleti dokumentumkezelő hozzáférési engedélyeinek megerősítése.](./media/BDM-Overview-TemplatesAccess2.png)

6. Válassza a **Hozzáadás** lehetőséget egy új üzleti szerepkör megadásához, amelyhez konfigurálni kell az Üzleti dokumentumkezelés sablonjainak elérését.
7. A **Biztonsági szerepkörök** párbeszédpanelen válassza ki a **Kinnlevőség-adminisztrátor** szerepkört, majd az **OK** gombbal nyugtázza a szerepkör beállítását.
8. A **Hozzáférési engedélyek címkék szerint** lapon válassza az **Új** lehetőséget.
9. A **Címke típusa** mezőben válassza a **Működési terület** elemet, majd az **Azonosító** mezőben válassza a **Számlázás** elemet.
10. Válassza a **Mentés** lehetőséget a megadott szerepkörhöz konfigurált hozzáférési engedélyek tárolásához.

    Az aktuális beállítás azt jelenti, hogy minden olyan felhasználó számára, aki **a Kinnlevőségek-adminisztrátor** szerepkörhöz van rendelve, és az **Üzleti dokumentumoksablonok kezelése** (AOT-név **ERBDManageTemplates**), feladatot látja el azon elektronikus formátumú konfigurációs sablonok, amelyek a **Számlázás** értékkel rendelkeznek a **Működési terület** címkében, elérhetők szerkesztésre az Üzleti dokumentumkezelés munkaterületen.

11. Váltson át a **Kapcsolódó információ** ablaktáblára az aktuális lap jobb oldaláról. A **Kapcsolódó információ** ablaktábla bemutatja, hogy hogyan lesznek alkalmazva a konfigurált hozzáférési engedélyek, többek között a **Kinnlevőség-adminisztrátor** szerepkörhöz rendelt felhasználók számára elérhető konfigurációs sablonokat.

    ![Kapcsolódó információs ablaktábla a Hozzáférési engedélyek konfigurálása lapon.](./media/BDM-Overview-TemplatesAccess3.png)

12. A **Hozzáférési engedélyek konfigurációk szerint** lapon válassza az **Hozzáadás** lehetőséget.
13. A **Konfiguráció kiválasztása** párbeszédpanelen jelölje be az **Intrastat-jelentés** elektronikus jelentés formátumkonfigurációját.
14. Az **OK** gombra kattintva nyugtázza a kiválasztott konfigurációk bejegyzését, majd a **Mentés** gombra kattintva tárolhatja a megadott szerepkörhöz konfigurált hozzáférési engedélyeket.

Az aktuális beállítás azt jelenti, hogy minden olyan felhasználó számára, aki a **Kinnlevőségek-adminisztrátor** szerepkörhöz van rendelve, és az **Üzleti dokumentumoksablonok kezelése** (AOT-név **ERBDManageTemplates**), feladatot látja el aa következő sablonok elérhetők szerkesztésre az Üzleti dokumentumkezelés munkaterületen:

- Sablonok, amelyek a **Számlázás** értékkel rendelkeznek a **Működési terület** címkében.
- Sablonok, amelyek olyan elektronikus formátumkonfigurációkból származnak, amelyek fel vannak sorolva a **Hozzáférési engedélyek konfigurációnként** lapon (például sablonok az **Intrastat jelentés** formátumkonfigurációból a **Kötelezően előírt jelentéskészítés** tartományból).

![Hozzáférési engedélyek gyorslap a Hozzáférési engedélyek konfigurátora lapon.](./media/BDM-Overview-TemplatesAccess4.png)

A következő ábra bemutatja, hogy milyen lehetőséget kínál az Üzleti dokumentumkezelés munkaterület a **Kinnlevőség-adminisztrátor** szerepkörhöz hozzárendelt felhasználók számára. Az aktuális Üzleti dokumentumkezelés hozzáférési engedélybeállításával a felhasználó szerkesztheti az üzleti dokumentumok sablonjait a **Számlázás** tartományból, és az **Intrastat-jelentés** elektronikus formátumkonfigurációjából. A **Kifizetések** tartomány sablonjai nem érhetők el a **Kinnlevőség-adminisztrátor** szerepkör számára.

![Üzleti dokumentumsablonok szerkesztése az Üzleti dokumentumkezelő munkaterület oldalon.](./media/BDM-Overview-TemplatesForAlice2.png)

> [!NOTE]
> A **Hozzáférési engedélyek konfigurációk szerint** szabályok egy elektronikus formátumkonfiguráció egyedi azonosítójával vannak tárolva. Ez azt jelenti, hogy ezeket a szabályokat nem törli a program, ha a rájuk hivatkozó elektronikus jelentéskészítési konfiguráció törlődik. Amikor törli a törölt konfigurációkat importál vissza példányba, ezek a szabályok újra megjelennek. A törölt konfigurációk újbóli importálása után a szabályokat nem kell újra beállítani.

## <a name="use-business-document-management-to-edit-templates"></a>Az üzleti dokumentumkezelés modul használata sablonok kezeléséhez

Az üzleti felhasználók hozzáférhetnek az üzleti dokumentumsablonokhoz a szerkesztéshez az Üzleti dokumentumok kezelése munkaterületen. Csak a következő felhasználók férhetnek hozzá az Üzleti dokumentumok kezelése munkaterülethez:

- A **Rendszergazda szerepkörhöz** hozzárendelt felhasználók.
- Azon felhasználók, akik olyan szerepkörhöz vannak hozzárendelve, amely **Üzleti dokumentumoksablonok kezelése** (AOT- **ERBDManageTemplates**) helyen meghatározott feladatokat végezhet el.

A következő eljárással szerkesztheti a szabadszöveges számlasablonokat az Üzleti dokumentumok kezelése munkaterületen. A művelet végrehajtása előtt el kell végeznie a témakör összes korábbi műveletét.

1. Az Üzleti dokumentum kezelése munkaterületre való hozzáféréssel rendelkező felhasználóként jelentkezzen be.
2. Nyissa meg az Üzletidokumentum-kezelés munkaterületet.

Amikor az **Office-szerű UI-élményt az üzleti Dokumentumkezelés számára** funkció ki van kapcsolva a **Funkciókezelés** munkaterületen, az **Üzleti dokumentumkezelés** munkaterületének fő rácsa a következő sablonokat jeleníti meg:

- Olyan sablonok, amelyek az Ön ER konfigurációs szolgáltatójának tulajdonában vannak (azaz az **elektronikus jelentési** munkaterületen aktívként megjelölt szolgáltató). Miután kiválasztotta a sablonok egyikét, a **Sablon szerkesztése** lehetőséggel elindíthatja vagy folytathatja annak szerkesztését.
- Más ER konfigurációszolgáltatók tulajdonában lévő sablonok szerkesztése. Miután kiválasztotta a sablonok egyikét, kiválaszthatja az **Új dokumentum** lehetőséget , és másolatot készíthet, amely az Ön ER konfigurációszolgáltatója tulajdonába kerül, majd megkezdheti a másolat szerkesztését.

![Sablonlista az Üzleti dokumentumkezelés munkaterület oldalán.](./media/BDM-Overview-EditingTemplate1.png)

A **Sablon** lap bemutatja a kiválasztott sablon tartalmát. Válassza a **Részletek** lapot a kiválasztott sablon részleteinek áttekintéséhez, valamint annak az elektronikusjelentés-formátumkonfigurációnak a megtekintéséhez, amelyben ez a sablon található. Figyelje meg, hogy minden sablon **Közzétett** állapotú, és a **Verzió** oszlopban nem tartalmaz részleteket. Ez azt jelenti, hogy ezek a sablonok jelenleg nincsenek szerkesztve.

Ha az **Office-szerű UI-élményt az üzleti Dokumentumkezelés számára** funkció be van kapcsolva a **Funkciókezelés** munkaterületen, akkor az **Üzleti dokumentumkezelés** munkaterületének fő rácsa azokat a sablonokat jeleníti meg, amelyek az Ön ER konfigurációs szolgáltatója (azaz az **Elektronikus jelentés** munkaterületen aktívként megjelölt szolgáltató) tulajdonában vannak. Miután kiválasztotta a sablonok egyikét, a **Sablon szerkesztése** lehetőséggel elindíthatja vagy folytathatja annak szerkesztését.

Ha más ER konfigurációs szolgáltatók által birtokolt sablonokat szeretne dolgozni, válassza az **Új dokumentum** lehetőséget, egy másolat létrehozásához, amely az Ön ER szolgáltatója tulajdonába kerül. Ezután szerkesztheti a másolatot. További információ: [Új dokumentum-felhasználói felület az üzleti Dokumentumkezelés modulban](er-business-document-management-new-template-ui.md).

### <a name="initiate-editing-templates-owned-by-your-configuration-provider"></a>A konfigurációs szolgáltató tulajdonában lévő sablonok szerkesztésének kezdeményezése

1. Az Üzletidokumentum-kezelés munkaterületen válassza ki a **Csekkek nyomtatási formátuma** sablont a listában.
2. Válassza ki az **Részletek** fület.

![Üzletidokumentum-kezelés munkaterület oldala, Részletek lap.](./media/BDM-Overview-EditingTemplate2.png)

A **Sablon szerkesztése** beállítás elérhető a kiválasztott sablonhoz. Ez a beállítás mindig elérhető olyan elektronikus formátumú sablon esetében, amelynek az aktív ER konfigurációs szolgáltató (**Litware, Inc.** ebben a példában) tulajdonosa. Ha a **Sablon szerkesztése** beállítás van kiválasztva, a mögöttes Elektronikus formátumkonfiguráció vázlatváltozatának meglévő sablonja lesz elérhető szerkesztésre.

### <a name="initiate-editing-templates-owned-by-other-providers"></a>Más szolgáltatók tulajdonában lévő sablonok szerkesztésének kezdeményezése

1. Az üzleti dokumentumkezelés munkaterületen válassza ki azt a dokumentumot, amelyet sablonként szeretne használni.

    ![Dokumentum kiválasztása az Üzleti dokumentumkezelés munkaterület lapon.](./media/BDM-Overview-EditingTemplate3.png)

2. Válassza ki az **Új dokumentum** majd a **Cím** mezőket, és szükség szerint módosítsa a szerkeszthető sablon címét. A program az ER formátumkonfiguráció elnevezésére használja a szöveget. Ne felejtse el, hogy a konfiguráció vázlatverziója (**Customer FTI report (GER) másolata**), amely tartalmazza a szerkesztett sablont, automatikusan meg lesz jelölve ezen ER-formátum futtatásához az aktuális felhasználóhoz. Ezzel egy időben a program az alap ER formátumból származó nem módosított eredeti sablon alapján futtatja ezt az ER formátumot bármely más felhasználó számára.
3. A **Név** mezőben módosítsa az automatikusan létrehozandó szerkeszthető sablon első verziójának nevét.
4. A **Megjegyzés** mezőben módosítsa a szerkeszthető sablon automatikusan létrehozott verziójának megjegyzését.
5. A szerkesztési folyamat kezdetének jóváhagyásához kattintson az **OK** gombra.

![Erősítse meg a szerkesztési folyamat kezdetét új sablon létrehozásához.](./media/BDM-Overview-EditingTemplate4.png)

Ha nincs másik szolgáltató, akkor felajánlja, hogy létrehozzon egyet. Ha nincs aktív szolgáltató, akkor a rendszer felkínál egyet, hogy aktiválja.

Szolgáltató létrehozásához módosítsa a szolgáltató nevét a **Név** mezőben, frissítse az új szolgáltató internetcímét az **Internetcím** mezőben, majd a megerősítéshez kattintson az **OK** gombra.

   ![Új szolgáltató létrehozása a BDM-ben.](./media/bdm_create_provider.png)

A meglévő szolgáltató aktiválásához válassza ki a szolgáltató nevét a **Konfigurációszolgáltató** mezőben, és válassza az **OK** gombot, a szolgáltató aktiválásához.

   ![Szolgáltató aktiválása a BDM-ben.](./media/bdm_choose_provider.png)

> [!NOTE]
> Minden egyes BDM-sablon a konfiguráció szerzőjeként hivatkozik a szolgáltatóra. Ezért van szükség egy aktív szolgáltatóra a sablonhoz.


Az **Új dokumentum** beállítás mindig elérhető olyan ER-formátumkonfiguráció sablonja esetében, amely egy jelenlegi és másik szolgáltatótól származik (a Microsoft ebben a példában), amelynek nincsenek revíziói. Ezt követően a szerkesztett sablon egy új, automatikusan létrejövő ER formátumkonfigurációban lesz tárolva.



### <a name="start-editing-a-template"></a>Sablonnal szerkesztésének elkezdése

1. A kiválasztott sablonból válassza ki az **Dokumentum szerkesztése** lehetőséget.
2. A **Név** mezőben módosítsa az automatikusan létrehozandó szerkeszthető sablon első verziójának nevét.
3. A **Megjegyzés** mezőben módosítsa a szerkeszthető sablon automatikusan létrehozott verziójának megjegyzését.

    ![Sablon szerkesztése az Üzleti dokumentumkezelés munkaterület oldalán.](./media/BDM-Overview-EditingTemplate5.png)

4. A szerkesztési folyamat kezdetének jóváhagyásához kattintson az **OK** gombra.

A **BDM sablonszerkesztő** lap megnyílik. A kiválasztott sablon elérhetővé válik az online szerkesztéshez a Microsoft 365 használatával.

![Az üzleti dokumentumkezelés sablonszerkesztő oldala.](./media/BDM-Overview-EditingLayout1.png)

### <a name="edit-a-template-in-microsoft-365"></a><a name="EditInOffice365"></a>Sablon szerkesztése az  megoldásban Microsoft 365

Módosíthatja a sablont az Microsoft 365 használatával. Például az Office Online webhelyen a sablon fejlécében lévő mező betűtípusát **Normál** értékről **Félkövérre** kell módosítani. Ezeket a módosításokat a rendszer automatikusan menti a szerkeszthető sablonban, amely az elsődleges sablon tárhelyén (alapértelmezés szerint az Azure blob tároló), amely konfigurálva van az ER keretrendszerben. Ez be van állítva az ER keretrendszerhez.

![Betűtípus módosítása félkövér betűtípusra a sablonfejlécben az Üzletidokumentum-kezelés sablonszerkesztő lapján.](./media/BDM-Overview-EditingLayout2.png)

### <a name="edit-a-template-in-the-office-desktop-application"></a><a name="EditInOfficeDesktopApp"></a>Sablon szerkesztése az Office asztali alkalmazásban

> [!NOTE]
> Ez a funkció csak akkor érhető el, ha a **SharePoint dokumentumtípus** paraméter megfelelően van konfigurálva. További információ: [Paraméterek konfigurálása](#SetupBdmParameters).

1. Jelölje be **Megnyitás az asztali alkalmazásban** ha módosítani szeretné a sablont az Office asztali alkalmazás funkciói segítségével (ebben a példában az Excel). A szerkeszthető sablont az állandó tárolóból az Üzletidokumentum-kezelés paraméterei között SharePoint mappaként megadott ideiglenes tárolóhelyre másolja a rendszer.
2. Győződjön meg róla, hogy a sablont az ideiglenes fájltárhelyből az Office asztali Excel alkalmazásban szeretné megnyitni.

    ![Az asztali Excel alkalmazásban megnyitott sablon.](./media/BDM-Overview-EditingLayout3.png)

3. Módosítsa a sablont. Például módosíthatja a mezők betűtípusát a fejlécben, ha a színt **fekete** értékről **kék** értékre módosítja.

    ![A sablon fejlécében található betűszín módosítása az asztali Excel alkalmazással.](./media/BDM-Overview-EditingLayout4.png)

4. Válassza az Excel asztali alkalmazás **Mentés** elemét, hogy a sablon változásai az ideiglenes tárolóban legyenek tárolva.

    ![Üzletidokumentum-kezelési sablonszerkesztő oldal módosításainak mentése az asztali Excel alkalmazással.](./media/BDM-Overview-EditingLayout5.png)

5. Zárja be az Excel asztali alkalmazást.
6. Válassza a **Tárolt másolat szinkronizálása** lehetőséget, ha szinkronizálni szeretné az ideiglenes sablon tárhelyét az állandó sablon tárhelyével.

> [!NOTE]
> Az ideiglenes fájlok tárhelyén található szerkeszthető sablon csak a sablonszerkesztés aktuális munkamenetéhez lesz megtartva. Ha befejezte ezt a munkamenetet a **BDM sablonszerkesztő** lapjának bezárásával, akkor a program törli a másolatot. Ha módosította a sablont az ideiglenes fájltérhelyen, és nem jelölte be a **Tárolt másolat szinkronizálása** lehetőséget , akkor a **BDM-sablonszerkesztő** lapjának bezárásakor egy üzenet meg fogja kérdezni, hogy a változtatásokat szeretné-e tárolni. Válassza az **Igen** beállítást, ha menteni szeretné a módosításokat a sablonban az állandó fájl helyén.

### <a name="validate-a-template"></a>Sablon érvényességének ellenőrzése

1. A **BDM sablonszerkesztő** lapján jelölje be a **Problémák keresése** lehetőséget a módosított sablon érvényesítéséhez az alapul szolgáló ER-formátumkonfigurációhoz képest. Hajtsa végre a javaslatokat (ha vannak), hogy a sablon illeszkedjen az alap ER formátumkonfiguráció formátumstruktúrájához.
2. A **Formátum megjelenítése** lehetőség kiválasztásával megjelenítheti a formátum aktuális szerkezetét az alap ER formátumkonfigurációból, amelyet a szerkeszthető sablonnal kell egyeztetni. 
3. A panel bezárásához válassz a **Formátum elrejtése** lehetőséget.

    ![BDM BDM-sablonszerkesztő lapja.](./media/BDM-Overview-EditingTemplate6.png)

4. Zárja be a **BDM sablonszerkesztő** lapot.

A frissített sablon megjelenik a **Sablon** lapon. Figyelje meg, hogy a szerkesztett sablon állapota most **Piszkozat**, és az aktuális verzió már nem üres. Ez azt jelenti, hogy a sablon szerkesztésének folyamata elindult.

![Frissített sablon az Üzleti dokumentumkezelés munkaterület oldalán.](./media/BDM-Overview-EditingTemplate5.png)

### <a name="test-the-modified-template"></a>A módosított sablon tesztelése 

1. Az alkalmazásban módosítsa a vállalatot az **USMF** vállalatra.
2. Válassza a következőt **Kinnlevőségek** \> **Számlák** \> **Kizárólag szabadszöveges számlák**.
3. Válassza ki az **FTI-00000002** számlát, majd válassza a **Nyomtatáskezelő** parancsot.
4. Válassza ki a **Modul – kintlévőségek** \> **Dokumentumok** \> **Szabadszöveges számla** \> **Eredeti dokumentum** szintet, hogy meghatározza a feldolgozandó számlák hatályát.
5. A **Jelentés formátuma** mezőben válassza ki a **Customer FTI report (GER) másolata** ER formátumot a megadott dokumentumszinthez.

    ![Nyomtatáskezelési beállítások oldal.](./media/BDM-Overview-TestRun1.png)

6. Az **Escape** gombbal zárja be az aktuális lapot.
7. Válassza a **Nyomtatás** lehetőséget, majd válassza a **Kiválasztott** lehetőséget.
8. Töltse le a dokumentumot, és nyissa meg az asztali Excel alkalmazás használatával.

![Szabadszöveges számlák oldal.](./media/BDM-Overview-TestRun2.png)

A módosított sablon a szabadszöveges számlajelentés generálására szolgál a kiválasztott tételhez. Annak elemzéséhez, hogy milyen hatással vannak a sablon módosításai erre a jelentésre, futtathatja ezt a jelentést egy alkalmazásmunkamenetben, közvetlenül azután, hogy módosította egy alkalmazásmunkamenetben.

### <a name="create-an-alternative-template-revision"></a>Alternatív sablonverzió létrehozása

1. Nyissa meg a **BDM sablonszerkesztő** lapott, és válassza ki a **Customer FTI report (GER) Copy** sablont.
2. A **Változatok** lapon válassza az **Új** elemet.
3. Ha szükséges, a **Név** mezőben módosítsa a második verzió nevét, és alapozza azt a jelenleg aktív első verzióra.
4. Ha szükséges, a **Megjegyzés** mezőben módosítsa a szerkeszthető sablon automatikusan létrehozott verziójának megjegyzését.

    ![Verziókezelés létrehozása a sablonhoz az Üzleti dokumentumkezelés munkaterület oldalán.](./media/BDM-Overview-AddRevision.png)

    Létrehozta az állandó sablontárhelyen tárolt sablon új verzióját. Ezután tovább szerkesztheti a jelenleg aktívként kiválasztott második verzió sablonját.

5. Válassza ki az első verziót, majd válassza a **Beállítás aktívként** lehetőséget. Más verziót is beállíthat aktívnak ha bármikor vissza szeretne térni a sablonnak ahhoz a változatához.
6. Válassza ki a második változatot, majd válassza a **Törlés** elemet.
7. Válassza az **OK** lehetőséget annak megerősítésére, hogy törölni szeretné a kiválasztott verziót. A nem aktív változatok bármelyikét törölheti, ha már nincs rájuk szükség.

### <a name="delete-a-modified-template"></a>Módosított sablon törlése

1. Válassza ki **Sablon** lapot a **BDM sablonszerkesztő** lapján.
2. Válassza a **Törlés** lehetőséget.
3. Ha az **Ok** gombra kattint a törlés jóváhagyásához **,Customer FTI report (GER) másolat** ER formátumot, amely tartalmazza a módosított sablont. Egyéb lehetőségek megismeréséhez válassza a **Mégsem** lehetőséget.

### <a name="revoke-changes-of-template"></a>Sablon módosításainak visszavonása

Amikor az aktuális aktív szolgáltató tulajdonában lévő ER-formátumból szerkeszti a sablont, a program felajánlja a sablonon végzett módosítások visszavonását.

![A sablon változásainak elutasítása az Üzleti dokumentumkezelés munkaterület oldalán.](./media/BDM-Overview-RevokeChanges.png)

1. Válassza ki **Sablon** lapot a **BDM sablonszerkesztő** lapján.
2. Válassza a **Visszavonás** lehetőséget.
3. Ha az **OK** gombra kattint a sablonban végzett módosítások visszavonásához, a módosított sablont a program felülírja az eredeti sablonnal, és minden módosítást eltávolít a program. Ha visszavonja a sablon módosításait, akkor lehetősége van arra, hogy törölje a sablont. Egyéb lehetőségek megismeréséhez válassza a **Mégsem** lehetőséget.

### <a name="publish-a-modified-template"></a>Módosított sablon közzététele

1. A **BDM sablonszerkesztő** lapon a **Sablon** lapon válassza a **Közzététel** lehetőséget.
2. Ha az **OK** gombra kattint a közzététel megerősítéséhez, akkor a származtatott **Customer FTI report (GER) másolat** ER formátum amely a módosított sablont tartalmazza, befejezettként lesz megjelölve. A módosított sablon elérhetővé válik a többi felhasználó számára. Az ER formátum befejezett verziói csak a sablon legutóbbi aktív felülvizsgálatát fogják megtartani. A többi változat törölve lesz. Egyéb lehetőségek megismeréséhez válassza a **Mégsem** lehetőséget.

## <a name="frequently-asked-questions"></a>Gyakori kérdések

### <a name="i-selected-edit-document-but-instead-of-going-to-the-bdm-template-editor-page-in-finance-i-was-sent-to-the-microsoft-365-webpage"></a>A Dokumentum szerkesztése beállítást választotta, de nem a Pénzügyi webhely BDM-sablonszerkesztő lapjára küldött a program, hanem a Microsoft 365 weblapra küldött.

Ez a probléma egy ismert hiba, amely Microsoft 365 átirányítást érint. Akkor fordul elő, amikor az Microsoft 365 első alkalommal jelentkezik be. A probléma megoldásához térjen vissza az előző lapra a böngészőben a **Vissza** gombbal.

### <a name="i-understand-how-to-edit-a-template-by-using-microsoft-365-in-the-first-application-session-and-how-to-use-the-template-in-the-second-application-session-and-adjust-the-template-to-see-how-my-changes-affect-the-generated-business-document-can-i-use-the-office-desktop-application-in-the-same-way"></a>Meg kell érteni, hogyan lehet sablont szerkeszteni az első pályázati munkamenetben, és hogyan lehet a sablont használni a második alkalmazás-munkamenetben, és módosítani a sablont, és látni, hogy a módosítások hogyan hatnak a létrehozott üzleti Microsoft 365 dokumentumra. Lehet ugyanúgy használni az Office asztali alkalmazást?

Igen, megteheti. Az első alkalmazásmunkamenetben válassza a **Megnyitás az asztali alkalmazásban** lehetőséget. A sablon az ideiglenes fájltárolási helyre kerül és megnyílik az Office asztali alkalmazásban. Ezután hajtsa végre a következő lépéseket a sablon módosításának előnézetéhez a létrehozott üzleti dokumentumban:

1. Végezze el a szükséges módosításokat a sablonban az Office asztali alkalmazás segítségével.
2. Válassza a **Mentés** elemet az Office asztali alkalmazásban.
3. Válassza ki **BDM-sablonszerkesztő** lapján az első alkalmazásmunkamenetnél a **Tárolt másolat szinkronizálása** lehetőséget.
4. Hajtsa végre ezt a sablon ER-formátumot a második alkalmazásmunkamentben.

### <a name="when-i-select-open-in-desktop-app-i-receive-the-following-error-message-value-cannot-be-null-parameter-name-externalid-how-do-i-work-around-this-issue"></a>Amikor a Megnyitás az asztali alkalmazásban lehetőséget választom, a következő hibaüzenet jelenik meg: „Az érték nem lehet null. Paraméter neve: externalId.” Hogyan lehet megoldani ezt a problémát?

Valószínűleg olyan Azure AD tartományból jelentkezett be az alkalmazás jelen példányába, amely eltér a az alkalmazás ezen példányának telepítéséhez használt Azure AD tartománytól. Mivel a SharePoint szolgáltatás, amely sablonokat tárol az Office asztali alkalmazásokkal történő szerkesztésre, a program ugyanazon tartományhoz tartozik, mint az alkalmazás nincs jogosultságunk a SharePoint szolgáltatás eléréséhez. A probléma megoldásához a megfelelő Azure AD tartománnyal rendelkező felhasználó hitelesítő adataival jelentkezzen be az aktuális példányba.

## <a name="additional-resources"></a>További erőforrások

[Elektronikus jelentéskészítés (ER) áttekintése](general-electronic-reporting.md)

[ER – Az OPENXML formátumban létrejövő jelentésekre vonatkozó konfigurációk tervezése (2016. november)](tasks/er-design-reports-openxml-2016-11.md)

[ER konfigurációk tervezése jelentések Word-formátumú előállításához](tasks/er-design-configuration-word-2016-11.md)

[Beágyazott képek és alakzatok az ER-rel generált dokumentumokban](electronic-reporting-embed-images-shapes.md)

[Elektronikus jelentéskészítés (ER) konfigurálása az adatok Power BI szolgáltatásba való lehívásához](general-electronic-reporting-report-configuration-get-data-powerbi.md)

## <a name="list-of-er-configurations-that-have-been-released-in-finance-to-support-configurable-business-documents"></a><a name="list-of-configurations-cbd"></a>A Finance megoldásban kiadott ER-konfigurációk listája a konfigurálható üzleti dokumentumok támogatásához

A Finance megoldásban az ER-konfigurációk [listája](general-electronic-reporting.md#list-of-configurations) folyamatosan frissül. Nyissa meg a [globális tárházat](er-download-configurations-global-repo.md) a jelenleg támogatott ER-konfigurációk listájának ellenőrzéshez. A globális tárház [szűrhető](../../../finance/localizations/enhanced-filtering-global-repo.md) a konfigurálható üzleti dokumentumok támogatásához használt ER-konfigurációk listájának áttekintéséhez.

![A globális tárház tartalmának szűrése a Konfigurációs tárház oldalon.](./media/bdm-overview-filterglobalrepo.gif)

Az alábbi táblázat bemutatja azon ER-konfigurációkat, amelyek konfigurálható üzleti dokumentumokat támogatnak, és amelyek 2020 decemberéig ki vannak adva a Finance megoldásban.

| Adatmodell konfigurációja    | Formátumkonfigurációk                           |
|-----------------------------|-------------------------------------------------|
| Fuvarlevélmodell        | Fuvarlevélmodell (Excel)                          |
|                             | Fuvarlevélmodell (Word)                           |
| Eredet igazolása modell | Eredet igazolása modell (Excel)                   |
|                             | Eredet igazolása modell (Word)                    |
| Számlamodell               | Vevői hitel és jóváírás (Excel)          |
|                             | Vevői hitel és jóváírás (Word)           |
|                             | Szabadszöveges számla (Excel)                       |
|                             | Szabadszöveges számla (Excel) (BH)                  |
|                             | Szabadszöveges számla (FR) (Excel)                  |
|                             | Szabadszöveges számla (LT) (Excel)                  |
|                             | Szabadszöveges számla (LV) (Excel)                  |
|                             | Szabadszöveges számla (PL) (Excel)                  |
|                             | Szabadszöveges számla (CZ) (Excel)                  |
|                             | Szabadszöveges számla (EE) (Excel)                  |
|                             | Szabadszöveges számla (HU) (Excel)                  |
|                             | Szabadszöveges számla (TH) (Excel)                  |
|                             | Szabadszöveges számla (Word)                        |
|                             | Projektszerződés sor elemei (Excel)             |
|                             | Projektszerződés sor elemei (CZ) (Excel)        |
|                             | Projektszerződés sor elemei (Excel) (BH)        |
|                             | Projektszerződés sor elemei (HU) (Excel)        |
|                             | Projektszerződés sor elemei (LT) (Excel)        |
|                             | Projektszerződés sor elemei (PL) (Excel)        |
|                             | Projektszerződés sor elemei (Word)              |
|                             | Projekt vevői visszatartásának felszabadítása (Excel)      |
|                             | Projekt vevői visszatartásának felszabadítása (CZ) (Excel) |
|                             | Projekt vevői visszatartásának felszabadítása (HU) (Excel) |
|                             | Projekt vevői visszatartásának felszabadítása (LT) (Excel) |
|                             | Projekt vevői visszatartásának felszabadítása (PL) (Excel) |
|                             | Projekt vevői visszatartásának felszabadítása (TH) (Excel) |
|                             | Projekt vevői visszatartásának felszabadítása (Word)       |
|                             | Projektszámla (Excel)                         |
|                             | Projektszámla (Word)                          |
|                             | Projektszámla (AE) (Excel)                    |
|                             | Projektszámla (CZ) (Excel)                    |
|                             | Projektszámla (Excel) (BH)                    |
|                             | Projektszámla (HU) (Excel)                    |
|                             | Projektszámla (JP) (Excel)                    |
|                             | Projektszámla (LT) (Excel)                    |
|                             | Projektszámla (PL) (Excel)                    |
|                             | Projektszámla (TH) (Excel)                    |
|                             | Teljes projektszámla (MY) (Excel)               |
|                             | Egyszerű projektszámla (MY) (Excel)             |
|                             | Projektkezelési számla (Excel)                  |
|                             | Projektkezelési számla (CZ) (Excel)             |
|                             | Projektkezelési számla (Excel) (BH)             |
|                             | Projektkezelési számla (HU) (Excel)             |
|                             | Projektkezelési számla (JP) (Excel)             |
|                             | Projektkezelési számla (LT) (Excel)             |
|                             | Projektkezelési számla (PL) (Excel)             |
|                             | Projektkezelési számla (Word)                   |
|                             | Beszerzési előlegszámla (Excel)                |
|                             | Beszerzési előlegszámla (Word)                 |
|                             | Értékesítési előlegszámla (Excel)                   |
|                             | Értékesítési előlegszámla (Word)                    |
|                             | Értékesítési előlegszámla (PL) (Excel)              |
|                             | Értékesítési számla (Excel)                           |
|                             | Értékesítési számla (Excel) (BH)                      |
|                             | Értékesítési számla (Excel) (CZ)                      |
|                             | Értékesítési számla (Excel) (EE)                      |
|                             | Értékesítési számla (Excel) (FR)                      |
|                             | Értékesítési számla (Excel) (HU)                      |
|                             | Értékesítési számla (Excel) (IN)                      |
|                             | Értékesítési számla (Excel) (LT)                      |
|                             | Értékesítési számla (Excel) (LV)                      |
|                             | Értékesítési számla (Excel) (PL)                      |
|                             | Értékesítési számla (Excel) (TH)                      |
|                             | Értékesítési számla (Word)                            |
|                             | TMS kereskedelmi számla (Excel)                  |
|                             | TMS kereskedelmi számla (Word)                   |
|                             | Szállítói számla dokumentum (Excel)                 |
|                             | Szállítói számla dokumentum (CZ) (Excel)            |
|                             | Szállítói számla dokumentum (HU) (Excel)            |
|                             | Szállítói számla dokumentum (IN) (Excel)            |
|                             | Szállítói számla dokumentum (LT) (Excel)            |
|                             | Szállítói számla dokumentum (LV) (Excel)            |
|                             | Szállítói számla dokumentum (MY) (Excel)            |
|                             | Szállítói számla dokumentum (Word)                  |
| Rendelési modell                 | Megállapodás megerősítése (Excel)                  |
|                             | Megállapodás megerősítése (Word)                   |
|                             | Beszerzési szerződés visszaigazolása (Excel)         |
|                             | Beszerzési szerződés visszaigazolása (Word)          |
|                             | Beszerzési rendelés (Excel)                          |
|                             | Beszerzési rendelés (CZ) (Excel)                     |
|                             | Beszerzésirendelés-értesítő (CZ) (Excel)             |
|                             | Beszerzési rendelés (HU) (Excel)                     |
|                             | Beszerzésirendelés-értesítő (HU) (Excel)             |
|                             | Beszerzési rendelés (Word)                           |
|                             | Beszerzésirendelés-értesítő (HU) (Excel)                  |
|                             | Beszerzésirendelés-értesítő (Word)                   |
|                             | Értékesítési rendelés visszaigazolása (Excel)                |
|                             | Értékesítési rendelés visszaigazolása (CZ) (Excel)           |
|                             | Értékesítési rendelés visszaigazolása (HU) (Excel)           |
|                             | Értékesítési rendelés visszaigazolása (Word)                 |
| Csomagjegyzékmodell          | Tároló tartalma (Excel)                      |
|                             | Tároló tartalma (Word)                       |
|                             | Rakománylista (Excel)                               |
|                             | Rakománylista (Word)                                |
|                             | Kitárolási lista (Excel)                            |
|                             | Kitárolási lista (CZ) (Excel)                       |
|                             | Kitárolási lista (Word)                             |
|                             | Termelési kitárolási lista (Excel)                    |
|                             | Termelési kitárolási lista (Word)                     |
|                             | Rakomány szállítási kitárolási listája (Excel)             |
|                             | Rakomány szállítási kitárolási listája (Word)              |
|                             | Szállítmány szállítási kitárolási listája (Excel)         |
|                             | Szállítmány szállítási kitárolási listája (Word)          |
|                             | Hullám szállítási kitárolási listája (Excel)             |
|                             | Hullám szállítási kitárolási listája (Word)              |
| Fizetési modell               | Vevői kifizetési bizonylat (Excel)                 |
|                             | Vevői kifizetési bizonylat (Word)                  |
|                             | Szállítói kifizetési bizonylat (Excel)                   |
|                             | Szállítói kifizetési bizonylat (Word)                    |
| Árajánlati modell             | Projektárajánlat (Excel)                       |
|                             | Projektárajánlat (Word)                        |
|                             | Ajánlatkérés (Excel)                   |
|                             | Ajánlatkérés (Elfogadás) (Excel)          |
|                             | Ajánlatkérés (Elfogadás) (Word)           |
|                             | Ajánlatkérés (Elutasítás) (Excel)          |
|                             | Ajánlatkérés (Elutasítás) (Word)           |
|                             | Ajánlatkérés (Visszatérítés) (Excel)          |
|                             | Ajánlatkérés (Visszatérítés) (Word)           |
|                             | Ajánlatkérés (Word)                    |
|                             | Értékesítési árajánlat (Excel)                         |
|                             | Értékesítési árajánlat (CZ) (Excel)                    |
|                             | Értékesítési árajánlat (HU) (Excel)                    |
|                             | Értékesítési árajánlat (Word)                          |
|                             | Értékesítési ajánlat visszaigazolása (Excel)            |
|                             | Értékesítési ajánlat visszaigazolása (Word)             |
| Egyeztetési modell        | Vevői számlakivonat, külső (Excel)             |
|                             | Vevői számlakivonat, külső (CN) (Excel)        |
|                             | Vevői számlakivonat, külső (Word)              |
|                             | Vevői számlakivonat, Franciaország (Excel)          |
| Emlékeztetőmodell              | Fizetésre felszólítás (Excel)                  |
|                             | Fizetésre felszólítás (CN) (Excel)             |
|                             | Fizetésre felszólítás (Word)                   |
|                             | Vevői kamatlevél (Excel)                  |
|                             | Vevői kamatlevél (Word)                   |
| Menetlevélmodell               | Rakománytender (Excel)                             |
|                             | Rakománytender (Word)                              |
|                             | Beszerzési rendelés szállítólevél (Excel)             |
|                             | Beszerzési rendelés szállítólevél (CZ) (Excel)        |
|                             | Beszerzési rendelés szállítólevél (Word)              |
|                             | Útvonal (Excel)                                   |
|                             | Útvonal (Word)                                    |
|                             | Értékesítési rendelés szállítólevél (Excel)                |
|                             | Értékesítési rendelés szállítólevél (CZ) (Excel)           |
|                             | Értékesítési rendelés szállítólevél (LT) (Excel)           |
|                             | Értékesítési rendelés szállítólevél (PL) (Excel)           |
|                             | Értékesítési rendelés szállítólevél (Word)                 |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
