---
title: Termelési folyamat áttekintése
description: Ez a témakör a gyártási folyamatokról nyújt áttekintést. Bemutatja a termelési rendelések, a kötegrendelések és a kanbanok különböző szintjeit, a rendelés létrehozásától a pénzügyi időszak zárásáig.
author: cvocph
manager: tfehr
ms.date: 09/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: JmgShopSupervisorWorkspace, Kanban, ProdTable, ProdTableOverview, EcoResProductDiscreteManufacturingWorkspace, KanbanPrepareProductForLeanWorkspace, EcoResProductProcessManufacturingWorkspace, OpResLifecycleManagementWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 19832
ms.assetid: 0e83c7ea-feba-4ed6-8717-8b48a3b8804a
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 27d955dd1ba12ff9897697fad50a0bc8172905ae
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/02/2020
ms.locfileid: "3211284"
---
# <a name="production-process-overview"></a>Termelési folyamat áttekintése

[!include [banner](../includes/banner.md)]

Ez a témakör a gyártási folyamatokról nyújt áttekintést. Bemutatja a termelési rendelések, a kötegrendelések és a kanbanok különböző szintjeit, a rendelés létrehozásától a pénzügyi időszak zárásáig. 

A termékek legyártása, más néven a termelési életciklus specifikus lépésekben történik, amelyeket a termék előállításához végre kell hajtani. Az életciklus kezdete a termelési rendelés, kötegrendelés vagy a kanban. A vége egy legyártott, kész cikk, amelyik átadható a vevőnek vagy egy másik gyártási fázisnak. Az életciklus minden lépése másféle információkat igényel a feladat végrehajtásához. Amikor az egyes lépések végrehajtása megtörténik, a termelési rendelés vagy kanban műveletben változás látható a gyártási állapotnál. Különböző termékekhez különböző gyártási folyamatok szükségesek.  

A **Gyártásvezérlés** modul egyéb modulokkal van összekötve, például **Termékinformációk kezelése**, **Készletkezelés**, **Főkönyv**, **Raktárkezelés**, **Projekt-könyvelés** és **Szervezeti adminisztráció**. Ez az integráció teremti meg annak az információáramlásnak a feltételeit, amely egy elkészült termék legyártásához szükséges.  

A gyártási folyamatot általában a költségkönyvelés és a készletértékelési módszerek befolyásolják, amelyeket egy specifikus gyártási folyamathoz határoztak meg. A Supply Chain Management támogatja a tényleges költség (elsőként be, elsőként ki \[FIFO\]; utolsóként be, utolsóként ki \[LIFO\]; mozgóátlag; és időszakos súlyozott átlag) és standard költség módszereket is. A lean gyártás a visszavezetéses költségelszámolás elv alapján valósítható meg.  

A kiválasztott költségmérési módszerek meghatározzák a jelentés anyagokkal és forrásfelhasználással kapcsolatos követelményeit a gyártási folyamat során. Általában a tényleges költség módszerekhez pontos jelentés szükséges a feladat szintjén, ugyanakkor az időszakos költségszámítási módszerek lehetővé teszik az elnagyoltabb anyag- és forrásfogyasztás jelentés elkészítését.

## <a name="mixed-mode-manufacturing"></a>Vegyes módú gyártás
Különböző termékek és termelési topológiák esetén különböző rendelési típusokat kell alkalmazni. A Supply Chain Management különböző típusú rendeléstípusokat használhat vegyes módban. Más szavakkal minden rendeléstípus megjelenhet a késztermék legyártásának teljes folyamata során.

-   **Termelési rendelés** – Ez a klasszikus rendeléstípus, egy adott termék vagy termékvariáns legyártására adott mennyiségben előre meghatározott időpontra. A termelési rendelések anyagjegyzékeken (AJ) és útvonalakon alapulnak.
-   **Kötegrendelés** – Ez a rendelési típus a feldolgozóiparhoz és a jól elkülöníthető folyamatokhoz használatos, ahol a termelési folyamat a receptúrán alapul, vagy ahol a társtermékek és melléktermékek végtermékek lehetnek, a fő termék helyett vagy annak hozzáadásával. A kötegelt rendelések **Receptúra** típusú anyagjegyzékeket és útvonalakat használnak.
-   **Kanban** – A kanbanok ismétlődő lean gyártási folyamatok jelzésére használatosak, amelyek a termelési folyamatokon, kanban szabályokon és anyagjegyzékeken alapulnak.
-   **Projekt** – A gyártási projekt egyesíti a termékeket és a szolgáltatásokat egy adott ütemezésben és költségvetésben. A projekt gyártási része az alábbi rendeléstípusok bármelyikében megvalósítható.

