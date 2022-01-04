---
title: A termelési üzem végrehajtási felületének dolgozók általi használata
description: Ez a témakör azt mutatja be, hogyan kell használni a termelési üzem végrehajtási felületét egy dolgozó szemszögéből.
author: johanhoffmann
ms.date: 10/05/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: JmgProductionFloorExecution
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-10-05
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: e872600222ad23bf3de62c0f2d6cda74942d5b55
ms.sourcegitcommit: 008779c530798f563fe216810d34b2d56f2c8d3c
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/14/2021
ms.locfileid: "7920648"
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

## <a name="reporting-scrap"></a>Selejt jelentése

Amikor egy dolgozó befejezte vagy részben befejezte a feladatot, akkor az **Aktív feladatok** lapon kiválaszthatna a **Selejtek jelentése** lehetőséget, hogy jelentse a legyártott leselejtezett mennyiséget. Ezután a **Selejtek jelentése** párbeszédpanelen a dolgozó beírja a leselejtezett mennyiséget a numerikus billentyűzet segítségével. A dolgozó az okot (*Semmilyen*, *Gép*, *Kezelő* vagy *Anyag*) is kiválasztja.

![A Selejtek jelentése párbeszédpanel.](media/pfei-report-scrap-dialog.png "A Selejtek jelentése párbeszédpanel")

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
