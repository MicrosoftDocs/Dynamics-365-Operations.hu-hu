---
title: Kettős pénznemtámogatás adó esetén
description: Ez a cikk bemutatja, hogy hogyan lehet kiterjeszteni a kettős pénznemkönyvelési funkciót az adótartományban, és hogyan lehet kiterjeszteni az adószámítást és a feladást.
author: EricWang
ms.date: 12/11/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: kfend
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2020-01-14
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: 13d70d964a83c2efba090244d549bdb38ad25af2
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8909040"
---
# <a name="dual-currency-support-for-sales-tax"></a>Kettős pénznemtámogatás áfa esetén
[!include [banner](../includes/banner.md)]

Ez a cikk bemutatja, hogy hogyan lehet kiterjeszteni a kettős pénznemelszámolást az áfákra, és hogyan lehet kiterjeszteni az áfaszámításokat, -feladásokat és kiegyenlítéseket.

A Dynamics 365 Pénzügy két pénznemes funkcióját a 8.1-es verzióban (2018. október 1.) vezették be. Megváltoztatja a könyvelési bejegyzések számításának módját a jelentési pénznemben.

A korábbi verziókban a tranzakciók a következő sorrendben lettek átváltva a jelentési pénznemre: 

- A tranzakció végösszege a tranzakció pénznemében lett kiszámítva, > A tranzakció összege a könyvelési pénznemre lett átváltva > A könyvelési pénznem összegét a jelentési pénznemre alakították át

A kettős pénznem funkció engedélyezése után a tranzakciók a következő sorrendben lettek átváltva a jelentési pénznembe:

- Tranzakció pénznemének összege > Jelentési pénznem összege

A kettős pénznemmel kapcsolatos további tudnivalókat lásd: [Kettős pénznem](dual-currency.md).

A kettős pénznemek támogatásának következményeként két új funkció érhető el a funkciókezelésben: 

- Áfa átváltása (új a 10.0.13-es verzióban)
- Pénzügyi dimenziók megadása a realizált pénznemkorrekció eredményszámláira az áfafizetéshez (újdonság a 10.0.17-es verzióban)

Az áfa kettős pénznemre vonatkozó támogatása biztosítja az adók helyes kiszámítását az adó pénznemében, és azt, hogy az áfaelszámolási egyenleg kiszámítása mind a könyvelési pénznemben, mind a jelentési pénznemben pontos legyen.

## <a name="sales-tax-conversion"></a>Áfa-konverzió

Az **áfa-átváltási paraméter** két lehetőséget biztosít arra, hogy az adó összegét a tranzakció pénzneméről az adó pénznemére átváltsák. 

- Könyvelési pénznem: Az útvonal a következő lesz: „Összeg a tranzakció pénznemében > Összeg a könyvelési pénznemben > Összeg az adó pénznemében”. A pénznem átváltásakor a könyvelési pénznem árfolyamtípusát (amelyet a Főkönyv beállításainál konfiguráltak) használja a rendszer.
- Jelentési pénznem: Az útvonal a következő lesz: „Összeg a tranzakció pénznemében > Összeg a jelentési pénznemben > Összeg az adó pénznemében”. A pénznem átváltásakor a jelentési pénznem árfolyamtípusát (amelyet a Főkönyv beállításainál konfiguráltak) használja a rendszer.

### <a name="example"></a>Példa

Egyszerű példa a funkció bemutatására:

A főkönyv és adó pénznemének beállítása

| Tranzakció pénzneme | Könyvelési pénznem | Jelentési pénznem | Adópénznem |
| -------------------- | ------------------- | ------------------ | ------------ |
| HUF                  | dollár                 | GBP                | GBP          |

Árfolyam

| Kezdő pénznem | Célpénznem | Szorzó | Árfolyam |
| ------------- | ----------- | ------ | ------------- |
| HUF           | dollár         | 1      | 1.11          |
| HUF           | GBP         | 1      | 0.83          |
| dollár           | GBP         | 1      | 0.75          |

Adó összegének számítása különböző paraméter-beállításoknál

Adó összege = 100 EUR

| Áfa átváltási paraméterei | Tranzakció pénzneme (EUR) | Könyvelési pénznem (USD) | Jelentési pénznem (GBP) | Adó pénzneme (GBP) |
| ------------------------------- | -------------------------- | ------------------------- | ------------------------ | ------------------ |
| Könyvelési pénznem             | 100                        | 111                       | 83                       | **83.25**          |
| Jelentési pénznem              | 100                        | 111                       | 83                       | **83**             |

Ezt a paramétert az adóhatóságnak való megfelelés szükségessége alapján lehet konfigurálni.


### <a name="upgrade-consideration"></a>Frissítési megfontolások

Ez a funkció csak az új tranzakciókra lesz alkalmazva. A TAXTRANS táblában más mentett, de még nem kiegyenlített adótranzakciók esetén a rendszer nem számítja újra az adó összegét az adó pénznemében, mert az adó feladási időpillanatában érvényes árfolyam már hiányzik.

Az előző eset megakadályozása érdekében ajánlott módosítani ezt a paramétert egy olyan új (tiszta) adóelszámolási időszakban, amely nem tartalmaz kiegyenlítetlen adózási tranzakciókat. Ha módosítani kívánja ezt az értéket egy adózási időszak közepén, futtassa "az áfa kiegyenlítése és feladása" programot a jelenlegi adózási időszakra, mielőtt módosítaná a paraméter értékét.

