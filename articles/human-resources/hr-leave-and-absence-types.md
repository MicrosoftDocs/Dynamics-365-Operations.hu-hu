---
title: Szabadság- és távolléttípusok konfigurálása
description: Beállíthatja, hogy az alkalmazottak milyen típusú szabadságot vehetnek igénybe a Dynamics 365 Human Resources alkalmazásban.
author: twheeloc
ms.date: 11/21/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: e35c5fed886ebf9a453c22b3e04ca9ffe50b6d70
ms.sourcegitcommit: e88ecaccd82afa3a915e41df1d4287d99da6a48a
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/29/2022
ms.locfileid: "9805204"
---
# <a name="configure-leave-and-absence-types"></a>Szabadság- és távolléttípusok konfigurálása

[!include [preview banner](../includes/preview-banner.md)]

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

1. A Szabadság **és távollét munkaterületen** válassza a Hivatkozások **lapot**.
2. A **Beállítás** területen válassza a **Szabadság- és távolléttípusok** lehetőséget.
3. Válassza az **Új** lehetőséget.
4. Adja meg a szabadságtípus **nevét a Típus** területen, adjon meg egy leírást a **Leírás** területen, és válasszon egy munkafolyamatot a Munkafolyamat-azonosító **mezőben** . A szabadság típusa alapján válasszon ki egy kérelemtípust a Kérelemtípus **mezőben** . Választhatja például a Szabadság **vagy**  **a Szabadság lehetőséget**.
5. Az **Általános** lapon válassza ki a **Nincs**, az **Ütemezett** vagy a **Nem ütemezett** elemet a **Kategória** legördülő listáról.
6. Válasszon bevételkódot a **Bevételkód** legördülő listáról.
7. A **kötelező okkód mezőben** adja meg, hogy szeretne-e okkódot megadni. Ha okkódokat szeretne megkövetelni, lehet, hogy hozzá kell adnia őket. Az **Okkódok** területen válassza a **Hozzáadás** elemet, válasszon egy okkódot, és jelölje be a mellette található **Engedélyezve** jelölőnégyzetet.
8. Ha a kérelem típusa Távollét **, a** következő lépéseket kell követni:

      1. A **Nyitott vége csoportban** adja meg, hogy a felhasználóknak létre kell-e hozni nyílt végű leveleket.
      2. Ha **a "Nyitott munka** vége" beállítás engedélyezve van, megadhatja, hogy a dolgozóknak be kell-e nyújtaniuk a munkahelyre való visszatérésről szóló értesítést, amikor visszatérnek a szabadságról.
      3. Ha a dolgozóknak munkára való visszaküldésről szóló értesítést kell benyújtaniuk, **engedélyezheti a munka-visszaküldési értesítés engedélyezését**. Ha **engedélyezve van a munkára való** visszatérés engedélyezése, **a melléklet** kötelező automatikusan engedélyezve van, és nem tiltható le.

9. Ha a felhasználóknak szabadságkérések létrehozása vagy frissítése során dokumentumokat kell feltölteniük, engedélyezheti a szükséges **mellékleteket**.
10. Válassza **ki, hogy korlátozni szeretné-e** a hozzáférést a kijelölt szerepkörökhöz. Ezután a szabadságtípus **Biztonsági szerepkörei** területén válassza ki a biztonsági szerepköröket. A biztonsági szerepkörök definiálása abban a munkafolyamatban történik, amely a munkafolyamat-azonosítónál **korábban** van kiválasztva ebben az eljárásban.
11. A Naptár **színcsoportban** válassza ki az adott távolléttípus távolléti és távolléti naptárainál látni kívánt színt.
11. A Felfüggesztés **kapcsolatok alatt** adja meg, hogy ez a szabadságtípus fel legyen-e függesztve egy másik szabadságtípussal vagy fel legyen függesztve egy másik szabadságtípussal. Ha egy szabadságkérelem kerül elküldésre a felfüggesztő szabadságtípusra, akkor egy szabadságfelfüggesztés automatikusan létrehozásra kerül a felfüggesztett szabadságléttípusra.
12. Válassza a **Mentés** lehetőséget.

## <a name="configure-leave-type-rules"></a>A szabadságtípus-szabályok konfigurálása

1. Az Szabadság és távollét típus kerekítési **beállításainak** megadása. Választási lehetőségek: **Nincs**, **Fel**, **Le** és **Legközelebbi**. A szabadságtípus kerekítési pontosságát is megadhatja.
2. Adja meg a szabadságtípus **Munkaszünet-korrekció** beállítását. Ha bejelöli ezt a lehetőséget, akkor a munkanapra eső napok száma alapján lesz meghatározva, hogyan kell elszámolni a szabadságtípus távolléti idejét. Ha például karácsony napja hétfőre esik, akkor a Human Resources szolgáltatás levon egy napot a szabadságtípusból a könyvelés feldolgozásakor.

   A szabadnapokat a munkaidőnaptárban állíthatja be. További információ: [Munkaidőnaptár létrehozása](hr-leave-and-absence-working-time-calendar.md).
   
 3. Állítsa be a szabadság típusaként az **Átvihető szabadságtípust**. Ha ezt a lehetőséget választja, akkor az átvitt egyenlegek átkerülnek a megadott szabadságtípusba. Az átvitt szabadságtípust is figyelembe kell venni a szabadság- és a távolléti tervben. 
 
