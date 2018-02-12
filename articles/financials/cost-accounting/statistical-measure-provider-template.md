---
title: "Statisztikai dimenziótagok és statisztikaimérték-szolgáltató sablonok"
description: "Ez a témakör a statisztikai dimenziótagokról és a statisztikaimérték-szolgáltató sablonokról nyújt tájékoztatást. A statisztikai dimenziótagok felosztási alapként használhatók olyan irányelvekben, mint a költségfelosztás és a költségfoglalás. Használhatók a nem pénzügyi költségfelhasználás bejelentésére is."
author: AndersGirke
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CAMCostAccountingLedgerSourceEntryProvider, CAMStatisticalDimension, CAMAXStatisticalMeasureProviderTemplate
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 2c0a00b6a1956f1f22a50951308c434c3f0eefc4
ms.contentlocale: hu-hu
ms.lasthandoff: 11/03/2017

---

# <a name="statistical-dimension-members-and-statistical-measure-provider-templates"></a>Statisztikai dimenziótagok és statisztikaimérték-szolgáltató sablonok

[!include[banner](../includes/banner.md)]

A statisztikai dimenzió és és azok tagjai a Költségkönyvelés nem monetáris tételeinek regisztrálására és szabályozására szolgálnak. A statisztikai dimenziótagok két célra használhatók:

- Felosztási alapként az irányelvekben, mint például a költségfelosztás vagy a költségfoglalás
- Nem pénzbeli felhasználás bejelentésére

## <a name="statistical-dimension"></a>Statisztikai dimenzió

A statisztikai dimenzió egyedi névvel és egyedi dimenziókészlet-tagokkal rendelkezik. A statisztikai dimenzió hozzá van rendelve a Költségkönyvelési főkönyv azonosítójához. Ez a kapcsolat köti az összes megfelelő statisztikai dimenziótagot a Költségkönyvelési főkönyvhöz. Ezért az összes statisztikai bejegyzés a Költségkönyvelési főkönyv keretén belül jön létre.

> [!NOTE]
> A statisztikai dimenzió egy vagy több Költségkönyvelési főkönyvhöz rendelhető hozzá.

Íme, egy példa a statisztikai dimenzióra.

| Név                        | Dimenziótagok adatcsatlakozója |
|-----------------------------|--------------------------------------|
| Megosztott statisztikai elemek | Importált dimenziótagok           |

Íme, egy példa egy Költségkönyveléi főkönyvhöz társított statisztikai dimenzióra.

| Név                  | Könyvelési pénznem | Árfolyamtípus | Pénzügyi naptár | Költségösszetevő-dimenzió | Statisztikai dimenzió       |
|-----------------------|---------------------|--------------------|-----------------|------------------------|-----------------------------|
| Vezetői könyvelés | dollár                 | Állandó pénznem  | Pénzügyi időszak   | Megosztott költségösszetevők   | Megosztott statisztikai elemek |

## <a name="statistical-dimension-members"></a>Statisztikai dimenziótagok

A statisztikai dimenziótag olyan entitás, amelyet nem pénzbeli mértékként kell regisztrálni. Ezek a mértékek akár felosztási alapként, akár nem pénzbeli értékek bejelentésére használhatók.

A statisztikai dimenziótagok manuálisan hozhatók létre. Másik lehetőségként importálhatóak egy fájlból az Adatkezelési importálás/exportálás eszközzel.

Statisztikai dimenziótag automatikusan előre meghatározott felosztási alappá válik. Felosztási alapként használható irányelvekben vagy más típusú felosztási alapok bemeneteként.

Az alábbiakban néhány példát talál tipikus statisztikai dimenziótagokra.

| Statisztikai dimenzió neve  | Statisztikai elemek | Leírás             | Egység |
|-----------------------------|----------------------|-------------------------|------|
| Megosztott statisztikai elemek | FTE                  | Teljes munkaidős alkalmazottak     | Darab  |
| Megosztott statisztikai elemek | Villamos energia          | Áramfogyasztás | kWh  |
| Megosztott statisztikai elemek | Csomag költséghelye              | Csomagolási költséghely   | Óra |

## <a name="statistical-measure-provider-template"></a>Statisztikaimérték-szolgáltató sablon

