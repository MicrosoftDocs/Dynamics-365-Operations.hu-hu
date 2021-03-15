---
title: Fizetési regisztráció alapján
description: Ez a témakör bemutatja, hogyan van kiszámítva a fizetés a dolgozói regisztrációk alapján.
author: johanhoffmann
manager: tfehr
ms.date: 03/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: JmgCalcApproveWeekView, JmgProdStatusListPagePayrollCostDetails, JmgPayCountTable, JmgPayStatConfig, JmgOvertimeSlize, JmgPayAgreementOverride, JmgPayCountSum, JmgPayAdjustSetup, JmgPayAdjustCostType, JmgPayEmployee, JmgMESBreak, JmgPayAddTable, JmgPayAddTransSelectTransId, JmgPayrollCostDetailsPart, jmgProdStatusListPagePayrollCosts, JmgPayrollCostPart, JmgPayEvents, JmgTermRegPayStatSetup, JmgPayStatGroup, JmgPayAddTrans, JmgPayStatTrans
audience: Application User
ms.reviewer: kamaybac
ms.custom: 1705903
ms.assetid: 427e01b3-4968-4cff-9b85-1717530f72e4
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2018-03-20
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: 98ca6f7713b2f605a49a97d391fb8485bea78c4b
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4966380"
---
# <a name="pay-based-on-registrations"></a>Fizetési regisztráció alapján

[!include [banner](../includes/banner.md)]

Ez a témakör részletesen bemutatja, hogyan van kiszámítva a fizetés a dolgozói regisztrációk alapján. Magában foglal olyan példákat is, amelyek bemutatják, hogy a számításhoz rendelkezésre álló beállítási lehetőségek kombinációi hogyan befolyásolják az eredményt. Íme néhány terület, amelyre vonatkozik:

- Rugalmas idő
- Túlóra
- Szünetek
- Kapcsolókódok
- Fizetési tételek
- Fizetési megállapodások
- A Munkaidő és jelenlét kiszámítási paraméterei
- Távollét

## <a name="the-use-of-flex-time"></a>A rugalmas idő használata

A rugalmas munkaidő-időszakok beállítása a Munkaidő és jelenlét funkció Időprofiljaiban történik. Két rugalmasidőprofil-típus van: **Rugalmasidő-többlet** és **Rugalmasidő-hiány**. Ha egy dolgozó rugalmasidő-többlet időszakban regisztrál időt, a dolgozó rugalmasidő-egyenlege nő a ledolgozott órák számával. A dolgozó nem kap kompenzációt a rugalmasidő-többlet időszakban ledolgozott órákért. A dolgozó azonban távozhat Rugalmasidő-hiány időszakok alatt, amiért a rugalmasidő-egyenlegéből kap majd kompenzációt. Emiatt a rugalmasidő időszakokban a távollétet szabadidőnek tekinti a rendszer.

## <a name="scenarios-based-on-flex-periods"></a>Rugalmasidő időszakokon alapuló esetek

A következő két forgatókönyv egy olyan rugalmasidő-profilra épül, amelyik egy munkanapot képvisel. Mindkét esetben a fizetés kiszámíthatására a rugalmas idő alapján kerül sor, az érkezéskori és távozáskori blokkolás alapján.

### <a name="flex-profile-for-one-workday"></a>Rugalmasidő-profil egy munkanapra

| Profil típusa  | Eleje    | Vége      | Nap     |
|---------------|----------|----------|---------|
| Túlóra     | 00:00 DE | 06:00 DE | Hétfő  |
| Rugalmasidő-többlet         | 06:00 DE | 07:00 DE | Hétfő  |
| Érkezéskori blokkolás      | 07:00 DE | 07:00 DE | Hétfő  |
| Szokásos idő | 07:00 DE | 02:30 DU | Hétfő  |
| Rugalmasidő-hiány         | 02:30 DU | 03:30 DU | Hétfő  |
| Távozáskori blokkolás     | 03:30 DU | 03:30 DU | Hétfő  |
| Túlóra     | 03:30 DU | 06:00 DE | Kedd |

### <a name="scenario-1-a-worker-registers-clock-in-during-a-flex-period-and-clock-out-during-a-flex--period"></a>1. eset: A dolgozó érkezéskor rugalmasidő-többlet időszak alatt, és távozáskor rugalmasidő-hiány időszak alatt blokkol

A dolgozói regisztrációk az adott napra vonatkozóan így jelennek meg.

| Naplóregisztráció típusa | Eleje    | Vége      |
|---------------------------|----------|----------|
| Érkezéskori blokkolás                  | 06:30 DE | 06:30 DE |
| Termelési feladat            | 06:30 DE | 02:45 DU |
| Távozáskori blokkolás                 | 02:45 DU | 02:45 DU |

A dolgozói regisztrációknak az adott napra vonatkozó kiszámítása és átvitele fizetésre a **Jóváhagy** lapon történik (**Munkaidő és jelenlét** &gt; **Áttekintés és jóváhagyás** &gt; **Jóváhagy**). A regisztrációk kiszámítása után a számítás eredményét az **Idők** lapon lehet megtekinteni. 

A forgatókönyv megértése érdekében lásd a következő mezőket.

| Rugalmasidő-többlet | Rugalmasidő-hiány | Idő | Fizetett idő |
|--------|--------|------|----------|
| 0,50   | 0.75   | 8,25 | 8,50     |

#### <a name="calculation-of-flex"></a>Rugalmasidő-többlet kiszámítása

A rugalmasidő-profil szerint a 06:00 DE és 07:00 DE közötti idő rugalmasidő-többlet időszaknak számít. Emiatt, ha a dolgozó érkezéskori blokkolása 06:30, 0,5 órát nyer. Ez az időmennyiség hozzáadódik a dolgozó rugalmasidő-fiókjához.

#### <a name="calculation-of-flex-"></a>Rugalmasidő-hiány kiszámítása

A rugalmasidő-profil alapján a rugalmasidő-időszak 02:30 DU kezdődik, és 03:30 DU időpontban ér véget. Emiatt, ha a dolgozó 14:45 órakor blokkol ki, a rugalmasidő-hiány időszakban maradó 45 perc (0,75 óra) fizetett időként lesz regisztrálva, és a rendszer ugyanannyi időt levon a dolgozó rugalmasidő-számlájáról. A 45 perc szerepel a fizetett időben, mert a dolgozó fizetést kap a fennmaradó 45 percért a rugalmasidő-hiány időszakban. Ha a dolgozó a Rugalmasidő-hiány időszakban van távol, a 45 perc levonásra kerül a rugalmasidő-egyenlegéből.

#### <a name="calculation-of-time"></a>Idő kiszámítása

Az időt a rendszer az érkezéskori blokkolás és a távozáskori blokkolás közötti időként számítja ki, vagyis 06:30 és 14:45 között egyenlő lesz 8,25 órával.

#### <a name="calculation-of-pay-time"></a>Fizetett idő kiszámítása

