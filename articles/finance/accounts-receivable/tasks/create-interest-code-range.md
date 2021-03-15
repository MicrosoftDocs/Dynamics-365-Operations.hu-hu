---
title: Kamatkód létrehozása tartománnyal
description: A kamatkódokat be lehet úgy állítani, hogy különböző kamatösszegeket számoljon egy értéktartomány alapján.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Interest, CustInterestRange
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 56f063e24e2c332889191638b4f6ffcb2c08500d
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4990992"
---
# <a name="create-an-interest-code-with-a-range"></a>Kamatkód létrehozása tartománnyal

[!include [banner](../../includes/banner.md)]
A kamatkódokat be lehet úgy állítani, hogy különböző kamatösszegeket számoljon egy értéktartomány alapján. Ez az eljárás bemutatja, hogyan adhat hozzá egy kamatkódot, illetve ahhoz egy tartományt.

1. Ugorjon a Követel és beszedések > Kamat > Kamatkódok beállítása pontra.
2. Kattintson az Új lehetőségre.
3. A Kamtkód mezőbe írja be a kamatkód nevét.
4. A Leírás mezőben adja meg a kamatkód leírását.
5. Hónap kiválasztása.
6. Bontsa ki a Bevételek szakaszt.
7. Bontsa ki a Bevételek pénznemenként szakaszt.
8. A Főkönyvi feladószámla mezőben adja meg a kívánt értékeket.
9. Válassza ki a „Hónapok” lehetőséget a Kamat tartomány alapján mezőben.
10. Kattintson a Hozzáadás gombra.
11. A Leírás mezőben adja meg a pénznem és a tartomány leírását.
12. Kattintson a Mentés gombra.
13. Kattintson az Tartományok elemre.
14. Kattintson az Új lehetőségre.
15. Adja meg a Kezdő értéknek a 0-t, majd adja meg a havi kamatszázalékot, amely alapján számítva lesz a kamat. Ezen példa esetében ez 1,5.
16. Kattintson az Új elemre.
17. Adja meg a következő kezdőértéknek adja meg a 4-et, ez az első hónap, amelyben új kamatösszeget fog számolni.
18. Adja meg a havi kamatszázalékot, amelyet a kamat kiszámítására használ a 4. hónaptól kezdődően. Ebben a példában ez 2,0.
19. Kattintson az Új elemre.
20. Adja meg a következő kezdőértéknek adja meg a 7-et, ez a következő hónap, amelyben új kamatösszeget fog számolni.
21. Adja meg a havi kamatszázalékot, amelyet a kamat kiszámítására használ a 7. hónaptól kezdődően. Ebben a példában ez 2,5.
22. Kattintson a Bezár gombra a beállítás befejezéséhez.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]