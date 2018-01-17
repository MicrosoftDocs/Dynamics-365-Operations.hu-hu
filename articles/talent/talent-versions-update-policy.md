---
title: "Dynamics 365 for Talent rendszerkövetelmények és frissítési irányelv"
description: "Ez a témakör a Dynamics 365 for Talent rendszerre vonatkozó rendszerkövetelményeket sorolja fel. Ezenkívül ismerteti a frissítési irányelvet is."
author: rschloma
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: Talent, update policy, requirements, system requirements
audience: Application User, IT Pro
ms.reviewer: rschloma
ms.search.scope: Operations, Core
ms.custom: 63213
ms.assetid: 5dbc62fc-0184-4c0e-9856-e735fc68799e
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 7bcc8464d34c35423e86c963c6b493fc09db4472
ms.contentlocale: hu-hu
ms.lasthandoff: 11/03/2017

---

# <a name="microsoft-dynamics-365-for-talent-system-requirements-and-update-policy"></a>A Microsoft Dynamics 365 for Talent rendszerkövetelményei és frissítési irányelve

[!include[banner](includes/banner.md)]


Ez a témakör a Microsoft Dynamics 365 for Talent rendszerre vonatkozó rendszerkövetelményeket sorolja fel. Ezenkívül ismerteti a frissítési irányelvet is.

## <a name="supported-web-browsers"></a>Támogatott böngészők

A Microsoft Dynamics 365 for Talent webes alkalmazása az alábbi böngészők bármelyikében működik, ha azok a megadott operációs rendszer alatt futnak: 

*   Microsoft Edge (legfrissebb elérhető verziója) a Windows 10 rendszeren
*   Internet Explorer 11, Windows 10, Windows 8.1 vagy Windows 7 rendszereken
*   Google Chrome (legfrissebb elérhető verziója) Windows 10, Windows 8.1, Windows 8, Windows 7 rendszereken, vagy Google Nexus 10 táblagépen
*   Apple Safari (legfrissebb elérhető verziója) Mac OS X 10.10 (Yosemite), 10.11 (El Capitan), 10.12 (Sierra) rendszereken, vagy Apple iPad gépen

A böngésző legfrissebb változatáért látogasson el a szoftver gyártójának webhelyére. 

> [!NOTE]
> * A Task Recorder által generált képek rögzítéséhez és Microsoft Word-dokumentumba való ágyazásához telepítenie kell egy Chrome-bővítményt. 
> * A munkafolyamat-szerkesztő ClickOnce-alkalmazásként indul el. Csak a Microsoft Edge és az Internet Explorer (a Microsoft Windows egy támogatott verziójának használata esetén) támogatja a ClickOnce-alkalmazásokat. A Workflow Editor ClickOnce alkalmazáshoz 64 bit-kompatibilis operációs rendszer szükséges.
> * A PDF-fájlok előnézetének megtekintéséhez olyan modern böngészők használatát javasoljuk, mint a Microsoft Edge (a legújabb nyilvánosan elérhető verzió) Windows 10 rendszeren, illetve a Google Chrome (a legújabb nyilvánosan elérhető verzió) Windows 10, Windows 8.1, Windows 8 vagy Windows 7 rendszeren vagy Google Nexus 10 táblagépeken.
Hálózati követelmények
> * A Dynamics 365 for Talent olyan hálózatokhoz tervezték, amelyek várakozási ideje kevesebb 250–300 milliszekund (ms) vagy annál kevesebb. Ez a latencia a böngészőklienstől a Microsoft Azure adatközpontig, amely tárolja a Dynamics 365 for Talent rendszert. Javasoljuk, hogy tesztelje a hálózati késleltetést a következő helyen: [www.azurespeed.com] (http://www.azurespeed.com "Azure késleltetési teszt").
> * A Dynamics 365 for Talent sávszélességi követelményei a forgatókönyvtől függenek. A legtöbb jellemző forgatókönyv másodpercenként több mint 50 kilobájt sávszélességet igényel (KBps).

> [!WARNING]
> Ne úgy számítsa ki a sávszélesség követelményeit az ügyfél helyéről, hogy megszorozza a felhasználók számát a minimális sávszélességi követelményekkel. Adott hely egyidejű használatát nagyon nehéz kiszámítani. A sávszélesség miatt aggódó ügyfelek számára a Dynamics 365 for Talent próbaverziójának használata ajánlott.

## <a name="supported-microsoft-office-applications"></a>Támogatott Microsoft Office-alkalmazások

*   A Microsoft Excel és Word bővítmények futtatásához telepítve kell lennie a Microsoft Office 2016 programnak Windows vagy Mac rendszeren. Verziójának követelményeivel kapcsolatos további részletekért lásd: [Office-integráció hibáinak elhárítása] (../dev-itpro/office-integration/office-integration-troubleshooting.md "Office-integráció hibáinak elhárítása").
*   Az Exportálás Excel-be vagy az Exportálás a Word programba funkcióval létrehozott dokumentumok megtekintéséhez telepíteni kell a Microsoft Office 2007 vagy újabb verzióját.

## <a name="update-policy"></a>Frissítési irányelv

A Microsoft Dynamics 365 for Talent szervizelése felhőalapú. A Dynamics 365 for Talent frissítései folyamatosak, és a Microsoft automatikusan alkalmazza őket.

A frissítések rendszeres ütemben jelennek meg, és a rendszer minden környezetben alkalmazza őket.  A Dynamics 365 for Talent rendszert a [Microsoft támogatási életciklus-irányelve] támogatja (https://support.microsoft.com/en-us/gp/lifecycle#gp/OSSLpolicy "Microsoft Support Lifecycle"), amely egységes és kiszámítható irányelveket nyújt a termék elérhetőségével kapcsolatos támogatásról.

