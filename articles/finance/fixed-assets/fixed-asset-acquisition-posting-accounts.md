---
title: Tárgyieszköz-beszerzés feladási számlája
description: Ez a cikk bemutatja, hogy hogyan állíthat be Főkönyvi feladási számlákat tárgyi eszközök beszerzéséhez.
author: moaamer
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetPosting
audience: Application User
ms.reviewer: kfend
ms.custom: 23021
ms.assetid: d7e86f72-95db-4423-9b04-761e9536a959
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 93cbfc46fb41e47fba8b6cecf7811c0cf838e7d3
ms.sourcegitcommit: e09f5c6d78d7942af950ae3f6407df2fedceeba4
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/06/2022
ms.locfileid: "8719820"
---
# <a name="fixed-asset-acquisition-posting-accounts"></a>Tárgyieszköz-beszerzés feladási számlája

[!include [banner](../includes/banner.md)]

Ez a cikk bemutatja, hogy hogyan állíthat be Főkönyvi feladási számlákat tárgyi eszközök beszerzéséhez.

Tárgyieszköz-beszerzések feladásához használt számlák az eszköz megszerzésének módszerétől függően változhat. A tárgyi eszköz feladási profilok lapján, a főkönyvi számlák lapján válassza a beszerzési és beszerzés-módosítás kiigazitása a tárgyi eszköz számlák beállításához a főkönyvbe történő feladás érdekében. 

A naplókban és a beszerzési rendelésekben a főkönyvi számla általános esetben a az a mérlegszámla, amelyen az új tárgyi eszköz beszerzési értéke terhelve van. Ez a számla a naplóban nem látható, és a tranzakciókban nem helyettesíthető. 

Ellenszámla szintén egy mérlegszámla. Az általános naplóban és a tárgyieszköznaplóban gyakran ez az a számla, amelyről az eszköz beszerzési árának a kifizetése történik. Az ellenszámla egy alapértelmezett számla, amelyet a program felajánl a naplókban. A naplóban át lehet állítani a számlatükör bármely másik számlájára vagy – ha a tárgyi eszközt egy szállítótól vásárolta – egy szállítói számlára. 

Amikor a számlanaplót vagy a beszerzési rendeléseket tárgyieszköz-beszerzésekhez használják a kötelezettségekben, akkor a tárgyi eszköz tranzakciók ellenszámláját a tranzakcióhoz kiválasztott szállító számla kicseréli.

A feladott beszerzések esetén a főkönyvben található tárgyi eszközök tárának felhasználásával a tárgyi eszköz beszerzése nem külső forrásból, hanem a vállalat saját készletéből történik. Emiatt az ellenszámla a  készletcikkének egy készletkiadási számlája.

További tudnivalókért lásd: [Eszközök vételezése beszerzésen keresztül](acquire-assets-procurement.md).





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
