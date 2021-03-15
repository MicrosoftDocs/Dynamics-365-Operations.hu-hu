---
title: A Dayforce szolgáltatással való integráció konfigurálása
description: A Microsoft Dynamics 365 Human Resources és a Ceridian Dayforce között végbemenő integrálás több olyan konfigurációs lépésre támaszkodik, amelyeket ebben a cikkben ismertünk. A fizetési időszak feldolgozása előtt konfigurálnia kell az integrációt a Human Resources alkalmazásban és a Dayforce alkalmazásban is.
author: andreabichsel
manager: tfehr
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: PersonnelIntegrationConfiguration
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 044a2d2f632b2c98ce94b6d61c2582a861640b68
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/03/2021
ms.locfileid: "5112808"
---
# <a name="configure-integration-with-dayforce"></a>A Dayforce szolgáltatással való integráció konfigurálása

A Microsoft Dynamics 365 Human Resources és a Ceridian Dayforce között végbemenő integrálás több olyan konfigurációs lépésre támaszkodik, amelyeket ebben a cikkben ismertünk. A fizetési időszak feldolgozása előtt konfigurálnia kell az integrációt a Human Resources alkalmazásban és a Dayforce alkalmazásban is.

Ha olyan szolgáltatást használ a fizetési időszak teljesítéséhez, mint a Dayforce, engedélyeznie kell az integrációt a Human Resources alkalmazásban. Az integrációhoz szükségesek bizonyos adatok a Human Resources alkalmazásból. Ezért ellenőriznie kell, hogy a Dayforce alkalmazáshoz hozzárendelt adatok olyan módon legyenek konfigurálva a Human Resources alkalmazásban, hogy az támogassa az integrációt. Az integráció a következő szélesebb adatkategóriákat használja:

- Emberierőforrás-adatok
- Kompenzációadatok
- Bérlistaadatok, mint kifizetési ciklus, fizetési időszakok és bevételkódok
- Dolgozóadatok

Ez a cikk leírja a lépéseket, amelyeket követni kell az integráció engedélyezéséhez. Azt is bemutatja, hogy milyen típusú adatok és konfiguráció szükséges az integrációhoz.

## <a name="enable-the-integration"></a>Engedélyezze az integrációt

A Dayforce alkalmazáshoz való csatlakozáshoz a Human Resources alkalmazásban be kell kapcsolnia az integrációt és meg kell adnia a konfiguráció adatait. Ha azt szeretné, hogy a létrehozott általános főkönyvi tranzakció importálva legyen a Microsoft Dynamics 365 Finance alkalmazásba, be kell állítania egy Microsoft Azure tárolási fiókot, majd adja meg, majd Azure tárolási kapcsolat karakterláncát a Finance alkalmazásban.

A Human Resources alkalmazásban lévő integráció bekapcsolásához kövesse az alábbi lépéseket.

1. A **Rendszerfelügyelet** oldalon válassza az **Integrációkonfiguráció** lehetőséget.
2. Adja meg a biztonságos fájl átviteli protokollt (FTP) végpontot és a biztonságos FTP-mappa elérési útja.
3. Adja meg azon felhasználó felhasználónevét és jelszavát, aki hozzáfér a biztonságos FTP végponthoz és a mappa elérési útjához.
4. Tesztelje a kapcsolatot szükség szerint, és állítsa a **Bérlista-integráció engedélyezése** lehetőséggel **Igenre**.

Ha az integráció engedélyezve van, adatexport adatcsomagok és fájlok jönnek létre, valamint a gyakoriság is be van állítva. Igény szerint módosíthatja a gyakoriságot.

Az Azure tárolási fiókokkal és az Azure tárolási kapcsolati karakterláncokkal kapcsolatos további információkat az alábbi Azure-cikkben találja:

- [Az Azure Storage-fiókokról](https://docs.microsoft.com/azure/storage/common/storage-create-storage-account?toc=%2fazure%2fstorage%2ffiles%2ftoc.json)
- [Azure Storage kapcsolati karakterláncok konfigurálása](https://docs.microsoft.com/azure/storage/common/storage-configure-connection-string)

### <a name="technical-details-when-payroll-integration-is-enabled"></a>Technikai részletek a bérlista integrációjának engedélyezésekor

A bérlista-integráció bekapcsolása két elsődleges hatással jár:

- Létrejön egy „bérlista-integráció exportálása” nevű adatexportálási projekt. Ez a projekt a bérlista-integrációhoz szükséges entitásokat és mezőket tartalmazza. A projekt vizsgálatához nyissa meg a **Rendszerfelügyeletet**, válassza ki az **Adatkezelési** csempét, majd nyissa meg az adatprojektet a projektek listájából.
- Ez a kötegelt feladat végrehajtja az adatexportálási projektet, titkosítja a létrejövő adatcsomagot, és átviszi az adatcsomag-fájlt az **Integráció konfigurációja** képernyőjén beállított SFTP végpontba.

> [!NOTE]
> Az SFTP végpontra átvitt adatcsomag titkosítva van a csomag egyedi kulcsával. A kulcs egy Azure kulcstárolóban van, amely csak Ceridian számára érhető el. Az adatcsomag tartalmát nem lehet dekódolni és megvizsgálni. Ha meg kell vizsgálnia az adatcsomag tartalmát, akkor manuálisan kell exportálnia a „Bérlista-integráció exportálása” adatprojektet, le kell töltenie, majd meg kell nyitnia. A manuális exportálás nem alkalmazza a titkosítást, és nem viszi át a csomagot.

## <a name="configure-your-data"></a>Adatai konfigurálása 

A bérlista feldolgozásához konfigurálnia kell az emberierőforrás-adatokat a Human Resources alkalmazásban. Be kell állítani a szervezeti adatokat, például a feladatokat és beosztásokat, valamint juttatásokra és a kompenzációra vonatkozó adatokat. Ez az információ megadja a foglalkoztatásra, fizetésre és levonásokra vonatkozó információkat, melyek szükségesek az alkalmazott fizetések generálásához.

### <a name="human-resource-data"></a>Emberierőforrás-adatok

#### <a name="benefits"></a>Juttatások 

Az emberi erőforrások számos beállítási és karbantartási eszközt biztosít, amelyek segítségével beállíthatja és karbantarthatja a szervezet által a dolgozónak biztosított juttatásokat, levonásokat és dolgozói kompenzációs terveket.

Juttatások létrehozása esetén ne felejtse el a következő adatokat és beállításokat, amelyeket a Dayforce használ.

##### <a name="benefit-plans"></a>Juttatási tervek

- Terv (szükséges)
- Típus (szükséges)
- Bérlista hatása (szükséges)
- Hátralékok helyreállítása
- Levonási módszer
- Levonás prioritása
- Időszak korlátozása
- Összeghatár

##### <a name="benefits"></a>Juttatások

- Terv (szükséges)
- Típus (szükséges)
- Lehetőség (szükséges)
- Juttatás azonosítója (szükséges)
- Gyakoriság
- Alap
- Összeg vagy mérték
- Bevételkód

##### <a name="supported-frequencies"></a>Támogatott gyakoriságok 

- Heti
- Kétheti
- Félhavi
- Havi

##### <a name="supported-bases"></a>Támogatott alapok 

- Rögzített összeg
- Bevételek százaléka
- Produktív órák

A Dayforce létrehozza a következő levonásokat, a juttatási tervben definiált bérlistahatás alapján.

| Kiválasztás a Human Resources alkalmazásban        | Eredmény a Dayforce-ban                            |
|----------------------------|-----------------------------------------------|
| Egyik sem                       | Nincs létrehozva levonás.                      |
| Csak levonás             | Alkalmazotti levonás jön létre.             |
| Csak hozzájárulás          | Egy alkalmazotti levonás jön létre.             |
| Levonás és hozzájárulás | Alkalmazotti és a munkáltatói levonások jönnek létre. |

A juttatási programok meghatározásával és kezelésével kapcsolatos további tájékoztatást a következő cikkekben találja:

- [Alkalmazotti juttatási program végrehajtása](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/deliver-employee-benefits-program)
- [Új juttatás létrehozása](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/create-new-benefit)
- [Juttatásra való jogosultsági szabályok és irányelvek meghatározása](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-benefit-eligibility-rules-policies)
- [Dolgozók juttatásainak felvétele és eltávolítása](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-remove-benefits-workers)

#### <a name="compensation"></a>Kompenzáció 

A kompenzációkezeléssel szabályozható az alapfizetés és a jutalmak kifizetése. Egy alkalmazott fix fizetési díjalapja és érdemeken alapuló fizetése kezelhető a fix kompenzációs tervekkel. Az ösztönző díjak kifizetése, például bónuszok, teljesítménydíjak, részvényopciók és kölcsönök, továbbá az egyszeri jutalmak a változó kompenzációs tervekben szabályozhatók.

A Dayforce a kompenzációs adatok segítségével kiszámítja az alkalmazott óradíját vagy éves díját. Fix kompenzációs tervek és a fizetési díjalap átalakítások szükségesek. Az alkalmazottakat hozzá kell rendelni a fix kompenzációs tervhez.

A következő cikkekben bővebben olvashat a kompenzációs tervekről:

- [Fix kompenzációs konstrukciók létrehozása](https://docs.microsoft.com/dynamics365/unified-operations/talent/create-fixed-compensation-plans)
- [Változó kompenzációs konstrukciók létrehozása](https://docs.microsoft.com/dynamics365/unified-operations/talent/create-variable-compensation-plans)
- [Munkabér-/kompenzációs struktúra és tervek kialakítása](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/develop-salary-compensation-structure-plan)
- [Folyamatkompenzáció](https://docs.microsoft.com/dynamics365/unified-operations/talent/process-compensation)
- [Kompenzációs folyamat meghatározása és eredmények kiszámítása](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-compensation-process-calculate-results)
- [Alkalmazottak felvétele fix kompenzációs konstrukcióba](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-fixed-compensation-plan)
- [Alkalmazottak felvétele változó kompenzációs konstrukcióba](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-variable-compensation-plan)

#### <a name="jobs"></a>Beosztások 

A munkakör azon feladatok és felelősségek gyűjteménye, amelyek egy adott munkát végrehajtó személytől elvártak. További információért tekintse át az alábbi cikkeket:

- [Feladat összetevőinek beállítása](https://docs.microsoft.com/dynamics365/unified-operations/talent/create-job)
- [Új feladatok meghatározása](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-jobs)

##### <a name="positions"></a>Beosztások

Egy beosztás egy feladat egyedi példánya. Például az „Értékesítési igazgató (Kelet)” pozíció egyike azon beosztásoknak, amelyek társíthatók az „Értékesítési igazgató” feladathoz. A beosztás létezik a részlegben. Egy beosztáshoz csak egy dolgozó rendelhető.

A következő adatokat és konfigurációkat szem előtt tartani beosztások beállításakor:

- Beosztás (szükséges)
- Leírás (kötelező)
- Munka (kötelező)
- Részleg (kötelező)
- Beosztás típusa (kötelező)
- Teljes munkaidőssel egyenértékű
- Éves rendes munkaidő (kötelező)
- Jogi személy által fizetett (kötelező)
- Fizetési ciklus (kötelező)
- Alapértelmezett pénzügyi dimenzió – Költséghely (kötelező)
- Dolgozó-hozzárendelés – dolgozó-hozzárendelés kezdete, hozzárendelés vége és okkód

A azonos osztály több beosztása társítva van az ugyanazon a feladathoz, azok össze lesznek vonva a Dayforce egyetlen pozíciójába.

További információért tekintse át az alábbi cikkeket:

- [Munkaerő szervezése részlegek, feladatok és beosztások szerint](https://docs.microsoft.com/dynamics365/unified-operations/talent/departments-jobs-positions#positions)
- [Beosztások beállítása](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/set-up-positions)

#### <a name="departments"></a>Osztályok

A részleg egy működési egység, amely a szervezet egy kategóriáját vagy működési területét képviseli. Egy részleg a szervezet egy konkrét területen végzett tevékenységeiért felel (például értékesítés, könyvelés, emberi erőforrások). A részlegek segítségével hozhatók létre jelentések a működési területekről. A részlegeknek lehet eredménykimutatási felelőssége.

További információért tekintse át az alábbi cikkeket:

- [Részleg létrehozása és társítása a szervezeti hierarchiához](https://docs.microsoft.com/dynamics365/unified-operations/talent/create-department-add-department-hierarchy)
- [Új részlegek meghatározása](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-departments)

#### <a name="pay-cycles-and-pay-periods"></a>Fizetési ciklusok és fizetési időszakok

A fizetési ciklus meghatározza, hogy milyen gyakran történik a bérlista folyósítása, és a dolgozók mely napokon kapnak fizetést,. Például a kifizetési ciklus lehet, havi, és az alkalmazottak kaphatják a hónap utolsó napján a fizetésüket. Vagy a kifizetési ciklus lehet heti, és az alkalmazottak a fizetési időszak utáni kedden kaphatják fizetésüket. Kifizetési ciklusok beosztásokhoz vannak rendelve, és szabályozzák, hogy az ebben a beosztásban lévő dolgozók mikor kapnak fizetést.

Miután létrehozott fizetési ciklusokat, minden egyes ciklushoz fizetési időszakot hozhat létre. Minden fizetési időszakban egy alapértelmezett fizetési dátum van, amely a megadott adatokon alapul. Ugyanakkor az alapértelmezett fizetési dátumot a fizetési időszakban módosíthatja kivételekhez például amikor egy kifizetési dátum ünnepnapra esik.

A következő adatokat használja a Dayforce:

- Fizetési ciklus (kötelező)
- Fizetési ciklus gyakorisága (kötelező)
- Az időszak kezdő dátuma (az első fizetési időszak szükséges)
- Alapértelmezett fizetési dátum (az első fizetési időszak szükséges)

Ez az információ Dayforceba fizetési csoportokként van integrálva országonként vagy régiónként le van választva egyes kifizetési ciklusokhoz. Legalább egy fizetési időszakot kell létrehozni az integráció előtt. A Dayforce fizetési csoportnaptárakat és kifizetési dátumokat hoz létre az első fizetési időszak kezdő dátuma és az alapértelmezett fizetési dátum alapján, amelyek a Human Resources alkalmazásban vannak beállítva.

#### <a name="earning-codes"></a>Bevételkódok

A bevételkódok egyedi módon azonosítják a dolgozók által kapott fizetéstípusokat. A kódoknak különböző paraméterei vannak, amelyek a bevételekhez kapcsolódnak, például könyvelési szabályok, jelentési követelmények és bruttósítási lehetőségek.

A következő adatokat használja a Dayforce:

- Bevételkód (kötelező)
- Leírás
- Mértékegység
- Produktív

### <a name="worker-data"></a>Dolgozóadatok

A dolgozók különböző típusaihoz tartozó rekordok, melyek fontosak az emberi erőforrásoknak és a bérlistarendszerekhez. A bevitt információk felhasználhatók az dolgozói és személyes adatok nyilvántartására.

A dolgozók következő adatait tarthatja karban:

- **Alapvető** – A dolgozók alapvető információi, például a kapcsolattartási adatok, demográfiai adatok azonosító adatok, családi adatok, a katonai szolgálat állapota, kiküldetésekre vonatkozó adatok, illetve személyes és rendkívüli kapcsolattartók.
- **Foglalkoztatás** – Információk a dolgozó munkaviszonyáról, például a vállalati vagy szervezeti kapcsolat, hozzárendelt pozíció, kezdő és záró dátumok, munkajogosultság, foglalkoztatás feltételei, nyugdíj, szabadság és áthelyezéssel kapcsolatos információk.
- **Szabadság és a távollét** – A dolgozó távolléteinek kezelése, például a munkaidő-naptárak, a távolléti tranzakciók és távollét beállítása.
- **Kompenzáció és bérlista** – dolgozói kompenzációs tervek és bérlistainformációk kezelése, például felvétel konstrukciója, jutalmak, teljesítmény, jutalék, adózási információk, nyugdíj és fizetéslevonások.

A dolgozóinformációk létrehozása esetén ne felejtse el a következő adatokat és beállításokat, amelyeket a Dayforce használ.

#### <a name="general-information"></a>Általános információk

- Személyzeti szám (kötelező)
- Utónév (kötelező)
- Vezetéknév (kötelező)
- Második keresztnév
- Szolgálati idő dátuma
- Más néven

#### <a name="personal-information"></a>Személyes információ

- Családi állapot (kötelező)
- Születési dátum (kötelező)
- Nem (szükséges)
- Fogyatékkal élő személy
- Állampolgárság ország régió (csak a Mexikó)

#### <a name="address-information"></a>Címadatok

- Elsődleges (kötelező)
- Ország/régiót (kötelező)
- Irányítószámot (kötelező)
- Utca, házszám (kötelező) (csak Mexikó esetén)
- Épületblokk (csak a Mexikó)
- Város (kötelező)
- Állam (kötelező)
- Megye (kötelező)

#### <a name="contact-information"></a>Névjegy adatai 

- Elsődleges (kötelező)
- Kapcsolattartó száma (kötelező)
- Mellék

#### <a name="payroll-information-and-earning-codes"></a>Bérlistaadatok és bevételkódok

Alkalmazottak hozzárendelhetők meghatározott bevételekhez adott fizetési gyakorisággal, és magadható elsődleges fizetési mód. A következő mezőket a Dayforce arra használja, hogy garantálja, hogy ezeket a preferenciákat és beállításokat használja.

##### <a name="earning-codes"></a>Bevételkódok

- Beosztás (szükséges)
- Bevételkód (kötelező)
- Gyakoriság (kötelező)
- Összeg (szükséges)

##### <a name="payroll-information"></a>Bérlistaadatok

- Kifizetési mód
- Gazdasági régió (szükséges)
- Alkalmazott juttatásainak azonosítója
- Nemzeti azonosító (szükséges)
- Katonai szolgálat száma
- Műszakazonosító (kötelező)
- Adószám (kötelező)
- Szakszervezeti azonosító (szükséges)
- Munkanap azonosítója (szükséges)
- Munkavállalási engedély száma

> [!NOTE]
> A fizetési módhoz Mexikó támogatja a **Készpénzt**, **Csekket** (a vállalat fizikai csekkjét) és az **Elektronikus fizetést**. Ha nincs fizetési mód van megadva, alapértelmezés szerint a **Csekk** használt.

#### <a name="employment-details"></a>Foglalkoztatás részletei

Foglalkoztatási előzményei kulcsfontosságú információkat tartalmaznak a munkavállaók felvételi, elbocsátási, és újbóli felvétele állapotával kapcsolatosan a Dayforce-ban. Dayforce egyszerre csak egy aktív foglalkoztatásrekordot tesz lehetővé.

- Foglalkoztatás kezdődátuma (kötelező)
- Munkaviszony záró dátuma
- Kezdő dátum
- Módosított kezdési időpont
- Munkaviszony megszűnésének dátuma (megszűntetéskor kötelező)
- Felmondás oka (megszűntetéskor kötelező)

Az alkalmazott legfontosabb dátumai a következő adatokból vannak származtatva.

| Emberi erőforrások                | Dayforce                                                                                             |
|-----------------------|------------------------------------------------------------------------------------------------------|
| Legutóbbi felvételi dátum | Foglalkoztatás kezdete az aktuális nem megszűntetett előzményrekordra                                 |
| Munkaviszony megszűnésének dátuma      | Foglalkoztatás befejezése az aktuális nem megszűntetett előzményrekordra                                 |
| Kezdő dátum            | Módosított kezdési időpont, kezdődátum vagy foglalkoztatás kezdete az aktuális nem aktív előzményrekordra |
| Eredeti felvételi dátum    | Foglalkoztatás kezdete legkorábbi foglalkoztatási előzményrekordra                                               |

#### <a name="compensation"></a>Kompenzáció

Egy fix kompenzációs tervet kell társítani minden alkalmazott elsődleges pozíciójához az alkalmazási időszak alatt. Az időszak a belépés dátumával (vagy a foglalkoztatás kezdő dátumával) kezdődik, és a munkaviszony megszűnéséig tart .

- Érvényesség dátuma (kötelező)
- Lejárati dátum
- Fizetési díjalap (kötelező)
- Fizetési díjalapok átalakításai (kötelező)
- Évi egyenérték (kötelező)
- Óránkénti egyenérték (kötelező)

Ha az óránkénti alkalmazottnak több beosztása van, az elsődleges beosztásához tartozó fix kompenzációja importálva lesz a Dayforce-ba, alkalmazott szintű alapdíj/-fizetés. A nem elsődleges beosztások esetén, az óránkénti díj a megfelelő pozícióba lesz mentve Dayforce-ban.

Ha a fizetett alkalmazott több beosztással rendelkezik, a összesített óradíj és éves fizetés származtatva lesz az összes aktív beosztásból mint az alkalmazotti szintű alapdíj/-fizetés.

#### <a name="identification-numbers"></a>Azonosítószámok

##### <a name="social-security-identifier"></a>Társadalombiztosítási azonosító 

Minden alkalmazottnak kell egy elsődleges azonosítóval rendelkeznie. Ez az azonosító legyen **TAJ-szám** azonosítótípus kell legyen. A Dayforce-ban automatikusan van származtatva az alkalmazott társadalombiztosítási azonosítójából, mely a felvételhez szükséges.

- Elsődleges (kötelező)
- Azonosító típusa = „TAJ-szám”
- Kibocsátás dátuma
- Lejárat dátuma

Az alkalmazottak több azonosítószámot is megadhatnak **TAJ-szám** azonosítótípushoz. Azonban csak az **Elsődlegesként** megjelölt rekord van integrálva Dayforce-ba, függetlenül attól, hogy a szám aktív vagy lejárt.

#### <a name="bank-accounts-and-disbursements"></a>Bankszámlák és kifizetések

Érvényes bankszámlaadatokat meg kell adni minden olyan alkalmazotthoz, aki úgy dönt, hogy a banki átutalással kéri fizetését.

| Emberi erőforrások                         | Dayforce                                                                                                    |
|--------------------------------|-------------------------------------------------------------------------------------------------------------|
| Bankszámlaszám (kötelező) |                                                                                                             |
| SWIFT-kód (kötelező)          | **Bankazonosító** ez a mező Mexikóban történő bérlistafeldolgozáskor használatos.                                                             |
| Ágazati szám (kötelező)       |                                                                                                             |
| Bankszámla típusa (kötelező)   | **Számlatípus** ez a mező Mexikóban történő bérlistafeldolgozáskor használatos. Támogatott értékek: **Folyószámla** és **Bérlista** |

> [!NOTE]
> Alkalmazottak, akik úgy döntenek, hogy a banki átutaláson keresztülkérik fizetésük, meg kell adniuk egy hivatkozást egy jogi személyhez tartozó egyenlegszámlához, melynek elsődleges címének Mexikóban kell lennie és egy Mexikói bank érvényes bankszámlájához van társítva. Minden egyéb nem egyenlegszámla figyelmen kívül lesz hagyva.

#### <a name="address-information"></a>Címadatok

Minden alkalmazottnak kell egy elsődleges hellyel rendelkeznie. A Dayforce-ban ezen hely alapján van meghatározva az alkalmazott elsődleges tartózkodási helye adózási célokból.

- Elsődleges (kötelező)
- Ország/régiót (kötelező)
- Irányítószám/postai kód (kötelező)
- Utca (kötelező)
- Házszám (kötelező)
- Épületblokk
- Város (kötelező)
- Állam (kötelező)
- Megye (kötelező)

## <a name="configure-your-data-to-generate-payroll-in-united-states-and-canada"></a>Az adatok konfigurálása bérlista létrehozásához az Egyesült Államokban és Kanadában

Ha a fizetést generálása alkalmazottaknak az Egyesült Államokban és Kanadában, a következő elemeket kell beállítani:

- Részlegek szükségesek beosztásokhoz.
- Költséghelyek pénzügyi dimenziókként kell beállítani, és az alapértelmezett pénzügyi dimenzió karakterlánc első elemének kell lennie.

> [!NOTE] 
> Konfigurálhatja a Human Resources alkalmazást úgy, hogy a beosztásokhoz kötelező legyen beállítani részleget. Ehhez kattintson a **Emberi erőforrások megosztott beosztásai > Beosztások > Részlegek szükségesek beosztásokhoz.** elemre. Azt ajánljuk, hogy ezt a beállítást tartassa be az integráció során.

### <a name="job-types"></a>Feladattípusok

Beosztástípusok használatával a hasonló feladatok kategóriákba sorolhatók. A beosztástípusok szükségesek az Egyesült Államokban és Kanadában a bérlisták feldolgozásához. Beosztástípusok többek között a teljes és részmunkaidős, illetve a munkabéres és az órabéres. A beosztástípusok a fizetéstípusokként vannak hozzárendelve a Dayforce-hoz, melyek jelzik, hogy a munkavállaló órás vagy bérezéses.

A következő feladattípusok és leírások szükségesek.

| Feladattípus   | Leírás |
|------------|-------------|
| Óránként     | Óránként      |
| Bérezéses   | Bérezéses    |

### <a name="position-types"></a>Beosztási típusok 

Ne használjon beosztástípusokat annak leírására, hogy a beosztás teljes munkaidős, részmunkaidős vagy más. A feladattípusok a fizetésosztályokként vannak hozzárendelve a Dayforce-hoz, melyek jelzik, hogy a munkavállaló teljes- vagy részmunkaidős.

A következő beosztástípusok és leírások szükségesek.

| Beosztás típusa   | Leírás        |
|-----------------|--------------------|
| Teljes munkaidős       | Teljes munkaidős alkalmazott |
| Részmunkaidős       | Részmunkaidős alkalmazott |

### <a name="reason-codes"></a>Okkódok

Az alkalmazottak állapotával kapcsolatos okkódok tájékoztatnak. Okkódok a Dayforce-hoz állapot okaként vannak hozzárendelve, melyek jelzik egy alkalmazott beosztásában vagy alkalmazotti státuszában bekövetkezett változások okát.

A következő okkódok és leírások szükségesek.

| Okkód    | Leírás      | Alkalmazandó forgatókönyvek |
|----------------|------------------|----------------------|
| RESIGNATION    | Felmondás      | Felmondás a dolgozónak     |
| TERMINATION    | Befejezés      | Felmondás a dolgozónak     |
| RETIREMENT     | Megszüntetés       | Felmondás a dolgozónak     |
| EGYÉB          | Egyéb okok    | Felmondás a dolgozónak     |
| DEATH          | Elhalálozás            | Felmondás a dolgozónak     |
| LEAVEOFABSENCE | Szabadság | Felmondás a dolgozónak     |
| CONTRACTEND    | Szerződés vége  | Felmondás a dolgozónak     |
| SALARYCHANGE   | Munkabér módosítása | Kompenzáció         |

### <a name="marital-status"></a>Családi állapot

Családi állapot értékei Dayforce-hoz vannak rendelve és konvertálva szükség esetén az elfogadható értékekre az integráció során.

Az alábbi táblázat bemutatja, hogy családi állapot értékek hogyan vannak leképezve a Dayforce -ban.

| Emberi erőforrások                 | Dayforce             |
|------------------------|----------------------|
| Nős/férjezett                | Nős/férjezett              |
| Egy                 | Egy               |
| Özvegy                | Özvegy              |
| Elvált               | Elvált             |
| Bejegyzett élettársi kapcsolat | Élettársi viszony |
| Nincs                   | Nincs                 |
| Együttélés             | Együttélés           |

### <a name="gender"></a>Nem

A nemek a Dayforce-hoz vannak rendelve és konvertálva szükség esetén az elfogadható értékekre az integráció során.

Az alábbi táblázat bemutatja, hogy a nemek hogyan vannak leképezve a Dayforce-ban.

| Emberi erőforrások       | Dayforce        |
|--------------|-----------------|
| Férfi         | Férfi            |
| Nő       | Nő          |
| Nem meghatározott | *Nem támogatott* |

### <a name="earning-codes"></a>Bevételkódok

A bevételkódok egyedi módon azonosítják a dolgozók által kapott fizetéstípusokat. A kódoknak különböző paramétereket fednek le, amelyek a bevételekhez kapcsolódnak, például könyvelési szabályok, jelentési követelmények és bruttósítási lehetőségek. Ha egy nem támogatott gyakoriság van használatban, a **Minden fizetés** gyakorisága van alapértelmezés szerint használva a kiszámításhoz.

#### <a name="supported-frequencies"></a>Támogatott gyakoriságok

- Összes
- EVERYPAY
- EACHPAYPERIOD
- EVRYOTHRPAYODD
- EVRYOTHRPAYEVN
- 1OFMTH
- LASTOFMTH
- 2OFMTH
- 3OFMTH
- 4OFMTH
- 5OFMTH
- 1N2OFMTH
- 3N4OFMTH
- 1N3OFMTH
- 1N4OFMTH
- 2N3OFMTH
- 2N4OFMTH
- 1N2N3OFMTH
- 1N2N4OFMTH
- 1N3N4OFMTH
- 2N3N4OFMTH
- 1N2N3N4OFMTH - 1N2N3N4OFMTH
- 2N3N4N5OFMth - 2N3N4N5OFMth
- 1OFQTR - 1OFQTR
- LASTOFQTR – LASTOFQTR
- LASTMTHOFQTR – LASTMTHOFQTR
- 1OFYEAR - 1OFYEAR
- LASTOFYEAR – LASTOFYEAR
- NOVNDECOFYEAR - NOVNDECOFYEAR

### <a name="addresses"></a>Címek

Az adott ország vagy régió, állam és megye (település) kódok specifikus formátumokat követelnek, hogy Dayforce és az országos és regionális szolgáltatók felismerjék azokat. Annak ellenére, hogy a városok formátuma rugalmas, minden városnak társítva kell lennie egy államhoz.

| Emberi erőforrások          | Dayforce              |
|-----------------|-----------------------|
| Ország/régió  | Országkód          |
| Irányítószám / postai kód | Irányítószám           |
| Állami           | Államkód            |
| Város            | Város                  |
| Megye          | Megye (Helyhatóság) |
| Utca          | Cím 1. sora        |

### <a name="tax-regions"></a>Adórégiók

Az adórégiók a megfelelő adó megállapítására szolgálnak, amelyet a bérlista létrehozásakor kell alkalmazni. Az adórégiók helycímként vannak a Dayforce-hoz rendelve. Az alapértelmezett adórégiót a dolgozó aktív beosztásával kell társítani. 

- Adórégió (kötelező)
- Ország/régió (kötelező)
- Állam (kötelező)
- Megye 
- Város (kötelező)

## <a name="configure-your-data-to-generate-payroll-in-mexico"></a>Adatok konfigurálása bérlista létrehozásához Mexikóban

Ha a fizetést generál alkalmazottaknak Mexikóban, a következő elemeket kell beállítani:

- Részlegek szükségesek beosztásokhoz.
- Költséghelyek pénzügyi dimenziókként kell beállítani, és az Alapértelmezett pénzügyi dimenzió karakterlánc első elemének kell lennie.

### <a name="job-types"></a>Beosztástípusok

Beosztástípusok használatával a hasonló feladatok kategóriákba sorolhatók. Mexikóban a Bérlista feldolgozásához feladattípusok szükségesek. Beosztástípusok többek között a teljes és részmunkaidős, illetve a munkabéres és az órabéres. A beosztástípusok a fizetéstípusokként vannak hozzárendelve a Dayforce-hoz, melyek jelzik, hogy a munkavállaló órás vagy bérezéses.

A következő feladattípusok és leírások szükségesek.

| Feladattípus   | Leírás |
|------------|-------------|
| Óránként     | MX Órabér   |
| Bérezéses   | MX Bérezéses |

### <a name="position-types"></a>Beosztási típusok 

Ne használjon beosztástípusokat annak leírására, hogy a beosztás teljes munkaidős, részmunkaidős vagy más. A feladattípusok a fizetésosztályokként vannak hozzárendelve a Dayforce-hoz, melyek jelzik, hogy a munkavállaló teljes- vagy részmunkaidős.

A következő beosztástípusok és leírások szükségesek.

| Beosztás típusa   | Leírás        |
|-----------------|--------------------|
| Teljes munkaidős       | Teljes munkaidős alkalmazott |
| Részmunkaidős       | Részmunkaidős alkalmazott |

### <a name="reason-codes"></a>Okkódok

Az alkalmazottak állapotával kapcsolatos okkódok tájékoztatnak. Okkódok a Dayforce-hoz állapot okaként vannak hozzárendelve, melyek jelzik egy alkalmazott beosztásában vagy alkalmazotti státuszában bekövetkezett változások okát.

A következő okkódok és leírások szükségesek.

| Okkód            | Leírás                    | Alkalmazandó forgatókönyvek |
|------------------------|--------------------------------|----------------------|
| DEPARTUREBEFOREPAYMENT | Indulás első bérlista előtt | Felmondás a dolgozónak     |
| RESIGNATION            | Felmondás                    | Felmondás a dolgozónak     |
| PENSION                | Nyugdíj                        | Felmondás a dolgozónak     |
| TERMINATION            | Befejezés                    | Felmondás a dolgozónak     |
| RETIREMENT             | Megszüntetés                     | Felmondás a dolgozónak     |
| ABSENTEE               | Távollevő                       | Felmondás a dolgozónak     |
| EGYÉB                  | Egyéb okok                  | Felmondás a dolgozónak     |
| CLOSURE                | Üzletzárás               | Felmondás a dolgozónak     |
| DEATH                  | Elhalálozás                          | Felmondás a dolgozónak     |
| LEAVEOFABSENCE         | Szabadság               | Felmondás a dolgozónak     |
| CONTRACTEND            | Szerződés vége                | Felmondás a dolgozónak     |
| SALARYCHANGE           | Munkabér módosítása               | Kompenzáció         |

### <a name="terms-of-employment"></a>Foglalkoztatási feltételek

A Foglalkoztatási feltételek foglalkoztatási feltételkategóriák létrehozására használatosak. A feltételek alkalmazási mutató értékekként vannak a Dayforce-hoz rendelve.

A következő alkalmazási feltételek és leírások szükségesek.

| Foglalkoztatási feltételek   | Leírás |
|-----------------------|-------------|
| Szabályos               | Szabályos     |
| Közvetlen                | Közvetlen      |
| Szakmai gyakorlat            | Szakmai gyakorlat  |
| Állandó             | Állandó   |

### <a name="marital-status"></a>Családi állapot

Családi állapot értékei Dayforce-hoz vannak rendelve és konvertálva szükség esetén az elfogadható értékekre az integráció során.

Az alábbi táblázat bemutatja, hogy családi állapot értékek hogyan vannak leképezve a Dayforce -ban.

| Emberi erőforrások                 | Dayforce                  |
|------------------------|---------------------------|
| Nős/férjezett                | Nős/férjezett                   |
| Egy                 | Egy                    |
| Özvegy                | Özvegy                   |
| Elvált               | Elvált                  |
| Bejegyzett élettársi kapcsolat | Élettársi viszony      |
| Nincs                   | *Mexikó nem támogatja* |
| Együttélés             | *Mexikó nem támogatja* |

### <a name="gender"></a>Nem

A nemek a Dayforce-hoz vannak rendelve és konvertálva szükség esetén az elfogadható értékekre az integráció során.

Az alábbi táblázat bemutatja, hogy a nemek hogyan vannak leképezve a Dayforce-ban.

| Emberi erőforrások       | Dayforce                  |
|--------------|---------------------------|
| Férfi         | Férfi                      |
| Nő       | Nő                    |
| Nem meghatározott | *Mexikó nem támogatja* |

### <a name="payment-method"></a>Kifizetési mód

A Fizetési módok adják meg az alkalmazott és a vállalat számára az alkalmazott kifizetésének módja leírásának lehetőségét. A Fizetési módok a Dayforce-hoz vannak rendelve és konvertálva szükség esetén az elfogadható értékekre az integráció során.

Az alábbi táblázat bemutatja, hogy a fizetés módok hogyan vannak leképezve a Dayforce-ban.

| Emberi erőforrások             | Dayforce                  |
|--------------------|---------------------------|
| Készpénz               | Készpénz                      |
| Elektronikus fizetés | Átvitel                  |
| Csekkes              | Csekk                    |
| Váltó         | *Mexikó nem támogatja* |
| Egyéb              | *Mexikó nem támogatja* |

### <a name="bank-account-type"></a>Bankszámla típusa

Bankszámla-típusok az alkalmazottaknak történő elektronikus kifizetésekhez szolgálnak. Bankszámla típusa a Dayforce-ba átutalási számlaadatként van rendelve. A bankszámlatípusok szükség esetén konvertálva vannak az elfogadható értékekké az integráció során.

| Emberi erőforrások            | Dayforce                  |
|-------------------|---------------------------|
| Folyószámla  | CheckingAccount           |
| Bérlista elszámolási számlája   | PayrollAccount            |
| Megtakarítási számla   | *Mexikó nem támogatja* |
| BankGirot-számla | *Mexikó nem támogatja* |
| PlusGirot-számla | *Mexikó nem támogatja* |

### <a name="earning-codes"></a>Bevételkódok

A bevételkódok egyedi módon azonosítják a dolgozók által kapott fizetéstípusokat. A kódoknak különböző paramétereket fednek le, amelyek a bevételekhez kapcsolódnak, például könyvelési szabályok, jelentési követelmények és bruttósítási lehetőségek. Ha egy nem támogatott gyakoriság van használatban, a **Minden fizetés** gyakorisága van alapértelmezés szerint használva a kiszámításhoz.

#### <a name="supported-frequencies"></a>Támogatott gyakoriságok

- Összes
- EVERYPAY
- EACHPAYPERIOD
- EVRYOTHRPAYODD
- EVRYOTHRPAYEVN
- 1OFMTH
- LASTOFMTH
- 2OFMTH
- 3OFMTH
- 4OFMTH
- 5OFMTH
- 1N2OFMTH
- 3N4OFMTH
- 1N3OFMTH
- 1N4OFMTH
- 2N3OFMTH
- 2N4OFMTH
- 1N2N3OFMTH
- 1N2N4OFMTH
- 1N3N4OFMTH
- 2N3N4OFMTH
- 1N2N3N4OFMTH - 1N2N3N4OFMTH
- 2N3N4N5OFMth - 2N3N4N5OFMth
- 1OFQTR - 1OFQTR
- LASTOFQTR – LASTOFQTR
- LASTMTHOFQTR – LASTMTHOFQTR
- 1OFYEAR - 1OFYEAR
- LASTOFYEAR – LASTOFYEAR
- NOVNDECOFYEAR - NOVNDECOFYEAR

### <a name="addresses"></a>Címek

Az adott ország vagy régió, állam és megye (település) kódok specifikus formátumokat követelnek, hogy Dayforce és az országos és regionális szolgáltatók felismerjék azokat. Annak ellenére, hogy a városok formátuma rugalmas, minden városnak társítva kell lennie egy államhoz.

| Emberi erőforrások              | Dayforce              |
|---------------------|-----------------------|
| Ország/régió      | Országkód          |
| Irányítószám / postai kód     | Irányítószám           |
| Állami               | Államkód            |
| Város                | Város                  |
| Megye              | Megye (Helyhatóság) |
| Utca              | Cím 1. sora        |
| Utca, házszám       | Cím 2. sora        |
| Épületblokk | Cím 5. sora        |

### <a name="passport-number"></a>Útlevél száma

Az alkalmazottak útlevél adatokat is nyilatkozhatnak. Az információ a **Útlevél** azonosítótípusra vonatkozik, és az alkalmazott Mexikó-specifikus adataiként van a Dayforce-ba integrálva.

- Azonosító típusa = „Útlevél”
- Kibocsátás dátuma
- Lejárat dátuma

Az alkalmazottak több azonosítószámot is megadhatnak az **Útlevél** azonosítótípushoz. Azonban csak az aktuális aktív útlevélbejegyzés van integrálva a Dayforce-ba. Ha az összes útlevélbejegyzés lejárt, a legutóbb kiállított lesz integrálva a Dayforce-ba.



[!INCLUDE[footer-include](../includes/footer-banner.md)]