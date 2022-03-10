---
title: Minőségbiztosítási tesztműszerek
description: Ez a témakör azt mutatja be, hogyan lehet tesztműszereket létrehozni, amelyek a minőségi rendelések tesztjeihez használhatók a Microsoft Dynamics 365 Supply Chain Management alkalmazásban.
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
ms.openlocfilehash: 4d80a4f784a43e0d83d1f5b42f6740ef6da3add1
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/29/2021
ms.locfileid: "7565903"
---
# <a name="quality-management-test-instruments"></a>Minőségbiztosítási tesztműszerek

[!include [banner](../includes/banner.md)]

Ez a témakör azt mutatja be, hogyan lehet tesztműszereket létrehozni, amelyek a minőségi rendelések tesztjeihez használhatók a Microsoft Dynamics 365 Supply Chain Management alkalmazásban.

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
