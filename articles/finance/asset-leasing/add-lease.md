---
title: Lingek hozzáadása vagy másolása (előzetes verzió)
description: Ez a témakör azt mutatja be, hogyan lehet új lízinget létrehozni az eszközlízingben való adatok megadásával vagy egy meglévő lízing adatainak másolásával.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 706b245971ba065bae86e31853832f721a6f9aff
ms.sourcegitcommit: aeee39c01d3f93a6dfcf2013965fa975a740596a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/28/2020
ms.locfileid: "4444189"
---
# <a name="add-or-copy-leases-preview"></a>Lingek hozzáadása vagy másolása (előzetes verzió)

[!include [banner](../includes/banner.md)]

Ez a témakör azt mutatja be, hogyan lehet a nulláról új lízinget létrehozni az eszközlízingben, illetve hogyan lehet lízinget létrehozni egy meglévő lízing adatainak másolásával. A lízingek nulláról való létrehozásának folyamata az új lízing adatainak megadását, majd a lízing ütemezés létrehozását jelenti. Ha legalább egy lízing be van állítva, akkor könnyebben megtalálhatja az adatok meglévő lízingből történő másolását, majd az új lízing létrehozásához szükséges adatok szerkesztését.

## <a name="create-a-lease"></a>Lízing létrehozása

A következő lépéseket követve hozzon létre egy lízinget az Eszközlízingben.

1. A **Lízing összefoglalása** lap műveleti paneljén válassza ki az **Új** elemet.
2. Adja meg a lízing adatait. A kötelezően kitöltendő mezők piros szegéllyel rendelkeznek.

## <a name="create-a-lease-schedule"></a>Lízingütemezés létrehozása

Miután befejezte a lízing adatainak megadását, hajtsa végre az alábbi lépéseket a lízingütemezés létrehozásához.

> [!NOTE]
> Előfordulhat, hogy a pénzügyi dimenziók a saját pénzügyi dimenziók alapján változnak.

1. A lízingkönyvek létrehozásához válassza az **Ütemezések létrehozása** lehetőséget. A lízingek tartalmazzák a kifizetést, az amortizációt, az értékcsökkenést és a költségütemezéseket.
2. A lízingek eléréséhez és az újonnan létrehozott ütemezések megtekintéséhez válassza ki a **Könyvek** fület.

    A **Könyv részletei** lap mutatja, hogy a lízinget milyen módon kell elszámolni a hozzárendelt könyvek között. Itt megtekintheti a lízingütemezéseket.

    A fizetési ütemezés tartalmazza a **Lízing hozzáadása** lap **Fizetési ütemezés sorai** fül bemeneteit. Továbbra is módosíthatja az egyes kifizetési összegeket és a változó fizetéseket. A lízingkötelezettséget a módosított fizetési ütemezés alapján számítja ki a program.

4. Miután befejezte a kifizetési ütemezés áttekintését, jelölje be az **Ütemezés jóváhagyása** jelölőnégyzetet. Az ütemezés megerősítése után a lízing már nem érhető el szerkesztésre.

    > [!NOTE]
    > A rendszer automatikusan kiszámítja a lízing feltételeit a **Lízing hozzáadása** lap kifizetési ütemezés soraiból.
    >
    > A lízingfutamidő hónapok szerinti kiszámításához a rendszer megkeresi az adott fizetési ütemezési sor kezdő és záró dátuma közötti különbséget. Ezt követően továbblép a következő fizetési ütemezési sorra, és megkeresi a különbözetet. Végezetül a rendszer az összes összegből összegzi a lízing feltételeit hónapok szerint.

5. A kiszámított időszakok kamatráfordításainak megtekintéséhez nyissa meg a **Lízingkötelezettség amortizációjának ütemezése** lapot. A számított lineáris értékcsökkenés megtekintéséhez nyissa meg az **Eszköz értékcsökkenésének ütemezése** lapját.
6. Miután befejezte a számított összeg áttekintését, létre lehet hozni a kezdeti felismerési napló bejegyzését a **Kezdeti felismerés** oldalon. Egy üzenet jelenik meg, amely jelzi, hogy a napló létrejött.

    > [!NOTE]
    > A naplóbejegyzés nem kerül feladásra a Főkönyvbe mindaddig, amíg a bejegyzést manuálisan fel nem adja.

7. Ha a feladást megelőzően át szeretné tekinteni a javasolt kezdeti felismerési bejegyzést, válassza ki az **Eszközlízing naplók** lehetőséget.

    > [!NOTE]
    > Az Eszközlízing napló nem hozható létre manuálisan. Automatikusan létrejön a lízingütemezések létrehozásakor.

8. Amikor befejezte a kezdeti felismerési napló bejegyzésének áttekintését, és készen áll a feladásra, válassza a **Feladás** lehetőséget, ha a Főkönyvben a használaton kívüli (ROU) eszközt és lízingkötelezettséget szeretné elismerni.

## <a name="copy-a-lease"></a>Lízing másolása

Az eszközlízing lehetővé teszi egy lízing adatainak másolását egy olyan új lízing létrehozásához, amelynek ugyanazok az adatai. Ezt követően módosíthatja a lízing mezőket, mielőtt létrehozza a másolt lízing ütemezését.

1. Válassza ki a másolni kívánt lízinget a **Lízing összegzése** oldalon, majd a művelet ablaktáblán válassza a **Lízing másolása** parancsot.

    > [!NOTE]
    > Ha a **Manuális** paraméter ki van kapcsolva a lízingazonosítók számsorozatához, a program automatikusan létrehozza a sorban szereplő következő számot a másolt lízing azonosítójaként. Ha a **Manuális** paraméter be van kapcsolva, akkor egy üzenet jelenik meg, amely kéri, hogy adja meg a lízingazonosítót, mielőtt továbblép a lízing másolásával.

2. Válassza a **Másolás** parancsot. A kiválasztott lízing adatait a program átmásolja egy új lízingbe. Ezután a mentés előtt szerkesztheti az új lízing adatait, és létrehozhatja a lízingütemezéseket.

## <a name="asset-leasing-journal"></a>Eszközlízing-napló

Az eszközlízing-naplóban létrehozott összes naplóbejegyzés az eszközlízing naplóban szerepel. Az **Eszközlízing-napló** oldalon (**Eszközlízing \> Naplóbejegyzések \> Eszközlízing-napló**) a megadott naplóbejegyzések és bizonylatok megtekintése, valamint a feladatlan naplóbejegyzések feladása alapján szűrhet.

> [!NOTE]
> Az Eszközlízing napló nem hozható létre manuálisan. Automatikusan létrejön a lízingütemezések létrehozásakor.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]