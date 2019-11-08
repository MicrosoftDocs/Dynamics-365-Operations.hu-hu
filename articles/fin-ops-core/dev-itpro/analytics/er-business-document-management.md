---
title: Üzletidokumentum-kezelés – áttekintés
description: Ez a témakör azt mutatja be, hogyan lehet használni az ER-keretrendszer üzletidokumentum-kezelő funkcióját.
author: NickSelin
manager: AnnBe
ms.date: 08/09/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 05dee1efc4e817795824e3fa1c41093d48a97d78
ms.sourcegitcommit: 219a73371638a9a4c6076d4c88b95fb2ebe95b00
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/23/2019
ms.locfileid: "2652617"
---
# <a name="business-document-management-overview"></a>Üzletidokumentum-kezelés – áttekintés

Az [elektronikus jelentési keretrendszer (ER)](general-electronic-reporting.md) a különböző országok/régiók jogi követelményeinek megfelelő formátumú elektronikus dokumentumok konfigurálását teszi lehetővé a Business felhasználói számára. A felhasználók definiálhatják az adatfolyamot, amely meghatározza, hogy milyen alkalmazásadatok kerüljenek a létrejövő dokumentumokba. Az ER keretrendszer előre definiált sablonok használatával készít kimenő dokumentumokat Microsoft Office formátumban (Excel-munkafüzetek vagy Word-dokumentumok). A sablonokat a program a szükséges adatokkal a konfigurált adatfolyammal tölti ki, miközben a szükséges dokumentumokat generálja. Minden konfigurált formátum közzétehető egy ER-megoldás részeként kimenő dokumentumok előállítása céljából. Ezt egy olyan ER formátumú konfiguráció képviseli, amely a különböző kimenő dokumentumok létrehozásához használható sablonokat tartalmazza. Az üzleti felhasználók ezt a keretrendszert használhatják a szükséges üzleti dokumentumok kezelésére.

**Az Üzleti dokumentumkezelés** az ER-keretrendszerre épül, és lehetővé teszi az üzleti felhasználók számára, hogy a szolgáltatások vagy a Microsoft Office 365 szolgáltatások vagy a megfelelő Microsoft Office asztali alkalmazások segítségével szerkesszék az üzleti dokumentumok sablonjait. Az üzleti dokumentumok szerkesztésével módosulhatnak az üzleti dokumentumok megjelenése, és a további adathelyőrzők a forráskód módosítása és az új telepítések nélkül is megadhatók. Az üzleti dokumentumok sablonjainak frissítéséhez nem szükséges az ER keretrendszer ismerete.

> [!NOTE]
> Ügyeljen arra, hogy az üzleti Dokumentumkezelés lehetővé teszi az üzleti dokumentumok (például rendelések, számlák stb.) előállításához használt sablonok módosítását. Amikor egy sablon módosult, és a rendszer egy új verziót publikált, ez a verzió lesz használva a szükséges üzleti dokumentumok létrehozásához. Az Üzleti dokumentumkezelés nem használható a már létrehozott üzleti dokumentumok módosításához.

## <a name="supported-deployments"></a>Támogatott telepítések

