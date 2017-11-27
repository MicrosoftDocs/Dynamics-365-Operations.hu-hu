---
title: "Felhőbeli telepítések rendszerkövetelményei"
description: "Ez a témakör a Microsoft Dynamics 365 for Finance and Operations Enterprise edition aktuális verziójára vonatkozó rendszerkövetelményeket sorolja fel felhőalapú telepítés esetén."
author: sericks007
manager: AnnBe
ms.date: 08/02/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 55651
ms.assetid: e564d51d-42d3-47c5-b388-93b8219c692a
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-08-30
ms.dyn365.ops.version: Platform update 8
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 83637b4b2ccc01950e68569b3b8bee1a7cd69855
ms.contentlocale: hu-hu
ms.lasthandoff: 11/03/2017

---

# <a name="system-requirements-for-cloud-deployments"></a>Felhőbeli telepítések rendszerkövetelményei

[!include[banner](../includes/banner.md)]

Ez a témakör a Microsoft Dynamics 365 for Finance and Operations Enterprise edition aktuális verziójára vonatkozó rendszerkövetelményeket sorolja fel felhőalapú telepítés esetén. Mielőtt telepíti a Finance and Operations szoftvert, amennyiben ez a lépés szükséges, biztosítsa, hogy az ön által használt rendszer eléri vagy meghaladja a minimális hálózati, hardver és szoftver követelményeket.

## <a name="supported-web-browsers"></a>Támogatott böngészők
A webes alkalmazás az alábbi böngészők bármelyikében működik, ha azok a megadott operációs rendszer alatt futnak:

-   Microsoft Edge (legfrissebb elérhető verziója) a Windows 10 rendszeren
-   Internet Explorer 11, Windows 10, Windows 8.1 vagy Windows 7 rendszereken
-   Google Chrome (legfrissebb elérhető verziója) Windows 10, Windows 8.1, Windows 8, Windows 7 rendszereken, vagy Google Nexus 10 táblagépen
-   Apple Safari (legfrissebb elérhető verziója) Mac OS X 10.10 (Yosemite), 10.11 (El Capitan), 10.12 (Sierra) rendszereken, vagy Apple iPad gépen

A böngésző legfrissebb változatáért látogasson el a szoftver gyártójának webhelyére. 

> [!NOTE]
> -   A Task Recorder által generált képek rögzítéséhez és Microsoft Word-dokumentumba való ágyazásához telepítenie kell egy előzetes verziójú Chrome-bővítményt. <!---For instructions about how to install the extension, see [Screenshot Extension setup](../../dev-itpro/user-interface/task-recorder).-->
> -   A munkafolyamat-szerkesztő ClickOnce-alkalmazásként indul el. Csak a Microsoft Edge és az Internet Explorer (a Microsoft Windows egy támogatott verziójának használata esetén) támogatja a ClickOnce-alkalmazásokat. A Workflow Editor ClickOnce alkalmazáshoz 64 bit-kompatibilis operációs rendszer szükséges.
> -   A Report Designer for Financial reporting ClickOnce alkalmazásként indul el. 64 bit-kompatibilis operációs rendszert igényel. Chrome használata esetén, telepítenie kell a ClickOnce kiterjesztést a jelentéstervező kliens letöltéséhez. Ha a Chrome böngészőt Inkognitó módban futtatja, győződjön meg arról, a ClickOnce kiterjesztés engedélyezve van-e az Inkognitó módban.
> -   A PDF-fájlok előnézetének megtekintéséhez olyan böngészők használatát javasoljuk, mint a Microsoft Edge (a legújabb nyilvánosan elérhető verzió) Windows 10 rendszeren, illetve a Google Chrome (a legújabb nyilvánosan elérhető verzió) Windows 10, Windows 8.1, Windows 8 vagy Windows 7 rendszeren vagy Google Nexus 10 táblagépeken.

### <a name="supported-web-browsers-for-retail-cloud-pos"></a>A kiskereskedelmi felhő-POS pénztárgép által támogatott böngészők

A Retail Cloud POS az alábbi böngészők bármelyikében működik, ha azok a megadott operációs rendszer alatt futnak:

-   Microsoft Edge (legfrissebb elérhető verziója) a Windows 10 rendszeren
-   Internet Explorer 11, Windows 10, Windows 8.1 vagy Windows 7 rendszereken
-   Chrome (legutóbbi nyilvánosan elérhető verzió) Windows 10, Windows 8.1 vagy Windows 7 rendszeren

## <a name="network-requirements"></a>Hálózati követelmények
-   A Finance and Operations szoftvert olyan hálózatokhoz tervezték, amelyek várakozási ideje 250-300 milliszekund (ms) vagy kevesebb. Ez a latencia a böngészőklienstől a Microsoft Azure adatközpontig, amely tárolja a Finance and Operationst. Javasoljuk, hogy tesztelje a hálózati késleltetést a következő helyen: <http://www.azurespeed.com>.
-   A Finance and Operations sávszélességi követelményei az ön körülményeitől függenek. A legtöbb jellemző forgatókönyv másodpercenként több mint 50 kilobájt sávszélességet igényel (KBps). Azonban olyan nagyteljesítményű forgatókönyvek esetében, mint például a munkaterületek vagy a kiterjedt testreszabást igénylő forgatókönyvek, nagyobb sávszélességet ajánlunk.

Általánosságban elmondható, hogy a Finance and Operations az internetre optimalizált. A böngésző kliensből az Azure adatközpontba történő oda-vissza utak száma nagyon kicsi, és a teljes hasznos tartalom tömörítve van. 

> [!WARNING]
> Ne úgy számítsa ki a sávszélesség követelményeit az ügyfél helyéről, hogy megszorozza a felhasználók számát a minimális sávszélességi követelményekkel. Adott hely egyidejű használatát nagyon nehéz kiszámítani. A sávszélesség miatt aggódó ügyfelek számára a Finance and Operations előzetes verziójának használata ajánlott.

