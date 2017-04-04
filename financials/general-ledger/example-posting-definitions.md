---
title: "Feladásdefiníciók"
description: "Ez a cikk példákat megjelenítése feladásdefiníciók kötelezettségvállalások a beszerzési rendelés és a költségvetési előirányzatok felhasználásáról."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: JournalizingDefinition, JournalizingDefinitionTrans
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 15772
ms.assetid: 3864e4da-853f-403d-b906-79631d80b363
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 4afe88012b28b74e25c30befb261b5ea2f633ce9
ms.openlocfilehash: 1091a37007146b36ba05aee3d047c4ae58f87168
ms.lasthandoff: 03/31/2017


---

# <a name="posting-definition-examples"></a>Feladási példák meghatározása

Ez a cikk példákat megjelenítése feladásdefiníciók kötelezettségvállalások a beszerzési rendelés és a költségvetési előirányzatok felhasználásáról.

Mielőtt ezt a témakört elolvassa, a feladási definíciókkal és a tranzakciós feladási feladási definíciókkal tisztában kell lennie. Információ: lásd a [Feladási definíciók](posting-definitions.md) részt. Az alábbi példákat be kell állítani a **Feladási definíciók** oldalon. Mindegyik példa ezeket a szakaszokat tartalmazza:

-   Feladási definíció – Egyeztetési feltételek
-   Feladási definíció – Generált tételek
-   Tranzakciók a számlákkal, a dimenzióértékekkel és összegekkel.
-   A feladási definíció által létrehozott főkönyvi bejegyzések

Egyezés esetén a számlák és dimenzióértékek között az **Egyeztetési feltételek** ablakban a feladási definíciónál és a számláknál és dimenzióértékeknél a tranzakcióm, főkönyvi bejegyzések készülnek a **Létrehozott bejegyzések** ablak alapján a feladási definíciónál. 
> [!NOTE]
> Feladási definíciót társítani egy adott tranzakció típusát, használja a **Tranzakció-feladásdefiníciók** oldalon. Miután feladási definíciót kapcsolhatja a tranzakció típusát, és válassza ki **Feladásdefiníciók használata** a a **főkönyvi paraméterek** lap, minden a kijelölt tranzakció típusú tranzakciókhoz használja feladásdefiníciók.

## <a name="example-purchase-order-encumbrances"></a>Példa: beszerzési rendelések terhelései
Amikor engedélyezi a kötelezettségvállalás feldolgozását a **Kötelezettségvállalási folyamat engedélyezése** lehetőség kiválasztásával a **Főkönyvi paraméterek** lapon, feladásdefiníciókat kell használni a kötelezettségvállalások rögzítéséhez főkönyvi számlában, bármely lefoglalandó számla esetében. A legtöbb esetben az összes költségszámla fenn van tartva a mérlegben. 

Feladásdefiníciók a kötelezettségvállalásokhoz a **Beszerzés** modulban a **Feladásdefiníciók** oldalon állíthatók be. Ezután a **Beszerzés** területen a **Tranzakció-feladásdefiníciók** lapon kiválaszthatja a **Beszerzési rendelés** tranzakciótípust a feladási definíciók beszerzési rendeléshez való társításához. 

A beszerzési rendelés kötelezettségvállalások összes bizonylattranzakciójának ki kell futnia nullára (vagyis a tartozás legyen ugyanannyi, mint a követelés) minden egyes bizonylatdimenzióban.

### <a name="posting-definition--match-criteria"></a>Feladási definíció – Egyeztetési feltételek

| Számlastruktúra       | Számlaszám egyeztetése | Prioritás |
|-------------------------|----------------------|----------|
| Számlastruktúra - P&L (eredmény) | \*                   | 1        |

* Az üres érték a **Számlaszám egyeztetése** mezőben azt jelzi, hogy az összes egyeztetési számla a definiált számlastruktúrában része az egyeztetési szabályoknak.

### <a name="posting-definition--generated-entries"></a>Feladási definíció – Generált tételek

| Számlastruktúra | Létrehozott számlaszám                    | Létrehozott terhelés/jóváírás |
|-------------------|---------------------------------------------|------------------------|
| Egyenleg           | 300143 --(Kötelezettségvállalási számla)             | Egyező                   |
| Egyenleg           | 300144 --(Tartalék a kötelezettségvállalási számlához) | Egyensúlyozás              |

### <a name="transactions-with-the-accounts-dimension-values-and-amounts"></a>Tranzakciók a számlákkal, a dimenzióértékekkel és összegekkel.

A számlák és dimenzióértékek vagy a beszerzési rendelés sorához beírt könyvelési felosztásokból származnak, vagy a számlák és dimenziók, szállítók, cikkek, kategóriák és dimenziók sablonjaihoz az alapbeállítások alapján automatikusan generált számlákból és dimenziókból.

