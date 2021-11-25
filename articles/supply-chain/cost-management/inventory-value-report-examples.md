---
title: Készletérték-jelentés – példák és logika
description: Ez a témakör néhány példát mutat be az egyes készletérték-jelentéseken megjelenő eredményekre. A készletérték-jelentések részletes adatokat tartalmaznak a tényleges és pénzügyi készletmennyiségről és -összegekről.
author: banluo-ms
ms.date: 10/19/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: banluo
ms.search.validFrom: 2021-10-19
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 4ad85058c8743895185d3da2e8975711f1e3bc2c
ms.sourcegitcommit: ba10ba2cd4fb4267afb5aacae4f6a52aa2456e7e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/11/2021
ms.locfileid: "7798405"
---
# <a name="inventory-value-report-examples-and-logic"></a>Készletérték-jelentés – példák és logika

[!include [banner](../includes/banner.md)]

A készletérték-jelentések részletes adatokat tartalmaznak a tényleges és pénzügyi készletmennyiségről és -összegekről. Ez a témakör néhány példát mutat be az egyes készletérték-jelentéseken megjelenő eredményekre.

Az egyes típusú készletérték-jelentések generálásról és használatával kapcsolatos további tudnivalókat lásd a [Készletérték-jelentéseknél](inventory-value-report-storage.md).

## <a name="sample-data-that-is-used-in-these-examples"></a>A példákban használt mintaadatok

Az ebben a témakörben szereplő példák az ebben a szakaszban ismertetett minta tranzakciós adatokon alapulnak.

### <a name="storage-dimension-setup"></a>Tárolásidimenzió beállítása

A példarendszer a tárolási dimenziók következő beállítását tartalmazza.

| Név | Aktív | Tényleges készlet | Pénzügyi készlet |
|---|---|---|---|
| Webhely | Igen | Igen | Igen |
| Raktár | Igen | Igen | Nincs |

### <a name="inventory-model"></a>Készletmodell

A példában a kiadott termékek készletmodellje FIFO, és a készletmodell Önköltségi ár mezője a Tényleges értékkel *·* való beszámításra van **·** *beállítva*.

### <a name="inventory-transactions"></a>Készlettranzakciók

A példa rendszer a B0001 cikkszámú kiadott termék következő készlettranzakcióit *·* tartalmazza.

| Hivatkozás | Hely | Raktár | Fogadás | Probléma | Tényleges dátum | Pénzügyi dátum | Mennyiség | Költség összege | Tényleges önköltségi érték |
|---|---|---|---|---|---|---|---|---|---|
| Beszerzési rendelés | 1 | 11 | Beszerezve | | március 15. | március 15. | 10 | 1000 | 1000 |
| Beszerzési rendelés | 2 | 21 | Beszerezve | | március 15. | március 15. | 10 | 2,000 | 2,000 |
| Beszerzési rendelés | 1 | 11 | Bevételezve | | április 15. | | 5 | | 375 |
| Átmozgatási rendelés | 1 | 11 | | Eladva | május 2. | május 2. | -5 | -458,33 | -458,33 |
| Átmozgatási rendelés | 1 | 12 | Beszerezve | | május 2. | május 2. | 5 | 458.33 | 458.33 |
| Értékesítési rendelés | 1 | 12 | | Eladva | május 3. | május 3. | -1 | -91,67 | -91,67 |

### <a name="inventory-value-report-configuration"></a>Készletérték-jelentés konfigurációja

A példarendszer egy készletérték-jelentési konfigurációt tartalmaz, amely a következő beállításokat tartalmazza:

- **Tartomány:** *feladási dátum*
- **Készlet:** *Igen*
- **Átlagos egységköltség számítása:** *Igen*
- **Összes mennyiség és érték:** *Igen*
- **Hely, nézet:** *kijelölve*
- **Erőforrás-azonosító, nézet:** *Igen*
- **Szint:** *Összegek*

