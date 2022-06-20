---
title: Termelési rendelés feladása
description: Ez a cikk a termelési rendelés feladásának különböző típusairól nyújt tájékoztatást.
author: rachelprofitt
ms.date: 04/25/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: InventPosting, InventItemGroup, ProdGroup, WrkCtrTable, WrkCtrResourceGroup, ProjCategory, CostSheetDesigner
audience: Application User
ms.search.region: Global
ms.author: raprofit
ms.openlocfilehash: d41725325a82b24c1e5aa6bd2c1a5322f3078ace
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8879624"
---
# <a name="production-postings"></a>Termelési feladások

Ez a cikk a termelési rendelési folyamat különféle feladási típusairól nyújt tájékoztatást.


## <a name="material-consumption"></a>Anyagfelhasználás

A termelési kitárolásilista-napló feladásakor az anyagokat a termelés során felhasználtként regisztrálják. Ezzel olyan tranzakciókat hoz létre, amelyek levonják az aktuális készletet. A Termelés **paraméterei között** megadhatja, hogy a folyamatban lévő nyersanyagok (más néven folyamatban lévő munka) értékét fel kell-e adni a főkönyvbe.

A folyamatban **lévő** **nyersanyagok értékét feladja a rendszer a felhasznált anyagok becsült költségének és a felhasznált anyagok becsült költségének számláira.** A termelési rendelés kitárolásilista-folyamata a termelési rendeléshez kapcsolódó készlettranzakciók fizikai frissítése. Amikor egy termelési rendelést végként regisztrálnak, a tényleges tranzakciókat sztornírozja a rendszer, és pénzügyileg frissíti a kapcsolódó készlettranzakciókat. A záró napló feladása **során** **a rendszer a felhasznált anyagköltséget és a felhasznált anyagköltséget, valamint a folyamatban lévő termelés** feladási típusait használja fel.

A **Készletfeladási** profilok lapon **a** Termelés lap szabályozza, hogyan adja fel a termelési rendeléseket a főkönyvbe. Ez akkor használatos, ha **a** Főkönyvi feladás mező beállítása **Cikk** **, erőforrás, illetve Cikk** **és kategória a Gyártásvezérlés paraméterei** lapon. 

Ahhoz, hogy egy kitárolási lista naplója feladható legyen a termelési rendelés főkönyvi moduljába, a következő feltételeknek kell teljesülnie:

-   A **Gyártásvezérlési paraméterek** **lapon be kell lennie jelölve a Kitárolási lista feladása a főkönyvbe jelölőnégyzetnek**. Ez a beállítás a **gyártásvezérlési paraméterek hely szerint lapon meghatározott telephelyén felülbírálható**.
-   A **Tényleges készlet feladása** jelölőnégyzetet **be** kell lennie jelölve a beszerzési rendelés sorában kiválasztott cikk cikkmodellcsoport-lapján.
-   A fő számlákat a következő feladási **típusokhoz** kell megadni a Készletfeladási profil oldalon:
    -   **Felhasznált anyagok becsült költsége**
    -   **Felhasznált anyagok becsült költsége, befejezetlen termelés**

## <a name="time-consumption"></a>Időfelhasználás

A dolgozók termelési feladatokkal töltött idejét az **útvonalkártya-napló vagy** a feladatkártya-napló **rögzíti**. A naplók feladása során a rendszer egy külön számlára feladja a folyamatban lévő erőforrásokra vonatkozó főkönyvi feladást. Ez a feladás a termelési rendeléssel töltött idő értékét képviseli. A termelési rendelés befejezettként való regisztrációja után a folyamatban lévő munka számlái kiegyenlítésre kerülnek.

A gyártásvezérlési **paraméterek** **lap Főkönyvi feladás mezőjében kiválasztott beállítástól függően háromféle lehetőség van az időfelhasználás feladására.**

## <a name="reporting-finished-goods-and-error-quantities"></a>Késztermékek és hibás mennyiségek jelentése

Amikor a termelési rendelést készként **jelentik**, **a befejezett késztermékek frissítése a Készként jelentve naplóban történik a készletben**. Ha folyamatban lévő folyamatban lévő raktározást használ, egy főkönyvi naplót ad fel a rendszer a folyamatban lévő termelés számláinak csökkentése és a késztermékek készletének növelése érdekében. A napló a termékre meghatározott elszámolóárat használja. Ha a **Gyártásvezérlés paraméterei** **lapon** be van jelölve a Becsült önköltségi ár használata beállítás, akkor a rendszer a termelési rendelésből származó becsült költséget használja.

