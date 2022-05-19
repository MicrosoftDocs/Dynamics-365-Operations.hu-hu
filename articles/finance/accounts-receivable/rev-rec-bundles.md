---
title: Bevételelszámolási csomagok
description: Ez a témakör a kinnlevőségek bevételelszámolási funkciójában elérhető csomagok működését mutatja be. A csomag egy szülőcikkből és több összetevő cikkből áll.
author: kweekley
ms.date: 01/04/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2021-01-04
ms.dyn365.ops.version: 10.0.7
ms.openlocfilehash: 62a4d7f36ad0b36edeaec75e9b670e2aad143703
ms.sourcegitcommit: 631d2cea52590af15f208e9af584446e85540fcf
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/07/2022
ms.locfileid: "8725819"
---
# <a name="revenue-recognition-bundles"></a>Bevételelszámolási csomagok

[!include [banner](../includes/banner.md)]

Ez a témakör a kinnlevőségek bevételelszámolási funkciójában elérhető csomagok működését mutatja be. A csomag egy szülőcikkből és több összetevő cikkből áll. A szülőcikket a hatékonyabb rendelésbevitel érdekében az értékesítési rendelésnél kell megadni. A szülőcikk később összetevő cikkekre bontható. A belső dokumentumok, például a szállítólevél felsorolja az összetevő cikkeket. A külső dokumentumokban azonban csak a szülőcikk fog szerepelni.

> [!NOTE]
> A Microsoft Dynamics 365 Commerce csatornái, például az online csatornák, a pénztár és hívásközpontok nem támogatják a bevételelszámolást (és így a csomagfunkciót sem). Ide tartozik a Dynamics 365 Supply Chain Management és a Dynamics 365 Sales szolgáltatásokban elérhető A potenciális vevők készpénzre váltása megoldás is. A bevételelszámolás használatára konfigurált cikkeket nem szabad hozzáadni a Commerce Channels rendszerben vagy a Potenciális vevők készpénzre váltása megoldásban létrehozott rendelésekhez és tranzakciókhoz.

A csomagok beállításhoz meg kell adni a bevételelszámolási konfigurációs kulcsait. A csomagokat azonban akkor is használhatja, ha nincs beállítva a bevételelszámolás. Hasonlóképpen akkor is használhat bevételelszámolást, ha a csomagok nincsenek beállítva. Ha beállította a bevételelszámolást, az összetevő cikkek határozzák meg az értékesítési rendelés számlázásakor a bevételelszámoláshez vagy -halasztásához használt bevételi árat és a bevételütemezést.

A csomagok beállítása a darabjegyzék funkciót használja. A csomagcikkek beállításához kapcsolódó további információkért lásd: [bevételelszámolás beállítása](revenue-recognition-setup.md). Ha a szülőcikk csomagként van megjelölve, a rendszer másképp kezeli, mint az anyagjegyzék többi cikkét. Alább felsoroltuk a főbb eltéréseket:

- A csomagokat az értékesítési rendelés visszaigazolásával kell kibontani. Ehhez válassza az **Értékesítési rendelések megerősítése** lehetőséget a Műveletpanel **Eladás** lapján, amelyet az értékesítési rendelés oldalán talál. A csomagcikkeket nem szabad az **Anyagjegyzéksor** lehetőséggel felbontani, amely az **Alábontás** résznél, az **Értékesítési rendelés sorai** menüben található az **Értékesítési rendelés sorai** gyorslapon. Ellenkező esetben a rendszer anyagjegyzékként, és nem csomagként fogja kezelni a cikket.
- A csomagcikket tartalmazó értékesítési rendeléseket a szállítólevél vagy a számla létrehozása előtt meg kell erősíteni.
- Ha egy csomagot az értékesítési rendelés visszaigazolásával bontanak fel, a program törli a szülőcikket, és felosztja a szülőcikkhez tartozó egységárat és engedményeket a csomag összetevő cikkei között.
- Az összetevő cikkek összegének meg kell egyeznie a szülőcikkhez tartozó árral. Ezért az összetevő cikkekben nem minden mező frissíthető vagy módosítható. Az egységár például nem módosítható manuálisan. Emellett közvetett módon, új ármegállapodás bevezetésével sem lehet módostani az egységárat. Az új ármegállapodás létrejöttének elkerülése érdekében az összetevő cikkek készletdimenziói sem módosíthatók.
- Külső dokumentum, például az értékesítési rendelés visszaigazolása vagy a számla nyomtatásakor a rendszer a szülőcikket nyomtatja ki, nem az összetevő cikkeket.