## <a name="inventory-value-report-example-1"></a>Készletérték-jelentés – 1. példa

Az alábbi táblázat és ábrák az ebben a témakörben korábban ismertetett mintaadatok és jelentéskonfigurációk használata esetén mutatják be az eredményeket.

| Erőforrás típusa | Erőforrás | Hely | Hivatkozás | Készlet: pénzügyi mennyiség | Készlet: pénzügyi összeg | Készlet: feladott tényleges mennyiség | Készlet: feladott tényleges összeg | Készlet: mennyiség | Készlet: összeg | Átlagos egységenkénti költség |
|---|---|---|---|---|---|---|---|---|---|---|
| Anyag | B0001 | 1 | Záró egyenleg | 9.00 | 908.33 | 5.00 | 375.00 | 14.00 | 1,283.33 | 91.67 |
| Anyag | B0001 | 2 | Záró egyenleg | 10,00 | 2,000.00 | 0,00 | 0,00 | 10,00 | 2,000.00 | 200.00 |

### <a name="standard-inventory-value-report-for-example-1"></a>Normál készletérték-jelentés, például 1

Az alábbi ábra a szokásos **készletérték-jelentést** mutatja be, például 1. (Válassza ki az ábrát egy nagyobb verzió megnyitásához.)

[![Készletérték-jelentés, például 1.](media/inventory-value-report-ex1-small.png "Készletérték-jelentés, például 1")](media/inventory-value-report-ex1.png)

### <a name="inventory-value-report-storage-report-for-example-1"></a>Készletérték-jelentés tárolási jelentése, például 1

A következő ábra a **Készletérték-jelentés tárolási jelentését mutatja** be, például 1. (Válassza ki az ábrát egy nagyobb verzió megnyitásához.)

[![Készletérték-jelentés tárolási jelentése, például 1.](media/inventory-value-report-storage-ex1-small.png "Készletérték-jelentés tárolási jelentése, például 1")](media/inventory-value-report-storage-ex1.png)

## <a name="inventory-value-report-example-2"></a>Készletérték-jelentés – 2. példa

A következő táblázat és ábrák az ebben a témakörben korábban ismertetett mintaadatok használata esetén mutatják be az eredményeket, de a jelentés konfigurálása során a Szint mező értékét a Tranzakciók értékre módosítja, és a jelentés futtatásakor március **·** *·* **·** *15-ére* állíthatja a "Dátumtartomány" mezőt.

| Erőforrás típusa | Erőforrás | Hely | Dátum | Szám | Hivatkozás | Készlet: pénzügyi mennyiség | Készlet: pénzügyi összeg | Készlet: feladott tényleges mennyiség | Készlet: feladott tényleges összeg | Készlet: mennyiség | Készlet: összeg |
|---|---|---|---|---|---|---|---|---|---|---|---|
| Anyag | B0001 | 1 | 3/15/2021 | 00000126 | Beszerzési rendelés | 0,00 | 0,00 | 10,00 | 1,000.00 | **10.00** | **1,000.00** |
| Anyag | B0001 | 1 | 3/15/2021 | 00000126 | Beszerzési rendelés | 10,00 | 1,000.00 | -10,00 | -1 000,00 | **0.00** | **0.00** |
| Anyag | B0001 | 1 | 4/15/2021 | 00000128 | Beszerzési rendelés | 0,00 | 0,00 | 5.00 | 375.00 | **5.00** | **375.00** |
| Anyag | B0001 | 1 | 5/2/2021 | 000003 | Átmozgatási rendelés szállítása | -5,00 | -458,33 | 0,00 | 0,00 | **-5.00** | **-458.33** |
| Anyag | B0001 | 1 | 5/2/2021 | 000003 | Átmozgatási rendelés bevételezése | 5.00 | 458.33 | 0,00 | 0,00 | **5.00** | **458.33** |
| Anyag | B0001 | 1 | 5/3/2021 | 000835 | Értékesítési rendelés | 0,00 | 0,00 | -1.00 | -91,67 | **-1.00** | **-91.67** |
| Anyag | B0001 | 1 | 5/3/2021 | 000835 | Értékesítési rendelés | -1.00 | -91,67 | 1,00 | 91.67 | **0.00** | **0.00** |
| Anyag | B0001 | 2 | 3/15/2021 | 00000127 | Beszerzési rendelés | 0,00 | 0,00 | 10,00 | 2,000.00 | **10.00** | **2,000.00** |
| Anyag | B0001 | 2 | 3/15/2021 | 00000127 | Beszerzési rendelés | 10,00 | 2,000.00 | -10,00 | -2000,00 | **0.00** | **0.00** |
| Anyag | B0001 | 2 | 5/2/2021 | 000003 | Átmozgatási rendelés szállítása | 5.00 | 458.33 | 0,00 | 0,00 | **5.00** | **458.33** |
| Anyag | B0001 | 2 | 5/2/2021 | 000003 | Átmozgatási rendelés bevételezése | -5,00 | -458,33 | 0,00 | 0,00 | **-5.00** | **-458.33** |

