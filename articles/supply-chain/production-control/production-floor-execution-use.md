---
title: A termelési üzem végrehajtási felületének dolgozók általi használata
description: Ez a témakör azt mutatja be, hogyan kell használni a termelési üzem végrehajtási felületét egy dolgozó szemszögéből.
author: johanhoffmann
ms.date: 01/24/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: JmgProductionFloorExecution
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-10-05
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: f163b8feb906470f31a648bf09abf5647c5f1bab
ms.sourcegitcommit: d715e44b92b84b1703f5915d15d403ccf17c6606
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/27/2022
ms.locfileid: "8644990"
---
# <a name="how-workers-use-the-production-floor-execution-interface"></a>A termelési üzem végrehajtási felületének dolgozók általi használata

[!include [banner](../includes/banner.md)]

A termelési üzem végrehajtási felületét az érintéses kezelésre optimalizálták. A kinézete vizuális kontrasztot nyújt, amely megfelel az üzemi környezetek hozzáférhetőségi követelményeinek. A feladatkártya-eszköz összes funkcióját felkínálja. Azt is lehetővé teszi azonban, hogy a feladatlistából párhuzamosan több feladat induljon el. (Ezt a lehetőséget nevezik *feladatkötegelésnek*.) Ezenkívül a feladatok listájából a dolgozók megnyithatnak egy, a Microsoft Dynamics 365 Guide alkalmazásban létrehozott útmutatót. Ily módon vizuális utasításokat kaphatnak a HoloLens felületen keresztül.

## <a name="sign-in-to-the-production-floor-execution-interface-as-a-worker"></a>Bejelentkezés a termelési üzem végrehajtási felületébe dolgozóként

Mielőtt a dolgozók elkezdhetik az eszköz használatát, egy felettesnek vagy egy műszaki alkalmazottnak elő kell készítenie, és meg kell nyitnia a megfelelő lapot a Dynamics 365 Supply Chain Management alkalmazásban. Az eszköz beállításával kapcsolatos további tudnivalókért lásd [Eszköz beállítása a termelési üzem végrehajtási felületének futtatására](production-floor-execution-setup.md) című témakört.

Az eszköz előkészítését követően megjelenik a bejelentkezési lap. Ez a lap a helyi munkacella feladatainak állapotát jeleníti meg. Ez az információ időszakosan frissül. A lapra a dolgozók a jelvényazonosítójukkal lépnek be. Annak ellenére, hogy a dolgozóknak nincs felhasználói fiókjuk a Supply Chain Management programhoz, rendelkezniük kell egy olyan *Munkaidő-nyilvántartásba vett munkavállalói* fiókkal, amelyet a bejelentkezéskor használni tudnak.

![A termelési üzem végrehajtási felületének bejelentkezési oldala.](media/pfei-sign-in-page.png "A termelési üzem végrehajtási felületének bejelentkezési oldala")

A témakör többi része leírja, hogy a dolgozók hogyan használják a kezelőfelületet.

## <a name="all-jobs-tab"></a>Minden feladat lap

A **Minden feladat** lap egy feladatlistát tartalmaz, amelyen látható az összes olyan termelési feladat, amely állapota *Nincs elindítva*, *Leállítva*, vagy *Elindítva*. (Ez a lapnév testreszabható, és az ön rendszerénél más lehet.)

![Minden feladat lap.](media/pfei-all-jobs-tab.png "Minden feladat lap")

A Feladatlista az alábbi oszlopokkal rendelkezik. A számok az előzőekben bemutatott számoknak felelnek meg.

1. **Kiválasztás oszlop** – a bal szélső oszlop ellenőrző pipákkal jelzi, hogy a dolgozó mely feladatokat választotta ki. A dolgozók egyszerre több feladatot is kijelölhetnek a listában. A lista minden feladatának kiválasztásához jelölje ki az oszlop fejlécét. Ha egy feladatot kijelölt, akkor a feladattal kapcsolatos részletek a lap alsó részén jelennek meg.
1. **Feladat állapota oszlop** – Ez az oszlop szimbólumok használatával jelzi az egyes feladatok állapotát. Azoknak a feladatoknak, amelyeknél nincs jel az oszlopban, az állapota *Nincs elindítva*. A zöld háromszög azt jelzi, hogy a feladatok állapota *Elindítva*. A két sárga függőleges sor a *Leállítva* állapotú feladatokat jelöli.
1. **Kiemelt prioritás oszlop** – Ez az oszlop felkiáltójelekkel jelzi a kiemelt prioritású feladatokat.
1. **Rendelés** – Ez az oszlop a feladathoz tartozó termelési rendelés számát jeleníti meg.
1. **Leírás** – Ez az oszlop megjeleníti annak a műveletnek a leírását, amelyhez a feladat tartozik.
1. **Igényelve** – Ez az oszlop azt a mennyiséget jeleníti meg, amelyet a feladatnak terv szerint elő kell állítania.
1. **Elindítva** – Ez az oszlop azt a mennyiséget jeleníti meg, amelyet már elindítottak a feladathoz.
1. **Befejezve** – Ez az oszlop azt a mennyiséget jeleníti meg, amelyet már befejeztek a feladathoz.
1. **Selejtezett** – Ez az oszlop azt a mennyiséget jeleníti meg, amelyet selejteztek a feladathoz.
1. **Hátralévő** – Ez az oszlop azt a mennyiséget jeleníti meg, amely még hátravan a feladatból.

