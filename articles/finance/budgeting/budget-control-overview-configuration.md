---
title: A költségvetés-ellenőrzés áttekintése
description: Ez a cikk bemutatja a költségvetés-ellenőrzést, és segítséget nyújt a költségvetés-ellenőrzés beállításához a Microsoft Dynamics 365 Finance rendszerben, úgy hogy kezelni tudja a pénzügyi erőforrásokat.
author: ShylaThompson
manager: AnnBe
ms.date: 01/11/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BudgetControlConfiguration
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 60493
ms.assetid: be964167-43bc-431d-9adb-48bff32d68d5
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 670e6be595fb891408b1b0804c68a41650b0da0b
ms.sourcegitcommit: e544c51a68ad5daf748c0e877bdbde094ad40bd2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/03/2020
ms.locfileid: "4444196"
---
# <a name="budget-control-overview"></a>Költségvetés-ellenőrzés áttekintése

[!include [banner](../includes/banner.md)]

Ez a cikk bemutatja a költségvetés-ellenőrzést, és segítséget nyújt a költségvetés-ellenőrzés beállításához, úgy hogy kezelni tudja a pénzügyi erőforrásokat.

<a name="overview"></a>Áttekintés
--------

A költségvetés-ellenőrzés funkció támogatja a szervezet pénzügyi forrásainak kezelését a számlatükrökön, munkafolyamaton, felhasználói csoportokon, forrásbizonylatokon, naplókon, konfigurálható források számításán, költségvetési ciklusokon és küszöbértékeken keresztül. Ha a szabályzók a helyén vannak, a szervezet megtervezheti, megmérheti, kezelheti és előre jelezheti a pénzügyi forrásokat a pénzügyi évben. 

Miután a költségvetéseket jóváhagyták a Microsoft Dynamics 365 Finance rendszerben, a költségvetési tervek használatával lehet létrehozni Költségvetési tételjegyzék-bejegyzéseket a szervezetre vonatkozó kiadási költség rögzítéséhez. Másik lehetőségként létrehozhat vagy importálhat a külső programokból költségvetési tételjegyzék-bejegyzéseket a költségvetés-tervezési funkció használata helyett. 

A fő számlák és a pénzügyi dimenziók használatával lehet rögzíteni a kiadásokokat. Konfigurálhatja a teljes kiadások vezérlőjét a szervezet szabályainak és követelményeinek teljesítéséhez a pénzügyi dimenziók és a fő számlák kombinációinak csoportosításával. 

A következő diagram a költségvetés-ellenőrzés helyét mutatja egy tipikus költségvetési ciklusban.

[![Tipikus költségvetési ciklus](./media/budgetingcycle-300x198.png)](./media/budgetingcycle.png) 

A költségvetés-ellenőrzést különböző szempontok szerint lehet beállítani:

-   **Pénzügyi dimenziók** - Milyen pénzügyi dimenziókat kell használni a költségvetés és az aktualitások rögzítéséhez, és milyen pénzügyi dimenziók szükségesek a költségvetés szabályzásához? Vannak meghatározott dimenziókombinációk vagy fő számlák, amelyek különös figyelmet igényelnek? Például van olyan követelmény, ami alapján követni kell a ténylegesek között a költségvetést költséghely és program szerint? Szükséges az utazási költségekhez különösebb figyelem?
-   **Idő** - Milyen időkeret (pénzügyi időszak, pénzügyi időszak adott dátumig, stb.) kerül felhasználásra az elérhető költségvetési alapok kiértékeléséhez?
-   **Forrás dokumentumok** – Milyen forrásbizonylatokat kell kiértékelni a költségvetés-ellenőrzéshez? Szükséges a dokumentumokat soronként vagy dokumentumonként kiértékelni?
-   **Rendelkezésre álló források számítása** - Szükséges a dokumentumokat beszerzési rendelésként (előzetes kötelezettségvállalások) és beszerzési rendelésként (kötelezettségvállalások) használni a rendelkezésre álló pénzalapok számításakor? Figyelembe kell venni a vázlat állapotú dokumentumokat a számítás során?
-   **Felülbírálási engedély** - Kinek van jogosultsága a rendelkezésre álló költségvetés átlépéséhez?

