---
title: Beszerzésikategória-hierarchiák irányelveinek beállítása
description: A következő lépésekkel egy kategóriába tartozó termékek megrendelésére vonatkozóan állíthat be szabályokat.
author: GalynaFedorova
ms.date: 07/22/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SysPolicyListPage, SysPolicy, ProcCategoryAccessPolicyRule, ProcCategoryPolicyRule, EcoResCategorySingleLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: gfedorova
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c2a8248374f34e0937aa569259c5925506857ddd
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/03/2022
ms.locfileid: "8675907"
---
# <a name="set-up-policies-for-procurement-category-hierarchies"></a>Beszerzésikategória-hierarchiák irányelveinek beállítása

[!include [banner](../../includes/banner.md)]

A következő lépésekkel egy kategóriába tartozó termékek megrendelésére vonatkozóan állíthat be szabályokat. Egy adott beszerzési irányelvhez határozunk meg szabályokat. A kategória-hozzáférési szabály meghatározza, hogy az alkalmazottaknak igénylések létrehozásakor mely beszerzési kategóriákhoz van hozzáférésük. Igénylés létrehozásakor a rendszer az alkalmazotthoz tartozó jogi személy és üzemi egység alapján határozza meg, hogy melyik beszerzési irányelvet és kategória-hozzáférési szabályt kell alkalmazni. Az USMF bemutatócég adataiban használhatja ezt az eljárást. Ezt a feladatot általában egy beszerzési vezető végezné el.


## <a name="find-the-procurement-policy"></a>Beszerzési irányelv keresése
1. A Navigációs ablaktáblán ugorjon a **Modulok > Beszerzés és forrás> Beállítás > Irányelvek > Beszerzési irányelvek**.
2. Kattintson az itt lévő hivatkozásra: „Beszerzési irányelv USMF” irányelv. Ez az az irányelv, amelyet hozzárendel a szabályhoz. Aktív irányelvnek kell lennie.  

## <a name="create-a-category-access-rule"></a>Kategória-hozzáférési szabály létrehozása
1. Bontsa ki az **Irányelvszabályok** gyorslapot.
2. Az **Irányelvszabály típusa** listán válassza ki a **Kategóriához való hozzáférés irányelvszabálya** lehetőséget. Ha az **Irányelvszabály létrehozása** gomb halványított, akkor a Kategóriához való hozzáféréshez már tartozik egy aktív irányelvszabály. Az **Érvényesség** és **Lejárat** mezők segítségével állapítsa meg, hogy melyik az, majd jelölje ki és kattintson az **Irányelvszabály hatályon kívül helyezése** gombra. Ha az **Irányelvszabály létrehozása** gomb elérhető, nincs teendője.  
3. Kattintson az **Irányelvszabályra** elemre.
4. Az **Érvényesség dátuma** mezőben adjon meg egy dátumot és időpontot. Az idő nem eshet egybe egy már aktív szabállyal.  
5. Válassza ki azt a kategóriát, amelyre a szabályt alkalmazni kívánja. Jegyezze fel, hogy melyik kategóriáról van szó – később szüksége lesz rá. Amikor kiválaszt egy kategóriát, annak szülőkategóriája vagy szülőkategóriái is hozzá fog(nak) adódni a Kiválasztott kategóriák listához. Amennyiben alkalmazni kívánja a szabályt a kijelölt kategória összes alkategóriájára, jelölje be az **Alkategóriákkal** lehetőséget.
6. A **Kiválasztott kategóriák** listához való hozzáadáshoz kattintson a jobbra nyílra.  
4. Kattintson az **OK** gombra. Ha az Igen lehetőségre állítja a **Fölérendelt szabállyal együtt** opciót, a szülőkategóriához meghatározott irányelvszabály az alárendelt kategóriákra is érvényes lesz, amennyiben azokhoz nincs megadva külön irányelvszabály.

## <a name="create-a-category-policy-rule"></a>Kategória-irányelvszabály létrehozása
1. Az **Irányelvszabály típusa** listán válassza ki a **Kategória irányelvszabálya** lehetőséget. Ha az **Irányelvszabály létrehozása** gomb halványított, válassza ki az aktív irányelvszabályt, majd kattintson az **Irányelvszabály hatályon kívül helyezése** gombra.  
2. Kattintson az **Irányelvszabályra** elemre.
3. Az **Érvényesség dátuma** mezőben adjon meg egy dátumot és időpontot.
4. Kattintson a **Hozzáadás** parancsra.
5. A **Kategória** mezőben válassza ki ugyanazt a kategóriát, amelyet a **Kategóriához való hozzáférési szabály** elemhez használt.
6. Válasszon ki egy lehetőséget a **Szállító kiválasztása** mezőben. Válasszon ki egy szabályt a kiválasztható szállítók típusának ellenőrzéséhez az igénylések létrehozásakor.  
7. Kattintson a **Bezárás** gombra. Az így definiált irányelvszabályok Felhasználás típusú igénylésekre érvényesek. Ha a Feltöltés típusú igénylések irányelveit kívánja meghatározni, „Feltöltési kategória hozzáférési irányelvszabálya” típusú irányelvszabályt kell létrehoznia.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]