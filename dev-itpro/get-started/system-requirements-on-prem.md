---
title: "Helyszíni telepítések rendszerkövetelményei"
description: "Ez a témakör a Microsoft Dynamics 365 for Finance and Operations Enterprise edition aktuális verziójára vonatkozó rendszerkövetelményeket sorolja fel helyszíni telepítés esetén."
author: kfend
manager: AnnBe
ms.date: 08/02/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core
ms.custom: 55651
ms.assetid: 
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2016-08-30
ms.dyn365.ops.version: Platform update 8
ms.translationtype: HT
ms.sourcegitcommit: 5230911e1febc66b294f1331846373a472789adf
ms.openlocfilehash: 721c5851cd399398a8dcec5ae110b97a4f17ae0a
ms.contentlocale: hu-hu
ms.lasthandoff: 08/04/2017

---

# <a name="system-requirements-for-on-premises-deployments"></a>Helyszíni telepítések rendszerkövetelményei

[!include[banner](../includes/banner.md)]

Ez a témakör a Microsoft Dynamics 365 for Finance and Operations Enterprise edition aktuális verziójára vonatkozó rendszerkövetelményeket sorolja fel helyszíni telepítés esetén. Mielőtt telepíti a Finance and Operations szoftvert, amennyiben ez a lépés szükséges, biztosítsa, hogy az ön által használt rendszer eléri vagy meghaladja a minimális hálózati, hardver és szoftver követelményeket.

## <a name="network-requirements"></a>Hálózati követelmények
A Microsoft Dynamics 365 for Finance and Operations Enterprise kiadása (helyszíni) olyan hálózatokon működik, melyek az Internet Protocol 4-es (IPv4) vagy 6-os (IPv6) verzióját használják. A rendszer tervezése közben vegye figyelembe a hálózati környezetet, és használja a következő irányelveket:

### <a name="network-response-time"></a>Hálózati válaszidő
Az alábbi táblázat felsorolja a minimális hálózati követelményeket a webböngésző és az Application Object Server (AOS), illetve az AOS és az adatbázis közötti kapcsolat esetén helyszíni rendszerekben.

| Érték     | Böngészőtől AOS-hez                      | AOS-től adatbázishoz |
|-----------|-----------------------------------------|------------------------------------------------------------------------------------------|
| Sávszélesség | 50 kilobájt másodpercenként (KBps) felhasználónként | 100 megabájt másodpercenként (MBps) |
| Késleltetés   | Legfeljebb 250–300 ezredmásodperc (ms)     | Kisebb mint 1 ms (csak helyi hálózat [LAN]). Az AOS-nek és az adatbázisnak egy helyen kell lenniük. |

- A Finance and Operations (helyszíni) szoftvert olyan hálózatokhoz tervezték, amelyek várakozási ideje 250-300 milliszekund (ms) vagy kevesebb. Ez a késleltetés a böngészőklienstől az adatközpontig, amely tárolja a Finance and Operations rendszert.
- A Finance and Operations (helyszíni) sávszélességi követelményei az ön körülményeitől függenek. Tipikus esetekben több mint 50 kilobájt másodpercenként (KBps) a szükséges sávszélesség a böngésző és a Finance and Operations kiszolgáló között. Azonban olyan nagyteljesítményű forgatókönyvek esetében, mint például a munkaterületek vagy a kiterjedt testreszabást igénylő forgatókönyvek, nagyobb sávszélességet ajánlunk. A sávszélesség adott összeg a használattól függ.

Nem támogatottak azok a telepítések, ahol az AOS és a Microsoft SQL Server adatbázis különböző adatközpontban vannak. Az AOS-nek és az SQL Server adatbázisnak egy helyen kell lenniük. 

A Finance and Operations általában optimalizált a böngésző és a kiszolgáló közti oda-vissza utak csökkentésére. A böngésző kliensből az adatközpontba történő oda-vissza utak száma vagy nulla, vagy egyenlő a felhasználói beavatkozások számával, és a hasznos tartalom tömörítve van.

