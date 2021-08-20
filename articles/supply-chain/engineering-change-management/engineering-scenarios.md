---
title: Mérnöki változtatások kezelése funkció áttekintése
description: Ez a témakör egy átfogó áttekintést tartalmaz, amely bemutatja a mérnöki változtatások kezelésével kapcsolatos munkát.
author: t-benebo
ms.date: 09/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: e95cb358b8e79ff091f428140e908be2ab3131f264e8cc43cd7de1f1745d8dfa
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6755419"
---
# <a name="engineering-change-management-feature-walkthrough"></a>Mérnöki változtatások kezelése funkció áttekintése

[!include [banner](../includes/banner.md)]

Ez a témakör egy átfogó áttekintést tartalmaz, amely bemutatja a mérnöki változtatások kezelésével kapcsolatos munkát. Végighalad a legfontosabb helyzetek mindegyikén:

- Alapvető funkciók konfigurálása
- Hogyan hoz létre egy mérnöki vállalat új mérnöki terméket?
- Hogyan ad ki egy mérnöki cég egy új mérnöki terméket egy helyi cégnek?
- Hogyan tekint át és fogad el egy helyi cég egy terméket, amelyet egy mérnöki cég adott ki neki?
- Hogyan használhat egy helyi cég egy mérnöki terméket normál tranzakciókban?
- Hogyan adhatók mérnöki termékek egy értékesítési rendeléshez?
- Hogyan kérhető egy mérnöki termék módosítása mérnöki módosítási kérelem létrehozásával?
- Hogyan ütemezhetők és valósíthatók meg kért módosítások egy mérnöki módosítási rendelés létrehozásával?
- Hogyan adható ki egy módosított termék?

Az ebben a témakörben szereplő összes gyakorlat a Microsoft Dynamics 365 Supply Chain Management számára biztosított szabványos mintaadatokat használja. Emellett mindegyik gyakorlat az előző gyakorlatra épül. Ezért azt ajánljuk, az elejétől a végéig, sorrendben haladjon végig a gyakorlatokon, különösen, ha korábban nem használta a mérnöki változtatások kezelési funkcióját. Ily módon a teljesen megértheti a funkciót.

## <a name="set-up-for-the-sample-scenario"></a>A mintaeset beállítása

Az ebben a témakörben megadott példa eset követéséhez először elő kell készítenie a funkciót a bemutatóadatok rendelkezésre bocsátásával és néhány egyéni rekord hozzáadásával.

Mielőtt a témakör többi részén megpróbálja végrehajtani a gyakorlatokat, kövesse az alábbi alszakaszok utasításait. Ezek az alszakaszok számos olyan fontos beállítási lapot is bemutatnak, amelyet a saját szervezetnél a mérnöki változtatások kezelésének beállításakor fog használni.

### <a name="make-standard-demo-data-available"></a>A standard bemutató adatok elérhetővé tétele

Azon a rendszeren dolgozzon, ahol a [standard bemutató adatok telepítve vannak](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md). A standard demó adatok több bemutató jogi személy (vállalatok és szervezetek) adatait adja hozzá. Ahogy végrehajtja a gyakorlatokat, a navigációs sáv jobb oldalán található vállalatválasztóval válthat egy olyan vállalat (*DEMF*) között, amely *mérnöki szervezetként* van beállítva, és egy másik vállalat (*USMF*) között, amely *műveleti szervezetként* van beállítva.

### <a name="set-up-an-engineering-organization"></a>Mérnöki szervezet beállítása

Egy mérnöki szervezet rendelkezik a mérnöki adatokkal, és felelős a termék tervezésével és a termékek változásaival kapcsolatban. A mérnöki szervezetek beállításához kövesse az alábbi lépéseket.

1. Lépjen a **Mérnöki változtatások kezelése &gt; Beállítás &gt; Mérnöki szervezetek** lehetőségre.
1. Válassza ismét az **Új** lehetőséget egy sor hozzáadásához a rácshoz, majd állítsa be a következő értékeket hozzá:

    - **Mérnöki szervezet:** *DEMF*
    - **Szervezet neve:** *Contoso Entertainment System Germany*

    ![Mérnöki szervezet hozzáadása.](media/engineering-org.png "Mérnöki szervezet hozzáadása")

### <a name="set-up-the-version-product-dimension-group"></a>A verzió termékdimenziójához tartozó csoport beállítása

