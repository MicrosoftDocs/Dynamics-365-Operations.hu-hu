---
title: Készpénzáttekintés Power BI-tartalom
description: Ez a témakör a Készpénzes áttekintés tartalmát Power BI írja le. Leírja, hogy hogyan kell hozzáférni a tartalomcsomagban szereplő jelentésekhez, és információkat nyújt a tartalomcsomag összeállításához előzőleg használt entitásokkal és adatmodellekkel kapcsolatban.
author: angelad116
ms.date: 07/16/2020
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: BankTreasurerWorkspace
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: angelading
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: a255afac3aa68f3a48b21e4d2fbfb046a9de603c
ms.sourcegitcommit: 0b7a034e644f4d93fe55c7baca5a3f89dbe56898
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/14/2022
ms.locfileid: "9151999"
---
# <a name="cash-overview-power-bi-content"></a>Készpénzáttekintés Power BI-tartalom

[!include [banner](../includes/banner.md)]

Ez a témakör a Készpénzes áttekintés **tartalmát** Microsoft Power BI írja le. Leírja, hogy hogyan kell hozzáférni a tartalomcsomagban szereplő jelentésekhez, és információkat nyújt a tartalomcsomag összeállításához előzőleg használt entitásokkal és adatmodellekkel kapcsolatban.

## <a name="overview"></a>Áttekintés

A **Készpénzáttekintés** Power BI-tartalom azon személyeknek szól, akik a szervezetük készpénzéért felelősek. A **Készpénzáttekintés** Power BI-tartalom áttekintést nyújt a pénzforgalmáról. Emellett előrejelzéseket kínál, melyek segíthetnek, hogy jobb döntéseket hozzon, és ezáltal javíthassa a pénzforgalom állapotát. A készpénzt jogi személy, pénznem és bankszámla szerint elemezheti, hogy jobban megértse a többleteket és hiányokat.

## <a name="setup-needed-to-view-power-bi-content"></a>A Power BI-tartalom megtekintéséhez beállítás szükséges

A következő beállításokat el kell végezni ahhoz, hogy az adatok megjelenjenek a **Készpénz-áttekintés** és **Banki menedzsment** Power BI megjelenítésekben.

1. Nyissa meg a **Rendszeradminisztráció > Beállítás > Rendszerparaméterek** pontot a **Rendszerpénznem** és a **Rendszerváltási árfolyam** beállításához.
2. Lépjen a **Főkönyv > Naptárak > Pénzügyi naptárak** részre, hogy ellenőrizze az aktív időszakhoz hozzárendelt pénzügyi naptár dátumait.
3. Ugrás a **Főkönyv > Beállítás > Főkönyv** részre a **Könyvelési pénznem** és az **Árfolyamtípus** beállításához.
4. Adja meg az árfolyamokat a tranzakció pénznemei és a könyvelési pénznem, a könyvelési pénznem és a rendszer pénzneme, a könyvelési pénznem és a banki pénznemek között. Lépjen ide: **Főkönyv > Pénznemek > Pénznemek árfolyamtípusai**.
5. Pénzforgalmi előrejelzés konfigurálása és futtatása. A Pénzforgalmi előrejelzés beállításával kapcsolatos további tudnivalókat lásd: [Pénzforgalmi előrejelzés](./cash-flow-forecasting.md). 
6. Lépjen a **Rendszerfelügyelet > Beállítás > Entitástár** részre a **LedgerCovLiquidityMeasurement** összesítő mérték frissítéséhez.

## <a name="accessing-the-power-bi-content"></a>A Power BI tartalom elérése

A **Készpénzáttekintés** Power BI-tartalom jelentései a **Készpénzáttekintés** és a **Bankszámla kezelése** munkaterületen jelennek meg.

Ha adatokkal együtt szeretné megtekinteni a pénzforgalmi előrejelzések jelentéseit, akkor először futtatnia kell az előrejelzés számítási folyamatát a Készpénz- és bankkezelés terület **Pénzforgalmi előrejelzések kiszámítása** funkciójánál. Ezt végre kell hajtani az előrejelzésben szereplő mindegyik vállalat esetén.  Ezt követően frissítenie kell a LedgerCovLiquidityMeasurement összesített mértéket az **Entitástár** oldalon.  

