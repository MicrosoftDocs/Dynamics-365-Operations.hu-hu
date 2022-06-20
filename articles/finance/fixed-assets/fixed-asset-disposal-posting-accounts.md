---
title: Tárgyieszköz-kivezetés feladási számlája
description: Ez a cikk bemutatja, hogyan lehet beállítani a főkönyvi feladási számlákat az eszközök kipüggesztése számára.
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
ms.openlocfilehash: 1272cdb16396d24b5495f023e7b9fe3dee341507
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8871333"
---
# <a name="fixed-asset-disposal-posting-accounts"></a>Tárgyieszköz-kivezetés feladási számlája

[!include [banner](../includes/banner.md)]

Ez a cikk bemutatja, hogy hogyan lehet beállítani a főkönyvi feladási számlákat az eszközök kiesése esetén.

Hogy beállítson tárgyi eszközök kivezetésére használt Főkönyvi feladási számlákat, válassza a **Kivezetés - értékesítés** és **Kivezetés - selejtezés** lehetőséget a **Tárgyi eszközök feladási profiljai** oldal **Főkönyvi számlák** gyorslapján.

A tárgyi eszköz kivezetési értéke mindkét tranzakciótípus (eszköz kivezetése értékesítés vagy selejtezés útján) esetén a főkönyvi számla követeleként jelenik meg. A tartozás ellenszámlára van feladva, amely például lehet egy bankszámla (példaként). Ha a tárgyi eszközt egy vevőnek adja el, akkor az ellenszámla helyett a vevői számlát alkalmazza a program. További tájékoztatás: [Tárgyi eszköz selejtezése selejtként](dispose-of-a-fixed-asset-as-scrap.md).

Kattintson a **Kivezetés** parancsra, majd kattintson az **Értékesítés** vagy **Selejt** lehetőségre, majd állítsa be tárgyi érték nettó könyv szerinti értékének sztornózásához használt számla részletes adatait. A **Feladási érték** és **Értékesítési értéktípus** mezőkben is lehet információkat megadni a **Selejtezési paraméterek** oldalon. 

Az alacsony értékű csoportban szereplő eszköz értékesítési tranzakciója csak az értékesítés összegével csökkenti az alacsony értékű csoport nettó könyv szerinti értékét. Amennyiben azonban az eszköz eladása meghaladja az alacsony értékű csoport nettó könyv szerinti értékét, a nettó könyv szerinti érték nullára csökken.







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
