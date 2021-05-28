---
title: Raktári kötegelt és sorozatfoglalási hierarchiák hibaelhárítása
description: Ez a témakör azt mutatja be, hogyan lehet megoldani gyakori problémákat, miközben az olyan foglalási hierarchiákat használja, amelyek kötegelt vagy sorozatdimenziókat használnak.
author: perlynne
ms.date: 3/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 3/12/2021
ms.openlocfilehash: 1cd4883cdd95a97f821e0103da910e2c0346a08d
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/11/2021
ms.locfileid: "6022546"
---
# <a name="troubleshoot-warehouse-batch-and-serial-reservation-hierarchies"></a>Raktári kötegelt és sorozatfoglalási hierarchiák hibaelhárítása

[!include [banner](../includes/banner.md)]

Ez a témakör azt mutatja be, hogyan lehet megoldani gyakori problémákat, miközben az olyan foglalási hierarchiákat használja, amelyek kötegelt vagy sorozatdimenziókat használnak.

További információ: [Rugalmas raktárszintű dimenzió foglalási irányelv](flexible-warehouse-level-dimension-reservation.md).

Egy cikk foglalási hierarchiája határozza meg a tárolási dimenziók követelményét, amelyet teljesíteni kell ahhoz, hogy helyet rendeljen egy igény szerinti rendeléshez. Ezek a dimenziók a *hely feletti dimenziókként* írhatóak le, a hely hozzárendelése előtt kitöltendő összes dimenzióhoz és a *hely alatti dimenziókhoz*, olyan dimenziókhoz, amelyek feloszthatók az igény szerinti rendeléshez rendelt hely után. Ezeket a foglalási hierarchiákat más néven *köteg-felett* és *köteg-alatt* foglalási hierarchiáknak is nevezik, vagy *sorozat-felett* és *sorozat-alatt* foglalási hierarchiáknak.

A készlet csak akkor osztható fel sikeresen, ha a hely feletti dimenziókban nincsenek rések. Például a *köteg-felett* foglalási hierarchiában az várható, hogy a **Telephely**, a **Raktár** és a **Kötegszám** dimenziók meg vannak adva az igény szerinti rendelésen. Ha ezek közül a dimenziók közül bármelyik hiányzik, a felosztási folyamat sikertelen lesz. Ezzel szemben a *köteg-alatt* vagy *sorozat-alatt* foglalási hierarchiában előfordulhat, hogy az igény szerinti rendelésen meg van adva egy köteg- vagy sorozatszám, de a felosztási folyamathoz nincs rá szükség.

## <a name="i-receive-the-following-error-message-to-be-assigned-to-wave-load-lines-must-specify-the-dimensions-above-the-location-to-assign-these-dimensions-reserve-and-recreate-the-load-line"></a>A következő hibaüzenet jelenik meg: „A hullámhoz hozzárendelni kívánt soroknak meg kell adni a hely fölötti dimenzióit. Ezeknek a dimenzióknak a hozzárendeléséhez foglalja le és hozza létre újból a rakománysort.”

### <a name="issue-description"></a>Probléma leírása

Ha olyan cikket használ, amelyben a *köteg-felett* foglalási hierarchia szerepel, akkor a **Rakománytervezési munkaterület** oldal **Kiadás a raktárba** parancsa nem működik, amikor részleges mennyiségre próbál kiadni egy rakományt. Ez a hibaüzenet jelenik meg, és a rendszer nem hoz létre munkát a részleges mennyiséghez.

Azonban ha olyan cikket használ, amelyben a *köteg-alatt* foglalási hierarchia szerepel, akkor kiadhat egy rakományt részleges mennyiségre a **Rakománytervezési munkaterület** oldaláról.

### <a name="issue-cause"></a>Probléma oka

Ha a foglalási hierarchiában a **Hely** dimenzió felett található egy dimenzió, akkor azt a raktárba történő kiadás előtt meg kell határozni. A részleges mennyiségek nem adhatók ki, ha a **Hely** fölötti egy vagy több dimenzió nincs meghatározva.

## <a name="the-auto-reservation-prompt-for-a-batch-number-is-triggered-even-though-there-is-available-inventory"></a>A kötegszámra vonatkozó automatikus foglalási kérése akkor is aktiválódik, ha rendelkezésre áll készlet.

### <a name="issue-description"></a>Probléma leírása

Ha olyan cikket használ, amely *köteg-felett* foglalási hierarchiával rendelkezik egy olyan raktárban, amely nem engedélyezte a raktári folyamatokat, és az automatikus foglalás engedélyezve van, a kötegszám automatikus foglalási kérése akkor is megjelenik, ha csak egy köteg áll rendelkezésre kitárolásra.

Ha azonban ugyanazt a cikket használja egy raktárban, ahol a raktári folyamatok engedélyezve vannak, az automatikus foglalási kérdés nem jelenik meg.

### <a name="issue-cause"></a>Probléma oka

Ha a foglalási hierarchia meghatározása *köteg-felett* vagy *sorozat-felett*, a hivatkozott dimenziót (**Kötegszám** vagy **Sorozatszám**) mindig meg kell adni igény szerinti rendeléseknél. A raktári folyamatok akkor tölthetik ki az adatokat, ha egyetlen köteg- vagy sorozatszám áll rendelkezésre. Mivel azonban a raktár nincs engedélyezve a raktári folyamatokhoz, a felhasználónak mindig meg kell adnia az összes **Hely** feletti dimenziót.

## <a name="slotting-templates-that-have-the-consider-on-hand-slot-criterion-dont-consider-current-on-hand-inventory-for-batch-enabled-items"></a>Azok az időközökre bontási sablonok, amelyeknél az Aktuálisan készleten lévők figyelembe vétele időközfeltétel fennáll, nem veszik figyelembe az aktuális tényleges készletet a kötegeléshez engedélyezett cikkeknél.

További információ: [Raktári időközökre bontás](warehouse-slotting.md).

### <a name="issue-description"></a>Probléma leírása

Azok az időközökre bontási sablonok, amelyeknél az *Aktuálisan készleten lévők figyelembe vétele* időközfeltétel fennáll, nem veszik figyelembe az aktuális tényleges készletet a *köteg-felett* cikkeknél. Csak akkor veszik figyelembe, ha a kötegszám meg van adva az értékesítésirendelés-sorban.

*Köteg-alatt* cikkek használatakor azonban az aktuális tényleges készlet az elvárt.

### <a name="issue-cause"></a>Probléma oka

Az időközökre bontási sablon fejlécében meg lehet határozni a *Megrendelve*, *Lefoglalva* vagy a *Kiadva* igény szerinti stratégiához. A *Megrendelve* igény szerinti stratégia esetén ugyanazok a foglalásihierarchia-követelmények érvényesek, amelyek a foglalási vagy raktárba kiadási folyamatok esetén érvényesek. Ezért a *köteg-feletti* és *sorozat-alatti* foglalási hierarchiákkal rendelkező cikkeknél meg kell adni a köteg- vagy sorozatszámot az igény szerinti rendelésen (értékesítés vagy átmozgatás). Másik lehetőségként a *Lefoglalva* igény szerinti stratégia arra használható, hogy kiválassza a köteg- vagy sorozatszámot, mielőtt létrejön a raktár időközökre bontási igénye.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