> [!WARNING]
> Ne úgy számítsa ki a sávszélesség követelményeit az ügyfél helyéről, hogy megszorozza a felhasználók számát a minimális sávszélességi követelményekkel. Adott hely egyidejű használatát nagyon nehéz kiszámítani. Javasolt egy, a valós életet tükröző szimuláció használata a Finance and Operations nem termelési közegében, ami a legpontosabb képet mutatja az ön esetében várható teljesítményről. 

### <a name="lan-environments"></a>Helyi hálózati (LAN) környezetek
Helyi hálózati (LAN) környezetekben a Microsoft Remote Desktop in Microsoft Windows Server-nek nem szükséges csatlakoznia a Finance and Operations-höz. Távoli asztal munkamenet lehet azonban szükséges a virtuális gépeken (VM) található karbantartási műveletekhez, amelyek a kiszolgálótelepítéseket alkotják.

### <a name="wan-environments"></a>Nagy kiterjedésű hálózati (WAN) környezetek
Nagy kiterjedésű hálózati (WAN) környezetekben a Remote Desktop in Windows Server-nek nem szükséges csatlakoznia a Finance and Operations rendszerhez.

### <a name="internet-connectivity-requirements"></a>Internetkapcsolati rendszerkövetelmények
A Finance and Operations (helyszíni) működtetéséhez nem szükséges internetkapcsolat a végfelhasználói munkaállomásokkal. Egyes szolgáltatások azonban nem lesznek elérhetőek internetkapcsolat nélkül.

|                    |   |
|--------------------|---|
| **Böngésző-kliens** | Az internetkapcsolat nélküli intranet esetek figyelembe vétele fontos szempont volt a helyszíni telepítési opció tervezésekor. Egyes felhő alapú szolgáltatások, mint például a súgó és feladat-útmutató könyvtárak a Microsoft Dynamics Lifecycle Services (LCS) rendszerben, nem lesznek elérhetőek. |
| **Kiszolgáló**         | Az AOS-nek vagy a Microsoft Azure Service Fabric szintnek képesnek kell lennie az LCS rendszerrel való kommunikációra. A helyszíni, böngésző alapú kliens használatához nem szükséges internet-hozzáférés. |
| **Telemetria**      | A kapcsolat hosszú megszakítása esetén telemetria-adatvesztés léphet fel. Az LCS rendszerrel való kapcsolat megszakítása nem befolyásolja a helyszíni alkalmazás funkcióit. |
| **LCS**            | Az LCS-szel való kapcsolat szükséges a telepítési, kód telepítési és karbantartási műveletek elvégzéséhez. |

## <a name="telemetry-data-transfer-to-the-cloud"></a>Telemetria-adatok átvitele a felhőbe
A telemetriaadatok általában helyben vannak tárolva, és a Microsoft Windows eseménynapló használatával elérhetők. A telemetria-események egy kis része átkerül a felhőn található Microsoft telemetria-prognózisra diagnosztikai célokból. A vevői és az azonosítható felhasználói adatok nem tartoznak a Microsoftnak küldött telemetria-adatokhoz. Az ÉM nevek a Microsofthoz kerülnek, ezzel elősegítve a környezet-kezelést és a diagnosztikát az LCS-portáltól.

## <a name="domain-requirements"></a>Tartományi rendszerkövetelmények
Vegye figyelembe az alábbi tartományi követelményeket a Finance and Operations (helyszíni) telepítésekor:

- A Finance and Operations (helyszíni) komponenseit futtató virtuális gépeknek (VM) Active Directory tartományhoz kell tartozniuk. Az Active Directory tartományi szolgáltatásokat (ADDS) natív módban kell konfigurálni.
- A Finance and Operations (helyszíni) komponenseit futtató virtuális gépeknek biztosítani kell az egymáshoz való hozzáférést. Ezt a hozzáférést az Active Directory tartományi szolgáltatásokban lehet konfigurálni. 
- A tartományvezérlő Microsoft Windows Server 2012 R2 vagy újabb kell, hogy legyen, illetve a tartomány működési szintjének el kell érnie a 2012 R2 vagy magasabb szintet..

