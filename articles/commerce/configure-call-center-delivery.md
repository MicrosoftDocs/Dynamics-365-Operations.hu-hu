---
title: Szállítási módok és költségek beállítása a hívásközponthoz
description: Ez a témakör leírja, hogyan lehet a hívásközpont rendeléshez tartozó költségeket és szállítási költségeket beállítani a Dynamics 365 Commerce szolgáltatásban.
author: josaw1
ms.date: 04/26/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailMCRChannelDetailPage, MCROrderParameters
audience: Application User
ms.reviewer: josaw
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-04-30
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: ac3d540ee3d1737e4e8be45394cd5807ae4a8d6f
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5796148"
---
# <a name="configure-call-center-delivery-modes-and-charges"></a>Szállítási módok és költségek beállítása a hívásközponthoz

[!INCLUDE [banner](includes/banner.md)]

Amikor leadnak egy értékesítési rendelést a Dynamics 365 Commerce szolgáltatásban, ha az értékesítési rendelést leadó személy hozzá van kapcsolva egy hívásközponti csatornához, a logika és a szabályok segítségével megtörténik a szállítás módjának (szállítási mód) ellenőrzése és a rendeléshez kapcsolódó költségek kiszámítása.

Értékesítési rendelés létrehozásakor az értékesítési rendelés fejlécén és az értékesítésirendelés-sorokban szereplő szállítási módok közül választhat. Alapértelmezés szerint a fejlécben kiválasztott szállítási mód fog szerepleni az összes értékesítésirendelés-sorban. Azonban szükség esetén felül lehet írni az alapértelmezett szállítási módot az egyes értékesítési sorokban. Vevőrekordban is meg lehet adni szállítási módot. Ezután amikor megtörténik a rendelések létrehozása a vevő számára, ezt a rendelési módot használja a rendszer alapértelmezettként az értékesítési rendelés fejlécében.

A Commerce funkciói lehetővé teszik a felhasználók számára, hogy korlátozzák a csatorna által használható szállítási módokat, a termékhez használt a szállítási módokat, és a meghatározott szállítási célokhoz érvényes szállítási módokat. A költségeket úgy is meg lehet határozni, hogy a kiegészítő költségek hozzáadódnak a vevő rendeléséhez, az értékesítési rendeléshez kijelölt szállítási módok és a rendelés teljes értéke alapján.

## <a name="define-delivery-modes"></a>Szállítási módok meghatározása

Mielőtt megadná, hogy mely szállítási módok használhatók a hívásközponti rendelésekhez, illetve meghatározná a kapcsolódó szabályokat és költségeket, meg kell adnia a szállítási módot. Lépjen az **Értékesítés és marketing \> Beállítás \> Elosztás \> Szállítási módok** pontra. Kattintson az **Új** lehetőségre új szállítási mód létrehozásához. Másik megoldásként válasszon a listából egy meglévő szállítási módot, majd válassza a **Szerkesztés** lehetőséges a szállítási mód módosításához.

A **Szállítási mód** mezőben alfanumerikus karakterek bármilyen kombinációját megadhatja az üzleti követelményei alapján. Ezután a **Leírás** mezőben további kontextust adhat meg. A **Költségcsoport** és **Sürgős** mezők kitöltése nem kötelező, és később részletesebben tárgyaljuk őket ebben a témakörben.

A **Commerce csatornák** gyorslapon adjon meg minden kiskereskedelmi csatornát, amely használhatja a szállítási módot, amikor értékesítési tranzakciót hoznak létre az adott csatornában.

A **Termékek** FastTabon adhatja meg, mely termékekhez és/vagy termékkategóriákhoz használható/nem használható a szállítási mód. Például ha egy terméket nem lehet légi úton szállítani veszélyes anyagokra vonatkozó korlátozás miatt, győződjön meg arról, hogy a termék vagy termékkategória ki van zárva az összes légi szállítást tartalmazó szállítási módból.

A **Címek** FastTabon adhatja meg, mely országokhoz/régiókhoz/államokhoz használható/nem használható a szállítási mód. Például a Hawaiira vagy Alaszkába szállított rendeléseknél nem engedélyezett a szárazföldi szállítás. Ezért ezeket az államokat ki kell zárni a szárazföldi szállítási szolgáltatásokhoz kapcsolódó szállítási módokból, de minden olyan szállítási módnak tartalmaznia kell őket, amely légi szállítási szolgáltatáshoz kapcsolódik.