## <a name="bundles-on-sales-orders"></a>Csomagok az értékesítési rendelésekben

Az USMF bemutatóvállalat a következő csomagbeállításokat tartalmazza. Ne feledje, hogy az ebben a forgatókönyvben használt összes cikknél eltávolítottuk a bevételelszámolási beállításokat, például a bevételi ütemezéseket.

**Szülőcikk:** Laptopcsomag

- **Összetevő cikk:** 1 darab az 1000 jelű cikkből
- **Összetevő cikk:** 1 darab az S0021 jelű cikkből
- **Összetevő cikk:** 1 darab a Support (Támogatás) nevű cikkből

Az összetevő cikkek *értékesítési alapára* az összetevők beállításainak alapvető része. Az eladási alapár a cikk **Eladás** gyorslapján határozható meg. A rendszer ezt használja a felosztási tényező kiszámítására, amikor a szülőcikk egységára az összetevő cikkek között van felosztva. A kereskedelmi szerződéshez tartozó eladási árakat a rendszer nem használja erre a célra.

Az összetevő cikkeknél a következő eladási alapárak vannak meghatározva:

- **1000:** 1900,00 $
- **S0021:** 150,00 $
- **Support** (Támogatás): 500,00 $

Bevisznek egy értékesítési rendelést az US-004, Cave Wholesales nevű vevőhöz. Csak a Laptop csomagcikkhez tartozó sort töltik ki. A szülősor alapértelmezett egységára számos helyről származhat, például a kereskedelmi szerződésből vagy az értékesítési alapárból. Ebben a példában a 2300 $ egységárat manuálisan adták meg.

[![A „Laptop” csomagcikk egy értékesítési rendelésen.](./media/bundle-01.png)](./media/bundle-01.png)

Mivel az értékesítési rendelés csomagot tartalmaz, meg kell erősíteni. A megerősítő párbeszédpanelben láthatók a csomag összetevői.

[![Az értékesítési rendelés megerősítésére szolgáló párbeszédpanel, amelyben megjelennek az összetevő cikkek.](./media/bundle-02.png)](./media/bundle-02.png)

A kinyomtatott megerősítési jelentésen azonban csak a csomag szülőcikke fog szerepelni, mivel ez a jelentés a vevőnek küldendő külső dokumentum.

[![A megerősítési jelentés, amelyben csak a szülőcikk szerepel.](./media/bundle-03.png)](./media/bundle-03.png)

Az értékesítési rendelés megerősítése után a szülőcikk továbbra is látható az értékesítési rendelésen, de állapota az **Érvénytelenítve** értékre módosul. Emellett a **Csomag nettó összege** mező jelzi a nettó összeget. Erre az összegre a számla kinyomtatásához van szükség, mert a számlán az összetevő cikkek helyett csak a szülőcikk szerepel.

Az összetevő cikkek összegének meg kell egyeznie a szülőcikkhez kapcsolódó **Csomag nettó összege** mező értékével, mivel ez az érték szerepel a vevő számára kinyomtatott számlán. Annak érdekében, hogy a számla megegyezzen a főkönyvbe feladott összegekkel, az összetevő cikkek szerkesztése korlátozva van. Például a telephely és a raktár nem módosítható, mert ezek a módosítások a kereskedelmi szerződés alapján árváltozást válthatnak ki.

