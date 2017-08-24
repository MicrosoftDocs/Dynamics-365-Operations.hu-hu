---
title: "Visszatérítés vevőknek"
description: "Ez a cikk ismerteti a vásárlók egy csoportját érintő visszatérítési tranzakciók létrehozásának folyamatát. Ha a vevőnek követel egyenlege van, visszatéríthet a vevőnek az egyenleg összegéért."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerJournalTransCustPaym, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 14191
ms.assetid: 53533ee3-470e-458a-ac8b-3815aa4cb502
ms.search.region: Global
ms.author: Shiva.Pandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: c3201166eb7054205647a54ed80f98968fcfda6e
ms.contentlocale: hu-hu
ms.lasthandoff: 05/25/2017

---

# <a name="reimburse-customers"></a>Visszatérítés vevőknek

[!include[banner](../includes/banner.md)]


Ez a cikk ismerteti a vásárlók egy csoportját érintő visszatérítési tranzakciók létrehozásának folyamatát. Ha a vevőnek követel egyenlege van, visszatéríthet a vevőnek az egyenleg összegéért. 

Az alábbi táblázat bemutatja a munka megkezdése előtt biztosítandó előfeltételeket.

| Előfeltételek                                                            | Leírás                                                                                                                                                                                 |
|-------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Adja meg a legalacsonyabb visszatérítés összegét a jogi személyhez.          | Az a **Kinnlevőségek paraméterei** oldalon, az **Általános** területen, a **A legalacsonyabb visszatérítés** mezőbe írja be azt a minimális összeget, amely a vevő általi túlfizetések miatt vissza kell fizetni. |
| Választható: Szállítói számla hozzáadása minden vevőhöz, akit vissza lehet téríteni. | A **Vevők** oldalon, a **Vegyes részletek** gyorslapon, a **Szállítókód** mezőben, válassza ki a szállítói számlát a vevő számára.                                           |

A visszatérítési tranzakciók létrehozásakor a szállítói számla a követel egyenleg összegéhez jön létre. A visszatérítési folyamat eltávolítja a követel egyenleget a vevői számlához, és létrehoz egy egyenleget, amely esedékes a szállítói számlához, amely megfelel a veőnek.

1.  A Kinnlevőségekben, futtassa a **Visszatérítés** folyamatot.
2.  Tegye a következők egyikét:
    -   Adott vevőszámlákon végzett visszatérítéshez kattintson a **Kiválaszt** elemre, és adja meg a lekérdezésben szereplő vevői számlákat.
    -   Az összes vevői számlán végzett visszatérítéshez kattintson az **OK** gombra.

    A követel összegek átkerülnek a vevők szállítói számláira, és normál kifizetésként dolgozza fel őket a program. Ha a vevő nem rendelkezik szállítói számlával, a program automatikusan létrehoz a vevő számára egy egyszer használatos szállítói számlát.
3.  A létrehozott visszatérítési tranzakciók megjelenítéséhez használja a **Visszatérítés** oldalt.
4.  A kötelezettségekben hozzon létre kifizetést a szállítói számlákhoz, amelyek a bevételezési folyamat során jöttek létre.





