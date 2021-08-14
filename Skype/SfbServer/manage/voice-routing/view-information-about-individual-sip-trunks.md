---
title: SIP의 개별 SIP 트렁크에 대한 비즈니스용 Skype 서버
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
description: 이 비즈니스용 Skype 서버 단일 PSTN 게이트웨이에 여러 트렁크를 할당할 수 있습니다. 즉, 게이트웨이와 트렁크가 동일하지는 않습니다. 관리자는 Get-CsTrunk cmdlet을 사용하여 개별 SIP 트렁크에 대한 정보를 보아야 합니다.
ms.openlocfilehash: 1fd465bcbf547471f9ca5ead562d8b77976be79621bd4246be85341126577936
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54351458"
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server"></a>SIP의 개별 SIP 트렁크에 대한 비즈니스용 Skype 서버

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