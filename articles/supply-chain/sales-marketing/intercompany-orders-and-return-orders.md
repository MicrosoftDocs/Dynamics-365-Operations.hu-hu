---
title: Vállalatközi rendelések és visszárurendelések
description: Ez a cikk bemutatja a vállalatközi rendeléseket és visszárurendeléseket.
author: Henrikan
ms.date: 09/01/2021
ms.topic: article
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 65d0dc6049969ff7d8f84ca4eb3baf486ddad660
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8859027"
---
# <a name="intercompany-orders-and-return-orders"></a>Vállalatközi rendelések és visszárurendelések

[!include [banner](../../includes/banner.md)]

Ez a témakör leírja, hogyan lehet vállalatközi beszerzési rendeléseket, értékesítési rendeléseket, visszárurendeléseket, beszerzési megállapodásokat és értékesítési szerződéseket létrehozni és frissíteni.

## <a name="about-intercompany-orders"></a>A vállalatközi rendelések

Vállalatközi értékesítési rendelések létrehozásakor a Microsoft Dynamics 365 Supply Chain Management automatikusan létrehozza a megfelelő beszerzési rendelést. Hasonló módon a vállalatközi beszerzési rendelések létrehozása kiváltja a megfelelő vállalatközi értékesítési rendelések automatikus létrehozását is.

Mindez igaz a kétszereplős rendelésekre (a két kapcsolatban lévő vállalat közötti tranzakciókra) és a legtöbb háromszereplős esetre is (ahol a vállalatközi tranzakció egy külső vevőnek készült értékesítési rendelésből származik).

## <a name="intercompany-order-example"></a>Vállalatközi rendelés – példa

Van két vállalat, amely kapcsolatban áll egymással. Az A vállalat egy értékesítő leányvállalat, a B vállalat pedig egy elosztóegység. A következő helyzetekben automatikusan létrejönnek a vállalatközi értékesítési rendelések és beszerzési rendelések:

- Ha az A vállalat létrehoz egy beszerzési rendelést, amelynek szállítója a B vállalat, akkor a B vállalatban automatikusan létrejön egy vállalatközi értékesítési rendelés. A kétszereplős rendelési lánc egy beszerzési rendelésből áll az A vállalatban, és egy vállalatközi értékesítési rendelésből a B vállalatban.
- Ha a B vállalat létrehoz egy értékesítési rendelést, amelynek vevője az A vállalat, akkor az A vállalatban automatikusan létrejön egy vállalatközi beszerzési rendelés. A kétszereplős rendelési lánc egy értékesítési rendelésből áll a B vállalatban, és egy vállalatközi beszerzési rendelésből az A vállalatban.
- Ha az A vállalat először egy külső vevő számára hoz létre értékesítési rendelést, akkor automatikusan létrehozható egy beszerzési rendelés az A vállalatban, amely ezután kiváltja egy vállalatközi értékesítési rendelés automatikus létrehozását a B vállalatban. A háromszereplős rendelési lánc egy értékesítési rendelésből, valamint egy beszerzési rendelésből áll az A vállalatban, és egy értékesítési rendelésből a B vállalatban.

## <a name="about-intercompany-return-orders"></a>A vállalatközi visszárurendelések

A vállalatközi tételeket érintő visszáru lényegében ugyanúgy küldhető vissza, mint a normál visszáru. A vállalatközi tételeknél azonban a külső vevőtől származó visszárurendelés létrehoz egy vállalatközi beszerzési rendelést. Ez azután automatikusan egy vállalatközi értékesítési visszárurendelés létrehozásához vezet. A vállalatközi tételeket a külső vevő visszárurendelése nélkül is visszaadhatja.

A vállalatközi visszárurendelések a rendes visszárurendelésekhez hasonlóan a **Visszárurendelés létrehozása** oldalról kezdeményezhetők.

A Microsoft Dynamics 365 Supply Chain Management alkalmazásban a vállalatközi értékesítési és beszerzési szerződéseket a rendszer automatikusan frissíti, hogy megjelenjenek bennük a visszárus cikkek. Az adott cikk értékesítési vagy beszerzési szerződésbeli kötelezettségvállalása automatikusan kiigazításra kerül, hogy tükrözze a visszaküldött cikk mennyiségét vagy összegét.

## <a name="intercompany-return-order-example"></a>Vállalatközi visszárurendelés – példa

A vállalat létrehoz egy, a vállalatközi cikk beszerzési szerződéséhez kapcsolt beszerzési rendelést. B vállalatban automatikusan létrejön egy vállalatközi értékesítési rendelés, ami az érintett értékesítési szerződéshez kapcsolódik. A beszerzési szerződés és az értékesítési szerződés vállalatközi megállapodásokként viszonyulnak egymáshoz.

A vállalat visszaküldi a vállalatközi cikket B vállalatnak. B vállalat létrehoz hozzá egy visszárurendelést, amihez A vállalatban automatikusan létrejön egy beszerzési visszárurendelés. Az eredeti rendeléshez kapcsolüdü beszerzési szerződés és értékesítési szerződés kötelezettségvállalásait a rendszer automatikusan kiigazítja, hogy tükrözzék a mennyiségben vagy az összegben bekövetkezett változást.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
