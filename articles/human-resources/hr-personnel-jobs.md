---
title: Feladat összetevőinek beállítása
description: Ez a cikk azt ismerteti, milyen fogalmi elemek alkothatnak egy feladatot, és példákat ad arra, hogyan használhatja ezen elemeket a szervezetben.
author: andreabichsel
ms.date: 06/24/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmJob, HcmJobFunction, HcmJobTask, HcmTitle, HcmPersonnelManagementWorkspace, HCMJobFamily
audience: Application User
ms.author: anbichse
ms.search.scope: Human Resources
ms.custom: 269054
ms.assetid: 889a8fab-0eef-45c2-91fc-ff2f4d44d54f
ms.search.region: Global
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 55f3edb53236734045e94ddd71461c739d3b5a8e0a2ac07a804dc2dfafabda57
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6754776"
---
# <a name="set-up-the-components-of-a-job"></a>Feladat összetevőinek beállítása

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Ez a cikk azt ismerteti, milyen fogalmi elemek alkothatnak egy feladatot, és példákat ad arra, hogyan használhatja ezen elemeket a szervezetben. 

Feladatok létrehozása előtt be kell állítania bizonyos referenciaadatokat. Létrehozhat olyan feladatot is, amelynek csak neve van. További információk - például beosztás - megadásával viszont alapértelmezett értékek biztosíthatók a feladathoz rendelt beosztások számára. Emellett a beírt adatok egy része használható kompenzációs konstrukciók szűréséhez konkrét feladatokhoz. Ha szeretne jogosultságot beállítani, amelyet felhasználhat bizonyos feladathoz tartozó kompenzációs konstrukciók szűrésére, úgy állítson be feladatbeosztásokat és feladattípusokat a feladatok beállítása előtt. Ha ezen alapértelmezett értékek elérhetők, időt takaríthat meg, amikor beosztások hozzáadását végzi a feladathoz. 

Egyes feladatadatok, például a beosztás, a típus és a funkció dátumfüggőek. Ha ma létrehoz egy feladatot, de ezeket az adatokat csak később adja hozzá, és aztán megnézi a feladatot a létrehozás dátuma szerint, úgy ezek az adatok nem jelennek meg. Ezért célszerű létrehozni ezeket az információkat még azelőtt, hogy szükség lenne rájuk. Ily módon az információkat hozzáadhatja új feladatok létrehozásakor.

## <a name="job-titles"></a>Beosztások
A létrehozni kívánt beosztásokhoz titulusokat is be kell állítania. A pozíciók azon beosztások titulusait öröklik, amelyekhez hozzárendelték őket. 

Beosztások karbantartásához használja a **Beosztások** oldalt, amely a keresés funkció segítségével nyitható meg. A **Beosztások** oldalon írja be a beosztásokat, amelyeket használni tervez a feladatokhoz.

## <a name="job-types"></a>Feladattípusok
Beosztástípusok segítségével a hasonló feladatok kategóriákba sorolhatók. A beosztástípusok használata nem kötelező, azonban ha a későbbiekben a kompenzációkezelés jogosultsági szabályainak beállításakor szeretne beosztástípusokat használni, ezeket még a beosztások előtt kell beállítania. Beosztástípusok például teljes és részmunkaidős, illetve a munkabéres és az órabéres. A beosztástípusok karbantartásához használja a **Beosztástípusok** oldalt. A **Beosztástípusok** oldalon adja meg a beosztástípus nevét és rövid leírását. A **Mentességi állapot** mezőben a következő lehetőségek közül választhat annak jelzésére az ilyen beosztástípusú feladatoknál, hogy az Egyesült Államok munkajogi törvénye (FLSA, Fair Labor Standards Act) ezekre a feladatokra nem vonatkozik:

-   **Mentes** – A beosztásokhoz az FLSA szerint túlórapénz nem jár.
-   **Nem mentes** – A beosztásokhoz az FLSA szerint túlórapénz jár.
-   **Nem alkalmazható** – Az FLSA hatálya erre nem terjed ki.

