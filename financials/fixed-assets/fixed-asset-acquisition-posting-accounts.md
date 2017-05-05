---
title: "Tárgyieszköz-kivezetés feladási számlái"
description: "Ez a cikk bemutatja, hogy hogyan állíthat be főkönyvi feladási számlákat tárgyi eszközök beszerzéséhez."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: AssetPosting
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 23021
ms.assetid: d7e86f72-95db-4423-9b04-761e9536a959
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 8e89a57dda8f2d392483ed13c686ea97b74926b0
ms.openlocfilehash: bd7f89a7dbf8aa87794f8d4b57bda54433e5feb1
ms.lasthandoff: 03/31/2017


---

# <a name="fixed-asset-acquisition-posting-accounts"></a>Tárgyieszköz-kivezetés feladási számlái

[!include[banner](../includes/banner.md)]


Ez a cikk bemutatja, hogy hogyan állíthat be főkönyvi feladási számlákat tárgyi eszközök beszerzéséhez.

Tárgyieszköz-beszerzések feladásához használt számlák az eszköz megszerzésének módszerétől függően változhat. A tárgyi eszköz feladási profilok lapján, a főkönyvi számlák lapján válassza a beszerzési és beszerzés-módosítás kiigazitása a tárgyi eszköz számlák beállításához a főkönyvbe történő feladás érdekében. 

A naplókban és a beszerzési rendelésekben a főkönyvi számla általános esetben a az a mérlegszámla, amelyen az új tárgyi eszköz beszerzési értéke terhelve van. Ez a számla a naplóban nem látható, és a tranzakciókban nem helyettesíthető. 

Ellenszámla szintén egy mérlegszámla. Az általános naplóban és a tárgyieszköznaplóban gyakran ez az a számla, amelyről az eszköz beszerzési árának a kifizetése történik. Az ellenszámla egy alapértelmezett számla, amelyet a program felajánl a naplókban. A naplóban át lehet állítani a számlatükör bármely másik számlájára vagy – ha a tárgyi eszközt egy szállítótól vásárolta – egy szállítói számlára. 

Amikor a számlanaplót vagy a beszerzési rendeléseket tárgyieszköz-beszerzésekhez használják a kötelezettségekben, akkor a tárgyi eszköz tranzakciók ellenszámláját a tranzakcióhoz kiválasztott szállító számla kicseréli.

A feladott beszerzések esetén a főkönyvben található tárgyi eszközök tárának felhasználásával a tárgyi eszköz beszerzése nem külső forrásból, hanem a vállalat saját készletéből történik. Emiatt az ellenszámla a  készletcikkének egy készletkiadási számlája.

További tudnivalókért lásd: [Eszközök vételezése beszerzésen keresztül](acquire-assets-procurement.md).



