---
title: Cikkek fedezeti szabályainak meghatározása
description: Ez az eljárás bemutatja, hogyan tud fedezeti szabályokat létrehozni és egy adott cikk fedezeti beállításait felülírni. Azt is bemutatja, hogyan kell megadni az alapértelmezett készletbeállításokat.
author: t-benebo
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ReqGroup, DefaultDashboard, EcoResProductDetailsExtended, EcoResProductCreate, InventItemOrderSetup, ReqItemTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bca0e1786adb08a7cd4795b49c974ab95183b1dd
ms.sourcegitcommit: ad1afc6893a8dc32d1363395666b0fe1d50e983a
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/23/2022
ms.locfileid: "8469322"
---
# <a name="define-coverage-rules-for-items"></a>Cikkek fedezeti szabályainak meghatározása

[!include [banner](../../includes/banner.md)]

Ez az eljárás az USMF bemutatócéget használja. Ez az eljárás bemutatja, hogyan tud fedezeti szabályokat létrehozni és egy adott cikk fedezeti beállításait felülírni. Azt is bemutatja, hogyan kell megadni az alapértelmezett készletbeállításokat.

## <a name="create-a-coverage-group"></a>Fedezetcsoport létrehozása

Hozzon létre egy fedezeti csoportot a következő lépések alapján:

1. Nyissa meg a **Navigációs ablak > Modulok > alaptervezés > Beállítások> Fedezeti csoportok** elemet.
1. Válassza az **Új** lehetőséget.
1. Írjon be egy értéket a **Fedezeti csoport** mezőbe.
1. Írjon be egy értéket a **Név** mezőbe.
1. Írjon be egy értéket a **Naptár** mezőbe. Válassza ki azt a naptárat, amely alapján az ebben a csoportban szereplő cikkek esetében az alaptervezés a feltöltési javaslatokat létrehozza.  
1. A **Fedezet kódja** mezőben válasszon ki egy lehetőséget. Jelölje be az eljáráshoz szükséges „követelményeket”.  
1. A **Fedezet időkorlátja (napok)** mezőben, írja be: '90'. Az ebben a csoportban szereplő cikkek esetében az alaptervezés legfeljebb 90 napos jövőbeni időszakra szóló feltöltési javaslatokat hoz létre.  
1. A **Negatív napok** mezőbe írja be az „1” értéket.
1. A **Pozitív napok** mezőbe írja be az „1” értéket.
1. Bontsa ki vagy zárja be az **Egyéb** szakaszt.
1. A **Biztonsági időtartalék napban** szakaszban a **Követelmény dátumához hozzáadott bevételezési időtartalék** mezőbe írja be az „1” értéket. Ha például a bevételezési különbözet 1 napra van állítva, és a beszerzési rendelési sor május 15-re van bevételezésre ütemezve, az alapütemezés május 16-ra számítja ki a korrigált bevételezési dátumot.
1. A **Követelmény dátumából levont kiadási időtartalék** mezőbe írja be az „1” értéket. Ha például a kiadási különbözet 1 napra van állítva, és az értékesítési rendelési sor május 15-re van kiszállításra ütemezve, az alapütemezés május 14-re számítja ki a korrigált kiadási dátumot.  
1. Az **Újrarendelési időtartalék hozzáadva a cikkátfutási időhöz** mezőbe írja be az „1” értéket.
1. Válassza a **Mentés** lehetőséget.

## <a name="create-a-new-product"></a>Új termék létrehozása

Hozzon létre egy új terméket a következő lépések alapján:

1. Kattintson ide: **Navigációs ablaktábla > Modulok > Termékinformációk kezelése > Termékek > Kiadott termékek**.
1. Válassza az **Új** lehetőséget.
1. Írjon be egy értéket a **Termékszám** mezőbe.
1. Írjon be egy értéket a **Terméknév** mezőbe.
1. A **Cikkmodellcsoport** mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
1. Keresse meg és jelölje ki a kívánt rekordot a listán.
1. A listában válassza ki a kiválasztott sorból a hivatkozást.
1. A **Cikkcsoport** mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
1. Keresse meg és jelölje ki a kívánt rekordot a listán.
1. A listában válassza ki a kiválasztott sorból a hivatkozást.
1. A **Tárolási dimenzió csoport** mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
1. Keresse meg és jelölje ki a kívánt rekordot a listán.
1. A listában válassza ki a kiválasztott sorból a hivatkozást.
1. A **Nyomon követési dimenzió csoport** mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
1. Keresse meg és jelölje ki a kívánt rekordot a listán.
1. A listában válassza ki a kiválasztott sorból a hivatkozást.
1. Válassza ki az **OK** lehetőséget.

