---
title: Szállítói kifizetési díjak meghatározása
description: Szállítói kifizetési díjak beállítása.
author: abruer
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendPaymFee, VendPaymModeFee, BankAccountTableLookUp
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 52321851a1aa588a0bbe238e366a28d503665988
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4979338"
---
# <a name="define-vendor-payment-fees"></a>Szállítói kifizetési díjak meghatározása

[!include [banner](../../includes/banner.md)]

Szállítói kifizetési díjak beállítása. Ez a feladat az USMF bemutatócéget használja.

1. Ugrás a Kötelezettségek > Kifizetés beállítása > Fizetési díj elemre.
2. Kattintson az Új lehetőségre.
3. Írjon be egy értéket a Díj azonosítója mezőbe.
    * A díj azonosítójának mutatnia kell, hogy mikor használatos a díj, pl. „elektronikus átutalási díj”.  
4. Írjon be egy értéket a Név mezőbe.
5. A „Díj leírása” mezőbe írjon egy értéket.
    * Adjon meg leírást, amelyben további részleteket közöl a díj értékeléséről.  
6. A Költség mezőben válassza ki a Szállító vagy Főkönyv lehetőséget.
    * A főkönyv akkor kerül használatra, ha a díj költségként megjelenik a szervezetében.  A Szállítót akkor használja, ha a díj a szállítónál kerül értékelésre.  
7. Adjon meg egy fő számlát, ahová a díj elszámolása megtörténik.
    * Ez a lehetőség csak akkor használható, ha meg van adva a Főkönyv a Költség lehetőségnél.  
8. Válassza ki a naplót, amelyben ez a díj felhasználható. 
    * Szállítói fizetési díj esetén válassza a „Szállítói kifizetés” naplót.  
9. Kattintson a Mentés gombra.
10. Kattintson a Kifizetési díj beállítására.
    * Folytassa a Fizetési díj beállítást, és adja meg a díj alapértelmezett idejét a kiválasztott naplóban.  
11. Válassza ki a Tábla, Csoport vagy Összes lehetőséget.
    * A Tábla lehetőséget egyetlen bankszámla kiválasztására használhatja, a Csoporttal bankcsoportot választhat ki, az Összes lehetőséggel pedig minden bankszámlához használhatja a mostani díjbeállítást.  
12. Válasszon bankcsoportot vagy bankszámlát.
    * A keresés bankcsoportot jelenít meg, ha a Csoport lehetőséget választotta, és bankszámlákat, ha a Tábla lehetőséget választotta.  
13. Válassza ki a fizetési módnál a díj értékelésének idejét.
14. Válassza ki a kiválasztott fizetési mód fizetési meghatározását.
    * A Fizetési meghatározás a kifizetések elektronikus alapok átutalási módjainak használatos.  
15. Adja meg, hogy a díj százalék, összeg vagy intervallum legyen.
16. Adja meg a díj százalékos értékét vagy összegét.
    * Ha a díj százalék, adja meg a százalékot. Ha a díj összeg, adja meg a díj összegét. Ha a díj intervallum, az Intervallum lapon határozza meg a díjak szintjeit.  
17. A Díj pénzneme mezőben válassza ki a díj értékelésének pénznemét.
    * Ez a pénznem a díjra vonatkozik. A fizetési pénznem azt határozza meg, hogy a díj szabálya a fizetés pénzneme alapján kerüljön-e értékelésre. Előfordulhat például, hogy a bank díjat számít fel, ha a fizetés EUR pénznemben történik, de az egyéb fizetések díjmentesek.  
18. Kattintson a Mentés gombra.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]