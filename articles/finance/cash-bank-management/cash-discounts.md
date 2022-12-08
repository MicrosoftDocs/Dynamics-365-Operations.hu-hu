---
title: Készpénzfizetési engedmények
description: A készpénzfizetési engedmények be vannak állítva és a meg vannak osztva a kötelezettségek és kinnlevőségek számára.  Az elérhető készpénzfizetési engedmény megadható a vevői számlán vagy a szállítói számlán, és ott meg fog jelenni, ha a számla kifizetése megtörténik a készpénzfizetési engedmény dátuma előtt.
author: angelad116
ms.date: 10/24/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CashDisc
audience: Application User
ms.reviewer: kfend
ms.custom: 3741
ms.assetid: c25f9d85-2702-46aa-8e61-0b4886e069b3
ms.search.region: Global
ms.author: angelading
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b75637bfb38c13591223ff11be36d958b3972d4f
ms.sourcegitcommit: 81bb8e51951395be3f18f45212e47e6c41656f6a
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/23/2022
ms.locfileid: "9804136"
---
# <a name="cash-discounts"></a>Készpénzfizetési engedmények

[!include [banner](../includes/banner.md)]

A készpénzfizetési engedmények be vannak állítva és a meg vannak osztva a kötelezettségek és kinnlevőségek számára. Az elérhető készpénzfizetési engedmény megadható a vevői számlán vagy a szállítói számlán, és ott meg fog jelenni, ha a számla kifizetése megtörténik a készpénzfizetési engedmény dátuma előtt. 

## <a name="cash-discounts"></a>Készpénzfizetési engedmények

A vevők és szállítók készpénzfizetési engedményei a Készpénzfizetési engedmények **lapon is létre lehet** hozva. A Következő **engedménykód** mező használatával egy sor készpénzfizetési engedményt is meghatározhat, amelyek egymást váltják ki a korábbi készpénzfizetési engedmények lejárata során. További tudnivalókat a cikk későbbi, "Példa: Készpénzfizetési engedmények sorozata" tartalmaz. Ha a számla vagy jóváírási tranzakció (jóváírás vagy kifizetés) vagy mindekettő a jogi személy könyvelési pénznemében eltérő pénznemben vannak megadva, a készpénzfizetési engedmény számítása a kifizetések vagy jóváírások napja alapján az érvényes árfolyamának felhasználásával történik. Ha a számlák és jóváírási bizonylat különböző jogi személyek esetében vannak megadva, és ha a jogi személyek könyvelési pénznemei különböznek, az átváltási árfolyam a számla jogi személyétől származnak, mint a hitel dokumentum dátuma. További tudnivalókat a cikk későbbi, "Példa: készpénzfizetési engedmények árfolyama" tartalmaz.

## <a name="defaulting-order-of-cash-discount-main-account"></a>Fő számla készpénzfizetési engedmény alapértelmezési sorrendje

Ha a számla kiegyenlítése időben megtörténik ahhoz, hogy a vevő készpénzfizetési engedményt kapjon, a program automatikusan feladja a készpénzfizetési engedményt a készpénzfizetési engedmény fő számlájára, az alábbi alapértelmezési prioritást figyelembe véve:
1.  A vevő Nyitott tranzakciók kifizetése lapon vagy a nyitott tranzakciókat **egyenlítő szállító lapon az Alternatív**  **·**  **készpénzfizetési** engedmények számlája mezőben megadott fő számla.
2.  A számla **áfakódjához**  **rendelt** főkönyvi feladási csoport Vevő készpénzfizetési engedmény mezőjében vagy Szállítói készpénzfizetési engedmény mezőjében megadott fő számla. Állítsa be a főkönyvi feladási csoportokat **a Főkönyvi feladási csoportok** oldalon **, és rendelje azokat áfakódhoz az Áfakódok** lapon.
3.  A fő feladási **számla** a Készpénzfizetési engedmények oldalon vagy a **Vevői** engedmények fő számlája mezőben, **vagy** a szállítói engedmények fő számlája mezőben a kiegyenlített számlán szereplő készpénzfizetési engedménykódhoz.
4.  A készpénzfizetési engedmények fő számlája, az automatikus tranzakciók **számlája lapon megadottak** szerint.

## <a name="example-series-of-cash-discounts"></a>Példa: Készpénzfizetési engedmények sorozatai
Állítson be három kódot a készpénzfizetési engedményekhez a következők szerint:
-   5D10% kód - 10%-os készpénzfizetési engedmény, amikor az összeg 5 napon belül kerül kiegyenlítésre.
-   10D5% kód - 5%-os készpénzfizetési engedmény, ha az összeg 10 napon belül kerül kiegyenlítésre.
-   14D2% kód - 2%-os készpénzfizetési engedmény, ha az összeg 14 napon belül kerül kiegyenlítésre.

A Következő **engedménykód mezőben** :
-   Az 5D10% kódnál válassza a 10D5% elemet.
-   A 10D5% kódnál válassza a 14D2% elemet.
-   A 14N2% kódnál hagyja üresen a Következő engedménykód mezőt.

A készpénzfizetési engedmény három kódja követi egymást mivel a fizetési dátum meghaladja a számlán szereplő előző készpénzfizetési engedmény dátumát. Egy készpénzfizetési engedmény csak akkor van engedélyezve, amikro a számla ki van egyenlítve, azon alapul, hogy melyik készpénzfizetési engedmény dátuma felel meg a készpénzfizetési engedmények sorozatában.

## <a name="example-exchange-rates-for-cash-discounts"></a>Példa: Készpénzfizetési engedmények átváltási díjai
A jogi személy könyvelési pénzneme EUR és a következő árfolyamok USD-ben vannak megadva:
-   február 1 = 110
-   március 1 = 80

Február 15-én adnak fel egy 20D2%-os készpénzfizetési engedménnyel rendelkező 1000 USD-s számlát. A számla összege a könyvelési pénznemben 1100 EUR. A számlaösszegből 980 USD kifizetése történik meg március 1-jén. A készpénzfizetési engedmény összege 20 USD. A fizetés könyvelési pénznemének összege 784 EUR. A készpénzfizetési engedmény összegének a könyvelési pénznemben történő kiszámítása március 1-jei átváltási árfolyam alapján történik: 20 \* 80 / 100 = 16 EUR.

> [!NOTE]
>  **Ha a Kinnlevőségek**  **·**  **paraméterei** vagy a Kötelezettségek paraméterei oldalon a Készpénzfizetési engedmények számítása beállítás van kiválasztva, akkor a program az egyes részfizetések dátumán érvényben maradó átváltási árfolyamot használja. 



[!INCLUDE[footer-include](../../includes/footer-banner.md)]
