---
title: Könyvvizsgálati irányelvszabály
description: Naplózási házirendek segítségével kiértékelhet költségjelentéseket, szállítói számlákat és beszerzési rendeléseket, hogy így meggyőződhessen arról, hogy azok megfelelnek-e az Ön által létrehozandó irányelvszabályoknak. Minden olyan szabály, amelyhez egy könyvvizsgálati irányelv van társítva, kötegelt módban van futtatva a megadott ütemezés szerint.  Minden egyes irányelvszabály egy irányelvszabály-típus egy példánya. Minden egyes irányelvszabály-típusra nézve csak egy irányelvszabály lehet aktív egyszerre.
author: ryansandness
manager: AnnBe
ms.date: 08/01/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AuditPolicyAdditionalOption, AuditPolicyRule
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 12991
ms.assetid: 8d787017-71dc-418f-b8c2-4ea9763d9978
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: de6406029aa88424863dd9a47505f5b3ad27f237
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4443937"
---
# <a name="audit-policy-rules"></a>Könyvvizsgálati irányelvszabály

[!include [banner](../includes/banner.md)]

Naplózási házirendek segítségével kiértékelhet költségjelentéseket, szállítói számlákat és beszerzési rendeléseket, hogy így meggyőződhessen arról, hogy azok megfelelnek-e az Ön által létrehozandó irányelvszabályoknak. Minden olyan szabály, amelyhez egy könyvvizsgálati irányelv van társítva, kötegelt módban van futtatva a megadott ütemezés szerint.  Minden egyes irányelvszabály egy irányelvszabály-típus egy példánya. Minden egyes irányelvszabály-típusra nézve csak egy irányelvszabály lehet aktív egyszerre. 

<a name="queries-and-query-types"></a>Lekérdezések és a lekérdezéstípusok
-----------------------

Ha könyvvizsgálati irányelvszabályt hoz létre, először irányelvszabály-típust választ. Az irányelvszabály-típus megadja az irányelvszabályok létrehozásának kiinduló pontjaként használandó alkalmazásobjektum-fa (AOT) lekérdezést. Az irányelvszabályhoz használandó lekérdezés típusát is megadja. A lekérdezés meghatározza azt a forrásbizonylatot, amit az irányelvszabály kiértékel. Azokat a mezőket is megadja a forrásdokumentumban, amelyek mind a jogi személyt mind a használandó dátumot azonosítják, amikor dokumentumokat választanak ki ellenőrzésre. A lekérdezéstípus meghatározza a lekérdezési oldalon és a Könyvviteli irányelvszabály oldalon levő alapértelmezett mezőket. Az alábbi táblázatban az audit-irányelvszabályokhoz elérhető lekérdezéstípusok felsorolása található.

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Lekérdezés típusa</th>
<th>Cél</th>
<th>További információ</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Feltételes</td>
<td>Értékelje ki a forrásdokumentum attribútumait megadott értékek ellenében.</td>
<td></td>
</tr>
<tr class="even">
<td>Összesítés</td>
<td>A numerikus értékek összesítésével értékelje a többszörös forrásbizonylatokat vagy forrásbizonylat-sorokat az irányelvszabállyal összehasonlítva.</td>
<td></td>
</tr>
<tr class="odd">
<td>Mintavétel</td>
<td>Az irányelvszegések megállapításához válasszon ki véletlenszerűen egy meghatározott százalékarányú forrásbizonylatot.</td>
<td>Ha ezt a lehetőséget választja, a Könyvviteli irányelvszabály oldalon adja meg az ellenőrzésre véletlenszerűen kiválasztandó bizonylatok százalékos arányát.</td>
</tr>
<tr class="even">
<td>Másolat</td>
<td>Értékelje a forrásbizonylatokat abból a szempontból, hogy tartalmaznak-e a megadott mezőkben ismétlődő bejegyzéseket.</td>
<td>Ha ezt a lehetőséget választja, használja a Könyvviteli irányelvszabály oldalt a bizonylatok kiválasztásához megadandó dátumtartomány kezdetéhez hozzáadandó napok számának megadásához, amikor a bizonylatokban ismétlődő bejegyzéseket keres.</td>
</tr>
<tr class="odd">
<td>Keresés listán</td>
<td>Konkrét entitások forrásbizonylatainak kiértékelése.</td>
<td>A lekérdezés főbizonylata meghatározza azt a bizonylatot, amely auditálás alatt áll. A lekérdezésnek a listalekérdezésnek kell lennie, amely tartalmaz egy hivatkozást a dirpartytable táblázatba. Ez a lehetőség csak a következő alkalmazásobjektum-fa lekérdezések esetén használható:
<ul>
<li><span class="ui">AuditPolicyExpenseList</span> (Költségjelentéssel ellenőrzött alkalmazottak)</li>
<li><span class="ui">AuditPolicyPurchList</span> (Beszerzési rendeléssel ellenőrzött szállítók)</li>
<li><span class="ui">AuditPolicyVendInvoiceList</span> (Szállítói számlával ellenőrzött szállítók)</li>
</ul>
Ha ezt a lehetőséget választja, adja meg a figyelt entitásokat a Könyvviteli irányelvszabály lapon.</td>
</tr>
<tr class="even">
<td>Kulcsszó keresése</td>
<td>Értékelje a forrásbizonylatokat abból a szempontból, hogy tartalmaznak-e bizonyos szavakat.</td>
<td>Ha ezt a lehetőséget választja, adja meg a keresett szavakat a Könyvviteli irányelvszabály lapon. A Könyvviteli irányelvszabály lap olyan lehetőségeket kínál, amelyek lehetővé teszik, hogy megadhassa az Ön által beírt szavak kiértékeléséhez szükséges táblákat és mezőket.</td>
</tr>
</tbody>
</table>

## <a name="common-parameters"></a>Gyakori paraméterek
Az egy adott auditirányelvre vonatkozó összes irányelvszabály ugyanazon kötegparaméterekkel és ugyanazon bizonylat-kiválasztási dátumtartománnyal rendelkezik. Ezek a paraméterek megadásra kerülnek az irányelvre a Könyvviteli irányelvszabály lapon.



<a name="additional-resources"></a>További erőforrások
--------

[Könyvvizsgálati irányelvmegsértések és esetek](audit-policy-violations-cases.md)
[Naplózási házirendek meghatározása a forrásbizonylatok számára](tasks/define-audit-policies-source-documents.md)




[!INCLUDE[footer-include](../../includes/footer-banner.md)]