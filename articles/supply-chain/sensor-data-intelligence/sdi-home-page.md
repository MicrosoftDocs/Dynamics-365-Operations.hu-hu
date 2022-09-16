---
title: Belső adatintelligencia honlapja
description: Ez a cikk áttekintést nyújt a Biztonsági adatok intelligenciája funkcióról. A szervezetek ennek a funkciónak az segítségével hajtják meg az üzleti folyamatokat a Microsoftban Dynamics 365 Supply Chain Management, a termelésben található gépek és berendezések Internet of Things (Internet of Things) jelzései alapján.
author: johanhoffmann
ms.date: 09/02/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2022-09-02
ms.dyn365.ops.version: 10.0.30
ms.openlocfilehash: 2e4cd8d4d4ffcd10d02fbf26615f12cdd6ccca9e
ms.sourcegitcommit: 3d7ae22401b376d2899840b561575e8d5c55658c
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/08/2022
ms.locfileid: "9428983"
---
# <a name="sensor-data-intelligence-home-page"></a>Belső adatintelligencia honlapja

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

A Microsoft Dynamics 365 Supply Chain Management adatinterejelzései lehetővé teszik a szervezetek számára az ellátásilánc-kezelés üzleti folyamatainak irányítását az Internet of Things (IOT) által a termelésirányításban használt gépek és berendezések által jelezve. Ez az Internet-intelligenciával *kapcsolatos* funkció frissített, átnevezett verziója, amely korábban elérhető volt az ellátásilánc-kezeléshez.

Az adatinte intelligenciával a következő feladatokat lehet elvégezni:

- Részletek gyűjtése gépektől és berendezésektől a karbantartási eszköz számlálóértékének az Ellátásilánc-kezelésben való frissítése és a várható karbantartás javítása érdekében.
- A megoldás beállítása egyszerű, onboarding varázslóval Microsoft Dynamics ahelyett, hogy kézzel telepítené és konfigurálja az összetevőket a Lifecycle Services (LCS) szolgáltatásban.
- Saját előfizetésre telepítse az összetevőket, hogy nagyobb rugalmasságot nyújt az Azure-összetevők kezelésében.
- A megoldás konfigurálása, skálázható és bővíthető az Azure-összetevők üzleti logikájaként. Ezeket az összetevőket most saját előfizetésen kezeli a rendszer. Ezért igény szerint testreszabhatja őket, hogy megfeleljen az egyedi üzleti igényeknek.

## <a name="business-scenarios"></a>Üzleti esetek

Az egyedi adatintelligencia többféle funkciót kínál, amelyek mindegyikét a rendszer egy *konkrét* helyzete képviseli. A rendszer konfigurációs lehetőségeinek egy-egy speciális halmazát tartalmazza az alábbi táblázatban részletezett esetekhez.

| Forgatókönyv | Leírás |
|---|---|
| [Eszköz leállása](sdi-scenario-asset-downtime.md) | A gépi eszközök hatékonyságának pontos nyomon követése a gép leállásának nyomon követésére. |
| [Eszköz karbantartása](sdi-scenario-asset-maintenance.md) | A karbantartási költség csökkentése és az eszköz élettartamának meghosszabbítása a gépi eszközök kritikus vezérlő pontjainak leolvasásán alapuló karbantartási tervek fejlesztésével. |
| [Gép állapota](sdi-scenario-equipment-downtime.md) | A működés hatékonyságát úgy garantálhatja, hogy a mérőműveleteket használja, hogy értesítse a tervezőket a gépek kieséséről, és adja meg a lehetséges késések kijavítására vonatkozó beállításokat. |
| [Termékminőség](sdi-scenario-product-quality.md) | A termékkötelegek minőségének összehasonlítása az egyes termékkötelegek tényleges tulajdonságainak ( például minőségbiztosítási, hőmérsékleti vagy egyénileg megadott minőségi mérőszámok) összehasonlításával. A rendszer értesíti a felhasználókat, ha eltérés lép fel. |
| [Termelés késései](sdi-scenario-production-delays.md) | A mérőolvasások segítségével összehasonlíthatja a tényleges ciklusidőt a tervezett ciklusidővel, és értesítheti a felügyelőket, ha a termelés nincs ütemezésben. A felettesek ezután a működés maximális hatékonyságának biztosításához a szükséges mértékben gondoskodhatnak. |

## <a name="architecture"></a>Felépítés

A következő diagram diagramja áttekintést nyújt a megoldásról és annak összetevőiről.

![A belső adatintelligencia diagramja](media/sdi-architecture.png "Belső adatintelligencia -diagram")
