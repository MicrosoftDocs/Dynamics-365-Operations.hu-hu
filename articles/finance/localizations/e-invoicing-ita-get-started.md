---
title: Első lépések az olasz elektronikus számlázásbővítménnyel
description: Ez a témakör olyan információkat tartalmaz, amelyek bemutatják az Első lépéseket az olasz elektronikus számlázásbővítmény Microsoft Dynamics 365 Finance és Dynamics 365 Supply Chain Management szolgáltatásban való használatát.
author: gionoder
manager: AnnBe
ms.date: 09/22/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: c513141f820c95fe3842478361693701f1e3641b
ms.sourcegitcommit: f860ac2b18f6bbbfc4a46b497baec2477105b116
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/19/2020
ms.locfileid: "4444156"
---
# <a name="get-started-with-the-electronic-invoicing-add-on-for-italy"></a>Első lépések az olasz elektronikus számlázásbővítménnyel

[!include [banner](../includes/banner.md)]


> [!IMPORTANT]
> Előfordulhat, hogy az Olasz elektronikus számlázásbővítmény jelenleg nem támogatja az elektronikus számlákhoz rendelkezésre álló összes funkciót a Microsoft Dynamics 365 Finance és Dynamics 365 Supply Chain Management számára. 

Ez a témakör olyan információkat tartalmaz, amelyek bemutatják az olasz elektronikus számlázásbővítménnyel kapcsolatos első lépéseket. Végigvezeti a Regulatory Configuration Services (RCS) és a Finance szolgáltatásban található ország-függő konfigurációs lépéseken. Továbbá a szolgáltatáson keresztül végigvezeti az Olaszország-specifikus **FatturaPA**-formátumban létrejövő elektronikus számlák küldésének folyamatán, és elmagyarázza, hogyan kell áttekinteni a feldolgozás eredményeit.

## <a name="prerequisites"></a>Előfeltételek

A témakör lépéseinek végrehajtása előtt végre kell hajtania az [Első lépések az Elektronikus számlázásbővítménnyel](e-invoicing-get-started.md) részben található lépéseket.

## <a name="rcs-setup"></a>RCS beállítása

Az RCS beállítása során a következő feladatokat kell elvégeznie:

1. A vevő elektronikus számlák exportálásához használt e-számlázási funkció importálása **FatturaPA**-formátumba.
2. Az elektronikus számlákkal kapcsolatos válaszok létrehozásához, küldéséhez és fogadásához szükséges fájlformátum-konfigurációk áttekintése.
3. Az elektronikus számlabeküldési forgatókönyveket támogató események konfigurálása.
4. Tegye közzé az e-számlázási funkciót.

> [!NOTE]
> „Az e-számlázás funkció” annak az erőforrásnak az általános neve, amely az Elektronikus számlázási bővítmény kiszolgáló felhasználásához van konfigurálva és közzétéve. Ebben az esetben a vevő elektronikus számlák exportálásához használt e-számlázási funkciót fogja beállítani.

## <a name="import-the-e-invoicing-feature"></a>Az e-számlázási funkció importálása

1. Jelentkezzen be a RCS-fiókba.
2. Nyissa meg a **Globalizációs funkciók** munkaterületet, a **Funkciók** szakaszban válassza az **e-számlázás** csempét.
3. Az **e-számlázási funkciók** oldalon jelölje be az **Importálás** lehetőséget a e-számlák funkció Globális adattárból történő importálásához.

    > [!NOTE]
    > Ha nem látja az elérhető szolgáltatások listáját, akkor válassza a **Szinkronizálás** elemet. 

4. Válassza ki az **e-számlák exportálása (IT)** funkciót, majd válassza az **Importálás** lehetőséget.

![Az e-számlák exportálása (IT) funkció importálása](media/e-Invoicing-services-get-started-ITA-Select-Import-e-Invoicing-feature.png)

Amikor az **e-számlák exportálása (IT)** funkciót a globális adattárból importálja, akkor azzal a következő szakaszokban ismertetett összes beállítást is importálja.

## <a name="create-a-new-version-of-the-e-invoices-export-it-feature"></a>Az e-számlák exportálása (IT) funkció új verziójának létrehozása

1. Az **e-számlázási funkciók** oldal **Verziók** lapján válassza az **Új** lehetőséget. 

    ![Új e-számlázási funkcióverzió hozzáadása](media/e-Invoicing-services-get-started-ITA-Select-New-e-Invoicing-feature-version.png)

    Ezután konfigurálhatja az e-számlázási funkcióhoz társított Elektronikus jelentéskészítési (ER) formátumokat.

