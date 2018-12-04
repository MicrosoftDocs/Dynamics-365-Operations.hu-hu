---
title: "Fizetési módok hívásközpontoknál"
description: "Ez a témakör bemutatja a Microsoft Dynamics 365 for Retail rendszer hívásközpontjaiban használható különböző fizetési módokat."
author: josaw1
manager: AnnBe
ms.date: 03/28/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: MCRSalesTableOrderHistory, MCRCCAuthManagement
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 92163
ms.assetid: 8e738907-870b-466c-ab0c-07f4a4aa47f3
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 5098fb3339403b6f2779dfe3bb7ef5c4ca78051f
ms.openlocfilehash: 0b86388efab113af605d62c6ad76c8169d9c4643
ms.contentlocale: hu-hu
ms.lasthandoff: 08/09/2018

---

# <a name="payment-methods-in-call-centers"></a>Fizetési módok hívásközpontoknál

[!include [banner](includes/banner.md)]

A Microsoft Dynamics 365 for Retail alkalmazásban a hívásközponti csatornák konfigurációja tartalmazza a **Rendeléskiegészítés engedélyezése** nevű beállítást. A beállítás segítségével garantálható, hogy minden olyan rendelés, amelyet a csatorna felhasználói hoznak létre, csak akkor lesz kiadva rendelésfeldolgozásra, ha a jóváhagyott tűréshatáron belüli előre kifizetett vagy előzetesen jóváhagyott kifizetése van. Ha a **Rendeléskiegészítés engedélyezése** beállítás engedélyezve van, a hívásközpont felhasználói bevihetnek kifizetéseket a vevőkhöz tartozó értékesítési rendelések ellenében a hívásközpont fizetésfeldolgozási funkciói segítségével. Ha a beállítás ki van kapcsolva, hívásközpont felhasználói nem használhatják a hívásközpont fizetésfeldolgozási funkcióit, de továbbra is alkalmazhatnak előlegeket az értékesítési rendelésekre a szabványos Kinnlevőségek funkció segítségével.

A csatorna konfigurálásának részeként a vállalat határozhatja meg, mely fizetési módokat engedélyezi a hívásközponti csatornára. A hívásközponti csatorna a kiskereskedelmi üzlet csatornákra megadottakkal azonos fizetési módokat használ.

Adja meg a fizetési módokat a hívásközponti csatornára: kattintson a **Kiskereskedelem** \> **Csatornák** \> **Hívásközpontok** \> **Összes hívásközpont** elemre, majd a **Beállítás** menüben válassza a **Fizetési módok** lehetőséget.

Fizetési mód létrehozásakor öt fizetési mód funkciót rendelhet hozzá.

