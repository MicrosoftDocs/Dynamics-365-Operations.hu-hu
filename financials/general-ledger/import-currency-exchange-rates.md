---
title: "Devizaárfolyamok importálása"
description: "Ha egy jogi személy devizában kapott számlák, elengedhetetlen a deviza alakítani a saját pénznemben. Ez azt jelenti, hogy különböző pénznemekben legfrissebb átváltási árfolyam szükség. Ez a témakör áttekintést a szükséges beállításokat és a feldolgozás átváltási árfolyam-szolgáltatók, mint az Európai Központi Bank és az Orosz Központi Bank által az interneten közzétett referencia-kamatlábnak importálásához."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ExchangeRateProviderConfiguration
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 261374
ms.assetid: b2b22868-de68-439f-914c-78c6930b7340
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: bf66a1b1c9314b454223274810a21913d54b702d
ms.lasthandoff: 03/31/2017


---

# <a name="import-currency-exchange-rates"></a>Devizaárfolyamok importálása

Ha egy jogi személy devizában kapott számlák, elengedhetetlen a deviza alakítani a saját pénznemben. Ez azt jelenti, hogy különböző pénznemekben legfrissebb átváltási árfolyam szükség. Ez a témakör áttekintést a szükséges beállításokat és a feldolgozás átváltási árfolyam-szolgáltatók, mint az Európai Központi Bank és az Orosz Központi Bank által az interneten közzétett referencia-kamatlábnak importálásához.

A következő részekben használt beállítása és feldolgozása az átváltási árfolyamok behozatalát az információáramlást.

## <a name="configure-an-exchange-rate-provider"></a>Az árfolyam-szolgáltató konfigurálása
Árfolyamok importálása előtt be kell állítania a a szolgáltatók, akik felajánlják az árfolyamok által igényelt információkat. Használja a **árfolyam-szolgáltatók beállítása** oldalra, ahol kiválaszthatja az árfolyam-szolgáltatók. Árfolyam-szolgáltatók egyes műveletek a Microsoft Dynamics 365 demó adatok részét képezik. A következő táblázat az ezen a lapon a vezérlőelemek leírását.

|           |                                                                                                                                                                                                                             |
|-----------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Field** | **Description**                                                                                                                                                                                                             |
| **Name**  | Az árfolyam-szolgáltató neve.                                                                                                                                                                                     |
| **Kulcs**   | A szolgáltató által igényelt specifikus egyes konfigurációs adatok egyedi azonosítója. Ezt az információt a rendszer automatikusan az egyes árfolyam-szolgáltató hozzáadásához kattintásra a **hozzáadása** gombra. |
| **Value** | Az egyes kulcsok adatai. Ezt az információt ad hozzá minden árfolyam-szolgáltató hozzáadásához kattintásra a **hozzáadása** gombra.                                                                                         |

## <a name="import-currency-exchange-rates"></a>Devizaárfolyamok importálása
Az árfolyam szolgáltatók forrásból importálni az árfolyamokat, és beállíthatja azokat a a **árfolyamok** oldalon. Használja a **Devizaárfolyamok importálása** lap importálni az árfolyamokat. A következő táblázat mutatja az importálási folyamat sikeres teljesítéséhez szükséges mezőket.

|                                        |                                                                                                                                                                                                                                                                                                                                                                             |
|----------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Field**                              | **Description**                                                                                                                                                                                                                                                                                                                                                             |
| **Exchange rate type**                 | Az árfolyam típusa.                                                                                                                                                                                                                                                                                                                                                      |
| **Exchange rate provider**             | Árfolyam-szolgáltató.                                                                                                                                                                                                                                                                                                                                                  |
| **Import as of**                       | Ez a paraméter kezeli-e importálni a mai napon vagy dátumtartományban. Ha használandó dátumtartományt, vagy jelölje ki a kezdő és záró dátumát.                                                                                                                                                                                                                |
| **Create necessary currency pairs**    | Ezt a jelölőnégyzetet párok, automatikus létrehozását kezeli, ha az importált párok nem léteznek. Ez a beállítás nem érhető el az egyes szolgáltatók lehet.                                                                                                                                                                                               |
| **Override existing exchange rates**   | Ezt a jelölőnégyzetet kezeli a két pénznem átváltási árfolyama a frissítést, ha létezik már egy bizonyos dátumra vonatkozó átváltási árfolyam. Ha nem jelöli be ezt a jelölőnégyzetet, a program nem importálja a megadott dátumokra vonatkozóan az átváltási árfolyamot, ha már létezik egy másik árfolyam.                                                                                       |
| **Prevent import on national holiday** | Ezt a jelölőnégyzetet a dátum munkaszüneti nap, az átváltási árfolyam az importálás kezeli. Például jelölje be a jelölőnégyzetet, és az Európai Központi Bank, az árfolyam-szolgáltató használata, ha a rendszer nem frissíti az árfolyamot az aktuális jogi személyhez kapcsolódó munkaszüneti. Ez a beállítás nem érhető el az egyes szolgáltatók lehet. |




