---
title: Mentett nézetek
description: Ez a témakör azt mutatja be, hogyan lehet használni a mentett nézetek funkcióit.
author: jasongre
manager: AnnBe
ms.date: 08/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2019-07-31
ms.dyn365.ops.version: Platform update 28
ms.openlocfilehash: 4b1bd7b869b68f82ce8056ac9f87a0d3bdce4102
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/27/2019
ms.locfileid: "2190879"
---
# <a name="saved-views"></a>Mentett nézetek

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

## <a name="introduction"></a>Bevezetés
A személyre szabás fontos szerepet játszik abban, hogy a felhasználók és szervezetek számára lehetővé váljon a felhasználói élmény szükségleteire való optimalizálása. A személyre szabással kapcsolatos további részleteket lásd: [A felhasználói élmény testreszabása](personalize-user-experience.md).

A hagyományos személyre szabással a felhasználók űrlaponként csak egyetlen testreszabási készlettel rendelkezhetnek. A mentett nézetek több fontos módon bővítik a személyre szabást:

-    A nézetek lehetővé teszik a felhasználók számára, hogy űrlaponként több névvel ellátott testreszabással rendelkezzenek, és ezek között szükség szerint váltsanak. Ez lehetővé teszi a felhasználónak, hogy egy oldalhoz több optimalizált nézetet is létrehozzon, ahol az egyes nézeteket egy adott üzleti feladat végrehajtására vonatkozó szükségletekhez igazították. 

