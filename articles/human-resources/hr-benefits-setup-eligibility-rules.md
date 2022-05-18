---
title: Jogosultsági szabályok és beállítások konfigurálása
description: Ez a témakör leírja, hogyan állíthatók be a jogosultsági szabályok és beállítások a Microsoft Dynamics 365 Human Resources rendszerben a Juttatások kezelése menüpontban.
author: twheeloc
ms.date: 08/24/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 88893f6ecee6d2bf0bb42bfa9043eb16a5ed4e90
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/04/2022
ms.locfileid: "8691273"
---
# <a name="configure-eligibility-rules-and-options"></a>Jogosultsági szabályok és beállítások konfigurálása 


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Miután konfigurálta a szükséges paramétereket a Juttatáskezeléséhez, létrehozhat a juttatási konstrukciókhoz rendelhető jogosultsági szabályokat, csomagokat, időszakokat és programokat.

A jogosultsági szabályok határozzák meg, hogy az alkalmazott jogosult-e egy konstrukcióra. Az alkalmazottaknak teljesíteniük kell legalább egy szabály feltételét ahhoz, hogy a juttatásra jogosultnak minősüljenek. Például egy tervhez két szabály tartozik. Az első szabály (1. sor) szerint az alkalmazott típusa csak **Alkalmazott** lehet. Az második szabály (2. sor) szerint az alkalmazottnak teljes munkaidősnek kell lennie. Ennek megfelelően az 1. szabálynak megfelelő alkalmazottak akkor is jogosultak, ha csak részmunkaidős alkalmazásban állnak.

Beállítható azonban egyetlen szabály, amely több feltételt is támaszt. Ebben az esetben az alkalmazottaknak teljesíteniük kell legalább a szabály összes feltételét ahhoz, hogy a juttatásra jogosultnak minősüljenek. Van például egy **Teljes munkaidős alkalmazott** nevű szabálya. Ez a szabály írja le, hogy az alkalmazott típusának **Alkalmazottnak** kell lennie, *és* az alkalmazottnak teljes munkaidősnek kell lennie. Ennek megfelelően az alkalmazottaknak teljesíteniük kell a szabály mindkét feltételét ahhoz, hogy jogosulttá tehetők legyenek.

> [!IMPORTANT]
> Minden juttatási csomaghoz legalább egy jogosultsági szabályt hozzá kell rendelni. Egy juttatáshoz több szabályt is társíthat.

## <a name="create-an-eligibility-rule"></a>Jogosultsági szabály létrehozása

A jogosultsági szabályok határozzák meg, hogy melyik alkalmazottak léphetnek be az egyes juttatási konstrukciókba. A jogosultsági szabályok meghatározása után hozzárendelheti azokat a juttatási konstrukciókhoz. Ezután feldolgozhatja a belépési jogosultságot, és megtekintheti, hogy melyik alkalmazottak jogosultak az egyes konstrukciókra. 

A nyitott jelentkezés során az alkalmazottak választhatnak juttatási konstrukciókat. Ha a belépésük után a jogosultsági szabályok alapján megszűnik a jogosultságuk egy juttatási konstrukcióban, akkor a rendszer nem lépteti ki őket automatikusan. Ha olyan élettartam-esemény következik be, amely érinti a konstrukció jogosultságát, akkor az alkalmazott számára el kell indítani egy belépési időszakot, hogy ki lehessen választani azokat a konstrukciókat, amelyekre jogosulttá válik. 

1. A **Juttatások kezelése** munkaterület **Beállítás** részén válassza a **Jogosultsági szabályok és beállítások** lehetőséget.

2. Jogosultsági szabály létrehozásához a **Jogosultsági szabályok** lapon válassza az **Új** lehetőséget. A jogosultsági szabályokhoz társított konstrukciók megtekintéséhez válassza a **Csatolt konstrukciók** elemet.

