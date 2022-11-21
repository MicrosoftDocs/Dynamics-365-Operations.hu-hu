---
title: Első lépések az alaptervezéssel
description: Ez a cikk bemutatja, hogy hogyan lehet elkezdeni használni az alaptervezési funkciókat a következőben:Dynamics 365 Supply Chain Management
author: t-benebo
ms.date: 05/20/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: MpsIntegrationParameters, MpsFitAnalysis
audience: Application User
ms.reviewer: kamaybac
ms.custom: intro-internal
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 4b986461e90b356580da8a136c1da95e7dc64696
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/16/2022
ms.locfileid: "9780305"
---
# <a name="get-started-with-master-planning"></a>Első lépések az alaptervezéssel

[!include [banner](../../includes/banner.md)]

Az ellátásilánc-kezelésben az alaptervezést a tervezésoptimalizálási bővítménynek nevezett külső szolgáltatás biztosítja Dynamics 365 Supply Chain Management. Ez a témakör bemutatja, hogy hogyan szerezheti be és állíthatja be a szolgáltatást.

## <a name="availability"></a>Elérhetőség

A tervezési optimalizálás jelenleg a következő Azure földrajzi elhelyezkedésben érhető el: Egyesült Államok, Kanada, Brazília, Európa, Franciaország, Egyesült Királyság, Norvégia, Svájc, Ausztrália, Ázsiai Csendes-óceáni, Japán és India. Ha egy másik földrajzi régióból kísérli meg telepíteni a bővítményt, akkor az LCS egy üzenetet jelenít meg, hogy ez a földrajzi hely nem támogatott. Az Azure földrajzi régiókkal és a kapcsolódó régiókkal kapcsolatos további tudnivalókat lásd: [Azure-földrajzi régiók](https://azure.microsoft.com/global-infrastructure/geographies/#geographies).

Ne feledje, hogy a Tervezés optimalizálása nem támogatott a Dynamics 365 Supply Chain Management helyszíni telepítései esetében.

## <a name="licensing"></a>Licenckezelés

Ha az alaptervezést az aktuális licenccel futtatja, akkor nem kell megvásárolnia egy további licencet, hogy a tervezésoptimalizációt használhassa.

## <a name="install-and-enable-planning-optimization"></a>A Tervezési optimalizálás telepítése és engedélyezése

A Tervezési optimalizálás csak akkor használható, ha a rendszerben minden előfeltétel megvan, majd engedélyezni kell a licenckulcsát, és telepíteni kell a Tervezési optimalizálási bővítményt a Dynamics 365 Supply Chain Management rendszerhez.

### <a name="prerequisites"></a>Előfeltételek

Mielőtt telepítené a Tervezési optimalizálási bővítményt, a következő előfeltételeknek meg kell lenniük:

- A Supply Chain Management rendszert egy 2. szintű vagy magasabb szintű, LCS-kompatibilis magas rendelkezésre állású környezeten kell futtatnia (nem OneBox környezet), a Dynamics 365 Supply Chain Management 10.0.7-es vagy újabb verziójával. Ha OneBox- környezetbe próbálja meg telepíteni a bővítményt, akkor a telepítés nem fejeződik be, és a telepítést vissza kell vonni.

- Be kell állítani a rendszert a Power Platform-integrációhoz. A további tudnivalókat lásd [Microsoft Power Platform a Pénzügyi és műveleti alkalmazásokkal való integrációban](../../../fin-ops-core/dev-itpro/power-platform/overview.md).

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
| Leválasztva | Nincs kapcsolat a tervezés optimalizálása szolgáltatással. A kapcsolat az LCS-ről is bekapcsolható a jelen cikk korábbi leírása szerint. | Nem |
| Kapcsolat letiltása | Jelenleg folyamatban van a Tervezésoptimalizálás szolgáltatással való kapcsolat kikapcsolási kérelme. | Nem |
| Állapot lekérése | A rendszer a tervezés optimalizálása szolgáltatásból származó állapotadatokra várakozik. | Nem |

### <a name="the-use-planning-optimization-option"></a>A Tervezésoptimalizálás beállítás használata

A **Tervezés optimalizálása használata** beállítás határozza meg, hogy melyik tervezési motor használható az alaptervezéshez:

- **Igen** – a tervezésoptimalizálás az alaptervezéshez használatos.
- **Nem** – az elavult alaptervezési motor az alaptervezéshez használható.

Ez a beállítás minden jogi személyre (vállalatra) vonatkozik. Egyes jogi személyeknél nem használható a tervezési optimalizálás, illetve más jogi személyek elavult alaptervezési motorja.

> [!NOTE]
> Ha az **elavult** **alaptervezési** motorhoz létrehozott meglévő tervezési kötegelt feladatok aktiválódnak, miközben a Tervezési optimalizálás használata beállítás Igen, ezek a feladatok nem fognak működni.

### <a name="integration-with-the-setup"></a>Integráció a beállítással

Ha a Tervezésoptimalizálás be van kapcsolva, akkor az alaptervezést a rendszer a Tervezésoptimalizálás bővítménnyel végzi. Ebben az esetben az Alaptervezés eredményeit és funkcióit érinti a program.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