A fizetett idő az az idő, amelyre a dolgozónak fizetés jár. Ebben az esetben az a dolgozó 8,25 órát van munkában (**Idő**). Azonban a **Fizetett idő** 8,50 órának adódik, mert a dolgozó fizetésre jogosult a Rugalmasidő-hiány időszakban a távozáskori blokkolás után. A fizetett idő megfelel a tervezett munkaóráknak, mivel a rugalmasidő-többlet idejét a dolgozó rugalmasidő-számlájához adjuk hozzá, nem a fizetett időhöz. A rugalmasidő-hiány időszak alatt a távolléti időt kompenzáljuk a fizetett idővel, és levonjuk a dolgozó rugalmasidő-fiókjából.

| Idő              | Regisztráció típusa | Fizetett idő (óra)      |
|-------------------|-------------------|-----------------------|
| 6:30 DE - 7:00 DE | Rugalmasidő-többlet             | 0                     |
| 7:00 DE – 2:45 DU | Szokásos idő     | 7,75                  |
| 2:45 DU – 3:30 DU | Rugalmasidő-hiány             | 0,75 (távolléti időszak) |
|                   | Összesen             | 8,50                  |

### <a name="scenario-2-a-worker-works-during-the-whole-flex--period-and-also-works-overtime"></a>2. eset: A dolgozó végigdolgozza a rugalmasidő-hiány időszakot, túlórázik is

A dolgozói regisztrációk az adott napra vonatkozóan így jelennek meg.

| Naplóregisztráció típusa | Eleje    | Vége      |
|---------------------------|----------|----------|
| Érkezéskori blokkolás                  | 06:30 DE | 06:30 DE |
| Termelési feladat            | 06:30 DE | 05:00 DU |
| Távozáskori blokkolás                 | 05:00 DU | 05:00 DU |

Miután kiszámította a napló regisztrációit a **Jóváhagyás** lapon, megtekintheti a számítás eredményét az **Idők** lapon. A forgatókönyv megértéséhez tekintse meg az alábbi mezőket.

| Rugalmasidő-többlet | Rugalmasidő-hiány | Idő  | Fizetett idő | Fizetett túlóra |
|--------|--------|-------|----------|--------------|
| 0,50   | 0,00   | 10,50 | 10,00    | 1.50         |

#### <a name="calculation-of-flex"></a>Rugalmasidő-többlet kiszámítása

A rugalmasidő-profil szerint a 06:00 DE és 07:00 DE közötti idő rugalmasidő-többlet időszaknak számít. Emiatt, ha a dolgozó érkezéskori blokkolása 06:30 óra, 0,5 óra rugalmasidő-többletet nyer a rugalmasidő-egyenlegére.

#### <a name="calculation-of-flex-"></a>Rugalmasidő-hiány kiszámítása

Mivel a dolgozó dolgozik a rugalmasidő-időszak alatt, a rugalmasidő számítására nem kerül sor. Rugalmasidő-hiány számítására csak akkor kerül sor, ha a dolgozó távol van a rugalmasidő-időszak alatt. Fizetési szempontból ha a dolgozó a rugalmasidő-időszak alatt dolgozik, a normál munkaidőre meghatározott fizetést kapja. Ha a dolgozó a Rugalmasidő-hiány időszak van távol, a 45 perc levonásra kerül a rugalmasidő-egyenlegéből.

#### <a name="calculation-of-time"></a>Idő kiszámítása

Az időt a rendszer az érkezéskori blokkolás és a távozáskori blokkolás közötti időként számítja ki, vagyis 06:30 és 17:00 között egyenlő lesz 10,50 órával.

#### <a name="calculation-of-pay-time"></a>Fizetett idő kiszámítása

Ebben az esetben az a dolgozó 10,50 órát dolgozik (**Idő**). Azonban a **Fizetett idő** 10,00 órának adódik a számítások alapján, mert a dolgozó nem jogosult fizetésre a rugalmasidő-többlet időszak alatt.

#### <a name="calculation-of-pay-overtime"></a>Fizetett túlóra kiszámítása

| Idő               | Regisztráció típusa | Fizetett idő (óra) |
|--------------------|-------------------|------------------|
| 6:30 DE - 7:00 DE  | Rugalmasidő-többlet             | 0                |
| 7:00 DE – 2:30 DU  | Szokásos idő     | 7,50             |
| 2:30 DU – 3:30 DU  | Rugalmasidő-hiány             | 1.00             |
| 3:30 DU – 05:00 DU | Túlóra          | 1.50             |
|                    | Összesen             | 10,00            |

### <a name="generation-of-pay-items"></a>Fizetési tételek létrehozása

A napi dolgozói regisztrációkat át lehet vinni a **Jóváhagyás** oldalról. Az átviteli folyamat során fizetési tételek és az átvitt regisztrációk keletkeznek. A fizetési tételek a fizetési időt a normál munkaidőre, túlórára, fizetett szünet idejére stb. osztják fel.

A fizetési tételek listájának megnyitásához válassza a következőt: **Munkaidő és jelenlét** &gt; **Áttekintés és jóváhagyás** &gt; **Jóváhagyás**. Ezután válassza a **Lekérdezés** &gt; **Átvitt regisztrációk** lehetőséget.

A fizetési tételek egy dolgozó fizetésének alapját képezik. A fizetési tételek adatait tartalmazó fájl hozható létre, és ezt a fájlt átviheti a bérrendszerbe.

Az átviteli folyamat részeként a termelésből és a projektektevékenységekből származó idő és költségek átkerülnek a termelési és a projektnaplókba az idő- és költségkiadások elszámolására. Az átvitt regisztrációk képezik a termelési rendelések és projektek óránkénti önköltségi árának alapját. Az átvitt regisztrációk megnyitásához használja a **Lekérdezés** menü **Jóváhagy** lapját.

A 2. esetben például a következő fizetési tételek jönnek létre.

| Munkabér típusa     | Kifizetés típusa | Fizetési egységek | Árfolyam  | Teljes költség |
|---------------|----------|-----------|-------|------------|
| Szokásos idő | 1201     | 10,0      | 10    | 100        |
| Túlóra      | 1301     | 1.50      | 5     | 7,50       |
|               |          |           | Összesen | 107,50     |

A fizetési tételnek a normál munkaidőhöz 10 órás a fizetési egysége, és ez magában foglalja a normál munkaidőt, a rugalmasidő-hiányt és a túlórát. A szokásos idő, a rugalmas idő és a túlóra egy fizetési tételbe lett összevonva, mert a rendszer az összes típust normál munkaidőként számítja ki, a **Számítási paraméterek** lap egyik paraméterének alapértelmezett beállítása alapján (**Munkaidő és jelenlét** &gt; **Beállítás** &gt; **Számítási paraméterek**). A túlóra kiszámítása a normál munkaidő fölött történik, további 5 árfolyamon.

