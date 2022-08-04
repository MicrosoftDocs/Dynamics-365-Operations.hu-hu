---
title: Vevői kifizetések feltételeinek kialakítása
description: Ez az eljárás a készpénzfizetési engedményt és az esedékességi dátumot állítja be.
author: aprilolson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PaymDay, PaymTerm, CashDisc
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6069d28d84ab1705fd62a33cea7e0b923f0e0705
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/29/2022
ms.locfileid: "9065708"
---
# <a name="establish-customer-payment-terms"></a>Vevői kifizetések feltételeinek kialakítása

[!include [banner](../../includes/banner.md)]

Ez az eljárás a készpénzfizetési engedményt és az esedékességi dátumot állítja be. Ez az útmutató-feladat az USMF bemutatócéget használja.

1. Válassza a **Navigációs ablaktábla >Modulok > Kinnlévőségek > Kifizetések beállítása > Kifizetési napok** elemet. A **fizetési feltételek** beállítását a **Kötelezettségek** és a **Kinnlevőségek** közösen használják. Ha azt megadja ebben a modulban, úgy az a többi modulban is elérhető lesz. Ehhez a feladat-útmutatóhoz **a** Kinnlevőségek között minden fizetési feltétel be van állítva.
2. Kattintson az **Új** elemre. Hozzon létre fizetési napot, amennyiben a fizetési feltételei a hét (hétfő, kedd stb.) vagy a hónap egy adott napját (5-e, 10-e stb.) írják elő. 
3. A **Fizetési nap** mezőbe írjon egy azonosítót.
4. Adja meg a fizetési nap leírását a **Leírás** mezőben.
5. A **hét/hónap** mezőben válassza a „Hét” vagy a „Hónap” lehetőséget. Válassza ki a Hét lehetőséget, ha a hét egy adott napját szeretné megadni, például a hétfőt. Válassza ki a Hónap lehetőséget, ha a hónap egy adott napját szeretné megadni, például a 10-ét. Ehhez a példához válassza a Hónap lehetőséget. 
6. Adjon meg egy dátumot **A hónap napja** mezőben. A dátumot szám formájában kell megadni, azaz például „10” és nem „10.” 
7. Kattintson a **Mentés** gombra.
8. Zárja be a lapot.
9. Válassza a **Navigációs ablaktábla >Modulok > Kinnlévőségek > Kifizetések beállítása > Fizetési feltételek** elemet.
10. Kattintson az **Új** elemre. **A fizetési feltételek** a határidők kiszámításának módját határozzák meg. A készpénzfizetési engedmény dátuma egy külön lapon kerül beállításra. 
11. A **Fizetési feltételek mezőbe** írjon egy azonosítót.
12. Adjon meg egy leírást a **Leírás** mezőben.
13. Válasszon egy **fizetési módot, például** **utánékot**, nettót **·**, **aktuális hónapot** stb. A **fizetési mód** határozza meg, hogy mikortól számítsa ki a program az esedékes összeget. Például a nettó érték akkor **használatos,** ha a határidő mindig a számla dátuma utáni hónapok vagy napok beállított száma. **Az** utánékot arra az időpontra lehet használni, amikor a számlán fizetés szükséges, így a határidő nem számítható ki. Válassza ki **az aktuális hónapot** ehhez a feladat-útmutatóhoz.  
14. Válasszon egy **Fizetési napot**, ha a számításban szerepel a hét egy adott napja vagy egy adott dátum. Az Ön fizetési feltételei függvényében adja meg a kívánt Hónapok vagy Napok számát. Másik lehetőségként a Fizetési **ütemezés** **vagy** a Fizetési nap segítségével "hozzáadhatja" a **fizetési mód végét.** Amennyiben az esedékességi dátum minden esetben a következő hónap 10-e, úgy válassza ki a 10-ét, mint **Fizetési napot**. Ha fizetési naptárat használ, megadhatja, hogyan határozza meg a **rendszer** az esedékesség dátumát, amikor a számított dátum leszáll egy nem munkanapra. A kezdeti határidő számítása a naptári napok alapján történik. Ha a számított dátum nem munkanapra tér vissza, a kiszámított határidő a következő munkanapra vagy korábbi munkanapra módosítható.
15. Kattintson a **Mentés** gombra.
16. Zárja be a lapot.
17. Ugorjon a **Kinnlevőségek > Kifizetés beállítása > Készpénzfizetési engedmények** pontra.
18. Kattintson az **Új** elemre. Ez az oldal a készpénzfizetési engedmény dátumának kiszámítására használható. 
19. A **Készpénzfizetési engedmény** mezőbe írjon egy azonosítót.
20. Adjon meg egy leírást a **Leírás** mezőben.
21. Többszintű készpénzfizetési engedmény esetén válassza ki az új készpénzfizetési engedmény után releváns **Következő engedmény kódját**.
22. A **Napok** mezőben adja meg a készpénzfizetési engedmény dátumához használandó napok számát. Ha a **Nettó** irányelv lehetőséget választotta, a napok száma hozzáadódik a számla dátumához, és így kerül kiszámításra a készpénzfizetési engedmény dátuma.  
23. Az **Engedmény** mezőben adja meg a készpénzfizetési engedmény százalékát.
24. A **Vevői engedmények fő számláján** adja meg azt a fő számlát, amelyet a készpénzfizetési engedmény felad a vevői számlákhoz.
25. Válasszon egy lehetőséget a **Kedvezmény ellenszámlák** mezőben. Ha a „Számlák a számlasorokban” beállítást választja, úgy a készpénzfizetési engedmény a szállítói számlasorok ugyanazon eszköz/költség főszámlájára kerül feladásra. Ha a Fő **számla használata** szállítói számlákhoz lehetőséget választja, **a készpénzfizetési engedmény a szállítói számlák fő számláján kiválasztott fő számlára adja fel a készpénzfizetési engedményt**. Ebben a példában válassza a Fő **számla használata szállítói számlákhoz lehetőséget**. 
26. A **Beszállítói engedmények fő számláján** adja meg azt a fő számlát, amelyet a készpénzfizetési engedmény felad a beszállítói számlákhoz.
27. Kattintson a **Mentés** gombra.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
