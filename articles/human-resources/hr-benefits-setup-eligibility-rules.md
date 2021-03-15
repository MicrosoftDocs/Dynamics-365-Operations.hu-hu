---
title: Jogosultsági szabályok és beállítások konfigurálása
description: A Microsoft Dynamics 365 Human Resources szolgáltatás juttatáskezelésében megadhatja a jogosultsági szabályokat és beállításokat.
author: andreabichsel
manager: tfehr
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 2920a03eaec226b306d03ebf8b899113128c410e
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/03/2021
ms.locfileid: "5112803"
---
# <a name="configure-eligibility-rules-and-options"></a>Jogosultsági szabályok és beállítások konfigurálása

Miután konfigurálta a szükséges paramétereket a Microsoft Dynamics 365 Human Resources juttatáskezeléséhez, létrehozhat a juttatási konstrukciókhoz rendelhető jogosultsági szabályokat, csomagokat, időszakokat és programokat.

## <a name="create-an-eligibility-rule"></a>Jogosultsági szabály létrehozása

A jogosultsági szabályok határozzák meg, hogy melyik alkalmazottak léphetnek be az egyes juttatási konstrukciókba. A jogosultsági szabályok meghatározása után hozzárendelheti azokat a juttatási konstrukciókhoz. Ezután feldolgozhatja a belépési jogosultságot, és megtekintheti, hogy melyik alkalmazottak jogosultak az egyes konstrukciókra. 

A nyitott jelentkezés során az alkalmazottak választhatnak juttatási konstrukciókat. Ha a belépésük után a jogosultsági szabályok alapján megszűnik a jogosultságuk egy juttatási konstrukcióban, akkor a rendszer nem lépteti ki őket automatikusan. Ha olyan élettartam-esemény következik be, amely érinti a konstrukció jogosultságát, akkor az alkalmazott számára el kell indítani egy belépési időszakot, hogy ki lehessen választani azokat a konstrukciókat, amelyekre jogosulttá válik. 

1. A **Juttatások kezelése** munkaterület **Beállítás** részén válassza a **Jogosultsági szabályok és beállítások** lehetőséget.

2. Jogosultsági szabály létrehozásához a **Jogosultsági szabályok** lapon válassza az **Új** lehetőséget. A jogosultsági szabályokhoz társított konstrukciók megtekintéséhez válassza a **Csatolt konstrukciók** elemet.

3. Adjon meg értékeket a következő mezőkben:

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

4. A **További feltételek** területen válassza ki a következő beállításokat, és adja meg a szükséges adatokat:

   | Lehetőség | Leírás |
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
   | **Jogosult szakszervezet** | Megadja a jogosultsági szabálynak eleget tevő szakszervezeti tagságot. Például: Forklift Drivers of America. </br></br>Ha szakszervezeti alapú jogosultsági szabályt alkalmaz, a dolgozó szakszervezeti rekordjában szerepelnie kell a záró dátumnak. Nem hagyhatja üresen. |
   | **Jogosult irányítószám** | Megadja a jogosultsági szabálynak eleget tevő irányítószámokat. Például, 58104 elem. |

5. A **További részletek** területen a következő további részleteket tekintheti meg:

   | Mező | Leírás |
   | --- | --- |
   | **Jogosult felhasználó mezője** | Megadja a felhasználó által definiált mezőkre alapuló további jogosultsági szabályokat. |
   | **Jogosultság típusa** | Megadja a **További feltételek** területen kiválasztott feltételkategóriát. |
   | **Jogosultsági referencia** | Megadja a **További feltételek** területen kiválasztott értékeket. |
   | **Leírás** | A **További feltételek** területen kiválasztott leírás. |

6. Válassza a **Mentés** lehetőséget.

## <a name="configure-bundles"></a>Csomagok konfigurálása

