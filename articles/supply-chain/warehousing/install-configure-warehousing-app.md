---
title: "A Microsoft Dynamics 365 for Finance and Operations &#8211; Warehousing telepítése és konfigurálása"
description: "Ez a témakör ismerteti, hogyan telepítse és konfigurálja a Microsoft Dynamics 365 for Finance and Operations - Warehousing alkalmazást."
author: MarkusFogelberg
manager: AnnBe
ms.date: 11/12/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SysAADClientTable, WHSMobileAppField, WHSMobileAppFieldPriority, WHSRFMenu, WHSRFMenuItem, WHSWorker
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 267694
ms.assetid: d95d43b2-13ff-4189-a71a-3a1fb57d55ed
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mafoge
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 0967b10c2037c24c044f38c49b1b998f6771c66b
ms.openlocfilehash: a1f3cb65e370154e8f3f94780ffb5cab223c85f8
ms.contentlocale: hu-hu
ms.lasthandoff: 12/04/2018

---

# <a name="install-and-configure-microsoft-dynamics-365-for-finance-and-operations-8211-warehousing"></a>A Microsoft Dynamics 365 for Finance and Operations &#8211; Warehousing telepítése és konfigurálása

[!include [banner](../includes/banner.md)]

> [!NOTE]
> 
> Ez a témakör ismerteti, hogyan kell konfigurálni a felhőbeli telepítések raktárkészlet-nyilvántartását. Ha azt szeretné megtudni, hogyan kell konfigurálni az on-premises telepítések raktárkészlet-nyilvántartását, lásd: [Helyszíni telepítések raktárkezelése](../../dev-itpro/deployment/warehousing-for-on-premise-deployments.md).


Ez a témakör ismerteti, hogyan telepítse és konfigurálja a Microsoft Dynamics 365 for Finance and Operations - Warehousing alkalmazást.

A Finance and Operations - Warehousing a Google Play Áruházban és a Windows Áruházban elérhető alkalmazás. A Finance and Operations alkalmazás különálló összetevőként érhető el, ami azt jelenti, hogy raktári feladatokhoz eszközökre önállóan telepíthető. Az alkalmazás a Finance and Operations környezetben való használatához minden eszközre le kell tölteni az alkalmazást, konfigurálni kell a Finance and Operations környezethez való kapcsolódáshoz. Ez a témakör ismerteti az alkalmazás eszközökre telepítésének módját. Azt is bemutatja, hogyan konfigurálhatja az alkalmazást a Finance and Operations környezethez való csatlakozáshoz.

## <a name="prerequisites"></a>Előfeltételek
Az alkalmazás Android és Windows operációs rendszereken érhető el. Az alkalmazás használatához rendelkeznie kell az eszközökre telepített alábbi támogatott operációs rendszerek egyikével. Emellett rendelkeznie kell a Finance and Operations következő támogatott verzióinak valamelyikével. A következő táblázatban található információk segítségével értékelje, hogy a hardver- és szoftverkörnyezetbe készen áll-e a telepítés támogatására.

| Platform                    | Verzió                                                                                                                                                                     |
|-----------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Android                     | 4.4, 5.0, 6.0, 7.0, 8.0                                                                                                                                                     |
| Windows (UWP)               | Windows 10 (összes verzió)                                                                                                                                                   |
| Finance and Operations | Microsoft Dynamics 365 for Operations, 1611-es verzió <br>– vagy – <br>Microsoft Dynamics AX 7.0/7.0.1 verziója és a Microsoft Dynamics AX platform 2. frissítése a KB 3210014 gyorsjavítással |

