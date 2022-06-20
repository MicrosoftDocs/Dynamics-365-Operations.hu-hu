---
title: Visszatérítés vevőknek
description: Ez a cikk ismerteti a vásárlók egy csoportját érintő visszatérítési tranzakciók létrehozásának folyamatát.
author: JodiChristiansen
ms.date: 09/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTransCustPaym, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: twheeloc
ms.custom: 14191
ms.assetid: 53533ee3-470e-458a-ac8b-3815aa4cb502
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 892b089edb16ba560f588c086d37faafdf16958d
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8891782"
---
# <a name="reimburse-customers"></a>Visszatérítés vevőknek

[!include [banner](../includes/banner.md)]

Ez a cikk ismerteti a vásárlók egy csoportját érintő visszatérítési tranzakciók létrehozásának folyamatát. Ha a vevőnek követel egyenlege van, visszatéríthet a vevőnek az egyenleg összegéért. 

Az alábbi táblázat bemutatja a munka megkezdése előtt biztosítandó előfeltételeket.

| Előfeltételek                                                            | Leírás |
|-------------------------------------------------------------------------|-------------|
| Adja meg a legalacsonyabb visszatérítés összegét a jogi személyhez.          | Az a **Kinnlevőségek paraméterei** oldalon, az **Általános** területen, a **A legalacsonyabb visszatérítés** mezőbe írja be azt a minimális összeget, amely a vevő általi túlfizetések miatt vissza kell fizetni. |
| Választható: Szállítói számla hozzáadása minden vevőhöz, akit vissza lehet téríteni. | A **Vevők** oldalon, a **Vegyes részletek** gyorslapon, a **Szállítókód** mezőben, válassza ki a szállítói számlát a vevő számára. |

A visszatérítési tranzakciók létrehozásakor a szállítói számla a követel egyenleg összegéhez jön létre. A visszatérítési folyamat eltávolítja a követel egyenleget a vevői számlához, és létrehoz egy egyenleget, amely esedékes a szállítói számlához, amely megfelel a veőnek.

1. A Kinnlevőségekben futtassa a **Visszatérítés** folyamatot (**Kinnlevőségek \> Időszakos feladatok \> Visszatérítés**).
2. Az összes tranzakció csoportosításához a főkönyvi dimenzióktól függetlenül állítsa be a **Vevő összegzése** lehetőséget **Igen** értékre. Ha csak a hasonló főkönyvi dimenziókkal rendelkező tranzakciókat szeretné csoportosítani, állítsa a lehetőséget **Nem** értékre.
3. Válassza a **Elmaradási megbízási tranzakciókkal rendelkező vevők felvétele** lehetőséget a kiegyenlítetlen összegekkel rendelkező vevők kiválasztásához.
4. Adott vevőszámlák visszatérítéséhez a **Rekordok felvétele** gyorslapon válassza a **Szűrő** lehetőséget, majd adja meg a lekérdezésben a vevői számlákat.

    A követel összegek átkerülnek a vevők szállítói számláira, és normál kifizetésként dolgozza fel őket a program. Ha a vevő nem rendelkezik szállítói számlával, a program automatikusan létrehoz a vevő számára egy egyszer használatos szállítói számlát.

5. A létrehozott visszatérítési tranzakciók megtekintéséhez használja a **Visszatérítési** jelentést (**Kinnlevőségek \> Lekérdezések és jelentések \> Visszatérítési jelentés**).
6. A kötelezettségekben hozzon létre kifizetést a szállítói számlákhoz, amelyek a bevételezési folyamat során jöttek létre. A szállítók kifizetéséről a [Szállítói kifizetések áttekintése](../accounts-payable/Vendor-payments-workspace.md) című témakörben olvashat.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
