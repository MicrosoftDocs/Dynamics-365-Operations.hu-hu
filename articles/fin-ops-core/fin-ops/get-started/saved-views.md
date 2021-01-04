---
title: Mentett nézetek
description: Ez a témakör azt mutatja be, hogyan lehet használni a mentett nézetek funkcióit.
author: jasongre
manager: AnnBe
ms.date: 09/11/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2019-07-31
ms.dyn365.ops.version: Platform update 28
ms.openlocfilehash: 8537ec87c625e8b54cdf7574216d66f285da3a48
ms.sourcegitcommit: f5e31c34640add6d40308ac1365cc0ee60e60e24
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/08/2020
ms.locfileid: "4693701"
---
# <a name="saved-views"></a>Mentett nézetek

[!include [banner](../includes/banner.md)]

## <a name="introduction"></a>Bevezetés

A személyre szabás fontos szerepet játszik abban, hogy a felhasználók és szervezetek számára lehetővé váljon a felhasználói élmény szükségleteire való optimalizálása. A személyre szabással kapcsolatos további részleteket lásd: [A felhasználói élmény testreszabása](personalize-user-experience.md).

A hagyományos személyre szabással a felhasználók csak egyetlen testreszabási oldallal rendelkezhetnek. A **Mentett nézetek** funkció több fontos módon bővítik a személyre szabást:

- A nézetek lehetővé teszik a felhasználók számára, hogy űrlaponként több névvel ellátott testreszabással rendelkezzenek, és ezek között szükség szerint váltsanak. Ez lehetővé teszi a felhasználónak, hogy egy oldalhoz több optimalizált nézetet is létrehozzon, ahol az egyes nézeteket egy adott üzleti feladat végrehajtására vonatkozó szükségletekhez igazították. 
- A bizonyos típusú lapokhoz létrehozott nézetekben szerepelhetnek a felhasználó által hozzáadott szűrők vagy sorba rendezések is, így a felhasználók gyorsan visszatérhetnek a gyakran szűrt adathalmazokhoz. További részleteket a [Mely lapok támogatják a nézeteket](saved-views.md#what-pages-support-views) című szakaszban talál. 
- A nézetek közzétehetők bizonyos biztonsági szerepkörökben és konkrét jogi személyekben számára. Emiatt a megadott jogi személynél meghatározott szerepkörrel és hozzáféréssel rendelkező felhasználók hozzáférhetnek a nézethez, annak ellenére, hogy a felhasználó nem rendelkezik engedéllyel annak személyre szabásához. Ez a közzétételi funkció lehetővé teszi a szervezetek számára, hogy az üzleti tevékenységekhez optimalizált vállalati standard nézeteket határozzanak meg. További információért lásd a [Testreszabások kezelése szervezeti szinten nézetekkel](saved-views.md#managing-personalizations-at-an-organizational-level-with-views) című szakaszban talál.
- A hagyományos testreszabással ellentétben a nézeteket a program nem menti automatikusan, amikor a felhasználó testreszabott beállításokat hajt végre, vagy listát szűr. Az kifejezett mentés szükséges ahhoz, hogy a felhasználók rugalmasan hozzanak létre nézeteket a nézethez társított módosítások előtt vagy után. Ez a követelmény biztosítja azt is, hogy a nézet definíciói nem módosulnak véletlenül olyan szűrők vagy egyéni beállítások alapján, amelyek nem hosszú távú használatra készülnek. A rendszer automatikusan tárolja azokat a cikkeket, amelyeket a rendszer a szokásos oldalszám részeként használ (például az oszlopok szélességét vagy a szakaszok kibontott vagy összeomlott állapotát).
- A nézeteket csempeként, listaként vagy hivatkozásként lehet felvenni a munkaterületekre. Ennek megfelelően a szűrt adatkészletek megjeleníthetők egy munkaterületen, és a felhasználók hozzárendelhetnek testreszabási készleteket, amelyek egy csempével vagy hivatkozással beállított adatokhoz kapcsolódnak.

## <a name="switching-between-views"></a>Váltás a nézetek között

Miután a nézeteket elérhetővé tették egy környezethez, a nézeteket támogató összes lap tartalmazni fog egy összecsukott nézetválasztót a felső részen, amely megjeleníti az aktuális nézet nevét.

A nézetválasztó két méretben elérhető: 

- **Nagyméretű nézetválasztók** – Az oldalakon, amelyeken jól láthatóan szerepel egy lista, nagyobb nézetválasztó szerepel több okból is. A legfontosabb, hogy a nagyobb nézetválasztó jelzi azokat a lapokat, amelyekben a nézet a felhasználó által definiált szűrőket tartalmazhat. Mivel a nézetek tartalmazzák a szűrőket, a nagyobb méretű választó azért is garantált, mivel a nézetek nevei gyakran a legjobb leírást nyújtják a képernyőn látható adatokról, és arra számítunk, hogy a felhasználók ezeken az oldaltípusokon gyakrabban váltanak nézeteket.
- **Kisméretű nézetválasztók** – Az összes többi teljes képernyős oldalon (a munkaterületek és az irányítópult kivételével) az a kisméretű nézetválasztó szerepel, amelyik az oldalfelirat mellett jelenik meg. Ezeken az oldalakon a nézetek csak testreszabásokat tartalmaznak, nem pedig felhasználó által megadott szűrőket. Ezeken a lapokon gyakran a felirat vagy rekordcím a legfontosabb információ az oldal felső részén. A nézetválasztó kisebb mérete azt is tükrözi, hogy ezeken az oldalakon kisebb gyakorisággal lehet a nézetek váltására számítani. 
 
Ha kiválasztja a nézet nevét, megnyílik a nézetválasztó, és megjelenik a laphoz elérhető nézetek listája.

- **Standard nézet** – A **Standard** nézet a lap beépített nézetét jeleníti meg, ahol nem alkalmaztak kifejezett testreszabásokat.
- **Személyes nézetek** – A lakat nélküli nézetek az Ön személyes nézeteit jelenítik meg. Ezeket a nézeteket vagy Ön hozta létre, vagy a rendszergazda adta Önnek.
- **Zárolt nézetek** – Néhány nézeten (például a **Standard** nézet és a szerepkörbe feladott összes nézet) egy lakat szimbólum látható nézetválasztóban. Ez a jel azt jelzi, hogy a nézeteket nem lehet módosítani. Az oldalak használatát tükröző módosítások azonban automatikusan menti a program. Ezek a módosítások a rácsvonalak szélességének változását, valamint a gyorslap kibontott vagy összeomlott állapotának módosításait tartalmazzák. Azonban létrehozhat egy személyes nézetet az egyik zárol nézet alapján a **Mentés másként** művelettel, ha rendelkezik testreszabási jogosultságokkal.
- **Új nézetek** – Az olyan közzétett nézetek, amelyeket még nem nyitottak meg egy csillaggal a nézet nevének bal oldalán jelennek meg.

Másik nézetre történő váltáshoz először nyissa meg a nézetválasztót, majd válassza ki a betölteni kívánt nézetet. 

## <a name="creating-and-modifying-views"></a>Nézetek létrehozása és módosítása

A hagyományos személyre szabásra vonatkozó beállításoktól eltérően a nézeteket a program nem menti automatikusan, amikor a felhasználó személyre szabja a lapot, vagy ha a felhasználó szűrőket alkalmaz egy listában, vagy rendezi azt. A változtatások nézetbe mentéséhez explicit művelet szükséges. Az követelmény lehetővé teszi, hogy a felhasználók rugalmasan hozzanak létre nézeteket a nézethez társított módosítások előtt vagy után. Biztosítja azt is, hogy a nézet definícióit egyszeres szűrőkkel vagy személyre szabásokkal ne lehessen módosítani. Ne felejtse, hogy azok cikkek, amelyeket a rendszer a szokásos oldalszám részeként használ (például az oszlopok szélességét vagy a szakaszok kibontott vagy összeomlott állapotát), automatikusan elmentődnek a jelenlegi nézetbe, még a zárolt nézeteknél is.

Ha azt szeretné, hogy a nézet aktuális állapota ismert legyen, amikor a nézet módosítását a személyre szabásával vagy szűrésével kezdi, az aktuális nézet neve mellett egy csillag (\*) jelenik meg. Ez a jel azt jelzi, hogy az adott nézet egy nem mentett, módosított verziója.

Ha menteni szeretné azokat a módosításokat, hajtsa végre az alábbi lépéseket.

1. Válassza ki a nézet nevét a nézetválasztó megnyitásához.
2. A meglévő nézet módosításásához válassza a **Mentés** lehetőséget. Ne felejtse, hogy ez a művelet zárolt nézeteknél nem érhető el. 
3. Új nézet létrehozása:

    1. Válassza a **Mentés másként** lehetőséget. 
    2. Írja be a nézet nevét és (ha van) a leírását.
    3. Válassza a **Mentés** lehetőséget.

## <a name="changing-the-default-view"></a>Az alapértelmezett nézet módosítása

Az alapértelmezett nézet az a nézet, amelyet a rendszer megpróbál megnyitni, amikor először megnyitja a lapot. Ezt beállíthatja az alapértelmezett nézetre, amelyet a leggyakrabban fog használni. 

> [!NOTE]
> A vállalatok között létezik egy globális alapértelmezett nézet. Ha módosítja az alapértelmezett nézetet, akkor az adott nézet alapértelmezettként fog megnyílni, függetlenül attól, hogy éppen melyik jogi személyben van. 

Ha szeretné egy lap alapértelmezett nézetét módosítani, kövesse az alábbi lépéseket:

1. Váltson az alapértelmezettként használt nézetre. 
2. Válassza ki a nézet nevét a nézetválasztó megnyitásához. 
3. Válassza a **Továbbiak** elemet, majd a **Rögzítés alapértelmezettként** lehetőséget.

A másik lehetőség az, hogy amikor új nézetet hoz létre (a **Mentrés másként** művelettel), az új nézetet alapértelmezetté teheti, ha beállítja a **Rögzítés alapértelmezettként** beállítást a nézet mentése előtt.

Ne feledje, hogy bizonyos esetekben az alapértelmezett nézethez társított lekérdezés nem fut, amikor először megnyit egy oldalt. Ha például egy lapot egy csempén keresztül nyit meg, akkor a rendszer a csempe lekérdezését az alapértelmezett nézethez társított lekérdezéstől függetlenül futtatja. Ráadásul, ha egy olyan oldalt nyit meg, amelynek a **Standard** nézete már rendelkezik egy megadott lekérdezéssel, akkor az eredeti lekérdezés kerül futtatásra, és nem az alapértelmezett nézet lekérdezése. Ebben az esetben egy tájékoztató üzenet jelenik meg, amikor a nézet betöltődik. Ha a lap betöltése után vált nézetet, a lekérdezésnek a várt módon kell futtatnia a nézetet. A 10.0.10-es vagy újabb verzió a kapott tájékoztató üzenet beágyazott művelettel fog rendelkezik, amely lehetővé teszi az alapértelmezett nézet lekérdezésének közvetlen betöltését.

## <a name="managing-personal-views"></a>Személyes nézetek kezelése

A **Saját nézetek kezelése** párbeszédpanel a alapvető karbantartási funkciókat biztosít a személyes nézetekre vonatkozóan, valamint a nézetválasztóban a nézetek sorrendjére vonatkozóan. A lap megnyitásához kattintson a nézet nevére a nézetválasztó legördülő menü megnyitásához, válassza a **Továbbiak**, majd a **Saját nézetek kezelése** lehetőséget.

Az adott lap elérhető nézeteinek listájához a következő műveletek állnak rendelkezésre.

- **Az alapértelmezett nézet módosítása** – A **Rögzítés alapértelmezettként** művelettel az aktuálisan kiválasztott nézetet az adott oldal alapértelmezett nézetévé teheti.
- **Nézetek átrendezése** – A **Mozgatás felfelé** és **Mozgatás lefelé** műveletekkel átrendezheti a nézeteit egy meghatározott sorrendbe.
- **Nézet átnevezése** – Az **Átnevezés** művelet segítségével módosíthatja az aktuálisan kiválasztott személyes nézet nevét. Ez a művelet le van tiltva a zárolt nézeteknél. 
- **Nézet törlése** – A **Törlés** művelet segítségével véglegesen törölheti az aktuálisan kiválasztott nézetet az oldalról. Nincs mód a nézet helyreállítására az eltávolítás után.

Az ebben a párbeszédablakban elvégzett módosítások a **Mentés** gomb megnyomása után lépnek érvénybe.

## <a name="managing-personalizations-at-an-organizational-level-with-views"></a>Testreszabások kezelése nézetekkel a szervezet szintjén

Ennek a szakasznak a segítségével megtudhatja, hogy a mentett nézetek hogyan javítják a személyre szabások kezelését szervezeti szinten, ezért a szakasz leír bizonyos különbségeket a testreszabások kezelésében a **Mentett nézetek** funkcióval és anélkül.

Nézetek nélkül a rendszergazdák a Testreszabás oldalon keresztül egyéni beállításokat alkalmazhatnak egy adott laphoz egy felhasználóra vagy felhasználói csoportra vonatkozóan.  Ha ezek a felhasználók testreszabási jogokkal rendelkeznek, a testreszabásokat a rendszer alkalmazza az adott lapra. Azonban nem léteztek olyan képességek, amelyek megakadályozták a felhasználókat abban, hogy további testreszabásokat végezzenek a lapon, így a szervezet nem tudta biztosítani, hogy a felhasználók egy konzisztens felhasználói felülettel rendelkeznek. Ha ezeknek a felhasználóknak nem volt testreszabási jogosultsága, akkor a rendszergazda által számukra biztosított testreszabások nem töltődnek be. Ezenkívül ha új felhasználókat vettek fel a szervezetbe, a rendszergazdáknak manuálisan kellett betölteniük a testreszabásokat a felhasználó számára. Nem volt automatikus mechanizmus annak meghatározására, hogy az adott felhasználó számára milyen testreszabásoknak kell elérhetőnek lenniük abban a szerepkörben.

A **Mentett nézetek** funkció a testreszabások szervezeti szintű kezelésé sokkal könnyebbé teszi, elsősorban a nézetek felhasználói csoportokba történő közzétételének köszönhetően. Miután közzétették a nézetet, minden olyan felhasználó hozzáférhet, aki rendelkezik a meghatározott biztonsági szerepkörök valamelyikével és rendelkezik hozzáféréssel valamelyikhez, a megadott jogi személyek láthatják és használhatják a nézetet, annak ellenére, hogy a felhasználó nem fér hozzá a testreszabáshoz. Noha minden felhasználó rendelkezik a közzétett nézet egy változatával, amelyben az oldalhasználat elemeinek módosításait a rendszer automatikusan alkalmazza, egyik felhasználó sem menthet el a közzétett nézet lekérdezésére vonatkozó testreszabást vagy frissítést. Más szóval a közzétett nézetek zárolva vannak. Ezenkívül ha a jogi személyekben olyan szerep van az új felhasználókhoz rendelve, hogy a nézeteit közzétették, a program automatikusan megjeleníti a saját szerepkörével és jogi személyével társított nézeteket. Nincs szükség további műveletre az adminisztrátorrészéről. Hasonlóképpen, ha a felhasználók egy szervezet szerepköreit módosítják, vagy különböző jogi személyekhez kapnak hozzáférést előfordulhat, hogy már nem férnek hozzá a korábban közzétett nézetekhez. Még egyszer, az adminisztrátornak nem kell további lépéseket tennie.

Egy közzétett nézeten végzett frissítéseket könnyedén megoszthatják a felhasználókkal, ha a nézetet újból közzéteszik a megfelelő biztonsági szerepkörökbe és jogi személyekbe.

A közzétételi funkció lehetővé teszi a szervezetek számára, hogy az üzleti tevékenységekhez optimalizált vállalati standard nézeteket határozzanak meg, amelyeket a megadott biztonsági szerepkörökkel rendelkező felhasználóknak céloznak.

## <a name="publishing-views"></a>Nézetek közzététele

A közzétételi folyamat során a nézeteket egy vagy több jogi személyhez egy vagy több biztonsági szerepkörhez rendelhetik hozzá. Ezért minden olyan felhasználó, aki hozzáfér egy jogi személyhez, és aki hozzá van rendelve egy ilyen szerepkörhöz, hozzáférhet a nézetekhez. A felhasználó azonban nem szerkesztheti a nézeteket. Alapértelmezettként csak a rendszergazdák rendelkeznek hozzáféréssel a **Közzététel** művelethez a nézetválasztó legördülő menüben. A szervezet más megbízható felhasználói azonban hozzáférhetnek az új **Mentett nézetek adminisztrátora** szerepkörhöz.

A nézet közzétételéhez kövesse az alábbi lépéseket:

1. Hozzon létre és mentsen el a közzétenni kívánt nézet egy személyes példányát. 
2. A jelenleg betöltött nézetnél válassza ki a nézet nevét a nézetválasztó legördülő menü megnyitásához. 
3. Válassza a **Továbbiak** gombot, és válassza a **Közzététel** lehetőséget. Megnyílik a Közzététel párbeszédpanel.
4. Adja meg a nézet nevét és (ha van) a leírását. A név, amelyet megad az, mely a nézetet megkapó felhasználók számára megjelenik a nézetválasztóban. A lap közzétett nézeteinek egyedinek kell lennie. Egy laphoz nem engedélyezettek az ismétlődő nevek a közzétett nézeteknél, még ha az alkalmazott szerepkörök listája vagy jogi személyek különböznek is.
5. **10.0.9-es vagy újabb verzió:** Határozza meg, hogy a nézet a kiválasztott felhasználók számára alapértelmezett nézetként legyen-e közzétéve. Amikor egy nézetet alapértelmezettnek állítanak be, a felhasználók a céloldal legközelebbi megnyitásakor ezt a nézetet fogják látni. Minden célfelhasználó egyetlen globálisan alapértelmezett nézete fog változni. A felhasználók azonban továbbra is módosíthatják a saját alapértelmezett nézetüket a közzététel után.
6. Adja hozzá azokat a biztonsági szerepköröket, amelyek kapcsolódnak a nézetettel megcélzott felhasználókhoz. 
7. **A 10.0.13-as és későbbi verzió:** Határozza meg, hogy a nézetet szeretné-e közzétenni a kiválasztott biztonsági szerepkör alárendelt szerepköreihez. Ha ezt a lehetőséget választja, akkor a megfelelő biztonsági szerepkörök sorában jelölje be az **Alárendelt szerepkörökkel együtt** jelölőnégyzetet. Ne feledje, hogy ez a jelölőnégyzet nem érhető el olyan szerepkörök esetében, amelyek nem rendelkeznek alárendelt szerepkörökkel.
7. Adja hozzá azokat a jogi személyeket, amelyeknek számára ez a nézet elérhető kell legyen. 
8. Válassza a **Közzététel** lehetőséget.

Ne feledje, hogy bizonyos környezetekben előfordulhat, hogy egy ideig (legfeljebb egy óráig) eltarthat, mielőtt a felhasználók megtekinthetik a közzétett nézetet.

> [!NOTE]
> Vegye figyelembe a következő elvárásokat, amikor a nézetet közzéteszi egy jogi személynek, vagy amikor a nézetet alapértelmezett nézetként teszi közzé.
> - Ha egy vagy több jogi személy számára látható nézetet tesz közzé, akkor minden egyes célfelhasználó egyetlen globálisan alapértelmezett nézetét módosítja. Ha egy felhasználónak több olyan nézete van, amelyek alapértelmezett nézetként vannak közzétéve, akkor a legutóbb közzétett nézet lesz a felhasználó alapértelmezett nézete. 
> - Ha jogi személynek teszi közzé a nézetet, de nem alapértelmezett nézetként teszi közzé, akkor csak a megadott jogi személy felhasználók fogják látni a nézetválasztóban. A nézet első betöltése után azonban mindig a felhasználó nézetválasztójának oldalán jelenik meg, a jogi személytől függetlenül. 

## <a name="modifying-a-published-view"></a>Közzétett nézet módosítása

A nézet közzététele után lehet, hogy módosítani szeretné. Habár a közzétett nézetekben nem lehet élő változtatásokat végezni, mivel ezeket a nézeteket minden felhasználó számára (a közzétevőket is beleértve), a frissítések végrehajtása érdekében újból közzéteheti a nézeteket.

Ha a közzétett nézet módosításai csak a közzétételi paraméterekre vonatkoznak (a nézet neve és leírása, vagy a biztonsági szerepkörök, amelyekbe közzétették), tegye a következőket:

1. Váltson a közzétett nézetre a frissíteni kívánt paraméterekhez. 
2. A nézetválasztó legördülő menübőlv válassza az **Újbóli közzététel** lehetőséget. Ha 10.0.12-es vagy korábbi verziót használ, akkora meglévő nézet frissítéséhez ki kell választania a **Közzététel**, majd az **Igen** lehetőséget.
3. Frissítse a nézet nevét, leírását és jogi személyek biztonsági szerepkörét. 
4. Válassza a **Közzététel** lehetőséget. 
5. **10.0.8-as és korábbi verzió:** Ha a közzétett nézet nevét frissítette, akkor törölnie kell a régi nevet tartalmazó közzétett nézetet is. (További információt a [Közzétett nézetek kezelése](saved-views.md#managing-published-views) szakaszban találhat.)

**10.0.9-es és újabb verzió:** Ha a közzétett nézet eredetileg alapértelmezett nézetként volt kiválasztva, akkor az újbóli közzététel után a ismét a felhasználók alapértelmezett nézete lesz.

Ha a közzétett nézet módosításai a nézethez társított testreszabásokat vagy szűrőket módosítják, kövesse az alábbi lépéseket: 

**10.0.13-as és újabb verzió:** Végezze el a szükséges módosításokat közvetlenül a nézetben. A nézet neve mellett egy csillag (\*) jelenik meg.

1. Töltse be a közzétett nézetet, amelyet változtatni szeretne. 
2. Végezze el a szükséges módosításokat a helyi piszkozatban.
3. A nézetválasztó legördülő menübőlv válassza az **Újbóli közzététel** lehetőséget.
4. Válassza az **Igen** lehetőséget, ha a nézetet a nem mentett módosításaival együtt szertené közzétenni. 
5. Módosítsa a módosítást igénylő közzétételi paramétereket, majd válassza a **Közzététel** lehetőséget. 

**10.0.12-es és újabb verzió**

1. Töltse be a közzétett nézetet, amelyet módosítani szeretne. 
2. Mentse el a közzétett nézet másolatát, amellyel létrehoz egy helyi vázlatot a közzétett nézetből. 
3. Módosítsa a helyi vázlatot a szükséges módosításokkal.
4. Tegye közzé a nézetet az eredeti névvel. 

## <a name="managing-published-views"></a>Közzétett nézetek kezelése

A személyes nézetek kezeléséhez hasonlóan a **Saját nézetek kezelése** párbeszédpanel segítségével a közzétételi jogosultsággal rendelkező felhasználók rendelkezhetnek az adott oldal közzétett nézeteire vonatkozó alapszintű karbantartási lehetőségekkel (a saját személyes nézeteik mellett). A lap megnyitásához kattintson a nézet nevére a nézetválasztó legördülő menü megnyitásához, válassza a **Továbbiak**, majd a **Saját nézetek kezelése** lehetőséget.

Habár minden felhasználónak van **Saját nézetek** lapja, amely a személyes nézeteiket jeleníti meg, a közzétételi jogosultsággal rendelkező felhasználók egy **Szervezeti nézetek** lapot is látnak, amelyen szerepel az adott oldalhoz közzétett és közzé nem tett összes nézet. Mivel előfordulhat, hogy több felhasználó is közzétesz nézeteket, ezért fontos, hogy a közzétett nézetek teljes listáját tudja kezelni, még akkor is, ha a nézetet ténylegesen nem Ön tette közzé.

Az adott lap összes közzétett nézetének listájához a következő műveletek állnak rendelkezésre. 

- **Újbóli közzététel** – Az **Újbóli közzététel** művelettel újból közzéteheti a nézeteket a későbbi közzétételi paraméterekkel (név, leírás, biztonsági szerepkörök).
- **Közzététel** – A **Közzététel** művelet segítségével közzétehet egy jelenleg közzé nem tett nézetet. 
- **Közzététel megszüntetése** – A **Közzététel megszüntetése** művelettel inaktívvá teheti a nézetet. A nézet továbbra is elérhető lesz a rendszerben, de a felhasználók nem fogják látni a nézetválasztóban addig, amíg a nézet újra közzé nem lesz téve.
- **Mentés személyesként** – A **Mentés személyesként** művelet a közzétett nézet személyes piszkozatának létrehozásához használható. Ez a funkció segít megérteni a nem publikált vagy az önnek még nem közzétett nézet tartalmát. A használatával szerkesztheti, majd újra közzéteheti a nézetet. Ez a funkció a 10.0.12 verzióban kerül bemutatásra.
- **Törlés** – A közzétett vagy közzé nem tett nézetek végleges törléséhez használja az **Törlés** műveletet. Ez a művelet többek között eltávolítja a nézetet rendszer minden felhasználójától. A közzétett nézetek eltávolítása a **Mentés** gomb kiválasztása után lép érvénybe. A nézet törlése nem vonható vissza. 

## <a name="managing-views-globally"></a>Nézetek globális kezelése

Bár egyes felügyeleti képességek megjelennek az összes oldalon, ahogyan a jelen témakörben is szerepel, a **rendszergazdák** és a **mentett nézet adminisztrátorok** a **Személyre szabás** oldalon keresztül a rendszerre nézve holisztikusabban kezelhetik a nézeteket. Ez a lap különösen a következő szakaszokat és funkciókat tartalmazza: 

- **Közzétett nézetek** – Ez a szakasz felsorolja azokat a nézeteket, amelyeket közzétettek a szervezeténél. Innen újra közzéteheti a nézeteket, miután módosítja azokat a biztonsági szerepköröket vagy jogi személyeket, amelyek a nézet céljai. Ezeket a nézeteket exportálhatja, törölheti vagy megszüntetheti a közzétételüket. A 10.0.12 és későbbi verziókban a **Mentés személyesként** művelet használható a nézet személyes példányának létrehozásához, hogy a nézet módosítható legyen, vagy jobban megérthesse a tartalmát. 
- **Nem közzétett nézetek** – Ez a szakasz felsorolja a rendszerben jelenleg közzé nem tett szervezeti nézeteket. Ezek a nézetek többnyire az importálási képességen keresztül kerülnek be a rendszerbe. Ezeket a nézeteket közzéteheti, exportálhatja vagy törölheti. A 10.0.12 verzióban hozzáadott **Gyors közzététel** művelet lehetővé teszi, hogy az ebből a szakaszból származó több nézetet egy műveletben tegyék közzé, a meglévő biztonsági szerepkör és a jogi személy-konfigurációk segítségével. A 10.0.12 és későbbi verziókban a **Mentés személyesként** művelet használható a nézetek személyes példányainak létrehozásához, hogy jobban megérthesse a tartalmukat.
- **Személyes nézetek** – Ez a szakasz listázza az összes olyan nézetet, amelyeket a rendszerben lévő felhasználók hozták létre. Innen közzétehet személyes nézeteket a szervezeten belül, vagy egy vagy több nézetet másik felhasználók számára is átmásolhat. Ezeket a nézeteket igény szerint exportálhatja vagy törölheti is.
- **Felhasználói beállítások** – Válassza ki a megtekinteni kívánt felhasználót, vagy módosítsa a felhasználó személyre szabását a teljes rendszerben, vagy a felhasználó által látogatott oldalakon. A rendszerben a felhasználó személyre szabásával kapcsolatos adatokkat megtekintheti és dolgozhat is velük. Az adott felhasználóhoz tartozó összes személyre szabott elemet törölheti, vagy alaphelyzetbe állíthatja a funkcióbuborékokat a felhasználó számára. Ha vissza vannak állítva a funkcióbuborékok, az új funkciókat bemutató előugró ablakok és a felhasználó korábban elutasított funkciók az előugró ablakok legközelebb újra megjelennek a felhasználó számára.
- **Rendszerbeállítások:** – Itt tudja ideiglenesen kikapcsolni a rendszerben személyre szabásokat az összes felhasználó számára. Ebben az esetben semmilyen személyre szabás nem vonatkozik a felhasználókra, és az összes lap visszaáll az alapértelmezett állapotába. Amennyiben később újra bekapcsolja a személyre szabásokat, a rendszer minden személyre szabást újra alkalmaz. Véglegesen is törölheti a rendszerben szereplő személyes beállításokat az összes felhasználó számára. A törölt személyes beállításokat nem lehet visszaállítani. Ezért a lépés végrehajtása előtt ellenőrizze, hogy exportálta mindazokat a személyes beállításokat, amelyeket később esetleg importálni szeretne.

Azoknak a felhasználóknak, akik hozzáférnek a **Személyre szabás** lapjához, személyes vagy szervezeti nézeteket is importálhatunk a művelet ablak **Nézetek importálása** gombjának használatával. A 10.0.12 verzióban és a későbbiekben egy olyan mechanizmust is hozzáadtak, amely azonnal közzéteszi a nézeteket importálásuk alkalmával.

## <a name="known-issues"></a>Ismert problémák
A mentett nézetekkel kapcsolatos ismert problémák listája a [Mentett nézeteket teljes mértékben használó Build-űrlapok](../../dev-itpro/user-interface/understanding-saved-views.md) témakörben találja.

## <a name="frequently-asked-questions"></a>Gyakori kérdések

### <a name="how-do-i-enable-saved-views-in-my-environment"></a>Hogyan lehet engedélyezni a mentett nézeteket a saját környezetemben?

> [!NOTE]
> A **Mentett nézetek** funkció használatához engedélyeznie kell a Finance and Operations rendszerben a testreszabási rendszert. Ha a teljes környezetnél ki van kapcsolva a testreszabás, a nézeteket a rendszer akkor is letiltja, ha a lenti lépéseket elvégzi. 

**10.0.13-as vagy újabb verzió**

A **Mentett nézetek** funkció már nem szerepel az előzetes verzióban. Már közvetlenül a Funkciókezelésen keresztül elérhető bármilyen környezetben.

**10.0.9-estől a 10.0.12-es verziókig**

A **Mentett nézetek** funkció elérhető közvetlenül a Funkciókezelésben bármilyen környezetben. A többi nyilvános előnézeti funkcióhoz hasonlóan a funkció engedélyezése termelési környezetben a [Kiegészítő felhasználási szerződés](https://go.microsoft.com/fwlink/?linkid=2105274) hatálya alá tartozik.

**10.0.8/32-es platformfrissítés vagy korábbi**

A **Mentett nézetek** funkció engedélyezhető az 1. szintű (fejlesztés/tesztelés) és a 2. szintű (tesztkörnyezet) környezetekben, hogy az alábbi lépések követésével további teszteket és tervezési változtatásokat lehessen biztosítani.

1. **Engedélyezze a tesztcsomagot**: hajtsa végre a következő SQL-utasítást: 

    `INSERT INTO SYSFLIGHTING (FLIGHTNAME, enabled, FLIGHTSERVICEID, PARTITION) VALUES('CLISavedViewsEnableFeature', 1, 0, 5637144576);`

2. **IIS alaphelyzetbe állítása** a statikus tesztelési gyorsítótár kiürítéséhez. 
3. **Keresse meg a funkciót**: ugorjon a **Funkciók kezelése** munkaterületre. Ha a **Mentett nézetek** nem jelennek meg a listában, válassza ki a **Frissítések keresése** lehetőséget.
4. **Engedélyezze a funkciót**: keresse meg a **Mentett nézetek** funkciót a funkciólistában, majd válassza ki az **Engedélyezés most** lehetőséget a részleteket tartalmazó ablaktáblán.

Minden további felhasználói munkamenet engedélyezett mentett nézetekkel indul.

### <a name="what-happens-to-existing-personalizations-when-views-are-enabled"></a>Mi történik a meglévő testreszabásokkal a nézetek engedélyezésekor? 

A nézetek engedélyezésekor minden meglévő testreszabást, amely az adott felhasználóhoz és űrlaphoz létezik, a rendszer menti egy új **Saját nézet** elnevezésű nézetbe, amelyet automatikus nézetként állít be. Ezzel biztosítani lehet, hogy a felhasználói élmény konzisztens a nézetek engedélyezése előtt és után is, kivéve az űrlapokon megjelenő nézetválasztó vezérlőt.

### <a name="what-pages-support-views"></a>Mely lapok támogatják a nézeteket? 

A nézetek elérhetők a legtöbb oldalon, bár nem mindegyiken. Pontosabban a nézetek jelenleg elérhetők az összes teljes képernyős lapon, kivéve az irányítópultokon és munkaterületeken. A nem teljes képernyős lapok, például a párbeszédpanelek, legördülő párbeszédpanelek, keresések, valamint a továbbfejlesztett előnézetek jelenleg nem támogatják a nézeteket. A további oldaltípusok, például a munkaterületek és párbeszédablakok esetében a nézetek támogatása esetlegesen egy jövőbeli frissítésben lehetséges.

### <a name="who-is-allowed-to-publish-views"></a>Kinek van engedélye a nézetek közzétételére?

Csak azok az adminisztrátorok és felhasználók férhetnek hozzá a nézetekhez, akiket a **Mentett nézetek adminisztrátora** szerepkörhöz hozzárendeltek. 

### <a name="why-am-i-not-able-to-save-filters-with-this-view"></a>Miért nem tudom elmenteni a szűrőket ezzel a nézettel? 

Számos oka lehet annak, hogy egy szűrő miért nem menthető egy nézettel: 

- A lap valószínűleg nem támogatja a szűrők mentését a nézet definíciójának részeként. Ne felejtse el, hogy csak nagy méretű nézetválasztókat tartalmazó lapokon lehet nézetként menteni a testreszabásokat és a lekérdezések módosítását. További információt a **Nézetek váltása** szakaszban találhat. 
- Előfordulhat, hogy a kérdéses oldal nem megfelelően támogatja a nézeteket, mivel teljesen figyelmen kívül hagyhatja a nézetlekérdezést, vagy olyan ideiglenes táblán működhet, amelynek adatai nem állandóak. 

### <a name="what-data-will-i-see-when-i-visit-a-page"></a>Milyen adatok jelennek meg a lap meglátogatása alkalmával?

A kis nézetű választókat tartalmazó lapok esetében (csak testreszabások menthetők a nézethez), ugyanazokat az adatokat fogja látni, mint a lap meglátogatásakor. 

A nagyméretű nézetű választókat tartalmazó lapok esetében (testreszabások és lekérdezések is menthetők a nézethez), leginkább az alapértelmezett nézethez társított lekérdezéshez kapcsolódó adatokat fogja látni. Két fő kivétel van:

- Ha például egy lapra egy csempéről navigál, akkor a rendszer végrehajtja a csempe lekérdezését az alapértelmezett nézethez társított lekérdezéstől függetlenül. Ha azt követően hozta létre a csempét, hogy a nézeteket már engedélyezték, akkor a csempe választásával megnyílik a lap a csempéhez társított nézettel.
- Ha egy oldalra navigál, és a belépési pont rendelkezik egy lekérdezéssel, akkor az eredeti lekérdezés kerül végrehajtásra, és nem az alapértelmezett nézet lekérdezése. Erre egy tájékoztató üzenet figyelmeztet, amikor a nézet betöltődik. Megerősítheti az adott nézetre váltást az oldal betöltődése után is, mivel ettől függetlenül engedélyezi a nézet lekérdezésének végrehajtását.
