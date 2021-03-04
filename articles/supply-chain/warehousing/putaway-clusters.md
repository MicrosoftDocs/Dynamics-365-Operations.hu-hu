---
title: Betárolási fürtök
description: A betárolási fürtökkel egyszerre több azonosítótábla felvételére is lehetőség van, majd a különböző helyeken történő betárolására. Rendkívül hasznosak lehetnek a kiskereskedelmi vállalatok számára, ahol az azonosítótábla általában nem teljes raklapnyi készletet jelentenek.
author: Mirzaab
manager: tfehr
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: 6a330ddccbd17c92443232fc8488e36a59235773
ms.sourcegitcommit: cfd84321fba38e02e270d361df369a536a48efa3
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/11/2020
ms.locfileid: "4512330"
---
# <a name="putaway-clusters"></a>Betárolási fürtök

[!include [banner](../includes/banner.md)]

A betárolási fürtökkel egyszerre több azonosítótábla felvételére is lehetőség van, majd a különböző helyeken történő betárolására. Ezt az folyamatot gyakran nevezik *gyűjtőszállítmánynak*. A betárolási fürtök rendkívül hasznosak lehetnek a kiskereskedelmi vállalatok számára, ahol az azonosítótábla általában nem teljes raklapnyi készletet jelentenek. 

## <a name="turn-on-the-cluster-putaway-feature"></a>A fürtbetárolási funkció bekapcsolása

A funkció használata előtt be kell azt kapcsolnia saját rendszerében. A rendszergazdák használhatják a [Funkciókezelés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) munkaterületet a funkció állapotának ellenőrzéséhez, és szükség esetén bekapcsolásához. A funkció a következő módon jelenik meg:

- **Modul:** *Raktárkezelés*
- **Szolgáltatás neve:** *Fürtbetárolási funkció*

## <a name="setup-for-the-example-scenario"></a>Beállítás a példahelyzethez

### <a name="cluster-profiles"></a>Fürtprofilok

A betárolási fürt profilja határozza meg, hogy hova kerülnek a cikkek a bevételezés időpontjában a cikkhez társított hely alapján. Ha különböző fürtökre van szükség, akkor minden mobileszköz-menüelemhez egy másik betárolási fürtöt kell létrehozni.

1. Kattintson a **Raktárkezelés \> Beállítás \> Mobileszköz \> Fürtprofilok** elemre.
1. A Műveleti ablaktáblán kattintson az **Új** elemre.
1. A **Fejléc** nézetben állítsa be a következő értékeket:

    - **Betárolási fürt profiljának azonosítója:** *Fürtbetárolás*
    - **Betárolási fürt profiljának neve:** *Fürtbetárolás*
    - **Fürttípus:** *Betárolási*
    - **Sorszám:** Fogadja el az alapértelmezett értéket.

1. A **Mentés** gombra kattintva elérhetővé válnak az **Általános** gyorslap kötelező mezői.
1. Az **Általános** gyorslapon állítsa be a következő értékeket:

    - **Fürthozzárendelés ütemezése:** *Bevételezésnél*

        Ez a mező határozza meg, hogy a betárolási fürtöt azonnal hozzá kell-e rendelni a készlet beérkezésekor, vagy később kell rendezni.

    - **Fürthozzárendelési szabály:** *Manuális*

        Ez a mező meghatározza, hogy a fürt hozzárendelését automatikusan határozza meg a rendszer, vagy manuálisan a felhasználó.

    - **Utasításkód:** Hagyja üresen ezt a mezőt.
    - **Betárolási fürt keresése:** *Bevételezés*

        A következő értékek állnak rendelkezésre:

        - **Bevételezés** – A hely keresése azonnal, a bevételezés során.
        - **Fürt lezárása** – A hely keresése a fürt lezárásakor.
        - **Felhasználó által irányított** – A hely keresése akkor történik, amikor az azonosítótábla kitárolásra kerül a betárolási fürtből. Ebben az esetben a betárolási munka létrehozásakor nincs megadva hely. Maga a betárolás során a felhasználónak be kell olvasnia az azonosítótáblát vagy munkaazonosítót a betárolási lépés kezdeményezéséhez. A rendszer ezután megkeresi a betárolási helyet, és megadja a felhasználó számára, hogy hová tegye a kitárolt mennyiséget.

    - **Betárolási fürt felhasználónként:** *Nem*

        Ez a mező határozza meg, hogy az egyes fürtöket felhasználónként kell-e egyedivé tenni a fürtök automatikus hozzárendelésekor. Csak akkor érhető el, ha a **Fürthozzárendelési szabály** mezője *Automatikus* értékre van állítva.

    - **Egység korlátozása:** Hagyja üresen ezt a mezőt.

        Ez a mező határozza meg, hogy melyik egységet kell fogadnia a profilnak, hogy érvényes legyen. Ha üresen marad, akkor az összes egység érvényes lesz.

    - **Munka a szünetig:** *Egyéni*

        Ez a mező határozza meg, hogy az összes készletet összesíteni kell-e (a fürtazonosító és az azonosítótábla használatával) egy adott azonosítótáblára, amikor egy fürt le van zárva, és hogy a betárolás egyetlen azonosítótáblaként történjen vagy külön, a bevételezett azonosítótáblákra. Ez a mező nem érhető el, ha a **Betárolási fürt keresése** mező a *Bevételezés* értékre van állítva.

    - **Fürt megőrzése szülő azonosítótáblaként:** *Nem*

        Ha ez a beállítás *Igen* értékre van állítva, akkor az adott lépés végrehajtásakor a fürtazonosító egy szülő azonosítótáblává válik, és a fürtazonosító minden cikke ehhez a szülő azonosítótáblához lesz kapcsolva.

