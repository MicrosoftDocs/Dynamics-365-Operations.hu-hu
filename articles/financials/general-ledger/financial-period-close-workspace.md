---
title: "Pénzügyi időszak lezárása munkaterület"
description: "Ez a cikk betekintést nyújt a Pénzügyi időszak zárásának munkaterületébe és az ehhez társított beállításokba."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerPeriodCloseProjectWorkspace
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 13791
ms.assetid: 6ee51758-639b-448e-9cb2-56cf1d804273
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 0bbf8f979aeb8b861164e345f9e46bb396f370ce
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="financial-period-close-workspace"></a>Pénzügyi időszak lezárása munkaterület

[!include[banner](../includes/banner.md)]


Ez a cikk betekintést nyújt a Pénzügyi időszak zárásának munkaterületébe és az ehhez társított beállításokba.

Pénzügyi időszak lezárása munkaterület

A **Pénzügyi időszak lezárása** munkaterület lehetővé teszi a vállalatok, területek, valamint emberek közti pénzügyi záró folyamatok nyomon követését. A **Pénzügyi időszak zárása** munkaterület nézetétől függően vagy az egy zárási ütemezéshez tartozó összes feladatot és állapotot látja, vagy csak azokat a feladatokat amelyek önre lettek kiosztva. 

Először meg kell adnia a zárási ütemezést a munkaterület tetején. Ezután a munkaterületen megjelenített összes adatot szűri a program, a kiválasztott zárási ütemterv szerint.

### <a name="summary-tiles"></a>Összesítő csempék

Az **Összefoglaló** csempéken áttekintheti a folyamatokat és az indikátorok segítenek a zárási folyamat kivitelezésében. Láthatja a lejárt határidejű, hátralévő feladatokat az adott napon, feladatokat amelyeknek az adott napon van a határideje, de a függőségek miatt blokkolva vannak és a folyamat hátralévő feladatait. Ez az információ minden vállalatra vonatkozik, amelyik a kiválasztott zárási ütemtervben szerepel.

### <a name="tasks-and-status-section"></a>Feladatok és állapot szakasz

A **Feladatok és állapot** szakaszban, az összesített zárási ütemezés állapota különböző módokon kerül lebontásra: vállalat szerinti állapot, terület szerinti állapot, felelős személy szerinti állapot. A kártyalista tetején látható szűrő módosításával megtekintheti a zárási ütemezésben szereplő összes feladat állapotát vagy akár csak a mai vagy a múltbéli feladatok állapotát is. A vállalat szűrőt beállíthatja egy kiválasztott vállalat állapotának mutatására is. Minden állapot lap lebontásra kerül a teljesített feladatok százalékos arányára és a hátralevő feladatok számára. Kattintson a kártyára vagy a **Részletek megtekintése** funkcióra a kiválasztott kártya által felsorolt részletes feladatlista kiszűrésére. 

Az utolsó lapon a részletes feladatok listája látható. Ez a lista a teljes feladatot megjeleníti és alkalmazható hozzá szűrő, hogy csak a kívánt feladatokat jelenítse meg. A feladatlistára számos szűrést alkalmazhat. Például alkalmazhat szűrést feladat, határidő, társított vállalat, társított terület szerint. Továbbá kiválaszthatja hogy a teljesített feladatok megjelenjenek-e a listában. 

Két kijelző használatos a feladatokhoz:

-   A felkiáltójel azt jelzi, hogy a feladat lejárt határidejű. A lejárt határidejű feladatok határideje piros színnel is ki van emelve.
-   A lakat ikon azt jelzi, hogy a feladat más, teljesítetlen feladatoktól függ. A függőségek miatt zárolt feladatokat nem lehet befejezettnek jelölni. A feladat függőségeit a **Függőségek beállítása** művelettel állíthatja be.

A feladat neve egy hivatkozás, amely a Microsoft Dynamics 365 for Operations oldalra vagy egy másik webhelyre mutat, amelyet a felhasználónak fel kell keresnie a feladat befejezéséhez. A **Feladathivatkozás** mezőben beállíthatja ezt a hivatkozást a feladat szerkesztésekor vagy létrehozásakor. 

