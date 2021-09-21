---
title: Hiba lép fel, ha a helyet választanak ki a kitárolási lista regisztrációja során
description: Hiba lép fel, ha a helyet választanak ki a kitárolási lista regisztrációja során.
author: perlynne
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: WMSPickingRegistration
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: ef34b4fdcc572c56319f6cbf4913d822d8857595
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/07/2021
ms.locfileid: "7474964"
---
# <a name="an-error-occurs-when-the-location-is-selected-during-picking-list-registration"></a>Hiba lép fel, ha a helyet választanak ki a kitárolási lista regisztrációja során

Tudásbáziscikk száma: 4613106

## <a name="symptoms"></a>Tünetek

Ez a probléma akkor jelentkezik, ha a rendszer úgy van beállítva, hogy automatikusan lefoglalja az értékesítési rendeléseket. Ha megpróbálja kiválasztani a kitárolási lista regisztrációs sorának helyét, a következő hibaüzenet jelenik meg a raktárkezelési (WMS) foglalási folyamatok használatakor:

> Nem frissíthető a mennyiség új dimenziókkal

Ez a probléma azért fordulhat elő, mert nincs elég készlete egy megadott helyen.

## <a name="resolution"></a>Felbontás

A rendszer úgy viselkedik, ahogy tervezték.

Azokban az esetekben, amikor a raktárszintű foglalási folyamatot használja, ha az aktuális készlet nem lesz lefoglalva az összes készletdimenziós szinten, és nincs elegendő akutális készlete egy megadott helyen, javasoljuk, hogy használja a kézi foglalási folyamatot a kitárolási sorból. Ezután az *Adag foglalása* funkcióval terjesztheti az alacsonyabb foglalásokat, például a helyeket az összes rendelkezésre álló aktuális mennyiségre.
