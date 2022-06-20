---
title: Elektronikus jelentéskészítéskészítési minta szállítói csekkekhez
description: Ez a cikk az elektronikus jelentési minta csekkformátumok használatával kapcsolatban tartalmaz általános tájékoztatást.
author: sunfzam
ms.date: 06/14/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: twheeloc
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: d2b26a083540924d2368a298632aea90ecf95e9b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8908183"
---
# <a name="electronic-reporting-sample-vendor-checks"></a>Elektronikus jelentéskészítés mintája szállítói csekkekhez

[!include [banner](../includes/banner.md)]

Az elektronikus jelentéskészítés segítségével formázhatja a szállítói csekkeket. Sok csekkspecifikus és csekkszolgáltató-specifikus csekkformátum áll rendelkezésre a piacon. A mintaellenőrzési formátumok szerepelnek az ER-eszköztár Fizetésicsekk-modelljében. A mintacsekkek megjelölése a következő: **Csekk középütt (USA)** és **Csekk a felső rész alján (USA)**.

## <a name="what-check-formats-are-currently-supported"></a>Melyik csekkformátumok támogatottak jelenleg?

Mindig meg kell keresnie a Microsoft Dynamics Lifecycle Services (LCS) megosztott eszközkönyvtárát, és meg kell tekintenie az aktuális listát a rendelkezésre álló fájlokról, amelyek **GER-konfiguráció** eszköztípusúak. A következő, "Mit kell beállítani?" rész egy olyan cikkre mutató hivatkozást tartalmaz, amely bemutatja egy LCS-tárház létrehozásához szükséges szükséges beállításokat, így áttekintheti a rendelkezésre álló konfigurációkat, és importálhatja a kiválasztott konfigurációkat.

Microsoft Dynamics A 365 Pénzügy egy olyan mintaformátumot tartalmaz, amelyben a csekk felül van, amelyet két átutalási szakasz követ. Olyan mintaformátumot is tartalmaz, ahol a csekk középütt van, két átutalási szakasz között. Ezek a mintaformátumok a Deluxe üzleti csekkformátumnak felelnek meg.

## <a name="what-do-i-have-to-set-up"></a>Mit kell beállítanom?

- Mielőtt csekkeket nyomtathatna az ER használatával, legalább egy aktív csekk-konfigurációt importálni kell az ER-konfigurációkba. További utasításokért lásd: [Az elektronikus jelentési beállítások letöltése a Lifecycle Services rendszerből](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).
- Ha készpénz- ls bankkezelési csekkeket konfigurál a bankszámlánál, jelölje be az **Általános elektronikus exportálási formátum** jelölőnégyzetet, majd válassza ki a megfelelő csekkformátumot az exportálási formátum konfigurációjaként.
- Azoknak a bizonylatsoroknak a számát is adja meg, amelyeket az utalásra nyomtat. Mindig szerepeltesse a fejlécsorokat a szám kiszámításakor. A két próbacsekkformátumnál a bizonylatsorok ajánlott száma 17. Ez a szám azonban változó, a csekk-készlettől és a nyomtatóillesztőktől függően.
- Javasoljuk, hogy nyomtasson próbacsekket a csekkelrendezés ellenőrzéséhez. Próbacsekk nyomtatásához válassza a **Tesztnyomtatás** lehetőséget. A mintacsekkformátumok akkor működnek legjobban, ha a **Margók** beállítása **Nincs** a Microsoft Excel speciális nyomtatótulajdonságaiban. Miután elkészült a próbacsekk, engedélyezze az Excel-kimenet szerkesztését, és konfigurálja az oldalelrendezést úgy, hogy az összes margó beállítása **0** (zéró) legyen. Hasonlítsa össze a csekkek próbapéldányát a készletével, és módosítsa a beállításokat addig, amíg nem elégedett az elrendezéssel.
- Amikor a konfigurált bankszámlára befizetéseket generál a fizetési naplóban, az ellenőrzéseket a megadott formátumban nyomtatja ki a rendszer.

További információ: [Elektronikus jelentés formátumának módosítása](../../fin-ops-core/dev-itpro/analytics/modify-electronic-reporting-format-reapply-excel-template.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
