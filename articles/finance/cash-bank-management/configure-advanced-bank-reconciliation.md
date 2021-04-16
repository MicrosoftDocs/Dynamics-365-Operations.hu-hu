---
title: Továbbfejlesztett banki egyeztetés beállításának folyamata
description: A Továbbfejlesztett banki egyeztetés lehetővé teszi Önnek az elektronikus banki kivonatok és az automatikus egyeztetés importálását a Microsoft Dynamics 365 Finance rendszer banki tranzakcióiba. Ez a cikk a beállítási folyamatokról nyújt tájékoztatást az egyeztetésre vonatkozóan.
author: panolte
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BankReconciliationMatchRule, BankReconciliationMatchRuleSet
audience: Application User
ms.reviewer: roschlom
ms.custom: 98303
ms.assetid: ae071f04-f038-4b17-812d-0a241ed15521
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9f4db43f50cc279ffc6c0ae91a16378de9567dd8
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5822975"
---
# <a name="advanced-bank-reconciliation-setup-process"></a>Továbbfejlesztett banki egyeztetés beállításának folyamata

[!include [banner](../includes/banner.md)]

A Továbbfejlesztett banki egyeztetés lehetővé teszi Önnek az elektronikus banki kivonatok és az automatikus egyeztetés importálását a Microsoft Dynamics 365 Finance rendszer banki tranzakcióiba. Ez a cikk a beállítási folyamatokról nyújt tájékoztatást az egyeztetésre vonatkozóan.  

Számos darabot a továbbfejlesztett banki egyeztetés funkció használata előtt be kell állítani. További információ a banki kivonat importálásának beállításáról: [Továbbfejlesztett banki egyeztetés importálási folyamata](set-up-advanced-bank-reconciliation-import-process.md).  Az egyeztetési folyamatra vonatkozó követelmények alább vannak részletezve.

## <a name="transaction-codes"></a>Tranzakciókódok
A tranzakciókódok a banki egyeztetési szabályok részeként használhatók. Tranzakciókódok segítségével biztosítható, hogy csak az azonos típusú tranzakciók kerüljenek egyeztetésre a Finance és a bankszámlakivonat között. Ezen típusú egyeztetés végrehajtásához először meg kell határozni a banki tranzakciókhoz használt tranzakciótípusokat a Finance alkalmazásból, majd e típusokat hozzá kell rendelni a bank kivonatán szereplő tranzakciókódokhoz. A banki tranzakciók tranzakciótípusai a **Banki tranzakciótípusok** lapon vannak meghatározva. Itt adhatja meg a tranzakció típusával társított feladásokhoz használt fő számlát is. 

Miután meghatározta a banki tranzakciókódokat, rendelje hozzá azokat az elektronikus banki kivonatokban használt tranzakciókódokhoz. Ez a leképezési folyamat a **Tranzakciókód-hozzárendelés** oldalon hajtható végre. A tranzakciókódok hozzárendelését minden bankszámlánál külön el kell végezni.

## <a name="matching-rules-and-matching-rule-sets"></a>Az Egyeztetési szabályok és a megfelelő szabálykészletek
Az egyeztetési szabályok lehetővé teszik a Finance banki tranzakciói és a bankszámlakivonat tranzakciói közötti automatikus egyeztetést. Egyeztetési szabályok beállításához használja az **Egyeztetési szabályok** oldalt. További tudnivalókért lásd: [Banki egyeztetési szabályok beállítása](set-up-bank-reconciliation-matching-rules.md). 

Az egyeztetési szabálykészlet olyan egyeztetési szabályok csoportjainak meghatározására szolgál, amelyeket a rendszer sorrendben futtat a banki kivonat egyeztetési folyamata során.  Az egyeztetési szabálykészletek konfigurálása az **Egyeztetési szabálykészletek** oldalon történik.

## <a name="cash-and-bank-management-parameters"></a>Készpénz- és bankkezelési paraméterek
A **Készpénz- és bankkezelési paraméterek** oldalon számos, kifejezetten a továbbfejlesztett banki egyeztetési folyamattal kapcsolatos paraméter található.  A **Kivonatsor mennyiségének megjelenítése tartozik/követel oszlopokban** módosítja a **Banki kivonat** oldalon szereplő összegek nézetét. Ha ezt a beállítást választja, a banki kivonat tranzakcióösszegei külön-külön a tartozik és követel oszlopokban fognak megjelenni. Ha nem ezt választja, akkor a banki kivonat tranzakcióösszegei a megfelelő jellel egy összegmezőben fognak megjelenni. 

A Paraméterek lapon beállított ellenőrzési beállítások felülírják az egyeztetési szabályokban beállított kiválasztásokat. Például nem lehet manuálisan vagy automatikusan egyeztetni dokumentumokat a paraméterek lapon beállított dátumkülönbségen túl. Ha a beállítás **Tranzakciótípus hozzárendelésének ellenőrzése** lehetőségre van beállítva, a tranzakciótípusokat a Finance banki tranzakciói és a banki kivonat tranzakciói között le kell képezni a tranzakciók manuálisan vagy automatikusan történő egyeztetéséhez. 

Továbbá konfigurálnia kell a szükséges számsorozatokat a **Készpénz- és bankkezelési paraméterek** oldalon.  A **Számsorozatok** lapon állítsa be a számsorozat-kódokat az **Azonosító, az Utasítás azonosítója, az Egyeztetési azonosító, és a banki egyeztetés** Letöltés hivatkozásra vonatkozóan.

## <a name="bank-account-reconciliation-options"></a>Bankszámla-egyeztetés beállítások
Először engedélyeznie kell a bankszámlához tartozó Továbbfejlesztett banki egyeztetést. Számos további beállítás érhető el a **Bankszámla** oldalon a Továbbfejlesztett banki egyeztetés funkció engedélyezése után. 

A **Banki kivonatok használata az elektronikus fizetések visszaigazolására** funkció a banki egyeztetés funkcióját az elektronikus fizetési állapotokba integrálja. Ha ez engedélyezve van, a banki bizonylat automatikusan létrejön az **Elküldött** állapotra beállított elektronikus fizetési állapotra vonatkozóan. Ezenkívül az elektronikus fizetések állapota az **Elküldött** állapotról **Fogadott** állapotra fog frissülni a fizetés megfeleltetése, egyeztetése és feladása után. 

**A kimutatásokban szereplő bankszámla neve** mező neve az elektronikus banki kivonatokban szereplő bankszámlára vonatkozó névvel egyezik meg. Ez a név annak eldöntésekor használatos, hogy mely tranzakciók kerüljenek importálásra azon kivonatból származó bankszámlára vonatkozóan, amely több bankszámlára vonatkozó információkat tartalmazhat. 

Az **Egyeztetés az importálás után** lehetőségre történő beállítás automatikusan ellenőrzi a banki kivonatot, új banki egyeztetést és munkalapot hoz létre, és futtatja az Alapértelmezett egyeztetési szabálykészletet. Ez a funkció automatizálja a folyamatot addig a pontig, ahol már a tranzakciókat kézzel kell egymáshoz rendelni. A bankszámla beállítása visszaáll alapértelmezésre az importáláskor.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]