4. Adja meg a szabadságtípus **Lejárati szabályait**. Ha beállítja ezt a lehetőséget, akkor a napok vagy hónapok egységét is megadhatja, és megadhatja a lejárat időtartamát. A lejárati szabály hatálybalépésének dátumát arra használjuk, hogy meghatározzuk, mikor kell elindítani a szabadság lejáratát feldolgozó kötegelt feladatot, vagy amikor a szabály hatályba lép. Maga a lejárat mindig az elhatárolás kezdetének napján következik be. Ha például a könyvelési időszak kezdő dátuma 2021. augusztus 3., és a lejárati szabály 6 hónapra van beállítva, akkor a rendszer a könyvelési időszak kezdő dátumához megadott lejárati ellenszámla alapján fogja feldolgozni, tehát 2022. február 3-án lesz végrehajtva. A lejárati időpontokban meglévő szabadságegyenlegeket a szabadság típusából kivonja a program, és ez a szabadságegyenlegében tükröződik.
 
## <a name="configure-the-required-attachment-per-leave-type"></a>Szükséges melléklet konfigurálása szabadságtípusonként

> [!NOTE]
> A **Melléklet kötelező** mező használatához be kell kapcsolnia a Funkciókezelés funkcióban az **Szabadságkérések kötelező mellékletének konfigurálása** elemet. A funkciók bekapcsolásával kapcsolatos további információt lásd a [Szolgáltatások kezelése](hr-admin-manage-features.md) című témakörben.

1. A **Szabadság és távollét** lapon a **Hivatkozások** lapon a **Beállítások** alatt válassza a **Szabadság- és távolléttípusok** lehetőséget.

2. A listában válassza **ki a** szabadság és a távollét típusát. Az Általános **szakaszban** a Melléklet szükséges mezőben adhatja meg, **hogy** feltölthető-e a melléklet, amikor egy alkalmazott új távolléti kérelmet küld a kiválasztott távolléttípusra vonatkozóan. 

Az alkalmazottaknak akkor kell feltölteniük a mellékletet, amikor olyan új szabadságkérést küldnek be, amelyben engedélyezve van a **Melléklet szükséges** mező. Szabadságigénylés részeként feltöltött melléklet megtekintéséhez a szabadságkérelem jóváhagyói használhatják a hozzájuk rendelt munkaelemekhez a **Mellékletek** lehetőséget. Ha egy szabadságkéréshez a Human Resources alkalmazás segítségével férnek hozzá a Microsoft Teams alkalmazásban, akkor a szabadságkérelem **Részletek megtekintése** lehetősége használható a részletei és mellékletei megtekintéséhez.

## <a name="configure-leave-units-hoursdays-per-leave-type"></a>Szabadság-mértékegységek (óra/nap) konfigurálása szabadságtípusonként

> [!NOTE]
> Az egységek szabadságtípusonként funkció használatához először be kell kapcsolni az **Szabadság-mértékegységek konfigurálása szabadságtípusonként** funkciót a Funkciókezelésben. A funkciók bekapcsolásával kapcsolatos további információt lásd a [Szolgáltatások kezelése](hr-admin-manage-features.md) című témakörben.

> [!IMPORTANT]
> A jogi személynél a szabadságtípusok alapértelmezés szerint a szabadságparaméterek konfigurációjában megadott szabadságegységeket használják a jogi személy szintjén.
> 
> A szabadság és a távollét típus szabadságegysége csak akkor módosítható, ha az adott távolléttípushoz nincsenek szabadságtranzakciók.
> 
> A funkciót a bekapcsolása után nem lehet kikapcsolni.

1. A **Szabadság és távollét** lapon a **Hivatkozások** lapon a **Beállítások** alatt válassza a **Szabadság- és távolléttípusok** lehetőséget.

2. Válassza ki a szabadság- és távollét típust a listában. Ezután az **Általános** szakaszban, az **Egység** mezőben válassza ki a szabadság egységét. Az **Óra** és a **Nap** beállítás közül választhat.

3. Nem kötelező: Ha az **Egység** mezőben az **Óra** lehetőséget választotta, akkor a **Félnapos meghatározás engedélyezése** mezőben adhatja meg, hogy az alkalmazottak kiválaszthatják-e a nap első felét vagy a nap második felét, amikor fél napos szabadságot kérnek.

Azok az alkalmazottak, akik új szabadságkérelmet nyújtanak be különböző szabadságtípusokat választanak ki a szabadságkérelem létrehozásához. Az egy szabadságkérés részeként kiválasztott összes szabadságtípushoz azonban ugyanazt a szabadságegységet kell választani. Az alkalmazottak megtekinthetik a szabadságegységet az egyes szabadságtípusokhoz a **Távollét kérelmezése** űrlapon.

## <a name="see-also"></a>Lásd még

- [Szabadság és távollét áttekintése](hr-leave-and-absence-overview.md)
- [Szabadság- és távolléti terv létrehozása](hr-leave-and-absence-plans.md)
- [Munkaidőnaptár létrehozása](hr-leave-and-absence-working-time-calendar.md)
- [Szabadság felfüggesztése](hr-leave-and-absence-suspend-leave.md)
- [Szabadság vásárlására és eladására irányuló kérelem munkafolyamatának létrehozása](hr-leave-and-absence-buy-sell-workflow.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
