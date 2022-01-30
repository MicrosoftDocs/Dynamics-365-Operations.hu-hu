---
title: Lingek hozzáadása vagy másolása (előzetes verzió)
description: Ez a témakör azt mutatja be, hogyan lehet új lízinget létrehozni az eszközlízingben való adatok megadásával vagy egy meglévő lízing adatainak másolásával.
author: moaamer
ms.date: 01/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: b09a87c7d4f5ba076647218c3586d17a13e6c558
ms.sourcegitcommit: 7adf9ad53b4e6d1c4d5d612ce0977b76c61ec173
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/13/2022
ms.locfileid: "7967926"
---
# <a name="add-or-copy-leases-preview"></a>Lingek hozzáadása vagy másolása (előzetes verzió)

[!include [banner](../includes/banner.md)]

Ez a témakör azt mutatja be, hogyan lehet a nulláról új lízinget létrehozni az eszközlízingben, illetve hogyan lehet lízinget létrehozni egy meglévő lízing adatainak másolásával. A lízingek nulláról való létrehozásának folyamata az új lízing adatainak megadását, majd a lízing ütemezés létrehozását jelenti. Ha legalább egy lízing be van állítva, akkor könnyebben megtalálhatja az adatok meglévő lízingből történő másolását, majd az új lízing létrehozásához szükséges adatok szerkesztését.

## <a name="create-a-lease"></a>Lízing létrehozása

A következő lépéseket követve hozzon létre egy lízinget az Eszközlízingben.

1. A **Lízing összefoglalása** lap műveleti paneljén válassza ki az **Új** elemet.
2. Adja meg a lízing adatait. A kötelezően kitöltendő mezők piros szegéllyel rendelkeznek.

A bérleti díj kezdő dátuma nem lehet korábbi a bérlet kezdő dátumán. Ha a bérlet kezdő dátumán korábbi dátumot ad meg a bérleti díj kifizetésére, akkor hibaüzenetet kap.

Alapértelmezés szerint a Bérlet részletei lap Általános gyorslapján a Fizetési összeg lebontása beállítás Nem beállítás van megjelölve, ha a Fizetéslebontás engedélyezése az Eszköz paraméterei lapon Az Igen **beállítás** **van** **·** **·** **·** **·** **megjelölve**. 

Ha a Kifizetés összegének lebontása beállítás Igen, a Fizetési ütemezés sorai gyorsábra Fizetési összeg **mezője** **·** **·** **zárolva** van. Ez lesz a kifizetés összegének összesítése, amely a kifizetési összegeket lebontó katalógusból később **van** beállítva.

Válassza **ki a Kifizetés összegének** lebontását egy olyan lap megnyitásához, ahol hozzáadhatja a részletezett kifizetéstípusokat. Az **Összegek hozzáadása a kifizetés összeghez gombja az összegeket a Kifizetés összege** **mezőbe** mozgatja.

> [!NOTE]
> Ha egy tételes kifizetési összeget ad hozzá, majd az Esc billentyűt választja, a beírt összegek nem kerülnek be a Fizetési ütemezés sorai gyorsbillentyű Fizetési ütemezés **sorai** **·** **mezőbe**. Ehelyett a Kifizetés összegeit részletező párbeszédpanelen **tárolja** őket a rendszer. Ha azt szeretné, hogy a párbeszédpanelen a teljes összeg látható, válassza az Összeg oszlopot, válassza ki és tartsa lenyomva (vagy kattintson a jobb **gombbal**), majd válassza az Összesítés ezt az **oszlopot**. 

A **Sor** másolása gomb a részletezett kifizetés részletezését másolja.

## <a name="create-a-lease-schedule"></a>Lízingütemezés létrehozása

Miután befejezte a lízing adatainak megadását, hajtsa végre az alábbi lépéseket a lízingütemezés létrehozásához.

> [!NOTE]
> Előfordulhat, hogy a pénzügyi dimenziók a saját pénzügyi dimenziók alapján változnak.

1. A lízingkönyvek létrehozásához válassza az **Ütemezések létrehozása** lehetőséget. A lízingek tartalmazzák a kifizetést, az amortizációt, az értékcsökkenést és a költségütemezéseket.
2. A lízingek eléréséhez és az újonnan létrehozott ütemezések megtekintéséhez válassza ki a **Könyvek** fület.

    A **Könyv részletei** lap mutatja, hogy a lízinget milyen módon kell elszámolni a hozzárendelt könyvek között. Itt megtekintheti a lízingütemezéseket.

    A fizetési ütemezés tartalmazza a **Lízing hozzáadása** lap **Fizetési ütemezés sorai** fül bemeneteit. Továbbra is módosíthatja az egyes kifizetési összegeket és a változó fizetéseket. A lízingkötelezettséget a módosított fizetési ütemezés alapján számítja ki a program.

    > [!NOTE]
    > A bérleti díj kezdő dátuma nem lehet későbbi, mint a bérlet kezdő dátuma. Hibaüzenetet kap, ha a kifizetés kezdő dátuma korábbi a bérlet kezdő dátumán. 

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
