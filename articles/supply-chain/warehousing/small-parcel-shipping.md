---
title: Kis csomagok szállítása
description: Ez a témakör a kis csomagok szállítása (SPS) funkcióról nyújt tájékoztatást. Ez a funkció lehetővé teszi, hogy a Microsoft Dynamics 365 Supply Chain Management részleteket bocsásson a szállítmányozó rendelkezésére egy csomagolt tárolóról, majd egy szállítási címkét, szállítási díjat és nyomon követési számot fogadjon a szállítmányozótól.
author: Mirzaab
ms.date: 01/08/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TMSRateEngine, TMSCarrier, CustTable, TMSShippingCarrierCustomerAccount, TMSSmallParcelShippingFeature
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-01-08
ms.dyn365.ops.version: Release 10.0.16
ms.openlocfilehash: 3969ee6b46f38fe2650881fb0183c60aadce6c8a
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5831170"
---
# <a name="small-parcel-shipping"></a>Kis csomagok szállítása

[!include [banner](../../includes/banner.md)]

A kis csomagszállítás (SPS) szolgáltatás lehetővé teszi a Microsoft Dynamics 365 Supply Chain Management számára, hogy közvetlenül kommunikáljon a szállítmányozókkal azáltal, hogy keretrendszert biztosít a szolgáltatói API-kon keresztüli kommunikációhoz. Ez a funkció akkor hasznos, ha az egyes értékesítési rendeléseket kereskedelmi szállítmányozókon keresztül szállítja ki, nem pedig konténeres vagy kisebb, mint a truckload szállítással.

Az SPS szolgáltatás egy külön *Díjazási motoron* keresztül kommunikál a szállítmányozóval. A szervezetnek a szállítmányozói vagy szállítmányozói központ szolgáltatással együttműködve ki kell dolgoznia ezt a díjazási motort. Ez díjazási motor lehetővé teszi, hogy a Supply Chain Management részleteket bocsásson az ön szállítmányozója rendelkezésére egy csomagolt tárolóról, majd egy szállítási címkét, szállítási díjat és nyomon követési számot fogadjon a szállítmányozótól.

A visszaküldött szállítási díj vegyes költségként hozzáadódik a kapcsolódó értékesítési rendeléshez. A visszaküldött levélcímke ezután automatikusan kinyomtatható egy Zebra programnyelvet (ZPL) használó nyomtató segítségével, és alkalmazható a szállítmányra. A szállítmányozó leolvassa ezt a levélcímkét, amikor felveszi a csomagokat a raktárban.

## <a name="prepare-your-system-to-support-sps"></a>A rendszer előkészítése az SPS támogatására

Az SPS funkció használatához először be kell kapcsolnia az SPS szolgáltatást a Funkciókezelésben, hozzá kell adnia az ön díjazási motorját, és be kell állítani a **Szállításkezelés** és a **Raktárkezelés** modulokat a támogatására.

### <a name="turn-on-the-sps-feature"></a>Az SPS funkció bekapcsolása

Az SPS funkció használata előtt be kell azt kapcsolnia saját rendszerében. A rendszergazdák használhatják a [Funkciókezelési](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) munkaterület a funkció állapotának ellenőrzéséhez, és szükség esetén bekapcsolásához. A funkció a következő módon jelenik meg:

- **Modul:** *Szállításkezelés*
- **Funkció neve:** *Kiscsomagos szállítás*

### <a name="deploy-and-set-up-rate-engines"></a>Díjazási motorok telepítése és beállítása

A Supply Chain Management nem tartalmaz díjazási motorokat. Be kell szereznie vagy létre kell hoznia minden szükséges díjazási motort, majd hozzá kell őket adni a rendszerhez. A Microsoft azonban egy bemutató díjazási motort biztosít, amely használható tesztelésre.

#### <a name="download-and-deploy-the-demo-rate-engine"></a>A bemutató díjazási motor letöltése és telepítése

Kövesse az alábbi lépéseket a bemutató díjazási motor letöltéséhez.

1. A GitHub szolgáltatásban töltse le a [dinamikus csatolású függvénytárat (DLL) a bemutató díjazási motorjához](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/SCM/SPS).
1. Mentse a DLL-fájlt a Supply Chain Management kiszolgálóra az **\\AOSService\\PackagesLocalDirectory\\ApplicationSuite\\bin** mappába.

#### <a name="create-and-deploy-functional-rate-engines"></a>Funkcionális díjazási motorok létrehozása és telepítése

