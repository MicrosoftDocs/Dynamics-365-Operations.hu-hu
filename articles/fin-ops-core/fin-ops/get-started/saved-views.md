---
title: Mentett nézetek
description: Ez a témakör azt ismerteti, hogyan lehet használni a mentett nézeteket.
author: jasongre
ms.date: 11/21/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2019-07-31
ms.dyn365.ops.version: Platform update 28
ms.openlocfilehash: 571a4f403da0d20256f788c791cab273827c91b5
ms.sourcegitcommit: fb9b6969218f2b82f0a4c72bfad75387fe00395c
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/22/2022
ms.locfileid: "9799491"
---
# <a name="saved-views"></a>Mentett nézetek

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

[!INCLUDE [PEAP](../../../includes/peap-1.md)]

## <a name="introduction"></a>Bevezetés

A személyre szabás fontos szerepet játszik abban, hogy a felhasználók és szervezetek számára lehetővé váljon a felhasználói élmény szükségleteire való optimalizálása. A személyre szabással kapcsolatos további részleteket lásd: [A felhasználói élmény testreszabása](personalize-user-experience.md).

A hagyományos személyre szabás segítségével a felhasználók oldalanként csak egy személyre szabási halmazt kínálnak. A **Mentett nézetek** funkció több fontos módon bővítik a személyre szabást:

