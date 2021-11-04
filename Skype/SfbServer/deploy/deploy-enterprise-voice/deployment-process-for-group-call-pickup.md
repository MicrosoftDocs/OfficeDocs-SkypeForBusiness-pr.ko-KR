---
title: 2016년 12월 그룹 통화 비즈니스용 Skype
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 082daeac-e667-4e2d-b78d-8e0901f9f0e9
description: 배포 프로세스 및 그룹 통화 선택에 대한 비즈니스용 Skype 서버 Enterprise Voice.
ms.openlocfilehash: 0694975515286920344ce2f21ef7ad1f0ab64242
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60775768"
---
# <a name="deployment-process-for-group-call-pickup-in-skype-for-business"></a>2016년 12월 그룹 통화 비즈니스용 Skype
 
배포 프로세스 및 그룹 통화 선택에 대한 비즈니스용 Skype 서버 Enterprise Voice.
  
그룹 통화 Pickup을 사용하면 사용자가 자신의 휴대폰에서 동료에게 걸려오는 전화에 응답할 수 있습니다. 
  
 그룹 통화 선택에서 사용하는 구성 요소는 배포할 때 프런트 엔드 서버 또는 Standard Edition 서버에 자동으로 설치되고 Enterprise Voice. 그러나 사용자가 그룹 통화를 사용하려면 먼저 다음 단계를 사용하여 그룹 통화 선택을 구성해야 합니다.
  
**그룹 통화 Pickup 배포 프로세스**

|**작업 단계**|**단계**|**필수 그룹 및 역할**|**배포 설명서**|
|:-----|:-----|:-----|:-----|
|토폴로지에서 SEFAUtil 도구 사용|New-CsTrustedApplicationPool cmdlet을 사용하여 신뢰할 수 있는 새 응용 프로그램 풀을 만들 수 있습니다. 이 New-CsTrustedApplication cmdlet을 사용하여 SEFAUtil 도구를 신뢰할 수 있는 응용 프로그램으로 지정합니다. 토폴로지 Enable-CsTopology cmdlet을 실행합니다. 아직 설치하지 않은 경우 이 위치에서 비즈니스용 SKYPE 서버 버전의 SEFAUtil 도구를 다운로드하고 1단계에서 만든 신뢰할 수 있는 응용 프로그램 풀에 설치합니다. 배포에서 사용자의 통화 전달 설정을 표시하도록 SEFAUtil을 실행하여 올바르게 실행되고 있는지 확인합니다. |RTCUniversalServerAdmins  <br/> |[2016에서 SEFAUtil 도구 비즈니스용 Skype](deploy-the-sefautil-tool.md) <br/> [New-CsTrustedApplicationPool](/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps) </br>[New-CsTrustedApplication](/powershell/module/skype/new-cstrustedapplication?view=skype-ps)</br>[Enable-CsTopology](/powershell/module/skype/enable-cstopology?view=skype-ps) <br/> [비즈니스용 Skype 서버 2015 Resource Kit 도구 설명서.](../../management-tools/resource-kit-tools.md) 이 비즈니스용 Skype 서버 도구의 현재 버전을 사용해야 하지만 Lync Server 2013의 이 설명서는 계속 적용됩니다.  <br/> |
|통화 파크 궤도 테이블에서 통화 Pickup 번호 범위 구성  <br/> |**New-CSCallParkOrbit** cmdlet을 사용하여 통화 파킹된 통화 번호 테이블에 통화 선택 번호 범위를 만들고 통화 Pickup 범위에 **GroupPickup** 형식을 할당합니다.  <br/> 기존 다이얼 플랜과 원활하게 통합하기 위해 번호 범위는 일반적으로 가상 내선 번호 블록으로 구성됩니다. DID(Direct Inward Dialing) 번호를 통화 파킹된 통화 번호 테이블의 범위 번호로 할당하는 것은 지원되지 않습니다.  <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[그룹 통화 선택 번호 범위를 만들거나 비즈니스용 Skype](create-or-modify-a-group-call-pickup-number-range.md) <br/> |
|사용자에게 통화 선택 번호를 할당하고 사용자에 대해 그룹 통화 선택을 사용하도록 설정  <br/> |SEFAUtil 리소스 키트 도구의 /enablegrouppickup 매개 변수를 사용하여 그룹 통화 Pickup을 사용하도록 설정하고 사용자에게 통화 선택 번호를 할당합니다.  <br/> |-  <br/> |[사용자에 대해 그룹 통화 Pickup을 사용하도록 설정하고 사용자에 대해 그룹 번호를 비즈니스용 Skype](enable-group-call-pickup-for-users-and-assign-a-group-number.md) <br/> |
|사용자에게 할당된 통화 Pickup 번호 및 기타 관심사에 대해 알릴 수 있습니다.  <br/> |사용자에 대해 그룹 통화 수신을 사용하도록 설정한 후 전자 메일 또는 다른 메커니즘을 사용하여 사용자에게 통화 Pickup 그룹 번호를 알릴 수 있습니다. 사용자에게 모니터링할 그룹의 통화 Pickup 그룹 번호를 알릴 수 있습니다. 사용자가 같은 그룹에 있지 않은 경우에도 다른 사용자에 대한 통화를 검색할 수 있기 때문에 사용자는 여러 그룹에 대한 통화 Pickup 그룹 번호가 필요할 수 있습니다.  <br/> |-  <br/> ||
|그룹 통화 Pickup 배포 확인  <br/> | 통화 배치 및 검색을 테스트하여 구성이 예상대로 작동하는지 확인 최소한 다음을 확인해야 합니다. <br/>  그룹 통화 선택을 사용할 수 있는 사용자에게 전화를 걸고 다른 사용자가 통화를 검색하도록 합니다. 다른 사용자는 같은 그룹에 있을 수도, 다른 그룹에 있을 수도, 그룹 통화 선택을 사용할 수 없습니다. <br/>  그룹 통화 선택을 사용할 수 있는 사용자에게 전화를 걸고 통화에 응답하지 않습니다. <br/> |-  <br/> ||
