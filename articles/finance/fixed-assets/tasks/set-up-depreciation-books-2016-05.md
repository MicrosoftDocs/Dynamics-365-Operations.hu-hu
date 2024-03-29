---
title: Értékcsökkenési könyvek beállítása
description: Ez az eljárás végigvezeti egy új értékcsökkenési könyv létrehozási folyamatán, és annak hozzárendelésén egy tárgyieszköz-csoporthoz.
author: moaamer
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: AssetDepBookTable, AssetGroupDepBookSetup
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4a4713d949fe119cde1b1187a7c485d291281a8f
ms.sourcegitcommit: 631d2cea52590af15f208e9af584446e85540fcf
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/07/2022
ms.locfileid: "8725652"
---
# <a name="set-up-depreciation-books"></a>Értékcsökkenési könyvek beállítása 

[!include [banner](../../includes/banner.md)]

Ez az eljárás végigvezeti egy új értékcsökkenési könyv létrehozási folyamatán, és annak hozzárendelésén egy tárgyieszköz-csoporthoz. 

## <a name="create-a-depreciation-book"></a>Hozzon létre egy értékcsökkenés könyvet.
1. Ugorjon a Tárgyi eszközök > Beállítás > Értékcsökkenés könyvek pontra.
2. Kattintson az Új lehetőségre.
3. Írjon egy értéket az Értékcsökkenés könyv mezőbe.
4. A Leírás mezőben adjon meg egy értéket.
5. Az Értékcsökkenés kiszámítása jelölőnégyzet bejelölése vagy a jelölés törlése.
6. Az Értékcsökkenési profil mezőben kattintson a legördülő gombra a keresőlista megnyitásához.
7. Keresse meg majd válassza ki a listából a kívánt értékcsökkenési profilt.
8. A listában kattintson a kijelölt sorban lévő hivatkozásra.
9. Az Alternatív értékcsökkenési profil mezőben kattintson a legördülő gombra a keresőlista megnyitásához.
10. Válassza ki a listából a kívánt értékcsökkenési profilt.
11. A listában kattintson a kijelölt sorban lévő hivatkozásra.
    * A Rendkívüli értékcsökkenési profil egy adott eszköz további értékcsökkenéséhez használható nem szokványos körülmények esetén. Ezt például akkor alkalmazhatja, ha természeti katasztrófa okozta értékcsökkenést kell rögzítenie.  
12. Jelölje be az Értékcsökkenés kiigazítása az értékcsökkenési alap kiigazításával jelölőnégyzetet vagy törölje a jelölést.
13. A Naptár mezőben kattintson a legördülő gombra a keresőlista megnyitásához.
14. A listában kattintson a kijelölt sorban lévő hivatkozásra.

## <a name="associate-the-depreciation-book-with-a-fixed-asset-group"></a>Társítsa az értékcsökkenés könyvet egy tárgyieszköz-csoporthoz
1. Kattintson a Tárgyieszköz-csoportok elemre.
2. A Tárgyieszköz-csoport mezőben kattintson a legördülő gombra a keresőlista megnyitásához.
3. A kívánt rekord megkeresése és kijelölése a listán
4. A listában kattintson a kijelölt sorban lévő hivatkozásra.
5. Válassza ki valamelyik lehetőséget az Értékcsökkenési szabály mezőben.
6. Adjon meg egy számot az Élettartam mezőben.
    * Figyelje meg, hogy az Értékcsökkenési időszakok mező értéke az Élettartam beállítását követően kerül kiszámításra.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