3. Adjon meg értékeket a következő mezőkben.

   | Mező | Leírás |
   | --- | --- |
   | **Jogosultsági szabály** | A jogosultsági szabály egyedi azonosítója. |
   | **Leírás** | A jogosultsági szabály leírása. |
   | **Érvényesség kezdő dátuma és időpontja** | A jogosultsági szabály kezdő dátuma. | 
   | **Érvényesség záró dátuma és időpontja** | A jogosultsági szabály záró dátuma. |
   | **Alkalmazott típusának használata** | Megadja, hogy az alkalmazott típusát kell-e használni a juttatás jogosultsági szabályában. |
   | **Dolgozó típusa** | A dolgozó típusa, ha az **Alkalmazott típusának használata** beállítás értéke **Igen**. |
   | **Alkalmazotti állapot használata** | Megadja, hogy az alkalmazott alkalmazotti állapotát kell-e használni a juttatás jogosultsági szabályában. |
   | **Állapot** | Az alkalmazott állapota, ha az **Alkalmazott állapotának használata** beállítás értéke **Igen**. Ha az **Alkalmazott állapotának használata** beállítás értéke **Nem**, a mező nem használható. |
   | **Foglalkoztatási kategória használata** | Megadja, hogy az alkalmazott **Foglalkoztatási kategória** értékét kell-e használni a juttatás jogosultsági szabályának részeként. | 
   | **Foglalkoztatási kategória** | Az alkalmazott foglalkoztatási kategóriája, ha a **Foglalkoztatási kategória használata** beállítás **Igen** értékűre van állítva. |
   | **Új dolgozóra vonatkozó szabály alkalmazása** | Megadja, hogy az új dolgozók új dolgozói időszakát kell-e használni a juttatások jogosultsági szabályának részeként. |
   | **Regisztrációs időszak** | Az az időszak, amikor az új dolgozói belépés engedélyezve van. Ha ezt a paraméterekben is beállítja, akkor a paraméterek beállítása felülbírálja ezt a beállítást. |
   | **Korábbi foglalkoztatási állapot használata** | Megadja, hogy az alkalmazott korábbi foglalkoztatási státuszát kell-e használni a juttatás jogosultsági szabályának részeként. Megadhat például egy jogosultsági szabályt, amely felold egy fedezeti várakozási időszakot minden olyan alkalmazott számára, aki az **Elbocsátott** állapotról egy **Alkalmazott** állapotba került az előző munkaviszonyától számított 90 napon belül. |

