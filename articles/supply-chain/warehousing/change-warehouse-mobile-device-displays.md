---
title: "Raktári mobileszköz megjelenítési beállításai"
description: "Ez a cikk azt mutatja be, hogy hogyan állíthatja be egy mobileszköz kijelzőjének megjelenését és hogyan adhatja hozzá a vezérlőkhöz a billentyűparancsokat, mint például gombokat."
author: perlynne
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SysUserSetup, WHSRFColor, WHSRFColorPicker, WHSWorkUserDisplaySettings
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 29071
ms.assetid: 931a02e8-b561-45e3-9c44-06b875ced1b4
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 799cd4a940813e39f8be6b4c127b9efabc88e909
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="warehouse-mobile-device-display-settings"></a>Raktári mobileszköz megjelenítési beállításai

[!include[banner](../includes/banner.md)]


Ez a cikk azt mutatja be, hogy hogyan állíthatja be egy mobileszköz kijelzőjének megjelenését és hogyan adhatja hozzá a vezérlőkhöz a billentyűparancsokat, mint például gombokat. 

Ez a cikk a „haladó raktározás” funkciókra vonatkozik a Raktárkezelési szolgáltatásokban. A mobileszközök több feladatra is használhatók, amelyeket a raktári dolgozók végeznek el.

## <a name="specify-styles-and-map-keyboard-shortcuts"></a>Stílusok megadása és billentyűparancsok hozzáadása
A mobileszköz-konfiguráció részeként be lehet állítani a mobileszközök különböző elrendezéseit. Ehhez ismernie kell az egymásba ágyazott stíluslapokat (CSS) és az aktív szerver oldali kiterjesztett fájlokat (ASPX). A raktári mobileszközportál telepítés részeként települnek az alapértelmezett fájlok. Ha nem ismeri a fájlneveket, kérdezze meg a rendszergazdát. Új stílust a **Mobileszköz megjelenítési beállítások** oldalon lehet megadni:

-    A **CSS fájl** mezőben adja meg a CSS fájl nevét. Tegye hozzá a .css kiterjesztést.
-   A **Mobileszköz megjelenítési beállítások nézet** mezőben adja meg az ASPX fájlt. **Ne** tegye hozzá az .aspx kiterjesztést.

A CSS és az ASPX fájloknak egy bizonyos útvonalon kell szerepelniük, hogy az Internet Information Services (IIS) betölthesse ezeket. Hasznos lehet a különböző CSS-fájlok meghatározásakor, ha a mobileszköz funkciót különböző böngészőkben futtatja vagy különböző hardveren, amely különböző elrendezés vezérlést igényel. Egyszerű beállítások, például a háttérszín, a betűtípus, a szöveg betűtípusa és betűmérete, és a gombok szélessége és működése könnyen vezérelhető a különféle CSS-fájlokkal. Az ASPX fájl a mobil webhely megjelenítésére használható a kiszolgálóoldali ASP.NET alkalmazásban. A fájl szabályozza a HTML átfogó szerkezetének elrendezését. Csak akkor tanácsos testreszabni ezt a funkciót, ha súlyos strukturális problémák találhatók a HTML-ben és a JavaScriptben, és módosítani kell az adott eszközökhöz a kódot. A HTML vezérlők gyorsbillentyűkhöz való hozzárendelése mobil eszközökön a **Mobileszköz megjelenítési beállítások** oldalon a **Billentyűparancs** mezőben lehetséges, a numerikus kódok kulcsokhoz való hozzárendelésével. Használhatja a **Billentyűparancsok kódjának megtekintése** menüt a mobileszközökön a numerikus karakterkódok megkeresésére. Vegye figyelembe, hogy a hozzárendelések eltérők lehetnek a használatban lévő hardvertől függően. Az összerendeléshez az alábbi szintaxist használja:

&lt;vezérlőelem neve&gt;(&lt;billentyű neve&gt;)=&lt;billentyű kódja&gt;;

Az alábbiakban a szintaxis részeinek magyarázatát találja:

-   **&lt;<a vezérlőelem neve&gt;** – Az adott vezérlőelem, például egy HTML-ben megjelenő gomb neve.
-   **(&lt;billentyű neve&gt;)** – A billentyűzet azon billentyűjének neve, amelyhez gyorsbillentyűt szeretne létrehozni.
-   **&lt;Billentyű kódja&gt;** – Azon billentyű numerikus karakterkódja, amelyet gyorsbillentyűként kíván használni.

Egy példa:

Mégse(Esc)=27; Teljes(F2)=113

Minden oldalon, amely **Mégse** gombot tartalmaz, ez a szöveg jelenik meg a gombon:

**(Esc) Mégse**

Ha megnyomja a billentyűzeten az Esc billentyűt, azzal a **Mégse** gombot aktiválja. Ha szeretné alkalmazni egy adott eszközön a stílust és a gyorsbillentyű-beállításokat, létre kell hoznia egy hozzárendelést a **Feltételek** mezőben. Egy .NET reguláris kifejezést kell használnia a hozzárendelés létrehozásához, és a kifejezésnek három részből kell állnia, amelyek egy függőleges vonallal (|) vannak elválasztva, ahogy itt látható:

Request.UserHostAddress=&lt;felhasználó állomásának címe&gt;|HostName=&lt;felhasználó állomásának neve&gt;|Request.UserAgent=&lt;felhasználói ügynök&gt;

Az alábbiakban a kifejezés részeinek magyarázatát találja:

-   **&lt;felhasználó állomásának címe&gt;** – A kérelmező IP-címének megfelelő .NET reguláris kifejezés.
-   **&lt;felhasználó állomásának neve&gt;** – A kérelmező hálózatnevének megfelelő .NET reguláris kifejezés.
-   **&lt;felhasználói ügynök&gt;** – A kérelmező által használt böngésző azonosítójának megfelelő .NET reguláris kifejezés.

A következő példa lehetővé teszi Internet Explorer 8 használatát is:

Request.UserHostAddress=.\*|HostName=.\*|Request.UserAgent=MSIE\\s8\\.0

Használhatja **A kiszolgálói konfiguráció megjelenítési beállításainak megtekintése** menüt a mobileszközön a beállítással kapcsolatos információk megtekintéséhez.

## <a name="define-text-colors-for-messages"></a>Szövegszín meghatározása üzenetekben
A **Mobileszköz szövegszínei** oldalt használhatja a rendszer által létrehozott üzenetek különböző szövegszíneinek beállításához, például a hibaüzenetekhez. Például a szöveg színe jelezheti az üzenet célját vagy fontosságát. A következő üzenetek jelennek meg.

| Üzenet típusa | Leírás                                                                                                                                                                            |
|--------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Alapértelmezett      | Az alapértelmezett üzenetek az alapértelmezett színbeállításokat használják minden üzenethez, amelyet a raktári mobileszközportál CSS-fájljában meghatároztunk.                                                   |
| Hiba        | A hibaüzenetek olyan hibát jeleznek, amelyeket a felhasználónak meg kell oldania, mielőtt továbblép.                                                                                             |
| Sikeres      | A sikeres üzenetek megerősítik egy művelet sikerességét.                                                                                                                                |
| Figyelmeztetés      | A figyelmeztető üzenetek tájékoztatják a dolgozót, hogy hiba történt, vagy hiba fog történni, ha a dolgozó folytatja a műveletet. A dolgozónak azonban nem kell megoldania a hibát a továbblépéshez. |

Szín kiválasztásához kattintson a **Szín kiválasztása** oldalon a palettára, vagy írjon be egy hexadecimális színkódot.

## <a name="define-the-date-format-to-use-on-mobile-devices"></a>A mobileszköz dátumformátumának megadása
Minden telepítésnél kibővítheti az elfogadott dátumformátumok listáját. Ez például akkor lehet hasznos, ha olyan formátumot szeretne használni, amellyel a dolgozónak könnyebb megadnia a dátumot a mobileszközön. Az alapértelmezett formátumot a felhasználó alapértelmezett nyelve határozza meg, amely a **Nyelv** mezőben a **Felhasználói beállítások** oldalon található. (Ugyanezen az oldalon lehet egy adott raktár munkafelhasználóját egy alkalmazotthoz társítani.) **Megjegyzés**: a raktári mobileszközportál nem használja a **Dátum-, idő- és számformátum** mező beállítását a **Nyelvi és területi beállítások** oldalon. Ha módosítani szeretné a kívánt dátumformátumot, ismernie kell a .NET-keretrendszer reguláris kifejezéseit. További tudnivalókért lásd: [A .Net keretrendszer reguláris kifejezései](http://go.microsoft.com/fwlink/?LinkId=391260). Dátumformátumok definiálásához szerkessze azt a Dates.ini fájlt, amely a Content\\\Settings\\\Dates.ini helyen található a raktári mobileszközportál szerverén. Ez a fájl .NET reguláris kifejezések alapján határozza meg a dátumformátumot. A reguláris kifejezésnek tartalmaznia kell a nap, hónap és év (DDMMYY) megjelölésére létrehozott, névvel ellátott csoportokat jelölő alkifejezéseket is, ahogyan azt a következő példa szemlélteti:

^(?&lt;nap&gt;\\d{2})(?&lt;hónap&gt;\\d{2})(?&lt;év&gt;\\d{2})$

Minden részkifejezéshez kötelező megadni a nap és a hónap egy vagy két számjegyét, illetve az évhez 1-4 számjegyet. Az alábbi példa olyan alkifejezést mutat be, amely meghatározza az év névvel ellátott csoportját, és legalább kettő, maximum négy számjegyet igényel:

(?&lt;év&gt;\\d{2,4})

Egynél több kifejezést is megadhat egy fájlban. Minden kifejezésnek külön sorban kell lennie. A dátum elemzésére az első megfelelő kifejezést használja a rendszer.

<a name="see-also"></a>Lásd még
--------

[Mobileszközök konfigurálása raktári munkához](configure-mobile-devices-warehouse.md)