2. A **Konfigurációk** lapon válassza a **Hozzáadás** lehetőséget a konfigurációs verziók kezeléséhez.

    ![E-számlázás funkció-konfigurációverziók kezelése](media/e-Invoicing-services-get-started-ITA-Manage-e-Invoicing-feature-configurations.png)

    Ebben a lépésben hozzáadja és konfigurálja az olasz e-számlák exportálásához használt különböző fájlok ER-formátumát. Az olasz FatturaPA e-számlák esetében a következő szokásos konfigurációkat, illetve az e-számlázáshoz használt tényleges egyéni konfigurációkat kell használni:

    - Értékesítési számla (IT)
    - Projektszámla (IT)

    Amikor egy másik e-számlázási funkcióból származtatott e-számlázási funkciót hoz létre, a program az eredeti funkcióból örökli az összes ER-formátumot.

3. A specifikus ER-formátum fájlkonfigurációjának kiválasztása.
4. Válassza a **Szerkesztés** vagy **Megtekintés** lehetőséget a **Formátumtervező** lap megnyitásához.

    ![A Formátumtervező lap megnyitása](media/e-Invoicing-services-get-started-ITA-Configuration-ER-format-designer.png)

5. Az ER-formátum fájlkonfiguráció szerkesztéséhez és megtekintéséhez használja a **Formátumtervező** lapot.

    ![Formátumtervező oldal](media/e-Invoicing-services-get-started-ITA-ER-format-designer.png)

## <a name="manage-the-e-invoicing-feature-setups"></a>Kezelje az e-számlázás funkció beállításait

- Az **e-számlázási funkciók** oldal **Beállítások** lapján válassza a **Hozzáadás**, **Törlés** vagy **Szerkesztés** parancsot az e-számlázási funkciók beállításainak kezeléséhez.

![Az e-számlázás funkció beállításainak kezelése](media/e-Invoicing-services-get-started-ITA-Manage-e-Invoicing-feature-setup.png)

Ebben a lépésben konfigurálhatja az elektronikus számlákra vonatkozó eseményeket, többek között az XML kimeneti fájlok **FatturaPA**-formátumban történő létrehozását, valamint a digitális aláírást (ha szükséges).

### <a name="configure-the-sales-invoice-feature-setup"></a>Az Értékesítési számla funkció beállításainak konfigurálása

1. Az **e-számlázási funkciók** oldal **Beállítások** lapjának **Funkcióbeállítás** oszlopában válassza ki az **Értékesítési számla** lehetőséget.
2. Válassza ki a **Szerkesztés** opciót.
3. A **Funkcióverzió beállítása** oldalon válassza ki a **Műveletek** lapot a műveletek listájának kezeléséhez. A műveletek határozzák meg azokat a műveleteket, amelyeket az esemény teljes végrehajtásához sorrendben kell végrehajtani.

    ![Műveletek lap](media/e-Invoicing-services-get-started-ITA-Select-Actions.png)

    | Műveletazonosító | Művelet neve        | Művelet leírása                                     |
    |-----------|--------------------|--------------------------------------------------------|
    | 1         | Dokumentum átalakítása | Az e-számla XML-fájljának létrehozása **FatturaPA**-formátumban. |
    | 2         | Dokumentum aláírása      | Digitális aláírás alkalmazása az XML-fájlon.             |

4. Válassza az **Alkalmazhatósági szabályok** lapot az alkalmazhatósági szabályok megtekintéséhez és kezeléséhez. Az alkalmazhatósági szabályok határozzák meg, hogy melyik környezetben fusson a művelet.

    ![Alkalmazhatósági szabályok lap](media/e-Invoicing-services-get-started-ITA-Select-Applicability-rules.png)

5. A **Változók** lapon megtekintheti és karbantarthatja a változókat.

    ![Változók lap](media/e-Invoicing-services-get-started-ITA-Select-Variables.png)

6. A műveletek futtatásához szükséges nyilvános változók meghatározása.

### <a name="configure-the-project-invoice-feature-setup"></a>A Projektszámla funkció beállításainak konfigurálása 

A **Projektszámla** funkció konfigurálásához szükséges lépések és beállítások nagyon hasonlóak az **Értékesítési számla** funkcióbeállítás lépéseihez és beállításaihoz. A projektszámlákkal való munkák során lásd az értékesítési számlák eljárásait.

## <a name="assign-the-e-invoicing-feature-to-the-environment"></a>Az e-számlázási funkció társítása a környezethez

1. Az **e-számlázási funkciók** oldal **Környezetek** lapján válassza az **Engedélyezés** lehetőséget.
2. A **Környezet** mezőben válassza ki a környezetet.
3. A **Hatálybalépés dátuma** mezőben válassza ki azt a dátumot, amikortól a környezetnek hatályossá kell válnia.
4. Válassza az **Engedélyezés** lehetőséget. 

