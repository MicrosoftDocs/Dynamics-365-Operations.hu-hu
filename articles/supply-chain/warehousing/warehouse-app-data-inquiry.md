---
title: Adatok lekérdezése a Warehouse Management mobilalkalmazás-kitérők segítségével
description: Ez a témakör azt ismerteti, hogyan kell konfigurálni az adat lekérdezési mobileszköz menüpontokat, és azokat használni a tölcsérek részeként.
author: perlynne
ms.date: 08/09/2022
ms.topic: article
ms.search.form: WHSMobileAppFlowStepListPage, WHSMobileAppFlowStepAddDetour,WHSMobileAppFlowStepDetourSelectFields
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2022-08-01
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: 39677ebfb9babeb7246ece4d27ab1813435ca12e
ms.sourcegitcommit: 3d7ae22401b376d2899840b561575e8d5c55658c
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/08/2022
ms.locfileid: "9427848"
---
# <a name="query-data-using-warehouse-management-mobile-app-detours"></a>Adatok lekérdezése a Warehouse Management mobilalkalmazás-kitérők segítségével

[!include [banner](../includes/banner.md)]

## <a name="feature-introduction"></a>Funkció bevezető

A vonalkód-beolvasásra való képesség biztosítása lehetővé teszi, hogy a Raktárkezelés mobilalkalmazás könnyen és pontos módon rögzítse az adatokat a raktári folyamatok részeként. A vonalkódok azonban időnként megsérülnek és olvashatatlanná válnak, vagy előfordulhat, hogy a szükséges adatok nem létezik vonalkódként az üzleti folyamatokban. Ilyen esetben az adatok manuális bevitele hosszú ideig is hosszú ideig tart, sőt, a helytelen adatok bevitelét is okozhatja. Az eredmények csökkenthetik a hatékonyságot és alacsonyabb szolgáltatási szintet.

A rugalmas adatbevallási folyamat segítségével a dolgozók egyszerűen megkeresik a szükséges adatokat a beágyazott Raktárkezelés mobilalkalmazások részeként, és szűrési beállításokat alkalmazhatnak, hogy csak a fontos adatok láthatók legyen. Emiatt a manuális kiválasztás gyorsabb és pontosabb.

Például a beszerzési rendelés bevételezése esetén a beszerzési rendelés számának meg kell egyeznie a érkező készlettel. Ennek a folyamatnak a részeként egyszerűen konfigurálhat olyan menüpontokat, amelyek a megfelelő beszerzési rendelési számok kártyalistanézetét biztosítják. Ily módon a gyors, pontról-kijelölés módszer használatával folytathatja a bevételi folyamatot. Ez a cikk példa eseteket mutat be, de ez a funkció bármelyik, vagy az összes Raktárkezelés mobilalkalmazás-folyamaton belül használható.

## <a name="turn-on-the-data-inquiry-flow-feature-and-its-prerequisites"></a>Az adat lekérdezési folyamat szolgáltatásának és előfeltételének bekapcsolása

A jelen cikkben ismertetett funkciók csak akkor használhatók, ha a következő eljárás szerint bekapcsolta a szükséges funkciókat.

1. Lépjen a **Rendszerfelügyelet \> Munkaterületek \> Funkciókezelés** részre. (További információ a <a0/<a2/<a2/4><a2/<a2 **Funkciókezelési** munkaterület, lásd [a Funkciókezelés áttekintését](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).)
1. Ha az Ellátásilánc-kezelés 10.0.28-as vagy korábbi verzióját futtatja, kapcsolja be a következő módon felsorolt funkciót:

    - **Modul:** *Raktárkezelés*
    - **Funkció neve:** *Raktáralkalmazás lépésutasításai*

    Ez a funkció előfeltétele a Raktárkezelés alkalmazás adatbevallési *folyamatának*. Az Ellátásilánc-kezelés 10.0.29-es verziója szerint kötelező, és nem lehet kikapcsolni. A *Raktári alkalmazás lépésutasítások* funkciójával kapcsolatos további információkért lásd: [Lépéscímek és utasítások testreszabása a Warehouse Management mobilalkalmazáshoz](mobile-app-titles-instructions.md).

