---
title: Készlettranzakciók archiválása
description: Ez a témakör azt ismerteti, hogyan lehet archiválni a készlettranzakciók adatait a rendszer teljesítményének javítása érdekében.
author: yufeihuang
ms.date: 05/10/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTransArchiveProcessForm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2021-03-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: c63cdee862e2e22649a3eb58ae37597741770e14
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8874101"
---
# <a name="archive-inventory-transactions"></a>Készlettranzakciók archiválása

[!include [banner](../../includes/banner.md)]

Az idő folyamán a készlettranzakciók táblája (`InventTrans`) tovább nő és több adatbázisterületet foglal el. Emiatt a táblába küldött lekérdezések fokozatosan lelassulnak. Ez a cikk azt ismerteti, hogyan *lehet* archiválni a készlettranzakciók archív funkcióját a készlettranzakciók adatainak archiválásához, hogy ezzel javítsa a rendszer teljesítményét.

> [!NOTE]
> Csak a pénzügyileg frissített készlettranzakciók archiválhatók a kiválasztott lezárt főkönyvi időszakban. Az archiváláshoz a pénzügyileg frissített kimenő készlettranzakciók kiadási állapotának *Eladva* értéknek kell lennie, a bejövő készlettranzakcióknak *Beszerzett* bevételezési állapotúnak kell lennie.

A készlettranzakciók archiválásakor minden kapcsolódó tranzakció az `InventTransArchive` táblába kerül. A készletkiadási tranzakciók és a készletbevételezési tranzakciók archiválása külön történik, a cikkazonosító (`itemId`) és a készletdimenzió-azonosító (`inventDimId`) kombinációja alapján, és a rendszer összesített kiadási és összesített bevételezési tranzakciók közé sorolja őket.

Ha egy `itemId` és `inventDimId` kombináció csak egy bevételezési vagy kibocsátási tranzakciót tartalmaz, a tranzakció nem lesz archiválva.

## <a name="turn-on-the-feature-in-your-system"></a>A funkció bekapcsolása a rendszerben

Ha a rendszer még nem tartalmazza az ebben a cikkben ismertetett funkciókat, [használja a Funkciókezelés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) funkciót, *és kapcsolja be a Készlettranzakciók archívum funkcióját*. Ne feledje, hogy ezt a funkciót engedélyezés után nem lehet letiltani.

## <a name="things-to-consider-before-you-archive-inventory-transactions"></a>Megfontolandó szempontok a készlettranzakciók archiválását megelőzően

A készlettranzakciók archiválását megelőzően figyelembe kell vennie a következő üzleti eseteket, mivel azok hatással lesznek a műveletre:

- Amikor a kapcsolódó dokumentumokból – például beszerzésirendelés-sorokból – könyvvizsgálati készlettranzakciókat végez, azok archiváltként jelennek meg. Az archivált tranzakciók ellenőrzéséhez lépjen a **Készletkezelés \> Időszakos feladatok \> Adattisztítás \> Készlettranzakciók archívuma** pontra.
- Archivált időszakok esetén nem érvénytelen lehet készletzárást visszavonni. Készletzárás visszavonása előtt az adott időszakra vonatkozóan sztornírozni kell a készlettranzakció-archívumot.
- Archivált időszakokra nem lehet elszámolóárra való átalakítást végezni. Elszámolóárra való átalakítás előtt az adott időszakra vonatkozóan sztornírozni kell a készlettranzakció-archívumot.
- A készlettranzakciókból származó készletjelentéseket befolyásolja a készlettranzakciók archiválása. Ezek a jelentések tartalmazzák a készletkorosítási jelentést és a készletérték-jelentéseket.
- A készlet-előrejelzésekre hatással lehet, ha az archivált időszakok időhorizontja alatt futnak.

## <a name="prerequisites"></a>Előfeltételek

A készlettranzakciók csak olyan időszakokban archiválhatók, ahol teljesülnek a következő feltételek:

- A főkönyvi időszakot le kell zárni.
- A készletzárást az archívum záró dátumán vagy azt követően kell futtatni.
- Az időszaknak legalább egy évvel az archívum időszakának kezdési dátuma előtt kell lennie.
- Nem létezhetnek meglévő készlet-újraszámítások.

## <a name="archive-inventory-transactions"></a>Készlettranzakciók archiválása

Készlettranzakciók archiválásához kövesse az alábbi lépéseket.

1. Lépjen a **Készletkezelés** \> **Időszakos feladatok** \> **Adattisztítás** \> **Készlettranzakció archívuma** pontra.

    Megjelenik a **Készlettranzakciók archívuma** oldal, és megjeleníti az archivált folyamatrekordok listáját.

    ![Készlettranzakciók archívumának oldala.](media/archive-inventory-empty.png "Készlettranzakciók archívumának oldala")

