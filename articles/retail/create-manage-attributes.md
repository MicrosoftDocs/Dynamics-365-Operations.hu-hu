---
title: "Attribútumok létrehozása és kezelése"
description: "Ez a cikk a Microsoft Dynamics 365 for Retail attribútumait írja le. Az attribútumokkal leírhat egy terméket és annak jellemzőit a felhasznál által meghatározott mezők segítségével."
author: pdp1207
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: EcoResAttributeType, EcoResAttribute
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 16461
ms.assetid: 2b85491c-f830-4e79-a2cb-681b7ced6988
ms.search.region: global
ms.search.industry: Retail
ms.author: prabhup
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: a98527d37040dfcc0e57b74d590802e8aa2cb0b6
ms.contentlocale: hu-hu
ms.lasthandoff: 11/03/2017

---

# <a name="create-and-manage-attributes"></a>Attribútumok létrehozása és kezelése

[!INCLUDE [banner](includes/banner.md)]

Ez a cikk a Microsoft Dynamics 365 for Retail attribútumait írja le. Az attribútumokkal leírhat egy terméket és annak jellemzőit a felhasznál által meghatározott mezők segítségével.

Az attribútumokkal leírhat egy terméket és annak jellemzőit a felhasznál által meghatározott mezők segítségével. Például megadhatja a termék memóriaméretét vagy merevlemez-kapacitását, és jelezheti, hogy a termék megfelel-e az Energy star előírásoknak. Az attribútumok különböző kiskereskedelmi entitásokhoz, például termékkategóriákhoz és kiskereskedelmi csatornákhoz, társíthatók, és megadhatók hozzájuk alapértelmezett értékek. A termékek öröklik az attribútumaikat és a hozzájuk tartozó alapértelmezett értékeket, amikor társítják őket egy termékkategóriához vagy kiskereskedelmi csatornához. Az alapértelmezett értékek felülírhatók az egyes termékek és a kiskereskedelmi csatorna szintjén vagy a kiskereskedelmi kategóriában.

#### <a name="examples"></a>Példák

| Kategória   | Attribútum                | Megengedett értékek          | Alapértelmezett érték |
|------------|--------------------------|-----------------------------|---------------|
| TV és videó | Márka                    | Bármilyen érvényes Márka érték       | Nincs          |
| TV         | Képernyőméret              | 20″–80″                     | Nincs          |
| TV         | Függőleges felbontás      | 480i, 720p, 1080i vagy 1080p | 1080p         |
| TV         | Képernyő-frissítési gyakoriság      | 60hz, 120hz vagy 240hz       | 60hz          |
| TV         | HDMI-bemenetek              | 0–10                        | 3             |
| TV         | DVI-bemenetek               | 0–10                        | 1             |
| TV         | Kompozit bemenetek         | 0–10                        | 2             |
| TV         | Komponens bemenetek         | 0–10                        | 1             |
| LCD        | 3D Ready                 | Igen vagy Nem                   | Igen           |
| LCD        | 3D Enabled               | Igen vagy Nem                   | Nincs            |
| Plazma     | Min. üzemhőmérséklet      | 32–110 fok              | 32            |
| Plazma     | Max. üzemhőmérséklet        | 32–110 fok              | 100           |
| Projektoros | Képcsőgarancia | 6, 12 vagy 18 hónap         | 12            |
| Projektoros | Képcsövek száma    | 1–5                         | 3             |


## <a name="attribute-type"></a>Attribútumtípus
  [![attributes-fixed-copy](./media/attributes-fixed-copy.png)](./media/attributes-fixed-copy.png) 

Az attribútumok az attribútumtípusokon alapulnak. Az attribútumtípusok az adott attribútumba bevihető adatok típusát azonosítják. Jelenleg a Microsoft Dynamics 365 for Retail a következő attribútumtípusokat támogatja:

-   **Currency** – Ez az attribútumtípus a pénznemértékeket támogatja. Lehet kötött (vagyis támogathat egy értéktartományt) vagy nyitva is hagyható.
-   **DateTime** – Ez az attribútumtípus a dátum és idő értékeket támogatja Lehet kötött (vagyis támogathat egy értéktartományt) vagy nyitva is hagyható.
-   **Decimal** – Ez az attribútumtípus numerikus értékeket támogat, amelyek tizedesjegyeket is tartalmaznak. Mértékegységeket is támogat. Lehet kötött (vagyis támogathat egy értéktartományt) vagy nyitva is hagyható.
-   **Itenger** – Ez az attribútumtípus a numerikus értékeket támogatja. Mértékegységeket is támogat. Lehet kötött (vagyis támogathat egy értéktartományt) vagy nyitva is hagyható.
-   **Text** – Ez az attribútumtípus a szöveges támogatja. Előre meghatározott, lehetséges értékcsoportokat is támogat (felsorolás).
-   **Boolean** – Ez az attribútumtípus bináris értékeket támogat (**igaz**/**hamis**).
-   **Hivatkozás**.

## <a name="attribute"></a>Attribútum
  [![createandmanageattribute-8](./media/createandmanageattribute-8.png)](./media/createandmanageattribute-8.png) Az attribútumhoz rögzíthető a név, a vezetéknév, a leírás és a súgó szövege mellett a következő információtípusok közül egy vagy több:

-   Alapértelmezett érték
-   Az attribútumok metaadatai, például azzal kapcsolatban, hogy az attribútum kereshető, finomítható vagy rendezhető-e

## <a name="attribute-group"></a>Attribútumcsoport
  [![createandmanageattribute-10](./media/createandmanageattribute-10.png)](./media/createandmanageattribute-10.png) Az attribútumok a meghatározásuk után attribútumcsoportokba csoportosíthatók. Az attribútumcsoportokkal csoportosíthatók az egyedi attribútumok, és kiskereskedelmi kategóriához vagy csatornákhoz társíthatjuk őket.

## <a name="assigning-attribute-groups-to-retail-categories"></a>Attribútumcsoportok társítása kiskereskedelmi kategóriákhoz
  [![createandmanageattribute-12](./media/createandmanageattribute-12.png)](./media/createandmanageattribute-12.png) Egy vagy több attribútumcsoport társítható kategória-csomópontokhoz a kiskereskedelmi termékek kategóriahierarchiájában. A kategorizálást követően a termékek öröklik az attribútumcsoportba tartozó attribútumokat.

## <a name="assigning-attribute-groups-to-retail-stores"></a>Attribútumcsoportok társítása kiskereskedelmi boltokhoz
  [![createandmanageattribute-13-1024x576](./media/createandmanageattribute-13-1024x576.png)](./media/createandmanageattribute-13-1024x576.png) Egy vagy több attribútumcsoport társítható kiskereskedelmi üzletekhez a kiskereskedelmi üzletek kategóriahierarchiájában. A kategorizálást követően a termékek öröklik az attribútumcsoportba tartozó attribútumokat.

## <a name="overriding-attribute-values"></a>Attribútumértékek felülbírálása
### <a name="at-the-product-level"></a>Termékszinten

  [![createandmanageattribute-14-1024x576](./media/createandmanageattribute-14-1024x576.png)](./media/createandmanageattribute-14-1024x576.png) Az attribútumok alapértelmezett értéke felülírható termékszinten (vagyis egyedi termékek esetében).

### <a name="in-a-retail-catalog"></a>Kiskereskedelmi katalógusban

  [![createandmanageattribute-2](./media/createandmanageattribute-2.png)](./media/createandmanageattribute-2.png) Az attribútumok alapértelmezett értéke felülírható meghatározott katalógusokba tartozó egyedi termékek esetében, amelyek egy adott kiskereskedelmi csatornát céloznak meg.

### <a name="at-the-retail-channel-level"></a>Kiskereskedelmi csatorna szintjén

  [![createandmanageattribute-1](./media/createandmanageattribute-1.jpg)](./media/createandmanageattribute-1.jpg) Az attribútumok alapértelmezett értéke felülírható meghatározott katalógusokba tartozó egyedi termékek esetében, amelyek egy adott kiskereskedelmi csatornát céloznak meg.




