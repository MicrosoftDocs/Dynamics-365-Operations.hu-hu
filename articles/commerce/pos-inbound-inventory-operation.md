---
title: Bejövő készletműveletek a pénztárban
description: Ez a témakör a pénztár (POS) bejövő készletműveletének képességeit írja le.
author: hhaines
manager: annbe
ms.date: 07/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: hhaines
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: aba4f2d7932ebc3a0129f04c60c8b6358da68c64
ms.sourcegitcommit: 0aabe4157f82d8c59dd2d285ab0b33f3c8ec5bbc
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/28/2020
ms.locfileid: "3627538"
---
# <a name="inbound-inventory-operation-in-pos"></a>Bejövő készletműveletek a pénztárban

[!include [banner](includes/banner.md)]

A Microsoft Dynamics 365 Commerce 10.0.10 és a későbbi verzióiban a bejövő és kimenő műveletek a pénztárnál (POS) lecserélik a kitárolási és bevételezési műveleteket.

> [!NOTE]
> A Commerce 10.0.10 és a későbbi verziókban a POS-alkalmazás olyan új szolgáltatásai, amelyek a beszerzési rendelések és átmozgatási rendelések fogadásával kapcsolatosak a **Bejövő műveletek** művelethez lesznek hozzáadva. Ha jelenleg a kitárolási és bevételezési műveletet használja a pénztárban, javasoljuk, hogy dolgozzon ki egy stratégiát arra, hogy ebből a műveletből a bejövő és kimenő műveletekbe költözzön. Annak ellenére, hogy a kitárolási és bevételezési művelet nem lesz eltávolítva a termékből, a 10.0.9 verzió után funkcionális és teljesítményi szempontból nem érkeznek hozzá újítások.

## <a name="prerequisite-configure-an-asynchronous-document-framework"></a>Előfeltétel: Az aszinkron dokumentumkezelési keretrendszer konfigurálása

A bejövő művelet javítja a teljesítményt, így biztosítható, hogy azok a felhasználók, akik nagy mennyiségű bevételezést adnak fel számos üzlet vagy vállalat között, illetve nagy készletdokumentumokkal dolgoznak úgy dolgozhassák fel ezeket a dokumentumokat a Commerce Headquarters felületen, hogy ne ütközzenek időtúllépésekbe vagy hibákba. Ezek a fejlesztések egy aszinkron dokumentum keretrendszer használatát igénylik.

Az aszinkron dokumentumok keretrendszerének használatakor véglegesítheti a bejövő dokumentumok változásait a pénztár és a Commerce Headquarters között, majd áthelyezheti azokat más feladatokra, miközben a feldolgozás a Commerce Headquarters modulban a háttérben történik. A dokumentum állapota a **Bejövő műveletek** dokumentum listaoldalon ellenőrizhető a pénztárban, hogy meggyőződhessen a sikeres feladásról. APénztár alkalmazásban a bejövő művelet aktív dokumentum-listája használható a Commerce Headquarters rendszerbe nem feladott dokumentumok megjelenítésére is. Ha egy dokumentum feladása nem sikerül, a POS-felhasználók korrigálni tudják, majd újra megpróbálkoznak a Commerce Headquarters rendszerben történő feldolgozással.

> [!IMPORTANT]
> Az aszinkron dokumentum keretrendszert azelőtt kell konfigurálni, mielőtt a vállalat megpróbálja használni a bejövő műveletet a pénztárban.

Az aszinkron dokumentum-keretrendszer konfigurálásához hajtsa végre a következő eljárásokat.

### <a name="create-and-configure-a-number-sequence"></a>Hozzon létre, és konfiguráljon egy számsorozatot

1. Válassza a **Szervezeti adminisztráció \> Számsorozatok \> Számsorozatok** lehetőséget.
2. A **Számsorozatok** lapon hozzon létre egy új számsorozatot.
3. A **Számsorozat kódja** és a **Név** mezőben adja meg a felhasználó által definiált értékeket.
4. Válassza a **Referenciák** gyorslap **Hozzáadás** elemét.
5. A **Terült** rész mezőjében válassza a **Commerce paraméterek** gombot.
4. A **Referencia** mezőben válassza ki a **Kiskereskedelmi dokumentum műveleti azonosítója** lehetőséget.
5. Az **Általános** gyorslap **Beállítások** szakaszában állítsa a **Folyamatos** elemet **Nem** értékre, így biztosíthatja, hogy ne legyenek teljesítménnyel kapcsolatos problémák.