4. A **További feltételek** területen válassza ki a következő beállításokat, és adja meg a szükséges adatokat.

   | Beállítás | Leírás |
   | --- | --- |
   | **Jogosult életkor** | Meghatározza a jogosultsági szabály teljesítéséhez szükséges életkortartományt vagy -tartományokat. |
   | **Jogosult részleg** | Megadja, hogy az alkalmazottnak milyen részlegben vagy részlegekben kell lennie ahhoz, hogy eleget tegyen a jogosultsági szabálynak. |
   | **Jogosult foglalkoztatási típus** | Megadja, hogy az alkalmazottnak milyen foglalkoztatási típushoz vagy típusokhoz kell tartoznia ahhoz, hogy eleget tegyen a jogosultsági szabálynak. Például: teljes munkaidős vagy részmunkaidős. |
   | **Jogosult feladat** | Megadja a jogosultsági szabálynak eleget tevő feladatot vagy feladatokat. A feladatok a pozíciókhoz vannak társítva, a pozíciókat pedig az alkalmazottak töltik be. |
   | **Jogosult beosztásfunkció** | Megadja a jogosultsági szabálynak eleget tevő beosztásfunkciót vagy -funkciókat. Például: értékesítési dolgozók vagy technikusok. |
   | **Jogosult feladattípus** | Megadja a jogosultsági szabálynak eleget tevő feladattípust vagy -típusokat. Például: irodai vagy ügyvezetői. |
   | **Jogosult jogi személy** | Megadja a jogosultsági szabályhoz érvényes jogi személyt vagy jogi személyeket. Például: Contoso Entertainment System USA. |
   | **Jogosult kompenzációs régió** | Megadja a jogosultsági szabálynak eleget tevő alkalmazotti helyet. Például: USA középső régiója. |
   | **Jogosult beosztás** | Megadja a jogosultsági szabálynak eleget tevő beosztást vagy beosztásokat. Például: HR asszisztens vagy HR vezető. |
   | **Jogosult beosztástípus** | Megadja a jogosultsági szabálynak eleget tevő beosztástípust vagy -típusokat. Például: teljes munkaidős. |
   | **Jogosult állapot** | Megadja a jogosultsági szabálynak eleget tevő államokat vagy tartományokat. Például: Észak-Dakota, USA vagy Brit Kolumbia, Kanada. |
   | **Jogosult foglalkoztatási feltételek** | Megadja a jogosultsági szabálynak eleget tevő foglalkoztatási feltételeket. Például: rendelkezésre vagy csoportos szerződés. |
   | **Jogosult szakszervezet** | Megadja a jogosultsági szabálynak eleget tevő szakszervezeti tagságot. Például: Forklift Drivers of America.</br></br>Ha szakszervezeti alapú jogosultsági szabályt alkalmaz, a dolgozó szakszervezeti rekordjában szerepelnie kell a záró dátumnak. Nem hagyhatja üresen. |
   | **Jogosult irányítószám** | Megadja a jogosultsági szabálynak eleget tevő irányítószámokat. Például, 58104 elem. |

5. A **További részletek** területen a következő további részleteket tekintheti meg.

   | Mező | Leírás |
   | --- | --- |
   | **Jogosult felhasználó mezője** | Megadja a felhasználó által definiált mezőkre alapuló további jogosultsági szabályokat. |
   | **Jogosultság típusa** | Megadja a **További feltételek** területen kiválasztott feltételkategóriát. |
   | **Jogosultsági referencia** | Megadja a **További feltételek** területen kiválasztott értékeket. |
   | **Leírás** | A **További feltételek** területen kiválasztott leírás. |

6. Válassza a **Mentés** lehetőséget.

## <a name="using-custom-fields-in-eligibility-rules"></a>Egyéni mezők használata a jogosultsági szabályokban

A további adatok nyomon követésére [egyéni mezőket](hr-developer-custom-fields.md) lehet létrehozni a Human Resourceson belül. Ezek a mezők közvetlenül hozzáadhatók a felhasználói felülethez, és egy oszlopot dinamikusan hozzá lehet adni az alapul szolgáló táblához.  

A jogosultsági folyamathban használhatók egyéni mezők. A jogosultsági szabályok egy vagy több egyéni mezőérték használatával határozhatják meg az alkalmazottak jogosultságát.  Ha egyéni mezőt szeretne hozzáadni egy meglévő szabályhoz, vagy ha új szabályt szeretne létrehozni, lépjen a **Juttatáskezelés > Hivatkozások > Beállítás > Jogosultsági szabályok > Egyéni mező jogosultsága** részre. Ezen az oldalon létrehozhat olyan szabályt, amely egy vagy több egyéni mezőt használ, és a jogosultság meghatározásához értékeket definiálhat az egyes egyéni mezőkhöz.

A következő táblák támogatják a jogosultsági feldolgozásban használható egyéni mezőket:

- Dolgozó (HcmWorker)  
- Feladat (HcmJob)  
- Beosztás (HcmPosition)  
- Beosztás részletei (HcmPositionDetail)  
- Beosztáshoz rendelt dolgozó  
- Foglalkoztatás (HcmEmployment)  
- Foglalkoztatás részletei (HcmEmploymentDetails)  
- Feladat részletei (HcmJobDetails)  

A következő egyéni mezőtípusok támogatottak a jogosultsági feldolgozásban:

- Szöveg  
- Értéklista  
- Szám  
- Decimális  
- Jelölőnégyzet  

Az alábbi táblázatban az egyéni mezők jogosultsági űrlapmezőjének adatai láthatók.

| Mező  | Leírás |
|--------|-------------|
| Név | Az éppen létrehozott feltételek neve. |
| Tábla neve | A jogosultsági szabályhoz használt egyéni mezőt tartalmazó tábla neve. |
| Mezőnév | A jogosultsági szabályhoz használandó mező. |
| Operátor típusa | Az egyéni mező jogosultsági konfigurációjában használt operátor megjelenítése. |
| Érték | Az egyéni mező jogosultsági konfigurációjában használt érték megjelenítése. |

## <a name="eligibility-logic"></a>Jogosultsági logika

Az alábbi szakaszok a juttatásokra való jogosultság feldolgozását ismertetik.

### <a name="rules-assigned-to-a-plan"></a>Tervhez hozzárendelt szabályok 
Ha egy juttatási tervhez több jogosultsági szabály van hozzárendelve, akkor egy adott alkalmazottnak legalább egy szabályt teljesítenie kell ahhoz, hogy regisztrálni lehessen a juttatási tervbe.  A következő példában az alkalmazottnak vagy a **Feladattípus**, vagy az **Aktív alkalmazottak** szabálynak meg kell felelnie.

![Az alkalmazottnak vagy a Feladattípus, vagy az Aktív alkalmazottak szabálynak meg kell felelnie.](media/RulesAssignedToAPlan.png)
 
### <a name="criteria-within-an-eligibility-rule"></a>Jogosultsági szabályon belüli feltételek 
A szabályokon belül definiálni lehet a szabályt alkotó feltételeket. A fenti példában a **Feladattípus** szabály feltételei láthatók, ahol a Feladattípus = Igazgatók. Ebből következően az alkalmazottnak igazgatónak kell lennie ahhoz, hogy jogosult legyen. Ez olyan szabály, amelyben csak egy feltétel van a szabályon belül.

Több feltétellel rendelkező szabályt is meg lehet határozni. Ha egy jogosultsági szabályon belül több feltételt is meghatároz, akkor az alkalmazottnak a szabályon belüli összes feltételnek meg kell felelnie ahhoz, hogy részt vehessen a juttatási tervben. 

A fenti **Aktív alkalmazottak** szabályban például a következő feltételek vannak: Ahhoz, hogy az alkalmazott az **Aktív alkalmazottak** szabály alapján jogosult lehessen, az alkalmazottat az USMF jogi személynek kell alkalmaznia, *és* teljes munkaidős alkalmazottnak kell lennie.  

![Jogosultsági szabályon belüli feltételek.](media/CriteriaWithinAnEligibilityRule.png) 
 
### <a name="multiple-conditions-within-criteria"></a>Több feltétel a feltételeken belül

A szabályok tovább bonthatóak, hogy egyetlen feltételen belül több feltételt használjanak. Az alkalmazott akkor lesz jogosult, ha legalább egy feltételnek megfelel. A fenti példa alapján az **Aktív alkalmazottak** szabály tovább tágítható, hogy a részmunkaidős alkalmazottak is szerepeljenek benne. Ez azt jelenti, hogy az alkalmazottnak az USMF alkalmazottjának *és* teljes vagy részmunkaidős alkalmazottnak kell lennie.  

![Több feltétel a feltételeken belül.](media/MultipleConditionsWithinCriteria.png) 
 
