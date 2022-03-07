---
title: A tervezett beszerzési rendelés akkor jön létre, ha a negatív napokon belül beszerzés létezik
description: Ha a fedezeti kód Min/max, a Tervezési optimalizálás tervezett beszerzési rendelést hoz létre, ha a negatív napokon belüli beszerzés létezik.
author: ChristianRytt
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo,MpsIntegrationParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ilebedev
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 94d569684a0bfa2398e98147b9b85531954f8d56748894034a048fa627230ef0
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6775507"
---
# <a name="planned-purchase-order-is-created-when-a-purchase-exists-within-negative-days"></a>A tervezett beszerzési rendelés akkor jön létre, ha a negatív napokon belül beszerzés létezik

Tudásbáziscikk száma: 4614298

## <a name="symptoms"></a>Tünetek

Ha a fedezeti kód *Min/max*, a Tervezési optimalizálás tervezett beszerzési rendelést hoz létre, ha a negatív napokon belüli beszerzés létezik.

## <a name="resolution"></a>Felbontás

A tervezési optimalizálás nem támogatja a negatív napokat. Ugyanakkor mindig gondoskodik arról, hogy a tervezett rendelések ne legyenek ütemezéve az aktuális dátumhoz képest az átfutási időben. Például a beszerzés átfutási ideje 10 nap, és a beszerzési rendelés várhatóan a mai naptól számítva nyolc nap múlva érkezik. Ebben az esetben a beszerzési rendelés lesz a mai naptól számított ötödik napon lesz igény szerinti beszállításként használva.

Ezért javasoljuk, hogy úgy módosítsa az átfutási időket, hogy minden (vagy szinte az összes) esetet lefedje.
