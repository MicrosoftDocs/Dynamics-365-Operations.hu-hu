---
title: Sablonanyagjegyzékek
description: A sablondarabjegyzékek segítségével szabványosított listát készíthet a rendszeresen szervizelt szolgáltatási tárgyak összetevőiről.
author: sorenva
ms.date: 09/19/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMATemplateBOMTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fdda8ffaaf4e5696b286273fd5ad770de5349b48
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/03/2022
ms.locfileid: "8678150"
---
# <a name="template-boms"></a>Sablonanyagjegyzékek

[!include [banner](../includes/banner.md)]

A sablondarabjegyzékek segítségével szabványosított listát készíthet a rendszeresen szervizelt szolgáltatási tárgyak összetevőiről. A sablondarabjegyzékben felsorolt összetevők a szolgáltatási objektum különálló alösszetevőit képviselik. Amikor a sablondarabjegyzéket a szolgáltatás tárgyára alkalmazza, egy olyan alösszetevő-rekordot kap, amely nyilvántartja a szolgáltatás tárgyában kicserélt alkatrészeket.

A sablonanyagjegyzéket úgy alkalmazhatja a szolgáltatási szerződésre vagy szervizrendelésre, hogy egy szolgáltatásitárgy-kapcsolathoz csatolja.

> [!NOTE]
> Minden szolgáltatás tárgyához csak egy sablondarabjegyzék csatolható.

## <a name="create-a-template-bom"></a>Sablonanyagjegyzék létrehozása

Az alábbi táblázat tartalmazza a sablondarabjegyzékek létrehozásához használható különböző módokkal kapcsolatos információk.

<table>
<colgroup>
<col />
<col />
</colgroup>
<thead>
<tr class="header">
<th><p>Metódus</p></th>
<th><p>Leírás</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Termelés</p></td>
<td><p>A sablonanyagjegyzék termelési rendeléseken alapul. Ez a lehetőség csak akkor alkalmazható, ha termelési környezetben dolgozik. A haszna pedig az, hogy naprakész és részletes alkatrészlistát tarthat nyilván a cikket alkotó elemekről.</p></td>
</tr>
<tr class="even">
<td><p>BOM cikk</p></td>
<td><p>Sablonanyagjegyzék létrehozása cikkanyagjegyzék alapján. A cikkdarabjegyzék, ellentétben a termelési darabjegyzékkel, a cikket alkotó összetevők statikus listája.</p></td>
</tr>
<tr class="odd">
<td><p>Meglévő sablon</p></td>
<td><p>A sablon alapja egy meglévő sablonanyagjegyzék.</p></td>
</tr>
<tr class="even">
<td><p>Manuális</p></td>
<td><p>Ha tudja, hogy általában milyen alkatrészeket kell cserélni a szolgáltatás tárgyában, akkor akár kézzel is létrehozhatja a sablonanyagjegyzéket. Ezzel a módszerrel gondoskodhat arról, hogy a sablonban rögzített összetevők a munkahely tényleges szükségleteit tükrözzék.</p></td>
</tr>
</tbody>
</table>

## <a name="apply-the-template-bom-to-a-service-agreement-or-service-order"></a>Sablonanyagjegyzék alkalmazása szolgáltatási szerződésre vagy szervizrendelésre

A sablonanyagjegyzék szolgáltatási szerződésre és szervizrendelésre vagy minkettőre alkalmazható. A szolgáltatási szerződés általában egy hosszú távú viszonyt testesít meg a vevővel. A szolgáltatási anyagjegyzék által nyilvántartott korábbi cserék hasznos információkat szolgáltatnak a szolgáltatási szerződéshez.

A sablonanyagjegyzék egy szervizrendelésre is alkalmazható, a szolgáltatás tárgyán végrehajtott szerviz előzményeinek rögzítéséhez.

## <a name="copy-the-history-of-a-service-bom"></a>A szolgáltatási anyagjegyzékben szereplő előzmények másolása

A szolgáltatási anyagjegyzék előzménysorai másolhatók az egyik szolgáltatási szerződésből egy másikba. A szolgáltatási előzmények szerződések közötti másolásával megőrizheti a nyilvántartást a cikkek cseréiről.

### <a name="example"></a>Példa

