---
title: A pénzügyi dimenziók és a feladás
description: Amikor megtervezi beállítja a számlatükröt, át kell gondolnia, hogyan működnek majd együtt az egyes elemek egy dokumentum vagy egy napló feladásakor. Ezen összetevők közé tartoznak a számlastruktúrák, a speciális szabályok, valamint a kiegyenlítő és a rögzített dimenziók. Ez a témakör ismerteti az összetevőket, valamint az összetevők együttműködését.
author: aprilolson
manager: AnnBe
ms.date: 08/04/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerChartofAccounts,DimensionDetails
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14091
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 2e218351f2462ca135ef6e453fb127c3e111fc40
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/01/2019
ms.locfileid: "1839665"
---
# <a name="financial-dimensions-and-posting"></a>A pénzügyi dimenziók és a feladás 

[!include [banner](../includes/banner.md)]

Amikor megtervezi beállítja a számlatükröt, át kell gondolnia, hogyan működnek majd együtt az egyes elemek egy dokumentum vagy egy napló feladásakor. Ezen összetevők közé tartoznak a számlastruktúrák, a speciális szabályok, valamint a kiegyenlítő és a rögzített dimenziók. Ez a témakör ismerteti az összetevőket, valamint az összetevők együttműködését.

## <a name="chart-of-accounts-and-financial-dimension-components"></a>Számlatükör és pénzügyi dimenzió összetevők

A Microsoft Dynamics 365 for Finance and Operations gazdag, szabály alapú rendszer a fő számlák és pénzügyi dimenzió értékeinek érvényes kombinációinak meghatározásához. Ez a témakör rövid áttekintést nyújt az egyes összetevők funkcióiról, és elmagyarázza, hogy hol található az összetevő.

### <a name="account-structures"></a>Számlastruktúrák

A főkönyv beállításakor számlastruktúrára van szükség. Meg kell határoznia és aktiválnia legalább egy számlastruktúrát, és hozzá kell rendelnie a főkönyvhöz. A számlastruktúrának tartalmaznia kell a fő számlát. Meghatározhatja a vállalkozása számára legjobban működő szegmenssorrendet. A fő számla meghatározása után a rendszer meghatározhatja a használt számlastruktúrát. Ha a fő számlát az első helyre vagy egy struktúra eleje mellé helyezi, segíthet az értékek korlátozásában, valamint segíthet a rendszernek az utolsó ismert érvényes érték alapértelmezett értékként való alkalmazásában. A számlastruktúrában legfeljebb 10 további pénzügyi dimenzió szerepelhet. A számlastruktúra határozza meg, hogy mely dimenzióértékek érvényesek egyéb értékekkel együtt kombinálva. azt is meghatározza, hogy meg kell-e adni dimenzióértékeket.

### <a name="advanced-rules"></a>Speciális szabályok

A speciális szabályok választható összetevők a számlatükör beállítása során. Egy számlastruktúrához tetszőleges számú kívánt speciális szabályt adhat hozzá. A speciális szabályok gyakran használatosak olyan helyzetek kezelésére, ahol a további pénzügyi dimenziókat követni kell bizonyos feltételek teljesülése esetén. Ha például Utazási költségek számlát használt, érdemes nyomon követni a további információkat, például azt az eseményt, amelyre az alkalmazott utazik. Ha több speciális szabály van, ezeket a rendszer betűrendben, a szabályok neve alapján alkalmazza. A szabály által hozzáadott szegmenseket csak a számlastruktúra szegmenseit követően lehet alkalmazni.

### <a name="balancing-dimension"></a>Kiegyenlítő dimenzió

Tetszés szerint meghatározhat egy kiegyenlítő pénzügyi dimenziót. A **Főkönyv** lapon megadhatja a kiegyenlíteni kívánt pénzügyi dimenziót. Ezt követően, ha tranzakciók kerülnek feladásra ehhez a pénzügyi dimenzióhoz, a rendszer automatikusan bejegyzéseket hoz létre és ad fel a pénzügyi dimenzió kiegyenlítése érdekében.

### <a name="defaultfixed-financial-dimensions-on-the-main-account"></a>Alapértelmezett/rögzített pénzügyi dimenziók a fő számlán

