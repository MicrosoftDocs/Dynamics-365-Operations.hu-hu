---
title: Cikkek regisztrálása alapvető raktározásra engedélyezett cikkre, cikkérkeztetési napló használatával
description: Ez az eljárás megmutatja, hogyan regisztrálhat cikkeket a cikkérkeztetési napló segítségével, ha a készletkezelési modulban „alapvető raktározást” használ.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart, PurchCreateOrder, WMSJournalTable, WMSJournalCreate, PurchEditLines
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 61ce76c5aac82ec95b7113066b47b85a9c944307
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5830858"
---
# <a name="register-items-for-a-basic-warehousing-enabled-item-using-an-item-an-item-arrival-journal"></a>Cikkek regisztrálása alapvető raktározásra engedélyezett cikkre, cikkérkeztetési napló használatával

[!include [banner](../../includes/banner.md)]

Ez az eljárás megmutatja, hogyan regisztrálhat cikkeket a cikkérkeztetési napló segítségével, ha a készletkezelési modulban „alapvető raktározást” használ. Ezt általában egy bevételezési adminisztrátor végzi. Ezt az eljárást az USMF bemutató vállalatban is futtathatja a megjelenített példákat használva.  Ha nem az USMF-et használja, a útmutató elkezdése előtt jóváhagyott beszerzési rendelésre van szüksége nyitott beszerzésirendelés-sorral. A sorban szereplő cikket raktárazni kell. A cikket egy olyan tárolásidimenzió-csoporthoz kell hozzárendelni, ahol a hely és a raktár aktív.


## <a name="create-item-arrival-journal-header"></a>Cikkérkeztetési napló fejlécének létrehozása
1. Lépjen a Készletgazdálkodás > Naplóbejegyzések > Cikkérkeztetés > Cikkérkeztetés menüpontra.
2. Kattintson az Új lehetőségre.
3. Írjon be egy értéket a Név mezőbe.
    * Az USMF használata esetén beírhatja a „WHS” lehetőséget. Ha más adatokat használ, a kiválasztott naplót az alábbiak szerint kell beállítania: A Kitárolási hely ellenőrzése legyen a Nem beállításon, és a Karanténkezelés legyen a Nem beállításon.  
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



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]