A folyamatban lévő nyersanyagok **értékét feladja a rendszer a Becsült gyártott** **költség és a Becsült gyártott költség, folyamatban lévő munka számláira**. A **termelési rendelés Készként** jelentve folyamata a termelési rendeléshez kapcsolódó készlettranzakciók fizikai frissítése. A termelési rendelés végén a tényleges tranzakciók sztornírozása és a kapcsolódó készlettranzakciók pénzügyi frissítése történik meg. A záró napló feladása esetén a legyártott **költség** és a Legyártott **költség, a folyamatban lévő termelés feladási** típusait használja a napló.

A **Készletfeladási** profilok **lapon** a Termelés lap használatával lehet szabályozni, hogyan adja fel a rendszer a termelési rendeléseket a főkönyvbe. Ez akkor használatos, ha **a** Főkönyvi feladás mező beállítása **Cikk** **, erőforrás, illetve Cikk** **és kategória a Gyártásvezérlés paraméterei** lapon. A **Termelési csoportok** **lapon** található Főkönyvi cikkek gyorslap a termelési rendelések feladását is szabályozhatja, ha a mező beállítása Termelési **csoportok.**

Ahhoz, hogy **egy** termelési rendelés főkönyvi naplójába feladható legyen a Készként jelentve napló, a következő feltételeknek kell teljesülnie:
-   A **Gyártásvezérlési paraméterek** **lapon be kell lennie jelölve a Készként jelentve a főkönyvbe jelölőnégyzet**. Ez a beállítás a **gyártásvezérlési paraméterek hely szerint lapon meghatározott telephelyén felülbírálható**.
-   A **Tényleges készlet feladása** jelölőnégyzetet **be** kell lennie jelölve a beszerzési rendelés sorában kiválasztott cikk cikkmodellcsoport-lapján.
-   A fő számlákat a **Készletfeladási** profil lapon kell megadni a következő feladási típusokhoz:
    -   **Becsült gyártási költség**
    -   **Becsült gyártási költség, befejezetlen termelés**

## <a name="ending-the-production-order"></a>A termelési rendelések befejezése

A termelési rendelés csak akkor ér véget, ha a meg termelt mennyiséghez tényleges költségek vannak kiszámítva. Minden becsült anyag-, munka- és többletköltséget sztorníroz a program, és a tényleges költségeket vezeti be a helyükre. A befejezett cikk teljes **költsége** **tartozik** tételként kerül a Legyártott költség számlára, és követel tételként a Folyamatban lévő költségeket számlán. A termelési rendelés **során** **felhasznált anyagokra követel tételek költségeket hoznak létre a felhasznált anyagok költségével, és terhelésként az Anyagköltség, folyamatban lévő termelés számláján**.

Ha a költségszámítás futtatásakor **bejel** jelzi a Záró feladat jelölőnégyzetet, **a termelési rendelés állapota "Véget ért"**. Ez az állapot meggátolja, hogy bármilyen további költséget véletlenül feladjanak egy már elkészült termelési rendeléshez. Megadhatja, hogy a készként jelentett hibamennyiségeket felosztja a program a készként jelentett jó mennyiségek között. Másik lehetőségként megadhatja, hogy a hibamennyiségek értékét egy külön selejtszámla számára adja fel a rendszer. 

Adott selejtszámla megadásához hajtsa végre a következő lépéseket:
1.  Ugrás a Gyártásvezérlés **beállítása** > **a** > **gyártásvezérlés paramétereihez**
2.  Válassza a **Szokásos frissítés lapot**.
3.  A Selejtezés **módja mezőben** válassza a Selejtszámla **lehetőséget**.
4.  A Selejtszámla **mezőben** válassza ki azt a fő számlát, amelybe a hibás mennyiség selejtját fel kell adja a termelési rendelés végén. Például válasszon ki egy költségszámlát, például a 510380: termelési selejt.

Ahhoz, hogy a záró napló feladható legyen egy termelési rendelés főkönyvi naplójába, a következő feltételeknek kell teljesülnie:
-   A fő számlákat **a** **Készletfeladási profil vagy a Termeléscsoportok** lapon kell megadni a következő feladási típusokhoz:
    -   **Felhasznált anyagok költsége**
    -   **Felhasznált anyagok költsége, befejezetlen termelés**
    -   **Gyártási költség**
    -   **Gyártási költség, befejezetlen termelés**
