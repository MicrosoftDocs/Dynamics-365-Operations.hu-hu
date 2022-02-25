---
title: Szállítói kifizetési díjak meghatározása
description: Szállítói kifizetési díjak beállítása.
author: abruer
ms.date: 02/11/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: VendPaymFee, VendPaymModeFee, BankAccountTableLookUp
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c490bb4d15fa03742b12f337046f26976ab70d29
ms.sourcegitcommit: 3105642fca2392edef574b60b4748a82cda0a386
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/12/2022
ms.locfileid: "8109831"
---
# <a name="define-vendor-payment-fees"></a>Szállítói kifizetési díjak meghatározása

[!include [banner](../../includes/banner.md)]

Szállítói kifizetési díjak beállítása. Ez a feladat az USMF bemutatócéget használja.

1. Ugrás a Kötelezettségek **> beállításhoz és > kifizetési díjhoz**.
2. Kattintson az **Új** elemre.
3. A Díjazonosító **mezőbe** írjon be egy értéket.
    * A **díjazonosítónak** le kell írnia, hogy mikor lesz használva ez a díj, például "EFT_Fee".  
4. Írjon be egy értéket a **Név** mezőbe.
5. A Díj **leírása mezőbe** írjon be egy értéket.
    * Adjon meg leírást, amelyben további részleteket közöl a díj értékeléséről.  
6. A Költség **mezőben** válassza a Szállító vagy a **Főkönyv** lehetőséget **·**.
    * **A** főkönyv akkor használatos, amikor a díj a vállalatnak lesz költségként felszámlázva. **A** szállító használata akkor történik meg, amikor a díjat ki kell fizetnie a szállítónak.  
7. Adjon meg egy fő számlát, ahová a díj elszámolása megtörténik.
    * Ez a lehetőség csak akkor érhető el, ha költségként **a** Főkönyv lehetőséget **választja**.  
8. Válassza ki a naplót, amelyben ez a díj felhasználható. 
    * Szállítói fizetési díj esetén válassza a „Szállítói kifizetés” naplót.  
9. Kattintson a Save **gombra**.
10. Kattintson a **Kifizetési díj beállítása** lehetőségre.
    * A kifizetési díj beállításának **folytatása annak** meghatározásához, hogy a kiválasztott naplóban mikor legyen alapértelmezés a díj.  
11. Válassza a **Tábla**, a **Csoport vagy** a Mind **lehetőséget**.
    * **A** tábla egyetlen bankszámla kiválasztására használható, **a** Csoport csoport egy bankcsoport kiválasztására, **és** mind ezt a díjbeállítást használja minden bankszámlára.  
12. Válasszon bankcsoportot vagy bankszámlát.
    * A keresés a bankcsoportot mutatja, ha a **Csoport** beállítást választotta, és a bankszámlákat is, ha a **Tábla beállítást választotta**.  
13. Válassza ki a fizetési módnál a díj értékelésének idejét.
14. A kiválasztott **fizetési mód** kifizetési előírásának kiválasztása.
    * A **kifizetési előírás** az elektronikus alap átutalási módjainál használatos.  
15. Adja meg, hogy a díj százalék, összeg vagy intervallum legyen.
16. Adja meg a díj százalékos értékét vagy összegét.
    * Ha a **Díj** egy százalék, adja meg a százalékot. Ha a **Díj** egy összeg, adja meg a díj összegét. Ha a **díj** intervallum, **akkor az Intervallum** lapon definiálja a többszintű díjakat.  
17. Válassza ki **a Díj pénzneme** mezőben azt a pénznemet, amelyben az illetéket ki fogja értékelni.
    * Ez a pénznem a díjra vonatkozik. A fizetési pénznem azt határozza meg, hogy a díj szabálya a fizetés pénzneme alapján kerüljön-e értékelésre. Előfordulhat például, hogy a bank díjat számít fel, ha a fizetés EUR pénznemben történik, de az egyéb fizetések díjmentesek.  
18. Kattintson a **Mentés** gombra.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
