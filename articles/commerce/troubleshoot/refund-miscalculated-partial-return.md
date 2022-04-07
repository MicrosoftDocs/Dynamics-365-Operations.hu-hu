---
title: A visszatéríthető költségek a visszaküldött mennyiség alapján vegyesen vannak elszámítva.
description: Ez a témakör olyan hibaelhárítási útmutatást tartalmaz, amelyek segítséget nyújtanak abban az esetben, ha a pénztárosok helytelen visszatérítési költségeket látnak a pénztárnál a visszaküldött cikkek mennyiségére vonatkozóan.
author: gvrmohanreddy
ms.date: 03/24/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: c8ecaa0cb73d06ac66b57cce815264e841a2259b
ms.sourcegitcommit: 94ebdaae6dc996b205ac78ed546e38f91f4f46ed
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/28/2022
ms.locfileid: "8489725"
---
# <a name="refundable-charges-are-miscalculated-based-on-the-quantity-returned"></a>A visszatéríthető költségek a visszaküldött mennyiség alapján vegyesen vannak elszámítva.

[!include [banner](../../includes/banner.md)]

Ez a témakör olyan hibaelhárítási útmutatást tartalmaz, amelyek segítséget nyújtanak abban az esetben, ha a pénztárosok helytelen visszatérítési költségeket látnak a pénztárnál a visszaküldött cikkek mennyiségére vonatkozóan.

## <a name="description"></a>Leírás

A vevő a cikkek egy részmennyiségét visszaadja, amit egy olyan értékesítési rendeléshez vásároltak, amelynél a sor szintű visszatéríthető költségek vannak. A POS azonban nem jeleníti meg a részleges visszatérítést, hanem minden költséget visszatéríthetőként megjelenít.

Például egy vevő cikkenként öt cikket vásárol $5 összes költségének $25. A vevő ezt követően visszaadja az öt cikkből a háromat. A pénztáros azonban $25 visszatéríthető költségként jelenik meg a POS-terminálon, nem pedig $15 visszaküldött cikk várható visszatéríthető árát.

## <a name="resolution"></a>Megoldás

### <a name="turn-on-the-enable-refunding-charges-based-on-the-refunded-quantity-feature"></a>A visszatérítési költségek engedélyezése a visszatérített mennyiség funkció alapján

Microsoft Dynamics 365 Commerce A 10.0.26-os **verziónál** a Visszatérítési költségek engedélyezése a visszatérítési mennyiség funkcióval lehetővé teszi, hogy a sor szintű visszatéríthető költségeket a visszaküldött cikkek mennyisége alapján számítsa ki a program.

Ha engedélyezni szeretné **a visszatérítési költségek visszatérítését a Commerce Headquarters Visszatérítési mennyiség** funkciója alapján, kövesse ezeket a lépéseket.

1. Nyissa meg **a Szolgáltatáskezelés munkaterületét** (**Rendszergazda – \> Munkaterületek \> funkciókezelés**).
1. Az elérhető funkciók listájában keresse **meg és válassza ki a Visszatérítési költségek engedélyezése a visszatérítési mennyiség funkció** alapján lehetőséget.
1. A jobb oldali ablakban válassza az Engedélyezés **lehetőséget**.