### <a name="standard-inventory-value-report-for-example-2"></a>Normál készletérték-jelentés, például 2

Az alábbi ábra a szokásos **készletérték-jelentést** mutatja be, például 2. (Válassza ki az ábrát egy nagyobb verzió megnyitásához.)

[![Készletérték-jelentés, például 2.](media/inventory-value-report-ex2-small.png "Készletérték-jelentés, például 2")](media/inventory-value-report-ex2.png)

### <a name="inventory-value-report-storage-report-for-example-2"></a>Készletérték-jelentés tárolási jelentése, például 2

A következő ábra a Készletérték-jelentés tárolási jelentését mutatja **·** be, például 2. (Válassza ki az ábrát egy nagyobb verzió megnyitásához.)

[![Készletérték-jelentés tárolási jelentése, például 2.](media/inventory-value-report-storage-ex2-small.png "Készletérték-jelentés tárolási jelentése, például 2")](media/inventory-value-report-storage-ex2.png)

## <a name="inventory-value-report-example-3"></a>Készletérték-jelentés – 3. példa

Javasoljuk, hogy újraszámítás vagy készletzárás után futtasson készletérték-jelentéseket, hogy az újraszámítás vagy készletzárás hatással legyen az újraszámítás vagy készletzárás által érintett tranzakciókra és összegekre.

A következő alszakaszok mutatják be a készlet május 30-ig való zárása után létrehozott készletérték-jelentéseket.

### <a name="example-3-when-the-totals-level-is-used"></a>3. példa az Összegszint használatakor

Az alábbi táblázat a témakörben korábban ismertetett mintaadatok és jelentéskonfigurációk használata esetén mutatja be az eredményeket. (A jelentés konfigurációjában a **A** Szint mező az Összegek *értékre van állítva.)*

| Erőforrás típusa | Erőforrás | Hely | Hivatkozás | Készlet: pénzügyi mennyiség | Készlet: pénzügyi összeg | Készlet: feladott tényleges mennyiség | Készlet: feladott tényleges összeg | Készlet: mennyiség | Készlet: összeg | Átlagos egységenkénti költség |
|---|---|---|---|---|---|---|---|---|---|---|
| Anyag | B0001 | 1 | Záró egyenleg | 9.00 | 900.00 | 5.00 | 375.00 | 14.00 | 1,275.00 | 91.07 |
| Anyag | B0001 | 2 | Záró egyenleg | 10,00 | 2,000.00 | 0,00 | 0,00 | 10,00 | 2,000.00 | 200.00 |

### <a name="example-3-when-the-transactions-level-is-used"></a>3. példa a Tranzakciószint használata esetén