## <a name="active-jobs-tab"></a>Aktív feladatok lap

Az **Aktív feladatok** lapok felsorolják azokat a feladatokat, amelyeket a bejelentkezett dolgozó már megkezdett. (Ez a lapnév testreszabható, és az ön rendszerénél más lehet.)

![Aktív feladatok lap.](media/pfei-active-jobs-tab.png "Aktív feladatok lap")

Az aktív feladatokat tartalmazó lista az alábbi oszlopokkal rendelkezik.

- **Kiválasztás oszlop** – a bal szélső oszlop ellenőrző pipákkal jelzi, hogy a dolgozó mely feladatokat választotta ki. A dolgozók egyszerre több feladatot is kijelölhetnek a listában. A lista minden feladatának kiválasztásához jelölje ki az oszlop fejlécét. Ha egy feladatot kijelölt, akkor a feladattal kapcsolatos részletek a lap alsó részén jelennek meg.
- **Rendelés** – Ez az oszlop a feladathoz tartozó termelési rendelés számát jeleníti meg.
- **Leírás** – Ez az oszlop megjeleníti annak a műveletnek a leírását, amelyhez a feladat tartozik.
- **Igényelve** – Ez az oszlop azt a mennyiséget jeleníti meg, amelyet a feladatnak terv szerint elő kell állítania.
- **Elindítva** – Ez az oszlop azt a mennyiséget jeleníti meg, amelyet már elindítottak a feladathoz.
- **Befejezve** – Ez az oszlop azt a mennyiséget jeleníti meg, amelyet már befejeztek a feladathoz.
- **Selejtezett** – Ez az oszlop azt a mennyiséget jeleníti meg, amelyet selejteztek a feladathoz.
- **Hátralévő** – Ez az oszlop azt a mennyiséget jeleníti meg, amely még hátravan a feladatból.

## <a name="my-jobs-tab"></a>Feladatok lap

A **Feladatok lap** segítségével a dolgozók egyszerűen megtekinthetik a kifejezetten hozzájuk rendelt még el nem adott és be nem adott feladatokat. Olyan vállalatoknál hasznos, ahol a feladatokat időnként vagy mindig meghatározott dolgozókhoz (emberi erőforrásokhoz) rendelik, nem pedig más típusú erőforrásokhoz (például gépekhez).

Az ütemezési rendszer automatikusan hozzárendel minden termelési feladatot egy adott erőforrásrekordhoz, és minden erőforrásrekordnak van típusa (például gép vagy emberi). Amikor beállít egy alkalmazottat termelési dolgozóként, a dolgozói számlát egy egyedi emberierőforrás-rekordhoz társíthatja.

A **Feladatok lap** felsorolja azokat a még el nem adott és be nem adott feladatokat, amelyek a bejelentkezett dolgozó emberierőforrás-rekordhoz vannak rendelve, amennyiben van bejelentkezett dolgozó. Soha nem sorolja fel azokat a feladatokat, amelyek hozzá vannak rendelve egy géphez vagy más típusú erőforráshoz, még akkor sem, ha a bejelentkezett dolgozó elkezdte dolgozni ezeket a feladatokat.

Ha az összes olyan feladatot meg kell tekinteni, amelyet a bejelentkezett dolgozó elindított, az egyes feladatokhoz rendelt erőforrás típusától függetlenül az **Aktív feladatok lapot** használja. A helyi feladatszűrő **konfigurációjának megfelelő összes befejezetlen feladat megtekintéséhez a dolgozó vagy a kezdés állapotától függetlenül használja a Minden feladat lapot**.

![Feladatok lap](media/pfei-my-jobs-tab.png "Feladatok lap")

## <a name="my-machine-tab"></a>Saját gép lap

A **Saját gép** lapon a dolgozók kiválasztják azt az eszközt, amely egy géperőforráshoz kapcsolódik a **Minden feladat** lapon beállított szűrőn belül. A dolgozó ezután megtekintheti a kiválasztott eszköz állapotát: legfeljebb négy kijelölt számláló értékét és a közelmúltbeli karbantartási kérések és a regisztrált leállások listáját olvassa be. A dolgozó a kiválasztott eszköz karbantartását is kérheti, valamint regisztrálhatja és szerkesztheti a gép leállását. (Ez a lapnév testreszabható, és az ön rendszerénél más lehet.)

![Saját gép lap.](media/pfei-my-machine-tab.png "Saját gép lap")

A **Saját gép lap** a következő oszlopokat tartalmazza. A számok az előzőekben bemutatott számoknak felelnek meg.

1. **Gépi eszköz** – Válassza ki a nyomon követni kívánt gépi eszközt. Kezdjen el beírni egy nevet, és válasszon az egyező eszközök listájáról, vagy válassza ki a nagyító ikont a feladatlista szűrőiben található erőforrásokhoz társított összes eszköz listájáról való kiválasztáshoz.

    > [!NOTE]
    > A Supply Chain Management felhasználói szükség szerint hozzárendelhetnek egy erőforrást az egyes eszközökhöz az **Összes eszköz** lap segítségével (az **Erőforrás** legördülő lista használatával a **Tárgyi eszköz** lapon). További tudnivalókért lásd: [Eszköz létrehozása](../asset-management/objects/create-an-object.md).