- A nézetek lehetővé teszik a felhasználók számára, hogy űrlaponként több névvel ellátott testreszabással rendelkezzenek, és ezek között szükség szerint váltsanak. Ez lehetővé teszi a felhasználónak, hogy egy oldalhoz több optimalizált nézetet is létrehozzon, ahol az egyes nézeteket egy adott üzleti feladat végrehajtására vonatkozó szükségletekhez igazították. 
- A bizonyos típusú lapokhoz létrehozott nézetekben szerepelhetnek a felhasználó által hozzáadott szűrők vagy sorba rendezések is, így a felhasználók gyorsan visszatérhetnek a gyakran szűrt adathalmazokhoz. További részleteket a [Mely lapok támogatják a nézeteket](saved-views.md#what-pages-support-views) című szakaszban talál. 
- A nézetek közzétehetők bizonyos biztonsági szerepkörökben és konkrét jogi személyekben számára. Emiatt bármely felhasználó, aki meghatározott szerepkört tölt be, és hozzáfér egy adott jogi személyhez, hozzáférhet a nézethez, és használhatja azt a nézetet, még akkor is, ha nincs jogosultsága a személyre szabásra. Ez a közzétételi funkció lehetővé teszi a szervezetek számára, hogy az üzleti tevékenységekhez optimalizált vállalati standard nézeteket határozzanak meg. További információért lásd a [Testreszabások kezelése szervezeti szinten nézetekkel](saved-views.md#managing-personalizations-at-an-organizational-level-with-views) című szakaszban talál.
- A hagyományos testreszabással ellentétben a nézeteket a program nem menti automatikusan, amikor a felhasználó testreszabott beállításokat hajt végre, vagy listát szűr. Az kifejezett mentés szükséges ahhoz, hogy a felhasználók rugalmasan hozzanak létre nézeteket a nézethez társított módosítások előtt vagy után. Ez a követelmény biztosítja azt is, hogy a nézet definíciói nem módosulnak véletlenül olyan szűrők vagy egyéni beállítások alapján, amelyek nem hosszú távú használatra készülnek. A rendszer automatikusan tárolja azokat a cikkeket, amelyeket a rendszer a szokásos oldalszám részeként használ (például az oszlopok szélességét vagy a szakaszok kibontott vagy összeomlott állapotát).
- A nézeteket csempeként, listaként vagy hivatkozásként lehet felvenni a munkaterületekre. Ennek megfelelően a szűrt adatkészletek megjeleníthetők egy munkaterületen, és a felhasználók hozzárendelhetnek testreszabási készleteket, amelyek egy csempével vagy hivatkozással beállított adatokhoz kapcsolódnak.

## <a name="switching-between-views"></a>Váltás a nézetek között

Miután a nézeteket elérhetővé tették egy környezethez, a nézeteket támogató összes lap tartalmazni fog egy összecsukott nézetválasztót a felső részen, amely megjeleníti az aktuális nézet nevét.

A nézetválasztó két méretben elérhető: 

- **Nagyméretű nézetválasztók** – Az oldalakon, amelyeken jól láthatóan szerepel egy lista, nagyobb nézetválasztó szerepel több okból is. A legfontosabb, hogy a nagyobb nézetválasztó jelzi azokat a lapokat, amelyekben a felhasználó által definiált szűrők és rendezések használhatók. Mivel a nézetek szűrőket és rendezéseket tartalmaznak, ezért a nagyobb választó méretét is garantálja a rendszer, mivel a nézetnevek gyakran a képernyőn látható adatok legjobb leírásai lesznek, és az elvárás az, hogy a felhasználók leggyakrabban váltsak a nézetek között az ilyen laptípusokon. A rácson való csoportosítást nagy nézetválasztókkal is el lehet menteni nézetként. 
    
    [![Nagy nézetválasztó, amely támogatja a nézet lekérdezési módosításait.](./media/views-largeViewSelector.png)](./media/views-largeViewSelector.png)

- **Kisméretű nézetválasztók** – Az összes többi teljes képernyős oldalon (a munkaterületek és az irányítópult kivételével) az a kisméretű nézetválasztó szerepel, amelyik az oldalfelirat mellett jelenik meg. Ezeken az oldalakon a nézetek csak testreszabásokat tartalmaznak, nem pedig felhasználó által megadott szűrőket. Ezeken a lapokon gyakran a felirat vagy rekordcím a legfontosabb információ az oldal felső részén. A nézetválasztó kisebb mérete azt is tükrözi, hogy ezeken az oldalakon kisebb gyakorisággal lehet a nézetek váltására számítani. 
    
    [![Kis nézetválasztó, amely nem támogatja a nézeten végzett lekérdezésmódosításokat.](./media/views-smallViewSelector.png)](./media/views-smallViewSelector.png)
 
Ha kiválasztja a nézet nevét, megnyílik a nézetválasztó, és megjelenik a laphoz elérhető nézetek listája.

Ha a jobb **jogi személy támogatása a mentett** nézeteknél funkció be van kapcsolva, a nézetválasztó két szakaszban jeleníti meg a rendelkezésre álló nézeteket. Az első rész az aktuális jogalanyra jellemző nézeteket, a második pedig az összes jogalany számára elérhető nézeteket mutatja. Az első szakasz csak akkor látható, ha az oldalra vonatkozóan vannak jogalany-specifikus nézetek.

- **Standard nézet** – A **Standard** nézet a lap beépített nézetét jeleníti meg, ahol nem alkalmaztak kifejezett testreszabásokat.
- **Személyes nézetek** – A lakat nélküli nézetek az Ön személyes nézeteit jelenítik meg. Ezeket a nézeteket vagy Ön hozta létre, vagy a rendszergazda adta Önnek.
- **Zárolt nézetek** – Néhány nézeten (például a **Standard** nézet és a szerepkörbe feladott összes nézet) egy lakat szimbólum látható nézetválasztóban. Ez a jel azt jelzi, hogy a nézeteket nem lehet módosítani. Az oldalak használatát tükröző módosítások azonban automatikusan menti a program. Ezek a módosítások a rácsvonalak szélességének változását, valamint a gyorslap kibontott vagy összeomlott állapotának módosításait tartalmazzák. Azonban létrehozhat egy személyes nézetet az egyik zárol nézet alapján a **Mentés másként** művelettel, ha rendelkezik testreszabási jogosultságokkal.
- **Új nézetek** – Az olyan közzétett nézetek, amelyeket még nem nyitottak meg egy csillaggal a nézet nevének bal oldalán jelennek meg.

Másik nézetre történő váltáshoz először nyissa meg a nézetválasztót, majd válassza ki a betölteni kívánt nézetet. 

## <a name="creating-and-modifying-views"></a>Nézetek létrehozása és módosítása

A hagyományos személyre szabásra vonatkozó beállításoktól eltérően a nézeteket a program nem menti automatikusan, amikor a felhasználó személyre szabja a lapot, vagy ha a felhasználó szűrőket alkalmaz egy listában, vagy rendezi azt. A változtatások nézetbe mentéséhez explicit művelet szükséges. Az követelmény lehetővé teszi, hogy a felhasználók rugalmasan hozzanak létre nézeteket a nézethez társított módosítások előtt vagy után. Biztosítja azt is, hogy a nézet definícióit egyszeres szűrőkkel vagy személyre szabásokkal ne lehessen módosítani. Ne felejtse, hogy azok cikkek, amelyeket a rendszer a szokásos oldalszám részeként használ (például az oszlopok szélességét vagy a szakaszok kibontott vagy összeomlott állapotát), automatikusan elmentődnek a jelenlegi nézetbe, még a zárolt nézeteknél is.

Ha azt szeretné, hogy a nézet aktuális állapota ismert legyen, amikor a nézet módosítását a személyre szabásával vagy szűrésével kezdi, az aktuális nézet neve mellett egy csillag (\*) jelenik meg. Ez a jel azt jelzi, hogy az adott nézet egy nem mentett, módosított verziója.

[![Nézet nem mentett módosításai](./media/views-unsavedChanges.png)](./media/views-unsavedChanges.png)

Ha menteni szeretné azokat a módosításokat, hajtsa végre az alábbi lépéseket.

1. Válassza ki a nézet nevét a nézetválasztó megnyitásához.
2. A meglévő nézet módosításásához válassza a **Mentés** lehetőséget. Ne felejtse, hogy ez a művelet zárolt nézeteknél nem érhető el. 
3. Új nézet létrehozása:

    1. Válassza a **Mentés másként** lehetőséget. 
    2. A **Nézet mentése másként** ablaktáblán adjon meg egy nevet és opcionálisan egy leírást a nézethez.
    3. Ha azt szeretné, hogy ez a nézet legyen az alapértelmezett nézet, jelölje be a **Kitűzés alapértelmezettként** lehetőséget. Az alapértelmezett nézetekkel kapcsolatos további információkért lásd az [alapértelmezett nézet módosítása](#changing-the-default-view) című részt. 
    4. Ha be van **kapcsolva** a Jobb jogi személy támogatás a mentett nézetekhez funkcióval, akkor eldöntheti, hogy ez a nézet az összes jogi személy, vagy csak egy részcsoport számára legyen elérhető.
    5. Válassza a **Mentés** lehetőséget.

## <a name="changing-the-default-view"></a>Az alapértelmezett nézet módosítása

Az alapértelmezett nézet az a nézet, amelyet a rendszer megpróbál megnyitni, amikor először megnyitja a lapot. Ezt beállíthatja az alapértelmezett nézetre, amelyet a leggyakrabban fog használni. 

> [!NOTE]
> - Az alap **Mentéses nézetek** funkcióban egyetlen, globális alapértelmezett nézet van a jogalanyok között. Ha módosítja az alapértelmezett nézetet, akkor az adott nézet alapértelmezettként fog megnyílni, függetlenül attól, hogy éppen melyik jogi személyben van.
> - Ha a mentett **nézetek** továbbfejlesztett jogi személy támogatása funkció be van kapcsolva, akkor minden jogi személynek saját alapértelmezett nézete lehet egy oldalon.

Ha szeretné egy lap alapértelmezett nézetét módosítani, kövesse az alábbi lépéseket:

1. Váltson az alapértelmezettként használt nézetre. 
2. Válassza ki a nézet nevét a nézetválasztó megnyitásához. 
3. Válassza a **Továbbiak** elemet, majd a **Rögzítés alapértelmezettként** lehetőséget.

A másik lehetőség az, hogy amikor új nézetet hoz létre (a **Mentrés másként** művelettel), az új nézetet alapértelmezetté teheti, ha beállítja a **Rögzítés alapértelmezettként** beállítást a nézet mentése előtt.

> [!WARNING]
> Bizonyos esetekben az alapértelmezett nézethez tartozó lekérdezés nem fut le az oldal első megnyitásakor. Ha például egy lapot egy csempén keresztül nyit meg, akkor a rendszer a csempe lekérdezését az alapértelmezett nézethez társított lekérdezéstől függetlenül futtatja. Továbbá, ha olyan oldalt nyit meg, amely egy olyan **szabványos** nézetet tartalmaz, amely már rendelkezik meghatározott lekérdezéssel, az eredeti lekérdezés fog lefutni az alapértelmezett nézet lekérdezése helyett. Ebben az esetben tájékoztató üzenet jelenik meg, amikor a nézet be van töltve egy olyan beágyazott művelettel, amely lehetővé teszi az alapértelmezett nézet lekérdezésének közvetlen betöltését. Ha a lap betöltése után vált nézetet, a lekérdezésnek a várt módon kell futtatnia a nézetet. 

## <a name="managing-personal-views"></a>Személyes nézetek kezelése

A **Saját nézetek kezelése** párbeszédpanel a alapvető karbantartási funkciókat biztosít a személyes nézetekre vonatkozóan, valamint a nézetválasztóban a nézetek sorrendjére vonatkozóan. A lap megnyitásához kattintson a nézet nevére a nézetválasztó legördülő menü megnyitásához, válassza a **Továbbiak**, majd a **Saját nézetek kezelése** lehetőséget.

Ha be van **kapcsolva a Jobb jogi személy támogatása a mentett nézetekhez funkció,**  **·**  **a Nézetek kezelése párbeszédpanel Saját nézetek szakasza szakasz a szakaszokban elérhető nézeteket jeleníti meg.**  Az aktuális jogalanyra vonatkozó nézetek külön szakaszban jelennek meg. A **Globális nézetek** rész mindig megjelenik, így az oldalhoz az összes jogalanyban elérhető nézetek kezelhetők. 

Az adott lap elérhető nézeteinek listájához a következő műveletek állnak rendelkezésre.

- **Az alapértelmezett nézet módosítása** – A **Rögzítés alapértelmezettként** művelettel az aktuálisan kiválasztott nézetet az adott oldal alapértelmezett nézetévé teheti. Ha a **Jogi személyek importálása a mentett nézetek támogatásához** funkció be van kapcsolva, a **Globális nézetek** szakasz lehetővé teszi, hogy egy nézetet az aktuális jogi személy vagy az összes jogi személy alapértelmezett nézetévé tegyen.
- **Nézetek átrendezése** – A **Mozgatás felfelé** és **Mozgatás lefelé** műveletekkel átrendezheti a nézeteit egy meghatározott sorrendbe.
- **Nézet átnevezése** – Az **Átnevezés** művelet segítségével módosíthatja az aktuálisan kiválasztott személyes nézet nevét. Ez a művelet le van tiltva a zárolt nézeteknél. 
- **Nézet törlése** – A **Törlés** művelet segítségével véglegesen törölheti az aktuálisan kiválasztott nézetet az oldalról. Nincs mód a nézet helyreállítására az eltávolítás után.

A párbeszédpanelen végrehajtott módosítások a **Frissítés** gomb kiválasztása után lépnek hatályba.

## <a name="managing-personalizations-at-an-organizational-level-with-views"></a>Testreszabások kezelése nézetekkel a szervezet szintjén

Ennek a szakasznak a segítségével megtudhatja, hogy a mentett nézetek hogyan javítják a személyre szabások kezelését szervezeti szinten, ezért a szakasz leír bizonyos különbségeket a testreszabások kezelésében a **Mentett nézetek** funkcióval és anélkül.

Nézetek nélkül a rendszergazdák a Testreszabás oldalon keresztül egyéni beállításokat alkalmazhatnak egy adott laphoz egy felhasználóra vagy felhasználói csoportra vonatkozóan.  Ha ezek a felhasználók testreszabási jogokkal rendelkeznek, a testreszabásokat a rendszer alkalmazza az adott lapra. Azonban nem léteztek olyan képességek, amelyek megakadályozták a felhasználókat abban, hogy további testreszabásokat végezzenek a lapon, így a szervezet nem tudta biztosítani, hogy a felhasználók egy konzisztens felhasználói felülettel rendelkeznek. Ha ezeknek a felhasználóknak nem volt testreszabási jogosultsága, akkor a rendszergazda által számukra biztosított testreszabások nem töltődnek be. Ezenkívül ha új felhasználókat vettek fel a szervezetbe, a rendszergazdáknak manuálisan kellett betölteniük a testreszabásokat a felhasználó számára. Nem volt automatikus mechanizmus annak meghatározására, hogy az adott felhasználó számára milyen testreszabásoknak kell elérhetőnek lenniük abban a szerepkörben.

A **Mentett nézetek** funkció a testreszabások szervezeti szintű kezelésé sokkal könnyebbé teszi, elsősorban a nézetek felhasználói csoportokba történő közzétételének köszönhetően. A nézet közzététele után bármelyik felhasználó láthatja és használhatja a nézetet, akinek van egy meghatározott biztonsági szerepköre és hozzáférése a megadott jogi személyek valamelyikhez, akkor is láthatja és használhatja a nézetet, ha annak a felhasználónak nincs hozzáférése a személyre szabáshoz. Noha minden felhasználó rendelkezik a közzétett nézet egy változatával, amelyben az oldalhasználat elemeinek módosításait a rendszer automatikusan alkalmazza, egyik felhasználó sem menthet el a közzétett nézet lekérdezésére vonatkozó testreszabást vagy frissítést. Más szóval a közzétett nézetek zárolva vannak. Ezenkívül ha a jogi személyekben olyan szerep van az új felhasználókhoz rendelve, hogy a nézeteit közzétették, a program automatikusan megjeleníti a saját szerepkörével és jogi személyével társított nézeteket. Nincs szükség további műveletre az adminisztrátorrészéről. Hasonlóképpen, ha a felhasználók egy szervezet szerepköreit módosítják, vagy különböző jogi személyekhez kapnak hozzáférést előfordulhat, hogy már nem férnek hozzá a korábban közzétett nézetekhez. Még egyszer, az adminisztrátornak nem kell további lépéseket tennie.

Egy közzétett nézeten végzett frissítéseket könnyedén megoszthatják a felhasználókkal, ha a nézetet újból közzéteszik a megfelelő biztonsági szerepkörökbe és jogi személyekbe.

A közzétételi funkció lehetővé teszi a szervezetek számára, hogy az üzleti tevékenységekhez optimalizált vállalati standard nézeteket határozzanak meg, amelyeket a megadott biztonsági szerepkörökkel rendelkező felhasználóknak céloznak.

## <a name="publishing-views"></a>Nézetek közzététele

A közzétételi folyamat során a nézeteket egy vagy több jogi személyhez egy vagy több biztonsági szerepkörhez rendelhetik hozzá. Ezért minden olyan felhasználó, aki hozzáfér egy jogi személyhez, és aki hozzá van rendelve egy ilyen szerepkörhöz, hozzáférhet a nézetekhez. A felhasználó azonban nem szerkesztheti a nézeteket. Alapértelmezettként csak a rendszergazdák rendelkeznek hozzáféréssel a **Közzététel** művelethez a nézetválasztó legördülő menüben. A szervezet más megbízható felhasználói azonban hozzáférhetnek az új **Mentett nézetek adminisztrátora** szerepkörhöz.

A nézet közzétételéhez kövesse az alábbi lépéseket:

1. Hozzon létre és mentsen el a közzétenni kívánt nézet egy személyes példányát. 
2. A jelenleg betöltött nézetnél válassza ki a nézet nevét a nézetválasztó legördülő menü megnyitásához. 
3. Válassza a **Továbbiak** gombot, és válassza a **Közzététel** lehetőséget. Megnyílik **a** Közzététel párbeszédpanel.
4. Adja meg a nézet nevét. A név, amelyet megad az, mely a nézetet megkapó felhasználók számára megjelenik a nézetválasztóban. A lap közzétett nézeteinek egyedinek kell lennie. Egy laphoz nem engedélyezettek az ismétlődő nevek a közzétett nézeteknél, még ha az alkalmazott szerepkörök listája vagy jogi személyek különböznek is.
5.  **Ha** a szervezetnézetek fordítási támogatása be van kapcsolva, a szervezet által megkövetelt több nyelven adhat hozzá fordításokat a nézetnévhez úgy, **·**  **hogy** a Név mező melletti Fordítások gombra kattint. A nézet neve megjelenik a felhasználók számára az aktuális nyelven. Beállíthatja az alapértelmezett nyelvet is, hogy megadja azt a fordítást, amely azon felhasználók számára jelenik meg, akik olyan nyelveket futtatnak, amelyekhez nincs megadva fordítás.
5. Nem kötelező: Adja meg a nézet leírását, hogy a nézetet megkapó felhasználók jobban megértsék a nézet célját. 
6. Határozza meg, hogy a nézet a kiválasztott felhasználók számára alapértelmezett nézetként legyen-e közzétéve. Amikor egy nézetet alapértelmezettnek állítanak be, a felhasználók a céloldal legközelebbi megnyitásakor ezt a nézetet fogják látni. Minden célfelhasználó egyetlen globálisan alapértelmezett nézete fog változni. A felhasználók azonban továbbra is módosíthatják a saját alapértelmezett nézetüket a közzététel után.

    > [!NOTE]
    > Figyeljen a következő viselkedésre, amikor egy nézetet alapértelmezett nézetként tesz közzé:
    >
    > - Ha egy nézetet alapértelmezett nézetként tesz közzé néhány vagy minden jogi személy számára, a következő viselkedés történik:
    >
    >    - Ha csak az alap **Mentett nézetek** funkció van bekapcsolva, akkor az egyetlen, globális alapértelmezett nézet minden célzott felhasználó számára megváltozik. 
    >    - **Ha a **Mentett nézeteknél a jobb jogi személyek támogatása** be van kapcsolva, és a nézetet jogi személyek egy részcsoportja számára teszi közzé, akkor a jogi személyek alapértelmezett nézete minden megcélzott felhasználóra vonatkozóan módosul.
    >
    > - Ha egy felhasználónak több olyan nézete van, amelyek alapértelmezett nézetként vannak közzétéve, akkor a legutóbb közzétett nézet lesz a felhasználó alapértelmezett nézete. 
    > - A közzététel nem működik az AAD-csoportok használatával hozzárendelt szerepkörök esetében. 

8. Adja hozzá azokat a biztonsági szerepköröket, amelyek kapcsolódnak a nézetettel megcélzott felhasználókhoz. 
9. Határozza meg, hogy a nézetet szeretné-e közzétenni a kiválasztott biztonsági szerepkör alárendelt szerepköreihez. Ha ezt a lehetőséget választja, akkor a megfelelő biztonsági szerepkörök sorában jelölje be az **Alárendelt szerepkörökkel együtt** jelölőnégyzetet. Ne feledje, hogy ez a jelölőnégyzet nem érhető el olyan szerepkörök esetében, amelyek nem rendelkeznek alárendelt szerepkörökkel.
10. Adja hozzá azokat a jogi személyeket, amelyeknek számára ez a nézet elérhető kell legyen. 

    > [!NOTE]
    > Vegye figyelembe a következő viselkedést, ha egy nézetet egy adott jogalany számára tesz közzé, de nem teszi közzé alapértelmezett nézetként:
    >
    > - Ha csak az alap **Mentett nézetek** funkció van bekapcsolva, akkor a felhasználó által az oldalra kiválasztott nézetválasztó kezdetben csak a megadott jogalanyok nézetét jeleníti meg. A nézet első betöltése után azonban az oldal nézetválasztója mindig megjeleníti azt, függetlenül a jogi személytől.
    > - Ha a **mentett nézetek** továbbfejlesztett jogi személy támogatása funkció be van kapcsolva, a nézetválasztó csak a megadott jogi személyek nézetét fogja mutatni.

11. Válassza a **Közzététel** lehetőséget.

Ne feledje, hogy bizonyos környezetekben előfordulhat, hogy egy ideig (legfeljebb egy óráig) eltarthat, mielőtt a felhasználók megtekinthetik a közzétett nézetet.

## <a name="modifying-a-published-view"></a>Közzétett nézet módosítása

A nézet közzététele után lehet, hogy módosítani szeretné. Habár a közzétett nézetekben nem lehet élő változtatásokat végezni, mivel ezeket a nézeteket minden felhasználó számára (a közzétevőket is beleértve), a frissítések végrehajtása érdekében újból közzéteheti a nézeteket.

Ha a közzétett nézet módosításai csak a közzétételi paraméterekre vonatkoznak (a nézet neve és leírása, vagy a biztonsági szerepkörök, amelyekbe közzétették), tegye a következőket:

1. Váltson a közzétett nézetre a frissíteni kívánt paraméterekhez. 
2. A nézetválasztó legördülő menübőlv válassza az **Újbóli közzététel** lehetőséget. Ha 10.0.12-es vagy korábbi verziót használ, akkora meglévő nézet frissítéséhez ki kell választania a **Közzététel**, majd az **Igen** lehetőséget.
3. Frissítse a nézet nevét, leírását és jogi személyek biztonsági szerepkörét. 
4. Válassza a **Közzététel** lehetőséget. Ha a közzétett nézet eredetileg alapértelmezett nézetként volt kiválasztva, akkor az újbóli közzététel után ismét a felhasználók alapértelmezett nézete lesz. 

Ha a közzétett nézet módosításai a nézethez társított testreszabásokat vagy szűrőket módosítják, kövesse az alábbi lépéseket.

1. Töltse be a közzétett nézetet, amelyet változtatni szeretne. 
2. Végezze el a szükséges módosításokat a helyi piszkozatban.
3. A nézetválasztó legördülő menübőlv válassza az **Újbóli közzététel** lehetőséget.
4. Válassza az **Igen** lehetőséget, ha a nézetet a nem mentett módosításaival együtt szertené közzétenni. 
5. Módosítsa a módosítást igénylő közzétételi paramétereket, majd válassza a **Közzététel** lehetőséget. 

## <a name="managing-published-views"></a>Közzétett nézetek kezelése

A személyes nézetek kezeléséhez hasonlóan a **Saját nézetek kezelése** párbeszédpanel segítségével a közzétételi jogosultsággal rendelkező felhasználók rendelkezhetnek az adott oldal közzétett nézeteire vonatkozó alapszintű karbantartási lehetőségekkel (a saját személyes nézeteik mellett). A lap megnyitásához kattintson a nézet nevére a nézetválasztó legördülő menü megnyitásához, válassza a **Továbbiak**, majd a **Saját nézetek kezelése** lehetőséget.

Bár minden felhasználónak van egy **Saját** nézetek lapja, amely a személyes nézeteket jeleníti meg, **a** közzétételi jogosultságokkal rendelkező felhasználók szervezetnézetekkel is rendelkezik, amely az adott lap összes közzétett és közzé nem tett nézetét megjeleníti. Mivel előfordulhat, hogy több felhasználó is közzétesz nézeteket, ezért fontos, hogy a közzétett nézetek teljes listáját tudja kezelni, még akkor is, ha a nézetet ténylegesen nem Ön tette közzé.

Az adott lap összes közzétett nézetének listájához a következő műveletek állnak rendelkezésre. 

- **Újbóli közzététel** – Az **Újbóli közzététel** művelettel újból közzéteheti a nézeteket a későbbi közzétételi paraméterekkel (név, leírás, biztonsági szerepkörök).
- **Közzététel** – A **Közzététel** művelet segítségével közzétehet egy jelenleg közzé nem tett nézetet. 
- **Közzététel megszüntetése** – A **Közzététel megszüntetése** művelettel inaktívvá teheti a nézetet. A nézet továbbra is elérhető lesz a rendszerben, de a felhasználók nem fogják látni a nézetválasztóban addig, amíg a nézet újra közzé nem lesz téve.
- **Mentés személyesként** – A **Mentés személyesként** művelet a közzétett nézet személyes piszkozatának létrehozásához használható. Ez a funkció segít megérteni a nem publikált vagy az önnek még nem közzétett nézet tartalmát. A használatával szerkesztheti, majd újra közzéteheti a nézetet.
- **Törlés** – A közzétett vagy közzé nem tett nézetek végleges törléséhez használja az **Törlés** műveletet. Ez a művelet többek között eltávolítja a nézetet rendszer minden felhasználójától. A közzétett nézetek eltávolítása a **Mentés** gomb kiválasztása után lép érvénybe. A nézet törlése nem vonható vissza. 

## <a name="managing-views-globally"></a>Nézetek globális kezelése

Bár egyes vezetői képességek minden oldalon láthatóak, mint azt a jelen cikk is jelzi, **·**  **·**  **·**  a rendszergazdák és a mentett nézetgazdák a Személyre szabás oldalon holisztikaibb módon kezelhetik a rendszernézeteket. Ez a lap különösen a következő szakaszokat és funkciókat tartalmazza: 

- **Közzétett nézetek** – Ez a szakasz felsorolja azokat a nézeteket, amelyeket közzétettek a szervezeténél. Innen újra közzéteheti a nézeteket, miután módosítja azokat a biztonsági szerepköröket vagy jogi személyeket, amelyek a nézet céljai. Ezeket a nézeteket exportálhatja, törölheti vagy megszüntetheti a közzétételüket. Használhatja a **Mentés személyesként** műveletet a nézet személyes példányának létrehozásához, hogy a nézet módosítható legyen, vagy jobban megérthesse a tartalmát. 
- **Nem közzétett nézetek** – Ez a szakasz felsorolja a rendszerben jelenleg közzé nem tett szervezeti nézeteket. Ezek a nézetek többnyire az importálási képességen keresztül kerülnek be a rendszerbe. Ezeket a nézeteket közzéteheti, exportálhatja vagy törölheti. A 10.0.12 verzióban hozzáadott **Gyors közzététel** művelet lehetővé teszi, hogy az ebből a szakaszból származó több nézetet egy műveletben tegyék közzé, a meglévő biztonsági szerepkör és a jogi személy-konfigurációk segítségével. A mentés személyes műveletként **használható** a nézetek személyes másolatának létrehozására, így jobban megértheti a nézet tartalmát.
- **Személyes nézetek** – Ez a szakasz listázza az összes olyan nézetet, amelyeket a rendszerben lévő felhasználók hozták létre. Innen közzétehet személyes nézeteket a szervezeten belül, vagy egy vagy több nézetet másik felhasználók számára is átmásolhat. Ezeket a nézeteket igény szerint exportálhatja vagy törölheti is.
- **Felhasználói beállítások** – Válassza ki a megtekinteni kívánt felhasználót, vagy módosítsa a felhasználó személyre szabását a teljes rendszerben, vagy a felhasználó által látogatott oldalakon. A rendszerben a felhasználó személyre szabásával kapcsolatos adatokkat megtekintheti és dolgozhat is velük. Az adott felhasználóhoz tartozó összes személyre szabott elemet törölheti, vagy alaphelyzetbe állíthatja a funkcióbuborékokat a felhasználó számára. Ha vissza vannak állítva a funkcióbuborékok, az új funkciókat bemutató előugró ablakok és a felhasználó korábban elutasított funkciók az előugró ablakok legközelebb újra megjelennek a felhasználó számára.
- **Rendszerbeállítások:** – Itt tudja ideiglenesen kikapcsolni a rendszerben személyre szabásokat az összes felhasználó számára. Ebben az esetben semmilyen személyre szabás nem vonatkozik a felhasználókra, és az összes lap visszaáll az alapértelmezett állapotába. Amennyiben később újra bekapcsolja a személyre szabásokat, a rendszer minden személyre szabást újra alkalmaz. Véglegesen is törölheti a rendszerben szereplő személyes beállításokat az összes felhasználó számára. A törölt személyes beállításokat nem lehet visszaállítani. Ezért a lépés végrehajtása előtt ellenőrizze, hogy exportálta mindazokat a személyes beállításokat, amelyeket később esetleg importálni szeretne.

Azoknak a felhasználóknak, akik hozzáférnek a **Személyre szabás** lapjához, személyes vagy szervezeti nézeteket is importálhatunk a művelet ablak **Nézetek importálása** gombjának használatával. A szervezetnézetek esetén az **Azonnali közzététel** lehetőséget kiválasztva további explicit közzététel nélkül elérhetővé teheti a nézeteket a felhasználók számára.

## <a name="known-issues"></a>Ismert problémák

A mentett nézetekkel kapcsolatos ismert problémák listája a [Mentett nézeteket teljes mértékben használó Build-űrlapok](../../dev-itpro/user-interface/understanding-saved-views.md) témakörben találja.

## <a name="frequently-asked-questions"></a>Gyakori kérdések

### <a name="how-do-i-enable-saved-views-in-my-environment"></a>Hogyan lehet engedélyezni a mentett nézeteket a saját környezetemben?

> [!NOTE]
> A **Mentett nézetek** funkcióhoz engedélyezni kell a Pénzügyi és műveletalkalmazások Személyre szabási rendszerét. Ha a teljes környezetnél ki van kapcsolva a testreszabás, a nézeteket a rendszer akkor is letiltja, ha a lenti lépéseket elvégzi. 

A **Mentett nézetek** funkciót bármely környezetben be- és kikapcsolhatja a Funkciókezelés segítségével. Ha be van kapcsolva, a mentett nézetek minden későbbi felhasználói munkamenetben engedélyezve lesznek.

### <a name="what-happens-to-existing-personalizations-when-views-are-enabled"></a>Mi történik a meglévő testreszabásokkal a nézetek engedélyezésekor? 

A nézetek engedélyezésekor minden meglévő testreszabást, amely az adott felhasználóhoz és űrlaphoz létezik, a rendszer menti egy új **Saját nézet** elnevezésű nézetbe, amelyet automatikus nézetként állít be. Ezzel biztosítani lehet, hogy a felhasználói élmény konzisztens a nézetek engedélyezése előtt és után is, kivéve az űrlapokon megjelenő nézetválasztó vezérlőt.

### <a name="what-pages-support-views"></a>Mely lapok támogatják a nézeteket? 

A nézetek a legtöbb oldalon elérhetők, de nem minden oldalon. A nézetek jelenleg az irányítópultok kivételével minden teljes képernyős oldalon elérhetők. A munkaterületek támogatásának megtekintése a Mentett **nézetek támogatása munkaterületek funkcióval** érhető el. A legtöbb nem teljes képernyős lap, amely legördülő párbeszédpaneleket, kereséseket és továbbfejlesztett előnézeteket tartalmaz, jelenleg nem támogatja a nézeteket. A párbeszédpanelek támogatásának megjelenítése a **Mentett nézetek támogatása párbeszédpanelek funkcióval** érhető el.

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

### <a name="why-is-a-view-that-was-published-for-a-specific-legal-entity-visible-in-all-legal-entities"></a>Miért látható egy adott jogalany számára közzétett nézet az összes jogalanynál?

Ha egy nézetet közzétesz egy adott jogalany számára, de nem teszi közzé alapértelmezett nézetként, a következő viselkedés következik be:

- Ha csak az alap **Mentett nézetek** funkció van bekapcsolva, akkor a felhasználó által az oldalra kiválasztott nézetválasztó kezdetben csak a megadott jogalanyok nézetét jeleníti meg. A nézet első betöltése után azonban az oldal nézetválasztója mindig megjeleníti azt, függetlenül a jogi személytől. Ez a viselkedés azért fordul elő, mert a felhasználók a betöltéskor megkapják a közzétett nézet saját személyes példányát, és a személyes nézetek globálisak.
- Ha a **mentett nézetek** továbbfejlesztett jogi személy támogatása funkció be van kapcsolva, a nézetválasztó csak a megadott jogi személyek nézetét fogja mutatni. Ez a viselkedés azért következik be, mert a funkció lehetővé teszi, hogy a nézetek (beleértve a személyes nézeteket is) meghatározott jogi személyekhez kapcsolódjanak.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

