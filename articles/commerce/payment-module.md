---
title: Fizetési modul
description: Ez a témakör leírja a fizetési modult, és bemutatja, hogyan kell konfigurálni a modulban Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 04/12/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: a89ca5dd4f46611e75faccd3213028750fa48d35
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8850275"
---
# <a name="payment-module"></a>Fizetési modul

[!include [banner](includes/banner.md)]

Ez a témakör leírja a fizetési modult, és bemutatja, hogyan kell konfigurálni a modulban Microsoft Dynamics 365 Commerce.

A fizetési modul lehetővé teszi a vásárlóknak a rendelések fizetését hitelkártyával vagy bankkártyával. A fizetés integrációját ehhez a modulhoz a Dynamics 365 fizetési összekötő az Adyen szolgáltatáshoz alkalmazás biztosítja. A fizetési összekötő telepítésével és konfigurálásával kapcsolatos további információkért lásd: [Dynamics 365 fizetési összekötő az Adyen szolgáltatáshoz](dev-itpro/adyen-connector.md).  

A Commerce 10.0.14-es kiadásátől kezdve a fizetési modult integrálták a Dynamics 365 fizetési összekötővel az Paypal szolgáltatáshoz, így a vevők a rendelésekért PayPal használatával is fizethetnek. A Dynamics 365 fizetési összekötő a PayPal szolgáltatáshoz telepítésével és konfigurálásával kapcsolatos további információkért lásd: [Dynamics 365 fizetési összekötő a Paypal szolgáltatáshoz](paypal.md). 

## <a name="dynamics-365-payment-connector-for-adyen"></a>Dynamics 365 fizetési összekötő az Adyen szolgáltatáshoz 

A fizetési modul fizetési információt szolgáltat, amit az Adyen a HTML szövegközi keret (iframe) által biztosít. A fizetési modul kölcsönhatásba lép a Commerce Scale Unit egységgel, hogy kinyerje az Adyen szolgáltatásból az információkat. A Commerce Scale Unit egységgel való interakció részeként a fizetési modul engedélyezi a számlázási címének információit, mind az iframe-ben az Adyen szolgáltatáson keresztül szolgáltatva, mind egy külön modulon keresztül. A Fabrikam témában a számlázási cím külön modulként kerül engedélyezésre. Ez a mód több formázási rugalmasságot engedélyez, mert a cím sorok megadhatók, így azok a szállítási cím soraihoz hasonlóan jelennek meg.

A fizetési modul lehetővé teszi a bejelentkezett vásárlóknak menteni a fizetési információikat. A fizetési információk és számlázási címek mentésre és kezelésre kerülnek az Adyen fizetési összekötőn keresztül.

A fizetési modul fedez minden egyes rendelési változtatást, melyek nem kerülnek fedezésre hűségpontok által vagy ajándékutalványokkal. Ha a rendelés összegét teljes mértékben fedezik a hűségpontok és/vagy ajándékutalványok, a fizetési modul elrejtésre kerül, és a vásárló enélkül is leadhatja rendelését.

Az Adyen fizetési összekötő támogatja az erős vevőhitelesítést (SCA) is. Az Európai Unió (EU) frissített Pénzforgalmi szolgáltatási irányelvek (PSD2) megköveteli, hogy az online vásárlók hitelesítve legyenek az online vásárlási tapasztalataikon kívül is, amikor egy elektronikus fizetési módot használnak. A fizetési folyamat során az ügyfeleket a rendszer átirányítja a banki webhelyre, majd a hitelesítés után visszairányítják őket a Commerce fizetési folyamatába. Ezalatt az átirányítás alatt az információ, amit egy vásárló megadott a fizetési folyamat során (például szállítási cím, szállítási lehetőségek, ajándékutalvány információ, hűségadatok) láthatók maradnak. Mielőtt bekapcsolhatná az Adyen fizetési összekötő funkciót, a fizetési összekötő konfigurálva kell legyen az SCA-hoz a Commerce headquartersben. További tudnivalókért lásd: [Erős vevőhitelesítés az Adyen használatával](adyen_redirect.md). Ez a funkció a Commerce 10.0.12-as kiadásában került engedélyezésre.

