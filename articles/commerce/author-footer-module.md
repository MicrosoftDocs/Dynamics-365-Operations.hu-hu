---
title: Láblécmodul
description: Ez a témakör a láblécmodulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket létrehozni a Dynamics 365 Commerce alkalmazásban.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 038fee32cbf1ed6b4967f440faaf3c0d4fa583f6
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4979947"
---
# <a name="footer-module"></a>Láblécmodul  

[!include [banner](includes/banner.md)]

Ez a témakör a láblécmodulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket létrehozni a Microsoft Dynamics 365 Commerce alkalmazásban.

## <a name="overview"></a>Áttekintés

A láblécmodul egy speciális tároló, amely a láblécben megjelenő modulok tárolására szolgál. Például a webhely különböző lapjaira mutató hivatkozásokat is tartalmazhat, mint például a **Kapcsolat** és **Áruházi szabályzat** lapokra.

A következő kép egy webhelyoldalon használt láblécmodul egy példáját jeleníti meg.

![Példa egy lábléc modulra](./media/ecommerce-footer.PNG)

## <a name="footer-module-properties"></a>Láblécmodul tulajdonságai 

A legtöbb tárolóhoz hasonlóan a láblécmodul a fejlécre és a szélességre vonatkozó tulajdonságokat támogatja. Emellett támogatja több lábléckategória modul hozzáadását is. Minden hozzáadott lábléckategória modul egy oszlopként jelenik meg a láblécmodulban.

## <a name="modules-available-in-a-footer-module"></a>A láblécmodulban elérhető modulok

**Láblécelemek** – Az láblécelemek modul tartalmaz egy fejlécet, egy képet és egy hivatkozást. A fejléc használható akár önmagában, akár egy képpel és hivatkozással együtt. A lábléc minden hivatkozása konfigurálható úgy, hogy csak szöveggel (például „Kapcsolat” és „Adatvédelem” hivatkozások) vagy szöveggel és képpel (például a közösségi média hivatkozások) rendelkezzen.

**Vissza a tetejére** – A vissza a tetejére modul egy hivatkozást biztosít a lap tetejére történő gyors navigáláshoz. Kötelező megadni egy célt. Az alapértelmezett célérték a \#, amely a felhasználó a lap tetejére viszi.

## <a name="create-a-footer-module"></a>Láblécmodul létrehozása

1. Lépjen a **Töredékek** pontra, és válassza az **Új** lehetőséget új töredék létrehozásához.
1. Az **Új töredék** párbeszédpanelen válassza ki a **Tároló** modult, adja meg a töredék nevét, majd kattintson az **OK** gombra.
1. Az **Alapértelmezett tároló** helyben válassza a három pont (**…**) gombot, majd válassza az **Modul hozzáadása** elemet.
1. A **Modul hozzáadása** párbeszédpanelen válassza ki a **Lábléckategória** modult, majd kattintson az **OK** gombra.
1. A **Lábléckategória** helyben válassza a három pont (**…**) gombot, majd válassza a **Modul hozzáadása** elemet.
1. A **Modul hozzáadása** párbeszédpanelen válassza ki a **Láblécelem** modult, majd kattintson az **OK** gombra.
1. Válassza ki a **Láblécelem** helyet, majd a jobb oldali tulajdonságok panelen konfigurálja a fejlécet, a hivatkozást, a hivatkozás szövegét, valamint igény szerint a képet.
1. További láblécelemek hozzáadásához ismételje meg az 5–7. mindegyikhez.
1. Egy „vissza a tetejére” hivatkozás hozzáadásához a lábléchez, válassza ki a három pont gombot (**...**) a **Lábléckategória** hely esetében, majd válassza a **Modul hozzáadása** elemet.
1. A **Modul hozzáadása** párbeszédpanelen válassza ki a **Vissza a tetejére** modult, majd kattintson az **OK** gombra.
1. Válassza ki a **Vissza a tetejére** helyet, majd a jobb oldali tulajdonságok panelen konfigurálja szöveget és más modultulajdonságokat igény szerint.
1. Válassza a **Szerkesztés befejezése** parancsot a töredék ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.

Ha azt szeretné, hogy minden lapon megjelenjen a fejléc, hajtsa végre az alábbi lépéseket a webhelyhez létrehozott összes oldalsablon esetében.

1. Az **Alapértelmezett** lap **Lábléc** helyén a láblécmodulban adja meg a létrehozott lábléctöredéket.
1. Válassza a **Szerkesztés befejezése** parancsot a sablon ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.

Ha hozzáadja a töredéket a lapsablonokhoz, akkor segít biztosítani azt, hogy a lábléc minden oldalon megjeleníthető legyen.

## <a name="additional-resources"></a>További erőforrások

[Modulkönyvtár – áttekintés](starter-kit-overview.md)

[Tárolómodul](add-container-module.md)

[Vásárlásmező-modul](add-buy-box.md)

[Kosármodul](add-cart-module.md)

[Pénztármodul](add-checkout-module.md)

[Rendelésmegerősítési modul](order-confirmation-module.md)

[Fejlécmodul](author-header-module.md)

[Láblécmodul](author-footer-module.md)
