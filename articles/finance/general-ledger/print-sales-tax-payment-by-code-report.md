---
title: Áfafizetés kód szerint jelentés nyomtatása
description: Ez a témakör olyan beállításokat és műveleteket tartalmaz, amelyek szükségesek az Áfa kifizetése kód szerinti jelentés szerinti kinyomtatásához a könyvelés vagy adózási kód pénznemében.
author: anasyash
ms.date: 05/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: anasyash
ms.search.validFrom: 2020-04-08
ms.dyn365.ops.version: 10.0.11
ms.openlocfilehash: 7c863308d2efc442ad16973407fe1cb72fb68cf89204c20f4468a3c98f4740c5
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6774329"
---
# <a name="print-the-sales-tax-payment-by-code-report"></a>Áfafizetés kód szerint jelentés nyomtatása 

[!include [banner](../includes/banner.md)]

Az **Áfafizetés kód szerint** jelentés kinyomtatásához nyissa meg az **Adó** \> **Lekérdezések és jelentések** \> **Áfajelentések** \> **Áfafizetés kód szerint** lehetőséget. Alapértelmezés szerint a jelentés összegeit a program a jogi személy könyvelési pénznemében generálja az összes jelentési kód esetében, amelyek az **Áfajelentési kódok** oldalon be van állítva.

Ezt a jelentést úgy is generálhatja, hogy az áfakód pénznemében megjelenített forgalmiadó-összegeket minden olyan jelentési kód esetében megjeleníti, amelyek az **Áfakód** lapon hozzá vannak rendelve az áfakódokhoz.

## <a name="turn-on-the-feature"></a>A funkció bekapcsolása

A **Funkciókezelés** munkaterületen kapcsolja be a következő funkciót: **Áfafizetés kód szerint jelentés generálása az áfakód pénznemében**.

## <a name="run-the-report"></a>A jelentés futtatása

1. Ugorjon az **Adó** \> **Lekérdezések és jelentések** \> **Áfajelentések** \> **Áfafizetés kód szerint** lehetőségre.
2. A **Jelentés pénzneme** mezőben válassza a következő értékek egyikét:

    - **Könyvelési pénznem** – A jelentés összegeinek nyomtatása a könyvelési pénznemben.
    - **Áfakód pénzneme** – A jelentés összegének nyomtatása az áfakód pénznemében.

    ![Áfafizetés kód szerint párbeszédpanel.](media/Sales-tax-payment-by-code.png)

A következő ábra egy példát mutat be a generált jelentésre. A jelentés azt jeleníti meg , hogy a **101** jelentési kód az pénzneme **EUR** ha az **Áfa pénzneme mező** **EUR** értékre van állítva az áfakódhoz, amelyhez a jelentési kód hozzá van rendelve.

![Áfafizetés kód szerint jelentés nyomtatása példája.](media/Sales-tax-payment-by-code-2.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]