### <a name="create-and-schedule-two-batch-jobs-for-the-document-processing-and-monitoring-tasks"></a>Hozzon létre két kötegelt feladatot a dokumentumok feldolgozási és felügyeleti feladatai számára

> [!NOTE]
> A Kiskereskedelem 10.0.13 és a későbbi verzióiban nem kell ezeket a kötegelt feladatokat a kötegelt feladat keretrendszerén belül konfigurálni. A kötegelt feldolgozások a **Kiskereskedelem és kereskedelem > Kiskereskedelem és kereskedelem IT** menüjéből is konfigurálhatók. A **Kiskereskedelem dokumentumműködés-figyelő** és **Kiskereskedelem dokumentumműködés-feldolgozás** menükkel konfigurálhatja a kötegelt feladatokat.

A létrehozott kötegelt feladatok felhasználhatók a meghiúsult vagy időtúllépésben érintett dokumentumok feldolgozására. Akkor is használhatók, ha a pénztárból eldolgozás alatt álló aktív készletdokumentumok száma meghaladja a rendszer által konfigurált értéket.

1. Ugorjon a **Rendszerfelügyelet \> Lekérdezések \> Kötegelt feladatok** pontra.
2. A **Kötegelt feladat** lapon hozzon létre két kötegelt feladatot:

    - Egy feladatot konfiguráljon a **RetailDocumentOperationMonitorBatch** osztály futtatására.
    - A másik feladatot konfigurálja a **RetailDocumentOperationProcessingBatch** osztály futtatására.

2. Az új kötegelt feladatok ismétlődő futtatását ütemezze. Az ütemezést például állítsa be úgy, hogy a feladatok öt percenként fussanak.

## <a name="prerequisite-add-inbound-operation-to-the-pos-screen-layout"></a>Előfeltétel: Bejövő művelet hozzáadása a pénztár képernyő-elrendezéséhez