## <a name="hardware-requirements"></a>Hardverkövetelmények
Ez a szakasz leírja, hogy milyen hardver szükséges a Finance and Operations (helyszíni) futtatásához.

A tényleges hardverkövetelmények változhatnak a rendszerkonfigurációtól, az adatösszetételtől,illetve a használni kívánt alkalmazásoktól és szolgáltatásoktól függően. Néhány tényező, ami befolyásolhatja döntését a Finance and Operations (helyszíni) futtatásához szükséges hardver kiválasztásában:

- Az óránkénti tranzakciók száma
- Az egyidejű felhasználók száma

## <a name="minimum-infrastructure-requirements"></a>Minimális infrastruktúra-követelmények
A Finance and Operations (helyszíni) a Service Fabric rendszert használja az AOS, köteg, adatkezelő,felügyeleti jelentéskészítő és környezeti szervező szolgáltatások ellátására. A Microsoft SQL Server Reporting Services (SSRS) nem található a Service Fabric fürtben.

Az SQL Servert egy magas rendelkezésre állású HADRON beállításra kell állítani, amelynek legalább két csomópontja van termelési használatra.

Az alábbi ábra megmutatja a csomópontok ajánlott minimális számát a Service Fabric fürtben.

[![Csomópontok ajánlott minimális száma a Service Fabric fürtben](./media/system-reqs-on-premises-01.png)](./media/system-reqs-on-premises-01.png) 

## <a name="processor-and-ram-requirements"></a>Processzor és RAM követelmények
Az alábbi táblázatok megmutatják a szükséges processzor-számot és véletlen hozzáférésű memória (RAM) mennyiséget azon szerepkörökhöz, amelyek szükségesek a telepítési opció futtatásához. További információkért olvassa el a minimális követelmény-javaslatot önálló Service Fabric fürthöz, [Saját Service Fabric fürt tervezése és előkészítése](/azure/service-fabric/service-fabric-cluster-standalone-deployment-preparation).

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

**Minimális méret becslések a termelés és védőfal telepítéseknél\***

| Topológia                                        | Szerep                          | Példányok száma |
|-------------------------------------------------|-------------------------------|---------------------|
| Termelés                                      | AOS (adatkezelés, köteg)  | 3                   |
|                                                 | Felügyeleti jelentéskészítő           | 2                   |
|                                                 | SQL Server Reporting Services szolgáltatás | 1                   |
|                                                 | Szervező\*\*              | 3                   |
| Védőfal                                         | AOS, adatkezelés, köteg   | 2                   |
|                                                 | Felügyeleti jelentéskészítő           | 1                   |
|                                                 | SQL Server Reporting Services szolgáltatás | 1                   |
|                                                 | Szervező                  | 3                   |
| *Összesítő termelési és Sandbox topológiák* |                               | *16*                |

\* A táblában szereplő számokat az előnézeti ügyfelek hitelesítik, és ezek az ügyfelek visszajelzései alapján módosíthatók.

\*\* A szervező a kijelölt elsődleges csomópont-típus, és ezzel futnak a Service Fabric szolgáltatások is.

**Háttér SQL server és Active Directory kezdeti becslések**

<table>
<thead>
<tr>
<th></th>
<th>Szerep</th>
<th>Virtuális gépek/példányok</th>
<th>Magok</th>
<th>Összes mag</th>
<th>Memória példányonként (GB)</th>
<th>Összes memória (GB)</th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan="3"><strong>Megosztott infrastruktúra</strong></td>
<td>SQL kiszolgáló*</td>
<td>2</td>
<td>8</td>
<td>16</td>
<td>32</td>
<td>64</td>
</tr>
<tr>
<td>Fájlkiszolgáló/Tároló hálózat/Magas rendelkezésre állású tároló</td>
<td colspan="5"><p>A háttértárolónak tartós állapotú meghajtókon (SSD) és futásidejű tárolási hálózaton (SAN) kell alapulnia.</p>
<p>A méret és a másodpercenkénti bemeneti/kimeneti műveletek (IOPS) teljesítménye a terhelés méretén alapul.</p></td>
</tr>
<tr>
<td>Active Directory</td>
<td>3</td>
<td>4</td>
<td>12</td>
<td>16</td>
<td>48.</td>
</tr>
<tr>
<td><em>Megosztott infrastruktúra összefoglalása</em></td>
<td></td>
<td><em>5</em></td>
<td></td>
<td><em>28</em></td>
<td></td>
<td><em>112</em></td>
</tr>
</tbody>
</table>

