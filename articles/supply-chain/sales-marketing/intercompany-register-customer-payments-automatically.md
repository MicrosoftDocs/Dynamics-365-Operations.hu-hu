---
title: A vállalatközi értékesítési ügyfélszámlák kifizetéseinek automatikus regisztrációja
description: Ez a témakör a vállalatközi értékesítési ügyfélszámlák kifizetéseinek automatikus regisztrációját ismerteti
author: Henrikan
ms.date: 09/01/2021
ms.topic: article
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: dbd06b21d736d1e247cd087e5bb86fbe641352e6
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/03/2022
ms.locfileid: "8669432"
---
# <a name="register-payments-automatically-for-intercompany-customer-invoices"></a>A vállalatközi értékesítési ügyfélszámlák kifizetéseinek automatikus regisztrációja

[!include [banner](../../includes/banner.md)]

A Microsoft Dynamics 365 Supply Chain Management program a vállalatközi ügyfél számlájának feladása esetén létrehoz egy vevői tranzakciót. Ez a vevői tranzakció a kiegyenlítéséig nyitott marad, ami azt jelenti, hogy ki van fizetve. Ha megtörténik a megfelelő vállalatközi beszerzési rendelés számlafrissítése, akkor a program létrehoz egy a vevői tranzakciónak megfelelő szállítói tranzakciót. Ez a szállítói tranzakció is nyitva marad a kiegyenlítésig. Az eltérések kockázatának csökkentése érdekében a kötelezettségek kifizetési naplójának feladása esetén automatikusan létre lehet hozni és fel lehet adni a kinnlevőségek kifizetési naplóját.

1. Lépjen az **Értékesítés és marketing \> Vevők \> Összes vevő** menüpontba.
1. A Műveleti ablaktábla **Általános** lapján válassza a **Vállalatközi** menüpontot.
1. A vállalatközi kinnlevőségek kifizetéseinek az értékesítési rendelések **Vállalatközi** lapján való beállításhoz válassza az **Értékesítési rendelés irányelvei** hivatkozást.
1. A **Kifizetési napló** mezőben válassza ki azt a kinnlevőségek kifizetési naplót, amelybe regisztrálni szeretné a vállalatközi szállítói kifizetéseket. Ezt a **Kinnlevőségek paraméterei** lapon állathatja be.
1. Ha automatikusan szeretne feladni ebbe a naplóba, jelölje be a **Napló automatikus közzététele** mezőt.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
