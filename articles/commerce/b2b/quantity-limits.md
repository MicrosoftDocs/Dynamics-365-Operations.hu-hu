---
title: Termékmennyiség-korlátok beállítása B2B e-kereskedelmi webhelyekhez
description: Ez a témakör azt ismerteti, hogyan állíthat be termékmennyiség-korlátokat a vállalkozások közötti (B2B) e-kereskedelmi webhelyekhez.
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
ms.openlocfilehash: 18dc138693dc9fb0e8cf8727de77b5f8584cde79
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/04/2022
ms.locfileid: "8690196"
---
# <a name="set-product-quantity-limits-for-b2b-e-commerce-sites"></a>Termékmennyiség-korlátok beállítása B2B e-kereskedelmi webhelyekhez

[!include [banner](../../includes/banner.md)]

Ez a témakör azt ismerteti, hogyan állíthat be termékmennyiség-korlátokat a vállalkozások közötti (B2B) e-kereskedelmi webhelyekhez.

A legtöbb terméknek van egy mértékegysége, amely meghatározza a csoportosításukat. A csoportosítás befolyásolja a termékek értékesítésének módját. Egyes termékek további, mennyiségi csoportosítást tartalmazhatnak. Ez a csoportosítás határozza meg, hogy a termékek egyedi egységként vagy többszörösként értékesíthetők-e, és hogy van-e minimális vagy maximális rendelési mennyiségi korlát, amelyet be kell tartani.

A mennyiségkorlátozó szolgáltatás biztosítja, hogy a Microsoft Dynamics 365 Commerce rendszerben (az alapértelmezett rendelési beállításokban vagy a Commerce webhelykészítő webhelybeállításaiban) konfigurált minimális, maximális, többszörös és szabványos mennyiségeket alkalmazza a rendszer az e-kereskedelmi webhelyeken leadott vevői rendelésekre. A termékmennyiség-korlátok jelenleg nem támogatottak pénztár és a hívásközpontok esetében.

Számos kiskereskedő biztosít lehetőséget vevői rendelésekre (más néven speciális rendelésekre), hogy így elégítsen ki termékkel és teljesítéssel kapcsolatos különböző igényeket. Íme néhány tipikus forgatókönyv:

- Az ügyfél azt szeretné, hogy a meghatározott változatokból álló termékeket kevés többszörösében értékesítsék.
- Egy vevő egy olyan üzetben vagy helyen szeretné átvenni a termékeket, amely eltér attól az üzlettől vagy helytől, ahol az ügyfél megvásárolta az adott termékeket. Az üzletek csomagolási szabványai azonban eltérnek az online forgalmazására vonatkozó csomagolási szabványoktól.
- Az ügyfél limitált kiadású terméket szeretne vásárolni, amely maximális mennyiségkorláttal rendelkezik a megvásárolható cikkekre vonatkozóan.

## <a name="turn-on-the-default-order-settings-feature-in-commerce-headquarters"></a>Az alapértelmezett rendelésbeállítások funkció bekapcsolása a Commerce központi felületén

A termékmennyiség-korlátok beállítása előtt az alapértelmezett rendelésbeállítások funkciót be kell kapcsolni a Commerce központi felületén.

Hajtsa végre az alábbi lépéseket az alapértelmezett rendelésbeállítások bekapcsolásához.

1. Lépjen a **Rendszerfelügyelet \> Munkaterületek \> Funkciókezelés** részre.
1. Keresse meg és válassza ki a **Webhely és az Alapértelmezett rendelésbeállítások támogatása a vevői rendelésben** funkciót.
1. A jobb oldali ablaktábla alján válassza az **Engedélyezés most** lehetőséget. 

## <a name="define-quantity-settings"></a>Mennyiségi beállítások meghatározása 

A mennyiségi beállításokat az **Alapértelmezett rendelésbeállítások** oldalon lehet beállítani.

A mennyiségi beállítások meghatározásához kövesse az alábbi lépéseket. 

1. Nyissa meg a következőt a Termék menüben: **Kiskereskedelem és kereskedelem \> Termékek és kategóriák \> Felszabadított termékek kategóriák szerint**.
1. Válasszon ki egy kiadott terméket.
1. A Művelet ablaktáblán a **Készlet kezelése** lapon a **Rendelés beállításai** csoportban válassza az **Alapértelmezett rendelési beállítások** lehetőséget. 
1. Az **Alapértelmezett rendelésbeállítások** oldal **Értékesítési rendelés** gyorslapjának **Értékesítési mennyiség** pontjában állítsa be a termék értékesítési mennyiségeit:

    - **Többszörös** – az a mennyiség, amellyel a termék többszörsen megvásárolható.
    - **Minimális rendelési mennyiség** – a bevásárláshoz minimálisan szükséges termékek száma.
    - **Maximális rendelési mennyiség** – a bevásárláshoz maximálisan engedélyezett termékek száma.
    - **Szokásos rendelési mennyiség** – a termék kiválasztásakor automatikusan megadott alapértelmezett mennyiség.

## <a name="turn-on-the-b2b-order-quantity-limits-feature-in-commerce-site-builder"></a>Kapcsolja be a B2B rendelési mennyiségi korlátok funkciót a Commerce webhelykészítőben

A B2B rendelési mennyiségi korlátok funkció Commerce webhelykészítőben való bekapcsolásához kövesse az alábbi lépéseket.

1. Lépjen a **Webhelybeállítások \> Bővítmények** pontra
1. A **Rendelési mennyiségi korlátok engedélyezése** pontban a legördülő menüben válassza az **Engedélyezve B2B-vevők esetében** beállítást. 

> [!NOTE] 
> A frissített webhelykészítői beállítások csak az app.settings.json fájl frissítése után lépnek hatályba. A további tudnivalókat lásd itt: [SDK- és modultár-frissítések](../e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).

## <a name="additional-resources"></a>További erőforrások

[B2B e-kereskedelmi webhely beállítása](set-up-b2b-site.md)

[B2B üzleti partnerek kezelése vevőhierarchiák használatával](partners-customer-hierarchies.md)

[Üzleti partner felhasználóinak kezelése a B2B e-kereskedelmi webhelyeken](manage-b2b-users.md)

[A B2B e-commerce webhelyekhez használt vevői számlafizetési mód konfigurálása](payment-method.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
