---
title: Szabadszöveges számlasablon létrehozása
description: Ez az eljárás bemutatja a szabadszöveges számla sablon létrehozását.
author: abruer
ms.date: 05/29/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1477227228ae9f79314d1e3b6da73446d660d108
ms.sourcegitcommit: 408786b164b44bee4e16ae7c3d956034d54c3f80
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/05/2021
ms.locfileid: "7753692"
---
# <a name="create-a-free-text-invoice-template"></a>Szabadszöveges számlasablon létrehozása

[!include [banner](../includes/banner.md)]

Ez az eljárás az USMF bemutatócéget használja. Az eljárást az a felhasználó használja, aki felelős a kintlévőségek számláinak kezeléséért és feldolgozásáért.

## <a name="create-a-template"></a>Sablon létrehozása

1. Ugrás a Kinnlevőségek > Számlák > Ismétlődő számlák > Szabadszöveges számlasablonok pontra.
    * A képernyőn szabadszöveges számlasablonokat hozhat létre, amelyek számlasorokat, költségeket, könyvelési felosztási sablont és főkönyvi számlainformációkat tartalmazhatnak.  
2. Új szabadszöveges számlasablon létrehozásához kattintson az „Új” elemre.
3. Írjon be egy értéket a Sablonnév mezőbe.
    * A „Sablonnév” egyedileg azonosítja a szabadszöveges számla sablonját. Egy „Sablonnév” csakis egyetlen sablonhoz tartozhat.  
4. Adja meg a sablon leírását a Leírás mezőben.
5. Bontsa ki a Számlasorok lapot.
6. A Leírás mezőbe írja be a számlasor leírását.
7. A fő számla mezőben válasszon ki egy bevételi számlát.
    * Egy vevői jóváírás ellentranzakciójának számláját a teljes számlaösszeghez a Vevői feladási profilok lapján választhatja ki.  
8. Az Áfacsoport mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
    * Az aktuális számlasor áfacsoportja, amely a vevőkód alapértelmezett áfacsoportja.  
9. A listában kattintson a kijelölt sorban lévő hivatkozásra.
10. A Cikkáfacsoport mezőben válassza ki az aktuális számlasorhoz tartozó cikkáfacsoportot.
11. A listában kattintson a kijelölt sorban lévő hivatkozásra.
12. Az Egységár mezőben megadhatja vagy megtekintheti a számlasor egységárát.
    * A rendszer ezt az összeget megszorozza a Mennyiség mezőben szereplő értékkel, így határozza meg a számlasor összegét.  
13. Adjon új sort a szabadszöveges számlasablonhoz.
14. A Leírás mezőbe írja be a számlasor leírását.
15. A fő számla mezőben válasszon ki egy bevételi számlát.
    * Egy vevői jóváírás ellentranzakciójának számláját a teljes számlaösszeghez a Vevői feladási profilok lapján választhatja ki.  
16. Az Áfacsoport mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
    * Az aktuális számlasor áfacsoportja, amely a vevőkód alapértelmezett áfacsoportja.  
17. A listában kattintson a kijelölt sorban lévő hivatkozásra.
18. A Cikkáfacsoport mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
    * Az aktuális számlatételhez tartozó cikkáfacsoport.  
19. A listában kattintson a kijelölt sorban lévő hivatkozásra.
20. Megadhatja vagy megtekintheti a számlasoron szereplő egységek számát
    * A rendszer ezt a számot megszorozza az Egységár mezőben szereplő értékkel, így határozza meg a számlasor összegét.  
21. Megadhatja vagy megtekintheti a számlasor egységárát. 
    * A rendszer ezt az összeget megszorozza a Mennyiség mezőben szereplő értékkel, így határozza meg a számlasor összegét.  
22. Megtekintheti és módosíthatja a könyvelési felosztást egy adott sorhoz és annak gyermeksoraihoz.
    * A könyvelési felosztások használatával lehet meghatározni, hogy hogyan lesz az összeg elszámolva, például hogyan lesznek könyvelve a bevételek, adó és költségek a szabadszöveges számlán.  
23. Frissítheti a könyvelési felosztást a kiválasztott számlasorhoz.
24. Kattintson a Bezárás gombra.

## <a name="save-a-free-text-invoice-as-a-template"></a>Szabadszöveges számla sablonként mentése
Egy meglévő szabadszöveges számlát menthet sablonként is. Kiválasztásakor a Mentés sablonhoz a Számla lapjáról, adja meg a sablon nevét és leírását. Ha ilyen nevű sablon már létezik, értesítés jelenik meg, hogy már létezik ilyen nevű sablon. Még rákattinthat a felülíráshoz az OK gombra. 


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
