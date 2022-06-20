---
title: A vállalatközi értékesítési ügyfélszámlák kifizetéseinek automatikus regisztrációja
description: Ez a cikk bemutatja, hogyan lehet automatikusan regisztrálni a kifizetéseket a vállalatközi vevői számlákhoz.
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
ms.openlocfilehash: 4e8f784cd310026f0a647a0f509999e11ab26ce5
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8878787"
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