1. A **Fürt rendezése** gyorslapon meghatározhatja a betárolás rendezési feltételeit. Válassza az **Új** lehetőséget az eszköztáron egy sor hozzáadásához, és állítsa be a következő értékeket:

    - **Sorszám:** Fogadja el az alapértelmezett értéket.
    - **Mező neve:** *WMSLocationId*

        Ez a mező azt a mezőt határozza meg, amelyet ennek a sornak rendezési feltételként kell használnia.

    - **Rendezés:** *Növekvő*

        Ez a mező határozza meg, hogy a rendezés növekvő vagy csökkenő sorrendben történjen-e.

1. A **Fürt munkasablonja** gyorslapon válassza az **Új** parancsot az eszköztáron egy sor hozzáadásához, majd állítsa be a következő értékeket hozzá:

    - **Munkarendelés típusa:** *Beszerzési rendelések*
    - **Munkasablon:** *61 közvetlen beszerzési rendelés*

1. Válassza a művelet panel **Mentés** elemét, majd válassza a **Lekérdezés szerkesztése** elemet.
1. A **Fürtbetárolás** párbeszédpanelen, a **Tartomány** lapon a **Hozzáadás** gombbal adjon hozzá egy második sort a lekérdezéshez. Ezután frissítse a lekérdezés sorait a következő táblázatban látható módon.

    | Tábla | Származtatott tábla | Mező | Feltételek |
    |---|---|---|---|
    | Munka | Munka | Raktár | *61* |
    | Munka | Munka | Munkaazonosító | Ezt a mezőt hagyja üresen. |

1. Az **OK** gombra kattintva mentse a lekérdezést, és zárja be a párbeszédpanelt.
1. A művelet panelen válassza a **Mentés** elemet, majd zárja be a lapot.

> [!IMPORTANT]
> A fürtprofil azon mezői, amelyek elhalványítva jelennek meg, ha a **Fürtazonosító létrehozása** *Igen* értékre van beállítva, nem érhetők el, és nem lesznek figyelembe véve a funkció használata esetén.

### <a name="mobile-device-menu-items"></a>Mobileszköz menüpontjai

Ehhez a funkcióhoz két új mobileszköz-menüelem használható. A **Bevételezés és fürt rendezése** menüpont a bevételezett készletnek egy betárolási fürtbe történő rendezéséhez használatos. A **Fürtbetárolás** menüelem a fürt betárolásához használatos, miután az hozzárendelésre került.

#### <a name="receive-and-sort-cluster"></a>Fürt bevételezése és rendezése

Hozzon létre egy új mobileszköz-menüelemet a készlet bevételezéséhez és egy fürtbe rendezéséhez. Ez a menüelem a készlet bevételezését követően hozza létre a bejövő munkát, ami azt jelzi, hogy a bevételezés menüpontot fogja használni a betárolási fürtök esetében.

> [!NOTE]
> A **Fürt bevételezése és rendezése** menüelem a következő bevételezési menüelemekkel használható:
>
> - Beszerzésirendelés-sor bevételezése
> - Beszerzési rendelési cikk bevételezése
> - Rakomány – cikk bevételezése

1. Lépjen a **Raktárkezelés \> Beállítás \> Mobileszköz \> Mobileszköz-menüelemek** részre.
1. A Műveleti ablaktáblán kattintson az **Új** elemre.
1. A **Fejléc** nézetben állítsa be a következő értékeket:

    - **Menüelem neve:** *Fürt bevételezése és rendezése*
    - **Cím:** *Fürt bevételezése és rendezése*
    - **Mód:** *Munka*
    - **Meglévő munka használata:** *Nem*