| Számla + dimenzió           | Tartozik  | Követel | Megjegyzés |
|--------------------------------|--------|--------|---------|
| 606400-OU\_1-OU\_3566-képzés | 250,00 |        |         |

### <a name="ledger-entries-generated-from-the-posting-definition"></a>A feladási definíció által létrehozott főkönyvi bejegyzések

A létrehozott főkönyvi bejegyzések a kötelezettségvállalások rögzítésére jönnek létre.

| Számla + dimenzió           | Tartozik  | Követel | Megjegyzés |
|--------------------------------|--------|--------|---------|
| 300143-OU\_1-OU\_3566-képzés | 250,00 |        |         |
| 300144-OU\_1-OU\_3566-képzés |        | 250,00 |         |

Az alábbi példában minden számla esetében, amely része a Számlastruktúrának - a P&L (eredmény) megfelel a feladási definíció kritériumainak. Ezért, ha 606500-OU\_1-OU\_3566-képzés értékelik, a létrehozott bejegyzések jönnek létre a fiókok definiált a **generálta tételek** ablak Könyvelés meghatározását.

## <a name="example-budget-appropriations"></a>Példa: Költségvetési előirányzatok
Amikor engedélyezi a költségvetési előirányzatot a **Költségvetési előirányzat engedélyezése** bejelölésével a **Főkönyvi paraméterek** lapon, feladásdefiníciókat kell használni a költségvetési tételjegyzék-bejegyzések főkönyvbe történő rögzítéséhez. Amikor egy költségvetés-ellenőrzési konfiguráció aktív, és be van kapcsolva, feladásdefiníciók és tranzakció-feladásdefiníciók használhatók a bejegyzések rögzítésére az előirányzatokról, változatokról, átvitelekről, projektekről, tárgyi eszközökről és kereslet-kínálati előrejelzésekről a főkönyvbe. 

Egy feladásdefiníció beállításához olyan költségvetési tételjegyzék-bejegyzéseknél, amelyeknek a költségvetési típusa **Eredeti költségvetés**, és az előirányzatok engedélyezve vannak, jelölje be a **Költségvetés** modult a **Feladásdefiníciók** lapon. Ezután a **Költségvetés** területen, a **Tranzakció-feladásdefiníciók** lapon költségvetési kódok segítségével a feladásdefiníciót társítani tudja a költségvetési tételjegyzék-bejegyzésekkel, amelyeknek a költségvetési típusa **Eredeti költségvetés**. 

Ha engedélyezve vannak a költségvetési előirányzatok és a feladásdefiníciók, a költségvetési tételjegyzék-bejegyzések rögzítésre kerülnek a költségvetés-ellenőrzésre és a főkönyvbe.

### <a name="posting-definition--match-criteria"></a>Feladási definíció – Egyeztetési feltételek

| Számlastruktúra       | Számlaszám egyeztetése | Prioritás |
|-------------------------|----------------------|----------|
| Számlastruktúra - P&L (eredmény) | \*                   | 1        |

* Az üres érték a **Számlaszám egyeztetése** mezőben azt jelzi, hogy az összes egyeztetési számla a definiált számlastruktúrában része az egyeztetési szabályoknak.

### <a name="posting-definition--generated-entries"></a>Feladási definíció – Generált tételek

| Számlastruktúra | Létrehozott számlaszám              | Létrehozott terhelés/jóváírás |
|-------------------|---------------------------------------|------------------------|
| Számlastruktúra | 300145 - -(Becsült bevételhez használt számla) | Egyező                   |
| Számlastruktúra | 300146 --(Előirányzati számla)     | Egyensúlyozás              |

### <a name="transactions-with-the-accounts-dimension-values-and-amounts"></a>Tranzakciók a számlákkal, a dimenzióértékekkel és összegekkel.

A számlákat, a dimenzióértékeket és az összegeket a költségvetési számlabejegyzéshez a **Költségvetési tételjegyzék-bejegyzés** oldalon adhatja meg.

| Számla + dimenzió           | Tartozik | Követel | Megjegyzés |
|--------------------------------|-------|--------|---------|
| 606400-OU\_1-OU\_3566-képzés |       | 250,00 |         |

### <a name="ledger-entries-generated-from-the-posting-definition"></a>A feladási definíció által létrehozott főkönyvi bejegyzések

A generált főkönyvi bejegyzések az eredeti költségvetés rögzítésére jönnek létre az egyes dimenziókban.

| Számla + dimenzió           | Tartozik  | Követel | Megjegyzés |
|--------------------------------|--------|--------|---------|
| 300145-OU\_1-OU\_3566-képzés |        | 250,00 |         |
| 300146-OU\_1-OU\_3566-képzés | 250,00 |        |         |

Az alábbi példában minden számla esetében, amely része a Számlastruktúrának - a P&L (eredmény) megfelel a feladási definíció kritériumainak. Ezért, ha 606400-OU\_1-OU\_3566-képzés értékelik, a létrehozott könyvelési tételek jönnek létre.




