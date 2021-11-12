---
title: Ütemezés képességen alapuló erőforrás-kijelöléssel
description: Ez a témakör leírja az erőforrás-kiválasztást a korlátlan kapacitásütemezés során, amikor erőforrásigényként adja meg a műveletekhez szükséges erőforrásokat.
author: ChristianRytt
ms.date: 9/3/2021
ms.topic: article
ms.search.form: RouteInventProd, WrkCtrTable, WrkCtrCapability
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-09-03
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 382814eb3d4322ed52bd39fcb22740201335614e
ms.sourcegitcommit: 1e5a46271bf7fae2f958d2b1b666a8d2583e04a8
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/25/2021
ms.locfileid: "7679005"
---
# <a name="scheduling-with-resource-selection-based-on-capability"></a>Ütemezés képességen alapuló erőforrás-kijelöléssel

[!include [banner](../../includes/banner.md)]

A termelési útvonal műveletéhez szükséges erőforrásigények megadásával megadhatja, hogy mi szükséges a művelet végrehajtásához. Egy művelethez például szükség lehet egy adott erőforrásra vagy erőforráscsoportra, illetve a szakértelem vagy a képességek kombinációjára. Ez a témakör leírja az erőforrás-kiválasztást a korlátlan kapacitásütemezés során, amikor erőforrásigényként adja meg a műveletekhez szükséges erőforrásokat.

## <a name="turn-on-the-capability-based-scheduling-feature"></a>A kapacitásalapú funkció bekapcsolása

A funkció használata előtt be kell azt kapcsolnia saját rendszerében. A rendszergazdák használhatják a [funkciókezelési](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) beállításokat a funkció állapotának ellenőrzéséhez, és bekapcsolásához. A **Funkció kezelése** munkaterületen a funkció a következő módon van listázva:

- **Modul:** *Alaptervezés modul*
- **Funkció neve:** *Végtelen kapacitásütemezés a tervezési optimalizáláshoz*

További tájékoztatás a funkcióval kapcsolatosan: [Ütemezés végtelen kapacitással](infinite-capacity-planning.md).

## <a name="capability-based-scheduling"></a>Képességen alapuló ütemezés

A képesség egy üzemi erőforrás képességét jelenti egy adott tevékenység végrehajtására. Egyetlen műveleti erőforráshoz több képesség is rendelhető, és egy képesség több erőforráshoz is hozzárendelhetők. Bármilyen típusú üzemi erőforráshoz rendelhetők hozzá képességek, például Eszköz, Szállító, Gép, Emberi erőforrások, Hely, illetve Létesítmény.

Ha erőforrásigényként adja meg a lehetőségeket, akkor a rendelések ütemezéséig halaszthatja az erőforrás-foglalást. Ahelyett, hogy konkrét erőforrásokat vagy erőforráscsoportokat rendel egy útvonalművelethez, meghatározhatja az egyes útvonalműveletekkel kapcsolatos képességeket. Ezután az ütemezés során a rendszer megfelelteti a szükséges képességeket az erőforrásokhoz meghatározott képességekhez. A rendszer csak a követelményeknek megfelelő erőforrásokat választja ki.

Ha egy műveleti erőforráshoz szeretne funkciókat hozzárendelni, használja az **Erőforrások** lap **Képességek** gyorslapját. Erőforrások hozzárendeléséhez egy képességhez, használja az **Erőforrások** lap **Erőforrás-képességek** gyorslapját. Mindkét oldal elérhető a **Gyártásvezérlés \> Beállítások \> Erőforrások** a navigációs ablakban. Mindkét gyorslap tartalmaz egy rácsot, amely felsorolja a kiválasztott erőforráshoz vagy képességhez társított erőforrásokat. Mindkét gyorslap egy eszköztárat is tartalmaz, amely a rács sorjainak hozzáadására, eltávolítására és szerkesztésére használható. A rács a következő oszlopokat tartalmazza:

- Az **Erőforrás** vagy **Képesség** – A sor által hozzárendelt erőforrás vagy képesség kiválasztása.
- **Leírás** – Adja meg az erőforrás vagy képesség rövid leírását.
- **Érvényes** – Adja meg az első dátumot, amikor az erőforrás vagy a képesség hozzárendelése érvényes. Az ütemezés során a rendszer nem használ olyan erőforrást vagy képességt, amely lejárt képesség-hozzárendeléssel rendelkezik, még akkor sem, ha az erőforrás egyébként kielégíti a követelményeket.
- **Lejárat** – Adja meg az utolsó dátumot, amikor az erőforrás vagy a képesség hozzárendelése érvényes. Az ütemezés során a rendszer nem használ olyan erőforrást vagy képességt, amely lejárt képesség-hozzárendeléssel rendelkezik, még akkor sem, ha az erőforrás egyébként kielégíti a követelményeket.
- **Szint** – Adja meg annak szintjét, hogy az erőforrásnak szintje szükséges legyen a képességhez. Ezt követően, ha az erőforrásra vagy képességre vonatkozó követelményhez **Minimálisan szükséges szint** értéket ad meg, az ütemezési motor figyelembe veszi az erőforrások kiválasztásakor figyelembe veszi a megfelelőség szintjét. A rendszer ezután csak olyan erőforrásokat választ ki amelyek rendelkeznek a szükséges képességgel, olyan szinten, ami megegyezik, vagy meghaladja a forrás szükségletben meghatározott szintet.
- **Prioritás** – A tervezési optimalizálás még nem támogatja ezt a mezőt. Ha azonban a beépített tervezőmotort használja, akkor az erőforrás vagy a képesség hozzárendelésének **Prioritás** mezőjével határozhatja meg az erőforrás prioritását. Tehát, ha a *Prioritás* van kiválasztva az **Ütemezési paraméterek** oldal **Elsődleges erőforrás kiválasztás**, mezőben, akkor a rendszer először legmagasabb prioritású erőforrást választja ki (tehát a **Prioritás** mezőben a legalacsonyabb számértékű) kerül kiválasztásra az ütemezéshez.

## <a name="example"></a>Példa

A példa azt mutatja be, hogyan választja ki az ütemezési motor az erőforrásokat a képességek alapján.

A termelési útvonalnak öt művelete van: *10*, *20*, *30*, *40*, és *50*. Minden útvonalművelethez különböző erőforrásokra van szükség. Például a *10*-es útvonalművelethez olyan erőforrás szükséges, amely képes hangszóró összeszerelésére (*0050 Spkr Assembly*) és képes a famunkára (*1010 famegmunkálási képességek*). Az *50*-es útvonalművelet olyan erőforrást igényel, amely képes termék csomagolására (*0070 Csomagolási képesség*).

![Képességen használata ütemezéshez.](media/capability-based-scheduling.png "Képességen használata ütemezéshez.")

Az ütemezés során a motor olyan erőforrásokat keres, amelyek megfelelnek a művelet követelményeinek. Az ütemezési motor például a *10*-es művelet végrehajtásához a *00101* erőforrást választja ki, mivel ez az erőforrás az első olyan erőforrás, amely mindkét szükséges képességgel rendelkezik. Az ütemezési motor az *50*-es művelet végrehajtásához a *00301* erőforrást választja ki, mivel ez az erőforrás az egyetlen erőforrás, amely rendelkezik a csomagolás képességgel.

Ezután vegye figyelembe, hogy milyen hatással van ez erre a példára a szakértelemszintek használata közben:

- A *10*-es művelet minimum *7*-es szakértelemszint szükséges a *0059 összeszerelés* képesség.
- A *00101* erőforrás képességszintje *5* a *0059 összeszerelés* képességhez.
- A *00102* erőforrás képességszintje *10* a *0059 összeszerelés* képességhez.

Ebben az esetben a végtelen kapacitásütemezés során az ütemezési motor a *10*-es művelet végrehajtásához a *00102*-es erőforrást választja ki, mivel ez az erőforrás a *00101*-es erőforrással ellentétben rendelkezik a képességhez szükséges képességszinttel.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