Ha egyértelműen szeretné megkülönböztethetni a normál munkaidőt és a túlórát, úgy, hogy a fizetési típusok fizetési egységei csak a normál munkaidő és a túlóra tényleges időráfordítását fedjék le, a normál munkaidő fizetési egységeit 8,50-ként kell számolni, a túlóra fizetési egységeit pedig 1,50-nel.

Annak a beállításához, hogy a rendszer egyértelműen megkülönböztesse a normál időt és a túlórát, ki kell zárnia a túlórát a szokásos időből. Módosítania kell a kifizetési típus beállítását a túlórához is, hogy a túlóra fizetési díjalapja lefedje a túlórával ténylegesen töltött órák összes kifizetését.

### <a name="exclude-overtime-from-the-standard-time"></a>Túlóra kizárása a normál időből

A **Számítási paraméterek** oldalon válassza **Túlóra** lehetőséget a profilspecifikáció típusaként, és állítsa a **Fizetett idő** lehetőséget **Nem** értékre, az itt leírt módon.

| Reg. meghatározása | Profilspecifikáció típusa | Számítás   |     | Fizetve         |     |
|--------------------|----------------------------|---------------|-----|--------------|-----|
| Munkaidő       | Túlóra                   | Szokásos idő | Igen | Fizetett idő     | Nincs  |
|                    |                            | Fizetett idő      | Igen | Fizetett túlóra | Igen |

A számítási paraméterek beállítása után a következő fizetési tételek jönnek létre.

| Munkabér típusa     | Kifizetés típusa | Fizetési egységek | Árfolyam  | Teljes költség |
|---------------|----------|-----------|-------|------------|
| Szokásos idő | 1201     | 8,50      | 10    | 85,0       |
| Túlóra      | 1301     | 1.50      | 15.    | 22,50      |
|               |          |           | Összesen | 107,50     |

> [!NOTE]
> A számítási paramétereknek van egy ajánlott, ajánlott szabványos beállítása. Általában óvatosnak kell lenni, amikor módosítja ezeket a paramétereket. Az ajánlott szabványos beállítások visszaállításához a **Számítási paraméterek** oldalon válassza az **Értékek visszaállítása** elemet.

### <a name="allow-a-deviation-from-the-standard-pay-profiles"></a>Szokásos fizetési profiltól való eltérés engedélyezése

A **Profilok** oldalon (**Munkaidő és jelenlét** &gt; **Beállítás** &gt; **Időprofilok** &gt; **Profilok**), be lehet állítani kapcsolókódokat és szüneteket tartalmazó profiltípusokat.

### <a name="switch-codes"></a>Kapcsolókódok

Kapcsolókódok segítségével engedélyezhető a dolgozók számára a saját profiltípustól különböző profiltípusra való váltás. Például engedélyezheti a dolgozó rugalmasidő-többletének túlórára történő módosítását. Egy dolgozó a regisztráció során kapcsolókódot adhat hozzá, vagy Ön hozzárendelheti a kapcsolókód hozzáadásának feladatát a regisztrációk jóváhagyójához.

Mielőtt kapcsolókódot használhatnánk, azt közvetett tevékenységként kell meghatározni. Ezután hozzá kell adnia a kapcsolókódot az időprofilhoz arra az időszakra, ahol a profiltípus módosítását engedélyezni akarja. Például kövesse ezeket a lépéseket egy kapcsolókód létrehozásához, amely lehetővé teszi a 06:00 DE és 07:00 DE közötti Rugalmasidő-többlet időszak túlórává alakítását.

1. Hozzon létre egy olyan kapcsolókódot, amelynek neve **OTBCI (rugalmas idő átalakítása túlórává érkezéskori blokkolás előtt)**. Válassza a **Munkaidő és jelenlét** &gt; **Közvetett tevékenységek karbantartása** &gt; **Közvetett tevékenységek** elemet.
2. A **Kapcsolókód** oszlopában adja hozzá az OTBCI-t a Rugalmasidő-többlet sorhoz az időprofilban.
3. A **Másodlagos** oszlopban adja hozzá a **Túlóra** profiltípust.

Vegye figyelembe a következő rugalmasidő-profilt, amely egy munkanapot képvisel.

| Profil típusa  | Eleje    | Vége      | Nap     |
|---------------|----------|----------|---------|
| Túlóra     | 00:00 DE | 06:00 DE | Hétfő  |
| Rugalmasidő-többlet         | 06:00 DE | 07:00 DE | Hétfő  |
| Érkezéskori blokkolás      | 07:00 DE | 07:00 DE | Hétfő  |
| Szokásos idő | 07:00 DE | 02:30 DU | Hétfő  |
| Rugalmasidő-hiány         | 02:30 DU | 03:30 DU | Hétfő  |
| Távozáskori blokkolás     | 03:30 DU | 03:30 DU | Hétfő  |
| Túlóra     | 03:30 DU | 06:00 DE | Kedd |

Itt vannak a napi dolgozói regisztrációk az adott napra vonatkozóan.

| Naplóregisztráció típusa | Eleje    | Vége      |
|---------------------------|----------|----------|
| Érkezéskori blokkolás                  | 06:30 DE | 06:30 DE |
| Termelési feladat            | 06:30 DE | 02:45 DU |
| Távozáskori blokkolás                 | 05:00 DU | 05:00 DU |

A következő fizetési tételek jönnek létre az átvitel után.

| Munkabér típusa     | Kifizetés típusa | Fizetési egységek | Árfolyam  | Teljes költség |
|---------------|----------|-----------|-------|------------|
| Szokásos idő | 1201     | 8,50      | 10    | 85,0       |
| Túlóra      | 1305     | 1.50      | 15.    | 22,50      |
|               |          |           | Összesen | 107,50     |

A **Jóváhagyás** lapon vonja vissza az átvitelt, és ezután a **Kapcsolókód** menüvel alkalmazza a **OTBCI** kapcsolókódot. Ha a regisztrációkat másodszor is átviszi, a következő fizetési tételek jönnek létre.

| Munkabér típusa     | Kifizetés típusa | Fizetési egységek | Árfolyam  | Teljes költség |
|---------------|----------|-----------|-------|------------|
| Szokásos idő | 1201     | 8,50      | 10    | 80,0       |
| Túlóra      | 1305     | 2.00      | 15.    | 30,0       |
|               |          |           | Összesen | 107,50     |

> [!NOTE]
> A kapcsolókód alkalmazásakor a túlóra 0,5 órával növekszik, 1,50 óráról 2,00 órára. A 0,5 óra a rugalmasidő-többletnek, amely regisztrálva van 6:30 és 07:00 között, az átalakítása túlórává.

### <a name="breaks"></a>Szünetek

A munka közben tartott szünetek érintik a dolgozó fizetését. A szünetek közvetett tevékenység egy típusaként vannak megadva. Megadható **Fizetve** módon, hogy a szünet hozzáadódjon a dolgozó fizetéséhez, vagy **Kifizetetlen** módon, a szünet ne adódjon hozzá a dolgozó fizetéséhez. Szünet megadható mint **Tervezett** vagy **Regisztrált**.

