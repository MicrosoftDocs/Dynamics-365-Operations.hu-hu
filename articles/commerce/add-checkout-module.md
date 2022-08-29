---
title: Pénztármodul
description: Ez a témakör azt ismerteti, hogyan lehet egy pénztármodult hozzáadni egy laphoz, és beállítani a szükséges tulajdonságokat.
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
ms.openlocfilehash: b6f3aef08f723eff8b172db2ca5c355121e93bdc
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9280474"
---
# <a name="checkout-module"></a>Pénztármodul

[!include [banner](includes/banner.md)]

Ez a témakör azt ismerteti, hogyan lehet egy pénztármodult hozzáadni egy laphoz, és beállítani a szükséges tulajdonságokat.

A fizetésmodul egy speciális tároló, amely a rendelés létrehozásához szükséges összes modult tárolja. Lépésről lépésre bemutatja a folyamatot, amely során a vevő megadja a vásárláshoz szükséges összes információt. A szállítási cím, a szállítási mód és a számlázási adatok rögzítése történik. Ezenkívül a rendelés összesítését és a vevői rendeléshez kapcsolódó egyéb információkat is tartalmaz.

A fizetésmodul a kosár azonosítója alapján jeleníti meg az adatokat. Ezt a kosárazonosítót a rendszer böngésző-cookie-ként menti. Egy kosárazonosító szükséges a fizetésmodul adatainak megjelenítéséhez, például a rendelésben szereplő cikkekhez, a teljes összeghez és az engedményekhez. 

A következő kép egy Pénztár oldalon használt Fabrikam pénztár modul egy példáját jeleníti meg.

![Példa egy pénztármodulra.](./media/Checkout.PNG)

## <a name="checkout-module-properties"></a>Fizetésmodul tulajdonságai

A fizetési modul a rendelés összesítését jeleníti meg, és biztosítja a rendelés elküldésére szolgáló funkciókat. A rendelés elküldése előtt szükséges összes ügyféladat összegyűjtéséhez további modulokat kell a fizetési modulhoz adni. Ezért a kiskereskedők rugalmasan hozzáadhatnak egyéni modulokat a fizetési folyamathoz, vagy szükség szerint kizárhatnak modulokat.

| Tulajdonság neve | Értékek | Leírás |
|----------------|--------|-------------|
| Pénztár címsora | A fejléc szövege és a fejléc címkéje (**H1**, **H2**, **H3**, **H4**, **H5** vagy **H6**) | A fizetésmodul címsora. |
| Rendelés összegzésének címsora | A címsor szövege | A modul rendelésösszesítési szakaszának címsora. |
| A kosár sortételeinek címsora | A címsor szövege | A kosár azon sortételeinek címsora, melyek a fizetésmodulon kerülnek megjelenítésre. |
| Szállítási költségek megjelenítése a sortételeken | **Igaz** vagy **Hamis** | Ha ez a tulajdonság **Igaz** értékre van állítva, a szállítási költségek, melyek a sortételekre vonatkoznak, megjelenítésre kerülnek a bevásárlókocsi soraiban. Ha a **Fejlécköltség arányosítás nélkül** funkció be van kapcsolva, a Commerce kezelési központban, a szállítási költség a fejléc szintjén kerül hozzáadásra, nem a sor szintjén. Ez a funkció a Commerce 10.0.13-as verziójában került hozzáadásra. |

## <a name="modules-that-can-be-used-in-the-checkout-module"></a>A fizetésmodulban használható modulok

- **Szállítási cím** – Ez a modul lehetővé teszi a vevő számára, hogy megadja vagy kiválassza a rendelés szállítási címét. A modullal kapcsolatos további tudnivalókért lásd: [Szállítási cím modul](ship-address-module.md).

    A következő kép egy Pénztár oldalon használt szállítási cím modul egy példáját jeleníti meg.

    ![Példa a szállítási cím modulra.](./media/ecommerce-shippingaddress.PNG)

- **Szállítási lehetőségek** – Ez a modul lehetővé teszi a vevő számára, hogy kiválasszon egy szállítási módot rendeléséhez. A modullal kapcsolatos további tudnivalókért lásd: [Szállítási lehetőségek modul](delivery-options-module.md).

    A következő kép egy Pénztár oldalon használt szállítási lehetőségek modul egy példáját jeleníti meg.
 
    ![Példa a szállítási lehetőségek modulra.](./media/ecommerce-deliveryoptions.PNG)

- **Fizetési szakasz tárolója** – Ez a modul egy olyan tároló, amelyben több modult is elhelyezhet egy szakasz létrehozásához a fizetési folyamaton belül. Például az összes fizetéshez kapcsolódó modult elhelyezheti ebben a tárolóban, hogy egy szakaszként jelenjenek meg. Ez a modul csak a folyamat elrendezését érinti.

- **Ajándékutalvány** – Ez a modul lehetővé teszi a vevők számára, hogy egy ajándékutalvány segítségével fizessenek egy rendelést. A modullal kapcsolatos további tudnivalókért lásd: [Ajándékutalvány modul](add-giftcard.md).

- **Hűségpontok** – Ez a modul lehetővé teszi, hogy a vevő a hűségpontok felhasználásával fizessen egy rendelést. A rendelkezésre álló pontok és lejáró pontok összesítését biztosítja, és lehetővé teszi a vevő számára, hogy kiválassza a beváltani kívánt pontok számát. Ha a vevő nincs bejelentkezve vagy nem tagja a hűségprogramnak, illetve a kosár teljes összege 0 (nulla), akkor a rendszer automatikusan elrejti ezt a modult.