-   A fő számlákat a **Költségkategóriák**, **Erőforrások** vagy Erőforráscsoportok lapon kell megadni a **következő** típusokhoz:
    -   **Gyártott költségek abszorbeáltak**
    -   **Gyártási költség felhasználva, befejezetlen termelés**

## <a name="indirect-costs-for-production-orders"></a>Termelési rendelések közvetett költségei

A termelési rendelés tranzakcióinak feldolgozásakor beállíthatja a közvetett költségeket úgy, hogy a főkönyvben rögzítik a járulékos költségeket vagy további díjakat. A közvetett költségek tényleges tranzakcióit a kitárolásilista-naplók és a készként jelentési naplók feladása során ismeri fel a készlet. A közvetett költségek pénzügyi tranzakcióit a rendszer a záró napló feladása során ismeri fel a készletben.

Az útvonalkártya-naplókhoz vagy feladatkártya-naplókhoz **·** **kapcsolódó** időfelhasználás közvetett költségei felismerhetők. Ezeket a tranzakciókat a termelési rendelés végén sztornírozja és feladja a pénzügyi számlákra. További tájékoztatás: Költségszámítási [táblázatok](/supply-chain/cost-management/costing-sheets.md).

## <a name="controlling-the-level-of-ledger-posting"></a>A főkönyvi feladás szintjének vezérlése

A Gyártásvezérlés **paraméterei** lapon a **Főkönyvi** feladás mező a termelési folyamatokhoz kapcsolódó főkönyvi feladás szintjének beállítására használható. 

Az alábbi mezők állnak rendelkezésre:

### <a name="item-and-resource"></a>Cikk és erőforrás

Ha a Főkönyvi **feladás** **mezőBen** a Cikk és erőforrás beállítást választja, akkor a feladási számlák az útvonal műveletének erőforrás vagy erőforráscsoportja alapján jönnek létre. Az adott erőforrás számlái lesznek az első feladási beállítás. Ha nincs megadva számla, az erőforráscsoportban megadott számlákat használja a alkalmazás. Az útvonal minden műveletsorában lehet egy költségszámítási erőforrásként megadott **erőforrás**. Ez az erőforrás a használt számla meghatározására használható. Ez a beállítás akkor használatos, amikor egy szervezet működési költségeket rendel az erőforrásokhoz. A költségek gyakran magasabbak az erőforrásoknál, és gyakran a "meghozás és vásárlás" döntésében segítenek. Ez a legrészletesebb feladási konfiguráció, és a legrészletesebben szabályozható a feladások és a termelési folyamat nagyon részletes analitika.

### <a name="item-and-category"></a>Cikk és kategória

Ha a Főkönyvi **feladás** **mezőben** a Cikk és kategória beállítást választja, **akkor** a feladási számlák az útvonal minden sorára vonatkozó Költségkategória lapról jönnek. Az útvonal minden műveletsorához három költségkategória tartozik: **beállítási** idő, **futási** idő és **a mennyiség**. Ez a beállítás általában akkor használatos, ha a szervezet fő feladata a folyamat hatékonysága és a tevékenység időtartama. Ez a beállítás egy összegzi a feladást, és így is kategóriákba csoportosítja a költségeket.

### <a name="production-group"></a>Termelési csoport

Ha a **Főkönyvi** **feladás** mezőben a Termeléscsoportok lehetőséget választja, akkor a feladási számlák a Termeléscsoportok **lapról jönnek.** **A termelési csoportokat** általában akkor használják, amikor egynél több termelési sorban hasonló termékek futnak, vagy hasonló berendezésekkel rendelkezik. Ezzel a beállítással összehasonlíthatja a költségeket két különböző termelési csoport között.  
  
> [!NOTE]
> Ha a késztermék költségének kiszámítására a szokásos módszert használja, akkor a végső tranzakciók tükrözik ezt. Ha a tényleges költségek és a normál módszerrel számított költségek eltérőek, a különbözeteket arra a számlára adják fel, amely az nyereséget vagy veszteséget mutatja.

### <a name="route-groups-and-ledger-posting"></a>Útvonalcsoportok és főkönyvi feladás

