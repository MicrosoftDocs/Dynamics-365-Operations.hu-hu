---
title: Telepítési irányelvek Norvégia készpénzjegyzékéhez (legacy)
description: Ez a cikk egy telepítési útmutató, amely bemutatja, hogyan lehet engedélyezni Microsoft Dynamics 365 Commerce Norvégia honosítását.
author: EvgenyPopovMBS
ms.date: 12/20/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2018-2-28
ms.openlocfilehash: 7a6450215f152779428d3b0fd83bf09761e2ad98
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8894462"
---
# <a name="deployment-guidelines-for-cash-registers-for-norway-legacy"></a>Telepítési irányelvek Norvégia készpénzjegyzékéhez (legacy)

[!include [banner](../includes/banner.md)]

Ez a cikk egy telepítési útmutató, amely bemutatja, hogyan lehet engedélyezni Microsoft Dynamics 365 Commerce Norvégia honosítását. A honosítás a Commerce összetevők több kiterjesztésből áll. A bővítményekben például ki lehet nyomtatni az egyéni mezőket a nyugtákra, regisztrálni lehet a további könyvvizsgálati eseményeket, értékesítési tranzakciókat és fizetési tranzakciókat a pénztárban, digitálisan alá lehet írni az értékesítési tranzakciókat, és helyi formátumban lehet X- és Z-jelentéseket nyomtatni. A Norvégiához való honosítással kapcsolatos további tudnivalókat [lásd a Pénztárgép szolgáltatás Norvégiához](./emea-nor-cash-registers.md).

Ez a minta a Kiskereskedelmi szoftverfejlesztői csomag (SDK) része. Az SDK-ről a [Retail szoftverfejlesztői csomag (SDK) architektúrája nyújt tájékoztatást](../dev-itpro/retail-sdk/retail-sdk-overview.md).

Ez a minta a Commerce runtime (), a Retail Server és CRT a POS bővítményeiből áll. A minta futtatásához módosítania CRT és fel kell építenie a, a Retail Server és a POS-projekteket. Javasoljuk, hogy egy nem módosított Retail SDK készlet használhatja az ebben a cikkben leírt módosításokat. Javasoljuk továbbá, hogy olyan forrás-ellenőrzési rendszert (például Microsoft Visual Studio Online – VSO) használjon, ahol még nem módosultak a fájlok.

> [!NOTE]
> A Commerce 10.0.8 és az felette található Retail Server kiszolgáló neve Commerce Scale Unit. Mivel ez a cikk az alkalmazás több korábbi verziójára is vonatkozik, *a Retail Server* a cikk számos verziójára alkalmazható.
>
> A cikk eljárásának egyes lépései az Ön által használt Commerce rendszer verziójától függően eltérőek. A további tudnivalókat lásd [: Újdonságok és módosulás a következőben Dynamics 365 Retail](../get-started/whats-new.md):

### <a name="using-certificate-profiles-in-commerce-channels"></a>Tanúsítványprofilok használata a Commerce-csatornákban

A Commerce rendszer 10.0.15-ös [és újabb verzióiban a felhasználó által definiált tanúsítványprofilok használhatók a kiskereskedelmi áruházak olyan szolgáltatása számára,](./certificate-profiles-for-retail-stores.md) amely támogatja a kapcsolat nélküli (offline) kapcsolatot, ha a KulcsLevél vagy a Commerce Headquarters nem érhető el. A funkció kiterjeszti a [Kiskereskedelmi csatornák kezelése szolgáltatást](../dev-itpro/manage-secrets.md).

A következő lépések szerint alkalmazhatja ezt CRT a funkciót a bővítményben.

