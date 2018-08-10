--- 
title: "Adja meg és hasonlítsa össze az Ajánlatkérés ajánlatait, és rendeljen hozzá szerződéseket"
description: "Ez az eljárás bemutatja az Ajánlatkérésre történő válaszadás, az ajánlatok pontozásának és összehasonlításának módját, és ezt követően bemutatja azt is, hogy hogyan rendelheti az ajánlatot egy szállítóhoz."
author: mkirknel
manager: AnnBe
ms.date: 06/07/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 5dea9d7bfb1bf7b11f6c49cccaab1b73d4e58d16
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="enter-and-compare-rfq-bids-and-award-contracts"></a>Adja meg és hasonlítsa össze az Ajánlatkérés ajánlatait, és rendeljen hozzá szerződéseket

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ez az eljárás bemutatja az Ajánlatkérésre történő válaszadás, az ajánlatok pontozásának és összehasonlításának módját, és ezt követően bemutatja azt is, hogy hogyan rendelheti az ajánlatot egy szállítóhoz. Az USMF bemutatócég adataiban használhatja ezt az eljárást. Mielőtt elkezdené, egy legalább két szállítónak elküldött sorral rendelkező Ajánlatkéréssel kell rendelkeznie. Előfeltételként az "Ajánlatkérés létrehozása" eljárást futtathatja ezen elem létrehozásához. Mielőtt lehetővé válik ezen eljárás futtatása létre kell hozni a pontozási feltételeket.


## <a name="enter-a-reply-from-a-vendor"></a>Adjon meg egy választ a szállítótól
1. Ugorjon a Beszerzés és forrás > Ajánlatkérések > Összes ajánlatkérés pontra.
2. Válasszon ki egy elküldött állapotú Ajánlatkérést, és kattintson a hivatkozásban szereplő ajánlatkérési eset számára.
    * Az Ajánlatkérést legalább két szállítónak kellett elküldeni.  
3. Kattintson a Fejlécre a szállítók listájára történő ugráshoz.
4. Válassza ki azt a szállítót, akire vonatkozóan meg szeretne adni választ az ajánlatkérésben.
5. Kattintson a Válasz beírása gombra.
6. A Művelet panelen kattintson a Válasz elemre.
7. Kattintson az Adatok másolása a válaszba elemre.
    * Ez a művelet másolja a kijelölt adatokat, például az Ajánlatkérési esetből származó mennyiséget az Ajánlatkérés-válaszához. Másik lehetőségként hagyja ki ezt a műveletet, és töltse ki manuálisan az összes válaszmezőt a válasz szerkesztésekor.  
8. Kattintson a Szerkesztés lehetőségre.
9. Adjon meg egy számot az Egységár mezőben.
10. Válasszon egy másik árajánlatsort.
11. Adjon meg egy számot az Egységár mezőben.

## <a name="score-the-bid"></a>Ajánlat pontozása
1. Kattintson a Fejlécre az ajánlat pontozására történő ugráshoz.
2. Bontsa ki az ajánlat pontozási szakaszát.
3. A pontszám mezőben adja meg a pontozási feltételek egyikét.
    * Ha a mutatót valamelyik pontozási feltétel fölé viszi, akkor az elemleírás megjeleníti azt a tartományt, amelyen belül el kell végeznie a pontozást. Ebben a bemutatóban hozzáadhat egy 1 és 5 közötti számot a feltételek bármelyikéhez.  
4. Válasszon ki egy másik pontozási feltételt.
5. A pontszám mezőben adjon meg egy számot.
6. Bontsa ki a Kérdőívek szakaszt.
    * Ha az ajánlatkérés egy olyan kérdőívet tartalmaz, amelyet már elküldtek a szállítóknak, akkor megadhatja a válaszaikat a Kérdőív szakaszban.  
7. Zárja be a lapot.

## <a name="enter-a-reply-for-another-vendor"></a>Adjon meg egy másik szállítóra vonatkozó választ
1. Válassza ki a következő szállítót, azon szállító törlésével, akire vonatkozóan megadta a választ és ezt követően a következő szállító sorának kiválasztásával.
2. Keresse meg és jelölje ki a kívánt rekordot a listán.
3. Kattintson a Válasz beírása gombra.
4. Kattintson az Adatok másolása a válaszba elemre.
5. Kattintson a Szerkesztés lehetőségre.
6. Adjon meg egy számot az Egységár mezőben.
7. Válasszon egy másik árajánlatsort.
8. Adjon meg egy számot az Egységár mezőben.

## <a name="score-the-second-bid"></a>Második ajánlat pontozása
1. Kattintson a Fejlécre az ajánlat pontozására történő ugráshoz.
2. A pontszám mezőben adjon meg egy számot.
3. Keresse meg és jelölje ki a kívánt rekordot a listán.
4. A pontszám mezőben adjon meg egy számot.

