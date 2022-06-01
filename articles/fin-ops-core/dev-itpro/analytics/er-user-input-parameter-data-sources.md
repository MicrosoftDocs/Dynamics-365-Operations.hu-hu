---
title: A FELHASZNÁLÓI BEVITELI PARAMÉTER adatforrások használata a jelentés paramétereinek megadásához
description: Ez a témakör bemutatja, hogy hogyan lehet a FELHASZNÁLÓI BEVITELI PARAMÉTER adatforrások használatával paramétereket megadni a generált jelentésekhez.
author: NickSelin
ms.date: 04/20/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERModelMappingDesigner, EROperationDesigner
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: Version 10.0.27
ms.openlocfilehash: 4e431c9dd59080af17fa073547073037ba233288
ms.sourcegitcommit: 6c1bf233748c4bc70fc5a1a9711758cdfd9e07dc
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/19/2022
ms.locfileid: "8782543"
---
# <a name="use-user-input-parameter-data-sources-to-specify-parameters-for-a-report"></a>A FELHASZNÁLÓI BEVITELI PARAMÉTER adatforrások használata a jelentés paramétereinek megadásához

[!include[banner](../includes/banner.md)]

Ha elektronikus jelentéskészítési (ER) [modellleképezést](general-electronic-reporting.md) és ER-formátum-összetevőket [tervez](er-overview-components.md#model-mapping-component) meg, [egy FELHASZNÁLÓI BEMENETI](er-overview-components.md#format-component) PARAMÉTERtípus adatforrását felhasználhatja, hogy be tudja szerezni a párbeszédpanel adatbeviteli mezőiben futásidőben, az ER-formátum végrehajtásának megkezdése előtt szükséges értékeket.*·* Ez a témakör a jelenleg *támogatott FELHASZNÁLÓI BEMENETI PARAMÉTER-adatforrásokat* írja le.

## <a name="mandatory-properties"></a><a name="mandatory-properties"></a> Kötelező tulajdonságok

Minden FELHASZNÁLÓI BEMENETI PARAMÉTERtípus adatforrására *a következő tulajdonságokat kell* megadni:

- A Név **mezőbe** írja be az adatforrás belső nevét. Ezt a nevet a konfigurált [modellleképezés](er-formula-language.md) vagy formátumösszetevő más kifejezéseinél és kötéseinél is használhatja.

## <a name="optional-properties"></a><a name="optional-properties"></a> Választható tulajdonságok

Felhasználói BEMENETI PARAMÉTER típusú adatforrások esetén a *következő tulajdonságokat lehet* megadni:

- A Címke **mezőben** adja meg a kapcsolódó adatbeviteli mezőhöz futásidőben használt címkét a párbeszédpanelen. Ha más címkeszöveget szeretne hozzáadni a különböző nyelvkódok **számára**, aktiválja a Címke mezőt, majd válassza a Fordítás **kódot**.
- A Súgó **mezőben** **·** **·** *adja meg a Formátumtervező lap vagy a Modellleképezés tervezőlap alján, a tervezés során megjelenő súgószöveget, ha egy FELHASZNÁLÓI BEVITELi* PARAMÉTERtípus szerkeszthető adatforrása ki van választva. Ez a szöveg további részleteket is nyújthat az adatforrásról, hogy a felhasználók segítséget nyújtson a szerkeszthető formátum vagy modellleképezés összetevő konfigurálása során. A fordítás lehetőség választásával más-más súgószöveget adhat meg a különböző nyelvkódok **számára**.

    > [!NOTE]
    > A **Nyelvspecifikus címkék**[és szövegek hozzáadására használható Fordítás](er-design-multilingual-reports.md#format-component) gomb csak az adatforrás hozzáadása, a módosítások mentése, majd az adatforrás ismételt megnyitása után válik elérhetővé szerkesztésre.

- A Csak **olvasható mezőben** konfigurálja a logikai értéket eredményül adó *[kifejezést](er-formula-supported-data-types-primitive.md#boolean)*.

    - **Ha** a konfigurált kifejezés futásidőben Igaz értéket ad vissza, a párbeszédpanelen halványul a kapcsolódó adatbeviteli mező, és az értéke nem változtatható meg.
    - Ha a **konfigurált** kifejezés futásidőben Hamis értéket ad vissza, vagy ha nincs beállítva kifejezés, a párbeszédpanelen elérhető a kapcsolódó adatbeviteli mező, és módosíthatja az értékét.

- Az Alapértelmezett **érték mezőben** konfigurálja azt a kifejezést, amely a hivatkozott paramétertípus értékét adja eredményül. Ez az érték arra használható, hogy futásidőben ki tudja tölteni a párbeszédpanel kapcsolódó adatbeviteli mezőjének alapértelmezett értékét.

    ER-formátum futtatásakor a párbeszédpanel kapcsolódó adatbeviteli mezőjébe futásidőben beírt értéket a program a korábban használt értékként menti a memóriába. A korábban használt értékeket a rendszer egyenként menti minden mezőhöz, a futó ER-formátumhoz, az aktuális felhasználóhoz és az aktuális szervezethez (vállalat).

    - **Állítsa Igen** **·** **értékre** az "Alapérték" beállítást, ha az Alapértelmezett érték kifejezés által visszaadott értéket mindig alapértelmezett értékként kell használni, függetlenül a korábban használt értéktől.
    - **Állítsa Nem értékre az** **·** **·**"Alapérték" beállítást, ha az Alapértelmezett érték kifejezés értéke által visszaadott értéket csak akkor használja alapértelmezettként, ha hiányzik a korábban használt érték.

    > [!NOTE]
    > Ha a Mindig **visszaállítva** **az** alapértelmezett értékre beállítást Igen értékre állítja, **az Alapértelmezett érték mezőben konfigurálni kell egy kifejezést.**

- Ha a Többszörös **kijelölés** **engedélyezése** beállítást Igen beállításra adja meg, futásidőben több értéket is bejelenhet a konfigurált paraméterhez. Ha Nem értékre áll **be**, csak egy értéket választhat.

    > [!NOTE]
    > Ez a beállítás nem alkalmazható minden FELHASZNÁLÓI *BEVITELI PARAMÉTERtípusra*. A tervezés ideje alatt kivétel történt, amely tájékoztatja a felhasználót, hogy a konfigurált felhasználói bemeneti paraméter nem támogatja a többszörös kijelölést, és csak egy értéket lehet kiválasztani vagy megadni.
    >
    > Ha a **Többszörös** **kijelölés** engedélyezése beállítást Igen értékre áll be, **és** az Alapértelmezett érték mezőben megadott egy kifejezést, akkor a kifejezés csak egyetlen alapértelmezett érték beállítását teszi lehetővé.

- A Láthatóság **szerkesztése beállítás** kiválasztásával adja meg, hogy futásidőben megjelenik-e a konfigurált paraméter a párbeszédpanelen.

    > [!NOTE]
    > A FELHASZNÁLÓI BEVITELi PARAMÉTERtípus adatforrásának alapértelmezett láthatósága a *őket* táraó ER-összetevőtől függ.
    >
    > - Ha egy adatforrás a formátumösszetevőben van konfigurálva, akkor alapértelmezés szerint látható.
    > - Ha egy adatforrás konfigurálva van a modellleképezési összetevőben, akkor csak akkor látható, ha az adatforrás értéke az ER-összetevő futtatásakor hatással van az eredményre. Például hozzáadott egy adatforrást, de nem használja az aktuális modellleképezési összetevő kifejezésekben és kötésében. Ebben az esetben alapértelmezés szerint a vonatkozó adatbeviteli mező futásidőben nem jelenik meg a párbeszédpanelen. 

    Konfigurálja a **Képletszerkesztő** lapján **a Képlet** mezőben azt a kifejezést, amely logikai értéket *ad* eredményül.

    - **Ha** a konfigurált kifejezés Igaz értéket ad vissza futásidőben, vagy ha nincs beállítva kifejezés, futásidőben a párbeszédpanelen megjelenik a kapcsolódó adatbeviteli mező.
    - Ha a konfigurált kifejezés Hamis értéket ad vissza, futásidőben rejtve marad a **kapcsolódó** adatbeviteli mező a párbeszédpanelen. Ha futásidőben más kifejezésekkel hívják, akkor az visszaadja az alapértelmezett értéket, a korábban használt értéket vagy az aktuális adattípus alapértelmezett értékét, a többi beállítástól függően.

## <a name="type-specific-properties"></a>Típusspecifikus tulajdonságok

### <a name="application-dependent-user-input-parameter"></a>Alkalmazásfüggő felhasználói beviteli paraméter

Az Általános felhasználói **beviteli** \> **paramétertípus** adatforrásának használatával lehet beszerezni a Microsoft Dynamics 365-ös pénzügyi alkalmazás aktuális példányához megadott adattípus szükséges értékét vagy értékeit. Amikor ilyen típusú adatforrást ad hozzá egy ER összetevőhez, adja meg a következő tulajdonságokat:

- A Műveletek adattípusának **neve (EDT, enum)**[mezőben válasszon ki egy alkalmazás kiterjesztett adattípusát (EDT)](../extensibility/extensible-edts.md) vagy egy alkalmazás enumerálását.

> [!NOTE]
> **·** **·** **A Felhasználói BEVITELi PARAMÉTER típus szerkeszthető adatforrásában a Műveletek adattípusnév (EDT, enum)** *hivatkozásának* módosításakor ajánlott áttekinti a Csak olvasható és az Alapértelmezett érték mezőkben beállított kifejezéseket.

Az alábbi ábra az `$TaxRegNum`**Instat XML (DE)** ER formátumkonfigurációban beállított adatforrás tulajdonságait mutatja be. Az adatforrás úgy van beállítva *, hogy futásidőben a Leírás* EDT **használatával** kínálja fel a párbeszédpanel adóregisztrációs szám adatbeviteli mezőjét.

![A FELHASZNÁLÓI BEMENETI PARAMÉTER egy adatforrásának tulajdonságai típusúak a Formátumtervező lap párbeszédpanelje.](./media/er-user-input-parameter-data-sources-01.png)

A következő ábra azt **a párbeszédpanelt mutatja be, amely futásidőben jelenik meg, amikor az Intrastat nyilatkozat előállításához futtatja az Instat XML(DE)** ER-formátum [konfigurációját](../../../finance/localizations/tasks/eur-00002-eu-intrastat-declaration.md). Ne feledje, hogy **a konfigurált adószám** mező elérhető adatbevitelre.

![Az Intrastat lapon futó ER-formátum Intrastat-jelentés párbeszédpanelje.](./media/er-user-input-parameter-data-sources-02.png)

### <a name="data-model-enumeration-user-input-parameter"></a>Adatmodell-felsorolás  felhasználói bemeneti paramétere

Az adatmodell enumerációja **felhasználói** \>**·**[bemeneti paramétertípusának adatforrását használja egyetlen adatmodell-enumeráció kötelező értékének vagy értékeinek lekérdezéséhez.](er-formula-supported-data-types-primitive.md#enumeration) Amikor ilyen típusú adatforrást ad hozzá egy ER összetevőhez, adja meg a következő tulajdonságokat:

- A Modell **mezőben** adja meg az alapadatmodellre való hivatkozást.
- A Modell **enumerációs mezőben** adja meg a hivatkozott adatmodell felsorolására való hivatkozást.
- A Verzió **mezőben** válassza ki a hivatkozott modell enumerációt tartalmazó ER-adatmodell-összetevő verziószámát.

    > [!TIP]
    > A tervezés **ideje során üresen hagyhatja a Verzió** mezőt, hogy hozzáférjen a hivatkozott adatmodell-összetevő felsorolásához, amely a megfelelő ER adatmodell-konfiguráció vázlatverziójában található. Ily módon párhuzamosan szerkesztheti a modellleképezés vagy -formátum összetevő vázlatverzióját és az alap adatmodell-összetevő vázlatverzióját is.
    >
    > Ne feledje azonban, hogy **a Verzió** mező csak modellleképezés vagy formátumösszetevő vázlatverziója esetén hagyható üresen. Ha egy **ER** **modellleképezés** vagy formátumkonfiguráció állapotát Vázlat értékről Készre módosítja, ezt a mezőt automatikusan az aktuális Pénzügyi példányban elérhető legnagyobb modell-verziószám tölti ki. Ha új felsorolást vagy új felsorolási értéket mutat be az alapadatmodell vázlatverziójában, és hivatkozik rá a szerkeszthető modellleképezés vagy -formátum összetevőben, akkor az ER modellleképezés vagy formátumkonfiguráció vázlatverziója előtt töltse ki az alapadatmodell konfigurációjának vázlatverzióját. Ellenkező esetben a program az "Elérési út nem található" **·** **kivételt hoz létre, amikor a modellleképezés vagy a formátumkonfiguráció állapotát Vázlat értékről Készre módosítja.** Az üzenet arról tájékoztat, hogy a hivatkozott felsorolási vagy felsorolási érték hiányzik az alapadatmodellből.

Az alábbi ábra az `$ReportDirection`**Instat XML (DE) Contoso** ER formátumkonfigurációban beállított adatforrás tulajdonságait mutatja be. Az **Instat XML (DE) Contoso** konfiguráció [az](general-electronic-reporting.md#Configuration)**Instat XML (DE) konfigurációból lett származva.** Ez az adatforrás a *ReportDirection* modell enumeráció használatára van konfigurálva, hogy futásidőben felajánlja a párbeszédpanel megfelelő keresési mezőjét.

![A FELHASZNÁLÓI BEMENETI PARAMÉTER adatforrásának tulajdonságai típusúak a Formátumtervező lap párbeszédpanelje.](./media/er-user-input-parameter-data-sources-03.png)

### <a name="format-enumeration-user-input-parameter"></a>Formátumok felsorolásának felhasználói bemeneti paramétere

Egyetlen formátumba **sorolt enumeráció kötelező értékének vagy értékeinek lekérdezéséhez használja a Format enumeration Enumeration** \> **felhasználói** beviteli paramétertípus egyik adatforrását. Amikor ilyen típusú adatforrást ad hozzá egy ER összetevőhez, adja meg a következő tulajdonságokat:

- A Formátum **enumerációs mezőben** adja meg a szerkeszthető formátum felsorolását.

> [!NOTE]
> Az ilyen típusú adatforrások csak a szerkeszthető formátumösszetevő hatókörében konfigurálhatók.

## <a name="additional-resources"></a>További erőforrások

[Képletszerkesztő az Elektronikus jelentéskészítésben](general-electronic-reporting-formula-designer.md)

[A USER INPUT PARAMETER típusú adatforrásértékek kezdeményezése forráskódból](er-initiate-uip-data-source-value-from-source-code.md)
