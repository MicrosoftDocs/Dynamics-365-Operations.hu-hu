---
title: Webes tevékenység eseménygyűjteményről való leiratkozás
description: Ez a témakör azt mutatja be, hogyan engedélyezheti a webhely látogatói számára, hogy leiratkozzanak a Microsoft Dynamics 365 Commerce webes tevékenység eseménygyűjteményről.
author: aamiral
manager: AnnBe
ms.date: 05/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 4b0e48307527a8fea729d8dfdcdbc6337be0faf1
ms.sourcegitcommit: 8058db089b8768076ff1250be77d42a6e2b3f570
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2020
ms.locfileid: "3378992"
---
# <a name="opt-out-of-web-activity-event-collection"></a>Webes tevékenység eseménygyűjteményről való leiratkozás
[!include [banner](includes/banner.md)]

Ez a témakör azt mutatja be, hogyan teheti lehetővé az ügyfeleinek a webes tevékenység eseménygyűjteményről való leiratkozást a Microsoft Dynamics 365 Commerce alkalmazásban.

## <a name="overview"></a>Áttekintés

A Dynamics 365 Commerce segítségével a webhely rendszergazdái elemezhetik az e-kereskedelmi webhelyeik felhasználóinak webes tevékenységét. Ily módon jobban megérthetik a webhelyeik használatát, és optimalizálni tudják a webhelyeket a továbbfejlesztett felhasználói élmény biztosítása és az üzleti célkitűzések kielégítése érdekében.


## <a name="ways-for-administrators-to-implement-an-opt-out-experience"></a>A leiratkozási élmény megvalósítási módjai a rendszergazdák számára

A leiratkozási élményt a rendszergazdák háromféle módon tudják megvalósítani.

### <a name="opt-out-on-behalf-of-users"></a>Leiratkozás a felhasználók nevében

A Commerce-központ (HQ) Fiókkezelés részében a rendszergazdák elvégezhetik a leiratkozást a felhasználók nevében.

1. A HQ-ügyfél részben, a **Minden ügyfél** oldalon keressen és válasszon ki egy vevőt.
1. A vevői részletek oldalon, a **Kiskereskedelem** gyorslap **Adatvédelem** részében adja meg a **Ne kövesse a webes tevékenységet** beállításnak az **Igen** értéket.

    ![Adatvédelmi beállítások](media/Disablepersonalizationpart2.png)

1. Válassza a **Mentés** gombot, majd zárja be az oldalt.

### <a name="module-based-opt-out-experience"></a>Modulalapú leiratkozási élmény

A rendszergazdák megengedik a hitelesített felhasználók számára, hogy saját maguk végezzék el a webes tevékenységek eseménygyűjtéséről való leiratkozást. Ennek a leiratkozási élménynek a biztosításához adja hozzá a leiratkozási modult a vásárlói fiók profiloldalaihoz.

### <a name="custom-extensions"></a>Egyéni bővítmények

A rendszergazdák saját bővítményeiket hozhatnak létre a felhasználók leiratkozási élményének kezeléséhez. További információk: [Retail Server API-k hívása](e-commerce-extensibility/call-retail-server-apis.md) és [Online csatorna bővíthetősége](e-commerce-extensibility/overview.md).
