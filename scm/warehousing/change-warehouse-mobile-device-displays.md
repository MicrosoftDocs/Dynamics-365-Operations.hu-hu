---
title: "Raktári mobileszköz megjelenítési beállításai"
description: "Ez a cikk azt mutatja be, hogy hogyan állíthatja be egy mobileszköz kijelzőjének megjelenését és hogyan adhatja hozzá a vezérlőkhöz a billentyűparancsokat, mint például gombokat."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: SysUserSetup, WHSRFColor, WHSRFColorPicker, WHSWorkUserDisplaySettings
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 29071
ms.assetid: 931a02e8-b561-45e3-9c44-06b875ced1b4
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: afa59439e06aad9d669eb352a9837a013f447249
ms.openlocfilehash: 721b293d1f8c76458ca510732f9bb94f003ac6e3
ms.lasthandoff: 03/31/2017


---

# <a name="warehouse-mobile-device-display-settings"></a>Raktári mobileszköz megjelenítési beállításai

Ez a cikk azt mutatja be, hogy hogyan állíthatja be egy mobileszköz kijelzőjének megjelenését és hogyan adhatja hozzá a vezérlőkhöz a billentyűparancsokat, mint például gombokat. 

Ez a cikk a „haladó raktározás” funkciókra vonatkozik a Raktárkezelési szolgáltatásokban. A mobileszközök több feladatra is használhatók, amelyeket a raktári dolgozók végeznek el.

## <a name="specify-styles-and-map-keyboard-shortcuts"></a>Stílusok megadása és billentyűparancsok hozzáadása
A mobileszköz-konfiguráció részeként be lehet állítani a mobileszközök különböző elrendezéseit. Ehhez ismernie kell az egymásba ágyazott stíluslapokat (CSS) és az aktív szerver oldali kiterjesztett fájlokat (ASPX). A raktári mobileszközportál telepítés részeként települnek az alapértelmezett fájlok. Ha nem ismeri a fájlneveket, kérdezze meg a rendszergazdát. Új stílust a **Mobileszköz megjelenítési beállítások** oldalon lehet megadni:

-    A **CSS fájl** mezőben adja meg a CSS fájl nevét. Tegye hozzá a .css kiterjesztést.
-   A **Mobileszköz megjelenítési beállítások nézet** mezőben adja meg az ASPX fájlt. **Ne** tegye hozzá az .aspx kiterjesztést.

A CSS és az ASPX fájloknak egy bizonyos útvonalon kell szerepelniük, hogy az Internet Information Services (IIS) betölthesse ezeket. Hasznos lehet a különböző CSS-fájlok meghatározásakor, ha a mobileszköz funkciót különböző böngészőkben futtatja vagy különböző hardveren, amely különböző elrendezés vezérlést igényel. Egyszerű beállítások, például a háttérszín, a betűtípus, a szöveg betűtípusa és betűmérete, és a gombok szélessége és működése könnyen vezérelhető a különféle CSS-fájlokkal. Az ASPX fájl a mobil webhely megjelenítésére használható a kiszolgálóoldali ASP.NET alkalmazásban. A fájl szabályozza a HTML átfogó szerkezetének elrendezését. Csak akkor tanácsos testreszabni ezt a funkciót, ha súlyos strukturális problémák találhatók a HTML-ben és a JavaScriptben, és módosítani kell az adott eszközökhöz a kódot. A HTML vezérlők gyorsbillentyűkhöz való hozzárendelése mobil eszközökön a **Mobileszköz megjelenítési beállítások** oldalon a **Billentyűparancs** mezőben lehetséges, a numerikus kódok kulcsokhoz való hozzárendelésével. Használhatja a **Billentyűparancsok kódjának megtekintése** menüt a mobileszközökön a numerikus karakterkódok megkeresésére. Vegye figyelembe, hogy a hozzárendelések eltérők lehetnek a használatban lévő hardvertől függően. Az összerendeléshez az alábbi szintaxist használja:

&lt;vezérlőelem neve&gt;(&lt;kulcs neve&gt;) =&lt;kulcs kód&gt;;

Az alábbiakban a szintaxis részeinek magyarázatát találja:

-   **&lt;vezérlőelem neve&gt;** – a neve a vezérlőelem (például egy gomb) HTML-formátumban jelenik meg.
-   **(&lt;kulcs neve&gt;) ** –, Amely a parancsikont hoz létre a billentyű nevét.
-   **&lt;Kulcs kód&gt;** – a billentyű billentyűparancsot használja a numerikus karakter kódját.

Egy példa:

Mégse(Esc)=27; Teljes(F2)=113

Minden oldalon, amely **Mégse** gombot tartalmaz, ez a szöveg jelenik meg a gombon:

**(Esc) Mégse**

Ha megnyomja a billentyűzeten az Esc billentyűt, azzal a **Mégse** gombot aktiválja. Ha szeretné alkalmazni egy adott eszközön a stílust és a gyorsbillentyű-beállításokat, létre kell hoznia egy hozzárendelést a **Feltételek** mezőben. Egy .NET reguláris kifejezést kell használnia a hozzárendelés létrehozásához, és a kifejezésnek három részből kell állnia, amelyek egy függőleges vonallal (|) vannak elválasztva, ahogy itt látható:

Request.UserHostAddress=&lt;felhasználói állomás címe&gt;|} HostName =&lt;felhasználói állomás neve&gt;|} Request.UserAgent=&lt;felhasználói ügynök&gt;

Az alábbiakban a kifejezés részeinek magyarázatát találja:

-   **&lt;felhasználói állomás címe&gt;** – A .NET reguláris kifejezés, amely megfelel a kérelmező IP-címét.
-   **&lt;felhasználói állomás neve&gt;** – A .NET reguláris kifejezés, amely a kérelmező hálózati neve megegyezik.
-   **&lt;felhasználói ügynök&gt;** – A .NET reguláris kifejezés, amely megfelel az a böngésző, amely a kérelmező által használt azonosító.

A következő példa lehetővé teszi Internet Explorer 8 használatát is:

Request.UserHostAddress=. \*| HostName =. \*| Request.UserAgent=MSIE\\s8\\.0

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
Minden telepítésnél kibővítheti az elfogadott dátumformátumok listáját. Ez például akkor lehet hasznos, ha olyan formátumot szeretne használni, amellyel a dolgozónak könnyebb megadnia a dátumot a mobileszközön. Az alapértelmezett formátumot a felhasználó alapértelmezett nyelve határozza meg, amely a **Nyelv** mezőben a **Felhasználói beállítások** oldalon található. (Ugyanarra az oldalra is szolgál alkalmazott társítása egy adott raktári munka felhasználó.) **Megjegyzés:** a raktári mobil eszközök Portal beállítása nem használja a **dátum, idő és szám formátum** mezőjében a **nyelvi és területi beállítások** lap. Ha módosítani szeretné a kívánt dátumformátumot, ismernie kell a .NET-keretrendszer reguláris kifejezéseit. További tudnivalókért lásd: [A .Net keretrendszer reguláris kifejezései](http://go.microsoft.com/fwlink/?LinkId=391260). Dátum-és időformátumok definiálásához szerkesztése a tartalom található Dates.ini fájl\\beállítások\\Dates.ini a raktári mobil eszközök Portal kiszolgálón. Ez a fájl .NET reguláris kifejezések alapján határozza meg a dátumformátumot. A reguláris kifejezésnek tartalmaznia kell a nap, hónap és év (DDMMYY) megjelölésére létrehozott, névvel ellátott csoportokat jelölő alkifejezéseket is, ahogyan azt a következő példa szemlélteti:

^(? &lt;day&gt;\\d{2})(?&lt; month&gt;\\d{2})(?&lt; év&gt;\\d {2}) $

Minden részkifejezéshez kötelező megadni a nap és a hónap egy vagy két számjegyét, illetve az évhez 1-4 számjegyet. Az alábbi példa olyan alkifejezést mutat be, amely meghatározza az év névvel ellátott csoportját, és legalább kettő, maximum négy számjegyet igényel:

(? &lt;year&gt;\\d{2,4})

Egynél több kifejezést is megadhat egy fájlban. Minden kifejezésnek külön sorban kell lennie. A dátum elemzésére az első megfelelő kifejezést használja a rendszer.

<a name="see-also"></a>Lásd még
--------

[Configuration of mobile devices for warehouse work](configure-mobile-devices-warehouse.md)


