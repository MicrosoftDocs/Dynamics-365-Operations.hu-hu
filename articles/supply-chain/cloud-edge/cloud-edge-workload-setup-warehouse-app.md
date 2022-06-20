---
title: A Warehouse Management mobilalkalmazás konfigurálása felhőalapú és peremhálózat-léptékű egységekhez
description: Ez a cikk bemutatja a raktárkezelés mobilalkalmazások beállítását olyan raktárakhoz, amelyek a felhők és a peremhálózatok egysége által szolgálnak.
author: perlynne
ms.date: 12/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SysAADClientTable, SysUserManagement
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: SCM
ms.author: perlynne
ms.search.validFrom: 2022-01-31
ms.dyn365.ops.version: 10.0.25
ms.openlocfilehash: 86edef2dfa6e9c71c04d50f185148be3a622fea1
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8865238"
---
# <a name="configure-the-warehouse-management-mobile-app-for-cloud-and-edge-scale-units"></a>A Warehouse Management mobilalkalmazás konfigurálása felhőalapú és peremhálózat-léptékű egységekhez

[!include [banner](../includes/banner.md)]

Ez a cikk bemutatja a Raktárkezelés mobilalkalmazások beállítását, hogy felhasználhatók legyen olyan raktárakban, ahol a felhők és a peremhálózatok egysége szolgál fel.

## <a name="prerequisites"></a>Előfeltételek

Mielőtt elindítja a mobileszközöknek a felhőhöz vagy peremhálózati egységhez való csatlakozását, győződjön meg arról, hogy tudnak kapcsolódni a vállalati központhoz. Az útmutatásért lásd [a Raktárkezelés mobilalkalmazás telepítése és csatlakoztatása tudnivalókat](../warehousing/install-configure-warehouse-management-app.md).

## <a name="additional-setup-when-you-run-the-warehouse-management-mobile-app-against-a-scale-unit"></a>További beállítások, amikor a Raktárkezelés mobilalkalmazást egy mérlegegységhez futtatja

A raktári [mérlegegység](cloud-edge-landing-page.md#scale-unit-manager-portal) terhelésének részeként a Raktárkezelés mobilalkalmazás-eszközök csatlakoztatásához szükséges legtöbb adat automatikusan szinkronizálódik a nagyvállalati központból a mérlegegységbe. A mérlegegység telepítéséhez azonban meg kell adnia az adatokat az alkalmazások lapján (**Azure Active Directory** **\>\> Rendszerfelügyelet- beállítási alkalmazások).Azure Active Directory** Ezenkívül előfordulhat, hogy **frissítenie** kell a felhasználói azonosító alapértelmezett Vállalati értékét, vagy létre kell hoznia egy új felhasználót. Azok a felhasználók, amelyek olyan vállalathoz vannak társítva, amely nem létezik a mérlegegység-telepítésben, nem fognak tudni bejelentkezni, ha a Raktárkezelés mobilalkalmazás ehhez a mérlegegységhez kapcsolódik.

> [!NOTE]
> Mivel az alkalmazásoldalon **Azure Active Directory** található adatok szinkronizálása nem történik meg, manuálisan kell karbantartani ezt az adatot, ha a raktári terheléseket át szeretné áthelyezni egy másik skálaegységbe.

Ne feledje, hogy az egyes Azure Active Directory Raktárkezelés mobilalkalmazások kapcsolatbeállításának részeként a megadott erőforrás-URL-címnek a mérlegegységhez kell esnie, nem a vállalati központhoz.
