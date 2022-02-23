---
title: " Hűségpontok definiálása"
description: Ez az eljárás hűségpontok definiálását mutatja be.
author: scott-tucker
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailLoyaltyRewardPoints
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4e40ebcbf3ab1befc641ae34571a8b974bd0425a
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4412905"
---
# <a name="define-loyalty-reward-points"></a> Hűségpontok definiálása

[!include [banner](../includes/banner.md)]

Ez az eljárás hűségpontok definiálását mutatja be. Hűségprogram beállítása előtt szükséges a hűségpontok beállítása. Ez az eljárás az USRT bemutatócéget használja.

1. Nyissa meg a következőt: Kiskereskedelem és kereskedelem > Vevők > Hűség > Hűségpontok.
2. Kattintson az Új elemre.
3. Írjon be egy értéket a Hűségpont azonosítója mezőbe.
4. A Leírás mezőben adjon meg egy értéket.
5. A Hűségpont típusa mezőben válasszon ki egy lehetőséget.
    * Válassza ki a Mennyiség lehetőséget, ha a legközelebb egész számra kívánja kerekíteni a hűségpontokat. Válassza ki az Összeg lehetőséget, ha a pénzkerekítés szabályai szerint kívánja kerekíteni a hűségpontokat. Ha a Mennyiség lehetőséget választja, hagyja ki az eljárás következő lépését.  
6. Érték beírása a Pénznem mezőbe.
    * Az Összeg típusú hűségpontok esetében minden pont a kiválasztott pénznemben kerül elszámolásra. A Mennyiség típusú hűségpontok esetében ez a mező nem érvényes, ugorja át ezt a lépést.  
7. Jelölje be a Beváltható jelölőnégyzetet, vagy törölje a jelölést.
8. Adjon meg egy számot a Beváltási rangsor mezőben.
    * Beváltási rangsort akkor használ a rendszer, ha két vagy több beváltható hűségponttal lehet fizetni a termékekért. Ha a két hűségpont beváltási rangsorban elfoglalt helye megegyezik, akkor a kevesebb pontszámot igénylő kerül felhasználásra.  
9. Adjon meg egy számot a Lejárati idő értéke mezőben.
    * A hűségpontok a kiadásukkor meghatározott napok, hónapok vagy évek elteltével lejárnak. A „0” érték azt jelenti, hogy a hűségpontok nem járnak le.  
10. Válasszon ki egy lehetőséget a Lejárati idő egysége mezőben.
11. Kattintson a Mentés gombra.

