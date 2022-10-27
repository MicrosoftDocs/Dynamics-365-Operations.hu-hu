---
title: A Warehouse Management mobilalkalmazás telepítése és csatlakoztatása
description: Ez a cikk bemutatja, hogy hogyan lehet telepíteni a Raktárkezelés mobilalkalmazást minden mobileszközre, és konfigurálni azt a Microsoft-környezethez való kapcsolódásra Dynamics 365 Supply Chain Management.
author: Mirzaab
ms.date: 02/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SysAADClientTable, WHSMobileAppField, WHSMobileAppFieldPriority, WHSRFMenu, WHSRFMenuItem, WHSWorker
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.custom: 267694
ms.assetid: d95d43b2-13ff-4189-a71a-3a1fb57d55ed
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mirzaab
ms.search.validFrom: 2021-02-28
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 940a3c1d60347c365575f29b853b83a028acad53
ms.sourcegitcommit: 229ea085cf35579a2631ea1e5fc2c602fa47e3f3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/24/2022
ms.locfileid: "9714762"
---
# <a name="install-and-connect-the-warehouse-management-mobile-app"></a>A Warehouse Management mobilalkalmazás telepítése és csatlakoztatása

[!include [banner](../includes/banner.md)]

Ez a cikk bemutatja, hogy hogyan lehet letölteni és telepíteni az egyes mobileszközre a Raktárkezelés mobilalkalmazást, és hogyan kell konfigurálni az alkalmazást az Ellátásilánc-kezelési környezethez való kapcsolódáshoz. Az egyes eszközöket manuálisan is konfigurálhatja, illetve a csatlakozási beállításokat egy fájlként vagy egy QR-kód beolvasásával is importálhatja.

## <a name="system-requirements"></a>Rendszerkövetelmények

A Raktárkezelés mobilalkalmazás Windows és Google Android operációs rendszereken érhető el. Az alkalmazás használatához rendelkeznie kell a mobileszközökre telepített alábbi támogatott operációs rendszerek egyikével:

- Windows 10 (Univerzális Windows-platform \[UWP\]) 2018. októberi frissítés, 1809 (10.0.17763-as build) vagy újabb
- Android 4.4 vagy újabb

## <a name="turn-warehouse-management-mobile-app-features-on-or-off-in-supply-chain-management"></a>A Raktárkezelés mobilalkalmazás funkcióinak be- és kikapcsolása az Ellátásilánc-kezelés eszközben

A Raktárkezelés mobilalkalmazás használatához az új raktári alkalmazás funkció felhasználói beállításait, *ikonjait* és lépéscímeit be kell kapcsolva a rendszerben. A 10.0.25-ös ellátásilánc-kezelésben ez a funkció kötelező, és nem lehet kikapcsolni. Ha 10,0,25-ösnél régebbi verziót futtat, *akkor a rendszergazdák a Funkciókezelés munkaterület új raktári alkalmazás funkciójának Felhasználói beállításai,*[ikonjai](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) és lépéscímei alapján kapcsolhatják be és kapcsolhat ki a funkciót.

## <a name="get-the-warehouse-management-mobile-app"></a>A Raktárkezelés mobilalkalmazás beszerzése

Kisebb telepítések esetén előfordulhat, hogy az alkalmazást jellemzően minden eszköz megfelelő áruházából telepíti, majd manuálisan konfigurálja a kapcsolatot az éppen használt környezettel.

Nagyobb telepítések esetén automatizálhatja az alkalmazástelepítést és/vagy -konfigurációt, ami több eszköz kezelése esetén kényelmesebb lehet. Használhat például egy olyan mobileszköz-kezelési és mobilalkalmazás-kezelési megoldást, mint például a [Microsoft Intune](/mem/intune/fundamentals/what-is-intune). Az alkalmazások Intune használatával történő hozzáadásával kapcsolatos tudnivalókat lásd: [Alkalmazások hozzáadása a Microsoft Intune szolgáltatáshoz](/mem/intune/apps/apps-add).

### <a name="install-the-app-from-an-app-store"></a>Az alkalmazás telepítése egy alkalmazás-áruházból

Az alkalmazás egyetlen eszközre való telepítésének legegyszerűbb módja az, ha egy alkalmazás-áruházból telepíti az alkalmazást, amely mindig a legfrissebb, általánosan elérhető verziót szolgáltatja. A Microsoft Intune alkalmazásokat is be tud szerezni az alkalmazás-áruházakból. A következő hivatkozások valamelyikével telepítheti az alkalmazást egy alkalmazás-áruházból:

