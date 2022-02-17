---
title: Útmutató a pénztárgépekhez Norvégiában
description: Ez a témakör útmutatást nyújt a pénztárgép funkciójának engedélyezéséhez a Microsoft Dynamics 365 Commerce lokalizáció Norvégiára.
author: EvgenyPopovMBS
ms.date: 12/20/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2019-3-1
ms.openlocfilehash: f0744b18ed59c692ae336c92e488d339ae158368
ms.sourcegitcommit: 5cefe7d2a71c6f220190afc3293e33e2b9119685
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/01/2022
ms.locfileid: "8077140"
---
# <a name="deployment-guidelines-for-cash-registers-for-norway"></a>Útmutató a pénztárgépekhez Norvégiában

[!include[banner](../includes/banner.md)]

Ez a témakör útmutatást nyújt a pénztárgép funkciójának engedélyezéséhez a Microsoft Dynamics 365 Commerce lokalizáció Norvégiára. A lokalizáció több komponensbővítésből áll. Ezekkel a bővítményekkel olyan műveleteket hajthat végre, mint például egyéni mezők nyomtatása a nyugtákon, további ellenőrzési események, értékesítési tranzakciók és fizetési tranzakciók regisztrálása az értékesítés helyén (POS), értékesítési tranzakciók digitális aláírása és jelentések helyi formátumban történő nyomtatása. A norvég lokalizációval kapcsolatos további információkért lásd: [Pénztárgép funkció Norvégiában](./emea-nor-cash-registers.md). A Commerce for Norway konfigurálásával kapcsolatos további információkért lásd: [A Commerce beállítása Norvégiában](./emea-nor-cash-registers.md#setting-up-commerce-for-norway).

> [!WARNING]
> A korlátok miatt a [új független csomagolási és bővítési modell](../dev-itpro/build-pipeline.md), jelenleg nem használható ehhez a lokalizációs funkcióhoz. A Norvégiára vonatkozó digitális aláírási minta verzióját kell használnia a Kiskereskedelmi szoftverfejlesztő készlet (SDK) előző verziójában egy fejlesztői virtuális gépen (VM)Microsoft Dynamics Életciklus-szolgáltatások (LCS). További információkért lásd [Norvégiában a pénztárgépek telepítési irányelvei (örökölt)](./emea-nor-loc-deployment-guidelines.md).
>
> A költségvetési integrációs minták új független csomagolási és kiterjesztési modelljének támogatását tervezik a későbbi verziókhoz.

## <a name="set-up-fiscal-registration-for-norway"></a>Fiskális regisztráció beállítása Norvégiában

A Norvégia adózási regisztrációs mintája a [fiskális integrációs funkcionalitás](fiscal-integration-for-retail-channel.md) és a Retail SDK része. A minta a **src\\ Fiskális integráció\\ SequentialSignatureNorvégia** mappa a [Dynamics 365 Commerce Megoldások](https://github.com/microsoft/Dynamics365Commerce.Solutions/) adattár (pl.[a minta kiadásban/9.34](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.34/src/FiscalIntegration/SequentialSignatureNorway)). A minta [áll](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services) egy fiskális dokumentum-szolgáltató és egy fiskális csatlakozó, amelyek a Commerce futtatókörnyezet kiterjesztései (CRT). A Kiskereskedelmi SDK használatáról a Retail SDK architektúrája [és](../dev-itpro/retail-sdk/retail-sdk-overview.md) build-folyamat beállítása a független csomagolású SDK-hoz [című témakörben talál](../dev-itpro/build-pipeline.md) további információt.

Végezze el a fiskális regisztráció beállítási lépéseit, amelyek leírása a következő helyen található: [Állítsa be a kereskedelmi csatornák pénzügyi integrációját](./setting-up-fiscal-integration-for-retail-channel.md):

1. [Állítsa be az adózási regisztrációs folyamatot](./setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process). Ügyeljen arra, hogy jegyezze fel a fiskális regisztrációs folyamat beállításait [Norvégiára jellemző](#configure-the-fiscal-registration-process).
1. [Állítsa be a hibakezelési beállításokat](./setting-up-fiscal-integration-for-retail-channel.md#set-error-handling-settings).
1. [Az elhalasztott adóregisztráció kézi végrehajtásának engedélyezése](./setting-up-fiscal-integration-for-retail-channel.md#enable-manual-execution-of-postponed-fiscal-registration).
1. [Csatornaösszetevők konfigurálása](#configure-channel-components).

### <a name="configure-the-fiscal-registration-process"></a>Állítsa be a fiskális regisztrációs folyamatot

Kövesse ezeket a lépéseket, hogy engedélyezze a Norvégia adóügyi regisztrációs folyamatát a Commerce központjában.

1. Töltse le az adódokumentum-szolgáltató és a fiskális csatlakozó konfigurációs fájljait a Commerce SDK-ból:

    1. Nyissa meg a [Dynamics 365 Commerce Megoldások](https://github.com/microsoft/Dynamics365Commerce.Solutions/) adattárat.
    1. Nyissa meg az utolsó elérhető kiadási ágat (például **[kiadás/9.34](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.34)**).
    1. Nyisd ki **src \> Fiskális integráció \> SequentialSignatureNorvégia \> CommerceRuntime**.
    1. Töltse le az adódokumentum-szolgáltató konfigurációs fájlját a következő címről: **DocumentProvider.SequentialSignNorway \> Konfiguráció \> DocumentProviderSequentialSignatureNorwaySample.xml** (például, [a kiadás/9.34 fájl](https://github.com/microsoft/Dynamics365Commerce.Solutions/blob/release/9.34/src/FiscalIntegration/SequentialSignatureNorway/CommerceRuntime/DocumentProvider.SequentialSignNorway/Configuration/DocumentProviderSequentialSignatureNorwaySample.xml)).
    1. Töltse le a fiskális csatlakozó konfigurációs fájlját a következő címről: **Csatlakozó.SequentialSignNorway \> Konfiguráció \> ConnectorSequentialSignatureNorwaySample.xml** (például, [a kiadás/9.34 fájl](https://github.com/microsoft/Dynamics365Commerce.Solutions/blob/release/9.34/src/FiscalIntegration/SequentialSignatureNorway/CommerceRuntime/Connector.SequentialSignNorway/Configuration/ConnectorSequentialSignatureNorwaySample.xml)).

1. Menj **Kiskereskedelem és kereskedelem \> A központ felállítása \> Paraméterek \> Megosztott paraméterek**. Az Általános **lapon állítsa a** Költségvetési integráció **engedélyezése beállítást Igen értékre** **.**
1. Lépjen a **Kiskereskedelmi és kereskedelmi \> csatorna beállítására \> Pénzügyi integráció \> Pénzügyi összekötők, és töltse be a korábban letöltött pénzügyi összekötő konfigurációs** fájlt.
1. Menj **Kiskereskedelem és kereskedelem \> Csatorna beállítása \> Fiskális integráció \> Fiskális dokumentumszolgáltatók**, és töltse be a korábban letöltött adódokumentum-szolgáltató konfigurációs fájlját.
1. Lépjen a **Kiskereskedelmi és kereskedelmi \> csatorna beállítására \> Pénzügyi integrációs \> összekötő funkcionális profiljai**. Hozzon létre egy új csatlakozási funkcióprofilt, és válassza ki a dokumentumszolgáltatót és a korábban betöltött csatlakozót.
1. Lépjen a **Kiskereskedelmi és kereskedelmi \> csatorna beállítására \> Pénzügyi integráció \> Összekötő technikai profiljai**. Hozzon létre egy új csatlakozási műszaki profilt, és válassza ki a korábban betöltött csatlakozót. Állítsa be a csatlakozó típusát **Belső**.
1. Menj **Kiskereskedelem és kereskedelem \> Csatorna beállítása \> Fiskális integráció \> Fiskális összekötő csoportok**, és hozzon létre egy új pénzügyi összekötő csoportot a korábban létrehozott összekötő funkcionális profilhoz.
1. Lépjen a **Kiskereskedelmi és kereskedelmi \> csatorna beállítására \> Pénzügyi integráció \> Pénzügyi regisztrációs folyamatok**. Hozzon létre egy új adóregisztrációs folyamatot és egy fiskális regisztrációs folyamat lépést, és válassza ki a korábban létrehozott adóösszekötő csoportot.
1. Ugorjon a következő elemre: **Retail és Commerce \>  Csatorna beállítása \> Pénztárbeállítás \>  Pénztárprofilok \> Funkcióprofilok**. Válasszon ki egy olyan funkcióprofilt, amely ahhoz az üzlethez kapcsolódik, ahol a regisztrációs folyamatot aktiválni kell. **A Pénzügyi regisztrációs folyamat** gyorslapon válassza ki a korábban létrehozott pénzügyi regisztrációs folyamatot. A **Adóügyi szolgáltatások** FastTab, válassza ki a korábban létrehozott csatlakozási műszaki profilt. 
1. Ugorjon a **Kiskereskedelem és kereskedelem \> Kiskereskedelem és kereskedelem informatika \> Elosztási ütemezés** pontra. Nyissa meg a terjesztési ütemezést, és válassza ki a munkákat **1070** és **1090** adatok átviteléhez a csatorna adatbázisba.

### <a name="configure-the-digital-signature-parameters"></a>Konfigurálja a digitális aláírás paramétereit

Be kell állítania az értékesítési tranzakciók digitális aláírására szolgáló tanúsítványokat az üzletben. Az Azure Key Vaultban tárolt digitális tanúsítványt használják az aláíráshoz. A Modern POS offline üzemmódjában az aláírás egy digitális tanúsítvány használatával is elvégezhető, amely annak a gépnek a helyi tárolójában van tárolva, amelyre a Modern POS telepítve van.

A Key Vault tárhelyen tárolt digitális tanúsítvány használata előtt a következő lépéseket kell végrehajtania.

1. Létre kell hozni a Key Vault tárhelyet. Javasoljuk, hogy a tárhelyet ugyanabban a földrajzi régióban telepítse, mint a Commerce Scale Unit.
1. A tanúsítványt fel kell tölteni a Key Vault tárhelyre base64 karakterlánc-titkaként.
1. Az Application Object Server (AOS) alkalmazásnak jogosultnak kell lennie a Key Vault tároló titkainak olvasására.

A Key Vault használatával kapcsolatos további információkért lásd: [Kezdje el az Azure Key Vault használatát](/azure/key-vault/key-vault-get-started).

Következő, a **Key Vault paraméterek** oldalon meg kell adnia a Key Vault tárhely eléréséhez szükséges paramétereket:

- **Név** és **Leírás** – A Key Vault tárhely neve és leírása.
- **Key Vault URL** – A Key Vault tárhely URL-címe.
- **Key Vault kliens** – Az interaktív ügyfélazonosító a Azure Active Directory (Azure AD) alkalmazás, amely hitelesítési célból a Key Vault tárolóhoz van társítva. Ennek az ügyfélnek hozzáféréssel kell rendelkeznie a tároló titkainak olvasásához.
- **Key Vault titkos kulcs** – Egy titkos kulcs, amely a Azure AD alkalmazás, amelyet a Key Vault tárolóban történő hitelesítésre használnak.
- **Név**, **·**, és **Titkos hivatkozás** – A tanúsítvány neve, leírása és titkos hivatkozása.

Ezután be kell állítania egy összekötőt a Key Vault-ban vagy a helyi tanúsítványtárolóban tárolt tanúsítványaihoz. Ez a csatlakozó a csatornaoldali aláírásra szolgál.

1. Lépjen a **Kiskereskedelmi és kereskedelmi \> csatorna beállítására \> Pénzügyi integráció \> Összekötő technikai profiljai**.
1. A **Beállítások** FastTab, adja meg a következő paramétereket a digitális aláírásokhoz:

    - **Titkos név** – Válassza ki a titkos nevet, amelyet korábban konfigurált az oldalon **Key Vault paraméterek** oldalon.
    - **Helyi tanúsítvány ujjlenyomata** – Adjon meg ujjlenyomatot a helyben tárolt tanúsítványhoz.
    - **Hash algoritmus** – Adja meg a által támogatott kriptográfiai hash algoritmusok egyikét Microsoft .NET, mint például **SHA1**.
    - **Tanúsítványbolt neve** – Ez a mező nem kötelező. Itt megadhat egy alapértelmezett üzletnevet, amelyet a helyi tanúsítványok keresésénél használni kell.
    - **Tanúsítvány bolt helye** – Ez a mező nem kötelező. Itt megadhat egy alapértelmezett üzlethelyet, amelyet a helyi tanúsítványok keresésénél lehet használni.
    - **Először próbálja ki a helyi tanúsítványt** – Válassza ezt a lehetőséget, ha alapértelmezés szerint a helyi tárolóból származó tanúsítványt szeretné használni az adatok aláírására a Key Vault tanúsítványa helyett.
    - **Aktiválja az állapotfelmérés** – Az állapotfelmérés funkcióval kapcsolatos további információkért lásd: [Fiskális regisztrációs állapotfelmérés](./fiscal-integration-for-retail-channel.md#fiscal-registration-health-check).

> [!NOTE]
> - Csak a **SHA1** kriptográfiai hash algoritmus jelenleg elfogadható Norvégia számára.
> - Az alapértelmezett boltnév és az áruház helye hozzáadásra került, hogy leegyszerűsítsék a helyi tanúsítványok keresésének folyamatát CRT. Az X509StoreProvider a mappák listáját tartalmazza, ahol a tanúsítványokat tárolják. Ha az alapértelmezett áruháznév és az alapértelmezett tárolóhely nincs megadva, az X509StoreProvider megpróbál tanúsítványt találni a listán szereplő összes mappában.

### <a name="configure-channel-components"></a>Csatornaösszetevők konfigurálása

### <a name="development-environment"></a>Fejlesztői környezet

Kövesse az alábbi lépéseket egy fejlesztői környezet beállításához, amely lehetővé teszi a minta tesztelését és kiterjesztését.

1. Klónozza vagy töltse le a [Dynamics 365 Commerce Solutions](https://github.com/microsoft/Dynamics365Commerce.Solutions) adattárat. Válassza ki a megfelelő kiadási ágverziót az SDK/alkalmazás verziójának megfelelően. További információkért lásd [Töltsön le Retail SDK-mintákat és referenciacsomagokat a GitHubból és a NuGet](../dev-itpro/retail-sdk/sdk-github.md).
1. Nyissa meg a **SequentialSignatureNorway.sln** alatti megoldás **Dynamics365Commerce.Solutions\\ Fiskális integráció\\ SequentialSignatureNorvégia**, és megépíteni.
1. Telepítés CRT kiterjesztések:

    1. Találd meg CRT bővítmény telepítő:

        - **Kereskedelmi mértékegység:** Ban,-ben **SequentialSignatureNorvégia\\ ScaleUnit\\ ScaleUnit.SequentialSignNorway.Installer\\ kuka\\ Debug\\ net461** mappát, keresse meg a **ScaleUnit.SequentialSignNorway.Installer** telepítő.
        - **Helyi CRT a modern POS-on:** Ban,-ben **SequentialSignatureNorvégia\\ Modern POS\\ ModernPos.SequentialSignNorway.Installer\\ kuka\\ Debug\\ net461** mappát, keresse meg a **ModernPos.SequentialSignNorway.Installer** telepítő.

    1. Indítsa el a CRT kiterjesztés telepítője a parancssorból:

        - **Kereskedelmi mértékegység:**

            ```Console
            ScaleUnit.SequentialSignNorway.Installer.exe install --verbosity 0
            ```

        - **Helyi CRT a modern POS-on:**

            ```Console
            ModernPOS.SequentialSignNorway.Installer.exe install --verbosity 0
            ```

### <a name="production-environment"></a>Működési környezet

Kövesse a lépéseket [Állítson be egy összeállítási folyamatot a fiskális integrációs mintához](fiscal-integration-sample-build-pipeline.md) a Cloud Scale Unit és az önkiszolgáló telepíthető csomagok létrehozása és kiadása a költségvetési integrációs mintához. A **SequentialSignatureNorway build-pipeline.yaml** sablon YAML fájl megtalálható a **Csővezeték\\ YAML_Files** mappa a [Dynamics 365 Commerce Megoldások](https://github.com/microsoft/Dynamics365Commerce.Solutions) adattár.

### <a name="enable-the-digital-signature-in-offline-mode-for-modern-pos"></a>Engedélyezze a digitális aláírást offline módban a Modern POS számára

Ha engedélyezni szeretné a digitális aláírást offline módban a Modern POS-hoz, kövesse ezeket a lépéseket, miután aktiválta a Modern POS-t egy új eszközön.

1. Bejelentkezés az POS alkalmazásba.
1. A **Adatbázis kapcsolat állapota** oldalon, győződjön meg arról, hogy az offline adatbázis teljesen szinkronizálva van. Amikor az értéke a **Függőben lévő letöltések** mező az **0** (nulla), az adatbázis teljesen szinkronizálva van.
1. Jelentkezzen ki a POS-ból.
1. Várja meg, amíg az offline adatbázis teljesen szinkronizálódik.
1. Bejelentkezés az POS alkalmazásba.
1. A **Adatbázis kapcsolat állapota** oldalon, győződjön meg arról, hogy az offline adatbázis teljesen szinkronizálva van. Amikor az értéke a **Függőben lévő tranzakciók az offline adatbázisban** mező az **0** (nulla), az adatbázis teljesen szinkronizálva van.
1. Nyissa meg újra a Modern POS-t.
