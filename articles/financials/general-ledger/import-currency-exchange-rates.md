---
title: "Devizaárfolyamok importálása"
description: "Ha egy jogi személy devizában kapott számlákat, a devizát át kell váltani a saját pénznembe. Ez azt jelenti, hogy különböző pénznemekre nézve szükség van a legfrissebb átváltási árfolyamra. Ez a témakör áttekintést ad a devizaárfolyam-szolgáltatók, mint az Európai Központi Bank és az Orosz Központi Bank által az interneten közzétett referencia-devizaárfolyamok feldolgozásához és importálásához szükséges beállításokról."
author: EvgenyPopovMBS
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ExchangeRateProviderConfiguration
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 261374
ms.assetid: b2b22868-de68-439f-914c-78c6930b7340
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: c80f6eec7c4d5129337b6f7869fbd8a4cc978acd
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="import-currency-exchange-rates"></a>Devizaárfolyamok importálása

[!include[banner](../includes/banner.md)]


Ha egy jogi személy devizában kapott számlákat, a devizát át kell váltani a saját pénznembe. Ez azt jelenti, hogy különböző pénznemekre nézve szükség van a legfrissebb átváltási árfolyamra. Ez a témakör áttekintést ad a devizaárfolyam-szolgáltatók, mint az Európai Központi Bank és az Orosz Központi Bank által az interneten közzétett referencia-devizaárfolyamok feldolgozásához és importálásához szükséges beállításokról.

Az alábbi szakaszok a devizaárfolyamok importálásának beállításához és feldolgozásához használt teljes információáramlást leírják.

## <a name="configure-an-exchange-rate-provider"></a>Árfolyam-szolgáltató konfigurálása
Árfolyamok importálása előtt be kell állítani az árfolyamokat biztosító szolgáltatók által igényelt információkat. Használja az **Árfolyam-szolgáltatók konfigurálása** oldalt az árfolyam-szolgáltatók kiválasztásához. Egyes árfolyam-szolgáltatók a Microsoft Dynamics 365 for Finance Operations, Enterprise kiadásban található bemutató adatokban is megtalálhatók. A következő táblázatban megtalálható az oldal vezérlőelemeinek leírása.

|           |                                                                                                                                                                                                                             |
|-----------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Mező** | **Leírás**                                                                                                                                                                                                             |
| **Név**  | Az árfolyam-szolgáltató neve.                                                                                                                                                                                     |
| **Kulcs**   | A szolgáltató által igényelt specifikus egyes konfigurációs adatok egyedi azonosítója. Ez az információ automatikusan hozzáadódik minden egyes olyan árfolyam-szolgáltatóhoz, amelyet a **Hozzáadás** gombbal ad hozzá. |
| **Érték** | Az egyes kulcsok adatai. Ez az információ hozzáadódik minden egyes olyan árfolyam-szolgáltatóhoz, amelyet a **Hozzáadás** gombbal ad hozzá.                                                                                         |

## <a name="import-currency-exchange-rates"></a>Devizaárfolyamok importálása
Az árfolyamokat az árfolyam-szolgáltatók forrásból lehet importálni, majd beállítani a **Pénznemárfolyamok** oldalon. Használja a **Devizaárfolyamok importálása** oldalt az árfolyamok importálásához. A következő táblázat bemutatja az importálási folyamat sikeres teljesítéséhez szükséges mezőket.

|                                        |                                                                                                                                                                                                                                                                                                                                                                             |
|----------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Mező**                              | **Leírás**                                                                                                                                                                                                                                                                                                                                                             |
| **Árfolyamtípus**                 | Árfolyam típusa.                                                                                                                                                                                                                                                                                                                                                      |
| **Árfolyam-szolgáltató**             | Árfolyam-szolgáltató.                                                                                                                                                                                                                                                                                                                                                  |
| **Importálás a következő dátum szerint:**                       | Ez a paraméter vezérli, hogy az imortálás a mai dátum szerint vagy dátumtartományban történjen-e. Ha dátumtartományt kíván használni, adja meg vagy válassza ki a kezdő és a záró dátumot.                                                                                                                                                                                                                |
| **A szükséges pénznempárok létrehozása**    | Ez a jelölőnégyzet vezérli a devizapárok automatikus létrehozását, ha az importált devizapárok nem léteznek. Egyes szolgáltatóknál lehet, hogy ez a beállítás nem érhető el.                                                                                                                                                                                               |
| **Meglévő árfolyamok felülbírálása**   | Ez a jelölőnégyzet vezérli a devizapár meglévő átváltási árfolyamának frissítését akkor, ha egy bizonyos dátumra vonatkozóan már létezik átváltási árfolyam. Ha nem jelöli be ezt a jelölőnégyzetet, a program nem importálja a megadott dátumokra vonatkozóan az átváltási árfolyamot, ha már létezik egy másik árfolyam.                                                                                       |
| **Importálás tiltása ünnepnapokon** | Ez a jelölőnégyzet vezérli az átváltási árfolyam importálását munkaszüneti napnak számító dátumokon. Például ha bejelöli a jelölőnégyzetet, és az Európai Központi Bankot használja árfolyam-szolgáltatóként, a rendszer nem frissíti az árfolyamot az olyan munkaszüneti napokon, amelyek érvényesek az aktuális jogi személyre. Egyes szolgáltatóknál lehet, hogy ez a beállítás nem érhető el. |