#### <a name="planned-breaks"></a>Tervezett szünetek

Ha egy cég rögzített szünetidővel dolgozik, például fix ebétszünettel, a szünetet előre lehet definiálni az időprofilban. Ebben az esetben a dolgozónak nem kell rögzítenie a szünetet a feladatkártya oldalon. Ehelyett a szünet automatikusan elszámolásra kerül, amikor az alkalmazotti regisztrációk kiszámítása a **Jóváhagyás** oldalon megtörténik.

#### <a name="registered-breaks"></a>Rögzített szünetek

Ha egy vállalat nem használ tervezett szüneteket, akkor a dolgozók a munkanap folyamán regisztrálhatnak szünetet. A rögzített szünetek például akkor használhatók, ha egy dolgozó olyan rugalmas időprofil alapján dolgozik, amely nem rendelkezik meghatározott érkezéskori és távozáskori blokkolási időkkel. A rögzített szünetek közvetett tevékenység egy típusának számítanak. A dolgozó regisztrálja a szünetet a **Feladatkártya** terminállapon vagy a **Feladatkártya** eszköz lapon. Mindkét oldalon a felhasználó előre meghatározott szünettevékenységek listájából kiválaszthatja a szünet típusát.

#### <a name="paid-and-unpaid-breaks"></a>Fizetett és nem fizetett szünetek

A szüneti tevékenységek beállíthatók mint **Fizetett** vagy **Nem fizetett**. A fizetett szünet szerepel a fizetési idő kiszámításánában, és a rendszer a fizetési megállapodásban a **Szünet** nyilvántartási típusra meghatározott fizetési típust használja.

### <a name="example-of-a-planned-break"></a>Példa tervezett szünetre

Vegye figyelembe a következő időprofilt, amely nem fizetett ebédszünetet tartalmaz.

| Profil típusa  | Eleje    | Vége      | Nap     |
|---------------|----------|----------|---------|
| Túlóra     | 00:00 DE | 06:00 DE | Hétfő  |
| Rugalmasidő-többlet         | 06:00 DE | 07:00 DE | Hétfő  |
| Érkezéskori blokkolás      | 07:00 DE | 07:00 DE | Hétfő  |
| Szokásos idő | 07:00 DE | 12:00 DU | Hétfő  |
| Szünet         | 12:00 DU | 12:30 DU | Hétfő  |
| Szokásos idő | 12:30 DU | 02:30 DU | Hétfő  |
| Rugalmasidő-hiány         | 02:30 DU | 03:30 DU | Hétfő  |
| Távozáskori blokkolás     | 03:30 DU | 03:30 DU | Hétfő  |
| Túlóra     | 03:30 DU | 06:00 DE | Kedd |

Itt vannak a napi dolgozói regisztrációk az adott napra vonatkozóan.

| Naplóregisztráció típusa | Eleje    | Vége      |
|---------------------------|----------|----------|
| Érkezéskori blokkolás                  | 06:30 DE | 06:30 DE |
| Termelési feladat            | 06:30 DE | 02:45 DU |
| Távozáskori blokkolás                 | 05:00 DU | 05:00 DU |

Miután kiszámította a napló regisztrációit a **Jóváhagyás** lapon, megtekintheti a számítás eredményét az **Idők** lapon. A forgatókönyv megértéséhez tekintse meg az alábbi mezőket.

| Rugalmasidő-többlet | Rugalmasidő-hiány | Idő  | Fizetett idő | Nem fizetett szünet ideje | Fizetett túlóra |
|--------|--------|-------|----------|---------------------|--------------|
| 0,50   | 0,00   | 10,50 | 9,50     | 0,5                 | 1.50         |

> [!NOTE] 
> A rendszer 0,5 óra nem fizetett szünetet számított ki, és ez az idő nem része a fizetett időnek.

### <a name="example-of-a-registered-break"></a>Példa regisztrált szünetre

Vegye figyelembe a következő időprofilt, amely nem tartalmaz tervezett szüneteket.

| Profil típusa  | Eleje    | Vége      | Nap     |
|---------------|----------|----------|---------|
| Túlóra     | 00:00 DE | 06:00 DE | Hétfő  |
| Rugalmasidő-többlet         | 06:00 DE | 07:00 DE | Hétfő  |
| Érkezéskori blokkolás      | 07:00 DE | 07:00 DE | Hétfő  |
| Szokásos idő | 07:00 DE | 02:30 DU | Hétfő  |
| Rugalmasidő-hiány         | 02:30 DU | 03:30 DU | Hétfő  |
| Távozáskori blokkolás     | 03:30 DU | 03:30 DU | Hétfő  |
| Túlóra     | 03:30 DU | 06:00 DE | Kedd |

Itt vannak a napi dolgozói regisztrációk az adott napra vonatkozóan.

| Naplóregisztráció típusa | Eleje    | Vége      |
|---------------------------|----------|----------|
| Érkezéskori blokkolás                  | 06:30 DE | 06:30 DE |
| Termelési feladat            | 06:30 DE | 05:00 DU |
| Szünet                     | 12:03 DU | 12:32 DU |
| Távozáskori blokkolás                 | 05:00 DU | 05:00 DU |

A regisztrációk kiszámítása során megtörténik az idő kiszámítása a tevékenységekhez.

| Naplóregisztráció típusa | Eleje    | Vége      | Idő  |
|---------------------------|----------|----------|-------|
| Érkezéskori blokkolás                  | 06:30 DE | 06:30 DE |       |
| Termelési feladat            | 06:30 DE | 05:00 DU | 10,00 |
| Szünet                     | 12:03 DU | 12:32 DU | 0,50  |
| Távozáskori blokkolás                 | 05:00 DU | 05:00 DU |       |

> [!NOTE]
> A szünet ideje a tevékenység (például egy termelési feladat) idejével párhuzamosan fut. Ez a viselkedés mindig használatos a szünet tevékenységekhez. A regisztrációk kiszámítása során a rendszer levonja a szünetek idejét a tevékenység idejéből. Ebben az esetben a termelési feladat időtartama 10,50 óra, de az idő 10-ként számítódik, mert a 0,5 órányi szünet idejét levonjuk a tevékenység idejéből.

Miután kiszámította a napló regisztrációit a **Jóváhagyás** lapon, megtekintheti a számítás eredményét az **Idők** lapon. A forgatókönyv megértéséhez tekintse meg az alábbi mezőket.

| Rugalmasidő-többlet | Rugalmasidő-hiány | Idő  | Fizetett idő | Nem fizetett szünet ideje | Fizetett túlóra |
|--------|--------|-------|----------|---------------------|--------------|
| 0,50   | 0,00   | 10,50 | 9,50     | 0,5                 | 1.50         |

Ha a tervezett szünet fizetett lett volna nem fizetett helyett, a számítás eredménye így nézne ki.