1. Lépjen a **Termékinformáció-kezelés &gt; Beállítás &gt; Dimenziók és változatcsoportok &gt; Termékdimenzió-csoportok** részre.
1. Válassza ki az **Új** lehetőséget egy új termékdimenzió-csoport létrehozásához.
1. A **Név** mezőt állítsa *Verzió* értékre.
1. A **Mentés** gombra kattintva mentheti az új dimenziót és a rakomány értékeit a **Termékdimenziók** gyorslapra.
1. A **Termékdimenziók** gyorslapon adja meg a **Verzió** elemet aktív termékdimenzióként.

    ![Termékdimenzió-csoport hozzáadása.](media/product-dimension-groups.png "Termékdimenzió-csoport hozzáadása")

### <a name="set-up-product-lifecycle-states"></a>Termékéletciklus állapotainak beállítása

Ahogy egy mérnöki termék végighalad az életciklusán, fontos, hogy tudja szabályozni, hogy az egyes életciklus-állapotokhoz melyik tranzakciók engedélyezettek. A termékéletciklus állapotainak beállításához kövesse az alábbi lépéseket.

1. Lépjen a **Mérnöki változtatások kezelése – &gt; Beállítás &gt; Termék életciklus-állapota** lehetőségre.
1. Válassza az **Új** lehetőséget egy életciklus-állapot hozzáadásához, majd állítsa be a következő értékeket hozzá:

    - **Állapot:** *Működő*
    - **Leírás:** *Működő*

1. A **Mentés** gombra kattintva mentheti az új életciklus-állapotot és a rakomány értékeit a **Beágyazott üzleti folyamatok** gyorslapra.
1. Az **Engedélyezett üzleti folyamatok** gyorslapon válassza ki azokat az üzleti folyamatokat, amelyeknek elérhetőknek kell lenniük. Ebben a példában az **Irányelv** mezőt hagyja *Engedélyezett* értékre állítva az összes üzleti folyamat számára.

    ![Üzleti folyamatok engedélyezése az életciklus-állapotokhoz.](media/product-lifecycle-states-1.png "Üzleti folyamatok engedélyezése az életciklus-állapotokhoz")

1. Válassza az **Új** lehetőséget egy további életciklus-állapot hozzáadásához, majd állítsa be a következő értékeket hozzá:

    - **Állapot:** *Prototípus*
    - **Leírás:** *Prototípus*

1. A **Mentés** gombra kattintva mentheti az új életciklus-állapotot és a rakomány értékeit a **Beágyazott üzleti folyamatok** gyorslapra.
1. Az **Engedélyezett üzleti folyamatok** gyorslapon válassza ki azokat az üzleti folyamatokat, amelyeknek elérhetőknek kell lenniük. Ebben a példában az **Irányelv** mezőt állítsa *Engedélyezett figyelmeztetéssel* értékre az összes üzleti folyamat számára.

    ![Üzleti folyamatok engedélyezése (figyelmeztetésekkel) az életciklus-állapotokhoz.](media/product-lifecycle-states-2.png "Üzleti folyamatok engedélyezése (figyelmeztetésekkel) az életciklus-állapotokhoz")

### <a name="set-up-a-version-number-rule"></a>Verziószám-szabály beállítása

1. Lépjen a **Mérnöki változtatások kezelése – &gt; Beállítás &gt; Termék verziószám-szabálya** lehetőségre.
1. Válassza az **Új** lehetőséget egy szabály hozzáadásához, majd állítsa be a következő értékeket hozzá:

    - **Név:** *Automatikus*
    - **Számszabály:** *Automatikus*
    - **Formátum:** *V-\#\#*

    ![Termék verziószám-szabályának hozzáadása.](media/version-number-rule.png "Termék verziószám-szabályának hozzáadása")

### <a name="set-up-a-product-release-policy"></a>Termék kiadási házirendjének beállítása

1. Lépjen a **Mérnöki változtatások kezelése – &gt; Beállítás &gt; Termék kiadási házirendjei** lehetőségre.
1. Válassza az **Új** lehetőséget egy kiadási házirend hozzáadásához, majd állítsa be a következő értékeket hozzá:

    - **Név:** *Összetevők*
    - **Leírás:** *Összetevők*

1. Az **Általános** gyorslapon állítsa be a következő értékeket:

    - **Terméktípus:** *Cikk*
    - **Sablonok alkalmazása:** *Mindig*
    - **Aktív:** *Igen*