1. **Beállítások** – A fogaskerekek ikonjának kiválasztásával egy párbeszédpanel nyílik meg, amelyen kiválaszthatja, hogy a kiválasztott gépeszköz mely számlálóit kell megtekinteni. Ezeknek a számlálóknak az értékei az **Eszközkezelés lap** tetején jelennek meg. A **Beállítások** menü (a következő képernyőképen látható) segítségével akár négy számlálót engedélyezhet. Az engedélyezni kívánt számlálókhoz használja a csempe tetején található keresési mezőt, és válasszon ki egy számlálót. A keresési mező az **Eszközkezelés** lap tetején kijelölt eszközhöz társított összes számlálót listázza. Állítsa be az egyes számlálókat az **Összesített** érték vagy a számláló legutóbbi **Tényleges** értékének figyeléséhez. Ha például olyan számlálót állít be, amely nyomon követi, hogy a gép hány órát fut, akkor azt **Összesített** értékre kell állítania. Ha a legutóbb frissített hőmérséklet vagy hőmérséklet mérésére állít be számlálót, akkor a **Tényleges** értékre kell beállítania. Az **OK** gombra kattintva mentse a beállításokat, és zárja be a párbeszédpanelt.

    ![Saját gép lap beállításai.](media/pfei-my-machine-tab-settings.png "Saját gép lap beállításai")

1. **Karbantartás kérése** – Ezzel a gombbal megnyithat egy párbeszédpanelt, ahol létrehozhatja a karbantartási kéréseket. Meg lehet adni egy leírást és megjegyzést. A kéréssel egy Supply Chain Management felhasználó fog foglalkozni, aki ezt követően karbantartási munkarendelésre konvertálhatja a karbantartási kérést.
1. **Leállás regisztrálása** – Ezzel a gombbal megnyithat egy párbeszédpanelt, ahol regisztrálhatja a gép leállását. Kiválaszthatja az okkódot, és megadhatja a leállás dátumát/tartományát. A gép leállási idejének regisztrációja a gépi eszköz hatékonyságának kiszámítására használható.
1. **Megtekintés vagy szerkesztés** – Ezzel a gombbal megnyithat egy párbeszédpanelt, ahol szerkesztheti és megtekintheti a meglévő leállási rekordokat.

## <a name="starting-and-completing-production-jobs"></a>Termelési feladatok elindítása és befejezése

A dolgozók egy termelési feladatot úgy indíthatnak el, hogy kijelölnek egy feladatot a **Minden feladat** lapon, majd a **Feladat megkezdése** lehetőséget választják a **Feladat megkezdése** párbeszédpanel megnyitásához.

![Feladat megkezdése párbeszédpanel.](media/pfei-start-job-dialog.png "Feladat megkezdése párbeszédpanel")

A dolgozók a **Feladat megkezdése** párbeszédpanelt használják a termelési mennyiség visszaigazolására, majd a feladat elindítására. A dolgozók a mennyiséget a **Mennyiség** mező kiválasztásával, majd a megjelenő numerikus billentyűzet használatával módosíthatják. A dolgozók ezt követően az **Elindítás** lehetőség kiválasztásával indíthatják el a feladatot. A **Feladat megkezdése** párbeszédpanel bezárulm és a feladat bekerül az **Aktív feladatok** lapra.

A dolgozók bármilyen állapotú feladatot elindíthatnak. Amikor egy dolgozó egy *Nincs elindíva* állapotú feladatot indít el, a **Feladat megkezdése** párbeszédpanel **Mennyiség** mezője először a teljes mennyiséget jeleníti meg. Amikor egy dolgozó egy *Elindítva* vagy *Leállítva* állapotú feladatot indít el, a **Mennyiség** mező először a hátrelevő mennyiséget jeleníti meg.

## <a name="reporting-good-quantities"></a>Jó mennyiségek jelentése

Amikor egy dolgozó befejezte vagy részben befejezte a feladatot, akkor az **Aktív feladatok** lapon kiválaszthatna az **Előrehaladás jelentése** lehetőséget, hogy jelentse a legyártott jó mennyiséget. Ezután az **Előrehaladás jelentése** párbeszédpanelen a dolgozó beírja a jó mennyiséget a numerikus billentyűzet segítségével. Alapértelmezetten a mennyiségben semmi nem látható. A mennyiség megadása után a dolgozó a feladatra vonatkozó állapotot frissítheti az alábbiak valamelyikére: *Folyamatban*, *Leállítva* vagy *Befejezve*.

![Az Előrehaladás jelentése párbeszédpanel.](media/pfei-report-progress-dialog.png "Az Előrehaladás jelentése párbeszédpanel")

## <a name="reporting-good-quantities-on-batch-orders-that-have-co-products-and-by-products"></a>Helyes mennyiségek jelentése olyan kötegelt rendelések esetén, amelyek társ- és melléktermékeket tartalmaznak

A dolgozók használhatják a gyártóterületi végrehajtási felületet a kötegelt rendelések előrehaladásának jelentéséhez. Ez a jelentésfunkció jelentéseket tartalmaz a társtermékekről és melléktermékekről.