A statisztikai mértékek többféle forrásból származhatnak. A Microsoft Dynamics 365 for Finance and Operations Enterprise edition rendszer kiváló forrás a statisztikai mértékek kigyűjtésére. A statisztikaimérték-szolgáltató sablon használatával egyszerűen konfigurálhatja a kigyűhteni kívánt statisztikai mértékeket.

A statisztikaimérték-szolgáltató sablon általános, és több statisztikai dimenziótagban is újrafelhasználható.

> [!NOTE]
> Minden olyan tábla, amely pénzügyi dimenziókat tartalmaz, statisztikai mérték forrásaként használható.

**Példa: Költséghely szerinti alkalmazottak száma**

A költséghely szerinti alkalmazottak létszáma olyan statisztikai mérték, amely többféle, vezetői betekintést nyújtó célra használható:

- Statisztikai jelentési mérték költséghely szerint
- Különböző költségek felosztási alapja
- Belső költségszorzók költséghely szerint:

    - Költség alkalmazottak szerint
    - Bevétel alkalmazottak szerint

A HcmEmployment tábla tartalmazza a példány összes alkalmazottjának listáját. Ez a tábla egy globális tábla. Ezért a rekordok nem kapcsolódnak egy konkrét adatterület-azonosítóhoz.

Íme, egy példa a HcmEmployment táblában levő alkalmazottakra.

| Név       | Költséghely | Leírás   | Dolgozó típusa |
|------------|-------------|----|-------------|
| 1. alkalmazott | CC001       | HR | Alkalmazott    |
| 2. alkalmazott | CC002       | FI | Alkalmazott    |
| 3. alkalmazott | CC002       | FI | Alkalmazott    |
| 4. alkalmazott | CC003       | Készletátadás | Alkalmazott    |
| 5. alkalmazott | CC003       | Készletátadás | Alkalmazott    |
| 6. alkalmazott | CC002       | FI | Alvállalkozó  |

**Statisztikaimérték-szolgáltató sablon** rekrod létrehozásakor döntse el, melyik funkciót szeretné használni:

- **Mennyiség** – Átvitelre kerül a költségobjektumonkénti rekordok száma.
- **Összeg** – Átvitelre kerül a költségobjektumonkénti rekordok összege. (Az **Összeg** mező és a **Dátum** mező kötelező mezők.)

## <a name="using-the-count-function"></a>A Mennyiség funkció használata

Egy statisztikaimérték-szolgáltató sablont a következőképpen lehet beállítani.

| Név  | Funkció | Forrástábla  | Összeg mező      | Dátummező     |
|-------|----------|---------------|----------------|----------------|
| Teljes munkaidős alkalmazottak  | Számolás    | HcmEmployment | Nem alkalmazható | Nem alkalmazható |

Egy vagy több tartomány hozzáadásával tovább szűkítheti a forrástábla mértékeit.

Ebben a példában ha csak a teljes munkaidős alkalmazottak létszámát szeretné megtudni, hozzáadhat egy tartományt a **Dolgozó típusa** mezőben. A **Feltételek** mezőben válassza ki az **Alkalmazott** lehetőséget a kimeneti tartomány következőképpen történő korlátozásához.

**Tartományok**

| Forrástábla  | Mező       | Feltételek |
|---------------|-------------|----------|
| HcmEmployment | Dolgozó típusa | Alkalmazott |

A statisztikai mértékek Költségkönyvelésben történő keresése előtt létre kell hoznia a kapcsolatot a statisztikaimérték-szolgáltató sablon és a statisztikai dimenziótag között. Ezt a kapcsolatot Költségkönyvelési főkönyvenként és verziónként kell létrehozni. A kapcsolat egy adatcsatlakozóból és egy adatszolgáltatóból áll. Egy statisztikai dimenziótag több adatcsatlakozóval és adatszolgáltatóval is rendelkezhet.

> [!NOTE]
> Ebben a példában csak a **Tényleges verzió** esetében hozzuk létre a kapcsolatot.

