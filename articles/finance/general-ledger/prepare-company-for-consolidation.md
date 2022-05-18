---
title: Jogi személy előkészítése a konszolidációs folyamathoz
description: A konszolidációb során több jogi személy számláinak tranzakcióit foglalhatja össze egyetlen jogi személyhez tartozó számlakészletbe. Ez a témakör bemutatja a jogi személyek konszolidációra való előkészítését.
author: jinniew
ms.date: 10/30/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2018-10-30
ms.dyn365.ops.version: 8.0.1
ms.openlocfilehash: 0ef6736046748b92357c41d27eeedfc88c610d33
ms.sourcegitcommit: 602a319f4720b39a56b7660b530236912d484391
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/06/2022
ms.locfileid: "8722038"
---
# <a name="prepare-a-legal-entity-for-the-consolidation-process"></a>Jogi személy előkészítése a konszolidációs folyamathoz

[!include [banner](../includes/banner.md)]

A konszolidációb során több jogi személy számláinak tranzakcióit foglalhatja össze egyetlen jogi személyhez tartozó számlakészletbe. Ez a témakör bemutatja a jogi személyek konszolidációra való előkészítését.

> [!NOTE]
> Javasoljuk, hogy a Management Reporter for Microsoft Dynamics 365 Finance segítségével konszolidált formában egyesítse több jogi személy pénzügyi eredményeit. A Felügyeleti jelentéskészítő segítségével konszolidált pénzügyi jelentéseket készíthet több jogi személy között, az Excel segítségével importálhatja a konszolidációs adatokat más forrásokból, és összegeket fordíthat le bármely jelentési pénznemre anélkül, hogy futtatnia kell a Dynamics 365 Pénzügy konszolidációs folyamatát.

Ezután lehetősége van a konszolidált jogi személyből jelentéseket, például pénzügyi kimutatásokat kinyomtatni. A konszolidált jogi személy azonban nem használható napi tranzakciókhoz.

Akár olyan jogi személyek adatait is konszolidálhatja, amelyek eltérő adatbázisokat használnak, mint a konszolidált jogi személy. Ezt a konszolidációs folyamatot *import konszolidációnak* nevezik. Emellett a jogi személyek használhatják ugyanazt az adatbázist is, mint a konszolidált jogi személy. Ezt a konszolidációs folyamatot *online konszolidációnak* nevezik.

A konszolidált jogi személyben lesznek összsegyűjtve a leányvállalatok eredményei és egyenlegei. A konszolidált jogi személy konszolidációra való előkészítéséhez kövesse az alábbi lépéseket.

1. Nyissa meg a következőt: **Főkönyv \> Beállítás \> Szervezet \> Jogi személyek**.
2. Az **Új** gombra kattintva hozza létre a konszolidált jogi személynek szánt új jogi személyt.
3. Jelölje be a **Pénzügyi konszolidálási folyamatokhoz** jelölőnégyzetet, majd adja meg a konszolidált jogi személy adatait. Pontosan úgy adja meg az információkat, ahogyan szerepeltetni szeretné azokat a konszolidált jogi személy pénzügyi kimutatásaiban.
4. Zárja be a lapot.
5. Válassza ki a konszolidált jogi személyt az oldal jobb felső sarkában látható mezőben, majd válassza az **OK** gombot.
6. Ugorjon a **Főkönyv \> Beállítás \> Főkönyv** elemre.
7. Válassza ki a konszolidált jogi személy számlatükrét, pénzügyi naptárát, alapértelmezett pénznemét, opcionális jelentési pénznemét, és alapértelmezett árfolyamtípusát. 
8. Lépjen ide: **Főkönyv \> Beállítás \> Pénznem \> Pénznemek árfolyamtípusai**.
9. Adja meg a leányvállalatok pénznemeinek árfolyamait a releváns időszakokban.
10. Zárja be a lapot.
11. Ha a konszolidált jogi személy leányvállalatai külföldi pénznemt használnak, kövesse az alábbi lépéseket:

    1. Ugrás ide: **Főkönyv \> Beállítás \> Feladás \> Számlák az automatikus tranzakciókhoz**.
    2. A **Feladás típusa** mezőben válasszon ki egy megfelelő számlát:

        - Ha a jogi személy olyan külföldi leányvállalatokkal rendelkezik, amelyek pénzügyileg vagy működésileg függetlenek a szülő jogi személytől, válassza ki a **Konszolidációs különbségekhez tartozó eredményszámla** feladási típust.
        - Ha olyan leányvállalatot konszolidál, amely pénzügyileg és irányítását tekintve független az anyag jogi személytől, vagy olyan jogi személyt, amely több, pénzügyileg és irányítását tekintve az anya jogi személytől független leányvállalat eredményeit tartalmazza, és amennyiben az adatok konszolidálásához átszámítási módokat használ, akkor válasszon egy megfelelő számlát a **Konszolidációs különbségekhez tartozó mérlegszámla** feladási típushoz.

    3. A **Fő számla** mezőben válassza ki a devizaértékelés-korrekciókhoz használni kívánt fő számlát.
    4. Zárja be a lapot.

    Ha a konszolidált jogi személyt egy időszak elején hozza létre, akkor a devizaösszegek átértékelését a konszolidációs időszak során árfolyamváltozásként is elvégezheti.

Ezzel beállította a konszolidált jogi személyt a **Konszolidálás** ismétlődő feladathoz. Import konszolidációt vagy online konszolidációt végezhet.

- Az import konszolidációhoz lépjen ide: **Főkönyv \> Időszakos \> Konszolidálás \> Konszolidálás \[Importálás innen:\]**.
- Az online konszolidációhoz lépjen ide: **Főkönyv \> Időszakos \> Konszolidálás \> Konszolidálás \[Online\]**.

> [!NOTE]
> A konszolidáció feldolgozása előtt elő kell készítenie a leányvállalati jogi személyeket a konszolidációra. További információ: [Alárendelt jogi személy beállítása a konszolidációra](set-up-subsidiary-company-for-consolidation.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