1. A következő módon lehet bekapcsolni a felsorolt funkciókat:

    - **Modul:** *Raktárkezelés*
    - **Funkció neve:** *Warehouse Management alkalmazás elterelések*

    Ez a funkció előfeltétele a Raktárkezelés alkalmazás adatbevallési *folyamatának*. Az ellátásilánc-kezelés 10.0.29-es verziója alapértelmezés szerint be van kapcsolva. A Raktárkezelés alkalmazás *hibatárai funkcióval kapcsolatos további tudnivalókat*[lásd a Mobileszköz menüpontok lépéseit a Hibatúrák konfigurálása](warehouse-app-detours.md) oldalon.

1. Ha még nem bekapcsolta a Raktárkezelés alkalmazás-hibakezelési szolgáltatást, frissítse a mezőneveket a Raktárkezelés mobilalkalmazásban *úgy, hogy a Raktárkezelés* **\>\>\> beállítása mobileszköz-alkalmazás mezőnevére vált, és az Alapértelmezett beállítás létrehozása lehetőséget választja.** **·** Ismételje meg ezt a lépést minden olyan jogi személynél (vállalatnál), ahol a Raktárkezelés mobilalkalmazást használja. ovábbi információ: [A Raktárkezelés mobilalkalmazás mezőinek konfigurálása](configure-app-field-names-priorities-warehouse.md).
1. A következő módon lehet bekapcsolni a felsorolt funkciókat:

    - **Modul:** *Raktárkezelés*
    - **Funkció neve:** *Raktárkezelés alkalmazásadat-lekérdezési folyamata*

    Ez a funkció az ebben a cikkben ismertetett funkció.

## <a name="example-scenarios"></a>Példaforgatókönyvek

Ez a cikk a példa eseteket *mutatja be, hogyan használható a Raktárkezelés alkalmazás* adatbevallása folyamat a beszerzési bevételezési folyamat javítására. Az esetek a szokásos mintaadatokat használják, amely a Beszerzés fogadása nevű *folyamatot foglalja magában*. A folyamat kezdete a dolgozókat annak a beszerzési rendelési számnak a azonosítására kéri, amely ellenük fognak kapni. Ha a dolgozók könnyebben azonosítani fogják a beszerzési rendelést, [a következő új lekérdezési beállításokat feltéve tovább javíthatja a folyamat első oldalát](warehouse-app-detours.md):

- **Beszerzési számlák szállítók szerint** – egy lap megnyitása, amely arra kéri a dolgozókat, hogy adja meg a szállító nevét vagy a szállító nevének egy részét. Helyettesítő karaktereket is lehet használni. Ha például *egy* dolgozó a mai napon bejövő szállítást vár egy szállítótól, amely a nevében szerepel Benne, **\*** akkor beírhatja Azokat a kártyákat, amelyek nyitott beszerzési rendelésekhez tartoznak, és ez tartalmazza ezt a szöveget. Minden kártya számos mezőt tartalmaz, amelyek információt nyújtanak az egyes beszerzési rendelésekről. A kártyákat a szállító nevén kívül úgy is meg lehet tervezni, hogy a szállító számlaszámát, a szállítási dátumot és a dokumentum állapotát mutatják.
- **Munkaablakok** mai napig – olyan lap megnyitása, amely nem kéri a dolgozókat az adatok beíratára, hanem előre konfigurált szűrőket (például a mai dátumot) jeleníti meg. A lapon ezután a szűrőnek megfelelő kártyák egy része jelenik meg. A dolgozók úgy folytatják, hogy kijelölnek egy kártyát ahhoz a beszerzési rendeléshez, amelynél készleten lévő cikkeket regisztrálni fognak.
- **Termékcsoport-keresés cikk szerint** – egy lap megnyitása, amely arra kéri a dolgozókat, hogy olvassanak be minden, a készletbe érkezett cikk vonalkódját. A folyamat ezután felsorolja azokat a nyitott beszerzési rendeléseket, amelyek a beolvasott cikkszám sorait tartalmazzák. Egy olyan helyzet fedezésére, ahol egy vonalkód nem olvasható, a laphoz egy másik kereséssel is felvehető, ami azt jelenti, hogy a dolgozók cikkszámokat kereshetnek egy adott beszerzési rendelésen belül.

A dolgozó minden esetben egy kártya kiválasztásával azonosítja a beszerzési rendelést, és az első oldalra visszaküldi, amelyen a kiválasztott beszerzési rendelés száma látható. A dolgozó ezt követően folytathatja a bejövő készletcikkek regisztrálásának folyamatát.

