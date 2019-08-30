---
title: Eszköztípusok
description: Ez a témakör bemutatja, hogyan lehet eszköztípusokat létrehozni az Eszközkezelés modulban. Leírja az eszköztípusokhoz kapcsolódó elemeket is.
author: josaw1
manager: AnnBe
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 288dac77f9d999012ec930ef2bca5c0921c2955f
ms.sourcegitcommit: 747bcd25ce7c6c20ce9eaa0027e730f74d4fd6aa
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/23/2019
ms.locfileid: "1783326"
---
# <a name="asset-types"></a>Eszköztípusok

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

Ez a témakör az eszköztípusok létrehozásának lépéseit mutatja be. Leírja az eszköztípusokhoz kapcsolódó elemeket is. Az eszköztípusokat az eszközök általános kategóriaként használják. Ilyenek például a CNC-gépek, mérőműszerek és teherautó-motorok. Az eszköztípusok a feladattípusok (karbantartási feladatok), az eszközök életciklus-állapotainak, az eszközmérések, az eszközattribútumok, az állapotértékelési sablonok és az eszközhöz választható eszközmodellek kezelésére szolgálnak. Az eszköz létrehozásakor meg kell adnia az eszköz típusát.

Minden eszköztípushoz az eszköztípus-beállítások különböző változatait lehet létrehozni. Például a **Teherautók** nevű eszköztípushoz létre lehet hozni különböző eszköztípus-változatokat a különböző eszközgyártókhoz és eszközmodellekhez. Az egyes eszköztípus-beállításokhoz hozzáadhatja a szükséges pótalkaltrészeket és karbantartási terveket.

Először be kell állítani a szükséges eszközök típusát. Ezután hozza létre azokat az eszközmodelleket, amelyek az eszköztípusokhoz kapcsolódnak. Végül az **Eszköztípus alapértelmezései** lapon a berendezéshez szükséges eszköztípusok valamennyi változatát létre kell hozni.

## <a name="create-an-asset-type"></a>Eszköztípus létrehozása

1. Válassza ki az **Eszközkezelés** \> **Beállítás** \> **Eszköztípusok** \> **Eszköztípusok** lehetőséget.
2. Válassza az **Új** lehetőséget az eszköztípus létrehozásához.
3. Az **Eszköztípus** mezőben adjon meg egy eszköztípus-azonosítót.
4. A **Név** mezőben adjon meg egy nevet.
5. Az **Eszköz életciklusmodellje** mezőben válasszon ki egy eszköz-életciklusmodellt. Ha további tájékoztatást szeretne az eszközök életciklus-állapotaival és életciklusmodelljeivel kapcsolatban, tekintse meg az [Eszközök életciklus-állapotai](object-stages.md) részt.
6. Állítsa az **Összesen** beállítást **Igen** értékre, ha szeretné, hogy az adott eszköztípusokkal rendelkező eszközökhöz a rendszer összesített fő teljesítménymutató-értékeket (KPI) számítson ki.
7. Válassza a **Mentés** lehetőséget.
8. A **Feladattípusok** gyorslapon válassza ki azokat a feladattípusokat, amelyek az adott eszköztípushoz kapcsolódnak:

    - A feladattípus kiválasztásához válassza ki a **Fennmaradó feladattípusok** mezőben, majd kattintson a jobbra mutató nyílra ![Jobbra mutató nyíl](media/29-setup-for-objects.png), és mozgassa a **Kiválasztott feladattípusok** szakaszba.
    - Az összes rendelkezésre álló feladattípus kiválasztásához válassza az ![Összes átirányítása nyíl](media/30-setup-for-objects.png) gombot. A program minden feladattípust a **Fennmaradó feladattípusok** mezőből átvisz a **Kválasztott feladattípusok** mezőbe.
    - A feladattípus kiválasztásának visszavonásához válassza ki a **Kiválasztott feladattípusok** mezőben, majd kattintson a balra mutató nyílra ![Balra mutató nyíl](media/31-setup-for-objects.png), és mozgassa a **Fennmaradó feladattípusok** szakaszba.