A költségvetés-ellenőrzés teljesen integrálva van az alkalmazással: Emiatt a rendelkezésre álló költségvetést kiértékelheti a tervezett beszerzésekre és a tényleges beszerzésre vonatkozóan egyaránt. Elérhetők a költségvetés lekérdezések és jelentések. Ezért a felhasználók kiértékelhetik a költségvetést a költségvetési cikluson keresztül, és bármennyi szükséges kiigazítást végezhet a költségvetés-verzió vagy átutalások formájában. A költségvetés-kezelő exportálhatja a költségvetést és tényleges kiadásokat a Microsoft Excel hogy szükség szerint jobban tudja elemezni és előre jelezni a folyamatokat.

## <a name="configuring-budget-control"></a>Költségvetés-ellenőrzés konfigurálása
### <a name="budget-cycle-time-span"></a>Költségvetési ciklus időtartama

Miután beállította az alapvető költségvetés-tervezést megadhatja a költségvetés tervezés és költségvetés-ellenőrzés időtartamát vagy a periódus kezdő és záró dátumát a **Költségvetési ciklus időtartama** oldalon. A költségvetési ciklusok gyakran egyeznek a pénzügyi naptárral, de pénzügyi évekre is kiterjedhetnek.

A konfiguráció következő lépéseinek elvégzése a **Költségvetés-ellenőrzési konfiguráció** oldal különféle lapjain történik.

### <a name="define-parameters"></a>Paraméterek meghatározása

A költségvetés számára engedélyezett pénzügyi dimenziók alapján használhatja az összes pénzügyi dimenziót a költségvetés-ellenőrzésre vagy azok egy részére vonatkozóan. 

Továbbá megadhatja az alapértelmezett időtartamot (például **Pénzügyi év**, **Pénzügyi év záró dátuma**, **Pénzügyi időszak**, vagy **Negyedéves**), a költségvetés ellenőrzés a kapcsolódó költségvetési ciklus időtartama során kerül sor. Megadhatja egy alapértelmezett költségvetés-kezelőjét és a küszöbértéket, amellyel értesítik a felhasználót, ha már elérte a küszöbértéket. Az ezekben a mezőkben szereplő értékeket alapértelmezett értékekként használnak bármely létrehozott költségvetési csoportban vagy új költségvetés-ellenőrzési szabályban. Az alapértelmezett értékeket azonban módosítani lehet az egyes csoportokra és szabályokra vonatkozóan. 

A költségvetések létrehozásának és rögzítésének módja a költségvetés-jegyzékben segít meghatározni a kiválasztott időtartamot az elérhető költségvetési pénzalapok kiértékelésekor. Ha egy dimenzióérték kombináció évre vetített mennyiségét kifejlesztik és használják a pénzügyi év vagy a pénzügyi év megközelítése az adott dátumig értelmet nyer. Ugyanakkor, ha egy szervezet pénzügyi időszak szerint hoz létre költségvetéseket vagy részletesebb irányítást megkövetelő pénzügyi időszakokhoz csoportosít, akkor megfontolandó a pénzügyi időszak az adott dátumig vagy negyedéves időtartamig történő alkalmazása. 

Továbbá egy szervezeti kultúra fontos szerepet játszik a konfigurációban is, mivel kapcsolódik a költségvetés-tervezéshez és a költségvetési-ellenőrzéshez.

### <a name="over-budget-permissions"></a>Költségvetés-túllépési engedélyek

A következő, a **Költségvetés-túllépési engedélyek** lapon megadhatja a felhasználói csoportokat. Megadhatja azt is, hogy azoknak a felhasználóknak, akik a csoport tagjai lehetőségük legyen a költségvetés átlépéséhez. Megakadályozhatja, hogy a felhasználók átlépjék a lejárt költségvetést és a **Költségvetési paraméterek** lapon beállított költségvetési küszöbértéket, vagy megakadályozhatja, hogy a költségvetést bármilyen tetszőleges összeggel átlépjék a küszöbérték tekintetbe vétele nélkül. Attól függően, hogy egy szervezet mennyire proaktív módon kezeli kiadásait, ezek az engedélyek segíthetnek a pénzügyi források kezelésében. 

### <a name="budget-funds-available"></a>Rendelkezésre álló költségvetési források

A következő, az **Rendelkezésre álló költségvetési alapok** lapon meghatározhatja a rendelkezésre álló költségvetési alapok kiszámításához használt képletet. Attól függően, hogy a vállalat mennyire konzervatívan kezeli a pénzügyi forrásokat, vagy a szabályozásoktól vagy az iparági követelményektől függően a számítás vázlatot vagy fel nem adott dokumentumokat tartalmazhat. 

> [!NOTE] 
> Ez a számítás módosul a költségvetési ciklusban, a változók nem befolyásolják azokat a dokumentumokat, amelyek megfeleltek korábban költségvetés-ellenőrzésen, és amelyek feladásra kerültek vagy befejeződtek.

