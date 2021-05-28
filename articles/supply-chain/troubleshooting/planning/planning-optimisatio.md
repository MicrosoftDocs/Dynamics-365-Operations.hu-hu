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
ms.openlocfilehash: 826496c2de956ff949dd79ab8aa643053719bf75
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026581"
---
# <a name="planned-purchase-order-is-created-when-a-purchase-exists-within-negative-days"></a>A tervezett beszerzési rendelés akkor jön létre, ha a negatív napokon belül beszerzés létezik

Tudásbáziscikk száma: 4614298

## <a name="symptoms"></a>Tünetek

Ha a fedezeti kód *Min/max*, a Tervezési optimalizálás tervezett beszerzési rendelést hoz létre, ha a negatív napokon belüli beszerzés létezik.

## <a name="resolution"></a>Felbontás

A tervezési optimalizálás nem támogatja a negatív napokat. Ugyanakkor mindig gondoskodik arról, hogy a tervezett rendelések ne legyenek ütemezéve az aktuális dátumhoz képest az átfutási időben. Például a beszerzés átfutási ideje 10 nap, és a beszerzési rendelés várhatóan a mai naptól számítva nyolc nap múlva érkezik. Ebben az esetben a beszerzési rendelés lesz a mai naptól számított ötödik napon lesz igény szerinti beszállításként használva.

Ezért javasoljuk, hogy úgy módosítsa az átfutási időket, hogy minden (vagy szinte az összes) esetet lefedje.
