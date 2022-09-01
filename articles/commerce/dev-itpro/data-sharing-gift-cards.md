---
title: Vállalatközi adatmegosztás ajándékutalványok számára
description: Ez a témakör azt ismerteti, hogyan Microsoft Dynamics 365 Commerce kell konfigurálni a Dynamics 365 Pénzügyi adatmegosztási funkció használatát az adatterületek között az ajándékutalvány-adatok szinkronizálására.
author: BrianShook
ms.date: 08/26/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.custom: 141393
ms.assetid: e23e944c-15de-459d-bcc5-ea03615ebf4c
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2022-06-20
ms.openlocfilehash: b56890b546c3cd74b75cf447e62495733ea8d288
ms.sourcegitcommit: 09d4805aea6d148de47c8ca38d8244bbce9786ce
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387372"
---
# <a name="cross-company-data-sharing-for-gift-cards"></a>Vállalatközi adatmegosztás ajándékutalványok számára

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

Ez a cikk azt ismerteti, hogyan kell konfigurálni úgy, Microsoft Dynamics 365 Commerce hogy a Dynamics 365 Pénzügyi adatmegosztási funkcióival szinkronizálja az ajándékutalványok adatait. Az adatrekord-megosztási funkciók ezután felhasználhatók az adatok vállalatközi megosztására két adatterület között. Ily módon a Commerce belső ajándékutalvány-tábla két vállalati entitás között oszthatja meg az adatokat. A Dynamics 365 Pénzügy vállalatközi adatmegosztásával kapcsolatos további tudnivalókat lásd a [Több vállalatot átvesző adatmegosztás című témakörben](/dynamics365/fin-ops-core/dev-itpro/sysadmin/cross-company-data-sharing).

## <a name="key-terms"></a>Kulcsfogalmak

| Időszak | Leírás |
|---|---|
| Vállalat | A jogi személy a Dynamics 365 Pénzügyi környezetben. |
| Ajándékutalvány | A Dynamics 365 Commerce belső ajándékutalvány-termék |

## <a name="prerequisites"></a>Előfeltételek

A felhasználóknak a vállalatközi [adatmegosztásban leírtak szerint konfigurálniuk kell a környezetüket](/dynamics365/fin-ops-core/dev-itpro/sysadmin/cross-company-data-sharing).

**A RetailGiftCardTable** táblában **a DataSharingType** **mezőt** Duplikáltra kell állítani, hogy az ajándékutalvány-tábla számára lehetővé tegye az ismétlődő rekordmegosztást (DRS). A további tudnivalókat lásd [a fejlesztők vállalatközi adatmegosztásával kapcsolatban](/dynamics365/fin-ops-core/dev-itpro/sysadmin/drs-srs-dev).

## <a name="configure-cross-company-data-sharing-for-gift-cards"></a>Vállalatközi adatmegosztás konfigurálása ajándékutalványok számára

A következő lépésekkel konfigurálhatja az ajándékutalványok vállalatközi adatmegosztását.

1. A Commerce Headquarters rendszerben kattintson **a Rendszerfelügyelet \>\> beállítása vállalatközi adatmegosztás konfigurálása webhelyre**.
1. A munkaablakban az Új **gombra kattintva** adjon hozzá egy adatmegosztási rekordot.
1. A Név **mezőbe** írja be az adatmegosztási rekord nevét (például **ajándékutalványok**).
1. A Megoszt kívánt **táblák és mezők szakaszban** válassza a Hozzáadás **lehetőséget**.
1. Az Új tábla **megosztása párbeszédpanel** **Táblanév** mezőjében adja **meg a RETAILGIFTCARDTABLE** (a kiskereskedelmi ajándékutalványok tábláját). A **Táblacímke** mezőben automatikusan ajándékutalvány-táblát **kell beállítani**.
1. Győződjön meg róla, hogy **az Adatok mentése vállalatonként**, **egyedi indexe** van, **és** a Még nincs közös jelölőnégyzet bejelölve. A jelölőnégyzetek bejelölése az adatmegosztási funkciókkal kapcsolatos érvényesítést indítja el.
1. Válassza a **Táblázat beszúrása** lehetőséget. Az **ajándékutalvány-tábla (RetailGiftCardTable)** rekordnak most meg kell jelenni a **megosztható táblák és mezők alatt**. Jelölje ki a tetves szimbólumot a tábla összes olyan mezőjének megtekintéséhez, amely automatikusan a táblához van társítva megosztásra.
1. Az ezekben **a táblákban lévő** rekordokat megválasztó Vállalatok szakaszban válassza a Hozzáadás lehetőséget, ha olyan vállalatot szeretne hozzáadni, **amellyel** megosztják az adatokat.
1. A Vállalat alatti **sorban** válasszon ki egy vállalatot a legördülő listából.
1. A Név **mezőbe** írja be a vállalat nevét.
1. További vállalati sorok hozzáadásához ismételje meg a 8–10. lépést.
1. Amikor befejezte a vállalati sorok hozzáadását, válassza az Engedélyezés lehetőséget a **munkaablakban**.
1. Megjelenik egy figyelmeztető üzenet, amely a következőt állítja be: "Ezt a műveletet csak munkaidőben javasolt végrehajtani. A házirendben lévő táblák minden egyidejű tranzakciós művelete sikertelen lesz. Folytatja?" Válassza az **Igen lehetőséget** a megállapodáshoz.
1. Egy figyelmeztető üzenet jelenik meg, hogy "Szeretné most átmásolni az összes létező adatot az összes megosztott vállalatra?" Válassza az **Igen lehetőséget** a megállapodáshoz.

Ha elfogadja mindkét üzenet küldését, a táblák elkezdik másolni az adatokat a konfigurált vállalatok között. Az egyik vállalat ajándékutalványán előforduló egyenlegek ezt követően láthatók lesznek a másik vállalat számára.

## <a name="additional-resources"></a>További erőforrások

[Kifizetésekkel kapcsolatos GYIK](payments-retail.md)

[Pénztármodul](../add-checkout-module.md)

[Fizetési modul](../payment-module.md)