\* Az SQL Server méretek nagy mértékben függenek a terheléstől. További információkért lásd: [Hardver méretezés helyszíni környezetben](hardware-sizing-on-premises-environments.md).

## <a name="storage"></a>Tárolás

- **AOS** – A Finance and Operations (helyszíni) a Server Message Block (SMB) 3.0-t használja a strukturálatlan adatok tárolására. További információkért lásd: [Storage Spaces Direct a Windows Server 2016-ban](/windows-server/storage/storage-spaces/storage-spaces-direct-overview).
- **SQL** – Az alábbi lehetőségek közül választhat:

    - Magas rendelkezésre állású SSD
    - Online tranzakció-feldolgozási (OLTP) teljesítményekre optimalizált SAN
    - Nagy teljesítményű közvetlen csatolt tárhely (DAS) 

- **SQL Server és adatkezelés IOPS** – Az adatkezelés és az SQL Server tárhelyének el kell érnie a másodpercenként 2000 műveletet (IOPS). A termelési IOPS számos tényezőtől függ. További információkért lásd: [Hardver méretezés helyszíni környezetben](hardware-sizing-on-premises-environments.md).
- **Virtuális gép IOPS** – Minden virtuális gépnek legalább 100 írási IOPS-szel kell rendelkeznie.

## <a name="virtual-host-requirements"></a>Virtuális állomás követelmények
A virtuális állomás Finance and Operations rendszerhez (helyszíni) való felállításakor kövesse az alábbi irányelveket: [Saját Service Fabric fürt tervezése és előkészítése](/azure/service-fabric/service-fabric-cluster-standalone-deployment-preparation) és [Service Fabric fürt leírása](/azure/service-fabric/service-fabric-cluster-resource-manager-cluster-description). Minden virtuális állomásnak rendelkeznie kell elég processzormaggal a méretezett infrastruktúra számára. Több speciális konfiguráció is lehetséges, ahol az SQL Server fizikai hardveren található, de minden más virtualizálva van. Ha az SQL Server virtualizálva van, a lemez alrendszer gyors SAN vagy annak megfelelő kell, hogy legyen. Minden esetben győződjön meg arról, hogy a virtuális állomás alapbeállítása nagy mértékben érhető el, és redundáns. Abban az esetben, ha virtualizálást használ,nem készíthet ÉM pillanatképeket.

## <a name="software-requirements-for-all-server-computers"></a>Az összes kiszolgáló számítógép szoftver követelményei
A következő szoftvereknek jelen kell lennie a számítógépen a Finance and Operations (helyszíni) komponenseinek telepítése előtt:

- A Microsoft .NET keretrendszer 4.5.1-es vagy későbbi verziója
- Szolgáltatási anyag

További információkért lásd: [Saját Service Fabric fürt tervezése és előkészítése](/azure/service-fabric/service-fabric-cluster-standalone-deployment-preparation).

## <a name="supported-server-operating-systems"></a>Támogatott kiszolgáló operációs rendszerek:
Az alábbi táblázat felsorolja a Finance and Operations komponensek által támogatott kiszolgálói operációs rendszereket.

| Operációs rendszer                                     | Megjegyzések |
|------------------------------------------------------|-------|
| Microsoft Windows Server 2016 Adatközpont vagy Standard | Ezek az AOS-t tartalmazó Service Fabric fürt és az adatbázis követelményei: |

## <a name="software-requirements-for-database-servers"></a>Az adatbázis kiszolgálók szoftver követelményei