Egyes gyártók, különösen a feldolgozóiparban, a kötegrendelések segítségével felügyelik a termelési folyamatokat. A kötegrendelések receptúrákból vannak létrehozva, és ezek a receptúrák úgy is definiálhatók, hogy társ- és melléktermékekkel is rendelkezzenek kimeneten. A kötegrendelésekre vonatkozó visszajelzések jelentésénél a kimenet mennyiségét regisztrálni kell a receptúracikken, valamint a társ- és melléktermékeken.

Amikor egy dolgozó kötegelt rendelésen befejez vagy részben befejez egy feladatot, akkor jelenteni tudja a jó vagy selejt termékek mennyiségét minden egyes termékhez, amely a rendelés kimeneteként van meghatározva. A kötegelt rendelés kimeneteként definiált termékek *Receptúra*, *Társtermék* vagy *Melléktermék* típusúak is lehetek.

A termékek jó mennyiségének jelentéséhez egy dolgozó kiválaszt egy feladatot az **Aktív feladatok** lapon, majd kiválasztja a **Jelentés az előrehaladásról** lehetőséget.

Ezután a **Jelentés az előrehaladásról** párbeszédpanelen a dolgozó kiválaszthat azok közül a termékek közül, amelyek kimenetként vannak megadva a kötegrendeléshez. A dolgozó kiválaszthat egy vagy több terméket a listából, majd kiválaszthatja a **Jelentés az előrehaladásról** lehetőséget. Alapértelmezés szerint minden terméknél üres a mennyiség, és a dolgozó a numerikus billentyűzet használatával adhatja meg a mennyiséget. A dolgozó az **Előző** és a **Következő** gombbal mozoghat a kijelölt termékek között. A mennyiség megadása után íz egyes termékekhez a dolgozó a feladatra vonatkozó állapotot frissítheti az alábbiak valamelyikére: *Folyamatban*, *Leállítva* vagy *Befejezve*.

![Társtermékek és melléktermékek jelentése.](media/report-co-by-products.png "Társtermékek és melléktermékek jelentése")

### <a name="reporting-on-batch-orders-for-planning-items"></a>Jelentés kötegrendelésről cikkek tervezéséhez

Amikor egy dolgozó befejez egy tervezési cikkre vonatkozó kötegrendelési feladatot, akkor a mennyiségeket csak a társ- és melléktermékekről jelenti, mivel a tervezési cikkek nem tartalmaznak *Receptúra* típusú cikket.

### <a name="reporting-co-product-variation"></a>Társtermék variációinak jelentése

Ha olyan receptúraverzióból jött létre kötegrendelés, amelyben a **Társtermékek változatai** beállítás *Igen* értékű a dolgozó jelenthet az olyan társtermékekről, amelyek nem részei a kötegrendelés definíciójának. Ez a funkció olyan helyzetekben használatos, amikor váratlan termékkimenet fordulhat elő a termelési folyamatban.

Ebben az esetben a dolgozó meghatározhatja a társterméket és a jelentendó mennyiséget, ha kiválasztja a **Társtermékek variációi** elemet az előrehaladás jelentése párbeszédpanelen. A dolgozó ezután választhat a társtermékként definiált kiadott termék közül.

### <a name="reporting-catch-weight-items"></a>A cikkeket jelentéskészítése

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]
<!-- KFM: preview until further notice -->

A dolgozók a termelés emeletének végrehajtási felületével jelentést tehetnek a cikkekhez létrehozott kötegrendelések előrehaladásáról. A kötegrendelések képletek alapján vannak létrehozva, amelyek definiálhatóak úgy, hogy receptúrás cikkként, társtermékként vagy társtermékként tartalmazzanak egy cikkeket. A receptúra úgy is definiálható, hogy receptúrás sorokat kap az összetevőkből, amelyek meg vannak határozva a catch weight számára. A tényleges stömegű cikkek két mértékegységet használnak a készlet nyomon követésére: a tényleges súly és a készletmennyiség. Például az élelmiszeriparban a dobozolt hús tényleges ssúlyos cikkként definiálható, ahol a tényleges súly mennyiségét használják a dobozok számának nyomon követésére, a készletmennyiséget pedig a dobozok súlyának nyomon követésére.

## <a name="reporting-scrap"></a>Selejt jelentése

Amikor egy dolgozó befejezte vagy részben befejezte a feladatot, akkor az **Aktív feladatok** lapon kiválaszthatna a **Selejtek jelentése** lehetőséget, hogy jelentse a legyártott leselejtezett mennyiséget. Ezután a **Selejtek jelentése** párbeszédpanelen a dolgozó beírja a leselejtezett mennyiséget a numerikus billentyűzet segítségével. A dolgozó az okot (*Semmilyen*, *Gép*, *Kezelő* vagy *Anyag*) is kiválasztja.

![A Selejtek jelentése párbeszédpanel.](media/pfei-report-scrap-dialog.png "A Selejtek jelentése párbeszédpanel")

## <a name="adjust-material-consumption-and-make-material-reservations"></a>Anyagfelhasználás kiigazítása és anyagfoglalások foglalása

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]
<!-- KFM: preview until further notice -->

