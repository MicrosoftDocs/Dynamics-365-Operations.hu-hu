---
title: Első lépések a Mexikóra vonatkozó elektronikus számlázás használata során
description: Ez a témakör olyan információkat tartalmaz, amelyek bemutatják a mexikói Elektronikus számlázással kapcsolatos első lépéseket.
author: gionoder
ms.date: 09/22/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom:
- "97423"
- intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 26091a068ed15ec9ff14c9194c3e0e0ad0779351
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/06/2021
ms.locfileid: "6344782"
---
# <a name="get-started-with-electronic-invoicing-for-mexico"></a>Első lépések a Mexikóra vonatkozó elektronikus számlázás használata során

[!include [banner](../includes/banner.md)]

> [!IMPORTANT]
> Előfordulhat, hogy a Mexikói elektronikus számlázás jelenleg nem támogatja a CFDI dokumentumban elérhető összes funkciót, valamint a Microsoft Dynamics 365 Finance vagy Dynamics 365 Supply Chain Management szolgáltatással kapcsolatos beépített integrációt.

Ez a témakör olyan információkat tartalmaz, amelyek bemutatják a mexikói Elektronikus számlázással kapcsolatos első lépéseket. Végigvezeti a Regulatory Configuration Services (RCS) és a Finance szolgáltatásban található ország-függő konfigurációs lépéseken. Ezenkívül végigvezeti azokon a lépéseken, amelyeket a CFDI a szolgáltatáson keresztül történő elküldése érdekében, a Finance szolgáltatásban követnie kell, valamint bemutatja, hogyan kell áttekinteni a feldolgozási eredményeket és a CFDI-számlák állapotát.

## <a name="prerequisites"></a>Előfeltételek

A témakör lépéseinek végrehajtása előtt végre kell hajtania az [Első lépések az Elektronikus számlázással](e-invoicing-get-started.md) részben található lépéseket.

## <a name="rcs-setup"></a>RCS beállítása

Az RCS beállítása során a következő feladatokat kell elvégeznie:

1. Az e-számlázási funkció importálása a CFDI-számlák feldolgozásához.
2. Tekintse át azokat a formátumkonfigurációkat, amelyek a CFDI-számlákkal kapcsolatos válaszok létrehozásához, beküldéséhez és fogadásához, valamint a törléssel kapcsolatos válaszok elküldéséhez és fogadásához szükségesek.
3. A CFDI számlabeküldési forgatókönyveket támogató események konfigurálása.
4. Tegye közzé az e-számlázási funkciót a CFDI-számlákhoz.

> [!NOTE]
> „Az e-számlázás funkció” annak az erőforrásnak az általános neve, amely az Elektronikus számlázási kiszolgáló felhasználásához van konfigurálva és közzétéve. Ebben az esetben a CFDI-számlák (MX) számítanak annak az e-számlázási funkciónak, amelyet be fog állítani.

## <a name="import-the-e-invoicing-feature"></a>Az e-számlázási funkció importálása

1. Jelentkezzen be a RCS-fiókba.
2. Nyissa meg a **Globalizációs funkciók** munkaterületet, a **Funkciók** szakaszban válassza az **e-számlázás** csempét.
3. Az **e-számlázási funkciók** oldalon jelölje be az **Importálás** lehetőséget a **CFDI-számlák (MX)** funkció Globális adattárból történő importálásához.

    > [!NOTE]
    > Ha nem látható a funkció a listán, válassza a **Szinkronizálás** elemet, majd ismételje meg a 3. lépést.

![A CFDI-számlák (MX) importálása funkció.](media/e-Invoicing-services-get-started-MEX-Select-Import-CFDI-feature.png)

A **CFDI-számlák (MX)** funkció Globális adattárból történő importálásakor az összes funkcióbeállítás – ideértve a konfigurációkat és a műveleteket is – importálva lesz.

### <a name="create-a-new-version-of-the-cfdi-invoices-mx-feature"></a>A CFDI-számlák (MX) funkció új verziójának létrehozása

Új verziót akkor lehet létrehozni, ha például az URL-címeket frissíteni kell. További tájékoztatást az [E-számlázás CFDI](tasks/mx-00010-e-invoicing-cfdi.md) részben talál.

- Az **e-számlázási funkciók** oldal **Verziók** lapján válassza az **Új** lehetőséget.

![Új e-számlázási funkcióverzió hozzáadása.](media/e-Invoicing-services-get-started-MEX-Select-New-e-Invoicing-feature.png)

