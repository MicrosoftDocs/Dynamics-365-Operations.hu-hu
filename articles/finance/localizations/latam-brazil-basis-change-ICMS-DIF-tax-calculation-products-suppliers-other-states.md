---
title: Más államok szállítói termékeire vonatkozó ICMS-DIF adószámítások alapváltozása
description: Ez a témakör az ICMS-DIF adótípus számításának konfigurációját írja le, amikor egy pénzügyi bizonylatot a brazil Grande do Sul (RS) vagy São Bizonylato (SP) államban érkezik.
author: Kai-Cloud
ms.date: 1/20/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.custom: ''
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2022-1-17
ms.dyn365.ops.version: 10.0.26
ms.openlocfilehash: 1fde18c79f375db4db6bc52cdb5c40a61625ae63
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8868262"
---
# <a name="basis-change-in-icms-dif-tax-calculations-for-products-from-suppliers-in-other-states"></a>Más államok szállítói termékeire vonatkozó ICMS-DIF adószámítások alapváltozása

Ez a témakör az **ICMS-DIF** adótípus számításának konfigurációját írja le, amikor egy pénzügyi bizonylatot a brazil Grande do Sul (RS) vagy São Bizonylato (SP) államban érkezik.

Az állami törvényben leírott definíciók szerint az összegyűjtött Mercadorias e De Mercadorias e Serviços (ICMS) szabálynak követnie kell ezt a szabályt:

*Beszedni szükséges ICMS* = ([(*Művelet* összege - *forrásból származó ICMS*) ÷ (1 – *ICMS %* belső)] × *ICMS %* belső) – *ICMS-összeg a forrásból*

## <a name="example"></a>Példa

Az RS-államban brazil vállalat pénzügyi bizonylatot kap egy beszerzésről az sp államban. A vállalatnak az RS állam (18 százalék) és a sp állam (12 százalék) között meg kell gyűjtenie az ICMS százalékos eltérését. Az alapot ugyanakkor az előző szabály szerint kell kiszámítani.

- **Művelet összege:** 1 000,00 Brazil reál (R$ 1 000,00)
- **ICMS-interstate:** R$ 120,00
- **ICMS-százalék AZ RS-állapotban:** 18 százalék
- **AZ RS-államban beszedhető ICMS-** (\[(1000 – 120) ÷ (1 – 0,18)\] × 0,18) – 120 = R$ 73,17 

## <a name="resolution"></a>Megoldás

Az ICMS-DIF eltérésnek az RS-állam szabályai szerinti kiszámításához a következő módon kell áfakódokat és áfacsoportokat beállítani:

1. Hozzon létre egy áfakódot a 12 százalékos ICMS fogadására (a másik államban). Ezzel a kóddal lehet regisztrálni a szállítótól visszakövethető adó összegét.
2. Hozzon létre egy áfakódot az ICMS-DIF összegyűjtéséhez. Ennek az áfakódnak 18 százalékos összeggel kell lennie (a saját államban), hogy meghatározza a 18 és 12 százalék közötti különbséget. Állítsa az adótípust **ICMS-DIF típusúra**. Ezt az áfakódot a következő módon kell meghatározni a számítási paraméterek között:

    - Az Eredet **mezőben** válassza a Bruttó **összeg százaléka lehetőséget**.
    - A Számítás **alapja mezőben** válassza a **Soronkénti nettó összeg** **vagy a Számlaegyenleg nettó összege lehetőséget**.
    - Az adózási kód megadása úgy, hogy 3 értékű **pénzügyi értéket tartalmazzon**. Ilyen módon a pénzügyi **könyvek** modul engedélyezésekor automatikusan létrejön a korrekciós tranzakció.
    - Az áfacsoport konfigurációjában válassza **ki az ICMS-DIF** áfakódhoz az "Use **tax**" beállítást.
