---
title: A Regression Suite Automation Tool beállítása és telepítése oktatóanyag
description: Ez a témakör azt mutatja be, hogyan lehet beállítani és telepíteni a Regression Suite Automation Tool (RSAT) szolgáltatást.
author: robinarh
manager: AnnBe
ms.date: 09/20/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ROBOTS: NOINDEX, NOFOLLOW
audience: Application User, Developer, IT Pro
ms.reviewer: rhaertle
ms.custom: 21761, NotInToc
ms.search.region: Global
ms.author: rhaertle
ms.search.validFrom: 2019-05-30
ms.dyn365.ops.version: AX 7.0.0, Operations
ms.openlocfilehash: 4757d506239e309dcbc3e181469b17e3286cc111
ms.sourcegitcommit: f5e31c34640add6d40308ac1365cc0ee60e60e24
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/08/2020
ms.locfileid: "4695115"
---
# <a name="set-up-and-install-regression-suite-automation-tool-tutorial"></a>A Regression Suite Automation Tool beállítása és telepítése oktatóanyag
Ez a témakör egy olyan oktatóanyag, amely segítséget nyújt a beállítások végrehajtásában, és az RSAT-tal, valamint a RSAT használatával kapcsolatos eszközökkel való megismerkedésben. 

[!include [banner](../includes/banner.md)]

> [!NOTE]
> Az internetböngésző eszközeivel letöltheti és mentheti ezt a lapot PDF-formátumban. 

## <a name="key-concepts"></a>Alapfogalmak

- A Regression Suite Automation Tool (RSAT) eszközt támogató különböző alkalmazásokhoz szükséges telepítési és előfeltételként megadott beállítások megértése.
- Annak megértése, hogy a Feladatrögzítő funkciója a Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásával és a Microsoft Azure DevOps szolgáltatással együtt lehetővé teszi a tesztesetek létrehozását, konfigurálását, futtatásáv, vizsgálatát és a róluk szóló jelentések készítését.
- Funkcionális felhasználók bátorítása arra, hogy az üzleti feladatokat a Feladatrögzítővel rögzítsék a szolgáltatásban, majd a feladatrögzítéseket automatizált testek sorozatává alakítsák forráskód írása nélkül.

## <a name="before-you-begin"></a>Előzetes feladatok

### <a name="prerequisites"></a>Előfeltételek

- Az oktatóanyaghoz olyan környezet szükséges, amely a Microsoft Dynamics 365 for Finance and Operations 10.0-s (2019. áprilisi) vagy újabb verzióját futtatja. A Microsoft Dynamics 365 for Finance and Operations, Enterprise edition 7.3 szolgáltatást használó ügyfelek számára a Platform update 20 (PU 20) vagy újabb verzió is támogatott.
- A felhasználónak rendszergazdai jogosultsággal kell rendelkeznie a környezethez.
- Rendelkeznie kell hozzáféréssel az ügyfél bérlői LCS-éhez és Azure DevOps szolgáltatásához (korábban Microsoft Visual Studio Team Services \[VSTS\] néven volt ismert).
- A tesztek létrehozásához és kezeléséhez a felhasználónak Azure DevOps Test Plans- vagy Test Manager-licenccel kell rendelkeznie. A következő licencekkel szintén hozzáférést nyerhet a Test Plans felületéhez:
    - Visual Studio Enterprise-licenc
    - Visual Studio Test Professional-licenc
    - MSDN platformok előfizetői licenc
- Az RSAT szolgáltatásnak hozzá kell férnie a tesztkörnyezethez internetböngészőn keresztül.
- A tesztparaméterek létrehozásához és szerkesztéséhez a Microsoft Excel alkalmazásnak telepítve kell lennie.

## <a name="configure-azure-devops"></a>Azure DevOps konfigurálása

### <a name="user-eligibility"></a>Felhasználhatói jogosultság

