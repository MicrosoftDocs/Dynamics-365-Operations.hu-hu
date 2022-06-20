---
title: Az olasz És az SDI közvetlen integrációjának beállítása
description: Ez a cikk segítséget nyújt az Elektronikus számlázás olaszországi modulban történő első lépéséhez, valamint az olasz ÁtturaPA és az Árfolyamrendszer (SDI) közvetlen integrációjának beállításhoz.
author: abaryshnikov
ms.date: 01/15/2022
ms.topic: article
audience: Application User, Developer
ms.reviewer: kfend
ms.search.region: Global
ms.author: abaryshnikov
ms.search.validFrom: 2021-10-18
ms.dyn365.ops.version: AX 10.0.20
ms.openlocfilehash: 510cf05e7bbc925478f9a1a4ea2ea27fe397c570
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8853192"
---
# <a name="set-up-direct-integration-of-italian-fatturapa-with-sdi"></a>Az olasz És az SDI közvetlen integrációjának beállítása

[!include [banner](../includes/banner.md)]

> [!IMPORTANT]
> Lehet, hogy az olaszországi Microsoft Dynamics elektronikus számlázás jelenleg nem támogat minden olyan funkciót, amely elérhető az elektronikus számlákhoz a 365 Pénzügy és a Pénzügyi modulban Dynamics 365 Supply Chain Management.

Ez a cikk olyan információkat tartalmaz, amelyek segítséget nyújtnak az olaszországi elektronikus számlázással kapcsolatos első lépésekhez a Pénzügy és az Ellátásilánc-kezelés modulban. Ez a varázsló végigvezeti a konfigurációs lépéseken, amelyek ország-/területfüggőek az RCS (Regulatory Configuration Services) szolgáltatásokban. Ezek a lépések kiegészítik az [Első lépések az elektronikus számlázással modulban ismertetett lépéseket](e-invoicing-get-started.md).

## <a name="prerequisites"></a>Előfeltételek

A cikk lépéseit csak akkor lehet végrehajtani, ha teljesülnek a következő előfeltételek:

- Az Elektronikus számlázás első [lépései modulban kell végrehajtani a szükséges lépéseket](e-invoicing-get-started.md).
- Importálja **az olasz ExportálásturaPA (IT)** elektronikus számlázási funkciót az RCS-be a globális tárházból. A további tudnivalókat [lásd az Elektronikus számlázás importálása a Microsoft konfigurációs szolgáltató](e-invoicing-get-started.md#import-an-electronic-invoicing-feature-from-the-microsoft-configuration-provider) szakaszának "Első lépések az elektronikus számlázással" című részében.
- Hivatkozások hozzáadása a szükséges tanúsítványokból a szolgáltatási környezetbe. A szükséges tanúsítványok közé tartozik a digitális aláírási tanúsítvány, a hitelesítésszolgáltatói tanúsítvány és az ügyféltanúsítvány. A további tudnivalókat [lásd az](e-invoicing-get-started-service-administration.md#create-a-digital-certificate-secret) "Elektronikus számlázás szolgáltatásfelügyelet – Első lépések" szakasz digitális tanúsítvány titkos létrehozása című részében.

## <a name="country-specific-configuration-for-the-italian-fatturapa-it-electronic-invoicing-feature"></a>Országspecifikus konfiguráció az olasz MelluraPA (IT) elektronikus számlázás funkcióhoz

A következő eljárásokat kell végrehajtani, mielőtt az alkalmazásbeállításokat a kapcsolódó Pénzügy vagy ellátásilánc-kezelés alkalmazásra telepíte.

Ez a szakasz kiegészíti [az](e-invoicing-get-started.md#country-specific-configuration-of-application-setup) "Elektronikus számlázással" című cikk alkalmazásbeállítási szakaszának Országspecifikus konfigurációját.

### <a name="create-a-new-feature"></a>Új funkció létrehozása

1. Bejelentkezés az RCS alkalmazásba.
2. Az Elektronikus jelentés **munkaterület** Konfigurációk **területen** jelölje meg aktívként a vállalat konfigurációszolgáltatóját.
3. A **Globalizációs funkció** munkaterületen a **Funkciók** szakaszban válassza ki az **Elektronikus számlázás** csempét.
4. Az Elektronikus számlázás **funkció lapon válassza a Hozzáadás** **·**\> meglévő funkció alapján lehetőséget.**·**
5. A **Microsoft konfigurációs szolgáltatónál válassza** **alapként az olaszLétrehozásáraturaPA (IT)** beállítást, adjon meg egy nevet, majd válassza **a Szolgáltatás létrehozása lehetőséget**.

### <a name="set-up-application-specific-parameters"></a>Alkalmazásfüggő paraméterek beállítása

1. Az Elektronikus **számlázás funkció lapon** válassza ki a szerkeszteni kívánt funkciót.
2. A **Verziók** lapon ellenőrizze, hogy a **Piszkozat** verzió ki van-e választva.
3. A Konfigurációk **lapon** válasszon egy konfigurációt, majd válassza ki az alkalmazásspecifikus **paramétereket**.
4. A Keresések **szakaszban** győződjön meg arról, **hogy be van jelölve a Fordított költség alkategóriák** listája keresés.
5. A Feltételek **szakaszban** válassza a Hozzáadás **lehetőséget**.
6. Adja hozzá az egyes alkategóriákhoz a rendszerben meghatározott feltételeket, majd mentse a módosításokat.

    > [!NOTE]
    > A Név **oszlopban** adott **\*\*** **\*\*** érték helyett az Üres vagy a Nem üres helyőrző értéket lehet kiválasztani.

### <a name="configure-a-processing-pipeline-for-export"></a>Feldolgozási folyamat konfigurálása exportáláshoz

1. Az Elektronikus **számlázás funkció lapon** válassza ki a szerkeszteni kívánt funkciót.
2. A Beállítások **lapon válassza ki az Értékesítési** **számlák, majd a Szerkesztés lehetőséget** **.**
3. A Feldolgozási **folyamat szakaszban** menjen végig a műveleteken, és állítsa be az összes szükséges mezőt:

    - A Dokumentum aláírása **művelet** Tanúsítvány **neve mezőjében** adja meg a Digitális aláírási tanúsítványt.
    - A Küldés **művelethez** állítsa be az **URL-cím és a** Tanúsítványok **mezőket**. A Tanúsítványok **mező** értéke tanúsítványlánc, az első a legfelső szintű hitelesítésszolgáltatói tanúsítvány (caentrate.cer), a második pedig az Ügyfél tanúsítvány.

4. Válassza az **Ellenőrzés** lehetőséget, ha gondoskodnia kell arról, hogy az összes kötelező mező be legyen állítva.
5. Mentse el a módosításokat, és zárja be az oldalt.
6. A Beállítások **lapon** válassza ki a Projekt **számláit**, majd a Szerkesztés **lehetőséget**.
7. Ismételje meg a 3–5. lépést a projektszámlákra.

### <a name="configure-the-processing-pipeline-for-import"></a>A feldolgozási folyamat konfigurálása importáláshoz

1. Az Elektronikus **számlázás funkció lapon** válassza ki a szerkeszteni kívánt funkciót.
2. A Beállítások **lapon** válassza a Számlák **importálása**, majd a Szerkesztés **lehetőséget**.
3. Az Adatcsatorna **szakasz** **Paraméterek** lapján az **Adatcsatorna** mezőben adjon meg egy karakterláncot.
4. Állítsa be **a** beállítások mezőit az Alkalmazhatósági szabályok lapon. Az alapértelmezett **csatornazáradékot** **·** **úgy használhatja, hogy az előző lépésben az Adatcsatorna mezőben beállított értéket az Érték mezőbe adja** át.

    ![Alkalmazhatósági szabályok beállítása](media/e-invoicing-ita-fatturapa-get-started-apprules-setup.png)

5. Válassza az **Ellenőrzés** lehetőséget, ha gondoskodnia kell arról, hogy az összes kötelező mező be legyen állítva.

### <a name="deploy-the-feature"></a>A funkció telepítése

1. A szolgáltatás befejezése, közzététele és üzembe helyezése a szolgáltatási környezetben. A további tudnivalókat [lásd az "](e-invoicing-get-started.md#deploy-the-electronic-invoicing-feature-to-service-environment) Elektronikus számlázással" című cikk "Az elektronikus számlázással kapcsolatos első lépések" szakaszának Elektronikus számlázás telepítése a szolgáltatási környezetben című részében.
2. A funkció telepítése a csatlakoztatott alkalmazásra. A további tudnivalókat [lásd az Elektronikus](e-invoicing-get-started.md#deploy-the-electronic-invoicing-feature-to-connected-application) számlázás telepítése a Csatlakoztatott alkalmazáshoz szakasz "Az Elektronikus számlázással" című cikknek.

### <a name="set-up-finance"></a>A Pénzügy beállítása

1. Jelentkezzen be a Pénzügyi környezetbe.
2. Az **Elektronikus jelentéskészítés** munkaterületen, a **Konfigurációszolgáltatók** szakaszban, válassza a **Microsoft** csempét.
3. A **Tárház globális** \> **megnyitási kiválasztása** \> **·**
4. A vevői számla környezetmodell **és** **szállítói számla importálási (IT) konfigurációjának kiválasztása és** importálása.
5. Menjen a **Szervezeti adminisztráció** \> **Beállítás** \> **Elektronikus dokumentumparaméterek** lehetőségre.
6. A Szolgáltatások **lapon** keresse meg és válassza ki az olasz **elektronikus számla** funkciót, majd jelölje be az **Engedélyezés** jelölőnégyzetet.
7. Az Elektronikus **dokumentum lapon győződjön meg arról,** **·** **hogy** a vevői számlanapló és a projektszámla mezői be vannak állítva az Alkalmazás beállításainak konfigurálása című dokumentumban szereplő adatok szerint.[...](e-invoicing-get-started.md#configure-the-application-setup)

### <a name="set-up-vendor-invoice-import"></a>Szállítói számla importálásának beállítása 

1. A Vállalat konfigurációszolgáltatóját **a** Pénzügy szakaszban, **az** Elektronikus jelentések munkaterületén jelölje meg aktívként a vállalat konfigurációszolgáltatóját.
2. Válassza a **Jelentéskészítési konfigurációk** elemet.
3. Válassza ki a **Vevői számla környezetmodellt**, majd válassza a Konfiguráció **létrehozása lehetőséget**.
4. Válassza **a Származtatott névből: Vevői számla környezete, a Microsoft** lehetőséget származtatott konfiguráció létrehozásához.
5. A Vázlat **verzióban** válassza a Tervező **lehetőséget**.
6. Az Adatmodell **fában** válassza **a Modell leképezés adatforráshoz beállítását**.
7. Válassza a **Definíciók fa** DataChannel **,** majd a Tervező **lehetőséget**.
8. Bontsa ki **a helyi csatorna tárolóját az adatforrásfában** **\$\_.**
9. Az Érték **mezőben** válassza a Szerkesztés **lehetőséget**. 
10. Az adatcsatorna nevének beírása. A név legfeljebb 10 karakterből állhat. Meg kell egyeznie **az** RCS elektronikus számlázási funkciója adatcsatorna-paraméterének értékével.
11. Mentse a módosításokat, majd kattintson a Jelentéskészítési **konfigurációk –** \> **Befejezve konfigurációs verzió.**
12. Válassza a **Hozzáadás lehetőséget a Külső csatornák** lap **Csatornák** szakaszában **·**.
13. A Csatorna **mezőben** adja meg a **\$ Context Channel** értékét.
14. Írja be az értékeket a Leírás **és a** **Vállalat mezőkbe**.
15. A Dokumentum **környezete** mezőben válassza ki a vevői számla **környezetmodellből származó új konfigurációt**. A leképezés leírásának **Adatcsatorna-kontextusnak** kell lennie.
16. Válassza a **Források importálása** lapon a Hozzáadás **gombra**, majd állítsa be a következő értékeket:

    - **Név:** OutputFile
    - **Adatentitás neve:** Szállítói számla fejléce (**Adatentitás:** VendorInvoiceHeaderEntity)
    - **Modellleképezés:** Szállítói számla importálása (It)

> [!NOTE]
> Ha különböző forrásból importál szállítói számlákat, **\$ létrehozhat több külső csatornát és több származtatott konfigurációt, amelyek eltérő helyi csatornaértékekkel** rendelkezik. Előfordulhat például, hogy különböző jogi személyek szállítói számláit szeretné importálni.

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
3. Jelentkezzen be rendszergazdaként [az Azure-portálra](https://portal.azure.com).
4. Alkalmazásregisztráció létrehozása az SDI Proxy szolgáltatáshoz.

    1. Menjen az **alkalmazásregisztrációkhoz**, hozzon létre egy regisztrációt, majd állítsa be a következő értékeket:

        - **Név:** SDI proxy ügyfél
        - **Támogatott fióktípusok:** Csak az ebben a szervezeti könyvtárban található fiókok (egy bérlő)

    2. Válassza **a Regisztrálás** lehetőséget, majd válassza ki a most létrehozott alkalmazásregisztrációt.
    3. Menjen az **API-engedélyekhez**, és válassza a Támogatás **rendszergazdai hozzájárulását**.
    4. Menjen a Tanúsítványok **& tanúsítványhoz**, válassza a Tanúsítvány **feltöltése** lehetőséget, majd töltse fel a .cer tanúsítványfájlt az S2S-hitelesítéshez.
    5. Menjen az **Enterprise-alkalmazásokhoz**, és válassza ki a létrehozott alkalmazást.
    6. Az alkalmazásazonosító **(ügyfél-azonosító**) és **az objektumazonosító értékek mentése** az alkalmazás számára.
    7. A Számlázási szolgáltatás csapatának meg kell bizonyosodnie a szolgáltatáshoz való alkalmazás-hozzáférésről. A következő paraméterek értékeinek küldése a következőnek <D365EInvoiceSupport@microsoft.com>:

        - AAD bérlő azonosítója
        - LCS-környezet azonosítója
        - Pályázat azonosítója
        - Objektumazonosító

5. Az RCS szolgáltatásban vegye fel az alkalmazást a szolgáltatási környezet alkalmazáslistába.

    1. Ugrás a **Globalization features** \> **Environment** \> **Electronic Invoicing** \> **Service** környezetekhez, és válassza ki a környezetet.
    2. A Pályázatok **szakaszban** adjon egy sort a rácshoz, majd adja meg az alkalmazás nevét és objektumazonosítóját.

        ![Az alkalmazás hozzáadása a szolgáltatási környezethez.](media/e-invoicing-ita-fatturapa-get-started-add-app-to-env.png)

    3. Válassza a **Mentés, majd a Közzététel lehetőséget** **.**

### <a name="create-an-azure-virtual-machine"></a>Azure virtuális gép létrehozása

1. [Az Azure-portálon menjen](https://portal.azure.com) a **Virtuális gépekhez**, és válassza az **Új létrehozása lehetőséget**.
2. Válassza ki az **előfizetést** és az erőforráscsoportot az Alapokkal lapon. Az értékeknek annak az előfizetésnek és erőforráscsoportnak kell lennie, ahol a kulcs és a Blob tároló található.
3. Válassza ki a régiót. Ennek az értéknek annak a régiónak kell lennie, ahol a Pénzügyi környezet telepítve van.
4. Adja hozzá a rendszergazda felhasználónevét és jelszavát, majd mentse a kulcskulcsba.
5. A Bejövő portok **kiválasztása mezőben válassza a** HTTPS (443) **és** az RPD (3389) lehetőséget **·**.

    > [!NOTE]
    > Azt ajánljuk, hogy akkor tiltsa le **az RDP-portot (3389-es),** amikor a rendszer termelésbe kerül. Ha hibaelhárítás céljából a virtuális géphez (VM) kell kapcsolódnia, újra engedélyezheti.

    ![Az Alap lap mezőinek beállítása Egy Azure-ás virtuális gép létrehozásához.](media/e-invoicing-ita-fatturapa-get-started-create-vm-1.png)

6. A Speciális **gyorslap Lemezek** lapján **·** **jelölje be a Felügyelt lemez használata** jelölőnégyzetet. Hagyja a **jelölőnégyzetet** törölve az Elektronikus operációs rendszer lemeze jelölőnégyzetből.

    ![A Hajlékonylemezek lapon található mezők beállítása Egy Azure-beli virtuális gép létrehozásához.](media/e-invoicing-ita-fatturapa-get-started-create-vm-2.png)

7. A Hálózat **lap Nyilvános IP-mezőjében** **válassza** az Új létrehozása lehetőséget **.**

    ![A Hálózat lap mezőinek beállítása Azure-ás virtuális gép létrehozása érdekében](media/e-invoicing-ita-fatturapa-get-started-create-vm-3.png)

8. A Nyilvános **IP-cím** létrehozása párbeszédpanelEn, a **Ku** mezőcsoportban válassza a Szokásos **beállítást**. A Hozzárendelés **mezőcsoportban** válassza a Statikus **beállítást**.

    ![Nyilvános IP-cím létrehozása](media/e-invoicing-ita-fatturapa-get-started-create-vm-4.png)

9. A Kezelés **lapon törölje a** jelölést **az Automatikus leállítás** jelölőnégyzetből, ha le szeretné tiltani az automatikus leállítást.
10. Állítsa Manuális **beállításra a Vendég** **operációs** rendszer frissítése mezőt, majd állítsa be az egyéb irányelveket.
11. Tekintse át és hozza létre az VM-t.
12. Az új VM-példányon menjen a **hozzárendelt** \> **identitásrendszerhez**, és állítsa **be az Állapot** beállítást Be állapotra.**·**
13. A kulcshoz való hozzáférés megadása az VM számára

    1. A kulcs kulcsában menjen a Hozzáférés-vezérlési **szerepkör** \> **hozzárendeléseihez.**
    2. Válassza a **Szerepkör-hozzárendelés hozzáadása** lehetőséget, majd állítsa be a következő mezőket:

        1. A Szerepkör **mezőben** adja meg a **Kulcs – Felhasználóbarát felhasználó beállítását**.
        2. A Hozzáférés **hozzárendelése mezőben** adja meg a **virtuális gépet**.
        3. Az Előfizetés **mezőben** adja meg az előfizetést.
        4. A Kijelölés **mezőben** adja meg az VM-t.

    3. Ugrás a Hozzáférési **irányelvekhez**.
    4. Válassza a **Hozzáférési irányelv hozzáadása** gombra, majd állítsa be a következő mezőket:

        1. A Kiválasztott **alapvető mezőben** válassza ki az VM-t.
        2. A Tanúsítvány **szakaszban** válassza a **Lista** és az Engedélyek **bejede** lehetőséget.

14. [Az Azure-portálon menjen](https://portal.azure.com)**a nyilvános IP-címekhez, és válassza ki az VM-ban létrehozott IP-címet**.
15. Menjen a **konfigurációhoz**, és állítsa be a tartománynév-rendszer (DNS) nevét.

### <a name="prepare-the-proxy-service-environment"></a>A proxy szolgáltatási környezetének előkészítése

Hajtsa végre a következő lépéseket ezen a számítógépen, ahol a proxyszolgáltatás található.

1. Csatlakozás az VM-hez távoli asztali kapcsolat segítségével
2. Nyissa meg a helyi számítógép tanúsítványának be- és betárolóját. A további tudnivalókat lásd [: Tanúsítványok megtekintése az HHC be- és utántával](/dotnet/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in).
3. Importálja **a caentrate.cer** tanúsítványt a **termeléshez, és a CAEntratetest.cer**[tanúsítványt a megbízható gyökér hitelesítésszolgáltató-üzletbe való teszteléshez](/dotnet/framework/wcf/feature-details/working-with-certificates#certificate-stores). (A **CAEntratetest.cer** a hatóság által megadott legfelső szintű hitelesítésszolgáltatói tanúsítvány.)
4. A Vezérlőpult Windows-funkcióinak **be**- és kikapcsolása, **illetve a kiszolgálói** \> **operációs** rendszer Szerepkör és szolgáltatások hozzáadása funkciójának megnyitása a Vezérlőpulton, illetve az Internet Information Services (IIS) szolgáltatásainak bekapcsolásán:

    - Webkezelési eszközök
        - IIS-kezelési konole
    - Webes szolgáltatások az egész világra kiterjedően
        - Alkalmazásfejlesztési funkciók
            - .NET extensibility 4.7 (vagy 4.8)
            - ASP
            - ASP.NET 4.7 (vagy 4.8)
            - CGI
            - ISAPI-bővítmények
            - ISAPI-szűrők
        - GYAKORI HTTP-funkciók
            - Alapértelmezett dokumentum
            - Címtár tallózása
            - HTTP-hibák
            - Statikus tartalom
        - Egészség és diagnosztika
            - HTTP-naplózás
            - Nyomkövetés
        - Teljesítményszolgáltatásokat
            - Statikus tartalomtömörítés
        - Biztonság
            - Kérelemszűrés

    ![Az IIS szolgáltatásainak bekapcsolása.](media/e-invoicing-ita-fatturapa-get-started-turnon-features.png)

### <a name="set-up-the-sdi-proxy-service-in-iis"></a>Az SDI Proxy szolgáltatás beállítása az IIS szolgáltatásban

1. A Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásban menjen a Megosztott eszköz tárba, **és válassza ki az** Adatcsomagot eszköztípusként.
2. Az **elektronikus számlázási szolgáltatás Sdi Proxy** megkeresása és letöltése az VM-be.
3. A szolgáltatás konfigurálása

    1. Az elektronikus **számlázási szolgáltatás letöltött Sdi Proxy archív** mappájának kibontása.
    2. Nyissa meg **az appsettings.json\\** **fájlt a src** Egyesetservice mappában, és állítsa be a következő paramétereket:

        - **KeyVaultUri** – adja meg a számlázási szolgáltatás ügyfélbizonyítványát tároló kulcscímet.
        - **Bérlőazonosító** – adja meg a vevő bérlőjéhez globálisan egyedi azonosítót (GUID).
        - **EnvironmentId** – adja meg az LCS-környezet azonosítóját.
        - **ClientId** – a közbenső szolgáltatások alkalmazásregisztrációs azonosítójának megadása a vevő bérlőjében.
        - **ClientCertificateName** – adja meg a kulcskulcsban az S2S-tanúsítvány nevét.
        - **SecurityServiceClientOptions.Endpoint** – a biztonsági szolgáltatás URL-címének megadása.
        - **SecurityServiceClientOptions.Resource** – adja meg azt a hatókört, amely számára be kell szerezni a tokent.
        - **InvoicingServiceClientOptions.Endpoint** – a számlázási szolgáltatás végpontjának megadása. Ennek az értéknek meg kell egy lennie az RCS és a Pénzügy esetében használt végpontnak.
        - **InvoicingServiceClientOptions.ServiceEnvironmentId** – adja meg a szolgáltatási környezet nevét. Ennek az értéknek a pénzügyi környezet nevének kell lennie.
        - **NotificationsFolder** – a bejövő értesítési fájlok mentésére vonatkozó mappa megadása.

    3. **A web.config fájlban** keresse meg a következő sort, és adja hozzá a proxykiszolgáló tanúsítványának ujjlenyomatát.

        `<serviceCertificate findValue="[certificate thumbprint]" storeLocation="LocalMachine" storeName="My" x509FindType="FindByThumbprint">`

        > [!TIP]
        > Ha a rendszer termelésbe kerül, a web.config fájlban található értékek módosítva csökkenthetők az összegyűjtött naplóinformációk mennyisége, és csökkenthető a lemezterület. A csomópontban **\<system.diagnostics\>\<source\>** módosítsa **a switchValue értékét** Kritikus,Hiba **értékre**. A további tudnivalókat lásd az [MS Szolgáltatás nyomkövetési megjelenítője oldalon](/dotnet/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe).

4. Nyissa meg az IIS-kezelőt. A bal oldali fában maradjon a gyökércsomópontban. Válassza a jobb oldalon a kiszolgáló **tanúsítványait**.

    ![Szolgáltatás-tanúsítványok kiválasztása az IIS-kezelőben](media/e-invoicing-ita-fatturapa-get-started-proxy-cert-1.png)

5. Nyissa meg a menüt, és válassza az Importálás **parancsot**.
6. Adja meg **a** Tanúsítvány importálása **párbeszédpanel Tanúsítványfájl (.pfx)** mezőjében a proxykiszolgáló tanúsítványának .pfx fájljának elérési útját.

    ![A proxyszolgáltatás tanúsítványfájlja.](media/e-invoicing-ita-fatturapa-get-started-proxy-cert-2.png)

7. Válassza ki és tartsa lenyomva a webhelyeket (**vagy** kattintson rá a jobb gombbal), majd válassza a **Webhely hozzáadása lehetőséget**.
8. A Webhely **hozzáadása párbeszédpanel** Webhely **neve mezőjébe** írja be a webhely nevét.
9. A Fizikai **elérési út** mezőben mutasson **a src\\ Arra a** mappára, amelybe a tetkre mutat.
10. A Kötéstípus **mezőben** válassza a **https lehetőséget**.
11. Az Állomásnév **mezőben** adja meg az állomás nevét.
12. Hagyja az **IP-címet és** **a portmezőket** az alapértelmezett értékekre állítva.
13. Győződjön meg arról, hogy **a** Kiszolgálónév jelzése megkövetelése jelölőnégyzetből törölve van a jelölés, mert az SDI nem támogatja ezt a technológiát.
14. Az SSL-tanúsítvány **mezőben** válassza ki az importált proxykiszolgálói tanúsítványt.
15. Az Alkalmazáskészlet **mezőben** adjon meg egy készletet a hely számára, és jegyezze fel a nevét (**például SdiAppPool**).

    ![Webhely hozzáadása](media/e-invoicing-ita-fatturapa-get-started-proxy-iis-setup-1.png)

16. Miután befejezte a webhely létrehozását, nyissa meg az SSL-beállítások **menüt**.

    ![Az SSL-beállítások menü megnyitása](media/e-invoicing-ita-fatturapa-get-started-proxy-iis-setup-2.png)

17. Jelölje be **az SSL megkövetelt** jelölőnégyzetet, **majd** az Ügyféltanúsítványok mezőcsoportban válassza a Kötelező **lehetőséget**.

    ![SSL-beállítások konfigurálása](media/e-invoicing-ita-fatturapa-get-started-proxy-iis-setup-3.png)

18. Nyissa meg **a Címtár tallózást**, és válassza az Engedélyezés **lehetőséget**.
19. Bármelyik webböngészőben menjen **a serverDNS/TrasmissioneFatture.svc fájlra**. Meg kell jelennie a szolgáltatásra vonatkozó szokásos lapnak.

    ![A szolgáltatás ellenőrzése böngészőben](media/e-invoicing-ita-fatturapa-get-started-proxy-open-browser.png)

20. Hozza létre a következő mappákat a naplók és fájlok tárolására:

    - **C:\\ Logs\\** – itt tárolja a naplófájlokat. Ezeket a fájlokat az [MS Service Trace Viewer segítségével lehet megtekinteni](/dotnet/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe).
    - **C:\\ Files\\** – az összes válaszfájlt tárolja itt.

21. A Fájlkezelőben **adja meg a HÁLÓZATI SZOLGÁLTATÁS** **és az IIS AppPool\\ SdiAppPool (vagy** az IIS AppPool **DefaultAppPool\\**) **·** **hozzáférést** az Alapértelmezett csoport használata esetén a Naplók és fájlok mappához.

    1. Jelölje ki és tartsa lenyomva az egyik mappát (vagy kattintson rá a jobb gombbal), majd válassza a Tulajdonságok **parancsot**.
    2. A Tulajdonságok **párbeszédpanel** Biztonsági **lapján** válassza a Szerkesztés **lehetőséget**.
    3. Vegye fel a felhasználókat, ha nem szerepelnek a listán.
    4. Ismételje meg az 1–3. lépést a másik mappával.

    ![Engedélyek hozzáadása a szolgáltatás felhasználója számára](media/e-invoicing-ita-fatturapa-get-started-proxy-add-user.png)

## <a name="privacy-notice"></a>Adatvédelmi nyilatkozat 

Az olasz elektronikus **számla funkció engedélyezéséhez** korlátozott adatok küldhetik el a szolgáltatást. Ezek az adatok tartalmazzák a szervezet adóregisztrációs azonosítóját. A rendszergazda engedélyezheti és letilthatja az olasz elektronikus számla funkciót. A funkció letiltásához kövesse az alábbi lépéseket.

1. Menjen a **Szervezeti adminisztráció** \> **Beállítás** \> **Elektronikus dokumentumparaméterek** lehetőségre.
2. A Szolgáltatások **lapon** jelölje ki azokat a sorokat, **amelyek tartalmazzák az olasz elektronikus** számla funkciót, majd válassza a **Disable now lehetőséget**.

A külső rendszerekből ebbe a Dynamics 365 online szolgáltatásba importált adatokra az adatvédelmi nyilatkozatunk [vonatkozik](https://go.microsoft.com/fwlink/?LinkId=512132). A további tudnivalókat lásd az ország-/régióspecifikus funkciódokumentáció "Adatvédelmi nyilatkozat" szakaszában.

## <a name="additional-resources"></a>További erőforrások

- [Elektronikus számlázás áttekintése](e-invoicing-service-overview.md)
- [Első lépések az elektronikus számlázási szolgáltatás adminisztrálása során](e-invoicing-get-started-service-administration.md)
- [Első lépések az elektronikus számlázási használata során](e-invoicing-get-started.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
