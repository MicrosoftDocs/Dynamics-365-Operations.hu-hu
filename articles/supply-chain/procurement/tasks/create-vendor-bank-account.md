--- 
title: "Szállítói bankszámla létrehozása"
description: "Ez az eljárás bemutatja a szállítóhoz tartozó bankszámla létrehozásának módját."
author: mkirknel
manager: AnnBe
ms.date: 08/25/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: adb759c59d7275e7323dbb760de56acdef2e3cff
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-vendor-bank-account"></a>Szállítói bankszámla létrehozása

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ez az eljárás bemutatja a szállítóhoz tartozó bankszámla létrehozásának módját. Az USMF bemutatócég adataiban használhatja ezt az eljárást.

1. Ugrás a Beszerzés és forrás > Beszállítók > Minden szállító pontra.
2. Válassza ki azt a szállítót, akihez létre szeretne hozni bankszámlát, majd kattintson a Szállítói számla azonosítón található hivatkozásra.
3. A Művelet ablaktáblában kattintson a Szállító elemre.
4. Kattintson a Bankszámlák lehetőségre.
5. Kattintson az Új lehetőségre.
6. A Bankszámla mezőben adjon meg egy értéket.
    * Ez az azonosító a szállítói rekordban szereplő bankszámla azonosítására szolgál.  
7. Írjon be egy értéket a Név mezőbe.
8. A Bankcsoportok mezőben adjon meg vagy válasszon ki egy értéket.
9. Válasszon ki egy beállítást az Útvonalszám típusa mezőben.
    * Ez a nemzetközi fizetésekhez használt útvonaltervezés típusa.  
10. A Bankszámlaszám mezőben adjon meg egy értéket.
11. A SWIFT kód mezőbe írjon be egy értéket.
12. Az IBAN mezőben adjon meg egy értéket.
    * Megfelelő formátumban kell megadni az IBAN számot. Például, a következő számot használhatja: DE89370400440532013000.  
    * A bankszámla állapota aktív, ha a rendszer elérte az Aktivitás dátumát, és nem lépte túl a Lejárati dátumot. Ez akkor is aktív, ha az Aktiválás dátuma és a Lejárati dátum mező egyaránt üres. Ha az Aktiválás dátuma és a Lejárati dátum mezőben szereplő dátumok egyaránt jövőbeli dátumok, akkor nincs lehetőség elektronikus fizetésre. A bankszámla egyébként aktív, és az egyéb fizetési típusok alkalmazhatók.  
13. Bontsa ki a Beállítások szakaszt.
14. Adjon meg egy értéket a Szöveges kód mezőben.
    * Ez a mező egy olyan kódot határoz meg, amely az átvevő banki kivonatán fog megjelenni.  
15. Adjon meg egy értéket az Üzenet a banknak mezőben.
16. Adjon meg egy értéket az Árfolyam-hivatkozás mezőben.
    * Ez az esetleges előzetes vagy a rögzített átváltási árfolyam hivatkozási száma.  
17. A Pénznem mezőben adjon meg vagy válasszon ki egy értéket.
    * Az ellenőrző tranzakciók elküldésekor, ez a szakasz egy áttekintést nyújt a (folyamatban lévő vagy engedélyezett) állapotukról.  
18. Bontsa ki a Cím szakaszt.
19. Bontsa ki az Ellenőrző tranzakciók szakaszt.
20. Bontsa ki vagy csukja össze a Kapcsolattartási adatok szakaszt.
21. Írjon be egy értéket a Telefon mezőbe.
22. Zárja be a lapot.
23. Kattintson a Szerkesztés lehetőségre.
24. Bontsa ki a Kifizetés szakaszt.
25. Válassza ki az újonnan létrehozott számlát a Bankszámla mezőben.
26. Kattintson a Mentés gombra.
    * A cím örökölhető a banki csoporttól, ha meg van határozva egy cím, illetve itt, hozzá is adhatja azt.  


