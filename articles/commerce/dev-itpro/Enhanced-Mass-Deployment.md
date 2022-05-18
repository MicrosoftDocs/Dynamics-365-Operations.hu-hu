---
title: Lepecsételt Commerce önkiszolgáló-összetevők központi telepítése
description: Ez a témakör bemutatja, hogy hogyan lehet csendes módon telepíteni és telepíteni az önkiszolgáló összetevők telepítőinek keretrendszerét.
author: jashanno
ms.date: 05/11/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: jashanno
ms.search.validFrom: 2021-04-30
ms.openlocfilehash: 5cb27fd0ea366d12c8bd6ee1cdb0c6d584375862
ms.sourcegitcommit: d70f66a98eff0a2836e3033351b482466bd9c290
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/11/2022
ms.locfileid: "8742582"
---
# <a name="mass-deployment-of-sealed-commerce-self-service-components"></a>Lepecsételt Commerce önkiszolgáló-összetevők központi telepítése

[!include [banner](../includes/banner.md)]

Ez a témakör a havonta kiadott lepecsételt keretrendszerre, a minden hónapban kiadott összetevő-telepítőkre vonatkozik, a 10.0.18-as kiadással kezdődően, Microsoft Dynamics és amelyek elérhetővé állnak a Lifecycle Services (LCS) Megosztott eszköztárában. Ne feledje, hogy ezeknek az új telepítőknek az első több kiadása előnézetként **van kiképve**. A megnevezés egyetlen célja azonban az, hogy megkülönböztesse az új telepítőket, míg a Microsoft meghatározza, hogy használ-e további funkcionális követelményeket. Ez nem jelenti azt, hogy a telepítők nem érvényesek termeléshez. Az új telepítők kiadása alapján a Microsoft azt tervezi, hogy 2023. októberben vagy annak körül elavulté tervezi a régi (örökölt) telepítőket. 

Ez a témakör bemutatja, hogyan használhatók az új telepítők csendes telepítésre és parancssori argumentumokkal történő frissítésre. Ezekkel az argumentumokkal többféle módon lehet tömegesen központi telepítést tenni.

> [!NOTE]
> Az új önkiszolgáló, lepecsételt telepítők nem lesznek elérhetők a Headquarters alkalmazásból, csak az LCS-n keresztül tölthetők le.

## <a name="delimiters-for-mass-deployment"></a>Elválasztók tömeges telepítéshez

A következő táblázat bemutatja a parancssori végrehajtásban használható elválasztókat.