![Az e-számlázási környezet engedélyezése](media/e-Invoicing-services-get-started-ITA-Enable-e-Invoicing-environment.png)

## <a name="publish-the-e-invoicing-feature"></a>Tegye közzé az e-számlázási funkciót

Az e-számlázási funkció közzétehető a verzió állapotának **Befejezett** vagy **Közzétett** értékre módosításával.

### <a name="change-the-version-status-to-completed"></a>A verzió állapotának módosítása Befejezett értékre

1. Az **e-számlázási funkciók** oldal **Verziók** lapján válassza ki a **Piszkozat** állapotú e-számlázási funkció verzióját.
2. Válassza az **Állapot módosítása \>Teljes** lehetőséget. 

### <a name="change-the-version-status-to-published"></a>A verzió állapotának módosítása Közzétett értékre 

1. Az **e-számlázási funkciók** oldal **Verziók** lapján válassza ki a **Befejezett** állapotú e-számlázási funkció verzióját.
2. Válassza az **Állapot módosítása \> Közzétett** lehetőséget.

![Az e-számlázási funkció állapotának módosítása](media/e-Invoicing-services-get-started-ITA-Change-status-of-e-Invoicing-feature.png)

## <a name="set-up-the-electronic-invoicing-add-on-integration-in-finance"></a>Az Elektronikus számlázásbővítmény integrációjának beállítása a Finance szolgáltatásban

A Finance szolgáltatás beállítása során a következő feladatokat kell elvégeznie:

1. Importálja az ER-adatmodellt, az ER-adatmodell-leképezést, valamint a kontextus-konfigurációkat a FatturaPA-számlákhoz.
2. Az olasz e-számlák digitális aláírásához szükséges tanúsítvány konfigurálása.

### <a name="import-the-er-data-model-data-model-mapping-and-formats"></a>Az ER-adatmodell, az adatmodell-leképezése és a formátumok importálása

1. Az **Elektronikus jelentéskészítés** munkaterületen ellenőrizze, hogy az **Üzleti dokumentum szolgáltatás** konfigurációszolgáltatója **Aktív** értékre van állítva.
2. Válassza ki a **Tárházak** lehetőséget.
3. Válassza ki a **Globális erőforrás \> Megnyitás** lehetőséget.
4. A **Számlamodell**, a **Számlamodell-leképezése** és a **Vevői számla kontextusmodell** importálása.

#### <a name="turn-on-the-feature-for-exporting-customer-electronic-invoices-for-italy"></a>Kapcsolja be a funkciót az olasz vevői elektronikus számlák exportálásához

1. Menjen a **Szervezeti adminisztráció \> Beállítás \> Elektronikus dokumentumparaméterek** lehetőségre.
2. A **Funkciók** lapon válassza ki az **Engedélyezett** jelölőnégyzetet az **IT00036** funkcióhivatkozás sorában.

![A FatturaPA funkció bekapcsolása](media/e-Invoicing-services-get-started-ITA-Enable-FatturaPA-feature.png)

#### <a name="configure-electronic-documents"></a>Elektronikus dokumentum konfigurálása

1. Menjen a **Szervezeti adminisztráció \> Beállítás \> Elektronikus dokumentumparaméterek** lehetőségre.
2. Az **Elektronikus dokumentum** lapon válassza a **Hozzáadás** elemet, majd adja meg az olasz e-számlák létrehozásához szükséges táblákat:

    - **Tábla neve:** Vevői számla naplója
    - **Tábla neve:** Projektszámla

3. Minden táblához határozzon meg egy kapcsolódó dokumentumkontextust:

    - Az **Ügyfélszámla napló** lehetőségben válassza a **Vevői számla kontextusát**.
    - A **Projektszámla** lehetőségnél válassza ki a **Projektszámla kontextusa** elemet.

![Választípusok beállítása](media/e-Invoicing-services-get-started-ITA-Set-up-response-types.png)

## <a name="electronic-invoice-processing"></a>Elektronikus számla feldolgozása

A Finance szolgáltatásban történő feldolgozás során a következő feladatokat kell elvégeznie:

1. Olasz e-számlák létrehozása az Elektronikus számlázásbővítménnyel
2. A végrehajtási naplók megtekintése, és a feldolgozás eredményeinek áttekintése

### <a name="generate-electronic-invoices"></a>Elektronikus számlák létrehozása

Miután bekapcsolta a **Konfigurálható elektronikus számlázásbővítmény integrációja** funkciót, és aktiválta az **IT00036** funkciót, az olasz e-számlák létrehozásához használt régi Finance-folyamatot már nem lehet használni. Ezt felváltotta egy új, **Elektronikus dokumentumok beküldése** nevű folyamat.

