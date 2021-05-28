---
title: Év végi záráskor hiányzó nyitó egyenlegek
description: Ez a témakör ismerteti, hogy miért hiányozhatnak nyitó egyenlegek egy év zárásakor, és hogyan tudja újból létrehozni ezeket az egyenlegeket, amennyiben hiányoznak.
author: kweekley
ms.date: 05/12/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2020-12-14
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 045d0bf11b11c9a353858ce3ca82c698dbceea7c
ms.sourcegitcommit: 817716c2e96f24af0ef1d7d5323afdeccdc602f3
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/13/2021
ms.locfileid: "6028567"
---
# <a name="year-end-close-missing-opening-balances"></a>Év végi záráskor hiányzó nyitó egyenlegek

[!include [banner](../includes/banner.md)]

Ez a témakör ismerteti, hogy miért hiányozhatnak nyitó egyenlegek egy év zárásakor, és hogyan tudja újból létrehozni ezeket az egyenlegeket, amennyiben hiányoznak.

### <a name="symptom"></a>Tünet

Miért nincsenek nyitó egyenlegek a Főkönyv év végi zárásának futtatása után? 

### <a name="resolution"></a>Megoldás

Az alábbiakat érdemes ellenőriznie, ha végrehajtotta az év zárását a Főkönyvben, majd létrehozott egy főkönyvi kivonatot, amelyben nem láthatók nyitó egyenlegek a következő pénzügyi évre vonatkozóan.

Ha az **Előző zárás visszavonása** mezőnél az **Igen** érték szerepel, a rendszer ugyanarra a pénzügyi évre vonatkozóan vissza fogja vonni az előző év végi zárást. Az év végi zárás visszavonási folyamatának futtatásakor a program a záró és nyitó egyenlegekhez kapcsolódó összes bejegyzést törli, mintha az évet nem zárták volna még le. A program a bizonylatokat is törli. A program nem indítja el automatikusan újra az év végi zárás folyamatát. A folyamatot Önnek kell újraindítania. Ügyeljen rá, hogy az **Előző zárás visszavonása** lehetőség értékét a **Nem** értékre frissítse.

Ezt a forgatókönyvet az év végi zárással kapcsolatos GYIK témakör tárgyalja. További információ: [Év végi tevékenységek GYIK](faq-year-end-activities.md).

### <a name="symptom"></a>Tünet

Az év végi zárást úgy futtattam, hogy az **Előző zárás visszavonása** beállítás értéke **Nem** volt, de még mindig nem jelennek meg nyitó egyenlegek a pénzügyi évhez.

### <a name="resolution"></a>Megoldás

Először ellenőrizze a kötegelt feladat állapotát. Az év lezárásához több különálló feladat tartozik, de a legkritikusabb lépés a **5.0.0. lépés** feladatleírással rendelkező kötegelt feladat. A nyitótranzakciók és opcionálisan a záró tranzakciók feladása a főkönyvbe ebben a lépésben történik. 

[![Kötegelőzmény-lista](./media/yec-mssng-open-blnces-01.png)](./media/yec-mssng-open-blnces-01.png)

Ha ez a lépés sikeresen befejeződött, de nem láthatók nyitó egyenlegek a **Főkönyvi kivonat lekérdezése** oldalon (**Főkönyv > Lekérdezések és jelentések > Főkönyvi kivonat**), vizsgálja meg az év végi zárás kötegelt feladatának eredményeit, hogy az Egyenlegek újbóli létrehozása lépés sikeresen befejeződött-e.

[![Az év végi zárás kötegelt feladatának eredményei](./media/yec-mssng-open-blnces-02.png)](./media/yec-mssng-open-blnces-02.png)

Ha ez a lépés bármilyen okból sikertelen volt, a nyitó (és opcionálisan a záró) tranzakciók feladása valószínűleg sikeres volt. A főkönyvi tranzakciók feladásának sikerességét a **Bizonylattranzakciók lekérdezése** oldal használatával ellenőrizheti, ha megadja a lezárt év év végi zárásakor megjelenő párbeszédablakán megadott bizonylat számát és dátumát (**Főkönyv > Lekérdezések és jelentések > Bizonylattranzakciók**).

[![Bizonylattranzakciók lekérdezése](./media/yec-mssng-open-blnces-03.png)](./media/yec-mssng-open-blnces-03.png)

Ha a nyitó (és opcionálisan a záró) bizonylatok jelen vannak, akkor nem kell újra futtatnia az év végi zárást. Ehelyett olvassa el a következő szakaszt a következő lépésekkel kapcsolatos információkért.

### <a name="symptom"></a>Tünet

Az év végi zárás „Egyenlegek újbóli létrehozása” lépés sikertelen volt, újra kell-e futtatnom a teljes év végi zárási folyamatot?

### <a name="resolution"></a>Megoldás

Az Egyenlegek újbóli létrehozása lépés frissíti a Főkönyvi kivonat lekérdezésének létrehozása során használt Főkönyvi egyenlegek értékét.  Ez az év végi zárási folyamat utolsó lépése.  Ha ez a lépés az egyetlen sikertelen lépés, a főkönyvi tranzakciók feladása sikerült.  Nem szükséges újra futtatnia az év végi zárást. A folyamat futtatásával manuálisan újból létrehozhatja az egyenlegeket a **Pénzügyi dimenziókészletek** oldalon (**Főkönyv > Számlatükör > Dimenziók > Pénzügyi dimenziókészletek**).

[![Egyenlegek újbóli létrehozása gomb a Pénzügyi dimenziókészletek oldalon](./media/yec-mssng-open-blnces-04.png)](./media/yec-mssng-open-blnces-04.png)

Ha a lépés feldolgozása hosszú időt vesz igénybe, javasoljuk, hogy tekintse át a pénzügyi dimenziókészletekre vonatkozó gyakorlati tanácsokat a [Pénzügyi dimenziókészletek frissítésére vonatkozó gyakorlati tanácsok](https://community.dynamics.com/365/financeandoperations/b/dynamics-365-finance-blog/posts/best-practices-for-updating-financial-dimension-set-dimension-sets) részben. 

