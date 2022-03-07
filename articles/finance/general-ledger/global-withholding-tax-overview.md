---
title: Globális adóelőleg
description: Ez a témakör a globális adóelőleg funkcióval és a funkció beállításával kapcsolatban tartalmaz tájékoztatást. A globális adóelőleg funkció továbbfejlesztett szállítói és vevői tranzakcióknál használható, így az adóelőleg számítása a cikk szintjén történik.
author: roschlom
ms.date: 01/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerParameters
audience: Application User
ms.reviewer: roschlom
ms.custom:
- "15721"
- intro-internal
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2020-01-12
ms.dyn365.ops.version: AX 10.0.16
ms.openlocfilehash: c51da1257e11543f025fda76c166301477ef78508caac0451267437e918435eb
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6727348"
---
# <a name="global-withholding-tax"></a>Globális adóelőleg

[!include [banner](../includes/banner.md)]

Ez a témakör a globális adóelőleg funkcióval és a funkció beállításával kapcsolatban tartalmaz tájékoztatást. Az új funkció a 10.0.17-es és későbbi verziókban áll rendelkezésre.

A globális adóelőleg funkció továbbfejlesztett szállítói és vevői tranzakcióknál használható, így az adóelőleg számítása a cikk szintjén történik. A beszerzési tranzakciók adóelőleg-számlájának egyenlege az adóelőleg-kiegyenlítési feladatnak az adóelőleg-elszámolási számlára vonatkozó futtatásával egyenlíthető ki.

> [!NOTE]
> A globális adóelőleg nem támogatja a **Költségek karbantartása** funkciót a beszerzési rendelés, a szállítói számla és az értékesítési rendelés oldalakon.

## <a name="turn-on-global-withholding-tax"></a>Globális adóelőleg bekapcsolása

1. A **Funkció kezelése** munkaterületen válassza ki a **Globális adóelőleg** lehetőséget, majd válassza az **Engedélyezés most** lehetőséget.
2. Lépjen az **Adó \> Beállítás \> Paraméterek \> Főkönyvi paraméterek** pontra, majd az **Adóelőleg** lapon állítsa a **Globális adóelőleg engedélyezése** beállítást **Igen** értékre.
3. Válassza a **Mentés** lehetőséget.
4. Frissítse az oldalt a webböngészőben.

> [!NOTE]
> A globális adóelőleg funkció nem kapcsolható be olyan országokban/régiókban, ahol már léteznek honosított adóelőleg-megoldások. Ezek a területek többek között Indiára, Brazíliára, Thaiföldre, Szaúd-Arábiára, Írországra, Nagy-Britanniára és az Egyesült Államokra korlátozódnak.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