1. A **Minden termék** gyorslapon válassza a **Hozzáadás** parancsot egy sor hozzáadásához, majd állítsa be a következő értékeket hozzá:

    - **Cég:** *DEMF*
    - **Kiadott termék sablonja:** *D0006*

1. Válassza ki a **Hozzáadás** lehetőséget egy további sor hozzáadásához, és állítsa be a következő értékeket:

    - **Vállalati számlák azonosítója:** *USMF*
    - **Kiadott termék sablonja:** *D0006*
    - **Fogadó AJ:** Válassza ki ezt a jelölőnégyzetet.
    - **Anyagjegyzék-jóváhagyás másolása:** Jelölje be ezt a jelölőnégyzetet.
    - **Anyagjegyzék-aktiválás másolása:** Jelölje be ezt a jelölőnégyzetet.
    - **Fogadási útvonal:** Válassza ki ezt a jelölőnégyzetet.
    - **Útvonal-jóváhagyás másolása:** Jelölje be ezt a jelölőnégyzetet.
    - **Útvonal-aktiválás másolása:** Jelölje be ezt a jelölőnégyzetet.

    ![Termék kiadási házirendjének hozzáadása.](media/product-release-policy.png "Termék kiadási házirendjének hozzáadása")

### <a name="set-up-an-engineering-product-category"></a>Mérnöki termékkategória beállítása 

A mérnöki termékkategóriák a mérnöki termékek (azaz a mérnöki változtatások kezelése révén verziószámozott és ellenőrzött termékek) létrehozásának alapját képezik. A mérnöki szervezetek termékkategóriáinak beállításához kövesse az alábbi lépéseket.

1. Lépjen a **Mérnöki változtatások kezelése &gt; Mérnöki termékkategória részletei** részre.
1. Válassza az **Új** lehetőséget egy kategória létrehozásához.
1. A **Részletek** gyorslapon állítsa be a következő értékeket:

    - **Név:** *Összetevők*
    - **Mérnöki szervezet:** *DEMF*
    - **Terméktípus:** *Cikk*
    - **A tranzakciók verziójának nyomon követése:** *Igen*
    - **Termékdimenzió-csoport:** *Verzió*
    - **A termék életciklusának állapota a létrehozásnál:** *Működik*
    - **Verziószámszabály:** *Automatikus*
    - **Érvényesség kényszerítése:** *Nem*
    - **Számszabály szerinti elnevezési rendszer használata:** *Nem*
    - **Névszabály szerinti elnevezési rendszer használata:** *Nem*
    - **Leírásszabály szerinti elnevezési rendszer használata:** *Nem*

1. A **Kiadási irányelv** gyorslapján adja meg a **Termék kiadási házirendje** mezőt az *Összetevők* értékkel.
1. Válassza a **Mentés** lehetőséget.

    ![Mérnöki termékkategória hozzáadása.](media/product-category-details.png "Mérnöki termékkategória hozzáadása")

### <a name="set-up-product-acceptance-conditions"></a>A termék elfogadási feltételeinek beállítása

1. A navigációs sáv jobb oldalán található vállalatválasztóval válthat a *USMF* jogi személyre (vállalatra).
1. Lépjen a **Mérnöki változtatások kezelése &gt; Beállítás &gt; Mérnöki változtatások kezelésének paraméterei** lehetőségre.
1. A **Kiadás szabályozása** lapon a **Termék elfogadása** szakaszban állítsa a **Termék elfogadása** mezőt *Manuális* értékre.

    ![A termék elfogadási feltételeinek beállítása.](media/engineering-change-management-parameters.png "A termék elfogadási feltételeinek beállítása")

## <a name="create-a-new-engineering-product"></a>Új mérnöki termék létrehozása

A mérnöki termék olyan termék, amelyet a mérnöki változtatások kezelése segítségével kerül verziószámozásra és szabályozásra. Más szóval szabályozhatja a változásokat az élettartama alatt, és a módosítási adatok a mérnöki módosítási rendelések segítségével kerülnek mentésre. Mérnöki termékek létrehozásához kövesse az alábbi lépéseket.

1. Győződjön meg róla, hogy a mérnöki szervezete jogi személyében van (*DEMF* ebben a példában). Szükség esetén használja a navigációs sáv jobb oldalán található vállalatválasztót.
1. Nyissa meg a **Kiadott termékek** oldalt az alábbi lépések valamelyikével:

    - Kattintson a **Termékinformációk kezelése &gt; Termékek &gt; Kiadott termékek** lehetőségre.
    - Lépjen a **Mérnöki változtatások kezelése – &gt; Általános &gt; Kiadott termékek** lehetőségre.

