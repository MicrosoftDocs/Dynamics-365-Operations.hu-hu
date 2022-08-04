---
title: ER-sablonok biztonságimentés-tárhelye
description: Ez a cikk bemutatja, hogy hogyan használható az elektronikus jelentéskészítés biztonsági másolattárolója a sablonok visszatérítéséhez.
author: NickSelin
ms.date: 04/29/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 27621
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-08-13
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 635e7152bece91d5dee47f82cef7052730eb0c82
ms.sourcegitcommit: 3289478a05040910f356baf1995ce0523d347368
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/01/2022
ms.locfileid: "9108952"
---
# <a name="backup-storage-of-er-templates"></a>ER-sablonok biztonságimentés-tárhelye

[!include [banner](../includes/banner.md)]

Az [Elektronikus jelentéskészítés (ER) áttekintése](general-electronic-reporting.md) a különböző országok/régiók jogi követelményeinek megfelelő formátumú elektronikus dokumentumok konfigurálását teszi lehetővé az üzleti felhasználók számára. A konfigurált ER-formátumok a különböző formátumú kimeneti dokumentumok (például Microsoft Excel munkafüzetek, Microsoft Word dokumentumok vagy PDF-dokumentumok) előállítására használhatnak előre meghatározott sablonokat. A sablonok olyan adatokkal vannak kitöltve, amelyekhez a megadott adatfolyamnak generált dokumentumokhoz szüksége van.

Minden konfigurált formátum közzétehető egy ER-megoldás részeként. Minden ER-megoldás exportálható egy pénzügyi példányból és műveletből, és importálható egy másikba.

Az ER keretrendszer a Dokumentumkezelés [konfigurálása](../../fin-ops/organization-administration/configure-document-management.md) keretrendszer használatával megtartja a szükséges sablonokat az aktuális pénzügyi és műveleti példányhoz. Az ER keretrendszer beállításaitól függően a Microsoft Azure Blob tároló vagy a Microsoft SharePoint mappa választható ki a sablonok fizikai elsődleges tárolóhelyéhez. (További tájékoztatás: [Az Elektronikus jelentéskészítés (ER) keretrendszer konfigurálása](electronic-reporting-er-configure-parameters.md).) A DocuValue tábla minden egyes sablonhoz külön rekordot tárol. A **AccessInformation** mező mindegyik rekordban tárolja a konfigurált tárhelyen található sablonfájl elérési útját.

A pénzügyi és műveleti példányok kezelésekor dönthet úgy, hogy az aktuális példányt egy másik helyre áttelepítése. Előfordulhat például, hogy egy új tesztkörnyezetbe szeretné áttelepíteni a termelési példányt. Ha úgy állította be az ER keretrendszert, hogy a Blob-tárolóban tárolja a sablonokat, akkor az új tesztkörnyezet DocuValue táblája a Blob tárhely példányára hivatkozik atermelési környezetben. Ez a példány azonban nem érhető el a tesztkörnyezetből, mivel az áttelepítési folyamat nem támogatja a Blob-tárolóban található összetevők áttelepítését. Ha tehát olyan ER formátumot próbál futtatni, amely sablon alapján üzleti dokumentumokat hoz létre, akkor kivétel történik, és a program értesíti a hiányzó sablonról. A program arra kéri, hogy használja az ER karbantartó eszközt, majd importálja újra az ER formátumkonfigurációt, amely a sablont tartalmazza. Mivel előfordulhat, hogy a több ER formátumkonfigurációja is van, ez a folyamat időigényes lehet.

A sablonok biztonsági mentése funkcióval elérheti, hogy mindig rendelkezésre álljanak a sablonjai az üzleti dokumentumok létrehozásához.

> [!NOTE]
> Ez a funkció csak akkor használható, ha Blob-tárhely van kiválasztva a fizikai tárolási helyként az ER-sablonokhoz.

## <a name="automated-recovery-and-notification"></a>Automatikus helyreállítás és értesítés

Ennek a funkciónak az esetében a program automatikusan menti az aktuális környezet ER formátumkonfigurációjának minden sablonját a sablonok biztonsági mentési tárhelyére (a ERDocuDatabaseStorage-adatbázistábla), amikor a következő események történnek:

- Egy új, a sablont tartalmazó ER formátumkonfigurációt importál.
- Befejezi egy ER formátumú konfiguráció piszkozatát, amely egy sablont tartalmaz.

A sablonok biztonsági másolatai áttelepítve az alkalmazás-adatbázis részeként egy új pénzügyi példányba és műveletbe.

Ha a kimenő dokumentumok létrehozásához, beszállítói fizetések feldolgozásához, beleértve fizetési értesítések és kontrolling jelentések generálását szükséges az ER formátum, de a szükséges sablon nem található az elsődleges tárolóhelyen, a következő események történnek:

- Ha a sablon a biztonsági mentési helyén elérhető, akkor a rendszer automatikusan betölti a biztonsági mentési helyről, és visszaállítja az elsődleges tárolóhelyre, és az aktuális feladathoz használja.
- Minden olyan felhasználót, aki az **Elektronikus jelentések fejlesztője** vagy **Rendszeradminisztrátori** szerepkörhöz van társítva, a program a műveleti központban értesíti a hiányzó sablonról. A megjelenő üzenet attól függ, hogy mi a **Hibás sablonok visszaállítási eljárásának automatikus kötegelt futtatása** paraméter értéke.

    - Ha ez a paraméter **Ki** értékre van állítva, akkor az üzenet azt javasolja, hogy a kötegelt feldolgozás elindításával automatikusan javítsa ki más ER formátumkonfigurációs sablonok problémáit is. Az üzenet tartalmaz egy hivatkozást, amely a kötegfolyamat elindítására használható.
    - Ha ez a paraméter **Be** értékre van állítva, akkor az üzenet értesíti, hogy a hiányzó sablonokat kapcsolatos problémákat talált, és egy új kötegfolyamat, a **Hibás sablonok visszaállítása a belső adatbázis-biztonsági mentéséből** automatikusan ütemezve lett. Ez a kötegfolyamat automatikusan kijavítja a többi sablon hasonló problémáit.

A **Hibás sablonok visszaállítási eljárásának automatikus kötegelt futtatása** paraméter beállításához végezze el az alábbi lépéseket:

1. A Pénzügy és műveletek területén nyissa meg a Szervezet **felügyelete \> – Elektronikus jelentési \> konfigurációk lapot**.
2. A **Konfigurációk** oldal műveleti ablaktábláján, a **Konfigurációk** lapon, a **Speciális beállítások** csoportban válassza a **Felhasználói paraméterek** lehetőséget.
3. A **Felhasználó paraméterei** párbeszédpanelen állítsa be a szükséges értéket a **Hibás sablonok visszaállítási eljárásának automatikus kötegelt futtatása** paraméterhez.

> [!NOTE]
> Ez a paraméter az alkalmazás felhasználójaként van definiálva vállalatspecifikusan naplózott.

![ER-konfigurációk oldal.](./media/GER-BackupTemplates-1.png)

A következő ábra egy példát mutat be az üzenetre, amely akkor jelenik meg, amikor a **Hibás sablonok visszaállítási eljárásának automatikus kötegelt futtatása** paraméter értéke **Be**.

![Szállítói kifizetési napló oldal.](./media/GER-BackupTemplates-2.png)

A következő ábra bemutatja a **Hibás sablonok visszaállítása a belső adatbázis-biztonsági mentéséből** kötegfolyamatot a **Kötegelt feladat** oldalon.

![Kötegelt feladat oldal.](./media/GER-BackupTemplates-3.png)

A **Hibás sablonok visszaállítása a belső adatbázis-biztonsági mentéséből** végrehajtási naplója tartalmazza azokat a sablonokat, amelyek a biztonsági mentés tárolóhelyéről az elsődleges tárolóhelyre lettek visszaállítva.

![Kötegelt feladatok előzményoldala.](./media/GER-BackupTemplates-4.png)

Alapértelmezésként a folyamat automatikusan létrehozza az ER formátumúkonfigurációban tárolt sablonok biztonsági másolatait. Ha le szeretné állítani a sablonok biztonsági másolatát, állítsa be **Sablonok biztonsági másolatai elkészítésének leállítása** elemet **Igen** értékre a **Mellékletek fülön** az **Elektronikus jelentéskészítés paraméterei** oldalon. Ezt a lapot megnyithatja az **Elektronikus jelentéskészítés** munkaterületről.

Ha a **Sablonok biztonsági másolatai elkészítésének leállítása** elem **Igen** értékre van beállítva, és nem szeretné megtartani azokat a biztonsági másolatokat, amelyek korábban a sablonokról készültek válassza a **Biztonsági mentés tárhelyének karbantartása** lehetőséget az **Elektronikus jelentéskészítés paraméterei** oldalon.

Ha frissítette a környezetet a pénzügyre és a műveletekre a 10.0.5-ös verzióra (2019. október), és olyan új környezetbe szeretne áttelepítést készíteni, amely futtatható ER-formátumkonfigurációkat tartalmaz, **·** **mielőtt** az áttelepítésre sor kerül. Ez a gomb elindítja az összes elérhető sablon biztonsági másolatainak elkészítésének folyamatát, így a sablonokat a biztonsági mentési tárolóhelyen tárolja.

![Elektronikus jelentéskészítés paraméterei lap.](./media/GER-BackupTemplates-5.png)

## <a name="manual-recovery"></a>Manuális helyreállítás

Ugrás a **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Hibás sablonok helyreállítása** lehetőséget az ER-sablonok biztonsági mentési helyről az elsődleges tárolóhelyre történő visszaállítási folyamatának manuális kezdeményezéséhez. A folyamat elkezdése előtt a **Hibás sablonok visszaállítása** lapon megadhatja, hogy a program interaktívan hajtja-e végre, vagy ehhez a kötegelt feldolgozást ütemez ehhez a program.

## <a name="supported-deployments"></a>Támogatott telepítések

A pénzügyek és műveletek 10.0.5-ös verziója esetén az ER-sablonok biztonsági mentése funkció csak a felhőalapú telepítés esetén érhető el.

## <a name="additional-resources"></a>További erőforrások

[Elektronikus jelentéskészítés (ER) áttekintése](general-electronic-reporting.md)

[Az elektronikus jelentéskészítési (ER) keretrendszer konfigurálása](electronic-reporting-er-configure-parameters.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