## <a name="enable-sample-data"></a>Mintaadatok engedélyezése

Az ebben a példában ismertetett eseteken való munkához olyan rendszeren kell lennie, ahol telepítve vannak a [szokásos](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) bemutatóadatok. Ezenkívül a kezdés előtt *ki kell választania az USMF* jogi személyt (vállalatot).

## <a name="configure-the-mobile-device-menu-items"></a>A mobileszköz menüpontok konfigurálása

Ha minden új lekérdezési lehetőséget létre szeretne hozni, amit fel kell adni a folyamat első oldalára, be kell állítania azt mobileszköz menüelemként. Később a lekérdezési beállításokat elérhetővé teszi a beszerzés fogadási folyamatának *hibatáraként*.

### <a name="create-the-look-up-pos-by-vendor-menu-item"></a>A "Szállító szerint keresse meg a cikkeket" menüpont létrehozása

A következő **lépések segítségével létrehozhatja a Beszerzési lista szállító szerint** menüpontot.

1. Lépjen a **Raktárkezelés \> Beállítás \> Mobileszköz \> Mobileszköz-menüelemek** részre.
1. A munkaablakban az Új **gombra kattintva** adjon hozzá egy mobileszköz-menüpontot.
1. Állítsa be a következő értékeket az új menüelemhez:

    - **Menüelem neve:** *Beszerzési szállítók szerint*
    - **Cím:** *Beszerzési számlák szállítók szerint*
    - **Mód:** *Közvetett*

1. Az **Általános** gyorslapon állítsa be a következő értékeket:

    - **Tevékenységkód: Adat** *lekérdezése*
    - **Folyamatvezető használata:** *Igen* (a program automatikusan kiválasztja ezt az értéket.)
    - **Tábla neve:** *PurchTable* (Beszerzési rendelési számokat szeretne keresni ebből a táblából.)

1. A munkaablakban válassza **a Lekérdezés** szerkesztése lehetőséget a kijelölt alaptáblán (ebben az esetben a beszerzési rendelések tábláján) alapuló lekérdezés meghatározásához.
1. A lekérdezésszerkesztő Tartomány **lapján** adja hozzá a következő sorokat a rácshoz.

    | Táblázat | Származtatott tábla | Mező | Feltételek |
    |---|---|---|---|
    | Beszerzési rendelések | Beszerzési rendelések | Beszerzési rendelés állapota | Nyitott rendelés |
    | Beszerzési rendelések | Beszerzési rendelések | Kiszállítási dátum | (dayRange(-10,10)) |
    | Beszerzési rendelések | Beszerzési rendelések | Szállító neve | |

1. Válassza ki az **OK** lehetőséget.

    Ebben a példában az új menüelem úgy van beállítva, hogy megtalálja az olyan nyitott beszerzési rendeléseket, amelyek az elmúlt 10 nap és 10 nappal később bármikor megérkeznek.

    A lekérdezésben a Szállító **nevének** *Feltétel* oszlopa üresen maradt. Ennek megfelelően a dolgozók meg tudják adni ezt az értéket a Raktárkezelés mobilalkalmazás használata közben.

    Ha meg szeretné adni, hogyan legyen rendezve a lista, **a rendezést a Rendezés lapon lehet** beállítani.

1. A lekérdezés meghatározásán kívül ki kell választania, hogy mely mezők jelennek meg a kártyákon a lekérdezési listaoldalon. Ezért a műveletpanelen válassza ki a **Mezőlistát**.
1. A Mezőlista **lapon** állítsa be a következő értékeket:

    - **1. megjelenítési mező:** *PurchId* (Ez a mező lesz látható minden egyes kártya fejléceként.)
    - **2. megjelenítési mező:** *PurchStatus*
    - **3. megjelenítési mező:** *PurchName*
    - **4. megjelenítési mező:** *OrderAccount*
    - **5. megjelenítési mező:** *DeliveryDate*
    - **6. megjelenítési mező:** *displayDocumentStatus() (Ez* az érték egy megjelenítési metódus, ahogy a "()" a végén látható.)

1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget. Ezután zárja be az oldalt.

### <a name="create-the-look-up-pos-for-today-menu-item"></a>Hozza létre a "Ma keresse meg a termékeket" menüpontot.

A következő **lépésekkel hozza** létre a mai menüelemhez a kereső alkalmazásokat.

