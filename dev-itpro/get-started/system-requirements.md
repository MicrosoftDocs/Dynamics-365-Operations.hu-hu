---
title: "Rendszerkövetelmények"
description: "Ez a témakör a Microsoft Dynamics 365 for Operations aktuális verziójára vonatkozó rendszerkövetelményeket sorolja fel."
author: sericks007
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, Developer, IT Pro
ms.search.scope: Core
ms.custom: 55651
ms.assetid: e564d51d-42d3-47c5-b388-93b8219c692a
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-08-30
ms.dyn365.ops.version: Platform update 2
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: 86053196a3aad6b7b5d7830860e1af347dd969d8
ms.contentlocale: hu-hu
ms.lasthandoff: 04/25/2017


---

# <a name="system-requirements"></a>Rendszerkövetelmények

[!include[banner](../includes/banner.md)]


Ez a témakör a Microsoft Dynamics 365 for Operations aktuális verziójára vonatkozó rendszerkövetelményeket sorolja fel.

<a name="supported-web-browsers"></a>Támogatott böngészők
----------------------

A Microsoft Dynamics 365 for Operations webes alkalmazása az alábbi böngészők bármelyikében működik, ha azok a megadott operációs rendszer alatt futnak:

-   Microsoft Edge (legfrissebb elérhető verziója) a Windows 10 rendszeren
-   Internet Explorer 11, Windows 10, Windows 8.1 vagy Windows 7 rendszereken
-   Google Chrome (legfrissebb elérhető verziója) Windows 10, Windows 8.1, Windows 8, Windows 7 rendszereken, vagy Google Nexus 10 táblagépen
-   Apple Safari (legfrissebb elérhető verziója) Mac OS X 10.10 (Yosemite), 10.11 (El Capitan), 10.12 (Sierra) rendszereken, vagy Apple iPad gépen

A böngésző legfrissebb változatáért látogasson el a szoftver gyártójának webhelyére. **Megjegyzések:**

-   A Task Recorder által generált képek rögzítéséhez és Microsoft Word-dokumentumba való ágyazásához telepítenie kell egy Chrome-bővítményt. <!---For instructions about how to install the extension, see [Screenshot Extension setup](/dynamics365/operations/dev-itpro/user-interface/task-recorder).-->
-   A munkafolyamat-szerkesztő ClickOnce-alkalmazásként indul el. Csak a Microsoft Edge és az Internet Explorer (a Microsoft Windows egy támogatott verziójának használata esetén) támogatja a ClickOnce-alkalmazásokat. A Workflow Editor ClickOnce alkalmazáshoz 64 bit-kompatibilis operációs rendszer szükséges.
-   A Report Designer for Financial reporting ClickOnce alkalmazásként indul el. 64 bit-kompatibilis operációs rendszert igényel. Chrome használata esetén, telepítenie kell a ClickOnce kiterjesztést a jelentéstervező kliens letöltéséhez. Ha a Chrome böngészőt inkognitómódban futtatja, győződjön meg arról, a ClickOnce kiterjesztés engedélyezve van-e az inkognitómódban.
-   A PDF-fájlok előnézetének megtekintéséhez olyan modern böngészők használatát javasoljuk, mint a Microsoft Edge (a legújabb nyilvánosan elérhető verzió) Windows 10 rendszeren, illetve a Google Chrome (a legújabb nyilvánosan elérhető verzió) Windows 10, Windows 8.1, Windows 8 vagy Windows 7 rendszeren vagy Google Nexus 10 táblagépeken.


### <a name="supported-web-browsers-for-retail-cloud-pos"></a>A kiskereskedelmi felhő-POS pénztárgép által támogatott böngészők

A Microsoft Dynamics 365 for Operations kiskereskedelmi felhő-POS pénztárgépe az alábbi böngészők bármelyikében működik, ha azok a megadott operációs rendszer alatt futnak:

-   Microsoft Edge (legfrissebb elérhető verziója) a Windows 10 rendszeren
-   Internet Explorer 11, Windows 10, Windows 8.1 vagy Windows 7 rendszereken
-   Chrome (legutóbbi nyilvánosan elérhető verzió) Windows 10, Windows 8.1 vagy Windows 7 rendszeren

## <a name="network-requirements"></a>Hálózati követelmények
-   A Dynamics 365 operációs rendszert olyan hálózatokhoz tervezték, amelyek várakozási ideje kevesebb, mint 150 milliszekund (ms). Ez a latencia a böngészőklienstől a Microsoft Azure adatközpontig, amely tárolja a Dynamics 365 for Operationst. Javasoljuk, hogy tesztelje a hálózati késleltetést a következő helyen: <http://www.azurespeed.com>.
-   A Dynamics 365 for Operations sávszélességi követelményei a forgatókönyvtől függenek. A legtöbb jellemző forgatókönyv másodpercenként több mint 50 kilobájt sávszélességet igényel (KBps). Azonban olyan nagyteljesítményű forgatókönyvek esetében, mint például a munkaterületek vagy a kiterjedt testreszabást igénylő forgatókönyvek, nagyobb sávszélességet ajánlunk.

Általánosságban elmondható, hogy a Dynamics 365 for Operations az internetre optimalizált. A böngésző kliensből az Azure adatközpontba történő oda-vissza utak száma nagyon kicsi, és a teljes hasznos tartalom tömörítve van. **Figyelmeztetés:** Ne úgy számítsa ki a sávszélesség követelményeit az ügyfél helyéről, hogy megszorozza a felhasználók számát a minimális sávszélességi követelményekkel. Adott hely egyidejű használatát nagyon nehéz kiszámítani. A sávszélesség miatt aggódó ügyfelek számára a Dynamics 365 for Operations előzetes verziójának használata ajánlott.

## <a name="net-framework-requirements"></a>A .NET keretrendszer követelményei
A Dynamics 365 for Operations esetében a .NET-keretrendszer 4.6.2-es verziója szükséges az összes click-once alkalmazáshoz, például a dokumentumátirányító ügynökhöz. További tájékoztatás: [A .NET keretrendszer telepítése](https://msdn.microsoft.com/en-us/library/5a4x27ek(v=vs.110).aspx).

## <a name="supported-microsoft-office-applications"></a>Támogatott Microsoft Office-alkalmazások
-   A Microsoft Excel és Word bővítmények futtatásához telepítve kell lennie a Microsoft Office 2016 programnak Windows vagy Mac rendszeren. Verziójának követelményeivel kapcsolatos további részletekért lásd: [Office-integráció hibáinak elhárítása](/dynamics365/operations/dev-itpro/office-integration/office-integration-troubleshooting).
-   Az Exportálás Excel-be vagy az Exportálás a Word programba funkcióval létrehozott dokumentumok megtekintéséhez telepíteni kell a Microsoft Office 2007 vagy újabb verzióját.

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
    -   Windows 7 Professional, Enterprise és Ultimate verziók **Megjegyzés:** A Windows 7 csak akkor támogatott, ha a rendszerre manuálisan telepítették az Internet Explorer 11-et.
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

## <a name="requirements-for-development-on-local-vms"></a>A helyi virtuális gépek fejlesztési követelményei
A helyi virtuális gépek fejlesztési követelményeiről lásd: [helyszínen futó virtuális gép](../dev-tools/access-instances.md).

<a name="see-also"></a>Lásd még
--------

[Szerezze be a Dynamics 365 for Operations bétaverzióját](/dynamics365/operations/dev-itpro/dev-tools/get-evaluation-copy)




