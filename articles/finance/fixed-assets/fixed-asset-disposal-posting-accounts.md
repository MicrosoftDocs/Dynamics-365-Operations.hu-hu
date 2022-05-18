---
title: Tárgyieszköz-kivezetés feladási számlája
description: Ez a témakör bemutatja, hogy hogyan állíthat be Főkönyvi feladási számlákat eszközök elhelyezésére.
author: moaamer
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetPosting
audience: Application User
ms.reviewer: kfend
ms.custom: 3461
ms.assetid: dfdc0730-e030-48cc-8d93-15bdc7b23776
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8501bbb0fc47fb52e100d9086054db4831dae178
ms.sourcegitcommit: e09f5c6d78d7942af950ae3f6407df2fedceeba4
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/06/2022
ms.locfileid: "8720251"
---
# <a name="fixed-asset-disposal-posting-accounts"></a>Tárgyieszköz-kivezetés feladási számlája

[!include [banner](../includes/banner.md)]

Ez a témakör bemutatja, hogy hogyan állíthat be Főkönyvi feladási számlákat eszközök kivezetésére.

Hogy beállítson tárgyi eszközök kivezetésére használt Főkönyvi feladási számlákat, válassza a **Kivezetés - értékesítés** és **Kivezetés - selejtezés** lehetőséget a **Tárgyi eszközök feladási profiljai** oldal **Főkönyvi számlák** gyorslapján.

A tárgyi eszköz kivezetési értéke mindkét tranzakciótípus (eszköz kivezetése értékesítés vagy selejtezés útján) esetén a főkönyvi számla követeleként jelenik meg. A tartozás ellenszámlára van feladva, amely például lehet egy bankszámla (példaként). Ha a tárgyi eszközt egy vevőnek adja el, akkor az ellenszámla helyett a vevői számlát alkalmazza a program. További tájékoztatás: [Tárgyi eszköz selejtezése selejtként](dispose-of-a-fixed-asset-as-scrap.md).

Kattintson a **Kivezetés** parancsra, majd kattintson az **Értékesítés** vagy **Selejt** lehetőségre, majd állítsa be tárgyi érték nettó könyv szerinti értékének sztornózásához használt számla részletes adatait. A **Feladási érték** és **Értékesítési értéktípus** mezőkben is lehet információkat megadni a **Selejtezési paraméterek** oldalon. 

Az alacsony értékű csoportban szereplő eszköz értékesítési tranzakciója csak az értékesítés összegével csökkenti az alacsony értékű csoport nettó könyv szerinti értékét. Amennyiben azonban az eszköz eladása meghaladja az alacsony értékű csoport nettó könyv szerinti értékét, a nettó könyv szerinti érték nullára csökken.







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
