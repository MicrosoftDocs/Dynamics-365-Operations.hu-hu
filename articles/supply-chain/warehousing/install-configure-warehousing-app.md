---
title: A raktári alkalmazás telepítése és csatlakoztatása
description: Ez a témakör azt mutatja be, hogyan lehet telepíteni a raktári alkalmazást mindegyik mobileszközre, és konfigurálni a Microsoft Dynamics 365 Supply Chain Management környezethez való csatlakozásra. Az egyes eszközöket manuálisan is konfigurálhatja, illetve a csatlakozási beállításokat egy fájlként vagy egy QR-kód beolvasásával is importálhatja.
author: MarkusFogelberg
manager: tfehr
ms.date: 05/25/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysAADClientTable, WHSMobileAppField, WHSMobileAppFieldPriority, WHSRFMenu, WHSRFMenuItem, WHSWorker
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 267694
ms.assetid: d95d43b2-13ff-4189-a71a-3a1fb57d55ed
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mafoge
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 88bce09a6d3bf154592955a6fb2dada6247f1993
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4429734"
---
# <a name="install-and-connect-the-warehouse-app"></a>A raktári alkalmazás telepítése és csatlakoztatása

[!include [banner](../includes/banner.md)]

> [!NOTE]
> Ez a témakör ismerteti, hogyan kell konfigurálni a felhőbeli telepítések raktárkészlet-nyilvántartását. Ha azt szeretné megtudni, hogyan kell konfigurálni a helyszíni telepítések raktárkészlet-nyilvántartását, tekintse meg a következőt: [Helyszíni telepítések raktárkezelése](../../dev-itpro/deployment/warehousing-for-on-premise-deployments.md).

A raktári alkalmazás a Google Play Store-ban és a Microsoft Store-ban érhető el. Önálló összetevőként áll rendelkezésre. Ezért minden eszközre le kell töltenie, majd be kell állítania, hogy csatlakozzon a Microsoft Dynamics 365 Supply Chain Management-környezetéhez.

Ez a témakör azt mutatja be, hogyan lehet telepíteni a raktári alkalmazást mindegyik mobileszközre, és konfigurálni a Supply Chain Management-környezethez való csatlakozásra. Az egyes eszközöket manuálisan is konfigurálhatja, illetve a csatlakozási beállításokat egy fájlként vagy egy QR-kód beolvasásával is importálhatja.

## <a name="system-requirements"></a>Rendszerkövetelmények

A raktári alkalmazás Windows és Android operációs rendszereken érhető el. Az alkalmazás legújabb verziójának használatához rendelkeznie kell a mobileszközökre telepített alábbi támogatott operációs rendszerek egyikével:

- Windows 10 (Univerzális Windows-platform \[UWP\]) őszi készítői frissítés, 1709 (10.0.16299-es build) vagy újabb
- Android 4.4 vagy újabb

