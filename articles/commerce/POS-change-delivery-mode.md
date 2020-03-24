---
title: Szállítási mód módosítása a pénztárban
description: Ez a témakör azt mutatja be, hogyan lehet konfigurálni és használni a szállítási mód módosítása műveletet a pénztárban.
author: hhainesms
manager: annbe
ms.date: 03/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: ''
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: hhainesms
ms.search.validFrom: 2020-02-20
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: 26e798c664844b575de6f019ad8f5349ed92be98
ms.sourcegitcommit: 141e0239b6310ab4a6a775bc0997120c31634f79
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/10/2020
ms.locfileid: "3114404"
---
# <a name="change-mode-of-delivery-in-pos"></a>Szállítási mód módosítása a pénztárban

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Ez a témakör azt mutatja be, hogyan lehet beállítani és használni a „szállítási mód módosítása” funkciót a pénztár (POS) környezetében. 

A Dynamics 365 Commerce 10.0.10 és a későbbi verziókban **Szállítási mód módosítása** művelet (647) elérhető a hozzáadásra pénztári képernyő-elrendezéseihez.

A szállítási mód módosítása funkció a pénztári tranzakcióban egy vagy több szállítmányhoz konfigurált értékesítési sor szállítási módjának módosítását teszi lehetővé. A Commerce korábbi verzióiban végig kellett mennie a teljes **Össze szállítása** vagy **Kijelölt szállítása** konfigurációs folyamatokon ha a szállítási módot módosítani szerette volna egy olyan meglévő sorban, amely már be van állítva a szállításhoz. Ez a folyamat időigényes volt, és a sorhoz tartozó szállítási dátumok véletlen módosítását eredményezhette. Az új funkciók alternatív módszert biztosítanak a szállítási mód hatékony frissítésére az értékesítési sorokban.

Ha további tájékoztatást szeretne arról, hogyan lehet hozzáadni egy műveletet a pénztári gombrács egy gombjához, tekintse meg a [Képernyő-elrendezések a pénztár (POS) számára](https://docs.microsoft.com/dynamics365/commerce/pos-screen-layouts) című cikket.

Ha ez a funkció a pénztárban be van állítva, és a **Szállításimód módosítása** lehetőséget választja, akkor egy lista jelenik meg, amely lehetővé teszi, hogy kiválassza azoknak a tranzakcióknak a sorait, amelyekhez a szállítási módot módosítani szeretné. Egy vagy az összes is kiválaszthatja, illetve módosítás nélkül kiléphet. A korábban szállítmányként konfigurált értékesítési sorok azok a sorok a listában, amelyeket módosíthat. Ha módosítani kívánja a felvételi vagy a kiszállítási sorokat akkor az **Összes szállítása** vagy a **Kijelöltek szállítása** műveleteket kell használnia. Ha viszont a szállítmányként kijelölt sort egy felvételi vagy kiszállításra szeretné módosítani, akkor az **Összes felvétele**, a **Kijelöltek felvétele**, **Összes kiszállítása** vagy **Kijelöltek kiszállítása** műveleteket kell választania.

Miután kiválasztotta a módosítani kívánt sorokat, kattintson a **Szállítási mód módosítása** lehetőségre, hogy lehetősége legyen a szállítási mód beállításainak kiválasztására. Ha több sort választott ki módosításra, akkor a pénztár csak a kiválasztott termékre vonatkozóan megengedettnek konfigurált szállítási módokat jeleníti meg. A szállítási módok beállítható meghatározott termékek és szállítási címek támogatásához. Ha egy olyan szállítási mód van, amely elfogadható egy termék és cím kombináció esetében, de egy másik kiválasztott termék-és címkombináció esetében nem elfogadható, akkor a szállítási mód nem érhető el. Előfordulhat, hogy egyenként kell kiválasztania a sorokat, és minden egyes sorhoz külön-külön kell módosítani a szállítási módot, ha ki szeretné választani egy olyan szállítási módot,amely egy másik termék által nem támogatott.  

Miután kiválasztotta az új szállítási módot, megjelenik a tranzakció lap. Az új szállítási mód beállításainak áttekintéséhez válassza ki a tranzakció listán a **Szállítás** fület.   
