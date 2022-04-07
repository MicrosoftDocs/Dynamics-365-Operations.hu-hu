---
title: Beosztások
description: Ez a témakör azokat a fogalmi elemeket írja le, amelyeket a beosztások tartalmazhatnak. Példákkal szolgál arra is, hogyan használhatók ezek az elemek a szervezeten belül.
author: twheeloc
ms.date: 06/24/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmPosition, HcmPersonnelManagementWorkspace
audience: Application User
ms.author: twheeloc
ms.reviewer: twheeloc
ms.search.scope: Human Resources
ms.custom: 269054
ms.search.region: Global
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: b0b11458ac5d41d08a245a1f5aa48fb4633ae075
ms.sourcegitcommit: d67f7edaf1a50077c2a7dd105e774f86fc586495
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/02/2022
ms.locfileid: "8534301"
---
# <a name="positions"></a>Beosztások


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Ez a témakör azokat a fogalmi elemeket írja le, amelyeket a beosztások tartalmazhatnak. Példákkal szolgál arra is, hogyan használhatók ezek az elemek a szervezeten belül.

Beosztás létrehozása előtt be kell állítani egy feladatot. Bizonyos beosztásadatok– például a kompenzációs régió, a dolgozó hozzárendelése, a beosztás időtartama és a jelentési kapcsolat – érvényessége dátumalapú.

## <a name="general-information"></a>Általános információk

Beosztás létrehozásakor ki kell választania egy feladatot. A rendszer a kiválasztott feladatból automatikusan kitölti a következő adatokat:

- Leírás
- Megszólítás
- Teljes munkaidőssel egyenértékű
- Feladatcsalád

A beosztás címe az alkalmazott beosztására való hivatkozásban használatos. (Az alkalmazott címében szereplő cím nincs használva.) Ezért a beosztások címét a lehető legnagyobb mértékben szabványosítani kell.

> [!NOTE]
> A dolgozókat nem lehet olyan dátummal hozzárendelni egy beosztáshoz, amely a hozzárendeléshez való elérhetőség dátuma előtt van.
>
> A **Human Resource megosztott paraméterei** oldal **Pozíciók** lapján található paraméter határozza meg a dolgozó-hozzárendelés működését. Válasszon a következő értékek közül:
>
> - **Mindig** – Hozzárendelheti a dolgozókat az új beosztásokhoz, amikor beosztásokat hoz létre. Beosztások létrehozásakor az **Elérhető hozzárendeléshez** dátum és az idő az **Általános** lapon, a **Beosztás** oldalon automatikusan a létrehozási dátum és idő lesz.
> - **Soha** – Nem rendelheti hozzá a dolgozókat az új beosztásokhoz, amikor beosztásokat hoz létre. Ha ezt a lehetőséget választja, minden új beosztáshoz meg kell nyitnia a **Pozíció** lapot, amint az elérhetővé válik. Ezután az **Általános** lapon adja meg az **Elérhető hozzárendeléshez** dátumot, hogy engedélyezze a dolgozó hozzárendelését. Ha ezt a lehetőséget választja, a dolgozó hozzárendelésének dátuma alapértelmezés szerint **Soha** lesz, amikor megpróbálja hozzárendelni a dolgozót.

## <a name="position-duration"></a>Beosztás időtartama

Minden beosztás egy meghatározott ideig hatályos – ezt nevezik időtartamnak. Például a nyári beosztások időtartama lehet: 2021. május 1-től 2021. augusztus 31-ig. Az aktiválás dátuma az a dátum, amikor a beosztás aktívvá válik a rendszerben. A kivezetés dátuma az a dátum, amikor a beosztás inaktívvá válik a rendszerben.

Ne feledje, hogy sem a Elérhető hozzárendeléshez dátum, sem a dolgozó hozzárendelésének dátuma nem lehet az aktiválás dátuma előtti időpont. Az aktiválási dátum elérése előtt a pozíció nem számít aktívnak. Ezenkívül a dolgozó-hozzárendelés nem nyúlhat túl a beosztás kivezetésének dátumán.

