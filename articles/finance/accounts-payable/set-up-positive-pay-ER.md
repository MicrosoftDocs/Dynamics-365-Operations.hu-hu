---
title: Fizetési pozitív fájlok beállítása és létrehozása az Elektronikus jelentés segítségével
description: Ez a témakör bemutatja, hogy hogyan lehet beállítani az elektronikus jelentéssel az pozitív fizetést.
author: panolte
ms.date: 03/20/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BankPositivePayFormat
audience: Application User
ms.reviewer: twheeloc
ms.custom: 88433
ms.assetid: 73f3dcf6-040a-44ad-9512-7b3e0d17a571
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: bc2f17d62b429b599d5ac5f2a521819275d36b64
ms.sourcegitcommit: 2b4ee1fe05792332904396b5f495d74f2a217250
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/18/2022
ms.locfileid: "8770247"
---
# <a name="set-up-positive-pay-files-by-using-electronic-reporting"></a>Fizetési fájlok beállítása elektronikus jelentéssel

Ez a témakör bemutatja, hogy hogyan lehet beállítani az elektronikus jelentés segítségével az pozitív fizetést és a fizetési fájlokat.

> [!NOTE] 
> A Banki fizetési **fájlok** létrehozása funkció használata előtt először frissítenie kell az entitáslistát.
> Kattintson az **Adatgazdálkodás > Importálás/exportálás > Keretrendszer-paraméterek** 
> **Entitásbeállítások** gyorslapra, és válassza az **Entitáslista frissítése** lehetőséget.


A fizetési ellenőrzés beállítása elektronikus csekklista generálásához, amely a banknak elküldhető. Amikor egy csekket bemutatnak a banknak, a bank összeveti a csekklistával. Ha a csekk megfelel a listában szereplő csekkel a bank törli azt. Ha a csekk nem egyezik meg a listában szereplő csekkel, akkor a bank bent tartja ellenőrzésre.

## <a name="security-for-positive-pay-files"></a>A fizetési ellenőrző fájlok biztonsága
Az ellenőrzött fizetési fájlok bizalmas információt tartalmazhatnak a kedvezményezettekről és a csekk-összegekről. Ezért győződjön meg róla, hogy a megfelelő biztonsági intézkedéseket használja attól az időponttól, hogy a fájlok létrejönnek addig, amíg a bank meg nem kapja őket. A fizetési ellenőrző fájlok a webböngészője által megadott helyre lesznek letöltve. Mivel a fizetési fizetési fájlok bizalmas adatokat tartalmazhatnak, ezért fontos, Microsoft Dynamics hogy csak erre jogosult felhasználóknak legyen hozzáférésük az adatok generálása és megtekintése a Pénzügy 365-ben. A következő táblázat segítségével határozza meg a szükséges jogosultságokkal.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Feladat</th>
<th>Jogosultság</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Fizetési ellenőrző fájlok létrehozása a <strong>Bankszámlák</strong> listaoldalon vagy a <strong>Bankszámlák</strong> lapon.</td>
<td><ul>
<li><strong>Banki ellenőrzött fizetési információk karbantartása</strong> (BankPositivePayProcess)</li>
<li><strong>BankPositivePayExportEntityView</strong> (BankPositivePayExportEntityView)</li>
</ul></td>
</tr>
<tr class="even">
<td>Ellenőrzött fizetési fájlok létrehozása több jogi személyhez és bankszámlához a <strong>Fizetési ellenőrző fájl létrehozása</strong> oldalon.</td>
<td><ul>
<li><strong>Banki ellenőrzött fizetési információk karbantartása</strong> (BankPositivePayProcess)</li>
<li><strong>BankPositivePayExportEntityView</strong> (BankPositivePayExportEntityView)</li>
</ul></td>
</tr>
<tr class="odd">
<td>Fizetési ellenőrző fájlok megtekintése a <strong>Fizetési ellenőrző fájl összegzése</strong> oldalon.</td>
<td><strong>Banki ellenőrzött fizetési információk megtekintése több jogi személynél</strong> (BankPositivePayView)</td>
</tr>
<tr class="even">
<td>Fizetési ellenőrző fájlok visszaigazolása a <strong>Fizetési ellenőrző fájl összegzése</strong> oldalon.</td>
<td><strong>Fizetési ellenőrző fájl visszaigazolása</strong> (BankPositivePayConfirm)</td>
</tr>
<tr class="odd">
<td>Fizetési ellenőrző fájlok visszahívása a <strong>Fizetési ellenőrző fájl összegzése</strong> oldalon.</td>
<td><strong>Fizetési ellenőrző fájl visszahívása</strong> (BankPositivePayRecall)</td>
</tr>
</tbody>
</table>