Bemutató céllal felvehet pénzforgalom-előrejelzési bemutató adatokat a Demóadatok modul **Adatok generálása** oldaláról.  Ez a szkript adatokat szúr be a pénzforgalmi előrejelzés táblázataiba annak érdekében, hogy gyorsan kitöltse azokat a jelentések számára szükséges adatokkal.  Ez a modul csak akkor érhető el, ha a bemutató adatmodellt telepítették a környezetnél. 

## <a name="reports-that-are-included-in-the-power-bi-content"></a>Jelentések, amelyek a Power BI-tartalomban szerepelnek

A következő táblázat ismerteti a **Készpénzáttekintés** Power BI-tartalom egyes jelentésoldalain található mutatókat.

| Jelentés                                | Tartalom |
|---------------------------------------|----------|
| Készpénzáttekintés – minden vállalat         | <ul><li>Pénzbeáramlások és pénzkiáramlások a rendszer pénznemében</li><li>Előre jelzett pénznemegyenlegek</li><li>Összesített egyenleg a rendszer pénznemében</li><li>Egyenleg jogi személy szerint</li><li>Aznapi tényleges és előrejelzett egyenleg a bankszámla pénznemében</li></ul> |
| Készpénzáttekintés – jelenlegi vállalat       | <ul><li>Pénzbeáramlások és pénzkiáramlások a könyvelési pénznemben</li><li>Előre jelzett pénznemegyenlegek</li><li>Összesített egyenleg a könyvelési pénznemben</li><li>Aznapi tényleges és előrejelzett egyenleg a bankszámla pénznemében</li></ul> |
| Pénzforgalmi előrejelzés – összes vállalat    | <ul><li>Pénzbeáramlások és pénzkiáramlások a rendszer pénznemében</li><li>Napi előrejelzés összegzése</li><li>Előrejelzés részletei</li></ul> |
| Pénzforgalmi előrejelzés – pénznem vállalata | <ul><li>Pénzbeáramlások és pénzkiáramlások a könyvelési pénznemben</li><li>Napi előrejelzés összegzése</li><li>Előrejelzés részletei</li></ul> |
| Pénznem előrejelzése                     | <ul><li>Előre jelzett pénznemegyenlegek</li><li>Napi pénznem összegzése</li><li>Előrejelzés részletei</li></ul> |
| Banki egyenlegek                         | <ul><li>Összesített egyenleg a rendszer pénznemében</li><li>Egyenleg jogi személy szerint</li><li>Aznapi tényleges és előrejelzett egyenleg a bankszámla pénznemében</li><li>Egyenleg bankszámla szerint</li><li>Egyenleg pénznemenként</li></ul> |


## <a name="understanding-the-data-model-and-entities"></a>Adatmodell, illetve entitások ismertetése

A következő táblázat megjeleníti azokat az entitásokat, amelyeken a **Készpénzáttekintés** Power BI-tartalom alapul.

| Entitás                                                                          | Tartalom |
|---------------------------------------------------------------------------------|----------|
| LedgerCovLiquidityMeasurement\_Vállalat                                          | Vállalatok a jelentések szűréséhez |
| LedgerCovLiquidityMeasurement\_Dátum                                             | Dátumok a jelentések szűréséhez |
| LedgerCovLiquidityMeasurement\_LedgerCovForecastActual                          | Jelenlegi banki egyenleg és az utolsó előre jelzett banki egyenleg |
| LedgerCovLiquidityMeasurement\_LedgerCovLiquidity                               | Előrejelzett tranzakció részletes adatai |
| LedgerCovLiquidityMeasurement\_LedgerCovLiquidityInflowOutflowBalanceCompany    | Összegzett pénzbevételek, kiadások és egyenlegek az egyes vállalatok könyvelési pénznemében |
| LedgerCovLiquidityMeasurement\_LedgerCovLiquidityInflowOutflowBalanceEnterprise | Összegzett pénzbevételek, kiadások és egyenlegek az összes vállalatnál a rendszer pénznemében |
| LedgerCovLiquidityMeasurement\_LedgerCovLiquidityTransactionCurrency            | Összegzett nettó tranzakciós összeg és devizaegyenleg a tranzakciós pénznem használatával |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
