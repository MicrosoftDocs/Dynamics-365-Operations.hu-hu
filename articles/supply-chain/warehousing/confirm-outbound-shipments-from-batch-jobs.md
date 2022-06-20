---
title: Kimenő szállítmányok megerősítése kötegelt feladatokból
description: Ez a témakör leírja, hogyan lehet olyan kötegelt feladatot beállítani, amely automatikusan megerősíti a kimenő átszállítású szállítmányokat a szállításra kész rakományok számára.
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
ms.openlocfilehash: 00749a69b17b0064290d7b41ccb2171386716302
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8875101"
---
# <a name="confirm-outbound-shipments-from-batch-jobs"></a>Kimenő szállítmányok megerősítése kötegelt feladatokból

[!include [banner](../includes/banner.md)]

Ez a témakör leírja, hogyan lehet olyan kötegelt feladatot beállítani, amely automatikusan megerősíti a kimenő átszállítású szállítmányokat a szállításra kész rakományok számára. Az itt leírt kötegelt feladat csak átmozgatási rendelések szállítására vonatkozik, az értékesítési rendelésekre nem.

## <a name="turn-the-confirm-outbound-shipments-from-batch-jobs-feature-on-or-off"></a>A Kimenő szállítmányok megerősítése kötegelt feladatokból funkció be- és kikapcsolása

Az ebben a cikkben ismertetett *funkció* használatához a rendszeren be kell kapcsolva lennie a Kimenő szállítmányok megerősítése kötegelt feladatokból funkciónak. Az Ellátásilánc-kezelés 10.0.21-es verziója szerint ez a funkció alapértelmezés szerint be van kapcsolva. A 10.0.25-ös ellátásilánc-kezelésben ez a funkció kötelező, és nem lehet kikapcsolni. Ha 10.0.25-ösnél régebbi verziót futtat, *·*[akkor](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) a rendszergazdák a Funkciókezelés munkaterület Kimenő szállítmányok megerősítése funkciójának keresésével kapcsolják be és kapcsolják ki a funkciót.

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