| Elválasztó                 | Leírás |
|---------------------------|-------------|
| --AadTokenIssuerPrefix | A Microsoft Azure Active Directory jogkivonat kibocsátójának előtagja Azure AD. |
| --AsyncClientAadClientId | Az Azure AD az ügyfélazonosító, amit az Async Clientnek használnia kell a Headquarters alkalmazással való kommunikáció során. |
| --AsyncClientAppInssyncsInstrumentationKey | Az Async Client AppInsights eszközkulcsa |
| --AsyncClientCertFullPath | A teljesen formázott URL-elérési út, amely az ujjlenyomatot a Headquarters alkalmazással való kommunikáció hitelesítésére használt Async Client Identity certificate Azure AD helyének keresési mérőszámaként használja. Például helyesen `store://My/LocalMachine?FindByThumbprint=<MyThumbprint>` formázott URL-cím. Az érték **\<MyThumbprint\>** helyére a használni szükséges tanúsítvány ujjlenyomata fog lecserélni. Ezt a paramétert ne használja az **-AsyncClientCertTsyncbprint paraméterrel** együtt. |
| --AsyncClientCertTsyncbprint | Az Async Client identitás tanúsítványának ujjlenyomata, Azure AD amely a Központtal való kommunikáció hitelesítésére használható. Ez az ujjlenyomat a **LocalMachine/Saját** üzlet helyének és nevének keresésében használható a megfelelő tanúsítvány megkeresésében. Ezt a paramétert ne használja az **-AsyncClientCertFullPath paraméterrel** együtt. |
| --ClientAppInsügyfélszámítógépInstrumentationKey | Az Ügyfélműszerkre AppInsights vonatkozó kulcs. |
| --CloudPosAppInstrófsInstrumentationKey | A Cloud POS AppInsights eszközkulcsa. |
| --Config | A telepítés során használt konfigurációs fájl. A fájlnévre példa a **Contoso.CommerceScaleUnit.xml**. |
| --CposAadClientId | Az Azure AD eszköz aktiválása során a Felhő POS rendszer által használt ügyfélazonosító. Erre a paraméterre nincs szükség a létesítményekben való telepítés esetén. |
| --Eszköz | Az eszköz azonosítója, amint az a Központ **Eszköz** lapján megjelenik. |
| --EnvironmentId | A környezet azonosítója. |
| --HardwareStationAppInshardsInstrumentationKey | A Hardverállomás AppInsights eszközkulcsa. |
| --Telepítés | Egy paraméter, amely megadja, hogy telepíteni kell-e a telepítő által adott összetevőt. Ez a paraméter nem kötelező. |
| --InstallOffline | A Modern POS rendszer esetében ez a paraméter azt határozza meg, hogy az offline adatbázist is telepíteni és konfigurálni kell. Használja az **-SQLServerName paramétert** is. Ellenkező esetben a telepítő az előfeltételeknek megfelelő alapértelmezett példányt keres. |
| --Port | Az a port, amelyet a Retail Server virtuális könyvtárának társítva kell lennie és használnia kell. Ha nincs beállítva port, a program a 443-as alapértelmezett portot használja. |
| --Jegyzék | A pénztárgép azonosítója, amint a Központ **Pénztárgép** lapján látható. |
| --RetailServerAadClientId | Az Azure AD az ügyfélazonosító, amit a Retail Servernek használnia kell a Headquarters alkalmazással való kommunikáció során. |
| --RetailServerAadResourceId | Az eszköz aktiválása során használt Retail Server Azure AD alkalmazás-erőforrás azonosítója. Erre a paraméterre nincs szükség a létesítményekben való telepítés esetén. |
| --RetailServerCertFullPath | A teljesen formázott URL-elérési út, amely az ujjlenyomatot a Retail Server Identity tanúsítványának Azure AD keresési mérőszámaként használja, és a Központtal való kommunikáció hitelesítésére kell használni. Például egy `store://My/LocalMachine?FindByThumbprint=<MyThumbprint>` megfelelően formázott URL-cím **\<MyThumbprint\>**, ahol az értéket a használni kívánt tanúsítvány ujjlenyomatával cseréli le. Ezt a paramétert ne használja a **-RetailServerCertTserverbprint paraméterrel** együtt. |
| --RetailServerCertTprintbprint | A Retail Server identity tanúsítványának ujjlenyomata, Azure AD amely a Központtal való kommunikáció hitelesítésére használható. Ez az ujjlenyomat a **LocalMachine/Saját** üzlet helyének és nevének keresésében használható a megfelelő tanúsítvány megkeresésében. Ezt a paramétert ne használja a **-RetailServerCertFullPath paraméterrel** együtt. |
| --RetailServerURL | A Retail Server url-címe, amit a telepítőnek használnia kell. (Ez az URL-cím kereskedelmi mérlegegységként is ismert. \[MEZŐ\] URL-CÍME.) A Modern POS rendszer ezt az értéket fogja használni az eszköz aktiválása során. |
| --SkipAadCredentialsCheck| Egy kapcsoló, amely megadja, hogy ki kell-e Azure AD hagyni a hitelesítő adatok előfeltételeit. Az alapértelmezett érték a **hamis**. |
| --SkipCertCheck | Ez a kapcsoló jelzi, hogy ki kell-e hagyni a tanúsítvány előfeltételeit. Az alapértelmezett érték a **hamis**. |
| --SkipIisCheck | Egy kapcsoló, amely azt jelzi, hogy ki kell-e hagyni az Internet Information Services (IIS) előfeltételeinek ellenőrzését. Az alapértelmezett érték a **hamis**. |
| --SkipNetFrameworkCheck | Egy kapcsoló, amely azt jelzi, hogy ki kell-e hagyni a .NET-keretrendszer előfeltétel-ellenőrzését. Az alapértelmezett érték a **hamis**. |
| --SkipScaleUnitHealthcheck | Egy kapcsoló, amely azt jelzi, hogy ki kell-e hagyni a telepített összetevők állapotellenőrzését. Az alapértelmezett érték a **hamis**. |
| --SkipSChannelCheck | Egy kapcsoló, amely azt jelzi, hogy ki kell-e hagyni a biztonságos csatorna-előfeltételek ellenőrzését. Az alapértelmezett érték a **hamis**. |
| --SkipSqlFullTextCheck | Egy kapcsoló, amely azt jelzi, hogy ki kell-e hagyni a teljes szöveges keresést igénylő SQL Server-előfeltétel érvényesítését. Az alapértelmezett érték a **hamis**. |
| --SkipSqlServerCheck | Egy kapcsoló, amely azt jelzi, hogy ki kell-e hagyni az SQL Server előfeltétel-ellenőrzését. Az alapértelmezett érték a **hamis**. |
| --SqlServerName | Az SQL Server neve. Ha a név nincs megadva, a telepítő megpróbálja megtalálni az alapértelmezett példányt. |
| --SslcertFullPath | A teljesen formázott URL-elérési út, amely az ujjlenyomatot használja annak a tanúsítványhelynek a keresési mérőszámaként, amely a mérlegegységRE vonatkozó HTTP-forgalom titkosítására használható. Például egy `store:\/\/My\/LocalMachine\?FindByThumbprint\=\<MyThumbprint\>` megfelelően formázott URL-cím **\<MyThumbprint\>**, ahol az értéket a használni kívánt tanúsítvány ujjlenyomatával cseréli le. Ezt a paramétert ne használja az **-SslCertT sslbprint paraméterrel** együtt. |
| --SslCertT socketbprint | A tanúsítvány ujjlenyomata, amely a mérlegegység HTTP-forgalmának titkosítására használható. Ez az ujjlenyomat a **LocalMachine/Saját** üzlet helyének és nevének keresésében használható a megfelelő tanúsítvány megkeresésében. Ezt a paramétert ne használja az **-SslCertFullPath paraméterrel** együtt. |
| --StoreSystemAosUrl | A Headquarters (AOS) URL-címe. |
| --StoreSystemChannelDatabaseId | A csatorna-adatbázis azonosítója (név). |
| --TenantId | A Azure AD bérlő azonosítója. |
| --TransactionServiceAzureAuthority | A Transaction Service hatósága Azure AD. |
| --TransactionServiceAzureResource | A Transaction Service erőforrása Azure AD. |
| --TrustSqlServerCertificate | Egy kapcsoló, amely megadja, hogy az SQL Server-kapcsolat létesítése során megbízhatónak kell-e lennie a kiszolgálói tanúsítványnak. A biztonsági kockázatok elkerülése érdekében a termelési telepítések soha nem adnak meg **itt igaz értéket**. Az alapértelmezett érték a **hamis**. |
| --Részletesség | A telepítés során kért naplózási szint. Ez az érték általában nem használható. |
| --WindowsPhoneAppInsxosInstrumentationKey | A Hardverállomás AppInsights eszközkulcsa. |