1. A műveleti ablaktáblán a **Termék** lapon az **Új** csoportban válassza a **Mérnöki termék** lehetőséget.
1. Az **Új termék** párbeszédpanelen adja meg a következő értékeket:

    - **Mérnöki termékkategória:** *Összetevők*
    - **Termék száma:** *Z0001*
    - **Termék neve:** *Hangszórókészlet*

    ![Mérnöki termék hozzáadása.](media/new-product-dialog.png "Mérnöki termék hozzáadása")

    Ne felejtse el, hogy a **Verzió** mezőt a korábban beállított termékverziószám-szabály alapján automatikusan beállítja a rendszer.

1. Válassza az **OK** gombot a termék létrehozásához és a párbeszédpanel bezárásához.
1. A program megnyitja az új termék részletes lapját. Figyelje meg, hogy bizonyos mezők, például a **Tárolásidimenzió-csoport**, a **Nyomonkövetésidimenzió-csoport** és/vagy a **Cikkmodellcsoport** értékei már ki vannak töltve. Ezeket a mezőket automatikusan beállítja a program, mert a termék ki van adva a *DEMF* jogi személyben, és az *Összetevők* termékkiadási irányelvet használja, amely az *Összetevők* mérnöki termékkategóriához van társítva. Mivel korábban a *D0006* cikket sablonként használta egy sor beállítására a *DEMF* jogi személyhez, a kitöltött értékeit a program a *D0006* elemből veszi.

    ![Megjelent termék részletei.](media/product-details.png "Megjelent termék részletei")

1. A művelet ablaktáblán, a **Mérnök** lapon, a **Mérnöki változtatások kezelése** csoportban válassza a **Mérnöki verziók** elemet a termék verzióinak megtekintéséhez.

    ![Tervezési verziók.](media/engineering-versions-list.png "Tervezési verziók")

1. A **Mérnöki verziók** lapon figyelje meg, hogy a termékhez csak egy verzió tartozik, és az aktív.
1. A részletek megtekintéséhez válassza ki a verziót.

    ![Mérnöki verzió részletei.](media/engineering-version-details.png "Mérnöki verzió részletei")

1. A **Mérnöki verzió** lapon, az **Anyagjegyzék** gyorslapon válassza az **Anyagjegyzék létrehozása** elemet.
1. Az **Anyagjegyzék létrehozása** párbeszédpanelen adja meg a következő értékeket:

    - **Anyagjegyzék száma:** Z0001
    - **Név:** Hangszórókészlet
    - **Telephely:** 1

    ![Anyagjegyzék létrehozása.](media/create-bom.png "BOM létrehozása")

1. Válassza az **OK** gombot az anyagjegyzék hozzáadásához, és a párbeszédpanel bezárásához.
1. Az **Anyagjegyzék** gyorslapon válassza ki az **Anyagjegyzék** lehetőséget.
1. Az **Anyagjegyzékek** oldalon, az **Anyagjegyzék sorai** gyorslapon adjon hozzá három sort, egyet a következő cikkszámok mindegyikéhez: *D0001*, *D0003* és *D0006*.

    ![Anyagjegyzéksorok hozzáadása.](media/bom.png "Anyagjegyzéksorok hozzáadása")

1. Válassza a **Mentés** lehetőséget.
1. Zárja be a lapot.
1. A **Mérnöki verzió** lapon, az **Anyagjegyzék** gyorslapon válassza a **Jóváhagyás** elemet.
1. A megjelenő párbeszédpanelen jelölje be az **OK** lehetőséget.

    ![Anyagjegyzék jóváhagyása.](media/approve-dialog.png "Anyagjegyzék jóváhagyása")

1. A **Mérnöki verzió** lapon, az **Anyagjegyzék** gyorslapon válassza az **Aktiválás** elemet.
1. Figyelje meg, hogy az **Aktív** és **Jóváhagyott** jelölőnégyzetek be vannak jelölve az anyagjegyzékhez.

    ![Aktív és jóváhagyott anyagjegyzék.](media/approved-bom.png "Aktív és jóváhagyott anyagjegyzék")

1. Zárja be a lapot.

## <a name="release-an-engineering-product-to-a-local-company"></a><a name="release"></a>Mérnöki termék kiadása egy helyi vállalatnak

