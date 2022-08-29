---
title: Láblécmodul
description: Ez a cikk a láblécmodulokat és a láblécmodulok szerzőjeként való bemutatja Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 05/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: fefeed37ba0d0e800b9cd3cefcf207cde9a625d8
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9282957"
---
# <a name="footer-module"></a>Láblécmodul  

[!include [banner](includes/banner.md)]

Ez a témakör a láblécmodulokat tartalmazza, és bemutatja, hogyan lehet létrehozni őket Microsoft Dynamics 365 Commerce.

A láblécmodul egy speciális tároló, amely a láblécben megjelenő modulok tárolására szolgál. Például a webhely különböző lapjaira mutató hivatkozásokat is tartalmazhat, mint például a **Kapcsolat** és **Áruházi szabályzat** lapokra.

A következő kép egy webhelyoldalon használt láblécmodul egy példáját jeleníti meg.

![Példa egy láblécmodulra.](./media/ecommerce-footer.PNG)

## <a name="footer-module-properties"></a>Láblécmodul tulajdonságai 

A legtöbb tárolóhoz hasonlóan a láblécmodul a fejlécre és a szélességre vonatkozó tulajdonságokat támogatja. Emellett támogatja több lábléckategória modul hozzáadását is. Minden hozzáadott lábléckategória modul egy oszlopként jelenik meg a láblécmodulban.

## <a name="modules-available-in-a-footer-module"></a>A láblécmodulban elérhető modulok

**Lábléccikk** – a láblécelem-modul fejlécet vagy hivatkozást tartalmazhat. A fejléc általában láblécszakasz címeként használatos.  A lábléc minden hivatkozása konfigurálható úgy, hogy csak szöveggel (például „Kapcsolat” és „Adatvédelem” hivatkozások) vagy szöveggel és képpel (például a közösségi média hivatkozások) rendelkezzen. Ha mind fejléc, mind hivatkozás meg van téve, akkor a fejléc tulajdonság elsőbbséget élvez a hivatkozással képest. 

**Vissza a tetejére** – A vissza a tetejére modul egy hivatkozást biztosít a lap tetejére történő gyors navigáláshoz. Kötelező megadni egy célt. Az alapértelmezett célérték a \#, amely a felhasználó a lap tetejére viszi.

## <a name="create-a-footer-module"></a>Láblécmodul létrehozása

1. Lépjen a **Töredékek** pontra, és válassza az **Új** lehetőséget új töredék létrehozásához.
1. A Részlet **kiválasztása párbeszédpanelen** válassza ki a Tároló modult, **adjon** nevet a részletnek, majd válassza **az OK gombra**.
1. Az Alapértelmezett tároló-ponthelyen **válassza** ki a három pontból (**...**), majd válassza a **Modul hozzáadása lehetőséget**.
1. A Modulok **kiválasztása párbeszédpanelen** válassza ki **a Lábléckategória** modult, majd válassza az **OK gombra.**
1. A Lábléc **kategóriabefejlécben** válassza ki a három pontból (**...**), majd válassza a **Modul hozzáadása lehetőséget**.
1. A Modulok **kiválasztása párbeszédpanelen** válassza ki a Lábléc **cikkmodult**, majd válassza az **OK elemet**.
1. Válassza ki a **Láblécelem** helyet, majd a jobb oldali tulajdonságok panelen konfigurálja a fejlécet, a hivatkozást, a hivatkozás szövegét, valamint igény szerint a képet.
1. További láblécelemek hozzáadásához ismételje meg az 5–7. mindegyikhez.
1. Ha a lábléchez egy "Vissza a lap tetejére" hivatkozást szeretne hozzáadni, **·** **válassza** ki a lábléckategória-pont három pontját, majd **válassza a Modul hozzáadása lehetőséget.**
1. A Modulok **kiválasztása párbeszédpanelen** válassza a **Vissza a felső** modult, majd kattintson az **OK gombra**.
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


[!INCLUDE[footer-include](../includes/footer-banner.md)]