## <a name="job-family"></a>Feladatcsalád
A feladatcsalád a hasonló munkát igénylő feladatok olyan csoportja, amely hasonló képzettséget, szakértelmet, tudást és tapasztalatot igényel. A feladatcsaládok összekapcsolhatók a **Feladatok** oldal **Feladatosztályozás** gyorslapján és a **Minden pozíció** oldal **Általános** gyorslapján lévő feladatokkal. A feladatcsaládok lehetnek általánosak vagy specifikusak az üzleti és a jelentési követelményektől függően. Az általános feladatcsaládokra jó példa a **Szakképzett munka** és a **Szakképzettséget nem igénylő munka**. Néhány példa a konkrét feladatcsaládokra a **Könyvelés**, a **Gyártás** és az **Értékesítés**.

A feladatcsaládok karbantartásához használja a **Feladatcsaládok** oldalt, amelyet a keresési funkció segítségével nyithat meg. A **Feladatcsalád** oldalon adjon meg egy egyedi nevet a családnak, és adja meg a feladatokhoz használni tervezett részletes leírást.

## <a name="job-functions"></a>Feladatfunkciók
A beosztási funkciók magas szintű funkcionális kategóriákat írnak le magas szintű feladatokat írnak elő. A beosztási funkciók használata nem kötelező, A beosztási funkciókat és beosztási típusokat együttesen felhasználva az egyes feladatokhoz hozzá lehet szűrni a kompenzációs konstrukciókat. A feladatfunkciók és feladattípusok kompenzációs konstrukciókhoz társítása az **Alkalmazhatósági szabályok** oldalon, alkalmazhatósági szabályok felállításával történik. Ezen túlmenően a kompenzációs konstrukcióhoz hozzá lehet csatolni a szintek azon csoportját, amelyek az alkalmazhatósági szabály által behatárolt, adott feladattípus/feladatfunkció kombinációra vonatkoznak. (Ezek a funkciók mind a fix, mind a változó kompenzációs konstrukcióra vonatkoznak.) A beosztásfunkciók használata nem kötelező, azonban ha a későbbiekben a kompenzációkezelés jogosultsági szabályainak beállításakor szeretne beosztásfunkciókat használni, ezeket még a beosztások előtt kell beállítania. Az alábbi táblázatban látható néhány példa munkaköri beosztásokra.

| Munka           | Beosztás         |
|---------------|----------------------|
| Értékesítési igazgató | Középvezetői szint    |
| Könyvelő    | Szakemberek        |

A beosztási funkciók karbantartásához használja a **Beosztási funkciók** oldalt. A **Beosztási funkciók** oldalon adja meg a beosztási funkció azonosító kódját és rövid leírását.

## <a name="compensation"></a>Kompenzáció
Ha fix kompenzációs konstrukciót szeretne hozzárendelni egy olyan alkalmazotthoz, aki egy adott beosztásban van egy adott feladaton belül, kompenzációs szinteket kell beállítania a feladathoz. A kompenzációs szintek akkor használatosak, amikor be van állítva a minimális, a középső és a maximális összeg egy kompenzációs struktúrában (kompenzációs rácsban). Fix kompenzációs konstrukció létrehozása esetén a kompenzációs szerkezetet kell kiválasztani. A kompenzációs struktúra tartalmazza a kompenzációs szintet is. Amikor egy alkalmazotthoz fix kompenzációs konstrukciót választ, a kiválasztható kompenzációs szintek az alkalmazott beosztásához hozzárendelt feladattól függenek. A kompenzáció beállításával kapcsolatos további információkért lásd: [Kompenzációs konstrukciók](hr-compensation-overview.md).

