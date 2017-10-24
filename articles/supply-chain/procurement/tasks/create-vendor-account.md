--- 
title: "Szállítói számla létrehozása"
description: "Ez az eljárás bemutatja, hogyan hozzon létre egy szállítói számlát, és adjon hozzá címet és kapcsolattartási adatokat."
author: mkirknel
manager: AnnBe
ms.date: 06/06/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 6ff2357d5266c45be2f403e463c72089d73db21b
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-vendor-account"></a>Szállítói számla létrehozása

[!include[task guide banner](../../includes/task-guide-banner.md)]

Ez az eljárás bemutatja, hogyan hozzon létre egy szállítói számlát, és adjon hozzá címet és kapcsolattartási adatokat. Az eljárás nem mutatja be, hogyan töltheti ki az összes mezőt a beszerzési és pénzügyi célokra. Az említett mezőkről további információkért olvassa el a mezőleírásokat. Ezt a folyamatot az USMF bemutatócéggel vagy saját adataival is használhatja. Szállítói számlákat általában egy beszerzési vagy kinnlevőségi szakember hozza létre.


## <a name="create-a-vendor-account"></a>Szállítói számla létrehozása
1. Ugrás a Beszerzés és forrás > Beszállítók > Minden szállító pontra.
2. Kattintson az Új lehetőségre.
3. Írjon be egy értéket a Szállítói számla mezőbe.
    * Az érték kitöltése automatikusan történhet. Ebben az esetben ezt a lépést kihagyhatja.  
    * Szállítói számlákat hozhat létre egy személyhez vagy szervezethez. Ez hatással lesz arra, hogy mely mezők érhetők el. Ebben a példában egy szállítói számlát hozunk létre egy szervezet számára.   
4. A Név mezőben adjon meg vagy válasszon ki egy értéket.
    * Ha a szállító egy már a rendszerben regisztrált fél, használhatja a legördülő listát, kiválaszthatja őket ebben a mezőben, és az új szállítói számla örökli a címet vagy elérhetőségi adatokat, amelyek már regisztrálva vannak.  
5. A Csoport mezőben adjon meg vagy válasszon ki egy értéket.
    * A szállítói csoportba olyan szállítók tartoznak, amelyek a következő közös paraméterekkel rendelkeznek: Fizetési feltételek; kiegyenlítési időszak; készlet feladási főkönyvi számlák – például áfacsoport; alapértelmezett főkönyvi számlák; termékszűrő kódok vagy kínálat-előrejelzési konfiguráció.  
6. Adjon meg egy számot az Alkalmazottak száma mezőben.
7. Írjon be egy értéket a Szervezet száma mezőbe.

## <a name="add-an-address"></a>Cím hozzáadása
1. Bontsa ki a Címek szakaszt.
2. Kattintson a Hozzáadás gombra.
3. A Cél mezőben adjon meg vagy válasszon ki egy értéket.
    * Egy vagy több célt is bejelölhet. Ezek segítségével válassza ki a megfelelő címet egy adott célra vonatkozóan. Például, ha a cél a „Számla”, azt a címet használja a program a számlák küldésekor.  
4. A „Név vagy leírás” mezőbe írjon be egy értéket.
5. Az Ország/régió mezőben adjon meg vagy válasszon ki egy értéket.
    * Adja meg a cím adatait. A kiválasztott ország/régió határozza meg a megjelenő megőket, az ország/régió címformátumának megfelelően.   
6. Kattintson az OK gombra.

## <a name="add-contact-information"></a>Kapcsolattartási adatok hozzáadása
1. Kattintson a Hozzáadás gombra.
2. A Leírás mezőben adjon meg egy értéket.
3. A Típus mezőben válasszon ki egy lehetőséget.
4. Írjon be egy értéket a Kapcsolattartó száma/címe mezőbe.
    * Kiválaszthatja az Elsődleges jelölőnégyzetet, ha ez az elsődleges kapcsolattartó.  
5. Kattintson a Mentés gombra.
6. Zárja be a lapot.
7. Zárja be a lapot.