- **Fizetés** – Ez a modul lehetővé teszi a vevő számára, hogy rendelését hitelkártyával fizethesse. A vevők számlázási címet is megadhatnak az általuk kiválasztott fizetési lehetőséghez. A modullal kapcsolatos további tudnivalókért lásd: [Fizetési modul](payment-module.md).

    A következő képen egy példa látható az ajándékutalványra, a hűségpontokra és a fizetési modulokra a fizetési oldalon.

    ![Példa az ajándékutalvány, a hűségpontok és a fizetési modulokra a fizetési oldalon.](./media/ecommerce-payments.PNG)

- **Kapcsolattartási adatok** – Ez a modul lehetővé teszi a vevő számára, hogy megadja vagy módosítsa a rendeléshez tartozó kapcsolattartási adatokat (e-mail-cím).

- **Szövegblokk** – Ez a modul minden olyan üzenetküldést tartalmaz, amelyet a tartalomkezelő rendszer (CMS) vezérel. Például tartalmazhatja a következő üzenetet: „A rendeléssel kapcsolatos problémák esetén hívja az 1-800-Fabrikam számot”. 

- **Fizetési feltételek és kikötések** – Ez a modul egy Rich Text szöveget jelenít meg, amely feltételeket és kikötéseket tartalmaz, valamint egy jelölőnégyzetet a vevői inputra vonatkozóan. A jelölőnégyzet szabadon választható és konfigurálható. A bevitel rögzítésre kerül a modul által és afféle csekként használható, mielőtt a rendelés leadásra kerül,ellenben ez nem kerül rögzítésre az rendelés összegzési információkban. Ez a modul a pénztár tárolójához, a fizetési szakasz tárolójához vagy egy feltételek és kikötések helyhez adható, üzleti igényeitől függően. Ha ez a pénztár tárolójához vagy a fizetési szakasz tárolójának helyéhez van rendelve, meg fog jelenni a fizetési folyamat egy lépéseként. Ha ez egy feltételek és kikötések helyhez van rendelve, akkor meg fog jelenni a rendelés leadása gomb közelében.

    A következő képen egy példa látható szerződési feltételekről egy fizetési oldalon.

    ![Példa szerződési feltételekre egy fizetési oldalon.](./media/ecommerce-checkout-terms.PNG)

## <a name="commerce-scale-unit-interaction"></a>Commerce Scale Unit-interakció

A legtöbb fizetési információt (például a szállítási címet és a szállítási módot) a kosár tárolja, és a rendelés részeként kerül feldolgozásra. Az egyetlen kivételt a hitelkártyával kapcsolatos adatok jelentik. Ezeket az adatokat a rendszer közvetlenül az Adyen fizetési összekötő használatával dolgozza fel. A kifizetés engedélyezve van, de a rendelés teljesítése előtt nem kerül sor.

## <a name="add-a-checkout-module-to-a-page-and-set-the-required-properties"></a>Fizetésmodul hozzáadása egy új oldalhoz és a kötelező tulajdonságok beállítása

A fizetésmodul új oldalra való felvételéhez és a kötelező tulajdonságok beállításához hajtsa végre az alábbi lépéseket.

1. Lépjen a **Töredékek** pontra, és válassza az **Új** lehetőséget új töredék létrehozásához.
1. A Részlet kiválasztása párbeszédpanelen **válassza ki a** Pénztár modult **.**
1. A **Töredék neve** pontban adja meg a **Fizetési töredék** nevet, majd válassza az **OK** lehetőséget.
1. Válassza ki a **Pénztár modul** helyet.
1. A jobb oldali tulajdonságok ablaktáblán válassza ki a ceruza szimbólumot, adja meg a címsor szövegét a mezőben, majd jelölje be a pipa jelet.
1. A Pénztár adatai **pontnál** válassza ki a három pontból (**...**), majd válassza a **Modul hozzáadása lehetőséget**.
1. A Modulok **kiválasztása párbeszédpanelen** válassza ki a Szállítási **cím,** **a** Szállítási beállítások, a **Pénztár szakasz** tárolóját és **a** Kapcsolattartási adatok modulokat, **majd válassza az OK gombra.**
1. A Pénztár **szakasz tárolómodulban** válassza ki a három pontból (**...**), majd válassza a **Modul hozzáadása lehetőséget**.
1. A Modulok kiválasztása párbeszédpanelen válassza ki az Ajándékutalvány, **·** **·** **a** Hűség és a Fizetés modult, majd kattintson **az OK gombra.** **·** Így biztosíthatja, hogy az összes fizetési mód együtt jelenjen meg egy szakaszban.
1. A **Feltételek és kikötések** helyen adja meg a **Fizetési feltételek és kikötések** modult, ha ez szükséges. A modul tulajdonságai ablakban adja meg a szerkessze meg a feltételek és kikötések szövegét szükséges esetben.
1. Válassza a **Mentés** lehetőséget, majd a töredék előnézetének megtekintéséhez az **Előnézet** elemet. Előfordulhat, hogy egyes modulok nem jelennek meg az előnézetben, mert nem rendelkeznek kosárkontextussal.
1. Válassza a **Szerkesztés befejezése** parancsot a töredék ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.
1. Hozzon létre egy olyan sablont, amely az új fizetési töredéket használja.
1. Hozzon létre egy olyan fizetési oldalt, amely az új sablont használja.

## <a name="additional-resources"></a>További erőforrások

[Kosármodul](add-cart-module.md)

[Kosárikon modul](cart-icon-module.md)

[Fizetési modul](payment-module.md)

[Szállítási cím modul](ship-address-module.md)

[Szállítási lehetőségek modul](delivery-options-module.md)

[Átvételi információk modul](pickup-info-module.md)

[Rendelési részletek modul](order-confirmation-module.md)

[Ajándékutalvány modul](add-giftcard.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