## <a name="job-skills"></a>Feladat – szakértelem
A feladathoz tartozó szakértelem írja le a feladat végrehajtásához szükséges készségeket. A feladat minden szakértelmi eleméhez társítani kell a szakértelem szintjét. A szakértelem szintjeit a felhasználó határozza meg. Jelzik, hogy milyen szintű tudás vagy jártasság szükséges az szakterületen. A vállalatok beállíthatnak például numerikus, 1-től 5-ig terjedő szintrendszert, amelyben az **1** a kezdő, az **5** pedig a szakértő szintet jelzi. Másik lehetőségként a vállalatok beállíthatnak **Kezdő**, **Haladó** és **Szakértő** jelölésű szinteket is. A szakértelem szintjének beállítása után a szakértelem fontossága is beállítható. Ha például egy könyvelőnek alapos Microsoft Excel-ismeretekkel kell rendelkezni, létrehozható egy **Excel-ismeretek** szakértelem. A szakértelemszinthez ezután beállítható a **Haladó** érték, míg a fontossághoz a **Legfontosabb** szint.

A feladathoz tartozó szakértelmek felhasználható a szakértelem hozzárendeléséhez. A szakértelem hozzárendelése összehasonlíthatja a feladathoz szükséges szakértelemkészletet a dolgozóhoz társított szakértelmi elemekkel. Ezután az egyező elemek alapján kiszámít egy százalékos értéket. A szakértelem-hozzárendelésről a [Szakértelem konfigurálása](hr-develop-skills.md) című témakörben olvashat bővebben. 

## <a name="job-tasks"></a>Munkaköri feladatok
A munkaköri feladatok bemutatják az adott pozíciójú dolgozótól elvárt alapvető feladatokat. Ugyanazon munkaköri feladatok több munkához, valamint a munkaköri feladatokat használó munkákkal kapcsolatos beosztásokhoz is hozzáadhatók. Az alábbi táblázatban látható néhány példa munkaköri feladatokra.

<table>
<thead>
<tr class="header">
<th>Munka</th>
<th>Munkaköri feladat</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Értékesítési igazgató</td>
<td><ul>
<li><strong>Teljesítményellenőrzés</strong> – Az egyes értékesítők teljesítményének áttekintése.</li>
<li><strong>Hiányzásellenőrzés</strong> – Az üzletkötők távolléti kérelmeinek vagy regisztrációnak jóváhagyása vagy elutasítása.</li>
</ul></td>
</tr>
<tr class="even">
<td>Könyvelő</td>
<td><strong>Pénzügyi jelentés</strong> – Heti pénzügyi jelentések bemutatása a pénzügyi igazgatónak.</td>
</tr>
</tbody>
</table>

A munkaköri feladatok karbantartásához használja a **Munkaköri feladatok** oldalt. A **Munkaköri feladatok** oldalon adja meg a munkaköri feladat nevét és leírását. A **Megjegyzés** mezőben igény szerint további információkat is megadhat. A megjegyzések anélkül frissülnek az adott feladathoz, hogy az itt Ön által megadott megjegyzések módosulnának.

## <a name="areas-of-responsibility"></a>Hatáskörök
Alkalmazzon hatásköröket azon a szerepkörök, folyamatok, termékek és műveletek megjelöléséhez, amelyekért a dolgozó egy adott beosztásban felelős. Például a „Könyvelő” nevű beosztáshoz tartozó hatáskörre példa lehet a „Pénzügyi jelentés az A termékkel kapcsolatban”. A hatáskörök karbantartására használja a **Hatáskörök** oldalt, amelyet a keresés funkció használatával találhat meg. A **Hatáskörök** oldalon adja meg a hatáskör nevét és leírását. A **Megjegyzés** mezőben igény szerint további információkat is megadhat. A megjegyzések anélkül frissülnek az adott feladathoz, hogy az itt Ön által megadott megjegyzések módosulnának.

## <a name="steps-for-creating-a-job"></a>A feladat létrehozásának lépései
Lásd az [Új feladatok meghatározása](./hr-personnel-define-jobs.md) cikket az új feladat létrehozásának lépésről lépésre útmutatójához. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
