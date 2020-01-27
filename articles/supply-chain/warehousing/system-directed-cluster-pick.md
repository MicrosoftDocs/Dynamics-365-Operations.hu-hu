---
title: Rendszer által irányított fürtkitárolás
description: Ez a témakör áttekintést nyújt a rendszer által fürtkitárolásról a Microsoft Dynamics 365 Supply Chain Management alkalmazásban.
author: Mirzaab
manager: AnnBe
ms.date: 12/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Supply Chain Management
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2019-12-31
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: c3b23a5d3b77bae89e4845bdff4ab20f95c46497
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917856"
---
# <a name="system-directed-cluster-picking"></a>Rendszer által irányított fürtkitárolás

[!include [banner](../includes/banner.md)]

A fürtkitárolás egy darabkitárolási folyamat, amely lehetővé teszi, hogy egy időben több rendelést is kitároljunk, és kivételezési fürtökhöz csoportosítsuk őket. Ezután csak egyszer kell felkeresnie a kivételezési helyet. Ez a funkció általában kis megrendelés kivételezéshez vagy esetmennyiségnél kisebb mennyiségekre használható.

Ha be van állítva a rendszer által irányított fürtkitárolás, a rendszer által létrehozott fürt alapján munkafejléceket is lehet fürtben kitárolni. A rendszer legfeljebb a fürtprofilban megadott számú pozíciókhoz tárolja ki fürtben a rendeléseket. Ezért a fürt manuális létrehozása nélkül egyszerre több rendelést is kitárolhat.

A rendszer által irányított fürtkitárolás alternatívát kínál a fürt kézi felépítéséhez, ahol fürtprofilt használnak a fürt létrehozásához. A fürtprofilban több, beállítással kapcsolatos sort kell definiálni a használata előtt:

- A **Pozíciók száma** a fürtre kerülő rendelések számára vonatkozik. Ezért, hogy megfelel a táskák számának.
- A **Fürt felbontása** meghatározza, hogy mikor kell felbontani a fürtöt.
- A **Fürtazonosító előállítása** határozza meg, hogy a rendszer létrehozza-e a fürtazonosítót, vagy a felhasználó adja-e meg azt.
- A **Rendezés ellenőrzési típusa** meghatározza, hogy szükség van-e pozícióellenőrzésre.

A rendszer által irányított fürtkitároláshoz egy új mobileszköz-menüelem használatos. A fürtprofil azonosítóját meg kell adni az **Irányítja** beállítás számára. Ezenfelül a rendszer által irányított lekérdezési sorrend csoportosíthatja a rendeléseket a vállalatra jellemző feltételek alapján. Ezért a munkarendelések hozzárendelését tovább optimalizálhatja a rendszer által irányított lekérdezési sorrend testreszabott rendezési feltételeinek megadásával.

A rendszer által irányított fürtkitároláskor a raktári dolgozók számára olyan fürt jelenik meg, amelyben a kitárolási rendeléseket eleve hozzárendelték a fürtpozíciókhoz. Ezért a dolgozók több munkához is kitárolhatják a cikkeket, és ehhez csak egyszer kell felkeresniük a kitárolási helyet. A rendszer által irányított fürtkitároláshoz tartozó kitárolási folyamat megegyezik a felhasználó által irányított fürtkitárolási folyamattal.

## <a name="set-up-system-directed-cluster-picking"></a>Rendszer által irányított fürtkitárolás beállítása

### <a name="create-cluster-profiles"></a>Fürtprofilok létrehozása

A fürtprofilok vezérlik, hogyan hozza létre a rendszer az egyes fürtöket. Ha különböző fürtökre van szükség, akkor minden mobileszköz-menüelemhez egy másik fürtprofilt kell létrehozni.

