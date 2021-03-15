---
title: A szállítmányozók beállítása
description: Ez a témakör bemutatja, hogyan lehet beállítani a szállítmányozót, és meghatározni az olyan részleteket, mint például a szolgáltatás, a szállítási mód, a szállítási ajánlat, a szállítási megszorítások és a szállítási díj.
author: ShylaThompson
manager: tfehr
ms.date: 07/19/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSShippingCarrierCustomerAccount,TMSCarrier
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 124f7473cbdae8890f74115d461603f50cc58be8
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "5004877"
---
# <a name="set-up-shipping-carriers"></a>A szállítmányozók beállítása

[!include [banner](../../includes/banner.md)]

Ez a témakör bemutatja, hogyan lehet beállítani a szállítmányozót, és meghatározni az olyan részleteket, mint például a szolgáltatás, a szállítási mód, a szállítási ajánlat, a szállítási megszorítások és a szállítási díj. A szállítási koordinátor ezután hozzárendelheti a szállítmányozót egy bejövő vagy kimenő rakományhoz.


## <a name="create-a-new-shipping-carrier"></a>Új szállítmányozó létrehozása
1. Ugorjon a **Navigációs ablaktábla > Modulok > Szállításkezelés > Beállítás > Szállítmányozók > Szállítmányozók** lehetőségre.
2. A Művelet panelen válassza az **Új** lehetőséget.
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



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]