1. Lépjen a **Raktárkezelés \> Beállítás \> Mobileszköz \> Mobileszköz-menüelemek** részre.
1. A munkaablakban az Új **gombra kattintva** adjon hozzá egy mobileszköz-menüpontot.
1. Állítsa be a következő értékeket az új cikkhez:

    - **Menüelem neve:** *Az adott naphoz keresse meg a termékeket.*
    - **Cím:** *Az egyenl<a2/201><a2/<a*
    - **Mód:** *Közvetett*

1. Az **Általános** gyorslapon állítsa be a következő értékeket:

    - **Tevékenységkód: Adat** *lekérdezése*
    - **Folyamatvezető használata:** *Igen* (a program automatikusan kiválasztja ezt az értéket.)
    - **Tábla neve:** *PurchTable* (Beszerzési rendelési számokat szeretne keresni ebből a táblából.)

1. A munkaablakban válassza **a Lekérdezés** szerkesztése lehetőséget a kijelölt alaptáblán (ebben az esetben a beszerzési rendelések tábláján) alapuló lekérdezés meghatározásához.
1. A lekérdezésszerkesztő Tartomány **lapján** adja hozzá a következő sorokat a rácshoz.

    | Táblázat | Származtatott tábla | Mező | Feltételek |
    |---|---|---|---|
    | Beszerzési rendelés | Beszerzési rendelés | Beszerzési rendelés állapota | Nyitott rendelés |
    | Beszerzési rendelés | Beszerzési rendelés | Kiszállítási dátum | (Nap(0)) |

1. Válassza ki az **OK** lehetőséget.

    Ebben a példában az új menüelem úgy van beállítva, hogy megkeresse a mai napon várható nyitott beszerzési rendeléseket.

    Ha meg szeretné adni, hogyan legyen rendezve a lista, **a rendezést a Rendezés lapon lehet** beállítani.

1. A lekérdezés meghatározásán kívül ki kell választania, hogy mely mezők jelennek meg a kártyákon a lekérdezési listaoldalon. Ezért a műveletpanelen válassza ki a **Mezőlistát**.
1. A Mezőlista **lapon** állítsa be a következő értékeket:

    - **1. megjelenítési mező:** *PurchName* (Ez a mező lesz látható minden egyes kártya fejléceként.)
    - **2. megjelenítési mező:** *PurchId*
    - **3. megjelenítési mező:** *PurchStatus*
    - **4. megjelenítési mező:** *DlvMode*
    - **5. megjelenítési mező:** *DlvTerm*
    - **6. megjelenítési mező:** *OrderAccount*
    - **7. megjelenítési mező:** *VendorName() (Ez* az érték egy megjelenítési metódus, ahogy a "()" a végén látható.)

1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget. Ezután zárja be az oldalt.

### <a name="create-the-look-up-pos-by-item-menu-item"></a>A "Cikkek szerint keresse meg a cikkeket" menüpont létrehozása

A következő **lépések segítségével létrehozhatja** a cikk alapján létrehozott cikkeket.

1. Lépjen a **Raktárkezelés \> Beállítás \> Mobileszköz \> Mobileszköz-menüelemek** részre.
1. A munkaablakban az Új **gombra kattintva** adjon hozzá egy mobileszköz-menüpontot.
1. Állítsa be a következő értékeket az új cikkhez:

    - **Menüpont neve:** *Cikk szerint keresse meg a termékeket.*
    - **Cím:** *Cikkek szerint keresse meg a termékeket.*
    - **Mód:** *Közvetett*

1. Az **Általános** gyorslapon állítsa be a következő értékeket:

    - **Tevékenységkód: Adat** *lekérdezése*
    - **Folyamatvezető használata:** *Igen* (a program automatikusan kiválasztja ezt az értéket.)
    - **Tábla neve:** *PurchLine* (A cikkszám alapján szeretne beszerzési rendelési számokat keresni a soradatokon keresztül.)

1. **A** munkaablakban válassza a Szerkesztés lekérdezést, és adja meg a kiválasztott alaptáblán (ebben az esetben a beszerzési rendelés sorait tartalmazó táblán) alapuló lekérdezést, *de a fejléchez kapcsolódó bármely érték használható a PurchTable* táblával való csatlakozással.
1. A lekérdezésszerkesztő Tartomány **lapján** adja hozzá a következő sorokat a rácshoz.

    | Táblázat | Származtatott tábla | Mező | Feltételek |
    |---|---|---|---|
    | Beszerzési rendelés sorai | Beszerzési rendelés sorai | Sor állapota | Nyitott rendelés |
    | Beszerzési rendelés sorai | Beszerzési rendelés sorai | Kiszállítási dátum | (dayRange(-10,10)) |
    | Beszerzési rendelés sorai | Beszerzési rendelés sorai | Cikkszám | |

