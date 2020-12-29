---
title: Visszavezetéses költségelszámolás
description: Ez a témakör bemutatja a lean manufacturing során használt visszavezetéses költségelszámolást.
author: cvocph
manager: tfehr
ms.date: 04/10/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LeanCosting, LeanCostingTimeBucket
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 272063
ms.assetid: 62a2a7da-ff79-49bf-a6e8-29460ba5252f
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 0c8ef901afacd4ae191f2d01114bbf4bac38b9cd
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4429723"
---
# <a name="backflush-costing"></a>Visszavezetéses költségelszámolás

[!include [banner](../includes/banner.md)]

Ez a témakör bemutatja a lean manufacturing során használt visszavezetéses költségelszámolást. 

A lean manufacturing során használt költségszámítás lehetővé teszi, hogy a termelési folyamat a visszavezetéses költségelszámolás néven ismert költséghalmozásos módszert használja. A visszavezetéses költségszámítási módszer esetén a felhasznált közvetlen szükséges anyagok felhalmozódnak a termelési folyamat befejezetlen termelés költségszámláján. Ennek során elszámolóáras készletmodellcsoport használatos. A termelési folyamatból érkező termékeket a folyamatban lévő munkából elszámolóáron vonják le. A visszavezetéses költségelszámolás és az elszámolóár közötti fő különbség, hogy a visszavezetéses költségelszámolás esetében az eltéréseket nem kanbanonként vagy késztermékekként számítják ki. Ehelyett a különbözeteket egy időszakon belül termelési folyamatonként számítják ki. Ez a módszer valódi lean koncepciót vezet be az anyagfelhasználás bejelentése tekintetében. Az erre a célra kijelölt kitárolt mennyiségeket nem jeleni jelentett kanban- vagy a termelési rendeléshez. Ehelyett teljes kötegeket vagy anyagkezelési egységeket helyeznek el a termelési folyamatban. A kötegek vagy az anyagkezelési egységek üresen történő regisztrálása után a rendszer azokat felhasználtnak tekinti. Speciális felhasználás használható a [termelési folyamat konfigurációjától](../production-control/lean-manufacturing-modeling-lean-organization.md) függően. A speciális felhasználás használata előtt a szervezeteknek lehetővé kell tenniük maguk számára, hogy az anyag eltűnjön a termelési folyamat folyamatban lévő munkájában. Az időszakos visszavezetéses költségelszámolás határozza meg a befejezetlen termelés tényleges értékét az időszak végére. Ez a meghatározás a kanban anyagkezelési egységek és a kanbanfeladat állapota alapján történik. A tényleges értékek és a tényleges befejezetlen termelés értékei közötti eltérések költségcsoportonként és cikkenként könyvelve és eltérésenként megjelenítve jelennek meg.

## <a name="configuring-backflush-costing"></a>Visszavezetéses költségelszámolás konfigurálása
A költségszámítás engedélyezéséhez meg kell adnia a következő beállításokat:

-   **Hozzon létre folyamatban lévő munkával kapcsolatos számlákat a termelési csoport és a termelési folyamat számára.** A termelési folyamat befejezetlen termelés számláit a termelési csoport határozza meg. A visszavezetéses költségelszámolásos termelési folyamat az eltéréseket a befejezetlen termelés értékében bekövetkező különbségként számítja ki a visszavezetéses költségelszámolás minden termelési folyamat előtt és után történő futtatása során. Ezért javasoljuk, hogy minden termelési folyamathoz hozzon létre egy befejezetlen termelés típusú számlát.
-   **Rendeljen hozzá egy költségkategóriát az erőforráscsoporthoz.** A munkacella futásiidő-kategóriájához hozzá kell rendelnie egy költségkategóriát. Az eltérések tevékenység alapján történő meghatározásához minden munkacellaához költségkategóriát kell létrehoznia. A beállítási és a mennyiségre vonatkozó költségkategóriákat a lean manufacturing költségszámításában nem veszik figyelembe. Az erőforrás-csoportonkénti befejezetlen termelés típusú számlákat a visszavezetéses költségelszámolás figyelmen kívül hagyja. Alvállalkozói tevékenységekhez nem kell költségkategóriát megadni. Ehelyett az aktív szolgáltatáshoz rendelt költségcsoportot használja.
-   **Rendeljen hozzá költségcsoportokat.** Ahhoz, hogy lehetővé tegye a költséghozzájárulás szegmentálását a termelési folyamatban, költségcsoporttípusonként költségcsoportokat kell megadnia:
    -   **Közvetlen anyagra szánt költségcsoport** – A közvetlen anyagnak olyan költségcsoportra van szüksége, amely meghatározza a költségszámítási anyagkategóriát. Ez a költségcsoport lehetővé teszi a költségek, a befejezetlen termelés és a közvetlen anyag szerinti eltérések összesített nézetét.
    -   **Közvetlen gyártás költségcsoport** – A közvetlen gyártási költségcsoport rögzíti a termelési folyamat operatív erőforrásainak közvetlen költség-hozzájárulását. Ez a költségcsoport lehetővé teszi a költségek, a befejezetlen termelés és a közvetlen gyártási költség szerinti eltérések összesített nézetét.
    -   **Közvetettköltség-csoport** – A közvetettköltség-csoportra a termelési folyamat közvetett költségeinek kiszámítása érdekében van szükség. Ez a költségcsoport lehetővé teszi a költségek, a befejezetlen termelés és a közvetett költség szerinti eltérések összesített nézetét.
    -   **Közvetlen kiszervezési költségcsoport** – A szolgáltatási költségcsoport lehetővé teszi a hozzárendelt költség és a befejezetlen termelés összesített nézetét, és meghatározza az alvállalkozói szolgáltatások költségeltéréseit.
    -   **Késztermék-költségcsoport** – A késztermékeknek olyan költségcsoportra van szükségük, amely meghatározza a termékkategóriát a költségszámításhoz. Ez a költségcsoport lehetővé teszi a költségek, a befejezetlen termelés és a termékkategória szerinti eltérések összesített nézetét. A termékek elszámolóárát olyan költségszámítás képezi, amelynek alapja az anyagjegyzék (AJ), valamint vagy a termelési folyamat és a kanbanszabályok vagy az útvonal.

### <a name="costing-sheet"></a>Költségszámítási táblázat

A költségszámítási táblázat a vállalat költségeinek szerkezetét modellezi, és a költségcsoportok szerint épül fel a költség osztályozása érdekében. A költségszámítási táblázatnak különböző formái vannak. A benne lévő szerkezet alapján jeleníti meg a költségadatokat. A költségszámítási táblázatban határozza meg a közvetett költségek számításához használt képletet is. A számítási képlet alapja lehet mennyiség, súly, térfogat vagy érték.

-   **Határozzon meg egy költségszámítási verziót.** A költségszámítási verzióban a vállalat határozza meg a költség karbantartásának módját. A költségszámítási verzió elszámolóár-rekordokat vagy tervezett költség rekordok halmazát tartalmazhatja attól függően, hogy milyen költségszámítás-típus van társítva a költségszámítási verzióhoz. A lean manufacturing költségszámításához használt költségszámítási verziónak elszámolóáron kell alapulnia.
-   **Rendeljen egy készletmodellcsoportot a kiadott termékekhez.** A termelési folyamathoz kapcsolódó összes terméket hozzá kell rendelni egy **Elszámolóáras** készletmodellcsoportot használó készletmodellcsoporthoz, Az elszámolóárat a hely és az aktiválás dátuma szerint kell karbantartani. Alaptermékek esetén a készletmodellcsoport választható ki, ha a költség változatonként vagy alaptermékenként van karbantartva.
-   **Alapértelmezés szerint az alvállalkozói szolgáltatások nem jegyzett szolgáltatásoknak minősülnek.** Az alvállalkozói tevékenységek nem rendelkeznek készletmodellcsoporttal. Az alvállalkozói tevékenységek a megfelelő költségszámításához meg kell győződnie arról, hogy a szolgáltatási tevékenység egy olyan készletmodellcsoporthoz tartozik, amelyben a készlet házirendjének értéke **Raktározott termék = Hamis**.