A csomagok a kapcsolódó juttatási konstrukciók csoportjai. A juttatáscsomagokat azon juttatási konstrukciók csoportosítására használhatja, amelyeket az alkalmazottaknak ki kell választaniuk ahhoz, hogy beléphessenek azokba a juttatási konstrukciókba, amelyek más juttatási konstrukciókba való belépéstől függnek. Csomagot például a következő esetben használhat:

- Egészségügyi konstrukció csomagja, amely a kapcsolódó egészségügyi előtakarékossági számlával (HSA) együttesen levonható egészségügyi biztosítást tartalmaz.

- Életbiztosítási konstrukció kötelező életbiztosítási konstrukcióval, egy függő élettartam-konstrukcióval a csomagban. Ez biztosítja, hogy az alkalmazott ne válassza ki a függő élettartam-fedezetet az alkalmazotti fedezetre való feliratkozás nélkül.

1. A **Juttatások kezelése** munkaterület **Beállítás** részén válassza a **Jogosultsági szabályok és beállítások** lehetőséget.

2. Csomag létrehozásához a **Csomagok** lapon válassza az **Új** elemet. A csomaghoz társított konstrukciók megtekintéséhez válassza a **Csatolt konstrukciók** elemet.

3. Adjon meg értékeket a következő mezőkben:

   | Mező | Leírás |
   | --- | --- |
   | **Csomag** | A csomag egyedi azonosítója. |
   | **Leírás** | A csomag leírása. |
   | **Fő** | Azt jelzi, hogy a csomagban lévő egyik konstrukciót alapkonstrukcióként kell megjelölni. Az alapkonstrukciót ki kell választani a csomag részeként a nyitott belépés során, a juttatások adminisztrátora csak ezután erősítheti meg az alkalmazottak juttatásokra vonatkozó választásait. |
   | **Érvényesség kezdő dátuma és időpontja** | A csomag aktívvá válásának dátuma és ideje. |
   | **Érvényesség vége** | A csomag lejáratának dátuma. Az alapértelmezett érték a 2154. 12. 31., ami a „soha” megfelelője. |

4. Válassza a **Mentés** lehetőséget.

## <a name="configure-periods"></a>Időszakok konfigurálása

Az időszakok határozzák meg, hogy a juttatások mikor lépnek érvénybe, és az alkalmazottak mikor léphetnek be. Tetszőleges számú időszakot is létrehozhat a juttatások nyitott felvételi és fedezeti időszakainak kezeléséhez. A juttatási konstrukció évei követhetik a naptári évet, de ez nem kötelező. 

1. A **Juttatások kezelése** munkaterület **Beállítás** részén válassza a **Jogosultsági szabályok és beállítások** lehetőséget.

2. Időszak létrehozásához az **Időszakok** lapon válassza az **Új** elemet. Ha olyan folyamatot szeretne futtatni, amely az összes érvényes aktív juttatási konstrukciót csatolja a juttatási időszakhoz, válassza a **Konstrukció csatolása** lehetőséget. A csomaghoz társított konstrukciók megtekintéséhez válassza a **Csatolt konstrukciók** elemet. 

3. Adjon meg értékeket a következő mezőkben:

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