1. Válassza ki az **OK** lehetőséget.

    Ebben a példában az új menüelem úgy van beállítva, hogy megtalálja az olyan nyitott beszerzésirendelés-sorokat, amelyek az elmúlt 10 nap és 10 nappal később bármikor megérkeznek.

    A lekérdezésben a **Cikkszám** *Feltétel* oszlopa üresen maradt. Ennek megfelelően a dolgozók meg tudják adni ezt az értéket, amíg a Raktárkezelés mobilalkalmazást használják.

    Ha meg szeretné adni, hogyan legyen rendezve a lista, **a rendezést a Rendezés lapon lehet** beállítani.

1. A lekérdezés meghatározásán kívül ki kell választania, hogy mely mezők jelennek meg a kártyákon a lekérdezési listaoldalon. Ezért a műveletpanelen válassza ki a **Mezőlistát**.
1. A Mezőlista **lapon** állítsa be a következő értékeket:

    - **1. megjelenítési mező:** *PurchId* (Ez a mezőérték lesz a kártya fejléce.)
    - **2. megjelenítési mező:** *VendAccount*
    - **3. megjelenítési mező:** *PurchQty*
    - **4. megjelenítési mező:** *PurchUnit*
    - **5. megjelenítési mező:** *PurchStatus*

1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget. Ezután zárja be az oldalt.

## <a name="add-the-new-mobile-device-menu-items-to-a-menu"></a>Az új mobileszköz menüelemek hozzáadása menühöz

A három új mobileszköz menüpont készen áll arra, hogy hozzáadja a mobileszköz menühöz. Ezt a feladatot be kell fejeződni, és a menüpontok csak akkor használhatók meg halasztási folyamat részeként. Ebben a példában új almenüt hoz létre, és hozzáadja az új menüpontokat.

1. Lépjen a **Raktárkezelés \> Beállítás \> Mobileszköz \> Mobileszköz menü** elemre.
1. A Műveleti ablaktáblán kattintson az **Új** elemre.
1. Állítsa be a következő értékeket az új rekord fejlécében:

    - **Név:** *Lekérdezés*
    - **Leírás:** *Lekérdezés*

1. Az Elérhető **menük és menüpontok** listáról válassza ki az előbb létrehozott mobileszköz-menüpontok közül az elsőt. Ezután a jobbra nyílgombbal áthelyezheti az elemet a menüstruktúra **listájára**.
1. Ismételje meg az előző lépést a másik két új menüpontmal.
1. A bal oldali listaablakban válassza a Fő **menüt**.
1. Az Elérhető **menük és** menüpontok listán **görgetés lefelé a Menük szakaszra**, és válassza az új **Lekérdezés** menüt. Ezután a jobbra nyílgombbal áthelyezheti az elemet a menüstruktúra **listájára**.

## <a name="configure-detours-in-your-mobile-device-steps"></a>A tölcsérek konfigurálása a mobileszköz lépéseinél

A **telepítés** *befejezéséhez a Mobileszköz lépéslapon található hibakonfigurációval kell hozzáadnia a három új mobileszköz-menüpontot a Beszerzés fogadása folyamat meglévő beszerzésirendelés-azonosító lépéséhez.*

