---
title: Expressz kifizetések konfigurálása a PayPal-hoz
description: Ez a témakör azt ismerteti, hogyan kell konfigurálni az expressz kifizetéseket a PayPal számára a gyorsabb pénztári funkciók engedélyezése érdekében Microsoft Dynamics 365 Commerce.
author: BrianShook
ms.date: 05/11/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: b69b7384992fb86370ff6881824a7d2c9a77d2c4
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8905282"
---
# <a name="configure-express-payments-for-paypal"></a>Expressz kifizetések konfigurálása a PayPal-hoz

[!include [banner](../includes/banner.md)]

Ez a témakör azt ismerteti, hogyan kell konfigurálni az expressz kifizetéseket a PayPal számára a gyorsabb pénztári funkciók engedélyezése érdekében Microsoft Dynamics 365 Commerce.

## <a name="key-terms"></a>Kulcsfogalmak

| Időszak | Leírás |
|---|---|
| PayPalpal | A PayPal csatlakoztató által támogatott felhasználói élmény és integráció. Másik neve PayPal gomb. |
| Pénztárca | Olyan fizetéstípus, amely nem tartalmazza a hagyományos fizetési jellemzőket, például a bank azonosítószám-tartományát és a lejárati dátumot, amely a hitelkártya- és bankkártyatípusok megkülönböztetésére szolgál. |
| Fizetés expressz | Commerce-modul, amely a támogatott fizetési módok használata esetén gyorsabb pénztári működést támogat. Ez a cikk a PayPal fizetési expressz modul használatát tartalmazza. |

Dynamics 365 Commerce A <a0/10/<a2/1><a2/5><a2/–<a3/<a Ha be van állítva a Dynamics 365 Payment Connector for PayPal, a PayPal gomb kiválasztható fizetési módként jelenik meg az online rendelés kifizetése során. Amikor a felhasználók kiválasztják a PayPal-kifizetést, a rendszer őket közvetlenül a PayPal szolgáltatáson keresztül fizeti ki, majd visszaküldi őket az online üzletnek, hogy teljesítse a rendelését. A PayPal bevásárlókocsiba történő fizetésnél a vevők a fizetési számla adatait használják a kifizetési képernyő előzetes kitöltésére, így gyorsabban befejeződhet a kifizetési folyamat.

A Commerce expressz fizetési modult adott hozzá az expressz kifizetések megkönnyítése érdekében. A fizetés expressz modulja egy olyan részletben használható, amely a pénztár vagy a bevásárlókocsi lapján szerepel. Amikor a PayPal be van állítva, ugyanaz a Dynamics 365 Payment Connector for PayPal connector hivatkozás használatos mind a fizetési expressz, mind a rendszeres pénztári beállításhoz.

## <a name="paypal-checkout-in-commerce"></a>PayPal pénztár a Commerce rendszerben

### <a name="prerequisites"></a>Előfeltételek

Állítsa be a PayPal És az Ön környezetét a [Dynamics 365 Payment Connector for PayPal témakörben leírt módon](../paypal.md).

Ha a PayPal-t a rendszeres kifizetési folyamat egyik beállítására használja (ahol a felhasználók manuálisan adhatja meg a számlainformációkat anélkül, hogy a fizetés expressz előzetes kitöltésével kapcsolatos műveleteket használnál), [kövesse a Fizetési modul beállítási utasításait](../payment-module.md).

### <a name="payment-express-module-with-paypal"></a>Fizetés expressz modulja a PayPal használatával

A Fizetés expressz modul támogatja a fizetési módokat, hogy a telephely vevői számára a pénztári folyamat során a fizetési szolgáltatás számlainformációinak előzetes feltöltésével lehetőséget kínál a hely vevőinek a kijelentkezésre. A fizetés expressz modulja a konfigurált fizetési csatlakoztató használatával előzetesen beállítja a kifizetési képernyőt a felhasználói fiók adataival, például a címmel, a kapcsolattartási adatokkal és a kiválasztott fizetési módokkal.

