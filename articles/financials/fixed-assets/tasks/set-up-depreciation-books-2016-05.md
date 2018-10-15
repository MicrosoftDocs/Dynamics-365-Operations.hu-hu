--- 
title: "Értékcsökkenési könyvek beállítása (2016. május)"
description: "Ez a feladat-útmutató új értékcsökkenés könyvet hoz létre, illetve azt egy tárgyieszköz-csoporthoz társítja."
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetDepBookTable, AssetGroupDepBookSetup
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 1fd53ea1dff9b116d19c525c5d6967ece0993b6f
ms.contentlocale: hu-hu
ms.lasthandoff: 09/14/2018

---
# <a name="set-up-depreciation-books-may-2016"></a>Értékcsökkenési könyvek beállítása (2016. május)

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ez a feladat-útmutató új értékcsökkenés könyvet hoz létre, illetve azt egy tárgyieszköz-csoporthoz társítja.  Ez a Könyvelői szerepkört és a bemutató adatokat használja a USMF jogi személyhez.


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


