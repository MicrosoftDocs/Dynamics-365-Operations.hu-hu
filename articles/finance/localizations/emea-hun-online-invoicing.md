---
title: Online számlázási rendszer
description: Ez a témakör azt mutatja be, hogyan lehet beállítani az elektronikus jelentéskészítési (ER) konfigurációkat, valamint azt, hogy hogyan lehet beállítani és használni az elektronikus üzenetküldési funkciókat (EM) a valós idejű számlajelentéshez (RTIR).
author: anasyash
manager: AnnBe
ms.date: 06/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetParameters
audience: Application User
ms.reviewer: kfend
ms.custom: 264684
ms.search.region: Hungary
ms.author: epopov
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: 10.0.0
ms.openlocfilehash: 9a0644a0da81824b3f34b876cbdfac1c499bb17e
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5204714"
---
# <a name="online-invoicing-system"></a>Online számlázási rendszer

[!include [banner](../includes/banner.md)]

A magyarországi belföldi adó-és vámigazgatás bejelentette, hogy 2018. július 1-től a magyarországi vállalatok kötelesek az online számlázási rendszer valós idejű számlajelentés (RTIR) platformján megadni a kiállított számláik adatait.

További tájékoztatást a következő témakörben talál: https://onlineszamla.nav.gov.hu.

Ez a témakör azt mutatja be, hogyan lehet beállítani az elektronikus jelentéskészítési (ER) konfigurációkat, valamint azt, hogy hogyan lehet beállítani és használni az elektronikus üzenetküldési funkciókat (EM) a valós idejű számlajelentéshez (RTIR).

A témakör a következő feladatok végrehajtásával kapcsolatban tartalmaz tájékoztatást:

- ER-konfigurációk importálása és a alkalmazásspecifikus paraméterek beállítása.
- Az EM (elektronikus üzenetküldés) funkció beállítása.
- Az EM funkció használata az RTIR-hez.

## <a name="import-er-configurations"></a>ER-konfigurációk importálása

A Microsoft Dynamics 365 Finance alkalmazás RTIR-re történő előkészítéséhez importálnia kell a következő ER-konfigurációkat.

| **Szám** | **Konfiguráció neve**                 | **Konfiguráció típusa** | **Leírás**                                                                                                 |
|------------|----------------------------------------|------------------------|-----------------------------------------------------------------------------------------------------------------|
| 1          | Számlák kommunikációs modellje           | Típus                  | Az a modell, amely a bejövő és a kimenő számlák jelentéshez kapcsolódó adatait jeleníti meg.                                    |
| 2          | RTIR-leképezés                           | Modell leképezése (exportálás) | A modell-leképezési konfiguráció, amely a magyar RTIR követelményeinek megfelelően gyűjti az adatokat a Finance alkalmazásból. |
| 3          | RTIR számlaadatok (HU)                 | XML-formátum (export)    | A RTIR számlaadatok exportálására szolgáló formátum.                                                                     |
| 4          | RTIR tokencsere-kérelem (HU)       | XML-formátum (export)    | A RTIR tokencsere-kérelmek exportálási formátuma.                                                          |
| 5          | RTIR számlakezelési kérelem (HU)       | XML-formátum (export)    | A RTIR számlakezelési kérelmek exportálási formátuma.                                                          |
| 6          | RTIR számlaállapot lekérdezési kérelem (HU) | XML-formátum (export)    | A RTIR számlaállapot kérelmek lekérdezésének exportálási formátuma.                                                    |
| 7          | Elektronikus üzenetek keretrendszer-modellje    | Típus                  | Az EM keretrendszer modellje.                                                                                 |
| 8          | RTIR-importálás modell-leképezés              | Modell-leképezés (importálás) | A modell-leképezési konfiguráció importálása, amely az EM-adatokhoz frissítést biztosít az RTIR során.                         |
| 9          | RTIR importálási formátum (HU)                | XML-formátum (HU)    | Az importálási formátumkonfigurációja, amely az EM keretrendszer adatstruktúrájában elemzi az RTIR válaszait.   |

> [!IMPORTANT]
> Győződjön meg róla, hogy a konfigurációk legújabb verzióit importálja. A verzió leírása általában tartalmazza a Microsoft Tudásbázis (KB) azon cikkének a számát, amely a konfiguráció verziójában bevezetett változtatásokat ismerteti.

> [!NOTE]
> Ha az előző táblából az összes ER-konfigurációt importálta, akkor az **Alapértelmezett a modell-hozzárendeléshez** beállítás értéke **Igen** az **RTIR-hozzárendelés** és az **RTIR importálás modell-leképezés** konfigurációk esetében.

További információért azzal kapcsolatosan, hogyan tölthet le ER-konfigurációkat a Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásból, lásd: [Az elektronikus jelentéskészítési konfigurációk letöltése a Lifecycle Services rendszerből](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).

## <a name="set-up-application-specific-parameters"></a>Alkalmazásfüggő paraméterek beállítása

A számlázási adatoknak a magyar online számlázási rendszerbe történő jelentéséhez használt formátum bizonyos elemekhez (például mértékegység vagy sor kifejezési mutatók) meghatározott értékeket kér számozott listákból. Ezekhez az elemekhez az RTIR használata előtt be kell állítania az alkalmazásfüggő paramétereket, amelyeket az **RTIR számlaadatok (HU)** formátum használni fog.

### <a name="line-expression-indicator"></a>Sorkifejezési mutató

A logikai típusú **lineExpressionIndicator** elemet jelenteni kell a számlasorokhoz az online számlázási rendszerben. A természetes mértékegységek esetében **igaz** értéket kell jelenteni a **lineExpressionIndicator** elemhez. Ha nincs megadva a mértékegység egy számlasorhoz akkor a **lineExpressionIndicator** elemnél **hamis** értéket kell jelenteni.

