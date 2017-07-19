---
title: "Vevői számla létrehozása"
description: 
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 77772
ms.assetid: 00b4b40c-1576-4098-9aed-ac376fdeb8c5
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: 2016-02-28T00:00:00.000Z
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: fd89921a97782c4d09807a730ab077809304159f
ms.contentlocale: hu-hu
ms.lasthandoff: 05/25/2017

---

# <a name="create-a-customer-invoice"></a>Vevői számla létrehozása

[!include[banner](../includes/banner.md)]




Egy **értékesítési rendeléshez kiállított vevői számla** az értékesítéshez kapcsolódó váltó, amelyet a szervezet egy vevőnek ad. Ezen típusú értékesítési számla kiállítása egy értékesítési rendelés alapján történik, amely tartalmazza a rendeléssorokat és cikkszámokat. A cikkszámok a főkönyvben vannak meghatározva és feladva. Analitikus naplóbejegyzések nem érhetők el értékesítési rendeléshez tartozó vevői számlához. 

A **szabadszöveges számla** nincs kapcsolatban értékesítési rendeléssel. Olyan rendelési sorokat tartalmaz, amelyek személyesen megadott főkönyvi számlákat, szabadszöveges leírásokat és értékesítési mennyiséget foglalnak magukban. Ezen a számlafajtán nem tud cikkszámot megadni. A megfelelő áfaadatokat kell megadnia. Az értékesítéshez tartozó fő számla fel van tüntetve mindegyik számlasornál, amelyet szét lehet osztani több főkönyvi számla között az **Összegek felosztása** lehetőségre kattintva a **Szabadszöveges számla** lapon. Ezen kívül a vevői egyenleg is feladásra kerül az összegző számlához a szabadszöveges számla esetében használt feladási profilból.

A **pro forma számla** olyan számla, amely a tényleges számla mennyiségeinek becsléseként készül el a számla feladása előtt. Pro forma számlát értékesítési rendeléshez kiadott vevői és szabadszöveges számlához is ki lehet nyomtatni.

## <a name="post-and-print-individual-customer-invoices-that-are-based-on-sales-orders"></a>Vevői számla feladása és nyomtatása az értékesítési rendelések alapján
Ezzel az eljárással olyan számlát hozhat létre, amely értékesítési rendelésen alapul. Erre akkor lehet szükség, ha az áruk vagy a szolgáltatások szállítása előtt kíván számlázni az ügyfélnek. 

A számla feladásakor a **Számlahátralék** mező mennyisége minden cikkre vonatkozóan frissül a választott értékesítési rendelésen szereplő számlázott mennyiségek összegével. Ha az értékesítési rendelésen található összes cikknél 0 (nulla) a **Számlahátralék** és a **Fennmaradó szállítása** értéke, az értékesítési rendelés **Számlázott** állapotú lesz. Ha a számlához tartozó **Számlahátralék** mennyisége nem 0 (nulla), akkor az értékesítési rendelés állapota változatlan marad, és további számlákat lehet hozzá rögzíteni.

Az **Összes értékesítési rendelés** listaoldalon tekintheti meg az értékesítési rendelések állapotát. Használja a **Vevői számlák megnyitása** listaoldalt a feladott számlák megtekintéséhez.

## <a name="post-and-print-individual-customer-invoices-that-are-based-on-packing-slips-and-the-date"></a>Vevői számla feladása és nyomtatása a szállítólevelek és a dátum alapján
Ezt a műveletet akkor alkalmazza, ha az értékesítési rendeléshez már legalább egy szállítólevél fel van adva. A vevői számla ezeken a szállítóleveleken alapul, és azok mennyiségeit tükrözi. A számla pénzügyi adatai a számla feladásakor megadott információkon alapulnak. 

A csomagjegyzék eddig kiszállított cikksorai alapján lehet vevői számlát készíteni még abban az esetben is, ha egy adott értékesítési rendelés összes cikke még nincs kiszállítva. Akkor lehet például ezt tenni, ha a jogi személy minden hónapban ad ki számlát a vevő számára, amely az adott havi összes szállítást tartalmazza. Mindegyik csomagjegyzék az értékesítési rendelésen található cikkek részleges vagy teljes kiszállítását képviseli. 

A számla feladásakor az egyes cikkekhez tartozó **Számlahátralék** értékét frissíti a program a kijelölt csomagjegyzékeken található, kiszállított mennyiségek összesítésével. Ha az értékesítési rendelésen található összes cikknél 0 (nulla) a **Számlahátralék** és a **Fennmaradó szállítása** értéke, az értékesítési rendelés **Számlázott** állapotú lesz. Ha a számlához tartozó **Számlahátralék** mennyisége nem 0 (nulla), akkor az értékesítési rendelés állapota változatlan marad, és további számlákat lehet hozzá rögzíteni. 

