---
title: Szállítói számla létrehozása
description: Ez az eljárás bemutatja, hogyan hozzon létre egy szállítói számlát, és adjon hozzá címet és kapcsolattartási adatokat.
author: GalynaFedorova
ms.date: 06/26/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: VendTable, LogisticsPostalAddressGrid, DirPartyLookup, LogisticsPostalAddress, SysLookupMultiSelectGrid, WHSFilterGenerallyAvail
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: gfedorova
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 34c6d14923bcfdbcbeffc44a5fd08286c60bfc13
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/03/2022
ms.locfileid: "8673886"
---
# <a name="create-a-vendor-account"></a>Szállítói számla létrehozása

[!include [banner](../../includes/banner.md)]

Ez az eljárás bemutatja, hogyan hozzon létre egy szállítói számlát, és adjon hozzá címet és kapcsolattartási adatokat. Az eljárás nem mutatja be, hogyan töltheti ki az összes mezőt a beszerzési és pénzügyi célokra. Az említett mezőkről további információkért olvassa el a mezőleírásokat. Ezt a folyamatot az USMF bemutatócéggel vagy saját adataival is használhatja. Szállítói számlákat általában egy beszerzési vagy kinnlevőségi szakember hozza létre.


## <a name="create-a-vendor-account"></a>Szállítói számla létrehozása
1. Válassza ezt: **Navigációs ablaktábla > Modulok > Beszerzés és forrás > Szállítók > Összes beszállító**.
2. Kattintson az **Új** elemre.
3. A **Szállítói számla** mezőben adjon meg egy értéket.
    - Az érték kitöltése automatikusan történhet. Ebben az esetben ezt a lépést kihagyhatja.  
    - Szállítói számlákat hozhat létre egy személyhez vagy szervezethez. Ez hatással lesz arra, hogy mely mezők érhetők el. Ebben a példában egy szállítói számlát hozunk létre egy szervezet számára.   
4. A **Név** mezőben adjon meg vagy válasszon ki egy értéket. Ha a szállító egy már a rendszerben regisztrált fél, használhatja a legördülő listát, kiválaszthatja őket ebben a mezőben, és az új szállítói számla örökli a címet vagy elérhetőségi adatokat, amelyek már regisztrálva vannak.
5. A **Csoport** mezőben adjon meg vagy válasszon ki egy értéket. A szállítói csoportba olyan szállítók tartoznak, amelyek a következő közös paraméterekkel rendelkeznek: Fizetési feltételek, kiegyenlítési időszak, készlet feladási főkönyvi számlák – például áfacsoport; alapértelmezett főkönyvi számlák; termékszűrő kódok vagy kínálat-előrejelzési konfiguráció.
6. Adjon meg egy számot az **Alkalmazottak száma** mezőben.
7. Írjon be egy értéket a **Szervezet száma** mezőbe.

## <a name="add-an-address"></a>Cím hozzáadása
1. Bontsa ki a **Címek** szakaszt.
2. Kattintson a **Hozzáadás** parancsra.
3. A **Cél** mezőben adjon meg vagy válasszon ki egy értéket. Egy vagy több célt is bejelölhet. Ezek segítségével válassza ki a megfelelő címet egy adott célra vonatkozóan. Például, ha a cél a „Számla”, azt a címet használja a program a számlák küldésekor.
4. Adjon meg egy értéket a **Név vagy leírás** mezőben.
5. Az **Ország/régió** mezőben adjon meg vagy válasszon ki egy értéket. Adja meg a cím adatait. A kiválasztott ország/régió határozza meg a megjelenő megőket, az ország/régió címformátumának megfelelően. 
6. Kattintson az **OK** gombra.

## <a name="add-contact-information"></a>Kapcsolattartási adatok hozzáadása
1. Bontsa ki a **Kapcsolattartási adatok** szakaszt.
2. Kattintson a **Hozzáadás** parancsra.
3. Írjon egy értéket a **Leírás** mezőbe.
4. A **Típus** mezőben válasszon ki egy lehetőséget.
5. Írjon be egy értéket a **Kapcsolattartó száma/címe** mezőbe. Kiválaszthatja az Elsődleges jelölőnégyzetet, ha ez az elsődleges kapcsolattartó.  
6. Kattintson a **Mentés** gombra.
7. Zárja be a lapot.
8. Zárja be a lapot.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]