1. A műveletpanelen válassza ki a **Készlettranzakciók archívumát** készlettranzakció-archívum létrehozásához.
1. A **Készlettranzakciók archívuma** párbeszédpanel **Paraméterek** gyorslapján állítsa be a következő mezőket:

    - **Kezdési dátum lezárt főkönyvi időszakban** – Válassza ki a legkorábbi tranzakció dátumát, amit szerepeltetni szeretne az archívumban.
    - **Záró dátum lezárt főkönyvi időszakban** – Válassza ki a legkésőbbi tranzakció dátumát, amit szerepeltetni szeretne az archívumban.

    ![Készlettranzakciók archívumának párbeszédablaka.](media/archive-inventory-dates.png "Készlettranzakciók archívumának párbeszédablaka")

    > [!NOTE]
    > Csak az [előfeltételeknek](#prerequisites) megfelelő időszakok választhatók ki.

1. A **Futtatás a háttérben** gyorslapon az igényeinek megfelelően állítsa be a kötegelt feldolgozás részleteit. Kövesse a Microsoft Dynamics 365 Supply Chain Management kötegelt feladatokkal kapcsolatos általános lépéseit.
1. Válassza ki az **OK** lehetőséget.
1. Egy üzenet jelenik meg, amely arra kéri, hogy erősítse meg a folytatást. Olvassa el alaposan az üzenetet, majd kattintson az **Igen** gombra, ha folytatni szeretné.

    Egy üzenet jelenik meg, amely jelzi, hogy a készlettranzakciók archiválási feladata felkerült a köteg feldolgozási sorára. A feladat elindul a kijelölt időszak készlettranzakcióinak archiválására.

## <a name="view-archived-inventory-transactions"></a>Archivált készlettranzakciók megtekintése

A **Készlettranzakciók archívuma** oldal a teljes archiválási előzményeket mutatja. A rács minden sorában olyan adatok láthatók, mint például az archívum létrehozási dátuma, az a felhasználó, aki létrehozta, valamint annak állapota.

![Készlettranzakciók archívumának oldalán található archiválási előzmények.](media/archive-inventory-full.png "Készlettranzakciók archívumának oldalán található archiválási előzmények")

Az oldal tetején lévő legördülő listából válasszon a következő értékek közül a rácsban látható archívum szűréséhez:

- **Aktív** – Csak az aktív archívumok megjelenítése, a sztornírozott archívumok nem.
- **Összes** – Minden archívum megjelenítése, aktív és sztornírozva is.

A rács minden egyes archívumához a következő információk biztosítanak:

- **Aktív** – A bejelölés jelzi, hogy az archívum aktív.
- **Kezdési dátum** – Az archívumba kerülő legrégebbi tranzakció dátuma.
- **Záró dátum** – Az archívumba kerülő legújabb tranzakció dátuma.
- **Ütemezte** – Az archívumot létrehozó felhasználói fiók.
- **Végrehajtva** – Az archívum létrehozásának dátuma.
- **Sztornírozás** – A jelölés azt jelzi, hogy az archívum sztornózva lett.
- **Aktuális frissítés leállítása** - A jelölés azt jelzi, hogy az archívum folyamatban van, de szünetel.
- **Állapot** – Az archívum feldolgozási állapota. A lehetséges értékek: *Várakozás*, *Folyamatban* és *Kész*.

A rács feletti eszköztár a következő gombokat tartalmazza, amelyek a kiválasztott archívummal való munkára használhatók:

- **Archivált tranzakciók** – a kijelölt archívum részletes megjelenítése. A megjelenő **Archivált tranzakciók** oldal az archívum összes tranzakcióját megjeleníti.

    ![Archivált tranzakciók oldala.](media/archive-inventory-transactions.png "Archivált tranzakciók oldala")

    Ha az **Archivált tranzakciók** lapon egy adott tranzakcióval kapcsolatban további információkat is meg kell jeleníteni, jelölje ki azt a rácsban, majd a műveleti ablaktáblán válassza ki az **Archivált tranzakció részletei** elemet. A megjelenő **Archivált tranzakció részletei** oldalon olyan adatok jelennek meg, mint a főkönyvi elszámolás, a kapcsolódó részfőkönyv hivatkozásai és a pénzügyi dimenziók.

- **Az archiválás szüneteltetése** – A jelenleg feldolgozás alatt álló kijelölt archívum szüneteltetése. A szünet csak az archiválási feladat létrehozása után lép életbe. Emiatt előfordulhat egy kis késés a szünet hatályba lépése előtt. Ha egy archívum szünetel, az **Aktuális frissítés leállítása** mezőben megjelenik egy pipa.
- **Az archiválás folytatása** – A jelenleg szünetelő kijelölt archívum feldolgozásának folytatása.
- **Sztornírozás** – A kijelölt archívum sztornírozása. Az archívum csak akkor sztornírozható, ha az **Állapot** mező beállítása *Kész*. Ha egy archívum sztornírozva van, a **Sztornírozás** mezőben megjelenik egy pipa.

## <a name="extend-your-code-to-support-custom-fields"></a>A kód kiterjesztése az egyéni mezők támogatásához

Ha a `InventTrans` tábla egy vagy több egyéni mezőt tartalmaz, akkor a névtől függően lehet, hogy ki kell bővítenie a kódot, hogy támogassák őket.

- Ha a tábla egyéni mezőinek `InventTrans``InventtransArchive` ugyanazok a mezőnevek vannak, mint a táblában, ez azt jelenti, hogy 1:1 megfeleltetve vannak. Ezért az egyéni mezőket be lehet tenni a `InventoryArchiveFields` tábla mezőcsoportba `inventTrans`.
- Ha a táblában található `InventTrans``InventtransArchive` egyéni mezőnevek nem egyeznek meg a táblában szereplő mezőnevekkel, akkor a leképezésükhöz kódokat kell hozzáadnia. Ha például `InventTrans.CreatedDateTime` rendszermezőt hívott, akkor más néven (`InventTransArchive` például) `InventtransArchive.InventTransCreatedDateTime``InventTransArchiveProcessTask` kell létrehoznia egy mezőt a `InventTransArchiveSqlStatementHelper` táblában, és kiterjesztéseket kell hozzáadnia az és az osztályokhoz, amint azt a következő mintakód mutatja.

Az alábbi mintakód egy példát mutat be arra, hogyan lehet hozzáadni a szükséges kiterjesztést az osztályhoz `InventTransArchiveProcessTask`.

```xpp
[ExtensionOf(classStr(InventTransArchiveProcessTask))]
Final class InventTransArchiveProcessTask_Extension
{

    protected void addInventTransFields(SysDaSelection _selectionObject)
    {
        _selectionObject.add(fieldStr(InventTrans, ModifiedBy))
            .add(fieldStr(InventTrans, CreatedBy)).add(fieldStr(InventTrans, CreatedDateTime));

        next addInventTransFields(_selectionObject);
    }


    protected void addInventTransArchiveFields(SysDaSelection _selectionObject)
    {
        _selectionObject.add(fieldStr(InventTransArchive, InventTransModifiedBy))
            .add(fieldStr(InventTransArchive, InventTransCreatedBy)).add(fieldStr(InventTransArchive, InventTransCreatedDateTime));

        next addInventTransArchiveFields(_selectionObject);
    }
}
```

Az alábbi mintakód egy példát mutat be arra, hogyan lehet hozzáadni a szükséges kiterjesztést az osztályhoz `InventTransArchiveSqlStatementHelper`.

```xpp
[ExtensionOf(classStr(InventTransArchiveSqlStatementHelper))]
final class InventTransArchiveSqlStatementHelper_Extension
{
    private str     inventTransModifiedBy;  
    private str     inventTransCreatedBy;
    private str     inventTransCreatedDateTime;

    protected void initialize()
    {
        next initialize();
        inventTransModifiedBy = new SysDictField(tablenum(InventTrans), fieldNum(InventTrans, ModifiedBy)).name(DbBackend::Sql);
        inventTransCreatedDateTime = new SysDictField(tablenum(InventTrans), fieldNum(InventTrans, CreatedDateTime)).name(DbBackend::Sql);
        inventTransCreatedBy = new SysDictField(tablenum(InventTrans), fieldNum(InventTrans, CreatedBy)).name(DbBackend::Sql);
    }

    protected str buildInventTransArchiveSelectionFieldsStatement()
    {
        str     ret;

        ret = next buildInventTransArchiveSelectionFieldsStatement();
        
        if (inventTransModifiedBy)
        {
            ret += ',';
            ret += strFmt('%1',  new SysDictField(tablenum(InventTransArchive), fieldNum(InventTransArchive, InventTransModifiedBy)).name(DbBackend::Sql));
        }

        if (inventTransCreatedBy)
        {
            ret += ',';
            ret += strFmt('%1',  new SysDictField(tablenum(InventTransArchive), fieldNum(InventTransArchive, InventTransCreatedBy)).name(DbBackend::Sql));
        }

        if (inventTransCreatedDateTime)
        {
            ret += ',';
            ret += strFmt('%1',  new SysDictField(tablenum(InventTransArchive), fieldNum(InventTransArchive, InventTransCreatedDateTime)).name(DbBackend::Sql));
        }

        return ret;
    }

    protected str buildInventTransTargetFieldsStatement()
    {
        str     ret;

        ret = next buildInventTransTargetFieldsStatement();

        if (inventTransModifiedBy)
        {
            ret += ',';
            ret += strFmt('%1', inventTransModifiedBy);
        }

        if (inventTransCreatedBy)
        {
            ret += ',';
            ret += strFmt('%1', inventTransCreatedBy);
        }

        if (inventTransCreatedDateTime)
        {
            ret += ',';
            ret += strFmt('%1', inventTransCreatedDateTime);
        }

        return ret;
    }
}
```