### <a name="eligibility-conditions-within-a-custom-field-criterion"></a>Jogosultsági feltételek egy egyéni mező feltételén belül 
A fentiekhez hasonlóan, az egyéni mezők hasonlóan használhatók a jogosultsági szabályok létrehozása és a munka során. Előfordulhat például, hogy az internetre vonatkozó visszatérítést szeretne nyújtani a fargói és koppenhágai, otthonról dolgozó alkalmazottaknak, mivel az internetköltségek magasabbak ezeken a helyeken. Ehhez két egyéni mezőt kell létrehoznia: **Iroda helye** (választólista) és **Munkavégzés otthonról** (jelölőnégyzet). Ezután hozzon létre egy **WFH-alkalmazottak** nevű szabályt. A szabályhoz tartozó feltétel az, hogy az **Iroda helye = Fargo** vagy **Koppenhága** *és* a **Munkavégzés otthonról = Igen**.

Az egyéni jogosultsági szabályokat a következő képen látható módon kell beállítani. 

![Jogosultsági feltételek egy egyéni mező feltételén belül.](media/EligibilityConditionsWithinACustomFieldCriterion.png) 
 
## <a name="configure-bundles"></a>Csomagok konfigurálása

A csomagok a kapcsolódó juttatási konstrukciók csoportjai. A juttatáscsomagokat azon juttatási konstrukciók csoportosítására használhatja, amelyeket az alkalmazottaknak ki kell választaniuk ahhoz, hogy beléphessenek azokba a juttatási konstrukciókba, amelyek más juttatási konstrukciókba való belépéstől függnek. Csomagot például a következő esetben használhat:

- Egészségügyi konstrukció csomagja, amely a kapcsolódó egészségügyi előtakarékossági számlával (HSA) együttesen levonható egészségügyi biztosítást tartalmaz.

- Életbiztosítási konstrukció kötelező életbiztosítási konstrukcióval, egy függő élettartam-konstrukcióval a csomagban. Ez biztosítja, hogy az alkalmazott ne válassza ki a függő élettartam-fedezetet az alkalmazotti fedezetre való feliratkozás nélkül.

1. A **Juttatások kezelése** munkaterület **Beállítás** részén válassza a **Jogosultsági szabályok és beállítások** lehetőséget.

2. Csomag létrehozásához a **Csomagok** lapon válassza az **Új** elemet. A csomaghoz társított konstrukciók megtekintéséhez válassza a **Csatolt konstrukciók** elemet.

3. Adjon meg értékeket a következő mezőkben.

   | Mező | Leírás |
   | --- | --- |
   | **Köteg** | A csomag egyedi azonosítója. |
   | **Leírás** | A csomag leírása. |
   | **Fő** | Azt jelzi, hogy a csomagban lévő egyik konstrukciót alapkonstrukcióként kell megjelölni. Az alapkonstrukciót ki kell választani a csomag részeként a nyitott belépés során, a juttatások adminisztrátora csak ezután erősítheti meg az alkalmazottak juttatásokra vonatkozó választásait. |
   | **Érvényesség kezdő dátuma és időpontja** | A csomag aktívvá válásának dátuma és ideje. |
   | **Érvényesség vége** | A csomag lejáratának dátuma. Az alapértelmezett érték a 2154. 12. 31., ami a „soha” megfelelője. |

4. Válassza a **Mentés** lehetőséget.

## <a name="configure-periods"></a>Időszakok konfigurálása

Az időszakok határozzák meg, hogy a juttatások mikor lépnek érvénybe, és az alkalmazottak mikor léphetnek be. Tetszőleges számú időszakot is létrehozhat a juttatások nyitott felvételi és fedezeti időszakainak kezeléséhez. A juttatási konstrukció évei követhetik a naptári évet, de ez nem kötelező. 

1. A **Juttatások kezelése** munkaterület **Beállítás** részén válassza a **Jogosultsági szabályok és beállítások** lehetőséget.

2. Időszak létrehozásához az **Időszakok** lapon válassza az **Új** elemet. Ha olyan folyamatot szeretne futtatni, amely az összes érvényes aktív juttatási konstrukciót csatolja a juttatási időszakhoz, válassza a **Konstrukció csatolása** lehetőséget. A csomaghoz társított konstrukciók megtekintéséhez válassza a **Csatolt konstrukciók** elemet. 