-    A bizonyos típusú lapokhoz létrehozott nézetekben szerepelhetnek a felhasználó által hozzáadott szűrők vagy sorba rendezések is, így a felhasználók gyorsan visszatérhetnek a gyakran szűrt adathalmazokhoz. További részleteket a [Mely lapok támogatják a nézeteket](saved-views.md#what-pages-support-views) című szakaszban talál. 

-    A nézetek közzétehetők a biztonsági szerepkörökben, ami azt jelenti, hogy az adott szerepkörrel rendelkező felhasználók hozzáférhetnek a nézethez, és használhatják is, a felhasználó testreszabási képességeitől függetlenül. Ez a közzétételi funkció lehetővé teszi a szervezetek számára, hogy az üzleti tevékenységekhez optimalizált vállalati standard nézeteket határozzanak meg. További információt a [Testreszabások kezelése szervezeti szinten nézetekkel](saved-views.md#managing-personalizations-at-an-organizational-level-with-views) című szakaszban talál.

-    A hagyományos testreszabással ellentétben a nézeteket a program nem menti automatikusan, amikor a felhasználó kifejezetten testreszabott beállításokat hajt végre, vagy listát szűr. A kifejezett mentés szükséges a rugalmasság biztosítása érdekében a nézetek létrehozása során, mielőtt és miután az adott nézethez társított módosításokat végrehajtják, és biztosítja, hogy a nézetek meghatározásai véletlenül nem módosulnak a nem hosszú távra szánt szűrések és testreszabások által.  

## <a name="switching-between-views"></a>Váltás a nézetek között
Miután a nézeteket engedélyezték egy környezethez, a nézeteket támogató összes lap tartalmazni fog egy összecsukott nézetválasztót a képernyő felső részén, amely megjeleníti az aktuális nézet nevét.  

A nézetválasztó két méretben elérhető: 

-   **Nagyméretű nézetválasztók**: Az oldalakon, amelyeken jól láthatóan szerepel egy lista, nagyobb nézetválasztó szerepel több okból is. A legfontosabb, hogy a nagyobb nézetválasztó jelzi azokat a lapokat, amelyekben a nézet a felhasználó által definiált szűrőket tartalmazhat. Mivel a nézetek tartalmazzák a szűrőket, a nagyobb méretű választó azért is garantált, mivel a nézetek nevei gyakran a legjobb leírást nyújtják a képernyőn látható adatokról, és arra számítunk, hogy a felhasználók ezeken az oldaltípusokon gyakrabban váltanak nézeteket.  
 
-   **Kisméretű nézetválasztók**: az összes többi teljes oldalas űrlapon (a munkaterületek és az irányítópult kivételével) az a kisméretű nézetválasztó szerepel, amelyik az oldalfelirat mellett jelenik meg. Ezeken az oldalakon a nézetek csak testreszabásokat tartalmaznak (és nincsenek felhasználó által megadott szűrők). Ezeken a lapokon gyakran az űrlap felirata vagy rekordcíme a legfontosabb információ az űrlap felső részén. A kisebb méret azt is tükrözi, hogy ezeken az oldalakon kisebb gyakorisággal lehet a nézetek váltására számítani. 
 
Ha rákattint a nézet nevére, megnyílik a nézetválasztó, és megjelenik az adott laphoz elérhető nézetek listája.

-    **Klasszikus nézet**: A klasszikus nézet a lap beépített nézetét jeleníti meg, ahol nem alkalmaztak kifejezett testreszabásokat.  
-    **Személyes nézetek**: A lakat nélküli nézetek az Ön személyes nézeteit jelenítik meg. Ezeket a nézeteket vagy Ön hozta létre, vagy a rendszergazda adta Önnek.  
-    **Zárolt nézetek**: Bizonyos nézetek (például a Klasszikus nézet, vagy az Ön szerepkörébe közzétett nézetek) neve mellett egy lakat szerepel a nézetválasztóban, amely azt jelenti, hogy Ön nem szerkesztheti ezeket a nézeteket. A rendszer azonban automatikusan menti az oldal használatát jelző implicit testreszabásokat, például a rácsoszlop szélességének módosítását, vagy egy gyorslap kibontását vagy összecsukását. Azonban létrehozhat egy személyes nézetet az egyik zárol nézet alapján a **Mentés másolatként** művelettel, ha rendelkezik testreszabási jogosultságokkal.
-    **Új nézetek**: Az olyan közzétett nézetek, amelyeket még nem nyitottak meg, vonallal körberajzolva láthatók, egy csillaggal a nézet nevének bal oldalán.  

Másik nézetre történő váltáshoz először nyissa meg a nézetválasztót, majd válassza ki a betölteni kívánt nézetet. 

## <a name="creating-and-modifying-views"></a>Nézetek létrehozása és módosítása
A hagyományos testreszabással ellentétben a nézeteket a program nem menti automatikusan, amikor a felhasználó kifejezetten testreszabott beállításokat hajt végre (vagy listát szűr). A változtatások nézetbe mentéséhez explicit művelet szükséges. Ez biztosítja a felhasználói rugalmasságot a nézetek létrehozása során, mielőtt és miután az adott nézethez társított módosításokat végrehajtják, és azt is biztosítja, hogy a nézetek meghatározásai véletlenül nem módosulnak az egyszeri szűrések és testreszabások által. Vegye azonban figyelembe, hogy a rendszer automatikusan menti az implicit testreszabásokat (például a rácsoszlop szélességének módosítását, vagy egy gyorslap kibontását vagy összecsukását) az aktuális nézetbe, még zárolt nézetek esetén is. 

Annak érdekében, hogy biztosan ismerje a nézet aktuális állapotát, a nézet explicit testreszabás vagy szűrés általi módosítása során egy csillag jelenik meg az aktuális nézetnév mellett, amely azt jelzi, hogy az adott nézet nem mentett, módosított verzióját látja.

Ha menteni szeretné azokat a módosításokat, hajtsa végre az alábbi lépéseket.
1.  Válassza ki a nézet nevét a nézetválasztó megnyitásához.
2.  A meglévő nézet módosítása:
     1. Válassza a **Mentés** lehetőséget. Ne felejtse el, hogy ez a művelet zárolt nézetekhez nem engedélyezett. 
3.  Új nézet létrehozása:
     1.    Válassza a **Másolat mentése** lehetőséget. 
     2.    Írja be a nézet nevét és (ha van) a leírását.
     3.    Válassza a **Mentés** lehetőséget.

## <a name="changing-the-default-view"></a>Az alapértelmezett nézet módosítása
Az alapértelmezett nézet az a nézet, amelyet a rendszer megpróbál megnyitni, amikor először navigál a lapra. Ezt beállíthatja arra a nézetre, amelyet a leggyakrabban fog használni.  

Ha szeretné egy lap alapértelmezett nézetét módosítani, kövesse az alábbi lépéseket: 
1.  Váltson az alapértelmezettként használt nézetre. 
2.  Válassza ki a nézet nevét a nézetválasztó megnyitásához. 
3.  Válassza a **Továbbiak** elemet, majd a **Rögzítés alapértelmezettként** lehetőséget.  

A másik lehetőség az, hogy amikor új nézetet hoz létre (a **Másolat mentése** művelettel), az új nézetet alapértelmezetté teheti, ha beállítja a **Rögzítés alapértelmezettként** beállítást a nézet mentése előtt.  

Ne feledje, hogy bizonyos esetekben az alapértelmezett nézethez társított lekérdezés nem hajtható végre, amikor először navigál egy oldalra. Ha például egy lapra egy csempén keresztül navigál, akkor a rendszer végrehajtja a csempe lekérdezését az alapértelmezett nézethez társított lekérdezéstől függetlenül. Ha egy olyan oldalra navigál, amelynek a Klasszikus nézete már rendelkezik egy megadott lekérdezéssel, akkor az eredeti lekérdezés kerül végrehajtásra, és nem az alapértelmezett nézet lekérdezése. Ha ez történik, akkor erre egy tájékoztató üzenet figyelmeztet, amikor a nézet betöltődik. A nézetek a lap betöltése utáni váltásának lehetővé kell tennie a nézet lekérdezése számára, hogy az elvártaknak megfelelően megvalósuljon.

## <a name="managing-personal-views"></a>Személyes nézetek kezelése 
A **Saját nézetek kezelése** párbeszédpanel a alapvető karbantartási funkciókat biztosít a személyes nézetekre vonatkozóan, valamint a nézetválasztóban a nézetek sorrendjére vonatkozóan. A lap megnyitásához kattintson a nézet nevére a nézetválasztó legördülő menü megnyitásához, válassza a **Továbbiak**, majd a **Saját nézetek kezelése** lehetőséget.  

Az adott lap elérhető nézeteinek listájához a következő műveletek állnak rendelkezésre.  
-    **Az alapértelmezett nézet módosítása**: A **Rögzítés alapértelmezettként** művelettel az aktuálisan kiemelt nézetet az adott oldal alapértelmezett nézetévé teheti.  
-    **Nézetek átrendezése**: A **Mozgatás felfelé** és **Mozgatás lefelé** műveletekkel átrendezheti a nézeteit egy meghatározott sorrendbe.  
-    **Nézet átnevezése**: Az **Átnevezés** művelet segítségével módosíthatja az aktuálisan kiemelt személyes nézet nevét. Ez a művelet le van tiltva a zárolt nézeteknél. 
-    **Nézet törlése**: Az **Eltávolítás** művelet segítségével véglegesen törölheti az aktuálisan kiemelt nézetet az oldalról. Nincs mód a nézet helyreállítására az eltávolítás után.  

Az ebben a párbeszédablakban elvégzett módosítások a **Mentés** gomb megnyomása után lépnek érvénybe.

## <a name="managing-personalizations-at-an-organizational-level-with-views"></a>Testreszabások kezelése nézetekkel a szervezet szintjén
A testreszabások kezelésére vonatkozó szervezeti szintű fejlesztések megértéséhez először nézzük meg, hogy a nézetek előtt hogyan működött a testreszabás kezelése.  

Nézetek nélkül a rendszergazdák a Testreszabás oldalon keresztül egyéni beállításokat alkalmazhatnak egy adott laphoz egy felhasználóra vagy felhasználói csoportra vonatkozóan.  Ha ezek a felhasználók testreszabási jogokkal rendelkeznek, a testreszabásokat a rendszer alkalmazza az adott lapra. Azonban nem léteztek olyan képességek, amelyek megakadályozták a felhasználókat abban, hogy további testreszabásokat végezzenek a lapon, így a szervezet nem tudta biztosítani, hogy a felhasználók egy konzisztens felhasználói felülettel rendelkeznek. Ha ezeknek a felhasználóknak nem volt testreszabási jogosultsága, akkor a rendszergazda által számukra biztosított testreszabások nem töltődnek be. Ezenkívül ha új felhasználókat vettek fel a szervezetbe, a rendszergazdáknak manuálisan kellett betölteniük a testreszabásokat a felhasználó számára. Nem volt automatikus mechanizmus annak meghatározására, hogy az adott felhasználó számára milyen testreszabásoknak kell elérhetőnek lenniük abban a szerepkörben.

Az elmentett nézetek funkcióval a testreszabások szervezeti szintű kezelése jelentősen könnyebb, elsősorban a nézetek biztonsági szerepkörökbe történő közzétételének köszönhetően. A nézetek közzétételét követően az adott szerepkörrel rendelkező felhasználók hozzáférhetnek a nézethez, és használhatják is, a felhasználó testreszabási képességeitől függetlenül. Npha minden felhasználó rendelkezik a közzétett nézet egy változatával, amelyben az oldalhasználat módosításait (implicit testreszabásokat) a rendszer automatikusan alkalmazza, egyik felhasználó sem menthet el a közzétett nézet lekérdezésére vonatkozó testreszabást vagy frissítést (azaz a közzétett nézetek zároltak). Ezenkívül ha új felhasználókhoz olyan szerepkört rendelnek, amelybe a nézetet közzétették, akkor ők automatikusan megtekinthetik a szerepkörükhöz társított nézeteket a rendszergazda küözbenjárása nélkül is. Hasonlóképpen ha egy felhasználó szerepköre megváltozik a szervezeten belül, a korábbi szerepköréhez társított nézetekhez már nem férhet hozzá, szintén a rendszergazda közbenjárása nélkül. Egy közzétett nézeten végzett frissítéseket könnyedén megoszthatják a felhasználókkal, ha a nézetet újból közzéteszik a megfelelő biztonsági szerepkörökbe.

A közzétételi funkció lehetővé teszi a szervezetek számára, hogy az üzleti tevékenységekhez optimalizált vállalati standard nézeteket határozzanak meg, amelyeket a megadott biztonsági szerepkörökkel rendelkező felhasználóknak céloznak.  

## <a name="publishing-views"></a>Nézetek közzététele
A közzétételi folyamat során a nézeteket egy vagy több biztonsági szerepkörhöz lehet rendelni, ami azt jelenti, hogy az adott szerepkörrel rendelkező felhasználók hozzáférhetnek a nézethez, és használhatják, de a nézetet nem szerkeszthetik. Jelenleg csak a rendszergazdáknak van joga a **Közzététel** művelet használatához a nézetválasztó legördülő menüből. Egy későbbi frissítésben azonban lesz egy olyan új biztonsági szerepkör, amely más megbízható felhasználóknak is közzétételi jogokat ad.  

A nézet közzétételéhez kövesse az alábbi lépéseket: 
1.  Hozzon létre és mentsen el a közzétenni kívánt nézet egy személyes példányát. 
2.  A jelenleg betöltött nézetnél válassza ki a nézet nevét a nézetválasztó legördülő menü megnyitásához. 
3.  Válassza a **Továbbiak** gombot, és válassza a **Közzététel** lehetőséget. Megnyílik a Közzététel párbeszédpanel.  
4.  Adja meg a nézet nevét és (ha van) a leírását. Ez az a név, amelyet a nézetet megkapó felhasználók számára megjelenik a nézetválasztóban. Ne feledje, hogy egy laphoz nem engedélyezettek az ismétlődő nevek a közzétett nézeteknél, még ha az alkalmazott szerepkörök listája különbözik.  
5.  Adja hozzá azokat a biztonsági szerepköröket, amelyek kapcsolódnak a nézetet megkapó felhasználókhoz.  
6.  Válassza a **Közzététel** lehetőséget.

Ne feledje, hogy bizonyos környezetekben előfordulhat, hogy egy ideig (legfeljebb egy óráig) eltarthat, mielőtt a felhasználók megtekinthetik a közzétett nézetet.

## <a name="modifying-a-published-view"></a>Közzétett nézet módosítása
A nézet közzététele után előfordulhat, hogy a módosításokat szeretne végrehajtani a közzétett nézeten. Noha a közzétett nézetekben nem lehet élő változtatásokat végezni, mivel ezeket a nézeteket minden felhasználó számára (a közzétevőket is beleértve) a szerkesztésre zárolták, a frissítések végrehajtása érdekében újból közzéteheti a nézeteket.  

Ha a közzétett nézet módosításai csak a közzétételi paraméterekre vonatkoznak (a nézet neve és leírása, vagy a biztonsági szerepkörök, amelyekbe közzétették), tegye a következőket: 
1.  Váltson a közzétett nézetre a frissíteni kívánt paraméterekhez. 
2.  Válassza a **Közzététel** lehetőséget a nézetválasztó legördülő menüből. 
3.  Válassza az **Igen** beállítást, ha frissíteni szeretné a meglévő nézetet (vagy a **Nem** lehetőséget, ha ezt a nézetet más néven szeretné közzétenni).
4.  Frissítse a nézet nevét, leírását és/vagy biztonsági szerepkörét. 
5.  Válassza a **Közzététel** lehetőséget. 
6.  Ha a közzétett nézet nevét frissítette, a régi névvel rendelkező közzétett nézetet is törölni kell (lásd a **Közzétett nézetek kezelése** szakaszt a részletekért). 

Ha a közzétett nézet módosításai a nézethez társított testreszabásokat vagy szűrőket módosítják, kövesse az alábbi lépéseket: 
1.  Váltson a közzétett nézetre, amelyet módosítani szeretne. 
2.  Mentse el a közzétett nézet másolatát, amellyel létrehoz egy helyi vázlatot a közzétett nézetből. 
3.  Módosítsa a helyi vázlatot a szükséges módosításokkal.
4.  Tegye közzé a nézetet az eredeti névvel. 

## <a name="managing-published-views"></a>Közzétett nézetek kezelése
A személyes nézetek kezeléséhez hasonlóan a **Saját nézetek kezelése** párbeszédpanel segítségével a közzétételi jogosultsággal rendelkező felhasználók rendelkezhetnek az adott oldal közzétett nézeteire vonatkozó alapszintű karbantartási lehetőségekkel (a saját személyes nézeteik mellett). A lap megnyitásához kattintson a nézet nevére a nézetválasztó legördülő menü megnyitásához, válassza a **Továbbiak**, majd a **Saját nézetek kezelése** lehetőséget.

Míg minden felhasználó láthatja a **Saját nézetek** lapot a személyes nézeteikkel, a közzétételi jogosultsággal rendelkező felhasználók egy **Közzétett** lapot is látnak, amelyen szerepel az adott oldalhoz közzétett összes nézet. Mivel előfordulhat, hogy több felhasználó is közzétesz nézeteket, ezért fontos, hogy a közzétett nézetek teljes listáját kezelni lehessen, függetlenül attól, hogy a nézetet ténylegesen Ön tette-e közzé.

Az adott lap összes közzétett nézetének listájához a következő műveletek állnak rendelkezésre. 

-    **Közzététel**: a **Közzététel** művelettel újból közzéteheti a nézeteket a módosított közzétételi paraméterekkel (név, leírás, biztonsági szerepkörök).  
-    **Eltávolítás**: A közzétett nézetek végleges törléséhez használja az **Eltávolítás** műveletet. Ez a művelet eltávolítja a nézetet rendszer minden felhasználójától.  
 
Az ebben a párbeszédablakban elvégzett módosítások a **Mentés** gomb kiválasztása után lépnek érvénybe.

## <a name="frequently-asked-questions"></a>Gyakori kérdések
### <a name="how-do-i-enable-saved-views-in-my-environment"></a>Hogyan lehet engedélyezni a mentett nézeteket a saját környezetemben? 
Ha a szolgáltatás villámnézetében szeretné engedélyezni a mentett nézeteket, kövesse az alábbi lépéseket: 

1.  **Engedélyezze a tesztcsomagot**: hajtsa végre a következő SQL-utasítást: 

    `INSERT INTO SYSFLIGHTING (FLIGHTNAME, enabled, FLIGHTSERVICEID, PARTITION) VALUES('CLISavedViewsEnableFeature', 1, 0, 5637144576);`

2. **IIS alaphelyzetbe állítása** a statikus tesztelési gyorsítótár kiürítéséhez. 

3.  **Keresse meg a funkciót**: ugorjon a **Funkciók kezelése** munkaterületre. Ha a **Mentett nézetek** nem jelennek meg a listában, válassza ki a **Frissítések keresése** lehetőséget.   

4.  **Engedélyezze a funkciót**: keresse meg a **Mentett nézetek** funkciót a funkciólistában, majd válassza ki az **Engedélyezés most** lehetőséget a részleteket tartalmazó ablaktáblán.

Minden további felhasználói munkamenet engedélyezett mentett nézetekkel indul.  

Ne feledje, hogy ha a környezetnél ki van kapcsolva a testreszabás, a nézeteket a rendszer akkor is letiltja, ha a fenti lépéseket elvégzi. Ennek az az oka, hogy a nézet funkció a testreszabási alrendszer tetejére épül.

### <a name="what-happens-to-existing-personalizations-when-views-are-enabled"></a>Mi történik a meglévő testreszabásokkal a nézetek engedélyezésekor? 
A nézetek engedélyezésekor minden meglévő testreszabást, amely az adott felhasználóhoz és űrlaphoz létezik, a rendszer menti egy új **Saját nézet** elnevezésű nézetbe, amelyet automatikus nézetként állít be. Ezzel biztosítani lehet, hogy a felhasználói élmény konzisztens a nézetek engedélyezése előtt és után is, kivéve az űrlapokon megjelenő nézetválasztó vezérlőt.  

### <a name="what-pages-support-views"></a>Mely lapok támogatják a nézeteket? 
A nézetek elérhetők a legtöbb oldalon, bár nem mindegyiken. Pontosabban a nézetek jelenleg elérhetők az összes teljes képernyős lapon, kivéve az irányítópultokon és munkaterületeken. A nem teljes képernyős lapok, például a párbeszédpanelek, legördülő párbeszédpanelek, keresések, valamint a továbbfejlesztett előnézetek jelenleg nem támogatják a nézeteket. A további oldaltípusok, például a munkaterületek és párbeszédablakok esetében a nézetek támogatása esetlegesen egy jövőbeli frissítésben lehetséges.   

### <a name="who-is-allowed-to-publish-views"></a>Kinek van engedélye a nézetek közzétételére?
Jelenleg csak a rendszergazdák rendelkeznek a nézetek közzétételi jogosultságával.  Egy későbbi frissítés tartalmazni fog egy új biztonsági szerepkört, amely további rugalmasságot biztosítana az ügyfelek számára a közzétételre jogosult személyekkel kapcsolatban.  

### <a name="why-am-i-not-able-to-save-filters-with-this-view"></a>Miért nem tudom elmenteni a szűrőket ezzel a nézettel? 
Számos oka lehet annak, hogy egy szűrő miért nem menthető egy nézettel: 

- A lap valószínűleg nem támogatja a szűrők mentését a nézet definíciójának részeként. Ne felejtse el, hogy csak nagyméretű nézetválasztókat tartalmazó lapokon lehet nézetként menteni a testreszabásokat és a lekérdezések módosítását. További információt a „Nézetek váltása” szakaszban találhat. 

- Ha a nézet az alapértelmezett nézet, és a lap navigációs útvonala tartalmaz egy lekérdezést, előfordulhat, hogy a nézet lekérdezése kezdetben nem kerül alkalmazásra. Az ehhez kapcsolódó két elsődleges eset a következő: 
     - Ha például egy lapra egy csempéről navigál, akkor a rendszer végrehajtja a csempe lekérdezését az alapértelmezett nézethez társított lekérdezéstől függetlenül. 
     - Ha egy oldalra navigál, és a belépési pont rendelkezik egy lekérdezéssel, akkor az eredeti lekérdezés kerül végrehajtásra, és nem az alapértelmezett nézet lekérdezése. 
     
  Ha ilyen esetek történnek, akkor erre egy tájékoztató üzenet figyelmeztet, amikor a nézet betöltődik. Megerősítheti az adott nézetre váltást az oldal betöltődése után is, mivel ettől függetlenül engedélyezi a nézet lekérdezésének végrehajtását.  

- Előfordulhat, hogy a kérdéses oldal nem megfelelően támogatja a nézeteket, mivel teljesen figyelmen kívül hagyhatja a nézetlekérdezést, vagy olyan ideiglenes táblán működhet, amelynek adatai nem állandóak. 