### <a name="documents-and-journals"></a>Dokumentumok és naplók

Következő, a **Dokumentumok és naplók** lapon kiválaszthatja, hogy mely forrásbizonylat és napló legyen a tárgya a költségvetés-ellenőrzés csekkekre vonatkozóan, és hogy a csekkek sorbejegyzés szintjén vagy az egész dokumentumnál jelenjen-e meg. 

Egyeztesse a kiválasztott forrásbizonylatokat az elérhető költségvetési alapok számításaiban szereplő egyenlegek jelölőnégyzeteivel. Például, ha a **Költségvetési zárolások a kötelezettségvállalásokhoz** lehetőséget választotta, akkor válassza a **Beszerzési rendelés** lehetőséget. Amikor a program költségvetés-ellenőrzést végez egy beszerzési sorban szereplő összegekre és számlákra vonatkozóan, a költségvetés-ellenőrzési kategóriát rendeli a **Kötelezettségvállaláshoz**. Amikor a program költségvetés-ellenőrzést végez egy beszerzési igénylésben szereplő összegekre és számlákra vonatkozóan, a költségvetés-ellenőrzési kategóriát rendel az **Előzetes kötelezettségvállalás** lehetőséghez. 

Ha a **Költségvetési zárolások a kötelezettségvállalásokhoz** és/vagy **Költségvetési zárolások az előzetes kötelezettségvállalásokhoz** szerepelnek az elérhető költségvetési alapok számításban és szükséges a feladásokon keresztül a főkönyvben, akkor engedélyeznie kell a **Főkönyv paraméterei** oldalon a kötelezettségvállalások könyvelését.  

### <a name="assign-budget-models"></a>Költségvetési modellek társítása

Következő, a **Költségvetési modellek társítása** lapon hozzárendeli a költségvetési modellt a költségvetési ciklus időtartamához, amelynek szerepelnie kell a költségvetés-ellenőrzésben.

### <a name="define-budget-control-rules"></a>Költségvetés-ellenőrzési szabályok meghatározása

Következő, a **Költségvetés-ellenőrzési szabályok meghatározása** lapon létre kell hoznia a költségvetés-ellenőrzés számára elérhető pénzügyi dimenziókon alapuló specifikus szabályokat. Például, ha a kiadáson vagy egy részlegre vonatkozó kiadások tartományán van a fókusz, akkor ezen a lapon található beállítások segítségével meghatározhatja és kiszámíthatja azokat a kiadásokat. Minden egyes költségvetés-ellenőrzési szabályra vonatkozóan meghatározhatja a küszöbéréket. 

> [!Important]
> A költségvetés-ellenőrzés engedélyezve lesz az **Eredmény**, **Költség** **Bevétel, mérleg, forrás, saját tőke** vagy **Eszköz** típus minden fő számlája számára. Ha ez a lap tartalmaz egy olyan szabályt, amelynek üres feltételei vannak, a költségvetés-ellenőrzés engedélyezve lesz az **minden** olyan pénzügyi dimenzió kombináció számára, amelyek tartalmazzák azoknak a típusoknak a fő számláját. Ezért győződjön meg róla, hogy létrehoz-e olyan költségvetés-ellenőrzési szabályokat, amelyek csak a pénzügyi dimenzió kombinációk tartományát szabják meg, ahol a költségvetés-ellenőrzés bekapcsolása fontos.  

### <a name="select-main-accounts"></a>Főszámlák kiválasztása

Ha a **Fő számla** nincs bejelölve költségvetés ellenőrzési dimenzióként a **Paraméterek meghatározása** lapon, de rendszer kezel bizonyos kiadásokat, kiválaszthatja azokat a kiadásokat a **Főszámlák kiválasztása** lapon. Ha a **Fő számla** ki van jelölve költségvetés-ellenőrzési dimenzióként nem szükségesek a bejegyzések.  

### <a name="define-budget-groups"></a>Költségvetési csoportok meghatározása

Következő, a **Költségvetési csoportok meghatározása** lapon választhatóan meghatározhatja a pénzügyi dimenzió egyedi kombinációit, ahol a költségvetési erőforrások a másodlagos költségvetés ellenőrzésére vonatkozóan összesítve vannak. Létrehozhat egy egyedi rekordot, amely tartalmazza az egész szervezetet, vagy megadhat több csoportot az önálló osztályok vagy költséghelyek képviseletére.  