A dolgozók minden termelési feladat esetében módosíthatja az anyagfelhasználást. Ez a funkció olyan helyzetekben használatos, amikor a termelési feladat által ténylegesen felhasznált anyagok mennyisége nagyobb vagy kisebb volt a tervezett mennyiségnél. Ezért módosítani kell, hogy a készletszintek aktuálisak maradjon.

A dolgozók foglalásokat is fel tudnak foglalni a köteg- és sorozatszámokra. Ez a funkció olyan helyzetekben használatos, amikor egy dolgozónak manuálisan meg kell adnia, hogy melyik anyagkötemény- vagy sorozatszámot használta a rendszer, hogy megfeleljen az anyag nyomonkövethetőségi követelményeinek.

A dolgozók az Anyag beállítása beállításával adhatja meg a módosítandó **mennyiséget**. Ez a gomb a következő helyeken érhető el:

- A Jelentés selejtes **párbeszédpanelén**
- A Jelentés állapota **párbeszédpanelen**
- A jobb oldalon található eszköztáron

### <a name="adjust-material-consumption-from-the-report-scrap-and-report-progress-dialog-boxes"></a>Az anyagfelhasználás beállítása a Selejtjelentés és a Jelentés állapota párbeszédpanelről

Miután a dolgozó beírja a jelentandó mennyiséget a **Jelentés** **állapota** vagy a Selejt jelentése párbeszédpanelen, **elérhetővé válik az Anyag** módosítása gomb. Amikor a felhasználó kiválasztja ezt a gombot, megjelenik az **Anyag** beállítása párbeszédpanel. Ezen a párbeszédpanelen azokat a cikkeket listázza, amelyek a feladathoz jelentett jó vagy selejt mennyiségei alapján tervezetten felhasználandók.

A párbeszédpanelen található lista a következő információkat mutatja:

- **Termékszám** – az alaptermék és a termékváltozat.
- **Terméknév** – A termék neve.
- **Javaslat** – a feladathoz megadott mennyiségre vonatkozó haladás vagy selejt jelentésekor felhasznált anyag becsült mennyisége.
- **Felhasználás** – az a tényleges anyagmennyiség, amely akkor lesz felhasználva, amikor a feladathoz megadott mennyiségre vonatkozó haladást vagy selejtet jelentik.
- **Lefoglalva** – a készletben fizikailag lefoglalt anyag mennyisége.
- **Egység** – az anyagjegyzék egysége.

A párbeszédpanel jobb oldala a következő információkat mutatja:

- **Termékszám** – az alaptermék és a termékváltozat.
- **Becsült** – a becsült felhasználandó mennyiség.
- **Elindítva** – a termelési feladatban elindított mennyiség.
- **Fennmaradó mennyiség** – a becsült mennyiségből a még felhasználandó mennyiség.
- **Kiadott mennyiség** – a felhasznált mennyiség.

A következő műveletek végezhetők el:

- A dolgozó a Felhasználás beállítása lehetőség választásával meghatározhatja az **anyagmennyiséget**. A mennyiség megerősítést követően **a** Felhasználás oszlopban szereplő mennyiség frissül a módosított mennyiséggel.
- Ha a dolgozó az Anyag beállítása lehetőséget **választja**, létrejön egy termelési kitárolásilista-napló. Ez a napló ugyanazokból a cikkekből és mennyiségekből áll, mint az Anyag **beállítása** lista.
- Amikor a dolgozó az Anyag beállítása párbeszédpanelen módosít egy mennyiséget, **a** megfelelő naplósor Javaslat mezőjében is ugyanannak a **mennyiségnek** a frissítése történik. Ha a dolgozó a Mégse **lehetőséget** választja az **Anyag** módosítása párbeszédpanelen, a kitárolási lista törlődik.
- Ha a dolgozó az OK **lehetőséget** választja, a kitárolási lista nem törlődik. A feladásra akkor történik meg, amikor **a** **feladatot jelentik a Selejtjelentés vagy a Jelentés állapota párbeszédpanelen.**
- Ha a dolgozó a Jelentés **folyamatban** **·** **vagy** a Selejt jelentése párbeszédpanelen a Mégse lehetőséget választja, a kitárolási lista törlődik.

### <a name="adjust-material-from-the-primary-or-secondary-toolbar"></a>Az elsődleges vagy másodlagos eszköztár anyagának beállítása

Az **Anyag beállítása** gomb beállítható úgy, hogy megjelenjen az elsődleges vagy a másodlagos eszköztáron. (További tájékoztatás: [A termelési emelet végrehajtási felületének tervezése](production-floor-execution-tabs.md).) Egy dolgozó beállíthatja az **Anyagok** kiigazítása lehetőséget a folyamatban lévő termelési feladathoz. Ebben az esetben megjelenik az **Anyag** beállítása párbeszédpanel, ahol a dolgozó módosíthatja a kívánt módosításokat. A párbeszédpanel megnyitásakor a termelési rendeléshez létrejön egy termelési kitárolási lista, amely tartalmazza a módosított mennyiségek sorait. Ha a dolgozó a Feladás lehetőséget **választja**, a módosítást visszaigazoljuk, és meg történik a kitárolási lista feladása. Ha a dolgozó a Mégse **lehetőséget választja**, a kitárolási lista törlődik, és nem kerül sor helyesbítésre.