1. Kattintson a **Raktárkezelés \> Beállítás \> Mobileszköz \> Fürtprofilok** elemre.
2. Válassza az **Új** lehetőséget.
3. A **Fürtprofil azonosítója** mezőbe írja be a **2 pozíció** értéket.
4. A **Név** mezőbe írja be a **2. pozíció** értéket.
5. Az **Általános** gyorslapon állítsa be a következő mezőket:

    - **Fürtazonosító létrehozása:** Állítsa ezt a beállítást **Igen** értékűre. Ez a beállítás határozza meg, hogy a rendszer automatikusan hozza-e létre a fürtazonosítót, vagy hogy a felhasználó hozza-e létre azt a kitárolás kezdetén.
    - **Pozíciók aktiválása:** Ezt az opciót állítsa **Igen** értékűre. Ez a beállítás határozza meg, hogy a pozíciónevek automatikusan létrejönnek-e a pozíciónév beállítása alapján. Ha ez az opció **Nem** értékre van beállítva, akkor a pozíció azonosítótábla-azonosítója kerül felhasználásra.
    - **Pozíciók száma:** Írja be a **2** értéket. Ez a mező határozza meg, hogy a fürt legfeljebb hány pozícióval rendelkezhet (vagyis a dobozok, táskák és egyebek maximális számát).
    - **Pozíció neve:** Válassza a **Numerikus** értéket, hogy a pozíciók egymást követő számok használatával legyenek elnevezve. Ha a **Betűrendben** beállítást jelöli ki, a rendszer a pozíciókat ábécérendben nevezi el.
    - **Fürt felbontása ennél:** Válassza a **Betárolás** lehetőséget. Ez a mező határozza meg, hogy mikor legyen felbontva a fürt.
    - **Rendezés ellenőrzési típusa:** Válassza a **Pozíció beolvasása** lehetőséget. Ez a mező határozza meg, hogy a betárolási lépés ellenőrzésre került-e.

6. A **Fürtrendezés** gyorslapon új sor létrehozásával és a következő mezők beállításával definiálhat rendezési feltételeket:

    - **Sorszám:** Ez a mező meghatározza, hogy a rendszer milyen sorrendben rendezzen. Az érték bevitele automatikus, de szükség esetén módosítható.
    - **Mező neve:** Válassza a **WMSLocationId** értéket. Ez a mező határozza meg azt a mezőt, amelyet a sor a rendezési feltételként használ.
    - **Rendezés:** Válassza a **Növekvő** értéket. Ez a mező határozza meg, hogy a rendezés növekvő vagy csökkenő sorrendben történjen-e.

### <a name="create-a-mobile-device-menu-item"></a>Mobileszköz-menüpont létrehozása

Ha új mobileszköz-menüelemet szeretne létrehozni a rendszer által irányított fürt kitárolása céljából, és csatolni kívánja a fürtprofil azonosítóját a mobileszköz menüelemhez, kövesse az alábbi lépéseket.

1. Lépjen a **Raktárkezelés \> Beállítás \> Mobileszköz \> Mobileszköz-menüelemek** részre.
2. Válassza az **Új** lehetőséget.
3. Írja be a **Menüelem neve** mezőbe az **SD-fürt** értéket.
4. A **Cím** mezőbe írja be az **SD-fürt** értéket.
5. A **Mód** mezőben válassza ki a **Munka** lehetőséget.
6. A **Meglévő munka használata** lehetőséget állítsa **Igen** értékre.
7. Az **Általános** gyorslapon állítsa be a következő mezőket:

    - **Irányítja:** Válassza a **Rendszer által irányított** lehetőséget.
    - **Azonosítótábla előállítása:** Állítsa ezt a beállítást **Igen** értékűre.
    - **Fürtprofil azonosítója:** Válassza a **2. pozíció** értéket.

8. A **Munkaosztályok** gyorslapon a következő mezők beállításával állíthatja be a mobileszköz menüelemének érvényes munkaosztályát:

    - **Munkaosztály azonosítója:** Győződjön meg arról, hogy az **Értékesítés** van megadva.
    - **Munkarendelés típusa:** Győződjön meg arról, hogy az **Értékesítési rendelések** van megadva.

9. Új, rendszer által irányított munkasorozat-lekérdezés megadásához kövesse az alábbi lépéseket:

    1. Válassza az **Új** lehetőséget.
    2. A **Sorozat száma** mezőben írja be az **1**-es számot.
    3. A **Leírás** mezőben válassza a **Munka prioritása – Munkaazonosító** lehetőséget.

10. A menüben válassza a **Lekérdezés szerkesztése** lehetőséget.
11. A **Rendezés** lapon adja meg a következő mezők beállításait:

    - **Tábla:** Válassza a **Munka** lehetőséget.
    - **Származtatott tábla:** Válassza a **Munka** lehetőséget.
    - **Mező:** Válassza a **Munka prioritása** lehetőséget.
    - **Keresés iránya:** Válassza a **Csökkenő** lehetőséget.
    - **Tábla:** Válassza a **Munka** lehetőséget.
    - **Származtatott tábla:** Válassza a **Munka** lehetőséget.
    - **Mező:** Válassza a **Munkaazonosító** lehetőséget.
    - **Keresés iránya:** Válassza a **Csökkenő** lehetőséget.

