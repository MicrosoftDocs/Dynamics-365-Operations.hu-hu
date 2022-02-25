---
title: Kamatkód létrehozása tartománnyal
description: A kamatkódokat be lehet úgy állítani, hogy különböző kamatösszegeket számoljon egy értéktartomány alapján.
author: ShivamPandey-msft
ms.date: 02/11/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: Interest, CustInterestRange
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d77fc88f606f4e690583fbcda79f628a35f14f6a
ms.sourcegitcommit: 6a269db08e8bb3bb3405c9f4a512091d13c80faa
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/14/2022
ms.locfileid: "8119474"
---
# <a name="create-an-interest-code-with-a-range"></a>Kamatkód létrehozása tartománnyal

[!include [banner](../../includes/banner.md)]
A kamatkódokat be lehet úgy állítani, hogy különböző kamatösszegeket számoljon egy értéktartomány alapján. Ez az eljárás bemutatja, hogyan adhat hozzá egy kamatkódot, illetve ahhoz egy tartományt.

1. Ugrás a Kamat **> és beszedési > Kamatkódok beállítása**.
2. Kattintson az **Új** elemre.
3. A Kamatkód **mezőbe** írja be a kamatkód nevét.
4. A Leírás **mezőbe** írja be a kamatkód leírását.
5. Válassza ki a **hónapot**.
6. Bontsa ki **a Bevételek szakaszt**.
7. Bontsa ki **a Bevétel pénznem szerint szakaszt**.
8. Adja meg **a kívánt** értékeket a Főkönyvi feladási számla mezőben.
9. A Kamat **tartomány szerint mezőben** válassza a "Hónapok" lehetőséget.
10. Kattintson a **Hozzáadás** parancsra.
11. A Leírás **mezőbe** írja be a pénznem és a tartomány leírását.
12. Kattintson a **Mentés** gombra.
13. Kattintson a Tartományok **gombra**.
14. Kattintson az **Új** elemre.
15. Adja meg **a 0 értéket** a From értékként, majd adja meg a kamatszámításhoz használt havontai kamat százalékos értékét. Ezen példa esetében ez 1,5.
16. Kattintson az **Új** elemre.
17. Adja meg a következő kezdőértéknek adja meg a 4-et, ez az első hónap, amelyben új kamatösszeget fog számolni.
18. Adja meg a havi kamatszázalékot, amelyet a kamat kiszámítására használ a 4. hónaptól kezdődően. Ebben a példában ez 2,0.
19. Kattintson az **Új** elemre.
20. Adja meg a következő kezdőértéknek adja meg a 7-et, ez a következő hónap, amelyben új kamatösszeget fog számolni.
21. Adja meg a havi kamatszázalékot, amelyet a kamat kiszámítására használ a 7. hónaptól kezdődően. Ebben a példában ez 2,5.
22. A beállítás **befejezéséhez** kattintson a Bezárás gombra.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