### <a name="update-the-configuration-version"></a>A konfigurációverzió frissítése

1. Az **e-számlázási funkciók** oldal **Konfigurációk** lapján válassza ki a **Hozzáadás** vagy a **Törlés** lehetőséget a konfigurációverziók (ER-fájlformátum-konfigurációk) kezeléséhez.

    ![E-számlázás funkciókonfigurációk kezelése.](media/e-Invoicing-services-get-started-MEX-Manage-e-Invoicing-feature-Configurations.png)

    Új verzió létrehozásakor az összes konfiguráció a legutóbbi közzétett verzióból öröklődik. A CFDI-számlák feldolgozásához a következő konfigurációk szükségesek:

    - CFDI-számla (BusinessDocumentService)
    - CFDI-válaszüzenet importálása
    - CFDI-hibanapló importálása
    - CFDI-törlési kérelem (MX) (BusinessDocumentService)
    - CFDI-számla (BusinessDocumentService)

2. A listáról válassza ki a kívánt konfigurációverziót, majd a **Szerkesztés** vagy **Nézet** elemet kijelölve nyissa meg a **Formátumtervező** oldalt, amelyen szerkesztheti és megtekintheti a konfigurációt.

    ![A Formátumtervező lap megnyitása.](media/e-Invoicing-services-get-started-MEX-Configuration-ER-format-designer.png)

3. Az ER-formátum fájlkonfiguráció szerkesztéséhez és megtekintéséhez használja a **Formátumtervező** lapot. További információ: [Elektronikus dokumentum-konfigurációk létrehozása](../../fin-ops-core/dev-itpro/analytics/electronic-reporting-configuration.md).

    ![Formátumtervező oldal.](media/e-Invoicing-services-get-started-MEX-ER-format-designer.png)

## <a name="manage-the-e-invoicing-feature-setups"></a>Kezelje az e-számlázás funkció beállításait

- Az **e-számlázási funkciók** oldal **Beállítások** lapján válassza a **Hozzáadás**, **Törlés** vagy **Szerkesztés** parancsot az e-számlázási funkciók beállításainak kezeléséhez.

![Az e-számlázás funkció beállításainak kezelése.](media/e-Invoicing-services-get-started-MEX-Manage-e-Invoicing-feature-Setup.png)

A CFDI-számlák engedélyezésre való beküldéséhez (XML-fájl létrehozásához, XML-fájl elküldéséhez és a válasz feldolgozásához) be kell állítani az **Értékesítési számla** funkciót.

A CFDI-számla érvénytelenítésre való beküldéséhez az **Érvénytelenítés** és a **Visszavonás** funkció beállítására van szükség.

### <a name="configure-the-sales-invoice-feature-setup"></a>Az Értékesítési számla funkció beállításainak konfigurálása

1. Az **e-számlázási funkciók** oldal **Beállítások** lapjának **Funkcióbeállítás** oszlopában válassza ki az **Értékesítési számla** lehetőséget.
2. Válassza a **Szerkesztés** lehetőséget a műveletek, alkalmazhatósági szabályokat és a változók konfigurálásához.

    ![Az e-számlázás funkció beállításainak szerkesztése.](media/e-Invoicing-services-get-started-MEX-Edit-e-Invoicing-feature-setup.png)

3. A **Funkcióverzió beállítása** oldalon válassza ki a **Műveletek** lapot a műveletek listájának kezeléséhez. A műveletek határozzák meg azokat a műveleteket, amelyeket az esemény teljes végrehajtásához sorrendben kell végrehajtani.

    ![Műveletek lap.](media/e-Invoicing-services-get-started-MEX-Select-Actions.png)

    | Műveletazonosító | Művelet                   | Művelet neve                                  | Művelet leírása                                          |
    |-----------|--------------------------|----------------------------------------------|-------------------------------------------------------------|
    | 1         | Dokumentum átalakítása       | CFDI e-számla létrehozása digitális bejelentkezés nélkül | CFDI e-számla létrehozása.                                |
    | 2         | Dokumentum aláírása            | Digitális aláírás                                 | A beküldeni kívánt e-számla digitális aláírása.                |
    | 3         | Mexikói PAC-szolgáltatás hívása | CFDI e-számla beküldése                        | A Windows kommunikációs alaprendszer (WCF) vevő elküldi a CFDI e-számlát. |
    | 4         | Folyamatválasz         | Webszolgáltatás válaszának elemzése                 | Elemezze a webszolgáltatás válaszát, és küldje vissza a hibanaplót. |

