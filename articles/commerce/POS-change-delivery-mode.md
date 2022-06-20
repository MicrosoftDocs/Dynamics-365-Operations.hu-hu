---
title: Szállítási mód módosítása a pénztárban
description: Ez a témakör leírja, hogyan kell konfigurálni és használni a POS-terminálon a szállítási mód változtatási műveletét.
author: hhainesms
ms.date: 03/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: ''
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: hhaines
ms.search.validFrom: 2020-02-20
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: 583f568164d0de70e22998bf5ded5f4616b00bd2
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8855821"
---
# <a name="change-mode-of-delivery-in-pos"></a>Szállítási mód módosítása a pénztárban

[!include [banner](includes/banner.md)]

Ez a témakör leírja, hogyan lehet beállítani és használni a "Szállítási mód módosítása" funkciót a pénztári környezetben. 

A Dynamics 365 Commerce 10.0.10 és a későbbi verziókban **Szállítási mód módosítása** művelet (647) elérhető a hozzáadásra pénztári képernyő-elrendezéseihez.

A szállítási mód módosítása funkció a pénztári tranzakcióban egy vagy több szállítmányhoz konfigurált értékesítési sor szállítási módjának módosítását teszi lehetővé. A Commerce korábbi verzióiban végig kellett mennie a teljes **Össze szállítása** vagy **Kijelölt szállítása** konfigurációs folyamatokon ha a szállítási módot módosítani szerette volna egy olyan meglévő sorban, amely már be van állítva a szállításhoz. Ez a folyamat időigényes volt, és a sorhoz tartozó szállítási dátumok véletlen módosítását eredményezhette. Az új funkciók alternatív módszert biztosítanak a szállítási mód hatékony frissítésére az értékesítési sorokban.

Ha további tájékoztatást szeretne arról, hogyan lehet hozzáadni egy műveletet a pénztári gombrács egy gombjához, tekintse meg a [Képernyő-elrendezések a pénztár (POS) számára](pos-screen-layouts.md) című cikket.

Ha ez a funkció a pénztárban be van állítva, és a **Szállításimód módosítása** lehetőséget választja, akkor egy lista jelenik meg, amely lehetővé teszi, hogy kiválassza azoknak a tranzakcióknak a sorait, amelyekhez a szállítási módot módosítani szeretné. Egy vagy az összes is kiválaszthatja, illetve módosítás nélkül kiléphet. A korábban szállítmányként konfigurált értékesítési sorok azok a sorok a listában, amelyeket módosíthat. Ha módosítani kívánja a felvételi vagy a kiszállítási sorokat akkor az **Összes szállítása** vagy a **Kijelöltek szállítása** műveleteket kell használnia. Ha viszont a szállítmányként kijelölt sort egy felvételi vagy kiszállításra szeretné módosítani, akkor az **Összes felvétele**, a **Kijelöltek felvétele**, **Összes kiszállítása** vagy **Kijelöltek kiszállítása** műveleteket kell választania.

Miután kiválasztotta a módosítani kívánt sorokat, kattintson a **Szállítási mód módosítása** lehetőségre, hogy lehetősége legyen a szállítási mód beállításainak kiválasztására. Ha több sort választott ki módosításra, akkor a pénztár csak a kiválasztott termékre vonatkozóan megengedettnek konfigurált szállítási módokat jeleníti meg. A szállítási módok beállítható meghatározott termékek és szállítási címek támogatásához. Ha egy olyan szállítási mód van, amely elfogadható egy termék és cím kombináció esetében, de egy másik kiválasztott termék-és címkombináció esetében nem elfogadható, akkor a szállítási mód nem érhető el. Előfordulhat, hogy egyenként kell kiválasztania a sorokat, és minden egyes sorhoz külön-külön kell módosítani a szállítási módot, ha ki szeretné választani egy olyan szállítási módot,amely egy másik termék által nem támogatott.  

Miután kiválasztotta az új szállítási módot, megjelenik a tranzakció lap. Az új szállítási mód beállításainak áttekintéséhez válassza ki a tranzakció listán a **Szállítás** fület.

## <a name="additional-resources"></a>További erőforrások

[Hívásközponti rendelések létrehozása](tasks/create-call-center-orders.md)

[Tranzakciós e-mailek testreszabása szállítási mód szerint](customize-email-delivery-mode.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]