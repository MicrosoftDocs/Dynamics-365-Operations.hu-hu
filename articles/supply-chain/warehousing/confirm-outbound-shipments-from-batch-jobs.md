---
title: Kimenő szállítmányok jóváhagyása kötegelt feladatokból
description: Ez a témakör azt mutatja be, hogyan lehet beállítani egy olyan kötegelt feladatot, amely automatikusan megerősíti a kimenő átmozgatási rendelések szállítását a szállításra kész rakományok számára.
author: perlynne
ms.date: 07/31/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-07-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: f68dcfc0c1454ee5b095e186c52faa6c83bf8dc6
ms.sourcegitcommit: fcb8a3419e3597fe855cae9eb21333698518c2c7
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/09/2022
ms.locfileid: "8103915"
---
# <a name="confirm-outbound-shipments-from-batch-jobs"></a>Kimenő szállítmányok jóváhagyása kötegelt feladatokból

[!include [banner](../includes/banner.md)]

Ez a témakör azt mutatja be, hogyan lehet beállítani egy olyan kötegelt feladatot, amely automatikusan megerősíti a kimenő átmozgatási rendelések szállítását a szállításra kész rakományok számára. Az itt leírt kötegelt feladat csak átmozgatási rendelések szállítására vonatkozik, az értékesítési rendelésekre nem.

## <a name="turn-the-confirm-outbound-shipments-from-batch-jobs-feature-on-or-off"></a>A Kimenő szállítmányok megerősítése kötegelt feladatokból funkció be- és kikapcsolása

Az ebben a témakörben *leírt* funkció használatához a rendszeren be kell kapcsolva lennie a Kimenő szállítmányok megerősítése kötegelt feladatokból funkciónak. Az Ellátásilánc-kezelés 10.0.21-es verziója szerint ez a funkció alapértelmezés szerint be van kapcsolva. A 10.0.25-ös ellátásilánc-kezelésben ez a funkció kötelező, és nem lehet kikapcsolni. Ha 10.0.25-ösnél régebbi verziót futtat, *·*[akkor](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) a rendszergazdák a Funkciókezelés munkaterület Kimenő szállítmányok megerősítése funkciójának keresésével kapcsolják be és kapcsolják ki a funkciót.

## <a name="process-outbound-shipments"></a>Kimenő szállítmányok feldolgozása

Ha be szeretné állítani, hogy a kimenő szállítmányok jóváhagyását a szállításra kész rakományok számára futtassa az ütemezett kötegelt feladathoz:

1. Lépjen a **Raktárkezelés \> Ismétlődő feladatok \> Kimenő szállítmányok feldolgozása** menüpontra.
1. Megnyílik a **Szállítmány jóváhagyása** párbeszédpanel. **A szerepeltetni kívánt rekordok** gyorslapján válassza a **szűrő** elemet.
1. Megnyílik a lekérdezéstervező párbeszédpanel. A **Tartomány** lapon adjon hozzá egy sort az alábbi értékekkel:
    - **Tábla** - *Rakományok*
    - **Származtatott tábla** - *Rakományok*
    - **Mező** - *Rakomány állapota*
    - **Feltételek** - *Betöltött*
1. Kattintson az **OK** gombra a **Szállítmány jóváhagyása** párbeszédpanelhez való visszatéréshez.
1. A **Futtatás a háttérben** gyorslapon állítsa a **Kötegelt feldolgozást** **Igen** értékre.
1. A **Futtatás a háttérben** gyorslapon válassz az **Ismétlődés** elemet.
1. Megnyílik az **Ismétlődés meghatározása** párbeszédpanel. Az üzleti tevékenységének megfelelően állítsa be a futási ütemezést.
1. Kattintson az **OK** gombra a **Szállítmány jóváhagyása** párbeszédpanelhez való visszatéréshez.
1. Válassza az **OK** gombot a **Szállítmány jóváhagyása** párbeszédpanelen a kötegelt feladat köteg várólistájához adásához.

További tudnivalókhoz lásd a [Kötegelt feldolgozás áttekintése](../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md) elemet.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]