> [!NOTE]
> Az Adyen payment összekötő esetében a kifizetési modul iframe modulja csak akkor jeleníthető meg, ha hozzáadja az Adyen URL-címet a webhely engedélyezési listájához. A lépés végrehajtásához adja hozzá az **\*.adyen.com** címet az oldala tartalmi biztonsági házirendjének **child-src**, **connect-src**, **img-src**, **script-src** és **style-src** direktíváihoz. További információ: [Tartalomra vonatkozó biztonsági irányelv kezelése](manage-csp.md). 

A következő ábrán egy példa látható az ajándékutalvány-, a hűség- és az Adyen fizetési modulokra a fizetési oldalon.

![Példa az ajándékutalványra, a hűségpontokra és az Adyen fizetési modulokra a fizetési oldalon.](./media/ecommerce-payments.PNG)

## <a name="dynamics-365-payment-connector-for-paypal"></a>Dynamics 365 Payment Connector a PayPal szolgáltatáshoz

A Commerce 10.0.14 kiadásától a fizetési modul integrálva van a Dynamics 365 fizetési összekötővel a PayPalhoz. A fizetési összekötő telepítésével és konfigurálásával kapcsolatos további információkért lásd: [Dynamics 365 fizetési összekötő a PayPal szolgáltatáshoz](paypal.md).
 
A fizetési oldalon az Adyen és a PayPal összekötők konfigurálhatók. A fizetési modult továbbfejlesztették további tulajdonságokkal, hogy könnyebben azonosíthassa, hogy melyik összekötővel kell dolgoznia. A részleteket lásd **a Támogatott fizetési módok és** **az Elsődleges fizetési** modul tulajdonságai az alábbi táblázatban.
  
Ha a fizetési modul a PayPal fizetési összekötő használatára van konfigurálva, egy PayPal gomb jelenik meg a fizetési oldalon. Amikor a vevő aktiválja, a fizetési modul egy PayPal információt tartalmazó iframe-et jelenít meg. Az ügyfél bejelentkezhet, és megadhatja PayPal adatait ezen az iframe-en belül a tranzakció befejezéséhez. Ha egy ügyfél úgy dönt, hogy PayPal használatával fizet, a rendelés fennmaradó egyenlege PayPalon keresztül kerül felszámolásra.

A PayPal fizetési összekötőhöz nem szükséges számlázási cím modul, mivel a számlázással kapcsolatos összes adatot a PayPal kezeli az iframe-en belül. Azonban a szállítási cím és a szállítási lehetőségek modulok szükségesek.

A következő ábra egy példát mutat be két fizetési modulra a fizetési oldalon, az egyik az Adyen fizetési összekötővel, a másik pedig a PayPal fizetési összekötővel van konfigurálva.
![Példa az Adyen fizetési modulokra és a PayPal modulokra a fizetési oldalon.](./media/ecommerce-paypal.png)

A következő ábra egy példát mutat be a PayPal gombbal megmeghívott PayPal iframe-re. 
![Példa Paypal iframe-re a pénztároldalon.](./media/ecommerce-paypal-iframe.png)

## <a name="payment-module-properties"></a>Fizetési modul tulajdonságai