A terméket most a mérnöki részleg tervezte. Ebben a példában a termék egy prototípus, amelyet a mérnökség egy felhasználó számára készített. Mivel az ügyfél a *USMF* jogi személy ügyfele, a terméket ki kell adni a jogi személynek.

1. Tartsa a jogi személyt a *DEMF* beállításon. (Szükség esetén használja a navigációs sáv jobb oldalán található vállalatválasztót.)
1. Kattintson a **Termékinformációk kezelése &gt; Termékek &gt; Kiadott termékek** lehetőségre.
1. Válassza ki a *Z0001* terméket.
1. A művelet ablaktábla **Termék** lapjának **Karbantartás** csoportjában válassza ki a **Termékszerkezet kiadása** lehetőséget a **Termékek kiadása** varázsló megnyitásához.
1. A **Mérnöki termékek kiválasztása kiadására** oldalon válassza a **Kiválasztás** jelölőnégyzetet a *Z0001* termék számára.

    ![A kiadandó mérnöki termékek kiválasztása.](media/select-eng-product-to-release.png "A kiadandó mérnöki termékek kiválasztása")

1. Válassza ki a **Kiadás részletei** lehetőséget.
1. Megjelenik a **Termékkiadás részletei** lap, amelyen megtekintheti a kiadott termék részletes adatait, valamint a termék szerkezetét. Figyelje meg, hogy az **Anyagjegyzék küldése** értéke *Igen*-re van állítva. Ezért a program kiadja mind a *Z0001* terméket és annak minden gyermekét az anyagjegyzékből.

    A bal oldali ablakban bármelyik gyermeket kiválaszthatja a részletek áttekintéséhez. Ha bármely gyermekcikkhez tartozik anyagjegyzék, akkor azt is beállíthatja, hogy az adott gyermek anyagjegyzékét is kiadja.

    ![A termék kiadásával kapcsolatos részletek megtekintése.](media/product-release-details.png "A termék kiadásával kapcsolatos részletek megtekintése")

1. Zárja be az oldalt a **Termékek kiadása** varázslóhoz való visszatéréshez.
1. Válassza a **Következő** lehetőséget a **Kiadandó termékek kiválasztása** oldal megnyitásához. Ha bármilyen szabványos (nem mérnöki) terméket választott, akkor ezek ezen az oldalon jelennek meg. Ne feledje, hogy ha a **Termékszerkezet kiadása** kiválasztásával egy szabványos terméket ad ki, akkor az anyagjegyzék és az útvonal is ki lesz adva.

    ![A kiadandó standard termékek kiválasztása.](media/select-std-product-to-release.png "A kiadandó standard termékek kiválasztása")

1. Válassza a **Következő** lehetőséget a **Kiadandó termékvariánsok kiválasztása** oldal megnyitásához. Ebben a példában nincsenek változatok.
1. Válassza a **Következő** lehetőséget a **Vállalatok kiválasztása** oldal megnyitásához.
1. Válassza ki azokat a vállalatokat, amelyeknek a terméket ki kell adni. A példa esetében válassza ki a **USMF** jelölőnégyzetét.

    ![Azoknak a vállalatoknak a kiválasztása, amelyeknek ki kell adni a termékeket.](media/select-release-companies.png "Azoknak a vállalatoknak a kiválasztása, amelyeknek kiadnak")

1. Válassza a **Következő** lehetőséget a **Kiválasztás megerősítése** oldal megnyitásához.
1. Válassza a **Befejezés** lehetőséget.

## <a name="review-and-accept-the-product-before-you-release-it-in-the-local-company"></a><a name="accept"></a>A termék áttekintése és elfogadása a helyi vállalatban történő kiadás előtt

A mérnöki részleg most kiadta az információt azoknak a helyi vállalatoknak, ahol a termék használatban lesz. Ebben a példában a helyi vállalat a *USMF*.

Mivel a **Termék elfogadása** mezőt *Manuális* értékre állította a **Mérnöki változtatások kezelésének paraméterei** oldalon az *USMF* vállalat számára, a vállalatnak történő kiadás előtt manuálisan el kell fogadni a termékeket. Más szóval ezeket át kell tekinteni és el kell fogadni, mielőtt kiadott termékek lehetnének.

A termék áttekintéséhez és a *USMF* vállalatban történő kiadásához kövesse az alábbi lépéseket.

