---
title: Áthidalt kifizetések beállítása és feldolgozása
description: Ez a cikk bemutatja az áthidalt vevői kifizetések beállítását és feldolgozását. Az áthidalt kifizetés olyan kifizetés, amely két lépésben van feladva a főkönyvbe.
author: rachel-profitt
ms.date: 12/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustPaymMode, VendPaymMode, LedgerJournalTable, LedgerJournalTransCustPaym, LedgerJournalTransVendPaym, LedgerJournalTransDaily
audience: Application User
ms.reviewer: twheeloc
ms.custom: ''
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2022-01-03
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bb563008f156e1bfa6e4e9a705e9170342719ce7
ms.sourcegitcommit: 9740f9b41a7dcf1821c6baccb2e05b9865ac2966
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/15/2022
ms.locfileid: "9775168"
---
# <a name="set-up-and-process-bridged-payments"></a>Áthidalt kifizetések beállítása és feldolgozása

[!include [banner](../includes/banner.md)]

Az áthidalt kifizetés olyan kifizetés, amely két lépésben van feladva a főkönyvbe. Ez a megközelítés **jellemzően akkor használatos, amikor a fizetési mód a Bank** beállításra van beállítva, és csak akkor kell tranzakciókat a bankszámlára könyvelni, ha már törölték a bankot. Főkönyvi számlákhoz azonban használható. Ebben az esetben az összeg átkerül az egyik fő számláról a másikra az áthidaló feladás feldolgozásakor.

Áthidalt kifizetéseket a Kötelezettségek és a Kinnlevőségek alapján is létre lehet hozni. Bár ez a cikk bemutatja, hogyan kell konfigurálni az áthidaló feladásokat a Kinnlevőségek esetében, a Kötelezettségek tranzakcióinak lépései hasonlóak.

## <a name="set-up-bridging-posting"></a>Áthidaló feladás beállítása

Az áthidaló feladás alkalmazáshoz **be** kell állítani egy vagy több fizetési módot, hogy az áthidaló feladási módszert használják. Ezután ki kell választania egy áthidaló számlát.

1. Ugrás a Kinnlevőségek **– &gt; Kifizetés beállítása &gt; fizetési módokhoz**.
2. Meglévő fizetési mód kiválasztása az áthidaló feladás engedélyezéséhez. Másik lehetőségként hozzon létre egy új fizetési módot.
3. Jelölje be az **Áthidalás feladás jelölőnégyzetet**.
4. Az Áthidaló **számla** mezőben válassza ki azt a fő számlát, amelyre a kifizetéseket fel kell adja, mielőtt törölve lesznek a bankszámlára.
5. Zárja be a lapot.

## <a name="process-and-transfer-bridging-posting"></a>Áthidaló feladás feldolgozása és átvitele

Az áthidaló feladás létrehozásához és feldolgozásához hajtsa végre ezeket a lépéseket.

1. Válassza a **Kinnlevőségek &gt; Kifizetések &gt; Kifizetési napló** lehetőséget.
2. Válassza az **Új** lehetőséget egy napló létrehozásához.
3. A Név **mezőben** válasszon ki egy nevet.
4. Sorok hozzáadása a vevői kifizetési naplóhoz, és az áthidaló feladáshoz beállított fizetési mód kiválasztása.
5. Napló feladása. A tranzakciók az előző művelet során **az** Áthidaló számla mezőben kiválasztott fő számlára lesznek feladva.

Ha a tranzakciók törölve vannak a bankból, és a kifizetést át szeretné utalni az áthidaló számláról a fizetési módhoz megadott fizetési számlára, kövesse ezeket a lépéseket.

1. Válassza a **Főkönyv &gt; Naplóbejegyzések &gt; Általános naplók** lehetőséget.
2. Válassza az **Új** lehetőséget egy napló létrehozásához.
3. A Név **mezőben** válasszon ki egy nevet.
4. Válassza ki **a sorokat** a napló részleteinek megnyitásához.
5. Válassza ki **a Funkciók &gt; kiválasztása áthidalt tranzakciókat**.
6. Jelöljön meg minden olyan kifizetést, amely törölve van, majd válassza az Elfogadás **lehetőséget**.
7. Napló feladása.
