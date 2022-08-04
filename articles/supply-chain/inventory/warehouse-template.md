---
title: Raktár beállítása a raktári konfigurációs sablon segítségével
description: Ez a cikk bemutatja, hogyan lehet raktárat beállítani a raktár konfigurációs sablon segítségével.
author: yufeihuang
ms.date: 11/16/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DataManagementWorkspace, DMFQuickImportExportEnhanced, DMFDefinitionGroupTemplate, DMFEntityTemplateDefinitionLoadDialog
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2017-12-31
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: dafd51a46b19f3709963ffc12b3c8c77b6c809ac
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/29/2022
ms.locfileid: "9070439"
---
# <a name="set-up-a-warehouse-by-using-a-warehouse-configuration-template"></a>Raktár beállítása a raktári konfigurációs sablon segítségével

[!include [banner](../includes/banner.md)]

Ez a cikk bemutatja, hogyan lehet raktárat beállítani a raktár konfigurációs sablon segítségével. Számos előre definiált konfigurációs sablont használhat. Ha tájékoztatást szeretne ezen sablonok használatáról, lásd a [Konfigurációs adatsablonok](../../fin-ops-core/dev-itpro/data-entities/configuration-data-templates.md) című részt.

## <a name="scenarios-where-configuration-templates-can-be-helpful"></a>Esetek, amikor a konfigurációs sablonok hasznosak lehetnek

A konfigurációs sablonok számos helyzetben hasznosak lehetnek. Íme néhány példa:

- Már befejezte és tesztelte a konfigurációs beállításokat tesztkörnyezetben, és most szeretné átmásolni a beállítást az éles környezetbe is.
- Be szeretné vezetni a raktárbeállításokat több jogi személynél, illetve új raktárat szeretne létrehozni ugyanannál a jogi személynél.
- Szeretne gyorsan felkészülni a raktárfunkciók bemutatójára.
- Azt szeretné, hogy a meglévő elemek és raktárak a Raktárkezelésben használják a funkciót a Készletkezelés modul funkciója helyett.

Ez a cikk az első ilyen helyzetre fókuszál. Megmutatja, hogyan használhat konfigurációs sablont egy konfigurációs beállítás tesztkörnyezetből éles környezetbe való másolására.

## <a name="copy-a-configuration-setup-from-a-test-environment-to-a-production-environment"></a>Konfigurációs beállítás átmásolása egy tesztkörnyezetből egy éles környezetbe

Ebben az esetben a raktár konfigurációs beállításai és egyes tranzakciós folyamatok már léteznek egy tesztkörnyezetben. Át szeretné másolni a raktárra vonatokozó konfigurációs beállításokat a tesztkörnyezetből az éles környezetbe.

> [!NOTE]
> Fontos, hogy a további kapcsolódó beállítási adatot is szerepeltesse akkor, amikor egy konfigurációs beállítást másol. A termékek beállításakor például át kell másolnia a beállításokat egy tesztkörnyezetből. Azonban nem állíthat be rögzített kitárolási helyet a termék számára a termék létrehozása előtt. Annak ellenére, hogy az egyes konfigurációs sablonok nem támogatják az ilyen típusú függőséget, vannak olyan alapértelmezett adatsablonok, amelyek igen. Ezeket az alapértelmezett adatsablonokat egyszerűen szerepeltetheti egy konfigurálási folyamatban.

### <a name="export-a-default-warehouse-template"></a>Alapértelmezett raktársablon exportálása 

1. Nyissa meg az **Adatkezelés** munkaterületet.

    > [!NOTE]
    > A munkaterület első használatakor be kell töltenie az összes adatentitást a folytatáshoz.

2. Válassza ki a **Sablonok** mozaikot, majd az **Alapértelmezett sablonok betöltése** lehetőséget az alapértelmezett sablonok betöltéséhez.

    > [!NOTE]
    > Az **Alapértelmezett sablonok betöltése** lehetőség csak a **Bővített** nézetben áll rendelkezésre. Válassza ki a **Keretrendszer paraméterei** lehetőséget, majd az **Alapértelmezettek megtekintése** elemet, és válassza a **Bővített nézet** pontot.

3. Az alapértelmezett sablonok betöltése után módosíthatja őket, hogy megfeleljenek az üzleti követelményeinek.

    > [!NOTE]
    > Alapértelmezett sablonok betöltéséhez és importálásához rendszergazdai hozzáféréssel kell rendelkeznie. Ez a követelmény segít annak garantálásában, hogy minden entitás megfelelően betöltődjön a sablonba.