1. Állítsa be a jogi személyt a *USMF* értékre. (Használja a navigációs sáv jobb oldalán található vállalatválasztót.)
1. Lépjen a **Mérnöki változtatások kezelése &gt; Általános &gt; Termékkiadások &gt; Nyitott termékkiadások** lehetőségre.

    A **Nyitott termékkiadások** oldal a *Z0001* terméket jeleníti meg, amely a *Függőben lévő elfogadás* állapottal rendelkezik.

    ![Nyitott termékkiadások.](media/open-product-releases.png "Nyitott termékkiadások")

1. Válassza ki a **Termékszám** oszlopát a **Termék kiadási részletei** oldal megnyitásához. Vegye figyelembe a következőket:

    - Az **Általános** gyorslap a termék kiadásával kapcsolatos információkat jelenít meg, például a kiadó vállalatot (a *DEMF* ebben a példában), a kiadó helyet (*1*) és a fogadó helyet (*1*). Mivel a **Termékek kiadása** varázslóban nem adott meg bevételezési helyet, a rendszer a bevételezési helyre másolja a kiadási hely értékét.
    - A **Kiadás részletei** gyorslap a termékkel és a kiadott verzióval kapcsolatos adatokat jeleníti meg. Itt módosíthatja a beállításokat, például az érvényesség dátumait.
    - Az **Útvonal** gyorslap a termék útvonalát jeleníti meg. Ebben a példában azonban nem adott ki útvonalakat.

    ![Termékkiadás részletei.](media/product-release-details-2.png "Termékkiadás részletei")

1. Ha befejezte az adatok áttekintését, akkor készen áll a termék elfogadására, és ily módon kiadni azt a *USMF* vállalatban. A Művelet ablaktáblán válassza ki a **Műveletek &gt; Elfogadás** lehetőséget.
1. A termék most kiadásra kerül a *USMF* vállalatban. Kattintson a **Termékinformációk kezelése &gt; Termékek &gt; Kiadott termékek** lehetőségre. A *Z0001* cikket kell látnia.

## <a name="use-the-product-in-transactions-in-the-local-company"></a>A termék használata a helyi vállalat tranzakciói között

A *USMF* vállalat törzsadatkezelőjének meg kell győződnie arról, hogy a termék *Prototípus* állapotban van, annak érdekében, hogy a felhasználó figyelmeztetést kapjon, ha véletlenül hozzáadja azokat a folyamatokhoz, amelyeken dolgoznak.

1. Kattintson a **Termékinformációk kezelése &gt; Termékek &gt; Kiadott termékek** lehetőségre.
1. Válassza ki a *Z0001* terméket a részletek oldalának megnyitásához. (A szűrőt a termék megtalálására használhatja.)
1. A művelet ablaktáblán, a **Mérnök** lapon, a **Mérnöki változtatások kezelése** csoportban válassza a **Mérnöki verziók** elemet.
1. A **Mérnöki verziók** oldalon válassza a *V-01* verziószámot a részletek lapjának megnyitásához.
1. A műveleti ablaktáblán a **Termék** lapon az **Életciklus-állapot** csoportban válassza az **Életciklus-állapot módosítása** lehetőséget.
1. Az **Életciklus-állapot módosítása** legördülő párbeszédpanelen állítsa be az **Állapot** mezőt a *Prototípus* elemre, majd kattintson az **OK** gombra.

    ![Az életciklus-állapot módosítása.](media/change-lifecycle-state.png "Az életciklus-állapot módosítása")

## <a name="add-the-engineering-product-to-a-sales-order"></a>Mérnöki termék hozzáadása egy értékesítési rendeléshez

A terméket most egy ügyfélnek lehet értékesíteni. A termék értékesítési rendeléshez való hozzáadásához kövesse ezeket a lépéseket.

1. Ugorjon az **Értékesítés és marketing &gt; Értékesítési rendelések &gt; Minden értékesítési rendelés** pontra.
1. A Műveleti ablaktáblán kattintson az **Új** elemre.
1. Az **Értékesítési rendelés létrehozása** párbeszédpanelen, a **Vevői számla** mezőt állítsa *US-0002* értékűre, majd válassza az **OK** lehetőséget.
1. A program megnyitja az új értékesítési rendelést. Az **Értékesítési rendelés sorai** gyorslapon adjon hozzá egy sort, és a **Cikkszám** mezőt állítsa be *Z000* értékre.
1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.

    Figyelmeztetés jelenik meg arról, hogy a cikk *Prototípus* állapottal rendelkezik. Mivel azonban az üzenet csak egy figyelmeztetés, az értékesítési rendelés létrehozása megtörtént.

    ![Mérnöki termék értékesítési rendelése.](media/sales-order-eng-product.png "Mérnöki termék értékesítési rendelése")