### <a name="define-message-levels"></a>Üzenetszintek meghatározása

Ha a költségvetés-ellenőrzési figyelmeztetéseket le kell tiltani bármilyen felhasználócsoporthoz, megadhatja azokat a csoportokat az **Üzenetszintek meghatározása** oldalon. A felhasználói csoportok tagjai továbbra is megkapják a hibaüzenetet, ha túllépik a költségvetés-túllépésen alapuló elérhető költségvetési alapokat.

### <a name="activate-budget-control"></a>Költségvetés-ellenőrzés aktiválása

A költségvetés-ellenőrzés beállítása után kapcsolja be, és aktiválja a **Költségvetés-ellenőrzés aktiválása** lapon. Ezt követően a piszkozati verzió érvényessé válik.
> [!Important]
> A költségvetés-ellenőrzés bekapcsolását és aktiválását, és a tranzakciók feladását követően ne kapcsolja ki év közben. A költségvetés-ellenőrzés kikapcsolásakor a tevékenységeket nem rögzítik a költségvetési-ellenőrzés céljaira vonatkozóan, és a költségvetés-ellenőrzés nem fut tovább. Ezért azokat a dokumentumokat, amelyek már fel lettek adva lehet, hogy nem megfelelően tükrözik a fennmaradó összegeket vagy egyenlegeket és jelentéseket, amelyek a költségvetés-ellenőrzéssel kapcsolatban állnak. Ezek közé tartozik az alsóbb rétegbeli vagy helyesbítő bizonylatok és-naplók költségvetés-ellenőrzési statisztikái. 

Ezenkívül vegye figyelembe, hogy azokat a tranzakciókat a költségvetési tételjegyzék-bejegyzéseket beleértve, amelyek feladásra kerültek a költségvetés-ellenőrzés bekapcsolása előtt nem veszi figyelembe a költségvetés-ellenőrzés. Ezért a költségvetés-ellenőrzés bekapcsolása csak az új költségvetési időszak kezdetekor ajánlott. Győződjön meg arról, hogy a Költségvetésjegyzék bejegyzései tartalmazzák a költségvetés kezdő egyenlegeit a költségvetés-ellenőrzésre vonatkozóan, és hogy a költségvetési egyenlegek frissítése csak a költségvetési-ellenőrzés bekapcsolását követően ment végbe. Bármilyen megnyitott dokumentum (pl. Beszerzési rendelés) ellenőrzi a program az elérhető forrásokra vonatkozóan és költségvetési tartalékot hoz létre a költségvetés-ellenőrzéshez, ha a felhasználó manuálisan lefuttatja a költségvetés-ellenőrzést a dokumentumban.

## <a name="using-budget-control"></a>Költségvetés-ellenőrzés használata
A költségvetés-ellenőrzés aktiválását követően, a felhasználók költségvetés-ellenőrzési figyelmeztetés és hibaüzenetet kapnak a költségvetés-ellenőrzéshez beállított dokumentumokban és naplókban. Ne feledje, hogy a költségvetés-ellenőrzést beállíthatja úgy, hogy a felhasználók figyelmeztetést kapnak, ha meghaladja a költségvetési alapokat, de továbbra is megerősítheti vagy feladhatja a tranzakciót. A felhasználók a sikertelen költségvetés-ellenőrzés részletes adatait megtekinthetik a **Költségvetés-ellenőrzési hibák és figyelmeztetések** oldalon.   

Erről a lapról a felhasználók a **Költségvetés-ellenőrzési statisztika időszak szerint** lapra léphetnek a költségvetés elérhetőségének részleteinek és a kiválasztott költségvetés-ellenőrzési dimenzióra vonatkozó foglalások megtekintéséhez. Felhasználók beléphetnek a **Költségvetés-ellenőrzési statisztika** lapra az összes költségvetés-ellenőrzésben használt pénzügyi dimenzió kombinációra vonatkozó költségvetés elérhetőségeinek megtekintéséhez. 

Ha a költségvetési-ellenőrzés aktív a beszerzési rendelésekre vonatkozóan a költségvetéskezelő használhatja a **Főkönyvi költségvetések és előrejelzések** munkaterületet az összes figyelmeztetéssel és hibával rendelkező jóváhagyásra váró beszerzési rendelés várakozási sorának áttekintéséhez. Ha a költségvetés-kezelő rendelkezik költségvetés átlépési engedéllyel, akkor jóváhagyható a beszerzési rendelés közvetlenül a munkahelyen.    


[!INCLUDE[footer-include](../../includes/footer-banner.md)]