## <a name="manufacturing-principles"></a>Gyártási alapelvek
A termékhez és az érintett piachoz legjobban illeszkedő gyártási alapelv kiválasztásához figyelembe kell venni a gyártási, logisztikai és vevői elvárásokat a szállítás átfutási idejével kapcsolatban.

-   **Elkészítés készletbe** – Ez a klasszikus gyártási elv, ahol a terméket raktárorozásra állítják elő, az előrejelzések vagy a minimális készletfeltöltés alapján (az utóbbit általában a fogyasztási előzmények alapján számítják).
-   **Készítés rendelésre** – Standard termékek készítése rendelésre vagy befejezés rendelésre. Annak ellenére, hogy az előgyártást végre lehet hajtani a Készítés készletre elv szerint, az értéklánc drága lépései, vagy lépések amelyek során változatok jönnek létre az értékesítési rendeléssel vagy átmozgatási rendeléssel aktiválódnak.
-   **Konfigurálja rendelésre** – Ahogy a Készítés rendelésre elvnél, az értéklánc végső műveletei rendelésre mennek végbe. A tényleges, legyártott termékváltozat nincs előre meghatározva, de a rendelésbevitel idejében jön létre, az értékesítési termék konfigurációs modellje alapján. A Konfigurálás rendelésre elvhez szükséges a folyamatok bizonyos szintű egységesítése egy adott termelési soron.
-   **Mérnöki rendelés** – A mérnöki rendelés folyamatok általában egy projekthez vannak rendelve és műszaki fázissal indulnak. A műszaki fázis során a tényleges termékek, amelyek szükségesek a tervezett és leírt rendelés teljesítéséhez. Termelési rendelések, kötegrendelések vagy kanbanok létrehozhatók ezen termékek gyártásához.

## <a name="overview-of-the-production-life-cycle"></a>A termelési életciklus áttekintése
Az alábbi lépések a gyártás életciklusában felléphetnek minden rendeléstípus vagy vegyes gyártástípus esetén is. Azonban nem mindegyik jelenik meg explicit rendelési állapotként.

1.  **Létrehozott** – Létrehozhat manuálisan termelési rendelést, kötegrendelést és kanbant, vagy konfigurálhatja a rendszerhez, hogy ezek alapján különböző igényjeleket hozzon létre. Az alaptervezés termelési rendeléseket, kötegrendeléseket vagy kanbanokat hoz létre a tervezett rendelések jóváhagyásával. Egyéb igényjelek a termelési rendelések vagy rögzített készletjelek a termelési rendelésekből vagy kanbanokból. Rögzített mennyiségű kanbanok, igényjelek jönnek létre, ha a üres kanbanokat regisztrálnak.
2.  **Becsült** – Kiszámíthatja a becsült anyag- és erőforrás-felhasználást. A becslés nyersanyagokra vonatkozó készlettranzakciókat generál, amelyek **Megrendelt** állapotúak. A fő termékek, társtermékek és melléktermékek nyugtái létrejönnek a termelési rendelések vagy kötegelt rendelések becslésekor. Ha az anyagjegyzék tartalmaz **Rögzített készletek** típusú sorokat, létrejönnek az anyagok vagy az alvállalkozói működtetési szolgáltatások beszerzési rendelései, és rögzítve lesznek a gyártási rendelésbe vagy a kötegelt rendelésbe. Cikkek vagy rendelések, amelyek foglalása a termelési rendelés foglalási stratégiája szerint történik, és a késztermék ára a paraméter beállítások szerint kerülnek kiszámításra.
3.  **Ütemezett** – Ütemezhet gyártást műveletek, egyéni munkák vagy mindkét lehetőség szerint.
    -   **Műveletek ütemezése** – Ez az ütemezési módszer elnagyolt, hosszú távú tervezést tesz lehetővé. Ezzel a módszerrel kezdeti és befejezési dátumokat rendelhet a termelési rendelésekhez. Ha a termelési rendelések útvonalműveletekhez vannak csatolva, akkor költséghelycsoportokhoz rendelheti őket.
    -   **Munkaütemezés** – Ez az ütemezési mód részletes tervet készít. Mindegyik művelet feladatokra van bontva, konkrét dátumokkal, időpontokkal és hozzárendelt üzemi erőforrásokkal. Ha véges kapacitás van használatban, a rendszer az elérhetőségük alapján rendeli az üzemi erőforrásokhoz a feladatokat. Az ütemezést a Gantt-diagramon tekintheti meg és módosíthatja.
    -   **Kanban ütemezés** – A kanbanfeladatokat a kanban ütemezés táblán vagy automatikusan lehet üzemeltetni, utóbbi esetben az ütemezés a kanbanszabályok konfigurációja szerint történik.