Amikor PayPal expressz kifizetést használ, és a felhasználó a Fizetés expressz szakaszban a PayPal gombot választja, a Fizetésipal fizetési iFrame ablak megnyílik. A felhasználó ezután bejelentkezik a PayPal-számlára, hogy a számlájához szállítási címét, számlázási címét, e-mail címét és a PayPal fizetési módot használja, amely a tranzakció kifizetésének módját válassza.

Miután a felhasználó befejezte a műveletet a PayPal ablakban, a rendszer a Commerce webhely pénztári lapjára irányítja őket, ahol a pénztári képernyőt előre kitöltik a kiválasztott adatokkal. A kifizetés expressz folyamatában a rendszer a visszaküldött szállítási cím első kézbesítési beállítását előre kitölti a felhasználó számára. A felhasználónak ezután lehetősége van **arra**, hogy ellenőrizze a rendelést, és módosítsa a rendelés adatait, mielőtt a Rendelés véglegesít helyére választják.

### <a name="add-the-payment-express-module-with-paypal-to-a-fragment"></a>A PayPal fizetési expressz modul hozzáadása egy részlethez

A PayPal fizetési expressz modulnak a Commerce webhelyszerkesztő egy részletéhez való hozzáadásához kövesse ezeket a lépéseket.

1. Keresse meg a webhelyet.
1. A bal oldali navigációs ablakban válassza a **Részlet**, majd az Új **lehetőséget**.
1. Az Új **részlet párbeszédpanelen** **keresse meg és válassza ki a Fizetés expressz** modult, **majd** a Részletnév alatt adja meg a részlet nevét **(** például Expressz kifizetés).
1. A **részlet létrehozásához kattintson az OK** gombra.
1. A szerkezeti nézetben válassza ki a saját maga által létrehozott fizetési expressz modul hasonmása.
1. Válassza a Tulajdonságok ablak Fejléc **beállítását**.
1. Adja meg **a** **Telephely** expressz pénztár szakaszában (**például** Expressz pénztár) a Fejléc szövegmezőben a Fejléc szövegmezőben azt a címsorszöveget, amely megjelenik.
1. A **Fejléc szintjén** válassza ki a fejlécszintet (például **H2**).
1. Válassza ki az **OK** lehetőséget.
1. Adja meg vagy módosítsa az elem magasságát **iFrame** iFrame a tulajdonságok ablaktáblájában a mező Magasság mezőjében (**például 60).**
1. A Támogatott **fizetési típusok mezőben** adja meg a **PayPal-t**.
1. Válassza a **Mentés** elemet, válassza a **Szerkesztés befejezése** parancsot a töredék ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.

### <a name="add-the-payment-express-fragment-to-the-checkout-page"></a>Fizetési expressz részlet hozzáadása a kifizetési oldalhoz

Ha a fizetés expressz részletét hozzá szeretne adni a helyszerkesztő pénztári oldalára, kövesse ezeket a lépéseket.

1. Keresse meg a webhelyet.
1. A bal oldali navigációs ablakban válassza **az** Oldalak lehetőséget, majd válassza ki a webhely pénztári lapját.
1. A lap **szerkesztéséhez** válassza a Szerkesztés lehetőséget.
1. A fő **pontnál** válassza ki a három pontból (**...**), majd válassza a Modul **hozzáadása lehetőséget**.
1. A Modulok **kiválasztása párbeszédpanelen** válassza ki **a** Tároló modult, majd válassza az **OK gombra.**

    > [!NOTE]
    > Ha már létezik pénztári részletet tartalmazó tárolómodul, úgy helyezze át a fizetési expressz **szakaszt, hogy az megjelenjen a fő pont meglévő pénztári tárolója felett**. A fizetési expressz szakasz ekkor a normál pénztár tároló fölött jelenik meg. A tárolómodul felfelé vagy lefelé való áthelyezéséhez válassza ki a három pontból (**...**), **majd válassza a Felfelé** vagy lefelé **lehetőséget**.

