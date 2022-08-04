---
title: Hitelkeret esetek
description: Ez a témakör azt ismerteti, hogyan történik a vevő hitelkeretének ellenőrzése, ha a vevő vevői hitelkeretcsoporthoz tartozik.
author: JodiChristiansen
ms.date: 06/28/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 539093
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2022-06-28
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 60b17a6b7f57b468610974ae9bd05b7db3584cc1
ms.sourcegitcommit: 85141b21ac90f3db1b378c21f9c7f3d8f74e182f
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/09/2022
ms.locfileid: "9130272"
---
# <a name="credit-limit-scenarios"></a>Hitelkeret esetek

A Hitelkezelésben hitelkeret rendelhető a vevőkhöz a vevő szintjén. Minden vevőt hozzá lehet rendelni egy vevői *hitelkeretcsoporthoz*, és mindegyik csoportnak van hitelkerete. Ezért csoportszinten hitelkeretet is hozzá lehet rendelni a vevőkhöz. Minden, ugyanannak a vevői hitelcsoportnak megfelelő vevőnek ugyanaz a hitelkerete.

A csoport hitelkeretei általában az egyes hitelkeretek előtt ellenőrizhetők. Az egyedi hitelkeret nem mindig bírálja felül a csoport hitelkeretét.

Ez a témakör öt esetet ismertet, amelyek a vevői jóváírási csoportokkal és az egyes hitelkeretekkel kapcsolatosak.

## <a name="the-customer-group-credit-limit-is-more-than-the-individual-credit-limit"></a>A vevőcsoport hitelkerete nagyobb az egyéni hitelkeretnél.

A vevő például egyéni hitelkeretet $10,000. A vevő hozzá van rendelve egy vevői hitelcsoporthoz, és a csoport hitelkerete $15,000. Ebben az esetben a vevő "tényleges hitelkerete" nem $10,000, mert az összeg kisebb a csoportkorlátozásnál. A blokkolási szabályok előbb ellenőrzik a csoportkorlátot. Ezután ellenőrzik az egyéni korlátot. A rendszer letiltja a $10,000 értékesítési rendeléseket.

## <a name="the-individual-credit-limit-is-more-than-the-customer-group-credit-limit"></a>Az egyedi hitelkeret nagyobb, mint a vevőcsoport hitelkerete.

Például a vevő egyéni hitelkeretet $20,000. A vevő hozzá van rendelve egy vevői hitelcsoporthoz, és a csoport hitelkerete $15,000. Ebben az esetben a vevő hatályos hitelkerete $15,000, mivel a blokkolási szabályok mindig a csoportkorlátot ellenőrzik előbb. A rendszer letiltja a $15,000 értékesítési rendeléseket.

## <a name="the-individual-credit-limit-is-set-to-000-and-mandatory-credit-limit-is-set-to-yes"></a>Az egyes hitelkeret beállítása 0,00, a kötelező hitelkeret beállítása Igen.

**Ha a vevő egyéni hitelkerete 0,00-ra** van állítva, **·** **és a kötelező hitelkeret beállítása Igen**, a vevő tényleges hitelkerete $0.00 akkor is, ha a vevő egy vevő hitelcsoporthoz van hozzárendelve. Ily módon a vevő egy csoport része lehet, de minden rendelés a Jóváíráskezeléshez fog hozzámenni.

## <a name="the-individual-credit-limit-is-set-to-000-and-unlimited-credit-limit-is-set-to-yes"></a>Az egyéni hitelkeret 0,00-ra van állítva, a Korlátlan hitelkeret beállítása Igen.

**Ha a vevő egyéni hitelkerete 0,00-ra** van állítva, **·** **de** a Korlátlan hitelkeret beállítás Igen beállításra van állítva, akkor a vevő korlátlan hitelkeretet kap, még akkor is, ha hozzá van rendelve egy vevői hitelcsoporthoz.

## <a name="the-individual-credit-limit-is-set-to-000-and-the-customer-is-part-of-a-customer-credit-group"></a>Az egyedi hitelkeret 0,00-ra van állítva, és a vevő egy vevői jóváírási csoport része.

Például a **vevő egyéni hitelkerete 0,00-ra** van állítva, **·** **a** Korlátlan hitel lehetőség Beállítása Nem, **·** **a Kötelező hitelkeret beállítás Pedig Nem.** A vevő hozzá van rendelve egy vevői hitelcsoporthoz, és a csoport hitelkerete $15,000. Ebben az esetben a vevő tényleges hitelkerete a csoport korlátja, amely $15,000. Ennek megfelelően a rendszer letiltja az ezen összeg felett értékesítési rendeléseket. Ez a viselkedés lehetővé teszi, hogy a hitelkeret kezelése az egyes vevői szint helyett a vevő hitelcsoport szintjén legyen. Minden, ugyanannak a csoporthoz rendelt vevőnek ugyanaz a hitelkerete.
