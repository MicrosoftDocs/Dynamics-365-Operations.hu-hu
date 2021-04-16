---
title: Többnyelvű jelentések tervezése elektronikus jelentésekben
description: Ez a témakör azt mutatja be, hogyan lehet használni az elektronikus jelentések (ER) címkéit a többnyelvű jelentések tervezéséhez és létrehozásához.
author: NickSelin
ms.date: 09/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERModelMappingDesigner, EROperationDesigner, ERExpressionDesignerFormula
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f5a2e8cca441189020e6274248a48c5e9dd80e00
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5753552"
---
# <a name="design-multilingual-reports-in-electronic-reporting"></a>Többnyelvű jelentések tervezése elektronikus jelentésekben

[!include[banner](../includes/banner.md)]

## <a name="overview"></a>Áttekintés

Üzleti felhasználóként az [elektronikus jelentési (ER)](general-electronic-reporting.md) keretrendszer a különböző országok/régiók jogi követelményeinek megfelelő formátumú, kötelezően létrehozandó elektronikus dokumentumok konfigurálását teszi lehetővé. Ha ezek a követelmények megkövetelik, hogy a kimenő dokumentumok a különböző országokban vagy régiókban különböző nyelveken jöjjenek létre, akkor konfigurálhat egy olyan egységes ER [formátumot](general-electronic-reporting.md#FormatComponentOutbound), amely nyelvfüggő erőforrásokat tartalmaz. Ily módon a formátumot újra felhasználhatja a különböző országok vagy régiók kimenő dokumentumainak létrehozásához. Előfordulhat, hogy a megfelelő vevők, szállítók, leányvállalatok vagy egyéb felek számára a különböző nyelvű kimenő dokumentumok előállításához egyetlen ER-formátumot szeretne használni.

Az ER-adatmodelleket és a modell-hozzárendeléseket konfigurálhatja úgy, hogy a konfigurált alapformátumok adatforrásai határozzák meg azt az adatforgalmat, amely meghatározza, hogy milyen adatok kerülnek a létrejövő dokumentumokba. ER-konfigurációs [szolgáltatóként](general-electronic-reporting.md#Provider) [közzéteheti](tasks/er-upload-configuration-into-lifecycle-services.md#upload-a-configuration-into-lcs) a konfigurált [adatmodelleket](general-electronic-reporting.md#data-model-and-model-mapping-components), [modell-leképezéseket](general-electronic-reporting.md#data-model-and-model-mapping-components) és [formátumokat](general-electronic-reporting.md#FormatComponentOutbound) meghatározott kimenő dokumentumok létrehozásához egy ER-megoldás részeként. Azt is lehetővé teheti a vevők számára, hogy a közzétett ER-megoldást [feltöltsék](general-electronic-reporting-manage-configuration-lifecycle.md) , hogy használhatók és testreszabhatók legyenek. Ha úgy gondolja, hogy a vevők más nyelveket is beszélnek, akkor konfigurálhatja, hogy a program a nyelvfüggő erőforrásokat tartalmazza. Ily módon egy szerkeszthető ER-komponens tartalma a vevő felhasználó által preferált nyelvén jeleníthető meg a tervezés idejében.

A nyelvtől függő erőforrásokat beállíthatja ER-címkékként. Ezeket a címkéket akkor használhatja, ha a következő célokból konfigurálja az ER-komponenseket:

- A tervezés idejében:

    - A konfigurált ER-komponensek tartalma a felhasználó által preferált nyelven jelenik meg.

- Futásidőben:

    - A kimenő dokumentumok nyelvtől függő tartalmának előállítása.
    - Figyelmeztetési és hibaüzenetek biztosítása a felhasználó által preferált nyelven.
    - A szükséges mezők rákérdezése a felhasználó által preferált nyelven.

A ER-címkék konfigurálható minden olyan ER-[konfigurációban](general-electronic-reporting.md#Configuration), amely különböző összetevőket tartalmaz. A címkék önállóan karbantarthatók az ER-adatmodellek, a ER-modell-hozzárendelések és ER-formátumú-összetevők konfigurált logikájától.

Minden ER-címkét egy olyan azonosító azonosít, amely a címkét birtokló ER-konfigurációban egyedi. Minden címke tartalmazhatja a Microsoft Dynamics 365 Finance jelenlegi példánya által támogatott összes nyelvhez tartozó címkeszöveget. Ezek a támogatott nyelvek magukban foglalják a telepített testreszabások nyelvét.

## <a name="entry"></a>Bejegyzés

Ha egy ER-adatmodellt, egy ER-modell-hozzárendelést vagy egy ER-formátumot hoz létre, akkor a **Fordítás** beállítás akkor jelenik meg, amikor kijelöl egy olyan mezőt, amely a fordítható környezetet tartalmazhatja. Ha bejelöli ezt a lehetőséget, a kiválasztott mező a **Szöveg fordítása** <a name="TextTranslationPane">ablaktáblán</a> egy ER-címkéhez kapcsolható. Kiválaszthat egy meglévő ER-címkét, vagy hozzáadhat egy új ER-címkét is, ha még nem áll rendelkezésre. Ha bejelöl vagy hozzáad egy ER-címkét, akkor az aktuális Finance példányban támogatott minden nyelvhez kapcsolódó szöveget is hozzáadhat.

A következő ábra azt mutatja be, hogy hogyan történik ez a fordítás egy szerkeszthető ER-adatmodellben. Ebben a példában a **Leírás** attribútumát a **PurchaseOrder** mezőnek a szerkeszthető **Számlamodellhez** kapcsolódóan a program lefordítja az osztrák német (de-at) és Japán (ja) nyelvekre.

![Egy ER-címke fordításának megadása az ER-adatmodelltervezőben](./media/er-multilingual-labels-refer.png)

Csak a szerkeszthető ER-összetevőkben található címkét lehet lefordítani. Ha például bejelöli az **Fordítás** lehetőséget egy ER-alapmodell-hozzárendelési adatforrás címkeattribútumához, és ezután egy olyan ER-címkét választ ki, amely a szülő ER-adatmodellben található, akkor a címke tartalma jelenik meg, de ez nem módosítható. Ezekben az esetekben a **Lefordított szöveg** mező nem érhető el, ahogy az a következő ábrán látható.

![Egy ER-címke megadott fordításának felülvizsgálata az ER-adatmodell-leképezés-tervezőben](./media/er-multilingual-labels-refer-mapping.png)

> [!NOTE]
> A tervezők nem tudják törölni azt a címkét, amely szerkeszthető ER-összetevőben szerepel.

## <a name="scope"></a>Hatókör

Az ER-címkék több lefordítható ER-összetevő attribútumban is szerepelhetnek.

### <a name="data-model-component"></a>Adatmodell összetevője

Ha beállít egy ER-adatmodellt, akkor felveheti a szükséges ER-címkéket a számára. A modellelem **Címke** és **Leírás** attribútumai, a modell összes mezője, valamint az egyes <a id="LinkModelEnum"></a>modellek számbavételi értéke egy olyan ER-címkéhez kapcsolható, amely hozzáadódik az ER-adatmodellhez.

![A Leírás attribútum fordításának megadása az ER-adatmodell-tervezőben](./media/er-multilingual-labels-refer.png)

Ha ilyen módon konfigurálnak egy ER-adatmodellt, akkor a program a tartalmat az ER-adatmodell-tervező felhasználó számára a felhasználó által preferált nyelven jeleníti meg. A modell karbantartása ezért egyszerűsített. A következő ábrák azt mutatják be, hogy hogyan működik ez a funkció azon felhasználók számára, akik DE-AT és JA beállítással rendelkeznek preferált nyelvükön.

![Az ER-adatbázismodell-tervező kinézete olyan felhasználóhoz, akinek a preferált nyelve a DE-AT](./media/er-multilingual-labels-refer-de.png)

![Az ER-adatbázismodell-tervező kinézete olyan felhasználóhoz, akinek a preferált nyelve a JA](./media/er-multilingual-labels-refer-ja.png)

### <a name="model-mapping-component"></a>Modell-leképezési összetevő

Mivel az ER-modell-leképezés egy ER-adatmodellen alapul, a hivatkozott adatmodell-elemek címkéi a felhasználó preferált nyelvén jelennek meg a modell-leképezés tervezőjében. A következő ábra azt mutatja be, hogyan történik a **PurchaseOrder** mező jelentésének leírása a szerkeszthető modell hozzárendelésében a megadott adatmodellhez hozzáadott **Leírás** attribútum címkéjének használatával. Figyelje meg, hogy ez a címke a felhasználó preferált nyelvén jelenik meg (ebben a példában ez a DE-AT).

![Az ER-modell-leképezéstervező kinézete olyan felhasználóhoz, akinek a preferált nyelve a DE-AT](./media/er-multilingual-labels-show-mapping.png)

Amikor a **Címke** attribútuma a **Felhasználó bemeneti paramétere** adatforrásnak egy ER-címkéhez van beállítva, akkor az ehhez az adatforráshoz tartozó paraméter mező a felhasználói párbeszédpanelen érhető el futásidőben, a felhasználók számára a preferált nyelven.

### <a name="format-component"></a>Formátum összetevője

Ha beállít egy ER-formátumot, akkor felveheti a szükséges ER-címkéket a számára. Minden konfigurált adatforrás **Címke** és **Súgószöveg** attribútumai csatolhatók az ER-formátumhoz hozzáadott ER-címkéhez. Az **Címke** és **Leírás** attribútuma az összes <a id="LinkFormatEnum"></a>formátum számbavételi értéknek is kapcsolható egy olyan ER-címkéhez, amely a szerkeszthető ER-formátumból érhető el.

> [!NOTE]
> Ezeket az attribútumokat a szülő ER-adatmodell ER-címkéjéhez is csatolhatja, amely a modell címkéit újra felhasználja az ehhez az ER-adatmodellhez konfigurált minden ER-formátumban.

Ha ilyen módon konfigurálnak egy ER-formátumot, akkor a program a formátum tartalmát az ER-művelettervező felhasználó számára a felhasználó által preferált nyelven jeleníti meg. A konfigurált logika karbantartása és elemzése így egyszerűbbé válik.

Mivel az ER-formátum egy ER-adatmodellen alapul, az adatmodell-elemek hivatkozott címkéi a felhasználó preferált nyelvén jelennek meg az ER-formátum tervezőjében.

Amikor a **Címke** attribútuma a **Felhasználó bemeneti paramétere** adatforrásnak egy ER-címkéhez van beállítva, akkor a paraméterhez tartozó mező a felhasználói párbeszédpanelen futásidőben a felhasználó számára kérésként jelenik meg. A következő ábrák azt mutatják be, hogyan lehet a **Címke** attribútumát a **Felhasználói bemeneti paraméter** adatforrásának a tervezés ideje alatt egy ER-címkéhez kapcsolni, hogy a felhasználók a különböző, a felhasználó által preferált nyelveken kapjanak kérést a paraméterre (az Egyesült Államokbeli angol (en-US) és a DE-AT jelenik meg itt) futásidőben.

![Egy felhasználói bemeneti paraméter attribútumainak fordítása az ER műveleti tervezőben](./media/er-multilingual-labels-refer-format.png)

![Az EN-US felhasználó által preferált nyelvhez tartozó ER-szállítói kifizetés feldolgozásának végrehajtása futásidőben](./media/er-multilingual-labels-show-runtime-en.png)

![A DE-AT felhasználó által preferált nyelvhez tartozó ER-szállítói kifizetés feldolgozásának végrehajtása futásidőben](./media/er-multilingual-labels-show-runtime-de.png)

### <a name="expressions"></a>Kifejezések

Ha azt szeretné, hogy egy címke legyen használva egy ER [kifejezésben](er-formula-language.md), akkor ezt a szintaxist kell használni: **@"GER\_LABEL:X"**, ahol a **@** jelzi, hogy az operandus címkére hivatkozik, a **GER\_LABEL** azt jelzi, hogy ER-címkéről van szó, és az **X** ER-címke azonosítója.

![ER-kifejezés konfigurálása, amely hivatkozásokat tartalmaz egy ER-címkére az ER-formulatervezőben.](./media/er-multilingual-labels-expression1.png)

Ha egy rendszer (alkalmazás) címkére hivatkozik, használja az **@"X"** szintaxist, ahol az **@** előtag azt jelzi, hogy az operandus címkére hivatkozik, és az **X** a rendszer címkéjének azonosítója.

![ER-kifejezés konfigurálása, amely hivatkozásokat tartalmaz egy alkalmazáscímkére az ER-formulatervezőben.](./media/er-multilingual-labels-expression2.png)

#### <a name="model-mapping"></a>Modell hozzárendelése

Egy ER-modellhozzárendelés kifejezését címkék használatával lehet konfigurálni. Ha ezt a hozzárendelést a kimenő dokumentumok előállításához futtatott ER-formátum hívja meg, akkor a végrehajtás környezete nyelvi kódot tartalmaz. A beállított kifejezés címkéjén a program kitölti azt a címkét, amely az adott környezet nyelvéhez be van állítva.

Ha egy hivatkozott címkén nem szerepel fordítás a modell-hozzárendelést meghívó formátum-végrehajtási környezet nyelvéhez, a program helyette az EN-US nyelvű címke szövegét használja.

#### <a name="format"></a>Formátum

Egy ER-formátum ER-kifejezését címkék használatával lehet konfigurálni. Ha ezt a hozzárendelést a kimenő dokumentumok előállításához hívja meg, akkor a végrehajtás környezete nyelvi kódot tartalmaz. A beállított kifejezés címkéjén a program kitölti azt a címkét, amely az adott környezet nyelvéhez be van állítva.

![A szerkeszthető ER-kifejezés ER-címkéjének fordításának elkészítése az ER-formátumtervezőben](./media/er-multilingual-labels-refer-in-expression.png)

![Olyan adatkötési minta, amely egy ER-címkére hivatkozik az ER műveleti tervezőben.](./media/er-multilingual-labels-refer-in-binding.png)

Beállíthatja, hogy az ER-formátum **FÁJL** összetevőjét, hogy a felhasználó által preferált nyelven hozza létre a jelentést.

![Állítsa be a FÁJL összetevőt az ER-műveleti tervezőben, hogy a jelentés előállítása a felhasználó preferált nyelvén történjen.](./media/er-multilingual-labels-language-context-user.png)

Ha ilyen módon állítja be az ER-formátumot, akkor a jelentés az ER-címkék megfelelő szövegével jön létre. A következő illusztrációk példákat jelenítenek meg az EN-US és a DE-AT felhasználói nyelvekről.

![A jelentés előnézete, amely az EN-US felhasználó által preferált nyelven lett létrehozva.](./media/er-multilingual-labels-report-preview-en.png)

![A jelentés előnézete, amely a DE-AT felhasználó által preferált nyelven lett létrehozva.](./media/er-multilingual-labels-report-preview-de.png)

Ha egy hivatkozott címkén nem szerepel fordítás a formátum-végrehajtási környezet nyelvéhez, a program helyette az EN-US nyelvű címke szövegét használja.

## <a name="language"></a>Nyelv

Az ER különböző módszereket támogat a létrejövő jelentések nyelvének meghatározására. A **Nyelvi beállítások** területén a **Formátum** lapon a következő értékek választhatók:

- **Vállalati preferencia** – Jelentés készítése a vállalat által meghatározott nyelven.

    ![Adja meg az ER műveleti tervezőben a vállalat által preferált nyelvet, amely a létrejövő jelentés nyelve lesz.](./media/er-multilingual-labels-language-context-company.png)

- **Felhasználói preferencia** – Jelentés készítése a felhasználó által preferált nyelven.
- **Explicit módon definiálva** – Jelentés készítése a tervezés ideje alatt megadott nyelven.

    ![Adja meg az ER műveleti tervezőben a tervezésidőben megadott t nyelvet, amely a létrejövő jelentés nyelve lesz](./media/er-multilingual-labels-language-context-fixed.png)

- **Futásidőben definiálva** – Jelentés készítése a futásidőben megadott nyelven. Ha ezt az értéket választja, a **Nyelv** mezőben konfiguráljon egy olyan ER-kifejezést, amely a nyelvhez tartozó nyelvi kódot adja vissza, például a megfelelő vevő nyelvét.

    ![Adja meg az ER műveleti tervezőben a futásidőben megadott nyelvet, amely a létrejövő jelentés nyelve lesz](./media/er-multilingual-labels-language-context-runtime.png)

## <a name="translation"></a>Átszámítás

A kötelezően felhasználható ER-címkéket egy szerkeszthető ER-komponenshez is hozzáadhatja. A hozzáadást követően kétféleképpen lehet lefordítani az ER-címkét: manuálisan és automatikusan.

### <a name="manual-translation"></a>Manuális fordítás

Ha hozzáad egy ER-címkét a **Szöveg fordítása** [ablaktáblában](#TextTranslationPane), akkor az aktuális Finance példányban támogatott összes nyelvre lefordíthatja. Válassza ki a preferált nyelvet a **Nyelv** mezőben a **Rendszer nyelve** vagy a **Felhasználó nyelve** területen, adja meg a megfelelő szöveget a megfelelő **Lefordított szöveg** mezőben, majd válassza a **Fordítás** elemet. Ezt a folyamatot meg kell ismételni minden szükséges nyelvnél és a hozzáadott címkéknél.

### <a name="automatic-translation"></a>Automatikus fordítás

Egy ER-összetevő konfigurációját azon az ER-konfiguráció piszkozat verzióban végezze el, amelyben a szerkeszthető ER-összetevő található.

![A konfiguráció piszkozat állapotához való hozzáférést ajánló ER-konfigurációk lapja](./media/er-multilingual-labels-configurations.png)

A témakör korábbi részében ismertetett módon egy szerkeszthető ER-összetevőhöz hozzáadhatja a kötelező ER-címkéket. Ily módon meghatározhatja az ER-címkék szövegét az EN-USA nyelven. Ezután a beépített ER-funkcióval exportálhatja az ER-összetevő címkéit. Válassza ki azt a piszkozat verzióját az ER-konfigurációnak, amely a szerkeszthető ER-összetevőt tartalmazza, majd válassza ki az **Átváltás \> Címkék exportálása** elemet.

![Az ER-konfigurációk lap a kiválasztott konfigurációverzióból származó címkék exportálását teszi lehetővé.](./media/er-multilingual-labels-export.png)

Exportálni lehet az összes címkét vagy az egyes nyelvek címkéit, amelyeket az exportálás kezdetén megadott. A címkéket az XML-fájlokat tartalmazó zip-fájlként exportálja a program. Minden XML-fájl tartalmaz egyetlen nyelvet.

![A DE-AT nyelvhez tartozó ER-címkéket tartalmazó exportált fájlok mintája](./media/er-multilingual-labels-in-xml.png)

Ez a formátum a címkék külső fordítási szolgáltatások, például a [Dynamics 365 Translation Service](../lifecycle-services/translation-service-overview.md) által a címkék automatikus fordításához használatosak. A lefordított címkék beolvasása alkalmával visszaimportálhatja őket egy olyan ER-konfigurációhoz, amely a címkék saját összetevőit tartalmazza. Válassza ki azt a piszkozat verzióját az ER-konfigurációnak, amely a szerkeszthető ER-összetevőt tartalmazza, majd válassza ki az **Átváltás \> Címkék betöltése** elemet.

![Az ER-konfigurációk lap a kiválasztott konfigurációverzióból származó címkék importálását teszi lehetővé.](./media/er-multilingual-labels-load.png)

A lefordított címkéket a program a kijelölt ER-konfigurációba importálja. Az ebben az ER-konfigurációban létező lefordított címkéket a program lecseréli. Ha egy lefordított címke hiányzik az ER-konfigurációban, akkor a program hozzáfűzi.

## <a name="lifecycle"></a>Életciklus

A szerkeszthető ER-összetevők címkéit a rendszer az összetevő egyéb tartalmával együtt az ER-konfiguráció megfelelő verziójában tárolja.

Egy alapszintű ER-összetevő címkéi hivatkozhatók a módosítások bevezetéséhez létrehozott ER-komponens származtatott verziójában.

Az ER-verziószámozása vezérli az ER-összetevőben bármely attribútumához való címke-hozzárendelést. A címke-hozzárendelés módosításait a program rögzíti egy olyan szerkeszthető ER-komponens változásainak (delta) a listájában, amelyek a megadott ER-összetevő származtatott változataként lett létrehozva. Ezek a módosítások akkor lesznek ellenőrizve, ha a származtatott verzió új alapverzióra lesz alapozva.

## <a name="functions"></a>Funkciók

A beépített [LISTOFFIELDS](er-functions-list-listoffields.md) ER-funkcióval olyan ER-címkék is elérhetők, amelyek az egyes összetevőkhöz vannak konfigurálva.

A jelen témakörben korábban ismertetett módon a **Címke** és **Leírás** attribútuma minden [modell](#LinkModelEnum) vagy [formátum](#LinkFormatEnum) ER-számlálás értékének ER-címkéhez kapcsolható, amely elérhető a megfelelő ER-összetevőben. Beállítható egy olyan ER-kifejezés, amelynél a **LISTOFFIELDS** funkciót hívja meg az ER-enumerálás használatával argumentumként. Ez a kifejezés visszaad egy listát, amely egy rekordot tartalmaz, amely a funkció argumentumaként meghatározott összes ER-számlálás értékére vonatkozik. Minden rekord tartalmazza egy ER-címke értékét, amely egy ER-enumerálási értékhez van kapcsolva:

- A **Címke** attribútumaihoz kapcsolt ER-címke értékét a visszaküldött rekord **Címke** mezőjében tárolja a program.
- A **Leírás** attribútumaihoz kapcsolt ER-címke értékét a visszaküldött rekord **Leírás** mezőjében tárolja a program.

## <a name="additional-resources"></a>További erőforrások

- [Elektronikus jelentések áttekintése](general-electronic-reporting.md)
- [Az elektronikus jelentéskészítés funkciói](er-formula-language.md#functions)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]