1. A Tárolótulajdonságok **ablakban** a következő módon ajánlott konfigurálni a tulajdonságbeállításokat:

    - **Tárolóelrendezés** – Halmozott **kijelölés kiválasztása**.
    - **Szélesség** – a Kitöltési **tároló kiválasztása**.
    - **Gyermekek mutatva** – háromat **válasszon**.

1. A tárolóhelyen **válassza** ki a három pontból (**...**), majd válassza a Részlet hozzáadása **lehetőséget**.
1. A Részletfizetés **kiválasztása párbeszédpanelen** keresse meg és válassza ki a létrehozott expressz fizetési részletet, majd válassza az **OK gombra.**
1. Válassza a **Mentés** elemet, válassza a **Szerkesztés befejezése** parancsot az oldal ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.

### <a name="add-the-payment-express-fragment-to-the-cart-page"></a>Fizetési expressz részlet hozzáadása a kosároldalhoz

A fizetés expressz részletének a webhelyszerkesztőben történő hozzáadásához hajtsa végre a következő lépéseket.

1. Keresse meg a webhelyet.
1. A bal oldali navigációs ablakban válassza **az** Oldalak lehetőséget, majd válassza ki a webhely bevásárlókocsiját.
1. A lap **szerkesztéséhez** válassza a Szerkesztés lehetőséget.
1. A fő **slotban** keresse meg a Bevásárlókocsi modult tartalmazó **tárolót**. A **Bevásárlókocsi** modul egy Fizetési expressz **rést fog** tartalmazni.
1. Válassza ki **a Payment Express-lehetőséget**, válassza ki a három pontból (**...**), majd válassza a Modul **hozzáadása lehetőséget**.
1. A Modulok **kiválasztása párbeszédpanelen** válassza ki **a Fizetés expressz** modult, majd válassza az **OK gombra.**
1. A Tulajdonságok ablak Támogatott **fizetésitípusok mezőjében adja** meg a mezőt **Paypal**.
1. Válassza a **Mentés** elemet, válassza a **Szerkesztés befejezése** parancsot az oldal ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.

### <a name="modes-of-delivery"></a>Szállítási módok

Amikor a Fizetési expressz modul be van állítva a PayPal használatára, a Rendszer előre kitölti a PayPal-számlához kiválasztott szállítási cím első kézbesítési beállítását. A felhasználók szükség esetén módosíthatjják a szállítási címet.

A szállítási mód sorrendjét **a Commerce Headquarters** csatorna Szállítási módok szakaszában lehet beállítani. További információkért lásd: [Szállítási módok beállítása](/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery).

A pénztári modul a szállítási beállítások modult is használni fogja, amikor a szállítási módok jelennek meg a pénztárnál. A további tudnivalókat lásd a Szállítási [beállítások modulban](../delivery-options-module.md).

A szállítási módok felkerülnek a Commerce Headquarters online áruházának listájára. Menjen a **Retail and Commerce \> Channels \> Online áruházakba**, és válassza ki az üzlet csatornaazonosítóját. Ezután válassza ki **a \> beállítási szállítási módokat**. A konfigurációban megjelenő modul szállítási módok a telephelyen is hasonló módon jelennek meg. Kiskereskedelmi csatorna vagy termék szállítási módjainak hozzáadásához vagy eltávolításához jelölje be a **Szállítási** módok kezelése lehetőséget a műveletpanelen.

## <a name="additional-resources"></a>További erőforrások

[Kifizetésekkel kapcsolatos GYIK](payments-retail.md)

[Pénztármodul](../add-checkout-module.md)

[Fizetési modul](../payment-module.md)

[Szállítási módok beállítása](/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery)

[Szállítási lehetőségek modul](../delivery-options-module.md)