| Rugalmasidő-többlet | Rugalmasidő-hiány | Idő  | Fizetett idő | Fizetett szünet ideje | Fizetett túlóra |
|--------|--------|-------|----------|-----------------|--------------|
| 0,50   | 0,00   | 10,50 | 10,00    | 0,5             | 1.50         |

### <a name="pay-items-and-paid-breaks"></a>Fizetési tételek és a fizetett szünetek

Ha regisztrációkat visz át a **Jóváhagyás** lapon, fizetési tételek jönnek létre. A fizetett szünetekhez külön fizetési tételt jön létre.

A fizetési díjalapot a fizetett szünetek esetében az a fizetéstípus határozza meg, amely be van állítva a fizetési megállapodásokban a szünetnél. Fizetési típus használata helyett beállíthatja az óránkénti önköltségi árat a szünetre meghatározott időszak használatával.

Vegye figyelembe a következő időprofilt.

| Profil típusa  | Eleje    | Vége      | Nap     |
|---------------|----------|----------|---------|
| Túlóra     | 00:00 DE | 06:00 DE | Hétfő  |
| Rugalmasidő-többlet         | 06:00 DE | 07:00 DE | Hétfő  |
| Érkezéskori blokkolás      | 07:00 DE | 07:00 DE | Hétfő  |
| Szokásos idő | 07:00 DE | 02:30 DU | Hétfő  |
| Rugalmasidő-hiány         | 02:30 DU | 03:30 DU | Hétfő  |
| Távozáskori blokkolás     | 03:30 DU | 03:30 DU | Hétfő  |
| Túlóra     | 03:30 DU | 06:00 DE | Kedd |

Itt vannak a napi dolgozói regisztrációk az adott napra vonatkozóan.

| Naplóregisztráció típusa | Eleje    | Vége      | Idő |
|---------------------------|----------|----------|------|
| Érkezéskori blokkolás                  | 07:00 DE | 07:00 DE |      |
| Termelési feladat            | 07:00 DE | 03:00 DU | 7,5  |
| Szünet (fizetett)              | 12:00 DU | 12:30 DU | 0,5  |
| Távozáskori blokkolás                 | 03:00 DU | 03:00 DU |      |

Az ebben a példában a fizetéstípus normál munkaidőre **1201**, és **10** van beállítva fizetési díjalapként a fizetési megállapodásban. A fizetett szünet kifizetési típusa **1301**, és a fizetési díjalap **8**. Ha a regisztrációkat átviszik, a következő fizetési tételek jönnek létre.

| Munkabér típusa     | Kifizetés típusa | Fizetési egységek | Árfolyam |
|---------------|----------|-----------|------|
| Szokásos idő | 1201     | 7,50      | 10   |
| Rugalmasidő-hiány         | 1201     | 0,50      | 10   |
| Szünet (fizetett)  | 1301     | 0,50      | 8    |

## <a name="how-the-cost-of-paid-breaks-is-allocated-to-projects-and-production-orders"></a>Hogyan rendeljük a fizetett szünetek költségét projektekhez és a termelési rendelésekhez

A projekttevékenységek és a termelési feladatok óránkénti költsége beállítható úgy, hogy vagy a Munkaidő és jelenlétben kiszámított fizetési díjalapok, vagy a tevékenységekre vonatkozó költségkategóriák szerint történjen a kiszámítása.

A költségkategória beállításához válassza ki a **Gyártásvezérlés** &gt; **Beállítás** &gt; **Gyártásvégrehajtás** &gt; **Termelési rendelés alapértelmezései** elemet, és a **Költségkategória** mezőt állítsa **Igen** vagy **Nem** értékre.

- **Nem** – A költség kiszámítása a Munkaidő és jelenlét regisztrációs típusokra meghatározott fizetési díjak alapján történik.
- **Igen** – A költségek kiszámítása a termelési és projekttevékenységek költségkategóriáinak alapján történik.

### <a name="cost-calculation-based-on-pay-rates-that-are-calculated-in-time-and-attendance"></a>A Munkaidő és jelenlét szakaszban kiszámított fizetési díjalapok alapján történő költségszámítás

A következő példa bemutatja, hogyan történik az óránkénti költség kiszámítása, ha a költség úgy van beállítva, hogy a program a fizetési díjalapok alapján számítsa ki.

A termelési rendelésekre és projektekre vonatkozó óránkénti költségszorzó számítása az átviteli folyamat során történik. Az órabér / tevékenység megtekintéséhez nyissa meg a Munkaidő és jelenlét **Jóváhagyás** oldalát, és válassza a **Lekérdezés** &gt; **Átvitt regisztrációk** elemet. A regisztrációnkénti óránkénti önköltséget megtalálhatja az **Önköltségi árak** lapon.

Figyelembe kell venni a következő regisztrációkat, amelyek ugyanazt az időprofilt használják, mint az előző példában.

| Naplóregisztráció típusa | Eleje    | Vége      | Idő |
|---------------------------|----------|----------|------|
| Érkezéskori blokkolás                  | 07:00 DE | 07:00 DE |      |
| Folyamat (rendelés: 4711)     | 07:00 DE | 11:00 DE | 4    |
| Folyamat (rendelés: 4712)     | 11:00 DE | 03:00 DU | 3,50 |
| Szünet (fizetett)              | 12:00 DU | 12:30 DU | 0,50 |
| Távozáskori blokkolás                 | 03:00 DU | 03:00 DU |      |

Amikor a regisztrációkat átviszik, a következő átvitt regisztrációk jönnek létre.

| Regisztráció típusa     | Idő | Óránkénti önköltségi ár |
|-----------------------|------|---------------------|
| Érkezéskori blokkolás              | 0,00 | 0,00                |
| Folyamat (rendelés: 4711) | 4,00 | 10,00               |
| Folyamat (rendelés: 4712) | 3,50 | 11,14               |
| Szünet (fizetett)          | 0,50 | 0,00                |
| Távozáskori blokkolás             | 0,00 | 0,00                |

Az óránkénti önköltségi ár számítása a fizetett szünetekre a közvetlen bérköltség egy beállításától függ. Válassz a **Munkaidő és jelenlét** &gt; **Beállítás** &gt; **Munkaidő és jelenlét paraméterei** lehetőséget. Az **Önköltségi ár** lapon, a **Közvetlen bérköltség** alatt a **Normál munkaidő** mezőben választhat az **Igen**, **Nem**, vagy **Felosztás** lehetőségek közül.

- **Igen** – Ez az érték az előző példában használatos. A költség ahhoz a termelési vagy projekttevékenységhez van rendelve, amelyik párhuzamosan fut a fizetett szünet tevékenységgel. Ebben a példában ez a tevékenység a 4712-es rendeléshez tartozó termelési feladat. Amint látható, a fizetett szünet óránkénti önköltségi ára 0 (nulla), és a szünettel párhuzamosan futó feladathoz van rendelve.

    A fizetett szünet 0,5 óra időtartamú, és a fizetési díjalap 8. A fizetett szünet teljes költsége ezért 4. A teljes költség ekkor hozzá lesz rendelve a 3,5 órás feldolgozási feladathoz. Emiatt a fizetett szünet hozzájárul óránként 1,14 értékkel a költséghez (4 ÷ 3,5 = 1,14).