1. Ugrás a **Raktárkezelés beállítása \> > mobileszköz lépéseinél \>**.
1. A Szűrő mezőben **adja** meg a *PONum mezőt*. Ezután válassza ki *a "PONum"* lépésazonosítót a legördülő listából.
1. Amíg a talált rekord ki van választva a rácsban, jelölje be **a Lépéskonfiguráció hozzáadása** lehetőséget a munkaablakban. A megjelenő legördülő párbeszédpanelen **állítsa a Menüelem** mezőt Beszerzés *fogadására*. Ezután az **OK gombra** kerül a párbeszédpanel bezárása.
1. Az új lépés konfigurációjának (**Beszerzés fogadása: PONum** **) részletező lapján, az Elérhető hibatúrák (menüpontok)** gyorslapon **válassza** az eszköztárOn a Hozzáadás lehetőséget.
1. A Detour **hozzáadása** párbeszédpanelen keresse **meg** és válassza ki a Korábban létrehozott szállítói menüelem szerint keresés menüpontot.
1. A **párbeszédpanel bezárásához és a kiválasztott menüelemnek a detours listához való hozzáadásához kattintson az OK** gombra.
1. Válassza ki az új hibajelet, majd válassza **az** eszköztáron elküldeni kívánt mezők kijelölése lehetőséget.
1. **A Küldés mező** **kiválasztása** párbeszédpanelen ne adjon hozzá semmit a Beszerzés fogadása szakaszhoz, mert a hiba menüelemnek nem szeretne értéket adni. A Beszerzési sorok visszahozása **szállító** szerint szakaszban azonban állítsa be a következő értéket ahhoz az üres sorhoz, amely már hozzá van adva a helyhez:

    - **Másolás beszerzési rendelés alapján beszerzési rendelés szerint** *·*
    - **Beillesztés beszerzési fogadásba:** *beszerzési rendelés*

1. Az **OK** gombbal zárja be a párbeszédpanelt.
1. Ismételje meg a 4–9. lépést a másik két új menüelemre is (**·** **A** mai naphoz keresse meg a termékeket, és cikk szerint keresse meg az egyes cikkeket). A beszerzési **rendelések szállító szerint** menüpontok szerint való lerendelése esetén nem szeretne adatokat küldeni ezeknek a cikkeknek, csak egy beszerzési rendelés számát szeretné visszaadni.
1. Zárja be a lapot.

## <a name="try-a-purchase-receiving-flow-that-has-a-data-inquiry-as-part-of-a-detour"></a>Próbálkozzon egy olyan beszerzési bevételi folyamatkal, amely adat lekérdezést tartalmaz egy hiba részeként.

A következő lépések szerint tesztelje az új mobilalkalmazás-beállításokat.

1. Hozzon létre több beszerzési rendelést, amelyek az 51-es raktárhoz vannak sorok.
1. Lépjen át a Raktárkezelés mobilalkalmazást futtató mobileszközre vagy emulátorra, majd jelentkezzen be a 51-es raktárba – a felhasználói azonosító legyen *51* és a jelszó legyen *1*.
1. Válassza a Mobilalkalmazás menü Bejövő, **majd** Beszerzés fogadása **parancsát**.

    A következő lapnak kell lennie, amely a három új menüpontot tartalmazza.

    ![Beszerzés bevétele a beszerzési rendelés száma alapján.](media/wma-purchase-receive-po-num-with-detours.png "Beszerzés bevétele a beszerzési rendelés száma alapján")

1. Próbálja ki a különböző lehetőségeket, és figyelje meg, hogy a listában kiválasztott kártyák egyikének kiválasztásával visszaküldheti a beszerzési rendelés számát.

    ![Beszerzés bevétele a beszerzési rendelés keresésének használatával szállító szerint, például 1.](media/wma-purchase-receive-lookup-po-vendor-keyin-detours.png "Beszerzés bevétele a beszerzési rendelések keresésének használatával szállító szerint, például 1")

    ![Beszerzés bevétele a beszerzési rendelés keresésének használatával szállító szerint, például 2.](media/wma-purchase-receive-lookup-po-vendor-detours.png "Beszerzés bevétele a beszerzési rendelés keresésének használatával szállító szerint, például 2")

> [!TIP]
> Ahelyett, hogy a Beszerzés bevételezve menüelem alapján keresné a **bevételi** folyamatot, elindíthat egy lekérdezési folyamatot (**\>\>** Fő lekérdezés – Beszerzési rendelések szállítók szerint) és meghívhat egy kitérőt, és a listában kiválasztva futtathatja a kívánt folyamatot. Ez a megközelítés akkor használható, ha a Mobileszköz lépéslapon definiálni lehet egy detour **értéket** ahhoz a lépéshez, amely **a** *GenericDataInquiryList lépésazonosító értéket tartalmazza.* [*·*](warehouse-app-detours.md) Ha a rendszer be van kapcsolva a Többszintű hibakezelés mobilalkalmazás funkcióhoz, szükség esetén további hiba is hozzáadható (ez a funkció két szint támpontot nyújt, és további szintek támogatása érdekében testre szabható).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