A készlettranzakciók a számla számával frissítődnek, míg az értékesítési rendelés **Sor állapota** mezőjének értéke **Számlázott** állapotúra változik. 

Tekintse meg az **Összes értékesítési rendelés** listaoldalon az értékesítési rendelések állapotát.

## <a name="consolidate-sales-orders-or-packing-slips-for-posting"></a>Értékesítési rendelések vagy szállítólevelek konszolidálása feladáshoz
Ezt a folyamatot akkor kell használni, amikor egy vagy több értékesítési rendelés is számlázásra kész, és azokat össze kívánja vonni egyetlen számlába. 

Több számlát is kiválaszthat az **Értékesítési rendelés** listaoldalon, és ezután a **Számlák létrehozása** lehetőséggel konszolidálhatja azokat. A **Számla feladása** lapon módosíthatja a **Rendelés összesítése** beállítást a rendelési szám (ha egy értékesítési rendeléshez több szállítólevél tartozik) vagy a számlaszám (ha egyetlen számlához több értékesítési rendelés tartozik) alapján történő összegzéshez. Használja az **Elrendezés** gombot az értékesítési rendelések összevonásához egyetlen számlába – a **Rendelés összesítése** beállítás alapján.

## <a name="additional-settings-that-change-the-posting-behavior"></a>További beállítások a feladás módjának megváltoztatásához
A következő mezők esetében módosul a viselkedés a feladási folyamat során.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Mező</th>
<th>Leírás</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Mennyiség</td>
<td>Válassza ki, hogy milyen mennyiségeken alapuljon a dokumentum feladása. A mezőben elérhető beállítások a feladott dokumentum típusától (például szállítólevél vagy számla) függenek.
<ul>
<li><strong>Szállítás most</strong> – A <strong>Szállítás most</strong> mezőben megadott összes mennyiség kijelölése. Ezzel a beállítással részleges rendelést lehet megerősíteni vagy szállítani.</li>
<li><strong>Kitárolt</strong> – A már kitárolt mennyiségek kiválasztása.</li>
<li><strong>Minden</strong> – Az aktuális dokumentumtípussal még nem frissített összes értékesítési rendelési mennyiség kijelölése.</li>
<li><strong>Csomagolási elismervény</strong> – A csomagjegyzéken szereplő összes, még nem frissített mennyiség kijelölése.</li>
<li><strong>Kitárolt mennyiség és nem raktározott termékek</strong> – Jelölje be az összes, már kitárolt mennyiséget és az összes nem raktározott termékmennyiséget.</li>
</ul></td>
</tr>
<tr class="even">
<td>Feladás</td>
<td><ul>
<li>Jelölje be ezt az opciót az értékesítési rendelés naplózásához.</li>
<li>Számviteli számla értékesítési rendelés nyomtatásához törölje ezt az opciót. <strong>Megjegyzés:</strong> Ha megállapodott a fizetési ütemezésről, akkor az nem látható a számviteli számla értékesítési rendelésen. A fizetési ütemezések csak magán az értékesítési rendeléseken láthatóak.</li>
</ul></td>
</tr>
<tr class="odd">
<td>Kiválasztás később</td>
<td>Akkor jelölje be ezt a lehetőséget, ha később szeretné alkalmazni a kiválasztott lekérdezést. Ezt a beállítást a kötegelt feladatokhoz szokás használni. A kötegelt feladat futtatása alkalmával a lekérdezés futtatása.</td>
</tr>
<tr class="even">
<td>Mennyiség csökkentése</td>
<td>Válassza ki ezt az opciót, hogy dokumentum feladásakor automatikusan csökkentse a megrendelt mennyiséget az elérhető készlettel megegyező értékre.</td>
</tr>
<tr class="odd">
<td>Nyomtatás</td>
<td>Válassza ki, mikor kerüljenek a dokumentumok nyomtatásra:
<ul>
<li><strong>Aktuális</strong> – Dokumentumok nyomtatása minden egyes számla frissítését követően.</li>
<li><strong>Utána</strong> – Dokumentumok nyomtatás az összes számla frissítését követően.</li>
</ul>
<strong>Megjegyzés:</strong> A <strong>Nyomtatás</strong> mező csak akkor érhető el, ha a <strong>Számla nyomtatása</strong>, <strong>Nyomtatás visszaigazolása</strong>, <strong>Kitárolási lista nyomtatása</strong> vagy <strong>Szállítólevél nyomtatása</strong> opció egyikét választja. Például, a <strong>Képernyőrendezés</strong> oldalon úgy állította be a programot, hogy számlafogadó szerint rendezze az információkat. Ekkor kiválaszthatja az <strong>Utána</strong> opciót, hogy számlafogadók szerint sorrendbe rakott kötegben nyomtassa a dokumentumokat. Ellenkező esetben a dokumentumok nyomtatása feldolgozás befejezése előtt megtörténik, és a dokumentumok nem lesznek a <strong>Képernyőrendezés</strong> oldalon megadott sorrendben rendezve.</td>
</tr>
<tr class="even">
<td>Számla nyomtatása</td>
<td>Jelölje be ezt az opciót az számla nyomtatásához. Ha ez a beállítás ki van kapcsolva, nyomtatás nélkül is fel lehet adni egy számlát.</td>
</tr>
<tr class="odd">
<td>E-mail küldése</td>
<td>Ezt a lehetőséget abban az esetben válassza, ha az értékesítési rendeléshez tartozó számlát a feladását követően egy e-mail üzenet mellékleteként szeretné elküldeni a vevőnek. A mellékletek PDF és XML formátumú fájlként kerülnek elküldésre. Ez a beállítás akkor érhető el, ha bejelöli a <strong>CFD (elektronikus számlák) engedélyezése</strong> beállítást az <strong>Elektronikus számla paraméterei </strong>oldalon. <strong>Megjegyzés:</strong> (MEX) Ez a vezérlő csak mexikói elsődleges címmel rendelkező jogi személyek számára elérhető.</td>
</tr>
<tr class="even">
<td>Nyomtatáskezelés céljának használata</td>
<td>Jelölje be ezt az opciót, ha azon nyomtatási beállításokat szeretné alkalmazni, amelyeket a tranzakció, a dokumentum vagy a modul esetében megadott a <strong>Nyomtatáskezelési beállítások</strong> oldalon.</td>
</tr>
<tr class="odd">
<td>Hitelkeret ellenőrzése</td>
<td>Válassza ki a hitelkeret-ellenőrzés alkalmával ellenőrizendő adatokat.
<ul>
<li><strong>Nincs</strong> – Nincs előírva hitelkeret-ellenőrzés.</li>
<li><strong>Egyenleg</strong> – A rendszer összeveti a vevő egyenlegét a hitelkerettel.</li>
<li><strong>Egyenleg + szállítólevél vagy termékbevételezési bizonylat</strong> – A hitelkeret összevetése a vevői egyenleggel és a szállításokkal.</li>
<li><strong>Egyenleg + Minden</strong> – A hitelkeret összevetése a vevői egyenleggel, a szállításokkal és a nyitott rendelésekkel.</li>
</ul></td>
</tr>
<tr class="even">
<td>Jóváírás korrekciója</td>
<td>Válassza ki ezt a lehetőséget, hogy a jóváírás tartozás tételként jelenjen meg a bizonylati tranzakciók között.</td>
</tr>
<tr class="odd">
<td>Fennmaradó mennyiség jóváírása</td>
<td>Akkor jelölje be ezt az opciót, ha jóváírást ad fel, és azt szeretné, ha a fennmaradó mennyiség rendelésen maradna. Ha törli a jelet a négyzetből, akkor a fennmaradó mennyiség nullára módosul.</td>
</tr>
<tr class="even">
<td>Összesített módosítás a következőhöz:</td>
<td>Válassza ki, hogy hogyan történjen több értékesítési rendelés frissítése:
<ul>
<li><strong>Nincs</strong> – Ne összegződjenek az értékesítési rendelések. Így például egy külön számla fog létrejönni minden értékesítési rendeléshez.</li>
<li><strong>Számlafogadó</strong> – A rendszer az <strong>Összesítő frissítés paraméterei</strong> oldalon beállított feltételeknek megfelelően összegzi a kiválasztott rendeléseket.</li>
<li><strong>Rendelés</strong> – Egy kiválasztott rendeléstartomány összegzése egyetlen, megadott rendelésbe. A rendszer az <strong>Összesítő frissítés paraméterei</strong> oldalon beállított feltételeknek megfelelően összegzi a kiválasztott rendeléseket. Ha ezt a lehetőséget választja, ki kell választania egy értéket az <strong>Értékesítési rendelés</strong> mezőben.</li>
<li><strong>Automatikus összegzés</strong> – Az összes kiválasztott rendelésen megtörténik az összesítő frissítés az <strong>Összesítő frissítés paraméterei</strong> oldalon beállított feltételeknek megfelelően, de csak abban az esetben, ha az <strong>Összesítés frissítése</strong> oldalon be van állítva az összesítő frissítés. Ha nem adott meg összesítő frissítést, a rendelés külön lesz feladva.</li>
<li><strong>Szállítólevél</strong> – A kiválasztott rendelések összegzése csomagjegyzékenként egy számlában. Ez a lehetőség csak akkor érhető el, ha a <strong>Szállítólevél</strong> beállítás van kiválasztva a <strong>Mennyiség</strong> mezőben.</li>
</ul></td>
</tr>
</tbody>
</table>