### <a name="set-up-the-url-for-mexican-pac-web-services"></a>A mexikói PAC webszolgáltatások URL-címének beállítása 

1. A **Funkcióverzió beállítása** oldal **Műveletek** lapjának **Műveletek** gyorslapján válassza a **mexikói PAC szolgáltatás hívása** lehetőséget.
2. A **Paraméterek** gyorslap **URL-cím** mezőjébe írja be a webszolgáltatás URL-címét a CFDI-számla küldéséhez.

> [!NOTE]
> Kövesse ugyanezeket a lépéseket a **Visszavonás** és az **Érvénytelenítési kérelem** funkció beállításaihoz a **mexikói PAC szolgáltatás** művelet URL-címének frissítéséhez.

## <a name="assign-the-draft-version-to-an-e-invoicing-environment"></a>A Piszkozat verzió hozzárendelése e-számlázási környezethez

1. Az **e-számlázási funkciók** oldal **Környezetek** lapján válassza az **Engedélyezés** lehetőséget.
2. A **Környezet** mezőben válassza ki a környezetet.
3. A **Hatálybalépés dátuma** mezőben válassza ki azt a dátumot, amikortól a környezetnek hatályossá kell válnia.
3. Válassza az **Engedélyezés** lehetőséget.

![E-számlázási környezet engedélyezése.](media/e-Invoicing-services-get-started-MEX-Enable-e-Invoicing-Environment.png)

## <a name="change-the-version-status-to-completed"></a>A verzió állapotának módosítása Befejezett értékre

1. Az **e-számlázási funkciók** oldal **Verziók** lapján válassza ki a **Piszkozat** állapotú e-számlázási funkció verzióját.
2. Válassza az **Állapot módosítása \>Teljes** lehetőséget.

## <a name="change-the-version-status-to-published"></a>A verzió állapotának módosítása Közzétett értékre

- Az **e-számlázási funkciók** oldal **Verziók** lapján válassza az **Állapot módosítása \> Közzétett** értékre lehetőséget.

## <a name="publish-the-e-invoicing-feature"></a>Tegye közzé az e-számlázási funkciót

1. Az **e-számlázási funkciók** oldalon jelölje be a **Verziók** lapot a **CFDI-számlák (MX)** funkció állapotának kezeléséhez.
2. A funkció állapotának módosításához jelölje be az **Állapot módosítésa** elemet.

![Az e-számlázási funkció állapotának módosítása.](media/e-Invoicing-services-get-started-MEX-Change-status-of-e-Invoicing-feature.png)

## <a name="set-up-electronic-invoicing--integration-in-finance"></a>Az Elektronikus számlázás integrációjának beállítása a Finance szolgáltatásban

Az Elektronikus számlázás Finance szolgáltatásban történő beállításához a következő feladatokat kell elvégeznie:

1. Importálja az ER-adatmodellt, az ER-adatmodell-leképezést, valamint a CFDI-számlákhoz szükséges formátumokat.
2. A CFDI-számlák frissítéséhez szükséges választípusok konfigurálása. Ezek a választípusok a jogosult minősítésszolgáltató (PAC) kiszolgáló válaszához használatosak.

### <a name="import-the-er-data-model-er-data-model-mapping-and-context-configurations-for-cfdi-invoices"></a>Importálja az ER-adatmodellt, az ER-adatmodell-leképezést, valamint a kontextus-konfigurációkat a CFDI-számlákhoz

1. Bejelentkezés a Finance szolgáltatásba.
2. Az **Elektronikus jelentéskészítés** munkaterületen, a **Konfigurációszolgáltatók** szakaszban, válassza a **Microsoft** címet. Győződjön meg róla, hogy ez a konfigurációszolgáltató **Aktív** értékre van állítva. A szolgáltatók **Aktív** értékre állításával kapcsolatban tekintse át a [Konfigurációszolgáltatók létrehozása és megjelölése aktívként](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md) elemet.
3. Válassza ki a **Tárházak** lehetőséget.
4. Válassza ki a **Globális erőforrás \> Megnyitás** lehetőséget.
5. **Számlamodell**, **Számlamodell-lekérdezés**, **CFDI-számlaformátum (MX)**, **CFDI-számlavisszavonási kérelemformátum (MX)**, és a **CFDI-számla érvénytelenítés formátum (MX)** importálása.

### <a name="turn-on-the-feature-for-processing-cfdi-invoices"></a>Kapcsolja be a CFDI-számlák feldolgozására szolgáló funkciót