Lépjen a **Költségkönyvelési főkönyv** \> **Tényleges verzió** \> **Kezelés** \> **Statisztikai mérések** pontra a kapcsolat létesítéséhez. Ebben az esetben válassza a **Dynamics 365 for Finance and Operations Enterprise edition – Statisztikai mértékek** adatcsatlakozót rendszerrel, mivel a Finance and Operations rendszerből szeretnénk kigyűjteni az adatokat.

**Adatforrás**

| Név        | Adatcsatlakozó                                                                     | Statisztikai dimenziótag |
|-------------|------------------------------------------------------------------------------------|------------------------------|
| Teljes munkaidős alkalmazottak D365FO | Dynamics 365 for Finance and Operations, Enterprise Edition – Statisztikai mértékek | Teljes munkaidős alkalmazottak                         |

**Adatszolgáltató konfigurációja**

| Statisztikai sablon neve |
|---------------------------|
| Teljes munkaidős alkalmazottak                      |

A statisztikai mértékét adatforrásának feldolgozása után a Költségkönyvelésben a következő statisztikai bejegyzések jönnek létre.

**Napló**

| Napló | Napló típusa                       | Pénzügyi naptári időszak | Év   |  Időszak  |  Verzió | Forrásbejegyzések adatcsatlakozója|
|---------|------------------------------------|------------------------|--------|----------|----------|------------------------------|
| 00001   | Statisztikai bejegyzés átviteli naplója | Pénzügyi                 | 2017   | 1. időszak | Hitelesítésszolgáltatói főkönyvi USMF | Teljes munkaidős alkalmazottak                   |

**Statisztikai bejegyzés átvitel naplóbejegyzései**

| Könyvelési dátum | Nagyság | Statisztikai elem |   Leírás       | Költséghely |
|-----------------|-----------|---------------------|---------------------|-------------|
| 2017/01/31      | 1.00      | Teljes munkaidős alkalmazottak                | Teljes munkaidős alkalmazottak | CC001       |
| 2017/01/31      | 2.00      | Teljes munkaidős alkalmazottak                | Teljes munkaidős alkalmazottak | CC002       |
| 2017/01/31      | 2.00      | Teljes munkaidős alkalmazottak                | Teljes munkaidős alkalmazottak | CC003       |

**Statisztikai bejegyzések**

| Költségobjektum |    | Könyvelési dátum | Statisztikai dimenziótag |  Leírás        | Nagyság |
|-------------|----|-----------------|------------------------------|---------------------|-----------|
| CC001       | HR | 2017/01/31      | Teljes munkaidős alkalmazottak                         | Teljes munkaidős alkalmazottak | 1.00      |
| CC002       | FI | 2017/01/31      | Teljes munkaidős alkalmazottak                         | Teljes munkaidős alkalmazottak | 2.00      |
| CC003       | Készletátadás | 2017/01/31      | Teljes munkaidős alkalmazottak                         | Teljes munkaidős alkalmazottak | 2.00      |

Ha a teljes munkaidős alkalmazottak előre definiált dimenziótagjának felosztási alapja felosztási alapként van hozzárendelve egy költségfelosztási szabályhoz, a költséget a következő felosztási tényező segítségével osztja el a rendszer.

| Költségobjektum | Leírás    | Nagyság | Felosztási tényező |
|-------------|----|-----------|-------------------|
| CC001       | HR | 1.00      | (1/5) x Összeg    |
| CC002       | FI | 2.00      | (2/5) x Összeg    |
| CC003       | Készletátadás | 2.00      | (2/5) x Összeg    |

## <a name="using-the-sum-function"></a>Az Összeg funkció használata

A CC010 (Csomagolás) termelés költséghely felelős a termékek vevőknek történő kiszállítása előtti csomagolásáért. A közvetlen munkaköltség hozzáadódik a termékekhez az anyagjegyzéken (AJ) és az útvonalon keresztül. A költséghely működtetésének közvetett költségét is hozzá kell rendelni az előállított termékekhez. Az ilyen felosztás gyakran legjobb statisztikai mértéke az adott időszakban a termékenkénti regisztrált produktív idő száma.

A ProdRouteTrans tábla tartalmazza a DataAreadID jogi személyhez tartozó összes termelési munkatranzakciót.

Íme, egy példa a ProdRouteTrans táblára.

