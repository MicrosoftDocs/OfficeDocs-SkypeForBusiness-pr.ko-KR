---
title: 비즈니스용 Skype 서버 - 개별 SIP 트렁크에 대한 정보 보기
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 이 비즈니스용 Skype 서버 단일 PSTN 게이트웨이에 여러 트렁크를 할당할 수 있습니다. 게이트웨이와 트렁크는 같지 않습니다. 관리자는 Get-CsTrunk cmdlet을 사용하여 개별 SIP 트렁크에 대한 정보를 보아야 합니다.
ms.openlocfilehash: 2c39a35ee0a42e2f54e87541cec857b3d90cd2c6
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58617804"
---
# <a name="skype-for-business-server---view-information-about-individual-sip-trunks"></a>비즈니스용 Skype 서버 - 개별 SIP 트렁크에 대한 정보 보기

이 비즈니스용 Skype 서버 단일 PSTN 게이트웨이에 여러 트렁크를 할당할 수 있습니다. 즉, 게이트웨이와 트렁크는 하나만 같지 않을 뿐만 아니라 [관리자가 Get-CsTrunk](/powershell/module/skype/Get-CsTrunk) cmdlet을 사용하여 개별 SIP 트렁크에 대한 정보를 볼 수 있어야 합니다.

이 Get-CsTrunk cmdlet은 비즈니스용 Skype 서버 관리 셸 또는 원격 세션에서 실행할 수 Windows PowerShell.

**모든 SIP 트렁크에 대한 정보를 확인**

다음 명령은 조직에서 사용 중이면 모든 SIP 트렁크에 대한 정보를 반환합니다.

`Get-CsTrunk`

**특정 SIP 트렁크에 대한 정보를 보기 위해**

이 명령은 ID가 PstnGateway:192.168.0.240인 SIP 트렁크에 대한 정보만 반환합니다.

`Get-CsTrunk -Identity "PstnGateway:192.168.0.240"`

**풀에 할당된 모든 SIP 트렁크에 대한 정보 보기**

이 예에서는 풀에 할당된 모든 SIP 트렁크에 대한 정보를 atl-cs-001.litwareinc.com.

`Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"`