Az alábbi táblázat bemutatja az eredményeket, amikor a témakörben korábban ismertetett mintaadatokat használja, de a jelentés konfigurációjában a Szint mező értékét Át kell változtatni Tranzakciók **·** *·* értékre.

| Erőforrás típusa | Erőforrás | Hely | Dátum | Szám | Hivatkozás | Készlet: pénzügyi mennyiség | Készlet: pénzügyi összeg | Készlet: feladott tényleges mennyiség | Készlet: feladott tényleges összeg | Készlet: mennyiség | Készlet: összeg |
|---|---|---|---|---|---|---|---|---|---|---|---|
| Anyag | B0001 | 1 | 3/15/2021 | 00000126 | Beszerzési rendelés | 0,00 | 0,00 | 10,00 | 1,000.00 | 10,00 | 1,000.00 |
| Anyag | B0001 | 1 | 3/15/2021 | 00000126 | Beszerzési rendelés | 10,00 | 1,000.00 | -10,00 | -1 000,00 | 0,00 | 0,00 |
| Anyag | B0001 | 1 | 4/15/2021 | 00000128 | Beszerzési rendelés | 0,00 | 0,00 | 5.00 | 375.00 | 5.00 | 375.00 |
| Anyag | B0001 | 1 | 5/2/2021 | 000003 | Átmozgatási rendelés szállítása | -5,00 | -458,33 | 0,00 | 0,00 | -5,00 | -458,33 |
| Anyag | B0001 | 1 | 5/2/2021 | 000003 | Átmozgatási rendelés bevételezése | 5.00 | 458.33 | 0,00 | 0,00 | 5.00 | 458.33 |
| Anyag | B0001 | 1 | 5/3/2021 | 000835 | Értékesítési rendelés | 0,00 | 0,00 | -1.00 | -91,67 | -1.00 | -91,67 |
| Anyag | B0001 | 1 | 5/3/2021 | 000835 | Értékesítési rendelés | -1.00 | -91,67 | 1,00 | 91.67 | 0,00 | 0,00 |
| Anyag | B0001 | 1 | 5/31/2021 | 000835 | Értékesítési rendelés | 0,00 | -8.33 | 0,00 | 0,00 | 0,00 | -8.33 |
| Anyag | B0001 | 1 | 5/31/2021 | 000003 | Átmozgatási rendelés szállítása | 0,00 | -41.67 | 0,00 | 0,00 | 0,00 | -41.67 |
| Anyag | B0001 | 1 | 5/31/2021 | 000003 | Átmozgatási rendelés bevételezése | 0,00 | 41.67 | 0,00 | 0,00 | 0,00 | 41.67 |
| Anyag | B0001 | 2 | 3/15/2021 | 00000127 | Beszerzési rendelés | 0,00 | 0,00 | 10,00 | 2,000.00 | 10,00 | 2,000.00 |
| Anyag | B0001 | 2 | 3/15/2021 | 00000127 | Beszerzési rendelés | 10,00 | 2,000.00 | -10,00 | -2000,00 | 0,00 | 0,00 |
| Anyag | B0001 | 2 | 5/2/2021 | 000003 | Átmozgatási rendelés szállítása | 5.00 | 458.33 | 0,00 | 0,00 | 5.00 | 458.33 |
| Anyag | B0001 | 2 | 5/2/2021 | 000003 | Átmozgatási rendelés bevételezése | -5,00 | -458,33 | 0,00 | 0,00 | -5,00 | -458,33 |
| Anyag | B0001 | 2 | 5/31/2021 | 000003 | Átmozgatási rendelés szállítása | 0,00 | 41.67 | 0,00 | 0,00 | 0,00 | 41.67 |
| Anyag | B0001 | 2 | 5/31/2021 | 000003 | Átmozgatási rendelés bevételezése | 0,00 | -41.67 | 0,00 | 0,00 | 0,00 | -41.67 |
