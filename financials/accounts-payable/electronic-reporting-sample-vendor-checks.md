---
title: "Elektronikus jelentéskészítés mintája szállítói csekkekhez"
description: "A témakör általános tájékoztatást nyújt az elektronikus jelentések mintacsekkformátumainak használatáról."
author: twheeloc
manager: AnnBe
ms.date: 06/14/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations, UnifiedOperations
ms.assetid: 
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: a8ba439ff643fce4811be9224a3edf96b2b9025c
ms.contentlocale: hu-hu
ms.lasthandoff: 07/27/2017

---

[!include[banner](../includes/banner.md)]

# <a name="electronic-reporting-sample-check-formats"></a>Elektronikus jelentéskészítés csekkformátumainak mintája

Az elektronikus jelentéskészítés segítségével formázhatja a szállítói csekkeket. Sok csekkspecifikus és csekkszolgáltató-specifikus csekkformátum áll rendelkezésre a piacon. A mintaellenőrzési formátumok szerepelnek az ER-eszköztár Fizetésicsekk-modelljében. A mintacsekkek megjelölése a következő: **Csekk középütt (USA)** és **Csekk a felső rész alján (USA)**.

## <a name="what-check-formats-are-currently-supported"></a>Melyik csekkformátumok támogatottak jelenleg?

Mindig meg kell keresnie a Microsoft Dynamics Lifecycle szolgáltatások (LCS) megosztott eszközkönyvtárát, és meg kell tekintenie az aktuális listát a rendelkezésre álló fájlokról, amelyek **GER-konfiguráció** eszköztípusúak. A következő szakasz, a "Mit kell beállítanom?" hivatkozást biztosít a témához, amely alapján LCS-adattárat hozhat létre az elérhető konfigurációk áttekintéséhez és a kiválasztott konfigurációk importálásához.

A Microsoft Dynamics 365 for Finance and Operations, Enterprise edition olyan mintaformátumot tartalmaz, amelynél a csekk felül látható, és két átutalási szakasz követi. Olyan mintaformátumot is tartalmaz, ahol a csekk középütt van, két átutalási szakasz között. Ezek a mintaformátumok a Deluxe üzleti csekkformátumnak felelnek meg.

## <a name="what-do-i-have-to-set-up"></a>Mit kell beállítanom?

- Mielőtt csekkeket nyomtathatna az ER használatával, legalább egy aktív csekk-konfigurációt importálni kell az ER-konfigurációkba. További utasításokért lásd: [Az elektronikus jelentési beállítások letöltése a Lifecycle Services rendszerből](/dynamics365/unified-operations/dev-itpro/analytics/download-electronic-reporting-configuration-lcs).
- Ha készpénz- ls bankkezelési csekkeket konfigurál a bankszámlánál, jelölje be az **Általános elektronikus exportálási formátum** jelölőnégyzetet, majd válassza ki a megfelelő csekkformátumot az exportálási formátum konfigurációjaként.
- Azoknak a bizonylatsoroknak a számát is adja meg, amelyeket az utalásra nyomtat. Mindig szerepeltesse a fejlécsorokat a szám kiszámításakor. A két próbacsekkformátumnál a bizonylatsorok ajánlott száma 17. Ez a szám azonban változó, a csekk-készlettől és a nyomtatóillesztőktől függően.
- Javasoljuk, hogy nyomtasson próbacsekket a csekkelrendezés ellenőrzéséhez. Próbacsekk nyomtatásához válassza a **Tesztnyomtatás** lehetőséget. A mintacsekkformátumok akkor működnek legjobban, ha a **Margók** beállítása **Nincs** a Microsoft Excel haladó nyomtatótulajdonságaiban. Miután elkészült a próbacsekk, engedélyezze az Excel-kimenet szerkesztését, és konfigurálja az oldalelrendezést úgy, hogy az összes margó beállítása **0** (zéró) legyen. Hasonlítsa össze a csekkek próbapéldányát a készletével, és módosítsa a beállításokat addig, amíg nem elégedett az elrendezéssel.
- Amikor a konfigurált bankszámlára befizetéseket generál a fizetési naplóban, az ellenőrzéseket a megadott formátumban nyomtatja ki a rendszer.

További információ: [Elektronikus jelentés formátumának módosítása](/dynamics365/unified-operations/dev-itpro/analytics/modify-electronic-reporting-format-reapply-excel-template).