Elkészült termékek esetén a termelési folyamatot alapul vevő költségszámítás előírja, hogy elszámolóárat kell karbantartani az alvállalkozói tevékenységekhez kapcsolódó szolgáltatások esetén. A szolgáltatásokhoz társított költségcsoport segítségével lehet meghatározni az alvállalkozói tevékenység költségeltéréseit.

## <a name="cost-calculation-for-lean-manufacturing"></a>Lean manufacturing költségszámítása
A termelési folyamaton kívül eső termékek esetében az anyagjegyzék-számításnak egy útvonalverzión vagy egy termelési folyamaton kell alapulnia. Az anyagjegyzék-számítás kiszámítja a termék költségeit és a termék összeállításához szükséges erőforrásokhoz és anyagokhoz kapcsolódó lebontást. A termelési folyamat befejezetlen termelés típusú számlájáról történő levonás a termék cikkenként és költségcsoportonként történő lebontásával történik.

### <a name="calculation-that-is-based-on-the-production-flow"></a>A termelési folyamaton alapuló számítás

A Dynamics 365 Supply Chain Management lean manufacturing funkciója útvonalaktól független. A termelési folyamatból megadott termékek költségszámítása magán a termelési folyamaton alapulhat. A számítás végrehajtásához előbb egy kanbanszabályt kell létrehozni, amely a terméket a termelési folyamaton kívül adja meg. Ha egy termék több ugyanazon a helyen több termelési folyamatból származhat a számítási dátumon, kiválaszthatja az anyagjegyzék-számítás termelési folyamatát. Az **Alapértelmezett termelési folyamat** lapon beállíthatja az alapértelmezett termelési folyamatot minden egyes cikkhez. Ha ugyanazon termék ugyanazon termelési folyamatánál több, a számítási napon aktív kanbanszabály létezik, a számítás a számításhoz az első aktív kanbanszabályt választja ki.

### <a name="calculation-that-is-based-on-the-route"></a>Az útvonalon alapuló számítás

Az útvonalon alapuló számítás ugyanolyan érvényes, mint a termelési folyamaton alapuló számítás. Azonban az útvonalon alapuló számítás nem használja a lean manufacturing funkciókra vonatkozó költségszámítást. Az útvonalnak erőforrásigényeket kell használnia az erőforráscsoportok számára. A rendszeres eltérések elkerülése érdekében ugyanazokat a munkacellákat vagy legalább azonos költségkategóriákat kell használnia. Kerülje a beállítási és a mennyiségre vonatkozó költségkategóriákat. Ezek nem segítenek kiszámítani a költséget részletesebb lebontásban, mint a lean manufacturing visszavezetéses költségelszámolás. Annak megállapításához, hogy melyik beállítás (a termelési folyamat vagy az útvonal) segítségével számítja ki a költséget, figyelembe kell venni a költséglebontás eredményeit. A valósághoz közelebb álló és kevesebb eltérést eredményező verzió általában a jobb választás. Lean manufacturing gyártási környezetben, ahol egy terméket egyetlen termelési folyamat és egyetlen kanbanszabály ad meg, a termelési folyamatot alapul vevő számítás valószínűleg pontosabb. Olyan termék esetében, amelyet ugyanazon a helyen lean manufacturing és termelési rendelések is biztosíthatnak, vagy amelyek több termelési folyamattal vagy több kanbanszabállyal rendelkezhetnek ugyanazon folyamaton belül, a számítás valószínűleg pontosabb, ha olyan útvonalverzióra épül, amely kifejezetten a költségszámításon, nem pedig a termelésen alapul. A termelési folyamat kiszámítását kell használni az alvállalkozásba adást érintő termékek kiszámítása esetén. A termelési rendelések alvállalkozói költségmodelljei és a lean manufacturingben történő alvállalkozásba adás két eltérő megközelítés használnak. A lean manufacturing gyártási egy új költségcsoporttípust vezet be: a **Közvetlen kiszervezés** segítségével számítja ki az alvállalkozói szolgáltatásokat.

## <a name="material-consumption"></a>Anyagfelhasználás
Ha az anyagot a készletből használják fel a folyamatban lévő munkában, az anyagköltséget a folyamatban lévő munkához a költségcsoport tényleges elszámolóáras költségével adják hozzá. Ez a művelet a következő feltételek esetén fordul elő:

-   Kanbanfeladatokat adnak fel a készletet frissítő kanban kitárolási soroknak.
-   Átviteli feladatok befejeződnek, amelyek frissítik az elérhető készletet, de a bevételezést nem (anyag készletből történő átvitele folyamatban lévő munkához).

## <a name="receiving-products-from-the-production-flow"></a>Termékek fogadása a termelési folyamatból
A termékek termelési folyamatból történő fogadása a következő feltételek fennállása esetén történik:

-   Olyan befejezett feldolgozási feladatok esetén, amelyek esetében a **Készlet frissítése bevételezéskor** beállítása **Igen**.
-   Olyan befejezett átviteli feladatok esetén, amelyek frissítik a készletet a bevételezéskor, de amelyek esetében a **Készlet frissítése kitároláskor** beállítása **Nem** (Átvitel folyamatban lévő munkából készletbe). Ez a beállítás lehetővé teszi, hogy bevételezhesse a termelési folyamaton kívül levő termékeket az anyagjegyzék és az útvonal konfigurációjától függetlenül. A folyamat kizárólag a fizikai áramlást követi. Ez a beállítás akkor különösen a melléktermékek, társtermékek vagy a termelési folyamaton kívül eső selejt bevételezése esetén hasznos, valamint a termelési folyamat folyamatban lévő munkája költségegyenlegének ennek megfelelően történő kiigazításához.

A termelési folyamatból érkező termékeket a folyamatban lévő munkából vonják le.

## <a name="products-in-wip"></a>Befejezetlen termelés termékei
A lean manufacturing befejezetlen termelés típusú modell lehetővé teszi, hogy a kanban anyagkezelési egység állapota segítségével használja azokat az anyagokat, félkész termékeket és késztermékeket, amelyek a befejezetlen termelés részei.

-   **Hozzárendelve** – A kanban tartalmazhat a folyamatban lévő munkában elszámolt felhasznált anyagot.
-   **Fogadva** – Ha a kanban egy legutóbbi tevékenységre hivatkozik, amelyben a **Készlet frissítése bevételezéskor** beállítása **Nem**, az azt jelenti, hogy egy termék vagy félkész termék olyan teljes anyagkezelési egységének felel meg, amely nincs regisztrálva a készletbe.

Ne feledje, hogy a befejezetlen termelés anyaga nem látható a készlet aktuális áttekintésében. Látható azonban a kanbanmennyiség áttekintéseiben.

## <a name="consuming-products-in-wip"></a>Befejezetlen termelés termékeinek felhasználása
A befejezetlen termelés termékeinek felhasználása akkor következik be, amikor a kanbanhoz kapcsolódó anyagkezelési egységek kiürülnek. Az üres kanban jelzés nem hoz létre aktív költségszámítási tranzakciót, de érvénybe lép a következő visszavezetéses költségelszámolás futtatása során. A kiürített kanban anyagkezelési egységek már nem az aktuális készletben lesznek könyvelve, és kiszámításuk ennek megfelelően időszakon belül felhasználtként történik.

### <a name="automatic-empty-registration"></a>Automatikus üres regisztráció

Az ütemezett vagy eseménykanbanok automatikus üres regisztrációra állíthatók be a kanbanszabályban:

-   **Anyagkezelési egységek fogadásakor** – Alapértelmezés szerint az ütemezett kanbanok esetén az anyagot a kanban utolsó feladatának befejezésekor felhasználtként deklarálja. A rögzített mennyiségű kanbanok esetében ez a lehetőség csak egyetlen tárolós kanbanok használatakor ajánlott, visszaküldi a kártyát az igény forrásához, amikor egy kanban bevételezése bekövetkezik a végcélnál.
-   **A forrásszükséglet regisztrálásakor** – Ez a beállítás csak eseménykanbanok esetében érhető el, és ez az alapértelmezett beállításuk. A befejezetlen termeléssel összefüggésben ez a befejezetlen termelés tisztán történő megőrzésére hasznos, mivel a befejezetlen termelés összetevőinek kanbanjai automatikusan ürülnek, a felhasználásuk tehát a befejezetlen termelésből történik a szülőkanban elkészülése esetén.

