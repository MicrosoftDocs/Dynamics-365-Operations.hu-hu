---
title: Kiskereskedelmi árjelentések
description: Ez a cikk áttekintést nyújt az árjelentés funkcióról, amely a kiválogatott termékek várható árváltozásának megtekintésére használható.
author: ShalabhjainMSFT
ms.date: 03/05/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.search.region: global
ms.author: shajain
ms.search.validFrom: 2019-01-18
ms.dyn365.ops.version: AX 10.0.0
ms.custom: 16181
ms.assetid: b1b57734-1406-4ed6-8e28-21c705ee17e2
ms.search.industry: Retail
ms.search.form: ''
ms.openlocfilehash: 09350d15660978126d36199a3b4e93f6be5fe157
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9269027"
---
# <a name="retail-price-reports"></a>Kiskereskedelmi árjelentések

[!include [banner](includes/banner.md)]


Annak érdekében, hogy versenyképes árakat nyújtsanak az ügyfeleknek, a kiskereskedők gyakran módosítják termékeik árait. Üzletvezetők szeretnének könnyen hozzáférni a legutóbbi vagy közelgő árváltozásokhoz hogy azokhoz tervezni lehessen a szükséges erőforrások, amelyek szükségesek a polccímkék módosításához. A Retail 10.0 kiadásában az üzletvezető megnyithatja az **Ár** jelentést a **Minden üzlet \> Üzlet \> Árjelentés** helyen, és az áruházhoz társított termékek frissített árait megtekintheti. 

Az árjelentés engedélyezéséhez az **Árjelentés engedélyezése áruházhoz** paramétert be kell kapcsolni. Ezt a paramétert a **Kereskedelmi paraméterek \> Engedmények \> Vegyes** fülön található. Az **Árjelentés** lap egy különböző konfigurációkat tartalmaz párbeszédpanelt jelenít meg. A rendelkezésre álló onfigurációk az alábbiakban láthatók.

| Konfiguráció | Leírás |
|---|---|
| Kezdő dátum / Záró dátum| A dátumtartomány, amelyhez az árjelentést generálni kell. Az az időtartam jelenleg 7 napra korlátozott. |
| Csatorna| Az áruház, amelyhez az árjelentést generálni kell. |
| A rendelkezésre álló készlettel rendelkező termékek megjelenítése| Ha ez **Igen** értékre van állítva csak azon termékeket árai jelennek meg, amelyeknek van fizikai készlete az üzletben. |
| Változatok árainak megjelenítése | Ha ez **Igen** értékre van állítva alaptermékek mellett a változatok árait is megjeleníti. Ez csak akkor kell **Be** kapcsolni, ha vannak változatspecifikus árak, mivel a sorok száma így nagyon nagy lesz. A jövőbeli kiadásokban elérhetővé tesszük a dimenzióalapú árakat, hogy az üzletvezetők kiválaszthassák azokat a dimenziókat, amelyhez az árak jelenítenek meg. |
| A módosult árral rendelkező termékek megjelenítése | Ha ez **Igen** értékre van állítva csak azokra dátumokra vonatkozóan jeleníti meg az árat, amelyeken az ár megváltozott. Az *Egy nappal előtte* ár a kiválasztott **Kezdő dátumtól** mindig megjelenik, így az üzletvezető egyszerűen azonosíthatja azokat a termékeket, amelyek árai nem módosultak a kijelölt teljes időtartamra, és megtekintheti az aktuális árat is. |

A jelentés generálása után, az Excel-fájl bármilyen további szűrési szükséglethez letölthető. Az árjelentés a termékek árelőzményeinek ellenőrzésére is használható régebbi dátumokon.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
