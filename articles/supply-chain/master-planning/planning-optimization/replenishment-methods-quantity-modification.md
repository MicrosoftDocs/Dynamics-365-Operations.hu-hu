---
title: Feltöltési módok és a mennyiség módosítása
description: Ez a témakör a Tervezési optimalizálásban szereplő feltöltési módokról szolgál információval. Azt is ismerteti, hogy hogyan befolyásolja egy termék több rendelési mennyisége az eredményt.
author: crytt
ms.date: 6/1/2021
ms.topic: article
ms.search.form: ReqGroup, ReqItemTable, InventItemOrderSetup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-06-01
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 19853bdb3c469dbfea3a3a0165a9cb5f47e73122cc695de3535a58f6e65e7933
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6759527"
---
# <a name="replenishment-methods-and-quantity-modification"></a>Feltöltési módok és a mennyiség módosítása

[!include [banner](../../includes/banner.md)]

Ez a témakör a Tervezési optimalizálásban szereplő feltöltési módokról szolgál információval. Azt is ismerteti, hogy hogyan befolyásolja egy termék több rendelési mennyisége az eredményt.

A feltöltési módszerek fedezeti vagy adagméretezési módszerekként is ismertek.

## <a name="coverage-codes"></a>Fedezeti kódok

A Tervezési optimalizálás beállítható úgy, hogy különböző feltöltési módokat használjon. A feltöltési módok olyan technikák, amelyekkel a rendszer a termékek követelményeit számítja ki. A feltöltési módokat olyan fedezeti kódok határozzák meg, amelyek a fedezeti csoportban vagy a termékben állíthatók be.

A Tervezési optimalizálásban a következő fedezeti kódok használhatók:

- **Időszak** – Ez a feltöltési módszer az adott időszakra vonatkozó összes igényt egy rendelésbe egyesíti a termékre vonatkozóan. A rendelés tervezése az időszak első napjához történik, és a rendelés mennyisége teljesíti a nettó szükségletet a meghatározott időszakban. Az időszak a termék első igényével kezdődik és a megadott időtartamra vonatkozik. A következő időszak a termék következő igényével kezdődik. Az *Időszak* fedezeti kód gyakran használatos előre nem jelezhető készletkérésre, szezonális termékekre vagy magas költségű termékekhez. A következő ábrán egy példa látható.

    ![Példa az Időszak fedezeti kód használatára.](./media/coverage-code-period.png "Példa az Időszak fedezeti kód használatára")

- **Igény** – A feltöltési módszerben a rendszer a termékre vonatkozó szükséglet alapján tervezett beszerzési, átmozgatási vagy termelési rendelést hoz létre. Ez a módszer olyan költséges termékeknél használatos, amelyekre időszakos igény van. Az *Igény* fedezeti kódot gyakran használják konfigurálható termékekhez és rendelésre történő gyártás esetén. A következő ábrán egy példa látható.

    ![Példa az Igény fedezeti kód használatára.](./media/coverage-code-requirement.png "Példa az Igény fedezeti kód használatára")

- **Min./max.** – A feltöltési módszer a készlet szintjén alapul. Ha az előrejelzett aktuális szint egy konkrét küszöbérték alatt van, akkor meghatározza a készlet adott szintig történő feltöltését. A feltöltési mennyiség a maximális szint és az előre jelzett aktuális szint közötti különbség lesz. A *Min./max.* fedezeti kódot gyakran használják kiszámítható készletkérésre, a legkeresettebb vagy a kevésbé drága termékeknél. A következő ábrán egy példa látható.

    ![Példa a Min./max. fedezeti kód használatára.](./media/coverage-code-min-max.png "Példa a Min./max. fedezeti kód használatára")

- **Manuális** – A feltöltési módszernél a rendszer nem javasol beszerzési, átviteli vagy termelési rendeléseket a termékhez. Ehelyett a termék tervezője felelős a termék feltöltéséhez szükséges rendelések létrehozásáért. A *Manuális* fedezeti kódot gyakran használják olyan termékekhez, amelyeknél nincs szükség rendszer által generált tervezett rendelésekre.

## <a name="impact-of-the-order-quantity-from-default-order-settings"></a>Az alapértelmezett rendelési beállításokból származó rendelési mennyiség hatása

A kiadott termékekhez tartozó **Alapértelmezett rendelésbeállítások** oldalon megadhatók a **Beszerzési rendelés**, a **Készlet** és az **Értékesítési rendelés** gyorslapon lévő következő mennyiségi beállítások. (A **Készlet** gyorslap az átmozgatási és a termelési rendelésekhez is használható.)

