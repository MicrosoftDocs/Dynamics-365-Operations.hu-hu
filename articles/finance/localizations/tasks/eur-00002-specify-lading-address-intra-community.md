---
title: EUR-00002 Közösségen belüli tranzakcióhoz berakodási cím megadása
description: Ez az eljárás bemutatja, hogyan adhatja meg egy közösségen belüli kereskedelmi tranzakció berakodási címét.
author: v-oloski
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PurchTable, PurchCreateOrder, InventItemIdLookupPurchase, TransportationDocument, LogisticsPostalAddress, SysLookupMultiSelectGrid,  VendEditInvoice, VendEditInvoiceDefaultQuantityForLinesDropDialog, Intrastat, SysQueryForm
audience: Application User
ms.reviewer: kfend
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: v-oloski
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 68a62a26be418b7a0cb8e17532d022d76cd552411f438ffc5a0ddad589a9e476
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6780793"
---
# <a name="eur-00002-specifying-a-lading-address-for-an-intra-community-transaction"></a>EUR-00002 Közösségen belüli tranzakcióhoz berakodási cím megadása

[!include [banner](../../includes/banner.md)]

Ez az eljárás bemutatja, hogyan adhatja meg egy közösségen belüli kereskedelmi tranzakció berakodási címét. Például egy német cég egy német üzleti címmel rendelkező szállítótól rendel cikkeket. A szállítónak van egy raktára Olaszországban, és innen szállítja a cikkeket. Ezt a szállítást jelenteni kell az Intrastatban. Ugyanez érvényes az ügyfél visszáruszállításaira is.
Ez az eljárás minden európai országra/régióra vonatkozik. Ezt a feladatot a németországi elsődleges címmel rendelkező DEMF bemutatócég segítségével hozták létre. Az eljárás végrehajtása előtt be kell állítania az Intrastat jelentéskészítést. Ez az eljárás könyvelőknek szól. Az eljárás egy olyan szolgáltatáshoz tartozik, amely a Dynamics 365 for Operations 1611-es verziójában jelent meg.

1. Nyissa meg a következőt: Kötelezettségek > Beszerzési rendelések > Minden beszerzési rendelés.
2. Kattintson az Új lehetőségre.
3. Érték megadása vagy kiválasztása.
    * Válassza ki például a DE-001-et. A szállító német üzleti címmel rendelkezik.  
4. Kattintson az OK gombra.
5. A listában jelölje meg a kiválasztott sort.
6. Az Elemszám mezőben adjon meg, illetve válasszon ki egy értéket: D0001.
7. Kattintson a Mentés gombra.
8. A Művelet panelen kattintson a Fogadás elemre.
9. Kattintson a Szállítás részletei lehetőségre.
10. A Berakodás dátuma és időpontja mezőben adjon meg egy dátumot és időpontot.
11. Kattintson az Új cím felvétele lehetőségre.
12. Kattintson az Új gombra, és hozzon létre egy új címet, amelynek a célja a berakodás.
13. A Név vagy leírás mezőbe írja be az „olasz” értéket.
14. Értékként válassza ki a berakodást.
    * Fontos megjegyezni, hogy a cím céljának berakodásnak kell lennie.  
15. Az Ország/régió mezőben adja meg vagy válassza az ITA értéket.
16. Kattintson a Mentés gombra.
17. Zárja be a lapot.
18. Kattintson a Mentés gombra.
    * Ellenőrizze a berakodási cím helyességét.  
19. Zárja be a lapot.
20. A Művelet panelen kattintson a Beszerzés elemre.
21. Kattintson a Megerősítés gombra.
22. A Művelet panelen kattintson a Számla lehetőségre.
23. Kattintson a Számla lehetőségre.
24. Érték beírása a Szám mezőbe.
25. A Számla dátuma mezőben adjon meg egy dátumot.
26. Kattintson az Alapértelmezett forrás: Termék érkező mennyisége lehetőségre a legördülő párbeszédablak megnyitásához.
27. A Sorok alapértelmezett mennyisége mezőben válassza ki a „Megrendelt mennyiség” lehetőséget.
28. Kattintson az OK gombra.
29. Kattintson a Szállítás részletei lehetőségre.
    * Győződjön meg arról, hogy az árukat Olaszországból szállítják. Szükség esetén módosíthatja a berakodás részleteit.  
30. Zárja be a lapot.
31. Kattintson a Feladás lehetőségre.
32. Zárja be a lapot.
33. Ugorjon az Adó > Nyilatkozatok > Külkereskedelem > Intrastat pontra.
34. Kattintson az Áthelyezés elemre.
35. Válassza ki az Igen lehetőséget a Szállítói számla mezőben.
36. Kattintson az OK gombra.
37. Kattintson az Általános fülre.
    * Keressen meg egy újonnan létrehozott sort, és győződjön meg arról, hogy a feladó az árukat Olaszországból szállította.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]