## <a name="get-the-app"></a>Az alkalmazás beszerzése
-   Windows (UWP)
     - [Finance and Operations - Warehousing a Windows Áruházban](https://www.microsoft.com/store/apps/9p1bffd5tstm)
-   Android
    - [Finance and Operations - Warehousing a Google Play Áruházban](https://play.google.com/store/apps/details?id=com.Microsoft.Dynamics365forOperationsWarehousing)
    - [Finance and Operations - Warehousing a Zebra AppGalleryben](https://appgallery.zebra.com/showcase/apps/146?type=showcase)

## <a name="create-a-web-service-application-in-azure-active-directory"></a>Webszolgáltatási alkalmazás létrehozása az Azure Active Directoryban
Ahhoz, hogy az alkalmazás együttműködhessen a kívánt Finance and Operations kiszolgálóval, regisztrálnia kell egy webszolgáltatási alkalmazást az Azure Active Directoryban a Finance and Operations bérlő számára. Biztonsági okokból az összes használt eszköz számára ajánlott létrehozni egy-egy webszolgáltatási alkalmazást. Webszolgáltatási alkalmazás létrehozásának lépései az Azure Active Directoryban (Azure AD):

1.  Lépjen egy böngészőben a <https://portal.azure.com> címre.
2.  Adja meg a felhasználó nevét és jelszavát, aki hozzáfér az Azure-előfizetéshez.
3.  Az Azure-portálon a bal oldali navigációs ablaktáblán kattintson az **Azure Active Directory** elemre.[](./media/WMA-01-active-directory-example.png)[![WMA-01-active-directory-example](./media/WMA-01-active-directory-example.png )](./media/WMA-01-active-directory-example.png)
4.  Győződjön meg róla, hogy az Active Directory-példány az, amelyet a Finance and Operations használ.
5.  A listában kattintson az **Alkalmazásregisztrációk** elemre. [![WMA-02-active-directory-app-registrations](./media/WMA-02-active-directory-app-registrations.png)](./media/WMA-02-active-directory-app-registrations.png)
6.  Kattintson a felső panelen az **Új alkalmazás regisztrálása** elemre. Az **Alkalmazás hozzáadása** varázsló elindul.
7.  Adjon meg egy nevet az alkalmazásnak, és válassza ki a **Webes alkalmazás / web API** lehetőséget. Adja meg a bejelentkezési URL-címet, amely a webes alkalmazás URL-címe. Az URL-cím megegyezik a telepítés URL-címével, de a végéhez hozzá van adva az oauth. Kattintson az **Új** > lehetőségre. [![WMA-03-active-directory-add-application](./media/WMA-03-active-directory-add-application.png)](./media/WMA-03-active-directory-add-application.png)
8.  Válassza ki az új alkalmazást a listából. [![WMA-04-active-directory-configure-app](./media/WMA-04-active-directory-configure-app.png)](./media/WMA-04-active-directory-configure-app.png)
9.  Ne felejtse el a **alkalmazásazonosítót**, később szükség lesz rá. Az **Alkalmazásazonosítóra** később **Ügyfél-azonosító** néven utalunk.
10. Kattintson a **Kulcsok** elemre a **Beállítások panelen**. Hozzon létre egy kulcsot egy kulcsleírás és egy időtartam beírásával a **Jelszavak** részben. 
11. Kattintson a **Mentés** elemre, és másolja le a kulcsot. A kulcs neve a továbbiakban: **Titkos ügyfélkód**. [![WMA-05-active-directory-create-key](./media/WMA-05-active-directory-create-key.png)](./media/WMA-05-active-directory-create-key.png)

## <a name="create-and-configure-a-user-account-in-finance-and-operations"></a>Felhasználói fiók létrehozása és konfigurálása a Finance and Operationsben
Annak érdekében, hogy a Finance and Operations képes legyen az Azure AD alkalmazás használatára, kövesse az alábbi konfigurációs lépéseket:

1.  Hozzon létre egy olyan Finance and Operations-felhasználót, amely megfelel a raktározási alkalmazás felhasználói hitelesítő adatainak.
    1.  A Finance and Operationsben lépjen a **Rendszerfelügyelet** &gt; **Közös** &gt; **Felhasználók** elemre.
    2.  Hozzon létre egy új felhasználót.
    3.  Rendelje hozzá a Warehouse-mobileszköz felhasználóját, amint azt a következő képernyőképen látható. [![wh-09-add-user-security-role](./media/wh-09-add-user-security-role.png)](./media/wh-09-add-user-security-role.png)

2.  Társítsa az Azure Active Directory alkalmazást a raktározási alkalmazás felhasználójával.
    1.  A Finance and Operationsben lépjen a **Rendszerfelügyelet** &gt; **Beállítás** &gt; **Azure Active Directory alkalmazások** elemre.
    2.  Hozzon létre egy új sort.
    3.  Adja meg az (az utolsó szakaszban kapott) **Ügyfél-azonosítót**, adjon neki nevet, és válassza ki a korábban létrehozott felhasználót. Azt javasoljuk, hogy az összes eszközt lássa el címkével, hogy egyszerűen eltávolíthassa hozzáférésüket a Finance and Operationshöz erről az oldalról abban az esetben, ha az eszközök elvesznek. [![wh-10-ad-applications-form](./media/wh-10-ad-applications-form.png)](./media/wh-10-ad-applications-form.png)

## <a name="configure-the-application"></a>Az alkalmazás konfigurálása
Konfigurálnia kell az alkalmazást az eszközön, hogy csatlakozni tudjon a Finance and Operations kiszolgálóhoz Azure AD alkalmazáson keresztül. Ehhez a következő lépéseket kell végrehajtani.

1.  Az alkalmazásban lépjen a **Kapcsolat beállításai** elemre.
2.  Törölje a **Bemutató mód** mezőt. <br>[![wh-11-app-connection-settings-demo-mode](./media/wh-11-app-connection-settings-demo-mode-169x300.png)](./media/wh-11-app-connection-settings-demo-mode.png)
3.  Adja meg a következő adatokat: 
    + **Azure Active Directory ügyfél-azonosító** - Az ügyfél-azonosító beszerzése a 9. „Webszolgáltatási alkalmazás létrehozása az Active Directoryban" című lépésben történik. 
    + **Azure Active Directory titkos ügyfélkód** - A titkos ügyfélkód beszerzése a 11. „Webszolgáltatási alkalmazás létrehozása az Active Directoryban" című lépésben történik. 
    + **Azure Active Directory-erőforrás** - Az Azure Active Directory-erőforrás a Finance and Operations gyökér-URL-jét jeleníti meg. **Megjegyzés:**: ne zárja perjellel (/) ezt a mezőt. 
    + **Azure Active Directory-bérlő** – a Finance and Operations kiszolgálón használt Azure AD Directory-bérlő: `https://login.windows.net/your-AD-tenant-ID`. Például: `https://login.windows.net/contosooperations.onmicrosoft.com.` 
    <br>**Megjegyzés:**: ne zárja perjellel (/) ezt a mezőt. 
    + **Vállalat** - adja meg a Finance and Operationsben szereplő jogi személyt, amelyhez az alkalmazásnak csatlakoznia kell. <br>[![wh-12-app-connection-settings](./media/wh-12-app-connection-settings-169x300.png)](./media/wh-12-app-connection-settings.png)
4.  Válassza a **Vissza** gombot az alkalmazás bal felső sarkában. Az alkalmazás ekkor csatlakozik a Finance and Operations kiszolgálóhoz, és megjelenik a raktári dolgozó bejelentkezési képernyője. <br>[![wh-13-log-in-screen](./media/wh-13-log-in-screen-180x300.png)](./media/wh-13-log-in-screen.png)

A Dynamics 365 for Finance and Operations – Raktárkezelés, vonalkódok beolvasása a mobiltelefon kamerával beállításával kapcsolatos tájékoztatásért lásd: [Vonalkódok beolvasása kamerával a Dynamics 365 for Finance and Operations szolgáltatásban – Raktárkezelés](scan-bar-codes-using-a-camera.md)

## <a name="remove-access-for-a-device"></a>Eszköz hozzáférésének eltávolítása
Abban az esetben, ha egy eszköz elveszett vagy a biztonsága sérült, el kell távolítania az eszköz a Finance and Operationshöz való hozzáférését. Az alábbi lépések leírják a hozzáférés-eltávolítás javasolt eljárását.

1.  A Finance and Operationsben lépjen a **Rendszerfelügyelet** &gt; **Beállítás** &gt; **Azure Active Directory alkalmazások** elemre.
2.  Törölje a sort, amely megfelel az eszköznek, amelynek a hozzáférését el szeretné távolítani. Ne felejtse el az eltávolított eszközhöz használt **ügyfél-azonosítót**, mert később szüksége lesz rá.
3.  Jelentkezzen be az Azure portálon: <https://portal.azure.com>.
4.  Kattintson az **Active Directory** ikonra a bal oldali menüben, és ellenőrizze, hogy a megfelelő könyvtárban van-e.
5.  A listában kattintson az **Alkalmazásregisztrációk** elemre, majd kattintson a konfigurálni kívánt alkalmazásra. Megjelenik a **Beállítások** oldal a konfigurációs adatokkal.
6.  Győződjön meg arról, hogy az alkalmazás **Ügyfél-azonosítója** ugyanaz, mint a 2. lépésben volt.
7.  Kattintson a felső panel **Törlés** gombjára.
8.  A megerősítő üzeneten kattintson az **Igen** gombra.