- **Többszörös** – A tervezett rendelések ennek a mennyiségnek a többszörösei lesznek.

    Ha a **Többszörös** mező értéke például *5*, akkor a rendelés mennyisége 10, 15, 20, stb. lehet.

- **Minimális rendelési mennyiség** – A tervezett rendelések nem lesznek kisebbek, mint a megadott érték.

    Ha a **Minimális rendelési mennyiség** mező értéke például *10*, akkor a rendszer által létrehozott tervezett rendelés mennyisége még akkor is 10 lesz, ha az igény kielégítéséhez csak 4 szükséges.

- **Maximális rendelési mennyiség** – A tervezett rendelések nem lesznek nagyobbak, mint a megadott érték. Ha az igény több, mint a **Maximális rendelési mennyiség**, akkor több tervezett rendelés jön létre a fedezéséhez.

    Ha például a **Maximális rendelés mennyisége** mező értéke *100*, 100-ra van állítva, és az igény 450, akkor négy 100 mennyiségű és egy 50 mennyiségű tervezett rendelés jön létre.

## <a name="examples-of-replenishment-that-use-the-minmax-coverage-code"></a>Példák a Min./max. fedezeti kódot használó feltöltésre

Ha egy terméknél nem ad meg értéket a **Többszörös** mezőben az **Alapértelmezett rendelésbeállítások** oldalon, és ha a *Min./max.* feltöltési módot használja, akkor a Tervezési optimalizálás egy konkrét szintig feltölti a készletet, amikor az előrejelzett készletszint egy adott küszöbérték alá csökken.

Ha egy termékhez több mennyiséget ad meg, akkor a *Min./max.* feltöltési mód viselkedése módosul, és figyelembe veszi a **Többszörös** értéket.

Más szóval, a Tervezési optimalizálás akkor is feltölti a megadott maximális szintig a készletet, ha az előrejelzett készletszint kisebb, mint a megadott minimális szint. A feltöltési mennyiségnek azonban a **Többszörös** érték többszörösének kell lennie.

Ha a feltöltési mennyiség (a maximális szint és az előrejelzett tényleges szint különbsége) nem a megadott többszörös mennyiség többszöröse, akkor a Tervezési optimalizálás az első olyan lehetséges értéket használja, amely az előrejelzett készletszinttel együtt a maximális szint alá kerül. Ha az összeg kisebb a minimális szintnél, akkor a Tervezési optimalizálás az első olyan értéket használja, amely az előrejelzett tényleges szinttel a maximális szint felett lesz.

Az alábbi alszakaszokban néhány olyan példa látható, amely bemutatja, hogy egy termék több rendelési mennyisége milyen hatással van a *Min./max.* feltöltési módra.

### <a name="example-1"></a>1. példa

Egy termék a következő konfigurációval rendelkezik:

- **Fedezeti kód:** *Min./max.*
- **Minimum:** *15*
- **Maximum:** *22*
- **Többszörös:** *0*

A termékhez 10 darab az aktuális készlet, és nincs más igény vagy ellátás.

Az alaptervezés futtatásakor egy 12 darabos tervezett rendelés jön létre, amely a maximális mennyiségre feltölti a készletet.

### <a name="example-2"></a>2. példa

Egy termék a következő konfigurációval rendelkezik:

- **Fedezeti kód:** *Min./max.*
- **Minimum:** *15*
- **Maximum:** *22*
- **Többszörös:** *5*

A termékhez 10 darab az aktuális készlet, és nincs más igény vagy ellátás.

Az alaptervezés futtatásakor egy 10 darabos tervezett rendelés jön létre (mivel a feltöltés 15 darab, az aktuális készlet pedig 10, és ez meghaladja a maximális mennyiséget).

### <a name="example-3"></a>3. példa

Egy termék a következő konfigurációval rendelkezik:

- **Fedezeti kód:** *Min./max.*
- **Minimum:** *21*
- **Maximum:** *24*
- **Többszörös:** *5*

A termékhez 10 darab az aktuális készlet, és nincs más igény vagy ellátás.

Az alaptervezés futtatásakor egy 15 darabos tervezett rendelés jön létre (mivel a feltöltés 10 darab, az aktuális készlet pedig 10, és ez kisebb a minimális mennyiségnél).

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