### <a name="adjust-material-consumption-for-catch-weight-items"></a>Anyagfelhasználás kiigazítása a catch weight cikkekhez

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]
<!-- KFM: preview until further notice -->

A dolgozók módosíthatja az anyagfelhasználást a catch weight cikkekhez. Ez a funkció olyan helyzetekben használatos, amikor a termelési feladat által felhasznált tényleges súlyú anyag tényleges mennyisége több vagy kevesebb volt, mint a tervezett mennyiség. Ezért módosítani kell, hogy a készletszintek aktuálisak maradjon. Ha egy dolgozó módosítja egy tényleges ssúlyos cikkfelhasználását, akkor a tényleges súly és a készletmennyiség is módosítható. Ha például egy termelési feladat a tervek szerint öt dobozt fog felhasználtani, amelyekben a becsült súly 2 kilogramm/doboz, akkor a dolgozó módosíthatja a felhasznált dobozok számát és a mezők súlyát is. A rendszer ellenőrzi, hogy a mezők megadott súlya a kiadott termékhez meghatározott minimális és maximális küszöbértéken belül van-e.

### <a name="reserve-materials"></a>Anyagok foglalása

Az Anyag beállítása **párbeszédpanelen** a **dolgozó az Anyagfoglalás lehetőség választásával anyagfoglalásokat hozhat és módosíthat**. A **megjelenő Anyag lefoglalása** párbeszédpanelen látható a cikk fizikailag elérhető készlete az egyes tárolási és nyomon követési dimenziókhoz.

Ha az anyag engedélyezve van a speciális raktári folyamatokban, akkor a lista csak a ténylegesen elérhető készletet jeleníti meg az anyag termelési bemeneti helyéhez. A termelés bemeneti helye abban az erőforrásban van definiálva, ahol a termelési feladatot tervezik. Ha a cikkszám köteg- vagy sorozatszám szerint ellenőrzött, akkor a ténylegesen elérhető köteg- és sorozatszámok teljes listája látható. A lefoglalandó mennyiség megadásához a dolgozó az Anyag lefoglalása lehetőséget **választhatja**. Meglévő foglalás eltávolításához a dolgozó a Foglalás eltávolítása lehetőséget **választhatja**.

A termelés bemeneti helyének beállításával kapcsolatos további tudnivalókat lásd a következő post- és utócímben: [A termelés bemeneti helyének beállítása](/archive/blogs/axmfg/deliver-picked-materials-to-the-locations-where-the-materials-are-consumed-by-operations-in-production).

> [!NOTE]
> A dolgozó által a Foglalások **párbeszédpanelen** **·** **·** **alkalmazott foglalások megmaradnak, ha a dolgozó a Mégse lehetőséget választja a Jelentés állapota vagy a Selejt jelentése párbeszédpanelen.**
>
> A cikk-foglalások nem helyesb módosíthatók.

## <a name="completing-a-job-and-starting-a-new-job"></a>Feladat befejezése és új feladat megkezdése

A dolgozók általában egy feladatot elvégeztével az **Aktív feladatok** lapon egy vagy több aktuális feladatot kiválaszt , majd az **Előrehaladás jelentése** lehetőséget választja. Ezután beírja a termelt mennyiséget (a jó mennyiséget), és átállítja az állapotot *Befejezettre*. Ha egynél több feladatot választott ki, akkor a dolgozó az **Előző** és a **Következő** gombbal mozoghat közöttük. Új feladat megkezdéséhez a dolgozó kiválasztja azt a **Minden feladat** lapon, majd kiválasztja a **Feladat megkezdése** lehetőséget.

Egy dolgozó akkor is elindíthat új feladatot, ha a korábbi feladat még nyitva van. Ebben az esetben is, a dolgozó kiválasztja az új feladatot a **Minden feladat** lapon, majd kiválasztja a **Feladat megkezdése** lehetőséget. Ebben az esetben azonban a **Feladat megkezdése** párbeszédpanel tájékoztatja a dolgozót, hogy éppen dolgozik egy feladaton, és ennek megfelelően az új feladat elkezdése előtt azt le kell állítania vagy be kell fejeznie.

## <a name="working-on-multiple-jobs-in-parallel"></a>Több feladaton történő dolgozás párhuzamosan

Egy dolgozó egyszerre több feladatön is dolgozhat (párhuzamosan). Ebben az esetben a dolgozó által használt feladatok gyűjteményét *munkacsomagnak* nevezzük. A dolgozó új feladatokat vehet fel a csomagba, vagy végrehajthat egy vagy több feladatot a csomagból. Az alábbi két forgatókönyv azt mutatja be, hogy hogyan lehet párhuzamosan dolgozni a feladatokon.

### <a name="scenario-1-a-worker-who-has-no-active-jobs-wants-to-start-two-jobs-and-work-on-them-in-parallel"></a>1. eset: egy olyan dolgozó, aki nem rendelkezik aktív feladattal, két feladatot indít el, és párhuzamosan dolgozik velük

A dolgozó kiválasztja a két feladatot a **Minden feladat** lapon, majd kiválasztja a **Feladat megkezdése** lehetőséget. A **Feladat megkezdése** párbeszédpanel megjeleníti a kiválasztott feladatokat, és a dolgozó módosíthatja az egyes feladatoknál elindítandó mennyiséget. A dolgozó ezt követően megerősíti a párbeszédpanelt, és mindkét feladatot elindíthatja.

