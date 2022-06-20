---
title: Norvégiai pénztárgépekkel kapcsolatos telepítési irányelvek
description: Ez a cikk útmutatást ad arról, hogyan lehet engedélyezni a pénztárgép funkciót Norvégia Microsoft Dynamics 365 Commerce honosításában.
author: EvgenyPopovMBS
ms.date: 12/20/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2019-3-1
ms.openlocfilehash: 1f2226432237662e28b9e26017020ab81bb6026b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8899067"
---
# <a name="deployment-guidelines-for-cash-registers-for-norway"></a>Norvégiai pénztárgépekkel kapcsolatos telepítési irányelvek

[!include[banner](../includes/banner.md)]

Ez a cikk útmutatást ad arról, hogyan lehet engedélyezni a pénztárgép funkciót Norvégia Microsoft Dynamics 365 Commerce honosításában. A honosítás az összetevők több kiterjesztésből áll. Ezek a bővítmények olyan műveletek végrehajtásához használhatók, mint például a nyugták egyéni mezőinek nyomtatása, további könyvvizsgálati események, értékesítési tranzakciók és fizetési tranzakciók regisztrálása a pénztárnál (POS), az értékesítési tranzakciók digitális aláírása és a jelentések helyi formátumban történő kinyomtatása. A Norvégiához való honosítással kapcsolatos további tudnivalókat [lásd a Pénztárgép szolgáltatás Norvégiához](./emea-nor-cash-registers.md). A Commerce for Norway konfigurálásról a Commerce for Norway [beállításában található további tájékoztatás](./emea-nor-cash-registers.md#setting-up-commerce-for-norway).

> [!WARNING]
> Az új független csomagolási és [bővítési](../dev-itpro/build-pipeline.md) modell korlátai miatt jelenleg nem használható ehhez a honosítási funkcióhoz. A Retail szoftverfejlesztői csomag (SDK) korábbi verziójában a Lifecycle Services (LCS) egy fejlesztői virtuális gépére (VM) Microsoft Dynamics vonatkozó digitális aláírási mintaverziót kell használnia Norvégiához. A további tudnivalókat [lásd a Norvégiához (legacy) pénztárgépekkel kapcsolatos telepítési irányelvekben](./emea-nor-loc-deployment-guidelines.md).
>
> Az új független csomagolási és kiterjesztésmodell támogatása a pénzügyi integrációs mintákkal a későbbi verziókban tervezve lesz.

## <a name="set-up-fiscal-registration-for-norway"></a>Pénzügyi regisztráció beállítása Norvégia esetében

A Norvégiához tartozó pénzügyi regisztrációs minta a pénzügyi [integrációs](fiscal-integration-for-retail-channel.md) funkciókon alapul, és része a Retail SDK csomagnak. A minta a **Solutions-tárház src\\ FiscalIntegration\\ SequentialSignatureNorway**[Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/) mappájában található ([például a release/9.34](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.34/src/FiscalIntegration/SequentialSignatureNorway) mintája). A minta [egy pénzügyi](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services) dokumentumszolgáltatóból és egy pénzügyi csatlakoztatóból áll, amelyek a Commerce runtime (commerce runtime) kiterjesztései CRT. A Retail SDK használatával kapcsolatos további tudnivalókat lásd a Retail SDK [architektúrája és a független csomagolásos SDK](../dev-itpro/retail-sdk/retail-sdk-overview.md)[felépítési csővezetékének beállítása.](../dev-itpro/build-pipeline.md)

A Pénzügyi regisztrálás beállításának [lépéseit a Commerce-csatornák pénzügyi integrációjának beállítása lépésekkel lehet végrehajtani](./setting-up-fiscal-integration-for-retail-channel.md):

1. [Pénzügyi regisztrációs folyamat beállítása](./setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process). Mindenképpen jegyezze fel a [Norvégiához specifikus pénzügyi regisztrációs folyamat beállításait](#configure-the-fiscal-registration-process).
1. [Hibakezelési beállítások megadása](./setting-up-fiscal-integration-for-retail-channel.md#set-error-handling-settings).
1. [Halasztott pénzügyi regisztráció kézi végrehajtásának engedélyezése](./setting-up-fiscal-integration-for-retail-channel.md#enable-manual-execution-of-postponed-fiscal-registration)
1. [Csatornaösszetevők konfigurálása](#configure-channel-components)

### <a name="configure-the-fiscal-registration-process"></a>A pénzügyi regisztrációs folyamat konfigurálása

A következő lépések szerint engedélyezheti a Pénzügyi nyilvántartási folyamatot Norvégia esetében a Commerce Headquarters számára.

1. A pénzügyi dokumentumszolgáltató és a pénzügyi csatlakoztató konfigurációs fájljainak letöltése a Commerce SDK készletből:

    1. Nyissa meg [Dynamics 365 Commerce a megoldástárházat](https://github.com/microsoft/Dynamics365Commerce.Solutions/).
    1. Az utolsó elérhető kiadási ág megnyitása (például kiadás **[/9.34](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.34)**).
    1. A **src \> FiscalIntegration \> SequentialSignatureNorway \> CommerceRuntime megnyitása**
    1. **Töltse le a pénzügyi bizonylat szolgáltatójának konfigurációs fájlját a DocumentProvider.SequentialSignNorway \> Configuration \> DocumentProviderSequentialSignatureNorwaySample.xml** fájlban ([például a release/9.34](https://github.com/microsoft/Dynamics365Commerce.Solutions/blob/release/9.34/src/FiscalIntegration/SequentialSignatureNorway/CommerceRuntime/DocumentProvider.SequentialSignNorway/Configuration/DocumentProviderSequentialSignatureNorwaySample.xml) fájlban).
    1. A pénzügyi csatlakoztató konfigurációs fájljának letöltése a Connector.SequentialSignNorway **Configuration \> ConnectorSequentialSignatureNorwaySample.xml \> fájlból (** például a kiadás fájlja/9.34 [).](https://github.com/microsoft/Dynamics365Commerce.Solutions/blob/release/9.34/src/FiscalIntegration/SequentialSignatureNorway/CommerceRuntime/Connector.SequentialSignNorway/Configuration/ConnectorSequentialSignatureNorwaySample.xml)

1. Ugrás a **Retail and Commerce \> Headquarters telepítőparaméterek \>\> megosztott paramétereihez** Az Általános **lapon** állítsa **a** Pénzügyi integráció engedélyezése lehetőséget Igen **beállításra**.
1. Menjen a **Retail és Commerce \> csatorna beállítása \> Pénzügyi integráció \> pénzügyi csatlakoztatóihoz**, és töltse be a korábban letöltött pénzügyi csatlakoztató konfigurációs fájlját.
1. Menjen a **Retail és Commerce \> Csatorna beállítása pénzügyi \> integráció \> pénzügyi dokumentumszolgáltatóihoz**, és töltse be a korábban letöltött pénzügyidokumentum-szolgáltató konfigurációs fájlját.
1. Ugrás a **Retail és Commerce \> csatorna beállítása \> Fiscal integration \> Connector funkcionális profiljaihoz**. Hozzon létre egy új funkcionális csatlakoztatóprofilt, és válassza ki a dokumentumszolgáltatót és a korábban betöltött csatlakoztatóját.
1. Ugrás a **Retail és Commerce \> csatorna beállítása \> Fiscal integration \> Connector műszaki profilokhoz**. Hozzon létre egy új technikai csatlakoztatóprofilt, és válassza ki a korábban betöltött csatlakoztatóját. A csatlakoztató típusának beállítása Belső **típusúra**.
1. Menjen a **Retail és Commerce \> csatorna \> beállítása Pénzügyi integráció \> pénzügyi csatlakoztatócsoportjához**, és hozzon létre egy új pénzügyi csatlakoztatócsoportot a korábban létrehozott csatlakoztató funkcionális profilhoz.
1. Ugrás a Kiskereskedelmi és **Commerce csatorna \> beállítása pénzügyi \> integráció \> pénzügyi regisztrációs folyamatainak lépéseihez**. Hozzon létre egy új pénzügyi regisztrációs folyamatot és egy pénzügyi nyilvántartási folyamat lépését, és válassza ki a korábban létrehozott pénzügyi csatlakoztatócsoportot.
1. Ugorjon a következő elemre: **Retail és Commerce \>  Csatorna beállítása \> Pénztárbeállítás \>  Pénztárprofilok \> Funkcióprofilok**. Válasszon ki egy funkcióprofilt, amely ahhoz az üzlethez kapcsolódik, ahol aktiválni kell a regisztrációs folyamatot. A Pénzügyi regisztráció **folyamata** gyors oldalon válassza ki a korábban létrehozott pénzügyi regisztrációs folyamatot. Válassza ki a **korábban** létrehozott csatlakoztató műszaki profilt a Pénzügyi szolgáltatások gyorstára. 
1. Ugorjon a **Kiskereskedelem és kereskedelem \> Kiskereskedelem és kereskedelem informatika \> Elosztási ütemezés** pontra. Az elosztási ütemezés megnyitása, és **az 1070-es és 1090-es** **feladat** kiválasztása az adatoknak a csatorna-adatbázisba történő átviteléhez.

### <a name="configure-the-digital-signature-parameters"></a>A digitális aláírás paramétereinek konfigurálása

Az üzlet értékesítési tranzakcióinak digitális aláírásához használt tanúsítványokat be kell állítania. Az Aláírás az Azure kulcsként tárolt digitális tanúsítványt használja. A Modern POS offline üzemmódjában az aláírás digitális tanúsítvány használatával is használhatja azt, amelyet a Modern POS telepített számítógépének helyi tárolójában tárolnak.

A kulcstárolóban tárolt digitális tanúsítvány használata előtt a következő lépéseket kell végrehajtani.

1. A kulcstárolót létre kell hozva. Javasoljuk, hogy a tárolást a Commerce Scale Unit mértékegység földrajzi elhelyezkedésének megfelelő területen telepítse.
1. A tanúsítványt base64-karakterlánc titkosként kell feltölteni a Key Tároló tárolóba.
1. Az Application Object Server (AOS) alkalmazásnak engedélyezve kell lennie ahhoz, hogy olvasni tudjon a Kulcs Tároló tárolóból.

A Kulcskulcs- és kulcskulcsok használatával kapcsolatos további tudnivalókat lásd [Az Azure kulcs– Kulcssúva (Im) használatának első lépésekben](/azure/key-vault/key-vault-get-started).

Ezután a Kulcs –**Paraméterek** lapon meg kell adnia a Kulcs– Tároló eléréséhez szükséges paramétereket:

- **Név** és **leírás** – a Kulcs Tároló neve és leírása.
- **Kulcs Url-címe** – a KulcsTároló tároló URL-címe
- **Kulcs ügyfél –** a Azure Active Directory Kulcs– Ügyféltároló kulcshoz hitelesítési célból társított (Azure AD) alkalmazás interaktív ügyfél-azonosítója. Ennek az ügyfélnek hozzáféréssel kell lennie a tárolóból való olvasáshoz.
- **Kulcs, Titkos kulcs** – Titkos Azure AD kulcs, amely az alkalmazáshoz van társítva, és amely hitelesítésre használatos a Kulcsot tároló tárolóban.
- **Név**, **leírás** és titkos **hivatkozás** – a tanúsítvány neve, leírása és titkos hivatkozása.

Ezután konfigurálnia kell egy csatlakoztatót a kulcstárolóban vagy a helyi tanúsítványtárolóban tárolt tanúsítványokhoz. Ez a csatlakoztató a csatorna oldalán való bejelentkezésre használható.

1. Ugrás a **Retail és Commerce \> csatorna beállítása \> Fiscal integration \> Connector műszaki profilokhoz**.
1. A Beállítások **gyors** lapon adja meg a digitális aláírások következő paramétereit:

    - **Titkos név** – válassza ki a kulcsparaméterek **lapon korábban beállított titkos nevet**.
    - **Helyi tanúsítvány ujjlenyomata** – adja meg a helyileg tárolt tanúsítvány ujjlenyomatát.
    - **Kivonat algoritmusa** – adja meg az egyik olyan kriptográfiai Microsoft .NET kivonati algoritmust, amelyet támogat például **az SHA1**.
    - **Tanúsítványtár neve** – ez a mező nem kötelező. Itt megadhat egy alapértelmezett üzletnevet, amelyet a helyi tanúsítványok keresésénél használni kell.
    - **Tanúsítványtároló helye** – ez a mező nem kötelező. Itt megadhat egy alapértelmezett üzlethelyet, amelyet a helyi tanúsítványok keresésénél lehet használni.
    - **Először próbálja meg a helyi tanúsítványt** – válassza ezt a lehetőséget, ha alapértelmezés szerint a helyi üzletből származó tanúsítványt használja adatok aláírásához, és nem a Kulcs Kulcs KulcsBól származó tanúsítványhoz.
    - **Állapotellenőrzés aktiválása** – az állapotellenőrzési funkcióval kapcsolatos további tudnivalókat lásd [: Pénzügyi regisztrációk állapotellenőrzése](./fiscal-integration-for-retail-channel.md#fiscal-registration-health-check).

> [!NOTE]
> - Norvégiában **jelenleg csak a SHA1** kriptográfiai kivonat algoritmusa fogadható el.
> - A program hozzáadja az alapértelmezett üzletnevet és tárolóhelyet a helyi tanúsítványok keresésének egyszerűsítése érdekében CRT. Az X509StoreProvider a mappák listáját tartalmazza, ahol a tanúsítványokat tárolják. Ha nincs megadva az alapértelmezett üzletnév és az alapértelmezett üzlethely, az X509StoreProvider a lista minden mappájában megpróbál tanúsítványt találni.

### <a name="configure-channel-components"></a>Csatornaösszetevők konfigurálása

### <a name="development-environment"></a>Fejlesztői környezet

A következő lépések szerint állíthatja be a fejlesztői környezetet, hogy tesztelni és ki tudja terjeszteni a mintát.

1. Le kell tölteni vagy le kell [Dynamics 365 Commerce tölteni a megoldástárházat](https://github.com/microsoft/Dynamics365Commerce.Solutions). Válassza ki a kiadási ág megfelelő verzióját az SDK-nak vagy az alkalmazásverziónak megfelelően. A további tudnivalókat lásd [a Retail SDK-minta- és hivatkozáscsomagok letöltése aHub és NuGet](../dev-itpro/retail-sdk/sdk-github.md) a.
1. Nyissa meg **a SequentialSignatureNorway.sln megoldást** **a Dynamics365Commerce.Solutions\\ FiscalIntegration\\ SequentialSignatureNorway alatt, és építse fel**.
1. A következő CRT bővítmények telepítése:

    1. A bővítmény telepítője CRT:

        - **Commerce Scale Unit:** **A ScaleUnit.SequentialSignatureNorway\\ ScaleUnit.SequentialSignNorway.Installer\\\\ bin\\ debug\\ net461** **mappában keresse meg a ScaleUnit.SequentialSignNorway.Installer** telepítőjét.
        - **CRT Helyi a Modern POS terminálon:** **A SzekquentialSignatureNorway ModernPOS.SequentialSignNorway.Installer\\\\ bin\\ debug\\ net461\\** mappában keresse meg a ModernPos.SequentialSignNorway.Installer **telepítőjét**.

    1. A kiterjesztés telepítőjét CRT a következő parancssorból indítja el:

        - **Commerce Scale Unit:**

            ```Console
            ScaleUnit.SequentialSignNorway.Installer.exe install --verbosity 0
            ```

        - **Helyi CRT a Modern POS terminálon:**

            ```Console
            ModernPOS.SequentialSignNorway.Installer.exe install --verbosity 0
            ```

### <a name="production-environment"></a>Működési környezet

Hajtsa végre [a pénzügyi integrációs minta felépítési folyamatának beállításához szükséges lépéseket a](fiscal-integration-sample-build-pipeline.md) felhőskálaegység és az önkiszolgáló rendszer telepíthető csomagjainak előállításához és kiadásához a pénzügyi integrációs mintához. A **SequentialSignatureNorway build-pipeline.stbml** sablonfájl a megoldástárház **\\**[Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions) tasmappában található YAML_Files csővezetékben.

### <a name="enable-the-digital-signature-in-offline-mode-for-modern-pos"></a>A digitális aláírás engedélyezése offline módban a Modern POS terminálon

A Modern POS kapcsolat nélküli módban való digitális aláírásának engedélyezéséhez ezeket a lépéseket kell követnie, miután aktiválta a Modern POS eszközt egy új eszközön.

1. Bejelentkezés az POS alkalmazásba.
1. Az Adatbázis-kapcsolat **állapotlapján** győződjön meg arról, hogy az offline adatbázis teljesen szinkronizálva van. Ha a Függőben **lévő** **letöltések mező értéke 0** (nulla), akkor az adatbázis teljesen szinkronizálva van.
1. Kijelentkezni a POS-terminálról
1. Az offline adatbázis teljes szinkronizálásának várakozása.
1. Bejelentkezés az POS alkalmazásba.
1. Az Adatbázis-kapcsolat **állapotlapján** győződjön meg arról, hogy az offline adatbázis teljesen szinkronizálva van. Ha az offline adatbázis **mezőjében** **a Függő tranzakciók értéke 0** (nulla), akkor az adatbázis teljesen szinkronizálva van.
1. A Modern POS újranyitása