Az alapértelmezett dimenziók különböző helyekről származnak, például törzsrekordokból (például vevő- vagy szállítórekordok), a dokumentum-fejlécekből és a fő számlából. Ez a témakör a jogi személy fő számlájának alapértelmezett dimenzióinak bemutatására szolgál. Megadhatja, hogy a fő számla rendelkezik-e **Nem rögzített** vagy **Rögzített** értékkel minden olyan pénzügyi dimenzió esetében, amelyet a főkönyv összes számlastruktúrájában használ. Ha a pénzügyi dimenzió **Nem rögzített**, akkor az alapértelmezett értéket használja, de ez az érték módosítható. Ez a viselkedés minden alapértelmezett értékre vonatkozik a rendszerben, még azokra is, amelyek a törzsrekordokból származnak. Ha egy pénzügyi dimenzió értéke **Rögzített**, a rendszer mindig azt az értéket alkalmazza, függetlenül attól, hogy alapértelmezett értékként vagy a felhasználó által megadott értékként érkezett.

## <a name="order-in-which-default-dimensions-are-applied-during-posting"></a>A rendelés feladása során alkalmazott alapértelmezett dimenziók sorrendje

Az emberekben gyakran felmerül az egyes elemek futtatásával kapcsolatos sorrend. Nagyon fontos megérteni az alapértelmezett dimenziók alkalmazási sorrendjét, mivel ez a viselkedés hatással van a beállítás során alkalmazott megközelítésre.

> [!NOTE]
> Ez az információ csak az alapértelmezett dimenziók alkalmazására vonatkozik. Ha a Microsoft Excel vagy az adatkezelési keretrendszer segítségével importálja az adatokat, ez a viselkedés eltérő.

### <a name="example-1"></a>1. példa

**Számlastruktúra**

| Fő számla            | Üzleti egység           | Osztály              | Költséghely             |
|-------------------------|-------------------------|-------------------------|-------------------------|
| Minden érték megengedett. | Minden érték megengedett. | Minden érték megengedett. | Minden érték megengedett. |

**Fő számla**

| Fő számla | Név          | Jogi személy | Osztály                                 |
|--------------|---------------|--------------|--------------------------------------------|
| 401100       | Termékértékesítés | USMF         | Rögzített – 022 Értékesítési és marketingrészleg |

A következő ábrán a rögzített alapértelmezett dimenzió látható, amely a 401100 fő számlán van beállítva.

[![Alapértelmezett pénzügyi dimenziók](./media/default-dimensions.png)](./media/default-dimensions.png)

Nagyon egyszerű példaként megadunk egy főkönyvi naplót, ahol a Részlegdimenziót a **023** (Műveletek) alapértelmezett érték használatára állítottuk be. Most beírunk és feladunk egy főkönyvi számlát. A következő ábrán az alapértelmezett pénzügyi dimenzió látható a főkönyv fejlécén.

[![Általános naplók](./media/general-journal.png)](./media/general-journal.png)

A naplófejlécen levő alapértelmezett dimenzió következtében a 023 részleg alapértelmezés szerint alkalmazandó lesz az értékesítési számlasorban. A következő ábrák az általános naplósort jelenítik, ahol a rendszer alkalmazza a **023** alapértelmezett dimenzióértéket a fejlécből.

[![Naplóbizonylat](./media/journal-voucher.png)](./media/journal-voucher.png)

Azonban a sor feladásakor a rendszer a rögzített dimenziót alkalmazza, és a sort a 022 részlegnek adja fel. Az alábbi ábra a feladott bizonylatot jeleníti meg, amelyre a rendszer a rögzített dimenziót alkalmazta az értékesítési számlára.

[![Bizonylattranzakciók](./media/voucher-transactions.png)](./media/voucher-transactions.png)

### <a name="example-2"></a>2. példa

Ez a példa ugyanazt a beállítást használja, mint az első példa. Mi azonban egy második összetevőt adunk hozzá, a Részlegdimenziót pedig kiegyenlítő dimenzióként használjuk. Az alábbi példában a **Részleg** az USMF főkönyvhöz beállított kiegyenlítő pénzügyi dimenzió.

[![Főkönyv](./media/ledger.png)](./media/ledger.png)

