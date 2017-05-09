---
title: "Attribútumok létrehozása és kezelése"
description: "Ez a cikk a Microsoft Dynamics 365 for Operations attribútumait írja le. Az attribútumokkal leírhat egy terméket és annak jellemzőit a felhasznál által meghatározott mezők segítségével."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 16461
ms.assetid: 2b85491c-f830-4e79-a2cb-681b7ced6988
ms.search.region: global
ms.search.industry: Retail
ms.author: prabhup
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 26c628e10aaa5f47bc87d7510ca8f41ab3630204
ms.lasthandoff: 03/31/2017


---

# <a name="create-and-manage-attributes"></a>Attribútumok létrehozása és kezelése

Ez a cikk a Microsoft Dynamics 365 for Operations attribútumait írja le. Az attribútumokkal leírhat egy terméket és annak jellemzőit a felhasznál által meghatározott mezők segítségével.

Az attribútumokkal leírhat egy terméket és annak jellemzőit a felhasznál által meghatározott mezők segítségével. Például megadhatja a termék memóriaméretét vagy merevlemez-kapacitását, és jelezheti, hogy a termék megfelel-e az Energy star előírásoknak. Az attribútumok különböző kiskereskedelmi entitásokhoz, például termékkategóriákhoz és kiskereskedelmi csatornákhoz, társíthatók, és megadhatók hozzájuk alapértelmezett értékek. A termékek öröklik az attribútumaikat és a hozzájuk tartozó alapértelmezett értékeket, amikor társítják őket egy termékkategóriához vagy kiskereskedelmi csatornához. Az alapértelmezett értékek felülírhatók az egyes termékek és a kiskereskedelmi csatorna szintjén vagy a kiskereskedelmi kategóriában.

#### <a name="examples"></a>Példák

Kategória

Attribútum

Megengedett értékek

Alapértelmezett érték

TV és videó

Márka

Bármilyen érvényes **Márka** érték

Egyik sem

TV

Képernyőméret

**20"**–**80"**

Egyik sem

Függőleges felbontás

**480i**, **720p**, **1080i** vagy **1080p**

**1080p**

Képernyő-frissítési gyakoriság

**60hz**, **120hz** vagy **240hz**

**60hz**

HDMI-bemenetek

**0**–**10**

**3**

DVI-bemenetek

**0**–**10**

**1**

Kompozit bemenetek

**0**–**10**

**2**

Komponens bemenetek

**0**–**10**

**1**

LCD

3D Ready

**Igen** vagy **Nem**

**Igen**

3D Enabled

**Igen** vagy **Nem**

**Nem**

Plazma

Min. üzemhőmérséklet

**32**–**110** fok

**32**

Max. üzemhőmérséklet

**32**–**110** fok

**100**

Projektoros

Képcsőgarancia

**6**, **12** vagy **18** hónap

**12**

Képcsövek száma (\# képcső)

**1**–**5**

**3**

## <a name="attribute-type"></a>Attribútumtípus
  [![attributes-fixed-copy](./media/attributes-fixed-copy.png)](./media/attributes-fixed-copy.png) Az attribútumok az attribútumtípusokon alapulnak. Az attribútumtípusok az adott attribútumba bevihető adatok típusát azonosítják. Jelenleg a Microsoft Dynamics 365 for Operations a következő attribútumtípusokat támogatja:

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