1. Az **Általános** gyorslapon állítsa be a következő értékeket:

    - **Munkalétrehozási folyamat:** *Beszerzési rendelési cikk bevételezése*
    - **Azonosítótábla létrehozása:** *Igen*
    - **Betárolási fürt hozzárendelése:** *Igen*

        > [!NOTE]
        > A **Betárolási fürt hozzárendelése** beállítás csak az egylépéses *Munkalétrehozási folyamat* betárolási tevékenységéhez áll rendelkezésre.

    Az fennmaradó mezőkben hagyja meg az alapértelmezett értékeket.

1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.

#### <a name="cluster-putaway"></a>Fürtbetárolás

Hozzon létre egy új mobileszköz-menüelemet, amellyel a fürtöt betárolja, miután hozzárendelte a rendszer.

1. Lépjen a **Raktárkezelés \> Beállítás \> Mobileszköz \> Mobileszköz-menüelemek** részre.
1. A Műveleti ablaktáblán kattintson az **Új** elemre.
1. A **Fejléc** nézetben állítsa be a következő értékeket:

    - **Menüelem neve:** *Fürtbetárolás*
    - **Cím:** *Fürtbetárolás*
    - **Mód:** *Munka*
    - **Meglévő munka használata:** *Igen*

1. Az **Általános** gyorslapon az **Irányító** mezőt *Fürtbetárolás* értékre kell beállítani. Az fennmaradó mezőkben hagyja meg az alapértelmezett értékeket.
1. A **Munkaosztályok** gyorslapon állítsa be a mobileszköz-menüelem érvényes munkaosztályát:

    - **Munkaosztály azonosítója:** *Beszerzés*
    - **Munkarendelés típusa:** *Beszerzési rendelések*

1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.

### <a name="mobile-device-menu"></a>Mobileszköz menü

Adja hozzá a most létrehozott menüelemeket a mobilalkalmazás bejövő menüjéhez.

1. Lépjen a **Raktárkezelés \> Beállítás \> Mobileszköz \> Mobileszköz menü** elemre.
1. A műveleti ablaktáblán válassza a **Szerkesztés** lehetőséget.
1. A menülistán válassza a **Bejövő** elemet.
1. A **Rendelkezésre álló menük és menüelemek** listájában keresse meg és válassza ki a **Fürt bevételezése és rendezése** menüelemet.
1. Válassza a jobbra mutató nyílgombot a kiválasztott menüelem **Menüstruktúra** listában való elhelyezéséhez.
1. A felfelé vagy lefelé mutató nyíllal a menüben mozgathatja a menüelemet a kívánt pozícióba.
1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.
1. A fennmaradó menüelemek hozzáadásához ismételje meg a 4–7. lépést.

    - Fürt hozzárendelése
    - Fürtbetárolás

## <a name="example-scenario"></a>Példaforgatókönyv

Ez a forgatókönyv szimulálja a betárolási fürtök feldolgozását.

### <a name="create-a-purchase-order"></a>Beszerzési rendelés létrehozása

1. Nyissa meg a következőt: **Kötelezettségek \> Beszerzési rendelések \> Minden beszerzési rendelés**.
1. A Műveleti ablaktáblán kattintson az **Új** elemre.
1. Az **Beszerzési rendelés létrehozása** párbeszédpanelen adja meg a következő értékeket:

    - **Szállítói számla:** *1001*
    - **Raktár:** *61*

1. Válassza ki az **OK** lehetőséget.

    Megjelenik a **Minden beszerzési rendelés** lap.

1. A **Minden beszerzési rendelés** lap **Beszerzési rendelés sorai** gyorslapján a **Sor hozzáadása** gombbal adja hozzá a következő sorokat:

    - Beszerzési rendelés 1. sora:

        - **Cikkszám:** *A0001*
        - **Mennyiség:** *10*

    - Beszerzési rendelés 2. sora:

        - **Cikkszám:** *A0002*
        - **Mennyiség:** *20*

    - Beszerzési rendelés 3. sora:

        - **Cikkszám:** *M9215*
        - **Mennyiség:** *30*

1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.
1. Jegyezze fel a beszerzési rendelés számát.

### <a name="receive-inventory-and-put-it-away-from-the-mobile-device"></a>Készlet bevételezése és eltárolása a mobileszközről

#### <a name="receive-and-sort-the-inventory-into-a-cluster"></a>A készlet bevételezése és rendezése egy fürtbe

