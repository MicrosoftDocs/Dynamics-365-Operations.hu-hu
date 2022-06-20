---
title: Minőségbiztosítási tesztműszerek
description: Ez a témakör azt mutatja be, hogyan lehet létrehozni olyan tesztmszereket, amelyek a Microsoftnál a minőségi rendeléseken végzett tesztekhez használhatók Dynamics 365 Supply Chain Management.
author: yufeihuang
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestInstrument
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 36b712e6a99a0625af28ef121d0c9c39c1e32603
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8857663"
---
# <a name="quality-management-test-instruments"></a>Minőségbiztosítási tesztműszerek

[!include [banner](../includes/banner.md)]

Ez a témakör azt mutatja be, hogyan lehet létrehozni olyan tesztmszereket, amelyek a Microsoftnál a minőségi rendeléseken végzett tesztekhez használhatók Dynamics 365 Supply Chain Management.

A **Teszteszközök** lapon lehet meghatározni és megtekinteni a minőségi rendeléseken végzett tesztekhez használt eszközök részletes adatait. Ezek a műszerek opcionálisak. A minőségbiztosító dolgozóknak segíthet ezzel, hogy tudják, milyen eszközt vagy szerszámot kell használniuk egy adott teszt elvégzéséhez.

## <a name="test-instrument-example"></a>Tesztműszer – példa

Különféle teszteket végez a elektromos alkatrészeken. Egyes tesztek az összetevők kimeneti feszültéségét ellenőrzik, egy teszt a hőmérsékletüket, és egy teszt a súlyukat. Az egyes tesztek végrehajtásához különböző szerszámok, eszközök és berendezések használhatók. Például egy voltmérő segítségével mérik a feszültséget a hőmérsékletet egy hőmérővel, a súly mérésére pedig mérleget használnak. Ezeket az eszközöket konfigurálni lehet tesztműszerként, és jelezni lehet, hogy a teszteredményeket milyen mértékegységgel kell rögzíteni. Például a feszültségmérő eredményeit a voltokban rögzítik, a hőmérőből származó eredményeket Fahrenheitben vagy Celsiusban, a mérlegből származó eredményeket pedig fontban vagy kilogrammban rögzíti a rendszer.

## <a name="create-a-test-instrument"></a>Tesztműszer létrehozása

1. Ugorjon a **Készletkezelés \> Beállítás \> Minőség-ellenőrzés \> Tesztműszerek** elemre.
1. A műveleti ablakpanelen válassza ki az **Új** lehetőséget, ha hozzá szeretne adni egy sort a rácshoz. Ezután új sorhoz állítsa be a következő mezőket:

    - **Tesztműszer** – Adja meg a tesztműszer egyedi azonosítóját vagy nevét.
    - **Leírás** – Adja meg a tesztműszer részletes leírását.
    - **Egység** – válassza ki a mértékegységet, amelyben a tesztműszer mér. A Program automatikusan bejelzi a **Pontosság** mezőt a kiválasztott mértékegység alapján.

1. Zárja be a lapot.

## <a name="additional-resources"></a>További erőforrások

- [Minőségbiztosítási teszt](quality-tests.md)
- [Minőségbiztosítási tesztcsoportok](quality-test-groups.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
