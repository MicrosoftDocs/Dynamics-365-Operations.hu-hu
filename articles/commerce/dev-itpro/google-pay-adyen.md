---
title: Adyen fizetési konfigurálása
description: 'Ez a témakör azt ismerteti, hogyan kell konfigurálni a Következőben: Pay with Adyen Microsoft Dynamics 365 Commerce.'
author: BrianShook
ms.date: 07/05/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: c3f049946c66fcd8560f7c08a4cb2beab0dcd5b2
ms.sourcegitcommit: 3d2c0a39c4f987e9ac71df2f2fa6df0f64f10b2b
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/06/2022
ms.locfileid: "9115013"
---
# <a name="configure-google-pay-with-adyen"></a>Adyen fizetési konfigurálása

[!include [banner](../includes/banner.md)]

Ez a témakör azt ismerteti, hogyan kell konfigurálni a Következőben: Pay with Adyen Microsoft Dynamics 365 Commerce.

Dynamics 365 Commerce A <a0/10/<a2/1><a2/<a2/–<a3/"<a2/"<a3/ a3/ Adyen fizetési átjáró szolgáltatás használata esetén A Pay az Adyen fizetési szolgáltatással együtt egy digitális fizetési mód, amely Pay Merchant számlát használ az Adyen fizetési szolgáltatással. Ha be van állítva, akkor az online rendelés kifizetése során a Kifizetés gomb választható fizetési módként érhető el. Amikor a felhasználók egy **támogatott böngészőben** vagy eszközben kiválasztják a Pay kifizetést, a rendszer arra irányítani őket, hogy a kifizetést közvetlenül a Fizetési díj szolgáltatással tássa el. Ezután visszakerülnek az online áruházhoz a rendelés befejezése érdekében.

Ha a Commerce expressz pénztári modullal használja a Fizetési fizetés modult, akkor a felhasználó fizetési számlájának adatait automatikusan előre kitölti a rendszer a pénztári képernyőn, hogy a felhasználó gyorsabban végig tud menni a fizetési folyamaton. A Commerce rendszer egy fizetés expressz modult tartalmaz, amely lehetővé teszi az expressz pénztár működését. A fizetés expressz modulja a pénztár vagy a bevásárlókocsi oldalán található részletben használható. A Dynamics 365 Payment Connector for Dynamics 365 Pay Connector hivatkozását a Dynamics 365 Payment Connector for Adyen hivatkozással lehet engedélyezni, hogy a fizetés expressz és rendszeres kijelentkezés is lehetséges a PayPal konfigurálásakor. A Pay fizetés az Adyen fizetési terminálokkal és a Commerce point of sale (POS) terminálokkal is konfigurálható az üzleten kívül történő használatra.

## <a name="key-terms"></a>Kulcsfogalmak

| Időszak | Leírás |
|---|---|
| Kifizető | Az Adyen csatlakoztató által támogatott Fizetési fizetés "gomb" néven is ismert. Lehetővé teszi a felhasználói élmény és integrációt, amelyet a Dynamics Bér pay Connector támogat. |
| Pénztárca | Olyan fizetéstípus, amely nem tartalmazza a hagyományos fizetési jellemzőket, például a bank azonosítószám-tartományát (BIN) és a lejárati dátumot, amely a hitelkártya- és bankkártyatípusok megkülönböztetésére szolgál. |
| Fizetés expressz modulja | A Dynamics 365 Commerce támogatott fizetési módokkal gyorsabb pénztári működést támogató modul. |

## <a name="prerequisites"></a>Előfeltételek