Mielőtt a szervezet használhatja a bejövő műveletek funkciókat, konfigurálnia kell a **Bejövő művelet** pénztárműveletet agy vagy több [Pénztári képernyőelrendezésen](https://docs.microsoft.com/dynamics365/unified-operations/retail/pos-screen-layouts). Az új művelet termelési környezetben történő üzembe helyezése előtt mindenképpen alaposan tesztelje, és tanítsa meg a felhasználókat a használatára.

## <a name="overview"></a>Áttekintés

A bejövő művelet révén a pénztári felhasználók a következő feladatokat hajtják végre:

- A készlet bevételezése az üzlet készletébe a visszaigazolt beszerzési rendelési dokumentumok vagy a szállított átmozgatási rendelések dokumentumaiból.
- A korábbi készlettranzakciók adatainak megtekintése a dokumentum teljes bevételezését követő hét napos időszakig.
- Új bejövő átmozgatási rendelési kérelmek létrehozása.

Amikor a pénztári alkalmazásból indul el a bejövő művelet, megjelenik a listaoldal nézete. Ez a nézet olyan nyitott beszerzési rendelés és átmozgatási rendelés dokumentumokat mutat be, amelyek ütemezve vannak bevételezésre az aktuális üzlet által. Egy adott dokumentum megkereséséhez és kiválasztásához a felhasználók görgethetik a listát, vagy használhatják a keresési funkciót.

A bejövő készlet dokumentumlista három lapból áll:

- **Aktív** – ez a lap olyan dokumentumokat jelenít meg, amelyek teljes egészében vagy részben nyitottal, és amelyek olyan sorokat vagy sorokban olyan mennyiségeket tartalmaznak, amelyeket még bevételezni kell.
- **Vázlat** – Ezen a lapon láthatók a felhasználó üzlete által létrehozott bejövő átmozgatásirendelés-kérelmek. A dokumentumok azonban csak helyben lettek mentve. A Commerce központba még nem küldték be feldolgozásra.
- **Kész** – Ez a lap felsorolja azokat a beszerzési rendelési átmozgatási rendelési dokumentumokat, amelyeket az üzlet teljesen bevételezett a legutóbbi hét napban. Ez a lap csak tájékoztatásra szolgál. A dokumentumokkal kapcsolatos összes adat írásvédett az üzlethez.

Amikor bármelyik lapon megtekinti a dokumentumokat, az **Állapot** mező segít megérteni azt a fázist, ahol a dokumentum tart.

- **Vázlat** – az átmozgatási rendelés dokumentum csak helyileg lett mentve az üzlet csatorna-adatbázisában. Az átmozgatási rendelési kérelemmel kapcsolatos adatokat még nem küldték el a Commerce központba.
- **Kérelmezve** – A beszerzési rendelés vagy átmozgatási rendelés a Commerce központ alkalmazásban lett létrehozva, és teljesen nyitva van. Még nem történt meg a bizonylattal szemben nyugta feldolgozása. A beszerzési rendelési dokumentum típus dokumentumaihoz a bevételezés bármikor elindítható, amíg az állapot **Kérelmezve**.
- **Részben szállított** – Az átmozgatási rendelés dokumentumának egy vagy több sora vagy részlege somennyisége fel lett adva szállítottként a kimenő raktárba. A leszállított sorok készen állnak a bejövő műveleten keresztüli fogadásra.
- **Teljesem kiszállított** – Az átmozgatási rendelésnek minden sora és teljes sormennyisége a kimenő raktár által szállítottként feladva. A teljes dokumentum készen áll a bejövő műveleten keresztüli fogadásra.
- **Részben bevételezve** – A beszerzési rendelésen vagy az átmozgatási rendelésen szereplő sorok vagy sormennyiségek bevételezve lettek az üzlet által, néhány sor azonban nyitva marad.
- **Teljesen bevételezve**– A beszerzési rendelésen vagy átmozgatási rendelésen szereplő összes sor és mennyiség teljes mértékben bevételezve lett. A dokumentumok csak a **Kész** lapon érhetők el, és csak olvashatók az üzlet felhasználói számára.
- **Folyamatban** – Ez az állapot tájékoztatja az eszköz felhasználóit, hogy a dokumentummal egy másik felhasználó aktívan dolgozik.
- **Szüneteltetve** – Ez az állapot azt követően jelenik meg, hogy a **Szüneteltetés kérelmezve** ki van választva fogadási folyamat ideiglenes leállításához.
- **Feldolgozás a központban**– Ezt a dokumentumot a Commerce Headquarters modulból átadták a pénztárba, de még nem lett sikeresen feladva a Commerce Headquarters modulba.. A dokumentum az aszinkron dokumentumfeladási folyamaton megy keresztül. Miután sikeresen feladta a dokumentumot a Commerce Headquarters modulba állapota a **Teljesen bevételezve** vagy **Részben bevételezve** kell legyen.
- **A feldolgozás nem sikerült** – A dokumentumot a Commerce Headquarters modulba adták fel, és elutasították. A **Részletek** ablaktábla a feladási hiba okát jeleníti meg. Az adathibák javítása érdekében szerkeszteni kell a dokumentumot, majd újra el kell küldeni a Commerce Headquarters modulba feldolgozásra.

Amikor kiválaszt egy bizonylatsort a listából, megjelenik egy **Részletek** ablaktábla. Ez a ablaktábla a dokumentum további adatait jeleníti meg, mint például a szállítási és a dátumadatokat. Egy folyamatjelző sáv azt mutatja, hogy hány cikket kell még feldolgozni. Ha a dokumentumot nem sikerült feldolgozni a Commerce Headquarters modulban, a **Részletek** ablaktábla megjeleníti a hibához kapcsolódó hibaüzeneteket.

A dokumentumlista lapnézetében kiválaszthatja a **Rendelés részletei** elemet az alkalmazássávon, és megtekintheti a dokumentum részletes adatait. A bevételezés feldolgozását is aktiválhatja a jogosult bizonylatsorok esetében.

A dokumentum lista oldal nézetben új bejövő átmozgatási rendelési kérelmet is létrehozhat egy üzlethez. A dokumentumok **Vázlat** állapotban jelennek meg, és a Commerce Headquarters részére feldolgozásra történő elküldésig módosíthatók és törölhetők. Miután ezeket beküldték a Commerce Headquarters rendszerbe, az átmozgatási rendelési sorok már nem módosíthatók a pénztári alkalmazásból.

## <a name="receiving-process"></a>Bevételezési folyamat

Miután kiválasztott egy beszerzési rendelési vagy átmozgatási rendelési dokumentumot az **Aktív** lapon, a bevételezési folyamat megkezdéséhez kiválaszthatja a **Rendelés részletei** elemet.

Alapértelmezés szerint a **Bevételezés most** nézet jelenik meg. Ez a nézet a vonalkódok beolvasására optimalizált. Felhasználható a beolvasott cikkek listájának összeállítására, hogy ezek a cikkek bevételezhetők legyenek. A bevételezési folyamat megkezdéséhez el lehet indítani a vonalkódok beolvasását.

A cikkvonalkódok beolvasása során a **Bevételezés most** nézetben az alkalmazás ellenőrzi a cikkeket a kiválasztott beszerzési vagy átmozgatási rendelési dokumentummal szemben, annak biztosításához, hogy minden beolvasott elem megfeleljen egy érvényes cikknek a dokumentumban. A **Bevételezés most** nézetben minden egyes vonalkód-beolvasásnál az van feltételezve, hogy egy egység van bevételezve, kivéve, ha a vonalkódba van ágyazva a mennyiség. Ebben a nézetben a vonalkódok többszöri beolvasásával a nyugta összes cikkét és mennyiségét tartalmazó listát készíthet.

### <a name="example-scenario"></a>Példaforgatókönyv

A felhasználó olyan beszerzési rendelést kap, amely 10 egységet tartalmaz az 5657900266-os vonalkódból. A felhasználó tízszer beolvashatja a vonalkódot, hogy a **Bevételezés most** mezőt beolvasásonként egy egységgel frissítse. Amikor a felhasználó befejezte a beolvasásokat a **Bevételezés most** mező a cikk sorához azt jelzi, hogy 10 darab érkezett.

Arra is van lehetőség, hogy olyan esetben, amikor a cikkmennyiség nagy, a felhasználó manuálisan is megadhatja a mennyiséget, ahelyett, hogy a vonalkódot beolvassa mindegyik beérkezett elemhez. Ebben az esetben a felhasználó egy alkalommal beolvassa a vonalkódot, hogy hozzáadja a tételt a **Bevételezés most** listához. Ezt követően a felhasználó kiválaszthatja a társított sort a **Bevételezés most** nézetben, majd a lap jobb oldalán megjelenő **Részletek** ablaktáblában frissítheti a cikk **Bevételezési mennyiség** mezőjét.

Ugyan a **Bevételezés most** nézet a vonalkódok szkenneléséhez van optimalizálva, a felhasználók az alkalmazássávon kiválaszthatják a **Termék bevételezése** lehetőséget is, majd a cikk azonosítóját vagy a vonalkód adatait egy párbeszédpanelen megadhatják. Miután a megadott elem ellenőrizve lett, a program felkéri a felhasználót, hogy adja meg a bevételezés mennyiségét.

A **Bevételezés most** nézet a felhasználók számára egy fókuszált módot biztosít arra, hogy lássák, milyen termékeket bevételeznek. Másik lehetőségként hogy a **Teljes rendelési lista** nézet használható. Ez a nézet a kiválasztott beszerzési vagy átmozgatási rendelési dokumentumhoz tartozó bizonylatsorok teljes listáját tartalmazza. A felhasználók manuálisan kijelölhetnek sorokat a listán, majd a **Részletek** ablaktáblában frissítheti a kiválasztott sor **Bevételezési mennyiség** mezőjét. A **Teljes rendelési lista** nézetben a felhasználók be tudják olvasni a vonalkódokat, vagy a **Termék bevételezése** funkcióval beírhatják a cikk azonosítóját vagy a vonalkódot, valamint a bevételezett mennyiség adatait, anélkül, hogy előbb ki kellene jelölniük a megfelelő cikksort a listában.

### <a name="over-receiving-validations"></a>Túlzott bevételezéssel kapcsolatos ellenőrzések

Az ellenőrzések a bizonylatsor bevételezési folyamata során történnek meg. Ezek a túlszállításra vonatkozó ellenőrzéseket is tartalmazzák. Ha egy felhasználó több készletet próbál meg bevételezni, mint amennyit megrendelt egy beszerzési rendelésen, de a túlszállítás nincs beállítva, vagy a bevételezett mennyiség meghaladja a beszerzési rendelés sorához beállított túlszállítási tűréshatárt, akkor a felhasználó hibaüzenetet kap, és a felesleges mennyiséget nem lehet fogadni.

Átmozgatási rendeléshez tartozó dokumentumok esetében nem engedélyezett a túlzott bevételezés. A felhasználók mindig hibát kapnak, ha az átmozgatási rendelés sorában szereplőnél nagyobb mennyiséget próbálnak bevételezni.

### <a name="receiving-location-controlled-items"></a>Helyvezérlet cikkek bevételezése

Ha a bevételezett cikkek helyvezéreltek, a felhasználók kiválaszthatják, hogy melyik helyen szeretnének bevételezni a cikkeket a bevételezési folyamat során. Javasoljuk, hogy a folyamat hatékonyabbá tételéhez konfiguráljon az üzlet raktárához egy alapértelmezett bevételezési helyet. Ha van alapértelmezett hely beállítva, akkor a felhasználó igény szerint felülbírálhatja a kiválasztott sorokban a bevételezési helyet.

A művelet figyelembe veszi az **Üres bevételezés engedélyezett** konfigurációját a **Hely** tárolási dimenziójánál, és nem követeli meg, hogy a helydimenziót adjon meg, ha üres nyugta van konfigurálva. Ha egy tétel esetében nem engedélyezettek az üres bevételezési helyek, a pénztár alkalmazás hibát jelez, és megköveteli hely megadását a bevételezés feladása.

### <a name="receive-all"></a>Összes bevételezése

Igény esetén kiválaszthatja az **Összes bevételezést** lehetőséget az alkalmazássávon hogy az összes dokumentumsorban gyorsan frissíthesse a **Bevételezés most** mennyiséget az összes dokumentumsorhoz arra a maximális értékre, amely elérhető bevételezésre azokhoz a sorokhoz.

### <a name="cancel-receiving"></a>Bevételezés megszakítása

Csak akkor használja az alkalmazássáv **Bevételezés visszavonása** funkcióját, ha ki szeretne lépni a dokumentumból, és nem szeretné menteni a változtatásokat. Például eredetileg nem megfelelő dokumentumot választott ki, és nem szeretné, hogy a korábbi bevételezési adatok bármelyike mentve legyen.

### <a name="pause-receiving"></a>Bevételezés szüneteltetése

Ha készletet bevételez, akkor a **Bevételezés szüneteltetése** funkciót használhatja, ha szünetet szeretne tartani a bevételezési folyamatban. Előfordulhat például, hogy egy másik műveletet szeretne végrehajtani a pénztárból, például fel szeretne hívni egy vásárlói eladást egy nyugta feladását szeretné késleltetni.

Amikor kiválasztja a **Bevételezés szüneteltetése**beállítást, a dokumentum állapota **Szüneteltetve** értékre. Ennélfogva a felhasználók tudni fogják, hogy a dokumentumban vannak megadva értékek, de a dokumentum még nem lett véglegesítve. Ha készen áll a bevételezési folyamat folytatására, válassza ki a szüneteltetett dokumentumot, majd válassza ki a **Rendelés részletei** elemet, A korábban mentett **Bevételezés most** mennyiségek megmaradnak, és a **Teljes rendelési lista** nézetből jeleníthetők meg.

### <a name="review"></a>Ellenőrzés

A Commerce központba (HQ) beérkezne, a végleges kötelezettségvállalás előtt az ellenőrzési funkció segítségével ellenőrizheti a bejövő dokumentumokat. Az ellenőrzéskor megjelenik egy figyelmeztetés minden olyan hiányzó vagy hibás adatról, amely feldolgozási hibát okozhat, és a bevételezési kérelem elküldése előtt lehetősége van a problémák megoldására. Ha engedélyezni szeretné az **Ellenőrzés** funkciót az alkalmazás eszköztárában, akkor engedélyezze az **Érvényesítés engedélyezése a pénztár bejövő és kimenő készlettranzakciók számára** funkciót a Commerce központ (HQ) **Funkciókezelési** munkaterületen.

Az **Ellenőrzés** funkció a következő hibákat ellenőrzi a bejövő dokumentumoknál:

- **Túlzott bevételezés** – a most bevételezett mennyiség nagyobb a megrendelt mennyiségnél. A hiba súlyosságát a Commerce központ (HQ) túlszállítási konfigurációja határozza meg.
- **Kevesebb bevételezés** – a most bevételezett mennyiség kevesebb a megrendelt mennyiségnél. A hiba súlyosságát a Commerce központ (HQ) kevesebb szállítás konfigurációja határozza meg.
- **Sorozatszám** – a sorozatszám nincs megadva vagy nincs érvényesítve egy szerializált cikknél, amelyhez regisztrálni kell a sorozatszámot a készletben.
- **A hely nincs beállítva** – a hely nincs megadva olyan helyvezérelt cikknél, ahol az üres hely nem engedélyezett.
- **Törölt sorok** – a rendelés sorait a Commerce központ (HQ) olyan felhasználója törölte, aki ismertelen a pénztár alkalmazásban.

Állítsa a **Commerce paraméterek** > **Készlet** > **Üzletkészlet** lehetőségben lévő **Automatikus ellenőrzés engedélyezése** elemet **Igen** értékre ahhoz, hogy az ellenőrzést automatikusan elvégezzék a **Bevételezés befejezése** elem kiválasztásakor.

### <a name="finish-receiving"></a>Bevételezés befejezése

Ha befejezte az összes **Bevételezés most** mennyiség megadását a termékekhez, akkor be kell jelölnie a **Bevételezés befejezése** elemet az alkalmazássávon a nyugta feldolgozásához.

Amikor a felhasználók egy beszerzési rendelés bevételezését elvégezték, a program kéri, hogy írjon be egy értéket a **Nyugtaszám** mezőbe, ha ez a funkció be van állítva. Ez az érték általában megegyezik a szállító szállítólevelének azonosítójával. A **Nyugtaszám** adatainak tárolása a Commerce Headquarters Termékbevételezési naplójában történik. Az átmozgatási rendelések bevételezés során nem jönnek létre Nyugtaszámok.

Az aszinkron dokumentum-feldolgozás használatakor a program az aszinkron dokumentum-keretrendszeren keresztül küldi be a bevételezést. A dokumentum feladásához szükséges idő a dokumentum méretétől (a sorok száma) és a kiszolgálón tapasztalható általános feldolgozási forgalomtól függ. Ez a folyamat általában másodpercek alatt megtörténik. Ha a dokumentum feladása sikertelen, akkor a rendszer a **Bejövő művelet** dokumentumlistán, az Aktív lapon keresztül értesíti a felhasználót, ahol a dokumentum állapota **Feldolgozás sikertelen** értékre módosul. A felhasználó ezt követően kiválaszthatja a hibás dokumentumot a POS-ban, és megtekintheti a hibaüzeneteket, valamint a hiba okát a **Részletek** ablaktáblán. Egy hibás dokumentum nem feladott marad, és szükséges, hogy a felhasználó visszatérjen a dokumentumsorokhoz a pénztár **Rendelés részletei** lehetőségének kiválasztásával. A felhasználónak ezt követően a hibák alapján módosítania kell a dokumentumot a javításokkal. A dokumentum javítása után a felhasználó megpróbálhatja újra feldolgozni azt úgy, az alkalmazássáv **Teljesírés befejezése** elemét választja.

## <a name="create-an-inbound-transfer-order"></a>Bejövő átmozgatási rendelés létrehozása

A pénztárból a felhasználók új átmozgatási rendelési dokumentumokat hozhatnak létre. A folyamat megkezdéséhez válassza az alkalmazássáv **Új** elemét, miközben a fő **Bejövő művelet** dokumentumlistán tartózkodik. Ezt követően a program felkéri, hogy válasszon egy raktárat vagy üzletet az **Átvitel forráshelyének** ahol a készlet lesz az üzlete helyén. Az értékek az üzlet teljesítési csoportjának konfigurációjában meghatározott lehetőségekre korlátozódnak. A bejövő átmozgatási kérelmekben a jelenlegi üzlet mindig az átmozgatási rendelés **Átvitel célhely** raktára. Ez az érték nem módosítható.

A szükséges értékeket a **Szállítási dátum** , **Bevételezés dátuma** és a **Szállítási mód** mezőkben adhatja meg igény szerint. Hozzáadhat olyan megjegyzést is, amely az átmozgatási rendelés fejlécével együtt lesz tárolva mellékletként a dokumentumban a Commerce Headquarters modulban.

Miután létrehozta a fejléc adatait, hozzáadhat termékeket az átmozgatási rendeléshez. A cikkek és a kívánt mennyiségek hozzáadási folyamatának megkezdéséhez vagy válassza a **Termék hozzáadása** lehetőséget. A **Részletek** ablaktáblán egy sorspecifikus megjegyzést is hozzáadhat a naplósorokhoz. Ezek a megjegyzések sormellékletként lesznek tárolva.

A bejövő átmozgatási rendelés sorainak megadása után a **Mentés** parancsot kell kiválasztania, hogy helyben mentse a dokumentum módosításait, vagy a **Kérelem benyújtása** lehetőséget a rendelés részleteinek a Commerce Headquarters részére történő elküldéséhez további feldolgozás céljából. Ha a **Mentés** lehetőséget választja, a piszkozatot a csatorna-adatbázisban tárolja a program, és a kimenő raktár nem futtathatja a dokumentumot mindaddig, amíg az nincs sikeresen feldolgozva a **Kérelem beküldése** folyamattal. Csak akkor válassz a **Mentés** lehetőséget, ha nem szeretné véglegesíteni a kérést a Commerce Headquarters modul felé feldolgozásra.

Ha a dokumentum helyben lett mentve, az a **Vázlatok** helyen található a **Bejövő művelet** dokumentumlistában. Amikor egy dokumentum **Vázlat** állapotú, szerkesztéshez válassza a **Szerkesztés** parancsot. A sorokat igény szerint frissítheti, hozzáadhatja vagy törölheti. A **Piszkozatok** lapon a **Törlés** gombra kattintva a teljes dokumentumot is törölheti, amíg az **Vázlat** állapotban van.

Miután sikeresen elküldte a vázlatdokumentumot a Commerce Headquarters modulba, az az **Aktív** lapon jelenik meg, és állapota **Kérelmezve**. Ezen a ponton a bejövő üzlet vagy raktár felhasználói már nem módosíthatják a kért bejövő átmozgatási rendelési dokumentumot. Csak a kimenő raktár felhasználói módosíthatják a dokumentumot a Pénztár alkalmazás **Kimenő művelet** elemének kiválasztásával. A szerkesztési zárolás biztosítja, hogy nem fordulnak elő ütközések, mert a bejövő kérelmező éppen akkor módosítja az átmozgatási rendelést, amikor a kimenő szállító aktívan kitárolja és szállítja a rendelést. Ha az átmozgatási rendelés elküldése után a bejövő üzletből vagy raktárból változtatások szükségesek, a kimenő szállítmányozóval kell felvenni a kapcsolatot, és kérni tőle a változtatásokat.

Miután a dokumentum **Kérelmezett** állapotban van, az **Aktív** lapon látható. Azonban a bejövő üzlet vagy raktár nem bevételezheti. Miután a kimenő raktár már szállított egy vagy több átmozgatási rendelést, a bejövő üzlet vagy raktár feladhatja a pénztárból a nyugtákat. Miután a kimenő oldal feldolgozta az átmozgatási rendelés dokumentumait állapotuk **Kérelmezett** állapotból **Szállítva** vagy **Részben szállítva** értékre módosul. Miután a dokumentumok **Kiszállított** vagy **Részben kiszállított** állapotban vannak, a bejövő üzlet vagy a raktár a bejövő művelet bevételezési folyamata alapján is feladhatja a bevételezéseket azokkal szemben.

## <a name="related-topics"></a>Kapcsolódó témakörök

[Kimenő készletműveletek a pénztárban](pos-outbound-inventory-operation.md)
