---
title: Devizaárfolyamok importálása
description: Ez a témakör a devizaárfolyam-szolgáltatók által közzétett árfolyam-referenciaértékekkel kapcsolatos követelményekkel kapcsolatban tartalmaz tájékoztatást.
author: EvgenyPopovMBS
manager: AnnBe
ms.date: 03/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ExchangeRateProviderConfiguration
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 261374
ms.assetid: b2b22868-de68-439f-914c-78c6930b7340
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: 74acfab28d45fc75c4ecd595aeba1fb1e13bbcff
ms.sourcegitcommit: c69926b4285cb2ec2d9ce1ad72d1cb852024dd5e
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/18/2020
ms.locfileid: "3138065"
---
# <a name="import-currency-exchange-rates"></a>Devizaárfolyamok importálása

[!include [banner](../includes/banner.md)]

Ha egy jogi személy devizában kapott számlákat, a devizát át kell váltani a saját pénznembe. Ez azt jelenti, hogy különböző pénznemekre nézve szükség van a legfrissebb átváltási árfolyamra. Ez a témakör áttekintést ad a devizaárfolyam-szolgáltatók, mint az Európai Központi Bank és az Orosz Központi Bank által közzétett referencia-devizaárfolyamok feldolgozásához és importálásához szükséges beállításokról.

Az alábbi szakaszok a devizaárfolyamok importálásának beállításához és feldolgozásához használt teljes információáramlást leírják.

## <a name="configure-an-exchange-rate-provider"></a>Árfolyam-szolgáltató konfigurálása
Árfolyamok importálása előtt be kell állítani az árfolyamokat biztosító szolgáltatók által igényelt információkat. Használja az **Árfolyam-szolgáltatók konfigurálása** oldalt az árfolyam-szolgáltatók kiválasztásához. Egyes árfolyam-szolgáltatók a Dynamics 365 Finance-ben található bemutató adatokban is megtalálhatók. A következő táblázatban megtalálható az oldal vezérlőelemeinek leírása.

|           |                                                                                                                                                                                                                             |
|-----------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Mező** | **Leírás**                                                                                                                                                                                                             |
| **Név**  | Az árfolyam-szolgáltató neve.                                                                                                                                                                                     |
| **Kulcs**   | A szolgáltató által igényelt specifikus egyes konfigurációs adatok egyedi azonosítója. Ez az információ automatikusan hozzáadódik minden egyes olyan árfolyam-szolgáltatóhoz, amelyet hozzáad. |
| **Value** | Az egyes kulcsok adatai. Ez az információ hozzáadódik minden egyes olyan árfolyam-szolgáltatóhoz, amelyet hozzáad.                                                                                         |

## <a name="import-currency-exchange-rates"></a>Devizaárfolyamok importálása
Az árfolyamokat az árfolyam-szolgáltatók forrásból lehet importálni, majd hozzáadni a **Pénznemárfolyamok** oldalon. Használja a **Devizaárfolyamok importálása** oldalt az árfolyamok importálásához. A következő táblázat bemutatja az importálási folyamat sikeres teljesítéséhez szükséges mezőket.

|                                        |                                                                                                                                                                                                                                                                                                                                                                             |
|----------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Mező**                              | **Leírás**                                                                                                                                                                                                                                                                                                                                                             |
| **Árfolyamtípus**                 | Árfolyam típusa.                                                                                                                                                                                                                                                                                                                                                      |
| **Árfolyam-szolgáltató**             | Árfolyam-szolgáltató.                                                                                                                                                                                                                                                                                                                                                  |
| **Importálás a következő dátum szerint:**                       | Ez a paraméter vezérli, hogy az imortálás az aktuális dátum szerint vagy egy megadott dátumtartományban történjen-e. Ha dátumtartományt kíván használni, adja meg vagy válassza ki a kezdő és a záró dátumot.                                                                                                                                                                                                                |
| **A szükséges pénznempárok létrehozása**    | Ez a jelölőnégyzet vezérli a devizapárok automatikus létrehozását, ha az importált devizapárok nem léteznek. Egyes szolgáltatóknál lehet, hogy ez a beállítás nem érhető el.                                                                                                                                                                                               |
| **Meglévő árfolyamok felülbírálása**   | Ez a jelölőnégyzet vezérli a devizapár meglévő átváltási árfolyamának frissítését akkor, ha egy bizonyos dátumra vonatkozóan már létezik átváltási árfolyam. Ha nem jelöli be ezt a jelölőnégyzetet, a program nem importálja a megadott dátumokra vonatkozóan az átváltási árfolyamot, ha már létezik egy másik árfolyam.                                                                                       |
| **Importálás tiltása ünnepnapokon** | Ez a jelölőnégyzet vezérli az átváltási árfolyam importálását munkaszüneti napnak számító dátumokon. Például ha bejelöli a jelölőnégyzetet, és az Európai Központi Bankot használja árfolyam-szolgáltatóként, a rendszer nem frissíti az árfolyamot az olyan munkaszüneti napokon, amelyek érvényesek az aktuális jogi személyre. Egyes szolgáltatóknál lehet, hogy ez a beállítás nem érhető el. |
| **Előző napról származó árfolyam** | Ez a jelölőnégyzet akkor érhető el, ha **EKB importálása az aktuális vagy előző dátumon** funkciót engedélyezi a **Funkció kezelése** lapon. Ez a jelölőnégyzet csak a szolgáltatónál, az *Európai Központi Banknál* érhető el. A jelölőnégyzet kiválasztásával importálhatja a pénznem az Európai Központi Bank által az azt megelőző munkanapon körülbelül 16 órakor (CET) közzétett árfolyamát. Alapértelmezésben a jelölőnégyzet be van jelölve. A jelölőnégyzet kiválasztásának törlésével importálhatja az ugyanazon a munkanapon közzétett átváltási árfolyamot.  |