## <a name="validate-delivery-modes-for-a-call-center-order"></a>Szállítási módok ellenőrzése hívásközponti rendelések esetén

Miután megadta a szállítási módokat, futtatnia kell a **Szállítási módok feldolgozása** kötegelt feladatot. Ez a feladat elérhetővé teszi a szállítási módokat, hogy használhatók legyenek az értékesítési rendelési folyamatoknál a csatornák esetén. A **Szállítási módok feldolgozása** feladat futtatásához lépjen a **Kiskereskedelem és kereskedelem \> Kiskereskedelem és kereskedelem IT \> Szállítási módok feldolgozása** pontra. Ezt a feladatot futtatni kell mindig, ha új szállítási módot ad hozzá egy csatornához vagy ha egy meglévő szállítási mód/csatorna kapcsolaton módosítást hajt végre.

Miután futtatta a **Szállítási módok feldolgozása** kötegelt feladatot, lépjen a **Kiskereskedelem és kereskedelem \> Csatornák \> Hívásközpontok \> Összes hívásközpont** ponthoz. Az **Összes hívásközpont** oldal műveleti paneljén, a **Beállítás** lapon válassza a **Szállítási módok** lehetőséget. A **Szállítási módok** lap felsorolja a kiválasztott hívásközponti csatornához tartozó összes érvényes szállítási módot. Új szállítási módok hozzáadásához vagy meglévő szállítási módok módosításához válassza a **Szállítási módok kezelése** lehetőséget. Vegye figyelembe, hogy a **Szállítási módok feldolgozása** feladatot minden módosításkor futtatnia kell.

## <a name="define-charges-for-delivery-services"></a>Szállítási szolgáltatásokhoz tartozó költségek megadása

A vevőkhöz tartozó értékesítési rendelések létrehozásakor előfordulhat, hogy a vállalat szeretne hozzáadni a rendeléshez kiválasztott szállítási módok alapján automatikusan kiszámított költségeket. Ezeket a költségeket be lehet úgy állítani, hogy az összes vevő és szállítási mód esetén azonosan legyenek. Másik lehetőségként a költségek változhatnak az értékesítési rendeléshez megadott vevőtől és/vagy szállítási módoktól függően.

A költségek meghatározásához lépjen a **Kiskereskedelem és kereskedelem \> Csatorna beállítása \> Költségek \> Automatikus költségek** ponthoz. Kattintson az **Új** lehetőségre új költségek hozzáadásához. Másik megoldásként válasszon ki egy meglévő bejegyzést, és válassza a **Szerkesztés** lehetőséget.

A költségek úgy is meghatározhatók, hogy a rendelés fejlécének vagy a rendelési soroknak a szintjén kerüljenek kiszámításra. Használja a **Szint** mezőt a kívánt szint kiválasztásához.

Egy bizonyos vevőre, vevőcsoportra vagy az összes vevőre érvényes költségek is megharározhat. A **Számlakód** mezőjében válassza a **Tábla** elemet, ha szeretne csak egy bizonyos vevőre vonatkozó költségek meghatározni. Válassza a **Csoport** lehetőséget egy bizonyos vevőcsoporthoz tartozó költségek meghatározásához. Válassza a **Minden** lehetőséget, ha a költségek szeretné minden olyan vevőre alkalmazni, aki a kapcsolódó szállítási módot használó értékesítési rendelést ad le. Ha kiválasztotta a **Tábla** vagy **Csoport** lehetőséget a **Számlakód** mezőben, válassza ki a vevőt vagy vevőcsoportot a **Számlakapcsolat** mezőben.