Következésképpen kanbankezelési egységeket lehet hozzárendelni (= folyamatban lévő), bevételezni (= teljes =) vagy üríteni. Nincs részleges ürítés. Ezért a felhasználás pontos nyilvántartása érdekében fontos a kanban termékmennyiségének korlátozása, hogy kisebbek legyenek, mint az időszakra jutó felhasználás. Az üzemirányításra nagy kötegekben átszállított, napi vagy heti igényt fedező termékeket nem szabad a befejezetlen termelésben felhasználni. Ehelyett ezeket a termékeket a készletben kell tartani.

## <a name="backflush-costing"></a>Visszavezetéses költségelszámolás
Futtasson visszavezetéses költségelszámolást a befejezetlen termelés rendszeres időközönként történő értékelése érdekében, és hozzon létre egy időszak végi állapotot, amely kiszámítja az anyag, a munka és a közvetett költségek eltéréseit. A kiszámított eltérések feladása a különbözeti számlákba történik. A visszavezetéses költségelszámolás során a jogi személy minden termelési folyamata ugyanabban a kötegelt futtatásban lesz felhasználva. Visszavezetéses költségelszámolás kötegelt feladatként történő futtatása során a feldolgozási többszálas lehet a termelési folyamat szerint. A visszavezetéses időszakot egy záró dátum határozza meg. Visszavezetéses költségelszámolási számítás futtatásakor nem adhat fel új tranzakciókat egy dátumra. Soha ne futtasson visszavezetéses költségelszámolást az adott napra vonatkozóan, mielőtt a nap alatt ténylegesen le nem jár. A visszavezetéses költségelszámolás az alábbi lépéseket hajtja végre.

1.  A termelési folyamat során felhasználatlan mennyiségek meghatározása az időszak záró dátumára vonatkozóan. A visszavezetéses költségelszámolás futtatása után megtekintheti a költségszámítás futtatásának dátumára vonatkozó felhasználatlan mennyiségeket a **Felhasználatlan mennyiségek** párbeszédpanelben.
2.  A termelési folyamat nettó realizált felhasználásának kiszámítása az időszak során.
3.  Törölje a befejezetlen termelést a realizált erőforrás-felhasználásból és a termékekből.
4.  Számítsa ki az adott időszakra vonatkozó termelési és az elszámolóár között eltéréseket. **Az adott időszakban felhasznált összetevők:**
    -   Végezze el azon anyagok nettó realizált mennyiségének pénzügyi frissítését, amelyet a termelési folyamat az adott időszak során felhasznált. A rendszer elsőként be, elsőként ki (FIFO) elvű sorrendben dolgozza fel az egyes készlettranzakciókat, hogy elvégezze a termelési folyamathoz ténylegesen frissített tranzakciók pénzügyi frissítését, mindaddig, amíg eléri az adott időszak nettó realizált mennyiségét.
    -   A tranzakciókat pénzügyileg felosztják a pontos felhasznált mennyiségek leképezése érdekében.
    -   A befejezetlen termelés termelési folyamata során felhasználatlan mennyiségek ténylegesen frissített állapotúak maradnak.

    **Az adott időszak befejeződött termelési mennyiségei esetén:**
    -   Végezze el a teljesített mennyiségek készlettranzakcióinak pénzügyi frissítését az adott időszakra vonatkozóan.

    **Az átalakítási költség esetében:**
    -   Az adott időszakra rögzített alkalmazott átváltási költségtranzakciók (útvonal-tranzakciók) esetében pénzügyi frissítés történik.
    -   Az összes közvetlen gyártási költség esetében pénzügyi frissítés történik. Az adott időszakban végrehajtott összes kanbanfeldolgozási feladat felhalmozódik.
    -   Minden, a felhasznált anyagra az adott időszakon belül kiszámított közvetett költség kiszámítása és levonása a befejezetlen termelésből történik. A fennmaradó közvetett költség eltérésként kerül feladásra.

5.  Számítsa ki a termelési és az elszámolóár között eltéréseket. Az eltérés kiszámítása költségcsoportonként történik.