| Hivatkozás        | Szám | Művelet | Típus | Idő  | Tényleges dátum | Termékcsoport (Pénzügyi dimenzió) | Jogi személy |
|------------------|--------|-----------|------|-------|---------------|-------------------------------------|--------------|
| Termelési rendelés | P0001  | Csomagolás | Idő | 8,00  | 2017/01/01    | Narancslé B2B                    | USMF         |
| Termelési rendelés | P0001  | Csomagolás | Idő | 8,00  | 2017/02/01    | Narancslé B2B                    | USMF         |
| Termelési rendelés | P0002  | Csomagolás | Idő | 4,00  | 2017/03/01    | Narancslé fogyasztó               | USMF         |
| Termelési rendelés | P0003  | Csomagolás | Idő | 4,00  | 2017/03/01    | Narancslé fogyasztó               | USMF         |
| Termelési rendelés | P0004  | Reconst.  | Idő | 1000 | 2017/03/01    | Narancslé fogyasztó               | USMF         |

**Statisztikaimérték-szolgáltató sablon** rekrod létrehozásakor döntse el, melyik funkciót szeretné használni:

- **Mennyiség** – Átvitelre kerül a költségobjektumonkénti rekordok száma.
- **Összeg** – Átvitelre kerül a költségobjektumonkénti rekordok összege. (Az **Összeg** mező és a **Dátum** mező kötelező mezők.)

A statisztikaimérték-szolgáltató sablont a következőképpen lehet beállítani.

| Név    | Funkció | Forrástábla   | Összeg mező | Dátummező    |
|---------|----------|----------------|-----------|---------------|
| Csomag költséghelye | Összeg      | ProdRouteTrans | óra     | Tényleges dátum |

Tartományok hozzáadásával tovább szűkítheti a forrástábla mértékeit.

Ebben a példában, ha csak a CC010 Csomagolási költséghelyhez kapcsolódó órák összegét szeretné megtudni, adjon hozzá egy tartományt a **Művelet** mezőben. A **Feltételek** mezőben válassza ki a **Csomagolás** lehetőséget a kimeneti tartomány következőképpen történő korlátozásához.

**Tartományok**

| Forrástábla   | Mező     | Feltételek  |
|----------------|-----------|-----------|
| ProdRouteTrans | Művelet | Csomagolás |

A statisztikai mértékek Költségkönyvelésben történő keresése előtt létre kell hoznia a kapcsolatot a statisztikaimérték-szolgáltató sablon és a statisztikai dimenziótag között. Ezt a kapcsolatot Költségkönyvelési főkönyvenként és verziónként kell létrehozni. A kapcsolat egy adatcsatlakozóból és egy adatszolgáltatóból áll. Egy statisztikai dimenziótag több adatcsatlakozóval és adatszolgáltatóval is rendelkezhet.

> [!NOTE]
> Ebben a példában csak a **Tényleges verzió** esetében hozzuk létre a kapcsolatot.

Lépjen a **Költségkönyvelési főkönyv** \> **Tényleges verzió** \> **Kezelés** \> **Statisztikai mérések** pontra a kapcsolat létesítéséhez. Ebben az esetben válassza a **Dynamics 365 for Finance and Operations Enterprise edition – Statisztikai mértékek** adatcsatlakozót rendszerrel, mivel a Finance and Operations rendszerből szeretnénk kigyűjteni az adatokat.

**Adatforrás**

| Név           | Adatcsatlakozó                                                                     | Statisztikai dimenziótag |
|----------------|------------------------------------------------------------------------------------|------------------------------|
| Csomag költséghelye D365FO | Dynamics 365 for Finance and Operations, Enterprise Edition – Statisztikai mértékek | Csomag költséghelye                      |

A rendszer felismeri, hogy a ProdRouteTrans olyan tábla, amelyben minden rekord egy külön jogi személyhez tartozik. Ezért rendszer megkéri, hogy jelölje ki azt a jogi személyt, amely esetében szeretné importálni a tranzakciókat.

**Adatszolgáltató konfigurációja**

| Statisztikai sablon neve | Jogi személy |
|---------------------------|--------------|
| Csomag költséghelye                   | USMF         |

