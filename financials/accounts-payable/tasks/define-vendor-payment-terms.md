--- 
title: "Szállítói kifizetési feltételek meghatározása"
description: "Fizetési feltételek beállítása szállítói számlákhoz."
author: abruer
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: cbac3b27c25377abff341c4bf259e553c14a4ae8
ms.contentlocale: hu-hu
ms.lasthandoff: 07/27/2017

---
# <a name="define-vendor-payment-terms"></a>Szállítói kifizetési feltételek meghatározása

[!include[task guide banner](../../includes/task-guide-banner.md)]

Fizetési feltételek beállítása szállítói számlákhoz. Ez a feladat az USMF bemutatócéget használja.

1. Ugrás a Kötelezettségek > Kifizetés beállítása > Fizetési feltételek elemre.
2. Kattintson az Új lehetőségre.
    * A fizetési feltételek oldalon meghatározhatja az esedékességi dátum számítását. Ez nem a készpénzfizetési engedmény dátumának számítására való.  
3. Írjon be egy értéket a Fizetési feltételek mezőbe.
4. A Leírás mezőben adjon meg egy értéket.
5. A Napok mezőbe írjon be egy számot.
    * Az itt megadott szám hozzáadódik az esedékességi dátumhoz vagy a fizetési módban meghatározott időszak végéhez. Ha például a Nettó lehetőséget választja, a szám az esedékességi dátumhoz adódik hozzá. Ha az Aktuális hónap lehetőséget választja, a szám hozzáadódik az aktuális hónap utolsó napjához, és így kerül kiszámításra az esedékességi dátum.  
6. Kattintson a Mentés gombra.
7. Zárja be a lapot.
8. Ugrás a Kötelezettségek > Kifizetés beállítása > Készpénzfizetési engedmények elemre.
9. Kattintson az Új lehetőségre.
10. A Készpénzfizetési engedmény mezőbe írjon egy azonosítót.
11. A Leírás mezőben adjon meg egy értéket.
12. Ha a szállító többszintű engedményt kínál, válassza ki a következő készpénzfizetési engedményt, ha a jelenlegi lejárt.
13. Zárja be a lapot.
14. A Napok mezőbe írjon be egy számot.
    * A Napok mezőben megadott mennyiség segítségével a készpénzfizetési engedmény számítása történik a Nettó/Aktuális mezőben megadott lehetőségeket is figyelembe véve. Ha a Nettó lehetőséget választotta, a mennyiség hozzáadódik a számla dátumához, és így kerül kiszámításra a készpénzfizetési engedmény dátuma. Ha az Aktuális hónap lehetőséget választotta, a mennyiség hozzáadódik az aktuális hónap végéhez, így kerül kiszámításra a készpénzfizetési engedmény dátuma.  
15. Az Engedmény mezőben adja meg a készpénzfizetési engedmény százalékát. 
16. Adja meg a fő számlát, amelyhez a vevői számlákon feladásra kerül a készpénzfizetési engedmény.
17. Adja meg a fő számlát, amelyhez a szállítói számlákon feladásra kerül a készpénzfizetési engedmény.
    * Ha a „Kedvezmény ellenszámlák” beállításnál a fő számlát jelöli meg a szállítói kedvezményekhez, akkor a rendszer a fő számlát fogja használni.  Ha a beállítás a számlasorokon Számlák, a készpénzfizetési engedmény feladása a számlasor eszköz-/költségszámla részére kerül feladásra.  
18. Kattintson a Mentés gombra.