### <a name="scenario-2-a-worker-who-has-two-active-jobs-that-are-in-progress-wants-to-start-a-third-job-and-work-on-it-in-parallel-with-the-other-two"></a>2. eset: egy olyan dolgozó, akinek két aktív feladata van folyamatban, egy harmadik feladatot akar elindítani, és a másik kettővel párhuzamosan dolgozni

A dolgozó kiválasztja a harmadik feladatot a **Minden feladat** lapon, majd kiválasztja a **Csomag** lehetőséget. A **Csomag** párbeszédpanelen a dolgozó módosíthatja az elindulási mennyiséget. A dolgozó ezt követően megerősíti a párbeszédpanelt, a **Csomag** lehetőség kiválasztásával.

## <a name="working-on-indirect-activities"></a>Közvetett tevékenységeken történő munka

A közvetett tevékenységek olyan tevékenységek, amelyek nem kapcsolódnak közvetlenül a termelési rendeléshez. A közvetett tevékenységek rugalmasan meghatározhatók, a [Munkaidő és jelenlét közvetett tevékenységeinek beállítása](/dynamicsax-2012/appuser-itpro/set-up-indirect-activities-for-time-and-attendance) című témakörben leírtak szerint.

Például Shannon, egy dolgozó a Contoso nevű vállalatnál, egy vállalati találkozón szeretne részt venni, és a találkozókat közvetett tevékenységnek tekinti. A következő két eset valamelyike érvényes:

- **Shannon egy vagy több aktív feladaton dolgozik.** Shannon kiválasztja a **Tevékenység** lehetőséget, azonosítja a tevékenységet (találkozó), és megerősíti a kijelölést. A megjelenő üzenet arról tájékoztatja, hogy már vannak folyamatban lévő feladatai. Az üzenetből Shannon eldöntheti, hogy befejezi vagy leállítja azokat a feladatokat, amelyeken dolgozik, mielőtt elmenne a találkozóra.
- **Shannonnak nincsenek aktív feladatai.** Shannon kiválasztja a **Tevékenység** lehetőséget, azonosítja a tevékenységet (találkozó), és megerősíti a kijelölést. A rendszer regisztrálta, hogy a találkozón van.

Mindkét esetben, miután Shannon megerősíti a kijelölést, vagy a bejelentkezési oldalra lép, vagy egy olyan oldalra, amelyen meg kell erősítenie, hogy visszatért a közvetett tevékenységből. A megjelenő lap a termelési üzem végrehajtási felületének konfigurációjától függ. (További tájékoztatás: [A termelési üzem végrehajtási felületének konfigurálása](production-floor-execution-configure.md).)

## <a name="registering-breaks"></a>Regisztrált szünetek

A dolgozók a szüneteket is regisztrálhatják. A szünetek rugalmasan meghatározhatók, a [Regisztrációk alapján történő fizetés](pay-based-on-registrations.md) témakör leírása alapján.

Ha dolgozó egy szünetet akar regisztrálni, kijelöli a **Szünet** lehetőséget , majd kiválasztja a szünet típusát képviselő lapot (például ebéd). Miután a dolgozó megerősíti a kijelölést, az eszköz a bejelentkezési oldalt vagy egy olyan oldalt jelenít meg, amelyen a dolgozónak vissza kell igazolnia, hogy visszatért a szünetből. A megjelenő lap a termelési üzem végrehajtási felületének konfigurációjától függ. (További tájékoztatás: [A termelési üzem végrehajtási felületének konfigurálása](production-floor-execution-configure.md).)

## <a name="view-the-my-day-dialog"></a>A "Saját nap" párbeszédpanel megjelenítése

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]
<!-- KFM: preview until 10.0.27 GA -->

A **Saját nap** párbeszédpanelen a dolgozók áttekintést kaphatnak regisztrációikról és egyenlegeikről. A párbeszédpanel a következő három szakaszra van felosztva:

- A fő szakasz felsorolja azokat a regisztrációkat, amelyekre az aktuális dolgozó a kiválasztott dátumon tett. Megjeleníti az aktuális nap regisztrációit, és olyan dátumválasztót biztosít, amely lehetővé teszi a dolgozó egyéb napok megjelenítését.
- A **Legutóbbi számított napi egyenleg** szakasz a dolgozó fizetett időre, fizetett túlórára, távollétre és fizetett távollétre vonatkozó aktuális egyenlegét mutatja. Ezek az értékek a jóváhagyási folyamat során kiszámított regisztrációkon alapulnak.
- Az **Egyenlegek** szakasz áttekintést nyújt a kiválasztott regisztrációs kategóriák (például szabadság, normál idő és túlóra) egy adott időszakon belüli egyenlegeiről. Ezek az egyenlegek azon alapulnak, hogy hogyan vannak beállítva a **statisztikai egyenlegek a Munka és jelenlét modulban**. További tájékoztatás a beállításról: [Szabadságegyenlegek megjelenítése a termelési emelet végrehajtási felületén](production-floor-execution-payroll-stats.md).

A rendszergazdák úgy **adhatják** hozzá ezt a funkciót a felülethez, hogy minden megfelelő laphoz egy eszköztáron elhelyezik a [Saját nap gombot, amint azt a Termelési üzem végrehajtási felületének tervezése című témakör ismerteti](production-floor-execution-tabs.md).

