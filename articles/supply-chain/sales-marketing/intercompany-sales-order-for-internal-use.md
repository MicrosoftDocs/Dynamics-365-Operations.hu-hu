---
title: Vállalatközi értékesítési rendelés létrehozása belső használatra
description: Ez a témakör bemutatja, hogyan lehet vállalatközi értékesítési rendelést létrehozni belső használatra
author: GalynaFedorova
ms.date: 09/01/2021
ms.topic: article
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 0718a1560ec42df2a0a12e8b81484aa3be46d2d8
ms.sourcegitcommit: fcfd85a508c0de52cfe11d1986892219e39ef406
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/23/2021
ms.locfileid: "7548305"
---
# <a name="create-an-intercompany-sales-order-for-internal-use"></a>Vállalatközi értékesítési rendelés létrehozása belső használatra

[!include [banner](../../includes/banner.md)]

Általánosságban a vállalatközi beszerzési rendelés alapján automatikusan létrejön egy vállalatközi értékesítési rendelés. A vállalatközi értékesítési rendelések manuálisan is létrehozhatók, amelyek ezután a vállalatközi vevő jogi személyében létrehoznak egy vállalatközi beszerzési rendelést.

![Vállalatközi belső értékesítési folyamat](media/intercompanyinternalsalesprocess.png)

## <a name="create-an-intercompany-sales-order-manually"></a>Vállalatközi értékesítési rendelés létrehozása manuálisan

Végezze el ezeket a lépéseket a B jogi személyen az ábrán látható módon.

1. Ugrás a **Kinnlevőségek \> Értékesítési rendelések \> Minden értékesítési rendelésre**.
1. Jelölje be a műveleti ablakban az **Értékesítési rendelés** lehetőséget az értékesítési rendelés létrehozásához.
1. Az **Értékesítési rendelés létrehozása** lapon válasszon ki egy vevői fiókot. Az **Általános** gyorslapon ügyeljen arra, hogy a **Vállalatközi** jelölőnégyzet be legyen jelölve. Ez azt jelzi, hogy a kiválasztott vevő egy vállalatközi vevő.
1. Írja be vagy módosítsa az adatokat, majd válassza az **OK** gombot, és a szokásos módon töltse ki a rendeléssorokat.

    A **Szállítási cím** mező értékét a program átmásolja a vállalatközi értékesítési rendelés fejlécből a vállalatközi beszerzési rendelés fejlécébe. A **Cikkszám** mező értékét, beleértve a termékdimenziókat, valamint a **Szállítási dátum** és **Pénznemkód mező** értékét a vállalatközi értékesítésirendelés-sorokból a vállalatközi beszerzésirendelés-sorokba másolja a program.

1. Válassza rendelés fejIécében lévő **Vállalatközi** parancsot a kapcsolódó vállalatközi beszerzési rendelés megtekintéséhez.
1. A rendeléssorok vállalatközi információinak megtekintéséhez válassza a **Vállalatközi** lehetőséget.

> [!TIP]
> A vállalatközi értékesítési rendeléseket a **Vállalatközi rendelések** lapon lehet megtekinteni.

> [!NOTE]
> A vállalatközi munka során javasoljuk, hogy számlázás után törölje a **Rendelés törlése számlázás után** jelölőnégyzetet jelölését a **Kinnlevőségek paraméterei** oldalon. Ellenkező esetben a kapcsolódó beszerzési rendelés törlődik. Azt is javasoljuk, hogy számlázás után törölje a **Beszerzési rendelés törlése számlázás után** jelölőnégyzetet jelölését a **Kötelezettségek paraméterei** oldalon.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
