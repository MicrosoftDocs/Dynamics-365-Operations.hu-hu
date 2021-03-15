---
title: Első lépések a tervezési optimalizálással
description: Ez a témakör bemutatja, hogyan kezdje el használni a tervezési optimalizáció funkciót.
author: ChristianRytt
manager: tfehr
ms.date: 10/09/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: MpsIntegrationParameters, MpsFitAnalysis
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: a41f69958d84fb67b7cd8b6b4c7de38da23552f3
ms.sourcegitcommit: 2b76d4443b2867205db156648125a894f395a495
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2021
ms.locfileid: "5091085"
---
# <a name="get-started-with-planning-optimization"></a>Tervezési optimalizálás kezdő lépései

[!include [banner](../../includes/banner.md)]

A [korábbi bejelentésnek megfelelően](https://docs.microsoft.com/dynamics365/supply-chain/get-started/removed-deprecated-features-scm-updates#use-of-built-in-supply-chain-management-master-planning-engine-for-distribution-scenarios) a Tervezési optimalizálás várhatóan felváltja a meglévő beépített alaptervezési motort.

Ha jelenleg a beépített alaptervezési motort használja, akkor most el kell indítania a Tervezési optimalizálását az áttelepítéshez. Fontos, hogy a program rögtön elindítsa az áttelepítési folyamatot, mert az elavulás kényszerítése hatással lehet a folyamatban lévő műveleteire. Az elavulás kikényszerítésekor az utolsó pillanatban jelentkező nehézségek elkerülése érdekében erősen javasoljuk, hogy végezze el az áttelepítést még 2020. december 1-je előtt. 

A tervezési optimalizálás funkció jelenleg nem támogatja az összes olyan funkciót, amely a Supply Chain Managementbe épített tervezőmotorban jelenleg elérhető. Ezért fontos, hogy meggyőződjön, hogy a tervezésoptimalizálásban jelenleg elérhető szolgáltatáskészlet kielégíti-e a követelményeket. A tervezési optimalizálás funkció alapértelmezés szerint nincs bekapcsolva a Dynamics Lifecycle Services (LCS) modulban, így még a funkció bekapcsolása előtt lehetősége van az értékelésre.

> [!NOTE]
> Ha az alaptervezési folyamat nem foglalja magában a termelést (az alaptervezés által létrehozott tervezett termelési rendeléseket), akkor kivételt kell kérnie a tervezési optimalizálás miatt szükséges áttelepítés alól, és egy 10.0.15-ös verzión túli beépített alaptervezési motort kell igényelnie. A 10.0.16 verziótól kezdődően egy hiba jelenik meg a környezetekben, amikor a tervezett termelési rendelések létrehozása nélkül futtatja a beépített alaptervezést. A tervezési optimalizálás minden olyan új telepítésnél használható, amely nem hoz létre tervezett termelési rendeléseket az alaptervezés során. Azok, akik beépített alaptervezési motort a tervezett termelési rendelések létrehozása nélkül, a meglévő környezetekben futtatnak, egy levelet fognak kapni, amely a kivételezési folyamat részleteit ismerteti. Javasoljuk, hogy egy partnerrel folytasson együttműködést a tervezési optimalizáláshoz szükséges áttelepítés értékeléséhez és megtervezéséhez.

A tervezés optimalizálása előtt kifejezetten ajánljuk, hogy értékelje a tervezésoptimalizálás illeszkedési elemzésének eredményeit. További tájékoztatás: [Tervezésoptimalizálás illeszkedési elemzése](planning-optimization-fit-analysis.md).

## <a name="availability"></a>Elérhetőség

A Tervezési optimalizálása jelenleg a következő Azure földrajzi területeken érhető el: Egyesült Államok, Kanada, Európa, Egyesült Királyság, Ausztrália és Ázsia és a Csendes-óceáni térség. Ha egy másik földrajzi régióból kísérli meg telepíteni a bővítményt, akkor az LCS egy üzenetet jelenít meg, hogy ez a földrajzi hely nem támogatott.

Ne feledje, hogy a Tervezés optimalizálása nem támogatott a Dynamics 365 Supply Chain Management helyszíni telepítései esetében.

## <a name="licensing"></a>Licenckezelés

Ha az alaptervezést az aktuális licenccel futtatja, akkor nem kell megvásárolnia egy további licencet, hogy a tervezésoptimalizációt használhassa.

## <a name="install-and-enable-planning-optimization"></a>A Tervezési optimalizálás telepítése és engedélyezése

A Tervezési optimalizálás csak akkor használható, ha a rendszerben minden előfeltétel megvan, majd engedélyezni kell a licenckulcsát, és telepíteni kell a Tervezési optimalizálási bővítményt a Dynamics 365 Supply Chain Management rendszerhez.

### <a name="prerequisites"></a>Előfeltételek

Mielőtt telepítené a Tervezési optimalizálási bővítményt, a következő előfeltételeknek meg kell lenniük:

- A Supply Chain Management rendszert egy 2. szintű vagy magasabb szintű, LCS-kompatibilis magas rendelkezésre állású környezeten kell futtatnia (nem OneBox környezet), a Dynamics 365 Supply Chain Management 10.0.7-es vagy újabb verziójával. Ha OneBox- környezetbe próbálja meg telepíteni a bővítményt, akkor a telepítés nem fejeződik be, és a telepítést vissza kell vonni.

- Be kell állítani a rendszert a Power Platform-integrációhoz. A további tudnivalókat lásd: [Bővítmények előfeltételei és telepítésük](../../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md#prerequisites-for-setting-up-add-ins) és [Bővítmények beállítása](../../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md#set-up-add-ins).

### <a name="enable-the-planning-optimization-license"></a>A Tervezési optimalizálás licencének engedélyezése

A Tervezési optimalizálás használatához engedélyeznie kell a konfigurációs kulcsot. Ehhez tegye a következőket:

1. Állítsa a rendszert karbantartási módba a [Karbantartási mód](../../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md) alatt leírtak szerint.
1. Lépjen a **Rendszerfelügyelet \> Beállítás \> Licenckonfiguráció** elemre.
1. A **Konfigurációs kulcsok** lapon jelölje be a **Tervezési optimalizálás** jelölőnégyzetet.
1. Kapcsolja ki a karbantartási módot a [Karbantartási mód](../../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md) alatt leírtak szerint.

### <a name="install-the-planning-optimization-add-in"></a>A Tervezési optimalizálás bővítményének telepítése

A bővítményt a LCS-projektből kell telepítenie, és a Supply Chain Management felhasználói felületéről (UI) kell bekapcsolni a Tervezési optimalizálás funkciót.

A Tervezési optimalizálás bővítményének telepítése:

1. Jelentkezzen be a LCS-ba, majd nyissa meg a kívánt környezetet.
1. Lépjen a **Teljes részletek** elemre.
1. Görgessen le a **Környezeti bővítmények** gyorslapra.
1. Válassza az **Új bővítmény telepítése** lehetőséget.
1. Válassza a **Tervezés optimalizálása** lehetőséget.
1. Kövesse a telepítési útmutatót, és fogadja el a feltételeit és kikötéseit.
1. Válassza a **Telepítés** parancsot.
1. A **Környezeti bővítmények** gyorslapon látnia kell, hogy a Tervezési optimalizálás telepítése folyamatban van.
1. Néhány perc múlva a **Telepítés** felirat erre módosul: **Telepítve** (előfordulhat, hogy frissíteni kell az oldalt). A telepítés befejezésekor készen áll a Tervezési optimalizálás funkció aktiválására a Dynamics 365 Supply Chain Management alkalmazásban.

A Tervezésoptimalizálás bővítmény telepítésének fő célja a szolgáltatás és a környezet csatlakoztatása. Ezért a bővítményt külön kell telepíteni minden olyan környezetre, ahol a tervezésoptimalizálást fogja használni, függetlenül a környezetek között áthelyezett kódoktól.

## <a name="integrate-planning-optimization-with-your-system"></a>Tervezési optimalizálás integrálása a rendszerével

Annak konfigurálásához, hogy a Tervezési optimalizálás bővítményt használja-e a rendszer az alaptervezéshez, nyissa meg az **Alaptervezés** \> **Beállítás** \> **Tervezési optimalizálás paraméterei** lehetőséget.

### <a name="connection-status"></a>Kapcsolat állapota

A kapcsolat állapota jelzi a kapcsolat aktuális állapotát a Supply Chain Management és a Tervezésoptimalizálás szolgáltatás között. A következő táblázat mutatja a lehetséges értékeket.

| Kapcsolat állapota | Leírás | Használható a Tervezésoptimalizálás? |
|---|---|---|
| Csatlakoztatva | A rendszer kapcsolatot létesített a Tervezésoptimalizálás és a Supply Chain Management között. | Igen |
| Kapcsolat engedélyezése | Jelenleg folyamatban van a Tervezésoptimalizálás szolgáltatással való kapcsolat bekapcsolási kérelme. | Nem |
| Leválasztva | Nincs kapcsolat a tervezés optimalizálása szolgáltatással. A kapcsolat a következő témakörben leírtak szerint a LCS-ről kapcsolható be. | Nem |
| Kapcsolat letiltása | Jelenleg folyamatban van a Tervezésoptimalizálás szolgáltatással való kapcsolat kikapcsolási kérelme. | Nem |
| Állapot lekérése | A rendszer a tervezés optimalizálása szolgáltatásból származó állapotadatokra várakozik. | Nem |

### <a name="the-use-planning-optimization-option"></a>A Tervezésoptimalizálás beállítás használata

A **Tervezés optimalizálása használata** beállítás határozza meg, hogy melyik tervezési motor használható az alaptervezéshez:

- **Igen** – a tervezésoptimalizálás az alaptervezéshez használatos.
- **Nem** – Az alaptervezéshez a Supply Chain Management beépített tervezési motorja használatos.

> [!NOTE]
> Ha meglévő tervezett kötegelt feladatok, amelyeket a beépített Supply Chain Management tervezési morothoz hoztak létre, elindulnak, miközben a **Tervezésoptimalizálás használata** beállítás értéke **Igen**, a feladatok sikertelenek lesznek.

### <a name="integration-with-the-setup"></a>Integráció a beállítással

Ha a Tervezésoptimalizálás be van kapcsolva, akkor az alaptervezést a rendszer a Tervezésoptimalizálás bővítménnyel végzi. Ebben az esetben az Alaptervezés eredményeit és funkcióit érinti a program.

## <a name="additional-resources"></a>További erőforrások

[Az előzetes verzió feltételei és kikötései](https://go.microsoft.com/fwlink/?linkid=2015274)

[Tervezési optimalizálás áttekintése](planning-optimization-overview.md)

[A tervezésoptimalizálása illeszkedési elemzése](planning-optimization-fit-analysis.md)

[Tervelőzmények és tervezési naplók megtekintése](plan-history-logs.md)

[Szűrők alkalmazása egy tervre](plan-filters.md)

[Tervezési feladat érvénytelenítése](cancel-planning-job.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]