- **Felosztás** – A fizetett szünet egyenlően oszlik meg a napra regisztrált munkákra. Ha ezt az értéket használjuk az előző példában, a következő átvitt regisztrációk jönnek létre.

    | Regisztráció típusa     | Idő | Óránkénti önköltségi ár |
    |-----------------------|------|---------------------|
    | Érkezéskori blokkolás              | 0,00 | 0,00                |
    | Folyamat (rendelés: 4711) | 4,00 | 10,53               |
    | Folyamat (rendelés: 4712) | 3,50 | 10,53               |
    | Szünet (fizetett)          | 0,50 | 0,00                |
    | Távozáskori blokkolás             | 0,00 | 0,00                |

    A teljes feldolgozási ideje a két termelési feladatnak 7,5 óra, a fizetett szünet teljes költsége pedig 4. Emiatt a szünet költségének számított értéke 0,53 (= 4 ÷ 7,5).

- **Nem** – A fizetett szünet költsége nem növeli a folyamattevékenységek óránkénti költségét.

    | Regisztráció típusa     | Idő | Óránkénti önköltségi ár |
    |-----------------------|------|---------------------|
    | Érkezéskori blokkolás              | 0,00 | 0,00                |
    | Folyamat (rendelés: 4711) | 4,00 | 10,00               |
    | Folyamat (rendelés: 4712) | 3,50 | 10,00               |
    | Szünet (fizetett)          | 0,50 | 0,00                |
    | Távozáskori blokkolás             | 0,00 | 0,00                |

## <a name="absence"></a>Távollét

A távolléti kód szolgál a dolgozó távollétének időszakának rögzítésére. Mint a sortörések és a kapcsolókódok, a távolléti kód közvetett tevékenységi típusnak számít. A távolléti idő lehet tervezett vagy regisztrált, és a távollét lehet szabályos vagy szabálytalan. Szabályos távollétek közé tartozik, ha az ember orvoshoz, konferenciára megy vagy esküdtszéki kötelezettségét teljesíti. Szabálytalan távollét olyan távollét, amelynek nincs jó oka, például amikor egy munkavállaló késik a munkából. Általában a szabályos távollét nem okoz a levonást a dolgozó fizetéséből, a szabálytalan távollét viszont levonást okoz.

### <a name="planned-absence"></a>Tervezett távollét

A dolgozók tervezett távolléte létrehozható a **Tervezett távollét létrehozása** lapon (**Munkaidő és jelenlég** &gt; **Tervezett távollét létrehozása**). A tervezett távollétet itt távolléthez kapcsolódó feladatként regisztrálják, egy megadott dátum- és időintervallumhoz.

A feladat lekérdezés alapul. Emiatt létrehozhat tervezett távollétet több dolgozóra, például az ugyanazon számítási csoportba tartozó dolgozókra. Ha a tervezett távollét egy dolgozót érint, a regisztráció bevihető a **Jelenlét** lapon vagy az **Időnyilvántartás - dolgozók** lapon.

- Távollét-regisztráció megadásához a **Jelenlét** oldalon válassza a **Munkaidő és jelenlét** &gt; **Lekérdezések és jelentések** &gt; **Jelenlét** &gt; **Jelenlét** elemet, majd válassza ki **Távollét-regisztráció** lehetőséget.
- Távollét-regisztráció megadásához , az *<strong><em>Időnyilvántartás - dolgozók</em></strong>* lapon, válassza a <strong>Munkaidő és jelenlét</strong> &gt; <strong>Beállítás</strong> &gt; <strong>Időnyilvántartás – dolgozók</strong> elemet, majd az <strong>Idő</strong> lapon, a <strong>Munkaidő-hozzárendelés</strong> alatt, jelölje be a <strong>Távollét-regisztrációk</strong> elemet.

Használja a **Tervezett hiányzások** jelentést áttekintés nyerésére a dolgozók tervezett távolléteiről. A jelentés megnyitásához válassza ki a **Munkaidő és jelenlét** &gt; **Lekérdezések és jelentések** &gt; **Távolléti jelentések** &gt; **Tervezett távollétek** lehetőséget.

### <a name="registered-absence"></a>Rögzített távollét

Általános szabály szerint a dolgozók hiányzónak számítanak, ha a tervezett érkezéskori blokkolási idő és a tervezett távozáskori blokkolás időpontja között bármikor nincsenek munkában. Ha a dolgozók a tervezettnél később blokkolnak érkezéskor, vagy ha a tervezettnél korábban blokkolnak távozáskor, a rendszer arra kéri őket, hogy válasszanak távolléti kódot, amely jelzi a távollét okát. A távolléti kódot be lehet állítani úgy, hogy érvényes legyen a regisztrációra. A listában csak a megfelelő kódok választhatók ki.

## <a name="scenarios-based-on-various-combinations-of-work-hour-registrations"></a>Forgatókönyvek különböző óraregisztrációk kombinációinak alapján

A következő forgatókönyvek azokat a jóváhagyásra váró fizetési tételeket és bejegyzéseket mutatják, amelyek a dolgozókhoz jönnek létre a regisztrációik alapján. Az összes eset a következő időprofilon alapulnak.

| Profil típusa  | Eleje    | Vége      | Nap     |
|---------------|----------|----------|---------|
| Túlóra     | 00:00 DE | 06:00 DE | Hétfő  |
| Rugalmasidő-többlet         | 06:00 DE | 07:00 DE | Hétfő  |
| Érkezéskori blokkolás      | 07:00 DE | 07:00 DE | Hétfő  |
| Szokásos idő | 07:00 DE | 02:30 DU | Hétfő  |
| Rugalmasidő-hiány         | 02:30 DU | 03:30 DU | Hétfő  |
| Távozáskori blokkolás     | 03:30 DU | 03:30 DU | Hétfő  |
| Túlóra     | 03:30 DU | 06:00 DE | Kedd |

### <a name="scenario-1-the-worker-clocks-in-later-than-planned"></a>1. eset: A dolgozó érkezéskor a tervezettnél később blokkol

A dolgozó 08:30 órakor blokkol be. Mivel tervezett érkezéskori blokkolásának ideje 07:00 DE, 1,50 órát késett a munkából. Mivel az 1.50 óra távolléti időnek számít, a dolgozót a rendszer távolléti kód kiválasztására kéri. A dolgozó 15:30 órakor hagyja el a munkahelyét, és egyben ez a tervezett kiblokkolás ideje is. Az alkalmazotti regisztrációk számítása és jóváhagyása során a távollét-regisztráció, valamint a dolgozó által az érkezéskori blokkolásakor kiválasztott távolléti kód, jelenik meg a 07:00 óra és 08:30 óra közötti időszakra.