4.  **Kiadott** – Kiadhatja a termelési rendelést vagy a kötegrendelést, ha az ütemezés lezajlott és az anyagok kitárolhatók vagy előkészítettek. Az anyag rendelkezésre állását mutató jelölőnégyzet segíti az üzemirányítási felelőst a termelési rendelésekhez vagy kötegrendelésekhez szükséges anyagok elérhetőségének felmérésében. Ki lehet továbbá nyomtatni a termelési rendelési dokumentumokat, például kitárolási listákat, feladatkártyákat, útvonalkártyákat és útvonalfeladatokat. Amikor a termelési rendelést kiadják, a rendelés állapota megváltozik, ezzel jelezve, hogy a termelés elkezdődhet. Raktározási rendszer használata esetén a termelési rendelés kiadása, vagy a kötegrendelés felszabadítja a termelési AJ sorokat a raktárkezeléshez. Raktárhullámok és raktári munkák jönnek létre a raktárbeállítások alapján.
5.  **Előkészített**/**Kitárolva** – Ha az összes anyag és erőforrás elő lett készítve a termelés helyén, a termelési anyagjegyzék sorok vagy kanban sorok **Kitárolva** állapotra frissülnek. A rögzített készletrendelések és a kapcsolódó raktározási munka általában befejeződött ebben a szakaszban. A kanbankártyák vagy útvonalkártyákat, amelyek a termelésben elért haladás jelentéséhez szükségesek, hozzá kell rendelni és ki kell nyomtatni.
6.  **Elindítva** – Ha egy termelési rendelés, kötegrendelés vagy kanban elindul, akkor jelentheti az anyag és erőforrás felhasználást a rendeléssel kapcsolatban. A rendszerben beállítható, hogy automatikusan adja fel az anyag és erőforrás fogyasztást, amelyet a rendeléshez különítettek el indításkor. Ezt a felosztást előzetes ürítésnek, előre ürítésnek vagy automatikus fogyasztásnak is nevezik. Manuálisan hozzárendelhet termelési rendelésekhez vagy kötegrendelésekhez anyagokat, ha létrehoz további kitárolási listasorokat. Manuálisan feloszthatja a munka- és egyéb útvonalköltségeket is a rendeléshez. Ha műveletütemezést használ, akkor útvonalkártya-napló létrehozásával is feloszhatja ezeket a költségeket. Ha feladatütemezést használ, akkor feladatkártya-napló létrehozásával is feloszthatja ezeket a költségeket. Termelési rendelések vagy kötegrendelések indítása a kötegeknél lehetséges, az igényelt végső mennyiséggel. Egy termelési rendelésben, kötegrendelésben vagy kanbanban létrehozott munkák külön elindíthatók és jelenthetők a naplókon keresztül, a gyártás végrehajtási terminálon keresztül (MES terminál) vagy a kanbantáblán keresztül.
7.  Haladás jelentése/**Kész** munkák – Használjon MES terminált, termelési naplókat, kanbantáblákat vagy mobil beolvasási lehetőségeket a termelési folyamat haladásának jelentéséhez, feladat vagy erőforrás szerint. Az anyag és erőforrás felhasználás feladásra kerül, és a kapcsolódó kanbanok, termelési rendelések, és kötegrendelések állapota frissíthető **Beérkezett** vagy **Készként jelentett** állapotra. Betárolási munka jöhet létre a raktárban, a raktár beállításaitól függően.
8.  **Készként jelentett** – (a termékbevételezés) – Amikor a termelési rendelést vagy kötegrendelést készként jelentik, a befejezett késztermék mennyisége frissül a készletben. Ez a mennyiség tartalmazza a vonatkozó társtermékeket és melléktermékeket. Amennyiben folyamatban lévő munkán alapuló könyvelést használ, egy főkönyvi napló jön létre a folyamatban lévő munka számlák egyenlegének csökkentésére és a késztermékek készletének növelésére. A termelési rendelés költségének kiszámításakor a program feladja a termelés tényleges költségét. Ha a termeléssel kapcsolatos anyag- és munkaköltségek még nem lettek felosztva egy naplóban vagy előzetes kiürítéssel, akkor utólagos ürítéssel automatikusan feloszthatók. A vissza-könyvelési felosztás tartalmazza a készlettranzakciós folyamatok utólagos levonását. Ha a termelési rendelés elkészült, jelölje be a **Záró feladat** jelölőmezőt, és változtassa a megmaradó állapotot **Befejezett** értékűre. Ellenkező esetben a mező üresen hagyható, így a kiegészítő termelt mennyiségek jelentése a későbbiekben is lehetséges.
9.  **Minőségellenőrzése** – A termékbevételezés minőségi rendelések létrehozását indíthatja el a tesztfolyamatok és a minőségi szabályok beállításaitól függően, amelyek az adott termékre vonatkoznak. A tesztelt termékek minőségi rendelése frissítheti a készletállapotot vagy a kötegattribútumokat, ezért a minőségellenőrzés kötelező számos iparágban.
10. **Betárolás** és **Szállítás rendelésre** – A termékbevételezés és minőségellenőrzés után a választható betárolási munka a bevételezett termékeket a felhasználás következő pontjára irányítja, egy késztermék raktárba vagy egy szállítási zónába, ha nincsenek szállítás rendelésre igények.
11. **Befejezett** – A megtermelt mennyiség tényleges költségeinek kiszámítása még a termelés befejezése előtt megtörténik. Minden becsült anyag-, munka- és többletköltséget sztorníroz a program, és a tényleges költségeket vezeti be a helyükre. Ha a **Záró feladat** jelölőnégyzetet bejelöli a költségszámítás futtatásakor, a termelési rendelés a **Befejezett** állapotra vált. Ez az állapot meggátolja, hogy bármilyen további költséget feladjanak egy már elkészült termelési rendeléshez.
12. **Időszakzárás** – Bizonyos költségelszámolási elvek, például ismétlődő átlag, vissza-ürítés költségszámítási, FIFO vagy LIFO kötelezővé teheti az időszakos tevékenységeknek a készlet vagy a pénzügyi időszak zárását. Általában a rendszer megpróbálja jelenteni az összes erőforrás és anyagfogyasztást, továbbá a készlet és selejt korrekciókat, mielőtt az időszak lezárul. Ez a jelentés általában készletmozgási naplók vagy a készlethelyesbítési naplók segítségével történik. Célja, üzemi egység adott időszak alatti teljesítményének gazdasági értékelése. Néhány esetben, amikor hosszútávú rendeléseket használnak, amelyek tartalmazzák a pénzügyi jelentések időtartamait, akkor a termelési naplók segítségével jelenthető a termelési előrehaladás és az erőforrás felhasználás az időszak végéig.


<a name="additional-resources"></a>További erőforrások
--------

[Termelési visszajelzés](production-feedback.md)

[Termékkonfigurálási modellek áttekintése](../pim/product-configuration-models.md)

[Lean manufacturing (áttekintés)](lean-manufacturing-overview.md)



