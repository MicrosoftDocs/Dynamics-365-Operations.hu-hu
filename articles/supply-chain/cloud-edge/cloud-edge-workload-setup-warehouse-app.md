---
title: Konfigurálja a Warehouse Management mobilalkalmazást felhő- és peremléptékű egységekhez
description: Ez a témakör elmagyarázza, hogyan állíthatja be a Warehouse Management mobilalkalmazásokat olyan raktárakhoz, amelyeket felhő vagy szélső léptékű egység szolgál ki.
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
ms.openlocfilehash: 1fa00b40db2f6246029876964dca9d3229567848
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/31/2022
ms.locfileid: "8071780"
---
# <a name="configure-the-warehouse-management-mobile-app-for-cloud-and-edge-scale-units"></a>Konfigurálja a Warehouse Management mobilalkalmazást felhő- és peremléptékű egységekhez

[!include [banner](../includes/banner.md)]

Ez a témakör bemutatja, hogyan állíthatja be a Warehouse Management mobilalkalmazásokat, hogy azokat felhő- vagy szélső léptékű egység által kiszolgált raktárakban lehessen használni.

## <a name="prerequisites"></a>Előfeltételek

Mielőtt elkezdené beállítani mobileszközeit, hogy csatlakozzanak egy felhőhöz vagy peremléptékű egységhez, győződjön meg arról, hogy tudnak csatlakozni a vállalati hubhoz. Az utasításokat lásd [Telepítse és csatlakoztassa a Warehouse Management mobilalkalmazást](../warehousing/install-configure-warehouse-management-app.md).

## <a name="additional-setup-when-you-run-the-warehouse-management-mobile-app-against-a-scale-unit"></a>További beállítások, amikor a Warehouse Management mobilalkalmazást mérlegegységen futtatja

Ennek részeként a [telepítési folyamat a raktári méretű egység munkaterheléseihez](cloud-edge-landing-page.md#scale-unit-manager-portal), a Warehouse Management mobilalkalmazás-eszközök csatlakoztatásához szükséges adatok nagy része automatikusan szinkronizálva van a vállalati központról a mérlegegységre. Az adatokat azonban meg kell adnia a **Azure Active Directory alkalmazások** oldal (**Rendszer adminisztráció \> Beállít \>Azure Active Directory alkalmazások**) a léptékű egység telepítéséről. Ezenkívül előfordulhat, hogy frissítenie kell az alapértelmezettet **Vállalat** értéket a felhasználói azonosítóhoz, vagy hozzon létre egy új felhasználót. Azok a felhasználók, akik olyan vállalathoz vannak társítva, amely nem létezik a mérlegegység üzembe helyezésében, nem tudnak bejelentkezni, ha a Warehouse Management mobilalkalmazás csatlakozik az adott mérlegegységhez.

> [!NOTE]
> Mivel az adatok a **Azure Active Directory alkalmazások** Az oldal nincs szinkronizálva, akkor manuálisan kell karbantartania ezeket az adatokat, ha át szeretné helyezni a raktári munkaterheléseket egy másik méretezési egységbe.

Ne feledje, hogy az egyes Warehouse Management mobilalkalmazások kapcsolatbeállításának részeként a megadott Azure Active Directory Az erőforrás URL-jének a méretezési egységnek kell lennie a vállalati hub helyett.