Ez a funkció olyan könyvelési tételeket vesz fel, amelyek egyértelművé teszik a pénznemek közötti átváltásból származó nyereségeket és veszteségeket. Amikor az áfafizetés során újraértékelés történik, a bejegyzéseket a realizált pénznemkorrekció eredményszámláira könyveli a program. A további tudnivalókat lásd [a](#tax-settlement-auto-balance-in-reporting-currency) jelentési pénznemek automatikus egyenlegének jelentési pénznemben című részében.

> [!NOTE]
> Az áfafizetés során a pénzügyi dimenziók adatai az adóügyi számlákból (a mérlegszámlákból) származnak, és az adatok a pénznemkorrekció – nyereséget vagy a veszteséget mutató – eredményszámláira kerülnek. Mivel a pénzügyi dimenziók értékére vonatkozó korlátozások eltérnek a mérlegszámlák és az eredményszámlák között, a forgalmi adó rendezése és feladása között hiba történhet. Ha el szeretné kerülni a számlastruktúrák módosítását bekapcsolhatja a „Pénzügyi dimenziók kitöltése a realizált pénznemkorrekció eredményszámláin az áfafizetéshez” funkciót. Ez a funkció kényszeríti a pénzügyi dimenziók pénznemkorrekciós eredményszámlákra történő származtatását. 

## <a name="track-reporting-currency-tax-amount"></a>Adó összegének nyomon követése jelentési pénznemben

Három új mező került az adóval kapcsolatos táblákba, hogy nyomon kövessék a jelentés pénznemében az összegeket. Ezek a mezők a TAXUNCOMMITTED és a TAXTRANS táblákon belül találhatók:

- TaxAmountRep: adó összege jelentési pénznemben
- TaxBaseAmountRep: alapösszeg jelentési pénznemben
- TaxInCostPriceRep: nem levonható összeg a jelentési pénznemben

A csak a TAXUNCOMMITTED táblában mentett, de még nem feladott adók esetén a rendszer újraszámítja az adó összegét jelentési pénznemben a feladás időpontjában, és menti a TAXTRANS táblába.

Ez a kiadás nem tartalmaz módosításokat a jelentésekhez és űrlapokhoz, amelyek a jelentés pénznemében tartalmazzák az adó összegét. A jelentések és űrlapok módosításai a jövőbeli verzióban lesznek kiadva.



## <a name="tax-settlement-auto-balance-in-reporting-currency"></a>Adóelszámolás automatikus egyenlege a jelentési pénznemben

Ha az adókiegyenlítés nincs egyensúlyban a jelentési pénznemben valamilyen okból, például az áfa-átváltás útvonala „Könyvelési pénznem”, vagy az árfolyam módosulása egyetlen adókiegyenlítési időszakon belül, a rendszer automatikusan létrehoz olyan könyvelési bejegyzéseket, amelyekkel módosítható az adóösszeg eltérése, és eltolható a realizált árfolyamnyereségi/veszteségi számlával szemben, amely a Főkönyv beállításaiban konfigurálható.

Ha a TAXTRANS tábla adatai a feladás időpontjában az alábbiak, akkor az előző példán keresztül bemutatható a funkció.

| Áfa átváltási paraméterei | Tranzakció pénzneme (EUR) | Könyvelési pénznem (USD) | Jelentési pénznem (GBP) | Adó pénzneme (GBP) |
| ------------------------------- | -------------------------- | ------------------------- | ------------------------ | ------------------ |
| Könyvelési pénznem             | 100                        | 111                       | 83                       | **83.25**          |
| Jelentési pénznem              | 100                        | 111                       | 83                       | **83**             |

Ha az áfakiegyenlítési programot a hónap végén futtatja, a könyvelési bejegyzés a következő lesz.
#### <a name="scenario-sales-tax-conversion--accounting-currency"></a>Forgatókönyv: áfa átváltása = „könyvelési pénznem”

| Fő számla           | Tranzakció pénzneme (GBP) | Könyvelési pénznem (USD) | Jelentési pénznem (GBP) |
| ---------------------- | -------------------------- | ------------------------- | ------------------------ |
| Fizetendő adó/visszaigényelhető adó | -83,25                     | -111                      | -83,25                   |
| Adó kiegyenlítése         | 83.25                      | 111                       | 83.25                    |
| Realizált nyereség/veszteség     | 0                          | 0                         | -0,25                    |
| Fizetendő adó/visszaigényelhető adó | 0                          | 0                         | 0.25                     |

#### <a name="scenario-sales-tax-conversion--reporting-currency"></a>Forgatókönyv: áfa átváltása = „jelentési pénznem”


| Fő számla           | Tranzakció pénzneme (GBP) | Könyvelési pénznem (USD) | Jelentési pénznem (GBP) |
| ---------------------- | -------------------------- | ------------------------- | ------------------------ |
| Fizetendő adó/visszaigényelhető adó | -83                        | -110,67                   | -83                      |
| Adó kiegyenlítése         | 83                         | 110.67                    | 83                       |
| Realizált nyereség/veszteség     | 0                          | 0.33                      | 0                        |
| Fizetendő adó/visszaigényelhető adó | 0                          | -0,33                     | 0                        |



További információért tekintse át az alábbi témaköröket:

- [Kettős pénznem](dual-currency.md)
- [Áfa áttekintése](indirect-taxes-overview.md)



[!INCLUDE[footer-include](../../includes/footer-banner.md)]
