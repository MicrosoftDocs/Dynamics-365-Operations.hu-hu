---
title: Talent bővítése a Power Apps és Power Automate szolgáltatásokkal
description: Ez a cikk néhány bővítési forgatókönyvet ír le a Microsoft Dynamics 365 Talent – Attract alkalmazáshoz, amelyek a Microsoft Power Apps és Microsoft Power Automate megoldásokat használják.
author: negudava
manager: Annbe
ms.date: 02/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent;Core;Experience Apps
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: negudava
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: cfdf36e9486aa4853d3bf674afa73ec3a4d1c161
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/17/2020
ms.locfileid: "4529634"
---
# <a name="extend-talent-with-power-apps-and-power-automate"></a>Talent bővítése a Power Apps és Power Automate szolgáltatásokkal

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Ez a cikk néhány bővítési forgatókönyvet ír le a Microsoft Dynamics 365 Talent: Attract alkalmazáshoz, amelyek a Microsoft Power Apps és Microsoft Power Automate megoldásokat használják. Az egyes példákhoz társított megoldáscsomagot importálhatja a Power Apps környezetébe. Majd használhatja a csomagokat iránymutatásként vagy kiindulási pontként a szervezetre vonatkozó forgatókönyvek végrehajtásához.

> [!IMPORTANT]
> Ha a cikkben bemutatott sablonokat és alkalmazást „adott” állapotukban szeretné használni, ügyeljen arra, hogy tesztelje az összeset, és győződjön meg arról minden az Ön implementációjához tartozó forgatókönyvet.


## <a name="prerequisites"></a>Előfeltételek

- Csomagok importálásához felhasználóknak rendelkezniük kell a **Környezetkészítő** engedéllyel.
- Az alkalmazások exportálásához vagy importálásához a felhasználóknak Power Apps Plan 2 licenccel, vagy Power Apps Plan 2 próbalicenccel kell rendelkezniük.

## <a name="power-automate--form-connect"></a>Power Automate – Form Connect

A **Power Automate – Form Connect** sablon adatok beolvasására használható Microsoft Forms űrlapokból illetve azok tárolására a Common Data Service entitásban.

Ez a sablonnal kiterjeszthető, hogy egyéb forgatókönyvekben is használható legyen. Íme néhány példa:

- Pályázó értékelések rögzítése.
- Tanfolyami kérdőív eredményeinek rögzítése.
- Interjú kérdések tárházának összeállítása Emberi erőforrások (HR) rendszergazdáknak.
- A jelentkező értékelésének rögzítése az interjúfolyamatból

A Microsoft Dynamics 365: Attract alkalmazásban űrlapokat használhat a Pályázói portálon, ahol a pályázók kitölthetik adataikat. Azonfelül tevékenységként űrlapokat ágyazhat be egy beosztássablonba.

Amikor a jelentkező egy elküld egy űrlapot, a Microsoft Power Automate rögzíti az űrlap benyújtását, beolvassa az adatokat, és tárolja azt a Common Data Service entitásban.

A **Power Automate – Form Connect** sablon és az egyéni entitásstruktúra letöltéséhez nyissa meg a [Power Automate – Form Connect](https://go.microsoft.com/fwlink/?linkid=2081988) elemet a Microsoft letöltőközpontban.

## <a name="power-automate--sharepoint-integration"></a>Power Automate – SharePoint-integráció

A **Power Automate – SharePoint-integráció** sablon használható adatok beolvasására egy Microsoft SharePoint-listát, a lista mezőértékeinek összehasonlításához bármely Common Data Service entitással, és az összehasonlítás eredményéről egy értesítő e-mail küldéséhez. 

Előfordulhat, hogy a szervezetnek sürgősen szüksége van egy szakértelemre. A szakértelmek tárolható SharePoint megoldásban, egy SharePoint listában. Ha egy jelölt olyan munkára jelentkezik, amelyhez szakértelmek vannak felsorolva, ha jelentős egyezés figyelhető meg a jelentkező szakértelme és a SharePoint megoldásban tárolt szakértelem között, egy értesítő e-mail érkezik. Ezzel a módszerrel a sürgősen szükséges pozíciókat gyorsabban be lehet tölteni, mivel az értesítések lehetővé teszik a toborzóknak, hogy a szervezetből más jelölteket vegyenek fel.

Ezzel a sablon bővíthető, így minden a SharePoint integrációt érintő forgatókönyvhöz használható.

A **Power Automate – SharePoint integráció** sablon letöltéséhez ugorjon a [Power Automate – SharePoint integráció](https://go.microsoft.com/fwlink/?linkid=2082109) oldalra a Microsoft Letöltőközpontban.

## <a name="referral-app"></a>Referral alkalmazás

A Referral alkalmazás segítségével jelölteket adhat hozzá egy közös tehetségállományhoz. Az ajánló megadhat **Utónevet**, **Vezetéknevet**, **E-mail-címet** és **LinkedIn URL-t** a jelölt beküldésekor. A pályázó forrásmetaadatai ezt követően lesznek generálva az ajánló adataival

Ez az alkalmazás beágyazható az Alkalmazotti önkiszolgáló rendszerbe, vagy használhatja azt hiperhivatkozásként a vállalati portálon, vagy futtathatja különálló alkalmazásként is.

A **Referral alkalmazás** letöltéséhez látogasson le a [Dynamics 365 Talent bővíthetőségi megoldás Referral App](https://www.microsoft.com/download/details.aspx?id=58497) oldalra a Microsoft letöltőközpontban. Ezt az alkalmazást importálhatja, és testreszabhatja további funkciók hozzáadásához.

## <a name="additional-resources"></a>További erőforrások

[A Microsoft Power Platform](https://docs.microsoft.com/power-platform/admin/admin-documentation)</br>
[Alkalmazás bérlők és környezetek közötti áttelepítése](https://docs.microsoft.com/power-platform/admin/environment-and-tenant-migration)


[!INCLUDE[footer-include](../includes/footer-banner.md)]