9. Ezután kiválaszthatja azokat az eszközmértékeket, amelyek az eszköztípushoz kapcsolódnak. Az **Eszközmértékek** gyorslapon végezze el a kívánt beállításokat a 8. lépésben a feladattípusoknál leírt módszerekkel. Az eszközmértékek beállításával kapcsolatos további információkért tekintse meg a [Karbantartás alatt álló eszköz mérései](counters.md) részt.
10. Ezután kiválaszthatja azokat az attribútumtípusokat, amelyek az eszköztípushoz kapcsolódnak. Az **Attribútumtípusok** gyorslapon végezze el a kívánt beállításokat a 8. lépésben a feladattípusoknál leírt módszerekkel. Ezután az attribútumtípusok preferált sorrendjének létrehozásához válasszon ki egy attribútumtípust a **Kiválasztott attribútumtípusok** mezőből, majd a fel és a le nyílgombokkal helyezze át. Az attribútumtípusok sorrendje az ilyen eszköztípust használó eszközöknél jelenik meg. Az eszközattribútumokról bővebben lásd: [Karbantartási attribútumtípusok](../setup-for-functional-locations/specification-types.md).

    > [!NOTE]
    > Amikor új attribútum-típusokat ad hozzá az **Attribútumtípusok** gyorslaphoz, a program automatikusan frissíti a meglévő eszközöket a megadott adatokkal.

11. Ezután kiválaszthatja azokat az állapotértékelési sablonokat, amelyek az eszköztípushoz kapcsolódnak. Az **Állapotértékelések** gyorslapon végezze el a kívánt beállításokat a 8. lépésben a feladattípusoknál leírt módszerekkel. Az állaportértékelési sablonokkal és regisztrációval kapcsolatos további tudnivalókat lásd: [Állapotértékelés](../setup-for-objects/condition-assessment.md).
12. Az **Eszközmodell** gyorslap a kiválasztott eszköztípuson beállított összes eszközgyártó és-modell kombinációját jeleníti meg. Ha a kombinációkat gyártó szerint szeretné megtekinteni, válassza az **Eszközmodell** lehetőséget az **Eszközmodell** oldal megnyitásához.

    Az **Eszközmodell** oldalon hozzáadhat eszközmodell-eszköztípus kapcsolatokat. Ezenkívül az **Eszköztípusok** oldalon az eszközgyártó-eszközmodell kapcsolatok közvetlenül is hozzáadhatók egy eszköz típusához. Végül az **Eszközmodell** oldalon (**Eszközkezelés** \> **Beállítás** \> **Eszközök** \> **Eszközmodell**) új eszközgyártó-eszközmodell-eszköztípus kapcsolatokat hozhat létre. Így három mód van az eszközgyártó-eszközmodell-eszköztípus kapcsolatok beállítására és szerkesztésére. Az összes elérhető kombináció különböző szempontokból látható, és a beállítással való munka során kiválaszthatja a kívánt belépési pontját.

> [!NOTE]
> - Ha meghatároz eszközmértéket egy eszköztípuson, akkor a kiválasztás automatikusan frissül az **Eszközmértékek** oldalon (**Eszközkezelés** \> **Beállítás** \> **Eszközök** \> **Eszköztípusok** \> **Eszközmértékek**).
> - Az **Általános** gyorslap **részletek** szakaszának mezői a kiválasztott eszköztípushoz beállított feladattípusokat, eszközmértékeket, attribútumokat stb. jelenítik meg.

A manuálisan létrehozott munkarendelések általában a hibaelhárító karbantartással kapcsolatosak, míg az automatikusan létrejövő munkarendelések a megelőző karbantartáshoz kapcsolódnak. A munkarendelések manuális létrehozásakor csak az **Eszköztípusok** oldal **Feladattípusok** gyorslapján kiválasztott feladattípusok használhatók. Az automatikusan létrehozott munkarendelések azonban a **Feladattípusok** oldalon létrehozott összes feladattípust használhatják (**Eszközkezelés** \> **Beállítás** \> **Feladatok** \> **Feladattípusok**).

## <a name="create-asset-type-setup-lines"></a>Eszköztípus-beállítási sorok létrehozása

1. Válassza ki az **Eszközkezelés** \> **Beállítás** \> **Eszközök** \> **Eszköztípusok** \> **Eszköztípus beállítása** lehetőséget. Másik lehetőségként válassza az **Eszközkezelés** \> **Beállítás** \> **Eszközök** \> **Eszköztípusok** \> **Eszköztípusok** lehetőséget, válasszon egy eszköztípust, majd az **Eszköztípus beállítása** elemet.
2. Amikor első alkalommal használja az **Eszköztípus beállítása** oldalt, hasznosnak találhatja a **Kombinációk létrehozása** gombot. Ezzel gombbal gyorsan létrehozhatja egy eszközmodell összes kombinációját egy eszköztípuson. Válassza a **Kombinációk létrehozása** elemet, válassza az eszköztípust, amelyhez kombinációkat szeretne létrehozni, majd az **Ok** gombot.

    > [!NOTE]
    > Ha nem fogja az összes automatikusan létrejött eszköztípus-beállítási kombinációt használni, törölheti a beállítást úgy, ha kiválasztja, majd a **Törlés** parancsra kattint.

