---
title: A Microsoft Power Apps portál használata a Fél adatmodelljével
description: Ez a témakör a Microsoft Power Apps portálok webszerepkörök változásait írja le a fél adatmodell megjelenése miatt a kettős írásban.
author: RamaKrishnamoorthy
ms.date: 03/22/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2021-03-22
ms.openlocfilehash: eee4076c5f16d9655bde3ee4943f79732598199f286d14aa542c167497d83262
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6726211"
---
# <a name="using-microsoft-power-apps-portals-with-the-party-data-model"></a>A Microsoft Power Apps portál használata a Fél adatmodelljével

[!INCLUDE[banner](../../includes/banner.md)]

[!INCLUDE[rename-banner](~/includes/cc-data-platform-banner.md)]

A kettős írású alkalmazás vezérlési megoldása 2.0.999.0 és későbbi verziója tartalmazza a partner- és globális címjegyzék adatmodell-módosításait a Számla és Kapcsolattartó táblákban. A módosítások több a többhöz kapcsolatot is lehetővé tesznek, amelyek speciális üzleti helyzeteket támogatnak. Ezeket a módosításokat nem támogatják a portál webes szerepkörei, köztük a vevői portál, amelyek a gyári telepítés része, vagy amelyek a környezetben léteztek a kettős írás telepítése előtt. Ahhoz, hogy a webes szerepkörök a várt módon működjenek, új webes szerepköröket kell létrehozni az új adatmodell segítségével. 

Összegzésképpen: a táblák kommunikációja megváltozott, de a vevői portál táblaengedélyei nem módosultak. Ez a témakör bemutatja az új speciális adatmodellel működő új webes szerepkörök létrehozásához szükséges feladatokat.

Ez az ábra a fél és a globális címjegyzék adatmodell **nélkül** ábrázolja a táblakapcsolatokat:

   ![Fél modell nélkül.](media/without-party-model.PNG)

Ez az ábra a fél és a globális címjegyzék adatmodell **esetén** ábrázolja a táblakapcsolatokat:

   ![fél modellel.](media/with-party-model.png)

## <a name="create-a-new-table-permission"></a>Új táblaengedély létrehozása

Az alábbi lépések szerint hozhatja létre az új táblaengedélyeket:

1. Jelentkezzen be a [Power Apps](https://make.powerapps.com) alkalmazásokba, és lépjen be az alkalmazásokba.
2. Válassza ki a Portálkezelést alkalmazást.
3. Válassza az oldalsávon a **Biztonság > Táblaengedélyek** lehetőséget.

    Három új engedélyt kell létrehoznia:

    + **Kapcsolattartó** a **Félhez** táblakapcsolat
    + **Fél** a **Számlához** táblakapcsolat
    + **Számla** a **Rendeléshez** táblakapcsolat

4. Új engedély létrehozása és mentése a Kapcsolattartó a Félhez kapcsolathoz a következő paraméterek beállításával:

    + **Név**: **Fél** – **Partner** táblakapcsolat (vagy az Ön választása)
    + **Tábla neve**: msdyn_contactforparty
    + **Weboldal**: Ügyfélportál
    + **Hatókör**: Kapcsolattartó
    + **Jogosultságok**: Az összes kijelölése
    + **Webes szerepkörök**: Hitelesített felhasználók, ügyfél-képviselő (vagy az Ön választása)

5. Új engedély létrehozása és mentése a Fél a Partnerhez kapcsolathoz a következő paraméterek beállításával:

    + **Név**: Fél-Partner kapcsolat (vagy az Ön választása)
    + **Tábla neve**: partner
    + **Weboldal**: Ügyfélportál
    + **Hatókör:** Szülő
    + **Jogosultságok**: Az összes kijelölése
    + **Szülőtábla engedélye**: Kapcsolattartó a Félhez kapcsolat

6. Új engedély létrehozása és mentése a Partner a Rendeléshez kapcsolathoz a következő paraméterek beállításával:

    + **Név**: Fél a Partnerhez kapcsolat (vagy az Ön választása)
    + **Tábla neve**: értékesítési rendelés
    + **Weboldal**: Ügyfélportál
    + **Hatókör:** Szülő
    + **Jogosultságok**: Az összes kijelölése
    + **Szülőtábla engedélye**: Fél a Partnerhez kapcsolat

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