1. Az **Elektronikus jelentéskészítés** munkaterületen válassza ki a **RTIR számlaadatok (HU)** formátum legújabb importált verzióját.
2. A Műveleti ablaktáblán a **Konfigurációk** lapon a **Alkalmazásspecifikus paraméterek** csoportban válassza a **Beállítás** lehetőséget.
3. A **Keresések** gyorslapon válassza ki a formátum legújabb verziójának **UnitOfMeasureTypeLookup** elemét, majd adja meg, hogy mely mértékegységeket kell természetesként jelenteni (azaz az online számlázási rendszer **lineExpressionIndicator** eleméhez **igaz** értéket jelenteni).
4. A jogi személy összes egységének egyeztetése. Például a kilométerek esetében a következő sort kell hozzáadni:

    - **Keresés eredménye:** Természetes
    - **Sor:** 1
    - **Mértékegység kódja:** km ez az érték a jogi személy **Mértékegységek** lapjáról származik (**Szervezeti adminisztráció** \> **Beállítások** \> **Mértékegységek**).

> [!IMPORTANT]
> A lista végén adja hozzá a következő két sort.
> 
> | **Keresési eredmény** | **Sor**                                   | **Mértékegység** |
> |-------------------|--------------------------------------------|---------------------|
> | NINCS              | Ennek a sornak a listában az utolsó előttinek kell lennie | \*Üres\*           |
> | Egyéb             | Ennek a sornak a listában az utolsónak kell lennie.        | \*Nem üres\*       |

A **lineExpressionIndicator** elem jelentésekor jelenteni kell a **lineDescription** elemet. Ha a számla kapcsolódó sorában nincs érték a **lineDescription** elemhez, akkor ez az elem jelöli a kapcsolódó számla bizonylatát. Azt ajánljuk, hogy az értékesítési rendelésből feladott számlák kivételével minden típusú számla sorában határozza meg a leírást. Ebben az esetben a **lineDescription** elem jelenteni fogja a tételt.

### <a name="unit-of-measure"></a>Mértékegység

A **unitOfMeasure** elem esetében jelenteni kell a **Számlaadat** XSD-sémában megadott felsorolt lista egyik értékét.

1. Az **Elektronikus jelentéskészítés** munkaterületen válassza ki a **RTIR számlaadatok (HU)** formátum legújabb importált verzióját.
2. A Műveleti ablaktáblán a **Konfigurációk** lapon a **Alkalmazásspecifikus paraméterek** csoportban válassza a **Beállítás** lehetőséget.
3. A **Keresések** gyorslapon válassza ki a **UnitOfMeasureLookup** elemet a formátum legújabb verziójához, majd adja meg a referencia mértékegységek és az Online számlázási rendszer sorszámozott listája közötti megfeleltetést. Például a kilométerek esetében a következő sort kell hozzáadni:

    - **Keresés eredménye:** KILOMÉTER
    - **Sor:** 1
    - **Mértékegység kódja:** km (ez az érték a jogi személy **Mértékegységek** lapjáról származik)

A jogi személy összes mértékegységének egyeztetése, hogy megtalálhasson egy kapcsolódó értéket a számozott listában.

| **UnitOfMeasureType** | **Leírás (hu)**               | **Leírás (en-us)** |
|-----------------------|------------------------------------|-------------------------|
| PIECE                 | Darab                              | Piece                   |
| KILOGRAM              | Kilogramm                          | Kilogram                |
| TON                   | Metrikus tonna                     | Metric ton              |
| KWH                   | Kilowatt óra                       | Kilowatt hour           |
| DAY                   | Nap                                | Day                     |
| HOUR                  | Óra                                | Hour                    |
| MINUTE                | Perc                               | Minute                  |
| MONTH                 | Hónap                              | Month                   |
| LITER                 | Liter                              | Liter                   |
| KILOMETER             | Kilométer                          | Kilometer               |
| CUBIC_METER           | Köbméter                           | Cubic meter             |
| METER                 | Méter                              | Meter                   |
| LINEAR_METER          | Folyóméter                         | Linear meter            |
| CARTON                | Karton                             | Carton                  |
| PACK                  | Csomag                             | Pack                    |
| OWN                   | Saját mennyiségi egység megnevezés | Own unit of measure     |

> [!IMPORTANT]
> Ahelyett, hogy az összes **saját** értékét hozzáadja a listához, az **OWN** keresési eredményhez definiálhatja a **\*Nem üres\*** értéket. A program minden egyéb értéket **OWN** értékkel fog jelenteni. Az **OWN** keresési eredményt hozzá kell adni, és az utolsóként kell szerepelnie a listán.

A **unitOfMeasureOwn** elemnek jelentenie kell információkat azokról a mértékegységekről, amelyhez nem tartozik érték a **unitOfMeasure** elem számozott listáján. Ezt az elemet jelenteni kell, ha a **unitOfMeasure** elem értéke **OWN**.

Az alkalmazásfüggő paraméterek beállítását exportálhatja a jelentés egyik verziójából, és importálhatja azt egy másik verziójába. A beállításokat egy jelentésből is exportálhatja, és egy másik jelentésbe importálhatja, feltéve, hogy mindkét jelentéshez ugyanaz a keresésimező-struktúra van hozzárendelve.

Ha befejezte a feltételek beállítását, módosítsa az **Állapot** mező értékét **Kész** értékre, mentse a módosításokat, és zárja be a lapot.

## <a name="import-a-package-of-data-entities-that-includes-a-predefined-em-setup"></a>Előre meghatározott EM-beállításokat tartalmazó adatentitások csomagjának importálása

