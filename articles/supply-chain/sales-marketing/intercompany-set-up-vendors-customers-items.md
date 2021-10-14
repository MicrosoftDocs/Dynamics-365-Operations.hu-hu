---
title: Szállítók, vevők, és cikkek beállítása vállalatközi kereskedelemhez
description: Ez a témakör a szállítók, vevők, és cikkek beállításának módját ismerteti a vállalatközi kereskedelemhez
author: GalynaFedorova
ms.date: 09/01/2021
ms.topic: article
ms.search.form: CustTable, VendTable, EcoResProductListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 062b8fe956fef0f8172d26aac3df54b93e1941ef
ms.sourcegitcommit: fcfd85a508c0de52cfe11d1986892219e39ef406
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/23/2021
ms.locfileid: "7548301"
---
# <a name="set-up-vendors-customers-and-items-for-intercompany-trade"></a>Szállítók, vevők, és cikkek beállítása vállalatközi kereskedelemhez

[!include [banner](../../includes/banner.md)]

A szervezet vállalatközi kereskedelemre való előkészítéséhez meg kell határoznia azokat a szállítókat és vevőket, akikkel belső kereskedelmet fog folytatni. Ezt követően társítani kell ezeket a szállítókat és vevőket a megvásárolni vagy eladni kívánt cikkekhez.

1. Ugrás a **Beszerzés és forrás \> Beszállítók \> Minden szállító** pontra.
1. A vállalatközi szállítóként definiálni kívánt szállító kiválasztása.
1. A Műveleti ablaktábla **Általános** lapján válassza a **Vállalatközi** menüpontot.
1. Vállalatközi beállítási paraméterek megadása a szállítói fiókhoz. A paraméterek közé tartoznak továbbá az ügyfél jogi személy és partner, értékesítési rendelések irányelvei, a beszerzési rendelések irányelvei, az értékleképezés, valamint a beszerzési és értékesítési szerződésekre vonatkozó irányelvek. Megadhatja azt is, hogy a szállítói számláról vagy a másik jogi személy vevői számlájáról származó alapadatokat használja-e.
1. Kattintson a **Termékinformációk kezelése \> Termékek \> Kiadott termékek** lehetőségre.
1. A **Kiadott termékek** listaoldalon jelölje ki a szállítóhoz hozzárendelni kívánt cikkeket, hogy a cikkek elérhetők a vállalatközi kereskedelemben. Minden egyes tételhez nyissa meg a **Megjelent termék részletei** lapot. A **Beszerzés** lap **Szállító** mezőjébe írja be a szállító számát.
1. Nyissa meg a **Kinnlevőségek \> Vevők \> Minden vevő** lehetőséget.
1. A vállalatközi szállítóként definiálni kívánt ügyfél kiválasztásához válassza ki az ügyfelet.
1. A Műveleti ablaktábla **Általános** lapján válassza a **Vállalatközi** menüpontot.
1. Vállalatközi beállítási paraméterek megadása a vevői fiókhoz. A paraméterek közé tartoznak továbbá a szállító jogi személy és partner, beszerzési rendelések irányelvei, a értékesítési rendelések irányelvei, az értékleképezés, valamint az értékesítési és beszerzési szerződésekre vonatkozó irányelvek. Megadhatja azt is, hogy a vevői számláról vagy a másik jogi személy szállítói számlájáról származó alapadatokat használja-e.
1. A **Vevők** lapon, a **Számla- és szállítás** gyorslapon jelölje be a **Vállalatközi rendelések létrehozása** jelölőnégyzetet. Ha a rendeléseket közvetlenül a vevőkhöz szeretné szállítani, jelölje be a **Közvetlen kiszállítás** jelölőnégyzetet.

    > [!NOTE]
    > Ha vannak olyan cikkek, amelyet a vállalat raktároz és szállít ki a vevőknek, akkor előfordulhat, hogy nem szeretne automatikusan vállalatközi rendelést létrehozni, még akkor sem, ha van raktáron a cikkből. Ha ki szeretné kapcsolni a rendelések automatikus létrehozását olyan cikkeknél, amelyekből néha lehet raktáron, törölje a **Vállalatközi értékesítései rendelések létrehozása** jelölőnégyzet jelölését.

1. Ha engedélyezni szeretné, hogy egy értékesítési rendelésen közvetetten további sorokat hozzanak létre, jelölje be a **Közvetett rendeléssorok létrehozása** jelölőnégyzetet. Így a felhasználó sorokat adhat hozzá az eredeti értékesítési rendeléshez a vállalatközi értékesítési rendelésből.

> [!WARNING]
> Ha engedélyezi a rendeléssorok közvetett létrehozását, lehetővé teszi, hogy a vállalatközi értékesítési rendelésből bármit hozzáadjanak az eredeti értékesítési rendeléshez. A program ezután feldolgoz minden kiegészítést a vevőn keresztül, és hozzáadja a rendeléshez és a számlához. Ezenkívül a program minden, az értékesítésben érintett dokumentumot kinyomtat és felad automatikusan. A felhasználók nem kapnak figyelmeztetést a kiegészítésről.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