Az időprofilban konfigurálhatja az **Érkezéskori blokkolás** regisztrációs típust úgy, legyen tűréshatár arra az esetre, ha a dolgozók késnek a munkából. Például ha tűréshatárnak 5-öt állít be, a dolgozótól a rendszer csak akkor kér távolléti kódot, ha érkezéskori blokkolását 07:05 DE után végzi el.

Ebben az esetben, mivel a dolgozónak nincs alapos oka a munkából való késésre, kiválasztja a szabálytalan távolléthez tartozó távolléti kódot. A távolléti kód akkor érvényes a szabálytalan távollétre, ha engedélyezve van a túlóra levonásának beállítása a távolléti csoportra, amelyhez a távolléti kód tartozik. A beállítás megadásához válassza ki a **Munkaidő és jelenlét** &gt; **Beállítás** &gt; **Csoportok** &gt; **Távolléti csoportok** elemet, majd jelölje be a **Túlóra levonása** jelölőnégyzetet.

Itt látható, az adott napra vonatkozóan hogyan jelennek meg a dolgozói regisztrációk a **Jóváhagyás** lapon számítás után.

| Naplóregisztráció típusa         | Eleje    | Vége      | Idő |
|-----------------------------------|----------|----------|------|
| Távollét (szabálytalan – késés munkából) | 07:00 DE | 08:30 DE | 1.5  |
| Érkezéskori blokkolás                          | 08:30 DE | 08:30 DE |      |
| Termelési feladat                    | 07:30 DE | 03:30 DU | 7.0  |
| Távozáskori blokkolás                         | 03:30 DU | 03:30 DU |      |

Itt látható az eredményül kapott fizetési tétel a regisztrációk átvitele után.

| Munkabér típusa     | Kifizetés típusa | Fizetési egységek | Árfolyam |
|---------------|----------|-----------|------|
| Szokásos idő | 1201     | 7:00      | 10   |

### <a name="scenario-2-the-worker-clocks-out-before-the-planned-clock-out-time-during-a-standard-time-period"></a>2. eset: A dolgozó távozáskor a tervezett távozáskori blokkolás ideje előtt blokkol, a szokásos időszakban

A dolgozó 07:00 órakor blokkol be, és korán, 13:00 órakor blokkol ki. Mivel az 1:00 DU korábbi, mint a tervezett kilépéskori blokkolás időpontja, 3:30 DU, és a 01:00 DE egy szabványos időszakban van, a dolgozót a rendszer felkéri a távollét kódjának kiválasztására. A dolgozó kiválasztja az orvosi vizsgálat távolléti kódját, amely szabályos távollétként van definiálva. A fizetési díjalapot a szabályos távollétnél a fizetési megállapodások határozzák meg az **Távollét** regisztrációs típusra (**Munkaidő és jelenlét** &gt; **Beállítás** &gt; **Bérlista** &gt; **Fizetési megállapodások**).

Itt látható, az adott napra vonatkozóan hogyan jelennek meg a dolgozói regisztrációk a **Jóváhagyás** lapon számítás után.

| Naplóregisztráció típusa              | Eleje    | Vége      | Idő |
|----------------------------------------|----------|----------|------|
| Érkezéskori blokkolás                               | 07:00 DE | 07:00 DE |      |
| Termelési feladat                         | 07:00 DE | 01:00 DU | 4.0  |
| Távozáskori blokkolás                              | 01:00 DU | 01:00 DU |      |
| Távollét (szabályos – orvosnál járt) | 01:00 DU | 03:30 DU | 3.5  |

Itt látható az eredményül kapott fizetési tétel a regisztrációk átvitele után.

| Munkabér típusa     | Kifizetés típusa | Fizetési egységek | Árfolyam |
|---------------|----------|-----------|------|
| Szokásos idő | 1201     | 7,50      | 10   |

### <a name="scenario-3-the-worker-clocks-out-before-the-planned-clock-out-time-during-a-flex--period"></a>3. eset: A dolgozó távozáskor a tervezett távozáskori blokkolás ideje előtt blokkol, a rugalmasidő-hiány időszakban

A dolgozó 07:00 órakor blokkol be, és 14:15 órakor blokkol ki, ami a tervezett rugalmasidő-hiány időszak. A távozáskori blokkolás tényleges időpontja és a tervezett távozáskori blokkolás időpontja között eltelt idő nem számít távollétnek, és a dolgozót a rendszer nem kéri a távollét kódjának kiválasztására. Az összeget levonjuk a dolgozó rugalmasidő-számlájáról, és a dolgozó fizetést kap a fennmaradó rugalmasidő-hiány időszak alatt, 14:15 és 15:30 között.

Itt látható, az adott napra vonatkozóan hogyan jelennek meg a dolgozói regisztrációk a **Jóváhagyás** lapon számítás után.

| Naplóregisztráció típusa | Eleje    | Vége      | Idő |
|---------------------------|----------|----------|------|
| Érkezéskori blokkolás                  | 07:00 DE | 07:00 DE |      |
| Termelési feladat            | 07:00 DE | 02:15 DU | 7,25 |
| Távozáskori blokkolás                 | 02:15 DU | 02:15 DU |      |

Itt látható az eredményül kapott fizetési tétel a regisztrációk átvitele után.

| Munkabér típusa     | Kifizetés típusa | Fizetési egységek | Árfolyam |
|---------------|----------|-----------|------|
| Szokásos idő | 1201     | 8,50      | 10   |

### <a name="scenario-4-the-worker-clocks-in-late-and-clocks-out-after-the-planned-clock-out-time-during-an-overtime-period"></a>4. eset: A dolgozó késve blokkol érkezéskor, és távozáskor a tervezett blokkolás ideje előtt blokkol, túlóra időszakban

A dolgozó 09:30 órakor blokkol be, majd ezután, a késedelmes jelenlét kompenzációjaként, túlórázik, és 17:00 órakor blokkol ki. Mivel a dolgozó későn érkezett be, és ezt hosszabb ideig tartó munkával kompenzálta, a vállalat nem akar a dolgozónak túlóradíjat fizetni azon órákért, amelyeket a tervezett 03:30 DU-i távozáskori blokkolás és a 05:00 DU-kori tényleges távozáskori blokkolás dolgozott, még akkor sem, ha ez az időintervallum az időprofilban túlóraként van meghatározva.

Az eset kezeléséhez a távolléti kód be lehet állítani arra, hogy csökkentse a túlórákat bármilyen szabálytalan távolléttel, amellyel a dolgozó rendelkezik ugyanazon a napon. Válassza ki a **Munkaidő és jelenlét** &gt; **Beállítás** &gt; **Csoportok** &gt; **Távolléti csoportok** elemet, majd a **Túlóra levonása** jelölőnégyzet bejelölésével állítsa be a túlóra levonását a szabálytalan távollét óráiból.

Itt látható, az adott napra vonatkozóan hogyan jelennek meg a dolgozói regisztrációk a **Jóváhagyás** lapon számítás után.

