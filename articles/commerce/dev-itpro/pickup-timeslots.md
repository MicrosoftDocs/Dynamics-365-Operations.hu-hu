---
title: Vevői átvételi időközök létrehozása és frissítése
description: Ez a témakör azt mutatja be, hogyan lehet a Commerce központban létrehozni, konfigurálni és frissíteni a vevői átvételi időközöket.
author: anupamar-ms
manager: AnnBe
ms.date: 01/05/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rapraj
ms.search.validFrom: 2020-09-20
ms.dyn365.ops.version: Retail 10.0.15 update
ms.openlocfilehash: 125696e8f32c2452a572a2316f512779f399f5c4
ms.sourcegitcommit: 8b4cb7b6ad4aab37566bcc91e426bd56db771416
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/06/2021
ms.locfileid: "4828211"
---
# <a name="create-and-update-time-slots-for-customer-pickup"></a>Vevői átvételi időközök létrehozása és frissítése

[!include [banner](../../includes/banner.md)]

Ez a témakör azt mutatja be, hogyan lehet a Commerce központban létrehozni, konfigurálni és frissíteni a vevői átvételi időközöket.

Az időköz funkció lehetővé teszi a kiskereskedők számára, hogy meghatározzák az időközt azon cikkek számára, amelyeknél be van kapcsolva a vevői átvétel kézbesítési mód. Az időközök segítségével a kiskereskedők határozzák meg azokat a napokat és időpontokat, amikor a megrendeléseket át lehet venni egy üzletből. A kiskereskedők azt is meghatározhatják, hogy hány rendelést lehet felvenni egy adott időszakban. Ily módon a kiskereskedők korlátozhatják az adott napon és egy adott időpontban átvehető megrendelések számát. Az eredmény egy jobb minőségű élményt az ügyfelek számára.

> [!NOTE]
> Az időköz funkció a Microsoft Dynamics 365 Commerce 10.0.15-ös és újabb verziójában érhető el.

A következő ábra egy példát mutat be az e-kereskedelmi fizetés során az időköz kiválasztására.

![Példa az időköz kiválasztására az e-kereskedelmi fizetés során](../dev-itpro/media/Curbside_timeslot_eCommerce.PNG)

## <a name="time-slot-properties"></a>Időköz tulajdonságai

Az időköz egy meghatározott intervallum, amikor az ügyfél választhat, hogy egy adott üzletből vagy helyről vesz fel rendelést. Az időközkezelési funkció csak akkor érhető el, ha az ügyfél felvételi szállítási módja a Dynamics 365 Commerce szolgáltatásban konfigurálva van.

Az időköz a következő tulajdonságok használatával van definiálva:

- **Szállítási mód** – Adja meg azt a szállítási módot, amelyre az időköz vonatkozik.
- **Minimális napok** és **Maximum napok** – Adja meg a legkorábbi és legkésőbbi dátumokat, amelyek a rendelés leadásának dátumához viszonyítva kiválaszthatók. 

    A **Minimális napok** tulajdonság biztosítja, hogy elegendő idő álljon a kiskereskedő számára a rendelés feldolgozására, mielőtt készen állna a felvételre. A **Maximális napok** tulajdonság biztosítja, hogy a felhasználó ne választhasson ki olyan dátumot, amely túl messze van a jövőben. Ha például a minimális érték **1**, és a megrendelést szeptember 20-án adják le, a legkorábbi nap, amikor a rendelés elérhető lesz a felvételhez, a következő jogosult nap (szeptember 21.). Hasonlóképpen, a maximális érték beállításával megadhatja, hogy a rendelés legfeljebb hány napig vehető át. Ha a minimális és maximális értékek meg vannak határozva, a webhely felhasználói csak egy meghatározott napokat láthatják és választhatják ki a fizetés során.

    A minimális értéket 1-nél kisebb decimális értékre is állíthatja. Ha például a felvétel a megrendelés elküldése után négy órával elérhető, állítsa a minimális értéket **0,17**-re (= 4 ÷ 24, két tizedesjegyre kerekítve). Ha azonban a minimális értéket 1-nél nagyobb decimális értékre állítja, a rendszer mindig a legközelebbi egész számra (felfelé) kerekíti. Például egy **1,2**-es érték **2**-re lesz felkerekítve. Hasonlóképpen ha a maximális értéket decimális értékre állítja, a rendszer mindig a legközelebbi egész számra (felfelé) kerekíti. 

