---
title: Rendszerkövetelmények
description: Ez a cikk leírja a Microsoft Dynamics 365 Human Resources rendszer követelményeit.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SystemAdministrationWorkspaceForm
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: f86cd60466661c87d762f2e2f0765b92351ee2b8
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/18/2021
ms.locfileid: "6053587"
---
# <a name="system-requirements"></a>Rendszerkövetelmények

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Ez a cikk leírja a Microsoft Dynamics 365 Human Resources rendszer követelményeit. Ezenkívül ismerteti azokat az országokat és régiókat, ahol a Human Resources alkalmazás elérhető, valamint a nyelvekkel és a Human Resources adatainak lokalizációjával kapcsolatban tartalmaz információkat.

## <a name="supported-web-browsers"></a>Támogatott böngészők

A Human Resources alkalmazás az alábbi böngészők bármelyikében működik, ha azok a megadott operációs rendszer alatt futnak: 

*   Microsoft Edge (legfrissebb elérhető verziója) a Windows 10 rendszeren
*   Internet Explorer 11, Windows 10, Windows 8.1 vagy Windows 7 rendszereken
*   Google Chrome (legfrissebb elérhető verzió)
*   Apple Safari (legfrissebb elérhető verzió)

A böngésző legfrissebb változatáért látogasson el a szoftver gyártójának webhelyére. 

> [!NOTE]
> * A Task Recorder által generált képek rögzítéséhez és Microsoft Word-dokumentumba való ágyazásához telepítenie kell egy Chrome-bővítményt. 
> * A munkafolyamat-szerkesztő ClickOnce-alkalmazásként indul el. Csak Microsoft Edge és Internet Explorer (a Microsoft Windows támogatott verzióin) ClickOnce alkalmazások támogatása. A Workflow Editor ClickOnce alkalmazáshoz 64 bit-kompatibilis operációs rendszer szükséges.
> * A PDF-fájlok előnézetének megtekintéséhez olyan modern böngészők használatát javasoljuk, mint a Microsoft Edge (a legújabb nyilvánosan elérhető verzió) Windows 10 rendszeren, illetve a Google Chrome (a legújabb nyilvánosan elérhető verzió) Windows 10, Windows 8.1, Windows 8 vagy Windows 7 rendszeren vagy Google Nexus 10 táblagépeken.
>   Hálózati követelmények
> * A Human Resources alkalmazást olyan hálózatokhoz tervezték, amelyek késleltetési ideje 250-300 milliszekund (ms) vagy kevesebb. Ez a késleltetés a böngészőklienstől a Microsoft Azure adatközpontig, amely tárolja a Human Resources szolgáltatást. Javasoljuk, hogy tesztelje a hálózati késleltetést a következő helyen: [www.azurespeed.com](https://www.azurespeed.com "Azure késleltetési teszt").
> * A Human Resources alkalmazás sávszélesség-követelményei a forgatókönyvtől függnek. A legtöbb jellemző forgatókönyv másodpercenként több mint 50 kilobájt sávszélességet igényel (KBps).
> 
> [!WARNING]
> Ne úgy számítsa ki a sávszélesség követelményeit az ügyfél helyéről, hogy megszorozza a felhasználók számát a minimális sávszélességi követelményekkel. Adott hely egyidejű használatát nagyon nehéz kiszámítani. A sávszélesség miatt aggódó ügyfelek számára a Human Resources próbaverziójának használata ajánlott.

## <a name="supported-microsoft-office-applications"></a>Támogatott Microsoft Office-alkalmazások

* A Microsoft Excel és Word bővítmények futtatásához telepítve kell lennie a Microsoft Office 2016 programnak Windows vagy Mac rendszeren. Verziójának követelményeivel kapcsolatos további részletekért lásd: [Office-integráció hibáinak elhárítása](../fin-ops-core/dev-itpro/office-integration/office-integration-troubleshooting.md "Office-integráció – hibaelhárítás").
* Az Exportálás Excel-be vagy az Exportálás a Word programba funkcióval létrehozott dokumentumok megtekintéséhez telepíteni kell a Microsoft Office 2007 vagy újabb verzióját.

## <a name="regional-availability-languages-and-localization"></a>Regionális elérhetőség, nyelvek és lokalizáció

A Human Resources által támogatott országok, régiók és nyelvek listáját tartalmazó PDF-fájlt a következő helyen töltheti le: [A Microsoft Dynamics 365](/dynamics365/get-started/availability) nemzetközi elérhetősége. 

> [!NOTE]
> A felhasználói felület más nyelvekre való lokalizálása esetén az összes felhasználói adat a megadott nyelven van tárolva. E-maileket és sablonokat más nyelveken is létre lehet hozni, de az adatok, például az ütemezési adatok csak angol nyelven érhetők el.

Ha fejlesztőként érdekelt az ország-vagy régióspecifikus testreszabások létrehozásában, illetve a Microsoft által jelenleg támogatott országhoz vagy régióhoz kapcsolódó megoldások létrehozásában, lásd: [Globalizáció](/dynamics365/unified-operations/dev-itpro/lcs-solutions/country-region).


[!INCLUDE[footer-include](../includes/footer-banner.md)]