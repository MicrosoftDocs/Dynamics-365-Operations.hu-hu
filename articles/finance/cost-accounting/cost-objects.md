---
title: Költségobjektum-dimenziók
description: Amikor költségeket elemez, a költségobjektum-dimenziók segítségével határozza meg, hová kerülnek a költségek. Használja a költségobjektum-dimenziókat a költségek hozzárendelésének meghatározására. Ez a témakör tájékoztatást nyújt a költségobjektum-dimenziókkal kapcsolatban.
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMDimensionMember, CAMCostObject
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 223174
ms.assetid: 2a1cdd35-30cb-41e7-9506-67fd04a537c5
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 879d4ce5710974d2838c646e0e184eab653f7293
ms.sourcegitcommit: cd339f48066b1d0fc740b513cb72ea19015acd16
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/02/2020
ms.locfileid: "3759400"
---
# <a name="cost-object-dimensions"></a>Költségobjektum-dimenziók

[!include [banner](../includes/banner.md)]

Amikor költségeket elemez, a költségobjektum-dimenziók segítségével határozza meg, hová kerülnek a költségek. Használja a költségobjektum-dimenziókat a költségek hozzárendelésének meghatározására. Ez a témakör tájékoztatást nyújt a költségobjektum-dimenziókkal kapcsolatban.

A költségobjektum lehet bármilyen olyan típusú objektum, amellyel becslést akar végezni, amelyhez költségeket akar rendelni, vagy amelyet közvetlenül mérni kíván. A tipikus költségobjektumok közé tartoznak a termékek, projektek, erőforrások, részlegek, költséghelyek és földrajzi területek. A vezetés a költségobjektumokat a költségek mennyiségének megállapítására és nyereségességi elemzés elvégzésére használja.

## <a name="cost-object-dimensions-and-cost-object-dimension-members"></a>Költségobjektum-dimenziók és költségobjektum-dimenziótagok
A költségobjektumok *költségobjektum-dimenzióként* ismertek. Miután eldöntötte, hogy a költségobjektum-dimenzió mely entitáshoz tartozzon, meg kell határoznia az egyedi dimenzióértékeket vagy importálnia kell azokat a költségkönyvelésbe más forrásokból. Ezek az egyes dimenzióértékek *költségobjektum-dimenziótagokként* ismertek. Példa: Ön a költséghely elnevezésű pénzügyi dimenziót akarja költségobjektum-dimenzióként használni. Ahhoz, hogy lássa, hogyan kerülnek a költségek az egyes költséghelyekhez, importálnia kell a költségobjektum-dimenziótagokat. Ebben az esetben a költségobjektum-dimenziótagok a tényleges költséghelyek, például értékesítés, termelés, felügyelet vagy földrajzi hely. Az alábbi képernyőképen látható példa a költséghelyeket ábrázolja költségobjektum-dimenzióként, ahol a tényleges költséghelyek a költségobjektum-dimenziótagok. 

[![A Költséghelyeket költségobjektum-dimenzióként bemutató képernyőkép](./media/cost-object-dimensions.png)](./media/cost-object-dimensions.png)

## <a name="import-cost-object-dimension-members-through-data-connectors"></a>Költségobjektum-dimenziókagok importálása át adatcsatolókon keresztül
Ahhoz, hogy a költségobjektum-dimenziótagokat könnyebben lehessen importálni, használja az adatcsatolókat az értékek lekéréséhez azokból az entitásokból, amelyeket költségobjektum-dimenzióként akar használni. Használhat előre elkészített adatcsatolókat vagy egyedi, saját összeállítású adatcsatolókat.



