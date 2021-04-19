---
title: Raktárak beállítása átmozgatási rendelésekhez
description: Ez a témakör leírja, hogyan állíthat be raktárakat átmozgatási rendelésekhez.
author: Mirzaab
ms.date: 01/18/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventLocation,CustVendTransportPoint2Point
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2018-4-30
ms.dyn365.ops.version: 8
ms.openlocfilehash: 9e4ea0f9720bd4e5d2724b507aa32525ac25fa52
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5823215"
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


[!INCLUDE[footer-include](../../includes/footer-banner.md)]