Ha a napló fejléce ugyanazt a beállítást használja, és ugyanazt a tranzakciót adja fel, először a rögzített dimenzió érvényesül. Ezután a kiegyenlítő logika következik, amely garantálja, hogy minden részleg kiegyensúlyozott tétellel rendelkezzen. Az alábbi ábra olyan bizonylattranzakciókat jelenít meg, amelyek tartalmazzák a rögzített dimenziók alkalmazása utáni kiegyenlítő bejegyzést.

[![Bizonylattranzakciók](./media/voucher-transactions2.png)](./media/voucher-transactions2.png)

### <a name="example-3"></a>3. példa

Ebben a példában hozzáadunk egy speciális szabályt. A speciális szabály meghatározza, hogy a 401100 értékesítési számla és a 022 részleg (Értékesítés és marketing) használata esetén a rendszernek egy további szegmenst kell nyomon követnie: ez a Vevő szegmens.

Ez a példa a sorrend miatt fontos. A számlastruktúra meghatározása a fő számla megadása után történik. Ha a számlastruktúra beállítására hivatkozik, a rendszer meghatározhatja, hogy a fő számla, az üzleti részleg, a részleg és a költséghely relevánsak-e. Ezen a ponton a speciális szabályra még nem került sor, mert rögzített dimenziók alkalmazása nem történik meg mindaddig, amíg az alapértelmezett dimenziókat nem alkalmazták a naplóbizonylathoz a feladás során. Az alábbi példában a Vevő szegmens nincs jelen, mert a speciális szabály kritériumai nem teljesültek.

[![Főkönyvi számla](./media/drop-down.png)](./media/drop-down.png)

A feladás sikertelen lesz, mert a rögzített dimenziót a folyamat végén alkalmazták. A dimenzió ellenőrzése meghatározza, hogy a Vevő szegmensre akkor van szükség, ha a fő számla 401100, a részleg pedig 022. A feladás ellenőrzési hiba miatt nem hajtható végre. A következő ábrán látható az az üzenet, amely azután jelenik meg, hogy a dimenzió ellenőrzése meghatározza, hogy a Vevő szükséges szegmens.

[![Üzenet részletei](./media/message.png)](./media/message.png)

Ebben a példában felül kell írni az alapértelmezett értéket úgy, hogy a speciális szabály elinduljon és megadhassa a Vevő szegmenst. Azonban ez a megoldás nem mindig lehetséges, és bizonyos felhasználók nem is tudnak a feladási szabályok létezéséről. Ezért fontos megérteni az alapértelmezett dimenziók alkalmazási sorrendjét a számlatükrök beállítása során.

Ebben a példában a kívánt eredmény eléréséhez többféle módon módosíthatja a konfigurációt. Például új számlastruktúrát hozhat létre az értékesítési számlákhoz, és felveheti a struktúrába a Vevő szegmenst. A meglévő számlastruktúrához további sorokat adhat hozzá, valamint megadhatja a fő számlát és az érvényes részlegértékeket is. Ezt követően a kiegészítő Vevő szerkezetben hasznosnak bizonyulhategy külön számlastruktúra azon értékesítési számlák esetében, ahol szerepel a Vevő szegmens.

## <a name="additional-resources"></a>További erőforrások 

Az alábbi segédanyagok egy része a Finance and Operations rendszer egy korábbi verziójára vonatkozik. Azonban az alapértelmezett dimenziók alkalmazásával kapcsolatos információk és fogalmak közül számos megegyezik a korábbi verzióval, és így a hivatkozások továbbra is érvényesek.

[Kiegyensúlyozott naplók egységközi számlázáshoz](example-balanced-journals-interunit-accounting.md)

[Számlatükör tervezése](plan-chart-of-accounts.md) 

[Számlatükör tervezése az AX 2012 rendszerben blog](https://blogs.msdn.microsoft.com/axsa/2014/06/12/planning-your-chart-of-accounts-in-ax-2012-part-1-of-7/) – A hivatkozás egy hétrészes cikksorozat első részére mutat.

[Dimenzió alapértelmezés a könyvelési felosztásokban](https://blogs.msdn.microsoft.com/ax_gfm_framework_team_blog/2013/12/16/dimension-defaulting-in-accounting-distributions-part-1-introduction/)

[Dimenzió alapértelmezés a Dimenzió-keretrendszerben](https://blogs.msdn.microsoft.com/ax_gfm_framework_team_blog/2014/09/)