| Funkció            | Leírás |
|---------------------|-------------|
| Normál              | Használja a **Normál** funkciót a fizetési módon, amikor olyan kifizetési módokat ad meg, mint a készpénz vagy a bizonylatok. Amikor ezeket a kifizetési típusokat alkalmazzák a hívásközpontban az értékesítési rendelésekhez, az **Előre fizetés** megjelölés alapértelmezett beállítása az **Igen**.  Ilyenkor a rendszer azonnal felad egy előlegfizetési bizonylatot a vevő számlájára, amikor ezt a rendelést elküldik. Ha szükséges, a felhasználók módosíthatják az **Előre fizetés** megjelölést **Nemre**, hogy a kifizetési bizonylat ne jöjjön létre, amíg nem történik számlafeladás.  Az előlegbizonylat a vevői tranzakciók előzményeinél kerül feladásra, ahol rendszeresen elszámolják az értékesítési rendelés számlájával szemben. |
| Csekkes               | Használja a **Csekk** funkciót, ha a fizetés formájaként határozza meg a banki csekk eszközt. Ha ezt a kifizetési típust alkalmazzák egy értékesítési rendelésre, a felhasználónak az kifizetésalkalmazás feldolgozásának részeként meg kell adnia a vevő csekkszámát. A csekkes fizetések mindig előlegnek tekintendők, amikor alkalmazásra kerülnek, és a kifizetési bizonylatok a rendelés benyújtása után azonnal létrejönnek. Ezeket az előlegbizonylatokat rendszeresen elszámolják az értékesítési rendelés számlájával szemben a számla létrehozásakor. |
| Kártyák               | A kártyás fizetési típusok az olyan fizetési típusokat fedik le, amelynél be kell vinni egy kártyaszámot, amely a vevő fizetési kártyáján van meghatározva. Például ilyenak a hitelkártyák és az ajándékutalványok. Az ilyen típusú fizetések konfigurálásakor a **Kártyabeállítások** menüt kell használnia az ehhez a fizetési módhoz társított kártyaazonosítók megadásához. A rendelésbevitel során a felhasználók megadhatják, hogy a kártyás fizetés előre fizetett lesz-e, a fizetési tétel lapon megjelenő **Előre fizetett** beállítás segítségével. Azt az esetet kivéve, amikor a vállalat előlegfizetéseket igényel, az igaz hitelkártyás fizetés jellemző két lépésből álló folyamat, ahol az engedélyezés a rendelésbevitel során történik, és a kifizetés kiegyenlítése és az összeg kártyára terhelése a számlázás időpontjában történik. Ajándékutalványos fizetés esetén az előlegfizetés ajánlott, mert az ajándékutalvány egyenlegét azonnal csökkenteni kell, hogy a vevő máshol ne költhesse el ugyanezt az értéket. |
| Vevő            | A **Vevő** funkció a fizetési módoknál azt jelenti, hogy a kifizetés a vevő hitelkeretére lesz alkalmazva, vagyis „részszámlázás” történik. A Retail esetében a vevőhöz hozzárendelhető hitelkeretet, amelyet ellenőrizni lehet a rendelésbevitel során. A **Vevő** funkcióhoz kapcsolódó fizetési mód használatával tett kifizetések kötelezettséget hoznak létre a vevő számlájával szemben. Ezután, az értékesítési rendelés számlázása esetén, az esedékes egyenleg jelenik meg. Ebben az esetben a vevők jellemzően a számukra megadott feltételek szerint kifizetést indítanak. Másik megoldásként a vevői számlán korábban nyitott jóváírási bizonylat is alkalmazható az esedékes összeg kiegyenlítésére. Vegye figyelembe, hogy még ha ezt a fizetési módot határozza is meg, a fizetési mód nem jelenik meg a hívásközpont rendelésbevitel fizetési választási lehetőségei között, kivéve, ha a **Részszámlázás engedélyezése** jelző be van állítva a vevőrekordon annál a vevőnél, akivel dolgozik. Ez a jelző megtalálható a vevőrekord **Fizetés alapértelmezései** lapján. |
| Fizetőeszköz eltávolítása/váltópénz | A **Fizetőeszköz eltávolítása/váltópénz** funkciót nem használja a hívásközpont. Csak akkor alkalmazható, ha azokat a fizetési módokat határozza meg, amelyeket a pénztár (POS) alkalmazás használ az üzlet csatornában. |

A fizetési módokat meghatározásukkor a főkönyvhöz vagy bankszámlához kell kapcsolni. Ha kihagyja ezt a lépést, a felhasználói hibákat kapnak, amikor megpróbálják menteni a fizetéstípust.

## <a name="refund-payment-methods"></a>Visszatérítési fizetési módok

A visszatérítés feldolgozásának eseteiben a hívásközpont olyan fizetési módokat is használ, amelyek a Kinnlevőségeknél vannak meghatározva. A fizetési módok konfigurálásához, kattintson a **Kiskereskedelem** \> **Csatornabeállítások** \> **Hívásközpont beállítása** \> **Hívásközpont visszatérítési módok** elemre. El kell végeznie ezt a konfigurálást, a vevőknek szóló visszatérítési csekkek feldolgozásához. Például ha a vevő eredetileg kifizette a megrendelést készpénz vagy egy csekk segítségével, a felhasználó visszatérítési csekket akarhat küldeni a vevőnek a Kinnlevőségeken keresztül. Ebben az esetben a készpénz és a csekk fizetéstípusokat a hívásközpontban hozzá kell rendelni a megfelelő fizetési módokhoz a Kinnlevőségeknél annak a biztosítására, hogy a visszatérítés feldolgozása megfelelő legyen.

Ezenkívül, ha a felhasználó visszárurendelést dolgoz fel a Retail hívásközpont-felhasználóként, de nem tudja csatolni a visszaárut egy eredeti értékesítéshez, a **Visszatérés** fizetési módot kell megadni a hívásközponti paraméterei között. Ugorjon ide: **Kiskereskedelem** \> **Csatorna beállítása** \> **Hívásközpont beállítása** \> **Hívásközponti paraméterek**, majd az **RMA/visszáru** lapon, a **Fizetési mód** mezőben, győződjön meg arról, hogy a fizetési mód meg van adva. A fizetési módszer az a fizetési módszer lesz, amely a visszatérítéseknél van alkalmazva. Általában vagy csekk, vagy vevői számla módként kerül meghatározásra.

