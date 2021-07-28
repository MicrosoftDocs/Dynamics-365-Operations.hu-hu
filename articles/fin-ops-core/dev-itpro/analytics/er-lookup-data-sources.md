---
title: Konfigurálja a Keresési adatforrásokat az ER-alkalmazásspecifikus paraméterek használatára
description: Ez a témakör azt mutatja be, hogyan lehet konfigurálni a Keresési adatforrásokat az Elektronikus jelentéskészítési (ER) formátumokban az ER alkalmazásspecifikus paraméterek használatához.
author: NickSelin
ms.date: 04/02/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, EROperationDesigner, ERLookupDesigner, ERComponentLookupStructureEditing
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-01-01
ms.dyn365.ops.version: Release 8.1.3
ms.openlocfilehash: 682910350832e441ed13c716c0c18200a3b7865d
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/06/2021
ms.locfileid: "6351073"
---
# <a name="configure-lookup-data-sources-to-use-er-application-specific-parameters"></a>Konfigurálja a Keresési adatforrásokat az ER-alkalmazásspecifikus paraméterek használatára 

[!include[banner](../includes/banner.md)]

Az [Elektronikus jelentéskészítési (ER)](general-electronic-reporting.md) alkalmazásspecifikus paraméterek funkcióval konfigurálhatja az adatszűrést egy ER formátumban, hogy az absztrakt szabályok egy csoportján alapuljon. Ezek a szabályok beállíthatók úgy, hogy az ER formátumban elérhető, **Keresési** típusú adatforrásokat használják. Ezután az ER-komponenstervezőkön túl valódi szabályokat is megadhat a felhasználói felület (UI) segítségével, amely a megfelelő ER formátum és az aktuális jogi személy adatainak **Keresési** adatforrásának beállításain alapulva automatikusan létrejön. A megadott szabályokat végül az ER-formátum **Keresési** adatforrása érheti el az ER-formátum végrehajtásakor.

> [!NOTE]
> A szerkeszthető ER-formátum konfigurált adatforrásával adhatja meg, hogy mely alkalmazásadatok használatosak a valós szabályok konfigurálása során.

