---
title: Vevői rendelésfelvételek feldolgozása a pénztárban
description: Ez a témakör bemutatja a pénztári alkalmazásban a vevői rendelés felvételének feldolgozására használható funkciókat.
author: Hhainesms
manager: annbe
ms.date: 01/06/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: global
ms.author: hhaines
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: 2156542ed0932fab6fb4fa4035e009ad89eeb18f
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "5003753"
---
# <a name="process-customer-order-pickups-in-pos"></a>Vevői rendelésfelvételek feldolgozása a pénztárban

[!include [banner](includes/banner.md)]

Amikor [vevői rendelést](customer-orders-overview.md) hoznak létre üzletben történő átvételre, az üzlet felhasználója a pénztári alkalmazás segítségével elindíthatja a készlet átvételét. A pénztár a szükséges feltételek szerint futtatja a kifizetés végleges rögzítését. Ezenkívül készletzárást és pénzügyi feladást végez az átvett mennyiségekre.

Ha üzleti felhasználó, az átvételt a **Rendelés visszahívása** művelettel, vagy a **Rendelés teljesítése** művelettel végezheti el a pénztárban. Ahhoz, hogy az **Átvétel** művelet elérhető legyen, először a következő lépések valamelyikét kell követnie:

- A **Rendelés visszahívása** művelethez keresse meg és válassza ki az átvenni kívánt rendelést.
- A **Rendelés teljesítése** művelet alkalmazáshoz keressen meg és válasszon ki egy vagy több rendeléssort.

Ha a kiválasztott rendelés vagy rendeléssorok nincsenek az adott üzletben való átvételre konfigurálva, vagy ha a rendelést már teljes mértékben átvették, az **Átvétel** művelet nem érhető el.

![Átvételi művelet](media/pickupoperation.png)

A Microsoft Dynamics 365 Commerce 10.0.17-es és újabb verzióiban a Commerce központi felületén a Funkciókezelés segítségével bekapcsolható a **Továbbfejlesztett felhasználói felület a rendelésfeldolgozás átvételéhez a pénztárban** funkció. Ha ez a funkció ki van kapcsolva, a felhasználók nem választhatnak ki átvételi mennyiséget. Alapértelmezés szerint a sorhoz rendelt teljes mennyiség az átvételre kiválasztott mennyiség. Ez problémás lehet, mert előfordulhat, hogy a felhasználók elfelejtik kiválasztani az átvenni kívánt cikkeket, amikor a rendelés teljesítésével elvégzik az átvételt.

A **Továbbfejlesztett felhasználói felület a rendelésfeldolgozás átvételéhez a pénztárban** funkció nagyobb ellenőrzést biztosít a felhasználóknak az átveendő termékek kiválasztása és az átveendő termékek mennyisége fölött. A felhasználóknak nem kell az értékesítési rendelés minden sorát kijelölniük a rendelés teljesítése oldalon az **Átvétel** lehetőség kiválasztása előtt. Minden átvehető cikk megjelenik. A felhasználók akkor is több sort határoznak meg az átvételhez, ha csak egy terméksor van kiválasztva.

Ha a **Továbbfejlesztett felhasználói felület a rendelésfeldolgozás átvételéhez a pénztárban** funkció be van kapcsolva, és az **Átvétel** műveletet választja, megjelenik az **Átvétel** párbeszédpanel. Itt kiválaszthatja az átveendő cikkeket és mennyiségeket. Alapértelmezés szerint minden olyan készleten tartott megrendelt mennyiség, amely kitárolt vagy csomagolt állapotban van, átvehető. Alapértelmezés szerint ez a mennyiség van beállítva átvételi mennyiségként. A megadott mennyiség módosítható, feltéve, hogy a mennyiség nem 0 (nulla), és nem haladja meg a kijelölt sor teljes nyitott (azaz nem számlázott) mennyiségét.

![Átvétel párbeszédpanel](media/pickupselect.png)

Miután kiválasztotta az átvenni kívánt mennyiségeket, majd kiválasztotta az **Átvétel** lehetőséget, megjelenik a tranzakcióoldal. Ha a [többcsatornás fizetések](omni-channel-payments.md) funkció be van kapcsolva, és előre engedélyezett hitelkártyás fizetések vannak rögzítve, alkalmaznia kell a kifizetést.

A tranzakcióoldalon a rendszer kiszámítja az esedékes összegeket úgy, hogy kiszámítja a kiválasztott átveendő cikkek esedékes összegét, majd kivonja a korábban alkalmazott betéteket és engedélyezett hitelkártyás kifizetéseket. A fizetést fel kell feldolgoznia az átvételi tranzakció befejezéséhez. Ha a tranzakcióoldal [képernyő-elrendezése](pos-screen-layouts.md) úgy van beállítva, hogy tartalmazza a **Tranzakció befejezése** műveletet, és nincs esedékes összeg, fizetési mód kiválasztása nélkül is befejezheti a tranzakciót. Ha a **Tranzakció befejezése** művelet nem érhető el, az **Összegek** ablakban kiválasztható a **0,00 USD esedékes összeg** hivatkozása, hogy a tranzakció befejeződjön, és ne kell kiválasztani fizetési módot.

![Vevői rendelés átvételi tranzakciójának tranzakciós oldala](media/pickupcart.png)

## <a name="changing-pickup-lines-or-quantities"></a>Átvlteli sorok vagy mennyiségek módosítása

Ha az átvételre kiválasztott cikkek kiválasztása után módosítania kell az átvételi mennyiséget, a kiválaszthatja a **Mennyiség beállítása** lehetőséget. A felvételi mennyiséget nem állíthatja **0** (nulla) értékre és nem növelheti olyan értékre, amely meghaladja a megrendelt sorban maradó, nem kiszámlázott mennyiséget. Ha el szeretne távolítani egy átvételi sort a tranzakciós kosárból, válassza a **Tranzakció érvénytelenítése** lehetőséget. Az aktuális tranzakció leáll, és a rendszer újraindítja az **Átvétel** művelet folyamatát.

Ha a **Továbbfejlesztett felhasználói felület a rendelésfeldolgozás átvételéhez a pénztárban** funkció be van kapcsolva, a szervezetek hozzáadhatnak egy gombot az **Átvételi sorok módosítása** művelethez a tranzakcióoldal képernyő-elrendezéséhez. Miután létrehozott egy átvételi tranzakciós kosarat a pénztárban és kiválasztotta a cikkeket, akkor választhatja az **Átvételi sorok módosítása** lehetőséget, ha módosítania kell az átvételi cikkeket, de nem szeretné érvényteleníteni a teljes tranzakciót. A megjelenő **Átvételi sorok módosítása** párbeszédpanelen módosíthatja az átvételi cikkeket és mennyiségeket. Ezt követően a rendszer frissíti a tranzakciós kosarat, hogy tükrözze a módosításokat.

![Átvételi cikkek módosítása párbeszédpanel](media/pickupchange.png)