3. Válassza az **Új** lehetőséget az eszköztípus beállításának manuális létrehozásához.
4. Attól függően, hogy az eszköztípus beállításának mennyire kell specifikusnak lennie, válassza ki a megfelelő lehetőséget az **Eszköztípus**, **Gyártó** és **Modell** mezőkben.
5. Ha egy jótállási megállapodás kapcsolódik az eszköztípushoz, válassza ki a szerződést a **Szállítói garancia** és a **Vevői garancia** mezőben. 
6. A **Pótalkatrészek** gyorslapon válassza a **Hozzáadás** lehetőséget, ha pótalkatrészeket szeretne hozzáadni a kiválasztott eszköztípus beállításához.
7. A pótalkatrész jóváhagyásához válassza ki a pótalkatrész sorát, majd válassza a **jóváhagyás** parancsot. A jóváhagyáshoz több sort is kiválaszthat.
8. Ha látni szeretné, hogy egy pótalkatrész használatban van-e máshol az Eszközkezelésben (például eszközökkel és munkarendelésekkel kapcsolatban), válassza ki a pótalkatrész sorát, majd a **Cikket hol használják** elem kiválasztásával megnyithatja a **Cikket hol használják** oldalt. A listában szereplő összes aktív pótalkatrész megjelenítéséhez jelölje be az **Aktív** jelölőnégyzetet. Ha csak a jóváhagyott pótalkatrészeket szeretné megjeleníteni, jelölje be a **Jóváhagyva** jelölőnégyzetet.
9. A **Karbantartási tervek** gyorslapon válassza a **Hozzáadás** lehetőséget, ha karbantartási terveket szeretne hozzáadni a kiválasztott eszköztípus beállításához.
10. Ha egy eszköztípus beállítását át szeretné másolni egy másik beállításba, akkor használhatja a Másolás funkciót. Válassza ki az eszköztípus-beállítást, ahova másolni szeretné a beállítást, majd a **Beállítás másolása** lehetőséget, majd válassza ki az eszköztípus-beállítást, ahonnan másolni szeretné a beállítást. A különböző lehetőségek beállításai határozzák meg, hogy mennyi adat szerepel. Ha befejezte, válassza az **Ok** lehetőséget a beállítás másolásához.

> [!NOTE]
> Ha sok olyan pótalkatrész-sorral és karbantartási tervvel rendelkezik, amelyet újra fog hasznosítani, akkor a Másolás funkcióval gyorsan és egyszerűen beállíthatja az adatokat számos eszköztípus-beállítási kombinációhoz.

## <a name="spare-parts-on-the-asset-type-setup"></a>Pótalkatrészek az eszköztípus beállításain

Az „Eszköztípus-beállítási sorok létrehozása” szakaszban leírtaknak megfelelően a pótalkatrészeket az eszközmodellekhez az **Eszköztípus beállítása** oldalon állíthat be. Így amikor megnyitja az **Eszköztípus beállítása** oldalt, akkor csak az adott eszköztípus-eszközgyártó-eszközmodell kombinációhoz kapcsolódó pótalkatrészeket látja. Ha a pótalkatrész-rekordok teljes listáját szeretné látni, nyissa meg a **Pótalkatrészek** oldalt (**Eszközkezelés** \> **Lekérdezések** \> **Pótalkatrészek**).

A **Pótalkatrészek** lapon új pótalkatrészeket is létrehozhat a meglévő eszköztípus-eszközgyártó-eszközmodell kombinációkhoz. Eldöntheti, hogy a pótalkatrész-rekodokat az **Eszköztípus beállítása** oldalon vagy a **Pótalkatrészek** oldalon kívánja létrehozni. Az **Eszköztípus beállítása** oldalon a kiválasztott eszköztípus-eszközgyártó-eszközmodell kombinációjára vonatkozó áttekintő adatok találhatók, míg a **Pótalkatrészek** oldalon teljes áttekintést láthat az összes eszköztípus-beállítási sorról. Ha a **Pótalkatrészek** lap túl sok rekordot tartalmaz, akkor az **Eszköztípus beállítása** oldalon jobb áttekintést kaphat.

Ha látni szeretné, hogy a kiválasztott sorban szereplő pótalkatrész használatban van-e bárhol az Eszközkezelésben (például eszközökkel és munkarendelésekkel kapcsolatban), válassza ki a **Cikket hol használják** elemet, amellyel megnyithatja a **Cikket hol használják** oldalt. 