1. Menjen a **Szervezeti adminisztráció \> Beállítás \> Elektronikus dokumentumparaméterek** lehetőségre.
2. A **Funkciók** lapon válassza ki az **Engedélyezés** jelölőnégyzetet az **MX-00010** és **MX-00016** funkcióhivatkozások soraiban.

![A CFDI-számlák feldolgozására szolgáló funkció bekapcsolása.](media/e-Invoicing-services-get-started-MEX-Enable-CFDI-feature.png)

### <a name="import-er-configurations-and-set-up-the-response-types-for-updating-cfdi-invoices"></a>A választípusok beállítása a CFDI-számlák frissítésére, illetve az ER-konfigurációk importálása

#### <a name="import-er-configurations"></a>ER-konfigurációk importálása

1. Az **Elektronikus jelentéskészítés** munkaterületen, a **Konfigurációszolgáltatók** szakaszban, válassza a **Microsoft** címet.
3. Válassza ki a **Tárházak** lehetőséget.
4. Válassza ki a **Globális erőforrás \> Megnyitás** lehetőséget.
5. A **Válaszüzenet-modell**, a **CFDI-hibanapló-importálás (MX)**, és a **CFDI-üzenetválasz-importálás (MX)** importálása.

#### <a name="set-up-the-response-types"></a>A választípusok beállítása

1. Menjen a **Szervezeti adminisztráció \> Beállítás \> Elektronikus dokumentumparaméterek** lehetőségre.
2. Az **Elektronikus dokument** lapon válassza a **Hozzáadás** lehetőséget.
3. Adja meg a vevői számla naplóját, majd a **Tábla neve** mezőben válassza ki a projekt számláját.
4. Minden táblához határozzon meg egy kapcsolódó dokumentumkontextust:

    - A **Vevői számla naplóban** adja meg az **Vevői számla kontextusát**.
    - A **Projektszámlához** adja meg a **Projektszámla kontextusát**.

4. Válassza ki azokat a konfigurálni kívánt **Választípusokat**, amelyek a vevői számlanaplón vagy a projektszámlán keresztül visszaállíthatók az elektronikus számlázásból.
5. Válassza az **Új**, majd a **Válasz típusa** mezőt, majd a **Válasz** elemet.
6. A **Beküldés állapota** mezőben válassza a **Függőben** lehetőséget.
7. A **Modell-leképezés** mezőben válassza a **Válaszüzenet importálási formátuma – Modell-leképezés válaszüzenetből** lehetőséget.
8. Válassza a **Mentés** lehetőséget.
9. Válassza az **Új**, majd a **Válasz típusa** mezőt, majd a **Válaszadatok** elemet.
10. A **Beküldés állapota** mezőben válassza a **Függőben** lehetőséget.
11. A **Modell-leképezés** mezőben válassza ki a **CFDI-válaszadatok importálási formátuma (részletek) – Válaszadatok importálása** lehetőséget.
12. Válassza a **Mentés** lehetőséget.

## <a name="process-electronic-invoices-in-finance"></a>Elektronikus számlák feldolgozása a Finance szolgáltatásban 

A CFDI-számlák Finance szolgáltatásban lévő Elektronikus számlázáson keresztül történő feldolgozásakor a következő feladatokat lehet végrehajtani:

- CFDI-számlák beküldése.
- A beküldési végrehajtási naplók megtekintése.
- CFDI-számla érvénytelenítésének beküldése.

### <a name="submit-cfdi-invoices"></a>CFDI-számlák beküldése

A **Konfigurálható elektronikus számlázás integrációja** funkció bekapcsolását követően a CFDI-számlák küldéséhez szükséges **Elektronikus számlák exportálása/importálása** folyamat (**Kinnlevőségek \> Számlák \> E-számlák**) már nem használható. Ezt felváltotta egy új, **Elektronikus dokumentumok beküldése** nevű folyamat.

> [!NOTE]
> Az új **Elektronikus dokumentumok beküldése folyamat** használata előtt győződjön meg arról, hogy a mexikói e-számlákhoz szükséges beállítások el lettek végezve. További tájékoztatást a [CFDI-elrendezés 3.3-as verziója](./latam-mex-cfdi-3-3.md) részben talál.

