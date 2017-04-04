---
title: "Telepítse és konfigurálja a Microsoft Dynamics 365 műveletek & #8211; Raktározás"
description: "Ez a témakör ismerteti, hogyan telepítse és konfigurálja a Microsoft Dynamics 365 raktározás - műveletekhez."
author: YuyuScheller
manager: AnnBe
ms.date: 2017-04-04
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: SysAADClientTable, WHSMobileAppField, WHSMobileAppFieldPriority, WHSRFMenu, WHSRFMenuItem, WHSWorker
audience: Application User, IT Pro
ms.search.scope: Operations, Core
ms.custom: 267694
ms.assetid: d95d43b2-13ff-4189-a71a-3a1fb57d55ed
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mafoge
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: f77012e7b64b7f153103e9bbe91e8ded202b509a
ms.openlocfilehash: 231c087ddc976aa552fc9cd6c89188f82a0247d1
ms.lasthandoff: 03/31/2017


---

# <a name="install-and-configure-microsoft-dynamics-365-for-operations-8211-warehousing"></a>Telepítse és konfigurálja a Microsoft Dynamics 365 műveletek & #8211; Raktározás

Ez a témakör ismerteti, hogyan telepítse és konfigurálja a Microsoft Dynamics 365 raktározás - műveletekhez.

365 Dynamics műveletek - raktározás a Google Play Store és a Windows áruház elérhető alkalmazás. A Microsoft Dynamics 365 műveletekhez aktuális verziójához ez app, ami azt jelenti, a raktári tevékenységek használt eszközök önálló telepítés önálló összetevőként biztosítja. Műveleti környezetben a Dynamics 365 az alkalmazás használatához mindkét eszközön az alkalmazás letöltése és konfigurálja a Dynamics 365 műveletek környezethez való kapcsolódáshoz. Ez a témakör ismerteti az alkalmazás telepíthető az eszközök. Azt is bemutatja, hogyan konfigurálhatja az alkalmazás csatlakozni a Dynamics 365 műveletek környezet.

## <a name="prerequisites"></a>Előfeltételek
Az alkalmazás Android és Windows operációs rendszereken érhető el. Az alkalmazás használatához rendelkeznie kell az eszközökre telepített alábbi támogatott operációs rendszerek egyike. Dynamics 365 műveletek következő támogatott verzióinak valamelyikét is kell. A következő táblázatban található információk segítségével értékeli, ha a hardver és szoftver környezetben támogatja a telepítés készen áll.

| Platform                    | Verzió                                                                                                                                                                     |
|-----------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Android                     | 4.4, 5.0, 6.0                                                                                                                                                               |
| Windows (UWP)               | Windows 10 (összes verzió)                                                                                                                                                   |
| 365 Dynamics műveletek | Microsoft Dynamics 365 a műveletek 1611 – vagy – Microsoft Dynamics Dynamics AX verziója 7.0/7.0.1 és a Microsoft Dynamics AX platform 2 frissítés gyorsjavítás 3210014 KB |