3. Adjon meg értékeket a következő mezőkben.

   | Mező | Leírás |
   | --- | --- |
   | **Időszak** | Az időszak egyedi azonosítója. |
   | **Érvényesség kezdő dátuma és időpontja** | A juttatási időszak aktív állapotának kezdő dátuma és időpontja. |
   | **Érvényesség záró dátuma és időpontja** | A juttatási időszak aktívvá válásának dátuma és időpontja. |
   | **Regisztráció kezdete** | A nyitott belépés kezdő dátuma. Nyitott belépésre akkor van lehetőség, amikor az alkalmazottak juttatásokat választhatnak az önkiszolgáló juttatások közül. |
   | **Regisztráció vége** | A nyitott belépés záró dátuma. |
   | **Nyitva** | Azt jelzi, hogy az időszak nyitott-e a rendszerdátum, valamint a kezdő és záró dátum és időpont alapján. | 
   | **Előző időszak** | Megadja a kiválasztott juttatási időszakot megelőző juttatási időszakot. Ezt az információt a jogosult juttatásokba való belépés során kell használni az előző év konstrukcióinak, fedezeti lehetőségeinek és megbízottjainak hozzárendeléséhez. |
 
4. Válassza a **Mentés** lehetőséget.

## <a name="use-a-flex-credit-program"></a>Rugalmas jóváírási program használata

A rugalmas jóváírási programokkal az alkalmazottakat előre meghatározott számú rugalmas jóváírásnak megfelelően lehet beléptetni a juttatásokba. Az alkalmazottak határozhatják meg, hogyan osztják fel a rugalmas jóváírásaikat. Ha például egy alkalmazottra a házastárs egészségbiztosítási konstrukciója érvényes, akkor felhasználhatja más juttatásokhoz az egyébként egészségbiztosításhoz használt jóváírásokat.

1. A **Juttatások kezelése** munkaterület **Beállítás** részén válassza a **Jogosultsági szabályok és beállítások** lehetőséget.

2. Az **Időszakok** lapon válassza a **Rugalmas jóváírási programok** lehetőséget.

