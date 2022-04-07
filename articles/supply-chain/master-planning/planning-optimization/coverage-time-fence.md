---
title: Fedezet időkorlátjai
description: Ez a témakör azt ismerteti, hogyan lehet fedezeti időkorlátokat beállítani a tervezési optimalizálás használata esetén. A fedezet időkorlátja a tervezési időhatárt és a korlátot jelzi.
author: t-benebo
ms.date: 01/18/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqGroup, ReqItemTable, ReqPlanSched
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2021-01-18
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 12deca22fd6ff3cb4556e0525ab831e1aea0ee33
ms.sourcegitcommit: ad1afc6893a8dc32d1363395666b0fe1d50e983a
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/23/2022
ms.locfileid: "8468916"
---
# <a name="coverage-time-fences"></a>Fedezet időkorlátjai

[!include [banner](../../includes/banner.md)]

Ez a témakör azt ismerteti, hogyan lehet *fedezeti időkorlátokat* beállítani a tervezési optimalizálás használata esetén. A tervezők meghatározhatják a tervezési időhatárt (a fedezet időkorlátját napokban), és kizárhatják az adott időhatáron túlra eső ellátásokat és igényeket. A fedezet időkorlátja így megakadályozza a „zajt”, amelyet az ellátási javaslatok okozhatnak, amelyekre nem kell hónapokig reagálnia. Ilyen például a következő év előrejelzése és a vevői rendelések, amelyeket a rendes átfutási időnél távolabbi időpontra adtak le.

A fedezeti időkorlát azon napok száma a mai dátum (vagy pontosabban a tervezési futtatás dátuma) után, amelyekből a készlet és az igény ki van zárva. A késések elkerülése érdekében gondoskodnia kell arról, hogy a fedezeti időkorlát hosszabb legyen a teljes átfutási időnél. Az alapértelmezett rendszerbeállítás a 100 nap.

A fedezet időkorlátja a következő szinteken adható meg:

- **Fedezeti csoport** – minden fedezeti csoporthoz be lehet állítani egy alapértelmezett fedezeti időkorlátot.
- **Cikkfedezet** – a cikkhez rendelt fedezetcsoportból örökölt fedezeti időkorlát felülbírálható.
- **Alapterv** – a fedezetcsoportból és a cikkfedezeti beállításokból örökölt fedezeti időkorlát felülbírálható.

Az alábbi szakaszok ismertetik a fedezeti csoportok megadását az egyes szinteken.

## <a name="set-a-coverage-time-fence-for-a-coverage-group"></a>Fedezeti időkorlát beállítása egy fedezeti csoporthoz

Amikor fedezeti időkorlátot ad meg egy fedezeti csoporthoz, a beállítás az adott csoporthoz tartozó összes cikkre (termékre) érvényes. Felülbírálhatja azonban a meghatározott cikkek vagy alaptervek beállítását.

A fedezeti csoportok fedezeti időkorlátját a következő lépések szerint adhatja meg.

1. Manjen az **Alaptervezés \> Beállítás \> Fedezet \> Fedezeti csoportok** menübe.
1. Válasszon ki egy meglévő fedezeti csoportot a listából, vagy hozzon létre egy új fedezeti csoportot.
1. Az **Általános** gyorslapon állítsa a **Fedezet időkorlátja (nap)** mezőt annyi napra, amennyit a fedezeti csoport fedezeti időkorlátjaként használni szeretne.

## <a name="set-a-coverage-time-fence-for-a-specific-item"></a>Fedezeti időkorlát beállítása egy adott cikkhez

Minden cikk (termék) fedezeti csoporthoz tartozik. Ha egy cikkhez kifejezetten nincs fedezeti csoport rendelve, akkor egy alapértelmezett fedezeti csoport érvényes. Minden cikk a fedezeti időkorlátot a fedezeti csoportból örökli. Az időkorlátot azonban szükség esetén felülbírálhatja az egyes cikkekre.

Egy adott cikk fedezeti időkorlátját a következő lépések szerint adhatja meg.

