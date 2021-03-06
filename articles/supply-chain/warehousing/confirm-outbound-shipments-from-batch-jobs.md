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
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: 69e61e1c04dd72efbe1d2f028c078100e07176f6
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5838442"
---
# <a name="confirm-outbound-shipments-from-batch-jobs"></a>Kimenő szállítmányok jóváhagyása kötegelt feladatokból

[!include [banner](../includes/banner.md)]

Ez a témakör azt mutatja be, hogyan lehet beállítani egy olyan kötegelt feladatot, amely automatikusan megerősíti a kimenő átmozgatási rendelések szállítását a szállításra kész rakományok számára. Az itt leírt kötegelt feladat csak átmozgatási rendelések szállítására vonatkozik, az értékesítési rendelésekre nem.

## <a name="enable-the-confirm-outbound-shipments-from-batch-jobs-feature"></a>Kimenő szállítmányok jóváhagyásának engedélyezése a kötegelt feladatok funkcióból

A funkció használata előtt engedélyeznie kell a saját rendszerében. A rendszergazdák használhatják a [Funkciókezelési](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) oldalt a funkció állapotának ellenőrzéséhez, és szükség esetén engedélyezéséhez. A funkció a következőként szerepel:

- **Modul** - *Raktárkezelés*
- **Funkció neve** - *Kimenő szállítmányok jóváhagyásának engedélyezése a kötegelt feladatok funkcióból*

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