- **Windows (UWP):** [Raktárkezelés a Microsoft Store áruházban](https://www.microsoft.com/store/apps/9pd35cdqcmg3)

- **Android:** [Raktárkezelés a Google Play Áruházban](https://play.google.com/store/apps/details?id=com.Microsoft.WarehouseManagement)

### <a name="download-the-app-from-microsoft-app-center"></a>Az alkalmazás letöltése a Microsoft App Center alkalmazásból

Ahelyett, hogy egy alkalmazás-áruházból telepít, letöltheti az alkalmazást a Microsoft App Center alkalmazásból. Az App Center olyan telepíthető csomagokat biztosít, amelyek áttöltésre használhatók. Az App Center a jelenlegi verzión kívül lehetővé teszi a korábbi verziók letöltését is, és emellett olyan előzetes verziókat is tartalmaz, amelyekben közelgő funkciók is elérhetőek. A Raktárkezelés mobilalkalmazás jelenlegi, korábbi vagy előzetes verzióinak a Microsoft App Center alkalmazásból való letöltéséhez használja a következő hivatkozásokat:

- **Windows (UWP):** [Raktárkezelés (Windows)](https://go.microsoft.com/fwlink/?linkid=2154406)  
    A letöltött csomagok Windows-eszközre történő telepítéséről, majd a szükséges tanúsítványok beállításáról lásd: [Build telepítése az App Center alkalmazásból](/appcenter/distribution/installation).

- **Android:** [Raktárkezelés (Android)](https://go.microsoft.com/fwlink/?linkid=2154613)  
    Ha egy előzetes verziót tölt le, néhány további lépés szükséges a telepítéshez. A részleteket lásd: [Android-alkalmazások tesztelése](/appcenter/distribution/testers/testing-android).

Az Alkalmazásközpontból letöltött build telepítésével kapcsolatos tudnivalókat [lásd: Build telepítése](/appcenter/distribution/installation).

## <a name="create-a-web-service-application-in-azure-active-directory"></a><a name="create-service"></a>Webes szolgáltatás alkalmazás létrehozása az Azure Active Directory szolgáltatásban

Ahhoz, hogy a Raktárkezelés mobilalkalmazás együttműködhessen a kívánt Supply Chain Management kiszolgálóval, regisztrálnia kell egy webszolgáltatási alkalmazást az Azure Active Directory (Azure AD) felületén a Supply Chain Management bérlő számára. A következő eljárás bemutatja a feladat végrehajtásának egyik módját. A részletes tudnivalókkal és alternatívákkal kapcsolatban lásd az eljárás utáni hivatkozásokat.

1. Lépjen egy böngészőben a [https://portal.azure.com](https://portal.azure.com/) címre.
1. Adja meg a felhasználó nevét és jelszavát, aki hozzáfér az Azure-előfizetéshez.
1. Az Azure portálon a bal oldali navigációs panelen válassza az **Azure Active Directory** lehetőséget.

    ![Azure Active Directory.](media/app-connect-azure-aad.png "Azure Active Directory")

1. Győződjön meg róla, hogy az Azure AD Supply Chain Management által használt példányával dolgozik.
1. A **Kezelés** listában válassza az **Alkalmazásregisztrációk** elemet.

    ![Alkalmazásregisztrációk.](media/app-connect-azure-register.png "Alkalmazásregisztrációk")

1. Az eszköztáron válassza az **Új regisztráció** parancsot az **Alkalmazás regisztrálása** varázsló megnyitásához.
1. Írjon be egy nevet az alkalmazás számára, válassza a **Számlák csak ebben a szervezeti könyvtárban** lehetőséget, majd válassza a **Regisztráció** lehetőséget.

    ![Alkalmazás regisztrálása varázsló.](media/app-connect-azure-register-wizard.png "Alkalmazás regisztrálása varázsló")

1. Megnyílik az új alkalmazás regisztrációja. Jegyezze fel az **Alkalmazás (ügyfél) azonosító** értékét, mert később szüksége lesz rá. Erre az azonosítóra a cikk később ügyfélazonosítóként *hivatkozik*.

    ![Alkalmazás (ügyfél) azonosítója.](media/app-connect-azure-app-id.png "Alkalmazás (ügyfél) azonosítója")

1. Válassza a **Tanúsítvány és titkok** lehetőséget a **Kezelés** listában. Ezt követően válassza ki a következő gombok egyikét, attól függően, hogy hogyan szeretné konfigurálni az alkalmazást hitelesítésre. (További tájékoztatás: [Hitelesítés tanúsítvány vagy ügyfél titkos szakaszának használatával](#authenticate) a cikk későbbi részében.)

    - **Tanúsítvány feltöltése** – A titkos kódként használt tanúsítvány feltöltése. Ezt a megközelítést ajánljuk, mert a biztonságosabb, és nagyobb mértékben automatizálható is. Ha Windows-eszközökön futtatja a Raktárkezelés mobilalkalmazást, jegyezze fel a tanúsítvány feltöltése után megjelenő **Ujjlenyomat** értéket. Erre az értékre akkor lesz szükségem amikor Windows-eszközökön konfigurálja a tanúsítványt.
    - **Új titkos ügyfélkód** – Hozzon létre egy kulcsot a kulcs leírásának és időtartamának megadásával a **Jelszavak** részben, majd válassza a **Hozzáadás** elemet. Készítsen másolatot a kulcsról, és tárolja biztonságosan.

    ![Tanúsítvány és titkos kódok.](media/app-connect-azure-authentication.png "Tanúsítvány és titkos kódok")

Az Azure AD webszolgáltatási alkalmazásainak beállításával kapcsolatos további tudnivalókat lásd a következő forrásokban:

- A webszolgáltatási alkalmazások Windows PowerShell eszközzel, az Azure AD rendszerben történő beállításával kapcsolatban a következő témakör tartalmaz további tájékoztatást: [Útmutató: Az Azure PowerShell használata egy tanúsítvánnyal rendelkező szolgáltatási főkiszolgáló létrehozásához](/azure/active-directory/develop/howto-authenticate-service-principal-powershell).
- A webszolgáltatás-alkalmazások kézi létrehozásáról a Azure AD következő cikkekben olvashat részletesen:

    - [Rövid útmutató: Alkalmazások regisztrálása a Microsoft Identity platformmal](/azure/active-directory/develop/quickstart-register-app)
    - [Útmutató: Erőforrások elérésére képes Azure AD alkalmazás és szolgáltatási főkiszolgáló létrehozása portál használatával](/azure/active-directory/develop/howto-create-service-principal-portal)

## <a name="create-and-configure-a-user-account-in-supply-chain-management"></a><a name="user-azure-ad"></a>Felhasználói fiók létrehozása és konfigurálása a Supply Chain Management megoldásban

A következő lépésekkel engedélyezheti az Supply Chain Management számára az Azure AD alkalmazása használatát.

1. Hozzon létre egy olyan felhasználót, amely megfelel a Raktárkezelés mobilalkalmazás felhasználói hitelesítő adatainak:

    1. A Supply Chain Management szolgáltatásban lépjen a **Rendszerfelügyelet \> Felhasználók \> Felhasználók** elemre.
    1. Hozzon létre egy felhasználót.
    1. Rendelje hozzá a *Raktározási mobileszköz felhasználója* szerepkört a felhasználóhoz.

    ![Rendelje hozzá a raktározási mobileszköz felhasználóját.](media/app-connect-app-users.png "Rendelje hozzá a raktározási mobileszköz felhasználóját")

1. Társítsa az Azure AD alkalmazást a Raktárkezelés mobilalkalmazás felhasználójával:

    1. Ugrás a **Rendszerfelügyelet \> Beállítás \> Azure Active Directory alkalmazások** elemre.
    1. Jelölje be a műveleti ablakban az **Új** lehetőséget az új sor létrehozásához.
    1. Az **Ügyfélazonosító** mezőben adja meg azt az ügyfélazonosítót amelyet feljegyzett az előző szakaszban.
    1. A **Név** mezőben adjon meg egy nevet.
    1. Válassza ki az újonnan létrehozott felhasználói azonosítót a **Felhasználói azonosító** mezőben.

    ![Azure Active Directory alkalmazások.](media/app-connect-aad-apps.png "Azure Active Directory alkalmazások")

> [!TIP]
> Ezeknek a beállításoknak a használatának az egyik módja az, hogy létrehoz egy ügyfélazonosítót az Azure szolgáltatásban minden egyes fizikai eszközhöz, majd hozzáadja az egyes ügyfélazonosítókat az **Azure Active Directory alkalmazások** oldalhoz. Ezt követően, ha elveszik egy eszköz, egyszerűen eltávolíthatja a Supply Chain Management alkalmazáshoz való hozzáférést, ha eltávolítja az ügyfélazonosítóját ezen az oldalon. (Ez a megközelítés működik, mert az egyes eszközökre mentett kapcsolati hitelesítő adatok szintén meghatároznak egy ügyfélazonosítót, amint azt a jelen cikk későbbi leírása ismerteti.)
>
> Ezenkívül az egyes ügyfélazonosítók alapértelmezett nyelv-, számformátum- és időzóna-beállításait az itt beállított **Felhasználói azonosítóhoz** beállított beállítások határozzák meg. Tehát ezeket a beállításokat használhatja az egyes eszközök vagy eszközgyűjtemények alapértelmezett beállításainak létrehozására, az ügyfélazonosító alapján. Ezeket az alapértelmezett beállításokat azonban felülbírálja a rendszer, ha azok a *raktári alkalmazás felhasználói fiókjához* is be vannak állítva, amelyről a dolgozó bejelentkezik az eszközre. (További tudnivalókat lásd: [Mobileszközök felhasználói azonosítói](mobile-device-work-users.md).)

## <a name="authenticate-by-using-a-certificate-or-client-secret"></a><a name="authenticate"></a>Hitelesítés tanúsítványok vagy titkos ügyfélkód használatával

Az Azure AD használatával történő hitelesítéssel biztonságos módon csatlakoztathat egy mobileszközt a Supply Chain Management alkalmazsáshoz. A hitelesítést elvégezheti titkos ügyfélkód vagy tanúsítványok használatával. Ha a csatlakozási beállításokat importálja, javasoljuk, hogy a titkos ügyfélkód helyett helyett használjon tanúsítványt. Mivel az ügyfél titkos adatát mindig biztonságosan kell tárolni, nem importálható kapcsolatbeállítási fájlból vagy QR-kódból, mint azt a jelen cikk későbbi leírása ismerteti.

A tanúsítványok felhasználhatók titkos kódokként az alkalmazás azonosságának igazolására, ha a rendszer tokent kér. A tanúsítvány nyilvános része fel van töltve az alkalmazásregisztrációba az Azure portálon, míg a teljes tanúsítványt telepíteni kell minden olyan eszközre, amelyre a Raktárkezelés mobilalkalmazás telepítésre kerül. A szervezet felelős a tanúsítvány rotációjának és egyéb szempontjainak kezelésével kapcsolatban. Önaláírt tanúsítványok is használhatók, de mindig nem exportálható tanúsítványokat kell használnia.

A tanúsítványt helyileg elérhetővé kell tenni minden olyan eszközön, amelyen a Raktárkezelés mobilalkalmazást futtatja. A Intune által vezérelt eszközök tanúsítványainak kezelésével kapcsolatban a következő témakör tartalmaz további tájékoztatást: [Tanúsítványok használata hitelesítéshez a Microsoft Intune szolgáltatásban](/mem/intune/protect/certificates-configure).

## <a name="configure-the-warehouse-management-mobile-app-for-cloud-and-edge-scale-units"></a>A Warehouse Management mobilalkalmazás konfigurálása felhőalapú és peremhálózat-léptékű egységekhez

További lépések szükségesek, ha azt tervezi, hogy a Raktárkezelés mobilalkalmazást egy felhőhöz vagy peremhálózati egységhez futtatja. Az utasításokat lásd [a Raktárkezelés mobilalkalmazás konfigurálása a felhő- és szélskálaegységekhez](../cloud-edge/cloud-edge-workload-setup-warehouse-app.md).

## <a name="configure-the-application-by-importing-connection-settings"></a>Az alkalmazás konfigurálása a kapcsolati beállítások importálásával

Annak érdekében, hogy az alkalmazások könnyebben karbantarthatók és telepíthetők legyenek számos mobileszközön, a csatlakozási beállításokat importálhatja az egyes eszközökbe történő kézi beírás helyett. Ez a szakasz bemutatja, hogyan lehet létrehozni és importálni a beállításokat.

### <a name="create-a-connection-settings-file-or-qr-code"></a>Kapcsolatbeállítási fájl vagy QR-kód létrehozása

A csatlakozási beállításokat egy fájlból vagy egy QR-kódból is importálhatja. Mindkét módszernél létre kell hoznia egy olyan beállításfájlt, amely JSON (JavaScript Object Notation) formátumot és szintaxist használ. A fájlnak tartalmaznia kell egy olyan kapcsolatlistát, amely tartalmazza a hozzáadandó egyéni kapcsolatokat. A következő táblázat összegzi azokat a paramétereket, amelyeket meg kell adnia a kapcsolatbeállítási fájlhoz.

| Paraméter | Leírás |
|---|---|
| ConnectionName | Adja meg a csatlakozási beállítás nevét. A maximális hossz 20 karakter. Mivel ez az érték egy csatlakozási beállítás egyedi azonosítója, győződjön meg arról, hogy egyedi a listán. Ha már létezik ilyen nevű kapcsolat az eszközön, akkor az importált fájl beállításai felülbírálják. |
| ActiveDirectoryClientAppId | Adja meg az ügyfélazonosítót, amelyet az Azure AD beállítása közben jegyzett fel a [Webszolgáltatási alkalmazás létrehozása az Azure Active Directory rendszerben](#create-service) szakaszban. |
| ActiveDirectoryResource | Adja meg a Supply Chain Management gyökér-URL-címét. |
| ActiveDirectoryTenant | Adja meg a Azure AD tartománynevet, amelyet a Supply Chain Management kiszolgálóval használ. Ez az érték a `https://login.windows.net/<your-Azure-AD-domain-name>` formátummal rendelkezik. Íme egy példa: `https://login.windows.net/contosooperations.onmicrosoft.com`. A Azure AD tartománynév megkeresésével kapcsolatos további információkért lásd: [Fontos azonosítók keresése egy felhasználóhoz](/partner-center/find-ids-and-domain-names). |
| Cég | Adja meg a Supply Chain Managementben szereplő jogi személyt, amelyhez az alkalmazásnak csatlakoznia kell. |
| ConnectionType | (választható) Adja meg, hogy a kapcsolatbeállításnak tanúsítvány vagy titkos ügyfélkód használatával kell-e kapcsolódnia egy környezethez. Az érvényes értékek: *"certificate"* és *"clientsecret"*. Az alapértelmezett érték a *"certificate"*.<p>**Megjegyzés:** A titkos ügyfélkódok nem importálhatók.</p> |
| IsEditable | (választható) Adja meg, hogy az alkalmazás felhasználója szerkesztheti-e a kapcsolatbeállítást. Az érvényes értékek az *"igaz"* és a *"hamis"*. Az alapértelmezett érték az *"igaz"*. |
| IsDefault | (választható) Adja meg, hogy a kapcsolat az alapértelmezett kapcsolat-e. Az alapértelmezett kapcsolatként beállított kapcsolatot a program automatikusan előre kiválasztja az alkalmazás megnyitásakor. Csak egy kapcsolat állítható be alapértelmezett kapcsolatként. Az érvényes értékek az *"igaz"* és a *"hamis"*. Az alapértelmezett érték a *"hamis"*. |
| CertificateThumbprint | (választható) Windows-eszközök esetében meg lehet adni a kapcsolathoz tartozó tanúsítvány ujjlenyomatát. Az Android-eszközök esetében az alkalmazás felhasználójának ki kell választania a tanúsítványt, amikor első alkalommal használja a kapcsolatot. |

A következő példa egy érvényes kapcsolatbeállítási fájlt mutat be, amely két kapcsolatot tartalmaz. Látható, hogy a kapcsolatlista (a fájlban *"ConnectionList"* névvel) egy olyan objektum, amelynek tömbje minden kapcsolatot objektumként tárol. Minden objektumot kapcsos zárójelbe ({}) kell tenni, vesszővel kell elválasztani, és a tömböt szögletes zárójelbe (\[\]) kell foglalni.

```json
{
    "ConnectionList": [
        {
            "ActiveDirectoryClientAppId":"aaaaaaaa-bbbb-ccccc-dddd-eeeeeeeeeeee",
            "ConnectionName": "Connection1",
            "ActiveDirectoryResource": "https://yourenvironment.cloudax.dynamics.com",
            "ActiveDirectoryTenant": "https://login.windows.net/contosooperations.onmicrosoft.com",
            "Company": "USMF",
            "IsEditable": false,
            "IsDefaultConnection": true,
            "CertificateThumbprint": "aaaabbbbcccccdddddeeeeefffffggggghhhhiiiii",
            "ConnectionType": "certificate"
        },
        {
            "ActiveDirectoryClientAppId":"aaaaaaaa-bbbb-ccccc-dddd-eeeeeeeeeeee",
            "ConnectionName": "Connection2",
            "ActiveDirectoryResource": "https://yourenvironment2.cloudax.dynamics.com",
            "ActiveDirectoryTenant": "https://login.windows.net/contosooperations.onmicrosoft.com",
            "Company": "USMF",
            "IsEditable": true,
            "IsDefaultConnection": false,
            "ConnectionType": "clientsecret"
        }
    ]
}
```

Az adatokat JSON-fájlként mentheti, vagy generálhat egy olyan QR-kódot, amelynek ugyanaz a tartalma. Ha az információt fájlként menti, azt ajánljuk, hogy az alapértelmezett *connections.json* nevet használja, különösen akkor, ha az alapértelmezett helyen fogja tárolni mindegyik mobileszköz esetében.

### <a name="save-the-connection-settings-file-on-each-device"></a>A kapcsolatbeállítási fájl mentése mindegyik eszközre

Általában egy eszközkezelő eszközzel vagy parancsfájllal terjesztheti a kapcsolati beállítások fájljait mindegyik éppen kezelt eszközre. Ha az alapértelmezett nevet és helyet használja a kapcsolatbeállításokat tartalmazó fájl mentésekor az egyes eszközökön, akkor a program automatikusan importálja azt, még a Raktárkezelés mobilalkalmazás telepítése utáni első futtatásakor is. Ha egyéni nevet vagy helyet ad meg a fájlnak, az alkalmazás felhasználójának meg kell adnia az értékeket az első futtatásakor. Az alkalmazás azonban továbbra is a megadott nevet és helyet fogja használni.

Az alkalmazás minden elindításakor újraimportálja a kapcsolatbeállításokat a korábbi helyről, és meghatározza, hogy vannak-e módosítások. Az alkalmazás csak azokat a kapcsolatokat fogja frissíteni, amelyeknek ugyanaz a neve, mint a kapcsolatbeállítási fájljához tartozó kapcsolatoknak. A felhasználó által létrehozott, más neveket használó kapcsolatok nem frissülnek.

Kapcsolatot nem lehet eltávolítani a kapcsolatbeállítások fájljával.

A fentiek szerint az alapértelmezett fájlnév a *connections.json*. A fájl alapértelmezett helye attól függ, hogy Windows-eszközt vagy Android-eszközt használ:

- **Windows:** `C:\Users\<User>\AppData\Local\Packages\Microsoft.WarehouseManagement_8wekyb3d8bbwe\LocalState`
- **Android:** `Android\data\com.Microsoft.WarehouseManagement\files`

Általában az útvonalak automatikusan létrejönnek az alkalmazás első futtatása után. Ezeket a beállításokat azonban manuálisan is létrehozhatja, ha a telepítés előtt át kell vinnie az eszközre a kapcsolatbeállításokat tartalmazó fájlt.

> [!NOTE]
> Ha eltávolítja az alkalmazást, akkor az alapértelmezett elérési út és annak tartalma törlődik.

### <a name="import-the-connection-settings"></a>A kapcsolat beállításainak importálása

Kövesse az alábbi lépéseket a csatlakozási beállítások egy fájlból vagy egy QR-kódból történő importálásához.

1. Indítsa el a Raktárkezelés mobilalkalmazást a mobileszközén. Az alkalmazás első elindításkor egy üdvözlő üzenet jelenik meg. Válassza a **Kapcsolat kiválasztása** lehetőséget.

    ![Üdvözlő üzenet.](media/app-configure-welcome-screen.png "Üdvözlő üzenet")

1. Ha egy fájlból importálja a kapcsolatbeállításokat, előfordulhat, hogy az alkalmazás már megtalálta a fájlt, ha a mentéskor az alapértelmezett név és az alapértelmezett hely került felhasználásra. Ebben az esetben ugorjon előre a 4. lépésre. Ellenkező esetben válassza a **Kapcsolat beállítása** lehetőséget, majd folytassa a 3. lépéssel.

    ![Kapcsolat beállítása.](media/app-configure-set-up-connection.png "Kapcsolat beállítása")

1. A **Kapcsolat beállítása** párbeszédpanelen válassza a **Hozzáadás fájlból** vagy **Hozzáadás QR-kódból** lehetőséget attól függően, hogy hogyan szeretné importálni a beállításokat:

    - Ha egy fájlból importálja a kapcsolati beállításokat, válassza a **Hozzáadás fájlból** lehetőséget, tallózással keresse meg a helyi eszközön található fájlt, és válassza ki. Ha kiválaszt egy egyéni helyet, akkor az alkalmazás tárolja és automatikusan felhasználja a következő alkalommal.
    - Ha QR-kód beolvasásával importálja a kapcsolatbeállításokat, válassza a **Hozzáadás QR-kódból** parancsot. A program engedélyt kér az eszköz kamerájának használatára. Miután megadta az engedélyt, a kamera elindul, így használható a szkenneléshez. Az eszköz kamerájának minőségétől és a QR-kód bonyolultságától függően előfordulhat, hogy nehéz megfelelően beolvasni. Ebben az esetben próbálja meg csökkenteni a QR-kód bonyolultságát úgy, hogy csak egy kapcsolatot generál QR-kódonként. (Jelenleg csak az eszköz kamerája használható a QR-kód beolvasására.)

    ![Kapcsolat beállítása menü.](media/app-configure-connection-setup-flyout.png "Kapcsolat beállítása menü")

1. Ha sikeresen betöltődnek a kapcsolati beállítások, megjelenik a kiválasztott kapcsolat.

    ![Kapcsolatbeállítások betöltve.](media/app-configure-select-connection.png "Kapcsolatbeállítások betöltve")

1. Ha Android-eszközt használ, és tanúsítványt használ a hitelesítéshez, az eszköz rákérdez a tanúsítvány kiválasztására.

    ![Tanúsítvány választására szolgáló kérés egy Android-eszközön.](media/app-configure-select-certificate.png "Tanúsítvány választására szolgáló kérés egy Android-eszközön")

1. Az alkalmazás összekapcsolja a Supply Chain Management-szerverrel, és a bejelentkezési oldalt jeleníti meg.

    ![Bejelentkezési oldal.](media/app-configure-sign-in-page.png "Bejelentkezési oldal")

## <a name="manually-configure-the-application"></a><a name="config-manually"></a>Az alkalmazás manuális konfigurálása

Ha nem rendelkezik fájllal vagy QR-kóddal, manuálisan konfigurálhatja az alkalmazást az eszközön, hogy csatlakozni tudjon a Supply Chain Management-kiszolgálóhoz Azure AD alkalmazáson keresztül.

1. Indítsa el a Raktárkezelés mobilalkalmazást a mobileszközén.
1. Ha az alkalmazást **Bemutató mód** üzemmódban indította el, válassza a **Kapcsolati beállítások** lehetőséget. Ha a **Bejelentkezés** oldal megjelenik az alkalmazás elindításakor, válassza a **Kapcsolat módosítása** lehetőséget.
1. Válassza ki az **Új kapcsolat beállítása** lehetőséget.

    ![Kapcsolat beállítása.](media/app-configure-set-up-connection.png "Kapcsolat beállítása")

1. Válassza ki a **Manuális bevitel** lehetőséget.

    ![Kapcsolat beállítása menü.](media/app-configure-connection-setup-flyout.png "Kapcsolat beállítása menü")

    Megjelenik az **Új kapcsolat** oldal, és megjeleníti a kapcsolati adatok manuális megadásához szükséges beállításokat.

    ![Manuális kapcsolati mezők.](media/app-configure-input-manually.png "Manuális kapcsolati mezők")

1. Adja meg a következő adatokat:

    - **Titkos ügyfélkód használata** – Adja meg ezt a beállítást _Igen_ értékkel titkos ügyfélkóddal történő hitelesítéshez a Supply Chain Management alkalmazásban. Állítsa _Nem_ értékre, ha tanúsítványt kíván használni a hitelesítéshez. (További tájékoztatás: [Hozzon létre egy webszolgáltatás alkalmazást Azure Active Directory](#create-service) a cikk korábbi szakaszában.)
    - **Kapcsolat neve** – Adjon nevet az új kapcsolatnak. Ez a név fog megjelenni a **Kapcsolat kiválasztása** mezőben, amikor legközelebb megnyitja a kapcsolatbeállításokat. A megadott névnek egyedinek kell lennie. (Más szóval különböznie kell az eszközön tárolt összes egyéb kapcsolatnévtől, ha más kapcsolatneveket is tárol ott.)
    - **Active directory ügyfélazonosító** – Adja meg az ügyfélazonosítót, amelyet az Azure AD beállítása közben jegyzett fel a [Webszolgáltatási alkalmazás létrehozása az Azure Active Directory rendszerben](#create-service) szakaszban.
    - **Active Directory titkos ügyfélkódja** – Ez a mező csak akkor érhető el, ha a **Titkos ügyfélkód használata** beállítás értéke _Igen_. Adja meg a titkos ügyfélkódot, amelyet az Azure AD beállítása közben jegyzett fel a [Webszolgáltatási alkalmazás létrehozása az Azure Active Directory rendszerben](#create-service) szakaszban.
    - **Active Directory tanúsítvány ujjlenyomata** – Ez a mező csak Windows-eszközökön érhető el, és csak akkor, ha a **Titkos ügyfélkód használata** beállítás értéke _Nem_. Adja meg a tanúsítvány ujjlenyomatát, amelyet az Azure AD beállítása közben jegyzett fel a [Webszolgáltatási alkalmazás létrehozása az Azure Active Directory rendszerben](#create-service) szakaszban.
    - **Active Directory-erőforrás** – Adja meg a Supply Chain Management gyökér URL-jét.

        > [!IMPORTANT]
        > Ne fejezze be ezt az értéket perjellel (/).
        > Győződjön meg róla, hogy a HTTPS (SSL) tanúsítvány érvényes.

    - **Active directory bérlő** - Adja meg a Azure AD tartománynevet, amelyet a Supply Chain Management kiszolgálóval használ. Ez az érték a `https://login.windows.net/<your-Azure-AD-domain-name>` formátummal rendelkezik. Íme egy példa: `https://login.windows.net/contosooperations.onmicrosoft.com`. A Azure AD tartománynév megkeresésével kapcsolatos további információkért lásd: [Fontos azonosítók keresése egy felhasználóhoz](/partner-center/find-ids-and-domain-names).

        > [!IMPORTANT]
        > Ne fejezze be ezt az értéket perjellel (/).

    - **Vállalat** – Adja meg a Supply Chain Managementben szereplő jogi személyt (vállalatot), amelyhez az alkalmazásnak csatlakoznia kell.

1. Kattintson bármely lap jobb felső sarkában látható **Mentés** gombra.
1. Ha Android-eszközt használ, és tanúsítványt használ a hitelesítéshez, az eszköz rákérdez a tanúsítvány kiválasztására.
1. Az alkalmazás összekapcsolja a Supply Chain Management-szerverrel, és a bejelentkezési oldalt jeleníti meg.

## <a name="remove-access-for-a-device"></a>Eszköz hozzáférésének eltávolítása

Ha egy eszköz elveszett vagy a biztonsága sérült, el kell távolítania az eszköz a Supply Chain Managementhez való hozzáférését. Az alábbi lépések leírják a hozzáférés-eltávolítás javasolt eljárását.

1. Ugrás a **Rendszerfelügyelet \> Beállítás \> Azure Active Directory alkalmazások** elemre.
1. Törölje a sort, amely megfelel az eszköznek, amelynek a hozzáférését el szeretné távolítani. Jegyezze fel az eszköz ügyfél-azonosítóját, mivel később szüksége lesz rá.

    Ha csak egy ügyfél-azonosítót regisztrált, és több eszköz ugyanazt az ügyfél-azonosítót használja, akkor az új kapcsolati beállításokat el kell küldenie ezekre az eszközökre. Ellenkező esetben elveszítik a hozzáférést.

1. Jelentkezzen be az Azure portálon: [https://portal.azure.com](https://portal.azure.com/).
1. A bal oldali navigációs ablaktáblán válassza az **Active Directory** lehetőséget, és győződjön meg arról, hogy a megfelelő könyvtárban van.
1. A **Felügyelet** listában kattintson az **Alkalmazásregisztrációk** elemre, majd kattintson a konfigurálni kívánt alkalmazásra. Megjelenik a **Beállítások** oldal a konfigurációs adatokkal.
1. Győződjön meg róla, hogy az alkalmazás ügyfél-azonosítója megegyezik azzal az ügyfél-azonosítóval, amelyet a 2. lépésben feljegyzett.
1. Válassza az eszköztár **Törlés** elemét.
1. A megerősítő üzenetben válassza az **Igen** gombot.

## <a name="additional-resources"></a>További erőforrások

- [Mobileszköz felhasználói beállításai](mobile-device-user-settings.md)
- [Lépésikonok és címek hozzárendelése a Warehouse Management mobilalkalmazáshoz](step-icons-titles.md)
- [A Warehouse Management mobilalkalmazás konfigurálása felhőalapú és peremhálózat-léptékű egységekhez](../cloud-edge/cloud-edge-workload-setup-warehouse-app.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