1. Kattintson a **Termékinformációk kezelése \> Termékek \> Kiadott termékek** lehetőségre.
1. A rácsban válasszon egy terméket.
1. A Művelet panelen a **Tervezés** lapon, a **Fedezet** csoportban, kattintson a **Cikk fedezete** elemre.
1. A **Cikkfedezet** lap **Áttekintés** lapján válasszon ki vagy hozzon létre egy sort ahhoz a helyhez, ahol be szeretné állítani a fedezeti időkorlátot.
1. Válassza az **Általános** lapot a kiválasztott telephely beállításainak megnyitásához.
1. Jelölje be a **Fedezeticsoport-beállítások felülbírálata** jelölőnégyzetet.
1. Állítsa a **Fedezet időkorlátja (nap)** mezőt annyi napra, amennyit a cikk fedezeti időkorlátjaként használni szeretne.

## <a name="set-a-coverage-time-fence-for-a-specific-master-plan"></a>Fedezeti időkorlát beállítása egy adott alaptervhez

A fedezet időkorlátja megadható az alapterv szintjén. Ezen a módon meghatározhatja, hogy hány napot fed le az alaptervezés számítása az alaptervre. Ez a beállítás felülbírálja az egyes cikkekre és fedezeti csoportokra beállított fedezeti időbeállításokat.

Egy adott alapterv fedezeti időkorlátját a következő lépések szerint adhatja meg.

1. Válassz az **Alaptervezés \> Beállítás \> Tervek \> Alaptervezések** lehetőséget.
1. Válasszon ki egy meglévő alaptervet a listából, vagy hozzon létre egy új alaptervet.
1. Az **Időkorlátok napokban** gyorslapon a **Fedezet** beállítása legyen *Igen*. Ezután, a beállítás alatti mezőben, adjon meg annyi napot, amennyit a cikk fedezeti időkorlátjaként használni szeretne.

## <a name="considerations-for-coverage-time-fences"></a>A fedezeti időkorlátokkal kapcsolatos szempontok

A fedezeti időkorlátok beállításakor vegye figyelembe a következő pontokat:

- A fedezeti időkorlátok csak az alaptervezés bemeneti adatait érintik. Késés esetén előfordulhat, hogy az eredményül kapott tervezett rendelések dátuma a mai dátum plusz a fedezeti időkorlát utáni.
- A fedezet időkorlátja naptári napban van megadva. A munkanapokat használó naptárak nem befolyásolják az időkorlát számítását. Például a hét mindig hét napnak számít, még akkor is, ha a hétvégék lezárt napként vannak beállítva a munkaidőnaptárban.
- Nem jönnek létre követelménytranzakciók olyan készlethez és igényekhez, amelyek kívül esnek a fedezeti időkorláton.
- Ha bármely jóváhagyott ellátás és igény kívül esik a fedezeti időkorláton, akkor nem lesz betöltve a motorba. Ennek megfelelően nem indít feltöltést, és nem számítja ki a késéseket. Ennek ellenére ezt a készletet és igényt nem szabad törölni a rendszerből.
- A biztonsági készlet mennyiségének variációit (a minimumkulcsokból) figyelmen kívül hagyja a rendszer, ha kívül esnek a fedezeti időkorláton.
- A vállalatközi igény figyelmen kívül lesz hagyva, ha a kért szállítási dátum számítása nem a fedezeti időkorláton belül van. Ne feledje, hogy a beépített alaptervezés esetén a vállalatközi igényt nem korlátozza a fedezeti időkorlát.
- Az igény-előrejelzések figyelmen kívül lesznek hagyva, ha a költségvetési dátum nincs a fedezeti időkorláton belül. Ne feledje, hogy a beépített alaptervezés esetén az igény-előrejelzéseket nem korlátozza a fedezeti időkorlát.
- A tervezés optimalizálása figyelembe veszi az időzónákat. Figyelembe veszi az ellátási és igényhelyek időzónát, valamint a tervezés futtatásának idejét. Az alaptervezés például október 15-én, 11 órakor lesz elindítva egy dán telephelyről (GMT +1 időzóna), és tíz napos fedezeti időkorlátot használ a program. Ebben az esetben az ellátás és igénylés egy seattle-i telephelyről (GMT-8 időzóna) október 25-én hajnali 2 óráig lesz belefoglalva (= az alaptervezés aktiválása után tíz 24 órás nap, mínusz a 9 órás időzóna-különbség). Ne feledje, hogy a beépített alaptervezési motor csak az időkorlát dátumát veszi figyelembe. Ennek megfelelően az eredmény eltérő lehet.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]