Győződjön meg arról, hogy létrehozták a felhasználót az Azure DevOps szolgáltatásban, és van egy előfizetési szintje, amely hozzáférést biztosít az Azure Test Plans szolgáltatáshoz. Az Azure DevOps Test Plans-licenc csak akkor szükséges, ha a felhasználó teszteseteket fog létrehozni és kezelni (azaz nem minden RSAT-felhasználónak szükséges ez a licenc). A licenc követelményeivel kapcsolatos tudnivalókat lásd: [Licenckövetelmények](https://docs.microsoft.com/azure/devops/test/manual-test-permissions#license-requirements).

### <a name="create-a-new-azure-devops-project"></a>Új Azure DevOps-projekt létrehozása
Az RSAT Azure Devops szolgáltatást használ a tesztesetek és tesztcsomag kezeléséhez, jelentéskészítéséhez és a tesztfuttatás eredményeinek vizsgálatához. 

> [!NOTE]
> Egy meglévő Azure DevOps-projekt használható. Ha azonban a meglévő Azure DevOps-projekt úgy van beállítva, hogy egyéni sablonnal rendelkezik, akkor egy „VSTS Sync Failure ” hibaüzenet jelenik meg, amikor a teszteseteket szinkronizálja az Üzletifolyamat-modellező (BPM) segítségével az Azure DevOps szolgáltatásba (lásd a következő szakaszt: [Szinkronizálás tesztelése a BPM-ből az Azure DevOps szolgáltatásba](#test-the-synchronization-from-bpm-to-azure-devops)). Ha az egyéni sablonhoz a következő gyakorlati tanácsokat követték, akkor szinkronizálni lehet a teszteseteket az Azure DevOps szolgáltatással. (Ezek a gyakorlati tanácsok a hibaüzenetben láthatók.)

- Ne töröljön semmilyen munkaelemtípust vagy beépített mezőt.
- Ne törölje a munkaelemtípusok állapotát.
- Ne adjon kötelező mezőket a munkaelemtípusokhoz.

![A gyakorlati tanácsok listáját tartalmazó hibaüzenet](./media/setup_rsa_tool_02.png)

Ha nem, akkor ehhez az oktatóanyaghoz javasoljuk, hogy hozzon létre egy új Azure DevOps-projektet. További tudnivalókért lásd: [Felmerülő problémák a BPM egyéni Azure DevOps (VSTS) folyamatsablon segítségével történő szinkronizálása során](https://blogs.msdn.microsoft.com/lcs/2018/11/28/issues-when-syncing-to-bpm-using-a-custom-azure-devops-vsts-process-template/).

1. Nyissa meg az Azure DevOps URL-címét (`https://dev.azure.com/<Azure DevOps Name>`).
2. Válassz a **Projekt létrehozása** lehetőséget az Azure DevOps oldal jobb felső sarkában.

    ![Projekt létrehozása gomb](./media/setup_rsa_tool_03.png)

3. Töltse ki a következő mezőket, majd válassza a **Létrehozás** lehetőséget:

    - **Projekt neve**
    - **Verziókövetés** – Válassza ki **Team Foundation Version Control** elemet. Ne feledje, hogy az alapértelmezett beállítás, **Git** nem támogatott.
    - **Munkaelem-folyamat**

    ![Új projekt létrehozása párbeszédpanel](./media/setup_rsa_tool_04.png)

### <a name="create-a-personal-access-token"></a>Személyes hozzáférési jogkivonat létrehozása

Ebben az oktatóanyagban az LCS Üzletifolyamat-modellező (BPM) szolgáltatással létrehoz egy teszteseteket tartalmazó tárat, és szinkronizálja a teszteseteket az Azure DevOps szolgáltatással. A BPM Azure DevOps szolgáltatással való szinkronizálásához személyes hozzáférési jogkivonat szükséges.

1. Válassza ki a Azure DevOps-projekthez tartozó lap jobb felső sarkában látható profil ikont, majd válassza a **Biztonság** elemet.

    ![Biztonsági parancs](./media/setup_rsa_tool_05.png)

2. A bal oldali panelen a **Biztonság** részben válassza ki a **Személyes hozzáférési jogkivonat** pontot. Majd válassza az **Új jogkivonat** lehetőséget.

    ![Új token gomb a felhasználói beállítások személyes hozzáférési jogkivonat lapján.](./media/setup_rsa_tool_06.png)

3. Töltse ki a következő mezőket, majd válassza a **Létrehozás** lehetőséget:

    - **Név**
    - **Lejárat (UTC)** – Válassza az **Egyénileg meghatározott** lehetőséget, majd a dátumválasztó segítségével válassza ki a legutóbbi elérhető dátumot.
    - **Hatókörök** – Válassza a **Teljes hozzáférés** beállítást.

    ![Új személyes hozzáférési token létrehozása párbeszédpanel](./media/setup_rsa_tool_07.png)

    > [!NOTE]
    > Jegyezze fel a létrehozott személyes hozzáférési jogkivonatot. A RSAT-konfiguráció beállítása után a későbbiekben szüksége lesz rá.

    ![Személyes hozzáférési jogkivonat](./media/setup_rsa_tool_08.png)

## <a name="configure-the-lcs-project"></a>LCS-projekt konfigurálása

A tesztek alaptárához szüksége van egy Lifecycle Services (LCS) projektre. Az LCS Üzletifolyamat-modellező (BPM) használatos alaptárként a tesztesetekhez. A BPM a teszttáraknak az LCS-projektekben történő kezelésére és terjesztésére szolgál. Például egy Microsoft partner vagy független szoftvergyártó (ISV) teszttárakat épít, azzal BPM-tárak formájában adja ki a teszteseteket. A BPM esetében a teszteseteket az üzleti folyamatok szerint szervezik. A BPM nem határozza meg a végrehajtási sorrendet vagy a sikeres tesztek gyakoriságát. Ezeket a részleteket az Azure DevOps szolgáltatásban kezelheti, ahogy a témakör későbbi részében le van írva.  

A LCS-projekthez meglévő ügyfélvégrehajtás vagy Partner projekt használható.

### <a name="update-the-lcs-language"></a>LCS-nyelv frissítése

> [!NOTE]
> A felhasználói felületen (UI) az üzleti folyamatok helyes megjelenítéséhez az LCS preferált nyelvét **Angol (Egyesült Államok)** értékre kell állítani.

1. Lépjen az LCS végrehajtási projekthez.
2. Válassza ki a **Beállítások** gombot (fogaskerék-szimbólum) a lap jobb felső sarkában, majd válassza a **Nyelvi preferencia** lehetőséget.

    ![Parancsok a Beállítások menüben](./media/setup_rsa_tool_09.png)

3. A **Preferált nyelv** mezőben válassza az **Angol (Egyesült Államok)** lehetőséget, majd a **Mentés** gombot.

    ![Felhasználói beállítások nyelvi preferencia lapja](./media/setup_rsa_tool_10.png)

### <a name="configure-lcs-to-connect-to-the-azure-devops-project"></a>Az LCS konfigurálása a Azure DevOps-projekthez való kapcsolódáshoz

Ha korábban létrehozott egy új Azure DevOps-projektet, konfigurálja az LCS-projektet, hogy csatlakozhasson hozzá. Ellenkező esetben, ha az LCS-projekt már csatlakozott az Azure DevOps-projekthez, folytathatja a következő szakaszt.

1. Lépjen az LCS végrehajtási projekthez.
2. Válassza a **Menü** gombot, majd válassza ki **Projektbeállítások** lehetőséget.

    ![Projektbeállítások parancs](./media/setup_rsa_tool_11.png)

3. A bal oldali ablaktáblán válassza **Visual Studio Team Services** elemet, majd a **Visual Studio Team Services beállítása** elemet.

    ![A Visual Studio Team Services lap a projektbeállításokban](./media/setup_rsa_tool_12.png)

4. Az **Azure DevOps webhely URL-címe** mezőbe írja be az Azure DevOps-webhely URL-címét. A **Személyes hozzáférési token** mezőbe írja be a korábban létrehozott személyes hozzáférési tokent.

    > [!NOTE]
    > Bár a VSTS mára úgy ismert, hogy Azure DevOps, az LCS Azure DevOps-projekthez csatlakoztatásához használja a régi URL-címet. Például a Azure DevOps URL-cím, amelyet az oktatóanyagban használunk: `https://dev.azure.com/D365FOFastTrack/`. A következő ábrán azonban így van beírva: `https://D365FOFastTrack.visualstudio.com/`.

    ![1. lépés a Visual Studio Team Services beállításaiban](./media/setup_rsa_tool_13.png)

5. Válassza **Folytatás** parancsot.
6. A **Visual Studio Team Services-projekt** mezőben válassza a kiválasztott webhelyen a VSTS-projektet, hogy összekapcsolja az LCS-projekttel. A **Feldolgozási sablon** mező értéke alapértelmezés szerinti értéke **Agilis**. Egy egyéni sablon esetében tekintse át az [Új Azure DevOps-projekt létrehozása](#create-a-new-azure-devops-project) szakasz gyakorlati tanácsokat tartalmazó útmutatóját. Válassza **Folytatás** parancsot.

    ![2. lépés a Visual Studio Team Services beállításaiban](./media/setup_rsa_tool_14.png)

7. Ellenőrizze a beállításokat, majd válassza a **Mentés** parancsot.

    ![3. lépés a Visual Studio Team Services beállításaiban](./media/setup_rsa_tool_15.png)

8. Válassza az **Engedélyezés** lehetőséget, ha engedélyezni szeretné az LCS számára a konfigurált Azure DevOps-webhelyhez az Ön nevében való hozzáférést, és a VSTS-sel integráló funkciók bekapcsolását.

    ![Engedélyezés gomb](./media/setup_rsa_tool_16.png)

9. Megjelenik egy üzenetablak: „A rendszer átirányítja Önt egy külső webhelyre, ahol engedélyezheti a LCS számára, hogy az Ön nevében csatlakozzon a Visual Studio Team Services rendszerhez. Folytatja?” Válassza ki az **Igen** lehetőséget.

    ![Üzenetpanel](./media/setup_rsa_tool_17.png)

10. Válassza az **Elfogadás** lehetőséget.

    ![Hozzáférés engedélyezése](./media/setup_rsa_tool_18.png)

11. Ha felhasználóként engedélyezve van, akkor a felhasználói felületnek vissza kell térnie az LCS projekt beállításai lapra.

    ![Jogosult felhasználó](./media/setup_rsa_tool_19.png)

### <a name="create-a-new-bpm-library"></a>Új BPM-tár létrehozása

1. Lépjen az LCS végrehajtási projekthez.
2. Válassza a **Menü** gombot, majd válassza ki **Üzletifolyamat-modellező** lehetőséget.

    ![Üzletifolyamat-modellező parancs](./media/setup_rsa_tool_20.png)

3. Válassza az **Új tár** elemet.

    ![Új tár gomb](./media/setup_rsa_tool_21.png)

4. A **Tár neve** mezőbe írjon be egy nevet, majd válassza a **Létrehozás** parancsot. Ehhez az oktatóanyaghoz nevezze el a BPM-tárat **RSAT** névre.

    ![Új tár létrehozása párbeszédpanel](./media/setup_rsa_tool_22.png)

5. Nyissa meg az új **RSAT** BPM-tárat.
6. Válassza ki az **Minta alapvető üzleti folyamat** folyamatot, majd a jobb oldalon a **Szerkesztési mód** elemet.

    ![Szerkesztési mód gomb](./media/setup_rsa_tool_23.png)

7. A **Név** és a **Leírás** mező értékét módosítsa **Termék létrehozása** értékre. Majd válassza a **Mentés** lehetőséget.

    ![Név és leírás mezők](./media/setup_rsa_tool_24.png)

## <a name="environment"></a>Környezet

### <a name="version-requirement"></a>Verziókövetelmények

10-es verziót futtató tesztkörnyezet szükséges. A 7.3-as verziót használó ügyfelek számára a Platform update 20 vagy újabb verzió is támogatott.

> [!NOTE]
> Az RSAT szolgáltatásnak hozzá kell férnie a tesztkörnyezetéhez internetböngészőn keresztül.

### <a name="user-criteria"></a>Felhasználói feltételek

A felhasználónak rendszergazdai jogosultsággal kell rendelkeznie ehhez a környezethez.

### <a name="set-up-help-settings-to-connect-with-lcs"></a>Adja meg az LCS-kapcsolathoz tartozó súgóbeállításokat.

Ezt a lépést szükséges megtenni annak érdekében, hogy csatlakozhasson az LCS-hez, így a feladatrögzítéseket az LCS megfelelő BPM-tárába tudja menteni a kliensen keresztül.

1. Nyissa meg az ügyfélprogramot.
2. Lépjen a **Rendszerfelügyelet \> Beállítás \> Rendszerparaméterek** elemre.
3. A **Súgó** lap **Lifecycle Services súgókonfiguráció** mezőjében válassza a releváns LCS-projektet (**RSAT** ehhez az oktatóanyaghoz).

    ![A Lifecycle Services súgókonfiguráció mezője a Súgó lapon](./media/setup_rsa_tool_25.png)

    A BPM-tárak a megfelelő LCS-projektben kerülnek kitöltésre.

4. Válassza a **Mentés** lehetőséget.
5. A frissített súgótartalom megtekintéséhez előfordulhat, hogy frissíteni kell a böngészőt.

    ![Értesítés a böngésző frissítéséről](./media/setup_rsa_tool_26.png)

## <a name="task-recordings"></a>Feladatrögzítések

> [!NOTE]
> Győződjön meg róla, hogy az összes feladatrögzítés a fő irányítópulton kezdődik. Az egyes rögzítések legyenek rövidek és egy üzleti feladatra koncentráljanak, például egy értékesítési rendelés létrehozásához.

### <a name="create-a-task-recording-and-save-it-to-the-bpm-library"></a>Feladatrögzítés létrehozása és BPM-tárba mentése

Hozzon létre egy megfelelő feladatrögzítést, amely az új BPM-tárban létrehozott egyszerű üzleti folyamathoz kapcsolható.

1. Nyissa meg az ügyfélprogramot.
2. Válassza ki a fő irányítópulton a **Beállítások** gombot (a fogaskerék szimbólumát), majd válassza ki a **Feladatrögzítőt**.

    ![Parancsok a Beállítások menüben](./media/setup_rsa_tool_27.png)

3. Válassza a **Rögzítés létrehozása** elemet.

    ![Rögzítés létrehozása gomb](./media/setup_rsa_tool_28.png)

4. Töltse ki a **Rögzítés neve** és **Rögzítés leírása** mezőket, majd válassza az **Indítás** parancsot.

    ![Rögzítés neve és Rögzítés leírása mezők](./media/setup_rsa_tool_29.png)

5. Rögzítse a termék létrehozásához szükséges lépéseket. Ha befejezte, **Leállítás** paranccsal leállíthatja a rögzítést.

    ![A termék létrehozásának lépései](./media/setup_rsa_tool_30.png)

6. Válassza a **Mentés a Lifecycle Services szolgáltatásba** elemet.

    ![Mentési beállítások](./media/setup_rsa_tool_31.png)

    A tár adatait a rendszer az LCS-ből tölti be.

    ![Folyamatjelző](./media/setup_rsa_tool_32.png)

7. Válassza ki a feladatrögzítéshez társítandó BPM-tárat. Ehhez az oktatóanyaghoz válassza ki a korábban létrehozott **RSAT** BPM-tárat, és az alatta lévő **termék létrehozása** üzleti folyamatot. Majd kattintson az **OK** lehetőségre.

    ![A feladatrögzítés társítása egy BPM-könyvtárral és egy üzleti folyamattal](./media/setup_rsa_tool_33.png)

    A „mentés a Lifecycle Services szolgáltatásba sikeresen megtörtént” üzenet jelenik meg.

    ![Üzenet az LCS-re történt sikeres mentésről](./media/setup_rsa_tool_34.png)

8. Ha azt szeretné, hogy a feladat rögzítése helyileg történjen, és utána töltse fel a BPM-tárba az LCS-en keresztül, hajtsa végre az alábbi lépéseket:

    1. A rögzítés befejezése után válassza a **Mentés erre a számítógépre** lehetőséget.

        ![Mentési beállítások](./media/setup_rsa_tool_35.png)

    2. A böngésző értesítési sávján válassza a **Mentés** vagy a **Mentés másként** parancsot, ha menteni szeretné a fájlokat a helyi számítógépen.

        ![Értesítési sáv](./media/setup_rsa_tool_36.png)

    3. Nyissa meg a **RSAT** BPM-tárat, és válassza ki azt az üzleti folyamatot, amellyel menteni szeretné a feladatrögzítést.
    4. Az **Áttekintés** lapon válassza a **feltöltés** elemet.

        ![Feltöltés gomb](./media/setup_rsa_tool_37.png)

    5. Válassza a **Tallózás** lehetőséget, majd válassza ki a korábban mentett .axtr-fájltípust. Ezután válassza a **feltöltés** elemet.

        ![A feltölteni kívánt .axtr-fájl kiválasztása](./media/setup_rsa_tool_38.png)

### <a name="test-the-synchronization-from-bpm-to-azure-devops"></a>A BPM-ről Azure DevOps szolgáltatásba történő szinkronizálás tesztelése

Miután az üzleti folyamathoz csatolt egy feladatrögzítést, ellenőriznie kell, hogy az üzleti folyamat és a társított feladatrögzítés funkcióként és tesztesetként (adott esetben) szinkronizálható-e az Azure DevOps szolgáltatásba a VSTS szinkronizálási funkciónak a LCS modulban való használatával.

> [!NOTE]
> Az Azure DevOps szolgáltatásban létrehozott kapcsolódó munkaelemtípus változhat, az LCS-projekt Azure DevOps-szolgáltatással való konfigurálása során kiválasztott folyamatsablontól függően, az [Új Azure DevOps-projekt létrehozása](#create-a-new-azure-devops-project) szakaszban leírtaknak megfelelően.

1. Nyissa meg a BPM-tárat, és nyissa meg a korábban létrehozott **RSAT**-tárat.
2. Válassza ki a három pont gombot(**...**), és válassza a **vsts szinkronizálás** parancsot.

    ![VSTS szinkronizálás parancs a három pont menün](./media/setup_rsa_tool_39.png)

    A VSTS szinkronizálásának befejezése után megjelenik a **Követelmények** lap a bal oldalon, amely a megfelelő Azure DevOps-munkaelemet tartalmazza.

    > [!NOTE]
    > Az Azure DevOps szolgáltatásban létrehozott munkatételnek a BPM-tár nevének kell lennie a cím előtagjának.

    ![Követelmények lap](./media/setup_rsa_tool_40.png)

3. Frissítse a lapot..
4. Válassza ki a három pont gombot(**...**). További beállítást, a **Tesztesetek szinkronizálása** fog látni. Válassza ki ezt a lehetőséget.

    ![Tesztesetek szinkronizálása parancs a három pont menün](./media/setup_rsa_tool_41.png)

    > [!NOTE]
    > Ha a **Tesztesetek szinkronizálása** beállítás nem érhető el a lap frissítése után, nyissa meg a BPM főoldalát, és válassza a **Tesztesetek szinkronizálása** lehetőséget a teljes könyvtárhoz. Ily módon gyakorlatilag egy szinkronizálást hajthat végre az egész könyvtárhoz.
    > 
    > ![A Tesztesetek szinkronizálása kiválasztása az egész könyvtárhoz](./media/setup_rsa_tool_42.png)

    A Tesztesetek szinkronizálását követően létrejön egy új tesztelési eset a **Követelmények** lapon.

    ![Új teszteset a követelmények lapon](./media/setup_rsa_tool_43.png)

5. Nyissa meg az Azure DevOps-projektet, és válassza a **Táblák \> Munkaelemek** elemet.

    ![Munkaelemek parancs a Táblák alatt](./media/setup_rsa_tool_44.png)

6. Ellenőrizze, hogy létezik-e a BPM-szinkronizálással létrehozott munkaelem és a teszteset.

    ![Munkaelem és teszteset](./media/setup_rsa_tool_45.png)

## <a name="install-and-configure-rsat"></a>Az RSAT konfigurálása és telepítése

Az RSAT minden olyan számítógépre telepíthető, amelyen fut a Windows 10, és amely webböngészőn (Internet Explorer vagy Google Chrome) keresztül csatlakozhat a környezethez.

> [!NOTE]
> Az eszköz új verziójának telepítése előtt ajánlott eltávolítani a korábbi verziót.

### <a name="install-an-authentication-certificate"></a>Hitelesítési tanúsítvány telepítése

Ha engedélyezni szeretné a hitelesítést, akkor ugyanazon a számítógépen kell létrehoznia és telepítenie a tanúsítványt, amelyen az RSAT fut.

#### <a name="generate-a-certificate"></a>Tanúsítvány létrehozása

1. A tanúsítványfájl létrehozásához nyissa meg a Microsoft Windows PowerShell ablakát rendszergazdaként, majd futtassa a következő parancsot.

    ```
    $certificate = New-SelfSignedCertificate -dnsname 127.0.0.1 -CertStoreLocation cert:\LocalMachine\My -FriendlyName "D365 Automated testing certificate" -Provider "Microsoft Strong Cryptographic Provider"
    ```

2. A Tanúsítványkezelő megnyitásához adja meg a **certlm.msc** parancsot a **Futtatás** párbeszédpanelen, és győződjön meg arról, hogy a **D365 automatikus teszttanúsítványa** a **Személyes \> Tanúsítványok** szakaszban létrejött.

    > [!NOTE]
    > Győződjön meg róla, hogy a **certlm.msc**, és nem a **certmgr.msc** parancsot írja be, mivel a tanúsítványok a helyi számítógépen vannak tárolva.

    ![D365 Automatizált teszttanúsítvány tanúsítványa](./media/setup_rsa_tool_46.png)

3. Kattintson a jobb gombbal a tanúsítványra, majd válassza a **Másolás** menüpontot.
4. Ugorjon a **Megbízható legfelső szintű hitelesítésszolgáltatók \> Tanúsítványok** pontra.

    ![A megbízható legfelső szintű hitelesítésszolgáltatók mappa alatti tanúsítványok mappa](./media/setup_rsa_tool_47.png)

5. A **Művelet** menüben válassza a **beillesztés** parancsot, hogy a tanúsítványt a **Megbízható legfelső szintű hitelesítésszolgáltatók** helyre másolja.

    ![Beszúrás parancs a Művelet menüben](./media/setup_rsa_tool_48.png)

6. Ha meg szeretné kapni a telepített tanúsítvány ujjlenyomatát, de szóközöket vagy speciális karaktereket nem, rendszergazdaként nyissa meg a Windows PowerShell ablakát, és futtassa a következő parancsokat.

    ```
    cd Cert:\LocalMachine\My

    Get-ChildItem | Where-Object { $_.Subject -like "CN=127.0.0.1" }
    ```

    > [!NOTE]
    > Mentse az ujjlenyomatot, mert az Alkalmazásobjektum-kiszolgáló (AOS) .wif-fájljainak frissítéséhez és a RSAT-konfiguráció beállításához később szüksége lesz rá.

#### <a name="configure-the-aos-computer-to-trust-the-connection"></a>Az AOS-számítógép konfigurálása a kapcsolatban való megbízásra

> [!NOTE]
> Ha a környezet egy 2. vagy magasabb szintű környezet, a tanúsítvány ujjlenyomatát frissíteni kell a wif.config fájlban a környezet **összes** AOS-számítógépéhez.

1. Hozzon létre egy távoli asztali protokoll (RDP) kapcsolatot az AOS-számítógéppel. A bejelentkezési adatok az LCS környezeti adatok lapján érhetők el.
2. Nyissa meg a Microsoft Internet Information Services (IIS) alkalmazást, és keresse meg az **AOSService** elemet a webhelyek listáján.

    ![AOSService a webhelyek listáján](./media/setup_rsa_tool_49.png)

3. Kattintson a jobb gombbal a **Felfedezés** gombra a **\<Drive\>: \\AosService\\WebRoot** mappa megnyitásához. Keresse meg a **wif.config** fájlját.

    ![Wif.config fájl a WebRoot mappában](./media/setup_rsa_tool_50.png)

4. A **wif.config** fájl frissítéséhez adjon hozzá egy új hitelesítésszolgáltatói bejegyzést a tanúsítványhoz és a hitelesítésszolgáltató nevét, amint az a következő példában látható.

    ```
    <issuerNameRegistry type="Microsoft.Dynamics.AX.Security.SharedUtility.AxIssuerNameRegistry,Microsoft.Dynamics.AX.Security.SharedUtility">
        <authority name="CN=127.0.0.1">
            <keys>
                <add thumbprint="xxxxxxxxxxxxxxxxxxxx" />
                <add thumbprint="xxxxxxxxxxxxxxxxxxxx" />
            </keys>
            <validIssuers>
                <add name="CN=127.0.0.1" />
            </validIssuers>
        </authority>
    ```

    > [!NOTE]
    > Ha több felhasználó ugyanazt az alkalmazást használja, akkor mindegyik felhasználónak külön ujjlenyomatot kell létrehoznia, és ezeket a ujjlenyomatokat is hozzá kell adni a **\<keys\>** szakaszban.

5. Ha egynél több AOS-számítógép van, akkor minden további számítógép esetében ismételje meg a 3. és 4. lépést.

    > [!NOTE]
    > A régebbi 2. szintű környezetekkel ellentétben az új 2. szintű környezetek két AOS-példányon telepíthetők.

6. Futtassa az **iisreset** parancsot az összes AOS-számítógépen.

    > [!NOTE]
    > Ha egy 1. szintű számítógépnél nem rendelkezik rendszergazdai jogosultsággal az **iisreset** parancs futtatásához, válassza a Karbantartás > Szolgáltatások újraindítása lehetőséget az LCS Környezet adatai oldalán.

#### <a name="tier-2-environment"></a>2. vagy magasabb szintű környezet

Ha egy 2. vagy magasabb szintű (szabványos elfogadási tesztkörnyezet vagy magasabb) környezet van használatban, ellenőrizze vagy állítsa be a következő jegyzékbeállítást azon a számítógépen, amelyen a RSAT telepítve van. Ezt a lépést kötelező végrehajtani, mert segít elkerülni a hitelesítési vagy RSAT-kapcsolati hibákat.

```
if ((Test-Path HKLM:\SOFTWARE\Wow6432Node\Microsoft\.NETFramework\v4.0.30319))
{
    Set-ItemProperty HKLM:\SOFTWARE\Wow6432Node\Microsoft\.NETFramework\v4.0.30319 -Name SchUseStrongCrypto -Value 1 -Type dword -Force -Confirm:$false
}
```

### <a name="install-rsat"></a>RSAT telepítése

1. Lépjen a <https://www.microsoft.com/download/details.aspx?id=57357> oldalra, majd válassza a **letöltés** parancsot.
2. Válassza ki az összes fájlt, majd kattintson a **Tovább** gombra.

    ![Az összes fájl kiválasztása](./media/setup_rsa_tool_51.png)

3. A telepítő futtatásához kattintson duplán a .msi csomagra. Ezt követően a telepítés befejezése után válassza a **Befejezés** parancsot.

    ![RSAT-telepítőfájl](./media/setup_rsa_tool_52.png)

### <a name="install-selenium-and-browser-drivers"></a>A Selenium és böngésző illesztőprogramjainak telepítése

Az RSAT régebbi verzióiban telepíteni kellett a Seleniumot és a böngésző-illesztőprogramokat. Ezeket az illesztőprogramokat már nem kell telepíteni, mert a program automatikusan telepíti azokat.

1. A RSAT első megnyitásakor a program megkérdezi, hogy automatikusan letölti és telepíti a Seleniumot. További információ: [RSAT konfigurálása](#configure-rsat).
2. A tesztesetek futtatása előtt a program rákérdez, hogy automatikusan letölti és telepíti-e a böngésző illesztőprogramját, amely megfelel a RSAT-konfigurációban kiválasztott alapértelmezett böngészőnek. A további információkat megtekintheti a [Tesztesetek betöltése és futtatása](#load-and-run-test-cases) szakaszban.

## <a name="get-started-with-rsat"></a>Első lépések az RSAT használatában

### <a name="create-a-test-plan-and-test-suites"></a>Tesztelési terv és a tesztcsomagok létrehozása

1. Nyissa meg Azure DevOps-projektet, és válassza ki a **Tesztelési tervek** elemet.

    ![Tesztelési tervek parancs](./media/setup_rsa_tool_53.png)

2. Válassza az **Új tesztelési terv** elemet.

    ![Új tesztelési terv gomb](./media/setup_rsa_tool_54.png)

3. Töltse ki a **Név** mezőt, majd válassza a **Létrehozás** lehetőséget. Ehhez az oktatóanyaghoz nevezze el a tesztelési tervet **RSAT tesztelési terv** néven.

    ![Új tesztelési terv párbeszédpanel](./media/setup_rsa_tool_55.png)

4. Kattintson a pluszjelre (**+**), majd válassza a **Statikus csomag** lehetőséget, amellyel az új tesztelési terv alatt létrehozhat egy statikus csomagot. Nevezze el az új tesztcsomagot **T01 – Készletre gyártás** néven.

    > [!NOTE]
    > Lekérdezés alapú csomagot is létre lehet hozni, ha azt szeretné, hogy a rendszer automatikusan behúzza az új teszteseteket a BPM-ből az RSAT tesztcsomagba.

    ![Statikus csomag létrehozása](./media/setup_rsa_tool_56.png)

### <a name="attach-test-cases-to-test-suites"></a>Tesztelési esetek csatolása a tesztcsomagokhoz

1. A jobb oldali **Meglévő hozzáadása** gombbal hozzáadhat meglévő teszteket a tesztcsomaghoz.

    ![Meglévő hozzáadása gomb](./media/setup_rsa_tool_57.png)

2. A **Tesztesetek hozzáadása csomaghoz** oldalon válassza a **Lekérdezés futtatása** parancsot, majd válassza ki a tesztcsomaghoz hozzáadni kívánt tesztesetet. Ehhez az oktatóanyaghoz válassza az **Új termék létrehozása** esetet. Ezután válassza a **Tesztesetek hozzáadása** lehetőséget az oldal jobb alsó sarkában (ez a gomb nem látható az alábbi ábrán).

    ![Lekérdezés futtatása gomb](./media/setup_rsa_tool_58.png)

    A tesztesetet hozzáadta a **T01 – Készletre gyártás** tesztcsomaghoz.

    ![Teszteset hozzáadva a tesztcsomaghoz](./media/setup_rsa_tool_59.png)

### <a name="configure-rsat"></a>RSAT beállítása

1. Nyissa meg az RSAT-ot.

    ![RSAT ikon](./media/setup_rsa_tool_60.png)

2. Figyelmeztető üzenet jelenik meg, amely kijelenti, hogy: „A Regression Suite Automation Tool használatához Selenium szükséges, szeretné automatikusan letölteni és telepíteni most?” Válassza ki az **Igen** lehetőséget.

    ![Figyelmeztető üzenet](./media/setup_rsa_tool_61.png)

3. Válassza a jobb felső sarokban a **Beállítások** gombot (fogaskerék szimbólum), majd a megjelenő párbeszédpanelen töltse ki a következő mezőket:

    - **Azure DevOps URL** – Adja meg a Azure DevOps-projekt URL-címét, például `https://yourAzureDevOpsUrlHere.visualStudio.com`.
    - **Hozzáférési token** – adja meg azt a hozzáférési tokent, amely lehetővé teszi, hogy az eszköz csatlakozhasson az Azure DevOps rendszerhez. Az oktatóprogramban korábban létrehozott személyes hozzáférési tokent használja. A további tudnivalókat lásd: [Hozzáférés hitelesítése személyes hozzáférési jogkivonatokkal](https://www.visualstudio.com/docs/setup-admin/team-services/use-personal-access-tokens-to-authenticate).
    - **Projekt neve** – válassza ki a Azure DevOps-projekt nevét.
    - **Tesztelési terv** – válassza ki azt a Azure DevOps-tesztelési tervet, amely a teszt eseteit tartalmazza. A további tudnivalókat lásd: [Tesztelési tervek és tesztcsomagok létrehozása](https://www.visualstudio.com/docs/test/manual-exploratory-testing/getting-started/create-a-test-plan). Miután kiválasztotta a tesztelési tervet, válassza a **Kapcsolat ellenőrzése** lehetőséget, és tesztelje a kapcsolatot az Azure DevOps rendszerhez.
    - **Állomásnév** – adja meg a tesztkörnyezet állomásnevét, például **\<myaos\>.cloudax.dynamics.com**. Ne szerepeljen a **https://** vagy **http://** előtag.
    - **SOAP állomásnév** – adja meg a tesztkörnyezet SOAP-állomásnevét. A SOAP-állomásnév általában ugyanaz, mint az állomásnév, de van **soap** -utótagja. Itt egy példa: **\<myaos\>soap.cloudax.dynamics.com**. Ne szerepeljen a **https://** vagy **http://** előtag.

        > [!NOTE]
        > Az állomásnév és a SOAP-állomás nevének megkereséséhez nyissa meg az IIS-kezelőt, kattintson a jobb gombbal a **Webhelyek \> AOSService** elemre, majd válassza a **Kötések szerkesztése** parancsot. Az **állomásnév** oszlopban szereplő értékek adják meg az állomásnevet és a SOAP-állomásnevet (a SOAP-állomásnév URL-címében **SOAP**-utótagnak kell lennie).

        ![Az állomásnév és SOAP-állomásnév az állomásnév oszlopban](./media/setup_rsa_tool_63.png)

    - **Rendszergazda felhasználóneve** – Adja meg a rendszergazda felhasználó e-mail-címét a tesztkörnyezetben.
    - **Ujjlenyomat** – adja meg a hitelesítési tanúsítvány ujjlenyomatát az oktatóanyagban korábban leírt módon.
    - **Munkakönyvtár** – adja meg a mappa helyét a tesztautomatizálás fájljainak (például az Excel tesztadatfájlok) tárolásához. Például írja be vagy válassza ki **C:\\Temp\\RegressionTool** mappát.

        > [!NOTE]
        > Ha a mappa neve szóközöket tartalmaz, akkor a végrehajtás sikertelen lesz, mert a mappa nem található. Ez a probléma ismert probléma, és kijavítjuk az eszköz egy későbbi verziójában.

    - **Alapértelmezett böngésző** – válassza vagy az **Internet Explorer** vagy **Google Chrome** elemet. Ellenőrizze, hogy telepítve vannak-e a megfelelő böngésző-illesztőprogramok.
    - **Tesztfuttatás időtúllépése** – Adja meg az időtúllépés hosszát percben megadva a tesztfutásokhoz. Amikor az időtúllépési időszak eltelik, az összes aktív ablak le lesz zárva, és a függőben lévő tesztesetek sikertelenek lesznek.
    - **Tesztelési művelet időtúllépése** – ez a mező a Finance and Operations környezet kiszolgálói kérelmeinek időtúllépési idejét határozza meg percben. Általában az alapértelmezett értéknek (2 perc) elégnek kell lennie. A lassabb környezetek esetében azonban előfordulhat, hogy érdemes az értéket növelni, ha időtúllépéssel kapcsolatos hibák történnek.
    - **Vállalatnév** – Adja meg annak a vállalatnak a nevét, amelyet alapértelmezett vállalatként kell használni az Excel-paraméterfájlok létrehozásakor. A vállalat később módosítható az Excel-paraméterfájl szerkesztésével.

    ![Beállítások párbeszédpanel](./media/setup_rsa_tool_62.png)

4. Válassza az **Alkalmazás** parancsot a beállítások alkalmazásához és mentéséhez.

    Ha menteni szeretné az aktuális beállításokat a számítógép konfigurációs fájljába, válassza a **Mentés másként** parancsot. Ha vissza szeretné állítani a beállításokat a számítógép konfigurációs fájljából, válassza a **Megnyitás** parancsot.

5. A **Bezárás** gombbal zárja be a párbeszédpanelt.

### <a name="load-and-run-test-cases"></a>Tesztesetek betöltése és futtatása

1. Válassza a **Betöltés** parancsot az **RSAT tesztelési terv** tesztelési terv betöltéséhez az Azure DevOps projektből.

    ![Betöltés gomb](./media/setup_rsa_tool_64.png)

2. Válassza a tesztcsomagból az **Új termék létrehozása** tesztesetet, majd az **Új \> Tesztvégrehajtás és paraméterfájlok létrehozása**.

    ![Tesztvégrehajtás és paraméterfájlok létrehozása parancs az Új menüben](./media/setup_rsa_tool_65.png)

    A program az Excel-paraméterfájlt a RSAT-konfigurációban megadott helyi mappában hozza létre (például **C:\\Temp\\RegressionTool**).

    ![Excel-paraméterfájl létrehozva](./media/setup_rsa_tool_66.png)

3. Ha menteni szeretné a paraméterfájlokat, válassza a **Feltöltés** elemet. A program az összes kiválasztott teszteset tesztautomatizálási fájljait feltölti az Azure DevOps rendszerbe jövőbeli használatra. (Ezek a fájlok tartalmazzák az Excel teszt-paraméterfájlokat.)

    Ilyenmódon a **Betöltés** paranccsal a paraméterfájlokat (és automatizálási fájlokat) a tesztesetből közvetlenül az Azure DevOps rendszerből töltheti be. Nem kell újragenerálni a paraméterfájlokat. Ez a megközelítés később fontos lesz, amikor meg szeretné tartani a módosításokat a paraméterfájlban, és nem szeretné, hogy felülírják őket.

4. Ha ellenőrizni szeretné, hogy az automatizálási fájlok és a paraméterfájlok mentésre kerültek az Azure DevOps rendszerbe, nyissa meg az Azure DevOps-projektet, válassza ki a **Táblák \> Munkaelemek** pontot, majd az **Új termék létrehozása** tesztesetet. A **Mellékletek** lapon négy fájl jelenik meg:

    - **.cs** – C\# automatizálási fájl
    - **.dll** – Lefordított automatizálási fájl szerelvényként
    - **.xlsx** – Excel-paraméterfájl
    - **.xml** – Rögzítési fájl

    ![A mellékletek lap fájljai](./media/setup_rsa_tool_67.png)

5. Válassza ki a futtatni kívánt tesztesetet, majd válassza a **Futtatás** parancsot.

    > [!NOTE]
    > Ha a használt böngésző Internet Explorer, akkor a tesztesetek futtatása előtt győződjön meg arról. hogy az Asztal felbontása **100%**-ra van állítva a **Windows képernyőbeállításai \> Méretezés és elrendezés** pontban. Ha nem tudja megváltoztatni ezt a beállítást egy virtuális gépen (VM), akkor módosítsa azt a kliensen (laptop), amelyről a VM-et szeretné elérni. A felbontás beállításait a VM képernyőbeállításai öröklik.

    ![Asztali felbontás 100%-ra állítva](./media/setup_rsa_tool_68.png)

6. Ha a böngésző illesztőprogramjai nincsenek telepítve a rendszerben, akkor egy figyelmeztető üzenet jelenik meg, amely kijelenti: „Ehhez a művelethez a \<browser name\> illesztőprogram szükséges. Automatikusan letölti és telepíti most?” Válassza ki az **Igen** lehetőséget.

    ![Figyelmeztető üzenet az Internet Explorer böngészőhöz](./media/setup_rsa_tool_69.png)

    ![Figyelmeztető üzenet az Chrome böngészőhöz](./media/setup_rsa_tool_70.png)

    > [!NOTE]
    > Ha a Chrome böngészőt használja, és egy hibaüzenet jelenik meg, amely azt jelzi, hogy a munkamenet nem lett létrehozva, mert a Chrome-verzió nem megfelelő, töltse le a legfrissebb Chrome-illesztőprogramot a <http://chromedriver.chromium.org/downloads> oldalról a **C:\\Program Files (x86)\\Regression Suite Automation Tool\\Common\\External\\Selenium** mappába.

    ![Hibaüzenet az Chrome böngészőhöz](./media/setup_rsa_tool_71.png)

    A program futtatja a tesztesetet, és frissíti az **eredmény** mezőt.

    ![Folyamatjelző](./media/setup_rsa_tool_72.png)

    Ha a leírtaknak megfelelően követte az oktatóanyagot, az **Új termék létrehozása** teszteset sikertelen lesz, mert a termék létrehozásához tartozó feladatrögzítés a terméknevet beégetett értékként mentette. Ha újból futtatja ugyanazt a tesztesetet, hibaüzenetet kap, mert a termék már létezik.

    ![Eredménymező értéke Sikertelen](./media/setup_rsa_tool_72.png)

### <a name="view-the-test-results"></a>Teszteredmények megtekintése

1. Kattintson duplán a sikertelen tesztesetre.

    Hibaüzenetet kap.

    ![Hibaüzenet](./media/setup_rsa_tool_73.png)

2. A teljes hibaüzenet megjelenítéséhez kattintson a **Részletek** gombra.

    ![Teljes hibaüzenet](./media/setup_rsa_tool_74.png)

3. A hibaüzenet részletes verziójának Azure DevOps rendszerben való megtekintéséhez válassza a **Megnyitás Azure DevOps rendszerben** elemet. Az Azure DevOps rendszerben megtekintheti a teszteset állapotát és a részletes hibaüzenetet.

    ![Részletes hibaüzenet az Azure DevOps rendszerben](./media/setup_rsa_tool_75.png)

4. Ha közvetlenül az Azure DevOps-projektben szeretné megtekinteni a teszt eredményeit, lépjen a **Tesztelési tervek \> Tesztelési tervek \> Futások** menüpontra. Kattintson duplán a teszt futtatására, amelyről további részleteket szeretne látni.

    ![Tesztfutások listája az Azure DevOps rendszerben](./media/setup_rsa_tool_76.png)

5. Az **Futás összefoglalása** lap azt jelzi, hogy a teszteset nem sikerült, de nem biztosítja a tényleges hibaüzenetet. Ha meg szeretné tekinteni a részletes hibaüzenetet, válassza ki a **Teszteredmények** lapot.

    ![Futás összefoglalása lap](./media/setup_rsa_tool_77.png)

    A **teszteredmények** lap a tesztesettel kapcsolatos információkat, valamint az eredményt és a hibaüzenetet tartalmazza.

    ![Teszteredmények lap](./media/setup_rsa_tool_78.png)

6. A részletes hibaüzenet megjelenítéséhez kattintson duplán a megfelelő rekordra.

    ![Részletes hibaüzenet](./media/setup_rsa_tool_79.png)

    > [!NOTE]
    > Minden hibaüzenet helyileg is elérhető itt: **C:\\Users\\\$YourUserName\\AppData\\Roaming\\regressionTool\\errormsg-.txt**.

7. A tesztfutás eredményeit a tesztelési terv szintjéről is exportálhatja az **Export** paranccsal.

    ![Tesztelési terv exportálása](./media/setup_rsa_tool_80.png)

### <a name="modify-the-excel-parameter-file"></a>Excel-paraméterfájl módosítása

1. Nyissa meg az RSAT-ot.
2. Válassza ki a tesztesetet, majd a **Szerkesztés** parancsot az Excel-paraméterfájl megnyitásához.

    Az **EcoResProductCreate** lapon figyelje meg, hogy a **Termékszám** mezőjének értéke nem beégetett. Ezt a mezőt új termékszámra kell frissítenie a teszteset újbóli futtatása előtt.

3. Ha minden egyes futtatáshoz egyedi termékazonosítót szeretne létrehozni anélkül, hogy minden alkalommal újra meg kelljen nyitni az Excel-paraméterfájlt, és manuálisan kelljen frissíteni a termékszámot, használja a következő Excel-formulát.

    ```
    ="RSAT_"&TEXT(NOW(),"yyymmddhhmm")
    ```

    > [!NOTE]
    > Az **Általános** lap mellett az Excel-paraméterfájl is tartalmaz egy adatlapot minden űrlapoldalhoz, amelyet a teszteset meglátogat.

    ![Termékszám mező](./media/setup_rsa_tool_81.png)

4. Válassza a **Mentés** gombot, majd zárja be az Excel-munkafüzetet.
5. Válassza a **Feltöltés** parancsot az Excel-paraméterfájl Azure DevOps rendszerbe való mentéséhez.

    ![Sikeres feltöltési üzenet](./media/setup_rsa_tool_82.png)

    > [!NOTE]
    > Ha a teszteseteket meghatározott felhasználói környezetben szeretné futtatni, adja meg a felhasználó e-mail-azonosítóját az Excel-paraméterfájl **Általános** lapján a **Tesztfelhasználó** mezőben. A RSAT legutóbbi verziójában módosult az Excel-paraméterfájl mezőinek elrendezése, de a koncepció ugyanaz marad.
    >
    > ![Tesztfelhasználó mező](./media/setup_rsa_tool_83.png)

### <a name="validate-the-results"></a>Eredmények ellenőrzése

- Válassza a **Futtatás** parancsot a teszt esetének újrafuttatásához, és ellenőrizze, hogy a teszteset sikeres volt-e. A teszt eredményeit a [Teszteredmények megtekintése](#view-the-test-results) szakaszban leírtaknak megfelelően tekintheti meg.

    ![Eredménymező értéke Sikeres](./media/setup_rsa_tool_84.png)

### <a name="chaining-of-test-cases"></a>Tesztesetek láncolása

A RSAT egyik alapvető funkciója a tesztesetek láncolása (az a képesség, amellyel egy teszt értékeket adhat át más teszteknek). A teszteseteket az Azure DevOps tesztelési tervben meghatározott sorrendben futtatjuk. (Ez a sorrend a tesztelési eszközben is módosítható.) Így ha az egyik tesztből a másikba szeretne változókat átadni, akkor fontos, hogy a tesztek megfelelő sorrendben legyenek.

Ebben a szakaszban egy mentett változót fog létrehozni az első tesztesethez, létrehoz egy második tesztesetet, majd átadja a mentett változót az első tesztesetből a második tesztesetbe. Ezt követően a teszteseteket láncolt tesztesetként futtatja majd az RSAT-ban.

#### <a name="modify-an-existing-task-recording-to-create-a-saved-variable"></a>Meglévő feladatrögzítés módosítása mentett változó létrehozásához

1. Nyissa meg az ügyfélprogramot.
2. Válassza ki a **Beállítások** gombot (a fogaskerék szimbólumát), majd válassza ki a **Feladatrögzítőt**.
3. Válassza a **Rögzítés szerkesztése** elemet.

    ![Rögzítés szerkesztése gomb](./media/setup_rsa_tool_85.png)

4. Válassza a **Megnyitás a Lifecycle Services szolgáltatásból** lehetőséget.

    ![Megnyitás a Lifecycle Services szolgáltatásból gomb](./media/setup_rsa_tool_86.png)

5. Válassza a **A Lifecycle Services-tár kiválasztása** elemet.

    ![A Lifecycle Services-tár kiválasztása gomb](./media/setup_rsa_tool_87.png)

    A BPM-tárak a LCS modulból töltődnek be.

    ![Folyamatjelző](./media/setup_rsa_tool_88.png)

6. Miután megtörtént a BPM-tárak betöltése az LCS-ból, válassza ki a **RSAT** BPM-tárat, és az **Új termék létrehozása** üzleti folyamatot, amelyhez a feladatrögzítést társították. Majd kattintson az **OK** lehetőségre.

    ![BPM-tár és üzleti folyamat kiválasztása](./media/setup_rsa_tool_89.png)

7. A megfelelő feladatrögzítés neve megadásra kerül a **Rögzítés neve** mezőbe. Válassza az **Indítás** lehetőséget.

    ![A feladatrögzítés neve a Rögzítés neve mezőben](./media/setup_rsa_tool_90.png)

8. Lépjen a **Termékinformációk kezelése \> Termékek** pontra, válassza az **Új** elemet az oldal megnyitásához, ahol az eredeti feladatrögzítés **Termék létrehozása** rögzítésre került.
9. Válassza a **Lépés beszúrása** lehetőséget.

    > [!NOTE]
    > A program az új lépést a panelen kiválasztott lépés **után** szúrja be.

    ![Lépés beszúrása gomb](./media/setup_rsa_tool_91.png)

10. Kattintson jobb gombbal a **Termékszám** mezőre, majd válassza a **Feladatrögzítő \> Másolás** lehetőséget.

    ![Másolás parancs](./media/setup_rsa_tool_92.png)

11. A program új lépést hozzáadta a panelhez. Jegyezze fel a **Termékszám** mezőjének értékét, mert később szüksége lesz rá.

    ![Új lépés hozzáadva](./media/setup_rsa_tool_93.png)

12. Válassza a **Szerkesztés kész** lehetőséget.
13. Válassza a **Mentés a Lifecycle Services szolgáltatásba** parancsot, majd társítsa az új feladatrögzítést ugyanahhoz a BPM-tárhoz és üzleti folyamathoz, amelyhez az eredeti feladatrögzítést társította. További információk: [Feladatrögzítés létrehozása és mentése BPM-tárba](#create-a-task-recording-and-save-it-to-the-bpm-library).
14. Lépjen a BPM-tárba és válassza a **Tesztesetek szinkronizálása** lehetőséget a tesztesethez az Azure DevOps rendszerben társított feladatrögzítés felülírása érdekében a [A BPM-ről az Azure DevOps szolgáltatásba történő szinkronizálás tesztelése](#test-the-synchronization-from-bpm-to-azure-devops) szakaszban leírtak szerint.
15. Nyissa meg az RSAT eszközt, és válassza a **Betöltés** parancsot a tesztcsomag összes tesztesetének újbóli betöltéséhez. A megfelelő tesztesethez újból létre kell hoznia az automatizálási és paraméterfájlokat úgy, hogy kiválasztja a tesztesetet, majd az **Új \> Teszt-végrehajtási és paraméterfájlok létrehozása** elemet választja, a [Tesztesetek betöltése és futtatása](#load-and-run-test-cases) részben leírtaknak megfelelően.

    > [!NOTE]
    > Ha az Excel-paraméterfájl nyitva maradt, az újbóli létrehozás nem fog sikerülni. Győződjön meg róla, hogy a tesztesethez tartozó Excel-paraméterfájl be van zárva, mielőtt létrehozza az új Excel-paraméterfájlt.

16. Az új Excel-paraméterfájl megnyitásához válassza a **Szerkesztés** parancsot. Egy új, **mentett változó** nevű bejegyzést fog látni a 9. sorban. Ez a változó, az **{{EcoResProductCreate\_Identification\_ProductNumber\_Copy}}** a feladatrögzítés XML-fájljába lett mentve, és az egymást követő teszteknél használható.

    ![Mentett változó bejegyzése](./media/setup_rsa_tool_94.png)

#### <a name="create-a-new-test-case"></a>Új teszteset létrehozása

1. Lépjen az **RSAT** BPM-tárhoz.
2. Válassza ki az **Minta támogatási üzleti folyamat** folyamatot, majd a jobb oldalon a **Szerkesztési mód** elemet.
3. A **Név** és a **Leírás** mező értékét módosítsa **Termék kiadása** értékre. Majd válassza a **Mentés** lehetőséget.

    ![Termék kiadása névre módosult a név és leírás](./media/setup_rsa_tool_95.png)

#### <a name="create-a-new-task-recording-that-has-a-validate-function"></a>Ellenőrzés funkciót tartalmazó új feladatrögzítés létrehozása

- Hozzon létre egy új feladatrögzítést, amely kiadja a korábban létrehozott terméket az USRT jogi személynek. További információk: [Feladatrögzítés létrehozása és mentése BPM-tárba](#create-a-task-recording-and-save-it-to-the-bpm-library).

    > [!NOTE]
    > A láncolt tesztesetekhez mindig azt ajánljuk, hogy keressen rá vagy szűrjön a szükséges mezőre *az érték manuális beírásával a mezőbe*. Ily módon az eszköz meghatározhatja azt a rekordot, amelyet a műveletnek az egymást követő teszteseteken kell elvégeznie.

    ![Ellenőrzés funkciót tartalmazó új feladatrögzítés](./media/setup_rsa_tool_96.png)

    Ahogy az előző ábra mutatja, miután a terméket megtalálta a gyorsszűrő segítségével, de mielőtt kiválasztja a **Termékek kiadása** elemet, ellenőrizze a **Termékszám** mező értékét, hogy a termékszám egyezik-e a korábban létrehozott termékszámmal. Az érték ellenőrzéséhez kattintson a jobb gombbal a **Termékszám** mezőre, majd válassza a **Feladatrögzítő \> Ellenőrzés \> Aktuális érték**

    ![Az aktuális érték ellenőrzése](./media/setup_rsa_tool_97.png)

#### <a name="save-the-task-recording-to-bpm"></a>Feladatrögzítés mentése a BPM-be

1. A feladatrögzítés befejezése után válassza a **Mentés a Lifecycle Services szolgáltatásba** lehetőséget.

    ![Mentési beállítások](./media/setup_rsa_tool_98.png)

2. A tár adatait a rendszer az LCS-ből tölti be.

    ![Folyamatjelző](./media/setup_rsa_tool_99.png)

3. Válassza ki a feladatrögzítéshez társítandó BPM-tárat. Ehhez az oktatóanyaghoz válassza ki a korábban létrehozott **RSAT** BPM-tárat, és az alatta lévő **termék kiadása** üzleti folyamatot. Majd kattintson az **OK** lehetőségre.

#### <a name="sync-bpm-to-azure-devops"></a>BPM szinkronizálása az Azure DevOps rendszerbe

1. Nyissa meg a BPM-tárat, és nyissa meg az **RSAT** -könyvtárat.
2. Válassza a **VSTS szinkronizálás**, majd a **Tesztesetek szinkronizálása** lehetőséget. További információk: [A BPM-ről Azure DevOps szolgáltatásba történő szinkronizálás tesztelése](#test-the-synchronization-from-bpm-to-azure-devops).

    A szinkronizálás befejezése után az új munkaelem és a kapcsolódó teszteset a **Termék kiadása** üzleti folyamathoz megjelenik az Azure DevOps rendszerben a **Táblák \> Munkaelemek** pontban.

#### <a name="add-the-new-test-case-to-the-existing-test-suite"></a>Az új tesztelési eset hozzáadása a meglévő tesztcsomaghoz

1. Lépjen a **Tesztelési tervek \> Tesztelési tervek** menüpontba, és válassza az **RSAT tesztelési terv** tervet.
2. Válassza a **Meglévő hozzáadása** parancsot.
3. A **Tesztesetek hozzáadása a csomaghoz** oldalon válassza a **Lekérdezés futtatása** parancsot.
4. Válassza ki a **Termék kiadása** címmel létrehozott új tesztesetet, majd válassza az oldal jobb alsó sarkában a **Tesztesetek hozzáadása** lehetőséget (ez a gomb nem látható az alábbi ábrán).

    ![Tesztesetek hozzáadása a csomaghoz oldal](./media/setup_rsa_tool_100.png)

    A tesztcsomagnak most két tesztesete van.

    ![Két teszteset a tesztcsomagban](./media/setup_rsa_tool_101.png)

#### <a name="load-test-cases-into-rsat"></a>Tesztesetek betöltése az RSAT-ba

1. Nyissa meg az RSAT-ot, majd válassza a **Betöltés** elemet.
2. A tesztesetek betöltődnek, és megjelenik egy figyelmeztetés, amit azt írja: „Ez a művelet felülírja az Excel-tesztadatfájlokat, a helyi módosítások elvesznek. Szeretné folytatni?” Válassza az **Igen** lehetőséget, ha szeretné a helyi rendszerben található Excel-paraméterfájlokat, de azokat az Excel-paraméterfájlokat nem, amelyeket feltöltött az Azure DevOps rendszerbe.

    ![Figyelmeztető üzenet](./media/setup_rsa_tool_102.png)

    Mindkét tesztesetet betölti a rendszer az első tesztesethez tartozó Excel-paraméterfájllal együtt. Mivel a **Feltöltést** a legutóbbi futtatáskor kiválasztotta, a program az Azure DevOps rendszerből húzza be a paraméterfájlokat.

    ![A tesztesetek betöltődtek](./media/setup_rsa_tool_103.png)

3. Válassza ki a második tesztesetet, majd válassza az **Új \> Teszt-végrehajtási és paraméterfájlok létrehozása** elemet.

#### <a name="edit-the-excel-parameter-file"></a>Excel-paraméterfájl szerkesztése

1. Válassza ki csak a második tesztesetet, majd a **Szerkesztés** parancsot a kapcsolódó Excel-paraméterfájl megnyitásához.
2. Másolja az **{{EcoResProductCreate\_Identification\_ProductNumber\_Copy}}** mentett változót (lásd: [Meglévő feladatrögzítés módosítása mentett változó létrehozásához](#modify-an-existing-task-recording-to-create-a-saved-variable) szakaszt) az első tesztesetből a termékszámot használó összes mezőbe. Ebben az esetben a változót a **Termékszám** és **Termékszám ellenőrzése** mezőkbe másolja az **EcoResProductListPage** munkafüzetben.

    ![Termékszám és Termékszám ellenőrzése mezők](./media/setup_rsa_tool_104.png)

    > [!NOTE]
    > A változók csak ugyanazon tesztfutás során adhatók át a tesztek között. A változók neveinek pontosan egyezniük kell.

3. Válassza a **Mentés** gombot, majd zárja be az Excel-munkafüzetet.
4. A **Feltöltés** gombra kattintva mentheti a módosításokat, amelyeket az Excel-paraméterfájlban tett.

#### <a name="run-the-chained-test-cases"></a>A láncolt tesztesetek futtatása

1. Válassza ki a mindkét tesztesetet, majd válassza a **Futtatás** parancsot.
2. Ellenőrizze, hogy mindkét teszteset sikeres volt-e.

    ![Eredmény mező Sikeres értékre állítva mindkét tesztesetnél](./media/setup_rsa_tool_105.png)
