--- 
title: "Cikkek regisztrálása alapvető raktározásra engedélyezett cikkre, cikkérkeztetési napló használatával"
description: "Ez az eljárás megmutatja, hogyan regisztrálhat cikkeket a cikkérkeztetési napló segítségével, ha a készletkezelési modulban „alapvető raktározást” használ."
author: ShylaThompson
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 809a1466b0f4674f503bc654175d8f94b37a6508
ms.openlocfilehash: c7148bd807ef29b0dd89204a0fbe9b8480095aba
ms.contentlocale: hu-hu
ms.lasthandoff: 11/02/2017

---
# <a name="register-items-for-a-basic-warehousing-enabled-item-using-an-item-arrival-journal"></a>Cikkek regisztrálása alapvető raktározásra engedélyezett cikkre, cikkérkeztetési napló használatával

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ez az eljárás megmutatja, hogyan regisztrálhat cikkeket a cikkérkeztetési napló segítségével, ha a készletkezelési modulban „alapvető raktározást” használ. Ezt általában egy bevételezési adminisztrátor végzi. Ezt az eljárást az USMF bemutató vállalatban is futtathatja a megjelenített példákat használva.  Ha nem az USMF-et használja, a útmutató elkezdése előtt jóváhagyott beszerzési rendelésre van szüksége nyitott beszerzésirendelés-sorral. A sorban szereplő cikknek raktározottnak kell lennie, és nem használhat termékváltozatokat, és nem lehet nyomon követési dimenziója. A cikket egy olyan tárolásidimenzió-csoporthoz kell hozzárendelni, ahol a hely és a raktár aktív.


## <a name="create-item-arrival-journal-header"></a>Cikkérkeztetési napló fejlécének létrehozása
1. Lépjen a Készletgazdálkodás > Naplóbejegyzések > Cikkérkeztetés > Cikkérkeztetés menüpontra.
2. Kattintson az Új lehetőségre.
3. Írjon be egy értéket a Név mezőbe.
    * Az USMF használata esetén beírhatja a „WHS” lehetőséget. Ha más adatokat használ, a kiválasztott naplót az alábbiak szerint kell beállítania: a kitárolási hely ellenőrzése legyen a Nem beállításon, és a Karanténkezelés legyen a Nem beállításon.  
4. Írjon be egy értéket a szállítólevél mezőbe.
    * Ez a szállítólevél azonosítója a vevő által kiállított szállítólevélről. Adjon meg egy egyedi számot.  
5. A Szám mezőben válassza ki a beszerzési rendelést.
6. Kattintson az OK gombra.

## <a name="add-lines-to-item-arrival-journal"></a>Sorok hozzáadása a cikkérkeztetési naplóhoz
1. Kattintson a Funkciók elemre.
2. Kattintson a Sorok létrehozása lehetőségre.
    * A sorokat létrehozhatja automatikusan, vagy megadhatja azokat a naplóba manuálisan. Ez az automatikus létrehozást mutatja be.  
3. Jelölje be vagy törölje a jelölést a Mennyiség kezdeti beállítása jelölőnégyzetből.
    * Ez inicializálja a naplósorok mennyiségét a beszerzési rendelés sorából nem regisztrált mennyiséggel.  
4. Kattintson az OK gombra.

## <a name="post-the-journal"></a>Napló feladása
1. Kattintson a Feladás lehetőségre.
2. Kattintson az OK gombra.

## <a name="generate-the-product-receipt"></a>Termékbevételezés létrehozása
1. Kattintson a Funkciók elemre.
2. Kattintson a Termékbevételezés elemre.
3. Kattintson az OK gombra.