## <a name="net-framework-requirements"></a>A .NET keretrendszer követelményei
A Finance and Operations esetében a Microsoft .NET-keretrendszer 4.6.2-es verziója szükséges az összes ClickOnce alkalmazáshoz, például a dokumentumátirányító ügynökhöz. További tájékoztatás: [A .NET keretrendszer telepítése](https://msdn.microsoft.com/en-us/library/5a4x27ek(v=vs.110).aspx).

## <a name="supported-microsoft-office-applications"></a>Támogatott Microsoft Office-alkalmazások
A következő Microsoft Office-alkalmazások a Finance and Operations felhő alapú vagy helyszíni telepítései esetén használhatók:

-   A Microsoft Excel és Word bővítmények futtatásához telepítve kell lennie a Microsoft Office 2016 programnak Windows vagy Mac rendszeren. Verziójának követelményeivel kapcsolatos további részletekért lásd: [Office-integráció hibáinak elhárítása](../../dev-itpro/office-integration/office-integration-troubleshooting.md).
-   Az Exportálás Excel-be vagy az Exportálás a Word programba funkcióval létrehozott dokumentumok megtekintéséhez telepíteni kell a Microsoft Office 2007 vagy újabb verzióját.

## <a name="retail-modern-pos-requirements"></a>Retail Modern POS követelményei

> [!NOTE]
> Ha a Retail Modern POS offline adatbázist fog használni, a számítógépnek teljesítenie kell a Microsoft SQL Server minden rendszerkövetelményét. A Retail Modern POS offline adatbázis a következőkön működik: Microsoft SQL Server 2012, Service Pack 3 vagy későbbi, Microsoft SQL Server 2014, Service Pack 2 vagy későbbi, valamint Microsoft SQL Server 2016. Javasoljuk, hogy mindig a rendelkezésre álló legújabb verziót használja, és telepítse az összes legújabb szervizcsomagot.

### <a name="supported-operating-systems"></a>Támogatott operációs rendszerek

-   A Retail Modern POS egy 32 bites alkalmazás, de egyaránt fut az x86 és az x64 architektúrán is.
-   A Retail Modern POS csak Windows 10 Pro, Enterprise, valamint Enterprise Long Term Servicing Branch (LTSB) kiadások esetén támogatott.

### <a name="minimum-system-requirements"></a>Minimális rendszerkövetelmények

-   A minimális támogatott felbontás az 1280×1024.
-   A Retail Modern POS rendszert futtató számítógépnek meg kell felelnie ezeknek a követelményeknek:

    -   Legalább kétmagos processzorral kell rendelkeznie, melynek legalább 2 GHz az órajele.
    -   Legalább 3 GB RAM-mal (véletlen hozzáférésű memória) kell rendelkeznie.
    -   Internet-hozzáféréssel kell rendelkeznie.

## <a name="retail-hardware-station-requirements"></a>Retail hardware station követelményei
### <a name="supported-operating-systems"></a>Támogatott operációs rendszerek

-   A Retail hardware station egy 32 bites alkalmazás, de egyaránt fut az x86 és az x64 architektúrán is.
-   A Retail hardware station a következő operációs rendszereken támogatott:

    -   Windows 7 Professional, Enterprise és Ultimate verzió 
    
        > [!NOTE]
        > A Windows 7 operációs rendszer csak akkor támogatott, ha ön manuálisan telepíti az Internet Explorer 11-et.

    -   Windows 8.1 Update 1 Professional, Enterprise és Embedded verzió
    -   Windows 10 Pro, Enterprise és Enterprise LTSB verzió

### <a name="minimum-system-requirements"></a>Minimális rendszerkövetelmények

A számítógépnek teljesítenie kell a rendszerkövetelményeket a következő elemek telepítéséhez és használatához:

-   Internet Information Services (IIS)
-   Harmadik fél által biztosított hardver

## <a name="retail-store-scale-unit-requirements"></a>Core Retail Store Scale Unit követelményei
### <a name="supported-operating-systems"></a>Támogatott operációs rendszerek

-   A Retail Store Scale Unit egy 32 bites alkalmazás, de egyaránt fut az x86 és az x64 architektúrán is.
-   A Retail Store Scale Unit a következő operációs rendszereken támogatott:

    -   Windows 7 Professional, Enterprise és Ultimate verzió
    -   Windows 8.1 Update 1 Professional, Enterprise és Embedded verzió
    -   Windows 10 Pro, Enterprise és Enterprise LTSB verzió

### <a name="minimum-system-requirements"></a>Minimális rendszerkövetelmények

-   4 GB RAM
-   Maximális processzorsebesség 1,6 GHz magonként (legalább kétmagos)
-   Legalább 10 GB szabad lemezterület (a csatorna-adatbázis használatához sok helyre lehet szükség).

### <a name="recommended-system-requirements"></a>Ajánlott rendszerkövetelmények

-   6 GB RAM
-   2.4 GHz i7 (vagy ezzel egyenértékű) magonkénti CPU-sebesség / (négymagos processzor ajánlott).
-   Legalább 10 GB szabad lemezterület (a csatorna-adatbázis használatához sok helyre lehet szükség).

## <a name="connector-requirements"></a>A Connector követelményei
### <a name="supported-operating-systems"></a>Támogatott operációs rendszerek

-   A Connector for Microsoft Dynamics AX két külön telepítőprogramot tartalmaz: az Async Server Connector service és a Real-time service for Dynamics AX 2012 R3 telepítőprogramokat.
-   Mindkét összetevő 32 bites alkalmazás, de egyaránt futnak az x86 és az x64 architektúrán is.
-   Mindkét összetevőt támogatják a következő operációs rendszerek:

    -   Windows 7 Professional, Enterprise és Ultimate verzió
    -   Windows 8.1 Update 1 Professional, Enterprise és Embedded verzió
    -   Windows 10 Pro, Enterprise és Enterprise LTSB verzió
    -   Microsoft Windows Server 2012 R2 és Microsoft Windows Server 2016

### <a name="minimum-system-requirements"></a>Minimális rendszerkövetelmények
-   2 GB memóriával (4 GB RAM ajánlott.)
-   Maximális processzorsebesség 1,6 GHz magonként (legalább kétmagos)
-   Legalább 10 GB szabad lemezterület (a csatorna-adatbázis használatához sok helyre lehet szükség).

## <a name="requirements-for-development-on-local-vms"></a>A helyi virtuális gépek fejlesztési követelményei
A helyi virtuális gépek fejlesztési követelményeiről lásd: [helyszínen futó virtuális gép](../../dev-itpro/dev-tools/access-instances.md).


## <a name="see-also"></a>Lásd még

[Szerezze be a Dynamics 365 for Finance and Operations Enterprise Edition bétaverzióját](../../dev-itpro/dev-tools/get-evaluation-copy.md)

