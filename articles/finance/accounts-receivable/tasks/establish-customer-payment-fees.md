---
title: Vevői kifizetések díjainak kialakítása
description: Fizetési díj létrehozása vevői kifizetésekhez.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/09/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustPaymFee, CustPaymModeFee, BankAccountTableLookUp
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b6475671002379d84519df05a0198a17ac000677
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/18/2020
ms.locfileid: "3143742"
---
# <a name="establish-customer-payment-fees"></a>Vevői kifizetések díjainak kialakítása

[!include [banner](../../includes/banner.md)]

Fizetési díj létrehozása vevői kifizetésekhez.

Ez a feladat az USMF bemutatócéget használja.

1. A **Navigációs ablaktáblán** ugorjon a **Modulok > Követelések és beszedések > Fizetés beállítása > Kifizetési illeték** elemre.
2. Kattintson az **Új** elemre.
3. A **Díj azonosítója** mezőben adjon meg egy azonosítót. A díj azonosítója megjelenik a kifizetési naplókban, ezért érdemes leíróvá tenni, hogy megértse, milyen díj kezelésére történik.  
4. A **Név** mezőben adjon meg egy nevet.
5. A **Díj leírása** mezőben adjon meg egy leírást a díjhoz.
6. Adja meg a **Díj mezőben**, hogy a díjat a vevőnek vagy a főkönyvnek számítsák fel. Ha a vevő kezelte a díjat, válassza a Vevő lehetőséget. Ha a díj kezelése a szervezetnél történik költségként, válassza a főkönyvet. Ehhez válassza ki a Vevőt.  
7. A **Napló típusa** mezőben válassza ki azt a naplótípust, amely a kifizetési díjhoz használható. Ha ezeket a díjakat vevőkifizetéshez használja, a naplótípus valószínűleg vevői kifizetés.  
8. Kattintson a **Mentés** gombra.
9. Kattintson a **Kifizetési díj beállítása** lehetőségre. A kifizetési díj beállításában meghatározhatja a kifizetési díj értékelésének feltételét.  Meghatározhatja például, hogy a díj akkor kerül kiszámításra, ha a bankszámla USMF OPER, és a fizetési mód csekk.  
10. A **Csoportosítások** mezőben válassza ki a Tábla, Csoport vagy Összes lehetőséget, hogy meghatározza, mely bankszámlák értékeljék ezt a díjat. Ha az Összes lehetőséget választja, minden bankszámla értékeli ezt a díjat.  Ha a Tábla lehetőséget választja, csak a kiválasztott bankszámla értékeli ezt a díjat. Ha a Csoport lehetőséget választja, csak a kiválasztott csoportban lévő bankszámlák értékelik ezt a díjat.  
11. A **Banki kapcsolat** mezőben válasszon ki egy banki csoportot vagy egy bankszámlát. Ha a Tábla lehetőséget választja, a keresés megjeleníti a bankszámlákat. Ha a Csoport lehetőséget választja, a keresés megjeleníti a bankcsoportokat.  
12. A listában kattintson a kijelölt sorban lévő hivatkozásra.
13. A **Fizetési mód** mezőben válassza ki azt a fizetési módot, amelyhez ezt a díját társítja. Például előfordulhat, hogy egy díjat akkor értékel a vevők számára, ha csekként küldenek fizetést elektronikus kifizetés helyett.  
14. Keresse meg és jelölje ki a kívánt rekordot a listán.
15. Ha szükséges, írjon be egy Fizetési pénznemet a **Kifizetés pénznem** mezőbe. A kifizetés pénzneme további feltétel a díj értékelésére.  Például a bank további díjat számíthat fel az USD pénznemben megkapott kifizetésekre, mert az általános tranzakciók EUR pénznemben történnek.  
16. Adja meg, hogy a díj százalék, összeg vagy intervallum legyen.
17. A **Százalék/összeg mezőbe**írja be a díj százalékát vagy összegét. Ha a Százalék/Összeg mező Százalék, akkor az itt bevitt érték százalék. Ha a Százalék/Összeg mező Összeg, akkor az itt bevitt érték összeg. Ha a Százalék/Összeg mező Intervallum, akkor a szintek meghatározásához használja az Intervallum lapot.  
18. A **Díj pénzneme** mezőben válassza ki a díj pénznemét. A díj ebben a pénznemben kerül létrehozásra.  
19. Kattintson a **Mentés** gombra.