Csatolhat fájlokat, megjegyzéseket, képeket és URL-eket egy feladathoz a **Mellékletek** művelettel. Például megjelölhet naplószámokat, amelyek a feladat részét képezik, és megjegyzéseket adhat egy adott feladathoz, vagy jelentést csatolhat a fájlhoz amelyik a feladathoz lett nyomtatva. Egy ikon jelenik meg a **Melléklet** oszlopban a feladatnál, ha a feladat rendelkezik melléklettel. 

A **Kész feladat** lehetőséget manuálisan lehet kiválasztani a feladat befejezése után. Amikor egy feladatot befejezettként jelöl meg, akkor a **Befejezés dátuma** mező automatikusan frissül az aktuális dátumra és időre. A függőségi indikátorok szükség szerint szintén frissülnek.

## <a name="all-financial-period-close-tasks-list-page"></a>Összes pénzügyi időszak lezárási feladatainak listaoldala
Megjelenítheti az összes jelenlegi és előző időszaklezárási feladatot az **Összes pénzügyi időszak zárási feladata** listaoldalon. Ez a listaoldal legjobban az előzmények vizsgálatához használható, zárási folyamat során, mert tartalmazza az ütemezett határidőket, a tényleges teljesítési dátumokat és a személyt aki befejezte a feladatot. Könnyedén exportálhatja az információkat a listaoldalról Microsoft Excel fájlba jelentések elkészítéséhez és auditokhoz.

## <a name="financial-period-close-configuration-page"></a>Pénzügyi időszak lezárási konfigurációs oldala
A **Pénzügyi időszak zárása** munkaterület használata előtt konfigurálja a folyamatot a Microsoft Dynamics 365 for Finance and Operations rendszerben a **Pénzügyi időszak lezárási konfigurációja** oldalon. (Kattintson a **Főkönyv** &gt; **Időszak zárása** &gt; **Pénzügyi időszak lezárási konfigurációja** lehetőségre.)

### <a name="resources"></a>Erőforrások

Az **Erőforrások** lapon meghatározhatja az alkalmazottakat, akiket be kíván vonni a zárási folyamatba. Minden alkalmazottat, aki zárási feladatért felelős, először itt kell hozzárendelni. Az alkalmazott munkaterület-nézetét is meg kel adnia. Az alábbi lehetőségek közül választhat:

-   **Kizárólag hozzárendelt tevékenységek** – A felhasználó csak a hozzárendelt feladatait látja.
-   **Feladatok és állapot** – A felhasználó teljes folyamat minden lezárási feladatot és állapotot lát.

A felhasználók, akik csak a saját feladataik megtekintéséhez rendelkeznek engedéllyel nem tudnak feladatot adni a feladatlistához, feladatot szerkeszteni vagy feladatot eltávolítani a feladatlistáról.

### <a name="task-areas"></a>Feladatterületek

Használhat logikai feladatterületeket a szervezeten belül, csoportos zárási feladatokhoz. Például a Kötelezettségek, Kinnlevőségek vagy a Főkönyv használható feladatterületként.

### <a name="calendars"></a>Naptárak

A Naptárak lapon létrehozhat és szerkeszthet pénzügyi zárási naptárakat. Itt definiálhatja a zárási folyamatok munkanapjait és ütemezheti a zárási feladatokat.  Hozzon létre egy új naptárat és jelölje meg a feladat-ütemezés munkanapjait.  Legjobb megoldás, ha hosszú időszakra hozza létre a naptárat, egy, vagy akár több évre, ugyanis a létrehozás után szerkeszthető.  Miután létrehozta a naptárat kattintson a Szerkesztés gombra a naptár frissítéséhez, ha szeretne konkrét napokat, például ünnepeket megadni.  A zárási feladatok olyan napokra lesznek ütemezve ahol a Vezérlőérték Nyitva.  Ha a zárási feladatokat nem akarja egy adott napra ütemezni, akkor azon a napon a Vezérlőértéket állítsa Zárt értékre.

### <a name="templates"></a>Sablonok

