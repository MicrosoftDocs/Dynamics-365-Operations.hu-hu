---
title: Szabadság- és távolléttípusok konfigurálása
description: Beállíthatja, hogy az alkalmazottak milyen típusú szabadságot vehetnek igénybe a Dynamics 365 Human Resources alkalmazásban.
author: andreabichsel
manager: tfehr
ms.date: 06/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: f1c3ced43b1f5693c5d5466fd97a20beb358fa20
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/17/2021
ms.locfileid: "5463334"
---
# <a name="configure-leave-and-absence-types"></a>Szabadság- és távolléttípusok konfigurálása

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

A Dynamics 365 Human Resources szabadságtípusai határozzák meg az alkalmazottak számára elérhető különböző típusú távolléteket. A szabadságtípusokat a szervezet igényeihez igazíthatja. Példák a szabadságtípusokra:

- Fizetett szabadság (PTO)
- Fizetés nélküli szabadság
- Fizetett szabadság
- Betegszabadság
- Betegszabadság
- Családi okokból történő
- Rövid távú fogyatékosság
- Haláleset miatti szabadság

## <a name="add-a-leave-type"></a>Szabadságtípus hozzáadása

1. A **Szabadság és távollét** oldalon válassza a **Hivatkozások** lapot.

2. A **Beállítás** területen válassza a **Szabadság- és távolléttípusok** lehetőséget.

3. Válassza az **Új** lehetőséget.

4. Írjon be a szabadságtípus nevét a **Típus** mezőbe, válasszon egy munkafolyamatot a **Munkafolyamat-azonosító** listáról, és adja meg a leírást a **Leírás** mezőben.

5. Az **Általános** lapon válassza ki a **Nincs**, az **Ütemezett** vagy a **Nem ütemezett** elemet a **Kategória** legördülő listáról.

6. Válasszon bevételkódot a **Bevételkód** legördülő listáról.

7. **Az okkódot meg kell adni** beállításnál válassza ki, hogy szeretné-e előírni az okkód megadását. Ha elő szeretné írni az okkódok használatát, akkor fel kell vennie ilyen kódokat. Az **Okkódok** területen válassza a **Hozzáadás** elemet, válasszon egy okkódot, és jelölje be a mellette található **Engedélyezve** jelölőnégyzetet.

8. A **Hozzáférés korlátozása a kijelölt szerepkörökre** beállításnál válassza ki, hogy szeretné-e korlátozni a hozzáférést. Ezután a **Szabadságtípus biztonsági szerepkörei** beállításnál válassza ki a biztonsági szerepköröket. A biztonsági szerepkörök a jelen eljárás korábbi pontján, a **Munkafolyamat-azonosító** beállításnál kiválasztott munkafolyamatban határozhatók meg.

9. A **Naptár színe** elemben válassza ki, hogy milyen színnel szeretné megjeleníteni ezeket a szabadságtípusokat a szabadság- és a távolléti naptárakban. 

10. A **Felfüggesztési kapcsolatok** alatt válassza ki, hogy szeretné, hogy ez a szabadságtípus felfüggesztene egy másik szabadságtípust, vagy ezt a szabadságtípust függesztené fel egy másik. Ha egy szabadságkérelem kerül elküldésre a felfüggesztő szabadságtípusra, akkor egy szabadságfelfüggesztés automatikusan létrehozásra kerül a felfüggesztett szabadságléttípusra. 

10. Válassza a **Mentés** lehetőséget.

## <a name="configure-leave-type-rules"></a>A szabadságtípus-szabályok konfigurálása

1. Adja meg a szabadságtípus kerekítési beállításait. Választási lehetőségek: **Nincs**, **Fel**, **Le** és **Legközelebbi**. A szabadságtípus kerekítési pontosságát is megadhatja.

2. Adja meg a szabadságtípus **Munkaszünet-korrekció** beállítását. Ha bejelöli ezt a lehetőséget, akkor a Human Resources szolgáltatás a munkanapra eső napok száma alapján határozza meg, hogyan kell elszámolni a szabadságtípus távolléti idejét. Ha például karácsony napja hétfőre esik, akkor a Human Resources szolgáltatás levon egy napot a szabadságtípusból a könyvelés feldolgozásakor.

   A szabadnapokat a munkaidőnaptárban állíthatja be. További információ: [Munkaidőnaptár létrehozása](hr-leave-and-absence-working-time-calendar.md)
   
 3. Állítsa be a szabadság típusaként az **Átvihető szabadságtípust**. Ha ezt a lehetőséget választja, akkor az átvitt egyenlegek átkerülnek a megadott szabadságtípusba. Az átvitt szabadságtípust is figyelembe kell venni a szabadság- és a távolléti tervben. 
 
 4. Adja meg a szabadságtípus **Lejárati szabályait**. Ha beállítja ezt a lehetőséget, akkor a napok vagy hónapok egységét is megadhatja, és megadhatja a lejárat időtartamát. Beállíthatja a lejárat szabályának érvényességi dátumát is. Az érvényességi dátum annak meghatározására használható, hogy mikor kell elkezdeni a szabadság lejáratát feldolgozó kötegelt feladat futtatását, vagy azt a dátumot, amikor a szabály hatályba lép. A lejárat maga mindig meg fog történni a szabadságterv kezdő dátumán, ha a kötegelt feladat feldolgozásra van beállítva. Például előfordulhat, hogy a terv kezdő dátuma 2020. 01. 01., de a szabályt csak 2020. 01. 06-án hozták létre. Ha a hatályba lépés dátumát 2020. 01. 06-ra állítják, a szabályt a következő év határán lesz feldolgozva, így 2021. 01. 01-jén. A lejárati időpontokban meglévő szabadságegyenlegeket a szabadság típusából kivonja a program, és ez a szabadságegyenlegében tükröződik. 
 
## <a name="see-also"></a>Lásd még

- [Szabadság és távollét áttekintése](hr-leave-and-absence-overview.md)
- [Szabadság- és távolléti terv létrehozása](hr-leave-and-absence-plans.md)
- [Munkaidőnaptár létrehozása](hr-leave-and-absence-working-time-calendar.md)
- [Szabadság felfüggesztése](hr-leave-and-absence-suspend-leave.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