4. Győződjön meg arról, hogy annál a jogi személynál van, amelyből szeretné exportálni a vállalatspecifikus adatokat.
5. A munkaterületen válassza az **Exportálás** lehetőséget.
6. Hozzon létre egy új exportálási projektet.
7. Válassza a **+ Sablon hozzáadása** lehetőséget, és keresse ki a **400 - WMS** alapértelmezett raktári sablont. Ez a sablon adatentitásokat ad a raktári konfigurációhoz.

    > [!NOTE]
    > Ha szűrni kell az exportálás alatt lévő adatokat (például csak az adott raktárhoz kapcsolódó adatokat szeretné átmásolni), akkor ki kell értékelnie minden egyes adatentitást, és hozzá kell adnia a szűrést egy lekérdezés útján. Azt is megteheti, hogy exportálja az összes adatot, majd törli azokat a rekordokat, amelyek nem szükségesek célfájlokban.

8. Válassza az **Exportálás** lehetőséget. A projekt összes adatentitásához kapcsolódó adatokat exportálja a rendszer.

Az adatcsomag zip-fájlját letöltheti. Ez a fájl minden adatot a kijelölt formátumban (például Excel-formátumban) tartalmaz. Ahogyan említettük, előfordulhat, hogy az adatcsomagfájlok egyes rekordjait frissíteni kell, hogy importálhassa őket az éles környezetbe. Rekord frissítése során győződjön meg arról, hogy nem módosítja a fájl nevét.

### <a name="import-a-warehouse-configuration-setup"></a>Raktári konfiguráció beállításának importálása

1. A cél környezetben győződjön meg róla, hogy annál a vállalatnál van, amelybe a raktár adatait importálni szeretné.

    > [!NOTE]
    > Az importálást megelőzően meg kell határoznia minden esetleges adatfüggőséget. A **Raktárkezelés** sablon például tartalmaz egy **Raktári intézkedéskódok** nevű adatentitást. Ez az entitás olyan adatokat tartalmaz, amelyek az **Intézkedési kódok** beállító oldalához kapcsolódnak (**Raktárkezelés** > **Beállítás** > **Mobileszköz** > **Intézkedési kódok**). Ha már egy korábbi beállítás kezeli a visszáru feldolgozását az értékesítési rendeléseknél, akkor a **Visszáru intézkedési kódja** mező értéket tartalmaz. Az ebben a mezőben szereplő intézkedési kód az **Intézkedési kód** adatentitáshoz kapcsolódik, amely része az **Értékesítés és marketing** sablonnak. Ha az **Intézkedési kód** adatentitás adatai nincsenek importálva a **Raktári intézkedési kódok** mező előtt, akkor az importálás sikertelen lesz.

2. Az **Adatkezelés** munkaterületen válassza az **Importálás** lehetőséget.
3. Hozzon létre egy új importálási projektet.
4. Válassza a **+ Fájl hozzáadása** lehetőséget, majd töltse fel az adatcsomag zip-fájlját.
5. Válassza az **Importálás** lehetőséget. Aa **Bővített** nézetben a **Szűrő** beállítással gyorsan áttekintheti az importálás során esetlegesen előforduló hibákat.

A **Végrehajtás megtekintése** napló részletes információt nyújt minden egyes importált adatentitásról. Az előkészítési adatok nézetének segítségével gyorsan megtekintheti a céladatokat. Ezzel a módszerrel megnézheti, hogy néznek ki az importált adatok a kapcsolódó lapokon az alkalmazásban. Az alapértelmezett adatsablonok használata esetén az egyes adatentitások importálási sorrendje az előre meghatározott módon történik annak biztosítása érdekében, hogy először az összes függő adat importálása történjen meg. Ha egyéni adatentitások is a projekt részét képezik, gondoskodnia kell arról, hogy meg van adva a megfelelő sorrend. További tájékoztatás: [Konfigurációs adatsablonok](../../fin-ops-core/dev-itpro/data-entities/configuration-data-templates.md).

Ha többet szeretne tudni arról, hogy hogyan lehet a raktársablon használatával átmásolni egy raktár konfigurációját az egyik vállalatból az ugyanazon a példányon belüli új vállalatba, akkor olvassa el ezt a három YouTube [perces útmutatót arról, hogyan lehet a raktársablon használatával átmásolni a konfigurációt a pénzügyek és műveletek számára](https://www.youtube.com/watch?v=K2WIfFlqJYs).

## <a name="related-article"></a>Kapcsolódó cikk

[Konfigurációs adatsablonok](../../fin-ops-core/dev-itpro/data-entities/configuration-data-templates.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
