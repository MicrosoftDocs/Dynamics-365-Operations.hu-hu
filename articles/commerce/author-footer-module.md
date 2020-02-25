---
title: Láblécmodul
description: Ez a témakör a láblécmodulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket létrehozni a Dynamics 365 Commerce alkalmazásban.
author: anupamar
manager: annbe
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar-ms
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: f8e0290b5af9d0c1fc9ad0279b0d7f81c9feb2fc
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/01/2020
ms.locfileid: "3001150"
---
# <a name="footer-module"></a>Láblécmodul  


[!include [banner](includes/banner.md)]

Ez a témakör a láblécmodulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket létrehozni a Microsoft Dynamics 365 Commerce alkalmazásban.

## <a name="overview"></a>Áttekintés

A láblécmodul egy speciális tároló, amely a láblécben megjelenő modulok tárolására szolgál. Például a webhely különböző lapjaira mutató hivatkozásokat is tartalmazhat, mint például a **Kapcsolat** és **Áruházi szabályzat** lapokra.

## <a name="footer-module-properties"></a>Láblécmodul tulajdonságai 

A legtöbb tárolóhoz hasonlóan a láblécmodul a fejlécre és a szélességre vonatkozó tulajdonságokat támogatja. Emellett támogatja több lábléckategória modul hozzáadását is. Minden hozzáadott lábléckategória modul egy oszlopként jelenik meg a láblécmodulban.

## <a name="modules-available-in-a-footer-module"></a>A láblécmodulban elérhető modulok

**Láblécelemek** – Az láblécelemek modul tartalmaz egy fejlécet, egy képet és egy hivatkozást. A fejléc használható akár önmagában, akár egy képpel és hivatkozással együtt. A lábléc minden hivatkozása konfigurálható úgy, hogy csak szöveggel (például „Kapcsolat” és „Adatvédelem” hivatkozások) vagy szöveggel és képpel (például a közösségi média hivatkozások) rendelkezzen.

**Vissza a tetejére** – A vissza a tetejére modul egy hivatkozást biztosít a lap tetejére történő gyors navigáláshoz. Kötelező megadni egy célt. Az alapértelmezett célérték a #, amely a felhasználó a lap tetejére viszi.

## <a name="author-a-footer-module"></a>Láblécmodul létrehozása

1. Válassza a navigációs ablak **Töredékek** elemét, majd válassza ki az **Új lap töredék** elemet.
1. Az **Új lap töredék** párbeszédpanelen jelölje ki a láblécmodult, adja meg a laptöredék nevét, majd kattintson az **OK** gombra.
1. A bal oldali fastruktúrában válassza ki a három pont gombot (**...**) a láblécmodul esetében, majd válassza a **Modul hozzáadása** elemet.
1. A **Modul hozzáadása** párbeszédpanelen válassza ki a lábléckategória modult, majd kattintson az **OK** gombra.
1. A bal oldali fastruktúrában válassza ki a három pont gombot a lábléckategória modul esetében, majd válassza a **Modul hozzáadása** elemet.
1. A **Modul hozzáadása** párbeszédpanelen válassza ki a láblécelem modult, majd kattintson az **OK** gombra.
1. A bal oldali fastruktúrában válassza ki a láblécelem modult. Ezután a jobb oldali tulajdonságok panelen konfigurálja a fejlécet, a hivatkozást, a hivatkozás szövegét, valamint igény szerint a képet.
1. További láblécelemek hozzáadásához ismételje meg az 5–7. lépéseket.
1. Egy „vissza a tetejére” hivatkozás hozzáadásához a lábléchez, válassza ki a három pont gombot a lábléckategória modul esetében, majd válassza a **Modul hozzáadása** elemet.
1. A **Modul hozzáadása** párbeszédpanelen válassza ki a vissza a tetejére modult, majd kattintson az **OK** gombra.
1. A bal oldali fastruktúrában válassza ki a vissza a tetejére modult. Ezután jobb oldali tulajdonságok panelen konfigurálja a vissza a tetejére modult az igényeinek megfelelően.
1. Mentse az oldaltöredéket, adja be és tegye közzé.

Hajtsa végre a következő lépéseket a webhelyhez létrehozott összes oldalsablon esetében.

1. Az alapértelmezett lap **Fő** helyén a láblécmodulban adja meg a létrehozott lábléctöredéket.
1. Mentse a sablont, adja be és tegye közzé.

Ha hozzáadja a laptöredéket a lapsablonokhoz, akkor segít biztosítani azt, hogy a lábléc minden oldalon megjeleníthető legyen.

## <a name="additional-resources"></a>További erőforrások

[Kezdő csomag áttekintése](starter-kit-overview.md)

[Tárolómodul](add-container-module.md)

[Vásárlásmező-modul](add-buy-box.md)

[Kosármodul](add-cart-module.md)

[Fizetésmodul](add-checkout-module.md)

[Rendelésmegerősítési modul](order-confirmation-module.md)

[Fejlécmodul](author-header-module.md)

[Láblécmodul](author-footer-module.md)
