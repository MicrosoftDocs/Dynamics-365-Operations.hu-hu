---
title: Alaptervezés hely- és raktárfedezethez, a raktár nem kötelező
description: Ez a témakör leírja, hogyan terveznek meg egy fedezeti dimenziókként webhellyel ás raktárral rendelkező cikket. A raktár dimenzió nincs kötelezően beállítva.
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResStorageDimensionGroup, ReqItemTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2514
ms.assetid: 92d47bdd-df68-4f60-ac9a-96aa08236c26
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 45796049cddef137eb2ca1e4331197e4b4a65071
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1546294"
---
# <a name="master-planning-for-site-and-warehouse-coverage-warehouse-not-mandatory"></a>Alaptervezés hely- és raktárfedezethez, a raktár nem kötelező

[!include [banner](../includes/banner.md)]

Ez a témakör leírja, hogyan terveznek meg egy fedezeti dimenziókként webhellyel ás raktárral rendelkező cikket. A raktár dimenzió nincs kötelezően beállítva.

Ez az alaptervezési eset a következő feltételeket tartalmazza:

-   A telephelydimenzió kötelezőre van állítva, és meg kell adni az igénytranzakcióban. Ez a beállítás nem módosítható.
-   A raktár dimenzió nincs kötelezően beállítva. Lehet, hogy a raktár ismert, de ez nem befolyásolja az alapütemezési számítást.
-   A telephely és raktár dimenzió be van állítva a fedezet tervezéséhez. Előfordulhat, hogy más dimenziók is be vannak állítva a fedezet tervezéséhez. A több telephelyes funkciók mindezeket nem érintik.

Az alábbi ábra az alapütemezés folyamatát illusztrálja. Az ábrán látható paraméterek és helyeik a következők:
-   A raktár beállítása Kézi. Kattintson a következő lehetőségre: **Készletgazdálkodás &gt; Beállítás &gt; Készlet részletezése &gt; Raktárak**. Az a **Alaptervezés** gyorslapon lásd a **Kézi** mezőt.
-   A cikkre cikkfedezet van meghatározva. Kattintson a **Termékinformációk kezelése &gt; Termékek &gt; Kiadott termékek** lehetőségre. Jelölje ki a cikket, majd a Műveleti ablak ablakon a **Tervezés** lapon kattintson a **Cikk fedezete** elemre.
-   A raktárban újratöltési viszonyok vannak meghatározva. Kattintson a következő lehetőségre: **Készletgazdálkodás &gt; Beállítás &gt; Készlet részletezése &gt; Raktárak**. Az **Alaptervezés** gyorslapon lásd az **Elsődleges raktár** mezőcsoportot.
-   Az alapértelmezett rendelési típus beállítása Termelés, Beszerzési rendelés vagy Kanban. Kattintson a **Termékinformációk kezelése &gt; Termékek &gt; Kiadott termékek** lehetőségre. Jelölje ki a cikket, majd a Műveleti ablak ablakon a **Tervezés** lapon kattintson az **Alapértelmezett rendelésbeállítások** elemre. Az a **Alapértelmezett rendelésbeállítások** űrlapon lásd a **Alapértelmezett rendeléstípus** elemet.

![Telephely és raktár igénylése, nem kötelező rakár](./media/multisitedemandexplosionscenarioforsiteandwarehousecoveragewarehousenotmandatory.jpg)


-



<a name="additional-resources"></a>További erőforrások
--------

[Az alaptervezés és a többhelyes funkció](master-plan-multisite-functionality.md)

[Alaptervezés - hely és raktár fedezet, a raktár kötelező](master-plan-site-warehouse-coverage-warehouse-mandatory.md)

[Alaptervezés - helyfedezet, a raktár kötelező](master-plan-site-coverage-warehouse-mandatory.md)

[Alaptervezés - helyfedezet, a raktár nem kötelező](master-plan-site-coverage-warehouse-not-mandatory.md)

[Alaptervezés - Anyagjegyzék verzió meghatározása](master-plan-bom-version-determined.md)



