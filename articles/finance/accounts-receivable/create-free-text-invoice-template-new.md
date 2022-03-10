---
title: Szabadszöveges számlasablon létrehozása
description: Ez az eljárás bemutatja a szabadszöveges számla sablon létrehozását.
author: abruer
ms.date: 02/15/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7baa29ad341bdf7ff874bd7f69cf483b7afc075a
ms.sourcegitcommit: 6102f70d4595d01b90afe5b23dfd8ec2ea030653
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/16/2022
ms.locfileid: "8182509"
---
# <a name="create-a-free-text-invoice-template"></a>Szabadszöveges számlasablon létrehozása

[!include [banner](../includes/banner.md)]

Ez az eljárás az USMF bemutatócéget használja. Az eljárást az a felhasználó használja, aki felelős a kintlévőségek számláinak kezeléséért és feldolgozásáért.

## <a name="create-a-template"></a>Sablon létrehozása

1. Ugrás a Kinnlevőségek **> számlákhoz > az ismétlődő számlákhoz > szabadszöveges számlasablonok esetén**.
    * Ezen a lapon létrehozhat olyan szabadszöveges számlasablonokat, amelyek számlasorokat, költségeket, könyvelési felosztási sablont és főkönyvi számlaadatokat tartalmazhatnak.  
2. Új **szabadszöveges** számlasablon létrehozásához kattintson az Új gombra.
3. A Sablon **neve mezőbe** írjon be egy értéket.
    * A „Sablonnév” egyedileg azonosítja a szabadszöveges számla sablonját. Egy „Sablonnév” csakis egyetlen sablonhoz tartozhat.  
4. A Leírás **mezőbe** írja be a sablon leírását.
5. Bontsa ki **a Számlasorok lapot**.
6. A Leírás **mezőbe** írja be a számlasor leírását.
7. A Fő számla **mezőben** válasszon ki egy bevételi számlát.
    * A vevői jóváírás ellentranzakciós számláját a **vevői feladási profilok lapján lehet kiválasztani a teljes számlaösszegre**.  
8. Az Áfacsoport **mezőben** kattintson a legördülő gombra a keresés megnyitásához.
    * Az aktuális számlasor áfacsoportja, amely a vevőkód alapértelmezett áfacsoportja.  
9. A listában kattintson a kijelölt sorban lévő hivatkozásra.
10. A Cikkadócsoport **mezőben** válassza ki az aktuális számlasor cikk áfacsoportját.
11. A listában kattintson a kijelölt sorban lévő hivatkozásra.
12. Az Egységár **mezőben** adja meg vagy tekintse meg a számlasor egységárát.
    * Ezt az összeget a Mennyiség **mezővel** megszorozva határozzák meg a számlasor összegét.  
13. Adjon új sort a szabadszöveges számlasablonhoz.
14. A Leírás **mezőbe** írja be a számlasor leírását.
15. A Fő számla **mezőben** válasszon ki egy bevételi számlát.
    * A vevői jóváírás ellentranzakciós számláját a **vevői feladási profilok lapján lehet kiválasztani a teljes számlaösszegre**.  
16. Az Áfacsoport **mezőben** kattintson a legördülő gombra a keresés megnyitásához.
    * Az aktuális számlasor áfacsoportja, amely a vevőkód alapértelmezett áfacsoportja.  
17. A listában kattintson a kijelölt sorban lévő hivatkozásra.
18. A **Cikkáfacsoport** mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
    * Az aktuális számlatételhez tartozó cikkáfacsoport.  
19. A listában kattintson a kijelölt sorban lévő hivatkozásra.
20. A számlasorhoz tartozó egységek számának be- vagy megtekintése.
    * A rendszer ezt a számot megszorozza az Egységár mezőben szereplő értékkel, így határozza meg a számlasor összegét.  
21. Megadhatja vagy megtekintheti a számlasor egységárát. 
    * Ezt az összeget a Mennyiség **mező** értékével megszorozva határozzák meg a számlasor összegét.  
22. Megtekintheti és módosíthatja a könyvelési felosztást egy adott sorhoz és annak gyermeksoraihoz.
    * A könyvelési felosztások használatával lehet meghatározni, hogy hogyan lesz az összeg elszámolva, például hogyan lesznek könyvelve a bevételek, adó és költségek a szabadszöveges számlán.  
23. Frissítheti a könyvelési felosztást a kiválasztott számlasorhoz.
24. Kattintson a **Bezárás** gombra.

## <a name="save-a-free-text-invoice-as-a-template"></a>Szabadszöveges számla sablonként mentése
Egy meglévő szabadszöveges számlát menthet sablonként is. Amikor a Számla lapon **a Mentés** sablonba lehetőséget **választja**, adja meg a sablon nevét és leírását. Ha ilyen nevű sablon már létezik, értesítés jelenik meg, hogy már létezik ilyen nevű sablon. Az OK gombra kattintva **is** lecserélheti. 


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
