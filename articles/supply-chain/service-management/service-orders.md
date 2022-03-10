---
title: Szervizrendelések
description: Ez a témakör a szolgáltatási szerződések használatával kapcsolatban nyújt áttekintést.
author: kamaybac
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8dc88d445e1331e1532cb3b7385cda39c4f22e80
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/29/2021
ms.locfileid: "7566119"
---
# <a name="service-orders"></a>Szervizrendelések

[!include [banner](../includes/banner.md)]

A szervizrendelések egy szerviztechnikus látogatását jelzik a vevő telephelyén, egy adott napon. Minden szervizrendelés egy vagy több sorból áll. A szolgáltatásrendelési sorok a szerviztechnikus által elvégzendő munkaórákat, valamint kapcsolódó cikkeket, költségeket és díjakat tartalmaznak.

A szervizrendeléssorhoz feladatokat és tárgyakat csatolhat. Ezután csoportosíthatja a szervizrendelési sorokat feladat vagy objektum szerint. A szervizrendeléssorokhoz a készletben felsorolt cikkek is csatolhatók.

## <a name="create-service-orders"></a>Szervizrendelések létrehozása

A szervizrendelések a szolgáltatási szerződés, valamint a szerződés sorai alapján hozhatók létre. Ugyanakkor csak a megállapodásban megadott időszakban hozhat létre a szolgáltatási szerződéshez kapcsolódó szervizrendeléseket. Ha például egy szolgáltatási szerződés érvényes a 2011-es naptári évben, létrehozhat a szerződéshez kapcsolódó szervizrendeléseket 2011. január 1. és 2011. december 31. között.

Szervizrendeléseket egyesével is készíthet úgy, hogy nem rendeli hozzá őket szolgáltatási szerződésekhez. Ezek a szervizrendelések nem tervezett vagy egyszeri szervizlátogatások kezelésére használhatók. Például március hónapban az egyik vevő úgy dönt, hogy a szolgáltatási szerződésben meghatározottakon felül két további gépén is elvégezteti a szervizt. Ehhez a feladathoz szervizrendeléseket készít, hogy nem rendeli hozzá őket szolgáltatási szerződésekhez.


> [!NOTE]
> Szervizrendelések létrehozásához, amelyek nem kapcsolódnak egy szolgáltatási szerződéshez, be kell jelölnie az **Engedélyezés szolgáltatási szerződés nélkül** jelölőnégyzetet a **Szolgáltatás kezelésének paraméterei** oldalon.

### <a name="scenario"></a>Forgatókönyv

A következő helyzet szintén olyan, amikor célszerű létrehozni egy szervizrendelést, amelyik nincs egy szolgáltatási szerződéshez rendelve.

A vállalat diszpécsere sürgős szervizhívást kap egy lifthez. Nincs idő szolgáltatási szerződés és egy projekt létrehozására a szolgáltatáshoz. Emiatt a diszpécser közvetlenül hoz létre egy szervizrendelést a **Szervizrendelések** oldalon, a szervizrendelést csatolja egy meglévő projekthez, és szervizrendelési sorokat hoz létre. Az operátor emellett létrehoz egy feladat- és tárgykapcsolatot egy meglévő szervizrendeléssel, hogy olyan munkát rögzítsen, ami nem kapcsolódik a szolgáltatási szerződéshez. További tudnivalókért lásd: [Szervizrendelések létrehozása manuálisan](create-service-orders-manually.md) és [Szervizfeladat-kapcsolatok létrehozása](create-service-task-relations.md).

## <a name="monitor-the-progress-of-service-orders"></a>A szervizrendelés előrehaladásának megfigyelése

Egy értékesítési rendelésen nyomon követéséhez a különböző csapatokon és munkafolyamatokon keresztül, beállíthat fokozatokat és okkódokat a szervizrendelésekhez. A következő műveleteket határozhatja meg az egyes fokozatokra vonatkozóan: További tájékoztatásért lásd: [Okkódok létrehozása](create-reason-codes.md).

### <a name="example"></a>Példa

Szervizrendelést a diszpécser jóváhagyja. A diszpécser frissíti a szervizrendelés fokozatát és megad egy megfelelő okkódot. Az okkód szerint a szervizrendelés át lett adva a technikusnak. A szerviztechnikus a vevő telephelyére megy, és elvégzi a szolgáltatást.

## <a name="specify-item-requirements-for-service-orders"></a>Cikkszükséglet megadása a szervizrendelésekhez

Megadhatja, hogy mely készletcikkek szükségesek a szervizrendelésekhez. A szervizrendelésnek azonban projekthez társítva kell lennie. Szervizrendelések cikkszükségleteinek feldolgozása projekten keresztül történik. 

### <a name="example"></a>Példa

A szolgáltatási szerződésből létrehozott szervizrendeléseket ezután feldolgozza a diszpécser. Az első szervizrendelésen észreveszi, hogy a technikusnak fontos cserealkatrészre van szüksége, ami nincs az aktuális készletben. Ezért a diszépcser létrehoz egy cikkszükségletet közvetlenül a szervizrendelésből, ami a cserealkatrészre vonatkozik.

## <a name="move-and-post-lines"></a>Sorok áthelyezése és feladása

A szerviztechnikus visszatér a kiszállásról, és módosítja és frissíti a szervizrendelés sorait. A szervizlátogatáskor a technikus elvégzett egy olyan munkát, amit eredetileg csak a következő látogatásra ütemeztek. Ezért a technikus következő szervizlátogatás sorait áthelyezi a jelenlegibe. A technikus ezután feladja a szervizrendelést. További információkkal kapcsolatban lásd: [Szervizrendeléssorok áthelyezése](move-service-order-lines.md).

## <a name="cancel-service-orders"></a>Szervizrendelések érvénytelenítése

A január hónapra generált szervizrendelések egyike lejár, mivel a munkát törölték. A diszpécser tehát törli a szervizrendelést. További információkkal kapcsolatban lásd: [Szervizrendelések törlése](cancel-service-orders.md).

## <a name="post-from-projects"></a>Feladás projektekből

A hetek utolsó napján a diszpécsernek minden projekthez csatolt szervizrendelést fel kell adnia. Emiatt a diszpécser megkeresi a megfelelő projektet a **Projektek** oldal, és feladja a szervizrendeléseket, amelyek már befejeződtek. További információkkal kapcsolatban lásd: [Szervizrendelések feladása (osztályképernyő)](https://technet.microsoft.com/library/aa574685\(v=ax.60\)).

## <a name="delete-service-orders"></a>Szervizrendelések törlése

Az év második felében az egyik vevő úgy dönt, hogy a szervizlátogatások túl ritkák. Ezért a szolgáltatási szerződés alapján egy új, sűrűbb rendeléssorozatot kell létrehoznia a hátralévő időre. A meglévő szervizrendeléseket törölni kell, majd ezután létrehozhatók az új szervizrendelések. További információkkal kapcsolatban lásd: [Szervizrendelések törlése](delete-service-orders.md).

## <a name="see-also"></a>Lásd még

[Szervizrendelések (képernyő)](https://technet.microsoft.com/library/aa554361\(v=ax.60\))

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]