## <a name="working-in-teams"></a>Csapatokban való munka

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]
<!-- KFM: preview until 10.0.27 GA -->

Ha ugyanannak a termelési feladatnak több dolgozója van, akkor csapatokat lehet csapatokat formba rendelni. A csoport egy dolgozót jelölhet meg pilotként. A többi dolgozó automatikusan ennek az pilotnak az asszisztense lesz. Az eredményül kapott csapatnál csak az első csapatnak kell regisztrálnia a feladat állapotát. Az időrekordok minden csapattagra érvényesek.

### <a name="prerequisites"></a>Előfeltételek

A csapatok alkalmazáshoz a **rendszergazdáknak engedélyezniük kell az Asszisztens** **műveletet** az elsődleges eszköztáron a termelési emelet végrehajtási felületÉnek Minden feladat lapján. Az utasításokat lásd [a Termelés - emelet végrehajtási felületének tervezése.](production-floor-execution-tabs.md)

### <a name="form-a-new-team-that-has-a-pilot-and-an-assistant"></a>Új csapat létrehozása, amely rendelkezik vezetővel és asszisztenssel

Ha egy dolgozó asszisztensként **regisztrál, válassza az Asszisztens** gombra a Minden feladat **lapon**. Ezután a Megjelenő Alkalmazott kiválasztása **párbeszédpanelen** a dolgozó kiválaszthat egy pilot listában azokat a dolgozókat, akik aktívan dolgoznak egy adott munkakörben. Miután a dolgozó megerősíti a választást, a kiválasztott dolgozó asszisztense lesz, aki az új csapat jelölője lesz.

### <a name="assign-a-new-pilot-to-an-existing-team"></a>Új pilot hozzárendelése meglévő csapathoz

Ha egy csapat új alkalmazottat szeretne kijelölni, akkor az aktuális pilotnak a csoportban egy másik dolgozót kell kijelölnie új pilotként. Új pilot elnevezésére az aktuális vezető a **Minden feladat lapon az Asszisztens** **lehetőséget** választja. Ezután a megjelenő **Változásválasztó párbeszédpanelen** az pilot kiválaszthat egy új pilotot a már a csapatban dolgozó dolgozók listájáról. Miután a jelenlegi pilot megerősíti a választásukat, teljesen el lesz dobva a csapatból. Azonban ha szükséges, újra egyesedhet a csapattal.

### <a name="assistant-clocks-out"></a>Asszisztens - érkezéskori érkezéskori idő

Amikor egy asszisztensként dolgozó elhagyja a csapatát, akkor elhagyják a csapatát. Ha a állandó **csapatok** **·** *és* az Újraindítás érkezéskori idő beállítása Igen, egy olyan dolgozó, aki a következő érkezéskori érkezéskor csatlakozik a csapathoz, automatikusan újra csatlakozik a csapathoz. Ezek a lehetőségek a Jelenléti és jelenléti **paraméterek lap** Általános lapján találhatóak **.**

## <a name="opening-instructions"></a>Utasítások megnyitása

A dolgozók megnyithatnak egy, a feladathoz csatolt dokumentumot, ha kijelölik az **Utasítások** lehetőséget. Az **Utasítások** gomb csak akkor érhető el, ha az alapadatokban a feladathoz társítottak dokumentumot. Például egy, a Supply Chain Management **Kiadott termékek** lapján a termékhez csatolt dokumentum elérhető lesz a dolgozók számára, hogy azok megnyissák azt az üzemi végrehajtási felületen.

## <a name="opening-mixed-reality-guides-for-hololens"></a>Útmutatók a vegyes valósághoz a HoloLens termékkel

A [Dynamics 365 Guides](https://dynamics.microsoft.com/mixed-reality/guides/) segíti a dolgozók cselekvő helyzetbe hozásár a vegyes valóságot alkalmazó gyakorlati tanulási lehetőségek biztosításával. Szabványosított folyamatok adhatók meg, olyan részletes utasításokkal, amelyek a dolgozókat a szükséges eszközökhöz és alkatrészekhez irányítják, és bemutatják, hogyan kell ezeket az eszközöket valódi munkakörülmények között használni. Itt következik egy áttekintés a folyamatról.

1. Mindig, amikor egy dolgozó megnyit egy feladatlistát az üzemi végrehajtási felületen, a felhasználói felület megkeresi az adott feladathoz tartozó útmutatókat.
1. A dolgozó az útmutatók listájának megtekintéséhez kiválasztja az **Útmutatók** lehetőséget.
1. A dolgozó kiválasztja a lista megfelelő útmutatóját.
1. Az üzemi végrehajtási felület megjeleníti a kiválasztott útmutató QR-kódját.
1. A dolgozó felveszi a HoloLens eszközt, majd a QR-kódra pillant az útmutató megkezdéséhez.
1. A dolgozó az útmutatón keresztül tanulja meg a feladat végrehajtását.

A HoloLens alapú útmutatók létrehozásával, hozzárendelésével és használatával kapcsolatos további információkért lásd: [Vegyes valóságot alkalmazó útmutatók biztosítása a termelésben dolgozók számára](instruction-guides-in-production-overview.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
