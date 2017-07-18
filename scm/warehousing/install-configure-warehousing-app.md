---
title: "A Microsoft Dynamics 365 for Finance and Operations &#8211; Warehousing telepítése és konfigurálása"
description: "Ez a témakör ismerteti, hogyan telepítse és konfigurálja a Microsoft Dynamics 365 for Finance and Operations - Warehousing alkalmazást."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SysAADClientTable, WHSMobileAppField, WHSMobileAppFieldPriority, WHSRFMenu, WHSRFMenuItem, WHSWorker
audience: Application User, IT Pro
ms.reviewer: yuyus
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 267694
ms.assetid: d95d43b2-13ff-4189-a71a-3a1fb57d55ed
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mafoge
ms.search.validFrom: 2016-11-30T00:00:00.000Z
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: 9262dcaa3b326d8c31b7d7416b102920795da94b
ms.openlocfilehash: 2e6b0fb81396eef945dbce3be8aee17c9fd455bc
ms.contentlocale: hu-hu
ms.lasthandoff: 06/13/2017

---

# <a name="install-and-configure-microsoft-dynamics-365-for-finance-and-operations-8211-warehousing"></a>A Microsoft Dynamics 365 for Finance and Operations &#8211; Warehousing telepítése és konfigurálása

[!include[banner](../includes/banner.md)]


Ez a témakör ismerteti, hogyan telepítse és konfigurálja a Microsoft Dynamics 365 for Finance and Operations - Warehousing alkalmazást.

A Finance and Operations - Warehousing a Google Play Áruházban és a Windows Áruházban elérhető alkalmazás. A Finance and Operations alkalmazás különálló összetevőként érhető el, ami azt jelenti, hogy raktári feladatokhoz eszközökre önállóan telepíthető. Az alkalmazás a Finance and Operations környezetben való használatához minden eszközre le kell tölteni az alkalmazást, konfigurálni kell a Finance and Operations környezethez való kapcsolódáshoz. Ez a témakör ismerteti az alkalmazás eszközökre telepítésének módját. Azt is bemutatja, hogyan konfigurálhatja az alkalmazást a Finance and Operations környezethez való csatlakozáshoz.

## <a name="prerequisites"></a>Előfeltételek
Az alkalmazás Android és Windows operációs rendszereken érhető el. Az alkalmazás használatához rendelkeznie kell az eszközökre telepített alábbi támogatott operációs rendszerek egyikével. Emellett rendelkeznie kell a Finance and Operations következő támogatott verzióinak valamelyikével. A következő táblázatban található információk segítségével értékelje, hogy a hardver- és szoftverkörnyezetbe készen áll-e a telepítés támogatására.

| Platform                    | Verzió                                                                                                                                                                     |
|-----------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Android                     | 4.4, 5.0, 6.0                                                                                                                                                               |
| Windows (UWP)               | Windows 10 (összes verzió)                                                                                                                                                   |
| Finance and Operations | Microsoft Finance and Operations 1611-es verzió <br>– vagy – <br>Microsoft Dynamics Dynamics AX 7.0/7.0.1 verziója és a Microsoft Dynamics AX platform 2. frissítése a KB 3210014 gyorsjavítással |

