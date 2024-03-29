---
title: Bankkezelési munkaterület
description: Ez a cikk a Bankkezelés munkaterületről nyújt tájékoztatást. Ez a munkaterület a vállalati bankszámlákhoz kapcsolódó információkat jeleníti meg.
author: angelad116
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BankTreasurerWorkspace
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: angelading
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: f9880928281e704edcd24a75f99d4562761b7c82
ms.sourcegitcommit: 0b7a034e644f4d93fe55c7baca5a3f89dbe56898
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/14/2022
ms.locfileid: "9151551"
---
# <a name="bank-management-workspace"></a>Bankkezelési munkaterület

[!include [banner](../includes/banner.md)]

A **Bankszámla kezelése** munkaterület olyan információkat jelenít meg, amelyek a vállalati bankszámlákhoz kapcsolódnak. Ez a munkaterület egy **Összefoglaló** nézetet és egy **Elemzés** oldalt tartalmaz. Az **Összefoglaló** nézet összegző csempéket, bankszámlaadatokat, egyenleget és kapcsolódó adatokat tartalmaz. Az **Elemzés** oldal a Microsoft Power BI funkciói révén vizuálisan megjeleníti a bankszámlaegyenlegekkel kapcsolatos információkat.

## <a name="summary-view"></a>Osszegzésé megtekintése

### <a name="summary"></a>Összegzés

Az **Összefoglaló** szakasz csempéi áttekintést nyújtanak a bankszámláiról, és hozzáférést biztosítanak azokról az oldalakról, amelyeket leggyakrabban kell használnia. A banki egyeztetés információi a Haladó banki egyeztetés funkciónál jelennek meg. Csak azoknál a bankszámláknál jelennek meg az információk, amelyeknél a **Továbbfejlesztett banki egyeztetés** lehetőség beállítása **Igen** a **Bankszámla** oldalon. Az **Összefoglalás** szakaszból importálhatja az elektronikus banki fájlokat mindegyik jogi személy bankszámláira vonatkozóan.

### <a name="bank-accounts"></a>Bankszámlák

A jogi személy minden egyes bankszámláját egy kártya jelzi a **Bankszámlák** szakaszban. Megjelenik az aktuális egyenleg, és Ön leáshat, azokig a tranzakciókig, amikből az összefoglaló számlaegyenleg áll. Az **Áthidalt tranzakciók** összegével Ön leáshat azokig a tranzakciókig, amikből az összefoglaló összeg áll. Az áthidalt tranzakciók olyan függőben lévő tranzakciók, amelyeket az áthidaló funkciók használatával adtak fel, de amelyeket még nem hajtottak végre. A **Függőben levő egyenleg** összege az aktuális egyenleg, mínusz az áthidalt, illetve függőben lévő tranzakciók.

A kártya azt is megjeleníti, hogy mikor egyeztették utoljára a bankszámlát. Ez az információ csak akkor jelenik meg, ha a Haladó banki egyeztetés engedélyezett a bankszámlánál.

### <a name="balance"></a>Egyenleg

Az **Egyenleg** diagram vagy a **Bankszámlák** szakaszban kijelölt bankszámla korábbi egyenlegére vonatkozó információkat jeleníti meg, vagy egy összegzést a korábbi egyenlegadatokról a jogi személy minden bankszámlájára vonatkozóan. Ez az információ különböző időszakokra vonatkozóan állnak rendelkezésre: az aktuális hét, az aktuális hónap, az aktuális év, az elmúlt öt év, illetve minden időszak (a bankszámla minden előzménye). 

Ha egyetlen bankszámlára vonatkozóan nézi meg az **Egyenleg** diagramot, a korábbi egyenlegek a bankszámla pénznemében jelennek meg Ha a jogi személy összes bankszámlájára vonatkozóan nézi meg a diagramot, a korábbi egyenlegek a könyvelés pénznemében jelennek meg

Az utolsó frissítés idejéről szóló információ a diagram tetején jelenik meg. Szükség esetén módosítani lehet az adatokat.

### <a name="related-information"></a>Kapcsolódó információ

A **Kapcsolódó információ** szakaszban megnyithatja az **Általános napló** oldalt, és végrehajthatja a banki átutalásokat. Emellett gyorsan megnyithatja a **Banki tranzakciók** és az **Áthidalt tranzakciók** oldalakat.

## <a name="analytics-view"></a>Elemzés nézet

Az **Elemzés** oldalon fontos mérőszámok tekinthetők meg a jelenlegi vállalat bankszámláiról. Az alábbi megjelenítési lehetőségek állnak rendelkezésre az oldalon:

-   Összesített egyenleg a rendszer pénznemében
-   Egyenleg jogi személy szerint
-   Aznapi tényleges és előrejelzett egyenleg a bankszámla pénznemében
-   Egyenleg bankszámla szerint
-   Egyenleg pénznemenként

Megtekintheti a banki elemzéseket az összes vállalatra vonatkozóan a **Készpénzáttekintés – minden vállalat** munkaterületen. További információkért lásd: [Készpénz áttekintés - Power BI tartalom](Cash-Overview-Power-BI-content.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
