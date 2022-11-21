---
title: 'Állítson be pay pay-t az Adyenhez a következőben: Dynamics 365 Commerce'
description: Ez a témakör azt ismerteti, hogyan lehet beállítani Az Adyen fizetési halmazt a következőben:Microsoft Dynamics 365 Commerce
author: BrianShook
ms.date: 11/15/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: josaw
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2022-06-20
ms.openlocfilehash: 0949b9d7a4b181605d43956932b4fc095940bd64
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/16/2022
ms.locfileid: "9780201"
---
# <a name="set-up-apple-pay-with-adyen-in-dynamics-365-commerce"></a>Állítson be pay pay-t az Adyenhez a következőben: Dynamics 365 Commerce

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

Ez a témakör azt ismerteti, hogyan lehet beállítani Az Adyen fizetési halmazt a következőben:Microsoft Dynamics 365 Commerce

## <a name="key-terms"></a>Kulcsfogalmak

| Időszak | Leírás |
|---|---|
| Kifizető | A Bérfizetés "gomb" néven is ismert, amely az Adyen csatlakoztató által támogatott kifizetés. Lehetővé teszi a felhasználói élmény és integrációt, Microsoft Dynamics amelyet a 365 Pay Connector támogat. |
| Pénztárca | Olyan fizetéstípus, amely nem tartalmazza a hagyományos fizetési jellemzőket, például a bank azonosítószám-tartományát és a lejárati dátumot, amely a hitel- és bankkártyatípusok megkülönböztetésére szolgál. |

Dynamics 365 Commerce A <a0/10/<a2/1><a2/1><a2/5><a2/"<a2/"A3/Adyen fizetési átjáró szolgáltatás használata esetén a Pay</ A Pay az Adyen fizetési szolgáltatással együtt egy digitális fizetési mód, amely Egy Kifizetés kifizetés kereskedői számláját használja. Ha be van állítva, akkor a Kifizetés gombra kattintva kiválaszthatja azt a fizetési módot, amely része egy online áruház rendelés-kifizetési oldalának. A Kifizetés gomb csak a támogatott Fizetési eszközök fizetési lehetőségként jelennek meg. Amikor a felhasználók egy **támogatott böngészőben vagy eszközön kiválasztják a Pay** kifizetést, a rendszer a kifizetés közvetlen befejezésére a Fizetési díj szolgáltatáshoz irányítja őket. Ezután a rendelés befejezésekor visszakerülnek az online áruházhoz.

A Dynamics 365 Payment Connector for Pay connector hivatkozását a Dynamics 365 Payment Connector for Adyen mellett a rendszer a hely fizetési és hitelkártyás kifizetésének engedélyezésére is használja. A Pay fizetési mód olyan üzletekben is konfigurálható, amelyekhez olyan Adyen fizetési terminálok is vannak, amelyek a Commerce Point of Sale (POS) számára a Dynamics 365 Payment Connector for Adyen terminált használják. Ebben az esetben a Dynamics 365 Payment Connector for Adyen kezeli a terminálon végigérkedő Kifizetés eszköz által érintett eszközt.

## <a name="prerequisites"></a>Előfeltételek