A statisztikai mértékét adatforrásának feldolgozása után a Költségkönyvelésben a következő statisztikai bejegyzések jönnek létre.

**Napló**

| Napló | Napló típusa                     | Pénzügyi naptári időszak | Év   | Időszak | Verzió   |   Forrásbejegyzések adatcsatlakozója  |
|---------|----------------------------------|------------------------|--------|---------|----------------|---------|
| 00002   | Statisztikai bejegyzés átviteli naplója | Pénzügyi               | 2017    | 1. időszak  | Hitelesítésszolgáltatói főkönyvi USMF | Csomag költséghelye |

**Statisztikai bejegyzés átvitel naplóbejegyzései**

| Könyvelési dátum | Nagyság | Statisztikai elem |  Leírás          | Termékcsoport         |
|-----------------|-----------|---------------------|-----------------------|-----------------------|
| 2017/01/31      | 16.00     | Csomag költséghelye             | Csomagolási költséghely | Narancslé B2B      |
| 2017/01/31      | 8,00      | Csomag költséghelye             | Csomagolási költséghely | Narancslé fogyasztó |

**Statisztikai bejegyzések**

| Költségobjektum           | Könyvelési dátum | Statisztikai dimenziótag |    Leírás        | Nagyság |
|-----------------------|-----------------|------------------------------|-----------------------|-----------|
| Narancslé B2B      | 2017/01/31      | Csomag költséghelye                      | Csomagolási költséghely | 16.00     |
| Narancslé fogyasztó | 2017/01/31      | Csomag költséghelye                      | Csomagolási költséghely | 8,00      |

Ha a Csomagolási költséghely előre definiált dimenziótagjának felosztási alapja felosztási alapként van hozzárendelve egy költségfelosztási szabályhoz, a költséget a következő felosztási tényező segítségével osztja el a rendszer.

| Költségobjektum           | Nagyság | Felosztási tényező  |
|-----------------------|-----------|--------------------|
| Narancslé B2B      | 16.00     | (16 ÷ 24) x Összeg |
| Narancslé fogyasztó | 8,00      | (8 ÷ 24) x Összeg  |

## <a name="imported-statistical-measures"></a>Importált statisztikai mértékek

A Költségkönyvelésbe importálhatja a statisztikai mértékeket az Adatkezelési importálás/exportálás eszközzel..

Az importáláshoz használt adatentitás neve Importált statisztikai mértékek.

> [!NOTE]
> Az adatentitásnak bejegyzésenként legfeljebb öt egyedi dimenzióértéke lehet.

Az áramfogyasztást a rendszer a Microsoft Excel alkalmazásban rögzíti az adatentitás előre meghatározott formátuma révén. Íme, egy példa.

| Könyvelési dátum | 1. dimenziótag neve | 2. dimenziótag neve | 5. dimenziótag neve | Nagyság  | Forrás azonosítója |
|-----------------|------------------------|------------------------|------------------------|------------|-------------------|
| 2017/01/31      | CC001                  |                        |                        | 2,450.00   | Villamos energia       |
| 2017/01/31      | CC002                  |                        |                        | 4,100.00   | Villamos energia       |
| 2017/01/31      | CC003                  |                        |                        | 15,000.00  | Villamos energia       |

Az adatok Adatkezelésen keresztül történő importálása után a rendszer az adatokat a Költségkönyvelési előkészítési táblában tárolja. Ezért az importált adatok több Költségkönyvelési főkönyvben használhatók. Nincs szükség az adatok újratöltésére.

Az adatok importálásához kattintson az **Importált adatok** \> **Adatentitás** \> **Importált statisztikai mértékek** lehetőségre.

| Forrás azonosítója | Könyvelési dátum | Nagyság  | 1. dimenziótag neve | 2. dimenziótag neve | 5. dimenziótag neve |
|-------------------|-----------------|------------|------------------------|------------------------|------------------------|
| Villamos energia       | 2017/01/31      | 2,450.00   | CC001                  |                        |                        |
| Villamos energia       | 2017/01/31      | 4,100.00   | CC002                  |                        |                        |
| Villamos energia       | 2017/01/31      | 15,000.00  | CC003                  |                        |                        |

