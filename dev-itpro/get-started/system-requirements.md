---
title: "Rendszerkövetelmények"
description: "Ez a témakör a Microsoft Dynamics 365 műveletekhez aktuális verziójának rendszerkövetelményeit."
author: sericks007
manager: AnnBe
ms.date: 2017-04-04
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
translationtype: Human Translation
ms.sourcegitcommit: c8c96dc9705688308dd4a5c720700ddc17657d75
ms.openlocfilehash: 9220c093d3f6d6700127c93651db4083be300311
ms.lasthandoff: 03/31/2017


---

# <a name="system-requirements"></a>Rendszerkövetelmények

Ez a témakör a Microsoft Dynamics 365 műveletekhez aktuális verziójának rendszerkövetelményeit.

<a name="supported-web-browsers"></a>Támogatott böngészők
----------------------

A Microsoft Dynamics 365 műveletek webalkalmazás az alábbi webböngészők az adott operációs rendszeren futó bármelyik futtatható:

-   A Microsoft Edge (legújabb verzió nyilvánosan elérhető) a Windows 10
-   Internet Explorer 11, Windows 10, Windows 8.1 vagy Windows 7 rendszereken
-   Google Chrome (legújabb verzió nyilvánosan elérhető) a Windows 10, Windows 8.1, Windows 8, Windows 7 vagy a Google Nexus 10 táblaszámítógépen
-   Apple Safari (legújabb verzió nyilvánosan elérhető) a Mac OS X 10.10 (Yosemite), 10.11 (El Capitan) vagy 10.12 (Sierra) vagy Apple iPad

A böngésző legfrissebb változatáért látogasson el a szoftver gyártójának webhelyére. **Megjegyzések:**

-   Vegyen fel lemezképeket a Feladatrögzítő alapján jöttek létre, és azok szerepelnek-e a Microsoft Word-dokumentumokban, a Chrome bővítmény telepítve kell rendelkeznünk. <!---For instructions about how to install the extension, see [Screenshot Extension setup](/dynamics365/operations/dev-itpro/user-interface/task-recorder).-->
-   A munkafolyamat-szerkesztőben a ClickOnce alkalmazás fut. Csak a Microsoft Edge és az Internet Explorer (a Microsoft Windows támogatott verziója) támogatja a ClickOnce alkalmazásoknak. A munkafolyamat-szerkesztő ClickOnce alkalmazás kompatibilis 64 bites operációs rendszert igényel.
-   A Report Designer, a pénzügyi jelentések a ClickOnce alkalmazás fut. Kompatibilis 64 bites operációs rendszert igényel. Chrome használata, telepítenie kell a ClickOnce-bővítmény a jelentés Tervező ügyfél letölteni. Ha Chrome az incognito mód használata esetén győződjön meg arról, hogy a ClickOnce kiterjesztést is engedélyezve van az incognito mód.

### <a name="supported-web-browsers-for-retail-cloud-pos"></a>A kiskereskedelmi felhő-POS pénztárgép által támogatott böngészők

A Retail POS Dynamics 365 műveletek felhő rendszer bármely az alábbi webböngészők az adott operációs rendszeren futó futtatható:

-   A Microsoft Edge (legújabb verzió nyilvánosan elérhető) a Windows 10
-   Internet Explorer 11, Windows 10, Windows 8.1 vagy Windows 7 rendszereken
-   Króm (legújabb verzió nyilvánosan elérhető) Windows 10, Windows 8.1 vagy a Windows 7

## <a name="network-requirements"></a>Hálózati követelmények
-   365 Dynamics műveletek hálózatokhoz tervezték, késés, kevesebb mint 150 milliszekundum (ms). Ez a böngésző ügyfélszámítógépről a Microsoft Azure adatközpont tároló Dynamics 365 műveletek várakozási ideje. Azt javasoljuk, hogy a hálózat késése, vizsgálati <http://www.azurespeed.com>.
-   Dynamics 365 műveletek sávszélességi követelmények függenek a forgatókönyv. Legjellemzőbb esetek több mint 50 kilobájt / másodperc (KB/s) esetén van szükség. Azonban nagy terhelés követelményeket támasztanak, például munkaterületek vagy forgatókönyvek széles körű testreszabási forgatókönyvek nagyobb sávszélességet ajánlott.

Dynamics 365 műveletek általában az interneten van optimalizálva. Elérését a böngészőben ügyfélben az Azure adatközpont száma nagyon kicsi, és a teljes tartalom tömörítve van. **Figyelmeztetés:** ügyfél helyről sávszélességi követelmények nem számítja ki a felhasználók számát megszorozzák a minimális sávszélesség-követelményeket. Egyidejű használatát egy adott helyen, akkor nagyon nehéz kiszámítani. Azok számára, akik aggódnak sávszélesség-követelményeket ezen bétaverziója Dynamics 365 műveletekhez.