## <a name="general-overview"></a>Általános áttekintés

Az önkiszolgáló telepítők új keretrendszere számos funkciót és fejlesztést tartalmaz. Az új keretrendszer jelenleg csak a Modern POS, a hardverállomás és aSTB (ön által használt) telepítőket hozza létre. Fontos megérteni a lepecsételt telepítők alapvető parancssori használatát, amelynek a következő példában használthoz hasonlónak kell lennie. 
 
```Console
<Component Installer Name>.exe install --<Parameter Name> "<Parameter Information>"
```

A telepítőnek telepítenie kell a **paramétert** (vagy **el** kell távolítania a telepítést), valamint a telepítéshez specifikus paramétereket. **A paraméternévnek** tartalmaznia kell minden szükséges paramétert, például a regisztrálást, a URL-címet vagy a tanúsítvány adatait. **A paraméterinformációknak** tartalmazniuk kell a paraméterekkel kapcsolatos további információkat.

A lepecsételt keretrendszer létrejött, hogy lehetővé tegye a következő módosításokat:
- **Lepecsételve** – az új telepítő keretrendszer teljesen elválasztja a Microsoft által elosztott alapösszetevő-telepítőket a extensibility alapú testreszabástól. A testreszabott beállítások telepítése ezt követően meg fog történt, de a frissítések kapcsán meg lesznek eresztve (így a frissítések csak a Microsoft alapösszetevőre, csak a testreszabott összetevőkre vagy mindkettőre lesznek engedélyezve).
- **GUI-kevesebb** – már nincs felhasználói felület. Ehelyett minden egyes összetevő telepítőjére egy teljes parancssori végrehajtást kell végrehajtani. Ez a módosítás annak a számos kulcsváltozásnak vagy funkciónak az egyike, amely az új telepítő keretrendszert a tömeges telepítéshez használja.
- **Mélyebb naplózás** – a továbbfejlesztett telepítési naplók segítségével jobban lehet érvényesíteni a telepítés befejeződését vagy sikertelenségét, a végrehajtott lépéseket, valamint a generált figyelmeztetéseket vagy hibákat.
- **Karbantartás** – az új keretrendszerben az összetevő-telepítők úgy tudják karbantartani a telepítési könyvtárak tisztítását, hogy az összetevőmappa teljes tartalmát törlik, mielőtt az újabb összetevőket telepíteik. Ezzel a tisztítással gondoskodhat arról, hogy ne legyenek olyan maradék fájlok, amelyek problémákat okozhatnak, és megakadályozhatják a telepítést.