## <a name="get-the-app"></a>Az alkalmazás letöltése
-   Windows (UWP) - [365 Dynamics műveletek - a Windows áruház a raktározás](https://www.microsoft.com/store/apps/9p1bffd5tstm)
-   Android - [365 Dynamics műveletek - a Google Play tároló raktározás](https://play.google.com/store/apps/details?id=com.Microsoft.Dynamics365forOperationsWarehousing)

## <a name="create-a-web-service-application-in-active-directory"></a>Az Active Directory szolgáltatás webalkalmazás létrehozása
Ahhoz, hogy az alkalmazás együttműködhet az egy adott Dynamics 365 műveletek kiszolgáló, regisztrálnia kell egy webes szolgáltatásalkalmazás Azure az Active Directoryban a Dynamics 365 műveletek bérlő számára. Biztonsági okokból ajánlott létrehozni egy webalkalmazás szolgáltatás összes eszköz használata. Azure az Active Directoryban (Azure AD) egy webes alkalmazás létrehozásához kövesse az alábbi lépéseket:

1.  A webböngészőben keressük <https://manage.windowsazure.com>.
2.  Adja meg a felhasználó, aki hozzáfér az Azure előfizetés nevét és jelszavát.
3.  Azure portálon, a bal oldali ablaktáblán kattintson a **az Active Directory**. [](./media/wh-01-active-directory-example.png)[![wh-01-active-directory-példa](./media/wh-01-active-directory-example.png)](./media/wh-01-active-directory-example.png)
4.  A rácsban válassza a műveletek Dynamics 365 által használt Active Directory-példány.
5.  Kattintson a felső eszköztár **alkalmazások**. [![Mi-02-active-directory-alkalmazások](./media/wh-02-active-directory-applications-1024x197.png)](./media/wh-02-active-directory-applications.png)
6.  Az alsó ablaktáblában kattintson a **hozzáadása**. A **-alkalmazás hozzáadása** varázsló elindul.
7.  Adjon meg egy nevet az alkalmazás, és válassza ki a **webes alkalmazás és/vagy web API**. [![Wh-03-Active-Directory-Add-Application](./media/wh-03-active-directory-add-application.png)](./media/wh-03-active-directory-add-application.png)
8.  Adja meg a bejelentkezés URL-CÍMÉT, amely az alkalmazás URL-címe a bérlő a gyökér URL műveletek. Bejelentkezési URL-cím jelenleg nem aktív használatban van a app hitelesítése, de kötelező mező. Azonosító URI Azonosítóját mezőjében adjon meg egy URL-CÍMÉT. [![Mi-04-ad-hozzáadása-tulajdonságok](./media/wh-04-ad-add-properties.png)](./media/wh-04-ad-add-properties.png)
9.  Keresse fel a **konfigurálása** fülre. [![Mi-05-ad-konfigurálása-app](./media/wh-05-ad-configure-app.png)](./media/wh-05-ad-configure-app.png)
10. Görgessen lefelé, amíg meg nem jelenik a **engedélyek más alkalmazások** szakasz. Kattintson a **-alkalmazás hozzáadása**. [![Wh-06-AD-App-Add-permissions](./media/wh-06-ad-app-add-permissions.png)](./media/wh-06-ad-app-add-permissions.png)
11. Válassza ki **a Microsoft Dynamics ERP** a listában. Kattintson a **teljes ellenőrzés** gombra az oldal jobb felső sarkában. [![Mi-07-ad-kijelölés-engedélyek](./media/wh-07-ad-select-permissions.png)](./media/wh-07-ad-select-permissions.png)
12. A a **engedélyek delegálása** listában, jelölje be a jelölőnégyzetet. Click **Save**. [![Mi-08-ad--engedélyek delegálása](./media/wh-08-ad-delegate-permissions.png)](./media/wh-08-ad-delegate-permissions.png)
13. Jegyezze fel a következő információkat:
    -   **Ügyfél-azonosító** görgetésekor az oldal jelenik meg - **ügyfél-azonosító** jelenik meg.
    -   **Kulcs** - a a **kulcsok** szakasz, időtartam megadásával kulcs létrehozása és másolása a kulcs. Ez a kulcs lesz később a továbbiakban: a **ügyfél titkos**.

## <a name="create-and-configure-a-user-account-in-dynamics-365-for-operations"></a>Létrehozhat és konfigurálhat egy felhasználói fiók Dynamics 365 műveletek
Dynamics 365 Azure AD alkalmazás használata műveletek engedélyezéséhez kövesse az alábbi konfigurációs lépéseket kell:

1.  Új felhasználói fiók létrehozása a Dynamics 365 a bérlő műveletek Azure az Active Directoryban. Ez a felhasználói fiók célja a vámraktározási app, amely felfedi a Dynamics 365 műveletek kiszolgáló az adott egyéni szolgáltatás eléréséhez. Ez a lépés befejeztével a WMDP felhasználó hitelesítő adatait, amely áll a WMDP e-mail cím és jelszó WMDP lesz. További információt a felhasználók hozzáadása Azure AD lépéseit és Dynamics 365 műveletekhez, olvassa el a tankönyv: [Regisztráljon a Microsoft Dynamics 365 előfizetés műveletek](/dynamics365/operations/dev-itpro/sign-up-preview-subscription).
2.  Hozzon létre egy Dynamics 365 műveletek felhasználó, amely megfelel a vámraktározási app felhasználói hitelesítő adatokat.
    1.  Műveletek 365 Dynamics, Ugrás **rendszerfelügyelet**&gt;**közös**&gt;**a felhasználók**.
    2.  Hozzon létre egy új felhasználót.
    3.  Rendelje hozzá a raktári mobil eszköz felhasználói, amint azt a következő képernyőkép. [![Wh-09-Add-User-Security-Role](./media/wh-09-add-user-security-role.png)](./media/wh-09-add-user-security-role.png)

3.  A raktározási app felhasználói az Azure Active Directory alkalmazás társítani.
    1.  Műveletek 365 Dynamics, Ugrás **rendszerfelügyelet**&gt;**a telepítő**&gt;**Azure Active Directory alkalmazások**.
    2.  Hozzon létre egy új sort.
    3.  Adja meg a **ügyfél-azonosító** (az utolsó szakaszban kapott), adjunk neki nevet, és jelölje ki a korábban létrehozott felhasználói. Azt javasoljuk, hogy az eszközök címkézése, így egyszerűen eltávolíthatja hozzáférésüket a Dynamics 365 műveletek erről a lapról abban az esetben, ha azok elvesznek. [![Mi-10-ad-alkalmazások-űrlap](./media/wh-10-ad-applications-form.png)](./media/wh-10-ad-applications-form.png)

## <a name="configure-the-application"></a>Az alkalmazás konfigurálása
Konfigurálnia kell az alkalmazás csatlakozni a Dynamics 365 műveletek kiszolgáló Azure AD alkalmazásával az eszközön. Ehhez hajtsa végre a következő lépéseket.

1.  Az alkalmazás az Ugrás **kapcsolat beállításai**.
2.  Egyértelmű a **Demo mód** mezőben. [![Wh-11-App-Connection-Settings-Demo-mode](./media/wh-11-app-connection-settings-demo-mode-169x300.png)](./media/wh-11-app-connection-settings-demo-mode.png)
3.  Adja meg a következő adatokat:- **Azure Active directory ügyfél-azonosító** -az ügyfél-azonosító kapjuk meg a 13 "Az Active Directory szolgáltatás webalkalmazás létrehozása". - **Azure Active directory ügyfél titkos** -az ügyfél titka kapjuk meg a 13 "Az Active Directory szolgáltatás webalkalmazás létrehozása". - **Azure Active directory-erőforráshoz** -Azure az Active directory-erőforráshoz ábrázol a Dynamics 365 műveletek gyökér URL-címhez. **Megjegyzés:**: ne zárja perjellel (/) ezt a mezőt. - **Azure Active directory bérlő** -a Azure Active directory bérlő a Dynamics 365 használt műveletek kiszolgáló: https://login.windows.net/&lt;a-AD-bérlő-ID&gt;. Például: https://login.windows.net/contosooperations.onmicrosoft.com. 
**Megjegyzés:**: ne zárja perjellel (/) ezt a mezőt. - **Vállalat** -adja meg a jogi személy 365 Dynamics műveleteket kíván csatlakozni az alkalmazás. [![Mi-12-app-kapcsolat-beállítások](./media/wh-12-app-connection-settings-169x300.png)](./media/wh-12-app-connection-settings.png)
4.  Válassza ki a **vissza** a bal felső sarkában az alkalmazás gombra. Az alkalmazás a Dynamics 365 műveletek kiszolgálóhoz csatlakozik, és a raktári dolgozó a bejelentkezési képernyő jelenik meg. [![Mi-13-bejelentkezési képernyő](./media/wh-13-log-in-screen-180x300.png)](./media/wh-13-log-in-screen.png)

## <a name="remove-access-for-a-device"></a>Eszköz hozzáférés eltávolítása
Abban az esetben, ha elveszett vagy sérült biztonságú eszközt el kell távolítania a Dynamics 365 hozzáférést az eszközhöz tartozó műveletek. Az alábbi lépések leírják az programokhoz való hozzáférés során.

1.  Műveletek 365 Dynamics, Ugrás **rendszerfelügyelet**&gt;**a telepítő**&gt;**Azure Active Directory alkalmazások**.
2.  Törölje a sort, amely megfelel az eszközre, amelyhez el szeretné távolítani az access. Írja le a **ügyfél-azonosító** az eltávolított eszköz használható.
3.  Jelentkezzen be az Azure klasszikus portálon, a <https://manage.windowsazure.com>.
4.  Kattintson a **az Active Directory** ikonra a bal oldali menüben, majd kattintson a kívánt könyvtárat.
5.  Kattintson a felső menü **alkalmazások**, majd kattintson a konfigurálni kívánt alkalmazás. A **kalauz** az egyszeri bejelentkezés és egyéb konfigurációs adatokat tartalmazó lap jelenik meg.
6.  Kattintson a **konfigurálása** fülre, keresse meg és biztosítása érdekében, hogy a **ügyfél-azonosító** az alkalmazás megegyezik a 2 ebben a szakaszban.
7.  Kattintson a **törlése** a parancssáv gombra.
8.  Kattintson a **Igen** a megerősítést kérő üzenet.