| Naplóregisztráció típusa         | Eleje    | Vége      | Idő |
|-----------------------------------|----------|----------|------|
| Távollét (szabálytalan – késés munkából) | 07:00 DE | 09:30 DE | 1.5  |
| Érkezéskori blokkolás                          | 09:30 DE | 09:30 DE |      |
| Termelési feladat                    | 09:30 DE | 05:00 DU | 7,5  |
| Távozáskori blokkolás                         | 05:30 DU | 05:30 DU |      |

Ha a **Túlóra levonása** jelölőnégyzet be van jelölve a kijelölt távolléti kódhoz, a túlórabérből levonásra kerülnek a dolgozó szabálytalan távollétének órái. Ebben az esetben a következő fizetési tételek jönnek létre a regisztrációk átvitele után.

| Munkabér típusa     | Kifizetés típusa | Fizetési egységek | Árfolyam |
|---------------|----------|-----------|------|
| Szokásos idő | 1201     | 9:00      | 10   |
| Túlóra      | 1301     | 0,5       | 15.   |

Itt 1,5 óra szabálytalan távollét, 07:00 DE és 09:30 DE között, vonandó le a 2,0 óra túlórából 03:30 DU és 05:30 DU között. A regisztráció eredménye 1,5 óra normál munkaidő és 0,5 túlóra.

Ezzel szemben ha a **Túlóra levonása** jelölőnégyzet nincs bejelölve a kijelölt távolléti kódhoz, a túlórabér garantált a dolgozónak annak ellenére, hogy késett és szabálytalanul volt távol. Ebben az esetben a következő fizetési tételek jönnek létre a regisztrációk átvitele után.

| Munkabér típusa     | Kifizetés típusa | Fizetési egységek | Árfolyam |
|---------------|----------|-----------|------|
| Szokásos idő | 1201     | 7,50      | 10   |
| Túlóra      | 1301     | 2,0       | 15.   |

### <a name="scenario-5-the-worker-clocks-out-before-the-planned-clock-out-time-and-can-convert-the-absence-period-to-a-flex--period"></a>5. eset: A dolgozó a tervezett távozáskori blokkolás ideje előtt blokkol ki, és a távolléti időszakot alakíthatja rugalmasidő-hiány időszakká

A következő példa bemutatja, hogy egy dolgozó rugalmasidő-fiókja hogyan csökkenthető a távolléti időszak konvertálásával egy rugalmasidő-időszakra.

A dolgozó 07:00 órakor blokkol be, és 13:00 órakor blokkol ki. Olyan megállapodást között a művezetőjével, hogy hazamehet a hétvégre, ha ezeket az órákat levonja a rugalmasidő-számlájáról. Amikor a dolgozó távozáskori blokkolást végez 13:00 órakor, a rendszer arra kéri, hogy válasszon ki egy távolléti kódot, mert a távollét időtartama a munkanap fennmaradó részére nem tervezett rugalmasidő-hiány időszakban van. A munkanap fennmaradó részének rugalmasidő-hiány időszakká alakításához a dolgozó kiválaszthat egy távolléti kódot, amely azért van beállítva, hogy csökkentse a rugalmasidő-fiókot.

A munkanapon távollétet regisztráló dolgozók rugalmasóra-egyenlegének csökkentéséhez válassza a **Munkaidő és jelenlét** &gt; **Beállítás** &gt; **Csoportok** &gt; **Távollétcsoportok** elemet, és jelölje be a **Rugalmas idő csökkentése** jelölőnégyzetet.

Itt látható, az adott napra vonatkozóan hogyan jelennek meg a dolgozói regisztrációk a **Jóváhagyás** lapon számítás előtt.

| Naplóregisztráció típusa | Eleje    | Vége      | Idő |
|---------------------------|----------|----------|------|
| Érkezéskori blokkolás                  | 07:00 DE | 07:00 DE |      |
| Termelési feladat            | 07:00 DE | 01:00 DU | 6,0  |
| Távozáskori blokkolás                 | 01:00 DU | 01:00 DU |      |

Ha a dolgozó szabálytalan távolléthez való távolléti kódot választ, itt látható, hogyan fog kinézni a kapott fizetési tétel a regisztráció átvitele után.

| Munkabér típusa     | Kifizetés típusa | Fizetési egységek | Árfolyam |
|---------------|----------|-----------|------|
| Szokásos idő | 1201     | 6,00      | 10   |

Ha a dolgozó szabályos távolléthez való távolléti kódot választ, és a távollét kódja be van állítva rugalmasidő-egyenlegének csökkentésére, itt látható, hogyan fog kinézni a kapott fizetési tétel a regisztráció átvitele után.

| Munkabér típusa     | Kifizetés típusa | Fizetési egységek | Árfolyam |
|---------------|----------|-----------|------|
| Szokásos idő | 1201     | 8,50      | 10   |

Ebben az esetben a dolgozó rugalmasidő-egyenlege csökken a távozáskori blokkolás tényleges időpontja és a távozáskori blokkolás tervezett időpontja közti idővel (vagyis a 01:00 DU és 03:30 DU közötti 2,5 órával).

> [!NOTE]
> Nem ajánlott, hogy a **Rugalmasidő levonása** jelölőnégyzet és a **Túlóra levonása** jelölőnégyzetek közül mindkettőt bejelölje egy távolléti kódhoz, mivel ez a beállítás levonja a dolgozó érvénytelen óráit a túlórák számából, és ezzel egy időben csökkenti a dolgozó rugalmasidő-számláját is.

### <a name="scenario-6-there-is-no-planned-absence-for-the-day-and-no-worker-attendance-for-the-day"></a>6. eset: Nincs tervezett távollét az adott napra, és nincs dolgozó jelenlét az adott napra vonatkozóan

Ha a dolgozó munkanapon nem jelenik meg munkaidőben, és nincs tervezett távolléte a dolgozónak azon a napon, akkor a dolgozó regisztrálásának kiszámítására a rendszer egy alapértelmezett távolléti kódot használ. Alapértelmezett távollétkódok meghatározásához válassza ki a **Munkaidő és jelenlét** &gt; **Munkaidő és jelenlét paraméterei** elemet. Ezután kiválaszthat egy távolléti kódot a következő mezőkben:

- Rugalmas idő automatikus beillesztése
- Távollét automatikus beillesztése

Amikor egy olyan dolgozó esetében számítják ki a napi regisztrációkat, akinél engedélyezve vannak a rugalmas órák, a **Rugalmasidő-hiány automatikus beillesztése** mezőben megadott távolléti kód lesz alapértelmezett távolléti kódként használva. Ha a dolgozónál a rugalmas órák nem engedélyezettek, a **Távollét automatikus beillesztése** mezőben megadott távolléti kód kerül használatra. Ha egy vállalatnál olyan dolgozók is találhatók, akiknél engedélyezettek a rugalmas órák, és olyanok is,a kiknél a rugalmas órák nem engedélyezettek, mindkét paramétert be kell állítani.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]