A dokumentumokat a saját e-számla dokumentumok igényeinek megfelelően manuálisan is elküldheti.

> [!NOTE]
> Mielőtt folytatná, győződjön meg arról, hogy az olasz e-számlákhoz szükséges beállítások el lettek végezve. A további információkat lásd: [Vevői elektronikus számlák](https://docs.microsoft.com/dynamics365/finance/localizations/emea-ita-e-invoices). Ne feledje, hogy a témakörben leírt néhány beállítási lépés nem érhető el az elektronikus számlázásbővítmény aktiválása miatt.

1. Menjen a **Szervezeti adminisztráció \> Időszakos \> Elektronikus dokumentumok \> Elektronikus dokumentumok beküldése** lehetőségre.
2. A dokumentumok első beküldésekor **Nem** értékre kell állítania a **Dokumentumok újraküldése** lehetőséget. Ha a szolgáltatáson keresztül újra kell küldenie a dokumentumot, akkor ezt a beállítást állítsa **Igen** értékre.
3. A **Szerepeltetni kívánt rekordok** gyorslapon válassza a **Szűrő** lehetőséget a **Lekérdezés** párbeszédpanel megnyitásához, amelyen létrehozhat egy lekérdezést, hogy milyen dokumentumok legyenek kiválasztva a beküldéshez.

![Elektronikus dokumentumok beküldése párbeszédpanel](media/e-Invoicing-services-get-started-ITA-Submission-form.png)

#### <a name="filter-query"></a>Lekérdezés szűrése

1. A **Lekérdezés** párbeszédpanelben konfigurálja az értékesítési- és a projektszámlák szűrési feltételeit, vagy hagyja üresen az összes feltételt az összes el nem küldött számla szerepeltetéséhez.

    ![Beküldési szűrési feltételek beállítása](media/e-Invoicing-services-get-started-ITA-Set-up-Submission-filter-criteria.png)

2. Kattintson az **OK** gombra a **Lekérdezés** párbeszédpanel bezárásához.
3. Kattintson az **OK** gombra a kiválasztott dokumentumok elküldéséhez.

> ![MEGJEGYZÉS]A dokumentum szolgáltatáson keresztüli beküldésének első kísérlete során a program rákérdez, hogy megerősíti-e a kapcsolatot az Elektronikus számlázásbővítménnyel. Válassza a **Kattintson az Elektronikus dokumentumbeküldési szolgáltatáshoz való csatlakozáshoz**.

#### <a name="view-submission-logs"></a>Beküldési naplók megtekintése

Megtekintheti az összes beküldött dokumentum beküldési naplóját.

1. Menjen a **Szervezeti adminisztráció \> Időszakos \> Elektronikus dokumentumok \> Elektronikus dokumentumbeküldési napló** lehetőségre.
2. A **Dokumentumtípus** mezőben válassza ki a **Vevői számlanapló** vagy a **Projektszámla** lehetőséget a szükséges elektronikus dokumentumok szűréséhez.

    ![A dokumentumtípus kiválasztása a beküldési naplók megtekintéséhez](media/e-Invoicing-services-get-started-ITA-Select-Document-type-for-viewing-submission-log.png)

    A **Beküldési állapot** oszlopban látható érték a beküldési folyamat állapotát jelöli. Azt jelzi, hogy a folyamatot konfigurálták-e, és hogy szükség van-e további műveletre.

3. A Művelet ablaktáblán válassza ki a **Lekérdezések \> Beküldések részletei** lehetőséget a beküldési végrehajtási naplók részleteinek megtekintéséhez.

    ![A beküldési napló részleteinek megtekintése](media/e-Invoicing-services-get-started-ITA-View-Submission-log-details.png)

4. A **Műveletek feldolgozása** gyorslapon az RCS-ben beállított funkcióverzióban konfigurált műveletekhez tartozó végrehajtási naplót tekintheti meg. Az **Állapot** oszlop azt jelzi, hogy a művelet futtatása sikeres volt-e.
5. A **Műveletfájlok** gyorslapon a műveletek végrehajtása során létrehozott közbenső fájlokat tekintheti meg. Kiválaszthatja a **Megtekintés** elemet a kimeneti XML-fájl **FatturaPA**-formátumban történő letöltéséhez, illetve annak tartalmának megtekintéséhez.

## <a name="related-topics"></a>Kapcsolódó témakörök

- [Elektronikus számlázásbővítmény – áttekintés](e-invoicing-service-overview.md)
- [Első lépések az Elektronikus számlázásbővítménnyel](e-invoicing-get-started.md)
- [Az Elektronikus számlázásbővítmény beállítása](e-invoicing-setup.md)