Három összetevő még nincs áttelepítve az új keretrendszerbe: a Virtuális perifériás szimulátor, az Async Server Connector szolgáltatás (a Dynamics AX 2012 R3 támogatásához használatos) és a Real-time Service replacement (a Dynamics AX 2012 R3 támogatásához használatos).

> [!NOTE]
> A telepítőket helyben tárolja a telepítő, és megtartja őket a telepítők.  Az idő során fontos a visszatartott telepítőket kezelni vagy törölni, hogy ne hulladékként tárolódjön a lemezterület. Azt ajánljuk, hogy a legújabb verziókban az alapösszetevők és a bővítménytelepítők aktuális telepítőjét megtartsa a rendkívüli helyzetek ki-visszaszerzés céljából.

## <a name="migration"></a>Áttelepítési

A keretrendszer régi összetevő-telepítőiből az új keretrendszer-összetevő telepítőibe való áttelepítéshez el kell távolítani a régi összetevőket.

- **Modern POS** – az új telepítő keretrendszer miatt az alkalmazás új aláírás-azonosítót kapott. Emiatt az új keretrendszer Modern POS összetevő telepítése előtt el kell távolítani a régi összetevőket. A teljes eltávolítás követelménye miatt újra szükség van az eszköz aktiválására. (Ez az eszköz-újraaktiválás egyszer szükséges, feltéve, hogy az eltávolítás nem történik meg újra.)
- **Hardverállomás** – az új telepítő keretrendszere megköveteli az alapmappa szerkezetének átdolgozását. Emiatt az új keretrendszer hardverállomás-összetevő telepítése előtt el kell távolítani a régi összetevőket.
- **Commerce Scale Unit (COMMERCE Scale Unit, önkihelyezett)** – az IIS-webhelyek sorozataként az új telepítő keretrendszer az alapmappa szerkezetének átdolgozását igényli.  A régi összetevők teljes eltávolítását ezért csak akkor lehet telepíteni, ha telepítve van a KERETRENDSZER ÚJ FOGJA (önkihelyezett) összetevő.

## <a name="modern-pos"></a>Modern POS

### <a name="before-you-begin"></a>Előzetes feladatok

Rendkívül fontos, hogy eltávolítsa a régi, önkiszolgáló Modern POS összetevőt. A további tudnivalókat lásd a témakör korábbi áttelepítési lépéseinél.

### <a name="examples-of-silent-deployment"></a>Példák csendes telepítésre

Ez a szakasz példákat mutat be a Modern POS telepítéséhez használt parancsokra.

#### <a name="silently-install-modern-pos"></a>A Modern POS csendes telepítése

A következő parancs csendes módon telepíti (vagy frissíti) a Modern POS alkalmazást. A szabványos parancssori struktúrával rendelkezik, amely az aktuálisan telepített összetevők csendes szervizelésére szolgál. A struktúra a **&lt; InstallerName.exe&gt; alapvető értékeit használja**.

A következő alapvető parancs a rendelkezésre álló beállításokat tartalmazza telepítés kérése esetén. Kifejezetten ajánljuk, hogy a rendszer ezt a parancsot használja az első teszteléskor vagy a telepítővel való használat során.

```Console
CommerceModernPOS.exe --help install
```

> [!NOTE]
> A Modern POS esetében nincs szükség konfigurációs fájlra. A telepítőnek már vannak paraméterei (a témakörben korábban látható) az eszköz aktiválása során használt különféle értékekre.

