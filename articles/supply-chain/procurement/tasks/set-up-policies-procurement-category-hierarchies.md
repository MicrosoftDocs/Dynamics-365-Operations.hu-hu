---
title: Beszerzésikategória-hierarchiák irányelveinek beállítása
description: A következő lépésekkel egy kategóriába tartozó termékek megrendelésére vonatkozóan állíthat be szabályokat.
author: mkirknel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysPolicyListPage, SysPolicy, ProcCategoryAccessPolicyRule, ProcCategoryPolicyRule, EcoResCategorySingleLookup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d1fdf357466de12bd0188fc43cd266c67af762c7
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "323157"
---
# <a name="set-up-policies-for-procurement-category-hierarchies"></a>Beszerzésikategória-hierarchiák irányelveinek beállítása

[!include [task guide banner](../../includes/task-guide-banner.md)]

A következő lépésekkel egy kategóriába tartozó termékek megrendelésére vonatkozóan állíthat be szabályokat. Egy adott beszerzési irányelvhez határozunk meg szabályokat. A kategória-hozzáférési szabály meghatározza, hogy az alkalmazottaknak igénylések létrehozásakor mely beszerzési kategóriákhoz van hozzáférésük. Igénylés létrehozásakor a rendszer az alkalmazotthoz tartozó jogi személy és üzemi egység alapján határozza meg, hogy melyik beszerzési irányelvet és kategória-hozzáférési szabályt kell alkalmazni. Az USMF bemutatócég adataiban használhatja ezt az eljárást. Ezt a feladatot általában egy beszerzési vezető végezné el.


## <a name="find-the-procurement-policy"></a>Beszerzési irányelv keresése
1. Navigáljon a következő helyre: Beszerzés és forrás > Beállítás > Irányelvek > Beszerzési irányelvek.
2. Kattintson az itt lévő hivatkozásra: Beszerzési irányelv USMF irányelv.
    * Ez az az irányelv, amelyet hozzárendel a szabályhoz. Aktív irányelvnek kell lennie.  

## <a name="create-a-category-access-rule"></a>Kategória-hozzáférési szabály létrehozása
1. Válassza ki a Kategóriához való hozzáférés irányelvszabályát.
    * Ha az Irányelvszabály létrehozása gomb nem működik (halványítva jelenik meg), akkor a Kategóriához való hozzáféréshez már tartozik egy aktív irányelvszabály. Az Érvényesség dátuma, illetve a Lejárat dátuma mezők segítségével állapítsa meg, hogy melyik az, majd jelölje ki és kattintson az Irányelvszabály kivezetése gombra. Ha rá tud kattintani az Irányelvszabály létrehozása gombra, nincsen teendője.  
2. Kattintson az Irányelvszabályra.
3. Az Érvényesség dátuma mezőben adjon meg egy dátumot és időpontot.
    * Az idő nem eshet egybe egy már aktív szabállyal.  
    * Válassza ki azt a kategóriát, amelyre a szabályt alkalmazni kívánja. Jegyezze fel, hogy melyik kategóriáról van szó – később szüksége lesz rá. Amikor kiválaszt egy kategóriát, annak szülőkategóriája vagy szülőkategóriái is hozzá fog(nak) adódni a Kiválasztott kategóriák listához.  
    * Amennyiben alkalmazni kívánja a szabályt a kijelölt kategória összes alkategóriájára, jelölje be az Alkategóriákkal lehetőséget.  
4. Kattintson a Hozzáadás gombra.
    * Ha az Igen lehetőségre állítja a Fölérendelt szabállyal együtt opciót, a szülőkategóriához meghatározott irányelvszabály az alárendelt kategóriákra is érvényes lesz, amennyiben azokhoz nincs megadva külön irányelvszabály.  
5. Kattintson az OK gombra.

## <a name="create-a-category-policy-rule"></a>Kategória-irányelvszabály létrehozása
1. Válassza ki a Kategória irányelvszabályát.
    * Ha az Irányelvszabály létrehozása gomb nem működik (halványítva jelenik meg), válassza ki az aktív irányelvszabályt, majd kattintson az Irányelvszabály kivezetése gombra.  
2. Kattintson az Irányelvszabályra.
3. Az Érvényesség dátuma mezőben adjon meg egy dátumot és időpontot.
4. Kattintson a Hozzáadás gombra.
5. Válassza ki ugyanazt a kategóriát, mint a Kategóriához való hozzáférési szabály esetén.
6. Válasszon ki egy lehetőséget a Szállító kiválasztása mezőben.
    * Válasszon ki egy szabályt a kiválasztható szállítók típusának ellenőrzéséhez az igénylések létrehozásakor.  
7. Kattintson a Bezárás gombra.
    * Az így definiált irányelvszabályok Felhasználás típusú igénylésekre érvényesek. Ha a Feltöltés típusú igénylések irányelveit kívánja meghatározni, „Feltöltési kategória hozzáférési irányelvszabálya” típusú irányelvszabályt kell létrehoznia.  

