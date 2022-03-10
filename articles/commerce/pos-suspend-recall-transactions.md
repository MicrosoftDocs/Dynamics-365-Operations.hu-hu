---
title: Tranzakció felfüggesztése és újraindítása a pénztárban (POS)
description: Ez a témakör bemutatja, a felhasználók, hogyan függeszthetnek fel folyamatban lévő tranzakciókat, majd folytathatják azokat később egy másik jegyzék használatával a Dynamics 365 Commerce használatával.
author: jblucher
ms.date: 11/27/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: 261234
ms.assetid: 7cd68ecc-cc09-48ab-8cb8-48d5c304effa
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 2efc88cfa7a8cede50969484d275c6fdbb2204dd2f29b3f8c7340d02cb61a79c
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6737554"
---
# <a name="suspend-and-resume-a-transaction-in-the-point-of-sale-pos"></a>Tranzakció felfüggesztése és újraindítása a pénztárban (POS)

[!include [banner](includes/banner.md)]


A pénztár (POS) felhasználók a folyamatban lévő tranzakciókat felfüggeszthetik, majd később folytathatják azokat később vagy egy másik jegyzékben. Tranzakciókat gyakran azért függesztik fel, hogy gyorsan felszabadítsanak egy jegyzéket egy másik feladathoz, anélkül, hogy elveszítenék az aktuális tranzakcióban a haladást. Például egy bolti alkalmazott elkezd feldolgozni egy ügyféltranzakciót egy mobileszközön, de készpénzfiókos kasszán kell azt befejeznie. Ebben az esetben a bolti alkalmazott felfüggesztheti a tranzakciót a mobileszközön, majd előhívhatja, és folytathatja egy pénztárgépen.

## <a name="configure-suspend-and-resume-functionality"></a>A felfüggesztés folytatás funkció beállítása

### <a name="pos-operations"></a>Pénztári műveletek

Két [pénztári művelet](pos-operations.md) teszi lehetővé a pénztárnak az esetek felfüggesztését és folytatását. Ezeket a műveleteke, hozzárendelheti [gombrácsokhoz](pos-screen-layouts.md) tranzakció lapon vagy a kezdőlapon.

- 503: Tranzakció felfüggesztése
- 504: Tranzakció visszahívása

### <a name="receipt-template"></a>Nyugtasablon

A pénztár beállítható úgy, hogy létrehozzon egy nyomtatott blokkot, ha a tranzakció fel van függesztve. A blokkal később gyorsan lehet azonosítani és előhívni a tranzakciót.

Ahhoz, hogy a pénztár blokkot nyomtathasson a **Felfüggesztett tranzakció** nyugtaformátumot hozzá kell adnia a bolt nyugtaprofiljához. A nyugtaformátumot megtervezheti úgy, hogy az tartalmazza vagy ne tartalmazza a tranzakció részleteit. A formátum például tartalmazhat vonalkódot a beolvasás támogatásához.

### <a name="receipt-numbering"></a>Nyugta számozása

Egyéb pénztártranzakció-típusok esetében, amelyek nyomtatott nyugtát hoznak létre, meghatározhat egy számsorozatot a felfüggesztett tranzakciókhoz a bolt működési profiljának **Nyugta számozása** részében.

### <a name="void-when-closing-shift"></a>Érvénytelenítés műszakzáráskor

Használhatja a **Érvénytelenítés műszakzáráskor** lehetőséget, így megkövetelheti a felhasználóktól, hogy befejezzék vagy érvénytelenítsék a felfüggesztett tranzakciókat műszakjuk zárásakor. A **Műszakzárás** művelet során, a pénztár felkéri a felhasználókat, hogy tekintsék meg vagy érvénytelenítsék a függőben lévő felfüggesztett tranzakciókat.

## <a name="suspend-and-resume-a-transaction"></a>Tranzakció felfüggesztése és folytatása

### <a name="suspend-a-transaction"></a>Tranzakció felfüggesztése

A felhasználók, akik rendelkezik a megfelelő jogosultságokkal, és akiknek képernyő-elrendezése tartalmazza a **Tranzakció felfüggesztése** műveletet, felfüggeszthetnek egy tranzakciót, hogy később azt egy másik pénztárban előhívhassák.

Tranzakciók csak akkor függeszthetők fel, ha **nem** tartalmazzák a következő sortípusokat:

- Aktív Fizetési sorok
- Ajándékutalvány-sorok (akár ajándékutalvány kibocsátása, akár hozzáadás ajándékkártya egyenlegéhez)

Felfüggesztett tranzakció nincs hatással a bolt értékesítési információira vagy raktárelérhetőséggel kapcsolatos információira.

### <a name="resume-a-suspended-transaction"></a>Felfüggesztett tranzakció visszahívása

Felfüggesztett tranzakciók visszahívhatók, és folytathatók ugyanabban az áruházban minden felhasználó által, aki rendelkezik a megfelelő jogosultságokkal és képernyő-elrendezése tartalmazza a **Tranzakció visszahívása** műveletet.

Egy felfüggesztett tranzakció gyors és könnyű visszahívásához olvassa be a kinyomtatott nyugta vonalkódját, amikor megtekinti a tranzakciók listáját a **Tranzakció visszahívása** műveletnél.

### <a name="considerations-for-offline-mode"></a>Információk offline módhoz

- A pénztár online módjában felfüggesztetett tranzakciók kapcsolat nélküli módban nem folytatható, mert az adatok nincsenek szinkronizálva az offline adatbázissal.
- Ha felfüggeszt egy tranzakciót, amíg a pénztár offline módban van, visszahívhatja azt offline módban, feltéve, hogy a pénztár nem váltott vissza online módba bármikor, amíg a tranzakció fel volt függesztve. A pénztár online módba kapcsolásakor felfüggesztett tranzakciók adatait átkerülnek az online adatbázis és az offline adatbázisból el lesznek távolítva. Emiatt a tranzakciók csak online módban folytathatók. Ha pénztárt offline módba váltja vissza, nem tudja folytatni ezeket a felfüggesztett tranzakciókat, mert azok már el lettek távolítva az offline adatbázisból.

### <a name="void-a-suspended-transaction"></a>Felfüggesztett tranzakció érvénytelenítése

A felfüggesztett tranzakciókat érvénytelenítheti úgy, hogy előhívja a tranzakciót,.majd elvégzi a **Tranzakció érvénytelenítése** műveletet, vagy a tranzakció kiválasztásával a **Tranzakció visszahívása** listán, majd az **Érvénytelenítés** kiválasztásával az alkalmazás sávján. Másik lehetőségként az üzlet beállítható úgy, hogy felkérje a felhasználókat a függőben lévő tranzakciók érvénytelenítésére, amikor lezárják műszakjukat.


[!INCLUDE[footer-include](../includes/footer-banner.md)]