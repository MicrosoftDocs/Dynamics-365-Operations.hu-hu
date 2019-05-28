---
title: Vevői kifizetések díjainak kialakítása
description: Fizetési díj létrehozása vevői kifizetésekhez.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustPaymFee, CustPaymModeFee, BankAccountTableLookUp
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5acb202d46ef39376a01ca592f60926786d11186
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1572974"
---
# <a name="establish-customer-payment-fees"></a>Vevői kifizetések díjainak kialakítása

[!include [task guide banner](../../includes/task-guide-banner.md)]

Fizetési díj létrehozása vevői kifizetésekhez.

Ez a feladat az USMF bemutatócéget használja.

1. Ugorjon a Kinnlevőségek > Fizetési beállítás > Fizetési díj pontra.
2. Kattintson az Új lehetőségre.
3. A Díj azonosítója mezőben adjon meg egy azonosítót.
    * A díj azonosítója megjelenik a kifizetési naplókban, ezért érdemes leíróvá tenni, hogy megértse, milyen díj kezelésére történik.  
4. A Név mezőben adjon meg egy nevet.
5. A Díj leírása mezőben adjon meg egy leírást a díjhoz.
6. Adja meg, hogy a díjat a vevőnek vagy a főkönyvnek számítsák fel.
    * Ha a vevő kezelte a díjat, válassza a Vevő lehetőséget. Ha a díj kezelése a szervezetnél történik költségként, válassza a főkönyvet. Ehhez válassza ki a Vevőt.  
7. Válassza ki a naplótípust, amely használhatja ezt a kifizetési díjat.
    * Ha ezeket a díjakat vevőkifizetéshez használja, a naplótípus valószínűleg vevői kifizetés.  
8. Kattintson a Mentés gombra.
9. Kattintson a Kifizetési díj beállítására.
    * A kifizetési díj beállításában meghatározhatja a kifizetési díj értékelésének feltételét.  Meghatározhatja például, hogy a díj akkor kerül kiszámításra, ha a bankszámla USMF OPER, és a fizetési mód csekk.  
10. Válassza ki a Tábla, Csoport vagy Összes lehetőséget, hogy meghatározza, mely bankszámlák értékeljék ezt a díjat.
    * Ha az Összes lehetőséget választja, minden bankszámla értékeli ezt a díjat.  Ha a Tábla lehetőséget választja, csak a kiválasztott bankszámla értékeli ezt a díjat. Ha a Csoport lehetőséget választja, csak a kiválasztott csoportban lévő bankszámlák értékelik ezt a díjat.  
11. Válasszon bankcsoportot vagy bankszámlát.
    * Ha a Tábla lehetőséget választja, a keresés megjeleníti a bankszámlákat. Ha a Csoport lehetőséget választja, a keresés megjeleníti a bankcsoportokat.  
12. A listában kattintson a kijelölt sorban lévő hivatkozásra.
13. Válassza ki azt a Fizetési módot, amelyhez ezt a díjat értékelik.
    * Például előfordulhat, hogy egy díjat akkor értékel a vevők számára, ha csekként küldenek fizetést elektronikus kifizetés helyett.  
14. Keresse meg és jelölje ki a kívánt rekordot a listán.
15. Ha szükséges, adja meg a kifizetés pénznemét.
    * A kifizetés pénzneme további feltétel a díj értékelésére.  Például a bank további díjat számíthat fel az USD pénznemben megkapott kifizetésekre, mert az általános tranzakciók EUR pénznemben történnek.  
16. Adja meg, hogy a díj százalék, összeg vagy intervallum legyen.
17. Adja meg a díj százalékát vagy összegét.
    * Ha a Százalék/Összeg mező Százalék, akkor az itt bevitt érték százalék. Ha a Százalék/Összeg mező Összeg, akkor az itt bevitt érték összeg. Ha a Százalék/Összeg mező Intervallum, akkor a szintek meghatározásához használja az Intervallum lapot.  
18. A Díj pénzneme mezőben válassza ki a díj pénznemét.
    * A díj ebben a pénznemben kerül létrehozásra.  
19. Kattintson a Mentés gombra.