Az EM-funkció segítségével különféle dokumentumtípusokhoz különböző elektronikus jelentéskészítési folyamatok karbantartása lehetséges. Az elektronikus üzenetekkel kapcsolatos további tudnivalókat lásd: [Elektronikus üzenetküldés](https://github.com/MicrosoftDocs/Dynamics-365-Operations/blob/HU-RTIR/articles/finance/general-ledger/electronic-messaging.md).

Az EM funkciónak a RTIR-hez történő beállításának folyamata számos lépésből áll. Mivel néhány előre definiált entitás használva van az ER-konfigurációkban, fontos, előre meghatározott értéke csomagját használja, amelyek a kapcsolódó táblákhoz adatentitások csomagjaként vannak közzé téve.

1. Az [LCS-ben](https://lcs.dynamics.com/v2) nyissa meg a Közös eszköz könyvtárat, és válassza ki az **Adatcsomag** eszköztípust.
2. Az adatcsomagok listájában keresse meg a **HU RTIR setup.zip**, és töltse le a számítógépére. A csomagnak számos verziója lehet. Ügyeljen arra, hogy a legújabb verziót töltse le.
3. A hu RTIR Setup. zip fájl letöltése után nyissa meg a Finance alkalmazást, válassza ki azt a vállalatot, amelynek együtt fog működni a Magyar online számlázási rendszerrel, majd nyissa meg a **Munkaterületek** \> **Adatkezelés** lehetőséget.
4. Az **Adatkezelés** munkaterületen nyissa meg a **Keretrendszer paraméterei** \> **Entitás beállításai** elemet, majd válassza az **Entitáslista frissítése** lehetőséget. Várja meg a megerősítést a frissítés elvégzéséről. Az entitások listájának frissítésével kapcsolatos további tudnivalókat lásd: [Entitáslista frissítése](https://docs.microsoft.com/dynamics365/dev-itpro/data-entities/data-entities#entity-list-refresh).
5. Annak az ellenőrzése, hogy a forrásadatok és a céladatok megfelelően vannak leképezve. A további tudnivalókat lásd az [Adatimportálási és -exportálási feladatok](https://docs.microsoft.com/dynamics365/dev-itpro/data-entities/data-import-export-job#validate-that-the-source-data-and-target-data-are-mapped-correctly) szakaszban.
6. Mielőtt az adatentitásokat első alkalommal használná, hogy adatokat importáljon a csomagból, szinkronitálja a forrásanyagok és a céladatok leképezéseit. A csomag listájában válasszon ki egy adatentitást, majd a művelet ablaktáblán válassza a **Cél-hozzárendelés módosítása** lehetőséget.
7. A csomaghoz tartozó rácsa fölött jelölje be a **Leképezés generálása** lehetőséget hozzárendelés nulláról történő létrehozásához, majd mentse a megfeleltetést.
8. Az importálás megkezdése előtt ismételje meg a 6–7. lépést a csomagban szereplő minden egyes adatentitás esetében.

    Az adatkezeléssel kapcsolatos további tudnivalókért lásd: [Adatkezelés](https://docs.microsoft.com/dynamics365/dev-itpro/data-entities/data-entities-data-packages).

9. Most importálnia kell az adatokat a HU RTIR setup.zip fájlból a kiválasztott vállalatba. Az **Adatkezelés** munkaterületen válassza az **Importálás** lehetőséget.
10. Válassza a **Feltöltés és hozzáadás** lehetőséget , válassza ki a **HU RTIR setup.zip** fájlt a számítógépen, és töltse fel azt.
11. Az adatentitások feltöltése után a műveleti ablaktáblán válassza az **Importálás** elemet.

![Adatkezelési munkaterület](media/1_Setup_EM.png)

Értesítést fog kapni az **Üzenetekben**, vagy a lap manuális frissítésével megtekintheti az adatimportálási folyamatokat. Az importálási folyamat befejezésekor a **Végrehajtási összesítő** lap az eredményeket jeleníti meg.

A HU RTIR setup.zip csomag a Magyar online számlázási rendszerrel való együttműködésre képes **Online számlázás** feldolgozás beállítását teszi lehetővé. A következő ábra az **Online számlázás** feldolgozásának sémáját mutatja be.

![Online számlázás feldolgozásának diagramja](media/2_Scema.png)

A következő táblázat leírja az **Online számlázás** feldolgozásának feldolgozási műveleteit.

| **Művelet**                     | **Típus**                            | **Leírás**                                                                                                                                                                                                                                                                                                                                                                                                    |
|--------------------------------|-------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| EM-elemek létrehozása                | Üzenetcikk végrehajtási szint        | Ez a művelet az **EMCreateItemsController_HU** futtatható osztályt futtatja a feladott kiállított számlákra vonatkozó elektronikus üzenetelemek létrehozásához. A **EMCreateItemsController_HU** futtatható osztály paramétereinek további beállításai szükségesek.                                                                                                                                                                    |
| EM-elemek értékelése              | Üzenetcikk végrehajtási szint        | Ez a művelet a **EMAdditionalFieldsEvaluationController_HU** végrehajtható osztályt futtatja az elektronikus üzenetek elemeihez tartozó további mezőértékeket számításához. Ezek az értékek tartalmazzák a számla műveletet, az eredeti számla hivatkozását, valamint az utolsó sor számát.                                                                                                                                                |
| EM létrehozása                    | Elektronikus jelentéskészítés exportálása         | Ez a művelet az **RTIR számla adatok (HU)** formátumot futtatja, amely az online számlázási rendszerbe elküldhető számlák csomagját hozza létre.                                                                                                                                                                                                                                                                       |
| Token-kérelem létrehozása         | Elektronikus jelentéskészítés üzenet exportálása | Ez a művelet futtatja az **RTIR tokencsere-kérelem (HU)** formátumot, amely XML-formátumban hozza létre a cseretoken fájlját.                                                                                                                                                                                                                                                                                                  |
| Token-kérelem beküldése           | Webes szolgáltatás                         | Ez a művelet XML-formátumú token-fájlt küld a **Tokencsere** webszolgáltatásnak.                                                                                                                                                                                                                                                                                                                            |
| Tokenválasz importálása          | Elektronikus jelentéskészítés importálása         | Ez a művelet importálja az Online számlázási rendszer válaszát, amely az **Üzenet további mezői** gyorslapon van fogadva az **RTIR importálási formátum (HU)** konfigurációval.                                                                                                                                                                                                       |
| Számlakérelem létrehozása       | Elektronikus jelentéskészítés üzenet exportálása | Ez a művelet futtatja az **RTIR számlakérelem kezelése (HU)** formátumot a **ManageInvoiceRequest.xml** fájlnak a számlák kódolásával történő létrehozásához, a kérelemben szereplő token beszúrásához és így tovább.                                                                                                                                                                                                                                |
| Számlakérelem benyújtása         | Webes szolgáltatás                         | Ez a művelet elküldi a **ManageInvoiceRequest.xml** fájlt a **Számlakezelés** webszolgáltatáshoz.                                                                                                                                                                                                                                                                                                                   |
| Számlaválasz importálása        | Elektronikus jelentéskészítés importálása         | Ez a művelet importálja az Online számlázási rendszer válaszát, és tárolja a tranzakciós azonosítót, amely az **Üzenet további mezői** gyorslapon van fogadva az **RTIR importálási formátum (HU)** konfigurációval.                                                                                                                                                                                              |
| Állapotkérelem létrehozása        | Elektronikus jelentéskészítés üzenet exportálása | Ez a művelet futtatja az **RTIR számlaállapot lekérdezési kérelem (HU)** formátumot a **QueryInvoiceStatusRequest.xml** fájl létrehozásához.                                                                                                                                                                                                                                                                                       |
| Állapotkérelem elküldése          | Webes szolgáltatás                         | Ez a művelet elküldi a **QueryInvoiceStatusRequest.xml** fájlt a **Számlaállapot lekérdezése** webszolgáltatáshoz.                                                                                                                                                                                                                                                                                                        |
| Állapotválasz importálása         | Elektronikus jelentéskészítés importálása         | Ez a művelet importálja az Online számlázási rendszer válaszát. Ha az EM elem állapota **Fogadva** (ami azt jelzi, hogy a számlát az Online számlázási rendszer fogadta) vagy **Feldolgozás alatt** (ami azt jelzi, hogy a számlát az Online számlázási rendszer éppen feldolgozza), akkor a rendszer újra elküldi az állapotjelentés-kérést, amíg az EM elem állapota fel nem frissül a **Feldolgozott** értékre. |
| EM-elemek kizárása               | Felhasználói feldolgozás                     | Ez a kézi felhasználói művelet visszaállítja az EM-elem állapotát a **Kiértékelt** értékről **Kizárva** értékre, és kizárja az elemet a feldolgozásból.                                                                                                                                                                                                                                                                                 |
| EM cikkek belefoglalása a fedolgozásba | Felhasználói feldolgozás                     | Ez a manuális felhasználói művelet visszaállítja az EM-elem állapotát a **Kizárt** vagy **Manuális szerkesztés** értékről **Kiértékelve** értékre.                                                                                                                                                                                                                                                                                                |
| EM elem állapotának visszaállítása           | Felhasználói feldolgozás                     | Ez a manuális felhasználói művelet visszaállítja az EM-elem állapotát a **Elutasítva** értékről **Létrehozva** értékre.                                                                                                                                                                                                                                                                                                                         |
| EM állapot visszaállítása                | Üzenetszint felhasználói feldolgozás       | Ez a manuális felhasználói művelet alaphelyzetbe állítja az elektronikus üzenet állapotát **Hiba a számlaválasz importálása során**, **Hiba a számlakérelem elküldése során** vagy **Hiba a tokenválasz importálása során** állapotról **Létrehozva** állapotra, hogy az elektronikus üzenet feldolgozása folytatódhasson.                                                                                                                                               |

Ha további tájékoztatást szeretne kapni az RTIR-hez tartozó csomag adatentiásainak előbeállításiaról, lásd [1. függelék: Elektronikus üzenetek beállítása az RTIR-hez](https://github.com/MicrosoftDocs/Dynamics-365-Operations/blob/HU-RTIR/articles/finance/localizations/emea-hun-online-invoicing.md#appendix-1-electronic-message-setup-for-rtir) részt a témakör későbbi szakaszában.

## <a name="set-up-em-for-rtir"></a>EM beállítása az RTIR-hez

Az adatentitások adatbázisba importálását követően hajtsa végre az alábbi lépéseket annak érdekében, hogy az EM funkció használatra kész legyen.

1. Nyissa meg az **Adó** \> **Beállítások** \> **Elektronikus üzenetek** \> **Végrehajtható osztály beállításai** menüpomtot, és válassza ki az **Üzenetelemk létrehozása** végrehajtható osztályt, ami az **EMCreateItemsController_HU** végrehajtható osztály nevéhez van társítva.
2. A Műveleti panelen válassza a **Paraméterek** elemet.
3. A párbeszédpanelen a **Szerepeltetni kívánt rekordok** gyorslapon határozza meg a lekérdezés paramétereinek értékeit.

![Új elektronikus üzenetelemek hozzáadása párbeszédpanel](media/3_New_EM_items.png)

4. Válassza ki az **OK** lehetőséget.
5. A **Végrehajtható osztály beállításai** lapon válassza ki az **EMAdditionalFieldsEvaluationController_HU** végrehajtható osztály nevéhez **További mezők értékelése** lehetőséget válassza ki a **Paraméterek** elkemet a Műveleti ablaktáblán, majd a párbeszádpanelen határozza meg a végrehajtható osztály paramétereinek értékeit.

![További mezők értékelési paramétereinek párbeszédpanel](media/4_Additional_fields.png)

A paramétereknél a következő értékeket kell beállítani.

| **Paraméter neve**                        | **Érték**                            |
|-------------------------------------------|--------------------------------------|
| Jelentési időszak kezdő dátuma                  | Az a dátum, amikor el szeretné indítani a RTIR-t |
| Kizárt cikkek állapota                 | Kizárva                             |
| Manuális szerkesztést igénylő elemek állapota | Manuális szerkesztés                       |
| Művelet mező                           | Művelet                            |
| Eredeti üzenet elemmező               | Eredeti üzenetelem                |
| Utolsó sor hivatkozási száma mező          | Utolsó sor hivatkozási száma           |
| Módosítási index                        | Módosítási index                   |

6. Válassza ki az **OK** lehetőséget.

    A magyar online számlázási rendszerrel való együttműködéshez technikai felhasználónevet és jelszót, valamint aláírási és helyettesítési kulcsokat kell megadni. Ennek a kényes adatnak a tárolásár két lehetősége van:

    - Azure Key Vault-tárhely
    - Helyi tároló

7. Nyissa meg a **Rendszerfelügyelet** \> **Beállítások** \> **Rendszerparaméterek** lehetőséget , és állítsa be a **Speciális tanúsítványtároló használata** lehetőséget **Nem** értékre, ha szeretné helyben tárolni a kényes adatokat. A Key Vault-tárhely használatához válassza az **Igen** beállítást. A Key Vault beállításával kapcsolatos további tudnivalókat lásd: [Azure Key Vault-ügyfél beállítása](https://support.microsoft.com/help/4040305/setting-up-azure-key-vault-client) és [Azure Key Vault-tárhely karbantartása](https://support.microsoft.com/help/4040294/maintaining-azure-key-vault-storage).
8. Ha a **Rendszerparaméterek** lap **Speciális tanúsítványtároló használata** beállítását **Igen** értékre állítja , akkor be kell állítania a Key Vault paramétereit a **Rendszerfelügyelet** \> **Beállítások** \> **Key Vault paraméterei** helyen.

![Key Vault paraméterek oldala](media/5_Key_Vault.png)

9. Nyissa meg az **Adó** \> **Beállítások** \> **Paraméterek** \> **Online számlázási rendszer paraméterei** menüpontot, és adja meg a következő adatokat:

    - Technikai felhasználó neve
    - Technikai felhasználó jelszava
    - Aláírási kulcs
    - Helyettesítő kulcs

10. Ha a **Rendszerparaméterek** lap **Speciális tanúsítványtároló használata** beállítását **Igen** értékre állítja , válassza a kapcsolódó titkokat az **Online számlázási rendszer paraméterei** lap **Általános** lapján.

![Az online számlázási rendszer azon paraméterei, amelyeknél a Speciális tanúsítványtároló használata beállítás értéke Igen](media/6_Key_Vault.png)

Azt is megteheti, hogy ha a **Speciális tanúsítványtároló használata** beállítást **Nem** értékre állítja, és manuálisan adja meg a magyar online számlázási rendszerrel való együttműködéshez kapott technikai felhasználónevet és jelszót, illetve az aláírási kulcsot és a helyettesítő kulcsot. A további tudnivalókat lásd [Regisztrációs eljárással kapcsolatos információk](https://onlineszamla-test.nav.gov.hu/tajekoztatas_a_regisztraciorol).

![Az online számlázási rendszer azon paraméterei, amelyeknél a Speciális tanúsítványtároló használata beállítás értéke Igen](media/7_system_parameters.png)

11. Nyissa meg az **Adó** \> **Beállítások** \> **Paraméterek** \> **Elektronikus üzenetek** \> **Webszolgáltatás beállításai** lehetőséget, és adja meg a következő adatokat a webszolgáltatások internetcímének meghatározásához.

| **Webszolgáltatás neve** | **Internetcím tesztelése**                                                      |
|----------------------|-----------------------------------------------------------------------------------|
| Számlák kezelése      | `https://api-test.onlineszamla.nav.gov.hu/invoiceService/v2/manageInvoice`         |
| Számlaállapot lekérdezése | `https://api-test.onlineszamla.nav.gov.hu/invoiceService/v2/queryTransactionStatus` |
| Tokencsere       | `https://api-test.onlineszamla.nav.gov.hu/invoiceService/v2/tokenExchange`          |

Az internetes címeket a Magyar online számlázási rendszer határozza módosíthatja. Ezért azt ajánljuk, hogy a [magyar online számlázási rendszer hivatalos weboldalán](https://onlineszamla.nav.gov.hu/) ellenőrizze a tényleges internetes címeket. A webhely azon aktuális *termelési* internetcímekről is tartalmaz adatokat , amelyeket be kell állítania.

12. Nyissa meg az **Adó** \> **Beállítások** \> **Paraméterek** \> **Elektronikus üzenetek** \> **Üzenet-feldolgozási műveletek** menüpontot, és válassza az **EM létrehozása** lehetőséget.
13. Az **Üzenetek száma exportálásonként** mezőben határozza meg, hogy hány üzenetelemet lehet szerepeltetni egy üzenetben. Ez a szám nem lehet nagyobb, mint 100.
14. A **Mellékelt elemek tömörítési típusa** mezőben adja meg a **Nincs** beállítást , és a **Fájlok csatolása a kimeneti archívumból az elemekhez** lehetőséget **Igen** értékre.

![Üzenetfeldolgozási műveletek lap, "EM" létrehozása lap](media/8_actions.png)

15. Nyissa meg az **Adó** \> **Beállítások** \> **Elektronikus üzenetek** \> **Elektronikus üzenetfeldolgozás** menüpontot, válassza ki az **Online számlázás** feldolgozását, majd a **Köteg** gyorslapon válassza ki a **Köteg létrehozása** elemet.
16. Biztonsági szerepkörök beállítása az **Online számlázás** feldolgozásához. Előfordulhat, hogy a felhasználók különböző csoportjainak kell hozzáféréstadni **Online számlázás** feldolgozásához. A feldolgozáshoz való hozzáférést korlátozhatja a rendszerben megadott biztonsági csoportok alapján. Nyissa meg az **Adó** \> **Beállítás** \> **Elektronikus üzenetek** \> **Elektronikus üzenetek feldolgozása** menüpontot, válassza ki az **Online számlázás feldolgozása** lehetőséget, és adja hozzá azokat a biztonsági csoportokat, amelyeknek dolgozniuk kell a feldolgozással kapcsolatosan. Ha nincs definiálva biztonsági csoport a feldolgozáshoz, akkor csak a rendszergazda láthatja a feldolgozást az **Elektronikus üzenetek** oldalon.

## <a name="set-up-financial-reasons-for-rtir"></a>Pénzügyi okok beállítása az RTIR-hez

Minden, a magyar online számlázási rendszernek jelentendő számlához meg kell adni egy konkrét művelettípust, és azt továbbítani kell az **\<invoiceOperation\>** elemben e **ManageInvoiceRequest.xml** fájl elemeként. A legtöbb esetben a Finance automatikusan meghatározza a számla műveleti típusát a magyar online számlázási rendszer követelményeiben meghatározott szabályoknak megfelelően:

- **Létrehozás** – Ezt a számlaműveleti típust akkor kell megadni, ha a Finance nem határoz meg az eredeti számlára mutató hivatkozást.
- **Módosítás** – Ezt a számlaműveleti típust akkor kell megadni, ha a Finance meghatároz az eredeti számlára mutató hivatkozást.

A számla feladásakor a **Pénzügyi okok** oldalon manuálisan is megadható a számlához tartozó Művelettípus.

- Lépjen a **Szervezeti adminisztráció** \> **Beállítás** \> **Pénzügyi okok** menüpontot. A **Művelet** oszlopban határozza meg a művelettípusokat. A magyar online számlázási rendszer a következő értékeket engedélyezi:

    - **Létrehozás** – A megadott pozíció számlája eredeti számlának tekintendő.
    - **Helyesbítés** – a számla egy helyesbítő számla.
    - **Sztronó** – a számla egy sztornószámla.

A számla feladásakor a kapcsolódó pénzügyi ok alkalmazásával a számlára vonatkozóan egy specifikus művelettípust jelenthet.

Például egy **Sztornó** művelettípus számláját be kívánja nyújtani az online számlázási rendszerbe. Ehhez a számlához adjon meg egy olyan pénzügyi okot, amelynek értéke **Sztornó** a **Művelet** mezőben. Olyan helyesbítő számla küldéséhez, amely nem hivatkozik az eredeti számlára, adja meg a **Művelet** mezőben a **Helyesbítés** értékkel rendelkező pénzügyi okot.

## <a name="rtir-process"></a>RTIR-folyamat

A Finance automatikusan futtatja a feldolgozásban szereplő műveleteket az üzenetek és az üzenetekelemek állapota alapján.

### <a name="additional-fields-for-message-items"></a>További mezők az üzenetelemekhez

Minden üzenetelem további, a feldolgozáshoz szükséges mezőkkel rendelkezik. A rendszer automatikusan beírja az értékeket a további mezőkbe, amikor műveleteket futtat.

| **További mező**       | **Leírás**                                                                                                                                                                                                                                                                                                                                                                                                                        |
|----------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Művelet                  | Az értékek többek között a **Létrehozás**, **Helyesbítés** és **Sztornó**. A Finance a kiegészítő mező értékét az **EM elemek kiértékelése** művelet végrehajtása során állítja be. A **Művelethez** tartozó további mező értéke automatikusan vagy a számlán szereplő pénzügyi indokkal definiálható. További tudnivalókért lásd a [Pénzügyi okok beállítása az RTIR-hez](#set-up-financial-reasons-for-rtir) című részt, a témakör korábbi részében.                           |
| Eredeti számlaelem      | Ha a **Művelet** kiegészítő mező **Helyesbítés** vagy **Sztornó** értékre van beállítva , akkor az eredeti **Számla elem** kiegészítő mezőt be kell állítani. Ha a rendszer nem tudja beállítani ezt a mezőt, a kapcsolódó üzenet elemét **Manuális szerkesztés** értékre állítja , és ezt a mezőt manuálisan kell beállítania.                                                                                                                                                  |
| Index                      | Ez a kiegészítő mező meghatározza a számla pozícióját a kérelemben (a számlák csomagja). Az érték jelentése a **ManageInvoiceRequest.xml** fájl **\<index\>** elemében történik. Ezt a kiegészítő mezőt a program automatikusan kitölti, amikor a **Számlázási kérelem létrehozása** művelet fut.                                                                                                                                          |
| Utolsó sor hivatkozási száma | A **Létrehozás** művelettípusú üzenetelemeknél ez a kiegészítő mező a csomag utolsó számát (a számlasor mennyiségét) tartalmazza. A **Helyesbítés** vagy **Sztornó** művelettípusú üzeneteknél ez a kiegészítő mező az eredeti számla **Index** értékét tartalmazza a **\<modificationIndex\>** elemnek megfelelően. Ezt a kiegészítő mezőt a program automatikusan kitölti, amikor a **Kiértékelés** művelet fut. |

### <a name="run-online-invoicing-processing"></a>Online számlázás feldolgozásának futtatása

Ez az eljárás végigvezeti a RTIR-folyamaton.

1. Lépjen az **Adó** \> **Lekérdezések és jelentések** \> **Elektronikus üzenetek** \> **Elektronikus üzenetelemek**  menüpontra.
2. A Műveleti ablaktáblán kattintson a **Feldogozás futtatása** elemre.
3. A legördülő párbeszédpanel **Feldolgozás** mezőjében válaassza az **OnlineInvoicing** lehetőséget.
4. Ha az **Online számlázás** feldolgozásának minden lehetséges műveletét futtatni szeretné , törölje a jelet a **Művelet kiválasztása** jelölőnégyzetből. Ha csak egy konkrét műveletet szeretne futtatni, jelölje be a **Művelet kiválasztása** jelölőnégyzetet, majd a **Művelet** mezőben válassza ki a futtatni kívánt műveletet.

### <a name="exclude-invoice-reporting-in-rtir"></a>Számlajelentés kihagyása az RTIR-ben

Ha ki szeretne zárni egy számlát a feldolgozásból az RTIR-ben, hajtsa végre az alábbi lépéseket.

1. Lépjen az **Adó** \> **Lekérdezések és jelentések** \> **Elektronikus üzenetek** \> **Elektronikus üzenetelemek**  menüpontra.
2.  Válassza az **Állapot frissítése** lehetőséget a Művelet panelen, hogy az üzenetelem állapotát **Kizárva** értékre. A program nem veszi figyelembe a jelentésben azokat a számlákat, amelyek állapota **Kizárva**.
3. Az **Állapotfrissítés** párbeszédpanelen válassza az **Online számlázás** feldolgozást. Ezután a **Művelet** mezőben válassza az **Üzenetelem kihagyása** lehetőséget. Az **Új állapot** mezőben válassza a **Kihagyva** lehetőséget.
4. További feltételek meghatározása a **Rekordok belefoglalása** gyorslap használatával, annak meghatározásához, hogy mely számlákat kell kizárni a további feldolgozásból.

### <a name="postpone-invoice-reporting-in-rtir"></a>Számlajelentés elhalasztása az RTIR-ben

A számlák RTIR-be történő jelentésének elhalasztásához kövesse az alábbi lépéseket.

1. Lépjen az **Adó** \> **Lekérdezések és jelentések** \> **Elektronikus üzenetek** \> **Elektronikus üzenetelemek**  menüpontra.
2. Válassza az **Állapot frissítése** lehetőséget a Művelet panelen, hogy az üzenetelem állapotát **Elhalasztott** értékre. A program nem veszi figyelembe a jelentésben azokat a számlákat, amelyek állapota **Elhalasztott**.
3. Az **Állapotfrissítés** párbeszédpanelen válassza az **Online számlázás** feldolgozást. Ezután a **Művelet** mezőben válassza a **Frissítés elhalasztottra** lehetőséget a **Művelet** mezőben. Az **Új állapot** mezőben válassza az **Elahlasztva** lehetőséget.
4. További feltételek meghatározása a **Rekordok belefoglalása** gyorslap használatával, annak meghatározásához, hogy mely számlák jelentését kell elhalasztani.

Az üzenetelemek **Kizárt** vagy **Elhalasztott** állapotát bármikor vissza lehet állítani a **Frissítés a kezdeti állapotra** lehetőség kiválasztásával.

## <a name="appendix-1-electronic-message-setup-for-rtir"></a>1. függelék: Elektronikus üzenetek beállítása az RTIR-hez

Ez a függelék azzal kapcsolatosan tartalmaz információkat, hogy hogyan kell beállítani az EM funkciókat úgy, hogy az **Online számlázás** feldolgozását támogassa. Ezekkel az adatokkal határozhatja meg, hogy az EM funkció helyesen van-e beállítva.

Bár ez a függelék a beállítás legfontosabb adatait tartalmazza, nem tartalmazza az összes adatot. Azt ajánljuk, hogy olyan adatentitások csomagját alkalmazza, amelyek előzetes beállításokat tartalmaznak a funkcionalitáshoz, és a RTIR feldolgozásához szükséges összes adatot tartalmazzák.

### <a name="web-service-settings"></a>Webszolgáltatás-beállítások

Az **Online számlázás** feldolgozása a következő webes szolgáltatásokat használja.

| **Webszolgáltatás neve** | **Internetcím tesztelése**                                                      |
|----------------------|-----------------------------------------------------------------------------------|
| Számlák kezelése      | `https://api-test.onlineszamla.nav.gov.hu/invoiceService/v2/manageInvoice`          |
| Számlaállapot lekérdezése | `https://api-test.onlineszamla.nav.gov.hu/invoiceService/v2/queryTransactionStatus` |
| Tokencsere       | `https://api-test.onlineszamla.nav.gov.hu/invoiceService/v2/tokenExchange`          |

### <a name="additional-fields"></a>További mezők

Ha meg kívánja tekinteni az **Online számlázás** feldolgozásának további mezőinek teljes leírását, tekinste meg a [További mezők az üzenetelemekhez](#additional-fields-for-message-items) szakaszt a témakör korábbi részében.

> [!NOTE]
> Ezeket a mezőket a felhasználó nem módosíthatja.

### <a name="electronic-message-item-types"></a>Elektronikusüzenet-elem típusai

Az elektronikus üzenetek beállítása az **Online számlázás** feldolgozásához egy típusú elektronikus üzenetelemet használ: **Vevői számla**.

### <a name="electronic-message-item-statuses"></a>Elektronikusüzenetelem-állapotok

Az **Online számlázás** feldolgozása a következő elektronikus üzenetelem-állapotokat használja.

| **Állapot**                  | **Leírás**                                                                                      | **Az ilyen állapotú rekordok törölhetők** |
|-----------------------------|------------------------------------------------------------------------------------------------------|-------------------------------------------|
| Elfogadva                    | Az online számlázási rendszer elfogadta az üzenetelemet.                                        | Igen                                       |
| Létrehozva                     | Az üzenetelem létrejött.                                                                        | Igen                                       |
| Kiértékelt                   | Az üzenethez tartozó további mezők ki lettek értékelve.                                                 | Igen                                       |
| Kizárva                    | Az üzenetelem ki van zárva a feldolgozásból.                                                        | Igen                                       |
| Előzetes feldolgozás alatt            | Az üzenetelem előfeldolgozása folyamatban van.                                                        | Igen                                       |
| A számlázási kérelemben szerepel | Az üzenet része a számla kezelésére vonatkozó kérelemben.                                          | Igen                                       |
| Belefoglalva az üzenetbe         | Az üzenetelemet tartalmazza az üzenet.                                                         | Igen                                       |
| Manuális szerkesztés              | Az üzenetelem manuális szerkesztése szükséges.                                                            | Igen                                       |
| Függőben lévő állapotválasz     | Az üzenet egy állapotválaszra várakozik.                                                   | Igen                                       |
| Feldolgozva                   | Az üzenetelem fel lett dolgozva.                                                                      | Igen                                       |
| Feldolgozás                  | Az online számlázási rendszer feldolgozza az üzenetelemet.                                  | Igen                                       |
| Bevételezve                    | Az online számlázási rendszer fogadta az üzenetelemet.                                        | Igen                                       |
| Elutasítva                    | Az online számlázási rendszer elutasította az üzenetelemet.                                        | Igen                                       |
| Elküldött                        | Az online számlázási rendszer részére az üzenetelem el lett küldve.                                            | Igen                                       |
| Mentve                       | Az üzenetelem az online számlázási rendszerben el lett mentve, de a feldolgozás még nem fejeződött be. | Igen                                       |

### <a name="electronic-message-statuses"></a>Elektronikusüzenet-állapotok

Az **Online számlázás** feldolgozása a következő elektronikus üzenetállapotokat használja.

| **Állapot**                              | **Leírás**                                                                         | **Az ilyen állapotú rekordok törölhetők** |
|-----------------------------------------|-----------------------------------------------------------------------------------------|-------------------------------------------|
| Hiba a számlakérelem létrehozásakor        | Technikai hiba történt a számlakérelem létrehozásakor.                | Nincs                                        |
| Hiba az állapotkérelem létrehozásakor         | Technikai hiba történt az állapotkérelem létrehozásakor.                 | Nincs                                        |
| Hiba a tokenkérelem létrehozásakor          | Technikai hiba történt az tokenkérelem létrehozásakor.                  | Nincs                                        |
| Hiba a számlaválasz importálásakor        | Technikai hiba történt a számlaválasz importálása során.                | Nincs                                        |
| Az állapotkérelem hibaválaszának importálása | Technikai hiba történt a az állapotkérelemre adott válasz importálása során. | Nincs                                        |
| Hiba a számlakérelem küldésekor           | Technikai hiba történt a számlakezelési kérelem elkeüldésekor.              | Nincs                                        |
| Hiba az állapotkérelem küldésekor            | Technikai hiba történt a számlaállapot-kérelem elküldésekor.              | Nincs                                        |
| Hiba a tokenkérelem küldésekor             | Technikai hiba történt az tokenkérelem elküldésekor.                       | Nincs                                        |
| Hiba a tokenválasz importálásakor          | Technikai hiba történt a tokenválasz importálása során.                  | Nincs                                        |
| Létrehozva                               | Az üzenet létre lett hozva.                                                              | Nincs                                        |
| Folyamatban                              | Az online számlázási rendszer feldolgozza az üzenetet.                          | Nincs                                        |
| Számlakérelem létrehozva               | A számlák beküldésére vonatkozó kérelem létre lett hozva.                                           | Nincs                                        |
| Számlakérelem beküldve               | A számlákat tartalmazó kérelem az Online számlázási rendszerbe be lett küldve.        | Nincs                                        |
| Feldolgozva                               | Az online számlázási rendszer feldolgozta az üzenetet.                               | Nincs                                        |
| Elküldött                                    | Az üzenet létre el lett küldve.                                                                   | Nincs                                        |
| Állapotkérelem létrehozva                | A számlaállapot-kérelem létrejött.                                               | Nincs                                        |
| Állapotkérelem beküldve                | A számlaállapot-kérelem be lett küldve.                                               | Nincs                                        |
| Token fogadva                          | A token fogadva lett.                                                                 | Nincs                                        |
| A tokenkérelem létrehozva                 | A tokenkérelem létre lett hozva.                                                        | Nincs                                        |
| Tokenkérelem beküldve                 | A tokenkérelem be lett küldve.                                                        | Nincs                                        |
| Tranzakcióazonosító fogadva                 | A tranzakcióazonosítót tartalmazó számlaválasz beérkezett.                     | Nincs                                        |

### <a name="electronic-message-actions"></a>Elektronikusüzenet-műveletek

A **OnlineInvoicing** feldolgozás elektronikus üzenetei műveleteinek teljes leírását lásd a [Előre meghatározott EM-beállításokat tartalmazó adatentitások csomagjának importálása](#import-a-package-of-data-entities-that-includes-a-predefined-em-setup) szakaszban a témakör korábbi részében.

### <a name="electronic-processing-actions"></a>Elektronikus feldolgozási műveletek

Az **Online számlázás** feldolgozása a következő elektronikus feldolgozási műveleteket használja.

| **Név**                       | **Futtatás külön** |
|--------------------------------|--------------------|
| EM-elemek létrehozása                | Nincs                 |
| EM-elemek értékelése              | Nincs                 |
| EM-elemek kizárása               | Igen                |
| EM létrehozása                    | Nincs                 |
| Számlakérelem létrehozása       | Nincs                 |
| Állapotkérelem létrehozása        | Nincs                 |
| Token-kérelem létrehozása         | Nincs                 |
| Számlaválasz importálása        | Nincs                 |
| Állapotválasz importálása         | Nincs                 |
| Tokenválasz importálása          | Nincs                 |
| EM cikkek belefoglalása a fedolgozásba | Igen                |
| EM elem állapotának visszaállítása           | Igen                |
| EM állapot visszaállítása                | Igen                |
| Számlakérelem benyújtása         | Nincs                 |
| Állapotkérelem elküldése          | Nincs                 |
| Token-kérelem beküldése           | Nincs                 |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]