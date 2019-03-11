---
title: A termelésbeállítás követelményei
description: Ez a cikk tájékoztatást ad a beállítási követelményekről a Gyártásvezérlés használatba vétele előtt.
author: johanhoffmann
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdParameters, RouteOpr, RouteOprTable, WorkCalendarTable, WorkTimeTable, WrkCtrTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 55561
ms.assetid: 1953059f-478d-4706-b461-25b89ace5fc3
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b811c11271097f4bb7910c34f7775955abba526d
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "366627"
---
# <a name="production-setup-requirements"></a>A termelésbeállítás követelményei

[!include [banner](../includes/banner.md)]

Ez a cikk tájékoztatást ad a beállítási követelményekről a Gyártásvezérlés használatba vétele előtt. 

A gyártásvezérlés integrálva van más modulokban lévő funkciókkal. Ez a kapcsolat lehetővé, hogy módosítsa a termelési megrendeléseket és megbizonyosodjon, hogy automatikusan frissítésre kerülnek minden vonatkozó folyamatban és számításban a rendszerben. A következő beállítási folyamatok abban a sorrendben vannak felsorolva, amelyben teljesítenie kell őket.

## <a name="required-baseline-setup-in-other-modules"></a>Kötelező alapbeállítás más modulokban
Az egyéb modulokban található információkat be kell állítania, mielőtt dolgozhat a gyártásvezérléssel. Az a beállítás a következő feladatokat tartalmazza:

-   Általános vállalati információk beállítása.
-   A főkönyv beállítása.
-   A cikkcsoportok meghatározása.
-   A cikkcsoportok főkönyvi számláinak beállítása.
-   A készletcikk-táblázat beállítása a készletgazdálkodásban.
-   Anyagjegyzékek (AJ) és az anyagjegyzék-verziók létrehozása a készletgazdálkodásban.

## <a name="required-calendar-and-resource-setup"></a>Kötelező naptár- és erőforrás beállítás
Mielőtt használja a gyártásvezérlést nyissa meg a szervezeti adminisztrációt és hozzon létre és határozzon meg egy naptárat és műveleti erőforrásokat a következő sorrendben:

1.  **Munkaidősablonok** – Állítsa be a munkaidősablonokat, hogy meghatározza az időket, amelyek elérhetőek a termelési ütemezés számára.
2.  **Naptárak** – Állítson be munkaidő naptárakat, hogy meghatározza az év azon napjait, amelyek elérhetőek a termelésütemezés számára.
3.  **Erőforráscsoportok** – Állítsa be az erőforráscsoportokat, hogy csoportosítsák a műveleti erőforrásokat, hogy áttekintést kaphasson a szabad kapacitásról, amikor az ütemezést futtatja. Az erőforráscsoportokat nem kell a műveleti erőforrások előtt beállítnia. Azonban azt javasoljuk, hogy értse az erőforrások csoportosítását, amikor gyártásvezérlést állít be.
4.  **Erőforrások** – Állítson be műveleti erőforrásokat, hogy meghatározza az erőforrásokat, amelyek ahhoz használatosak, hogy elvégezze a termelési folyamatot és kapacitást tervezzen.

## <a name="required-production-parameters-setup"></a>Kötelező termelési paraméterek beállítása
**Gyártásvezérlési paraméterek** – Állítson be alapvető termelési paramétereket, hogy meghatározza, hogy a rendszer hogyan kezelje a folyamatokat és termelési rendeléseket. Határozz meg a termelési rendelések létrehozását, becslését, ütemezését és elhasználódását. Kijelölheti, hogy milyen visszajelzést kíván kapni és hogy hogyan történjen a költségkönyvelés.

## <a name="required-journal-name-identification"></a>Kötelező naplónevek azonosítása
**Termelésinapló-nevek** – Adja meg a termelésinapló-neveket, amelyek tranzakciók feljegyzésénél és feladásánál használatosak.

## <a name="setup-if-you-use-operations"></a>Beállítás műveletek használata esetén
A műveletek meghatározott tevékenységeket jelölnek, amelyek a befejezett cikk előállítása érdekében történnek. **Megjegyzés:** Ismernie kell a tevékenységtípusokat, amelyek szükségesek cikk előállításához és ezen tevékenységek sorrendjét és prioritásait. Azt is ismernie kell, hogy melyik erőforrásból mennyi kerül bevonásra.

1.  **Műveletek** – Állítsa be a műveleteket, hogy jelöljék a feladatokat, amelyeket el kell végezni a befejezett cikk előállításának érdekében.
2.  **Kapcsolatok** – Állítsa be a műveleti kapcsolatok, hogy részletes tulajdonságokat alakítson ki. Műveleti kapcsolatok meghatározásához kattintson a **kapcsolatok** elemre a **műveletek** oldalon.

## <a name="setup-if-you-use-routes"></a>Beállítás útvonalak használata esetén
Ha útvonalakkal dolgozik, a műveleteket minden beállított termelési útvonalhoz meg kell határozni. Az útvonalak kijelölik a cikk útját műveletről műveletre haladva, a folyamat indításától kezdve egészen a befejezésig.

1.  **Költségkategóriák** – Állítson be költségkategóriákat, hogy meghatározza a meghatározott folyamatok és beállítási idők óránkénti költségét.
2.  **Költségcsoportok** – Állítson be költségcsoportokat, hogy különböző költségszámítási módokat hozzon létre és tartson fent.
3.  **Útvonalcsoportok** – Állítson be útvonalcsoportokat, az útvonalak csoportjainak vonatkozó paramétereinek meghatározásához. Be kell állítania az útvonalcsoportokat, mielőtt termelési útvonalakat tud létrehozni.
4.  **Útvonalak** – Állítson be termelési útvonalakat, és határozzon meg alapértelmezett beállításokat, hogy irányítsa az útvonalműveletek ütemezését, költségszámítását és árképzését és hogy irányítsa az előrehaladottság jelentést.
5.  **Útvonalak** – Állítson be útvonalverziókat, hogy engedélyezze a cikkváltozatokat a termelésben.

## <a name="optional-advanced-settings"></a>Opcionális speciális beállítások
1.  **Termelési csoportok** – Állítson be termelési csoportokat, hogy kapcsolatokat alakítson ki a termelési rendelés és a főkönyvi számlák között. A főkönyvi számlák rendelések jelentésekhez történő feladásához vagy csoportosításához használatosak.
2.  **Termelési gyűjtők** – Hozzon létre termelési gyűjtőket, hogy csoportosítsa a termelési rendeléseket, annak érdekében, hogy feldolgozhassa a sürgős termelési rendeléseket vagy töröljön és feladjon megrendeléscsoportokat.
3.  **Tulajdonságok** – Határozzon meg tulajdonságokat, hogy különleges attribútumokat hozzon létre, amelyeket az erőforrásaihoz rendelhet a termelési sorrend irányítása érdekében. Ezek az attribútumok hozzá vannak kapcsolva a munkaidő sablonnal.




