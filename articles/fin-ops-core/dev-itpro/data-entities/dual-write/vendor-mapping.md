---
title: Integrált szállítói alapadat
description: Ez a témakör leírja a szállítók adatintegrációját a pénzügyi és műveleti alkalmazások és a Dataverse.
author: RamaKrishnamoorthy
ms.date: 07/15/2019
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: a2c32ef546a5bc74e090591c0ac9d51529299041
ms.sourcegitcommit: 6781fc47606b266873385b901c302819ab211b82
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/02/2022
ms.locfileid: "9112195"
---
# <a name="integrated-vendor-master"></a>Integrált szállítói alapadat

[!include [banner](../../includes/banner.md)]



A *szállító* kifejezés egy szállító szervezetre vagy egy olyan kizárólagos tulajdonosra vonatkozik, aki árukat vagy szolgáltatásokat nyújt egy vállalkozásnak. A *szállító* fogalmat ugyan kiterjedten használják a Microsoft Dynamics 365 Supply Chain Management alkalmazásban, a szállító fogalma nem létezik az ügyfélkapcsolati alkalmazásokban. A szállítói adatok tárolására azonban lehetősége van az **Ügyfél/kapcsolattartó** tábla túlterhelésével. A integrált szállító alapadat az ügyfélkapcsolati alkalmazásokban explicit szállítói fogalmat vezet be. Használhatja az új szállító megoldást vagy a szállítói adatokat a **Partner/kapcsolattartó** táblában is tárolhatja. A kettős írás mindkét megközelítést támogatja.

Mindkét módszernél a szállítói adatok integrálva lesznek a Dynamics 365 Supply Chain Management, a Dynamics 365 Sales, a Dynamics 365 Field Service és Power Apps portálok között. A Supply Chain Management alkalmazásban az adatok olyan munkafolyamatokhoz érhetők el, mint például a beszerzési igénylések és a beszerzési rendelések.

## <a name="vendor-data-flow"></a>Szállítói adatok áramlása

Használhatja az új szállító megoldást ha a szállítói adatokat nem szeretné a **Partner/kapcsolattartó** táblában tárolni a Dataverse megoldásban.

![Szállítói adatok áramlása.](media/dual-write-vendor-data-flow.png)

Ha a szállítói adatokat továbbra is a **Partner/kapcsolattartó** táblában szeretné tárolni, használhatja a kibővített szállítói megoldást. A kiterjesztett szállítói megoldás használatához konfigurálnia kell a szállítói munkafolyamatokat a kettős írás megoldási csomagjában. További információ: [Váltás a szállítói arculatok között](vendor-switch.md).

![Bővített szállítói adatok áramlása.](media/dual-write-vendor-detail.jpg)

> [!TIP]
> Ha önkiszolgáló áruházhoz Power Apps portálokat használ, akkor a szállító adatai közvetlenül a pénzügyi és műveleti alkalmazásokba is átfolyhat.

## <a name="templates"></a>Sablonok

A szállítói adatok között a szállító minden részlete (például a szállítói csoport, a címek, a kapcsolatfelvételi adatok, a fizetési és a számlázási profil) szerepel. Ahogy az alábbi táblázatban látható, az táblaleképezések gyűjteménye együttműködik a szállítói adatokkal végzett interakciók során.

Finance and Operations alkalmazások | Customer Engagement alkalmazások     | Leírás
----------------------------|-----------------------------|------------
[CDS névjegyek V2](mapping-reference.md#115) | kapcsolattartók | Ez a sablon a vevők és a szállítók összes elsődleges, másodlagos és harmadlagos kapcsolattartási adatát szinkronizálja.
[Névutótagok](mapping-reference.md#155) | msdyn_nameaffixes | Ez a sablon szinkronizálja a vevők és szállítók névutótagjaira vonatkozó hivatkozási adatokat.
[Fizetési nap sorai, CDS V2](mapping-reference.md#157) | msdyn_paymentdaylines | Ez a sablon szinkronizálja a vevők és szállítók fizetési nap soraira vonatkozó hivatkozási adatait.
[Fizetési napok, CDS](mapping-reference.md#158) | msdyn_paymentdays | Ez a sablon szinkronizálja a vevők és szállítók fizetési napokra vonatkozó hivatkozási adatait.
[Kifizetési lista sorai](mapping-reference.md#159) | msdyn_paymentschedulelines | Szinkronizálja a vevők és szállítók fizetési ütemezés soraira vonatkozó hivatkozási adatait.
[Fizetési ütemezés](mapping-reference.md#160) | msdyn_paymentschedules | Ez a sablon szinkronizálja a vevők és szállítók fizetési ütemezésre vonatkozó hivatkozási adatait.
[Fizetési feltételek](mapping-reference.md#161) | msdyn_paymentterms | Ez a sablon szinkronizálja a vevők és szállítók fizetési feltételekre vonatkozó hivatkozási adatait.
[Szállítók V2](mapping-reference.md#202) | msdyn_vendors | Azok a vállalatok, amelyek egyéni megoldást használnak a Dataverse szállítóknak, a pénzügyek és az üzemeltetés alkalmazásintegrációs alkalmazások integrálása miatt ki használják a most bevezetett, egyedi szállítói koncepciót.
[Szállítói csoportok](mapping-reference.md#200) | msdyn_vendorgroups | Ez a sablon szinkronizálja a szállítói csoport adatait.
[Szállítói fizetési mód](mapping-reference.md#201) | msdyn_vendorpaymentmethods | Ez a sablon szinkronizálja a szállító fizetési módra vonatkozó adatait.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]