1. Menjen a **Szervezeti adminisztráció \> Időszakos \> Elektronikus dokumentumok \> Elektronikus dokumentumok beküldése** lehetőségre.
2. A dokumentumok első beküldésekor mindig **Nem** értékre kell állítania a **Dokumentumok újraküldése** lehetőséget. Ha a szolgáltatáson keresztül újra kell küldenie a dokumentumot, akkor ezt a beállítást állítsa **Igen** értékre.
3. A **Szerepeltetni kívánt rekordok** gyorslapon válassza a **Szűrő** lehetőséget a **Lekérdezés** párbeszédpanel megnyitásához, amelyen létrehozhat egy lekérdezést, hogy milyen dokumentumok legyenek kiválasztva a beküldéshez.

![CFDI-dokumentum beküldése.](media/e-Invoicing-services-get-started-MEX-Submit-CFDI-document.png)

> [!NOTE]
> A dokumentum szolgáltatáson keresztüli beküldésének első kísérlete során a program rákérdez, hogy megerősíti-e a kapcsolatot az Elektronikus számlázással. Válassza a **Kattintson az Elektronikus dokumentumbeküldési szolgáltatáshoz való csatlakozáshoz**.

### <a name="view-submission-logs"></a>Beküldési naplók megtekintése

Megtekintheti az beküldött dokumentumok beküldési naplóit, vagy csak egy adott dokumentumot.

#### <a name="view-all-submission-logs"></a>Az összes beküldési napló megtekintése

A **Konfigurálható elektronikus számlázás integráció** funkció bekapcsolása után egy új lap érhető el, amellyel nyomon követheti a dokumentum beküldési folyamatát. Ezen a lapon megtekintheti az összes beküldött dokumentum beküldési naplóját.

1. Menjen a **Szervezeti adminisztráció \> Időszakos \> Elektronikus dokumentumok \> Elektronikus dokumentumbeküldési napló** lehetőségre.
2. A **Dokumentumtípus** mezőben válassza ki a **Vevői számlanapló** lehetőséget a szükséges elektronikus dokumentumok szűréséhez.

    ![A dokumentumtípus kiválasztása a beküldési naplók megtekintéséhez.](media/e-Invoicing-services-get-started-MEX-Select-document-type-for-viewing-submission-log.png)

3. A Művelet ablaktáblán válassza ki a **Lekérdezések \> Beküldések részletei** lehetőséget a beküldési végrehajtási naplók részleteinek megtekintéséhez.

    ![A beküldési napló részleteinek megtekintése.](media/e-Invoicing-services-get-started-MEX-View-submission-log-details.png)

A beküldési naplókban lévő adatok három gyorslap között vannak felosztva:

- **Műveletek feldolgozása** – Ez a gyorslap azon végrehajtási naplót mutatja meg, amely az RCS-ben beállított funkcióverzióban konfigurált műveletekhez tartozik. Az **Állapot** oszlop azt jelzi, hogy a művelet futtatása sikeres volt-e.
- **Műveletfájlok** – Ez a gyorslap a műveletek végrehajtása során létrehozott közbenső fájlokat jeleníti meg. A fájl letöltéséhez és megtekintéséhez válassza a **Megtekintés** lehetőséget.
- **Műveletnapló feldolgozása** – Ez a gyorslap az Elektronikus számlázás és a cél webszolgáltatás közötti kommunikáció eredményeit jeleníti meg. Azt is bemutatja, hogy mit küldött vissza a webszolgáltatásból a feldolgozás. A **Hibakód** oszlop az engedélyezés webszolgáltatása által visszaküldött visszajuttatási kódot jeleníti meg.

Amikor a beküldött CFDI-számla engedélyezve van, az állapota **Engedélyezve** értékre módosul.

#### <a name="view-submission-logs-from-cfdi-invoices"></a>Tekintse meg a CFDI-számlákból származó beküldési naplókat

A **Konfigurálható elektronikus számlázás integrációja** funkció bekapcsolása után megtekintheti a CFDI-számlákból származó beküldési naplókat is.

1. Menjen a **Kinnlevőségek \> Lekérdezések és jelentések \> CFDI (elektronikus számlák)** pontra.
2. Válasszon egy olyan CFDI-számlát, amelyet a **Konfigurálható elektronikus számlázás integrációja** funkció bekapcsolása után küldtek be.
3. A Művelet panel **Előzmények** lapján válassza az **Elektronikus dokumentumnapló** menüpontot.

![CFDI-számlákból származó beküldési naplók megtekintése.](media/e-Invoicing-services-get-started-MEX-View-submission-log-from-CFDI-invoice.png)

> [!NOTE]
> Azon CFDI-számláknál, amelyeket a **Konfigurálható elektronikus számlázás integrációja** funkció bekapcsolása előtt küldtek be, elérhető az **Előzmények** gomb. Azon CFDI-számláknál, amelyeket a **Konfigurálható elektronikus számlázás integrációja** funkció bekapcsolása után küldtek be, nem elérhető az **Előzmények** gomb.