> [!NOTE]
> Ha támogatnia kell a Windows legújabb verzióját nem futtató régebbi Windows-eszközöket, akkor is továbbra is letöltheti a Microsoft Store-ból a raktári alkalmazás 1.6.3.0-ás verzióját. Ez a verzió fut a Windows 10 (UWP) novemberi frissítés, 1511 (10.0.10586-os build) vagy később verzióján. Ne feledje azonban, hogy a raktári alkalmazás ezen verziója nem támogatja a kapcsolati beállítások tömeges telepítését. Ezért minden olyan eszköz esetében, amely az alkalmazásnak ezt a verzióját futtatja, [kézzel kell konfigurálnia a kapcsolatot](#config-manually).

## <a name="get-the-warehouse-app"></a>A raktári alkalmazás letöltése

Az alkalmazás letöltéséhez használja a következő hivatkozások egyikét:

- **Windows (UWP):** [Dynamics 365 for Finance and Operations - Warehousing a Microsoft Store-ban](https://www.microsoft.com/store/apps/9p1bffd5tstm)
- **Android:** [Warehousing - Dynamics 365 a Google Play Store-ban](https://play.google.com/store/apps/details?id=com.Microsoft.Dynamics365forOperationsWarehousing)

Kisebb telepítések esetén előfordulhat, hogy az alkalmazást minden eszköz megfelelő áruházából telepíti, majd manuálisan konfigurálja a kapcsolatot az éppen használt környezettel. A raktári alkalmazás 1.7.0.0-ás és újabb verzióiban azonban automatizálhatja az alkalmazások telepítését és/vagy konfigurációját. Ez a megközelítés akkor lehet hasznos, ha sok eszközt kezel, és mobileszköz-kezelő, valamint mobilalkalmazás-kezelő megoldást használ, mint a [Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune). Az alkalmazások Intune használatával történő hozzáadásával kapcsolatos tudnivalókat lásd: [Alkalmazások hozzáadása a Microsoft Intune szolgáltatáshoz](https://docs.microsoft.com/mem/intune/apps/apps-add).

## <a name="create-a-web-service-application-in-azure-active-directory"></a><a name="create-service"></a>Webes szolgáltatás alkalmazás létrehozása az Azure Active Directory szolgáltatásban

Ahhoz, hogy a raktári alkalmazás együttműködhessen a kívánt Supply Chain Management kiszolgálóval, regisztrálnia kell egy webszolgáltatási alkalmazást az Azure Active Directory (Azure AD) felületén a Supply Chain Management bérlő számára. A következő eljárás bemutatja a feladat végrehajtásának egyik módját. A részletes tudnivalókkal és alternatívákkal kapcsolatban lásd az eljárás utáni hivatkozásokat.

1. Lépjen egy böngészőben a [https://portal.azure.com](https://portal.azure.com/) címre.
1. Adja meg a felhasználó nevét és jelszavát, aki hozzáfér az Azure-előfizetéshez.
1. Az Azure portálon a bal oldali navigációs panelen válassza az **Azure Active Directory** lehetőséget.

    ![Azure Active Directory](media/app-connect-azure-aad.png "Azure Active Directory")

1. Győződjön meg róla, hogy az Azure AD Supply Chain Management által használt példányával dolgozik.
1. A **Kezelés** listában válassza az **Alkalmazásregisztrációk** elemet.

    ![Alkalmazásregisztrációk](media/app-connect-azure-register.png "Alkalmazásregisztrációk")

1. Az eszköztáron válassza az **Új regisztráció** parancsot az **Alkalmazás regisztrálása** varázsló megnyitásához.
1. Írjon be egy nevet az alkalmazás számára, válassza a **Számlák csak ebben a szervezeti könyvtárban** lehetőséget, majd válassza a **Regisztráció** lehetőséget.

    ![Alkalmazás regisztrálása varázsló](media/app-connect-azure-register-wizard.png "Alkalmazás regisztrálása varázsló")

1. Megnyílik az új alkalmazás regisztrációja. Jegyezze fel az **Alkalmazás (ügyfél) azonosító** értékét, mert később szüksége lesz rá. Erre az azonosítóra a témakör későbbi részében *ügyfélazonosítóként* hivatkozunk.

    ![Alkalmazás (ügyfél) azonosítója](media/app-connect-azure-app-id.png "Alkalmazás (ügyfél) azonosítója")

1. Válassza a **Tanúsítvány és titkok** lehetőséget a **Kezelés** listában. Ezt követően válassza ki a következő gombok egyikét, attól függően, hogy hogyan szeretné konfigurálni az alkalmazást hitelesítésre. (További információkért tekintse meg a [Hitelesítés tanúsítványok vagy titkos ügyfélkód használatával](#authenticate) fejezetet a témakör későbbi részében.)

    - **Tanúsítvány feltöltése** – A titkos kódként használt tanúsítvány feltöltése. Ezt a megközelítést ajánljuk, mert a biztonságosabb, és nagyobb mértékben automatizálható is. Ha Windows-eszközökön futtatja a raktári alkalmazást, jegyezze fel a tanúsítvány feltöltése után megjelenő **Ujjlenyomat** értéket. Erre az értékre akkor lesz szükségem amikor Windows-eszközökön konfigurálja a tanúsítványt.
    - **Új titkos ügyfélkód** – Hozzon létre egy kulcsot a kulcs leírásának és időtartamának megadásával a **Jelszavak** részben, majd válassza a **Hozzáadás** elemet. Készítsen másolatot a kulcsról, és tárolja biztonságosan.

    ![Tanúsítvány és titkos kódok](media/app-connect-azure-authentication.png "Tanúsítvány és titkos kódok")

Az Azure AD webszolgáltatási alkalmazásainak beállításával kapcsolatos további tudnivalókat lásd a következő forrásokban:

- A webszolgáltatási alkalmazások Windows PowerShell eszközzel, az Azure AD rendszerben történő beállításával kapcsolatban a következő témakör tartalmaz további tájékoztatást: [Útmutató: Az Azure PowerShell használata egy tanúsítvánnyal rendelkező szolgáltatási főkiszolgáló létrehozásához](https://docs.microsoft.com/azure/active-directory/develop/howto-authenticate-service-principal-powershell).
- A webszolgáltatási alkalmazások Azure AD rendszerben való manuális létrehozásával kapcsolatos további tudnivalókat lásd a következő témakörökben:

    - [Rövid útmutató: Alkalmazások regisztrálása a Microsoft Identity platformmal](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app)
    - [Útmutató: Erőforrások elérésére képes Azure AD alkalmazás és szolgáltatási főkiszolgáló létrehozása portál használatával](https://docs.microsoft.com/azure/active-directory/develop/howto-create-service-principal-portal)

## <a name="create-and-configure-a-user-account-in-supply-chain-management"></a>Felhasználói fiók létrehozása és konfigurálása a Supply Chain Management megoldásban

A következő lépésekkel engedélyezheti az Supply Chain Management számára az Azure AD alkalmazása használatát.

1. Hozzon létre egy olyan felhasználót, amely megfelel a raktári alkalmazás felhasználói hitelesítő adatainak:

    1. A Supply Chain Management szolgáltatásban lépjen a **Rendszerfelügyelet \> Felhasználók \> Felhasználók** elemre.
    1. Hozzon létre egy felhasználót.
    1. Rendelje hozzá a raktározási mobileszköz felhasználóját.

    ![Rendelje hozzá a raktározási mobileszköz felhasználóját](media/app-connect-app-users.png "Rendelje hozzá a raktározási mobileszköz felhasználóját")

1. Társítsa az Azure AD alkalmazást a raktári alkalmazás felhasználójával:

    1. Ugrás a **Rendszerfelügyelet \> Beállítás \> Azure Active Directory alkalmazások** elemre.
    1. Hozzon létre egy sort.
    1. Írja be az előző szakaszban feljegyzett ügyfél-azonosítót, adja meg a nevet, és válassza ki az imént létrehozott felhasználót. Javasoljuk, hogy az összes eszközt címkézze fel. Ezt követően, ha elvesznek, egyszerűen eltávolíthatja a Supply Chain Management alkalmazáshoz való hozzáférést ezen az oldalon.

    ![Azure Active Directory alkalmazások](media/app-connect-aad-apps.png "Azure Active Directory alkalmazások")

## <a name="authenticate-by-using-a-certificate-or-client-secret"></a><a name="authenticate"></a>Hitelesítés tanúsítványok vagy titkos ügyfélkód használatával

Az Azure AD használatával történő hitelesítéssel biztonságos módon csatlakoztathat egy mobileszközt a Supply Chain Management alkalmazsáshoz. A hitelesítést elvégezheti titkos ügyfélkód vagy tanúsítványok használatával. Ha a csatlakozási beállításokat importálja, javasoljuk, hogy a titkos ügyfélkód helyett helyett használjon tanúsítványt. Mivel a titkos ügyfélkódot mindig biztonságosan kell tárolni, nem importálhatja azt egy kapcsolatbeállítási fájlból vagy egy QR-kódból, a témakörben később ismertetett módon.

A tanúsítványok felhasználhatók titkos kódokként az alkalmazás azonosságának igazolására, ha a rendszer tokent kér. A tanúsítvány nyilvános része fel van töltve az alkalmazásregisztrációba az Azure portálon, míg a teljes tanúsítványt telepíteni kell minden olyan eszközre, amelyre a raktári alkalmazás telepítésre kerül. A szervezet felelős a tanúsítvány rotációjának és egyéb szempontjainak kezelésével kapcsolatban. Önaláírt tanúsítványok is használhatók, de mindig nem exportálható tanúsítványokat kell használnia.

A tanúsítványt helyileg elérhetővé kell tenni minden olyan eszközön, amelyen a raktári alkalmazást futtatja. A Intune által vezérelt eszközök tanúsítványainak kezelésével kapcsolatban a következő témakör tartalmaz további tájékoztatást: [Tanúsítványok használata hitelesítéshez a Microsoft Intune szolgáltatásban](https://docs.microsoft.com/mem/intune/protect/certificates-configure).

## <a name="configure-the-application-by-importing-connection-settings"></a>Az alkalmazás konfigurálása a kapcsolati beállítások importálásával

Annak érdekében, hogy az alkalmazások könnyebben karbantarthatók és telepíthetők legyenek számos mobileszközön, a csatlakozási beállításokat importálhatja az egyes eszközökbe történő kézi beírás helyett. Ez a szakasz bemutatja, hogyan lehet létrehozni és importálni a beállításokat.

### <a name="create-a-connection-settings-file-or-qr-code"></a>Kapcsolatbeállítási fájl vagy QR-kód létrehozása

A csatlakozási beállításokat egy fájlból vagy egy QR-kódból is importálhatja. Mindkét módszernél létre kell hoznia egy olyan beállításfájlt, amely JSON (JavaScript Object Notation) formátumot és szintaxist használ. A fájlnak tartalmaznia kell egy olyan kapcsolatlistát, amely tartalmazza a hozzáadandó egyéni kapcsolatokat. A következő táblázat összegzi azokat a paramétereket, amelyeket meg kell adnia a kapcsolatbeállítási fájlhoz.

| Paraméter | Leírás |
| --- | --- |
| ConnectionName | Adja meg a csatlakozási beállítás nevét. A maximális hossz 20 karakter. Mivel ez az érték egy csatlakozási beállítás egyedi azonosítója, győződjön meg arról, hogy egyedi a listán. Ha már létezik ilyen nevű kapcsolat az eszközön, akkor az importált fájl beállításai felülbírálják. |
| ActiveDirectoryClientAppId | Adja meg az ügyfélazonosítót, amelyet az Azure AD beállítása közben jegyzett fel a [Webszolgáltatási alkalmazás létrehozása az Azure Active Directory rendszerben](#create-service) szakaszban. |
| ActiveDirectoryResource | Adja meg a Supply Chain Management gyökér-URL-címét. |
| ActiveDirectoryTenant | Adja meg az Azure AD Supply Chain Management-kiszolgálón használt bérlőt. Ez az érték a `https://login.windows.net/<your-Azure-AD-tenant-ID>` formátummal rendelkezik. Íme egy példa: `https://login.windows.net/contosooperations.onmicrosoft.com`. |
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

Általában egy eszközkezelő eszközzel vagy parancsfájllal terjesztheti a kapcsolati beállítások fájljait mindegyik éppen kezelt eszközre. Ha az alapértelmezett nevet és helyet használja a kapcsolatbeállításokat tartalmazó fájl mentésekor az egyes eszközökön, akkor a program automatikusan importálja azt, még a raktári alkalmazás telepítése utáni első futtatásakor is. Ha egyéni nevet vagy helyet ad meg a fájlnak, az alkalmazás felhasználójának meg kell adnia az értékeket az első futtatásakor. Az alkalmazás azonban továbbra is a megadott nevet és helyet fogja használni.

Az alkalmazás minden elindításakor újraimportálja a kapcsolatbeállításokat a korábbi helyről, és meghatározza, hogy vannak-e módosítások. Az alkalmazás csak azokat a kapcsolatokat fogja frissíteni, amelyeknek ugyanaz a neve, mint a kapcsolatbeállítási fájljához tartozó kapcsolatoknak. A felhasználó által létrehozott, más neveket használó kapcsolatok nem frissülnek.

Kapcsolatot nem lehet eltávolítani a kapcsolatbeállítások fájljával.

A fentiek szerint az alapértelmezett fájlnév a *connections.json*. A fájl alapértelmezett helye attól függ, hogy Windows-eszközt vagy Android-eszközt használ:

- **Windows:** `C:\Users\<User>\AppData\Local\Packages\Microsoft.Dynamics365forOperations-Warehousing_8wekyb3d8bbwe\LocalState`
- **Android:** `Android\data\com.Microsoft.Dynamics365forOperationsWarehousing\files`

Általában az útvonalak automatikusan létrejönnek az alkalmazás első futtatása után. Ezeket a beállításokat azonban manuálisan is létrehozhatja, ha a telepítés előtt át kell vinnie az eszközre a kapcsolatbeállításokat tartalmazó fájlt.

> [!NOTE]
> Ha eltávolítja az alkalmazást, akkor az alapértelmezett elérési út és annak tartalma törlődik.

### <a name="import-the-connection-settings"></a>A kapcsolat beállításainak importálása

Kövesse az alábbi lépéseket a csatlakozási beállítások egy fájlból vagy egy QR-kódból történő importálásához.

1. Nyissa meg a mobileszközén a raktári alkalmazást.
1. Lépjen a **Kapcsolat beállításai** elemre.
1. A **Bemutató mód használata** lehetőséget állítsa _Nem_ értékre.

    ![Bemutató mód használata beállítás](media/app-connect-app-demo-mode.png "Bemutató mód használata beállítás")

1. Válassza ki a **Fájl kiválasztása** vagy **QR-kód beolvasása** lehetőséget, attól függően, hogy hogyan szeretné importálni a beállításokat:

    - Ha egy fájlból importálja a kapcsolatbeállításokat, előfordulhat, hogy az alkalmazás már megtalálta a fájlt, ha a mentéskor az alapértelmezett név és az alapértelmezett hely került felhasználásra. Ellenkező esetben jelölje be a **Fájl kiválasztása** lehetőséget, tallózással keresse meg a fájlt a helyi eszközön, majd válassza ki azt. Ha kiválaszt egy egyéni helyet, akkor az alkalmazás tárolja és automatikusan felhasználja a következő alkalommal.
    - Ha QR-kód beolvasásával importálja a kapcsolatbeállításokat, válassza a **QR-kód beolvasása** parancsot. A program engedélyt kér az eszköz kamerájának használatára. Miután megadta az engedélyt, a kamera elindul, így használható a szkenneléshez. Az eszköz kamerájának minőségétől és a QR-kód bonyolultságától függően előfordulhat, hogy nehéz megfelelően beolvasni. Ebben az esetben próbálja meg csökkenteni a QR-kód bonyolultságát úgy, hogy csak egy kapcsolatot generál QR-kódonként. (Jelenleg csak az eszköz kamerája használható a QR-kód beolvasására.)

    ![A kapcsolat beállításainak importálása](media/app-connect-app-select-file.png "A kapcsolat beállításainak importálása")

1. Amikor a kapcsolatok beállításai sikeresen betöltődnek, válassza a **Vissza** (balra nyíl) gombot az oldal felső sarkában.

    ![Kapcsolatbeállítások betöltve](media/app-connect-app-settings-loaded.png "Kapcsolatbeállítások betöltve")

1. Ha Android-eszközt használ, és tanúsítványt használ a hitelesítéshez, az eszköz rákérdez a tanúsítvány kiválasztására.

    ![Tanúsítvány választására szolgáló kérés egy Android-eszközön](media/app-connect-app-choose-cert.png "Tanúsítvány választására szolgáló kérés egy Android-eszközön")

1. Az alkalmazás összekapcsolja a Supply Chain Management-szerverrel, és a bejelentkezési oldalt jeleníti meg.

    ![Bejelentkezési oldal](media/app-connect-sign-in.png "Bejelentkezési oldal")

## <a name="manually-configure-the-application"></a><a name="config-manually"></a>Az alkalmazás manuális konfigurálása

Manuálisan konfigurálhatja az alkalmazást az eszközön, hogy csatlakozni tudjon a Supply Chain Management-kiszolgálóhoz Azure AD alkalmazáson keresztül.

1. Nyissa meg a mobileszközén a raktári alkalmazást.
1. Lépjen a **Kapcsolat beállításai** elemre.
1. A **Bemutató mód használata** lehetőséget állítsa _Nem_ értékre.

    ![Bemutató mód kikapcsolva](media/app-connect-app-select-file.png "Bemutató mód kikapcsolva")

1. A **Kapcsolat kiválasztása** mezőben bontsa ki a kapcsolati adatok manuális megadásához szükséges beállításokat.

    ![Manuális kapcsolati mezők](media/app-connect-manual-connect.png "Manuális kapcsolati mezők")

1. Adja meg a következő adatokat:

    - **Titkos ügyfélkód használata** – Adja meg ezt a beállítást _Igen_ értékkel titkos ügyfélkóddal történő hitelesítéshez a Supply Chain Management alkalmazásban. Állítsa _Nem_ értékre, ha tanúsítványt kíván használni a hitelesítéshez. (További tájékoztatás: [Webszolgáltatás-alkalmazás létrehozása az Azure Active Directory rendszerben](#create-service).)
    - **Kapcsolat neve** – Adjon nevet az új kapcsolatnak. Ez a név fog megjelenni a **Kapcsolat kiválasztása** mezőben, amikor legközelebb megnyitja a kapcsolatbeállításokat. A megadott névnek egyedinek kell lennie. (Más szóval különböznie kell az eszközön tárolt összes egyéb kapcsolatnévtől, ha más kapcsolatneveket is tárol ott.).
    - **Active directory ügyfélazonosító** – Adja meg az ügyfélazonosítót, amelyet az Azure AD beállítása közben jegyzett fel a [Webszolgáltatási alkalmazás létrehozása az Azure Active Directory rendszerben](#create-service) szakaszban.
    - **Active Directory titkos ügyfélkódja** – Ez a mező csak akkor érhető el, ha a **Titkos ügyfélkód használata** beállítás értéke _Igen_. Adja meg a titkos ügyfélkódot, amelyet az Azure AD beállítása közben jegyzett fel a [Webszolgáltatási alkalmazás létrehozása az Azure Active Directory rendszerben](#create-service) szakaszban.
    - **Active Directory tanúsítvány ujjlenyomata** – Ez a mező csak Windows-eszközökön érhető el, ha a **Titkos ügyfélkód használata** beállítás értéke _Nem_. Adja meg a tanúsítvány ujjlenyomatát, amelyet az Azure AD beállítása közben jegyzett fel a [Webszolgáltatási alkalmazás létrehozása az Azure Active Directory rendszerben](#create-service) szakaszban.
    - **Active Directory-erőforrás** – Adja meg a Supply Chain Management gyökér URL-jét.

        > [!NOTE]
        > Ne fejezze be ezt az értéket perjellel (/).

    - **Active Directory-bérlő** – Adja meg a Supply Chain Management-kiszolgálón használt Azure AD bérlőt. Ez az érték a `https://login.windows.net/<your-Azure-AD-tenant-ID>` formátummal rendelkezik. Íme egy példa: `https://login.windows.net/contosooperations.onmicrosoft.com`.

        > [!NOTE]
        > Ne fejezze be ezt az értéket perjellel (/).

    - **Vállalat** – Adja meg a Supply Chain Managementben szereplő jogi személyt, amelyhez az alkalmazásnak csatlakoznia kell.

1. Kattintson bármely lap jobb felső sarkában látható **Mentés** gombra.
1. Ha Android-eszközt használ, és tanúsítványt használ a hitelesítéshez, az eszköz rákérdez a tanúsítvány kiválasztására.
1. Az alkalmazás összekapcsolja a Supply Chain Management-szerverrel, és a bejelentkezési oldalt jeleníti meg.

## <a name="remove-access-for-a-device"></a>Eszköz hozzáférésének eltávolítása

Abban az esetben, ha egy eszköz elveszett vagy a biztonsága sérült, el kell távolítania az eszköz a Supply Chain Managementhez való hozzáférését. Az alábbi lépések leírják a hozzáférés-eltávolítás javasolt eljárását.

1. Ugrás a **Rendszerfelügyelet \> Beállítás \> Azure Active Directory alkalmazások** elemre.
1. Törölje a sort, amely megfelel az eszköznek, amelynek a hozzáférését el szeretné távolítani. Jegyezze fel az eltávolított eszköz ügyfél-azonosítóját, mivel később szüksége lesz rá.

    Ha csak egy ügyfél-azonosítót regisztrált, és több eszköz ugyanazt az ügyfél-azonosítót használja, akkor az új kapcsolati beállításokat el kell küldenie ezekre az eszközökre. Ellenkező esetben elveszítik a hozzáférést.

1. Jelentkezzen be az Azure portálon: [https://portal.azure.com](https://portal.azure.com/).
1. A bal oldali navigációs ablaktáblán válassza az **Active Directory** lehetőséget, és győződjön meg arról, hogy a megfelelő könyvtárban van.
1. A **Felügyelet** listában kattintson az **Alkalmazásregisztrációk** elemre, majd kattintson a konfigurálni kívánt alkalmazásra. Megjelenik a **Beállítások** oldal a konfigurációs adatokkal.
1. Győződjön meg róla, hogy az alkalmazás ügyfél-azonosítója megegyezik azzal az ügyfél-azonosítóval, amelyet a 2. lépésben feljegyzett.
1. Válassza az eszköztár **Törlés** elemét.
1. A megerősítő üzenetben válassza az **Igen** gombot.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]