3. Válassza ki az alkalmazni kívánt rugalmas jóváírási programot. A mező a következő adatokat tartalmazza:

   | Mező | Leírás |
   | --- | --- |
   | Juttatás-jóváírás azonosítója | A rugalmas jóváírási program egyedi azonosítója. |
   | Leírás | A rugalmas jóváírási program leírása. | 
   | Kezdő dátum | A rugalmas jóváírási program aktívvá válásának dátuma. |
   | Záró dátum | A rugalmas jóváírási program záró dátuma. Az alapértelmezett érték (2154. 12. 31.) megtartásával jelezheti, hogy a rugalmas jóváírási programnak nincs ütemezett lejárata. |
   | Jóváírás értéke összesen | Azoknak a jóváírásoknak a száma, amelyeket az alkalmazottak használni fognak a juttatásaikhoz. |
   | Arányosítási szabály | A rugalmas jóváírások arányosításához használt szabály, amely akkor használható, amikor az alkalmazottat a rugalmas jóváírási program időszakának közepén veszik fel. </br></br><ul><li>**Nincs** – Az alkalmazott nem kap rugalmas jóváírásokat, ha a rugalmas jóváírási program időszak kezdete után veszik fel.</li><li>**Teljes jóváírás** – Az alkalmazott megkapja a rugalmas jóváírások teljes összegét, függetlenül attól, hogy mikor vették fel.</li><li>**Arányosítás** – Az alkalmazott a rugalmas jóváírások arányosított összegét kapja meg a kezdési dátumától függően.</li></ul> |
   | Rugalmas jóváírás arányosítási képlete | A rugalmas jóváírások arányosításához használt szabály azon alkalmazottak esetében, akiket a rugalmas jóváírási program juttatási időszakának közepén vesznek fel. Az arányosítás az alkalmazott foglalkoztatásának kezdő dátuma alapján történik. Ez a mező csak akkor használható, ha az **Arányosítás** lehetőséget választja az **Arányosítási szabály** mezőben. </br></br><ul><li>**Napi** – Az alkalmazott által kapott rugalmas jóváírások számát a nap szintjéig arányosítja. A rugalmas jóváírások számát az időszak napjainak számával kell elosztani. Ha például a juttatási időszak 400 nap, akkor a rendszer a rugalmas jóváírások számát 400-zal elosztva számítja ki, hogy az alkalmazottak hány rugalmas jóváírást kapnak naponta.</li><li>**Aktuális hónap** – Az alkalmazott által kapott rugalmas jóváírások számát a hónap szintjéig arányosítja, az aktuális hónapra kerekítve. A rugalmas jóváírások számát az időszak hónapjainak számával kell elosztani. Ha például a juttatási időszak 15 hónap, akkor a rendszer a rugalmas jóváírások számát 15-tel elosztva számítja ki, hogy az alkalmazottak hány rugalmas jóváírást kapnak havonta.</li><li>**Következő hónap** – Az alkalmazott által kapott rugalmas jóváírások számát a hónap szintjéig arányosítja, a következő hónapra kerekítve. A rugalmas jóváírások számát az időszak hónapjainak számával kell elosztani. Ha például a juttatási időszak 15 hónap, akkor a rendszer a rugalmas jóváírások számát 15-tel elosztva számítja ki, hogy az alkalmazottak hány rugalmas jóváírást kapnak havonta.</li></ul> |
   
   Ügyeljen arra, hogy minden juttatási konstrukciót juttatási időszakonként csak egy rugalmas jóváírási programba léptessen be. Ellenkező esetben a rendszer nem fogja tudni, hogy melyik rugalmas jóváírási programot kell használnia, és ez problémákat fog okozni. 

## <a name="configure-programs"></a>Programok konfigurálása

A programok olyan juttatási konstrukciók csoportjai, amelyek közös jogosultsági szabályokat használnak. A jogosultsági szabályokat a teljes programra vonatkozóan határozhatja meg, és nem külön az egyes konstrukciókra vonatkozóan. Például: Contoso Canada FTE program vagy Contoso Europe vezetői szintű program. 

1. A **Juttatások kezelése** munkaterület **Beállítás** részén válassza a **Jogosultsági szabályok és beállítások** lehetőséget.

2. Program létrehozásához a **Programok** lapon válassza az **Új** elemet. Ha kivételt szeretne tenni olyan alkalmazottak esetében, akik nem felelnek meg a jogosultsági szabályok követelményeinek, válassza a **Jogosultsági szabály felülbírálása** lehetőséget. A programhoz társított konstrukciók megtekintéséhez válassza a **Csatolt konstrukciók** elemet.

3. Adjon meg értékeket a következő mezőkben:

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