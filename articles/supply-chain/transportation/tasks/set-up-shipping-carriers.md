---
title: A szállítmányozók beállítása
description: Ez a témakör bemutatja, hogyan lehet beállítani a szállítmányozót, és meghatározni az olyan részleteket, mint például a szolgáltatás, a szállítási mód, a szállítási ajánlat, a szállítási megszorítások és a szállítási díj.
author: ShylaThompson
manager: AnnBe
ms.date: 07/19/2019
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
ms.openlocfilehash: 7a43a99e10b915f1265be14f2442069dae3a22e5
ms.sourcegitcommit: a368682f9cf3897347d155f1a2d4b33e555cc2c4
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/08/2019
ms.locfileid: "1867027"
---
# <a name="set-up-shipping-carriers"></a>A szállítmányozók beállítása

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ez a témakör bemutatja, hogyan lehet beállítani a szállítmányozót, és meghatározni az olyan részleteket, mint például a szolgáltatás, a szállítási mód, a szállítási ajánlat, a szállítási megszorítások és a szállítási díj. A szállítási koordinátor ezután hozzárendelheti a szállítmányozót egy bejövő vagy kimenő rakományhoz.


## <a name="create-a-new-shipping-carrier"></a>Új szállítmányozó létrehozása
1. Ugorjon a **Navigációs ablaktábla > Modulok > Szállításkezelés > Beállítás > Szállítmányozók > Szállítmányozók** lehetőségre.
2. A műveleti ablaktáblán válassza ki az **Új** elemet.
3. Adjon meg egy értéket a **Szállítmányozók** mezőben.
4. Írjon be egy értéket a **Név** mezőbe.
5. A **Mód** mezőben válasszon ki egy opciót a legördülő menüben.

## <a name="fill-in-the-general-information-for-the-shipping-carrier"></a>A szállítmányozóra vonatkozó általános információk kitöltése
1. Bontsa ki az **Áttekintés** részt.
2. Jelölje be a **Szállítmányozó aktiválása** jelölőnégyzetet, vagy törölje a kijelölést.
3. A **Szállítói számla** mezőben válasszon ki egy lehetőséget a legördülő menüben. Válassza ki a szállítmányozóhoz hozzárendelendő szállítókódot.  
4. A **Szállítási ajánlat típusa** mezőben válasszon ki egy lehetőséget. Válassza ki a **Kézi** lehetőséget a Szállítási ajánlat oldal használatához, vagy válassza ki az **EDI** lehetőséget az ajánlat frissítéséhez az Electronic Data Interchange (EDI) szolgáltatással.  
5. Jelölje be a **Szállítmányozóminősítés engedélyezése** jelölőnégyzetet, vagy törölje a kijelölést.

## <a name="create-the-necessary-services-for-the-shipping-carrier"></a>A szállítmányozó számára szükséges szolgáltatások létrehozása
1. Bontsa ki a **Szolgáltatások** részt.
2. Válassza az **Új** lehetőséget.
3. Adjon meg egy értéket a **Szállítmányozói szolgáltatás** mezőben.
4. Írjon be egy értéket a **Név** mezőbe.
5. A **Szállítási mód** mezőben válasszon ki egy opciót a legördülő menüben.

## <a name="set-up-the-address-for-the-carrier-optional"></a>A szállítmányozó címének beállítása (opcionális)
1. Bontsa ki a **Címek** szakaszt.
2. Válassza az **Új** lehetőséget.
3. Adjon meg egy értéket a **Név vagy leírás** mezőben.
4. Az **Ország/régió** mezőben válasszon ki egy lehetőséget a legördülő menüben.
5. A **Záró irányítószám** mezőben válasszon ki egy lehetőséget a legördülő menüben.
6. Adjon meg egy értéket az **Utca** mezőben.
7. Válassza ki az **OK** lehetőséget.

## <a name="set-up-the-rating-profile-for-the-shipping-carrier"></a>A szállítmányozó díjazási profil beállítása.
1. Bontsa ki a **Díjazási profilok** részt.
2. Válassza az **Új** lehetőséget.
3. Adjon meg egy értéket a **Díjazási profilok** mezőben.
4. Írjon be egy értéket a **Név** mezőbe.
5. A **Hely** mezőben válasszon ki egy lehetőséget a legördülő menüben.
6. A **Raktár** mezőben válasszon ki egy lehetőséget a legördülő menüben.
7. A **Díjkalkulátor** mezőben válasszon ki egy lehetőséget a legördülő menüben. Válassza ki a szállítmányozóval kötött szerződésnek megfelelő díjkalkulátort.  
8. A **Díjjegyzék** mezőben válasszon ki egy lehetőséget a legördülő menüben.
9. A **Szállításiidő-kalkulátor** mezőben válasszon ki egy lehetőséget a legördülő menüben.
10. Válassza a **Mentés** lehetőséget.