- Az SQL Server 2016-nak csak a 64 bites verziói támogatottak.
- Éles környezetben ajánlott telepíteni a használt SQL Server verziójának legújabb összegző frissítését (CU).
- A Finance and Operations (helyszíni) azokat a Unicode rendezési sorrendeket támogatja, melyek nem tesznek különbséget a kis- és a nagybetűk között, továbbá figyelembe veszik az ékezeteket és a kana jeleket, a szélességet viszont nem. A rendezési sorrendnek meg kell egyeznie az AOS-példányt futtató számítógép Windows területi beállításaival. Új telepítés beállításakor Windows rendezési sorrend választása ajánlott egy SQL Server rendezési sorrend helyett. További információkért SQL szerver adatbázis rendezési sorrendjének kiválasztásáról lásd a [SQL Server dokumentációja](/sql/sql-server/sql-server-technical-documentation).

Az alábbi táblázat felsorolja a Finance and Operations adatbázisok által támogatott SQL Server verziókat.. További információkért lásd a minimális hardverkövetelményeit az [SQL Server-nek](https://www.microsoft.com/en-us/sql-server/sql-server-2016).

| Követelmény                                                      | Megjegyzések |
|------------------------------------------------------------------|-------|
| Microsoft SQL Server 2016 Standard Edition vagy Enterprise Edition | Az SQL Server 2016 hardverkövetelményeiért lásd [Az SQL Server 2016 telepítésének hardver- és szoftver követelményei](/sql/sql-server/install/hardware-and-software-requirements-for-installing-sql-server). |

## <a name="software-requirements-for-client-computers"></a>A kliens számítógépek szoftver követelményei
A Finance and Operations webalkalmazás minden olyan eszközön futtatható, amely rendelkezik HTML 5.0-kompatibilis böngészővel. A Microsoft által megerősített specifikus eszköz-/böngészőkombinációk a következők:

- Microsoft Edge (legfrissebb elérhető verziója) a Windows 10 rendszeren
- Internet Explorer 11, Windows 10, Windows 8.1 vagy Windows 7 rendszereken
- Google Chrome (legfrissebb elérhető verziója) Windows 10, Windows 8.1, Windows 8, Windows 7 rendszereken, vagy Google Nexus 10 táblagépen
- Apple Safari (legfrissebb elérhető verziója) Mac OS X 10.10 (Yosemite), 10.11 (El Capitan), 10.12 (Sierra) rendszereken, vagy Apple iPad gépen

## <a name="software-requirements-for-active-directory-federation-services"></a>Az Active Directory Federation Services szoftver követelményei 
Windows Server 2016 Active Directory Federation Services (AD FS) szükséges.

A tartományvezérlő Windows Server 2012 R2 vagy újabb kell, hogy legyen, illetve a tartomány működési szintjének el kell érnie a 2012 R2 vagy magasabb szintet.. További információ a tartomány működési szintekről a következő oldalakon:

- [Active Directory működési szintjeinek fogalma](https://technet.microsoft.com/en-us/library/cc787290(v=ws.10).aspx)
- [Az Active Directory Domain Services működési szintjeinek ismertetése](https://technet.microsoft.com/en-us/library/understanding-active-directory-functional-levels(v=ws.10).aspx)

## <a name="supported-microsoft-office-applications"></a>Támogatott Microsoft Office-alkalmazások
A következő Microsoft Office-alkalmazások a Finance and Operations felhő alapú vagy helyszíni telepítései esetén használhatók:

-   A Microsoft Excel és Microsoft Word-bővítmények futtatásához telepítve kell lennie a Microsoft Office 2016 programnak Windows vagy Mac rendszeren. Verziójának követelményeivel kapcsolatos további részletekért lásd: [Office-integráció hibáinak elhárítása](/dynamics365/unified-operations/dev-itpro/office-integration/office-integration-troubleshooting).
-   Az Exportálás Excel-be vagy az Exportálás a Word programba funkcióval létrehozott dokumentumok megtekintéséhez telepíteni kell a Microsoft Office 2007 vagy újabb verzióját.
 
## <a name="hardware-and-software-requirements-for-retail-components"></a>A kiskereskedelmi összetevők hardver- és szoftver követelményei
Jelenleg a Finance and Operations (helyszíni) jelenleg nem tartalmazza a Kiskereskedelem összetevőket.