A rendszer most rendezni fogja a munkaazonosítókat a fürtben, először a munka prioritása, majd a munkaazonosító szerint.

### <a name="set-up-a-mobile-device-menu"></a>Mobileszköz-menü beállítása

1. Lépjen a **Raktárkezelés \> Beállítás \> Mobileszköz \> Mobileszköz menü** elemre.
2. Adja hozzá az imént létrehozott menüelemet a kívánt menühöz.

## <a name="example"></a>Példa

### <a name="create-picking-work"></a>Kitárolási munka létrehozása

A rendszer által irányított fürtkitárolás beállítása előtt létre kell hoznia néhány alkalmas kimenő munkát. A korábban létrehozott fürtprofil két fürtpozíciót határoz meg. Ezért legalább két munkaazonosítót kell létrehoznia.

1. Ugorjon az **Értékesítés és marketing \> Értékesítési rendelések \> Minden értékesítési rendelés** pontra.
2. Új értékesítési rendelés létrehozásához kattintson az **Új** elemre.
3. Válasszon ki egy tetszőleges vevőt a **Vevői számla** mezőben.
4. Az **Általános** gyorslap **Raktár** mezőjében válassza ki a **62** számú raktárt.
5. Válassza ki az **OK** lehetőséget.
6. Az **Értékesítési rendelés sorai** gyorslapon válassza a **Sor hozzáadása** lehetőséget.
7. A **Cikkszám** mezőben válassza ki a **A0001** cikkszámot.
8. Írja be a **1** értéket a **Mennyiség** mezőbe.
9. Második sor hozzáadásához válassza a **Sor hozzáadása** lehetőséget.
10. A **Cikkszám** mezőben válassza ki a **A0002** cikkszámot.
11. Írja be a **3** értéket a **Mennyiség** mezőbe.
12. Ismételje meg a 2. lépéstől a 6. lépésig a folyamatot.
13. A **Cikkszám** mezőben válassza ki a **A0001** cikkszámot.
14. Írja be a **4** értéket a **Mennyiség** mezőbe.
15. Második sor hozzáadásához válassza a **Sor hozzáadása** lehetőséget.
16. A **Cikkszám** mezőben válassza ki a **A0002** cikkszámot.
17. Írja be a **2** értéket a **Mennyiség** mezőbe.

Foglalja le a készletet, és adja ki a raktárba. Két különböző munkaazonosító jön létre. Minden munkaazonosítóhoz két kivételezési sor tartozik.

### <a name="run-the-mobile-device-flow"></a>Futtassa a mobileszközön a folyamatot

1. A mobileszközön válassza ki azt a menüt, amely az új mobileszköz-menüelemet tartalmazza.
2. Válassza ki az **SD-fürt** menüelemet, és kezdeményezzen egy kitárolást. Létrejön egy fürt, és a két korábban létrehozott munkaazonosító hozzá van csatolva. Ha kettőnél több munkaazonosítót hozott létre, csak az első kettő kerül hozzáadásra a fürthöz. Figyelje meg, hogy a munkaazonosítók növekvő sorrendben adódnak hozzá a fürthöz, ahogy a lekérdezési beállításnál megadta.

    > [!NOTE]
    > Az új fürt létrehozása csak akkor történik meg, ha korábban már elég további munkaazonosítót hoztak létre. Ellenkező esetben a következő üzenet jelenik meg: „A fürthöz nincs elegendő munka.”

    Miután kiválasztotta a menüt, megjelenik az első kitárolási képernyő. A rendszer összesíti a két munkaazonosítóból az összes egyező kitárolási sort, és a kitárolási hely egyszeri meglátogatására utasítja, így egy kitárolással mindkét rendelést teljesítheti. Ez a folyamat ugyanúgy történik, mint a felhasználó által irányított fürtkitárolás folyamata.

3. Erősítse meg az első kitárolást. Ezután meg kell adnia a pozíció nevét, hogy megerősítse, hogy a cikkeket a megfelelő pozícióba helyezték.
4. Ismételje meg ezt a folyamatot, amíg az összes elemet ki nem tárolta és a megfelelő pozícióba nem helyezte.
5. A mobileszköz utolsó lépés az, hogy a fürtöt a végleges helyre helyezzük. Ha ez a betárolási művelet meg van erősítve, a fürt bezáródik és felbontásra kerül, a fürtprofilban lévő **Fürt felbontása ennél** mezőben beállított érték alapján. A munkaazonosítók szintén lezárásra kerülnek.
6. A mobileszközön a „Fürt befejezve” üzenet jelenik meg.