A szülőcikkhez tartozó sorban szereplő egységár a következő módon oszlik meg az összetevők között:

**Összetevők teljes értékesítési alapára:** 1900 $ + 500 $ + 150 $= 2550 $

- **1. összetevő:** 2300 $ x (1900 ÷ 2550) = 1713,73 $
- **2. összetevő:** 2300 $ x (500 ÷ 2550) = 450,98 $
- **3. összetevő:** 2300 $ x (150 ÷ 2550) = 135,29 $

Az összetevők összegének 2300 $-nek kell lennie. Így is van (1713,73 $ + 450,98 $ + 135,29 $ = 2300 $).

Ha az összes összetevő cikknél módosításokra van szükség, a szülőcikk eltávolítható. Ebben az esetben a rendszer az összetevő cikkeket is eltávolítja. Ezt követően az értékelési rendelés megerősítése előtt ismét hozzáadhatja a szülőcikket, és elvégezheti a szükséges módosításokat.

[![Az összetevő cikk módosításait tartalmazó csomagcikk.](./media/bundle-04.png)](./media/bundle-04.png)

Az értékesítési rendelés kiszedése és becsomagolása után a dokumentumok csak a csomag összetevőit fogják tartalmazni. A szállítólevélnek és a számlának a teljes csomagot kell tartalmaznia. Ellenkező esetben nem lehet őket feladni. A párbeszédpanelen például három összetevő cikk látható. Ha megpróbálja törölni valamelyiket, hibaüzenet jelenik meg, amely jelzi, hogy a számlázáshoz a csomagban található összes terméket ki kell szállítani.

A csomagot teljes csomagként kell szállítani és számlázni. Ha például az 1000 jelű cikk mennyiségét 4-re módosítja, de a többi összetevő cikk mennyisége 5 marad, a szállítólevelet és a számlát nem lehet feladni.

Részleges mennyiséget csak akkor lehet szállítani és számlázni, ha a csomag összes összetevőjénél csökkenti a mennyiséget. Például az értékesítési rendelésnél az „5” mennyiséget adják meg a „Laptop” csomagcikkhez. Az értékesítési rendelés megerősítését követően három összetevő cikk látható a rendelésen, mindegyik mennyisége 5. Alapértelmezés szerint a szállítás és számlázás során a mennyiség 5-re lesz állítva minden összetevőnél. Azt megteheti, hogy mind a három összetevő cikknél 3-ra módosítja a mennyiséget. Ebben az esetben három teljes csomag szállítására és számlázására kerül sor. A fennmaradó két csomagcikk (2 darab mind a három összetevő cikkből) később szállítható és számlázható.

Az utolsó lépés az értékesítési rendelés kiszámlázása. A számlázás során a Számla párbeszédpanelen megjelennek az összetevő cikkek.

[![A Számla párbeszédpanel, amelyen az összetevő cikkek láthatók.](./media/bundle-06.png)](./media/bundle-06.png)

A kinyomtatott számlán azonban csak a szülőcikk fog szerepelni.
 
[![A kinyomtatott számla, amelyen csak a szülőcikk szerepel.](./media/bundle-07.png)](./media/bundle-07.png)

A feladás után létrehozott számlanapló nem tartalmazza a csomaghoz tartozó szülőcikket, mert a cikk állapota **Érvénytelenítve**.

[![A számlanapló, amely nem tartalmazza a szülőcikket.](./media/bundle-08.png)](./media/bundle-08.png)

Fontos, hogy a számlanapló ne tartalmazza a csomag szülőcikkét, mert a számla feladása után végrehajtott folyamatok a számlanaplón alapulnak. Ha például a Műveletpanel **Eladás** lapján létrehoz egy jóváírást, ez a jóváírás tartalmazni fogja az összetevő cikket, de a szülőcikket nem.

[![A jóváírás, amely a szülőcikket nem, de az összetevő cikkeket tartalmazza.](./media/bundle-09.png)](./media/bundle-09.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