- **Kezdő dátum** és **záró dátum** – adja meg az idősáv kezdő és záró dátumát. Minden időközbejegyzés rendelkezik kezdő dátummal és záró dátummal. Éppen ezért rugalmasan lehet a különböző időpontokat felvenni az egész év folyamán (például felvétel munkaszüneti órákban). Ha egy rendelés elküldése után változik egy időköz kezdete és dátumai, akkor a módosítások nem vonatkoznak erre a rendelésre. A kezdő és záró dátumok megadásakor figyelembe kell venni a szünnapok dátumát (például karácsony napja), és gondoskodniuk kell arról, hogy az időközök ne legyenek meghatározva az adott napok esetében.
- **Aktív felvételi órák** – adja meg azt az időszakot, amikor a felvétel engedélyezve van. Például a felvételi idők naponta délután 2 és 5 óra között lehetnek. Ez a tulajdonság azt teszi lehetővé, hogy a felvételi idők függetlenek legyenek a nyitvatartási időtől. Ennélfogva a kiskereskedő beállíthat olyan átvételi időpontokat, amelyek megfelelnek a megadott üzleti követelményeknek. Amikor meghatározza az aktív felvételi órákat, figyelembe kell vennie a nyitvatartás idejét, és biztosítania kell, hogy a felvételi idők ne legyenek beállítva, amikor az üzlet zárva van.

    > [!NOTE]
    > Az üzleti felvétel idejét a megfelelő üzlet időzónájában kell megadni.

- **Időköz intervalluma** – Adja meg az időtartamot, amely az egyes időpontokhoz hozzárendelhető. Például az egyes időközök hossza 15 perc, 30 perc vagy egy óra lehet. Ha az időköz értéke 0, akkor az időköz a kezdési és a záró időpont közötti teljes időtartamra rendelkezésre áll.
- **Időközök intervallumonként** – adja meg, hogy hány vevő vagy rendelés szolgálható ki az egyes időköz-intervallumokban. Például megadhatja az **1**, **2**, **3**, vagy bármely más egész szám értékét.
- **Aktív napok** – adja meg a hét azon napjait, amikor a felvételi időközök aktívak. Ez a tulajdonság azt teszi lehetővé, hogy a kiskereskedő határozza meg azokat a napokat, amikor a felvételi rendeléseket támogatni szeretné.
- **Kiskereskedelmi csatornák** – adja meg a kiskereskedelmi csatornákat. Minden időközt egy vagy több kiskereskedelmi üzlethez kapcsolható. Az egyes üzletek nyitvatartási idejétől függően egy vagy több időközbejegyzést lehet létrehozni és társítani a csatornához. 

<!-- ![HQ Timeslot overview](../dev-itpro/media/Curbside_timeslot_Settings_overview.PNG) -->

Csatornánként csak egy időközsablon konfigurálható. Ilyen csatornák a fizikai üzlethelyiségek, a telefonos ügyfélszolgálatok, a mobileszközök és az elektronikus kereskedelmi webhelyek.

## <a name="configure-the-time-slot-feature-in-commerce-headquarters"></a>A Commerce központ időköz funkciójának konfigurálása

A Commerce Központ alkalmazásban minden egyes szállítási mód esetében meg kell adni az időközöket, hogy a pénztár (POS) és az e-kereskedelmi csatornák hivatkozhassanak rájuk.

- Minden üzlethez vagy csatornához csak egy időközsablon tartozhat.
- Minden létrehozott időköznek egyedinek kell lennie az egyes szállítási módokhoz az egyes sablonokban.
- Az időköz funkció konfigurálása után az időköznaptár elérhetővé válik a kiválasztott áruházak vagy üzletcsoportok számára. Hivatkozásként a pénztárban is látható lesz.

A Commerce központ időköz funkciójának konfigurálásához kövesse az alábbi lépéseket.