Egy kereskedői számlára van szükség ahhoz, hogy a Commerce rendszer használja az Adyen esetén a Következő kereskedői számlát: A teszt vevői területének beállítását a Fizetési [fizetés integrációval kapcsolatban lásd](https://docs.adyen.com/payment-methods/apple-pay/web-drop-in#set-up-apple-pay). Arról, hogy mi a mit kell tenni, ha készen áll az éles környezetben való élő használatra, [lásd Az éles környezetben való indulást](https://docs.adyen.com/payment-methods/apple-pay/web-drop-in#going-live).

A Fizetési fizetés fizetési módot szintén integrálni kell az Adyen számlával. Az Adyen segítségével beállíthatja a fizetési módot, és gondoskodhat arról is, hogy a tanúsítványhoz használni fogja a tartományokat, amelyekhez a tanúsítványt fogja használni.

Ha engedélyezni szeretné a továbbfejlesztett funkciók jelzőit a Commerce Headquarters alkalmazásban, **\>** keresse meg a Munkaterületek funkciókezelését, **és keressen rá a Továbbfejlesztett ügyfélszolgálati** és fizetési javítások szolgáltatásra. Válassza ki a funkciót, majd válassza az Engedélyezés **lehetőséget**. A funkció engedélyezése után futtassa a 1110 **elosztási ütemezést,** hogy a módosítás minden csatornában elérhető legyen.

## <a name="map-the-apple-pay-payment-method"></a>A Kifizetés kifizetése fizetési mód leképezés

A Bérfizetés egy digitális fizetési mód. A Fizetés fizetésleképezésének beállítását lásd a Kifizetés [kifizetéstámogatása mezőben](../wallets.md).

A Commerce Headquarters fizetési módjait a következő lépések szerint lehet leképezni.

1. Ugrás a **Retail és Commerce \> Csatorna beállítása fizetési \> módok kártyatípusaihoz \>**
1. Válassza az **Új** lehetőséget, ha egy sort szeretne hozzáadni a Fizetés fizetéshez, és állítsa be a következő értékeket:

    - **Azonosító:** Pay
    - **Elektronikus kifizetés neve:** Pay
    - **Típus:** Író
    - **Kibocsátó:** Kiállító

1. A Feldolgozó **hozzárendelése lehetőség kiválasztásával** nyissa meg a Feldolgozók **fizetés-hozzárendelési metódusai párbeszédpanelt**. A **Nem hozzárendelt** feldolgozó fizetési módok oszlop felsorolja az egyes elérhető csatlakoztató (Adyen, PayPal és Mellán) támogatott fizetési módjait.
1. Leképezi a **támogatott fizetési módokat, amelyek a Dynamics 365 Payment Connector for Adyen** connector csatlakoztatóhoz használhatók (a POS terminálon való használatra), **valamint a Dynamics 365 Payment Connector for Pay** Connector csatlakoztatóhoz (az online csatornához).
1. Mindegyik megfeleltetési **sor** Megfeleltetés nélküli feldolgozó fizetési módok oszlopában válassza ki a támogatáshoz kívánt sort, **·** **majd** válassza a Hozzáadás lehetőséget, ha a kiválasztott értékeket a Hozzárendelt feldolgozó fizetési módok oszlopba szeretne áthelyezni.
1. Válassza **az OK** gombra, majd a **Kártyatípusok** lapon válassza a Mentés **lehetőséget**.

## <a name="set-up-the-apple-pay-certificate-for-your-site"></a>A saját webhely fizetési tanúsítványának beállítása

Mindegyik helyhez fel kell töltenie a tartomány-hozzárendelési fájlt (más néven Bérfizetői tanúsítvány) [az Adyen Fizetési dokumentációban leírtaknak megfelelő módon](https://docs.adyen.com/payment-methods/apple-pay/web-drop-in#going-live). A Commerce Webhelyszerkesztő segítségével feltöltheti a tartomány-társítási fájlt a webhely médiakönyvtárába.

A Következő lépések szerint állíthatja be a Fizetés fizetése tanúsítványát a helyszerkesztőben.

1. A tanúsítvány (tartomány-hozzárendelési fájl) letöltése az [Adyen rendszerből](https://docs.adyen.com/payment-methods/apple-pay/web-drop-in#going-live).
1. Adja hozzá a .txt kiterjesztést a tartomány-hozzárendelési fájlhoz.
1. A webhelyszerkesztőben töltse [fel a](../upload-serve-static-files.md) tartomány-társítási fájlt a webhely médiakönyvtárába.
1. Ugrás URL-címekre **·**
1. Válassza az **Új \> Új URL-cím** lehetőséget.
1. Az Új **URL-párbeszédpanelen** válassza ki a Médiatár **eszközt**.
1. Az URL elérési **út mezőjében** adja meg az URL-cím elérési útját (ha még nincs megadva). A tartomány alap URL-címe után adja meg a következő szükséges String karakterláncot:`<domain>/.well-known/apple-developer-merchantid-domain-association.txt`
1. Válassza ki **Következő** lehetőséget. A médiatár a **dokumentum** (.txt) típusú feltöltött médiaeszközöket jeleníti meg.
1. Válassza ki azt a tartomány-társítási fájlt, amely a korábban meghatározott URL-címre vonatkozó kérések esetén használható.
1. Válassza a **Létrehozása** lehetőséget.

Ezen a ponton a létrehozott URL piszkozat állapotban van. A folyamat befejezéséhez tegye közzé az URL-címet. Az URL-cím által mutatott fájl csak akkor lesz visszaadva, ha közzéteszi az URL-címet.

## <a name="configure-a-commerce-online-store-for-apple-pay"></a>Commerce Online áruház konfigurálása Pay fizetéshez

A Következő lépések szerint konfigurálhatja a Commerce Online áruházat a Pay fizetéshez.

1. A Commerce Headquarters elérhető a **Retail and Commerce \> Channels \> Online áruházakban**.
1. Válassza ki **a webhely** online áruházi csatornájának kiskereskedelmi csatornaazonosító értékét.
1. **·** **Adja hozzá a Dynamics 365 Payment Connector for Adyen** csatlakoztatóhoz a Fizetési számlák gyorsét, ha még nincs beállítva, [kövesse a Dynamics 365 Payment Connector for Adyen](adyen-connector-setup.md) beállításában található utasításokat.
1. Az Adyen-csatlakoztató **·** **konfigurálása után válassza a Hozzáadás lehetőséget a Dynamics 365 Payment Connector for Bér Pay connector hozzáadásához**.
1. Adja meg a csatlakoztató kereskedő tulajdonságainak értékeit.

    | Tulajdonság               | Leírás | Kötelező | Automatikus beállítás | Mintaérték |
    | ---------------------- | ----------- | -------- | ----------------- | ------------ |
    | Szerelvény neve          | A Dynamics 365 Payment Connector for Pay szerelvényének neve. | Igen | Igen | Bináris név |
    | Szolgáltatásfiók azonosítója     | A kereskedői tulajdonságok beállításának egyedi azonosítója Ez az azonosító rá van pecsételve a fizetési tranzakciókra, és azonosítja azokat a kereskedői tulajdonságokat, amelyekre a lefelé irányuló folyamatoknak (például a számlázásnak) használniuk kell. | Igen | Igen | Guid |
    | Kereskedő számlaazonosítója    | Az Adyen kereskedő egyedi azonosítójának beírható. Ez az érték akkor áll rendelkezésre, amikor az Adyen regisztrációját az Adyen [regisztrációja](adyen-connector-setup.md#sign-up-with-adyen) ismerteti. | Igen | Nem | MerchantIdentifier |
    | Felhő API-kulcsa          | Adja meg az Adyen felhő API-kulcsot. Ezt a kulcsot az [API-kulcs bejedő útmutatójának útmutatása segítségével szerezheti be](https://docs.adyen.com/developers/user-management/how-to-get-the-api-key). | Igen | Nem | abcdefg |
    | Gateway környezet    | Adja meg azt az Adyen átjáró környezetet, amelybe leképezi. A lehetséges értékek: **Teszt** és **Élő**. Ezt a mezőt csak termelési eszközöknél **és** tranzakcióknál kell Live beállításra állítani. | Igen | Igen | Élő |
    | Támogatott pénznemek   | Adja meg, hogy a csatlakoztatónak mit kell feldolgoznia. Kártyás esetekben az Adyen [a](https://www.adyen.com/pos-payments/dynamic-currency-conversion) tranzakciókérésnek a fizetési terminálra történő elküldését követően dinamikus pénznemátváltás révén további pénznemeket támogathat. Lépjen kapcsolatba az Adyen támogatási szolgálatával a támogatott pénznemek listájának beszerzése érdekében. | Igen | Igen | USD; Eur |
    | Támogatott fizetőeszköz-típusok | Adja meg, hogy milyen fizetőeszköz-típusokat kell feldolgoznia a csatlakoztatónak. | Igen | Igen | Előleg |

1. A kereskedői adatok bevitele után futtassa a **1070-es** csatornakonfiguráció-elosztási ütemezési feladatot.

## <a name="configure-commerce-pos-for-apple-pay"></a>A Commerce POS konfigurálása Pay fizetéshez

A POS-konfiguráció a **Dynamics 365 Payment Connector for Adyen hardverprofil EFT-szolgáltatási** mezőjének konfigurációját használja. A Commerce Headquarters programban konfigurálja a Dynamics 365 Payment Connector for Adyen [elektronikus átutalási szolgáltatását a Dynamics 365 POS hardverprofilja szakasz beállításában leírtaknak megfelelően](adyen-connector-setup.md#set-up-a-dynamics-365-pos-hardware-profile).

Győződjön meg róla, hogy **a Támogatott** fizetési típusok **mezőben a Fizetési fizetést hozzáadja a fizetési típusok listájához**. Pontosvesszők használata (;) – külön fizetési típusok a listában.

Az Adyen csatlakoztató processzor-hozzárendelése rögzíti a Pay pay által a POS terminálon használt kártyatípusokat.

### <a name="configure-content-security-policies-in-site-builder"></a>Tartalom-biztonsági házirendek konfigurálása a webhelyszerkesztőben

Ahhoz, hogy beállítja a darabokat vagy lapokat a Pay fizetés használatára, gondoskodnia kell arról, hogy a tartalom-biztonsági házirendek (CSPs) konfigurálva vannak a Commerce webhely-szerkesztőben.

A webhelyszerkesztőben a tartalom-biztonsági házirendek konfigurálása érdekében hajtsa végre ezeket a lépéseket.

1. Lépjen a **Webhelybeállítások \> Bővítmények** pontra.
1. A Tartalom biztonsági házirend lapján válassza a Hozzáadás **lehetőséget, ha olyan sort szeretne hozzáadni, amely a gyermek-src**, **a connect-src**, `https://applepay.cdn-apple.com/jsapi/v1/apple-pay-sdk.js` a frame-src **,** az img-src **,** a script-src **és** a **stílus**-src **szakaszhoz kapcsolódik.** **·**
1. Ha végzett, a módosítások véglegesítéshez válassza a Mentés **és** közzététel lehetőséget.

### <a name="set-up-apple-pay-as-a-checkout-payment-option"></a>Fizetés beállítása fizetés kifizetési lehetőségként

A következő lépések szerint állíthatja be Kifizetési fizetés fizetését a webhely (nem expressz) pénztári lapján.

1. A webhelyszerkesztőben menjen a Részletek **gombra**, és válassza ki a webhely pénztári részletét.
1. Válassza ki a **Szerkesztés** opciót.
1. A Pénztár **szakasz tárolókban válassza** ki a három pontból (**...**), majd válassza a **Modul hozzáadása lehetőséget**.
1. A Modulok **kiválasztása párbeszédpanelen** válassza ki **a Fizetés fizetés** modult, majd válassza az **OK gombra.**
1. Válassza a **Mentés** lehetőséget.
1. Válassza a **Szerkesztés befejezése** parancsot a töredék ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.

**A Pay modul** beállításai a modulba épülnek, és csatlakoznak a Commerce Headquarters online csatornájához beállított, konfigurált Dynamics 365 Payment Connector for Pay Connector alkalmazáshoz.

### <a name="apple-pay-payment-behavior"></a>Fizetés fizetésének viselkedése

A **Fizetés kifizetése** gomb csak a támogatott Pay eszközöknél látható (iPhones, iPads és Webböngésző böngészőkben, amelyek támogatják a Fizetés kifizetést). Ha egy felhasználó nem használja ezeket az eszközöket, **akkor a Fizetési** fizetés gomb el van rejtve a nézetben.

Amikor egy felhasználó a Fizetés **kifizetése** gombot választja, megjelenik egy **Kifizetés** párbeszédpanel. A felhasználó hitelesítheti magát saját Pay-eszközével vagy böngészőjével szemben. A **Kifizetés kifizetése** párbeszédpanelen megjelenik a rendelés összegének és a felhasználó által a saját Összesítésben beállított fizetési módnak az összegzése. A felhasználó áttekintheti ezeket az adatokat, majd **a Fizetés** kiválasztásával befejezheti a kifizetést. A kifizetés befejezése után a rendszer a Felhasználót a Teljes rendelés webhelyre irányítja, **amely** a befejeződött tranzakció részletes rendelési összegzését mutatja.

## <a name="additional-resources"></a>További erőforrások

[Kifizetésekkel kapcsolatos GYIK](payments-retail.md)

[Pénztármodul](../add-checkout-module.md)

[Fizetési modul](../payment-module.md)
