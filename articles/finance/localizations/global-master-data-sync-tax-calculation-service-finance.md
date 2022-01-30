---
title: 'Adóbeállítások szinkronizálása az adószámítási szolgáltatásból a következőbe: Dynamics 365 Finance'
description: Ez a témakör bemutatja, hogy hogyan lehet szinkronizálni az adóbeállítási alapadatokat az adószámítási szolgáltatásból a Microsoft számára Dynamics 365 Finance.
author: wangchen
ms.date: 01/05/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TaxIntegration, TaxServiceParameters
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: intro-internal
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: d5d994934014a146f825431cb53dfbef8fe20bc8
ms.sourcegitcommit: 27475081f3d2d96cf655b6afdc97be9fb719c04d
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/12/2022
ms.locfileid: "7965107"
---
# <a name="sync-the-tax-setup-from-the-tax-calculation-service-to-dynamics-365-finance"></a>Adóbeállítások szinkronizálása az adószámítási szolgáltatásból a következőbe: Dynamics 365 Finance

[!include [banner](../includes/banner.md)]

Ez a témakör bemutatja, hogy hogyan lehet szinkronizálni az adóbeállítási alapadatokat az adószámítási szolgáltatásból a Microsoft számára Dynamics 365 Finance.

Miután befejezte az Adószámítás – Első lépésekkel lépést, a következő adóbeállítási adatok automatikusan szinkronizálódnak az adószámítási szolgáltatásból a [pénzügyekbe](global-get-started-with-tax-calculation-service.md).

## <a name="sales-tax-code"></a>Áfakód

| Áfaszámítási szolgáltatás           | Finance                             |
| --------------------------------- | ----------------------------------- |
| Adókód                          | Áfakód                      |
| Leírás                       | Név                                |
| Felhasználói adatbevitel                        | Kifizetési időszak                   |
| Felhasználói adatbevitel                        | Főkönyvi feladási csoport                |
| Felhasználói adatbevitel                        | Áfa pénznem                  |
| Negatív adókulcs van beállítva. | Negatív áfaszázalék engedélyezése |

## <a name="tax-value"></a>Adó értéke

| Áfaszámítási szolgáltatás | Finance                   |
| ----------------------- | ------------------------- |
| Tranzakció kezdő dátuma   | Kezdő dátum                 |
| Tranzakció záró dátuma     | Záró dátum                   |
| Minimális összeg          | Minimumhatár             |
| Maximális összeg          | Maximum határ             |
| Áfakulcs                | Érték                     |
| Nem levonható díj     | Nem levonható százalék |

## <a name="tax-limits"></a>Adókorlátok

| Áfaszámítási szolgáltatás | Finance           |
| ----------------------- | ----------------- |
| Tranzakció kezdő dátuma   | Kezdő dátum         |
| Tranzakció záró dátuma     | Záró dátum           |
| Minimális adóösszeg      | Minimális áfa |
| Adó maximális összege      | Maximális áfa |

## <a name="sales-tax-group"></a>Áfacsoport

| Áfaszámítási szolgáltatás                         | Finance                                    |
| ----------------------------------------------- | ------------------------------------------ |
| Adócsoport                                       | Áfacsoport                            |
| Az adócsoporthoz alatti adókódok                  | Az áfacsoport alatti áfakódok |
| Az adókód Adómentesként **van megjelölve.**         | Mentes                                     |
| Az adókód Adómentesként **van megjelölve.**         | Adómentesség kódja                                |
| Az adókód fordított **áfafizetésűként van megjelölve.** | Fordított áfa                             |
| Az adókód "Használat adó" **jelöléssel van megjelölve.**        | Importadó                                    |

## <a name="item-sales-tax-group"></a>Cikkáfacsoport

| Áfaszámítási szolgáltatás             | Finance                                         |
| ----------------------------------- | ----------------------------------------------- |
| Tétel adócsoport                      | Cikkáfacsoport                            |
| A cikk adócsoportja alatti adókódok | A cikk áfacsoportja alatti áfakódok |

A szinkronizálás befejezése után folytassa a feladási és jelentéskészítési célokra a Pénzügy fennmaradó paramétereinek karbantartását.

> [!NOTE]
> Az adóbeállítás szinkronizálása a Pénzügy és az adószámítási szolgáltatás között nem támogatott. Meglévő pénzügyi környezetek esetén először hozza létre az adóbeállításokat az adószámítási szolgáltatásban. Ezután szinkronizálja a beállítási adatokat a Pénzügyi környezettel.