### <a name="submit-cancellation-of-cfdi-invoices"></a>CFDI-számlák érvénytelenítésének beküldése

A **Konfigurálható elektronikus számlázás integrációja** funkció bekapcsolása után már nem használható a régi folyamat a CFDI-számlák érvénytelenítésére. Egy új érvénytelenítési folyamat váltja fel, amely az **Elektronikus dokumentum beküldési naplója** lapon lesz beágyazva.

1. Menjen a **Kinnlevőségek \> Lekérdezések és jelentések \> CFDI (elektronikus számlák)** pontra.
2. Ha a CFDI-számla **Jóváhagyva** állapotú, akkor válassza a **Funkciók \> CFDI érvénytelenítése** lehetőséget.
3. Menjen a **Szervezeti adminisztráció \> Időszakos \> Elektronikus dokumentumok \> Elektronikus dokumentumbeküldési napló** lehetőségre.
4. Válassza ki a CFDI-számla, majd a **Funkciók \> Kapcsolódó beküldés küldése** funkciót.
5. Adja meg a kapcsolódó beküldés leírását, majd kattintson az **OK** gombra.

#### <a name="view-cancellation-submission-logs"></a>Tekintse meg az érvénytelenítési beküldési naplókat

1. Menjen a **Szervezeti adminisztráció \> Időszakos \> Elektronikus dokumentumok \> Elektronikus dokumentumbeküldési napló** lehetőségre.
2. A **Dokumentumtípus** mezőben válassza ki a **Vevői számlanapló** lehetőséget kizárólag a vevői számla naplózási dokumentumainak szűréséhez.
3. Válassza ki a CFDI-számlát, majd a Műveleti ablaktáblán válassza ki a **Lekérdezések \> Kapcsolódó beküldés** lehetőséget.

    A **Kapcsolódó beküldések** oldal egy adott CFDI-számla összes kapcsolódó beküldésér és beküldési állapotát megjeleníti. A következő ábrán az első sor azt a beküldést jelöli, amely a CFDI-számla jóváhagyását kérte. A második sor azt a beküldést jelöli, amely érvénytelenítette az adott CFDI-számlát.

    ![Az érvénytelenítési beküldési naplók megtekintése.](media/e-Invoicing-services-get-started-MEX-View-cancellation-submission-log.png)

4. A Művelet ablaktáblán válassza ki a **Lekérdezések \> Beküldések részletei** lehetőséget a beküldési végrehajtási naplók részleteinek megtekintéséhez.

    ![Az érvénytelenítési beküldési napló részleteinek megtekintése.](media/e-Invoicing-services-get-started-MEX-View-cancellation-submission-log-details.png)

## <a name="privacy-notice"></a>Adatvédelmi nyilatkozat
A **CFDI mexikói elektronikus számla (MX)** funkcióhoz korlátozott számú adat küldése válhat szükségessé, ideértve a szervezet adóregisztrációs azonosítóját. Ezek továbbítva lesznek az adóhatóság által kinevezett harmadik fél ügynökségekhez, az elektronikus számlák – kormányzati szervek webszolgáltatással való integrációhoz szükséges, előre meghatározott formátumban való – adott adóhatósághoz történő elküldése céljából. A rendszergazda engedélyezheti és letilthatja a **CFDI mexikói elektronikus számla (MX)** funkciót a **Szervezeti adminisztráció \> Beállítások \> Elektronikus dokumentumparaméterek** lehetőségre való navigálással. Válassza ki a **Funkciók** lapot, majd a **CFDI mexikói elektronikus száma (MX)** funkciókat tartalmazó sorokat, és végezze el a megfelelő kijelölést. A külső rendszerekből ebbe a Dynamics 365 online szolgáltatásba importált adatok az [Adatvédelmi nyilatkozatunk](https://go.microsoft.com/fwlink/?LinkId=512132) hatálya alá tartoznak. További tájékoztatásért olvassa el az országspecifikus funkciók dokumentációja szakaszokban található Adatvédelmi nyilatkozatot.

## <a name="additional-resources"></a>További erőforrások

- [Elektronikus számlázás áttekintése](e-invoicing-service-overview.md)
- [Első lépések az elektronikus számlázási használata során](e-invoicing-get-started.md)
- [Az elektronikus számlázás beállítása](e-invoicing-setup.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]