Az útvonal minden műveletsorában meg van **adva egy útvonalcsoport**. **A becslési** **és** költségszámítási csoport útvonalcsoportjában a beállítási idő, **·** **·** **a** futási idő és a mennyiség mező segítségével lehet szabályozni, hogy az idő költségszámításra használható-e **a** **termelési** rendelés feladatkártyája vagy útvonalkártya-naplója feladása során. Ha a beállítások nincsenek engedélyezve, nem jön létre bizonylat a főkönyvben az időfelhasználáshoz.

Ahhoz, hogy egy **termelési rendelés** **útvonalkártyája** vagy feladatkártya-naplója feladható legyen a főkönyvbe, teljesülnie kell a következő feltételeknek:

-   Az **Útvonalcsoport lap** Becslés és költségszámítás csoportjában be kell választani a Beállítási idő, **·** **·** **·** **a Futási idő vagy a Mennyiség mezőt.**
-   A fő számlákat vagy a **Költségkategória**, Útvonal, **Útvonalcsoport** **vagy** Termelési **csoportok** lapon kell megadni a következő feladási típusok esetén:
    -   Felhasznált becsült gyártási költség
    -   Felhasznált gyártás becsült költsége, befejezetlen termelés

A következő ábra bemutatja az útvonalcsoport és az adott útvonal egyes műveletei (útvonalsorok) teljes költségének számítása közötti viszonyt. Minden útvonalsorhoz egy útvonalcsoport tartozik. Az útvonalcsoport szabályozza a beállítási idő, a futási idő és a mennyiség paramétereit. A **Költségkategória lap** három beállítási **lehetőséget** kínál a beállításhoz, **a** futtatáshoz és a mennyiséghez, **amelyek** az útvonalcsoportok beállításai alapján engedélyezhetők. Az **Időzítések** gyorscsoportnak három mezője van, amelyek az útvonalcsoporton alapulnak.

A használt képlet azon alapul, hogy a beállítás engedélyezve van-e az útvonalcsoportban. A program megszorozza a kiválasztott költségkategóriából származó költséget az időmérésben megadott mennyiséggel, és így kiszámítja a teljes költséget.

:::image type="complex" source="media/RouteGroupRelationship.png" alt-text="Az útvonalcsoportok viszonya a teljes számított költséghez.":::
Az útvonalcsoportok viszonya a teljes számított költséghez. Minden útvonalsorhoz egy útvonalcsoport tartozik. Az útvonalcsoport szabályozza a beállítási idő, a futási idő és a mennyiség paramétereit. A költségkategória lap három beállítással rendelkezik az útvonalcsoportok beállításai alapján engedélyezett Beállítás, Futtatás és Mennyiség esetében. Az Időmérések gyorscsoport három mezőt tartalmaz, amelyek az útvonalcsoport alapján engedélyezve vannak és költségszámításban. A használt képlet azon alapul, hogy az útvonalcsoportban engedélyezve van-e a beállítás. A program megszorozza a kiválasztott költségkategóriából származó költséget az időmérésben megadott mennyiséggel, és így kiszámítja a teljes költséget.
:::image-end:::

## <a name="sample-posting-profile-configuration"></a>Minta feladási profil konfigurációja

Az alábbi táblázat példákat mutat be az alapértelmezett feladási típusokra a minta fő számlákkal és leírásokkal. 

 - A **Tartozik/Követel** oszlop jelzi, hogy a tranzakció általában Tartozik vagy Követel, vagy bizonyos esetekben fel is adhatja. 
 - Az **Elszámolószámla** oszlop jelzi, hogy a feladás elszámolószámla-e. Egy későbbi tranzakció feladása során a program automatikusan sztornírozi az erre a számlára feladott összeget. 
 - A **P/F** oszlop mutatja **, hogy tényleges feladásra P**, **pénzügyi feladásra pedig F**. 
 - A **Követés** oszlop jelzi, hogy egy adott feladási típus fő számlája általában megegyezik-e egy másik feladási típussal. Az oszlopban lévő érték jelzi a általában követett feladási típust.

> [!NOTE]
> Javaslatok a javasolt fő számlák és fő számlák nevei. Javasoljuk, hogy a könyvelővel együtt határozza meg, hogy az üzleti igényeknek megfelelő konfigurációt szeretné-e meghatározni.


