---
title: "Rendszerkövetelmények"
description: "Ez a témakör a Microsoft Dynamics 365 Finance and Operations Enterprise edition aktuális verziójára vonatkozó rendszerkövetelményeket sorolja fel felhő alapú vagy helyszíni telepítés esetén."
author: sericks007
manager: AnnBe
ms.date: 07/14/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, Developer, IT Pro
ms.reviewer: robinr
ms.search.scope: Core
ms.custom: 55651
ms.assetid: e564d51d-42d3-47c5-b388-93b8219c692a
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-08-30T00:00:00.000Z
ms.dyn365.ops.version: Platform update 2
ms.translationtype: HT
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: 871ba89973f6af341c536f67db056bebb54600b3
ms.contentlocale: hu-hu
ms.lasthandoff: 07/25/2017

---

# <a name="system-requirements"></a>Rendszerkövetelmények

[!include[banner](../includes/banner.md)]


Ez a témakör a Microsoft Dynamics 365 Finance and Operations Enterprise edition aktuális verziójára vonatkozó rendszerkövetelményeket sorolja fel, felhő alapú vagy helyszíni telepítés esetén. Mielőtt telepíti a Finance and Operations szoftvert, amennyiben szükséges, biztosítsa, hogy az ön által használt rendszer eléri vagy meghaladja a minimális hálózati, hardver és szoftver követelményeket.


## <a name="supported-microsoft-office-applications"></a>Támogatott Microsoft Office-alkalmazások
A következő Office-alkalmazások a Finance and Operations felhő alapú vagy helyszíni telepítései esetén használhatók.
-   A Microsoft Excel és Word bővítmények futtatásához telepítve kell lennie a Microsoft Office 2016 programnak Windows vagy Mac rendszeren. Verziójának követelményeivel kapcsolatos további részletekért lásd: [Office-integráció hibáinak elhárítása](/dynamics365/unified-operations/dev-itpro/office-integration/office-integration-troubleshooting).
-   Az Exportálás Excel-be vagy az Exportálás a Word programba funkcióval létrehozott dokumentumok megtekintéséhez telepíteni kell a Microsoft Office 2007 vagy újabb verzióját.

# <a name="system-requirements-specific-to-cloud-deployments"></a>Felhő alapú telepítésre vonatkozó rendszerkövetelmények
## <a name="network-requirements"></a>Hálózati követelmények
-   A Finance and Operations szoftvert olyan hálózatokhoz tervezték, amelyek várakozási ideje 250-300 milliszekund (ms) vagy kevesebb. Ez a latencia a böngészőklienstől a Microsoft Azure adatközpontig, amely tárolja a Finance and Operationst. Javasoljuk, hogy tesztelje a hálózati késleltetést a következő helyen: <http://www.azurespeed.com>.
-   A Finance and Operations sávszélességi követelményei az ön körülményeitől függenek. A legtöbb jellemző forgatókönyv másodpercenként több mint 50 kilobájt sávszélességet igényel (KBps). Azonban olyan nagyteljesítményű forgatókönyvek esetében, mint például a munkaterületek vagy a kiterjedt testreszabást igénylő forgatókönyvek, nagyobb sávszélességet ajánlunk.

Általánosságban elmondható, hogy a Finance and Operations az internetre optimalizált. A böngésző kliensből az Azure adatközpontba történő oda-vissza utak száma nagyon kicsi, és a teljes hasznos tartalom tömörítve van. 

> [!WARNING]
> Ne úgy számítsa ki a sávszélesség követelményeit az ügyfél helyéről, hogy megszorozza a felhasználók számát a minimális sávszélességi követelményekkel. Adott hely egyidejű használatát nagyon nehéz kiszámítani. A sávszélesség miatt aggódó ügyfelek számára a Finance and Operations előzetes verziójának használata ajánlott.