Az üzleti dokumentumkezelő funkció jelenleg csak felhő-telepítések esetén van bevezetve. Ha ez a funkció kritikus fontosságú egy helyszíni telepítéshez, tudassa velünk; adjon visszajelzést az [Ötletek](https://experience.dynamics.com/ideas/) webhelyen.

## <a name="supported-microsoft-office-applications"></a>Támogatott Microsoft Office-alkalmazások

Az Excel vagy Word formátumú sablonoknak a Microsoft Office asztali alkalmazások segítségével történő szerkesztéséhez az üzleti dokumentumkezelés használatával a Microsoft Office 2010 vagy újabb verziót kell telepítenie. Ez a felhőalapú és helyszíni telepítésű verziókban is támogatott

## <a name="business-document-availability"></a>Üzleti dokumentum elérhetősége

A következő, Excel-alapú sablonokat tartalmazó jelentések válnak elérhetővé a nyilvános előzetes kiadásakor:

**Kinnlevőségek** (2019. augusztus)

- Értékesítési előlegszámla
- Értékesítési rendelés - szállítólevél

**Kötelezettségek** (2019. augusztus)

- Beszerzési előlegszámla
- Beszerzési rendelés
- Beszerzési rendelés - szállítólevél

További jelentések lesznek majd elérhetők. A további jelentésekkel kapcsolatos különleges értesítések küldése külön történik. 

Az októberi 2019 kiadásra tervezett összes jelentés teljes listája megtalálható a [Konfigurálható üzleti jelentések Word és Excel szoftverekben](https://docs.microsoft.com/en-us/dynamics365-release-plan/2019wave2/dynamics365-finance-operations/configurable-business-documents-reporting-word-excel-pdf#feature-details) szakaszban.

# <a name="example-enable-configure-and-use-business-document-management"></a>Példa: Az Üzleti dokumentumkezelés engedélyezése, konfigurálása és használata

Ha további tájékoztatást szeretne erről a funkcióról, végezze el a példafeladatot ebben a témakörben.

## <a name="configure-er-parameters"></a>ER-paraméterek konfigurálása

Mivel az üzleti Dokumentumkezelés az ER-keretrendszerre épül, konfigurálnia kell az ER paramétereit az üzleti dokumentumkezelés használatának megkezdéséhez. Ehhez be kell állítania az ER-paramétereket az [ER-keretrendszer konfigurálása](electronic-reporting-er-configure-parameters.md) témakörben leírtak szerint. Új konfigurációs szolgáltatókat is meg kell adni a [A konfigurációs szolgáltatók létrehozása és megjelölése aktívként](tasks/er-configuration-provider-mark-it-active-2016-11.md) szakaszban leírtak szerint.

![ER-munkaterület](./media/BDM-Overview-ERSetting.png)

## <a name="import-er-solutions"></a>ER-megoldások importálása

Az üzleti dokumentumok sablonokat tartalmazó ER-konfigurációkat importálnia kell az aktuális példányba. A következő fájlok letöltésével és helyben történő tárolásával hajthatja végre ezt a műveletet.

**ER vevői számlázási mintamegoldása**

| **Fájl**                                  | **Tartalom**                                |
|-------------------------------------------|--------------------------------------------|
| Customer invoicing model.version.2.xml    | [ER-adatmodell konfigurációja](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |
| Customer FTI report (GER).version.2.3.xml | [Szabadszöveges számla ER-formátumkonfigurációija](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |

**ER kifizetési csekkek mintája**

| **Fájl**                                  | **Tartalom**                                |
|-------------------------------------------|--------------------------------------------|
| Model for cheques.version.10.xml          | [ER-adatmodell konfigurációja](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |
| Cheques printing format.version.10.9.xml  | [Fizetési csekk ER formátumkonfigurációja](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |

**ER külföldi kereskedelmi megoldás mintája**

| **Fájl**                                  | **Tartalom**                                |
|-------------------------------------------|--------------------------------------------|
| Intrastat model.version.1.xml             | [ER-adatmodell konfigurációja](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |
| Intrastat report.version.1.9.xml          | [Intrastat-ellenőrzési jelentés ER formátumának konfigurálása](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |

A következő eljárással importálhatja az egyes fájlokat. Importálja az ER *adatmodell* konfigurációját az egyes elektronikus megoldásokhoz a fenti táblázat alapján, mielőtt importálná a kapcsolódó ER *formátumkonfigurációt*.

1. Nyissa meg a **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk** oldalt.
2. Válassza a **Csere** lehetőséget az oldal tetején.
3. Kattintson a **Betöltés XML-fájlból** lehetőségre.
4. A szükséges XML-fájl betöltéséhez kattintson a **Tallózás** gombra.
5. A konfiguráció importálásának jóváhagyásához kattintson az **OK** gombra.

![ER-konfigurációk oldal](./media/BDM-Overview-ERSolutions.png)

Az ER-konfigurációk importálásával kapcsolatos további tudnivalókat lásd: [Elektronikus jelentéskészítési konfigurációk életciklusainak kezelése](general-electronic-reporting-manage-configuration-lifecycle.md).

## <a name="enable-business-document-management"></a>Az Üzletidokumentum-kezelés engedélyezése

Az Üzletidokumentum-kezelés elindításához meg kell nyitnia a **Funkciókezelés** munkaterületet , és engedélyeznie kell az **Üzletidokumentum-kezelés** funkciót.

A következő eljárással engedélyezheti az üzletidokumentum-kezelési funkciókat az összes jogi személy számára.

1. Nyissa meg a **Funkciókezelés** munkaterületet.
2. Az **Új** lapon válassza ki a **Üzletidokumentum-kezelés** funkciót a listából.
3. Válassza az **Engedélyezés most** lehetőséget a kiválasztott funkció bekapcsolásához.
4. Az új funkció eléréséhez frissítse a lapot.

![A Funkciókezelés munkaterület](./media/BDM-Overview-FMEnabling.png)

Az új funkciók aktiválásával kapcsolatos további tudnivalókat lásd [Funkciókezelés áttekintése](https://docs.microsoft.com/en-us/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview).

## <a name="configure-parameters"></a>Paraméterek konfigurálása

A következő szakaszokban található információk alapján beállíthatja az Üzletidokumentum-kezelés alapvető paramétereit.

### <a name="prerequisites-for-parameter-setup"></a>A paraméterek beállításának előfeltételei
Mielőtt beállíthatná az üzleti dokumentumok kezelését, be kell állítania a szükséges dokumentumtípust a dokumentumkezelési keretrendszerben. Ez a dokumentumtípus az Office-formátumokban (Excel és Word) használt dokumentumok ideiglenes tárolását határozza meg, amlyek sablonok az elektronikus jelentésekhez. Az ideiglenes tárolási sablon az Office asztali alkalmazások segítségével szerkeszthető.

Ehhez a dokumentum típushoz ki kell választani a következő attribútum-értékeket.

| **Attribútum neve**  | **Attribútumérték**   |
|---------------------|-----------------------|
| Osztály               | Fájl csatolása           |
| Csoport               | Fájl                  |
| Helyszín            | SharePoint            |

A szükséges dokumentumkezelési paraméterek és dokumentumtípusok beállításával kapcsolatos tudnivalókat lásd: [Dokumentumkezelés konfigurálása.](https://docs.microsoft.com/en-us/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-document-management).

![Dokumentumkezelés dokumentumtípusának beállítása](./media/BDM-Overview-DMSetting.png)

### <a name="set-up-parameters"></a>Paraméterek beállítása

Az alapvető üzletidokumentum-paraméterek lapon beállíthatja az alapvető az **Üzleti dokumentumok paraméterei** oldalon állíthatók be. Csak meghatározott felhasználók férhetnek hozzá a laphoz. Ezek közé a következők tartoznak:

- A **Rendszergazda** szerepkörhöz hozzárendelt felhasználók.
- Azon felhasználók, akik olyan szerepkörhöz vannak hozzárendelve, amely **Az Üzleti dokumentumkezelés paraméterei** (AOT- **ERBDMaintainParameters**) helyen meghatározott feladatokat végezhet el.

A következő eljárással beállíthatja az összes jogi személy alapvető paramétereit.

1. Az **Üzleti dokumentum paraméterei** lapjához való hozzáféréssel rendelkező felhasználóként jelentkezzen be.
2. Nyissa meg a **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Üzleti dokumentumok kezelése** \> **Üzleti dokumentumok paraméterei** lapot.
3.  Az **Üzleti dokumentum paraméterei** lap **Mellékletek** lapjának **SharePoint bizonylattípus** mezőjében határozza meg, hogy milyen dokumentumtípusban szeretné ideiglenesen tárolni az Office-formátumú sablonokat, amikor azok szerkesztése történik asztali Office alkalmazásokkal. 

> [!NOTE]
> Csak azok a dokumentumtípusok érhetők el ehhez a paraméterhez, amelyek egy SharePoint-hely használatával vannak konfigurálva.

![Üzleti dokumentumkezelés paramétereinek beállítása](./media/BDM-Overview-BDMSetting.png)

A kiválasztott dokumentumtípus a vállalatspecifikus, és akkor használatos, ha a felhasználó az Üzleti dokumentumkezelés modulban dolgozik azon a vállalatnál, amelyhez a kiválasztott dokumentumtípus be van állítva. Ha a felhasználó az Üzleti dokumentumkezelés modulban egy másik vállalatnál dolgozik, ugyanez a dokumentumtípus lesz használva, ha nem lett ehhez a vállalathoz ilyen konfigurálva. Ha egy dokumentumtípus lett konfigurálva, akkor ez lesz használva a **SharePoint-dokumentumtípus** mezőben kiválasztott típus helyett.

## <a name="configure-access-permissions"></a>Hozzáférési engedélyek konfigurálása

Alapértelmezés szerint, amikor az üzleti dokumentumkezelő engedélyeihez való hozzáférés nincs engedélyezve, minden, az üzleti dokumentumkezelő munkaterülethez hozzáférő felhasználó látni fogja az alkalmazásban rendelkezésre álló összes megoldás-sablont. Az Üzletidokumentum-kezelés munkaterület csak azokat a sablonokat jeleníti meg, amelyek a elektronikus formátum konfigurációban vannak, és amelyeket egy **Üzleti dokumentumtípus** címkével vannak megjelölve.

![ER-konfigurációk oldal](./media/BDM-Overview-ERFormatTags.png)

Az üzleti dokumentumok kezelése munkaterületen elérhető sablonok listája korlátozható hozzáférési engedélyek konfigurálásával. Ez akkor lehet fontos, ha a különböző sablonok a különböző üzleti tartományok számára (funkcionális területek) szükségesek üzleti dokumentumok előállítására, és engedélyezni szeretné, hogy az egyes felhasználók különböző sablonokhoz férjenek hozzá szerkesztés céljából az Üzleti dokumentumok kezelése munkaterületen.

Az üzleti dokumentumok kezelése hozzáférési engedélyeit a **Hozzáférési engedélyek konfigurátorában** lehet megadni. Csak a következő felhasználók férhetnek hozzá a laphoz:

- A **Rendszergazda szerepkörhöz** hozzárendelt felhasználók.
- A kötelezettség elvégzésére beállított egyéb szerepkörhöz hozzárendelt felhasználók, **Az üzleti dokumentumok sablonjainak szerkesztéséhez szükséges engedélyek konfigurálása** (AOT-név **ERBDTemplatesSecurity**).

A következő eljárással állíthatja be az üzletidokumentum-kezelési funkcióinak elérésével kapcsolatos engedélyeket az összes jogi személy számára.

1. A **Hozzáférési engedélyek konfigurátora** laphoz való hozzáféréssel rendelkező felhasználóként jelentkezzen be az alkalmazásba.
2. Nyissa meg a **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Üzleti dokumentumok kezelése** \> **Hozzáférési engedélyek kezelése** lapot.

Figyeljen oda az értesítésre, miszerint hogy az Üzleti dokumentumkezelés modulhoz jelenleg nincs engedélyezve a hozzáférési engedélyek használata.

![Üzleti dokumentumkezelő hozzáférési engedélyeinek konfigurátora lap](./media/BDM-Overview-TemplatesAccess1.png)

Ezzel a beállítással minden olyan felhasználó, aki bármely, olyan biztonsági szerepkörhöz van hozzárendelve, amely az **Üzleti dokumentumoksablonok kezelése** (AOT név **ERBDManageTemplates**) feladat elvégzéséhez be van állítva, meg tudja nyitni az üzleti dokumentum kezelése munkaterületet, és szerkesztheti az alkalmazásban rendelkezésre álló sablonokat.

A következő ábra bemutatja, hogy milyen lehetőségek érhetők el az Üzleti dokumentumkezelés munkaterületen a **Kinnlevőség-adminisztrátor** szerepkörhöz hozzárendelt felhasználók számára. Az aktuális hozzáférési jogosultságok beállításával a felhasználó szerkesztheti a különböző funkcionális területek üzleti dokumentumait, többek között a számlázást, a szabályozási jelentéseket és a kifizetéseket is.

![Üzletidokumentum-kezelés munkaterület oldala](./media/BDM-Overview-TemplatesForAlice1.png)

3. A **Hozzáférési engedélyek konfigurátora** lapon válassza a **Hozzáférési engedélyek beállítása** lehetőséget.
4. A **Sablonok szerkesztésére vonatkozó hozzáférési engedélyek beállításai** párbeszédpanelen kapcsolja be a **Konfigurált hozzáférési engedélyek alkalmazása** beállítást.
5. Az **OK** gombra kattintva győződjön meg arról, hogy engedélyezve vannak az Üzleti-dokumentumkezelés hozzáférési engedélyei.

![Üzleti dokumentumkezelő hozzáférési engedélyeinek konfigurátora lap konfigurálása](./media/BDM-Overview-TemplatesAccess2.png)

6. Válassza a **Hozzáadás** lehetőséget egy új üzleti szerepkör megadásához, amelyhez konfigurálni kell az Üzleti dokumentumkezelés sablonjainak elérését.
7. A **Biztonsági szerepkörök** párbeszédpanelen válassza ki a **Kinnlevőség-adminisztrátor** szerepkört, majd az **OK** gombbal nyugtázza a szerepkör beállítását.
8. A **Hozzáférési engedélyek címkék szerint** lapon válassza az **Új** lehetőséget.
9. A **Címke típusa** mezőben válassza a **Működési terület** elemet, majd az **Azonosító** mezőben válassza a **Számlázás** elemet.
10. Válassza a **Mentés** lehetőséget a megadott szerepkörhöz konfigurált hozzáférési engedélyek tárolásához.

  Az aktuális beállítás azt jelenti, hogy minden olyan felhasználó számára, aki **a Kinnlevőségek-adminisztrátor** szerepkörhöz van rendelve, és az **Üzleti dokumentumoksablonok kezelése** (AOT-név **ERBDManageTemplates**), feladatot látja el azon elektronikus formátumú konfigurációs sablonok, amelyek a **Számlázás** értékkel rendelkeznek a **Működési terület** címkében, elérhetők szerkesztésre az Üzleti dokumentumkezelés munkaterületen.

11. Váltson át a **Kapcsolódó információ** ablaktáblára az aktuális lap jobb oldaláról. A **Kapcsolódó információ** ablaktábla bemutatja, hogy hogyan lesznek alkalmazva a konfigurált hozzáférési engedélyek, többek között a **Kinnlevőség-adminisztrátor** szerepkörhöz rendelt felhasználók számára elérhető konfigurációs sablonokat.

![Üzleti dokumentumkezelő hozzáférési engedélyeinek konfigurátora lap konfigurálása](./media/BDM-Overview-TemplatesAccess3.png)

12. A **Hozzáférési engedélyek konfigurációk szerint** lapon válassza az **Hozzáadás** lehetőséget.
13. A **Konfiguráció kiválasztása** párbeszédpanelen jelölje be az **Intrastat-jelentés** elektronikus jelentés formátumkonfigurációját.
14. Az **OK** gombra kattintva nyugtázza a kiválasztott konfigurációk bejegyzését, majd a **Mentés** gombra kattintva tárolhatja a megadott szerepkörhöz konfigurált hozzáférési engedélyeket.

Az aktuális beállítás azt jelenti, hogy minden olyan felhasználó számára, aki a **Kinnlevőségek-adminisztrátor** szerepkörhöz van rendelve, és az **Üzleti dokumentumoksablonok kezelése** (AOT-név **ERBDManageTemplates**), feladatot látja el aa következő sablonok elérhetők szerkesztésre az Üzleti dokumentumkezelés munkaterületen:

- Sablonok, amelyek a **Számlázás** értékkel rendelkeznek a **Működési terület** címkében.
- Sablonok, amelyek olyan elektronikus formátumkonfigurációkból származnak, amelyek fel vannak sorolva a **Hozzáférési engedélyek konfigurációnként** lapon (például sablonok az **Intrastat jelentés** formátumkonfigurációból a **Kötelezően előírt jelentéskészítés** tartományból).

![Üzleti dokumentumkezelő hozzáférési engedélyeinek konfigurátora lap konfigurálása](./media/BDM-Overview-TemplatesAccess4.png)

A következő ábra bemutatja, hogy milyen lehetőséget kínál az Üzleti dokumentumkezelés munkaterület a **Kinnlevőség-adminisztrátor** szerepkörhöz hozzárendelt felhasználók számára. Az aktuális Üzleti dokumentumkezelés hozzáférési engedélybeállításával a felhasználó szerkesztheti az üzleti dokumentumok sablonjait a **Számlázás** tartományból, és az **Intrastat-jelentés** elektronikus formátumkonfigurációjából. A **Kifizetések** tartomány sablonjai nem érhetők el a **Kinnlevőség-adminisztrátor** szerepkör számára.

![Üzletidokumentum-kezelés munkaterület oldala](./media/BDM-Overview-TemplatesForAlice2.png)

> [!NOTE]
> A **Hozzáférési engedélyek konfigurációk szerint** szabályok egy elektronikus formátumkonfiguráció egyedi azonosítójával vannak tárolva. Ez azt jelenti, hogy ezeket a szabályokat nem törli a program, ha a rájuk hivatkozó elektronikus jelentéskészítési konfiguráció törlődik. Amikor törli a törölt konfigurációkat importál vissza példányba, ezek a szabályok újra megjelennek. A törölt konfigurációk újbóli importálása után a szabályokat nem kell újra beállítani.

## <a name="use-business-document-management-to-edit-templates"></a>Az üzleti dokumentumkezelés modul használata sablonok kezeléséhez

Az üzleti felhasználók hozzáférhetnek az üzleti dokumentumsablonokhoz a szerkesztéshez az Üzleti dokumentumok kezelése munkaterületen. Csak a következő felhasználók férhetnek hozzá az Üzleti dokumentumok kezelése munkaterülethez:

- A **Rendszergazda szerepkörhöz** hozzárendelt felhasználók.
- Azon felhasználók, akik olyan szerepkörhöz vannak hozzárendelve, amely **Üzleti dokumentumoksablonok kezelése** (AOT- **ERBDManageTemplates**) helyen meghatározott feladatokat végezhet el.

A következő eljárással szerkesztheti a szabadszöveges számlasablonokat az Üzleti dokumentumok kezelése munkaterületen. A művelet végrehajtása előtt el kell végeznie a témakör összes korábbi műveletét.

1. Az Üzleti dokumentum kezelése munkaterületre való hozzáféréssel rendelkező felhasználóként jelentkezzen be.
2. Nyissa meg az Üzletidokumentum-kezelés munkaterületet.

![Üzletidokumentum-kezelés munkaterület oldala](./media/BDM-Overview-EditingTemplate1.png)

A **Sablon** lap bemutatja a kiválasztott sablon tartalmát. Válassza a **Részletek** lapot a kiválasztott sablon részleteinek áttekintéséhez, valamint annak az elektronikusjelentés-formátumkonfigurációnak a megtekintéséhez, amelyben ez a sablon található. Figyelje meg, hogy minden sablon **Közzétett**állapotú, és a **Verzió** oszlopban nem tartalmaz részleteket. Ez azt jelenti, hogy ezek a sablonok jelenleg nincsenek szerkesztve.

### <a name="initiate-editing-templates-owned-by-your-configuration-provider"></a>A konfigurációs szolgáltató tulajdonában lévő sablonok szerkesztésének kezdeményezése

1. Az Üzletidokumentum-kezelés munkaterületen válassza ki a **Csekkek nyomtatási formátuma** sablont a listában.
2. Válassza ki az **Részletek** fület.

![Üzletidokumentum-kezelés munkaterület oldala](./media/BDM-Overview-EditingTemplate2.png)

A **Sablon szerkesztése** beállítás elérhető a kiválasztott sablonhoz. Ez a beállítás mindig elérhető olyan elektronikus formátumú sablon esetében, amelynek az aktív ER konfigurációs szolgáltató (**Litware, Inc.** ebben a példában) tulajdonosa. Ha a **Sablon szerkesztése** beállítás van kiválasztva, a mögöttes Elektronikus formátumkonfiguráció vázlatváltozatának meglévő sablonja lesz elérhető szerkesztésre.

### <a name="initiate-editing-templates-owned-by-other-providers"></a>Más szolgáltatók tulajdonában lévő sablonok szerkesztésének kezdeményezése

1. Az Üzletidokumentum-kezelés munkaterületen válassza ki az **Ügyfél FTI jelentés (GER)** sablont a listában.
2. Válassza ki az **Részletek** fület.

![Üzletidokumentum-kezelés munkaterület oldala](./media/BDM-Overview-EditingTemplate3.png)

Az **Új dokumentum** beállítás elérhető a kiválasztott sablonhoz. Ez a beállítás mindig elérhető olyan elektronikus formátumú sablon esetében, amely egy másik szolgáltatótól származik (A **Microsoft** ebben a példában). Amikor az **Új dokumentum** van kiválasztva, a szerkesztéshez egy új sablon lesz elérhető. Ezt követően a szerkesztett sablon egy új, automatikusan létrejövő ER formátumkonfigurációban lesz tárolva.

### <a name="start-editing-a-template"></a>Sablonnal szerkesztésének elkezdése

1. A kiválasztott sablonból válassza ki az **Új dokumentum** lehetőséget.
2. Ha szükséges, módosítsa a szerkeszthető sablon címét a **Cím** mezőben. A program az ER formátumkonfiguráció elnevezésére használja a szöveget. Ne felejtse el, hogy a konfiguráció vázlatverziója (**Customer FTI report (GER) másolata**), amely tartalmazza a szerkesztett sablont, automatikusan meg lesz jelölve ezen ER-formátum futtatásához az aktuális felhasználóhoz. Ezzel egy időben a program az alap ER formátumból származó nem módosított eredeti sablon alapján futtatja ezt az ER formátumot bármely más felhasználó számára.
3. A **Név** mezőben módosítsa az automatikusan létrehozandó szerkeszthető sablon első verziójának nevét.
4. A **Megjegyzés** mezőben módosítsa a szerkeszthető sablon automatikusan létrehozott verziójának megjegyzését.

![Üzletidokumentum-kezelés munkaterület oldala](./media/BDM-Overview-EditingTemplate4.png)

5. A szerkesztési folyamat kezdetének jóváhagyásához kattintson az **OK** gombra.

A **BDM sablonszerkesztő** lap megnyílik. A kiválasztott sablon elérhetővé válik az online szerkesztéshez a Office 365 használatával.

![Üzletidokumentum-kezelés munkaterület oldala](./media/BDM-Overview-EditingLayout1.png)

### <a name="edit-a-template-in-office-365"></a>Sablon szerkesztése az Office 365 megoldásban

A sablon módosítása az Office 365 funkcióinak segítségével. Például az Office Online webhelyen a sablon fejlécében lévő mező betűtípusát **Normál** értékről **Félkövérre** kell módosítani. Ezeket a módosításokat a rendszer automatikusan menti a szerkeszthető sablonhoz, amely az elsődleges sablon tárhelyén (alapértelmezés szerint az Azure blob tároló), amely konfigurálva van az ER keretrendszerben.

![Az üzleti dokumentumkezelés sablonszerkesztő oldal](./media/BDM-Overview-EditingLayout2.png)

### <a name="edit-a-template-in-the-office-desktop-application"></a>Sablon szerkesztése az Office asztali alkalmazásban

1. Jelölje be **Megnyitás az asztali alkalmazásban** ha módosítani szeretné a sablont az Office asztali alkalmazás funkciói segítségével (ebben a példában az Excel). A szerkeszthető sablont az állandó tárolóból az Üzletidokumentum-kezelés paraméterei között SharePoint mappaként megadott ideiglenes tárolóhelyre másolja a rendszer.
2. Győződjön meg róla, hogy a sablont az ideiglenes fájltárhelyből az Office asztali Excel alkalmazásban szeretné megnyitni.

![Üzletidokumentum-kezelés munkaterület oldala](./media/BDM-Overview-EditingLayout3.png)

3. Módosítsa a sablont. Például módosíthatja a mezők betűtípusát a fejlécben, ha a színt **fekete** értékről **kék** értékre módosítja.

![Az üzleti dokumentumkezelés sablonszerkesztő oldal](./media/BDM-Overview-EditingLayout4.png)

4. Válassza az Excel asztali alkalmazás **Mentés** elemét, hogy a sablon változásai az ideiglenes tárolóban legyenek tárolva.

![Az üzleti dokumentumkezelés sablonszerkesztő oldal](./media/BDM-Overview-EditingLayout5.png)

5. Zárja be az Excel asztali alkalmazást.
6. Válassza a **Tárolt másolat szinkronizálása** lehetőséget, ha szinkronizálni szeretné az ideiglenes sablon tárhelyét az állandó sablon tárhelyével.

> [!NOTE]
> Az ideiglenes fájlok tárhelyén található szerkeszthető sablon csak a sablonszerkesztés aktuális munkamenetéhez lesz megtartva. Ha befejezte ezt a munkamenetet a **BDM sablonszerkesztő** lapjának bezárásával, akkor a program törli a másolatot. Ha módosította a sablont az ideiglenes fájltérhelyen, és nem jelölte be a **Tárolt másolat szinkronizálása** lehetőséget , akkor a **BDM-sablonszerkesztő** lapjának bezárásakor egy üzenet meg fogja kérdezni, hogy a változtatásokat szeretné-e tárolni. Válassza az **Igen** beállítást, ha menteni szeretné a módosításokat a sablonban az állandó fájl helyén.

### <a name="validate-a-template"></a>Sablon érvényességének ellenőrzése

1. A **BDM sablonszerkesztő** lapján jelölje be a **Problémák keresése** lehetőséget a módosított sablon érvényesítéséhez az alapul szolgáló ER-formátumkonfigurációhoz képest. Hajtsa végre a javaslatokat (ha vannak), hogy a sablon illeszkedjen az alap ER formátumkonfiguráció formátumstruktúrájához.
2. A **Formátum megjelenítése** lehetőség kiválasztásával megjelenítheti a formátum aktuális szerkezetét az alap ER formátumkonfigurációból, amelyet a szerkeszthető sablonnal kell egyeztetni. 
3. A panel bezárásához válassz a **Formátum elrejtése** lehetőséget.

![BDM BDM-sablonszerkesztő lapja](./media/BDM-Overview-EditingTemplate6.png)

4. Zárja be a **BDM sablonszerkesztő** lapot.

A frissített sablon megjelenik a **Sablon** lapon. Figyelje meg, hogy a szerkesztett sablon állapota most **Piszkozat**, és az aktuális verzió már nem üres. Ez azt jelenti, hogy a sablon szerkesztésének folyamata elindult.

![Üzletidokumentum-kezelés munkaterület oldala](./media/BDM-Overview-EditingTemplate5.png)

### <a name="test-the-modified-template"></a>A módosított sablon tesztelése 

1. Az alkalmazásban módosítsa a vállalatot az **USMF** vállalatra.
2. Válassza a következőt **Kinnlevőségek** \> **Számlák** \> **Kizárólag szabadszöveges számlák**.
3. Válassza ki az **FTI-00000002** számlát, majd válassza a **Nyomtatáskezelő**parancsot.
4. Válassza ki a **Modul – kintlévőségek** \> **Dokumentumok** \> **Szabadszöveges számla** \> **Eredeti dokumentum** szintet, hogy meghatározza a feldolgozandó számlák hatályát.
5. A **Jelentés formátuma** mezőben válassza ki a **Customer FTI report (GER) másolata** ER formátumot a megadott dokumentumszinthez.

![Nyomtatáskezelési beállítások oldal](./media/BDM-Overview-TestRun1.png)

6. Az **Escape** gombbal zárja be az aktuális lapot.
7. Válassza a **Nyomtatás** lehetőséget,majd kattintson a **Kiválasztott** gombra.
8. Töltse le a dokumentumot, és nyissa meg az asztali Excel alkalmazás használatával.

![Szabadszöveges számlák oldal](./media/BDM-Overview-TestRun2.png)

A módosított sablon a szabadszöveges számlajelentés generálására szolgál a kiválasztott tételhez. Annak elemzéséhez, hogy milyen hatással vannak a sablon módosításai erre a jelentésre, futtathatja ezt a jelentést egy alkalmazásmunkamenetben, közvetlenül azután, hogy módosította egy alkalmazásmunkamenetben.

### <a name="create-an-alternative-template-revision"></a>Alternatív sablonverzió létrehozása

1. Nyissa meg a **BDM sablonszerkesztő** lapott, és válassza ki a **Customer FTI report (GER) Copy** sablont.
2. A **Változatok** lapon válassza az **Új** elemet.
3. Ha szükséges, a **Név** mezőben módosítsa a második verzió nevét, és alapozza azt a jelenleg aktív első verzióra.
4. Ha szükséges, a **Megjegyzés** mezőben módosítsa a szerkeszthető sablon automatikusan létrehozott verziójának megjegyzését.

![Üzletidokumentum-kezelés munkaterület oldala](./media/BDM-Overview-AddRevision.png)

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

![Üzletidokumentum-kezelés munkaterület oldala](./media/BDM-Overview-RevokeChanges.png)

1. Válassza ki **Sablon** lapot a **BDM sablonszerkesztő** lapján.
2. Válassza a **Visszavonás** lehetőséget.
3. Ha az **OK** gombra kattint a sablonban végzett módosítások visszavonásához, a módosított sablont a program felülírja az eredeti sablonnal, és minden módosítást eltávolít a program. Ha visszavonja a sablon módosításait, akkor lehetősége van arra, hogy törölje a sablont. Egyéb lehetőségek megismeréséhez válassza a **Mégsem** lehetőséget.

### <a name="publish-a-modified-template"></a>Módosított sablon közzététele
1. A **BDM sablonszerkesztő** lapon a **Sablon** lapon válassza a **Közzététel** lehetőséget.
2. Ha az **OK** gombra kattint a közzététel megerősítéséhez, akkor a származtatott **Customer FTI report (GER) másolat** ER formátum amely a módosított sablont tartalmazza, befejezettként lesz megjelölve. A módosított sablon elérhetővé válik a többi felhasználó számára. Az ER formátum befejezett verziói csak a sablon legutóbbi aktív felülvizsgálatát fogják megtartani. A többi változat törölve lesz. Egyéb lehetőségek megismeréséhez válassza a **Mégsem** lehetőséget.

## <a name="frequently-asked-questions"></a>Gyakori kérdések

#### <a name="i-selected-new-document-but-instead-of-opening-the-bdm-template-editor-page-in-finance-and-operations-i-have-been-sent-to-the-office-365-web-page"></a>Kiválasztottam az **Újdokumentum** lehetőséget de a Finance and Operations **BDM sablonszerkesztő** lapja helyett az Office 365 weboldalára kerültem.
Ez az Office 365 átirányítás egy ismert hibája. Ez akkor fordulhat elő, ha első alkalommal jelentkezik be az Office 365 rendszerbe. A hiba megkerüléséhez válassza a böngészőben a **Vissza** gombját a visszatéréshez.

#### <a name="i-understand-how-to-edit-a-template-by-using-office-365-in-the-first-application-session-and-how-to-use-the-template-in-the-second-application-session-adjusting-the-template-to-see-how-my-changes-affect-the-generated-business-document-can-i-do-this-using-the-office-desktop-application"></a>Értem, hogyan szerkeszthetek a sablonokat Office 365 használatával az első alkalmazásmunkamenetben, és azt, hogyan kell használni a sablont a második alkalmazásmunkamenetben a sablon módosításával, hogy megtekintsem a módosítások hogyan hatnak a létrejövő üzleti dokumentumra. Megtehetem ezt az asztali Office alkalmazás segítségével?
Igen, megteheti. Az első alkalmazásmunkamenetben válassza a **Megnyitás az asztali alkalmazásban** lehetőséget. A sablon az ideiglenes fájltárolási helyre kerül és megnyílik az Office asztali alkalmazásban. Ezután hajtsa végre a következő lépéseket a sablon módosításának előnézetéhez a létrehozott üzleti dokumentumban:

1. Végezze el a szükséges módosításokat a sablonban az Office asztali alkalmazás segítségével.
2. Válassza a **Mentés** elemet az Office asztali alkalmazásban.
3. Válassza ki **BDM-sablonszerkesztő** lapján az első alkalmazásmunkamenetnél a **Tárolt másolat szinkronizálása** lehetőséget.
4. Hajtsa végre ezt a sablon ER-formátumot a második alkalmazásmunkamentben.

#### <a name="i-get-the-error-value-cannot-be-null-parameter-name-externalid-when-i-select-open-in-desktop-app-how-do-i-work-around-this"></a>Az „Érték nem lehet nulla” üzenetet kapom. Paraméter neve: "externalId", ha a **Megnyitás asztali alkalmazásban**lehetőséget választom. Hogyan lehet ezt megoldani? 
Valószínűleg olyan Azure AD tartományból jelentkezett be az alkalmazás jelen példányába, amely eltér a az alkalmazás ezen példányának telepítéséhez használt Azure AD tartománytól. Mivel a SharePoint szolgáltatás, amely sablonokat tárol az Office asztali alkalmazásokkal történő szerkesztésre, a program ugyanazon tartományhoz tartozik, mint az alkalmazás nincs jogosultságunk a SharePoint szolgáltatás eléréséhez. A probléma megoldásához a megfelelő Azure AD tartománnyal rendelkező felhasználó hitelesítő adataival jelentkezzen be az aktuális példányba.

## <a name="additional-resources"></a>További erőforrások

[Az Elektronikus jelentéskészítés áttekintése](general-electronic-reporting.md)

[Az OPENXML formátumban létrejövő jelentésekre vonatkozó konfigurációk tervezése](tasks/er-design-reports-openxml-2016-11.md)

[ER konfigurációk tervezése jelentések Word-formátumú előállításához](tasks/er-design-configuration-word-2016-11.md)

[Beágyazott képek és alakzatok az ER-rel generált dokumentumokban](electronic-reporting-embed-images-shapes.md)

[Elektronikus jelentéskészítés konfigurálása az adatok Power BI szolgáltatásba való lehívásához](general-electronic-reporting-report-configuration-get-data-powerbi.md)