## <a name="request-changes-in-the-engineering-product"></a>A mérnöki termék módosításainak kérése

A termék egy vevőnek lett elküldve, de a vevő nem volt teljesen elégedett, és visszajelzést ad, amely a fejlesztéssel kapcsolatos javaslatokat tartalmaz. Miközben a vevő egy értékesítési ügyintézővel beszél a telefonon, az értékesítési ügyintéző kérheti a vevő által leírt változtatásokat.

1. Ugorjon az **Értékesítés és marketing &gt; Értékesítési rendelések &gt; Minden értékesítési rendelés** pontra.
1. Keresse meg és nyissa meg a korábbi gyakorlatban létrehozott értékesítési rendelést.
1. Az **Értékesítési rendelés** gyorslapon válassza ki a **Mérnöki változtatások kezelése &gt; Új mérnöki módosítási kérés** lehetőséget.

    ![Mérnöki módosítás iránti kérelem létrehozása értékesítési rendelésből.](media/sales-order-eng-change-request.png "Mérnöki módosítás iránti kérelem létrehozása értékesítési rendelésből")

1. Töltse ki a mérnöki változtatás kérését a vevő visszajelzése alapján. Ebben a példában a következő értékeket állítsa be:

    - **Módosítási kérelem:** *555*
    - **Cím:** *Z0001 vevői módosítás*
    - **Prioritás:** *alacsony*
    - **Kategória:** módosítás beállítása
    - **Súlyosság:** *Közepes*

1. Az **Információk** gyorslapon válassza az **Új &gt; Megjegyzés** parancsot, ha egy megjegyzést szeretne hozzáadni a rácshoz.
1. Az új megjegyzés **Leírás** mezőjében jelezze, hogy a *D0003* cikket törölni kell az anyagjegyzékből. Ha további adatokat kell megadnia a megjegyzéshez, akkor szöveget vihet be a **Megjegyzések** mezőbe.

    ![Tervezési módosítási kérelem.](media/eng-change-request.png "Tervezési módosítási kérelem")

1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.
1. Figyelje meg, hogy a program automatikusan hozzáadta a cikket a **Termékek** gyorslaphoz, és a mérnöki változtatás kérésének forrását (az értékesítési rendelés) hozzáadta a **Forrás** gyorslaphoz.

## <a name="make-changes-to-the-product-by-using-an-engineering-change-order"></a>A termék módosítása egy mérnöki változtatási rendelés segítségével

A kereskedelmi ügyintéző tudja, hogy a termék fontos, és kifejezetten a vevő számára készült. Ezért az értékesítési ügyintéző felhív egy mérnököt a *DEMF* vállalatnál, hogy értesítse őket a módosítási kérelemről. Ily módon a mérnök fel tudja gyorsítani a folyamatot.

A mérnök most áttekinti a vevőtől érkező kérést, és a termékhez módosítási rendelést hoz létre.

1. Mivel a mérnök a *DEMF* vállalatnál dolgozik, a jogi személy a *DEMF* értékre lesz beállítva. (Használja a navigációs sáv jobb oldalán található vállalatválasztót.)
1. Lépjen a **Mérnöki változtatások kezelése &gt; Általános &gt; Mérnöki változtatási kérelmek** lehetőségre.
1. Nyissa meg az *555*-ös módosítási kérést.
1. Tekintse át az adatokat, majd hagyja jóvá a módosítást. A Művelet ablaktábla **Módosítási kérés** lapjának **Állapot módosítása** csoportjában válassza a **Jóváhagyás** elemet.
1. Lépjen a **Mérnöki változtatások kezelése &gt; Általános &gt; Mérnöki változtatási rendelések** lehetőségre.
1. A műveleti ablaktáblán válassza az **Új** parancsot egy módosítási rendelés létrehozásához, és állítsa be a következő értékeket hozzá:

    - **Módosítási rendelés:** *555*
    - **Cím:** *Z0001 vevői módosítás*
    - **Kategória:** *Vevői módosítás*
    - **Prioritás:** *Alacsony*
    - **Súlyosság:** *Közepes*