A következő parancs minden paramétert meghatároz, amely az eszköz aktiválása során szükséges a Modern POS alkalmazás telepítése után. Ez a példa a **Demo-3** pénztárgépet használja, amely általában bemutatóadatokban Dynamics 365 Commerce használatos.

```Console
CommerceModernPOS.exe install --Register "Houston-3" --Device "Houston-3" --RetailServerURL "https://MyDynamics365CommerceURL.dynamics.com/Commerce"
```

Az alábbi parancs beállítja az offline adatbázis telepítéséhez és konfigurálához használt paramétereket. Az SQL Server a használni kívánt konfigurációs fájllal együtt van megadva.

```Console
CommerceModernPOS.exe install --InstallOffline --SQLServerName "SQLExpress" --Config "ModernPOS.Houston-3.xml"
```

Ezeknek a fogalmaknak a kombinációval lehet megvalósítani a kívánt telepítési eredményeket.

## <a name="hardware-station"></a>Hardverállomás

### <a name="before-you-begin"></a>Előzetes feladatok

Kulcsfontosságú, hogy eltávolítsa a régi önkiszolgáló hardverállomás összetevőt. A további tudnivalókat lásd a témakör korábbi áttelepítési lépéseinél. Már nincs kereskedőiszámla-információs eszköz. Ehelyett a kereskedői számla adatait telepíti a rendszer, amikor a POS terminált párosítja a hardverállomással. Amikor első alkalommal teszteli ezt a telepítőt, kifejezetten ajánljuk, hogy futtassa a következő parancsot:

```Console
CommerceHardwareStation.exe --help install
```

### <a name="examples-of-silent-deployment"></a>Példák csendes telepítésre

Ez a szakasz néhány példát mutat be a hardverállomás telepítéséhez szükséges parancsokra.

#### <a name="silently-install-hardware-station"></a>Hardverállomás csendes telepítése

A következő parancs csendes módon telepíti (vagy frissíti) a hardverállomást. Az aktuálisan telepített összetevők szervizszolgáltatására használt szabványos parancssori struktúrával rendelkezik. A struktúra a **&lt; InstallerName.exe&gt; alapvető értékeit használja**.

A következő alapparancs a végrehajtható fájl telepítőjét futtatja.

```Console
HardwareStation.exe install --Port 443 --StoreSystemAOSURL "https://MyDynamics365CommerceURL.dynamics.com/" --StoreSystemChannelDatabaseID "Houston" --SSLCertThumbprint "MySSLCertificateThumbprintOftenHasNumbers"
```

> [!NOTE]
> A hardverállomáshoz nem szükséges konfigurációs fájl. A telepítőnek már vannak paraméterei (a témakörben korábban látható) a különféle szükséges értékekre.

A következő parancs minden paramétert megad, amely szükséges az előfeltételek ellenőrzésének kihagyásához egy szokásos telepítés során. 

> [!NOTE]
> A csekkek kihagyása nem ajánlott teljes előre történő tesztelés nélkül, illetve fejlesztési helyzetekben.

```Console
HardwareStation.exe install --SkipFirewallUpdate --SkipOPOSCheck --SkipVersionCheck --SkipURLCheck --Config "HardwareStation.Houston.xml"
```

Ahogy az a szokásos, az általános fogalom, hogy a kombinációs vagy megfeleltethető ezeknek a fogalmaknak a elérése érdekében el lehet érni a kívánt telepítési eredményeket.

## <a name="commerce-scale-unit-self-hosted"></a>Commerce Scale Unit (saját tárolású)

Amikor a telepítőt első alkalommal teszteli, javasolt a következő parancs futtatása:

```Console
CommerceStoreScaleUnitSetup.exe --help install
```

### <a name="before-you-begin"></a>Előzetes feladatok

Rendkívül fontos, hogy eltávolítsa a régi ÖNkiszolgáló RENDSZER (önkihelyezett) összetevőt. A további tudnivalókat lásd a témakör korábbi áttelepítési lépéseinél.

### <a name="examples-of-silent-deployment"></a>Példák csendes telepítésre

Ez a szakasz példákat mutat be a PARANCCS (ön által használt) telepítéséhez használt parancsokra.

#### <a name="silently-install-csu-self-hosted"></a>Csendes telepítés – FOGJA (ön által tárolt)