1. Nyissa meg a **Commerce** \> **Csatornabeállítás** \> **Üzleti felvételi időköz** pontot.
1. Válassza az **Új** lehetőséget egy új időközsablon létrehozásához. Meglévő sablon használatához válassza ki a sablont a bal oldali ablaktáblán.
1. Adjon meg értékeket a **Időköz azonosítója** és a **Leírás** mezőkben.
1. A **Rendelés felvételi idejének beállításai** gyorslapon válassza a **Hozzáadás** elemet.
1. A **Rendelés felvételi idejének beállításai** párbeszédpanelen határozza meg a dátumtartományt, a szállítási módot, a szállítás aktív idejét, az aktív napokat, az időköz intervallumát, az időközök számát intervallumonként és más beállításokat.

    Ha a belátható jövőben az időközök statikusak lesznek, állítsa a **Záró dátum** mezőt **Soha** értékre.

    > [!NOTE]
    > Több sablon is létrehozható, de egyetlen csatornához vagy üzlethez csak egy sablon tartozhat.

    ![Rendelés felvételi idejének beállításai párbeszédpanel](../dev-itpro/media/Curbside_timeslot_Settings_Page.PNG)

1. Amikor elkészült, válassza az **OK** elemet.
1. Ha egy napon belül az időközök eltérnek, hozzon létre további bejegyzéseket a **Rendelés felvételi idejének beállításai** gyorslapon, hogy biztosítsa, a dátumok és időpontok ne legyenek átfedésben.
1. A **kiskereskedelmi csatornák** gyorslapon válassza a **Hozzáadás** lehetőséget, hogy az időközsablont társítsa az üzletekhez vagy csatornákhoz, ahol használni fogja azokat.
1. A **Szervezeti csomópontok kiválasztása** párbeszédpanelen a nyílgombok segítségével válassza ki azokat az üzleteket, régiókat és szervezeteket (vagy törölje azok kiválasztását), amelyekkel a sablont társítani szeretné.

    <!-- ![HQ Timeslot overview](../dev-itpro/media/Curbside_timeslot_Settings_overview.PNG) -->

1. Amikor elkészült, válassza az **OK** elemet.
1. Az **Elosztási ütemezés** lapon, futtassa a **1070** és **1135** feladatokat az adatok szinkronizálásához a csatornával.

## <a name="time-slot-selection-for-pos-orders"></a>Időköz kiválasztása pénztári rendelésekhez

A pénztárnál, amikor egy rendelés vagy rendelési sor felvételre van meghatározva, a pénztáros kiválaszthatja a felvételi üzletet vagy a helyet, valamint a dátumot és időközt. Ha egy vevőnek egy másik üzletben felvehető rendelése van, akkor a pénztáros kiválaszthatja azokat a dátumokat, amikor a rendelés felvehetővé válik abban az üzletben. Az üzletkeresésben megjelennek a dátumok és a nyitvatartási idők.

A következő ábra egy példát mutat be a pénztári rendelés során az időköz kiválasztására.

![Példa egy pénztári rendelés időköz-kiválasztására](../dev-itpro/media/Curbside_timeslot_POS.png)

## <a name="time-slot-selection-for-e-commerce-orders"></a>Időköz kiválasztása e-kereskedelmi rendelésekhez

Az időközök e-kereskedelmi rendelésekhez való kiválasztásával kapcsolatos további információkért lásd: [Átvételi információk modul](../pickup-info-module.md).

> [!NOTE]
> A felhasználók megtekinthetik vagy szerkeszthetik az átvételi időközöket a Commerce webhely fizetési oldalán csak akkor, ha az átvételi információk modult hozzáadták ahhoz az oldalhoz. Ha a fizetési oldal nem tartalmazza az átvételi információk modult, akkor a rendelések anélkül kerülnek elküldésre, hogy a felhasználók megadhatnák vagy megtekinthetnék az időközökkel kapcsolatos információkat.

A következő ábra példát mutat be egy e-kereskedelmi rendelésre, amelynél a felvételi időköz ki van kiválasztva.

![Példa egy e-kereskedelmi rendelésre, amelynél a felvételi időköz ki van kiválasztva](../dev-itpro/media/Curbside_timeslot_eCommerce_checkoutsummary.PNG)

## <a name="time-slot-selection-for-call-center-orders"></a>Időköz kiválasztása hívásközponti rendelésekhez

A hívásközponti alkalmazásban a hívásközponti ügynökök kiválaszthatják az átvételi áruházat vagy helyet, valamint a dátumot és az időt is, amint azt az alábbi ábra is mutatja.

![Példa hívásközponti rendelésre, amelynél a felvételi időköz ki van kiválasztva](../dev-itpro/media/Curbside_timeslot_callcenter.png)

## <a name="additional-resources"></a>További erőforrások

[Átvételi információk modul](../pickup-info-module.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]