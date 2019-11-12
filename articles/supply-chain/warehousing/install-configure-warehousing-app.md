---
title: A Raktározási alkalmazás telepítése és konfigurálása áttekintése
description: Ez a témakör leírja, hogyan telepítheti és konfigurálhatja a Dynamics 365 for Finance and Operations – Warehousing alkalmazást.
author: MarkusFogelberg
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
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
ms.openlocfilehash: f629fffc5c424c244a25bb8faef0435814398ee1
ms.sourcegitcommit: 4aac45c84b87f463b22b318f5f6f729f8d737090
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/03/2019
ms.locfileid: "2548968"
---
# <a name="install-and-configure-the-warehousing-app-overview"></a>A Raktározási alkalmazás telepítése és konfigurálása áttekintése

[!include [banner](../includes/banner.md)]

> [!NOTE]
> 
> Ez a témakör ismerteti, hogyan kell konfigurálni a felhőbeli telepítések raktárkészlet-nyilvántartását. Ha azt szeretné megtudni, hogyan kell konfigurálni az on-premises telepítések raktárkészlet-nyilvántartását, lásd: [Helyszíni telepítések raktárkezelése](../../dev-itpro/deployment/warehousing-for-on-premise-deployments.md).


Ez a témakör leírja, hogyan telepítheti és konfigurálhatja a Dynamics 365 for Finance and Operations – Warehousing alkalmazást.

A Warehousing alkalmazás a Google Play Store-ban és a Windows Áruházban érhető el. A Dynamics 365 Supply Chain Management alkalmazás különálló összetevőként érhető el, ami azt jelenti, hogy raktári feladatokhoz eszközökre önállóan telepíthető. Az alkalmazás használatához minden eszközre le kell tölteni az alkalmazást, konfigurálni kell a Supply Chain Management környezethez való kapcsolódáshoz. Ez a témakör ismerteti az alkalmazás eszközökre telepítésének módját. Azt is bemutatja, hogyan konfigurálhatja az alkalmazást a Supply Chain Management környezethez való csatlakozáshoz.

## <a name="prerequisites"></a>Előfeltételek
Az alkalmazás Android és Windows operációs rendszereken érhető el. Az alkalmazás használatához rendelkeznie kell az eszközökre telepített alábbi támogatott operációs rendszerek egyikével. Az alábbi támogatott verziók közül is rendelkeznie kell az egyikkel. A következő táblázatban található információk segítségével értékelje, hogy a hardver- és szoftverkörnyezetbe készen áll-e a telepítés támogatására.

| Platform                    | Verzió                                                                                                                                                                     |
|-----------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Android                     | 4.4, 5.0, 6.0, 7.0, 8.0, 9.0                                                                                                                                                     |
| Windows (UWP)               | Windows 10 (összes verzió)                                                                                                                                                   |
| Finance and Operations | Microsoft Dynamics 365 for Operations, 1611-es verzió <br>– vagy – <br>Microsoft Dynamics AX 7.0/7.0.1 verzió és Microsoft Dynamics AX platform update 2 a KB 3210014 gyorsjavítással |