3. Válassza ki az alkalmazni kívánt rugalmas jóváírási programot. A mező a következő adatokat tartalmazza.

   | Mező | Leírás |
   | --- | --- |
   | **Juttatás-jóváírás azonosítója** | A rugalmas jóváírási program egyedi azonosítója. |
   | **Leírás** | A rugalmas jóváírási program leírása. | 
   | **Kezdő dátum** | A rugalmas jóváírási program aktívvá válásának dátuma. |
   | **Záró dátum** | A rugalmas jóváírási program záró dátuma. Az alapértelmezett érték (2154. 12. 31.) megtartásával jelezheti, hogy a rugalmas jóváírási programnak nincs ütemezett lejárata. |
   | **Jóváírás értéke összesen** | Azoknak a jóváírásoknak a száma, amelyeket az alkalmazottak használni fognak a juttatásaikhoz. |
   | **Arányosítási szabály** | A rugalmas jóváírások arányosításához használt szabály, amely akkor használható, amikor az alkalmazottat a rugalmas jóváírási program időszakának közepén veszik fel. </br></br><ul><li>**Nincs** – Az alkalmazott nem kap rugalmas jóváírásokat, ha a rugalmas jóváírási program időszak kezdete után veszik fel.</li><li>**Teljes jóváírás** – Az alkalmazott megkapja a rugalmas jóváírások teljes összegét, függetlenül attól, hogy mikor vették fel.</li><li>**Arányosítás** – Az alkalmazott a rugalmas jóváírások arányosított összegét kapja meg a kezdési dátumától függően.</li></ul> |
   | **Rugalmas jóváírás arányosítási képlete** | A rugalmas jóváírások arányosításához használt szabály azon alkalmazottak esetében, akiket a rugalmas jóváírási program juttatási időszakának közepén vesznek fel. Az arányosítás az alkalmazott foglalkoztatásának kezdő dátuma alapján történik. Ez a mező csak akkor használható, ha az **Arányosítás** lehetőséget választja az **Arányosítási szabály** mezőben. </br></br><ul><li>**Napi** – Az alkalmazott által kapott rugalmas jóváírások számát a nap szintjéig arányosítja. A rugalmas jóváírások számát az időszak napjainak számával kell elosztani. Ha például a juttatási időszak 400 nap, akkor a rendszer a rugalmas jóváírások számát 400-zal elosztva számítja ki, hogy az alkalmazottak hány rugalmas jóváírást kapnak naponta.</li><li>**Aktuális hónap** – Az alkalmazott által kapott rugalmas jóváírások számát a hónap szintjéig arányosítja, az aktuális hónapra kerekítve. A rugalmas jóváírások számát az időszak hónapjainak számával kell elosztani. Ha például a juttatási időszak 15 hónap, akkor a rendszer a rugalmas jóváírások számát 15-tel elosztva számítja ki, hogy az alkalmazottak hány rugalmas jóváírást kapnak havonta.</li><li>**Következő hónap** – Az alkalmazott által kapott rugalmas jóváírások számát a hónap szintjéig arányosítja, a következő hónapra kerekítve. A rugalmas jóváírások számát az időszak hónapjainak számával kell elosztani. Ha például a juttatási időszak 15 hónap, akkor a rendszer a rugalmas jóváírások számát 15-tel elosztva számítja ki, hogy az alkalmazottak hány rugalmas jóváírást kapnak havonta.</li></ul> |
   
   Ügyeljen arra, hogy minden juttatási konstrukciót juttatási időszakonként csak egy rugalmas jóváírási programba léptessen be. Ellenkező esetben a rendszer nem fogja tudni, hogy melyik rugalmas jóváírási programot kell használnia, és ez problémákat fog okozni. 

## <a name="configure-programs"></a>Programok konfigurálása

A programok olyan juttatási konstrukciók csoportjai, amelyek közös jogosultsági szabályokat használnak. A jogosultsági szabályokat a teljes programra vonatkozóan határozhatja meg, és nem külön az egyes konstrukciókra vonatkozóan. Például: Contoso Canada FTE program vagy Contoso Europe vezetői szintű program. 

1. A **Juttatások kezelése** munkaterület **Beállítás** részén válassza a **Jogosultsági szabályok és beállítások** lehetőséget.

2. Program létrehozásához a **Programok** lapon válassza az **Új** elemet. Ha kivételt szeretne tenni olyan alkalmazottak esetében, akik nem felelnek meg a jogosultsági szabályok követelményeinek, válassza a **Jogosultsági szabály felülbírálása** lehetőséget. A programhoz társított konstrukciók megtekintéséhez válassza a **Csatolt konstrukciók** elemet.

3. Adjon meg értékeket a következő mezőkben.

   | Mező | Leírás |
   | --- | --- |
   | **Program** | A program egyedi azonosítója. |
   | **Leírás** | A program leírása. | 
   | **Érvényesség kezdő dátuma és időpontja** | A program aktívvá válásának dátuma és ideje. |
   | **Érvényesség záró dátuma és időpontja** | A program lejáratának dátuma és ideje. Az alapértelmezett érték a 2154. 12. 31., ami a „soha” megfelelője. |
   | **Fedezet várakozási időszaka** | Az az időszak, ameddig az alkalmazottnak várnia kell a juttatási program elkezdődése előtt. |
   | **Levonás várakozási időszaka** | Az az időszak, ameddig az alkalmazottnak várakozik a juttatási program levonásainak elkezdődése előtt. |
   | **Jogosultsági szabályok** | Válassza ki a juttatási programra alkalmazandó jogosultsági szabályokat. A jogosultsági szabályokat a **Jogosultsági szabályok** lapon határozhatja meg. |
   
4. Válassza a **Mentés** lehetőséget.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
