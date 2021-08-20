---
title: A B2B e-commerce webhelyekhez használt vevői számlafizetési mód konfigurálása
description: Ez a témakör azt ismerteti, hogyan kell konfigurálni a B2B e-commerce webhelyekhez használt vevői számlafizetési módot.
author: josaw1
ms.date: 01/20/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailOperations
audience: Application User, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: josaw
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 628f3b3b2d86154190dfdcc82b8b391c2facce103f607519514c65b5fba26653
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6738053"
---
# <a name="configure-the-customer-account-payment-method-for-b2b-e-commerce-sites"></a>A B2B e-commerce webhelyekhez használt vevői számlafizetési mód konfigurálása

[!include [banner](../../includes/banner.md)]

Ez a témakör azt ismerteti, hogyan kell konfigurálni a B2B e-commerce webhelyekhez használt vevői számlafizetési módot.

A kiskereskedők különböző típusú kifizetéseket fogadhatnak el e-kereskedelmi csatornán értékesített termékeikért és szolgáltatásaikért. Minden egyes fizetéstípust, amelyet egy kiskereskedő elfogad, konfigurálni kell a Microsoft Dynamics 365 Commerce rendszer beállításakor. A vevői számla (vagy részszámlázás) fizetési módnak támogatottnak kell lennie a B2B e-kereskedelmi webhelyeken. 

## <a name="prerequisites"></a>Előfeltételek

1. Adja hozzá a vevői számlafizetési módot a Commerce központi felületéhez.
2. Társítsa a vevői számlafizetési módot egy e-kereskedelmi csatornához.
3. Győződjön meg róla, hogy a **Részszámlázás engedélyezése** aktív a vevő számára a **Kiskereskedelem és kereskedelem \> Vevők \> Összes vevő \> Fizetés alapértelmezései** pontban a Commerce központi felületén. Győződjön meg arról is, hogy a **Hitelkeret** paraméterei megfelelően legyenek beállítva a vevőhöz a **Kiskereskedelem és kereskedelem \> Vevők \> Összes vevő \> Követelések és beszedések** pontban a Commerce központi felületén. 

## <a name="enable-the-customer-account-payment-method-in-commerce-site-builder"></a>A vevői számlafizetési mód engedélyezése a Commerce webhelykészítőben 

A vevői számlafizetési mód Commerce webhelykészítőben való engedélyezéséhez kövesse az alábbi lépéseket.

1. Lépjen a **Webhelybeállítások \> Bővítmények** pontra.
1. Állítsa a **Vevői számlafizetések engedélyezése** tulajdonságot **Engedélyezve B2B vevők esetében** értékre. 
1. Válassza a **Mentés és közzététel** lehetőséget.

> [!NOTE]
> Az új webhelybeállítások csak az app.settings.json fájl frissítése után lépnek hatályba. A további tudnivalókat lásd itt: [SDK- és modultár-frissítések](../e-commerce-extensibility/sdk-updates.md).

## <a name="enable-the-customer-account-payment-method-on-the-checkout-page-for-the-b2b-e-commerce-site"></a>A vevői számlás fizetési mód engedélyezése a B2B e-kereskedelmi webhely pénztároldalán

A vevői számlás fizetési mód B2B e-kereskedelmi webhely pénztároldalán való engedélyezéséhez kövesse az alábbi lépéseket.

1. A Commerce webhelykészítőben keresse meg és szerkessze a B2B e-kereskedelmi webhely pénztármodulját tartalmazó pénztároldalt vagy töredéket.
1. A **Fizetési szakasz tárolója** helyen válassza a **Modul hozzáadása** lehetőséget, majd adjon hozzá egy **Vevői számlafizetés** modult.
1. A **Vevői számlafizetés** modult úgy pozicionálja, hogy kijelöli a három pontot (**...**), majd a **Felfelé** vagy a **Lefelé** nyíl kiválasztásával állítsa be a pozíciót.
1. Válassza a **Mentés** elemet, válassza a **Szerkesztés befejezése** parancsot az oldal ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.

## <a name="confirm-that-the-customer-account-payment-method-has-been-enabled-and-published"></a>A vevői számlafizetési mód engedélyezésének és közzétételének megerősítése

A vevői számlafizetési mód engedélyezésének megerősítéséhez kövesse az alábbi lépéseket.

1. Jelentkezzen be az e-kereskedelmi webhelyre.
1. Adjon hozzá egy terméket a kosárhoz.
1. Lépjen a pénztároldalra. Itt látnia kell az új **Vevői számla** fizetési módot.

## <a name="additional-resources"></a>További erőforrások

[B2B e-kereskedelmi webhely beállítása](set-up-b2b-site.md)

[Szervezeti modellezési hierarchiák létrehozása B2B szervezetek számára](org-model.md)

[Üzleti partner típusú felhasználók kezelése a B2B e-kereskedelmi webhelyeken](manage-b2b-users.md)

[Termékmennyiség-korlátok beállítása B2B e-kereskedelmi webhelyekhez](quantity-limits.md)

[SDK- és modulkönyvtár-frissítések](../e-commerce-extensibility/sdk-updates.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]