1. Az **Érintett termékek** gyorslapon válassza az **Új &gt; Meglévő termék hozzáadása** lehetőséget ha sort szeretne hozzáadni egy rácshoz, majd állítsa be a következő értékeket hozzá:

    - **Termék:** *Z0001*
    - **Hatás:** *Új verzió*

    ![Mérnöki módosítási rendelés létrehozása.](media/eng-change-order.png "Mérnöki módosítási rendelés létrehozása")

1. Figyelje meg, hogy mivel a **Hatás** mezőt az *Új verzió* értékre állította be, az **Új verzió** mező a **Termékrészletek** gyorslap **Termékrészletek** lapján megmutatja, hogy mi lesz az új verziószám (*V-02* ebben a példában).

    ![Mérnöki módosítási rendelés termékrészletei.](media/eng-change-order-product-details.png "Mérnöki módosítási rendelés termékrészletei")

1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.
1. A **Termékrészletek** gyorslapon, az **Anyagjegyzék** lapon válassza a **Sorok** lehetőséget a *Z0001* termék *V-01* verziójához tartozó anyagjegyzék megnyitásához.

    ![Mérnöki termék anyagjegyzéksorai.](media/eng-product-bom-lines.png "Mérnöki termék anyagjegyzéksorai")

1. Válassza ki a *D0003* cikkszám sorát, majd a művelet ablaktáblán válassza a **Törlés** parancsot. A **Módosítás típusa** mező ehhez a sorhoz tartozó értéke *Törölt* értékre változik.
1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.

    ![Módosított mérnöki termék anyagjegyzéksorai.](media/eng-product-bom-lines-modified.png "Módosított mérnöki termék anyagjegyzéksorai")

1. Zárja be az **Anyagjegyzéksor** oldalt a **Mérnöki módosítási rendelés** lapra.
1. A **Termék részletei** gyorslap **Darabjegyzék** lapján figyelje meg, hogy a *Z0001* anyagjegyzék **Módosítás típusa** mezőjének értéke most *Megváltozott*.

    ![Anyagjegyzéket tartalmazó mérnöki módosítási rendelés.](media/eng-change-order-changed-bom.png "Anyagjegyzéket tartalmazó mérnöki módosítási rendelés")

    A módosítások feldolgozása előtt jóvá kell hagyni a rendelést. A módosítások feldolgozásakor a rendszer frissíti a termékeket a mérnöki módosítási rendelésben szereplő módosításokkal. A példa esetében a mérnöki módosítási rendelést létrehozó személyt a jóváhagyóként határozták meg.

1. A Művelet ablaktábla **Módosítási rendelés** lapjának **Állapot módosítása** csoportjában válassza a **Jóváhagyás** elemet.
1. Válassza ki a **Feldolgozás** lehetőséget a termék adatainak frissítéséhez.

## <a name="release-the-changed-product"></a>A módosított termék kiadása

A termék most újra kiadható a *USMF* vállalatnak, majd elküldhető a vevőnek. A termék közvetlenül a mérnöki módosítási rendelésből történő kiadásához kövesse az alábbi lépéseket.

1. Nyissa meg a korábbi gyakorlat során létrehozott mérnöki módosítási rendelést, ha még nincs megnyitva.
1. A Művelet ablaktábla **Módosítási rendelés** lapjának **Termékkiadások** csoportjában válassza a **Keresés** elemet.
1. A keresési eredmények azt mutatják, hogy az érintett termékeket mely vállalatoknak adták ki. Zárja be a keresési találatokat.
1. A Művelet ablaktábla **Módosítási rendelés** lapjának **Termékkiadások** csoportjában válassza a **Megjelenítés** parancsot, hogy megnyíljon a **Kiadások** párbeszédpanel, amelyen megtekintheti az előző keresés eredményét.
1. Válassza ki azt a vállalatot, amelynek a termékeket ki kívánja adni.
1. Válassza az **OK** gombot a **Kiadások** párbeszédpanel bezárásához és a visszatéréshez a módosítási rendeléshez.
1. Válassza ki a művelet ablaktábla **Módosítási rendelés** lapján a **Termékkiadások** csoportban a **Feldolgozás** lehetőséget, hogy az érintett termékeket kiadja a kiválasztott vállalatoknak. Azt is megteheti, hogy a kiadási folyamat elindításához kijelöli **Termékszerkezet kiadása** lehetőséget.

## <a name="complete-the-change-order"></a>A módosítási utasítás befejezése

A módosítási utasítás befejezettként való megjelöléséhez, amely azt jelzi, hogy nincs további művelet, a műveleti ablaktáblán válassza a **Kész** lehetőséget.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