## <a name="get-the-app"></a>Az alkalmazás beszerzése
-   Windows (UWP)
     - [Finance and Operations - Warehousing a Windows Áruházban](https://www.microsoft.com/store/apps/9p1bffd5tstm)
-   Android
    - [Finance and Operations - Warehousing a Google Play Áruházban](https://play.google.com/store/apps/details?id=com.Microsoft.Dynamics365forOperationsWarehousing)

> [!NOTE]
> A Zebra App Galleryt már megszüntették, ami azt jelenti, hogy a Warehousing alkalmazás nem lesz letölthető erről a helyről.

## <a name="create-a-web-service-application-in-azure-active-directory"></a>Webes szolgáltatás alkalmazás létrehozása az Azure Active Directory szolgáltatásban
Ahhoz, hogy az alkalmazás együttműködhessen a kívánt Supply Chain Management kiszolgálóval, regisztrálnia kell egy webszolgáltatási alkalmazást az Azure Active Directory felületén a Supply Chain Management bérlő számára. Biztonsági okokból az összes használt eszköz számára ajánlott létrehozni egy-egy webszolgáltatási alkalmazást. Hozzon létre a szolgáltatási webalkalmazást az Azure Active Directory (Azure AD) felületén, tegye a következőket:

1.  Lépjen egy böngészőben a <https://portal.azure.com> címre.
2.  Adja meg a felhasználó nevét és jelszavát, aki hozzáfér az Azure-előfizetéshez.
3.  Az Azure-portálon a bal oldali navigációs ablaktáblán kattintson az **Azure Active Directory**elemre.[](./media/WMA-01-active-directory-example.png)[![WMA-01-active-directory-example](./media/WMA-01-active-directory-example.png )](./media/WMA-01-active-directory-example.png)
4.  Győződjön meg róla, hogy az Active Directory-példány az, amelyet a Supply Chain Management használ.
5.  A listában kattintson az **Alkalmazásregisztrációk** elemre. [![WMA-02-active-directory-app-registrations](./media/WMA-02-active-directory-app-registrations.png)](./media/WMA-02-active-directory-app-registrations.png)
6.  Kattintson a felső panelen az **Új regisztrálás** elemre. Az **Alkalmazás regisztrálása varázsló** elindul.
7.  Írjon be egy nevet az alkalmazás számára, válassza a **Számlák csak ebben a szervezeti könyvtárban** lehetőséget. Kattintson a **Regisztráció** lehetőségre.  [![WMA-03-active-directory-add-application](./media/WMA-03-active-directory-add-application.png)](./media/WMA-03-active-directory-add-application.png)
8.  Megnyílik az új alkalmazás regisztrációja. [![WMA-04-active-directory-configure-app](./media/WMA-04-active-directory-configure-app.png)](./media/WMA-04-active-directory-configure-app.png)
9.  Ne felejtse el a **alkalmazásazonosítót**, később szükség lesz rá. Az **Alkalmazásazonosítóra** később **Ügyfél-azonosító** néven utalunk.
10. Kattintson a **Tanúsítványok és titkok** hivatkozásra a **Kezelés** ablaktáblán. Kattintson az **Új ügyféltitok** hivatkozásra. [![WMA-05-active-directory-create-key](./media/WMA-05-active-directory-create-key.png)](./media/WMA-05-active-directory-create-key.png)
11. Hozzon létre egy kulcsot egy kulcsleírás és egy időtartam beírásával a **Jelszavak** részben. Kattintson a **Hozzáadás** elemre, és másolja le a kulcsot. A kulcs neve a továbbiakban: **Titkos ügyfélkód**. [![WMA-06-active-directory-save-key](./media/WMA-06-active-directory-save-key.png)](./media/WMA-06-active-directory-save-key.png)

## <a name="create-and-configure-a-user-account-in-supply-chain-management"></a>Felhasználói fiók létrehozása és konfigurálása a Supply Chain Management megoldásban
Annak érdekében, hogy a Supply Chain Management képes legyen az Azure AD alkalmazás használatára, kövesse az alábbi konfigurációs lépéseket:

1.  Hozzon létre egy olyan felhasználót, amely megfelel a raktározási alkalmazás felhasználói hitelesítő adatainak.
    1.  Ugrás a **Rendszerfelügyelet** &gt; **Közös** &gt; **Felhasználók** elemre.
    2.  Hozzon létre egy új felhasználót.
    3.  Rendelje hozzá a Warehouse-mobileszköz felhasználóját, amint azt a következő képernyőképen látható. [![wh-09-add-user-security-role](./media/wh-09-add-user-security-role.png)](./media/wh-09-add-user-security-role.png)

2.  Társítsa az Azure Active Directory alkalmazást a raktározási alkalmazás felhasználójával.
    1.  A Supply Chain Management szolgáltatásban lépjen a **Rendszerfelügyelet** &gt; **Beállítás** &gt; **Azure Active Directory alkalmazások** elemre.
    2.  Hozzon létre egy új sort.
    3.  Adja meg az (az utolsó szakaszban kapott) **Ügyfél-azonosítót**, adjon neki nevet, és válassza ki a korábban létrehozott felhasználót. Azt javasoljuk, hogy az összes eszközt lássa el címkével, hogy egyszerűen eltávolíthassa hozzáférésüket a Supply Chain Managementhez erről az oldalról abban az esetben, ha az eszközök elvesznek. [![wh-10-ad-applications-form](./media/wh-10-ad-applications-form.png)](./media/wh-10-ad-applications-form.png)

## <a name="configure-the-application"></a>Az alkalmazás konfigurálása
Konfigurálnia kell az alkalmazást az eszközön, hogy csatlakozni tudjon a Supply Chain Management kiszolgálóhoz Azure AD alkalmazáson keresztül. Ehhez a következő lépéseket kell végrehajtani.

1.  Az alkalmazásban lépjen a **Kapcsolat beállításai** elemre.
2.  Törölje a **Bemutató mód** mezőt. <br>[![wh-11-app-connection-settings-demo-mode](./media/wh-11-app-connection-settings-demo-mode-169x300.png)](./media/wh-11-app-connection-settings-demo-mode.png)
3.  Adja meg a következő adatokat: 
    + **Azure Active Directory ügyfél-azonosító** - Az ügyfél-azonosító beszerzése a 9. „Webszolgáltatási alkalmazás létrehozása az Active Directoryban" című lépésben történik. 
    + **Azure Active Directory titkos ügyfélkód** - A titkos ügyfélkód beszerzése a 11. „Webszolgáltatási alkalmazás létrehozása az Active Directoryban" című lépésben történik. 
    + **Azure Active Directory-erőforrás** - Az Azure AD könyvtár-erőforrás a Supply Chain Management gyökér-URL-jét jeleníti meg. **Megjegyzés:**: ne zárja perjellel (/) ezt a mezőt. 
    + **Azure Active Directory-bérlő** – a Supply Chain Management kiszolgálón használt Azure AD könyvtárbérlő: `https://login.windows.net/your-AD-tenant-ID`. Például: `https://login.windows.net/contosooperations.onmicrosoft.com.` 
    <br>**Megjegyzés:**: ne zárja perjellel (/) ezt a mezőt. 
    + **Vállalat** - Adja meg a Supply Chain Managementben szereplő jogi személyt, amelyhez az alkalmazásnak csatlakoznia kell. <br>[![wh-12-app-connection-settings](./media/wh-12-app-connection-settings-169x300.png)](./media/wh-12-app-connection-settings.png)
4.  Válassza a **Vissza** gombot az alkalmazás bal felső sarkában. Az alkalmazás ekkor csatlakozik a Supply Chain Management kiszolgálóhoz, és megjelenik a raktári dolgozó bejelentkezési képernyője. <br>[![wh-13-log-in-screen](./media/wh-13-log-in-screen-180x300.png)](./media/wh-13-log-in-screen.png)

További információkért a Warehousing alkalmazás beállításával kapcsolatban arra, hogy a mobileszköz kameráját vonalkódok leolvasására használja, lásd: [Vonalkódok beolvasása kamera használatával a Dynamics 365 for Finance and Operations – Warehousing alkalmazásban](scan-bar-codes-using-a-camera.md)

## <a name="remove-access-for-a-device"></a>Eszköz hozzáférésének eltávolítása
Abban az esetben, ha egy eszköz elveszett vagy a biztonsága sérült, el kell távolítania az eszköz a Supply Chain Managementhez való hozzáférését. Az alábbi lépések leírják a hozzáférés-eltávolítás javasolt eljárását.

1.  Ugrás a **Rendszerfelügyelet** &gt; **Beállítás** &gt; **Azure Active Directory alkalmazások** elemre.
2.  Törölje a sort, amely megfelel az eszköznek, amelynek a hozzáférését el szeretné távolítani. Ne felejtse el az eltávolított eszközhöz használt **ügyfél-azonosítót**, mert később szüksége lesz rá.
3.  Jelentkezzen be az Azure portálon: <https://portal.azure.com>.
4.  Kattintson az **Active Directory** ikonra a bal oldali menüben, és ellenőrizze, hogy a megfelelő könyvtárban van-e.
5.  A listában kattintson az **Alkalmazásregisztrációk** elemre, majd kattintson a konfigurálni kívánt alkalmazásra. Megjelenik a **Beállítások** oldal a konfigurációs adatokkal.
6.  Győződjön meg arról, hogy az alkalmazás **Ügyfél-azonosítója** ugyanaz, mint a 2. lépésben volt.
7.  Kattintson a felső panel **Törlés** gombjára.
8.  A megerősítő üzeneten kattintson az **Igen** gombra.