## <a name="set-up-the-electronic-reporting-configuration"></a>Az elektronikusjelentés-konfiguráció beállítása

1. Ugrás a Munkaterületek **elektronikus \> jelentéséhez**
2. A Microsoft **konfigurációs szolgáltató csempe** tárházát **jelölje ki**.
3. Válassza ki a **Globális**, majd a **Megnyitás** lehetőséget.
4. Ha kapcsolatot kell létesíteni a tárházzal, jelölje ki a kék kapcsolatot a párbeszédpanelen.
5. A konfigurációs listában keresse meg és válassza **a Pozitív fizetési modell \> fizetési formátumot**.
6. Válassza ki **a legújabb** verziót a Verziók gyorsgombra, majd válassza az Importálás **lehetőséget**.

## <a name="set-up-a-positive-pay-format"></a>Ellenőrzött fizetési formátum beállítása

1. Ugrás a Készpénz- **és bankkezelés beállítása \> pozitív \> fizetési formátumokhoz**.
2. Válassza az **Új** lehetőséget.
3. A Kifizetés formátuma **és** **Leírása mezők** beállítása.
4. Jelölje be az **Általános elektronikus exportálási formátum jelölőnégyzetet**.
5. Az Exportálás formátum **konfigurációs mezőjének** beállítása Pozitív **fizetési formátumra**.

## <a name="assign-a-positive-pay-format-to-a-bank-account"></a>Fizetési pozitív formátum hozzárendelése bankszámlához
Minden egyes bankszámlához, amelyhez szeretne létrehozni ellenőrzött fizetési információt, hozzá kell rendelnie az előző szakaszban megadott ellenőrzött fizetési formátumot. A Bankszámlák oldalon válassza ki azt az ellenőrzött fizetési formátumot, amely megfelel a bankszámlájának. Az **Ellenőrzött fizetés kezdő dátuma** mezőbe írja be az ellenőrzött fizetési fájlok létrehozásának kezdő dátumát. 

>[!Important]
> Adjon meg egy dátumot a Fizetés **pozitív kezdő dátuma mezőben**. Ha üresen hagyja a mezőt, akkor a generált első fizetési ellenőrző fájl tartalmazni fogja az ehhez a bankszámlához létrehozott összes csekket.

1. Ugrás a Készpénz- **és bankkezelés – \> Bankok bankszámlákhoz \>**.
2. Nyissa meg a bankszámlát.
3. Az Általános **gyorstára** a Korábban **létrehozott** formátumra állítsa a Pozitív fizetési formátum mezőt.
4. A Fizetés pozitív **kezdő dátum mezőjének** beállítása az aktuális dátumra.

## <a name="assign-a-number-sequence-for-positive-pay-files"></a>Számsorozat hozzárendelése az ellenőrzött fizetési fájlokhoz
Minden ellenőrzött fizetési fájlnak rendelkeznie kell egy egyedi számmal. A Készpénz- **és bankkezelés paraméterei** lapon hozzon létre egy számsorozatot a **Fizetési adatokat a Számsorozatok** lapon.

