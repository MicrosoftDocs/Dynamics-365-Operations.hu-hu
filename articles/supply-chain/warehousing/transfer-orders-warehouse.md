---
title: Raktárak beállítása átmozgatási rendelésekhez
description: Ez a témakör leírja, hogyan állíthat be raktárakat átmozgatási rendelésekhez.
author: Mirzaab
manager: AnnBe
ms.date: 01/18/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2018-4-30
ms.dyn365.ops.version: 8
ms.openlocfilehash: 91db6e8f921bd674211f6d478b6d0f0a832c983c
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/01/2019
ms.locfileid: "1847015"
---
# <a name="set-up-warehouses-for-transfer-orders"></a>Raktárak beállítása átmozgatási rendelésekhez 

[!include [banner](../includes/banner.md)]

A raktári szintek segítségével lehet létrehozni olyan hierarchiát, amely támogatja a raktárok közötti átmozgatási rendeléseket. Ezen beállítás alapján számítja ki az alapütemezés az egyedi raktári szinteken szükséges cikkeket, és létrehozza a tervezett átmozgatási rendeléseket a feltöltéshez társított forrásraktárból.

1.  Kattintson a **Készletgazdálkodás > Beállítás > Készlet részletezése > Raktárak** lehetőségre.

2.  Az  lapon válassza ki a újratöltendő raktárat.

3.  Az **Alaptervezés** gyorslapon jelölje be a **Feltöltés** jelölőnégyzetet.

4.  A **Főraktár** mezőben válassza ki az újratöltési raktárként társítandó raktárt. Az alapütemezés kiszámítja a kiválasztott raktár esetében szükséges átmozgatást, és létrehoz egy tervezett átmozgatási rendelést a társított **Főraktár** forrásból.
   
    > [!NOTE]
    > <P>Ha üresen hagyja a <STRONG>Feltöltés</STRONG> jelölőnégyzetet a kiválasztott raktárhoz a rendszer a <STRONG>Főraktár</STRONG> alapján viszonyított raktárszintet társít, a <STRONG>Főraktár</STRONG> azonban nincs beállítva feltöltő raktárként.</P>

5.  Az új beállítások alkalmazásához zárja be az oldalt.


> [!TIP]
> <P>Ha szeretne feltöltési raktárt társítani, először tárolási dimenzióként kell beállítani a raktárt a <STRONG>Tárolásidimenzió-csoportok</STRONG> lapon. Ezen a lapon válassza ki a <STRONG>Aktív</STRONG> mezőt és a <STRONG>Fedezeti terv dimenziónként</STRONG> mezőt a raktárhoz.</P>

## <a name="set-up-transport-lead-time"></a>Szállítás átfutási idejének beállítása

Be kell állítania a raktárak között a szállítás átfutási idejét is a **Szállítási napok** oldalon. 
1. Menjen a **Készletkezelés > Beállítások > Elosztás > Szállítási napok** menübe.
2. Válasszon egy **raktárat** a **Bevételezési pont** mezőben.
3. Válassza ki a **Szállítási raktár**, **Fogadó raktár**, és **Szállítási napok** értékeket. 
4. (Nem kötelező) Beállíthatja a szállítási időt, a szállítási módtól függően a **Szállítási napok a szállítás módja szerint** lapon.