1. Új bővítményprojekt CRT létrehozása (C# osztálytár projekttípus). Használja a Retail szoftverfejlesztői csomag (SDK) mintasablonját (RetailSDK\SampleExtensions\CommerceRuntime).

2. Egyéni kezelő hozzáadása a CertificateSignatureServiceRequest számára a SzekvenciálisSignatureRegister projektben.

3. Titkos hívás olvasása `GetUserDefinedSecretCertificateServiceRequest` profileId paraméterrel megadott konstruktor használatával. Elindítja a tanúsítványprofilok beállításaival való munkát. A beállítások alapján a tanúsítványt vagy az Azure-kulcsból, vagy a helyi számítógép tárolóiból olvassa be a rendszer.

    ```csharp
    GetUserDefinedSecretCertificateServiceRequest getUserDefinedSecretCertificateServiceRequest = new GetUserDefinedSecretCertificateServiceRequest(profileId: "ProfileId", secretName: null, thumbprint: null, expirationInterval: null);
    GetUserDefinedSecretCertificateServiceResponse getUserDefinedSecretCertificateServiceResponse = request.RequestContext.Execute<GetUserDefinedSecretCertificateServiceResponse>(getUserDefinedSecretCertificateServiceRequest);

    X509Certificate2 Certificate = getUserDefinedSecretCertificateServiceResponse.Certificate;
    ```

4. A tanúsítvány beolvassa, folytassa az adatalá aláírásával.

5. A bővítményprojekt CRT összeállítása.

6. A kimeneti osztálytár másolása és beillesztése a...\RetailServer\webroot\bin\Ext könyvtárba manuális tesztelés céljából.

7. A CommerceRuntime.Ext.config fájlban frissítse a kiterjesztés-összeállítási szakaszt az egyéni tár adataival.

## <a name="development-environment"></a>Fejlesztői környezet

A következő eljárásokkal fejlesztői környezetet állíthat be, így tesztelheti és bővítheti a mintát.

### <a name="the-crt-extension-components"></a>A CRT kiterjesztési összetevők

A CRT kiterjesztési összetevők a mintában vannak CRT. A következő eljárások CRT **befejezéséhez nyissa meg a CommerceRuntimeSamples.sln** megoldást a **RetailSdk\\ SampleExtensions\\ CommerceRuntime** alatt.

#### <a name="receiptsnorway-component"></a>ReceiptsNorway összetevő

1. Keresse meg **a Runtime.Extensions.ReceiptsNorway** projektet, és építse fel.
2. **Az Extensions.ReceiptsNorway\\ bin\\ hibakeresési** **mappában keresse meg a Contoso.Commerce.Runtime.ReceiptsNorway.dll** szerelvényfájlt.
3. A szerelvényfájl másolása a bővítmények CRT mappájába:

    - **Retail Server:** A szerelvény másolása **\\\\ a Microsoft Internet Information Services (IIS) Retail Server webhelyének bin ext** mappájába.
    - **Helyi CRT a Modern POS terminálon:** A **\\ szerelvény másolása a helyi ügyfélügynök helye alatti ext** CRT mappába.

4. A következő bővítmény-konfigurációs fájl megkeresve CRT:

    - **Retail Server:** **A fájl neve Commerceruntime.ext.config**, **és az IIS Retail Server webhely bin\\ ext** mappájában található.
    - **Helyi CRT a Modern POS terminálon:** **A fájl neve CommerceRuntime.MPOSOffline.Ext.config**, CRT és a helyi ügyfélügynök helye alatt található.

5. A változás CRT regisztrálása a kiterjesztés konfigurációs fájljában.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.ReceiptsNorway" />
    ```

    > [!WARNING]
    > Ne **szerkessze** a commerceruntime.config és a CommerceRuntime.MPOSOffline.config fájlokat. Ezek a fájlok nem testreszabott fájlok.

#### <a name="salespaymenttransext-component"></a>SalesPaymentTransExt összetevő

1. Keresse meg **és építse fel a Runtime.Extensions.SalesPaymentTransExt** projektet.
2. Az Extensions.SalesPaymentTransExt **bin\\ Hibakeresés\\** mappában keresse meg a Contoso.Commerce.Runtime.SalesPaymentTransExt.dll **szerelvényfájlt**.
3. A szerelvényfájl másolása a bővítmények CRT mappájába:

    - **Retail Server:** A szerelvény másolása **\\\\ az IIS Retail Server webhely bin ext** mappájába.
    - **Helyi CRT a Modern POS terminálon:** A **\\ szerelvény másolása a helyi ügyfélügynök helye alatti ext** CRT mappába.

4. A következő bővítmény-konfigurációs fájl megkeresve CRT:

    - **Retail Server:** **A fájl neve Commerceruntime.ext.config**, **és az IIS Retail Server webhely bin\\ ext** mappájában található.
    - **Helyi CRT a Modern POS terminálon:** **A fájl neve CommerceRuntime.MPOSOffline.Ext.config**, CRT és a helyi ügyfélügynök helye alatt található.

5. A változás CRT regisztrálása a kiterjesztés konfigurációs fájljában.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.SalesPaymentTransExt" />
    ```

    > [!WARNING]
    > Ne **szerkessze** a commerceruntime.config és a CommerceRuntime.MPOSOffline.config fájlokat. Ezek a fájlok nem testreszabott fájlok.

#### <a name="xzreportsnorway-component"></a>XZReportsNorway összetevő

1. Keresse meg **a Runtime.Extensions.XZReportsNorway** projektet, és építse fel.
2. Az Extensions.XZReportsNorway **bin\\ Hibakeresés\\** mappában keresse meg a Contoso.Commerce.Runtime.XZReportsNorway.dll **szerelvényfájlt**.
3. A szerelvényfájl másolása a bővítmények CRT mappájába:

    - **Retail Server:** A szerelvény másolása **\\\\ az IIS Retail Server webhely bin ext** mappájába.
    - **Helyi CRT a Modern POS terminálon:** A **\\ szerelvény másolása a helyi ügyfélügynök helye alatti ext** CRT mappába.

4. A következő bővítmény-konfigurációs fájl megkeresve CRT:

    - **Retail Server:** **A fájl neve Commerceruntime.ext.config**, **és az IIS Retail Server webhely bin\\ ext** mappájában található.
    - **Helyi CRT a Modern POS terminálon:** **A fájl neve CommerceRuntime.MPOSOffline.Ext.config**, CRT és a helyi ügyfélügynök helye alatt található.

5. A változás CRT regisztrálása a kiterjesztés konfigurációs fájljában.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.XZReportsNorway" />
    ```

    > [!WARNING]
    > Ne **szerkessze** a commerceruntime.config és a CommerceRuntime.MPOSOffline.config fájlokat. Ezek a fájlok nem testreszabott fájlok.

# <a name="application-update-4"></a>[4-as alkalmazásfrissítés](#tab/app-update-4)

#### <a name="registerauditevent-sample-component"></a>RegisterAuditEvent mintaösszetevő

1. Keresse meg **a Runtime.Extensions.RegisterAuditEventSample** projektet, és építse fel.
2. A Extensions.RegisterAuditEventSample **\\ bin\\ hibakeresési** **mappában keresse meg a Contoso.Commerce.Runtime.RegisterAuditEventSample.dll** szerelvényfájlt.
3. A szerelvényfájl másolása a bővítmények CRT mappájába:

    - **Retail Server:** A szerelvény másolása **\\\\ az IIS Retail Server webhely bin ext** mappájába.
    - **Helyi CRT a Modern POS terminálon:** A **\\ szerelvény másolása a helyi ügyfélügynök helye alatti ext** CRT mappába.

4. A következő bővítmény-konfigurációs fájl megkeresve CRT:

    - **Retail Server:** **A fájl neve Commerceruntime.ext.config**, **és az IIS Retail Server webhely bin\\ ext** mappájában található.
    - **Helyi CRT a Modern POS terminálon:** **A fájl neve CommerceRuntime.MPOSOffline.Ext.config**, CRT és a helyi ügyfélügynök helye alatt található.

5. A változás CRT regisztrálása a kiterjesztés konfigurációs fájljában.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.RegisterAuditEventSample" />
    ```

    > [!WARNING]
    > Ne **szerkessze** a commerceruntime.config és a CommerceRuntime.MPOSOffline.config fájlokat. Ezek a fájlok nem testreszabott fájlok.

#### <a name="salestransactionsignature-sample-component"></a>SalesTransactionSignature mintaösszetevő

1. A Runtime.Extensions.SalesTransactionSignatureSample **projekt** megkeresve.
2. **Az App.config fájl** módosítása az értékesítési tranzakciók aláírására használt tanúsítvány ujjlenyomatának, tárolóhelyének és üzletnevének megadásával.
3. A projekt összeállítása.
4. **Az Extensions.SalesTransactionSignatureSample\\ bin\\ Hibakeresés** mappában keresse meg a következő fájlokat:

    - A **Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll szerelvényfájl**
    - A **Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll.config konfigurációs** fájl

5. A fájlok másolása a bővítmények CRT mappájába:

    - **Retail Server:** A szerelvény másolása **\\\\ az IIS Retail Server webhely bin ext** mappájába.
    - **Helyi CRT a Modern POS terminálon:** A **\\ szerelvény másolása a helyi ügyfélügynök helye alatti ext** CRT mappába.

6. A következő bővítmény-konfigurációs fájl megkeresve CRT:

    - **Retail Server:** **A fájl neve Commerceruntime.ext.config**, **és az IIS Retail Server webhely bin\\ ext** mappájában található.
    - **Helyi CRT a Modern POS terminálon:** **A fájl neve CommerceRuntime.MPOSOffline.Ext.config**, CRT és a helyi ügyfélügynök helye alatt található.

7. A változás CRT regisztrálása a kiterjesztés konfigurációs fájljában.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureSample" />
    ```

    > [!WARNING]
    > Ne **szerkessze** a commerceruntime.config és a CommerceRuntime.MPOSOffline.config fájlokat. Ezek a fájlok nem testreszabott fájlok.

# <a name="application-update-5-and-later"></a>[5-ös vagy újabb alkalmazásfrissítés](#tab/app-update-5-and-later)

#### <a name="registerauditevent-sample-component"></a>RegisterAuditEvent mintaösszetevő

1. Keresse meg **a Runtime.Extensions.RegisterAuditEventSample** projektet, és építse fel.
2. A Extensions.RegisterAuditEventSample **\\ bin\\ hibakeresési** **mappában keresse meg a Contoso.Commerce.Runtime.RegisterAuditEventSample.dll** szerelvényfájlt.
3. A szerelvényfájl másolása a bővítmények CRT mappájába:

    - **Retail Server:** A szerelvény másolása **\\\\ az IIS Retail Server webhely bin ext** mappájába.
    - **Helyi CRT a Modern POS terminálon:** A **\\ szerelvény másolása a helyi ügyfélügynök helye alatti ext** CRT mappába.

4. A következő bővítmény-konfigurációs fájl megkeresve CRT:

    - **Retail Server:** **A fájl neve Commerceruntime.ext.config**, **és az IIS Retail Server webhely bin\\ ext** mappájában található.
    - **Helyi CRT a Modern POS terminálon:** **A fájl neve CommerceRuntime.MPOSOffline.Ext.config**, CRT és a helyi ügyfélügynök helye alatt található.

5. A változás CRT regisztrálása a kiterjesztés konfigurációs fájljában.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.RegisterAuditEventSample" />
    ```

    > [!WARNING]
    > Ne **szerkessze** a commerceruntime.config és a CommerceRuntime.MPOSOffline.config fájlokat. Ezek a fájlok nem testreszabott fájlok.

#### <a name="salestransactionsignature-sample-component"></a>SalesTransactionSignature mintaösszetevő

1. A Runtime.Extensions.SalesTransactionSignatureSample **projekt** megkeresve.
2. **Az App.config fájl** módosítása az értékesítési tranzakciók aláírására használt tanúsítvány ujjlenyomatának, tárolóhelyének és üzletnevének megadásával.
3. A projekt összeállítása.
4. **Az Extensions.SalesTransactionSignatureSample\\ bin\\ Hibakeresés** mappában keresse meg a következő fájlokat:

    - A **Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll szerelvényfájl**
    - A **Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll.config konfigurációs** fájl

5. A fájlok másolása a bővítmények CRT mappájába:

    - **Retail Server:** A szerelvény másolása **\\\\ az IIS Retail Server webhely bin ext** mappájába.
    - **Helyi CRT a Modern POS terminálon:** A **\\ szerelvény másolása a helyi ügyfélügynök helye alatti ext** CRT mappába.

6. A következő bővítmény-konfigurációs fájl megkeresve CRT:

    - **Retail Server:** **A fájl neve Commerceruntime.ext.config**, **és az IIS Retail Server webhely bin\\ ext** mappájában található.
    - **Helyi CRT a Modern POS terminálon:** **A fájl neve CommerceRuntime.MPOSOffline.Ext.config**, CRT és a helyi ügyfélügynök helye alatt található.

7. A változás CRT regisztrálása a kiterjesztés konfigurációs fájljában.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureSample" />
    ```

    > [!WARNING]
    > Ne **szerkessze** a commerceruntime.config és a CommerceRuntime.MPOSOffline.config fájlokat. Ezek a fájlok nem testreszabott fájlok.

#### <a name="salestransactionsignaturesamplemessages-component"></a>SalesTransactionSignatureSample.Messages összetevő

1. A Runtime.Extensions.SalesTransactionSignatureSample.Messages **projekt** megkeresve.
2. Az Extensions.SalesTransactionSignatureSample.Messages **bin\\ hibakeresési\\** mappában keresse meg a Contoso.Commerce.Runtime.SalesTransactionSignatureSample.Messages.dll **szerelvényfájlt**.
3. A szerelvényfájl másolása a bővítmények CRT mappájába:

    - **Retail Server:** A szerelvény másolása **\\\\ az IIS Retail Server webhely bin ext** mappájába.
    - **Helyi CRT a Modern POS terminálon:** A **\\ szerelvény másolása a helyi ügyfélügynök helye alatti ext** CRT mappába.

4. A következő bővítmény-konfigurációs fájl megkeresve CRT:

    - **Retail Server:** **A fájl neve Commerceruntime.ext.config**, **és az IIS Retail Server webhely bin\\ ext** mappájában található.
    - **Helyi CRT a Modern POS terminálon:** **A fájl neve CommerceRuntime.MPOSOffline.Ext.config**, CRT és a helyi ügyfélügynök helye alatt található.

5. A változás CRT regisztrálása a kiterjesztés konfigurációs fájljában.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureSample.Messages" />
    ```

    > [!WARNING]
    > Ne **szerkessze** a commerceruntime.config és a CommerceRuntime.MPOSOffline.config fájlokat. Ezek a fájlok nem testreszabott fájlok.

# <a name="retail-731"></a>[Kiskereskedelmi 7.3.1](#tab/retail-7-3-1)

#### <a name="registerauditevent-sample-component"></a>RegisterAuditEvent mintaösszetevő

1. Keresse meg **a Runtime.Extensions.RegisterAuditEventSample** projektet, és építse fel.
2. A Extensions.RegisterAuditEventSample **\\ bin\\ hibakeresési** **mappában keresse meg a Contoso.Commerce.Runtime.RegisterAuditEventSample.dll** szerelvényfájlt.
3. A szerelvényfájl másolása a bővítmények CRT mappájába:

    - **Retail Server:** A szerelvény másolása **\\\\ az IIS Retail Server webhely bin ext** mappájába.
    - **Helyi CRT a Modern POS terminálon:** A **\\ szerelvény másolása a helyi ügyfélügynök helye alatti ext** CRT mappába.

4. A következő bővítmény-konfigurációs fájl megkeresve CRT:

    - **Retail Server:** **A fájl neve Commerceruntime.ext.config**, **és az IIS Retail Server webhely bin\\ ext** mappájában található.
    - **Helyi CRT a Modern POS terminálon:** **A fájl neve CommerceRuntime.MPOSOffline.Ext.config**, CRT és a helyi ügyfélügynök helye alatt található.

5. A változás CRT regisztrálása a kiterjesztés konfigurációs fájljában.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.RegisterAuditEventSample" />
    ```

    > [!WARNING]
    > Ne **szerkessze** a commerceruntime.config és a CommerceRuntime.MPOSOffline.config fájlokat. Ezek a fájlok nem testreszabott fájlok.

#### <a name="salestransactionsignature-sample-component"></a>SalesTransactionSignature mintaösszetevő

1. A Runtime.Extensions.SalesTransactionSignatureSample **projekt** megkeresve.
2. **Az App.config fájl** módosítása az értékesítési tranzakciók aláírására használt tanúsítvány ujjlenyomatának, tárolóhelyének és üzletnevének megadásával.
3. A projekt összeállítása.
4. **Az Extensions.SalesTransactionSignatureSample\\ bin\\ Hibakeresés** mappában keresse meg a következő fájlokat:

    - A **Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll szerelvényfájl**
    - A **Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll.config konfigurációs** fájl

5. A fájlok másolása a bővítmények CRT mappájába:

    - **Retail Server:** A szerelvény másolása **\\\\ az IIS Retail Server webhely bin ext** mappájába.
    - **Helyi CRT a Modern POS terminálon:** A **\\ szerelvény másolása a helyi ügyfélügynök helye alatti ext** CRT mappába.

6. A következő bővítmény-konfigurációs fájl megkeresve CRT:

    - **Retail Server:** **A fájl neve Commerceruntime.ext.config**, **és az IIS Retail Server webhely bin\\ ext** mappájában található.
    - **Helyi CRT a Modern POS terminálon:** **A fájl neve CommerceRuntime.MPOSOffline.Ext.config**, CRT és a helyi ügyfélügynök helye alatt található.

7. A változás CRT regisztrálása a kiterjesztés konfigurációs fájljában.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureSample" />
    ```

    > [!WARNING]
    > Ne **szerkessze** a commerceruntime.config és a CommerceRuntime.MPOSOffline.config fájlokat. Ezek a fájlok nem testreszabott fájlok.

#### <a name="sequentialsignatureregistercontracts-component"></a>SequentialSignatureRegister.Contracts összetevő

1. A Runtime.Extensions.SequentialSignatureRegister.Contracts **projekt** megkeresve.
2. **Az Extensions.SequentialSignatureRegister.Contracts\\ bin \\** **hibakeresési mappában keresse meg a Contoso.Commerce.Runtime.SequentialSignatureRegister.Contracts.dll** szerelvényfájlt.
3. A szerelvényfájl másolása a bővítmények CRT mappájába:

    - **Retail Server:** A szerelvény másolása **\\\\ az IIS Retail Server webhely bin ext** mappájába.
    - **Helyi CRT a Modern POS terminálon:** A **\\ szerelvény másolása a helyi ügyfélügynök helye alatti ext** CRT mappába.

# <a name="retail-732-and-later"></a>[Retail 7.3.2 és újabb](#tab/retail-7-3-2)

#### <a name="registerauditevent-sample-component"></a>RegisterAuditEvent mintaösszetevő

1. Keresse meg **a Runtime.Extensions.RegisterAuditEventSample** projektet, és építse fel.
2. A Extensions.RegisterAuditEventSample **\\ bin\\ hibakeresési** **mappában keresse meg a Contoso.Commerce.Runtime.RegisterAuditEventSample.dll** szerelvényfájlt.
3. A szerelvényfájl másolása a bővítmények CRT mappájába:

    - **Retail Server:** A szerelvény másolása **\\\\ az IIS Retail Server webhely bin ext** mappájába.
    - **Helyi CRT a Modern POS terminálon:** A **\\ szerelvény másolása a helyi ügyfélügynök helye alatti ext** CRT mappába.

4. A következő bővítmény-konfigurációs fájl megkeresve CRT:

    - **Retail Server:** **A fájl neve Commerceruntime.ext.config**, **és az IIS Retail Server webhely bin\\ ext** mappájában található.
    - **Helyi CRT a Modern POS terminálon:** **A fájl neve CommerceRuntime.MPOSOffline.Ext.config**, CRT és a helyi ügyfélügynök helye alatt található.

5. A változás CRT regisztrálása a kiterjesztés konfigurációs fájljában.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.RegisterAuditEventSample" />
    ```

    > [!WARNING]
    > Ne **szerkessze** a commerceruntime.config és a CommerceRuntime.MPOSOffline.config fájlokat. Ezek a fájlok nem testreszabott fájlok.

#### <a name="sequentialsignatureregister-component"></a>SzekvenciálisSignatureRegister összetevő

1. **A Runtime.Extensions.SequentialSignatureRegister projekt** megkeresve.
2. **Az App.config fájl** módosítása az értékesítési tranzakciók aláírására használt tanúsítvány ujjlenyomatának, tárolóhelyének és üzletnevének megadásával.
3. A projekt összeállítása.
4. **Az Extensions.SequentialSignatureRegister\\ bin\\ Hibakeresés** mappában keresse meg a következő fájlokat:

    - A **Contoso.Commerce.Runtime.SequentialSignatureRegister.dll szerelvényfájl**
    - A **Contoso.Commerce.Runtime.SequentialSignatureRegister.dll.config konfigurációs** fájl

5. A fájlok másolása a bővítmények CRT mappájába:

    - **Retail Server:** A szerelvény másolása **\\\\ az IIS Retail Server webhely bin ext** mappájába.
    - **Helyi CRT a Modern POS terminálon:** A **\\ szerelvény másolása a helyi ügyfélügynök helye alatti ext** CRT mappába.

6. A következő bővítmény-konfigurációs fájl megkeresve CRT:

    - **Retail Server:** **A fájl neve Commerceruntime.ext.config**, **és az IIS Retail Server webhely bin\\ ext** mappájában található.
    - **Helyi CRT a Modern POS terminálon:** **A fájl neve CommerceRuntime.MPOSOffline.Ext.config**, CRT és a helyi ügyfélügynök helye alatt található.

7. A változás CRT regisztrálása a kiterjesztés konfigurációs fájljában.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.SequentialSignatureRegister" />
    ```

    > [!WARNING]
    > Ne **szerkessze** a commerceruntime.config és a CommerceRuntime.MPOSOffline.config fájlokat. Ezek a fájlok nem testreszabott fájlok.

#### <a name="salestransactionsignaturenorway-component"></a>SalesTransactionSignatureNorway összetevő

1. **A Runtime.Extensions.SalesTransactionSignatureNorway projekt** megkeresve.
2. Az Extensions.SalesTransactionSignatureNorway **bin\\ Hibakeresés\\** mappában keresse meg a Contoso.Commerce.Runtime.SalesTransactionSignatureNorway.dll **szerelvényfájlt**.
3. A szerelvényfájl másolása a bővítmények CRT mappájába:

    - **Retail Server:** A szerelvény másolása **\\\\ az IIS Retail Server webhely bin ext** mappájába.
    - **Helyi CRT a Modern POS terminálon:** A **\\ szerelvény másolása a helyi ügyfélügynök helye alatti ext** CRT mappába.

4. A következő bővítmény-konfigurációs fájl megkeresve CRT:

    - **Retail Server:** **A fájl neve Commerceruntime.ext.config**, **és az IIS Retail Server webhely bin\\ ext** mappájában található.
    - **Helyi CRT a Modern POS terminálon:** **A fájl neve CommerceRuntime.MPOSOffline.Ext.config**, CRT és a helyi ügyfélügynök helye alatt található.

5. A változás CRT regisztrálása a kiterjesztés konfigurációs fájljában.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureNorway" />
    ```

    > [!WARNING]
    > Ne **szerkessze** a commerceruntime.config és a CommerceRuntime.MPOSOffline.config fájlokat. Ezek a fájlok nem testreszabott fájlok.

#### <a name="sequentialsignatureregistercontracts-component"></a>SequentialSignatureRegister.Contracts összetevő

1. A Runtime.Extensions.SequentialSignatureRegister.Contracts **projekt** megkeresve.
2. **Az Extensions.SequentialSignatureRegister.Contracts\\ bin \\** **hibakeresési mappában keresse meg a Contoso.Commerce.Runtime.SequentialSignatureRegister.Contracts.dll** szerelvényfájlt.
3. A szerelvényfájl másolása a bővítmények CRT mappájába:

    - **Retail Server:** A szerelvény másolása **\\\\ az IIS Retail Server webhely bin ext** mappájába.
    - **Helyi CRT a Modern POS terminálon:** A **\\ szerelvény másolása a helyi ügyfélügynök helye alatti ext** CRT mappába.

#### <a name="salespaymenttransextnorway-component"></a>SalesPaymentTransExtNorway összetevő

1. Keresse meg **és építse fel a Runtime.Extensions.SalesPaymentTransExtNorway** projektet.
2. Az Extensions.SalesPaymentTransExtNorway **bin\\ Hibakeresés\\** mappában keresse meg a Contoso.Commerce.Runtime.SalesPaymentTransExtNorway.dll **szerelvényfájlt**.
3. A szerelvényfájl másolása a bővítmények CRT mappájába:

    - **Retail Server:** A szerelvény másolása **\\\\ az IIS Retail Server webhely bin ext** mappájába.
    - **Helyi CRT a Modern POS terminálon:** A **\\ szerelvény másolása a helyi ügyfélügynök helye alatti ext** CRT mappába.

4. A következő bővítmény-konfigurációs fájl megkeresve CRT:

    - **Retail Server:** **A fájl neve Commerceruntime.ext.config**, **és az IIS Retail Server webhely bin\\ ext** mappájában található.
    - **Helyi CRT a Modern POS terminálon:** **A fájl neve CommerceRuntime.MPOSOffline.Ext.config**, CRT és a helyi ügyfélügynök helye alatt található.

5. A változás CRT regisztrálása a kiterjesztés konfigurációs fájljában.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.SalesPaymentTransExtNorway" />
    ```

    > [!WARNING]
    > Ne **szerkessze** a commerceruntime.config és a CommerceRuntime.MPOSOffline.config fájlokat. Ezek a fájlok nem testreszabott fájlok.

# <a name="retail-735-and-later"></a>[Retail 7.3.5 és újabb](#tab/retail-7-3-5)

#### <a name="registerauditeventnorway-component"></a>RegisterAuditEventNorway összetevő

1. A következő bővítmény-konfigurációs fájl megkeresve CRT:

    - **Retail Server:** **A fájl neve Commerceruntime.ext.config**, **és az IIS Retail Server webhely bin\\ ext** mappájában található.
    - **Helyi CRT a Modern POS terminálon:** **A fájl neve CommerceRuntime.MPOSOffline.Ext.config**, CRT és a helyi ügyfélügynök helye alatt található.

2. A változás CRT regisztrálása a kiterjesztés konfigurációs fájljában.

    ``` xml
    <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.RegisterAuditEventNorway" />
    ```

    > [!WARNING]
    > Ne **szerkessze** a commerceruntime.config és a CommerceRuntime.MPOSOffline.config fájlokat. Ezek a fájlok nem testreszabott fájlok.

#### <a name="sequentialsignatureregister-component"></a>SzekvenciálisSignatureRegister összetevő

1. **A Runtime.Extensions.SequentialSignatureRegister projekt** megkeresve.
2. **Az App.config fájl** módosítása az értékesítési tranzakciók aláírására használt tanúsítvány ujjlenyomatának, tárolóhelyének és üzletnevének megadásával.
3. A projekt összeállítása.
4. **Az Extensions.SequentialSignatureRegister\\ bin\\ Hibakeresés** mappában keresse meg a következő fájlokat:

    - A **Contoso.Commerce.Runtime.SequentialSignatureRegister.dll szerelvényfájl**
    - A **Contoso.Commerce.Runtime.SequentialSignatureRegister.dll.config konfigurációs** fájl

5. A fájlok másolása a bővítmények CRT mappájába:

    - **Retail Server:** A szerelvény másolása **\\\\ az IIS Retail Server webhely bin ext** mappájába.
    - **Helyi CRT a Modern POS terminálon:** A **\\ szerelvény másolása a helyi ügyfélügynök helye alatti ext** CRT mappába.

6. A következő bővítmény-konfigurációs fájl megkeresve CRT:

    - **Retail Server:** **A fájl neve Commerceruntime.ext.config**, **és az IIS Retail Server webhely bin\\ ext** mappájában található.
    - **Helyi CRT a Modern POS terminálon:** **A fájl neve CommerceRuntime.MPOSOffline.Ext.config**, CRT és a helyi ügyfélügynök helye alatt található.

7. A változás CRT regisztrálása a kiterjesztés konfigurációs fájljában.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.SequentialSignatureRegister" />
    ```

    > [!WARNING]
    > Ne **szerkessze** a commerceruntime.config és a CommerceRuntime.MPOSOffline.config fájlokat. Ezek a fájlok nem testreszabott fájlok.

#### <a name="salestransactionsignaturenorway-component"></a>SalesTransactionSignatureNorway összetevő

1. **A Runtime.Extensions.SalesTransactionSignatureNorway projekt** megkeresve.
2. Az Extensions.SalesTransactionSignatureNorway **bin\\ Hibakeresés\\** mappában keresse meg a Contoso.Commerce.Runtime.SalesTransactionSignatureNorway.dll **szerelvényfájlt**.
3. A szerelvényfájl másolása a bővítmények CRT mappájába:

    - **Retail Server:** A szerelvény másolása **\\\\ az IIS Retail Server webhely bin ext** mappájába.
    - **Helyi CRT a Modern POS terminálon:** A **\\ szerelvény másolása a helyi ügyfélügynök helye alatti ext** CRT mappába.

4. A következő bővítmény-konfigurációs fájl megkeresve CRT:

    - **Retail Server:** **A fájl neve Commerceruntime.ext.config**, **és az IIS Retail Server webhely bin\\ ext** mappájában található.
    - **Helyi CRT a Modern POS terminálon:** **A fájl neve CommerceRuntime.MPOSOffline.Ext.config**, CRT és a helyi ügyfélügynök helye alatt található.

5. A változás CRT regisztrálása a kiterjesztés konfigurációs fájljában.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureNorway" />
    ```

    > [!WARNING]
    > Ne **szerkessze** a commerceruntime.config és a CommerceRuntime.MPOSOffline.config fájlokat. Ezek a fájlok nem testreszabott fájlok.

#### <a name="sequentialsignatureregistercontracts-component"></a>SequentialSignatureRegister.Contracts összetevő

1. A Runtime.Extensions.SequentialSignatureRegister.Contracts **projekt** megkeresve.
2. **Az Extensions.SequentialSignatureRegister.Contracts\\ bin \\** **hibakeresési mappában keresse meg a Contoso.Commerce.Runtime.SequentialSignatureRegister.Contracts.dll** szerelvényfájlt.
3. A szerelvényfájl másolása a bővítmények CRT mappájába:

    - **Retail Server:** A szerelvény másolása **\\\\ az IIS Retail Server webhely bin ext** mappájába.
    - **Helyi CRT a Modern POS terminálon:** A **\\ szerelvény másolása a helyi ügyfélügynök helye alatti ext** CRT mappába.

#### <a name="salespaymenttransextnorway-component"></a>SalesPaymentTransExtNorway összetevő

1. Keresse meg **és építse fel a Runtime.Extensions.SalesPaymentTransExtNorway** projektet.
2. Az Extensions.SalesPaymentTransExtNorway **bin\\ Hibakeresés\\** mappában keresse meg a Contoso.Commerce.Runtime.SalesPaymentTransExtNorway.dll **szerelvényfájlt**.
3. A szerelvényfájl másolása a bővítmények CRT mappájába:

    - **Retail Server:** A szerelvény másolása **\\\\ az IIS Retail Server webhely bin ext** mappájába.
    - **Helyi CRT a Modern POS terminálon:** A **\\ szerelvény másolása a helyi ügyfélügynök helye alatti ext** CRT mappába.

4. A következő bővítmény-konfigurációs fájl megkeresve CRT:

    - **Retail Server:** **A fájl neve Commerceruntime.ext.config**, **és az IIS Retail Server webhely bin\\ ext** mappájában található.
    - **Helyi CRT a Modern POS terminálon:** **A fájl neve CommerceRuntime.MPOSOffline.Ext.config**, CRT és a helyi ügyfélügynök helye alatt található.

5. A változás CRT regisztrálása a kiterjesztés konfigurációs fájljában.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.SalesPaymentTransExtNorway" />
    ```

    > [!WARNING]
    > Ne **szerkessze** a commerceruntime.config és a CommerceRuntime.MPOSOffline.config fájlokat. Ezek a fájlok nem testreszabott fájlok.

# <a name="retail-811-and-later"></a>[Retail 8.1.1 és újabb](#tab/retail-8-1-1)

#### <a name="registerauditeventnorway-component"></a>RegisterAuditEventNorway összetevő

1. A következő bővítmény-konfigurációs fájl megkeresve CRT:

    - **Retail Server:** **A fájl neve Commerceruntime.ext.config**, **és az IIS Retail Server webhely bin\\ ext** mappájában található.
    - **Helyi CRT a Modern POS terminálon:** **A fájl neve CommerceRuntime.MPOSOffline.Ext.config**, CRT és a helyi ügyfélügynök helye alatt található.

2. A változás CRT regisztrálása a kiterjesztés konfigurációs fájljában.

    ``` xml
    <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.RegisterAuditEventNorway" />
    ```

    > [!WARNING]
    > Ne **szerkessze** a commerceruntime.config és a CommerceRuntime.MPOSOffline.config fájlokat. Ezek a fájlok nem testreszabott fájlok.

#### <a name="sequentialsignatureregister-component"></a>SzekvenciálisSignatureRegister összetevő

1. **A Runtime.Extensions.SequentialSignatureRegister projekt** megkeresve.
2. **Az App.config fájl** módosítása az értékesítési tranzakciók aláírására használt tanúsítvány ujjlenyomatának, tárolóhelyének és üzletnevének megadásával.
3. A projekt összeállítása.
4. **Az Extensions.SequentialSignatureRegister\\ bin\\ Hibakeresés** mappában keresse meg a következő fájlokat:

    - A **Contoso.Commerce.Runtime.SequentialSignatureRegister.dll szerelvényfájl**
    - A **Contoso.Commerce.Runtime.SequentialSignatureRegister.dll.config konfigurációs** fájl

5. A fájlok másolása a bővítmények CRT mappájába:

    - **Retail Server:** A szerelvény másolása **\\\\ az IIS Retail Server webhely bin ext** mappájába.
    - **Helyi CRT a Modern POS terminálon:** A **\\ szerelvény másolása a helyi ügyfélügynök helye alatti ext** CRT mappába.

6. A következő bővítmény-konfigurációs fájl megkeresve CRT:

    - **Retail Server:** **A fájl neve Commerceruntime.ext.config**, **és az IIS Retail Server webhely bin\\ ext** mappájában található.
    - **Helyi CRT a Modern POS terminálon:** **A fájl neve CommerceRuntime.MPOSOffline.Ext.config**, CRT és a helyi ügyfélügynök helye alatt található.

7. A változás CRT regisztrálása a kiterjesztés konfigurációs fájljában.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.SequentialSignatureRegister" />
    ```

    > [!WARNING]
    > Ne **szerkessze** a commerceruntime.config és a CommerceRuntime.MPOSOffline.config fájlokat. Ezek a fájlok nem testreszabott fájlok.

#### <a name="salestransactionsignaturenorway-component"></a>SalesTransactionSignatureNorway összetevő

1. **A Runtime.Extensions.SalesTransactionSignatureNorway projekt** megkeresve.
2. Az Extensions.SalesTransactionSignatureNorway **bin\\ Hibakeresés\\** mappában keresse meg a Contoso.Commerce.Runtime.SalesTransactionSignatureNorway.dll **szerelvényfájlt**.
3. A szerelvényfájl másolása a bővítmények CRT mappájába:

    - **Retail Server:** A szerelvény másolása **\\\\ az IIS Retail Server webhely bin ext** mappájába.
    - **Helyi CRT a Modern POS terminálon:** A **\\ szerelvény másolása a helyi ügyfélügynök helye alatti ext** CRT mappába.

4. A következő bővítmény-konfigurációs fájl megkeresve CRT:

    - **Retail Server:** **A fájl neve Commerceruntime.ext.config**, **és az IIS Retail Server webhely bin\\ ext** mappájában található.
    - **Helyi CRT a Modern POS terminálon:** **A fájl neve CommerceRuntime.MPOSOffline.Ext.config**, CRT és a helyi ügyfélügynök helye alatt található.

5. A változás CRT regisztrálása a kiterjesztés konfigurációs fájljában.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureNorway" />
    ```

    > [!WARNING]
    > Ne **szerkessze** a commerceruntime.config és a CommerceRuntime.MPOSOffline.config fájlokat. Ezek a fájlok nem testreszabott fájlok.

#### <a name="sequentialsignatureregistercontracts-component"></a>SequentialSignatureRegister.Contracts összetevő

1. A Runtime.Extensions.SequentialSignatureRegister.Contracts **projekt** megkeresve.
2. **Az Extensions.SequentialSignatureRegister.Contracts\\ bin \\** **hibakeresési mappában keresse meg a Contoso.Commerce.Runtime.SequentialSignatureRegister.Contracts.dll** szerelvényfájlt.
3. A szerelvényfájl másolása a bővítmények CRT mappájába:

    - **Retail Server:** A szerelvény másolása **\\\\ az IIS Retail Server webhely bin ext** mappájába.
    - **Helyi CRT a Modern POS terminálon:** A **\\ szerelvény másolása a helyi ügyfélügynök helye alatti ext** CRT mappába.

#### <a name="salespaymenttransextnorway-component"></a>SalesPaymentTransExtNorway összetevő

1. Keresse meg **és építse fel a Runtime.Extensions.SalesPaymentTransExtNorway** projektet.
2. Az Extensions.SalesPaymentTransExtNorway **bin\\ Hibakeresés\\** mappában keresse meg a Contoso.Commerce.Runtime.SalesPaymentTransExtNorway.dll **szerelvényfájlt**.
3. A szerelvényfájl másolása a bővítmények CRT mappájába:

    - **Retail Server:** A szerelvény másolása **\\\\ az IIS Retail Server webhely bin ext** mappájába.
    - **Helyi CRT a Modern POS terminálon:** A **\\ szerelvény másolása a helyi ügyfélügynök helye alatti ext** CRT mappába.

4. A következő bővítmény-konfigurációs fájl megkeresve CRT:

    - **Retail Server:** **A fájl neve Commerceruntime.ext.config**, **és az IIS Retail Server webhely bin\\ ext** mappájában található.
    - **Helyi CRT a Modern POS terminálon:** **A fájl neve CommerceRuntime.MPOSOffline.Ext.config**, CRT és a helyi ügyfélügynök helye alatt található.

5. A változás CRT regisztrálása a kiterjesztés konfigurációs fájljában.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.SalesPaymentTransExtNorway" />
    ```

    > [!WARNING]
    > Ne **szerkessze** a commerceruntime.config és a CommerceRuntime.MPOSOffline.config fájlokat. Ezek a fájlok nem testreszabott fájlok.

---

### <a name="the-retail-server-extension-components"></a>A Retail Server bővítmény összetevői

#### <a name="salestransactionsignature-retail-server-sample-component"></a>SalesTransactionSignature Retail Server - mintaösszetevő

1. **A RetailSDK\\ SampleExtensions\\ RetailServer.Extensions.SalesTransactionSignatureSample \\** **mappában keresse meg és építse fel a RetailServer.Extensions.SalesTransactionSignatureSample** projektet.
2. **A RetailServer Extensions.SalesTransactionSignatureSample\\\\ bin\\ Hibakeresési** **mappában keresse meg a Contoso.RetailServer.SalesTransactionSignatureSample.dll** szerelvényfájlt.
3. A szerelvényfájl másolása a Retail Server bővítménymappába.

    # <a name="application-update-4"></a>[4-as alkalmazásfrissítés](#tab/app-update-4)

    Ez a mappa az **\\** IIS Retail Server webhelyének bin mappája.

    # <a name="application-update-5-and-later"></a>[5-ös vagy újabb alkalmazásfrissítés](#tab/app-update-5-and-later)

    Ez a mappa az **\\** IIS Retail Server webhelyének bin mappája.

    # <a name="retail-731"></a>[Kiskereskedelmi 7.3.1](#tab/retail-7-3-1)

    Ez a mappa az **\\\\ IIS Retail Server webhely bin ext** mappája.

    # <a name="retail-732-and-later"></a>[Retail 7.3.2 és újabb](#tab/retail-7-3-2)

    Ez a mappa az **\\\\ IIS Retail Server webhely bin ext** mappája.

    # <a name="retail-735-and-later"></a>[Retail 7.3.5 és újabb](#tab/retail-7-3-5)

    Ez a mappa az **\\\\ IIS Retail Server webhely bin ext** mappája.

    # <a name="retail-811-and-later"></a>[Retail 8.1.1 és újabb](#tab/retail-8-1-1)

    Ez a mappa az **\\\\ IIS Retail Server webhely bin ext** mappája.

    ---

4. A Retail Server konfigurációs fájljának megkeresve. A fájl neve **web.config**, és az IIS Retail Server webhelyének gyökérmappában található.
5. Regisztrálja a Retail Server bővítményei a **konfigurációs fájl extensionComposition** szakaszában.

    ``` xml
    <add source="assembly" value="Contoso.RetailServer.SalesTransactionSignatureSample" />
    ```

6. Regisztrálja a Retail Server bővítményeinek függőségeit.

    # <a name="application-update-4"></a>[4-as alkalmazásfrissítés](#tab/app-update-4/)

    1. **A CommerceRuntime\\ Extensions.SalesTransactionSignatureSample\\ bin\\ hibakeresési** mappában keresse meg a következő fájlokat:

        - A **Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll szerelvényfájl**
        - A **Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll.config konfigurációs** fájl

    2. Másolja a fájlokat **\\** az IIS Retail Server webhelyének bin mappájába.
    3. A bővítmény CRT konfigurációs fájljában változás regisztrálása a következőben CRT: A fájl neve **Commerceruntime.ext.config**, **és** az IIS Retail Server webhely bin mappájában található.

        ``` xml
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureSample" />
        ```

    # <a name="application-update-5-and-later"></a>[5-ös vagy újabb alkalmazásfrissítés](#tab/app-update-5-and-later/)

    1. **A CommerceRuntime\\ extensions.SalesTransactionSignatureSample.Messages\\ bin\\ Hibakeresési** **mappában keresse meg a Contoso.Commerce.Runtime.SalesTransactionSignatureSample.Messages.dll** szerelvényfájlt.
    2. A fájl másolása az **\\** IIS Retail Server webhelyének bin mappájába.
    3. A bővítmény CRT konfigurációs fájljában változás regisztrálása a következőben CRT: A fájl neve **Commerceruntime.ext.config**, **és** az IIS Retail Server webhely bin mappájában található.

        ``` xml
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureSample.Messages" />
        ```

    # <a name="retail-731"></a>[Kiskereskedelmi 7.3.1](#tab/retail-7-3-1)

    > [!NOTE]
    > Nincs szükség műveletekre.

    # <a name="retail-732-and-later"></a>[Retail 7.3.2 és újabb](#tab/retail-7-3-2)

    > [!NOTE]
    > Nincs szükség műveletekre.

    # <a name="retail-735-and-later"></a>[Retail 7.3.5 és újabb](#tab/retail-7-3-5)

    > [!NOTE]
    > Nincs szükség műveletekre.

    # <a name="retail-811-and-later"></a>[Retail 8.1.1 és újabb](#tab/retail-8-1-1)

    > [!NOTE]
    > Nincs szükség műveletekre.

    ---

### <a name="the-modern-pos-extension-components"></a>A Modern POS bővítmény összetevői

#### <a name="implement-the-proxy-code-for-offline-mode"></a>A proxykód megvalósítása offline módban

Ez a rész megegyezik a Retail Server kontrollerrel, de kiterjeszti azt a helyi kiszolgálót, CRT amely akkor használatos, ha az ügyfél nincs csatlakoztatva.

1. Módosítsa a **customization.settings fájlban** a @(RetailServerLibraryPathForProxyGeneration) **szakaszt úgy,** hogy az új Retail Server-szerelvényt használja a proxyk generálása során.
2. Implementálja a következő interfész metódusokat **a StoreOperationsManager osztályban**. Az első iterációban adja hozzá a következő kódot:

    # <a name="application-update-4"></a>[4-as alkalmazásfrissítés](#tab/app-update-4)

    ``` csharp
    public Task<bool> SalesTransactionSignatureServiceIsReady()
    {
        throw new NotImplementedException();
    }
    public Task<FiscalTransaction> GetLastFiscalTransaction(string storeNumber, string terminalId)
    {
        throw new NotImplementedException();
    }
    ```

    # <a name="application-update-5-and-later"></a>[5-ös vagy újabb alkalmazásfrissítés](#tab/app-update-5-and-later)

    ``` csharp
    public Task<bool> SalesTransactionSignatureServiceIsReady(string correlationId)
    {
        throw new NotImplementedException();
    }
    public Task<FiscalTransaction> GetLastFiscalTransaction(string storeNumber, string terminalId)
    {
        throw new NotImplementedException();
    }
    ```

    # <a name="retail-731"></a>[Kiskereskedelmi 7.3.1](#tab/retail-7-3-1)

    > [!NOTE]
    > Ez a lépés nem érvényes erre a verzióra.

    # <a name="retail-732-and-later"></a>[Retail 7.3.2 és újabb](#tab/retail-7-3-2)

    > [!NOTE]
    > Ez a lépés nem érvényes erre a verzióra.

    # <a name="retail-735-and-later"></a>[Retail 7.3.5 és újabb](#tab/retail-7-3-5)

    > [!NOTE]
    > Ez a lépés nem érvényes erre a verzióra.

    # <a name="retail-811-and-later"></a>[Retail 8.1.1 és újabb](#tab/retail-8-1-1)

    > [!NOTE]
    > Ez a lépés nem érvényes erre a verzióra.

    ---

3. A proxykód újragenerálható, **hozza létre a Proxyk mappát** **a parancssorból az msbuild /t:Rebuild parancs** használatával.
4. Oldja fel **a Proxies.RetailProxy** projekt függőségeit:

    # <a name="application-update-4"></a>[4-as alkalmazásfrissítés](#tab/app-update-4)

    Nyissa meg a RetailSDK **proxies\\ RetailProxy\\ Proxies.RetailProxy.csproj webhelyet, adja hozzá a RetailSDK\\ SampleExtensions** CommerceRuntime **extensions.SalesTransactionSignatureSample CommerceRuntime.Extensions.SalesTransactionSignatureSample\\ projektet a megoldáshoz, és adjon hozzá egy projekthivatkozást a \\ RetailProxy\\\\ projekthez a SalesTransactionSignatureSample** hivatkozásához.**·** **·**

    # <a name="application-update-5-and-later"></a>[5-ös vagy újabb alkalmazásfrissítés](#tab/app-update-5-and-later)

    Nyissa meg a RetailSDK **proxies\\ RetailProxy\\ Proxies.RetailProxy.csproj webhelyet, adja hozzá a RetailSDK\\ SampleExtensions** CommerceRuntime **extensions.SalesTransactionSignatureSample.Messages CommerceRuntime.Extensions.SalesTransactionSignatureSample.Messages projektet a megoldáshoz, és adjon hozzá egy projekthivatkozást a \\ RetailProxy \\\\ projekthez a SalesTransactionSignatureSample.Messages\\** hivatkozásához.**·** **·**

    # <a name="retail-731"></a>[Kiskereskedelmi 7.3.1](#tab/retail-7-3-1)

    > [!NOTE]
    > Ez a lépés nem érvényes erre a verzióra.

    # <a name="retail-732-and-later"></a>[Retail 7.3.2 és újabb](#tab/retail-7-3-2)

    > [!NOTE]
    > Ez a lépés nem érvényes erre a verzióra.

    # <a name="retail-735-and-later"></a>[Retail 7.3.5 és újabb](#tab/retail-7-3-5)

    > [!NOTE]
    > Ez a lépés nem érvényes erre a verzióra.

    # <a name="retail-811-and-later"></a>[Retail 8.1.1 és újabb](#tab/retail-8-1-1)

    > [!NOTE]
    > Ez a lépés nem érvényes erre a verzióra.

    ---

5. **A StoreOperationsManager osztály felületi metódusának** beállítása:

    # <a name="application-update-4"></a>[4-as alkalmazásfrissítés](#tab/app-update-4)

    ``` csharp
    public Task<bool> SalesTransactionSignatureServiceIsReady()
    {
        return Task.Run(() => CommerceRuntimeManager.Runtime.Execute<SalesTransactionSignatureServiceIsReadyResponse>(new SalesTransactionSignatureServiceIsReadyRequest(), null).IsReady);
    }
    public Task<FiscalTransaction> GetLastFiscalTransaction(string storeNumber, string terminalId)
    {
        return Task.Run(() => CommerceRuntimeManager.Runtime.Execute<GetLastFiscalTransactionResponse>(new GetLastFiscalTransactionRequest(), null).FiscalTransaction);
    }
    ```

    # <a name="application-update-5-and-later"></a>[5-ös vagy újabb alkalmazásfrissítés](#tab/app-update-5-and-later)

    ``` csharp
    public Task<bool> SalesTransactionSignatureServiceIsReady(string correlationId)
    {
        return Task.Run(() => CommerceRuntimeManager.Runtime.Execute<SalesTransactionSignatureServiceIsReadyResponse>(new SalesTransactionSignatureServiceIsReadyRequest(), null).IsReady);
    }
    public Task<FiscalTransaction> GetLastFiscalTransaction(string storeNumber, string terminalId)
    {
        return Task.Run(() => CommerceRuntimeManager.Runtime.Execute<GetLastFiscalTransactionResponse>(new GetLastFiscalTransactionRequest(), null).FiscalTransaction);
    }
    ```

    # <a name="retail-731"></a>[Kiskereskedelmi 7.3.1](#tab/retail-7-3-1)

    > [!NOTE]
    > Ez a lépés nem érvényes erre a verzióra.

    # <a name="retail-732-and-later"></a>[Retail 7.3.2 és újabb](#tab/retail-7-3-2)

    > [!NOTE]
    > Ez a lépés nem érvényes erre a verzióra.

    # <a name="retail-735-and-later"></a>[Retail 7.3.5 és újabb](#tab/retail-7-3-5)

    > [!NOTE]
    > Ez a lépés nem érvényes erre a verzióra.

    # <a name="retail-811-and-later"></a>[Retail 8.1.1 és újabb](#tab/retail-8-1-1)

    > [!NOTE]
    > Ez a lépés nem érvényes erre a verzióra.

    ---

6. Frissítse a **dllhost.exe.config fájlt** úgy, hogy az ügyfélügynök betölti az új RetailProxy szerelvényt.

    ``` xml
    <add key="RetailProxyAssemblyName" value="Contoso.Commerce.RetailProxy" />
    <add key="AdaptorCallerFullTypeName" value="Contoso.Commerce.RetailProxy.Adapters.AdaptorCaller" />
    ```

#### <a name="retail-proxy-extension-component-retail-731-and-later"></a>Retail proxykiterjesztési összetevő (Retail 7.3.1 és újabb)

Csak akkor kell végrehajtani a következő eljárást, ha a Retail 7.3.1-es és újabb rendszereket használja.

1. **A RetailSDK\\ SampleExtensions\\ RetailProxy.Extensions.SalesTransactionSignatureSample \\** **mappában keresse meg és építse fel a RetailServer.Extensions.SalesTransactionSignatureSample** projektet.
2. **A RetailProxy\\ RetailProxy.Extensions.SalesTransactionSignatureSample\\ bin\\ Hibakeresési** **mappában keresse meg a Contoso.Commerce.RetailProxy.SalesTransactionSignatureSample** szerelvényfájlt.
3. A szerelvényfájlok másolása **\\ a helyi ügyfélügynök** helye alatti ext CRT mappába.
4. Regisztrálja a Retail proxy változtatását a kiterjesztés konfigurációs fájljában. A fájl neve **RetailProxy.MPOSOffline.ext.config**, CRT és a helyi ügyfélügynök helye alatt található.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.RetailProxy.SalesTransactionSignatureSample" />
    ```

#### <a name="modern-pos-extension-components"></a>Modern POS-bővítmények összetevői

1. Nyissa meg a megoldást a **RetailSdk\\ POS\\ ModernPOS.sln** terminálon, és ellenőrizze, hogy hiba nélkül fordítható-e. Ezenkívül a Futtatás parancs használatával győződjön meg arról, hogy a Modern POS futtatható a Microsoft Visual Studio **rendszerből**.

    > [!NOTE]
    > A Modern POS nem szabható testre. Engedélyeznie kell a Felhasználói fiókok vezérlése (UAC) alkalmazást, és szükség szerint el kell távolítania a Modern POS korábban telepített példányait.

2. A következő, meglévő forráskódmappák megjelenítése a **Pos.Extensions projektben**.

    # <a name="application-update-4"></a>[4-as alkalmazásfrissítés](#tab/app-update-4)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample

    # <a name="application-update-5-and-later"></a>[5-ös vagy újabb alkalmazásfrissítés](#tab/app-update-5-and-later)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample

    # <a name="retail-731"></a>[Kiskereskedelmi 7.3.1](#tab/retail-7-3-1)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample

    # <a name="retail-732-and-later"></a>[Retail 7.3.2 és újabb](#tab/retail-7-3-2)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample
    - SalesTransactionSignatureNorway
    - Szekvenciálissignature

    # <a name="retail-735-and-later"></a>[Retail 7.3.5 és újabb](#tab/retail-7-3-5)

    - SalesTransactionSignatureSample
    - SalesTransactionSignatureNorway
    - Szekvenciálissignature

    # <a name="retail-811-and-later"></a>[Retail 8.1.1 és újabb](#tab/retail-8-1-1)

    - SalesTransactionSignatureSample
    - SalesTransactionSignatureNorway
    - Szekvenciálissignature

    ---

3. A bővítmények fordításának **engedélyezése a tsconfig.json fájlban** a következő mappák kizárási listából való eltávolításával.

    # <a name="application-update-4"></a>[4-as alkalmazásfrissítés](#tab/app-update-4)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample

    # <a name="application-update-5-and-later"></a>[5-ös vagy újabb alkalmazásfrissítés](#tab/app-update-5-and-later)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample

    # <a name="retail-731"></a>[Kiskereskedelmi 7.3.1](#tab/retail-7-3-1)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample

    # <a name="retail-732-and-later"></a>[Retail 7.3.2 és újabb](#tab/retail-7-3-2)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample
    - SalesTransactionSignatureNorway
    - Szekvenciálissignature

    # <a name="retail-735-and-later"></a>[Retail 7.3.5 és újabb](#tab/retail-7-3-5)

    - SalesTransactionSignatureSample
    - SalesTransactionSignatureNorway
    - Szekvenciálissignature

    # <a name="retail-811-and-later"></a>[Retail 8.1.1 és újabb](#tab/retail-8-1-1)

    - SalesTransactionSignatureSample
    - SalesTransactionSignatureNorway
    - Szekvenciálissignature

    ---

4. A bővítményeknek a **megfelelő helyre való felvételével engedélyezhető a bővítmények.json** fájlba való betöltésének engedélyezése a következő soroknak a megfelelő helyre való hozzáadásával.

    # <a name="application-update-4"></a>[4-as alkalmazásfrissítés](#tab/app-update-4)

    ``` json
    {
        "baseUrl": "AuditEventExtensionSample"
    },
    {
        "baseUrl": "SalesTransactionSignatureSample"
    }
    ```

    # <a name="application-update-5-and-later"></a>[5-ös vagy újabb alkalmazásfrissítés](#tab/app-update-5-and-later)

    ``` json
    {
        "baseUrl": "AuditEventExtensionSample"
    },
    {
        "baseUrl": "SalesTransactionSignatureSample"
    }
    ```

    # <a name="retail-731"></a>[Kiskereskedelmi 7.3.1](#tab/retail-7-3-1)

    ``` json
    {
        "baseUrl": "AuditEventExtensionSample"
    },
    {
        "baseUrl": "SalesTransactionSignatureSample"
    }
    ```

    # <a name="retail-732-and-later"></a>[Retail 7.3.2 és újabb](#tab/retail-7-3-2)

    ``` json
    {
        "baseUrl": "AuditEventExtensionSample"
    },
    {
        "baseUrl": "SalesTransactionSignatureSample"
    },
    {
        "baseUrl": "SalesTransactionSignatureNorway"
    },
    {
        "baseUrl": "SequentialSignature"
    }
    ```

    # <a name="retail-735-and-later"></a>[Retail 7.3.5 és újabb](#tab/retail-7-3-5)

    ``` json
    {
        "baseUrl": "Microsoft/AuditEvent.NO"
    },
    {
        "baseUrl": "SalesTransactionSignatureSample"
    },
    {
        "baseUrl": "SalesTransactionSignatureNorway"
    },
    {
        "baseUrl": "SequentialSignature"
    }
    ```

    # <a name="retail-811-and-later"></a>[Retail 8.1.1 és újabb](#tab/retail-8-1-1)

    ``` json
    {
        "baseUrl": "Microsoft/AuditEvent.NO"
    },
    {
        "baseUrl": "SalesTransactionSignatureSample"
    },
    {
        "baseUrl": "SalesTransactionSignatureNorway"
    },
    {
        "baseUrl": "SequentialSignature"
    }
    ```

    ---

    > [!NOTE]
    > A további tudnivalókat, valamint azokat a **mintákat, amelyek mutatják, hogyan kell a forráskódmappákat szerepeletni, és hogyan lehet a bővítményeket betölteni, lásd a Pos.Extensions** projekt readme.md fájljában található utasításokat.

5. A megoldás újraépítése.
6. Futtassa a Modern POS szolgáltatást a hibakeresőben, és tesztelje a funkciót.

### <a name="cloud-pos-extension-components"></a>A Felhő POS bővítmény összetevői

1. Nyissa meg a megoldást a **RetailSdk\\ POS\\ CloudPOS.sln** terminálon, és ellenőrizze, hogy hiba nélkül fordítható-e.
2. A következő forráskódmappák megjelenítése a **Pos.Extensions projektben**.

    # <a name="application-update-4"></a>[4-as alkalmazásfrissítés](#tab/app-update-4)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample

    # <a name="application-update-5-and-later"></a>[5-ös vagy újabb alkalmazásfrissítés](#tab/app-update-5-and-later)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample

    # <a name="retail-731"></a>[Kiskereskedelmi 7.3.1](#tab/retail-7-3-1)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample

    # <a name="retail-732-and-later"></a>[Retail 7.3.2 és újabb](#tab/retail-7-3-2)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample
    - SalesTransactionSignatureNorway
    - Szekvenciálissignature

    # <a name="retail-735-and-later"></a>[Retail 7.3.5 és újabb](#tab/retail-7-3-5)

    - SalesTransactionSignatureSample
    - SalesTransactionSignatureNorway
    - Szekvenciálissignature

    # <a name="retail-811-and-later"></a>[Retail 8.1.1 és újabb](#tab/retail-8-1-1)

    - SalesTransactionSignatureSample
    - SalesTransactionSignatureNorway
    - Szekvenciálissignature

    ---

3. A bővítmények fordításának **engedélyezése a tsconfig.json fájlban** a következő mappák kizárási listából való eltávolításával.

    # <a name="application-update-4"></a>[4-as alkalmazásfrissítés](#tab/app-update-4)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample

    # <a name="application-update-5-and-later"></a>[5-ös vagy újabb alkalmazásfrissítés](#tab/app-update-5-and-later)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample

    # <a name="retail-731"></a>[Kiskereskedelmi 7.3.1](#tab/retail-7-3-1)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample

    # <a name="retail-732-and-later"></a>[Retail 7.3.2 és újabb](#tab/retail-7-3-2)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample
    - SalesTransactionSignatureNorway
    - Szekvenciálissignature

    # <a name="retail-735-and-later"></a>[Retail 7.3.5 és újabb](#tab/retail-7-3-5)

    - SalesTransactionSignatureSample
    - SalesTransactionSignatureNorway
    - Szekvenciálissignature

    # <a name="retail-811-and-later"></a>[Retail 8.1.1 és újabb](#tab/retail-8-1-1)

    - SalesTransactionSignatureSample
    - SalesTransactionSignatureNorway
    - Szekvenciálissignature

    ---

4. A bővítményeknek a **megfelelő helyre való felvételével engedélyezhető a bővítmények.json** fájlba való betöltésének engedélyezése a következő soroknak a megfelelő helyre való hozzáadásával.

    # <a name="application-update-4"></a>[4-as alkalmazásfrissítés](#tab/app-update-4)

    ``` json
    {
        "baseUrl": "AuditEventExtensionSample"
    },
    {
        "baseUrl": "SalesTransactionSignatureSample"
    }
    ```

    # <a name="application-update-5-and-later"></a>[5-ös vagy újabb alkalmazásfrissítés](#tab/app-update-5-and-later)

    ``` json
    {
        "baseUrl": "AuditEventExtensionSample"
    },
    {
        "baseUrl": "SalesTransactionSignatureSample"
    }
    ```

    # <a name="retail-731"></a>[Kiskereskedelmi 7.3.1](#tab/retail-7-3-1)

    ``` json
    {
        "baseUrl": "AuditEventExtensionSample"
    },
    {
        "baseUrl": "SalesTransactionSignatureSample"
    }
    ```

    # <a name="retail-732-and-later"></a>[Retail 7.3.2 és újabb](#tab/retail-7-3-2)

    ``` json
    {
        "baseUrl": "AuditEventExtensionSample"
    },
    {
        "baseUrl": "SalesTransactionSignatureSample"
    },
    {
        "baseUrl": "SalesTransactionSignatureNorway"
    },
    {
        "baseUrl": "SequentialSignature"
    }
    ```

    # <a name="retail-735-and-later"></a>[Retail 7.3.5 és újabb](#tab/retail-7-3-5)

    ``` json
    {
        "baseUrl": "Microsoft/AuditEvent.NO"
    },
    {
        "baseUrl": "SalesTransactionSignatureSample"
    },
    {
        "baseUrl": "SalesTransactionSignatureNorway"
    },
    {
        "baseUrl": "SequentialSignature"
    }
    ```

    # <a name="retail-811-and-later"></a>[Retail 8.1.1 és újabb](#tab/retail-8-1-1)

    ``` json
    {
        "baseUrl": "Microsoft/AuditEvent.NO"
    },
    {
        "baseUrl": "SalesTransactionSignatureSample"
    },
    {
        "baseUrl": "SalesTransactionSignatureNorway"
    },
    {
        "baseUrl": "SequentialSignature"
    }
    ```

    ---

    > [!NOTE]
    > A további tudnivalókat, valamint azokat a **mintákat, amelyek mutatják, hogyan kell a forráskódmappákat szerepeletni, és hogyan lehet a bővítményeket betölteni, lásd a Pos.Extensions** projekt readme.md fájljában található utasításokat.

5. A megoldás újraépítése.
6. Futtassa a megoldást a Futtatás **parancs** használatával, és kövesse a Retail SDK útmutató lépéseit.
7. A funkció tesztelése.

### <a name="set-up-required-parameters-in-headquarters"></a>Kötelező paraméterek beállítása a Központban

További információ a Norvégiához [használható pénztárgép-funkcióknál található](./emea-nor-cash-registers.md).

## <a name="production-environment"></a>Működési környezet

A következő lépések szerint hozhatja létre a Commerce összetevőket tartalmazó telepíthető csomagokat, és ezeket a csomagokat éles környezetben alkalmazhatja.

1. A cikk korábbi részében, [a Cloud POS bővítmény összetevőinek vagy](#cloud-pos-extension-components)[a Modern POS-bővítmények](#modern-pos-extension-components) összetevőinek lépéseit kell végrehajtani.
2. Tegye a következő módosításokat **a RetailSdk\\ Assets mappa csomagkonfigurációs fájljaiban**:

    1. **A Commerceruntime.ext.config** **és a CommerceRuntime.MPOSOffline.Ext.config** **konfigurációs fájlokban adja hozzá a következő sorokat az összeállítási szakaszhoz**:

        # <a name="application-update-4"></a>[4-as alkalmazásfrissítés](#tab/app-update-4)

        ``` xml
        <add source="assembly" value="Contoso.Commerce.Runtime.ReceiptsNorway" />
        <add source="assembly" value="Contoso.Commerce.Runtime.RegisterAuditEventSample" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesPaymentTransExt" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureSample" />
        <add source="assembly" value="Contoso.Commerce.Runtime.XZReportsNorway" />
        ```

        # <a name="application-update-5-and-later"></a>[5-ös vagy újabb alkalmazásfrissítés](#tab/app-update-5-and-later)

        ``` xml
        <add source="assembly" value="Contoso.Commerce.Runtime.ReceiptsNorway" />
        <add source="assembly" value="Contoso.Commerce.Runtime.RegisterAuditEventSample" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesPaymentTransExt" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureSample" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureSample.Messages" />
        <add source="assembly" value="Contoso.Commerce.Runtime.XZReportsNorway" />
        ```

        # <a name="retail-731"></a>[Kiskereskedelmi 7.3.1](#tab/retail-7-3-1)

        ``` xml
        <add source="assembly" value="Contoso.Commerce.Runtime.ReceiptsNorway" />
        <add source="assembly" value="Contoso.Commerce.Runtime.RegisterAuditEventSample" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesPaymentTransExt" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureSample" />
        <add source="assembly" value="Contoso.Commerce.Runtime.XZReportsNorway" />
        ```

        # <a name="retail-732-and-later"></a>[Retail 7.3.2 és újabb](#tab/retail-7-3-2)

        ``` xml
        <add source="assembly" value="Contoso.Commerce.Runtime.ReceiptsNorway" />
        <add source="assembly" value="Contoso.Commerce.Runtime.RegisterAuditEventSample" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesPaymentTransExt" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesPaymentTransExtNorway" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SequentialSignatureRegister" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureNorway" />
        <add source="assembly" value="Contoso.Commerce.Runtime.XZReportsNorway" />
        ```

        # <a name="retail-735-and-later"></a>[Retail 7.3.5 és újabb](#tab/retail-7-3-5)

        ``` xml
        <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.RegisterAuditEventNorway" />
        <add source="assembly" value="Contoso.Commerce.Runtime.ReceiptsNorway" />
        <add source="assembly" value="Contoso.Commerce.Runtime.RegisterAuditEventSample" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesPaymentTransExt" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesPaymentTransExtNorway" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SequentialSignatureRegister" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureNorway" />
        <add source="assembly" value="Contoso.Commerce.Runtime.XZReportsNorway" />
        ```

        # <a name="retail-811-and-later"></a>[Retail 8.1.1 és újabb](#tab/retail-8-1-1)

        ``` xml
        <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.RegisterAuditEventNorway" />
        <add source="assembly" value="Contoso.Commerce.Runtime.ReceiptsNorway" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesPaymentTransExt" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesPaymentTransExtNorway" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SequentialSignatureRegister" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureNorway" />
        <add source="assembly" value="Contoso.Commerce.Runtime.XZReportsNorway" />
        ```

        ---

    2. A Commerce Proxy testreszabásának engedélyezése:

        # <a name="application-update-4"></a>[4-as alkalmazásfrissítés](#tab/app-update-4)

        Adja hozzá **a következő sorokat a dllhost.exe.config** konfigurációs fájlban **a konfigurációs szakasz appSettings** alszakaszában **·**.

        ``` xml
        <add key="RetailProxyAssemblyName" value="Contoso.Commerce.RetailProxy"/>
        <add key="AdaptorCallerFullTypeName" value ="Contoso.Commerce.RetailProxy.Adapters.AdaptorCaller"/>
        ```

        # <a name="application-update-5-and-later"></a>[5-ös vagy újabb alkalmazásfrissítés](#tab/app-update-5-and-later)

        Adja hozzá **a következő sorokat a dllhost.exe.config** konfigurációs fájlban **a konfigurációs szakasz appSettings** alszakaszában **·**.

        ``` xml
        <add key="RetailProxyAssemblyName" value="Contoso.Commerce.RetailProxy"/>
        <add key="AdaptorCallerFullTypeName" value ="Contoso.Commerce.RetailProxy.Adapters.AdaptorCaller"/>
        ```

        # <a name="retail-731"></a>[Kiskereskedelmi 7.3.1](#tab/retail-7-3-1)

        **A RetailProxy.MPOSOffline.ext.config** konfigurációs fájlban adja hozzá a következő sorokat az összeállítási **szakaszhoz**:

        ``` xml
        <add source="assembly" value="Contoso.Commerce.RetailProxy.SalesTransactionSignatureSample" />
        ```

        # <a name="retail-732-and-later"></a>[Retail 7.3.2 és újabb](#tab/retail-7-3-2)

        **A RetailProxy.MPOSOffline.ext.config** konfigurációs fájlban adja hozzá a következő sorokat az összeállítási **szakaszhoz**:

        ``` xml
        <add source="assembly" value="Contoso.Commerce.RetailProxy.SalesTransactionSignatureSample" />
        ```

        # <a name="retail-735-and-later"></a>[Retail 7.3.5 és újabb](#tab/retail-7-3-5)

        **A RetailProxy.MPOSOffline.ext.config** konfigurációs fájlban adja hozzá a következő sorokat az összeállítási **szakaszhoz**:

        ``` xml
        <add source="assembly" value="Contoso.Commerce.RetailProxy.SalesTransactionSignatureSample" />
        ```

        # <a name="retail-811-and-later"></a>[Retail 8.1.1 és újabb](#tab/retail-8-1-1)

        **A RetailProxy.MPOSOffline.ext.config** konfigurációs fájlban adja hozzá a következő sorokat az összeállítási **szakaszhoz**:

        ``` xml
        <add source="assembly" value="Contoso.Commerce.RetailProxy.SalesTransactionSignatureSample" />
        ```

        ---

3. Tegye a következő módosításokat **a Testreszabás.beállítások** csomag testreszabása konfigurációs fájlban:

    1. A Retail Proxy testreszabásának engedélyezése.

        # <a name="application-update-4"></a>[4-as alkalmazásfrissítés](#tab/app-update-4)

        Adja hozzá a **&lt; következő sorokat az ItemGroup condition="@(RetailServerLibraryPathForProxyGeneration)" == "" szakaszhoz&gt;**.

        ``` xml
        <RetailServerLibraryPathForProxyGeneration Include="$(SdkReferencesPath)\Contoso.RetailServer.SalesTransactionSignatureSample.dll"/>
        ```

        # <a name="application-update-5-and-later"></a>[5-ös vagy újabb alkalmazásfrissítés](#tab/app-update-5-and-later)

        Adja hozzá a **&lt; következő sorokat az ItemGroup condition="@(RetailServerLibraryPathForProxyGeneration)" == "" szakaszhoz&gt;**.

        ``` xml
        <RetailServerLibraryPathForProxyGeneration Include="$(SdkReferencesPath)\Contoso.RetailServer.SalesTransactionSignatureSample.dll"/>
        ```

        # <a name="retail-731"></a>[Kiskereskedelmi 7.3.1](#tab/retail-7-3-1)

        Vegye fel a következő sorokat **az ItemGroup szakaszba**, hogy a retail proxykiterjesztés szerepeljen a telepíthető csomagokban:

        ``` xml
        <ISV_RetailProxy_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.RetailProxy.SalesTransactionSignatureSample.dll" />
        ```

        # <a name="retail-732-and-later"></a>[Retail 7.3.2 és újabb](#tab/retail-7-3-2)

        Vegye fel a következő sorokat **az ItemGroup szakaszba**, hogy a retail proxykiterjesztés szerepeljen a telepíthető csomagokban:

        ``` xml
        <ISV_RetailProxy_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.RetailProxy.SalesTransactionSignatureSample.dll" />
        ```

        # <a name="retail-735-and-later"></a>[Retail 7.3.5 és újabb](#tab/retail-7-3-5)

        Vegye fel a következő sorokat **az ItemGroup szakaszba**, hogy a retail proxykiterjesztés szerepeljen a telepíthető csomagokban:

        ``` xml
        <ISV_RetailProxy_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.RetailProxy.SalesTransactionSignatureSample.dll" />
        ```

        # <a name="retail-811-and-later"></a>[Retail 8.1.1 és újabb](#tab/retail-8-1-1)

        Vegye fel a következő sorokat **az ItemGroup szakaszba**, hogy a retail proxykiterjesztés szerepeljen a telepíthető csomagokban:

        ``` xml
        <ISV_RetailProxy_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.RetailProxy.SalesTransactionSignatureSample.dll" />
        ```

        ---

    2. Vegye fel a következő sorokat **az ItemGroup szakaszba** CRT, hogy a bővítmények belevehetőek a telepíthető csomagokba:

        # <a name="application-update-4"></a>[4-as alkalmazásfrissítés](#tab/app-update-4)

        ``` xml
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.ReceiptsNorway.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.RegisterAuditEventSample.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesPaymentTransExt.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll.config" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.XZReportsNorway.dll" />
        ```

        # <a name="application-update-5-and-later"></a>[5-ös vagy újabb alkalmazásfrissítés](#tab/app-update-5-and-later)

        ``` xml
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.ReceiptsNorway.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.RegisterAuditEventSample.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesPaymentTransExt.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll.config" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesTransactionSignatureSample.Messages.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.XZReportsNorway.dll" />
        ```

        # <a name="retail-731"></a>[Kiskereskedelmi 7.3.1](#tab/retail-7-3-1)

        ``` xml
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.ReceiptsNorway.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.RegisterAuditEventSample.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesPaymentTransExt.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll.config" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SequentialSignatureRegister.Contracts.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.XZReportsNorway.dll" />
        ```

        # <a name="retail-732-and-later"></a>[Retail 7.3.2 és újabb](#tab/retail-7-3-2)

        ``` xml
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.ReceiptsNorway.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.RegisterAuditEventSample.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesPaymentTransExt.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesPaymentTransExtNorway.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SequentialSignatureRegister.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesTransactionSignatureNorway.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SequentialSignatureRegister.dll.config" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SequentialSignatureRegister.Contracts.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.XZReportsNorway.dll" />
        ```

        # <a name="retail-735-and-later"></a>[Retail 7.3.5 és újabb](#tab/retail-7-3-5)

        ``` xml
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.ReceiptsNorway.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesPaymentTransExt.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesPaymentTransExtNorway.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SequentialSignatureRegister.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesTransactionSignatureNorway.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SequentialSignatureRegister.dll.config" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SequentialSignatureRegister.Contracts.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.XZReportsNorway.dll" />
        ```

        # <a name="retail-811-and-later"></a>[Retail 8.1.1 és újabb](#tab/retail-8-1-1)

        ``` xml
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.ReceiptsNorway.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesPaymentTransExt.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesPaymentTransExtNorway.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SequentialSignatureRegister.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesTransactionSignatureNorway.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SequentialSignatureRegister.dll.config" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SequentialSignatureRegister.Contracts.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.XZReportsNorway.dll" />
        ```

        ---

    3. Adja hozzá a következő sorokat az **ItemGroup szakaszhoz**, hogy a Retail Server bővítmény szerepeljen a telepíthető csomagokban:

        # <a name="application-update-4"></a>[4-as alkalmazásfrissítés](#tab/app-update-4)

        ``` xml
        <ISV_RetailServer_CustomizableFile Include="$(SdkReferencesPath)\Contoso.RetailServer.SalesTransactionSignatureSample.dll" />
        <ISV_RetailServer_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll" />
        <ISV_RetailServer_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll.config" />
        ```

        # <a name="application-update-5-and-later"></a>[5-ös vagy újabb alkalmazásfrissítés](#tab/app-update-5-and-later)

        ``` xml
        <ISV_RetailServer_CustomizableFile Include="$(SdkReferencesPath)\Contoso.RetailServer.SalesTransactionSignatureSample.dll" />
        <ISV_RetailServer_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesTransactionSignatureSample.Messages.dll" />
        ```

        # <a name="retail-731"></a>[Kiskereskedelmi 7.3.1](#tab/retail-7-3-1)

        ``` xml
        <ISV_RetailServer_CustomizableFile Include="$(SdkReferencesPath)\Contoso.RetailServer.SalesTransactionSignatureSample.dll" />
        ```

        # <a name="retail-732-and-later"></a>[Retail 7.3.2 és újabb](#tab/retail-7-3-2)

        ``` xml
        <ISV_RetailServer_CustomizableFile Include="$(SdkReferencesPath)\Contoso.RetailServer.SalesTransactionSignatureSample.dll" />
        ```

        # <a name="retail-735-and-later"></a>[Retail 7.3.5 és újabb](#tab/retail-7-3-5)

        ``` xml
        <ISV_RetailServer_CustomizableFile Include="$(SdkReferencesPath)\Contoso.RetailServer.SalesTransactionSignatureSample.dll" />
        ```

        # <a name="retail-811-and-later"></a>[Retail 8.1.1 és újabb](#tab/retail-8-1-1)

        ``` xml
        <ISV_RetailServer_CustomizableFile Include="$(SdkReferencesPath)\Contoso.RetailServer.SalesTransactionSignatureSample.dll" />
        ```

        ---

4. Módosítsa a következő fájlokat, hogy a Norvégia erőforrásfájljai telepíthető csomagokban szerepeljenek:
    - SharedPackagingProjectComponents\_\Sdk.ModernPos.Shared.csproj csomagok
    - Csomagok\RetailServer\Sdk.RetailServerSetup.proj
  
  - **Az Sdk.ModernPos.Shared.csproj fájlhoz** 
    - Sor hozzáadása az **ItemGroup szakaszhoz**
    
        ``` xml
        <<File_name> Include="$(SdkReferencesPath)\nb-NO\*" />
        ```
    > [!Note]
    > A fájl <File_name> erőforrásfájl nevének megadása. Ugyanez érvényes az alábbi példákra is.
 
    - Sor hozzáadása a célnév **="CopyPackageFiles" szakaszhoz**
       ``` xml
        <Copy SourceFiles="@(<File_name>)" DestinationFolder="$(OutputPath)content.folder\CustomizedFiles\ClientBroker\ext\nb-NO" SkipUnchangedFiles="true" />
        ```
  
  - **Az Sdk.RetailServerSetup.proj fájlhoz** 
    - Sor hozzáadása az **ItemGroup szakaszhoz**
        ``` xml
        <<File_name> Include="$(SdkReferencesPath)\nb-NO\*" />
        ```    
    - Sor hozzáadása a célnév **="CopyPackageFiles" szakaszhoz**
         ``` xml
        <Copy SourceFiles="@(<File_name>)" DestinationFolder="$(OutputPath)content.folder\RetailServer\Code\bin\ext\nb-NO" SkipUnchangedFiles="true" />
        ```    

5. A tanúsítvány konfigurációs fájljának módosítása az értékesítési tranzakciók aláírására használt tanúsítvány ujjlenyomatának, tárolóhelyének és üzletnevének megadásával. Ezután másolja a konfigurációs fájlt a Hivatkozások **mappába**.

    # <a name="application-update-4"></a>[4-as alkalmazásfrissítés](#tab/app-update-4)

    A fájl neve **Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll.config**, **és a CommerceRuntime\\ Extensions.SalesTransactionSignatureSample\\ bin\\ hibakeresés** alatt található.

    # <a name="application-update-5-and-later"></a>[5-ös vagy újabb alkalmazásfrissítés](#tab/app-update-5-and-later)

    A fájl neve **Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll.config**, **és a CommerceRuntime\\ Extensions.SalesTransactionSignatureSample\\ bin\\ hibakeresés** alatt található.

    # <a name="retail-731"></a>[Kiskereskedelmi 7.3.1](#tab/retail-7-3-1)

    A fájl neve **Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll.config**, **és a CommerceRuntime\\ Extensions.SalesTransactionSignatureSample\\ bin\\ hibakeresés** alatt található.

    # <a name="retail-732-and-later"></a>[Retail 7.3.2 és újabb](#tab/retail-7-3-2)

    A fájl neve Contoso.Commerce.Runtime.SequentialSignatureRegister.dll.config **,** és az Extensions.SequentialSignatureRegister **bin\\ hibakeresés alatt található\\.**

    # <a name="retail-735-and-later"></a>[Retail 7.3.5 és újabb](#tab/retail-7-3-5)

    A fájl neve Contoso.Commerce.Runtime.SequentialSignatureRegister.dll.config **,** és az Extensions.SequentialSignatureRegister **bin\\ hibakeresés alatt található\\.**

    # <a name="retail-811-and-later"></a>[Retail 8.1.1 és újabb](#tab/retail-8-1-1)

    A fájl neve Contoso.Commerce.Runtime.SequentialSignatureRegister.dll.config **,** és az Extensions.SequentialSignatureRegister **bin\\ hibakeresés alatt található\\.**

    ---

6. A Retail Server konfigurációs fájljának frissítése. **A RetailSDK\\ Packages\\ RetailServer\\ Code\\ web.config fájlban** **adja hozzá a következő sorokat az extensionComposition szakaszhoz**.

    ``` xml
    <add source="assembly" value="Contoso.RetailServer.SalesTransactionSignatureSample" />
    ```

7. Futtassa **az msbuild** csomagot a teljes Retail SDK készletből, hogy telepíthető csomagokat hozzon létre.
8. A csomagok alkalmazása a Microsoft Dynamics Lifecycle Services (LCS) szolgáltatáson keresztül vagy manuálisan. A további tudnivalókat lásd [a Telepíthető csomagok létrehozása.](../dev-itpro/retail-sdk/retail-sdk-packaging.md)

### <a name="enable-the-digital-signature-in-offline-mode-for-modern-pos"></a>A digitális aláírás engedélyezése offline módban a Modern POS terminálon

A Modern POS kapcsolat nélküli módban való digitális aláírásának engedélyezéséhez ezeket a lépéseket kell követnie, miután aktiválta a Modern POS eszközt egy új eszközön.

1. Bejelentkezés az POS alkalmazásba.
2. Az Adatbázis-kapcsolat **állapotlapján** győződjön meg arról, hogy az offline adatbázis teljesen szinkronizálva van. Ha a Függőben **lévő** **letöltések mező értéke 0** (nulla), akkor az adatbázis teljesen szinkronizálva van.
3. Kijelentkezni a POS-terminálról
4. Várjon egy kis ideig, amíg az offline adatbázis teljesen szinkronizálva lesz.
5. Bejelentkezés az POS alkalmazásba.
6. Az Adatbázis-kapcsolat **állapotlapján** győződjön meg arról, hogy az offline adatbázis teljesen szinkronizálva van. Ha az offline adatbázis **mezőjében** **a függő tranzakciók értéke 0** (nulla), akkor az adatbázis teljesen szinkronizálva van.
7. A Modern POS újraindítása.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