| Tulajdonság neve | Értékek | Leírás |
|---------------|--------|-------------|
| Fejléc | A címsor szövege | Egy választható címsor a fizetési modulhoz. |
| Az iframe magassága | Képpontok | Az iframe magassága képpontokban. A magasság növelhető, ha szükséges. |
| Számlázási cím megjelenítése | **Igaz** vagy **Hamis** | Ha ez a tulajdonság **Igaz** értékre van állítva, akkor a számlázási cím az Adyen által lesz szolgáltatva, a fizetési modul iframe-jében. Ha ez **Hamis** értékre van állítva, akkor a számlázási cím nem az Adyen által lesz szolgáltatva, és a Commerce-felhasználónak konfigurálnia kell egy modult, hogy az mutassa a számlázási címét a fizetési oldalon. A PayPal fizetési összekötőre ez a mező nincs hatással, mivel a számlázási címet teljes mértékben kezeli a PayPal. |
| Fizetés stílus felülbírálása | Stíluslapok (CSS) kód | Mivel a fizetési modul az iframe-en keresztül van szolgáltatva, véges számú formázási képesség áll rendelkezésre. Elérhet néhány formázási lehetőséget ennek a tulajdonságnak a használatával. A webhelystílusok felülírásához be kell illesztenie a CSS-kódot a tulajdonság értékeként. A webhely CSS -építő felülbírálásai és a stílusok nem vonatkoznak erre a modulra. |
|Támogatott fizetőeszköz-típusok| Sztring| Ha több fizetési csatlakoztató van konfigurálva, akkor a Commerce Headquarters fizetési csatlakoztató konfigurációjában megadott támogatott fizetési mód karakterláncot kell használnia (lásd a következő képet). Ha üres, akkor az Adyen fizetési összekötő az alapértelmezett. Hozzáadva a Commerce 10.0.14-es kiadásában.|
|Elsődleges fizetés|  **Igaz** vagy **Hamis** | Ha **Igaz**, a rendszer hibaüzeneteket hoz létre a fizetési oldalon található elsődleges fizetési összekötőből. Ha mind az Adyen, mind PayPal fizetési összekötők konfigurálva vannak, állítsa az Adyen értéket **Igaz** értékre, amely a 10.0.14 Commerce kiadásban lett hozzáadva.|
|Összekötő-azonosító használata| **Igaz** vagy **Hamis** | Akkor használja ezt a tulajdonságot, ha a helyhez több fizetési csatlakoztató van konfigurálva. Ha **igaz**, a csatlakoztatónak a csatlakoztató azonosítóját kell használnia a fizetési korrelációhoz.|
|Böngészőkészlet nyelvkódja a <a0/<a0/<a iFrame|  **Igaz** vagy **Hamis** | (Csak Adyen) Ha **igaz**, akkor az Adyen iFrame a webhely felhasználója böngészőkörnyezete alapján adja meg a nyelvet, nem pedig a webhelyhez beállított Commerce-csatorna nyelvkódja alapján. Hozzáadva a Commerce 10.0.27-es kiadásában.|

A következő ábra egy példát mutat be, ahol a **Támogatott fizetőeszköz-típusok** érték "PayPal" értékre állítva a Commerce központ fizetési összekötő konfigurációjában.
![Példa támogatott fizetőeszköz-típusokra a Commerce Központban.](./media/ecommerce-paymenttendertypes.png)

## <a name="billing-address"></a>Számlázási cím

A számlázási cím modul akkor használható a fizetési oldalon, ha az Adyen fizetési összekötő számlázási címsorai nem felelnek meg kellőképpen a webhely többi részének megjelenéséhez. 

Ha számlázási cím modult szeretne használni a fizetési oldalon, amikor a fizetési modul integrálva van az Adyen fizetési összekötővel, állítsa a **Számlázási cím megjelenítése** tulajdonságot **Hamis** értékre, hogy az alapértelmezett Adyen számlázási cím helyett egy kijelölt számlázási címmodul használható legyen. Ebben az esetben a webhely szerzőjének tartalmaznia kell egy számlázási cím modult a pénztároldalon. Az Adyen fizetési összekötő lehetővé teszi, hogy a szállítási címet számlázási címként használja, a webhely felhasználója számára a lépések számának minimalizálása érdekében.