A következő parancs csendes módon telepíti (vagy frissíti) AZ ADATOKAT (ön által tárolt). A szabványos parancssori struktúrával rendelkezik, amely az aktuálisan telepített összetevők csendes szervizelésére szolgál. A struktúra a **&lt; InstallerName.exe&gt; alapvető értékeit használja**.

A többi önkiszolgáló telepítővel összehasonlítva a Commerce Scale Unit (STB) összetettebb, és meglehetősen nagy mennyiségű további információt igényel. A következő parancs az a minimális parancs (paraméterekkel), amely a végrehajtható fájl telepítőjének futtatásához szükséges, ha nincs konfigurációs fájl.

```Console
CommerceScaleUnit.exe install --port 446 --SSLCertThumbprint "MySSLCertificateThumbprintOftenHasNumbers" --RetailServerCertFullPath "store://My/LocalMachine?FindByThumbprint=MyCertificateThumbprintUsedByRetailServer" --AsyncClientAADClientID "MyAAD-Client-IDFor-AsyncClient" --RetailServerAADClientID "MyAAD-Client-IDFor-RetailServer" --CPOSAADClientID "MyAAD-Client-IDFor-CloudPOS" --RetailServerAADResourceID "https://retailstorescaleunit.retailserver.com" --TrustSqlServerCertificate --Config "Contoso.StoreSystemSetup.xml"
```

> [!NOTE]
> Konfigurációs fájlra akkor is szükség van, ha a VAN (ön által tárolt) fájl szükséges.

A következő parancs egy pontosabb parancs, amely a végrehajtható fájl telepítőjét bizonyos alternatív paraméterekkel futtatja.

```Console
CommerceScaleUnit.exe install --Port 446 --SSLCertFullPath "store://My/LocalMachine?FindByThumbprint=MySSLCertificateThumbprintOftenHasNumbers" --AsyncClientCertFullPath "store://My/LocalMachine?FindByThumbprint=MySSLCertificateThumbprintOftenHasNumbers" --RetailServerCertFullPath "store://My/LocalMachine?FindByThumbprint=MyCertificateThumbprintUsedByRetailServer" --AsyncClientAADClientID "MyAAD-Client-IDFor-AsyncClient" --RetailServerAADClientID "MyAAD-Client-IDFor-RetailServer" --CPOSAADClientID "MyAAD-Client-IDFor-CloudPOS" --RetailServerAADResourceID "https://retailstorescaleunit.retailserver.com" --TrustSqlServerCertificate --Verbosity 0 --Config "Contoso.StoreSystemSetup.xml"
```

A következő parancs olyan paramétereket ad meg, amelyek szükségesek ahhoz, hogy a rendszer átugorja az előfeltételek ellenőrzését egy szokásos telepítés során. 

> [!NOTE]
> A csekkek kihagyása nem ajánlott teljes előre történő tesztelés nélkül, illetve fejlesztési helyzetekben.


```Console
CommerceScaleUnit.exe installer --skipscaleunithealthcheck --skipcertcheck --skipaadcredentialscheck --skipschannelcheck --skipiischeck --skipnetcorebundlecheck --skipsqlservercheck --skipnetframeworkcheck --skipversioncheck --skipurlcheck --Config "Contoso.StoreSystemSetup.xml" --SSLCertFullPath "store://My/LocalMachine?FindByThumbprint=MySSLCertificateThumbprintOftenHasNumbers" --AsyncClientCertFullPath "store://My/LocalMachine?FindByThumbprint=MySSLCertificateThumbprintOftenHasNumbers" --RetailServerCertFullPath "store://My/LocalMachine?FindByThumbprint=MyCertificateThumbprintUsedByRetailServer" --AsyncClientAADClientID "MyAAD-Client-IDFor-AsyncClient" --RetailServerAADClientID "MyAAD-Client-IDFor-RetailServer" --CPOSAADClientID "MyAAD-Client-IDFor-CloudPOS" --RetailServerAADResourceID "https://retailstorescaleunit.retailserver.com" --TrustSqlServerCertificate
```

Ezeknek a fogalmaknak a kombinációval lehet megvalósítani a kívánt telepítési eredményeket.

<!--## Mass deployment examples using InTune

This section will be added in a future update.

## Mass deployment examples using System Center Configuration Manager (SCCM)

This section will be added in a future update.-->

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
