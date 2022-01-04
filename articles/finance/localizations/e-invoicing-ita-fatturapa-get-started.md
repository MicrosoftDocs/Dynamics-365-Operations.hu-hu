---
title: Az olasz FatturaPA közvetlen integrációja az SDI-vel
description: Ez a témakör olyan információkat tartalmaz, amelyek segítenek az olaszországi elektronikus számlázás megkezdésében, és az olasz FatturaPA közvetlen integrációjának beállításában az Exchange rendszerrel (SDI).
author: abaryshnikov
ms.date: 12/14/2021
ms.topic: article
audience: Application User, Developer
ms.reviewer: kfend
ms.search.region: Global
ms.author: abaryshnikov
ms.search.validFrom: 2021-10-18
ms.dyn365.ops.version: AX 10.0.20
ms.openlocfilehash: 0ccc9f04e42e748b4531622a1c90559d4ca17196
ms.sourcegitcommit: b1c758ec4abfcf3bf9e50f18c1102d4a9c1316d0
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/15/2021
ms.locfileid: "7922462"
---
# <a name="set-up-direct-integration-of-italian-fatturapa-with-sdi"></a>Az olasz FatturaPA közvetlen integrációja az SDI-vel

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

> [!IMPORTANT]
> Előfordulhat, hogy az Olasz elektronikus számlázás jelenleg nem támogatja az elektronikus számlákhoz rendelkezésre álló összes funkciót a Microsoft Dynamics 365 Finance és Dynamics 365 Supply Chain Management számára.

Ez a témakör olyan információkat tartalmaz, amelyek segítenek az olaszországi elektronikus számlázás megkezdésében a pénzügyi és ellátási lánc menedzsment területén. Végigvezeti Önt a szabályozási konfigurációs szolgáltatásokban (RCS) országtól/régiótól függő konfigurációs lépéseken. Ezek a lépések kiegészítik az Elektronikus számlázás első lépések című témakörben ismertetett [lépéseket](e-invoicing-get-started.md).

## <a name="prerequisites"></a>Előfeltételek

A témakör lépéseinek elvégzése előtt a következő előfeltételeknek kell teljesülniük:

- Végezze el az [Elektronikus számlázás első lépéseit](e-invoicing-get-started.md).
- Importálja az **olasz FatturaPA (IT)** elektronikus számlázási funkciót az RCS-be a globális adattárból. További információt a [Korábban említett "Az elektronikus számlázással való kezdés" témakör Elektronikus számlázás importálása című](e-invoicing-get-started.md#import-an-electronic-invoicing-feature-from-the-microsoft-configuration-provider) témakörben talál.
- Hivatkozásokat adhat hozzá a szükséges tanúsítványokból a szolgáltatási környezetbe. A szükséges tanúsítványok közé tartozik a digitális aláírási tanúsítvány, a hitelesítésszolgáltatói tanúsítvány és az Ügyfelek tanúsítvány. További információ: [Digitális tanúsítvány titkos létrehozása az](e-invoicing-get-started-service-administration.md#create-a-digital-certificate-secret) "Első lépések az elektronikus számlázási szolgáltatás adminisztrációjával" témakörben.

## <a name="country-specific-configuration-for-the-italian-fatturapa-it-electronic-invoicing-feature"></a>Az olasz FatturaPA (IT) elektronikus számlázási funkció országspecifikus konfigurációja

Az alkalmazás beállításának üzembe helyezése előtt hajtsa végre a következő eljárásokat a csatlakoztatott Pénzügyi vagy Ellátási Lánckezelő alkalmazásban.

Ez a szakasz kiegészíti az ["Első lépések az elektronikus számlázással" témakör alkalmazásbeállítási szakaszának országspecifikus](e-invoicing-get-started.md#country-specific-configuration-of-application-setup) konfigurációját.

### <a name="create-a-new-feature"></a>Új funkció létrehozása

1. Bejelentkezés az RCS alkalmazásba.
2. Az **Elektronikus jelentéskészítés** munkaterület **Konfigurációs szolgáltatók** szakaszában jelölje meg a vállalat konfigurációs szolgáltatóját aktívként.
3. A **Globalizációs funkció** munkaterületen a **Funkciók** szakaszban válassza ki az **Elektronikus számlázás** csempét.
4. Az Elektronikus számlázási szolgáltatások lapon válassza a **Hozzáadás a meglévő funkció alapján** **·** \> **lehetőséget**.
5. A **Microsoft konfigurációs szolgáltatója területen válassza az Olasz** **FatturaPA (IT)** elemet alapfunkcióként, adjon meg egy nevet, majd válassza a Szolgáltatás létrehozása **lehetőséget**.

### <a name="set-up-application-specific-parameters"></a>Alkalmazásfüggő paraméterek beállítása

1. Az **Elektronikus számlázási szolgáltatások** lapon válassza ki a szerkeszteni kívánt funkciót.
2. A **Verziók** lapon ellenőrizze, hogy a **Piszkozat** verzió ki van-e választva.
3. A **Konfigurációk** lapon válasszon ki egy konfigurációt, majd válassza a **Alkalmazásspecifikus paraméterek** lehetőséget.
4. A **Keresések** szakaszban győződjön meg arról, hogy a **Natura fordított adózási alkategóriák listája** beállítás van kiválasztva.
5. A **Feltételek** szakaszban válassza a **Hozzáadás** lehetőséget.
6. Adjon hozzá konkrét feltételeket a rendszerben definiált minden alkategóriához, majd mentse a módosításokat.

    > [!NOTE]
    > A **Név** oszlopban egy adott érték helyett az **\* Üres vagy Nem üres \*** **\* helyőrző értéket választhatja \*** ki.

### <a name="configure-a-processing-pipeline-for-export"></a>Feldolgozási folyamat konfigurálása exportálásra

1. Az **Elektronikus számlázási szolgáltatások** lapon válassza ki a szerkeszteni kívánt funkciót.
2. A Beállítások lapon válassza a **Eladási** számlák lehetőséget, majd válassza **a Szerkesztés** **parancsot**.
3. A **Folyamat feldolgozása** szakaszban végigmenjen a műveleteken, és állítsa be az összes szükséges mezőt:

    - A **Dokumentum aláírása** művelethez a **Tanúsítvány neve** mezőben adja meg a Digitális aláírási tanúsítványt.
    - A **Küldés** művelethez állítsa be az **URL-címet és a Tanúsítványok** **mezőket**. A Tanúsítványok mező értéke **tanúsítványok** láncolata, amelyek közül az első a legfelső szintű hitelesítésszolgáltatói tanúsítvány (caentrate.cer), a második pedig az Ügyfelek tanúsítvány.

4. Válassza az Érvényesítés lehetőséget **az összes szükséges mező** beállításának ellenőrzéséhez.
5. Mentse el a módosításokat, és zárja be az oldalt.
6. A Beállítások lapon válassza a **Projektszámlák** lehetőséget, **majd válassza a Szerkesztés** **parancsot**.
7. Ismételje meg a projektszámlák 3–5. lépését.

### <a name="configure-the-processing-pipeline-for-import"></a>A feldolgozási folyamat konfigurálása importálásra

1. Az **Elektronikus számlázási szolgáltatások** lapon válassza ki a szerkeszteni kívánt funkciót.
2. A Beállítások lapon válassza a **Számlák** **importálása** lehetőséget, majd válassza a Szerkesztés **lehetőséget**.
3. Az Adatcsatorna szakasz Paraméterek lapján az Adatcsatorna mezőben adjon meg **egy** **·** **karakterláncot**.
4. Állítsa be a beállítások mezőit az Alkalmazhatósági **szabályok** lapon. Az alapértelmezett csatornazáradékot úgy használhatja, hogy az előző lépésben az Adatcsatorna mezőben beállított értéket az **Érték** mezőbe **adja** **át**.

    ![Alkalmazhatósági szabályok beállítása](media/e-invoicing-ita-fatturapa-get-started-apprules-setup.png)

5. Válassza az Érvényesítés lehetőséget **az összes szükséges mező** beállításának ellenőrzéséhez.

### <a name="deploy-the-feature"></a>A funkció telepítése

1. A szolgáltatás befejezése, közzététele és üzembe helyezése a szolgáltatási környezetben. A további tudnivalókat lásd az "Elektronikus számlázással" című témakör "Az elektronikus számlázással kapcsolatos első lépések" szakaszának Elektronikus számlázás szolgáltatáskörnyezetre [telepítése](e-invoicing-get-started.md#deploy-the-electronic-invoicing-feature-to-service-environment) című témakörében.
2. A funkció telepítése a csatlakoztatott alkalmazásra. A további tudnivalókat lásd az Elektronikus számlázás telepítése a Csatlakoztatott alkalmazásra szakaszának "Az Elektronikus számlázással" című [témakörében](e-invoicing-get-started.md#deploy-the-electronic-invoicing-feature-to-connected-application).

### <a name="set-up-finance"></a>A Pénzügy beállítása

1. Jelentkezzen be a Pénzügyi környezetbe.
2. Az **Elektronikus jelentéskészítés** munkaterületen, a **Konfigurációszolgáltatók** szakaszban, válassza a **Microsoft** csempét.
3. Válassza **ki a Tárház globális** \> **·** \> **megnyitási** lehetőséget.
4. A vevői számla **környezetmodell és szállítói számla** **importálási (IT) konfigurációjának** kiválasztása és importálása.
5. Menjen a **Szervezeti adminisztráció** \> **Beállítás** \> **Elektronikus dokumentumparaméterek** lehetőségre.
6. A Szolgáltatások lapon keresse meg és válassza ki az **olasz** elektronikus számla **funkciót**, majd jelölje be az **Engedélyezés** jelölőnégyzetet.
7. Az Elektronikus dokumentum lapon győződjön meg arról, hogy a vevői számlanapló és a projektszámla mezői be vannak állítva az Alkalmazás beállításainak konfigurálása című dokumentumban szereplő **adatok** **·** **·**[szerint](e-invoicing-get-started.md#configure-the-application-setup).

### <a name="set-up-vendor-invoice-import"></a>Szállítói számla importálásának beállítása 

1. A Vállalat konfigurációszolgáltatóját a Pénzügy szakaszban, az Elektronikus jelentések munkaterületén jelölje meg aktívként a **vállalat** **konfigurációszolgáltatóját**.
2. Válassza a **Jelentéskészítési konfigurációk** elemet.
3. Válassza ki **a Vevői számla környezetmodellt,** majd válassza a Konfiguráció létrehozása **lehetőséget**.
4. Válassza **a Származtatott névből: Vevői számla környezete, a Microsoft** lehetőséget származtatott konfiguráció létrehozásához.
5. A Vázlat **verzióban** válassza a **Tervező** lehetőséget.
6. Az Adatmodell fában válassza a **Modell** **leképezés adatforráshoz** beállítását.
7. Válassza a **Definíciók fa** **DataChannel,** majd a Tervező **adatokat**.
8. Bontsa ki a helyi csatorna **tárolóját** az **\$\_** adatforrásfában.
9. Az Érték **mezőben** válassza a **Szerkesztés** lehetőséget. 
10. Az adatcsatorna nevének beírása. A név legfeljebb 10 karakterből állhat. Meg kell egyeznie az RCS elektronikus számlázási funkciója **adatcsatorna**-paraméterének értékével.
11. Mentse a módosításokat, majd kattintson a **Jelentéskészítési konfigurációk –** \> **Befejezve konfigurációs** verzió.
12. Válassza a Hozzáadás lehetőséget a Külső **csatornák** lap **Csatornák** **szakaszában**.
13. A Csatorna **mezőben** adja meg a **\$ Context Channel** értékét.
14. Írja be az értékeket **a Leírás és a Vállalat** **mezőkbe**.
15. A Dokumentum környezete mezőben válassza ki a vevői számla környezetmodellből származó **új** **konfigurációt**. A leképezés leírásának **Adatcsatorna-kontextusnak** kell lennie.
16. Válassza a **Források** importálása lapon a Hozzáadás gombra, majd **állítsa be a következő** értékeket:

    - **Név:** OutputFile
    - **Adatentitás** neve: Szállítói számla fejléce (**Adatentitás**: VendorInvoiceHeaderEntity)
    - **Modellleképezés:** Szállítói számla importálása (It)

> [!NOTE]
> Ha különböző forrásból importál szállítói számlákat, létrehozhat több külső csatornát és több származtatott konfigurációt, amelyek eltérő helyi **\$ csatornaértékekkel** rendelkezik. Előfordulhat például, hogy különböző jogi személyek szállítói számláit szeretné importálni.

## <a name="proxy-server-setup"></a>Proxykiszolgáló beállítása

Ez a szakasz olyan információkat tartalmaz, amelyek segítségével beállíthatja és beállíthatja a proxyszolgáltatást az Adatcsere-rendszer (SDI) és az Elektronikus számlázási szolgáltatás közötti kommunikációhoz.

### <a name="create-an-app-registration"></a>Alkalmazásregisztráció létrehozása

1. A következő Windows PowerShell-parancsfájl használatával hozzon létre egy önkiszolgáló tanúsítványt a szolgáltatás-szolgáltatásnak (S2S) hitelesítéshez.

    ```powershell
    $certOutputLocation = "C:\certs\proxytest"
    $certName = "sdiProxyClientS2SCert"
    $certPassword = "123"

    $certCerFile = Join-Path $certOutputLocation "$certName.cer"
    $certPfxFile = Join-Path $certOutputLocation "$certName.pfx"

    $securePassword = ConvertTo-SecureString $certPassword -AsPlainText -Force

    $cert = New-SelfSignedCertificate -KeyLength 2048 -KeyExportPolicy Exportable -FriendlyName "CN=$certName" -CertStoreLocation Cert:\CurrentUser\My -Subject $certName -Provider "Microsoft Enhanced RSA and AES Cryptographic Provider"

    Export-Certificate -Cert $cert -FilePath $certCerFile -type CERT | Out-Null
    Export-PfxCertificate -Cert $cert -FilePath $certPfxFile -Password $securePassword | Out-Null
    ```

2. Mentse a .pfx tanúsítványfájlt a kulcsba, majd törölje a helyi példányt.
3. Jelentkezzen be rendszergazdaként az [Azure](https://portal.azure.com)-portálra.
4. Alkalmazásregisztráció létrehozása az SDI Proxy szolgáltatáshoz.

    1. Menjen az **alkalmazásregisztrációkhoz, hozzon létre egy regisztrációt, majd állítsa be a következő** értékeket:

        - **Név:** SDI proxy ügyfél
        - **Támogatott fióktípusok:** Csak az ebben a szervezeti könyvtárban található fiókok (egy bérlő)

    2. Válassza **a** Regisztrálás lehetőséget, majd a most létrehozott alkalmazásregisztrációt.
    3. Menjen az **API-engedélyekhez,** és válassza a Támogatás **rendszergazdai hozzájárulását.**
    4. Menjen a Tanúsítványok & kulcshoz, válassza a Tanúsítvány feltöltése lehetőséget, majd töltse fel **a** **·** .cer tanúsítványfájlt az S2S-hitelesítéshez.
    5. Menjen az **Enterprise**-alkalmazásokhoz, és válassza ki a létrehozott alkalmazást.
    6. Az **alkalmazásazonosító** (ügyfél-azonosító) és **az objektumazonosító értékek mentése az alkalmazás** számára.
    7. A Számlázási szolgáltatás csapatának meg kell bizonyosodnie a szolgáltatáshoz való alkalmazás-hozzáférésről. A következő paraméterek értékeinek küldése <D365EInvoiceSupport@microsoft.com> a következőnek:

        - AAD bérlő azonosítója
        - LCS-környezet azonosítója
        - Pályázat azonosítója
        - Objektumazonosító

5. Az RCS szolgáltatásban vegye fel az alkalmazást a szolgáltatási környezet alkalmazáslistába.

    1. Ugrás **a Globalization features** \> **Environment** \> **Electronic Invoicing** \> **Service környezetekhez, és** válassza ki a környezetet.
    2. A Pályázatok szakaszban adjon egy sort a rácshoz, majd adja meg az alkalmazás **nevét** és objektumazonosítóját.

        ![Az alkalmazás hozzáadása a szolgáltatási környezethez.](media/e-invoicing-ita-fatturapa-get-started-add-app-to-env.png)

    3. Válassza **a** Mentés, majd a Közzététel **lehetőséget**.

### <a name="create-an-azure-virtual-machine"></a>Azure virtuális gép létrehozása

1. Az [Azure-portálon menjen a Virtuális](https://portal.azure.com)**gépekhez**, és válassza az Új létrehozása **lehetőséget**.
2. Válassza ki az előfizetést és az **erőforráscsoportot** az Alapokkal lapon. Az értékeknek annak az előfizetésnek és erőforráscsoportnak kell lennie, ahol a kulcs és a Blob tároló található.
3. Válassza ki a régiót. Ennek az értéknek annak a régiónak kell lennie, ahol a Pénzügyi környezet telepítve van.
4. Adja hozzá a rendszergazda felhasználónevét és jelszavát, majd mentse a kulcskulcsba.
5. A **Bejövő portok kiválasztása** mezőben válassza a **HTTPS (443) és** az **RPD (3389)** lehetőséget.

    > [!NOTE]
    > Azt ajánljuk, hogy akkor tiltsa le az **RDP-portot (3389-es),** amikor a rendszer termelésbe kerül. Ha hibaelhárítás céljából a virtuális géphez ( VM) kell kapcsolódnia, újra engedélyezheti.

    ![Az Alap lap mezőinek beállítása Egy Azure-ás virtuális gép létrehozásához.](media/e-invoicing-ita-fatturapa-get-started-create-vm-1.png)

6. A Speciális gyorslap Lemezek lapján jelölje be a Felügyelt lemez **használata** **·** **jelölőnégyzetet**. Hagyja a jelölőnégyzetet törölve az Elektronikus operációs **rendszer** lemeze jelölőnégyzetből.

    ![A Hajlékonylemezek lapon található mezők beállítása Egy Azure-beli virtuális gép létrehozásához.](media/e-invoicing-ita-fatturapa-get-started-create-vm-2.png)

7. A Hálózat lap Nyilvános **IP**-mezőjében **válassza az Új létrehozása** **lehetőséget**.

    ![A Hálózat lap mezőinek beállítása Azure-ás virtuális gép létrehozása érdekében](media/e-invoicing-ita-fatturapa-get-started-create-vm-3.png)

8. A Nyilvános **IP-cím létrehozása** párbeszédpanelEn, a **Ku** mezőcsoportban válassza a **Szokásos** beállítást. A Hozzárendelés **mezőcsoportban** válassza a **Statikus** beállítást.

    ![Nyilvános IP-cím létrehozása](media/e-invoicing-ita-fatturapa-get-started-create-vm-4.png)

9. A Kezelés lapon törölje a jelölést az **Automatikus** **leállítás** jelölőnégyzetből, ha le szeretné tiltani az automatikus leállítást.
10. Állítsa a **vendég operációs rendszer frissítés** mezőjét Kézi **mezőbe**, majd állítsa be az egyéb házirendeket.
11. Tekintse át és hozza létre a virtuális gépet.
12. Az új virtuális gépen lépjen **a** \> **Hozzárendelt Identitásrendszer** elemre, és állítsa be az **Állapot beállítást** Be **parancsra**.
13. Adja meg a virtuális gépnek a kulcstartóhoz való hozzáférést.

    1. A kulcstartóban nyissa meg a **Hozzáférés-vezérlés (IAM)** \> **szerepkör-hozzárendelések** parancsát.
    2. Válassza a **Szerepkör-hozzárendelés hozzáadása** lehetőséget, majd állítsa be a következő mezőket:

        1. A **Szerepkör** mezőben adja meg **a Key Vault Secrets User** parancsot.
        2. A **Hozzáférés hozzárendelése** mező mezőben adja meg a **Virtuális gép** parancsot.
        3. Az **Előfizetés** mezőben adja meg az előfizetést.
        4. A **Kijelölés** mezőben adja meg a virtuális gépet.

    3. Nyissa meg az **Access-házirendeket**.
    4. Válassza a **Hozzáférési házirend hozzáadása** lehetőséget, majd állítsa be a következő mezőket:

        1. A **Kijelölt fő** mezőben válassza ki a virtuális gépet.
        2. A **Tanúsítvány szakaszban válassza a Lista és az** Engedélyek **·** **lekért** lehetőséget.

14. Az [Azure Portal](https://portal.azure.com) webhelyen lépjen a **Nyilvános IP-címek** elemre, és válassza ki a virtuális gépen létrehozott IP-címet.
15. Lépjen a **Konfiguráció** elemre, és állítsa be a DNS-nevet.

### <a name="prepare-the-proxy-service-environment"></a>A proxyszolgáltatás környezetének előkészítése

Kövesse az alábbi lépéseket azon a gépen, ahol a proxyszolgáltatást üzemelteti.

1. Csatlakozzon a virtuális géphez a Távoli asztali kapcsolat használatával.
2. Nyissa meg a Helyigép-tanúsítvány beépülő modult. További információ: [Hogyan: Tanúsítványok megtekintése az MMC beépülő modullal](/dotnet/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in) című témakörben.
3. Importálja a **caentrate.cer** tanúsítványt a termeléshez és a **CAEntratetest.cer** teszteléshez a [Megbízható legfelső szintű hitelesítésszolgáltatók tárolóba](/dotnet/framework/wcf/feature-details/working-with-certificates#certificate-stores). (**A CAEntratetest.cer** a hitelesítésszolgáltató által biztosított legfelső szintű hitelesítésszolgáltatói tanúsítvány.)
4. A Vezérlőpulton nyissa meg **a Windows-szolgáltatások be- és kikapcsolása** című részt, vagy nyissa meg a **Kiszolgálókezelő** \> **Szerepkörök és szolgáltatások hozzáadása** a kiszolgáló operációs rendszeréhez (OS) elemre, és kapcsolja be az Internet Information Services (IIS) funkcióit:

    - Webkezelő eszközök
        - IIS menedzsment concole
    - Világszintű webszolgáltatások
        - Alkalmazásfejlesztési funkciók
            - .NET Bővíthetőség 4,7 (vagy 4,8)
            - ÁSPISKÍGYÓ
            - ASP.NET 4.7 (vagy 4.8.)
            - CGI
            - ISAPI-bővítmények
            - ISAPI szűrők
        - Gyakori HTTP-funkciók
            - Alapértelmezett dokumentum
            - Könyvtárböngészés
            - HTTP-hibák
            - Statikus tartalom
        - Egészség és diagnosztika
            - HTTP naplózás
            - Nyomkövetés
        - Teljesítményjellemzők
            - Statikus tartalomtömörítés
        - Biztonság
            - Szűrés kérése

    ![Az IIS-funkciók bekapcsolása.](media/e-invoicing-ita-fatturapa-get-started-turnon-features.png)

### <a name="set-up-the-sdi-proxy-service-in-iis"></a>Az SDI-proxy szolgáltatás beállítása az IIS-ben

1. Az Microsoft Dynamics Életciklus-szolgáltatások (LCS) területen lépjen a Megosztott eszköz tárba, és válassza az Adatcsomag lehetőséget **eszköztípusként**.
2. Keresse meg **az Elektronikus számlázási szolgáltatás Sdi Proxy** parancsot, és töltse le a virtuális gépre.
3. Konfigurálja a szolgáltatást.

    1. Csomagolja ki a **letöltött Elektronikus számlázási szolgáltatás Sdi Proxy** archív mappáját.
    2. Az **src \\ FattureService** mappában nyissa meg az **appsettings.json** fájlt, és állítsa be a következő paramétereket:

        - **KeyVaultUri** – Adja meg annak a kulcstartónak a címét, amely a számlázási szolgáltatás ügyféltanúsítványát tárolja.
        - **TenantId** – Adja meg az ügyfél bérlőjének globálisan egyedi azonosítóját (GUID).
        - **EnvironmentId** – Adja meg az LCS-környezet azonosítóját.
        - **ClientId** – Adja meg a köztes szolgáltatások alkalmazásregisztrációjának alkalmazásazonosítóját az ügyfél bérlőjében.
        - **ClientCertificateName** – Adja meg az S2S tanúsítvány nevét a kulcstartóban.
        - **SecurityServiceClientOptions.Endpoint** – Adja meg a biztonsági szolgáltatás URL-címét.
        - **SecurityServiceClientOptions.Resource** – Adja meg azt a hatókört, amelyhez be szeretné szerezni a jogkivonatot.
        - **SzámlázásServiceClientOptions.Endpoint –** Adja meg a számlázási szolgáltatás végpontját. Ennek az értéknek ugyanaznak a végpontnak kell lennie, amelyet az RCS és a Finance használ.
        - **SzámlázásServiceClientOptions.ServiceEnvironmentId –** Adja meg a szolgáltatási környezet nevét. Ennek az értéknek kell lennie a pénzügyi környezetének.
        - **NotificationsFolder** – Adja meg azt a mappát, amelybe a bejövő értesítési fájlokat menteni szeretné.

    3. A **web.config** fájlban keresse meg a következő sort, és adja hozzá a proxykiszolgáló tanúsítványának ujjlenyomatát.

        `<serviceCertificate findValue="[certificate thumbprint]" storeLocation="LocalMachine" storeName="My" x509FindType="FindByThumbprint">`

        > [!TIP]
        > Amikor a rendszer élesbe kerül, módosíthatja a web.config fájl egyes értékeit, hogy csökkentse az összegyűjtött naplóadatok mennyiségét, és segítsen megtakarítani a lemezterületet. A **\<system.diagnostics\>\<source\>** csomópontban módosítsa a **switchValue értékét** **Kritikus,Hiba** értékre. További információ: [MS Service Trace Viewer](/dotnet/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe).

4. Nyissa meg az IIS-kezelőt. A bal oldali fán maradjon a gyökércsomópontban. A jobb oldalon válassza a **Kiszolgálótanúsítványok** lehetőséget.

    ![A szolgáltatási tanúsítványok kiválasztása az IIS-kezelőben.](media/e-invoicing-ita-fatturapa-get-started-proxy-cert-1.png)

5. Nyissa meg a menüt, és válassza a **Importálás** lehetőséget.
6. A **Tanúsítvány importálása** párbeszédpanel **Tanúsítványfájl (.pfx)** mezőjében adja meg a proxykiszolgálói tanúsítvány .pfx fájljának elérési útját.

    ![A proxyszolgáltatás tanúsítványfájljának megadása.](media/e-invoicing-ita-fatturapa-get-started-proxy-cert-2.png)

7. Jelölje ki és tartsa lenyomva (vagy kattintson a jobb gombbal) **a Webhelyek** elemre, majd válassza a Webhely hozzáadása **lehetőséget**.
8. A **Webhely hozzáadása** párbeszédpanel **Webhelynév** mezőjében adja meg a webhely nevét.
9. A **Fizikai elérési út** mezőben mutasson az **src \\ FattureService** mappára.
10. A **Kötés típusa** mezőben válassza a **https** lehetőséget.
11. A **Gazdagép neve** mezőben adja meg az állomás nevét.
12. Hagyja az **IP-címet** és a Port **mezőket** az alapértelmezett értékekre állítva.
13. Győződjön meg arról, hogy a **Kiszolgálónév-indikáció megkövetelése** jelölőnégyzet be van jelölve, mert az SDI nem támogatja ezt a technológiát.
14. Az **SSL-tanúsítvány** mezőben jelölje ki az importált proxykiszolgáló-tanúsítványt.
15. Az **Alkalmazáskészlet** mezőben adjon meg egy készletet a webhelyhez, és jegyezze fel a nevét (például **SdiAppPool**).

    ![Weboldal hozzáadása.](media/e-invoicing-ita-fatturapa-get-started-proxy-iis-setup-1.png)

16. Miután befejezte a webhely létrehozását, nyissa meg az **SSL-beállítások** menüt.

    ![Az SSL-beállítások menüjének megnyitása.](media/e-invoicing-ita-fatturapa-get-started-proxy-iis-setup-2.png)

17. Jelölje be az **SSL megkövetelése** jelölőnégyzetet, majd az **Ügyféltanúsítványok** mezőben válassza a **Igény** lehetőséget.

    ![SSL-beállítások konfigurálása.](media/e-invoicing-ita-fatturapa-get-started-proxy-iis-setup-3.png)

18. Nyissa meg **a Címtárböngészés** lehetőséget, és válassza a **Engedélyezés** lehetőséget.
19. Bármely webböngészőben látogasson el a **serverDNS/TrasmissioneFatture.svc** webhelyre. Meg kell jelennie a szolgáltatásról szóló szabványos oldalnak.

    ![A szolgáltatás ellenőrzése böngészőben.](media/e-invoicing-ita-fatturapa-get-started-proxy-open-browser.png)

20. Hozza létre a következő mappákat a naplók és fájlok tárolásához:

    - **C: \\ Naplók \\** – Tárolja a naplófájlokat itt. Ezeket a fájlokat az [MS Service Trace Viewer tekintheti](/dotnet/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe) meg.
    - **C: \\ Fájlok – Tárolja az összes \\** válaszfájlt itt.

21. A Fájlkezelőben biztosítson **hozzáférést a NETWORK SERVICE és az** **IIS AppPool \\ SdiAppPool** (vagy az **IIS AppPool \\ DefaultAppPool,** ha az alapértelmezett készlet használatával) a **Naplók és fájlok** **mappához**.

    1. Jelölje ki és tartsa lenyomva (vagy kattintson a jobb gombbal) az egyik mappára, majd válassza a **Tulajdonságok** lehetőséget.
    2. A **Tulajdonságok** párbeszédpanel Biztonság **lapján válassza a Szerkesztés** **lehetőséget**.
    3. Adja hozzá a felhasználókat, ha nem szerepelnek a listában.
    4. Ismételje meg az 1–3. lépést a másik mappához.

    ![Engedélyek hozzáadása a szolgáltatás felhasználójához.](media/e-invoicing-ita-fatturapa-get-started-proxy-add-user.png)

## <a name="privacy-notice"></a>Adatvédelmi nyilatkozat 

Az olasz elektronikus számla funkció engedélyezése **korlátozott** adatok küldését teheti szükségessé. Ezek az adatok tartalmazzák a szervezet adóregisztrációs azonosítóját. A rendszergazda engedélyezheti és letilthatja az olasz elektronikus számla funkciót. A funkció letiltásához kövesse az alábbi lépéseket.

1. Menjen a **Szervezeti adminisztráció** \> **Beállítás** \> **Elektronikus dokumentumparaméterek** lehetőségre.
2. A **Szolgáltatások** lapon jelölje ki az olasz elektronikus számla funkciót tartalmazó sorokat, **majd válassza a** **Letiltás most lehetőséget**.

Az ezekből a külső rendszerekből ebből a Dynamics 365 online szolgáltatásba importált adatokra [adatvédelmi nyilatkozatunk vonatkozik](https://go.microsoft.com/fwlink/?LinkId=512132). További információért tekintse meg az ország-/régióspecifikus funkciódokumentáció "Adatvédelmi nyilatkozat" című szakaszát.

## <a name="additional-resources"></a>További erőforrások

- [Elektronikus számlázás áttekintése](e-invoicing-service-overview.md)
- [Első lépések az elektronikus számlázási szolgáltatás adminisztrálása során](e-invoicing-get-started-service-administration.md)
- [Első lépések az elektronikus számlázási használata során](e-invoicing-get-started.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