## <a name="reports-to-position"></a>Felettes beosztás

A beosztások a szervezeti hierarchia alacsonyabb szintjének fontos részei. A **Pozíció** oldalon megadhatja azt a beosztást, amely felé az adott beosztásnak jelentenie kell. Ha hozzárendel egy dolgozót egy olyan pozícióhoz, amely egy másik pozíció számára jelent, akkor jelentési kapcsolatot hoz létre az ehhez a két beosztáshoz hozzárendelt dolgozók között. Például a 000220 beosztás a 000300 beosztásnak tesz jelentést. A 000220 beosztáshoz Kim Akers, a 000300 beosztáshoz pedig Sanjay Patel kerül hozzárendelésre. Így Kim Akers Sanjay Sanjay számára jelent.

> [!TIP]
> A felettes beosztásokat a rendszer annak meghatározására használja, hogy ki egy adott alkalmazott felettese. Az előző példában, ha a vezető beosztás Sanjay Patelhez van hozzárendelve a rendszerben, akkor Kim Akers közvetlenül jelentőként fogja látni a Vezetői önkiszolgáló rendszerben. A jelentési kapcsolatot munkafolyamat-útvonaltervezési szabályok és ellenőrzőlista-feladatok létrehozása során is fel lehet használni.

## <a name="relationships"></a>Kapcsolatok

Ha a szervezet mátrixhierarchiát vagy más egyéni hierarchiát használ, beosztáshierarchia-típusokat állíthat be. Ezután minden beállított hierarchiatípus beosztásaihoz hozzá lehet adni a jelentési kapcsolatokat. Például Lori Penor az Adventure Works általános igazgatója, így hozzá van rendelve az **Általános igazgató** beosztáshoz. Lori kezeli a fejlesztését egy olyan terméknek, amely különböző eszközök tisztítására szolgál. Könyvelőt igényel, hogy segítsen neki a pénzügyekben. Ezért felvette Kim Akerst könyvelőnek. Kim közvetlenül Sanjay Patel felé jelent, ugyanakkor együtt dolgozik Lori Penorral is, aki szintén az eszköztisztító fejlesztésével kapcsolatos pénzügyek kezelésében vesz részt.

Az előző példához a következő feladatokat kellene végrehajtani Kim Akers és Lori Penor munkakapcsolatának beállításához:

1. Egyéni pozícióhierarchia létrehozása **Eszköz** néven az eszköztisztító termék fejlesztéséért felelős beosztásokat magában foglaló hierarchia létrehozásához.
2. Az **Általános igazgató** pozíció megadása olyan beosztásként az **Eszköz** hierarchiában, amelynek Kim beosztása jelent.
3. A beosztáshierarchia a pozíciók jelentési szerkezetének megtekintésére használható. Ha több beosztáshierarchiával rendelkezik, a beosztáshierarchia minden egyes hierarchiatípusához kapcsolódóan megtekintheti a hierarchiákat. Emellett a pozícióazonosító vagy a beosztáshoz hozzárendelt dolgozó neve alapján is megkereshet a pozíciókat. A beosztáshierarchia egy szervezeti hierarchia.

## <a name="labor-union"></a>Szakszervezet

Rögzítheti, hogy a beosztáshoz szükséges-e szakszervezeti megállapodás, és hogy melyik szakszervezetet kell használni. A megállapodást jogi személyhez is társíthatja.

## <a name="financial-dimensions"></a>Pénzügyi dimenziók

A beosztások pénzügyi dimenziójának létrehozásakor meg kell adnia egy jogi személyt. Az egyes dimenziók alapértelmezett dimenzióit egyenként is kiválaszthatja. Másik lehetőségként kiválaszthat egy elosztási sablont az alapértelmezett dimenziók automatikus kitöltéséhez. Az elosztási sablonok lehetőséget biztosítanak az összegek több dimenzióérték közötti felosztására is.