A statisztikai mértékek Költségkönyvelésben történő keresése előtt létre kell hoznia a kapcsolatot a forrás azonosítója és a statisztikai dimenziótag között. Ezt a kapcsolatot Költségkönyvelési főkönyvenként és verziónként kell létrehozni. A kapcsolat egy adatcsatlakozóból és egy adatszolgáltatóból áll. Egy statisztikai dimenziótag több adatcsatlakozóval és adatszolgáltatóval is rendelkezhet.

> [!NOTE]
> Ebben a példában csak a **Tényleges verzió** esetében hozzuk létre a kapcsolatot.

Lépjen a **Költségkönyvelési főkönyv** \> **Tényleges verzió** \> **Kezelés** \> **Statisztikai mérések** pontra a kapcsolat létesítéséhez. Ebben az esetben válassza az **Importált statisztikai mértékek** adatcsatlakozót, mivel az adatokat egy külső rendszerből importálták a Költségkönyvelésbe Excelen keresztül.

**Adatforrás**

| Név        | Adatcsatlakozó                | Statisztikai dimenziótag |
|-------------|-------------------------------|------------------------------|
| Villamos energia | Importált statisztikai mértékek | Villamos energia                  |

**Adatszolgáltató konfigurációja**

| Importforrás azonosítója | Funkció | 1. dimenzió   | 2. dimenzió | 5. dimenzió |
|--------------------------|----------|--------------|------------|------------|
| Villamos energia              | Összeg      | Költséghelyek |            |            |

> [!NOTE]
> Az adatszolgáltató konfigurálásának definiálásakor meg kell adnia az importált tranzakciókkal egyeztetendő költségobjektum dimenzióit. A statisztikai mértékét adatforrásának feldolgozása után a Költségkönyvelésben a következő statisztikai bejegyzések jönnek létre.

**Napló**

| Napló | Napló típusa                       | Pénzügyi naptári időszak | Év  | Időszak  |Verzió      |Forrásbejegyzések adatcsatlakozója |
|---------|------------------------------------|------------------------|-------|--------|---------------|-------------|
| 00002   | Statisztikai bejegyzés átviteli naplója | Pénzügyi                 | 2017  | 1. időszak | Hitelesítésszolgáltatói főkönyvi USMF | Villamos energia |

**Statisztikai bejegyzés átvitel naplóbejegyzései**

| Könyvelési dátum | Nagyság  | Költségösszetevő |   Leírás           | Költséghely |
|-----------------|------------|--------------|-------------------------|-------------|
| 2017/01/31      | 2,450.00   | Villamos energia  | Áramfogyasztás | CC001       |
| 2017/01/31      | 4,100.00   | Villamos energia  | Áramfogyasztás | CC002       |
| 2017/01/31      | 15,000.00  | Villamos energia  | Áramfogyasztás | CC003       |

**Statisztikai bejegyzések**

| Költségobjektum |    | Könyvelési dátum | Statisztikai dimenziótag |      Leírás                   | Nagyság  |
|-------------|----|-----------------|------------------------------|-------------------------|------------|
| CC001       | HR | 2017/01/31      | Villamos energia                  | Áramfogyasztás | 2,450.00   |
| CC002       | FI | 2017/01/31      | Villamos energia                  | Áramfogyasztás | 4,100.00   |
| CC003       | Készletátadás | 2017/01/31      | Villamos energia                  | Áramfogyasztás | 15,000.00  |

Ha a Villamos energia előre definiált dimenziótagjának felosztási alapja felosztási alapként van hozzárendelve egy költségfelosztási szabályhoz, a költséget a következő felosztási tényező segítségével osztja el a rendszer.

| Költségobjektum |    | Nagyság | Felosztási tényező          |
|-------------|----|-----------|----------------------------|
| CC001       | HR | 2,450.00  | (2,450 ÷ 21,550) x Összeg  |
| CC002       | FI | 4,100.00  | (4,100 ÷ 21,550) x Összeg  |
| CC003       | Készletátadás | 15,000.00 | (15,000 ÷ 21,550) x Összeg |

## <a name="see-also"></a>Lásd még

[Felosztás alapjai](allocation-bases.md)