Az [ER-műveletek tervezője](general-electronic-reporting.md#building-a-format-that-uses-a-data-model-as-a-base) segítségével hozzon az ER-formátumba egy **Keresési** típusú adatforrást. Az adatforrást úgy kell konfigurálni, hogy leírja, hogyan néznek ki az absztrakt szabályok, többek között a következők:

   - Egy bizonyos adattípus paraméterkészlete, amelynek értéke meg van adva egyetlen szabály megadásához.
   - Bizonyos adattípusnak az az értéktípusa, amelyet egyetlen szabály ad vissza, ha a szabályt a rendszer a legmegfelelőbbnek tartja a többi közül.

Attól függően, hogy milyen típusú értékeket adott vissza egy konfigurált szabály, a következő típusú **Keresési** adatforrásokat lehet konfigurálni:

   - Használja az **Adatmodell\Keresési** típust olyankor, amikor vissza kell adni a modell enumerációs értékét.
   - Használja a **Dynamics 365 Operations\Keresési** típust, ha alkalmazás enumerációs értéket vagy egy alkalmazás [kiterjesztett adattípusának](../extensibility/extensible-edts.md) értékét kell visszaadni.
   - Használja a **Formátumok felsorolása\Keresési** típust olyankor, amikor vissza kell adni a modell enumerációs értékét.

Az alábbi ábra azt mutatja be, hogyan lehet konfigurálni egy formátumfelsorolást a minta ER-formátumban.

   ![Formátumfelsorolás megjelenítése a konfigurált keresési adatforrás alapjaként.](./media/er-lookup-data-sources-img1.gif)

Az alábbi ábra azokat a formátumösszetevőket mutatja be, amelyeket azért konfiguráltak, hogy a különböző adótípusokat a létrehozott jelentés különböző szakaszaiban jelentsék le.

   ![A formátumszakaszok megjelenítése a különböző adótípusú adók elkülönített jelentéséhez.](./media/er-lookup-data-sources-img2.png)

Az alábbi ábra azt mutatja be, hogyan teszi lehetővé az ER művelettervező a **Formátumok felsorolása\Keresési** típus adatforrások hozzáadását.  A hozzáadott adatforrás úgy van konfigurálva, hogy visszaadja a `List of taxation levels` formátumfelsorolás értékét.

   ![Egy Formátumok felsorolása\Keresési típus ER-adatforrás hozzáadása.](./media/er-lookup-data-sources-img3.gif)

A következő ábra bemutatja, hogy a hozzáadott adatforrás hogyan van beállítva arra, hogy a **Modell** adatforrás **Model.Data.Tax** rekordlista **Kód** mezőjét olyan paraméterként használja, amelyet minden konfigurált szabályhoz meg kell adni.

![A Formátumok felsorolása\Keresési típusú hozzáadott adatforrás paramétereinek konfigurálása.](./media/er-lookup-data-sources-img4.gif)

A hozzáadott `Model.Data.Tax` adatforrás úgy van beállítva, hogy megadjon egy adókódot minden konfigurált szabályhoz a **TaxTable** alkalmazástábla rekordjainak elérésével.

   ![A Formátumok felsorolása\Keresési típusú egy vállalatos keresési adatforrás áttekintése.](./media/er-lookup-data-sources-img5.gif)

A kiválasztott ER-formátum keresési szabályait a konfigurált adatforrás szerkezetéhez automatikusan igazodó felhasználói felület használatával lehet beállítani. Ez a felhasználói felület jelenleg megköveteli, hogy minden szabálynál meg kell adni a visszaadott értéket `List of taxation levels` formátum felsorolási értékeként, valamint az adókódot paraméterként.

   ![Szabályok beállítása a konfigurált adatforráshoz.](./media/er-lookup-data-sources-img6.gif)

A következő ábra bemutatja, hogyan lehet beállítani a **Számított mezőtípus** `Model.Data.Summary.LevelByLookup` adatforrását úgy, hogy a szükséges paraméterekkel meg tudja hívni a konfigurált **Keresési** adatforrást. A hívás futásidőben való feldolgozásához az ER végigfut a megadott sorrendben beállított szabályok listáján, és megkeresi az első szabályt, amely kielégíti a megadott feltételeket. Ebben a példában ez a szabály tartalmazza a megadottnak megfelelő adókódot. Ennek eredményeképpen a rendszer a legmegfelelőbb szabályt találta, és a szabályhoz beállított felsorolási értéket visszaadja ez az adatforrás.

> [!NOTE]
> Kivétel akkor áll elő, ha nem található alkalmazható szabály. A kivételek megakadályozásához konfigurálja a szabályok listájának végén található további szabályokat, hogy kezelni tudja az eseteket, ha nem konfigurált értéket van megadva, vagy nincs megadott érték. Ennek megfelelően használja a **\*Nem üres\*** és az **\*Üres\*** lehetőséget.  
>
> ![Adatforrás hozzáadása a konfigurált Keresési adatforrás meghívására.](./media/er-lookup-data-sources-img7.png)

Ha a **Vállalatközi beállítást** **Igen** beállításra adja a szerkeszthető keresési adatforráshoz, egy új szükséges **Vállalat** paramétert ad hozzá az adatforrás paramétereinek halmazához. A keresési adatforrás hívása esetén futásidőben meg kell adni a **Vállalat** paraméter értékét. Ha futásidőben meg van adva a vállalati kód, az ehhez a vállalathoz beállított szabályok segítségével lehet megtalálni a legmegfelelőbb szabályt, és a rendszer a megfelelő értéket adja vissza. Az alábbi ábra bemutatja, hogyan lehet ezt megtenni, és hogyan módosulnak a szerkeszthető adatforrás paraméterei.

   ![A Formátumok felsorolása\Keresési típusú vállalatközi keresési adatforrás áttekintése.](./media/er-lookup-data-sources-img8.gif)

> [!NOTE]
> Válasszon ki minden vállalatot külön-külön a szerkeszthető ER-formátum keresési adatforrására vonatkozó szabályok beállításához. Futásidőben kivétel lép fel, amikor a vállalatközi keresés meg van hívva annak a vállalatnak a kódjával, amelynek keresési beállítása még nem fejeződött be.
>
> Győződjön meg róla, hogy megadja az engedélyeket egy olyan felhasználónak, aki az ER-formátumot a vállalatközi **Keresési** adatforrással futtatja, hogy hozzáférjen az adatforráshoz tartozó összes vállalat adataihoz. Ellenkező esetben a rendszer futásidejű kivételt ad.

A 10.0.19-es verziótól kezdve elérhetők a **Keresési** adatforrások kiterjesztett funkciói. Ha a szerkeszthető keresési adatforrásra a **Kiterjesztett** lehetőséget **Igen** beállításra állítja, a konfigurált keresési adatforrás átvált arra a strukturált adatforrásra, amely további lehetőségeket kínál a konfigurált szabálykészlet elemzésére. A következő ábrán ez az átalakítás látható.

   ![A Formátumok felsorolása\Keresési típusú strukturált keresési adatforrás áttekintése.](./media/er-lookup-data-sources-img9.gif)

- A **Keresési** részelem függvényként van kialakítva, amely a konfigurálható szabályok készletéből a megadott paraméterek alapján a legmegfelelőbb szabályt keresi meg.
- Az **IsLookupResultSet** alelem úgy van kialakítva, hogy elfogadja az alap felsorolási adatforrás megadott értékét, és **Igaz** *logikai értéket* adjon vissza, ha a szabályok halmaza legalább egy olyan szabályt tartalmaz, amelyhez a megadott felsorolási érték be lett állítva visszatérési értékként. Ez a függvény a **Hamis** *logikai értéket* adja eredményül, ha nincsenek olyan konfigurált szabályok, amelyek a megadott felsorolási értéket adják vissza.
- A **Beállítás** részelem olyan funkcióként van kialakítva, amely rekordlista rekordjaiként visszaadja a konfigurált szabályok halmazát. A visszaadott értékek és a konfigurált szabálykészletek paraméterei megjelennek minden visszaadott rekordban a megfelelő adattípusok mezőiként:

    - A visszaadott érték a **Keresési eredmény** mezőjeként van megjelenítve.
    - A konfigurált paraméterek paraméternevekkel rendelkező mezőkként jelennek meg ( ebben a példában a **Kód** mező).

A **Keresési** adatforrás konfigurálásáról további tudnivalókat lásd: [ER-formátumok konfigurálása a jogi személyenként meghatározott paraméterek használatára](er-app-specific-parameters-configure-format.md). A keresési szabályok beállításának további tudnivalóit lásd: [Az ER-formátum paramétereinek beállítása jogi személyenként](er-app-specific-parameters-set-up.md).

## <a name="additional-resources"></a>További erőforrások

[ER-formátumok konfigurálása a jogi személyenként meghatározott paraméterek használatára](er-app-specific-parameters-configure-format.md)

[Az ER-formátum paramétereinek beállítása jogi személyenként](er-app-specific-parameters-set-up.md)