## <a name="compare-the-replies"></a>Válaszok összehasonlítása
1. A Művelet panelen kattintson az Általános elemre.
2. Kattintson a Válaszok összehasonlítása elemre.
3. Adjon meg egy számot a helyezés mezőben.
    * Ez a lap megjeleníti a fejléccel és sorokkal ellátott ajánlatokat, és a fejléc szintjén szereplő összpontszámot. Összehasonlíthatja a sorokat a rácsba történő rendezéssel, ami által az összehasonlítható sorok egymás mellé kerülnek. Az információ szintén tartalmazza: Mennyiség: A szállító által ajánlott mennyiség. Ez a mennyiség eltérhet az ajánlatkérésben szereplő mennyiségtől.   Nettó összeg: A szállító által ajánlott összeg, a sor cikkeire vonatkozó bármely engedmény levonása után.   Eltérés: Az ajánlat fejlécében vagy sorában megadott szállítási dátum ennyi nappal tér el az ajánlatkérés fejlécében vagy az ajánlatkérés sorában kért szállítási dátumtól.   Minden egyes ajánlat rangsorban elfoglalt helyét megadhatja.  
4. Válassza ki az azokra az ajánlatokra vonatkozó fejlécet, amelyeket rangsorolni kíván.
5. Adjon meg egy számot a helyezés mezőben.
6. Kattintson a Mentés gombra.

## <a name="reject-a-bid"></a>Ajánlat elutasítása
1. Válassza ki az azokra az ajánlatokra vonatkozó fejlécet, amelyeket el akar utasítani.
    * Egyszerre csak egy ajánlatot vagy az ajánlaton belül szereplő sorokat fogadhatja el, utasíthatja el, vagy küldheti vissza.  
2. Jelölje be a Megjelölve jelölőnégyzetet.
    * Ha az ajánlat fejlécének jelölőnégyzetét bejelöli, akkor az összes sor meg lesz jelölve. Kijelölheti az ajánlaton belül szereplő sorok egy részét azok elutasításához vagy elfogadásához. Arra is lehetőség van, hogy egy ajánlatkérés néhány sorára vonatkozó szállító ajánlatát elfogadja, és ezt követően a többi ajánlatkérés sorát a különböző szállítókhoz rendelje. Azonban két lépésben tudja ezt csak megtenni és egyszerre csak egy ajánlatot tud elvégezni. Ha az alternatívasorok elérhetőek, akkor vagy csak az eredeti ajánlat sorát vagy csak annak alternatíváját fogadhatja el, de mindkettőt egyszerre nem.  
3. Kattintson az elutasítás elemre.
4. A „Paraméter” gombra kattintva nyissa meg a legördülő párbeszédpanelt.
5. A Ok elutasítás mezőben adjon meg vagy válasszon ki egy értéket.
    * Az elutasítás okát a rendszer a válaszban tárolja.  
6. Kattintson az OK gombra.
7. Kattintson az OK gombra.
8. Zárja be a lapot.
9. Zárja be a lapot.
10. Frissítse a lapot..

## <a name="accept-a-bid"></a>Válasz elfogadása
1. Válassza ki azt az ajánlatot, amelyet el akar fogadni majd kattintson az Ajánlatkérés mezőjében szereplő hivatkozásra.
2. A Művelet panelen kattintson a Válasz elemre.
3. Kattintson az Elfogadás lehetőségre.
    * Ha megjelölt bizonyos sorokat, akkor nem más, mint az elfogadás művelet tartalmazni fogja a megjelölt sorokat. Ha elfogadja az ajánlat összes sorát, akkor nem kell bejelölni a sorokat.  
4. A „Paraméter” gombra kattintva nyissa meg a legördülő párbeszédpanelt.
    * Ez lehetővé teszi az ajánlat elfogadására vonatkozó ok rögzítését. Az okot a rendszer az ajánlatban tárolja.  
5. A Ok elfogadása mezőben adjon meg vagy válasszon ki egy értéket.
6. Kattintson az OK gombra.
7. Kattintson az OK gombra.
    * Amikor az Ok gombra kattint, a rendszer az Ajánlatkérés elfogadás sorain alapuló beszerzési rendelést hoz létre. Más ajánlatok esetén, amelyek még nincsenek feldolgozva (elfogadva, elutasítva vagy visszaadva) esetén a rendszer figyelmezteti Önt a fennmaradó ajánlatok elutasítására.  

## <a name="view-the-purchase-order-thats-been-generated"></a>A létrejött beszerzési rendelés megtekintése
1. A Művelet panelen kattintson az Általános elemre.
2. Kattintson a Beszerzési rendelés lehetőségre.
    * Itt látható az ajánlat elfogadásakor létrehozott beszerzési rendelés.  
3. Zárja be a lapot.
4. Zárja be a lapot.
5. Zárja be a lapot.
6. Zárja be a lapot.


