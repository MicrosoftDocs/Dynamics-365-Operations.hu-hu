---
title: Információs kódok és információs kódcsoportok
description: Ez a cikk áttekintést nyújt az infókódokról, az infókód-csoportokról és azok használatáról.
author: mugunthanm
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailInfocodeTable
audience: Application User
ms.reviewer: josaw
ms.custom: 22761
ms.assetid: 99877dba-a6e3-4d88-ba0a-ee5913aea17e
ms.search.region: global
ms.search.industry: Retail
ms.author: mumani
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 2f905fda2224da8fd15a287f20339a9bfd1cab992024c195ca040ce2c1c671d4
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6729119"
---
# <a name="info-codes-and-info-code-groups"></a>Információs kódok és információs kódcsoportok

[!include [banner](includes/banner.md)]

Ez a cikk áttekintést nyújt az infókódokról, az infókód-csoportokról és azok használatáról.

Az infókódok lehetőséget nyújtanak az adatrögzítésre a pénztárgép (POS) jegyzékben. Az infókódok segítségével a pénztáros információt vihet be a pénztárgépbe az előforduló különféle műveletek során, például cikkeladásokat, visszárukat vagy vevőket választhat ki. A pénztárosok kiválaszthatják a bevitelt a listából, vagy megadhatják kódként, számként, dátumként vagy szövegként. Az infókódokat előre meghatározott üzleti tevékenységekhez, kiskereskedelmi cikkekhez, fizetési módokhoz, vevőkhöz vagy meghatározott pénztári tevékenységekhez társíthatja. Az infókódokat a következőkre használhatja:

- Extra információ rögzítése a tranzakció időpontjában, például egy járatszám vagy a visszatérés oka.
- Kérje a pénztárost, hogy bizonyos termékekre vonatkozóan az árlistából válasszon.
- Kapcsoljon alkódot az infókódhoz, amely segíti a pénztárost a bevitelben, amikor adott tevékenységet hajt végre. Például amikor a vevő visszaküld egy terméket, megkérheti a pénztárost, hogy kérdezze meg, hogy miért küldi vissza a vevő a terméket. Ezután az alkódok segítségével megjeleníthető az okok listája, amelyből a pénztáros választhat.
- Termék eladása rendes értékesítésként, kedvezményes értékesítésként vagy ingyenes termékként.
- A pénztáros a pénztárgép fiókjának kinyitásakor értékesítési művelet végrehajtása nélkül megadhat értéket, vagy az alkódok listájából választhat.

## <a name="info-codes-group"></a>Infókódok csoport

A Commerce esetében az infókódok csoportjait hozhatja létre. Az infókód-csoportok rugalmasságot nyújtanak azáltal, hogy lehetővé teszik a kevesebb infókód meghatározását, és ezeket többféle módon használhatja fel. Az infókód-csoportok az alábbi módokon használhatók:

- Kevesebb infókód meghatározása és egyszerű újra felhasználása. Az iinfókód-csoportokban szereplő nfókódok nem rendelkeznek előre meghatározott függőséggel más infókódoktól. Az azonos infókódot több infókódcsoport is tartalmazhatja, és rangsor segítségével az azonos infókódok megjeleníthetők a megadott sorrendben, amely értelmes bármely adott helyzetben.
- Infókódok csatolása más infókódokhoz vagy infókód-csoportokhoz egy termékről vagy tranzakcióról szóló információ gyűjtéséhez oly módon, ahogyan szüksége van rá anélkül, hogy külön infókódot vagy csatolt infókódot kellene megadnia minden egyes esethez.

## <a name="info-code-examples"></a>Csatolt infókód

**1. példa: Infókódok újra felhasználása**

Csatolhatja az infókódokat, így amikor egy infókód kiváltása megtörténik, egy másik infókód kiváltása is megtörténik közvetlenül utána. Például egyes termékek eladása esetén azt szeretné a pénztárostól, hogy kérdezze meg a vevőt, hogy kívánja-e elemek és termék garancia beszerzését. Más termékekre vonatkozóan azt szeretné a pénztárostól, hogy kérdezze meg a vevőt, hogy kívánja-e elemek beszerzését és összegyűjtheti az irányítószámokat is. Ha csatolt infókódokat hoz létre ezekre az esetekre, be kell állítania az infókód minden változatát úgy, hogy a pénztáros a megfelelő információkat tudja elkérni. Azonban infókód-csoportok, gyakori infókódok használata esetén, például elemek kérése esetén, ezeket egyszer be lehet állítani majd több infókód-csoportban újra felhasználni. Használhat priorizálást is az infókód-csoportokban a sorrend azonosítására, amelyben az utasítások megjelennek.

**2. példa: Infókód-csoportok infókódokhoz történő csatolása**

Egyes termékek, például mobileszközök eladása esetén bizonyos adatokat kell mindig összegyűjtenie, mint például a telefonszám, mozgó berendezés azonosítója (MEID) és sorozatszám. Ugyanakkor érdemes különböző adatokat összegyűjtenie a tabletekkel és mobiltelefonokkal kapcsolatban. Beállíthat egy infókód-csoportot, amely utasításokat tartalmaz a telefonszámra, MEID azonosítóra és a sorozatszámra vonatkozóan, majd az infókód-csoportokat az egyes infókódokhoz csatolja. Ha termékspecifikus infókód kiváltása történik, az infókód-csoport kiváltása lehet a következő, hogy lehetővé tegye a gyakori adatok gyűjtését anélkül, hogy minden egyes eszközre több csatolt infókódot kellene meghatároznia.


[!INCLUDE[footer-include](../includes/footer-banner.md)]