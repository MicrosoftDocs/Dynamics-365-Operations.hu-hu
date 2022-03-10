---
title: Üres adó funkciólista az adószámítási paraméterekben
description: Ez a témakör azt mutatja be, hogyan lehet elhárítani azokat a problémákat, amelyeknél az Adószámítási paraméterek lapon üres a lista.
author: wangchen
ms.date: 03/04/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TaxIntegrationTaxServiceParameters
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-10-26
ms.dyn365.ops.version: Version 10.0.21
ms.openlocfilehash: 5b87499042c9c4bfe76e182b170adf4f1cfeac4b
ms.sourcegitcommit: b80692c3521dad346c9cbec8ceeb9612e4e07d64
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/05/2022
ms.locfileid: "8389125"
---
# <a name="empty-tax-feature-list-in-tax-calculation-parameters"></a>Üres adó funkciólista az adószámítási paraméterekben

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

## <a name="symptom"></a>Tünet

Közzétett egy funkciót a Regulatory Configuration Service (RCS) szolgáltatásban, hogy használni tudja a Microsoftban Dynamics 365 Finance. Amikor azonban megnyitja a Pénzügy szolgáltatást, **·** \> **·** \> **·** \> **nyissa** meg az Adóbeállítás adóbeállítása konfigurációs adó számítási paramétereit, és válasszon ki egy értéket a **Funkcióbeállítás neve** mezőben, az értékek listája üres.

## <a name="reason"></a>OK

Ez a probléma általában azért fordul elő, mert a pénzügyi környezet és az RCS környezet nem ugyanazon a bérlőn van.

### <a name="rcs-tenant"></a>RCS -bérlő

A következő lépések szerint keresse meg az RCS-bérlő azonosítóját.

1. A teljes RCS URL-cím másolása Az URL-cím lehet például `https://rcs-rts-sf-ed22b5aeea8-int-westus2.configure.global.int.dynamics.com/namespaces/817ff7a0-0d77-4aba-9360-3c9749e2c5de/?cmp=dat&mi=RCSFeatureDomainsWorkspace`.
2. Nyisson meg egy InPrivate böngészőablakot, illessze be az RCS URL-címet a címsávba, majd válassza az Enter **gombra.** A bejelentkezési oldalra irányítják, ahol megkeresheti az RCS bérlőazonosítót. Ha például a bejelentkezési oldal URL-címe `https://login.microsoftonline.com/d335a570-a05b-4bc5-8eb3-c42c65f9560d`, `https://login.microsoftonline.com/` akkor a bérlőazonosító az után megjelenő információ, vagy **d335a570-a05b-4bc5-8eb3-c42c65f9560d**.

### <a name="finance-environment-tenant-id"></a>Pénzügyi környezet - bérlőazonosító

A pénzügyi környezet bérlőazonosítójának megkereséséhez kövesse ugyanezeket a lépéseket, amelyek után megkeresi az RCS-bérlőt. Azonban a pénzügyi környezet teljes URL-címének másolása és beillesztése a teljes RCS URL-cím helyett.

## <a name="resolution"></a>Megoldás

Ha a két bérlő-szám eltér egymástól, akkor az ebben a témakörben leírt probléma merül fel. Ha azonosak, akkor nem kapcsolódó probléma ad problémát. Ebben az esetben javasoljuk, hogy forduljon a Microsoft támogatási szolgálatához.

### <a name="solution-1"></a>1. megoldás

Az RCS-környezet bejelentkezése ugyanannak a bérlőnek, akihez a Pénzügy környezet be van jelentkezve. Ezután hozza létre és tegye közzé az adó funkciót.

### <a name="solution-2"></a>2. megoldás

Ossza meg az adó funkciót az RCS pénzügyi bérlővel.

1. Az RCS esetében használja az Adószámítás **globalizációs funkciókat** \> **·**.
2. Válassza ki a megoszt kívánt funkciót, **majd** a Szervezetek lapon válassza a **Megosztás lehetőséget**.
3. Adjon meg **egy** nevet a Szervezet tartománynév mezőjében. Megadhatja például a **contoso.onmicrosoft.com**.
4. Válassza ki a **Megosztás** elemet.

![Megosztás külső szervezet legördülő párbeszédpanelével](media/ShareTaxFeature.png)
