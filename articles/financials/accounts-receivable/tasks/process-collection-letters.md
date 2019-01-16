--- 
title: "Fizetési felszólítások feldolgozása"
description: "Ez az eljárás a fizetési felszólítások létrehozását, nyomtatását és feladását mutatja be."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 12/04/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustPosting, CustCollectionLetterNote
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2018-12-01
ms.dyn365.ops.version: 8.1.3
ms.translationtype: HT
ms.sourcegitcommit: 075d0f5dc0c9dc4e46dc92a2da75da9f7a207472
ms.openlocfilehash: 33d9fd62a780ab109474eefa9e322a9c529f9e72
ms.contentlocale: hu-hu
ms.lasthandoff: 12/06/2018

---
# <a name="process-collection-letters"></a>Fizetési felszólítások feldolgozása

[!include [banner](../../includes/banner.md)]
[!include [preview banner](../../includes/preview-banner.md)]

Ez az eljárás a fizetési felszólítások létrehozását, nyomtatását és feladását mutatja be. Ez a feladat az USMF bemutatócéget használja.

## <a name="set-up-a-collection-letter-sequence-on-the-posting-profile"></a>Állítson be egy fizetésifelszólítás-sorozatot a feladási profilon.
1. Ugorjon a **Követelések és beszedések > Beállítás > Vevői feladási profilok pontra**.
2. Kattintson a **Szerkesztés** lehetőségre.
3. Válasszon egy fizetésifelszólítás-sorozatot a legördülő listából. Ha nem szeretne fizetési felszólításokat létrehozni a tranzakciókhoz ezzel a feladói profillal, hagyja a mezőt üresen.  
4. A Tábla korlátozási lapjának kinyitásával módosíthatja a fizetési felszólítások feldolgozásának módját. Ha ez a mező **Igen** értékre van állítva, fizetési felszólítások kerülnek létrehozásra a feladási profilhoz.  

## <a name="create-collection-letters"></a>Fizetési felszólítások létrehozása
1. Ugorjon a **Követelések és beszedések > Fizetési felszólítás > Fizetési felszólítások létrehozása** pontra.
2. Válassza ki azokat a tranzakciótípusokat, amelyekre fizetési felszólítást szeretne létrehozni. Ez ilyen típusokhoz tartozó nyitott tranzakciók szerepelni fognak a számításban.  
2. A **Fizetési felszólítás** mezőben válassza ki a kívánt beállítást.
3. Adja meg a fizetési felszólítás dátumát.
4. Válasszon ki egy feladási profilt, ha módosította a **Feladási profil használata képernyő** lehetőséget **Kiválasztott** lehetőségre. Kétféle feladási profil létezik:   
   - **Számla** – az egyes kamatlevelek vevőkódjához rendelt feladási profil használata.   
   - **Kiválasztott** – a Feladási mezőben megadott **Feladási profil** használata.  
5. Bontsa ki a **Szerepeltetni kívánt rekordok** szakaszt.
6. Kattintson a **Szűrő** parancsra.
7. A **Feltétel** mezőben adjon meg Vevőazonosítót. Adja meg például az „US-001”értéket.
8. Kattintson az **OK** gombra.
9. Kattintson az **OK** gombra.

## <a name="print-collection-letters"></a>Fizetési felszólítások nyomtatása
1. Ugorjon a **Követelések és beszedések > Fizetési felszólítás > Fizetési felszólítások áttekintése és feldolgozása** pontra.
2. Az **Állapot** mezőben válassza ki a **Létrehozva** értéket.
3. A **Nyomtatott** mezőben válassza a **Nem nyomtatva** lehetőséget.
4. Kattintson a **Nyomtatás** parancsra.
5. Kattintson a **Fizetésre felszólítás** gombra.
6. Bontsa ki a **Szerepeltetni kívánt rekordok** szakaszt.
7. Adja meg a feladások fordulónapjának dátumát.
8. Kattintson az **OK** gombra a fizetési felszólítás nyomtatásához.
9. Adja fel a fizetési felszólítást.
   1. Kattintson a **Bejegyzés** lehetőségre.
   2. Adja meg a fizetési felszólítás feladási dátumát.
   3. Bontsa ki a **Szerepeltetni kívánt rekordok** szakaszt.
   4. Kattintson az **OK** gombra.
   5. Az **Állapot** mezőben válassza ki a **Feladott** értéket.
   6. Válasszon ki egy lehetőséget a **Nyomtatott** mezőben.

## <a name="control-collection-letters-at-the-customer-level"></a>A fizetési felszólítások ellenőrzése a vevő szintjén
Fizetési felszólításokat a vevők szintjén is beállíthatja, hogy a fizetésifelszólítás-kód az egyes tranzakciókhoz nyomon legyen követve de a fizetési felszólítás feldolgozása a vevőhöz tárolt egyetlen fizetésifelszólítás-szinten alapuljon. Az egyetlen fizetési felszólítás aí vevőhöz tartozó összes lejárt tranzakció fogja tartalmazni. Mivel a türelmi napok mostantól nyomon követhetők a vevői szinten, a következő fizetési felszólítás nem lesz elküldve mindaddig, amíg a sorozatban következő fizetési felszólításhoz kapcsolódó türelmi időszak le nem jár, annak ellenére, a tranzakciók késedelmessé váltak az utolsó fizetési felszólítás elküldése után. Ez a lehetőség csökkenti a vevőnként elküldött a fizetési felszólítások számát. 

### <a name="set-up-the-customer-to-control-collection-letters-at-the-customer-level"></a>A fizetési felszólítások ellenőrzésének beállítása a vevő szintjén
1.  Ugorjon a **Követelések és beszedések > Beállítás > Kinnlevőségek paraméterei**, és kattintson a **Beszedések** lapra. 
2.  A **Fizetési felszólítás létrehozása a következő szerint:** értékét módosítsa **Vevő** értékre. 
3.  Ugorjon a **Követelések és beszedések > Fizetési felszólítás > Fizetési felszólítások áttekintése és feldolgozása** pontra. Csak egy fizetési felszólítás jön létre a vevőhöz az összes lejárt tranzakció tekintetében.

## <a name="ignore-payments-and-credit-memos-when-calculating-the-collection-letter-code"></a>Fizetések és jóváírások figyelmen kívül hagyása a fizetési felszólítás kódjának kiszámítása során
Ha kifizetéseket és jóváírásokat is szerepeltetni kíván a tranzakciókban, amelyek szerepelni fognak a fizetési felszólításokban, előfordulhat, hogy vannak olyan kifizetések vagy jóváírások, amely elindítják a fizetési felszólítást. Megadhatja, hogy kifizetések és jóváírások, hogyan vezéreljék a fizetésifelszólítás-kódokat a **Fizetések és jóváírások figyelmen kívül hagyása a fizetési felszólítás kódjának kiszámítása során** paraméter értékének módosításával. 

Fizetések és jóváírások figyelmen kívül hagyásához a fizetési felszólítás kódjának kiszámítása során tegye a következőket.
1. Ugorjon a **Követelések és beszedések > Beállítás > Kinnlevőségek paraméterei**, és kattintson a **Beszedések** lapra. 
2. A **Fizetések és jóváírások figyelmen kívül hagyása a fizetési felszólítás kódjának kiszámítása során** paramétert állítsa **Igen** értékre.

