---
title: Vállalaton belüli árumozgás dokumentumainak beállítása
description: Ez az eljárás bemutatja, hogyan lehet átadási dokumentumokat beállítani a vállalaton belüli árumozgáshoz.
author: v-oloski
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventTransferOrders, InventLocationIdLookup, TransportationDocument, HcmWorkerLookUp, SrsReportViewerForm, InventTransferParmShip
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: v-oloski
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 80805bf30b4be753d7543ed4c6de30401d36e981
ms.sourcegitcommit: 2fba4f2ef7e513357366fc640befe0d2f7bc31f5
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/05/2021
ms.locfileid: "7601450"
---
# <a name="set-up-the-transfer-documents-for-goods-movement-inside-a-company"></a>Vállalaton belüli árumozgás dokumentumainak beállítása

[!include [banner](../../includes/banner.md)]

Ez az eljárás bemutatja, hogyan lehet átadási dokumentumokat létrehozni a vállalaton belüli árumozgáshoz. Ez az eljárás csak litvániai elsődleges címmel rendelkező jogi személyek számára áll rendelkezésre. Az eljárást a DEMF bemutatócéget használva hozták létre, az elsődleges címéhez tartozó ország pedig Litvánia. Ahhoz, hogy befejezhesse ezt az eljárást, végre kell hajtania a következő eljárást: „Vállalaton belüli árumozgás dokumentumainak beállítása”. Ez az eljárás készletkönyvelőknek szól. Az eljárás egy olyan szolgáltatáshoz tartozik, amely a Dynamics 365 for Operations 1611-es verziójában jelent meg.


## <a name="create-a-transfer-order"></a>Átmozgatási rendelés létrehozása
1. Ugrás a következőre: Készletnyilvántartás > Bejövő rendelések > Átmozgatási rendelés.
2. Kattintson az Új lehetőségre.
3. A Forrásraktár mezőben adjon meg vagy válasszon ki egy értéket.
4. A Célraktár mezőben adjon meg vagy válasszon ki egy értéket.
5. Kattintson a Hozzáadás gombra.
6. A listában jelölje meg a kiválasztott sort.
7. Az Elemszám mezőben adjon meg, vagy válasszon ki egy értéket.

## <a name="enter-transportation-details-for-the-transfer-order"></a>Szállítás részleteinek bevitele az átmozgatási rendeléshez
1. Kattintson a Mentés gombra.
2. A Művelet panelen kattintson a Szállítás elemre.
3. Kattintson a Szállítás részletei lehetőségre.
4. Válassza az Igen lehetőséget a Szállítás részletes adatainak nyomtatása mezőben.
5. Az Áruk kiadva általa mezőben adjon meg vagy válasszon ki egy értéket.
6. A Csomag mezőben adjon meg egy értéket.
7. A Rakomány kockázatszintje mezőben adjon meg egy értékét.
8. A Szállítmányozó mezőben adjon meg vagy válasszon ki egy értéket.
9. A Modell mezőben adjon meg vagy válasszon ki egy értéket.
10. Írjon be egy értéket a Regisztrációs szám mezőbe.
11. Írjon be egy értéket az Utánfutó regisztrációs száma mezőbe.
12. A Sofőr mezőben adjon meg vagy válasszon ki egy értéket.
13. Írjon be egy értéket a Járművezető neve mezőbe.
14. Kattintson a Mentés gombra.
15. Zárja be a lapot.

## <a name="view-the-packing-slip-for-the-unposted-transfer-order"></a>Szállítólevél megtekintése a könyveletlen átmozgatási rendeléshez
1. Kattintson a Szállítólevél lehetőségre.
2. Kattintson az OK gombra.
3. Zárja be a lapot.

## <a name="view-the-packing-slip-for-the-posted-transfer-order"></a>Szállítólevél megtekintése a könyvelt átmozgatási rendeléshez
1. Kattintson az Átmozgatási rendelés lehetőségre a Művelet Panelen.
2. A Művelet panelen kattintson a Szállítás elemre.
3. Kattintson az Átmozgatási rendelések szállítása elemre.
4. Kattintson az Általános fülre.
5. A Frissítés mezőben válasszon egy lehetőséget.
6. Kattintson az Áttekintés fülre.
7. Írjon be egy értéket a szállítólevél mezőbe.
8. Kattintson az OK gombra.
9. A Művelet panelen kattintson a Szállítás elemre.
10. Kattintson a Szállítólevél lehetőségre.
11. Kattintson az OK gombra.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
