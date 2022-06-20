---
title: Feladásdefiníciók
description: A cikk feladás-definíciókról, valamint azok meghatározásáról és linkeléséről biztosít információt. A támogatott feladási típusok és dokumentumok esetében feladásdefiníciókat használhat a feladási profilok helyett, és ezekkel osztályozhatja a fő számlákat és a pénzügyi dimenziókat a könyvelési tételekben.
author: kweekley
ms.date: 09/03/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: JournalizingDefinition, JournalizingDefinitionTrans, LedgerParameters
audience: Application User
ms.reviewer: kfend
ms.custom: 15741
ms.assetid: 1495e7e0-2e39-464c-8da9-f55b1ca1c6bb
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f60506e039623ae7a97f6b4e835f751da15ac0c1
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8898149"
---
# <a name="posting-definitions"></a>Feladásdefiníciók

[!include [banner](../includes/banner.md)]

A cikk feladás-definíciókról, valamint azok meghatározásáról és linkeléséről biztosít információt.
A támogatott feladási típusok és dokumentumok esetében feladásdefiníciókat használhat a feladási profilok helyett, és ezekkel osztályozhatja a fő számlákat és a pénzügyi dimenziókat a könyvelési tételekben. A támogatott dokumentumok és feladási típusok listáját a **Tranzakció-feladásdefiníciók** oldalon tekintheti meg. 

A feladásdefiníciók használatának megkezdéséhez jelölje be a **Feladásdefiníciók használata** opciót a **Főkönyvi paraméterek** oldalon. Még a feladásdefiníciók használata esetén is kell definiálnia feladási profilokat az eredeti bejegyzések és a nem támogatott feladási típusok és dokumentumok számára. 

Feladásdefiníciókat kell használnia annak érdekében, hogy lehetővé tegye a kötelezettségvállalás-könyvelést a beszerzési rendeléseknél, és a használja, és a pre-kötelezettségvállalási könyvelsét beszerzési igényléseknél.

## <a name="defining-posting-definitions"></a>Feladásdefiníciók meghatározása
A **Feladásdefiníciók** lapon adhatja meg az egyeztetési feltételeket és határozhatja meg azokat a bejegyzéseket, amelyeket a rendszer egyezés esetén kell generáljon. A egyezési feltételeket az eredeti bejegyzésekre vonatkozóan könyvelési felosztásként értékeli a rendszer. 

A **Feladásdefiníciók** lapon prioritási számértékeket is hozzárendelhet a beérkezési sorokhoz, így vezérelheti, hogy milyen sorrendben értékelje őket a rendszer. A legalacsonyabb prioritási számú sorokat fogja először értékelni. Így például először az 1. prioritási számú sorok következnek, majd a 2. számúak, satöbbi. Egyezés esetén a többi egyezési feltétel figyelmen kívül lesz hagyva. Emellett csak azon feltétel generál majd bejegyzést, amely az eredeti tranzakcióval is egyezik. 

A feladásdefiníciókat a **Tesztelje a feladásdefiníciót** varázsló segítségével ellenőrizheti. Miután definiált egy mintaként szolgáló eredeti bejegyzést a feladásdefinícióhoz, megjelennek a létrehozott bejegyzések. 

A feladásdefiníció-verziókat érvényességi dátumokkal együtt használhatja. Példáu létrehozhat egy jövőbeli verziót egy feladásdefinícióból, amelyet az új pénzügyi évben egy másik főkönyvre való feladásokhoz használhat. 

A **Tranzakció-feladásdefiníciók** oldalon rendelhet hozzá feladásdefiníciókat a tranzakciótípusokhoz.

## <a name="linking-posting-definitions"></a>Feladásdefiníciók összekapcsolása
A feladásdefiníciók létrehozásakor hozzá is kapcsolhatja azokat egy másikhoz. A rendszer ezek után az aktuális feladásdefiníció feltételeinek kiegészítéseként figyelembe veszi a hozzákapcsolt definíció feltételeit is. Ezzel a funkcióval idő takarítható meg, mert nem kell ismételten megadnia a feltételeket az akatuális feladásdefinícióhoz a **Bejegyzések** gyorslapon a **Feladásdefiníciók** oldalon, ha azokat egy másik definícióban már rögzítette. 

A diagramokon és a táblákban rögzítsen minden hivatkozást, amelyet a későbbiekben még használni szeretne. Az aktuális feladásdefinícióval való ütközés elkerülése érdekében ügyeljen rá, hogy minden hivatkozott feladásdefiníció sorai egyedi legyen. 

Az alábbi korlátozásokkal kell számolnia a feladásdefiníció-összekapcsolások létrehozásakor:

-   Egy adott feladásdefinícióból vagy egy másikra hivatkozhat, vagy egy másikból hivatkozhat erre, de nem lehet mindkettő. Egy feladásdefiníció azoban több másikra is hivatkozhat.
-   Csak olyan feladásdefiníciók között állíthat fel kapcsolatot, amelyek ugyanabban a modulban találhatóak.
-   Egy feladásdefiníciót bármely tranzakciótípushoz hozzárendelhet, de a tranzakciótípus is ugyanabban a modulban kell legyen, mint a feladásdefiníció. Használja a **Tranzakció-feladásdefiníciók** lapot, ahol láthatja, melyik modulban szerepel egy adott tranzakciótípus.


További információkért lásd: [A feladásdefiníció példái](example-posting-definitions.md). 




[!INCLUDE[footer-include](../../includes/footer-banner.md)]
