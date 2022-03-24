---
title: TDS-adókódok csatolása a TDS-adócsoportokhoz, és a TDS kiszámításának képletének meghatározása
description: Ez a témakör elmagyarázza, hogyan lehet beállítani a levont adót a Forrás (TDS) adócsoportokban, és csatolni kell a TDS adókódokat a TDS adócsoportokhoz. A TDS-adócsoport TDS-ének kiszámításához meg kell határoznia a hozzá csatolt TDS-adókódok képletét.
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: ce4c2dcfb6ac6f95af3bc354412c36956ae63242
ms.sourcegitcommit: 6dc2b877cf8ea9185a07964ec05c5ddb7a78471b
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/12/2022
ms.locfileid: "8407485"
---
# <a name="attach-tds-tax-codes-to-tds-tax-groups-and-define-the-formula-for-calculating-tds"></a>TDS-adókódok csatolása a TDS-adócsoportokhoz, és a TDS kiszámításának képletének meghatározása

[!include [banner](../includes/banner.md)]

Ez a témakör elmagyarázza, hogyan lehet beállítani a levont adót a Forrás (TDS) adócsoportokban, és csatolni kell a TDS adókódokat a TDS adócsoportokhoz. A TDS-adócsoport TDS-ének kiszámításához meg kell határoznia a hozzá csatolt TDS-adókódok képletét.

Kövesse ezeket a lépéseket a TDS-adócsoport beállításához, csatolja hozzá a TDS-adókódokat, és határozza meg a TDS kiszámításának képletét.

1. Ugorjon az **Adó \> Közvetett adók \> Adóelőleg \> Adóelőlegcsoportok** elemre.

    [![Adóelőleg-csoportok oldal.](./media/apac-ind-TDS-29.png)](./media/apac-ind-TDS-29.png)

2. A Műveletablakban válassza az **Új** lehetőséget a TDS adóelőleg-csoportjának létrehozásához, és adja meg a szükséges adatokat.
3. Az **Adó típusa** mezőben válassza ki a **TDS** lehetőséget.
4. A **Beállítás** gyorsfülön válassza a **Hozzáadás** lehetőséget egy új sor létrehozásához.
5. Az **Adóelőlegkód** mezőben válassza ki a TDS-adócsoport TDS-adóelőlegkódját. Az **Adóelőlegnév** mező a TDS adókód nevét mutatja, az **Érték** mező pedig az értéket.
6. Ha figyelmen kívül szeretné hagyni a TDS-tranzakciók TDS-adókódjához csatolt TDS-adóösszetevőre meghatározott küszöbértéket és kivételküszöb-értéket, válassza a **Küszöbérték figyelmen kívül hagyása** jelölőnégyzetet.
7. Jelölje be a **Mentesít** jelölőnégyzetet, ha meg akarja előzni, hogy az adócsoport a tranzakciókban kiszámításra kerüljön.
8. A Műveletablakban válassza a **Tervező** lehetőséget a képlettervező megnyitásához, így meghatározhatja a TDS-adócsoport TDS-kiszámításának képletét. A **Tervező** lapon az **Adók** fülön láthatók a TDS-adócsoporthoz kiválasztott TDS-adókódok.

    [![Tervező oldal.](./media/apac-ind-TDS-30.png)](./media/apac-ind-TDS-30.png)

9. A **Számítás** fülön válassza az **Alt+N** lehetőséget egy sor létrehozásához. Az **azonosítómező** a TDS-számítás automatikusan generált prioritásazonosítóját mutatja.
10. Az **Adókód** mezőben válassza ki a TDS-adókódját a képlet meghatározásához. A TDS-adócsoporthoz kiválasztott összes TDS-adókód választható ebben a mezőben.
11. Az **Adóköteles összeg** mezőben válassza ki a TDS kiszámításának alapját:

    - **Bruttó összeg** – Számítsa ki a TDS-t a bruttó tranzakciós összeg (azaz a számla összege) alapján az adókódhoz definiált számítási kifejezéssel.
    - **Kiz. bruttó összeg** – Számítsa ki a TDS-t az adókódhoz definiált számítási kifejezés alapján.

    > [!NOTE]
    > Az **Adóköteles összeg** mező nem állítható be prioritásazonosítóval rendelkező TDS adókód **Kiz. bruttó összegére** **1**.

12. A TDS-számítás a TDS-adócsoporthoz csatolt minden egyes adókód **Számítási kifejezés** mezőjében meghatározott képleten alapul. Válassza a pluszjel (+), mínuszjel (-), szorzójel (\*) vagy osztásjel (/) gombot a kiválasztott TDS-adókódhoz tartozó számítási kifejezés megadásához a **Számítási kifejezés** mezőben.

    > [!NOTE]
    > Nem határozható meg számítási kifejezés az **1** prioritási azonosítóval rendelkező TDS-adókódhoz.

13. A **Számítási** kifejezés mezőben a TDS-adókód számítási kifejezésének meghatározásához adjon hozzá TDS-adókódokat, amelyek az **Adók** fülön érhetők el. A TDS-adókódok **Számítási kifejezés** mezőbe történő hozzáadásához az alábbi módszerek bármelyikét használhatja:

    - Húzza a szükséges adókódot az **Adók** fülről a **Számítási kifejezés** mezőbe.
    - Koppintson duplán (vagy kattintson duplán) a szükséges adókódra az **Adók** fülön.
    - Válassza ki és tartsa lenyomva (vagy kattintson a jobb gombbal) a szükséges adókódot az **Adók** fülön, majd válassza az **Adókód hozzáadása** lehetőséget.

    > [!NOTE]
    > Számítási kifejezés beszúrása minden TDS-adókód előtt. A számítási kifejezéshez hozzáadott TDS-adókódok zárójelben (\[...\]) jelennek meg.

14. A **Számítási kifejezés** mezőben található adókódhoz definiált számítási kifejezés törléséhez válassza a **C** gombot.
15. A **Számítás** fülön lévő rekord törléséhez válassza a **Törlés** lehetőséget.
16. Zárja be a lapot.
