---
title: Vevői számlák és visszárukra vonatkozó értékesítési rendelések a kelet-európai országokban
description: Ez a cikk azt ismerteti, hogyan lehet beállítani a vevői számlákra és a visszárurendelésre vonatkozó információkat a közép-kelet-európai országok számára.
author: EvgenyPopovMBS
ms.date: 10/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.search.region: Czech Republic, Estonia, Hungary, Latvia, Lithuania, Poland, Russia
ms.author: josaw
ms.search.validFrom: 2018-10-31
ms.dyn365.ops.version: 8.0999999999999996
ms.search.industry: Retail
ms.openlocfilehash: 6ebf3740b9ae93cecd5592a5564574e7f49ab5b4
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9286547"
---
# <a name="customer-invoices-and-return-sales-orders-in-eastern-european-countries"></a>Vevői számlák és visszárukra vonatkozó értékesítési rendelések a kelet-európai országokban


[!include [banner](../../includes/banner.md)]

Ez a cikk azt ismerteti, hogyan lehet beállítani a vevői számlákra és a visszárurendelésre vonatkozó információkat a közép-kelet-európai országok számára.

Az alábbi információkat állíthatja be a Retail POS rendszerben generált vevői számlákhoz és a visszáru típusú értékesítési rendelésekhez:

- Áfacsoportok használhatók a visszaküldések értékesítési visszárurendelésekkel való feldolgozásában. Menjen a **Kiskereskedelem és kereskedelem \> Központ beállítása \> Paraméterek \> Kiskereskedelmi paraméterek** lehetőségre. Nyissa meg a **Feladás \> Számla** lapot, és ezután állítsa a **Visszáruk áfacsoportjának használata** lehetőséget **Igen** beállításra.

    * A vevői által a kiskereskedelmi értékesítési helyen visszaadott visszáruhoz tartozó áfacsoport megadásához az **Ügyfelek** lap **Kereskedelem** gyorslapján a **Visszáruk áfacsoportja** mezőben, válasszon ki egy áfacsoportot. Egy vevői visszárurendelés feladásakor a visszárurendelés sorában frissül a visszáruhoz az **Ügyfelek** képernyőn megadott áfacsoport.
    * A vevői által a Retail POS helyen visszaadott visszáruhoz tartozó áfacsoport megadásához az **Üzletek** lap **Általános** gyorslapján a **Visszáruk áfacsoportja** mezőben, válasszon ki egy áfacsoportot. Egy bolt vevői visszárurendelésének feladásakor a visszárurendelés sorában frissül a visszáruhoz az **Üzletek** lapon megadott áfacsoport.

- Ha egy vevői számlának vagy visszáru típusú értékesítési rendelésnek nincs alapértelmezett értékesítési dátuma, akkor a számla vagy a visszáru feladási dátumát használhatja értékesítési dátumként. Menjen a **Kiskereskedelem és kereskedelem \> Központ beállítása \> Paraméterek \> Kiskereskedelmi paraméterek** lehetőségre. Nyissa meg a **Feladás \> Számla** lapot, és ezután állítsa **A feladási dátum használata értékesítési dátumként lehetőséget** **Igen** beállításra.
- Lett és litván vevői számlák és visszáru típusú értékesítési rendelések számozásához az adóhatóságtól kapott számtartományt használhatja.

    * Ugrás a **Szervezeti adminisztráció \> Számsorozatok \> Számlálókezelés elemre**. Rekordnak kell lennie ahol **Modul** = **Értékesítés** és **Típus** = **Számla**.
    * Ugrás a **Szervezeti adminisztráció \> Számsorozatok \> Számlaszámozás beállítása elemre**. Jelölje be a **Kereskedelem** jelölőmezőt annál a számsorozatnál, amellyel a vevői számlákat számozza.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
