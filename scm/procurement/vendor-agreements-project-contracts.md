---
title: "Fizetés a szállítói megállapodások kifizetésekor"
description: "Ez a cikk a „saját fizetés beérkezésekor történő fizetés” lehetséges feltételeit (a PWP-feltételeket) ismerteti a szállítói megállapodásokra vonatkozóan. A PWP-feltételek segítségével részlegesen vagy teljesen visszatarthat egy szállítói kifizetést mindaddig, amíg a projekt vevője nem fizet. A cikk egy való életből vett példát is bemutat annak szemléltetésére, hogy hogyan használhatók fel a PWP-feltételek egy projekthez."
author: kfend
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ProjProjectsListPage
audience: Application User, IT Pro
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 23131
ms.assetid: 20bf1d7f-8813-4c69-9cd7-576884a7e169
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 7b21d4e93ec22715d530b75f75f3ba475e561f62
ms.contentlocale: hu-hu
ms.lasthandoff: 05/25/2017


---

# <a name="pay-when-paid-vendor-agreements"></a>Fizetés a szállítói megállapodások kifizetésekor

[!include[banner](../includes/banner.md)]


Ez a cikk a „saját fizetés beérkezésekor történő fizetés” lehetséges feltételeit (a PWP-feltételeket) ismerteti a szállítói megállapodásokra vonatkozóan. A PWP-feltételek segítségével részlegesen vagy teljesen visszatarthat egy szállítói kifizetést mindaddig, amíg a projekt vevője nem fizet. A cikk egy való életből vett példát is bemutat annak szemléltetésére, hogy hogyan használhatók fel a PWP-feltételek egy projekthez.

Amikor engedélyezi egy szállítónak, hogy alvállalkozóként egy projekten dolgozzon, visszatarthatja a szállító vagy az alvállalkozó kifizetését, amíg a vevő ki nem fizeti a projektet. A szállítói kifizetésének visszatartása érdekében állítsa be fizetés beérkezésekor fizetendő (PWP) feltételeket beállításakor a beszerzési rendelés a szállítóval beállításakor. Amikor létrehoz egy szállítói beszerzési rendelést és a projekt azonosítót a beszerzési rendeléshez társítja, a projektben szereplő fizetés beérkezésekor fizetendő feltételeket társítják a beszerzési rendeléssel és a szállítóval. A **Fizetés beérkezésekor fizetendő móddal rendelkező szállítói számlák** lapon megtekintheti a beszerzési rendelés és a társított vevői számlák kiegyenlítetlen szállítói számláit. Ezen a képernyőn határozza meg szállítót és hogy mennyit fizet a szállítónak. Például, amikor a vevő a projektszámlán szereplő összeget kifizeti, kiadhatja a kifizetéshez kapcsolódó szállítói számlák egy részét vagy egészét. PWP feltételek beállításával meghatározhatja, hogy a szállítót a vevőtől származó kapcsolódó fizetés meghatározott százalékának átutalását követően fizetik ki. Amikor egy vevőtől részleges kifizetés érkezik, manuálisan kiadhatja a kifizetéshez kapcsolódó szállítói számlákat. A következő példa bemutatja, hogyan használhatja a PWP feltételeket a szállító vagy az alvállalkozói kifizetés visszatartására, amíg a vevő ki nem fizeti Önt. A szervezet megállapodást köt a vevővel a vevővel 100 számítógép biztosítására, amelyen telepíti a vevő által kért szoftvert. A vevő és Ön által megállapodott ár számítógépenként 150.00. Külső szállító szolgáltatásokat alkalmaz annak érdekében, hogy számítógépeket biztosítsanak az Ön számára. A vevő jóváhagyhatja a számítógépek minőségét, mielőtt kifizeti a szervezetet. A szervezet irányelve az, hogy visszatartja a külső szállító kifizetését egészen addig, amíg a projektben a vevő ki nem fizeti Önt. Ezért állítja be 100 százalék PWP százalékával a projektet, úgy, hogy minden a szállítónak fizetendő kifizetést visszatart egészen addig, amíg a vevői számla teljes kifizetése nem történt meg. A szállítóo költségek számítógépenként 100.00. Amikor a szállító küldi a számítógépeket, a szállítmány tartalmazza a 100 számítógép 10 000,00-es számláját. Mivel beállította a PWP feltételekkel a projektet, nem fizeti ki a szállítót. A szállítótól érkező számítógépek megérkezésekor, telepítse a szükséges szoftvert a számítógépen. Amikor elküldi a számítógépeket a vevőnek, elküldi a vevő 15,000.00-os számláját is. A vevő megvizsgálja a számítógépeket és jóváhagyja a termék minőségét. A vevő ezt követően kiegyenlíti a projekthez tartozó számla teljes összegét a szervezet részére. A vevőtől érkező teljes kifizetés megérkezését követően, kifizeti a szállító részére a 10 000,00-os szállítói számla teljes összegét.