1. Jelentkezzen be a raktározási alkalmazásba olyan felhasználóként, aki a *61*. raktárban be van állítva.
1. Válassza a főmenü **Kimenő** elemét.
1. Válassza a **Bejövő** menü **Fürt bevételezése és rendezése** lehetőségét.
1. A **Ponum** mezőben adja meg a beszerzési rendelés számát.
1. Válassza az **OK** gombot (a pipa szimbólum gombja).
1. Válassza ki a **Cikk** mezőt, majd adja meg cikkszámként az *A0001* értéket, és válassza az **OK** gombot.
1. Válassza ki a **Mennyiség** mezőt, írja be a *10* értéket a számbillentyűzet használatával, majd jelölje be a jelölőnégyzetet.
1. A **Mennyiség** lapon jelölje be az **OK** (pipa gomb) lehetőséget, hogy megerősítse a megadott mennyiséget.
1. A **Cikk** feladatoldalon válassza az **OK** gombot a megadott *A0001* cikk jóváhagyásához.
1. Válassza ki a **Fürtazonosító** mezőt, és adjon meg egy értéket a létrehozni kívánt fürt azonosítójának hozzárendeléséhez.

    Az itt megadott azonosító akkor használatos, amikor a beszerzési rendelésen szereplő két cikk bevételezésre kerül.

1. Válassza ki az **OK** lehetőséget.

    Megjelenik a **Ponum** feladatoldal, és egy „Munka befejezve” üzenetet jelenít meg.

    Az *A0001* már bevételezésre került a *RECV* helyre, és a rendszer a 10. lépésben megadott fürtazonosítóhoz rendeli hozzá.

1. Ismételje meg a 4–11. lépést, ha a beszerzési rendelés maradék két cikkét szeretné bevételezni, és a fürtazonosítóhoz rendeli hozzá:

    - A *20* mennyiség az *A0002* cikkhez
    - A *30* mennyiség az *M9215* cikkhez

#### <a name="close-the-cluster"></a>A fürt bezárása

A fürtben lévő cikkek betárolása előtt le kell zárni a fürtöt.

1. A Supply Chain Management alkalmazásban nyissa meg a **Raktárkezelés \> Munka \> Kimenő \> Munkafürtök** elemet.
1. A **Munkafürtök** lap **Munkafürt** szakaszában keressen rá a korábban megadott fürtazonosítóra a **Fürtazonosító** mezőben.
1. Ha a fürt nem jelenik meg, lehet, hogy már lezárták. Ha meg szeretné állapítani, hogy a fürt le van-e zárva, jelölje be a **Lezárt munka megjelenítése** jelölőnégyzetet, és keresse meg a korábban megadott fürtazonosítót. Majd tegye a következők egyikét:

    - Ha a fürt le van zárva, akkor ugorja át az eljárás további lépéseit, és lépjen tovább a következő műveletre: [Fürt betárolása](#put-the-cluster-away).
    - Ha a fürt nincs lezárva, akkor az eljárás további lépéseivel zárja be manuálisan a fürtöt. Ezután lépjen tovább a következő eljárásra.

1. A **Munkafürt** szakaszban válassza ki a korábban megadott fürtazonosítót.
1. A művelet ablaktáblán kattintson az **Fürt lezárása** elemre.

    Miután a fürt le van zárva, már nem jelenik meg a **Munkafürt** szakaszban (hacsak nem jelöli be a **Lezárt munka megjelenítése** jelölőnégyzetet).

#### <a name="put-the-cluster-away"></a>Fürt betárolása

1. Jelentkezzen be a raktározási alkalmazásba olyan felhasználóként, aki a *61*. raktárban be van állítva.
1. Válassza a főmenü **Kimenő** elemét.
1. Válassza a **Bejövő** menü **Fürtbetárolás** elemét.
1. Válassza ki a **Fürtazonosító** lehetőséget, majd adja meg a lezárt fürtnél korábban megadott fürtazonosítót.
1. Válassza ki az **OK** lehetőséget.

    Megjelenik a **Fürtbetárolás: Kitárolás** oldal. A program megjeleníti a fürtazonosítót, a kitárolási helyet, a cikkeket (a *Több* érték jelenik meg), és a fürtben lévő teljes mennyiséget, amelyet ki kell tárolni.

1. Válassza ki az **OK** lehetőséget.

    Megjelenik a **Fürtbetárolás: Betárolás** oldal. A **Betárolás** utasításai határozzák meg a fürt azonosítóját, a betárolási helyet, a cikkeket, a teljes mennyiséget és az azonosítótábla azonosítóját a fürtön bevételezett cikkekhez.

    A lépés felülbírálásához vagy átadásához a szokásos lehetőségek állnak rendelkezésre.

    ![Fürtbetárolás: Betárolási oldal](media/Cluster_putaway-Put.png "Fürtbetárolás: Betárolási oldal")

1. A fürt betárolásának jóváhagyásához kattintson az **OK** gombra.

    Megjelenik a „Fürt befejezve” üzenet.

## <a name="notes-and-tips"></a>Megjegyzések és tippek

Azokban az esetekben, amikor a fürt azonosítója egy beágyazott raklap számára egy szülő azonosítótábla lesz, a program automatikusan beírja a betárolási pozíciót, amikor a rendszer beolvassa a fürtazonosítót. Nem kell több azonosítótáblát beolvasni akkor sem, ha az azonosítótábla-létrehozás manuálisra van állítva.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]