## <a name="get-the-app"></a>Az alkalmazás beszerzése
-   Windows (UWP): [Finance and Operations - Warehousing a Windows Áruházban](https://www.microsoft.com/store/apps/9p1bffd5tstm)
-   Android:
    - [Finance and Operations - Warehousing a Google Play Áruházban](https://play.google.com/store/apps/details?id=com.Microsoft.Dynamics365forOperationsWarehousing)
    - [Finance and Operations - Warehousing a Zebra AppGalleryben](https://appgallery.zebra.com/showcase/apps/146?type=showcase)

## <a name="create-a-web-service-application-in-active-directory"></a>Webszolgáltatási alkalmazás létrehozása az Active Directoryban
Ahhoz, hogy az alkalmazás együttműködhessen a kívánt Finance and Operations kiszolgálóval, regisztrálnia kell egy webszolgáltatási alkalmazást az Azure Active Directoryban a Finance and Operations bérlő számára. Biztonsági okokból az összes használt eszköz számára ajánlott létrehozni egy-egy webszolgáltatási alkalmazást. Webszolgáltatási alkalmazás létrehozásának lépései az Azure Active Directoryban (Azure AD):

1.  Egy  webböngészőben lépjen a <https://manage.windowsazure.com> oldalra.
2.  Adja meg a felhasználó nevét és jelszavát, aki hozzáfér az Azure-előfizetéshez.
3.  Az Azure-portálon a bal oldali navigációs ablaktáblán kattintson az **Active Directory** elemre.[](./media/wh-01-active-directory-example.png)[![wh-01-active-directory-example](./media/wh-01-active-directory-example.png)](./media/wh-01-active-directory-example.png)
4.  A rácsban válassza a Finance and Operations által használt Active Directory-példányt.
5.  Kattintson a felső eszköztáron az **Alkalmazások** elemre. [![wh-02-active-directory-applications](./media/wh-02-active-directory-applications-1024x197.png)](./media/wh-02-active-directory-applications.png)
6.  Az alsó panelen kattintson a **Hozzáadás** elemre. Az **Alkalmazás hozzáadása** varázsló elindul.
7.  Adjon meg egy nevet az alkalmazásnak, és válassza ki a **Webes alkalmazás és/vagy web API** lehetőséget. [![wh-03-active-directory-add-application](./media/wh-03-active-directory-add-application.png)](./media/wh-03-active-directory-add-application.png)
8.  Adja meg a bejelentkezési URL-címet, amely a webes alkalmazás URL-címe. Az URL-cím megegyezik a telepítés URL-címével, de a végéhez hozzá van adva az oauth. Adja meg az alkalmazásazonosító URI-t: ez az érték kötelező, de nem szükséges a hitelesítéshez. Győződjön meg arról, hogy ez az alkalmazásazonosító URI ál-URI, például https://contosooperations/wmapp, mivel a telepítés URL-címének használata bejelentkezési problémákat okozhat más AAD-alkalmazásokban, például az Excel-bővítményben. [![WH-04-AD-add-properties3](./media/WH-04-AD-add-properties3.png)](./media/WH-04-AD-add-properties3.png)
9.  Lépjen a **Konfigurálás** lapra. [![wh-05-ad-configure-app](./media/wh-05-ad-configure-app.png)](./media/wh-05-ad-configure-app.png)
10. Görgessen lefelé, amíg meg nem jelenik az **Engedélyek más alkalmazások számára** szakasz. Kattintson az **Alkalmazás hozzáadása** lehetőségre. [![wh-06-ad-app-add-permissions](./media/wh-06-ad-app-add-permissions.png)](./media/wh-06-ad-app-add-permissions.png)
11. Válassza ki a **Microsoft Dynamics ERP** elemet a listában. Kattintson a lap jobb felső sarkában látható **Teljesség ellenőrzése** gombra. [![wh-07-ad-select-permissions](./media/wh-07-ad-select-permissions.png)](./media/wh-07-ad-select-permissions.png)
12. Az **Engedélyek delegálása** listában jelölje be az összes jelölőnégyzetet. Kattintson a **Mentés** gombra. [![wh-08-ad-delegate-permissions](./media/wh-08-ad-delegate-permissions.png)](./media/wh-08-ad-delegate-permissions.png)
13. Jegyezze fel a következő információkat:
    -   **Ügyfél-azonosító** - a lapon legörgetve megjelenik az **Ügyfél-azonosító**.
    -   **Kulcs** - a **Kulcsok** szakaszban hozzon létre egy kulcsot az időtartam megadásával, majd másolja le a kulcsot. A kulcs neve a továbbiakban: **Titkos ügyfélkód**.

## <a name="create-and-configure-a-user-account-in-finance-and-operations"></a>Felhasználói fiók létrehozása és konfigurálása a Finance and Operationsben
Annak érdekében, hogy a Finance and Operations képes legyen az Azure AD alkalmazás használatára, kövesse az alábbi konfigurációs lépéseket:

1.  Hozzon létre új felhasználói fiókot a Finance and Operations bérlője számára az Azure Active Directoryban. E felhasználói fiók célja a raktáralkalmazás konkrét egyéni szolgáltatásának elérése, amit a Finance and Operations-kiszolgáló tesz lehetővé. Ezen lépés befejeztével rendelkezni fog a WMDP felhasználóhitelesítő adataival, amelyek WMDP e-mail-címből és WMDP-jelszóból állnak. Felhasználók az Azure AD-hez és a Finance and Operationshöz történő hozzáadásának alaplépéseiről a következő oktatóanyagból tájékozódhat: [Finance and for Operations-előfizetés regisztrálása](/dynamics365/unified-operations/dev-itpro/dev-tools/sign-up-preview-subscription).
2.  Hozzon létre egy olyan Finance and Operations-felhasználót, amely megfelel a raktározási alkalmazás felhasználói hitelesítő adatainak.
    1.  A Finance and Operationsben lépjen a **Rendszerfelügyelet** &gt; **Közös** &gt; **Felhasználók** elemre.
    2.  Hozzon létre egy új felhasználót.
    3.  Rendelje hozzá a Warehouse-mobileszköz felhasználóját, amint azt a következő képernyőképen látható. [![wh-09-add-user-security-role](./media/wh-09-add-user-security-role.png)](./media/wh-09-add-user-security-role.png)

3.  Társítsa az Azure Active Directory alkalmazást a raktározási alkalmazás felhasználójával.
    1.  A Finance and Operationsben lépjen a **Rendszerfelügyelet** &gt; **Beállítás** &gt; **Azure Active Directory alkalmazások** elemre.
    2.  Hozzon létre egy új sort.
    3.  Adja meg az (az utolsó szakaszban kapott) **Ügyfél-azonosítót**, adjon neki nevet, és válassza ki a korábban létrehozott felhasználót. Azt javasoljuk, hogy az összes eszközt lássa el címkével, hogy egyszerűen eltávolíthassa hozzáférésüket a Finance and Operationshöz erről az oldalról abban az esetben, ha az eszközök elvesznek. [![wh-10-ad-applications-form](./media/wh-10-ad-applications-form.png)](./media/wh-10-ad-applications-form.png)

## <a name="configure-the-application"></a>Az alkalmazás konfigurálása
Konfigurálnia kell az alkalmazást az eszközön, hogy csatlakozni tudjon a Finance and Operations kiszolgálóhoz Azure AD alkalmazáson keresztül. Ehhez a következő lépéseket kell végrehajtani.

1.  Az alkalmazásban lépjen a **Kapcsolat beállításai** elemre.
2.  Törölje a **Bemutató mód** mezőt. <br>[![wh-11-app-connection-settings-demo-mode](./media/wh-11-app-connection-settings-demo-mode-169x300.png)](./media/wh-11-app-connection-settings-demo-mode.png)
3.  Adja meg a következő adatokat: 
    + **Azure Active Directory ügyfél-azonosító** - Az ügyfél-azonosító beszerzése a 13. „Webszolgáltatási alkalmazás létrehozása az Active Directoryban" című lépésben történik. 
    + **Azure Active Directory titkos ügyfélkód** - A titkos ügyfélkód beszerzése a 13. „Webszolgáltatási alkalmazás létrehozása az Active Directoryban" című lépésben történik. 
    + **Azure Active Directory-erőforrás** - Az Azure Active Directory-erőforrás a Finance and Operations gyökér-URL-jét jeleníti meg. **Megjegyzés:**: ne zárja perjellel (/) ezt a mezőt. 
    + **Azure Active Directory-bérlő** - a Finance and Operations kiszolgálón használt Azure AD Directory-bérlő https://login.windows.net/az-Ön-AD-bérlői-azonosítója. Például: https://login.windows.net/contosooperations.onmicrosoft.com. 
    <br>**Megjegyzés:**: ne zárja perjellel (/) ezt a mezőt. 
    + **Vállalat** - adja meg a Finance and Operationsben szereplő jogi személyt, amelyhez az alkalmazásnak csatlakoznia kell. <br>[![wh-12-app-connection-settings](./media/wh-12-app-connection-settings-169x300.png)](./media/wh-12-app-connection-settings.png)
4.  Válassza a **Vissza** gombot az alkalmazás bal felső sarkában. Az alkalmazás ekkor csatlakozik a Finance and Operations kiszolgálóhoz, és megjelenik a raktári dolgozó bejelentkezési képernyője. <br>[![wh-13-log-in-screen](./media/wh-13-log-in-screen-180x300.png)](./media/wh-13-log-in-screen.png)

## <a name="remove-access-for-a-device"></a>Eszköz hozzáférésének eltávolítása
Abban az esetben, ha egy eszköz elveszett vagy a biztonsága sérült, el kell távolítania az eszköz a Finance and Operationshöz való hozzáférését. Az alábbi lépések leírják a hozzáférés-eltávolítás javasolt eljárását.

1.  A Finance and Operationsben lépjen a **Rendszerfelügyelet** &gt; **Beállítás** &gt; **Azure Active Directory alkalmazások** elemre.
2.  Törölje a sort, amely megfelel az eszköznek, amelynek a hozzáférését el szeretné távolítani. Írja le az eltávolított eszköz által használt **Ügyfél-azonosítót**.
3.  Jelentkezzen be az Azure klasszikus portálon, a <https://manage.windowsazure.com> címen.
4.  Kattintson az **Active Directory** ikonra a bal oldali menüben, majd kattintson a kívánt könyvtárra.
5.  Kattintson a felső menü **Alkalmazások** elemére, majd kattintson a konfigurálni kívánt alkalmazásra. Megjelenik a **Kalauz** oldal az egyszeri bejelentkezési és egyéb konfigurációs adatokkal.
6.  Kattintson a **Konfigurálás** lapra, görgessen le, és győződjön meg róla, hogy az alkalmazás **Ügyfél-azonosítója** megegyezik a jelen szakasz 2. lépésében látottal.
7.  Kattintson az eszköztár **Törlés** gombjára.
8.  A megerősítő üzeneten kattintson az **Igen** gombra.