A költségek úgy is beállíthatók, hogy egy adott szállítási módra, egy szállításimód-csoportra vagy minden szállítási módra vonatkozzanak. Ha a **Tábla** lehetőséget választja a **Szállítási mód kódja** mezőben, választania kell egy adott szállítási módot a **Szállításimód-kapcsolat** mezőben. Ha a **Csoport** lehetőséget választja, választania kell egy szállításimód-csoportot a **Szállításimód-kapcsolat** mezőben. A szállításimód-csoportokat a **Kiskereskedelem és kereskedelem \> Csatorna beállítása \> Költségek \> Szállításiköltség-csoportok** pontban határozhatja meg. Ezek ezután hozzákapcsolhatja őket egy vagy több szállítási módokhoz a **Szállítási módok** oldalon. Ha a költségek meghatározásakor kiválaszt egy csoportot, a kiválasztott szállítási csoporthoz tartozó bármely szállítási módra ezek a költségek vonatkoznak majd. Végül, ha az **Összes** lehetőséget választotta a **Szállítási mód kódja** mezőben, minden szállítási módra ezek a költségek vonatkoznak majd. Ezért ne válasszon ki értéket a **Szállításimód-kapcsolat** mezőben.

A **Sorok** szakaszban szükség esetén megadhat egy vagy több költséget pénznemenként. A költségeket hozzá kell kapcsolni egy költségkódhoz, amely meghatározza a költségre vonatkozó pénzügyi feladási szabályokat. A **Kategória** mező segítségével határozható meg, hogyan történik a költségek számítása. Például ha a vevőknek 9,95 USD fix díjat kell felszámítani, hogy a megrendelésük kiszállítása egy adott szállítási móddal történjen, használja a **Rögzített** kategóriát. Ha a vállalat úgy dönt, hogy a rendelés végösszegének bizonyos százalékát terheli a vevőkre a szállítási költségek fedezéséhez, használja a **Százalék** kategóriát. A vevőknek felszámított tényleges költség a **Költségek értéke** mezőben szerepel.

A vállalatok gyakran állítanak be többszintű költségeket. Ebben az esetben a vevők a rendelés értéke alapján fizetnek a kiszállításért. Többszintű költségek beállításához adja meg az értékeket az **Összeg alsó határa** és az **Összeg felső határa** mezőkben, illetve definiálja magát a költséget a **Költségek értéke** mezőben. Például olyan rendeléseknél, amelyeknek az értéke kisebb, mint 50 USD, a kiskereskedő 5,95 USD költséget számít fel a szárazföldi szállításért. Olyan rendeléseknél, amely értéke egyenlő vagy nagyobb, mint 50 USD, de kevesebb, mint 100 USD, a kiskereskedő 7,95 USD költséget számít fel. Végül azokat a rendeléseket, amelyek értéke egyenlő vagy nagyobb, mint 100 USD, a kiskereskedő ingyenesen kiszállítja. Az alábbi ábra az említett költségek konfigurációját mutatja be.

![Példa rögzített többszintű költségekre](media/fixedtieredcharges.png)

Az üzleti szükségletektől függően a költségkategóriákat vegyesen is használhatja. Például minden olyan rendelésnél, amelynek az értéke kisebb, mint 100 USD, fix 9,95 USD költséget számítanak fel a szállításért. Azoknál a rendeléseknél, amelyeknek az értéke egyenlő vagy nagyobb, mint a 100 USD, a szállítási költséget a rendelés értékének 5 százaléka adja. Az alábbi ábra az említett költségek konfigurációját mutatja be.

![Példa vegyes többszintű költségekre](media/mixedtieredcharges.png)

## <a name="apply-delivery-modes-during-order-entry-in-a-call-center"></a>Szállítási módok alkalmazása a rendelésbevitel során egy hívásközpontban

Új értékesítési rendelés létrehozásakor meg kell adnia egy értéket a **Szállítási mód** mezőben a **Szállítás** FastTabon az értékesítési rendelés fejlécében. Lehet, hogy ez a mező automatikusan ki van töltve a vevőrekord alapértelmezett értékei alapján.

A rendelés fejlécében megadott szállítási mód a rendszer automatikusan átmásolja az értékesítésirendelés-sorokba azok létrehozásakor. Azonban módosíthatja a szállítási mód beállítását egy adott sortételre vonatkozóan a **Szállítás** lapon a **Sor adatai** résznél az értékesítésirendelés-bevitel oldalon.

Ha a kijelölt szállítási mód nem érvényes a rendeléshez vagy rendelési sorban megadott termékre vagy a szállítási címre, akkor megjelenik egy hibaüzenet. Ezután ki kell választania egy olyan szállítási módot, amelyet megadtak az adott termékhez vagy címkonfigurációhoz.