## <a name="net-framework-requirements"></a>A .NET keretrendszer követelményei
A Finance and Operations esetében a .NET-keretrendszer 4.6.2-es verziója szükséges az összes click-once alkalmazáshoz, például a dokumentumátirányító ügynökhöz. További tájékoztatás: [A .NET keretrendszer telepítése](https://msdn.microsoft.com/en-us/library/5a4x27ek(v=vs.110).aspx).

## <a name="supported-web-browsers"></a>Támogatott böngészők
A webes alkalmazás az alábbi böngészők bármelyikében működik, ha azok a megadott operációs rendszer alatt futnak:


-   Microsoft Edge (legfrissebb elérhető verziója) a Windows 10 rendszeren
-   Internet Explorer 11, Windows 10, Windows 8.1 vagy Windows 7 rendszereken
-   Google Chrome (legfrissebb elérhető verziója) Windows 10, Windows 8.1, Windows 8, Windows 7 rendszereken, vagy Google Nexus 10 táblagépen
-   Apple Safari (legfrissebb elérhető verziója) Mac OS X 10.10 (Yosemite), 10.11 (El Capitan), 10.12 (Sierra) rendszereken, vagy Apple iPad gépen

A böngésző legfrissebb változatáért látogasson el a szoftver gyártójának webhelyére. 

> [!NOTE]
> -   A Task Recorder által generált képek rögzítéséhez és Microsoft Word-dokumentumba való ágyazásához telepítenie kell egy előzetes verziójú Chrome-bővítményt. <!---For instructions about how to install the extension, see [Screenshot Extension setup](/dynamics365/unified-operations/dev-itpro/user-interface/task-recorder).-->
> -   A munkafolyamat-szerkesztő ClickOnce-alkalmazásként indul el. Csak a Microsoft Edge és az Internet Explorer (a Microsoft Windows egy támogatott verziójának használata esetén) támogatja a ClickOnce-alkalmazásokat. A Workflow Editor ClickOnce alkalmazáshoz 64 bit-kompatibilis operációs rendszer szükséges.
> -   A Report Designer for Financial reporting ClickOnce alkalmazásként indul el. 64 bit-kompatibilis operációs rendszert igényel. Chrome használata esetén, telepítenie kell a ClickOnce kiterjesztést a jelentéstervező kliens letöltéséhez. Ha a Chrome böngészőt inkognitómódban futtatja, győződjön meg arról, a ClickOnce kiterjesztés engedélyezve van-e az inkognitómódban.
> -   A PDF-fájlok előnézetének megtekintéséhez olyan böngészők használatát javasoljuk, mint a Microsoft Edge (a legújabb nyilvánosan elérhető verzió) Windows 10 rendszeren, illetve a Google Chrome (a legújabb nyilvánosan elérhető verzió) Windows 10, Windows 8.1, Windows 8 vagy Windows 7 rendszeren vagy Google Nexus 10 táblagépeken.


### <a name="supported-web-browsers-for-retail-cloud-pos"></a>A kiskereskedelmi felhő-POS pénztárgép által támogatott böngészők

A Retail Cloud POS az alábbi böngészők bármelyikében működik, ha azok a megadott operációs rendszer alatt futnak:

-   Microsoft Edge (legfrissebb elérhető verziója) a Windows 10 rendszeren
-   Internet Explorer 11, Windows 10, Windows 8.1 vagy Windows 7 rendszereken
-   Chrome (legutóbbi nyilvánosan elérhető verzió) Windows 10, Windows 8.1 vagy Windows 7 rendszeren

## <a name="retail-modern-pos-requirements"></a>Retail Modern POS követelményei
### <a name="supported-operating-systems"></a>Támogatott operációs rendszerek

-   A Retail Modern POS egy 32 bites alkalmazás, de egyaránt fut az x86 és az x64 architektúrán is.
-   A Retail Modern POS csak Windows 10 Pro, Enterprise, valamint Enterprise Long Term Servicing Branch (LTSB) kiadások esetén támogatott.

### <a name="minimum-system-requirements"></a>Minimális rendszerkövetelmények

-   A minimális támogatott felbontás az 1280×1024.
-   A Retail Modern POS rendszert futtató számítógépnek meg kell felelnie ezeknek a követelményeknek:
    -   Legalább kétmagos processzorral kell rendelkeznie, melynek legalább 2 GHz az órajele.
    -   Legalább 3 GB RAM-mal kell rendelkeznie.
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

-   A Connector for Microsoft Dynamics AX két külön telepítőprogramot tartalmaz, az **Async Server Connector service** és a **Real-time service for Dynamics AX 2012 R3** telepítőprogramokat.
-   Mindkét összetevő 32 bites alkalmazás, de egyaránt fut az x86 és az x64 architektúrán is.
-   Mindkét összetevőt támogatják a következő operációs rendszerek:
    -   Windows 7 Professional, Enterprise és Ultimate verzió
    -   Windows 8.1 Update 1 Professional, Enterprise és Embedded verzió
    -   Windows 10 Pro, Enterprise és Enterprise LTSB verzió
    -   Windows Server 2012 R2, Windows Server 2016

### <a name="minimum-system-requirements"></a>Minimális rendszerkövetelmények

-   2 GB memóriával, 4 GB RAM ajánlott
-   Maximális processzorsebesség 1,6 GHz magonként (legalább kétmagos)
-   Legalább 10 GB szabad lemezterület (a csatorna-adatbázis használatához sok helyre lehet szükség).

## <a name="requirements-for-development-on-local-vms"></a>A helyi virtuális gépek fejlesztési követelményei
A helyi virtuális gépek fejlesztési követelményeiről lásd: [helyszínen futó virtuális gép](../dev-tools/access-instances.md).

# <a name="system-requirements-for-on-premises-deployments"></a>Helyszíni telepítések rendszerkövetelményei

## <a name="network-requirements"></a>Hálózati követelmények
A Finance and Operations (helyszíni) olyan hálózatokon működik, melyek az Internet Protocol 4-es (IPv4) vagy 6-os (IPv6) verzióját használják. A rendszer tervezése közben vegye figyelembe a hálózati környezetet, és használja a következő irányelveket:

### <a name="network-response-time"></a>Hálózati válaszidő
Az alábbi táblázat felsorolja a minimális hálózati követelményeket a webböngésző és az Application Object Server (AOS), illetve az AOS és az adatbázis közötti kapcsolat esetén helyszíni rendszerekben.

| Érték     | Böngészőtől AOS-hez | AOS-től adatbázishoz                                            |
|-----------|--------------------|------------------------------------------------------------|
| Sávszélesség | 50 KBps felhasználónként   | 100 MBps                                                   |
| Késleltetés   | < 250-300 ms       | < 1 ms (csak helyi hálózat). Az AOS-nek és az adatbázisnak egy helyen kell lenniük. |

- A Finance and Operations (helyszíni) szoftvert olyan hálózatokhoz tervezték, amelyek várakozási ideje 250-300 milliszekund (ms) vagy kevesebb. Ez a késleltetés a böngészőklienstől az adatközpontig, amely tárolja a Finance and Operations-t.
- A Finance and Operations (helyszíni) sávszélességi követelményei az ön körülményeitől függenek. Tipikus esetekben több mint 50 kilobájt másodpercenként (KBps) a szükséges sávszélesség a böngésző és a Finance and Operations kiszolgáló között. Azonban olyan nagyteljesítményű esetekben, mint például a munkaterületek vagy a kiterjedt testreszabást igénylő esetek, nagyobb sávszélességet ajánlunk a tervezett használattól függően.
Nem támogatottak azok a telepítések, ahol az AOS és az SQL Server adatbázis különböző adatközpontban vannak. Az AOS-nek és az SQL Server adatbázisnak egy helyen kell lenniük. A Finance and Operations általában optimalizált a böngésző és a kiszolgáló közti oda-vissza utak csökkentésére. A böngésző kliensből az adatközpontba történő oda-vissza utak száma vagy nulla, vagy egyenlő a felhasználói beavatkozások számával, és a hasznos tartalom tömörítve van.

> [!WARNING]
> Ne úgy számítsa ki a sávszélesség követelményeit az ügyfél helyéről, hogy megszorozza a felhasználók számát a minimális sávszélességi követelményekkel. Adott hely egyidejű használatát nagyon nehéz kiszámítani. Javasolt egy, a valós életet tükröző szimuláció használata a Finance and Operations nem termelési közegében, ami a legpontosabb képet mutatja az ön esetében várható teljesítményről. 

### <a name="lan-environments"></a>Helyi hálózati (LAN) környezetek
Helyi hálózati (LAN) környezetekben a Microsoft Remote Desktop in Microsoft Windows Server-nek nem szükséges csatlakoznia a Finance and Operations-höz. Ez szükséges lehet azonban a VMs-en található karbantartási műveletekhez, amik a server-telepítéseket alkotják.

### <a name="wan-environments"></a>Nagy kiterjedésű hálózati (WAN) környezetek
Nagy kiterjedésű hálózati (WAN) környezetekben a Remote Desktop in Windows Server-nek nem szükséges csatlakoznia a Finance and Operations-höz.

### <a name="internet-connectivity-requirements"></a>Internetkapcsolati rendszerkövetelmények
A Finance and Operations (helyszíni) működtetéséhez nem szükséges internetkapcsolat a végfelhasználói munkaállomásokkal. Egyes szolgáltatások azonban nem lesznek elérhetőek internetkapcsolat nélkül.

| Böngésző-kliens | Az internetkapcsolat nélküli intranet esetek figyelembe vétele fontos szempont volt a helyszíni telepítési opció tervezésekor. Egyes felhő alapú szolgáltatások, mint például a súgó és feladat-útmutató könyvtárak az LCS-ben, nem lesznek elérhetőek. |
|----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Kiszolgáló         | Az AOS-nek vagy a Service Fabric szintnek képesnek kell lennie az LCS-szel való kommunikációra. A helyszíni, böngésző alapú kliens használatához nem szükséges internet-hozzáférés.                                                                                |
| Telemetria      | A kapcsolat hosszú megszakítása esetén telemetria-adatvesztés léphet fel. Az LCS-szel való kapcsolat megszakítása nem befolyásolja a helyszíni alkalmazás funkcióit.                                                |
| LCS            | Az LCS-szel való kapcsolat szükséges a telepítési, kód telepítési és karbantartási műveletek elvégzéséhez.                                                                                                                                 |
## <a name="telemetry-data-transfer-to-the-cloud"></a>Telemetria-adatok átvitele a felhőbe
A telemetria általában helyben tárolt, és a Microsoft Windows eseménynapló használatával elérhető. A telemetria-események egy kis része átkerül a felhőn található Microsoft telemetria-prognózisra diagnosztikai célokból. A vevői és az azonosítható végfelhasználói adatok nem tartoznak a Microsoftnak küldött telemetriához. Az ÉM nevek a Microsofthoz kerülnek, ezzel elősegítve a környezet-kezelést és a diagnosztikát az LCS-portáltól.

## <a name="domain-requirements"></a>Tartományi rendszerkövetelmények
Vegye figyelembe az alábbi tartományi követelményeket a Finance and Operations (helyszíni) telepítésekor:

- A Finance and Operations (helyszíni) komponenseit futtató virtuális gépeknek Active Directory tartományhoz kell tartozniuk. Az Active Directory tartományi szolgáltatásokat (ADDS) natív módban kell konfigurálni.
- A Finance and Operations (helyszíni) komponenseit futtató virtuális gépeknek biztosítani kell az egymáshoz való hozzáférést,amit az Active Directory tartományi szolgáltatásokban lehet konfigurálni. 
- A tartományvezérlőt Microsoft Windows Server 2016-on kell futtatni.

## <a name="hardware-requirements"></a>Hardverkövetelmények
Ez a szakasz leírja, hogy milyen hardver szükséges a Finance and Operations (helyszíni) futtatásához.
A tényleges hardverkövetelmények változhatnak a rendszerkonfigurációtól, az adatösszetételtől,illetve a használni kívánt alkalmazásoktól és szolgáltatásoktól függően. Néhány tényező, ami befolyásolhatja döntését a Finance and Operations (helyszíni) futtatásához szükséges hardver kiválasztásában:

- Az óránkénti tranzakciók száma.
- Az egyidejű felhasználók száma.

## <a name="minimum-infrastructure-requirements"></a>Minimális infrastruktúra-követelmények
A Finance and Operations (helyszíni) a Microsoft Azure Service Fabric-et használja az AOS, köteg, adatkezelő,felügyeleti jelentéskészítő és környezeti szervező szolgáltatások ellátására. A Microsoft SQL Server Reporting Services (SSRS) nem található a Service Fabric fürtben.
Az SQL Servert egy magas rendelkezésre állású HADRON beállításra kell állítani, amelynek legalább két csomópontja van termelési használatra.
Az alábbi ábra megmutatja a csomópontok ajánlott minimális számát a Service Fabric fürtben.

[![csomópontok ajánlott minimális száma a service fabric fürtben](./media/system-reqs-on-premises-01.png)](./media/system-reqs-on-premises-01.png) 

## <a name="processor-and-ram-requirements"></a>Processzor és RAM követelmények
Az alábbi táblázat megmutatja a szükséges processzor-számot és véletlen hozzáférésű memória (RAM) mennyiséget azon szerepkörökhöz, amik szükségesek a telepítési opció futtatásához. További információkért olvassa el a minimális követelmény-javaslatot önálló Service Fabric fürthöz, [Saját Service Fabric fürt tervezése és előkészítése](/azure/service-fabric/service-fabric-cluster-standalone-deployment-preparation).

> [!NOTE]
> Ha egyéb Microsoft-program van telepítve ugyanazon a számítógépen, akkor a rendszernek ezen szoftver hardverkövetelményeinek is meg kell felelnie. Ajánlott az AOS-szel egy számítógépen lévő egyéb szerver alkalmazásokat 1 gigabájt (GB) memóriára korlátozni.

**A topológia típusa és a szerepkör szerinti méretezés**

| Topológia   | Szerep (csomópont típusa)              | Processzormagok ajánlott száma | Javasolt memóriamennyiség (GB) |
|------------|-------------------------------|-----------------------------|-------------------------|
| Termelés | AOS, adatkezelés, köteg   | 8                           | 24                      |
|            | Felügyeleti jelentéskészítő           | 4                           | 16                      |
|            | SQL Server Reporting Services szolgáltatás | 4                           | 16                      |
|            | Szervező                  | 4                           | 16                      |
| Védőfal    | AOS, adatkezelés, köteg   | 4                           | 24                      |
|            | Felügyeleti jelentéskészítő           | 4                           | 16                      |
|            | SQL Server Reporting Services szolgáltatás | 4                           | 16                      |
|            | Szervező                  | 4                           | 16                      |

**Minimális méret becslések a termelés és védőfal telepítéseknél**\*

| Topológia                                  | Szerep                          | Példányok száma |
|-------------------------------------------|-------------------------------|---------------------|
| Termelés                                | AOS (adatkezelés, köteg)  | 3                   |
|                                           | Felügyeleti jelentéskészítő           | 2                   |
|                                           | SQL Server Reporting Services szolgáltatás | 1                   |
|                                           | Szervező\*\*                | 3                   |
| Védőfal                                   | AOS, adatkezelés, köteg   | 2                   |
|                                           | Felügyeleti jelentéskészítő           | 1                   |
|                                           | SQL Server Reporting Services szolgáltatás | 1                   |
|                                           | Szervező                  | 3                   |
| *Összesítő termelési és Sandbox topológiák* |                               | 16                  |

\*Ezeket a számokat az előnézeti ügyfeleink ellenőrzik, és még módosulhatnak az adott visszajelzés alapján.

\*\*A szervező a kijelölt elsődleges csomópont-típus, és ezzel futnak a Service Fabric szolgáltatások is.

**Háttér SQL Server és Active Directory kezdeti becslések**

[![Háttér SQL server és Active Directory kezdeti becslések](./media/system-reqs-on-premises-02.PNG)](./media/system-reqs-on-premises-02.PNG) 

\*Az SQL Server méretek nagy mértékben függenek a terheléstől. További információkért lásd a [Hardver méretezés helyszíni környezetben](#Hardware-sizing-for-on-premises-environments) szakaszt.

## <a name="storage"></a>Tárolás

- **AOS** – A Finance and Operations (helyszíni) a Server Message Block (SMB) 3.0-t használja a strukturálatlan adatok tárolására. További információkért lásd: [Storage Spaces Direct a Windows Server 2016-ban](/windows-server/storage/storage-spaces/storage-spaces-direct-overview).
- **SQL** – megvalósítható lehetőségek:
    - Egy magas rendelkezésre állású tartós álapotú meghajtó (SSD) beállítása.
    - Egy tároló hálózat (SAN) OLTP teljesítményekre optimalizálva.
    - Nagy teljesítményű közvetlen csatolt tárhely (DAS) 
- **SQL és adatkezelés IOPS** – Az adatkezelés és az SQL Server tárhelyének el kell érnie a másodpercenként 2000 bemeneti/kimeneti műveletet (IOPS). A termelési IOPS számos tényezőtől függ. További információkért lásd a “Hardver méretezés helyszíni környezetben” szakaszt. 
- **Virtuális gép IOPS** – Minden virtuális gépnek el kell érnie 100 írási IOPS-t.

## <a name="virtual-host-requirements"></a>Virtuális állomás követelmények
A virtuális állomás Finance and Operations-höz (helyszíni) való felállításakor kövesse az alábbi irányelveket: [Saját Service Fabric fürt tervezése és előkészítése](/azure/service-fabric/service-fabric-cluster-standalone-deployment-preparation) és [Service Fabric fürt leírása](/azure/service-fabric/service-fabric-cluster-resource-manager-cluster-description). Minden virtuális állomásnak rendelkeznie kell elég processzormaggal a méretezett infrastruktúra számára. Több speciális konfiguráció is lehetséges, ahol az SQL Server fizikai hardveren található, de minden más virtualizálva van. Ha az SQL Server virtualizálva van, a lemez alrendszer gyors SAN vagy annak megfelelő kell, hogy legyen. Minden esetben győződjön meg arról, hogy a virtuális állomás alapbeállítása nagy mértékben érhető el, és redundáns. Abban az esetben, ha virtualizálást használ,nem készíthet ÉM pillanatképeket.

## <a name="software-requirements-for-all-server-computers"></a>Az összes kiszolgáló számítógép szoftver követelményei
A következő szoftvereknek jelen kell lennie a számítógépen a Finance and Operations (helyszíni) komponenseinek telepítése előtt:

- Microsoft .NET-keretrendszer 4.5.1 vagy magasabb
- Service Fabric További információkért lásd: [Saját Service Fabric fürt tervezése és előkészítése](/azure/service-fabric/service-fabric-cluster-standalone-deployment-preparation).

## <a name="supported-server-operating-systems"></a>Támogatott kiszolgáló operációs rendszerek:
Az alábbi táblázat felsorolja a Finance and Operations komponensek által támogatott kiszolgálói operációs rendszereket.

| Operációs rendszer                                     | Megjegyzések                                                                                  |
|------------------------------------------------------|----------------------------------------------------------------------------------------|
| Microsoft Windows Server 2016 Adatközpont vagy Standard | Ezek az AOS-t tartalmazó Service Fabric fürt és az adatbázis követelményei: |

## <a name="software-requirements-for-database-servers"></a>Az adatbázis kiszolgálók szoftver követelményei

- Az SQL Server 2016-nak csak a 64 bites verziói támogatottak.
- Éles környezetben ajánlott telepíteni a használt SQL Server verziójának legújabb összegző frissítését (CU).
- A Finance and Operations (helyszíni) azokat a Unicode rendezési sorrendeket támogatja, melyek nem tesznek különbséget a kis- és a nagybetűk között, továbbá figyelembe veszik az ékezeteket és a kana jeleket, a szélességet viszont nem. A rendezési sorrendnek meg kell egyeznie az AOS-példányt futtató számítógép Windows területi beállításaival. Új telepítés beállításakor Windows rendezési sorrend választása ajánlott egy SQL Server rendezési sorrend helyett. További információkért SQL szerver adatbázis rendezési sorrendjének kiválasztásáról lásd a [SQL Server dokumentációja](/sql/sql-server/sql-server-technical-documentation).
Az alábbi táblázat felsorolja a Finance and Operations adatbázisok által támogatott SQL Server verziókat.. További információkért lásd a minimális hardverkövetelményeit az [SQL Server-nek](https://www.microsoft.com/en-us/sql-server/sql-server-2016).

| Követelmény                                                      | Megjegyzések                                                                                                                     |
|------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------|
| Microsoft SQL Server 2016 Standard Edition vagy Enterprise Edition | Az SQL Server 2016 hardverkövetelményeiért lásd [Az SQL Server 2016 telepítésének hardver- és szoftver követelményei](/sql/sql-server/install/hardware-and-software-requirements-for-installing-sql-server). |

## <a name="software-requirements-for-client-computers"></a>A kliens számítógépek szoftver követelményei
A Finance and Operations webalkalmazás minden olyan eszközön futtatható, amely rendelkezik HTML5.0-kompatibilis böngészővel. A Microsoft által megerősített specifikus eszköz/böngésző kombinációk a következők:

- Microsoft Edge (legfrissebb elérhető verziója) a Windows 10 rendszeren
- Internet Explorer 11, Windows 10, Windows 8.1 vagy Windows 7 rendszereken
- Google Chrome (legfrissebb elérhető verziója) Windows 10, Windows 8.1, Windows 8, Windows 7 rendszereken, vagy Google Nexus 10 táblagépen
- Apple Safari (legfrissebb elérhető verziója) Mac OS X 10.10 (Yosemite), 10.11 (El Capitan), 10.12 (Sierra) rendszereken, vagy Apple iPad gépen

## <a name="software-requirements-for-active-directory-federation-services"></a>Az Active Directory Federation Services szoftver követelményei 
Active Directory Federation Services (AD FS) a Windows Server 2016-on

A tartományvezérlő Windows Server 2012 R2 vagy újabb kell, hogy legyen, illetve a tartomány működési szintjének el kell érnie a 2012 R2-t

További információ a tartomány működési szintekről: 
- [Active Directory működési szintjeinek fogalma](https://technet.microsoft.com/en-us/library/cc787290(v=ws.10).aspx)
- [Az Active Directory Domain Services működési szintjeinek ismertetése](https://technet.microsoft.com/en-us/library/understanding-active-directory-functional-levels(v=ws.10).aspx)
 
## <a name="hardware-and-software-requirements-for-retail-components"></a>A kiskereskedelmi összetevők hardver- és szoftver követelményei
A Finance and Operations (helyszíni) jelenleg nem tartalmazza a kiskereskedői összetevőket.

<a name="see-also"></a>Lásd még
--------

[Szerezze be a Dynamics 365 for Finance and Operations Enterprise Edition bétaverzióját](/dynamics365/unified-operations/dev-itpro/dev-tools/get-evaluation-copy)