## <a name="set-up-default-order-settings"></a>Alapértelmezett rendelésbeállítások beállítása

Adja meg az alapértelmezett rendelési beállításokat a következő lépések alapján:

1. A **Műveleti ablaktáblán** válassza a **Tervezés** elemet.
1. Kattintson a **Rendelésbeállításai** alatt válassza az **Alapértelmezett rendelés beállítások** elemet.
1. A **Beszerzési rendelés** alatta az **Alapértelmezett telephely** mezőbe írja be azt a telephelyet amelyet alapértelmezettként használtak a beszerzési rendelések létrehozásakor.
1. Az **Alapértelmezett raktár** mezőjébe írja be azt a helyet, ahol a cikket tárolják.
1. Bontsa ki vagy csukja össze a **Készlet** szakaszt.
1. A **Többszörös** mezőbe írja be 10 értéket.
1. A **Minimális rendelési mennyiség** mezőbe írja be a „10” értéket.
1. A **Maximális rendelési mennyiség** mezőbe írja be a „100” értéket.
1. A **Standard rendelési mennyiség** mezőbe írja be a „10” értéket.
1. Adjon meg egy számot az **Beszerzési átfutási idő** mezőben.
1. Jelölje be törölje a **Munkanapok** jelölőnégyzetet.
1. Válassza a **Mentés** lehetőséget.
1. Az **Alapértelmezett rendeléstípus** mezőben válassza ki a „Beszerzési rendelés” elemet.
1. Válassza a **Mentés** lehetőséget.
1. Zárja be a lapot. Zárja be az Alapértelmezett rendelésbeállítások oldalt.  

## <a name="add-an-item-to-a-coverage-group"></a>Cikk felvétele egy fedezetcsoportba

Adjon hozzá egy elemet a fedezeti csoporthoz a következő lépések alapján:

1. Bontsa ki vagy zárja be a **Terv** szakaszt.
1. A **Fedezeti csoport** mezőben válassza a legördítő nyilat a keresőlista megnyitásához.
1. Keresse meg a létrehozott **Fedezeti csoportot** a listában.
1. A listában válassza ki a kiválasztott sorból a hivatkozást.

## <a name="create-item-coverage-rules"></a>Cikkfedezet szabályainak létrehozása

Hozzon létre cikkfedezeti-szabályokat a következő lépések alapján:

1. A **Műveleti ablaktáblán** válassza a **Tervezés** elemet.
1. A **Fedezet** területen válassza a **Cikkfedezeti** elemet.
1. Válassza az **Új** lehetőséget.
1. Válassza ki az **Általános** fület.
1. Jelölje be a négyzetet a fejlécben a **Fedezeticsoport** beállítások felülbírálatában.
1. A **Fedezet időkorlátja (napok)** mezőbe, írja be: '60'. Annak ellenére, hogy a fedezeti csoport Követelményeket 90 nappal előre megtervezik, ezt a cikket 60 nappal előre fogják tervezni.  
1. A **Negatív napok** mezőbe írja be az „2” értéket.
1. A **Pozitív napok** mezőbe írja be az „2” értéket.
1. Válasza az **Átfutási idő** fület.
1. Jelölje be a **Vásárlás** fejlécén lévő jelölőnégyzetet.
1. A **Beszerzés ideje** mezőbe írja be, hogy „5”.
1. Válassza a **Mentés** lehetőséget.

> [!NOTE]
> Gyártott cikkek esetén a termelés átfutási **idejét** használja a rendszer, ha nincs útvonal a cikkhez. Ha a cikkhez van aktív útvonal társítva, az alaptervezés ütemezi a rendelést, és kiszámítja a dátumokat az erőforrások útvonal-időpontjai és kapacitása alapján (ha van ilyen).

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
