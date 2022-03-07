---
title: Kifizetési díj beállítása TDS-hatósági fizetésekhez
description: Ez a témakör elmagyarázza, hogyan lehet beállítani a forrásnál levont adóért felszámított (TDS) hatósági kifizetéseknél kifizetési díjait.
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: b52331bb1c7a1bc2c764008112f3df9cc0385995
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023313"
---
# <a name="set-up-payment-fees-for-tds-authority-payments"></a>Kifizetési díj beállítása TDS-hatósági fizetésekhez

[!include [banner](../includes/banner.md)]

Ez a témakör elmagyarázza, hogyan lehet beállítani a forrásnál levont adóért felszámított (TDS) hatósági kifizetéseknél kifizetési díjait.

1. Ugrás a **Kötelezettségek \> Kifizetés beállítása \> Fizetési díj** elemre.

    [![Kifizetési díj oldal](./media/apac-ind-TDS-28.png)](./media/apac-ind-TDS-28.png)

2. Válassza az **Új** lehetőséget, hozzon létre egy kifizetési díjat, majd adja meg a szükséges adatokat.
3. A **Díj típusa** mezőben válassza ki a kifizetési díj típusát.

    - **None**
    - **Kamat** – A TDS-hatóság szállítójának teljesített késedelmes fizetések után kamatot számítunk fel.
    - **Egyebek** – A TDS-hatóság szállítójának teljesített késedelmes fizetések után egyéb díjakat számítunk fel.

    Ha a **Kamat** vagy az **Egyéb** lehetőséget választja, a **Költség** mező automatikusan **Főkönyvre** lesz beállítva.

4. Ha a **Mezőtípus** mezőben a **Kamat** vagy az **Egyebek** lehetőséget választotta, a **Főszámla** mezőben válassza ki a főkönyvszámlát, amire könyvelheti a kamatot vagy az egyéb díjakat.
5. Adja meg az egyéb szükséges adatokat.
6. A Műveletablakban válassza a **Fizetési díj beállítása** beállítást a **Fizetési díj beállítása** oldal megnyitásához, ahol beállíthatja a fizetési díjakat a bankok különböző kombinációihoz, a fizetési módokhoz, a fizetési előírásokhoz, a pénznemekhez és a dátumintervallumokhoz.

    [![Kifizetési díj beállítása oldal](./media/apac-ind-TDS-21.png)](./media/apac-ind-TDS-21.png)

7. Adja meg a **Csoportosítások** mező **Áttekintés** lapján, hogy mely bankokhoz állítja be a kifizetési díjat:

    - **Tábla** – Az díj egy adott bankszámlára érvényes.
    - **Csoport** – A díj egy adott bankcsoportra érvényes.
    - **Mind** – A díj minden bankszámlára érvényes.

8. Ha a **Csoportosítások** mezőben a **Tábla** vagy a **Csoport** lehetőséget választotta, akkor a **Bankkapcsolat** mezőben válassza ki azt a bankszámlát vagy bankcsoportot, amely számára beállítja a kifizetési díjat.
9. A **Kifizetési módszer** mezőben válassza ki kifizetési díjak megfizetésének fizetési módját.
10. A **Kifizetés meghatározása** mezőben válassza ki vagy írja be a **Kifizetés meghatározása** lapon létrehozott kifizetési előírás kódját.
    - A Fizetési meghatározás a kifizetések elektronikus alapok átutalási módjainak használatos.
12. A **Kifizetés pénzneme** mezőben válassza ki a pénznemet, ami aktiválja a díjat. Csak a kiválasztott pénznemet használó tranzakciók aktiválják a díjat. Ha üresen hagyja ezt a mezőt, minden pénznem aktiválja a díjat.
13. A **Százalék/összeg** mezőben válassza ki a számítási módot. A lehetőségek az **Összeg**, a **Százalék** és az **Intervallum**.
14. A **Díj összege** mezőben adja meg a díj összegét a kifizetés százalékaként vagy egy kifizetés összegeként.
15. A **Díj pénzneme** mezőben pontosítsa a díj pénznemének kódját.
16. Válassza az **Általános** lapot a kiválasztott bankszámla részleteinek megtekintéséhez vagy módosításához.

    [![Általános fül](./media/apac-ind-TDS-22.png)](./media/apac-ind-TDS-22.png)

16. A **Minimális** mezőben adja meg azt a minimális tranzakcióösszeget, amely aktiválja a díjat.
17. A **Maximális** mezőben adja meg azt a maximális tranzakcióösszeget, amely aktiválja a díjat.
18. A Költségek kiszámításához a **Kezdő dátum** és a **Befejező dátum** mezőkben határozzon meg egy dátumtartományt.
19. A **Minimális díj** mezőben adja meg a díj összegét a kifizetés százalékaként vagy egy kifizetés összegeként.
20. Az **Áfacsoport** mezőben válassza ki az áfa összegének kiszámításához használt áfacsoportot.
21. A **Cikkáfacsoport** mezőben válassza ki a cikkáfa összegének kiszámításához használt áfacsoportot.
22. Válassza ki az **Intervallum** lapot. 

    [![Intervallum lap](./media/apac-ind-TDS-23.png)](./media/apac-ind-TDS-23.png)

23. A **Napok** mezőben adja meg a kifizetés feladási dátuma (engedményezés dátuma) és a kötelezvény határideje között eltelt napok számát.
24. A **Százalék/Összeg** mezőben adja meg, hogy százalék vagy meghatározott összeg-e a meghatározás.
25. A **Díj összege** mezőben adja meg a díj összegét a kifizetés százalékaként vagy egy kifizetés összegeként.
26. Zárja be a **Kifizetési díj beállítása** lapot.
27. Zárja be a **Kifizetési díj** lapot.