## <a name="net-framework-requirements"></a>NET-keretrendszer követelmények
365 Dynamics műveletekhez szükséges .NET Framework 4.6.2 minden kattintson-egyszer alkalmazások, például a dokumentum útválasztási ügynök. Telepítési utasítások, lásd: [a .NET keretrendszer telepítése](https://msdn.microsoft.com/en-us/library/5a4x27ek(v=vs.110).aspx).

## <a name="supported-microsoft-office-applications"></a>Támogatott Microsoft Office-alkalmazások
-   A Microsoft Excel és Word bővítmény futtatásához szükséges Microsoft Office 2016 Windows vagy Mac telepítve. Verziójával kapcsolatos további részletekért lásd: [Office-integráció hibáinak elhárítása](/dynamics365/operations/dev-itpro/office-integration/office-integration-troubleshooting).
-   Az Exportálás az Excel vagy Word funkciók Export által létrehozott dokumentumok megtekintéséhez a Microsoft Office 2007-es vagy újabb verziója szükséges.

## <a name="retail-modern-pos-requirements"></a>A Retail Modern POS követelmények
### <a name="supported-operating-systems"></a>Támogatott operációs rendszerek

-   Modern a Retail POS rendszer egy 32 bites alkalmazás, de a x86 és a x64 architektúrák futni fog.
-   Modern a Retail POS csak Windows 10 Pro, vállalati és vállalati hosszú távú karbantartási ág (LTSB) verziója esetén támogatja.

### <a name="minimum-system-requirements"></a>Minimális rendszerkövetelmények

-   A minimális támogatott felbontása 1280 × 1024.
-   A számítógépen futó Modern Retail POS ezeknek a követelményeknek kell megfelelniük:
    -   Kell lennie, legalább egy kétmagos processzorral futó, nem kevesebb, mint 2 gigahertzes (GHz).
    -   Kell lennie, legalább 3 gigabájt (GB) RAM.
    -   Azt az Internet-hozzáféréssel kell rendelkeznie.

## <a name="retail-hardware-station-requirements"></a>Kiskereskedelmi állomás hardverkövetelmények
### <a name="supported-operating-systems"></a>Támogatott operációs rendszerek

-   Kiskereskedelmi hardver állomás egy 32 bites alkalmazás, de a x86 és a x64 architektúrák futni fog.
-   Kiskereskedelmi hardver állomás a következő operációs rendszerek támogatják:
    -   Windows 7 Professional, Enterprise és Ultimate kiadások **Megjegyzés:** a Windows 7 támogatott csak akkor, ha az Internet Explorer 11 kézzel telepíti a rendszer.
    -   Windows 8.1 Update 1 Professional, Enterprise és beágyazott kiadások
    -   Windows 10 Pro, vállalati és vállalati LTSB

### <a name="minimum-system-requirements"></a>Minimális rendszerkövetelmények

A számítógépnek meg kell felelnie minden rendszerkövetelmények telepítéséről és használatáról a következő elemeket:

-   Internet Information Services (IIS)
-   Harmadik féltől származó hardver

## <a name="retail-store-scale-unit-requirements"></a>Kiskereskedelmi üzlet skála egységre követelmények
### <a name="supported-operating-systems"></a>Támogatott operációs rendszerek

-   Retail Store időskála-egységet egy 32 bites alkalmazás, de a x86 és a x64 architektúrák futni fog.
-   Retail Store időskála-egységet a következő operációs rendszerek támogatják:
    -   Windows 7 Professional, Enterprise és Ultimate kiadásához
    -   Windows 8.1 Update 1 Professional, Enterprise és beágyazott kiadások
    -   Windows 10 Pro, vállalati és vállalati LTSB

### <a name="minimum-system-requirements"></a>Minimális rendszerkövetelmények

-   4 GB RAM
-   Maximális processzorsebesség 1,6 GHz-es per core (két magot minimális is.)
-   Legalább 10 GB szabad lemezterület (a csatorna-adatbázisból is szükséges nagy mennyiségű helyet.)

### <a name="recommended-system-requirements"></a>Ajánlott rendszerkövetelményei

-   6 GB RAM
-   2.4 GHz i7 (vagy ezzel egyenértékű) csúcs CPU sebessége / core (négy magot ajánlott.)
-   Legalább 10 GB szabad lemezterület (a csatorna-adatbázisból is szükséges nagy mennyiségű helyet.)

## <a name="requirements-for-development-on-local-vms"></a>A helyi VMs fejlesztési követelményei
Fejlesztési követelmények információt a helyi virtuális gépek (VMs), lásd: [helyszíni futtató virtuális gép](/dynamics365/operations/dev-itpro/dev-tools/access-instances#vm-that-is-running-in-premises).

<a name="see-also"></a>Lásd még
--------

[Műveletek Dynamics 365 próbaverziójának letöltése](/dynamics365/operations/dev-itpro/dev-tools/get-evaluation-copy)


