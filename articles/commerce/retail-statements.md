---
title: Kiskereskedelmi kimutatások
description: Ez a témakör a kimutatások létrehozási és feladási módszerét ismerteti.
author: ashishmsft
ms.date: 04/04/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailParameters
audience: Application User
ms.reviewer: josaw
ms.custom: 85183
ms.assetid: df9c62a2-6f13-4a08-bdca-07d041172c1b
ms.search.region: Global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: Retail July 2017 update
ms.openlocfilehash: 0717c1198171f411e3c52233200ecfcc213dc13f
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8878457"
---
# <a name="retail-statements"></a>Kiskereskedelmi kimutatások

[!include [banner](includes/banner.md)]

A Dynamics 365 Commerce programban a kimutatások feladásával számolhatók el azok a tranzakciók, amelyek a felhőalapú pénztárban (POS) vagy a Modern POS rendszerű pénztárban (MPOS) jönnek létre. A kimutatás feladási folyamatában az elosztási ütemezés lekérés a POS-tranzakciók a központ (HQ) ügyfél történő sorozatát használja. A **Kereskedelmi paraméterek** és **Üzletek** lapokon megadott paraméterek segítségével egyedi kimutatásokba húzott tranzakciók választhatók ki.

A következő ábra bemutatja a kimutatás feladási folyamatot: Ebben a folyamatban a rögzített tranzakciók a pénztárnál továbbításra kerülnek a vevőnek a Commerce ütemező segítségével. Miután a vevő megkapta a tranzakciókat, létrehozhatja, számíthatja, és feladhatja a tranzakció kimutatást az üzlet számára.

[![Kimutatás feladási folyamata.](./media/retail-statements.png)](./media/retail-statements.png)

## <a name="creating-and-posting-statements"></a>Kimutatások létrehozása és feladása

Kimutatást létrehozhat manuálisan vagy a kötegelt folyamatok használatával, amelyeket úgy állít be, hogy időszakosan fussanak a nap folyamán. Mindkét esetben a következő lépések segítségével hozhat létre és adhat fel kimutatásokat.

### <a name="create-the-statement"></a>A kimutatás létrehozása.

Ez a lépés azonosítja az üzletet, amelyhez a kimutatás manuálisan jön létre. Kötegfeldolgozás konfigurálásakor, automatikusan létrehozhat kimutatásokat minden üzlethez, a meghatározott ütemezést alapján.

### <a name="calculate-the-statement"></a>A kimutatás számítása

Ebben a lépésben a tranzakció sorai vannak kijelölve az egyes üzletekhez meghatározott feltételek alapján a **Kereskedelmi paraméterek** és **Üzletek** képernyőkben. Ezeken az oldalakon határozza meg a feltételeket, majd adja meg, hogyan történik a tranzakciók számítása. A kimutatás számítása előtt a kimutatásban szereplő tranzakciók listájának megtekintéséhez használja a **Tranzakciók** képernyőt.

A kimutatásszámítás fizetőeszköz-elszámolásokat használ a pénztárgépekről a leszámolt összegként. Másik lehetőségként manuálisan is meg lehet adni a leszámolt összeget. A kimutatás megmutatja a különbséget az értékesítés összege között a tranzakciókhoz és a fizetési módok ténylegesen leszámlált összege között. A kimutatás feladására csak akkor kerül sor, ha ez a különbözet kevesebb mint az üzlethez meghatározott maximális feladási különbség.

> [!NOTE]
> A kimutatás számítási folyamat a globális számsorozatot használja.

Amikor kimutatást számít, akkor a számítás a következő feladatokból áll:

- Tranzakciók, amelyek nem szerepeltek az előző kimutatásszámításban, a kiválasztott dátumtartományban.
- A teljes olyan összegek kiszámítása, amelyek a kijelölt tranzakciókban lettek ajánlatba véve. Az eredmények láthatók a kimutatási sorokon a kimutatás módszerétől függően:

    - Ha a kimutatás módszere az **Összesen**, egy sor jön létre minden egyes fizetési módszerhez a kiválasztott tranzakciókban.
    - Ha a kimutatás módszere **Személyzet**, egy sor jön létre minden egyes fizetési módszerhez a a kijelölt munkatárs által végrehajtott tranzakciókban.
    - Ha a kimutatás módszere **POS terminál**, egy sor jön létre minden egyes fizetési módszerhez a kijelölt jegyzéken végrehajtott tranzakciókban.
    - Ha a kimutatás módszere **Műszak** egy sor jön létre minden egyes fizetési módszerhez a kijelölt jegyzéken végrehajtott tranzakciókban egy műszak alatt.

Ha a **kimutatás szerinti bontás módszere** jelölőnégyzet be van jelölve a **üzletek** lapon külön kimutatást alapján jön létre a kiválasztott érték a **kimutatás módszere** mező.

Ha az üzlet munkaideje meghaladta az éjfelet, a kimutatásokat a munkanap vége szerint adjon fel, ahelyett, hogy a naptári nap vége szerint tenné.

Az **Üzletek** képernyőn a **Kimutatás/zárás** gyorslapon, a **Munkanap vége** mezőbe írja be az időt, amikor az utolsó tranzakciónak szerepelnie kell a munkanap kimutatásában. Jelölje be a **Feladás munkanapként** jelölőnégyzetet az ugyanazon a munkanapon feladni kívánt tranzakciókhoz. A kimutatás feladásakor az ugyanazon a munkanapon belül rögzített tranzakciók szerepelhetnek ugyanabban az értékesítési rendelésben, akkor is, ha éjfél előtt vagy éjfél után következnek be egyes tranzakciók.

#### <a name="example-post-a-statement-for-a-business-day-that-extends-over-two-calendar-days"></a>Példa:, Kimutatás feladása munkanaphoz, amely meghalad két naptári napot

Üzlet meg nyitva, 8:00 óra között 3:00 óra, és a **feladás munkanapként** jelölőnégyzet be van jelölve, az áruház-konfigurációban. Az üzlet május 31-én 8:00 óra, és éjfél közötti tranzakcióit tartja nyilván. Az üzlet is 12 óra 1 és 3:00 óra június 1-jén közötti tranzakcióit tartja nyilván.

Ha az üzlet feladja a kivonatot a a munkanap lezárásához, egy értékesítési rendelés generálódik, amely tartalmazza az összes tranzakciót, amely reggel 8:00 óra és hajnali 3:00 óra között került rögzítésre, annak ellenére, hogy a tranzakciók két napon, május 31-én és június 1-jén történtek.

Ha ugyanannál az üzletnél a **Feladás munkanapként** jelölőnégyzet nincs bejelölve, külön értékesítési rendelések jönnek létre, amikor az üzlet feladja az a munkanap zárása kivonatot. Egy értékesítési rendelés tartalmazza a tranzakciókat, amelyek május 31-én reggel 8 óra és éjfél között kerültek nyilvántartásra és a második értékesítési rendelés tartalmazza a tranzakciókat, amelyek június 1-jén 12 óra 1 perc és hajnali 3 óra között lettek nyilvántartva.

> [!NOTE]
> Kimutatások létrehozása előtt zárja le a műszakokat a kimutatás időszakában.

### <a name="post-the-statement"></a>A kimutatás feladása

A kimutatás feladásakor értékesítési rendelések és számlák jönnek létre az értékesítés kimutatásban.

- Készpénz és átviteli értékesítés berakodása egy értékesítési rendelésre történik, és számlázása az alapértelmezett vevőhöz történik, akit a rendszer az üzlethez társított.
- Értékesítések, amelyeknél egy vevőt adtak a pénztári tranzakcióhoz, külön értékesítési rendeléseket és számlákat hoznak létre az egyes egyedi vevőkhöz.

Kifizetési naplók automatikusan létrejönnek a fizetési kimutatásban, és a készlet úgy frissül, ahogy a POS üzlet.


[!INCLUDE[footer-include](../includes/footer-banner.md)]