A funkcionális díjazási motorok termelési vagy tesztkörnyezetben való felhasználhatósága érdekében történő létrehozásával és telepítésével kapcsolatban a következő témakörök tartalmaznak tájékoztatást:

- [Új szállításkezelő motor létrehozása](../transportation/create-new-transportation-management-engine.md)
- [Szállításkezelő kalkulátorok beállítása](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-transportation-management-engines)

Az SPS díjazási motor létrehozásáról további információ: [Kiscsomagos szállítás: A kiscsomagos szállítás funkcióinak alkalmazása a Microsoft Dynamics 365 szolgáltatásban](https://hub.bhsolutions.com/creating-a-mock-parcel-engine-in-d365?submissionGuid=46a1fccf-80b0-4b70-a6a0-4bf45a8756b5).

#### <a name="set-up-a-rate-engine-in-supply-chain-management"></a>Díjazási motor beállítása a Supply Chain Management szolgáltatásban

Miután létrehozta és telepítette az SPS díjazási motorját, a következő lépések szerint állíthatja be.

1. Lépjen a **Szállításkezelés \> Beállítás \> Motorok \> Díjazási motor** elemre.
1. A műveleti ablakpanelen válassza ki az **Új** lehetőséget, ha hozzá szeretne adni egy sort a rácshoz.
1. Az új sorban állítsa be a következő mezőket:

    - **Minősítési motor** – adja meg a díjazási motor egyedi nevét. Ha bemutató díjazási motort használ, adja meg a *Bemutató díjazási motor* értéket.
    - **Név** – adja meg a díjazási motor rövid leírását. Ha bemutató díjazási motort használ, adja meg a *Bemutató díjazási motor* értéket.
    - **Minősítési metaadatok azonosítója** – válassza ki a díjszámítás alapját. Például a díj a távolság alapján számítható ki. Ha bemutató díjazási motort használ, ezt a mezőt üresen hagyhatja.
    - **Kalkulátorszerelvény** – adja meg a telepített DLL-csomag fájlnevét. Ha bemutató díjazási motort használ, adja meg a *TMSSmallParcelShippingEngine.dll* értéket.
    - **Kalkulátorosztály** – adja meg a díjazási motorban meghatározott osztálynevet. Ha bemutató díjazási motort használ, adja meg a *TMSSmallParcelShippingEngine.SmallParcelShippingRateEngine* értéket.

## <a name="example-scenario"></a>Példaforgatókönyv

A példa azt mutatja be, hogyan lehet beállítani és használni az SPS-t, miután a témakörben korábban leírtak szerint előkészítette a rendszert. Ez az eset a korábban említett bemutató díjazási motort használja.

### <a name="make-demo-data-available"></a>A bemutató adatok elérhetővé tétele

Ha ezt a forgatókönyvet az itt megadott bemutatórekordok és értékek alapján kívánja elvégezni, akkor egy olyan rendszert kell használnia amelynél a szokásos [bemutatóadatok](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) telepítve vannak. Emellett az **USMF** jogi személyt is ki kell választani a kezdés előtt.

### <a name="set-up-the-scenario"></a>Forgatókönyv beállítása

Ebben a példában bemutató szállítmányozónak, szállítmányozócsoportnak, csomagolási irányelvnek és csomagolási profilnak kell lennie. Az alábbi alszakaszok az esethez szükséges rekordok előkészítését ismertetik. Termelési forgatókönyv esetében a beállítási folyamat általában hasonló az itt ismertetett folyamathoz. Eltérő értékeket azonban beállíthat.

#### <a name="set-up-carriers"></a>Szállítmányozók beállítása

Szállítmányozó beállításához kövesse az alábbi lépéseket.

1. Ugorjon a **Szállításkezelés \> Beállítás \> Szállítmányozók \> Szállítmányozók** lehetőségre.
1. Jelölje be a Műveleti ablaktáblán az **Új** lehetőséget szállítmányozó hozzáadásához.
1. A fejlécben állítsa be a következő értékeket:

    - **Szállítmányozó:** *Bemutató szállítmányozó*
    - **Név:** *Bemutató szállítmányozó*
    - **Mód:** *földi*

1. Az **Áttekintés** gyorslapon állítsa be a következő értékeket:

    - **A szállítmányozói felületek aktiválása:** *Igen*
    - **A szállítmányozó minősítésének aktiválása:** *Igen*

1. A **Szolgáltatások** gyorslapon válassza az **Új** parancsot, ha egy szolgáltatást szeretne hozzáadni a rácshoz.
1. Állítsa be a következő értékeket az új szolgáltatáshoz:

    - **Szállítmányozói szolgáltatás:** *Bemutató szállítmányozói szolgáltatás*
    - **Név:** *Bemutató szállítmányozói szolgáltatás*
    - **Szállítási mód:** *Földi*

    Igény szerint adjon meg tetszőleges értékeket a minden egyéb mezőben. (Amikor menti az új szállítmányozói rekordot, létrejön egy új szállítási mód, és a **Szállítási mód** mező beállítása automatikus lesz.)

1. A **Díjazási profilok** gyorslapon válassza az **Új** lehetőséget a díjazási profil rácshoz történő hozzáadásához.
1. Állítsa be a következő értékeket az új profilhoz:

    - **Díjazási profil:** *Bemutató szállítmányozói szolgáltatás*
    - **Név:** *Bemutató szállítmányozói szolgáltatás*
    - **Díjazási motor:** *Bemutató díjazási motor*

    Igény szerint adjon meg tetszőleges értékeket a minden egyéb mezőben.

1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.

A szállítmányozók beállításának módjáról bővebben lásd: [Szállítmányozók beállítása](../transportation/tasks/set-up-shipping-carriers.md).

#### <a name="set-up-carrier-service-accounts"></a>Szállítmányozói szolgáltatás fiókjainak beállítása

Szállítmányozói szolgáltatási fiók beállításához kövesse az alábbi lépéseket.

1. Lépjen a **Szállításkezelés \> Beállítás \> Díjazás \> Szállítmányozó szolgáltatási fiókja** elemre.
1. A műveleti ablakpanelen válassza ki az **Új** lehetőséget, ha hozzá szeretne adni egy szállítmányozói szolgáltatási fiókot.
1. Állítsa be a következő értékeket az új fiókhoz:

    - **Szállítmányozó:** *Bemutató szállítmányozó*
    - **Szállítmányozói szolgáltatás:** *Bemutató szállítmányozói szolgáltatás*
    - **Szállítmányozó vevői számlaszáma:** Az a szállítmányozói vevői számlaszám, amely a szállítmányozóval létesíthető kapcsolat ellenőrzésére és hitelesítésére szolgál. A szállítmányozó meg fogja adni ezt az értéket. Ha bemutatószolgáltatást használ, akkor megadhat egy tetszőleges értéket.
    - **Telephely:** *6*
    - **Raktár:** *62*

    > [!NOTE]
    > Gyakran a **Szállítmányozó vevői számlaszáma** az egyetlen olyan érték, amely a kapcsolat hitelesítéséhez szükséges. Ha azonban a szállítmányozó további hitelesítési paramétereket igényel, a szervezetnek testre kell szabnia ezt a lapot, hogy szükség szerint további mezőket adjon hozzá.

#### <a name="set-up-a-container-packing-policy"></a>Tárolók csomagolási irányelvének beállítása

Tárolók csomagolási irányelvének beállításához kövesse az alábbi lépéseket.

1. Ha még nem állított be ZPL-nyomtatódefiníciót, állítsa be a Dokumentumirányítási ügynök alkalmazás segítségével. További információk: [Dokumentumnyomtatás áttekintése](../../fin-ops-core/dev-itpro/analytics/print-documents.md) és kapcsolódó témakörök.
1. Ugorjon a **Raktárkezelés \> Beállítás \> Tárolók \> Tárolócsomagolási házirendek** pontra.
1. A műveleti ablakpanelen válassza ki az **Új** lehetőséget egy tárolócsomagolási irányelv hozzáadásához.
1. Az új irányelv fejlécében adja meg a következő értékeket:

    - **Tárolócsomagolási irányelv:** *Bemutató csomagolási irányelv*
    - **Leírás:** Az irányelv leírása

1. Az **Áttekintés** gyorslapon állítsa be a következő értékeket:

    - **Raktár:** *62*
    - **Végső szállítmány alapértelmezett helye:** *Baydoor*
    - **Tömegegység:** *KG*
    - **Tároló záró irányelve:** *Automatikus kiadás*
    - **Tárolókiadási irányelv:** *Elérhetővé tétel a végleges kiszállítási helyen*

1. A **Tároló jegyzékfájlja** gyorslapon állítsa be a következő értékeket:

    - **Automatikus jegyzékfájl tárolózáráskor:** *Igen*
    - **Tárolóra vonatkozó jegyzékfájl-követelmények:** *Szállításkezelés*
    - **Tároló tartalmának nyomtatása:** *Nem*

1. A **Szállítmányozói címke nyomtatása** gyorslapon állítsa be a következő értékeket:

    - **Tároló levélcímkéjének nyomtatása:** *Mindig*
    - **Nyomtató neve:** Annak a ZPL-nyomtatónak a neve, amely a levélcímkéket nyomtatja

#### <a name="set-up-a-packing-profile"></a>Csomagolási profil beállítása

Csomagolási profil beállításához kövesse az alábbi lépéseket:

1. Ugorjon a **Raktárkezelés \> Beállítás \> Csomagolás \> Csomagolási profilok** pontra.
1. A Művelet panelen válassza ki az **Új** lehetőséget, ha hozzá szeretne adni egy csomagolási profilt a rácshoz.
1. Állítsa be a következő értékeket az új profilhoz:

    - **Csomagolási profil azonosítója:** *Bemutató csomagolási profil*
    - **Leírás:** A profil leírása
    - **Tárolócsomagolási irányelv:** *Bemutató csomagolási irányelv*
    - **Tároló-azonosító mód:** *Automatikus*
    - **Tárolótípus:** *SmallBox*

#### <a name="set-up-a-customer-to-use-the-sps-carrier"></a>Vevő beállítása az SPS-szállítmányozó használatára

A következő lépések szerint beállíthatja a vevőt, hogy a létrehozott szállítmányozót használni tudja.

1. Ugorjon a **Kintlevőségek \> Vevők \> Minden vevő** pontra.
1. Keresse meg és válassza ki az *US-027* vevőt a rácson.
1. A Művelet panel **Általános** lapján, a **Beállítás** csoportban válassza a **Szállítmányozó vevői számla** lehetőséget.
1. A **Szállítmányozó vevői számlák** lapon, a Műveleti panelen válassza az **Új lehetőséget**, ha számlát szeretne hozzáadni a rácshoz.
1. Állítsa be a következő értékeket az új fiókhoz:

    - **Szállítmányozó:** *Bemutató szállítmányozó*
    - **Szállítmányozó vevői számlaszáma:** *12345* (Az érték ebben az esetben nem fontos, de hivatkozni fognak rá a következő szakaszban.)

### <a name="go-through-the-example-scenario"></a>A példaforgatókönyv áttekintése

Miután az előző szakaszban leírt módon beállította az összes mintaadatot, készen áll a példaforgatókönyv áttekintésére.

#### <a name="create-a-sales-order-and-process-the-work"></a>Értékesítési rendelés létrehozása és a munka feldolgozása

Értékesítési rendelés létrehozásához kövesse az alábbi lépéseket.

1. Ugorjon az **Értékesítés és marketing \> Értékesítési rendelések \> Minden értékesítési rendelés** pontra.
1. Új értékesítési rendelés létrehozásához kattintson az **Új** elemre.
1. Az **Értékesítési rendelés létrehozása** párbeszédpanelen, a **Vevői számla** mezőben állítsa a mező értékét *US-027* értékre.
1. Válassza az **OK** gombot a beszerzési rendelés létrehozásához és a párbeszédpanel bezárásához.
1. A program megnyitja az új értékesítési rendelést. Az **Értékesítési rendelés fejléc** gyorslapon állítsa a **Szállítmányozó vevői számlaszáma** mezőt arra az értékre, amelyet korábban kiválasztott ehhez a vevőhöz(*12345*).
1. Az **Értékesítésirendelés-sorok** szakaszban adjon hozzá egy értékesítési sort, és állítsa be a következő értékeket:

    - **Cikkszám:** *A0002*
    - **Mennyiség:** *1*
    - **Telephely:** *6*
    - **Raktár:** *62*

1. Váltson a **Fejléc** nézetre.
1. A **Szállítás** gyorslapon állítsa be a következő értékeket:

    - **Szállítmányozó:** *Bemutató szállítmányozó*
    - **Szállítmányozói szolgáltatás:** *Bemutató szállítmányozói szolgáltatás*

1. Váltson vissza a **Sorok** nézetre. Ha a program megkérdezi, hogy frissíti-e a szállítási módot az értékesítési sorokban, válassza az **Igen** lehetőséget.
1. Az **Értékesítésirendelés-sorok** szakaszban válassza ki a korábban beállított rendeléssort, majd válassza a **Készlet \> Foglalás** lehetőséget.
1. A **Foglalás** oldalon válassza ki az **Adag foglalása** lehetőséget, hogy lefoglalja a kiválasztott sor teljes mennyiségét a raktárban.
1. Zárja be a **Foglalás** lapot, hogy visszatérjen az értékesítési rendeléshez.
1. Válassza ki a művelet ablaktáblán a **Raktár** lapon a **Kiadás raktárba** lehetőséget.

    A létrehozott munka a kitárolási helyről a csomagolóhelyre mozgatja a cikkeket.

1. Az **Értékesítési rendelés sorai** szakaszban válassza ki a **Raktár \> Szállítmány részletes adatai** lehetőséget.
1. A **Szállítmány részletei** lapon jegyezze fel a szállítmány azonosítóját. Erre akkor lesz szüksége, amikor a szállítmányt a csomagolóállomáson csomagolja.
1. Zárja be a **Szállítmány adatai** lapot, hogy visszatérjen az értékesítési rendeléshez.
1. Jegyezze fel az értékesítési rendelés számát, majd kattintson a **Raktárkezelés \> Munka \> Minden munka** pontra.
1. Az értékesítési rendelés számának használatával keresse meg és válassza ki a rendeléshez létrehozott munkát.
1. A Művelet panelen a **Munka** lapon válassza a **Munka befejezése** menüpontot.
1. A **Munka befejezése** lapon, a **Felhasználói azonosító** mezőben válassza ki a felhasználói azonosítót. Majd a műveleti ablaktáblán válassza ki a **Munka ellenőrzése** elemet.
1. Ha a munka megfelel az ellenőrzésen, válassza a **Munka befejezése** elemet a Művelet panelen.

    A munka készként van megjelölve a cikkeknek a csomagoló állomásra való mozgásának szimulálása érdekében.

#### <a name="pack-the-shipment"></a>A szállítmány csomagolása

A szállítmány csomagolásához kövesse az alábbi lépéseket.

1. Ugorjon a **Raktárkezelés \> Beállítás \> Dolgozó** pontra, és győződjön meg róla, hogy a felhasználói fiók társítva van egy dolgozói fiókhoz a raktárkezelésnél.
1. Nyissa meg a **Raktárkezelés \> Kitárolás és tárolólétrehozás \> Csomagolás** menüt.
1. A **Csomagolóállomás kiválasztása** párbeszédpanelen adja meg a következő értékeket:

    - **Telephely:** *6*
    - **Raktár:** *62*
    - **Hely:** *Csomag*
    - **Csomagolási profil azonosítója:** *Bemutató csomagolási profil*

1. Válassza ki az **OK** lehetőséget.
1. Megjelenik a **Csomag** oldal. Egy termelési forgatókönyvben a dolgozó beolvas egy azonosítótáblát vagy szállítmányazonosítót. Ehhez a forgatókönyvhöz azonban nyissa meg a **Minden szállítmány** lapot, és keresse meg a szállítmányhoz most létrehozott számot. Ezt követően írja be ezt az értéket az **Azonosítótábla vagy szállítmány** mezőjébe a **Csomag** oldalon. Másik lehetőségként adja meg annak a szállítmánynak az azonosítóját, amelyről korábban megjegyzést készített.
1. A műveleti ablaktáblán kattintson az **Új tároló** elemre.
1. A megjelenő párbeszédpanelen megjelennek az új tároló részletei. Hagyja meg az alapértelmezett értékeket, majd válassza az **OK** elemet.
1. A **Csomag** lapon a **Cikk csomagolása** gyorslapon az **Azonosító** mezőjében válassza az *A0002* elemet a cikk csomagolására. A cikk bekerül a tárolóba.
1. A Művelet panelen válassza a **Szállítmányhoz tartozó tárolók** elemet.

    A megjelenő **Szállítmányhoz tartozó tárolók** oldalon található egy sor az imént létrehozott tárolóhoz. A sor **Tároló jegyzékfájl-azonosító** mezője azonban jelenleg üres, mivel ön még nem kapta meg a levélcímkét és a követési számot a szállítmányozótól.

1. A műveleti ablaktáblán kattintson az **Tároló bezárása** elemre.
1. A **Tároló bezárása** párbeszédpanelen állítsa *1 kg-ra* a **Bruttó tömeg** mezőt, majd válassza az **OK** gombot.

    A korábban kiválasztott ZPL-nyomtatóra most rá kell nyomtatni a levélcímkét. Az alábbi példához hasonlóan jelenik meg.

    ![Példa levélcímkére](media/sps-label-example.png "Példa levélcímkére")

1. Figyelje meg, hogy a **Tároló jegyzékfájl-azonosítója** és a **Teljes fuvar** érték hozzá lett adva a címkéhez.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]