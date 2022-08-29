---
title: Adóbeállítások szinkronizálása az adószámítási szolgáltatásból a Dynamics 365 Pénzügy szolgáltatásba
description: Ez a cikk bemutatja, hogy hogyan Microsoft Dynamics szinkronizálhatja az adóbeállítási alapadatokat az adószámítási szolgáltatásból a 365-ös pénzügyi dokumentumba.
author: EricWangChen
ms.date: 01/05/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: kfend
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.21
ms.custom: intro-internal
ms.search.form: TaxIntegration, TaxServiceParameters
ms.openlocfilehash: 315f2b27a64906ca0fc404d704d0b170dbfa48c5
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9283853"
---
# <a name="sync-the-tax-setup-from-the-tax-calculation-service-to-dynamics-365-finance"></a>Adóbeállítások szinkronizálása az adószámítási szolgáltatásból a Dynamics 365 Pénzügy szolgáltatásba

[!include [banner](../includes/banner.md)]

Ez a cikk bemutatja, hogy hogyan Microsoft Dynamics szinkronizálhatja az adóbeállítási alapadatokat az adószámítási szolgáltatásból a 365-ös pénzügyi dokumentumba.

Miután befejezte az [Adószámítás](global-get-started-with-tax-calculation-service.md)– Első lépésekkel lépést, a következő adóbeállítási adatok automatikusan szinkronizálódnak az adószámítási szolgáltatásból a pénzügyekbe.

## <a name="sales-tax-code"></a>Áfakód

| Adószámítási szolgáltatás           | Finance                             |
| --------------------------------- | ----------------------------------- |
| Adókód                          | Áfakód                      |
| Leírás                       | Név                                |
| Felhasználói adatbevitel                        | Kifizetési időszak                   |
| Felhasználói adatbevitel                        | Főkönyvi feladási csoport                |
| Felhasználói adatbevitel                        | Áfa pénznem                  |
| Negatív adókulcs van beállítva. | Negatív áfaszázalék engedélyezése |

## <a name="tax-value"></a>Adó értéke

| Adószámítási szolgáltatás | Finance                   |
| ----------------------- | ------------------------- |
| Tranzakció kezdő dátuma   | Kezdő dátum                 |
| Tranzakció záró dátuma     | Záró dátum                   |
| Minimális összeg          | Minimumhatár             |
| Maximális összeg          | Maximum határ             |
| Áfakulcs                | Érték                     |
| Nem levonható díj     | Nem levonható százalék |

## <a name="tax-limits"></a>Adókorlátok

| Adószámítási szolgáltatás | Finance           |
| ----------------------- | ----------------- |
| Tranzakció kezdő dátuma   | Kezdő dátum         |
| Tranzakció záró dátuma     | Záró dátum           |
| Minimális adóösszeg      | Minimális áfa |
| Adó maximális összege      | Maximális áfa |

## <a name="sales-tax-group"></a>Áfacsoport

| Adószámítási szolgáltatás                         | Finance                                    |
| ----------------------------------------------- | ------------------------------------------ |
| Adócsoport                                       | Áfacsoport                            |
| Az adócsoporthoz alatti adókódok                  | Az áfacsoport alatti áfakódok |
| Az adókód Adómentesként **van megjelölve.**         | Adómentes                                     |
| Az adókód Adómentesként **van megjelölve.**         | Adómentesség kódja                                |
| Az adókód fordított áfafizetésűként **van megjelölve.** | Fordított áfa                             |
| Az adókód "Használat adó" jelöléssel **van megjelölve.**        | Importadó                                    |

## <a name="item-sales-tax-group"></a>Cikkáfacsoport

| Adószámítási szolgáltatás             | Finance                                         |
| ----------------------------------- | ----------------------------------------------- |
| Cikk adócsoportja                      | Cikkáfacsoport                            |
| A cikk adócsoportja alatti adókódok | A cikk áfacsoportja alatti áfakódok |

A szinkronizálás befejezése után folytassa a feladási és jelentéskészítési célokra a Pénzügy fennmaradó paramétereinek karbantartását.

> [!NOTE]
> Az adóbeállítás szinkronizálása a Pénzügy és az adószámítási szolgáltatás között nem támogatott. Meglévő pénzügyi környezetek esetén először hozza létre az adóbeállításokat az adószámítási szolgáltatásban. Ezután szinkronizálja a beállítási adatokat a Pénzügyi környezettel.
