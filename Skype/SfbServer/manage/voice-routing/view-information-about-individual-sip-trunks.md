---
title: 비즈니스용 Skype 서버에서 개별 SIP 트렁크에 대한 정보 보기
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 비즈니스용 Skype 서버에서는 단일 PSTN 게이트웨이에 여러 트렁크를 할당할 수 있습니다. 즉, 게이트웨이와 트렁크가 하나만 같지 않은 것이고 관리자는 Get-CsTrunk cmdlet을 사용하여 개별 SIP 트렁크에 대한 정보를 보아야 합니다.
ms.openlocfilehash: b49846ed7244dec2f51f51f262becc440662026c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826178"
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 개별 SIP 트렁크에 대한 정보 보기

비즈니스용 Skype 서버에서는 단일 PSTN 게이트웨이에 여러 트렁크를 할당할 수 있습니다. 즉, 게이트웨이와 트렁크는 하나만 같지 않을 뿐만 아니라 관리자가 [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk) cmdlet을 사용하여 개별 SIP 트렁크에 대한 정보를 보아야 합니다.

이 Get-CsTrunk 비즈니스용 Skype 서버 관리 셸 또는 비즈니스용 Skype 서버 관리 셸의 원격 세션에서 실행할 수 Windows PowerShell.

**모든 SIP 트렁크에 대한 정보를 확인**

다음 명령은 조직에서 사용 하는 모든 SIP 트렁크에 대 한 정보를 반환 합니다.

`Get-CsTrunk`

**특정 SIP 트렁크에 대한 정보를 보기 위해**

이 명령은 ID가 PstnGateway:192.168.0.240인 SIP 트렁크에 대한 정보만 반환합니다.

`Get-CsTrunk -Identity "PstnGateway:192.168.0.240"`

**풀에 할당된 모든 SIP 트렁크에 대한 정보 보기**

이 예제에서는 풀에 할당된 모든 SIP 트렁크에 대한 정보를 atl-cs-001.litwareinc.com.

`Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"`