A fizetési modulokhoz hasonlóan egy **Támogatott fizetőeszköz-típus** tulajdonság is hozzá lett adva a 10.0.14-es Commerce kiadás számlázási cím moduljához. Ennek a tulajdonságnak meg kell egyeznie a fizetési modulban megadott értékkel, hogy azok együttműködjenek. Az Adyen fizetési összekötő esetében mind a fizetési modulnak, mind a számlázási cím modulnak üresen kell hagynia ezt az értéket (az alapértelmezett állapot). A PayPal-összekötőhöz nincs szükség dedikált számlázási címmodulra. Más típusú fizetési összekötők esetén a karakterláncot a Commerce-központban konfigurálva kell megadni.

## <a name="add-a-payment-module-to-a-checkout-page-and-set-the-required-properties"></a>Adjon meg egy fizetési modult a kifizetési oldalhoz, és állítsa be a kötelező tulajdonságokat

A fizetésimodul csak a kifizetési modulhoz adható hozzá. A fizetési modul konfigurálásával és a kifizetési oldalhoz való hozzáadásával kapcsolatos további tudnivalókért lásd: [Fizetési modul](add-checkout-module.md).

## <a name="configure-the-adyen-and-paypal-payment-connectors-when-both-are-used"></a>Az Adyen és a PayPal fizetési csatlakoztató konfigurálása mindkét használata esetén

Ha a webhely mind az Adyen, mind a PayPal fizetési csatlakoztatóját használni fogja, a Commerce webhely alábbi lépéseit követve adhat hozzá fizetési modulokat minden egyes csatlakoztatóhoz a pénztári modulhoz, majd konfigurálja az egyes modulok tulajdonságait.

1. A PayPal fizetési modul tulajdonságainak ablaktáblájában hajtsa végre a következő lépéseket:

    1. A Támogatott fizetőeszköz-típusok tulajdonság **mezőjében** adja meg a **PayPal mezőt**.
    1. Törölje a jelölést az **Elsődleges fizetési tulajdonság jelölőnégyzetből**.
    1. Jelölje be a **Use Connector ID tulajdonság** jelölőnégyzetét.

1. Az Adyen fizetési modul tulajdonságainak ablaktáblájában hajtsa végre a következő lépéseket:

    1. Hagyja üresen a Mezőt **a Támogatott fizetési típusok** tulajdonságnál.
    1. Jelölje be az Elsődleges **fizetési tulajdonság jelölőnégyzetét**.
    1. Jelölje be a **Use Connector ID tulajdonság** jelölőnégyzetét.

> [!NOTE]
> Amikor konfigurálja az Adyen és a PayPal csatlakoztató együttesen történő felhasználhatóságát, **a Dynamics 365 Payment Connector for Adyen** konfigurációnak az online **csatorna** Commerce Headquarters Fizetési számlák csatlakoztató-konfigurációjában az első helyen kell lennie. A csatlakoztató rendelés megerősítéséhez vagy módosítása érdekében váltson **online áruházakba**, és válassza ki a webhely csatornáját. **·** **·** **Ezután** a Fizetési számlák gyorslapOn, a Csatlakoztatva lapon győződjön meg arról, **hogy az Adyen-konfiguráció** Dynamics 365 Payment Connectorja az első pozícióban van (azaz a felső sorban), **és hogy a Dynamics 365 Payment Connector for PayPal** konfiguráció a második sorban van. Az újrarendeléshez szükséges csatlakoztatók hozzáadása vagy eltávolítása.

## <a name="additional-resources"></a>További erőforrások

[Kosármodul](add-cart-module.md)

[Kosárikon modul](cart-icon-module.md)

[Pénztármodul](add-checkout-module.md)

[Szállítási cím modul](ship-address-module.md)

[Szállítási lehetőségek modul](delivery-options-module.md)

[Átvételi információk modul](pickup-info-module.md)

[Rendelési részletek modul](order-confirmation-module.md)

[Ajándékutalvány modul](add-giftcard.md)

[Dynamics 365 fizetési összekötő az Adyen szolgáltatáshoz](dev-itpro/adyen-connector.md)

[Dynamics 365 fizetési összekötő a PayPal szolgáltatáshoz](paypal.md)

[Erős vevőhitelesítés (SCA) az Adyen segítségével](adyen_redirect.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