A Fizetési fizetés használata az Adyennek a Commerceben szükséges Egy Kereskedői számlához. A Kereskedői számla [beállítását az Adyen dokumentációja tartalmazza a Fizetési](https://docs.adyen.com/payment-methods/google-pay/)[és Az integrációs ellenőrzőlistán](https://developers.google.com/pay/api/web/guides/test-and-deploy/integration-checklist).

A Fizetési fizetés fizetési módot szintén integrálni kell az Adyen számlával. Az integrációs hivatkozásokkal kapcsolatos tudnivalókat lásd [: Adyen Pay](https://www.adyen.com/payment-methods/google-pay).

Engedélyeznie kell a továbbfejlesztett funkciókat a központon Dynamics 365 Commerce kívül. Menjen a Munkaterületek funkciókezeléshez, keressen rá **\> a Továbbfejlesztett ügyfélszolgálati és fizetési javítások szolgáltatásra, válassza ki a funkciót,** majd válassza az Engedélyezés lehetőséget **.** **·** A funkció engedélyezése után futtassa a 1110 **elosztási ütemezést,** hogy a módosítás minden csatornában elérhető legyen.

## <a name="map-the-google-pay-payment-method"></a>A Pay fizetési mód leképezés

A Fizetési díj egy digitális fizetési mód. A Fizetés fizetésleképezésének beállítását lásd a Kifizetés [kifizetéstámogatása mezőben](../wallets.md).

A következő lépések szerint lehet a Fizetési fizetés fizetési módot a pénztári és online csatornák kártya fizetőeszköz-típusaihoz leképezni.

1. A Commerce Headquarters rendszer a **Retail és Commerce \> Csatorna beállítása fizetési \> módok kártyatípusainál \> indul el**.
1. Ha új **sort szeretne hozzáadni a Fizetési fizetéshez, válassza az Új** lehetőséget.
1. Az Azonosító **mezőben** adja meg **aPay kifizetést**.
1. Az Elektronikus **fizetés neve mezőbe** írja be **a Fizetés fizetést**.
1. A Típus **mezőben** adja meg a **Mezőjét**.
1. A Kibocsátó **mezőben** adja meg a **Következőt**:
1. A munkaablakban válassza **ki a Feldolgozó** hozzárendelése lehetőséget a Feldolgozók **fizetés-hozzárendelési metódusok párbeszédpanelének** megnyitásához.
1. A **Nem hozzárendelt** feldolgozó fizetési módok alatt megjelenik a nem hozzárendelt feldolgozó fizetési módok listája, amelyek mindegyike a megfelelő csatlakoztatóval van párosítva. A nem hozzárendelt Hitelkártyás fizetés feldolgozója fizetési módoknak a kártya fizetőeszköz-típusokhoz való leképezésével hajtsa végre a következő lépéseket mindegyik kártya fizetőeszköz-típusnál:

    1. A Kártya **fizetőeszköz-típusoknál** válasszon ki egy kártya fizetőeszköz-típust.
    1. **A Megfeleltetetlen feldolgozó fizetési** **módok oszlopban válassza ki a Dynamics 365 Payment Connector for Adyen** connector (a POS számára) és a Dynamics 365 Payment Connector for Hozzárendelt **fizetési csatlakoztató (online csatornákban való használatra)** beállítását.
    1. Válassza a **Hozzáadás** lehetőséget. A kiválasztott beállításokat a rendszer hozzáadja a **Hozzárendelt feldolgozó fizetési módok oszlophoz**.

1. Ha befejezte a fizetési módok leképezését, válassza a Mentés **lehetőséget**.
1. A Kártyatípusok **lapon** válassza a Mentés **lehetőséget**.

## <a name="configure-a-commerce-online-store-for-google-pay"></a>Commerce Online áruház konfigurálása Pay fizetéshez

A Következő lépések szerint konfigurálhatja a Commerce online áruházat a Következő módon:

1. A Commerce Headquarters elérhető a **Retail and Commerce \> Channels \> Online áruházakban**.
1. Válassza ki a webhely online áruházának csatornáját a **csatorna kiskereskedelmi csatornaazonosító-értékének kiválasztásával**.
1. A Fizetési **számlák** gyorstára a **Connector** alatt győződjön meg arról, **hogy fel van sorolva a Dynamics 365 Payment Connector for Adyen** connector. Ha nem szerepel a listán, [kövesse a Hozzáadás a Dynamics 365 Payment Connector for Adyen](adyen-connector-setup.md) beállításában szereplő útmutatást.

    > [!NOTE]
    > A legtöbb esetben **az Adyen-csatlakoztató** Dynamics 365 Payment Connector típusának a csatorna első csatlakoztatójaként (az első csatlakoztatónak is elsődleges csatlakoztatónak) kell lennie. Ezt követően követnie kell a többi használt csatlakoztatónak, **például a Dynamics 365 Payment Connector for PayPal** **és a Dynamics 365 Payment Connector for ThePay csatlakoztatónak**.

1. **A Dynamics 365 Payment Connector for Adyen** connector **·** **hozzáadása után válassza a Hozzáadás lehetőséget a Dynamics 365 Payment Connector for DynamicsPay connector** hozzáadásához. Ezután állítsa be a következő tulajdonságokat a csatlakoztatóhoz.

    | Mező                  | Leírás | Kötelező | Automatikus beállítás | Mintaérték |
    | ---------------------- | ----------- | -------- | ----------------- | ------------ |
    | Szerelvény neve          | A Dynamics 365 Payment Connector for Dynamics 365 PaymentPay szerelvényének neve. | Igen | Igen | *Bináris név* |
    | Szolgáltatásfiók azonosítója     | A kereskedői tulajdonságok beállításának egyedi azonosítója Ez az azonosító rá van pecsételve a fizetési tranzakciókra, és azonosítja azokat a kereskedői tulajdonságokat, amelyekre a lefelé irányuló folyamatoknak (például a számlázásnak) használniuk kell. | Igen | Igen | *GUID* |
    | Kereskedő azonosítója     | Annak a kereskedőnek az azonosítója, amely az Ön Kereskedő számlájához van rendelve. Erre a tulajdonságra éles környezetben van szükség, tesztkörnyezetben azonban nem kötelező. További információ:<https://pay.google.com/> | Igen | Nem | *Numerikus azonosító* |
    | Kereskedői számla azonosítója    | Az Adyen kereskedő egyedi azonosítójának beírható. Ez az érték akkor áll rendelkezésre, amikor az Adyen regisztrációját az Adyen [regisztrációja](adyen-connector-setup.md#sign-up-with-adyen) ismerteti. | Igen | Nem | *Kereskedőazonosító* |
    | Felhő API-kulcsa          | Adja meg az Adyen felhő API-kulcsot. A kulcs beszerzéséhez kövesse az [API-kulcs bejedő útmutatását](https://docs.adyen.com/developers/user-management/how-to-get-the-api-key). | Igen | Nem | "abcdefg" |
    | Átjáró környezet    | A leképezni szükséges Adyen átjáró környezet. A lehetséges értékek: **Teszt** és **Élő**. Ezt a mezőt csak termelési eszközöknél **és** tranzakcióknál kell Live beállításra állítani. | Igen | Igen | "Élő" |
    | Támogatott pénznemek   | A csatlakoztató által feldolgozott pénznemek. Kártyás esetekben az Adyen [a](https://www.adyen.com/pos-payments/dynamic-currency-conversion) tranzakciókérésnek a fizetési terminálra történő elküldését követően a dinamikus pénznemátváltás révén további pénznemeket is támogathat. Lépjen kapcsolatba az Adyen támogatási szolgálatával a támogatott pénznemek listájának a kilistával. | Igen | Igen | "USD; EUR" |
    | Támogatott fizetőeszköz-típusok | Az a fizetőeszköz-típus, amit a csatlakoztatónak fel kell feldolgoznia. | Igen | Igen | "Pay" |

1. Miután befejezte a csatlakoztató tulajdonságainak beállítását, futtassa a **1070-es (** csatorna-konfiguráció) elosztási ütemezési feladatot.

## <a name="configure-commerce-pos-for-google-pay"></a>A Commerce POS konfigurálása Pay fizetéshez

A POS-konfiguráció a **Dynamics 365 Payment Connector for Adyen hardverprofil EFT-szolgáltatási** mezőjének beállítását használja. Az elektronikus átutalási (EFT) szolgáltatásnak a Dynamics 365 Payment Connector for Adyen alkalmazáshoz történő konfigurálásával kapcsolatban a Dynamics [365 POS](adyen-connector-setup.md#set-up-a-dynamics-365-pos-hardware-profile) hardverprofilja szakasz beállítása című témakör nyújt tájékoztatást.

Az Adyen csatlakoztató processzor-hozzárendelése a Pénztár terminálon használt kártyatípusokat rögzíti.

### <a name="use-the-payment-express-module-with-google-pay"></a>A Fizetési expressz modul használata a Fizetési fizetés modullal

A Commerce Payment Express modul támogatja a fizetési módokat, hogy a webhely vevői lehetőséget adjanak a gyorsabb kijelentkezésre azáltal, hogy a fizetési szolgáltatás számlájának adatait felhasználják a pénztári folyamat során. A Fizetés expressz modul hivatkozik a konfigurált csatlakoztató gombra, és a felhasználó által kiválasztott rendelés adatait (címet, kapcsolattartási adatokat és fizetési módot) visszaküldi a pénztári képernyő előretöltéséhez.

Ha a Fizetési expressz modult a Fizetési fizetés modulban használják, és a vevők a Fizetési expressz **szakaszban a Fizetési** fizetés gombot használják, akkor a Fizetési fizetés keretablaka nyílik meg. A felhasználók ezután bejelentkezve a számlázási címük, számlázási címük, e-mail címük és Fizetési fizetési módjuk segítségével fizetik ki a tranzakciót.

Amikor a felhasználók befejezik a műveletet a Fizetési fizetés ablakban, a rendszer a Commerce webhely pénztári lapjára irányítja őket, ahol a pénztári képernyőt előre kitöltik a Fizetési számla adataival. Miután a felhasználók visszatérnek a Fizetés fizetése ablakból a pénztári oldalra, a következő részleteket láthatják:

- A fizetés expressz folyamatában a rendszer a visszaküldött szállítási cím első kézbesítési beállítását előre be fogja jelölve a vevőnél.
- A Fizetési fizetés használata esetén a rendszer nem küld vissza kapcsolattartói e-mail címet. A vendég-pénztári felhasználóknak meg kell adnia egy e-mail címet a pénztár oldal kapcsolattartói szakaszában. A bejelentkezett felhasználóknak a kapcsolattartási adatai automatikusan a Dynamics vevőfiókjukból (a hitelesítéshez használt elsődleges e-mail címükből) lesznek kitöltve.

A vevőknek lehetősége van a rendelések áttekintésára és a pénztári rendelés részleteinek a módosítása előtt **, mielőtt kiválasztják a Rendelés véglegesizálása** lehetőséget.

### <a name="configure-google-pay-in-site-builder"></a>A Webhely-készítő Fizetési szolgáltatás konfigurálása 

Mielőtt beállítja a részleteket vagy lapokat a Pay fizetéshez, gondoskodnia kell arról, hogy a webhely tartalom-biztonsági házirendje be legyen állítva a Commerce webhelyszerkesztőben.

A következő lépésekkel gondoskodhatja arról, hogy a tartalom-biztonsági házirendek be vannak állítva a webhelyszerkesztőben.

1. A webhelyen kattintson a Webhelybeállítás-bővítmények **\> elemre**.
1. A Tartalom biztonsági házirend lapján adjon hozzá egy sort a gyermekrc, a connect-src **,**`*.google.com` a keret-elődök **,** a váz-src **,** az img-src **,** a parancsfájl-src **és** a **·** **stílus-src** utasításokhoz.**·**
1. Ha végzett, válassza a Mentés és **közzététel lehetőséget**.

### <a name="configure-the-payment-express-fragment-with-google-pay-in-site-builder"></a>A fizetési expressz részlet konfigurálása a Helyszerkesztő Fizetési fizetés beállításával

Az online áruház fizetési expressz részletének beállítását a következő lépések szerint lehet beállítani.

1. A Helyszerkesztőben menjen a Részletek **gombra**.
1. Válassza az **Új** lehetőséget.
1. Az Új **részlet párbeszédpanelen** válassza ki a Tároló modult, **adjon** meg egy részletnevet (például **Expressz pénztár**), majd válassza **az OK gombra.** 
1. Az új részlet alapértelmezett tárolóhelyének **kiválasztása**.
1. A jobb oldali tulajdonságablakban állítsa be a tárolómodul tulajdonságait:

    - **Fejléc** – adjon meg egy fejlécet, amely a webhely expressz pénztár szakasza számára jelenik meg (például **Expressz pénztár**).
    - **Tárolóelrendezés** – a Folyamat **kiválasztása**
    - **Szélesség** – a Kitöltési **tároló kiválasztása**.
    - **Megmutatott** gyermekek – **válassza** a Három lehetőséget azon gyermekek számának megadásához, amelyek a pénztárlap expressz kifizetési szakaszának sorában elférnek (például szövegmező, fizetési expressz a PayPal, illetve fizetési expressz a Fizetés fizetéshez).
    - **CSS osztálynév** – adja meg az **msc-expressz fizetési tárolót** (kötelező).

    > [!IMPORTANT]
    > - A **CSS tároló fizetés** közbeni **viselkedésének szabályozásához az osztálynév értékét msc-expressz fizetési tárolóra** kell beállítani. Ez a viselkedés magában foglalja a elrejtés, összecsukás és egyéb műveleteket, amelyek az expressz pénztár szakaszra vonatkoznak a pénztári folyamat során. Az **msc-expressz-payment-container** osztály a modultár kifizetési modulja által kiadott alapértelmezett műveletekkel működik együtt.
    > - A további stílusokat az osztálynévhez lehet **CSS használni**. Ha testreszabja a modul viselkedését, ellenőrizze a stílust, amely meghatározza, hogy ugyanazt a modultár-kód viselkedést használja-e a pénztári modulban, hogy kifejezze a pénztári viselkedést.

1. Az Alapértelmezett tároló-ponthelyen **válassza** ki a három pontból (**...**), majd válassza a **Modul hozzáadása lehetőséget**.
1. A Modulok **kiválasztása párbeszédpanelen** válassza ki **a Fizetés expressz** modult, majd válassza az **OK gombra.**
1. A Fizetés **expressz modul** tulajdonságai ablakban **iFrame** állítsa be vagy módosítsa az érték képpontban megadott magasságát (**például 60**).
1. A Támogatott **fizetési típusok mezőben** adja meg **aPay kifizetést**. Az értéknek meg **kell** egyeznie a csatornához beállított csatlakoztató Támogatott fizetőeszköz-típusok karakterláncának ([a cikk korábbi részében, a Commerce online áruház konfigurálása a Kapcsolódó](#configure-a-commerce-online-store-for-google-pay) fizetéshez szakaszban ismertetett leírásnak megfelelően).

    > [!NOTE]
    > A 6–9. lépés megismétlhető az **egyéb fizetési módok Fizetési expressz** moduljainak hozzáadása. A támogatott **fizetési módok értékének** beállítása a további konfigurált fizetési típusokhoz (például **Paypal**).

1. Nem kötelező: Az alapértelmezett tárolómodulhoz felvehet szövegblokkmodult, hogy az útmutatásokat és közzétételi adatokat tartalmazza. Miután hozzáadta a modult, írja **be a kívánt szöveget a Tulajdonságok ablakba a Rich Text mezőbe**. A szöveget a Fizetési expressz modulok fölé vagy alá lehet pozicionani: válassza ki a Szövegblokk beállítási pontnak megfelelő (**...**) **·** **ellipszis**, majd a Felfelé vagy lefelé **gombra kattintva**.
1. A **módosítások mentéséhez** válassza a Mentés, majd a Szerkesztés befejezése **lehetőséget**.
1. Válassza a **Közzététel** lehetőséget a részlet közzétételéhez.

### <a name="add-the-payment-express-fragment-to-the-checkout-page"></a>Fizetési expressz részlet hozzáadása a kifizetési oldalhoz

Ha a fizetési expressz részletet hozzá szeretne adni a pénztári laphoz, kövesse ezeket a lépéseket.

1. A webhelyszerkesztőben menjen a Pages **oldalra**, majd válassza ki a webhely pénztári lapját.
1. Válassza ki a **Szerkesztés** opciót.
1. A fő **pontnál válassza** ki a három pontból (**...**), majd válassza a **Modul hozzáadása lehetőséget**.
1. A Modulok **kiválasztása párbeszédpanelen** válassza ki **a** Tároló modult, majd válassza az **OK gombra.**
1. A jobb oldali tulajdonságablakban állítsa be a tárolómodul tulajdonságait:

    - **Tárolóelrendezés** – Halmozott **kijelölés kiválasztása**.
    - **Szélesség** – a Kitöltési **tároló kiválasztása**.
    - **Megjelenő** gyermekek – **a** Három beállítás megadásával meghatározhatja, hogy hány gyermek fog elférni a kifizetési oldal expressz kifizetési szakaszának sorában (például szövegmező, expressz a következő esetén: PayPal kifizetés, vagy fizetési expressz a Fizetés fizetéshez).

1. A Tároló modulban **válassza** ki a három pontból (**...**), majd válassza a Részlet hozzáadása **lehetőséget**.
1. A Részletfizetés **kiválasztása párbeszédpanelen** válassza ki a létrehozott expressz fizetési részletet, majd válassza az **OK gombra.**
1. A **módosítások mentéséhez** válassza a Mentés, majd a Szerkesztés befejezése **lehetőséget**.
1. A lap **közzétételéhez** válassza a Közzététel lehetőséget.

> [!NOTE]
> Ha a pénztári lap már tartalmaz egy olyan tárolót, amelynél a pénztári részlet található, és azt szeretné, hogy a fizetés Express modulja látható legyen a normál pénztár tároló fölött, a meglévő pénztárgép fölé vagy alá lehet helyezni, ha a fő pontnál a három pont (**...**)**·** **·** **gombra**, majd a Felfelé vagy lefelé gombra kattintva használhatja.

### <a name="add-the-payment-express-fragment-to-the-cart-page"></a>Fizetési expressz részlet hozzáadása a kosároldalhoz

A fizetési expressz részletnek a bevásárlókocsiba történő felvételét a következő lépések szerint hajtsa végre.

1. A webhelyszerkesztőben menjen a Pages **oldalra**, majd válassza ki a webhely bevásárlókocsiját.
2. Válassza ki a **Szerkesztés** opciót.
3. A szerkezet nézetben bontsa ki **a** fanézetben a fő rést, és keresse meg a **Kocsi** modult tartalmazó tárolót.
4. A Bevásárlókocsi **modulban** válassza **ki a Payment Express ponthelyet**, válassza ki a három pontból (**...**), **majd válassza a Modul hozzáadása lehetőséget**.
5. A Modulok **kiválasztása párbeszédpanelen** válassza ki **a Fizetés expressz** modult, majd válassza az **OK gombra.**
6. Válassza ki **a Fizetés expressz modulja** által legépelt lehetőséget. Ezután a jobb oldali tulajdonságok ablakában, a Támogatott **fizetési típusok** pontba írja be a **Kifizetés gombra.** Az értéknek meg **kell** egyeznie a csatornához beállított csatlakoztató Támogatott fizetőeszköz-típusok karakterláncának ([a cikk korábbi részében, a Commerce online áruház konfigurálása a Kapcsolódó](#configure-a-commerce-online-store-for-google-pay) fizetéshez szakaszban ismertetett leírásnak megfelelően).
1. A **módosítások mentéséhez** válassza a Mentés, majd a Szerkesztés befejezése **lehetőséget**.
1. A lap **közzétételéhez** válassza a Közzététel lehetőséget.

A felhasználók legfeljebb három **támogatott Payment Express** modult (más szóval három rendelkezésre álló támogatott fizetési lehetőséget) **tartalmazhatnak a Payment Express fizetési pontba**.

### <a name="set-up-google-pay-as-an-option-in-the-checkout-payment-section"></a>Fizetési díj beállítása a fizetés kifizetési szakaszának lehetőségként

A Fizetés fizetés beállítását a fizetés kifizetési szakaszában lehet beállítani kizárólag fizetésre, de nem expressz funkciókra. A pénztári képernyőt a felhasználó tölti ki, és a Fizetési díj lapon csak a Kifizetés fiz. A pénztári számlaadatok nem lesznek használva a kitöltött pénztári adatok felülírásakor.

> [!NOTE]
> A következő eljárás feltételezi, hogy a telephely egy felvételi adatokkal konfigurált pénztári részletet, szállítási címet, szállítási beállításokat, kapcsolattartási adatokat, választható feltételeket és feltételeket, valamint a kifizetési elemek egy szakaszát használja. Az alapértelmezett modultár kifizetési modulja egy pénztári szakasztárolóval van kiadva, amely szöveges blokkot, hűségpontokat, ajándékutalványt és fizetési modulokat tartalmaz. További információ a Kifizetési modulban [található](../payment-module.md).

A fizetési mód lap **Fizetési** mód szakaszának rendszeres fizetési beállítását a következő lépések szerint állíthatja be.

1. A webhelyszerkesztőben menjen a Részletek **gombra**, majd válassza ki a webhely pénztári részletét.
1. Válassza ki a **Szerkesztés** opciót.
1. Válassza ki **a pénztári** információs pontnál a három pontból (**...**), majd válassza a **Modul hozzáadása lehetőséget**.
1. A Modulok **kiválasztása párbeszédpanelen** válassza ki **a Kifizetés** modult, majd válassza az **OK gombra**.
1. A jobb **oldali Fizetési** modul tulajdonságai ablakban állítsa be a tárolómodul tulajdonságait:

    - **Fejléc** – adjon meg egy fejlécet, amely a webhely expressz pénztár szakasza számára jelenik meg (például **: Fizetés fizetés**).
    - **Magassága – iFrame** az érték módosítása a kívánt tervezési magasságra képpontban (**például 75**). 
    - **Támogatott fizetési típusok** – a **Commerce Headquarters** szoftverBen használt Bérfizetés csatlakoztató konfigurációjának egyeztetéséhez adja meg aPay-kifizetést.
    - **Elsődleges kifizetés** – hagyja a jelölőnégyzetet törölve. (Ez a tulajdonság jellemzően engedélyezve van az Adyen pénztár modulban.)
    - **Fizetési stílus felülbírálása** – ez a tulajdonság nem támogatott a Fizetési díj konfigurációban.
    - **Csatlakoztató azonosítója** – ezt a tulajdonságot kell kiválasztani, ha az oldalon több fizetési csatlakoztató van használatban.

1. Helyezze a modult más fizetési modulok fölé vagy alatt úgy, hogy kijelöli a fizetési pont pontokat (**...**), **·** **majd** a Felfelé vagy lefelé **gombra kattintva.**
1. A **módosítások mentéséhez** válassza a Mentés, majd a Szerkesztés befejezése **lehetőséget**.
1. Válassza a **Közzététel** lehetőséget.

### <a name="modes-of-delivery"></a>Szállítási módok

Ha a Fizetési fizetés modult használja, akkor a program az első olyan szállítási beállítást választja, amely a Kiválasztott szállítási cím ellenében vissza lesz jelölve a Fizetési díj számláról. A felhasználóknak lehetőségük van arra, hogy ha másik beállításra módosítják a szállítási címet.

A Commerce Headquarters csatorna Szállítási módok lapján konfigurálható, hogy milyen sorrendben jelennek meg a szállítási módok a Fizetés expressz **modulban**. A Commerce Headquarters alkalmazásba menjen a **Retail és Commerce \> Channels \> Online áruházakba**, és **válassza ki az üzlet kiskereskedelmi** csatornaazonosító-értékét. A Műveletpanel Beállítás lapján **válassza** a **Szállítási módok lehetőséget**. A felsorolt szállítási módok ugyanabban a sorrendben jelennek meg a Fizetés expressz modulban. Válassza **a Szállítási módok kezelése lehetőséget** a munkaablakban a kiskereskedelmi csatornák vagy termékek szállítási módjainak hozzáadásához vagy eltávolításához. A szállítási módok beállításának további tudnivalókat lásd [: Szállítási módok beállítása](/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery).

A pénztári modul a szállítási beállítások modult is használja, amikor a szállítási módok jelennek meg a pénztárnál. A további tudnivalókat lásd a Szállítási [beállítások modulban](../delivery-options-module.md).

A szállítási módok akkor jelennek meg, amikor hozzáadják **őket** az online áruház Szállítási módok listájához.

## <a name="additional-resources"></a>További erőforrások

[Kifizetésekkel kapcsolatos GYIK](payments-retail.md)

[Pénztármodul](../add-checkout-module.md)

[Fizetési modul](../payment-module.md)
