---
title: Talent rendszerkövetelményei
description: Ez a témakör felsorolja a Dynamics 365 Talent követelményeit.
author: andreabichsel
manager: AnnBe
ms.date: 10/21/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.custom: 63213
ms.assetid: 5dbc62fc-0184-4c0e-9856-e735fc68799e
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 509827d5736887f56e7754a0760af7dea76277f7
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/03/2020
ms.locfileid: "3006055"
---
# <a name="talent-system-requirements"></a>Talent rendszerkövetelményei

[!include [banner](includes/banner.md)]

Ez a témakör a Microsoft Dynamics 365 Talent követelményeit írja le, beleértve az Attract és Onboard követelményeit is. Ezenkívül kiemeli azokat az országokat és régiókat, ahol a Talent elérhető, valamint a Talent adatainak lokalizációjával és a nyelvekkel kapcsolatos információkat. Mindemellett ez a témakör a Talent frissítési irányelveit is tartalmazza.

## <a name="supported-web-browsers"></a>Támogatott böngészők

A Microsoft Dynamics 365 Talent az alábbi böngészők bármelyikében működik, ha azok a megadott operációs rendszer alatt futnak: 

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
> * Dynamics 365 Talent szoftvert olyan hálózatokhoz tervezték, amelyek várakozási ideje 250-300 milliszekund (ms) vagy kevesebb. Ez a késleltetés a böngészőklienstől a Microsoft Azure adatközpontig, amely tárolja a Talent szolgáltatást. Javasoljuk, hogy tesztelje a hálózati késleltetést a következő helyen: [www.azurespeed.com](https://www.azurespeed.com "Azure késleltetési teszt").
> * A Talent sávszélesség-követelményei a forgatókönyvtől függnek. A legtöbb jellemző forgatókönyv másodpercenként több mint 50 kilobájt sávszélességet igényel (KBps).
> 
> [!WARNING]
> Ne úgy számítsa ki a sávszélesség követelményeit az ügyfél helyéről, hogy megszorozza a felhasználók számát a minimális sávszélességi követelményekkel. Adott hely egyidejű használatát nagyon nehéz kiszámítani. A sávszélesség miatt aggódó ügyfelek számára a Talent próbaverziójának használata ajánlott.

## <a name="supported-microsoft-office-applications"></a>Támogatott Microsoft Office-alkalmazások

* A Microsoft Excel és Word bővítmények futtatásához telepítve kell lennie a Microsoft Office 2016 programnak Windows vagy Mac rendszeren. Verziójának követelményeivel kapcsolatos további részletekért lásd: [Office-integráció hibáinak elhárítása](../dev-itpro/office-integration/office-integration-troubleshooting.md "Office-integráció – hibaelhárítás").
* Az Exportálás Excel-be vagy az Exportálás a Word programba funkcióval létrehozott dokumentumok megtekintéséhez telepíteni kell a Microsoft Office 2007 vagy újabb verzióját.

## <a name="regional-availability-languages-and-localization"></a>Regionális elérhetőség, nyelvek és lokalizáció

A Talent által támogatott országok, régiók és nyelvek listáját tartalmazó PDF-fájlt a következő helyen töltheti le: [A Microsoft Dynamics 365](https://docs.microsoft.com/dynamics365/get-started/availability) nemzetközi elérhetősége. 

> [!NOTE]
> A felhasználói felület más nyelvekre való lokalizálása esetén az összes felhasználói adat a megadott nyelven van tárolva. E-maileket és sablonokat más nyelveken is létre lehet hozni, de az adatok, például az ütemezési adatok csak angol nyelven érhetők el.

Ha fejlesztőként érdekelt az ország-vagy régióspecifikus testreszabások létrehozásában, illetve a Microsoft által jelenleg támogatott országhoz vagy régióhoz kapcsolódó megoldások létrehozásában, lásd: [Globalizáció](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lcs-solutions/country-region).