| Feladás típusa  | Példa a fő számlára | Példa a fő számlanévre| Számla típusa | Tartozik/követel? | Elszámolási számla | Fizikai vagy pénzügyi | Kövesse | Leírás |
|---------------|----------------------|--------------------------|--------------|----------------|------------------|-----------------------|--------|------------|
| Felhasznált anyagok becsült költsége      | 140100               | Anyagkészlet        | Eszközök        | Jóváírás         | Y                | P                     | Felhasznált anyagok költsége                | Ez a számla akkor használatos, amikor kitárolásilista-naplót ad fel egy termelési rendeléshez. Ennek a számlának az ellenszámlája a becsült anyagköltség (folyamatban lévő termelés). A termelési rendelés végén a számlán automatikusan sztornírozódik az összeg. Ez a számla a készlet számlát jelöli a mérlegben.       |
| Felhasznált anyagok becsült költsége, befejezetlen termelés | 150150               | Termelési folyamatban lévő termelés - anyagok | Eszközök        | Terhelés          | Y                | P                     | Becsült gyártási költség, befejezetlen termelés          | Ez a számla akkor használatos, amikor kitárolásilista-naplót ad fel egy termelési rendeléshez. Ennek a számlának az ellenszámlája a felhasznált anyagok becsült költsége. A számlán a termelési rendelés végén a program automatikusan sztornírozja az összeget. Ez a számla a folyamatban lévő munka mérlegben való ábrázolását jelzi.                  |
| Becsült gyártási költség               | 140200               | Késztermékek készlete   | Eszközök        | Terhelés          | Y                | P                     | Gyártási költség                         | Ez a számla akkor használatos, amikor készként jelentési naplót ad fel egy termelési rendeléshez. Ennek a számlának az ellenszámlája a Becsült legyártott költség, amely a folyamatban lévő költségeket veszi figyelembe. A termelési rendelés végén a számlán automatikusan sztornírozódik az összeg. Ez a számla a készlet számlát jelöli a mérlegben. |
| Becsült gyártási költség, befejezetlen termelés          | 150150               | Termelési folyamatban lévő termelés - anyagok | Eszközök        | Jóváírás         | Y                | P                     | Gyártási költség, befejezetlen termelés                    | Ez a számla akkor használatos, amikor készként jelentési naplót ad fel egy termelési rendeléshez. Ennek a számlának az ellenszámlája a Becsült legyártott költség. A számlán a termelési rendelés végén a program automatikusan sztornírozja az összeget. Ez a számla a folyamatban lévő munka mérlegben való ábrázolását jelzi.                     |
| Felhasznált anyagok költsége                | 140100               | Anyagkészlet        | Eszközök        | Jóváírás         | N                 | P                     | Felhasznált anyagok becsült költsége      | Ezen a számlán lehet elismerni a termelési rendelés által a befejezési folyamat során felhasznált anyagokat. Ennek a számlának az ellenszámlája a felhasznált anyagok költsége, a folyamatban lévő termelés.                                                                                                    |
| Felhasznált anyagok költsége, befejezetlen termelés           | 150150               | Termelési folyamatban lévő termelés - anyagok | Eszközök        | Terhelés          | N                 | P                     | Felhasznált anyagok becsült költsége, befejezetlen termelés | Ezen a számlán lehet elismerni a folyamatban lévő olyan anyagokat, amelyek a termelési rendelés során a befejezési folyamat során felhasználnak. A számla ellenszámlája a felhasznált anyagköltség.                                                |
| Gyártási költség                         | 140200               | Késztermékek készlete   | Eszközök        | Terhelés          | N                 | P                     | Becsült gyártási költség               | Ezen a számlán lehet elismerni a termelési rendelés befejezésekor a termelési rendelés által előállított késztermék költségét. Ennek a számlának az ellenszámlája a Legyártott költség, folyamatban lévő termelés számla.                                                                  |
| Gyártási költség, befejezetlen termelés                    | 150150               | Termelési folyamatban lévő termelés - anyagok | Eszközök        | Jóváírás         | N                 | P                     | Becsült gyártási költség, befejezetlen termelés          | Ez a számla a készterméknek a termelési rendelés befejezésekor előállított folyamatban lévő költségeket ismeri fel. Ennek a számlának az ellenszámlája a Legyártott költség számla.                                     |

> [!NOTE]
> A **lean szolgáltatás folyamatban lévő termelésének bevételezési** **és** leanszolgáltatásos folyamatban lévő költségeket elszámoló számlája a lean manufacturing (lean gyártás) visszavezetéses költségszámítására használható. További tájékoztatás: Visszavezetéses [költségszámítás](/supply-chain/cost-management/backflush-costing.md).