A pénzügyi zárási sablont az olyan feladatok definiálásához használhatja, amelyek részei a zárási folyamatnak. A zárási feladat egy ismétlődő munka, amely egy személyhez van rendelve, akinek a zárási folyamat részeként kell azt elvégeznie. A sablonban meg kell adni egy relatív határidőt minden egyes zárási feladathoz. A relatív határidő azoknak a napoknak a száma amelyek előtt vagy után az adott feladatnak a határideje meg lesz határozva minden időszakban. Határidő minden feladathoz szintén hozzárendelésre kerül. A határidő az Ön időzónája alapján kerül meghatározásra, és a rendszer átalakítja a felhasználó időzónájára. 

A sablonban hozzárendelhet egy feladatot egy vagy több vállalatot, amire a feladat vonatkozik. Ha egy másik személy van hozzárendelve a munkához minden egyes vállalatnál, akkor hasznos lehet több feladat létrehozása ugyanahhoz a munkához. Külön feladat létrehozása minden egyes vállalathoz. 

A **Feladathivatkozás** menüelem a feladathoz van rendelve és segítségével közvetlenül a társított oldalara lehet ugrani a feladathivatkozásról a munkaterületen. Például egy zárási feladat pénznem-újraértékelési folyamatának futtatása a Kötelezettségekben hozzárendelhető a Microsoft Dynamics 365 for Finance and Operations, Enterprise kiadás **Devizaátértékelés** oldalához. Külső URL-címet is hivatkozhat. 

> [!Javaslat] Ha szeretne egy adott Felügyeleti jelentéskészítő jelentést csatolni egy pénzügyi időszak zárási feladatához, akkor használhat jelentés-URL-t. A jelentés-URL-címének eléréséhez nyissa meg a jelentést a jelentéstervezőben, és kattintson a **Fájl** &gt; **Jelentés megtekintése** elemre, ha szeretné a jelentést egy webböngészőben megnyitni. Ezután bemásolhatja az URL-címet a böngésző címsorába, és beillesztheti a **Feladathivatkozás** **URL** cím mezőbe. 

Megadhat feladatfüggéseket a sablonban. Ha egy feladat egy vagy több feladattól is függ, akkor az a feladat nem jelölhető meg befejezettként, amíg a függő feladatokat nem végezték el. 

Több pénzügyi zárási sablont is létrehozat. Ezután a különböző sablonokat használhatja a különböző időszaktípusokhoz, például hónap végéhez, év végéhez tartozó zárási folyamatok nyomon követéséhez, vagy figyelemmel követhet vállalatokat, amelyek eltérő zárási folyamatokat használnak. Miután létrehozott egy sablont, bemásolhatja egy új sablonba és módosíthatja. Egy zárási ütemtervhez csak egy sablont rendelhet hozzá.

### <a name="closing-schedules"></a>Lezárási ütemezések

Használhat egy zárási ütemtervet arra, hogy egy pénzügyi zárási sablont hozzárendeljen egy pénzügyi időszakhoz, amit le kell zárni. A sablonon lévő feladatok ezután automatikusan létrejönnek az adott időszakra, és az új zárási ütemterv hozzáadódik a munkaterülethez. Amikor új zárási ütemtervet hoz létre, akkor az **Időszak záró dátuma** mező határozza meg a tényleges határidőket a lezárási feladatokhoz, a relatív határidő alapján, amelyet a pénzügyi zárási sablonban adott meg. 

Rendelje hozzá a megfelelő naptárat a zárási ütemtervhez, hogy megjelölje a feladat ütemezéséhez a munkanapokat. Ha nem ad meg konkrét naptárat, akkor a feladat határidői a hét minden napját igénybe veszik. 

Létre kell hoznia a vállalatokat is, amelyekhez a záró ütemezés társítva lesz. Ha a sablonfeladatok több vállalathoz vannak hozzárendelve, akkor külön feladatok jönnek létre minden egyes vállalathoz, amely szerepel a zárási ütemtervben és hozzá van rendelve a sablonfeladathoz. 

Miután befejezte a záró ütemtervet, válassza a **Lezárt** lehetőséget. A feladatelőzmények továbbra is elérhetők az **Összes pénzügyi időszak zárási feladatai** listaoldalon, de a zárási ütemterv eltávolításra kerül a munkaterületről. A zárási ütemtervhez **Lezárt** állapotban már nem lehet feladatokat adni, azokat szerkeszteni vagy eltávolítani belőle.




