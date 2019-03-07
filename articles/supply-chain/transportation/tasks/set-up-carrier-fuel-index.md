---
title: Szállítmányozói üzemanyag-mutató beállítása
description: Ez az útmutató bemutatja, hogyan hozhat létre üzemanyag-mutató régiót, üzemanyag mutatót és szállítmányozói üzemanyag-mutatót.
author: ShylaThompson
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b6f72de7ad54a2b2dc1bf40fd8cb86d8b055e2d1
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "366581"
---
# <a name="set-up-a-carrier-fuel-index"></a>Szállítmányozói üzemanyag-mutató beállítása

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ez az útmutató bemutatja, hogyan hozhat létre üzemanyag-mutató régiót, üzemanyag mutatót és szállítmányozói üzemanyag-mutatót. Az üzemanyag-mutató régió megadja, hogy mely régióra kell vonatkoznia az üzemanyag-mutatónak, az üzemanyag-mutató pedig megadja az adott időszakra érvényes üzemanyagárat. Üzemanyag-árak időbeli változásának tükrözéséhez több üzemanyag-mutatót is társíthat a szállítmányozóhoz.  Ezeket a feladatokat általában a szállítási koordinátor végzi. Ezt a folyamatot az USMF bemutatócéggel vagy saját adataival is használhatja.


## <a name="create-a-fuel-index-region"></a>Üzemanyag-mutató régió létrehozása
1. Ugorjon a Szállítási kezelés > Beállítás > Üzemanyag-mutatók > Üzemanyag-mutató régiók lehetőségre.
    * Először létre kell hoznia különböző régiókat, ahol dolgozik, aztán ki kell számolnia az üzemanyag-pótdíjakat.  
2. Kattintson az Új lehetőségre.
3. A Régió mezőbe írjon be egy értéket.
4. Írjon be egy értéket a Név mezőbe.
5. Kattintson a Mentés gombra.

## <a name="create-a-fuel-index"></a>Hozzon létre egy üzemanyag-mutatót
1. Ugorjon a Szállítási kezelés > Beállítás > Üzemanyag-mutatók > Üzemanyag-mutatók lehetőségre.
    * A beállított régiókhoz meg kell adnia a jelenlegi üzemanyagárakat.  
2. Kattintson az Új lehetőségre.
3. A Régió mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
4. A listában kattintson a kijelölt sorban lévő hivatkozásra.
5. Az Ár/gallon mezőben adjon meg egy számot.
6. Az Érvényesség kezdő dátuma és időpontja mezőben adjon meg egy dátumot és időpontot.
7. Kattintson a Mentés gombra.

## <a name="create-a-carrier-fuel-index"></a>Szállítmányozói üzemanyag-mutató létrehozása
1. Ugorjon a Szállítási kezelés > Beállítás Üzemanyag-mutatók > Szállítmányozói üzemanyag-mutatók lehetőségre.
2. Kattintson az Új lehetőségre.
3. Írjon be egy értéket a Szállítmányozói üzemanyag-mutató mezőbe.
4. A Leírás mezőben adjon meg egy értéket.
5. Kattintson az Új elemre.
6. Az Érvényesség kezdő dátuma és időpontja mezőben adjon meg egy dátumot és időpontot.
7. Írjon be egy számot a Kezdő üzemanyagár mezőbe.
    * Ebben a példában a Kezdő üzemanyagár mezőt 1,95-re állíthatja.  
8. Írjon be egy számot a Záró üzemanyagár mezőbe.
    * Ebben a példában a Záró üzemanyagár mezőt 2-re állíthatja.  
9. Adjon meg egy számot a Százalék mezőben.
    * Ebben a példában a százalékot 3-ra állíthatja.  
10. A Pénznem mezőben kattintson a legördülő gombra a keresőlista megnyitásához.
11. Keresse meg és jelölje ki a kívánt rekordot a listán.
12. A listában kattintson a kijelölt sorban lévő hivatkozásra.
13. Kattintson a Mentés gombra.