A vállalat három évre szóló szolgáltatási szerződést kötött a vevő autójára. Ezen időszak alatt a vevő hozzászokik a vállalat által nyújtott kiváló szolgáltatáshoz. Emiatt a szerződés lejárta után a vevő szeretne beállítani egy újat. Ebben a helyzetben lehetősége van arra, hogy a vállalat számára kedvezőbb szerződést kössön. Mivel a cserélt alkatrészek nyilvántartása hasznos lehet a jövőben is, ezért a szolgáltatási anyagjegyzék sorait átmásolja az új szerződésbe.

## <a name="modify-the-template-bom"></a>A sablonanyagjegyzék módosítása

Ha egy sablonanyagjegyzék nincs csatolva egy szolgáltatási tárgyhoz, módosíthatja vagy törölheti a sorait. Miután a sablon anyagjegyzéket csatolták egy szolgáltatási tárgyhoz, csak az anyagjegyzék helyi verziója módosítható. Ha szeretné duplikálni a sablonanyagjegyzék helyi változatának beállításait, új sablon anyagjegyzék hozható létre a helyi verzió alapján. További információkkal kapcsolatban lásd: [Szolgáltatási darabjegyzék módosítása](modify-service-bom.md).

Ha kicserél egy anyagjegyzékben szereplő cikket, akkor ezt az anyagjegyzék-szerkesztőben bejegyezheti az anyagjegyzékbe. Opcionálisan szervizrendeléssort hozhat létre a cserecikkhez. Ha szervizrendeléssort hoz létre, akkor számlázhatja a cserecikket. Ha nem hoz létre szervizrendeléssort a cseréhez, akkor a csere regisztrációja a szolgáltatás tárgyán végzett cserék nyilvántartására lesz megőrizve.

## <a name="change-how-information-on-the-bom-line-is-displayed"></a>Az anyagjegyzéksor adatai megjelenítési módjának módosítása

Minden sablonban és szolgáltatási anyagjegyzékre nézve módosíthatja, hogy hogyan jelenjenek meg az anyagjegyzéksor adatai. A módosítások minden sablon anyagjegyzékre és szolgáltatási anyagjegyzékre alkalmazva lesznek. Ebbe beletartoznak azok is, amelyek a szolgáltatás tárgyaihoz kapcsolódnak.

## <a name="set-up-number-sequences-for-template-boms"></a>A sablonanyagjegyzékek számsorozatainak beállítása

Sablonanyagjegyzékek használatához két számsorozatot kell beállítani. Állítson be egy számsorozatot a sablonanyagjegyzékhez, és egyet az anyagjegyzék-előzmény sorszámához.

> [!NOTE]
> A számsorozatokat a rendszer mindenütt használja azonosítók kiosztásához azoknak a rekordoknak, amelyek igénylik őket. Mielőtt hozzárendelhetne egy számsorozatot egy sablonanyagjegyzékhez vagy egy anyagjegyzék-előzmény sorszámához, be kell állítania a számsorozat kódokat.

## <a name="set-up-number-sequences"></a>Számsorozatok beállítása

1. A **Számsorozatok** listaoldalon hozza létre számsorozatokat a sablonanyagjegyzékek és az anyagjegyzék-előzmény sorszámához.
1. Válassza a **Szolgáltatáskezelés** \> **Beállítás** \> **Szolgáltatáskezelési paraméterek** pontot.
1. Válassz a **Számsorozatok** elemet, és ezután válassza ki a számsorozat kódját a számsorozat-hivatkozásokhoz, amelyeket létrehozott a **Számsorozatok** képernyőn.
1. A módosítások mentéséhez zárja be a képernyőt.

> [!NOTE]
> Az anyagjegyzék-előzmény sorszáma szolgál a rendszerben az anyagjegyzék-előzményekben a tranzakciók társítására egy szolgáltatási szerződéssel vagy szervizrendeléssel. A szám nem jelenik meg a felhasználói felületen.

## <a name="see-also"></a>Lásd még

[Sablonanyagjegyzék létrehozása](create-template-bom.md)

[Anyagjegyzéksablonok kezelése tárgykapcsolatokon](manage-template-boms-on-object-relations.md)

[Szolgáltatási anyagjegyzék módosítása](modify-service-bom.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