## <a name="generate-a-positive-pay-file-for-a-single-bank-account"></a>Ellenőrzött fizetési fájl létrehozása egyetlen bankszámlához
Létrehozhat egy ellenőrzött fizetési fájlt egyetlen jogi személyhez és egyetlen bankszámlához. További információért arról, hogy hogyan hozhat létre ellenőrzött fizetési fájlokat egyszerre több jogi személyhez és bankszámlához lásd a következő részt. Ellenőrzött fizetési fájl létrehozásához, egyetlen jogi személyhez és egyetlen bankszámlához, nyissa meg a **Fizetési ellenőrző fájl létrehozása** párbeszédablakot a **Bankszámlák** oldalon. A **Fordulónap dátuma** mezőben adja meg a fizetési ellenőrző fájlban használni kívánt utolsó csekk dátumát. Minden olyan csekk, amely nem került bele az ellenőrzött fizetési fájlba ezen csekkdátum végéig bekerül a fájlba.

1. Váltson a Készpénz **- és bankkezelés bankszámláihoz \>\>**.
2. Annak a bankszámlának a megnyitása, amely számára a fizetési pozitív beállítás van beállítva.
3. Válassza a **Fizetések kezelése \> fizetési pozitív \> fizetési fájlt**.
4. Állítsa be **a Határidő mező** beállítását. A program az e dátum előtt létrehozott csekkeket is tartalmazza.

## <a name="generate-a-positive-pay-file-for-multiple-bank-accounts"></a>Ellenőrzött fizetési fájl létrehozása több bankszámlához
Több bankszámlához is létre kell hozni fizetési pozitív fájlt, használja **a Fizetési ellenőrzés fájlja** ismétlődő feladatot. Válassza ki az ellenőrzött fizetés fájlformátumát és adja meg, hogy minden jogi személyhez létrejöjjön-e a fájl, vagy csak egy kijelölt jogi személyhez. Létrehozhatja továbbá a fájlt minden bankszámlához, amely az adott ellenőrzött fizetési formátumot használja, vagy egy kijelölt bankszámlához. A **Fordulónap dátuma** mezőben adja meg a fizetési ellenőrző fájlban használni kívánt utolsó csekk dátumát. Minden olyan csekk, amely nem került bele az ellenőrzött fizetési fájlba ezen csekkdátum végéig bekerül a fájlba.

## <a name="view-the-results-of-positive-pay-file-generation"></a>Az ellenőrzött fizetési fájl létrehozásának eredményeinek megtekintése
Miután a fizetési ellenőrző fájl létrejött, megtekintheti az eredmények a **Fizetési ellenőrző fájl összegzése** lapon. Az egyes csekkek részleteinek megtekintéséhez kattintson **a Fizetési ellenőrző fájl részletei lapra**.

## <a name="confirm-a-positive-pay-file"></a>A fizetési ellenőrző fájl visszaigazolása
Miután kifizetésre kerültek a fizetési ellenőrző fájlban felsorolt csekkek, a bank visszaigazolási számot küld róla. Ezt követően visszaigazolhatja a fizetési ellenőrző fájlt. A **Fizetési ellenőrző fájl összegzése** lapon, válasszon ki egy ellenőrzött fizetést, amelynek állapota **Létrehozva**, majd válassza ki a **Visszaigazolás beírása** művelet. Amikor visszaigazol egy ellenőrzött fizetési fájlt, akkor a banktól kapott visszaigazolási szám rögzítésre kerül.

## <a name="recall-a-positive-pay-file"></a>Fizetési ellenőrző fájl visszahívása
Ha módosítania kell valamit a fizetési ellenőrző fájlban, akkor vissza tudja hívni. A **Fizetési ellenőrző fájl összegzése** lapon, válasszon ki egy ellenőrzött fizetést, amelynek állapota **Létrehozva**, majd válassza ki a **Visszahívás** művelet. Minden csekkhez a mező, amely a fizetési ellenőrző fájlban azt jelöli, hogy a csekk szerepel-e egy fizetési ellenőrző fájlban visszaállításra kerül. Ezt követően létrehozhat egy új ellenőrzött fizetési fájlt, amely tartalmazza a visszavont csekket.


A kapott XML-fájl letölti.
