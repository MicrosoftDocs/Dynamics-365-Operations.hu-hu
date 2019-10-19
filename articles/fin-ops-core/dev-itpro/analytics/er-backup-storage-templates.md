---
title: ER-sablonok biztonságimentés-tárhelye
description: Ez a témakör azt mutatja be, hogyan lehet használni az elektronikus jelentések (ER) biztonságimentés-tárhelyét a sablonok helyreállításához.
author: NickSelin
manager: AnnBe
ms.date: 08/19/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Operations
ms.custom: 27621
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-08-13
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 8b4e783f79b02c77a27fc59c2f4be8a192f2f476
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/30/2019
ms.locfileid: "2248700"
---
# <a name="backup-storage-of-er-templates"></a>ER-sablonok biztonságimentés-tárhelye

[!include [banner](../includes/banner.md)]

Az [elektronikus jelentési keretrendszer (ER)](general-electronic-reporting.md) a különböző országok/régiók jogi követelményeinek megfelelő formátumú elektronikus dokumentumok konfigurálását teszi lehetővé az üzleti felhasználók számára. A konfigurált ER-formátumok a különböző formátumú kimeneti dokumentumok (például Microsoft Excel munkafüzetek, Microsoft Word dokumentumok vagy PDF-dokumentumok) előállítására használhatnak előre meghatározott sablonokat. A sablonok olyan adatokkal vannak kitöltve, amelyekhez a megadott adatfolyamnak generált dokumentumokhoz szüksége van.

Minden konfigurált formátum közzétehető egy ER-megoldás részeként. Minden egyes ER megoldást exportálható a Finance and Operations egyik példányából, és importálható egy másik példányba.

Az ER keretrendszer a [Dokumentumkezelési keretrendszer](../../fin-and-ops/organization-administration/configure-document-management.md) segítségével tárolja a szükséges sablonokat az aktuális Finance and Operations példányhoz. Az ER keretrendszer beállításaitól függően a Microsoft Azure Blob tároló vagy a Microsoft SharePoint mappa választható ki a sablonok fizikai elsődleges tárolóhelyéhez. (További tájékoztatás: [Az Er keretrendszer](electronic-reporting-er-configure-parameters.md) konfigurálása.) A DocuValue tábla minden egyes sablonhoz külön rekordot tárol. A **AccessInformation** mező mindegyik rekordban tárolja a konfigurált tárhelyen található sablonfájl elérési útját.

A Finance and Operations példányok kezelésekor úgy is dönthet, hogy áttelepíti az aktuális példányt egy másik helyre. Előfordulhat például, hogy egy új tesztkörnyezetbe szeretné áttelepíteni a termelési példányt. Ha úgy állította be az ER keretrendszert, hogy a Blob-tárolóban tárolja a sablonokat, akkor az új tesztkörnyezet DocuValue táblája a Blob tárhely példányára hivatkozik atermelési környezetben. Ez a példány azonban nem érhető el a tesztkörnyezetből, mivel az áttelepítési folyamat nem támogatja a Blob-tárolóban található összetevők áttelepítését. Ha tehát olyan ER formátumot próbál futtatni, amely sablon alapján üzleti dokumentumokat hoz létre, akkor kivétel történik, és a program értesíti a hiányzó sablonról. A program arra kéri, hogy használja az ER karbantartó eszközt, majd importálja újra az ER formátumkonfigurációt, amely a sablont tartalmazza. Mivel előfordulhat, hogy a több ER formátumkonfigurációja is van, ez a folyamat időigényes lehet.

A sablonok biztonsági mentése funkcióval elérheti, hogy mindig rendelkezésre álljanak a sablonjai az üzleti dokumentumok létrehozásához.

> [!NOTE]
> Ez a funkció csak akkor használható, ha Blob-tárhely van kiválasztva a fizikai tárolási helyként az ER-sablonokhoz.

Ennek a funkciónak az esetében a program automatikusan menti az aktuális környezet ER formátumkonfigurációjának minden sablonját a sablonok biztonsági mentési tárhelyére (a ERDocuDatabaseStorage-adatbázistábla), amikor a következő események történnek:

- Egy új, a sablont tartalmazó ER formátumkonfigurációt importál.
- Befejezi egy ER formátumú konfiguráció piszkozatát, amely egy sablont tartalmaz.

A sablonok biztonsági másolatait a program az alkalmazás-adatbázis részeként telepíti át egy új Finance and Operations példányra.

Ha a kimenő dokumentumok létrehozásához, beszállítói fizetések feldolgozásához, beleértve fizetési értesítések és kontrolling jelentések generálását szükséges az ER formátum, de a szükséges sablon nem található az elsődleges tárolóhelyen, a következő események történnek:

- Ha a sablon a biztonsági mentési helyén elérhető, akkor a rendszer automatikusan betölti a biztonsági mentési helyről, és visszaállítja az elsődleges tárolóhelyre, és az aktuális feladathoz használja.
- Minden olyan felhasználót, aki az **Elektronikus jelentések fejlesztője** vagy **Rendszeradminisztrátori** szerepkörhöz van társítva, a program a műveleti központban értesíti a hiányzó sablonról. A megjelenő üzenet attól függ, hogy mi a **Hibás sablonok visszaállítási eljárásának automatikus kötegelt futtatása** paraméter értéke.

    - Ha ez a paraméter **Ki** értékre van állítva, akkor az üzenet azt javasolja, hogy a kötegelt feldolgozás elindításával automatikusan javítsa ki más ER formátumkonfigurációs sablonok problémáit is. Az üzenet tartalmaz egy hivatkozást, amely a kötegfolyamat elindítására használható.
    - Ha ez a paraméter **Be** értékre van állítva, akkor az üzenet értesíti, hogy a hiányzó sablonokat kapcsolatos problémákat talált, és egy új kötegfolyamat, a **Hibás sablonok visszaállítása a belső adatbázis-biztonsági mentéséből** automatikusan ütemezve lett. Ez a kötegfolyamat automatikusan kijavítja a többi sablon hasonló problémáit.

A **Hibás sablonok visszaállítási eljárásának automatikus kötegelt futtatása** paraméter beállításához végezze el az alábbi lépéseket:

1. A Finance and Operations alkalmazásban nyissa meg a **Szervezeti adminisztráció \> Elektronikus jelentéskészítés \> Konfigurációs oldal** menüt.
2. A **Konfigurációk** oldal műveleti ablaktábláján, a **Konfigurációk** lapon, a **Speciális beállítások** csoportban válassza a **Felhasználói paraméterek** lehetőséget.
3. A **Felhasználó paraméterei** párbeszédpanelen állítsa be a szükséges értéket a **Hibás sablonok visszaállítási eljárásának automatikus kötegelt futtatása** paraméterhez.

> [!NOTE]
> Ez a paraméter az alkalmazás felhasználójaként van definiálva vállalatspecifikusan naplózott.

![ER-konfigurációk oldal](./media/GER-BackupTemplates-1.png)

A következő ábra egy példát mutat be az üzenetre, amely akkor jelenik meg, amikor a **Hibás sablonok visszaállítási eljárásának automatikus kötegelt futtatása** paraméter értéke **Be**.

![Szállítói kifizetési napló oldal](./media/GER-BackupTemplates-2.png)

A következő ábra bemutatja a **Hibás sablonok visszaállítása a belső adatbázis-biztonsági mentéséből** kötegfolyamatot a **Kötegelt feladat** oldalon.

![Kötegelt feladat oldal](./media/GER-BackupTemplates-3.png)

A **Hibás sablonok visszaállítása a belső adatbázis-biztonsági mentéséből** végrehajtási naplója tartalmazza azokat a sablonokat, amelyek a biztonsági mentés tárolóhelyéről az elsődleges tárolóhelyre lettek visszaállítva.

![Kötegelt feladatok előzményoldala](./media/GER-BackupTemplates-4.png)

Alapértelmezésként a folyamat automatikusan létrehozza az ER formátumúkonfigurációban tárolt sablonok biztonsági másolatait. Ha le szeretné állítani a sablonok biztonsági másolatát, állítsa be **Sablonok biztonsági másolatai elkészítésének leállítása** elemet **Igen** értékre a **Mellékletek fülön** az **Elektronikus jelentéskészítés paraméterei** oldalon. Ezt a lapot megnyithatja az **Elektronikus jelentéskészítés** munkaterületről.

Ha a **Sablonok biztonsági másolatai elkészítésének leállítása** elem **Igen** értékre van beállítva, és nem szeretné megtartani azokat a biztonsági másolatokat, amelyek korábban a sablonokról készültek válassza a **Biztonsági mentés tárhelyének karbantartása** lehetőséget az **Elektronikus jelentéskészítés paraméterei** oldalon.

Ha frissítette a környezetet a Finance and Operations 10.0.5 (október 2019) verzióra, és egy olyan új környezetbe kíván áttérni, amely futtatható ER formátumkonfigurációkat tartalmaz válassza ki a **Biztonsági mentést kitöltése** lehetőséget az **Elektronikus jelentéskészítési paraméterek** oldalon még az áttelepítés előtt. Ez a gomb elindítja az összes elérhető sablon biztonsági másolatainak elkészítésének folyamatát, így a sablonokat a biztonsági mentési tárolóhelyen tárolja.

![Elektronikus jelentéskészítés paraméterei lap](./media/GER-BackupTemplates-5.png)

## <a name="supported-deployments"></a>Támogatott telepítések

A Finance and Operations 10.0.5 verziójában az ER sablonok biztonságimentés tárhelye csak felhő alapú telepítésekben érhető el.

## <a name="additional-resources"></a>További erőforrások

[Az Elektronikus jelentéskészítés áttekintése](general-electronic-reporting.md)

[Az elektronikus jelentéskészítési keretrendszer konfigurálása](electronic-reporting-er-configure-parameters.md)