## <a name="calculation-of-delivery-charges-during-entry-of-order"></a>Szállítási költségek számítása rendelés bevitelekor

Ha a **Rendeléskiegészítés engedélyezése** beállítás engedélyezve van a hívásközponti csatorna esetében, az értékesítési rendelésekre vonatkozó szállítási költségeket a rendszer automatikusan kiszámítja, amikor a felhasználó kiválasztja a **Befejezés** lehetőséget. A következő üzenet jelenik meg az **Értékesítési rendelés összesítése** oldal a felső részén: "Többszintű költségek kiszámítva." A kiszámított költségek hozzáadódnak az **Értékesítés összesen** mező értékéhez. Az **Összeg** FastTabon, a **Költségek** mezőben látható a rendeléshez és a sorokhoz kiszámított költségek teljes összege. A költségek részletes lebontásának megtekintéséhez válassza a **Rendelés** lehetőséget az **Értékesítési rendelés összesítése** oldalon, majd válassza a **Költségek** lehetőséget a költségek megtekintéséhez, hozzáadásához és szerkesztéséhez. Vegye figyelembe, hogy a rendelési fejlécben szereplő szállítási költségek kiszámítása a fejléchez kapcsolt szállítási mód alapján történik. A sorszintű szállítási költségek számítása az értékesítési sorban beállított szállítási mód alapján történik. Ha több szállítási módot használ különböző sorokban, előfordulhat, hogy a rendszer több költséget vesz figyelembe és a költségek összeadódnak. Ezután megjelenik a teljes összeg a **Költségek** mezőben az **Értékesítési rendelés összesítése** oldalon.

Ha a **Rendeléskiegészítés engedélyezése** beállítás ki van kapcsolva, a felhasználóknak manuálisan kell elindítaniuk a költségek kiszámítását. Az **Értékesítési rendelés** oldal műveleti ablaktábláján, az **Eladás** lapon, a **Számítás** csoportban válassza ki a **Többszintű költségek** lehetőséget. Megjelenik a "Többszintű költségek kiszámítva" üzenet. Ezután kiválaszthatja a **Költségek** lehetőséget az **Eladás** lapon a kiszámított költségek megtekintéséhez, szerkesztéséhez vagy törléséhez.

## <a name="use-expedited-delivery-modes-on-call-center-orders"></a>Sürgős szállítási módok alkalmazása hívásközponti rendeléseknél

Minden konfigurált szállítási módhoz opcionálisan hozzákapcsolhat egy sürgősségi kódot. Ez a kód prioritási sorrend szerinti rendezéshez és jelentéskészítő eszközként használható. Jelenleg nem ad hozzá kiegészítő díjakat a rendeléshez. Sürgősségi kódok beállításához lépjen az **Értékesítés és marketing \> Beállítás \> Elosztás \> Sürgősségi kódok** ponthoz.

Például azokat a rendeléseket, amelyek következő napon kerülnek kiszállításra légi úton, fel kell venni a raktárból minden nap 13:00 óráig. Ebben az esetben létre lehet hozni egy sürgősségi kódot, és ezt a kódot hozzá lehet kapcsolni a rendszerben beállított minden egyes következő napi szállítási módhoz. Amikor a raktár létrehozza a kitárolási hullámot, a **Sürgős** mezőben szereplő megfelelő sürgősségi kód szűrőként használható, így csak azoknak a rendeléseknek a kitárolása történik meg, amelyeknek a szállítási módja hozzá van kapcsolva az adott kódhoz.

Továbbá a hívásközponti rendelés bevitelekor a sürgősségi kód manuális alkalmazható az értékesítési rendelés fejlécére vagy egy értékesítésirendelés-sorra. A kód rendezési és jelentési célokra használható. Bizonyos esetekben a megrendeléseket gondosan kell kezelni a vevőszolgálati hibák miatt. Ebben az esetben alkalmazhatunk egy meghatározott sürgősségi kódot a rendelés fejlécére vagy soraira, hogy segítsük a rendelés azonosítását és priorizálását a teljesítési folyamat során.


[!INCLUDE[footer-include](../includes/footer-banner.md)]