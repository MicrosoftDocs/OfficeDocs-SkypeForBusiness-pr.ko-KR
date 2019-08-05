---
title: 비즈니스용 Skype의 그룹 통화 픽업 배포 프로세스
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 082daeac-e667-4e2d-b78d-8e0901f9f0e9
description: 비즈니스용 Skype Server Enterprise Voice의 그룹 통화 픽업 배포 프로세스 및 단계
ms.openlocfilehash: f493c3c83f3fa703dd5f62989f4f2e444e83ed5d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36191700"
---
# <a name="deployment-process-for-group-call-pickup-in-skype-for-business"></a>비즈니스용 Skype의 그룹 통화 픽업 배포 프로세스
 
비즈니스용 Skype Server Enterprise Voice의 그룹 통화 픽업 배포 프로세스 및 단계
  
그룹 통화 픽업 사용자는 자신의 전화기에서 자신의 동료에 게 걸려오는 전화를 받을 수 있습니다. 
  
 그룹 통화 픽업이 사용 하는 구성 요소는 엔터프라이즈 음성을 구축할 때 프런트 엔드 서버 또는 Standard Edition 서버에서 자동으로 설치 되 고 사용 하도록 설정 됩니다. 그러나 사용자가 사용할 수 있으려면 먼저 다음 단계를 사용 하 여 그룹 통화 픽업을 구성 해야 합니다.
  
**그룹 통화 픽업 배포 프로세스**

|**단계의**|**방법은**|**필수 그룹 및 역할**|**배포 설명서**|
|:-----|:-----|:-----|:-----|
|토폴로지에서 SEFAUtil 도구 사용|새 CsTrustedApplicationPool cmdlet을 사용 하 여 신뢰할 수 있는 새 응용 프로그램 풀을 만듭니다. 새 CsTrustedApplication cmdlet을 사용 하 여 SEFAUtil 도구를 신뢰할 수 있는 응용 프로그램으로 지정 합니다. Enable-CsTopology cmdlet을 실행 하 여 토폴로지를 사용 하도록 설정 합니다. 아직 없는 경우 비즈니스용 Skype 서버 버전을이 위치에서 다운로드 하 고 1 단계에서 만든 신뢰할 수 있는 응용 프로그램 풀에 설치 합니다. 배포에 있는 사용자의 착신 전환 설정을 표시 하려면 SEFAUtil를 실행 하 여 제대로 실행 중인지 확인 합니다. |RTCUniversalServerAdmins  <br/> |[비즈니스용 Skype에서 SEFAUtil 도구 배포](deploy-the-sefautil-tool.md) <br/> [새로운 CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps) </br>[새로운 CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplication?view=skype-ps)</br>[Enable-CsTopology](https://docs.microsoft.com/powershell/module/skype/enable-cstopology?view=skype-ps) <br/> [비즈니스용 Skype 서버 2015 리소스 키트 도구 문서](../../management-tools/resource-kit-tools.md). (비즈니스용 Skype 서버용) 현재 버전의 도구를 사용 해야 하지만 Lync Server 2013의이 문서는 여전히 적용 됩니다.  <br/> |
|통화 공원에서 통화 픽업 번호 범위 구성 표  <br/> |**CSCallParkOrbit** cmdlet을 사용 하 여 통화 공원 표 안에 통화 픽업 번호 범위를 만들고 통화 픽업 범위에 **grouppickup**형식을 지정 합니다.  <br/> 기존 다이얼 플랜에 대 한 원활한 통합을 위해 숫자 범위가 일반적으로 가상 확장 블록으로 구성 됩니다. 직접 연결 된 전화 접속 (a) 번호를 통화 공원 궤도 테이블의 범위 번호로 지정 하는 것은 지원 되지 않습니다.  <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[비즈니스용 Skype에서 그룹 통화 픽업 번호 범위 만들기 또는 수정](create-or-modify-a-group-call-pickup-number-range.md) <br/> |
|사용자에 게 통화 픽업 번호를 할당 하 고 사용자를 위해 그룹 통화 픽업 기능을 사용 하도록 설정  <br/> |SEFAUtil resource kit 도구의/enablegrouppickup 매개 변수를 사용 하 여 그룹 통화 픽업 기능을 사용 하도록 설정 하 고 사용자에 게 통화 픽업 번호를 할당 합니다.  <br/> |-  <br/> |[비즈니스용 Skype에서 그룹 통화 픽업으로 사용자를 설정 하 고 그룹 번호를 할당 합니다.](enable-group-call-pickup-for-users-and-assign-a-group-number.md) <br/> |
|사용자에 게 할당 된 통화 픽업 번호와 기타 관심 있는 수에 대해 알림  <br/> |사용자를 위해 그룹 통화 픽업을 사용 하도록 설정한 후에는 전자 메일 또는 기타 메커니즘을 사용 하 여 사용자에 게 통화 픽업 그룹 번호를 알립니다. 사용자에 게 모니터링 하려는 모든 그룹에 대 한 통화 픽업 그룹 번호를 알립니다. 사용자는 같은 그룹에 속하지 않더라도 다른 사용자에 대 한 통화를 검색할 수 있으므로 사용자는 여러 그룹에 대 한 통화 픽업 그룹 번호가 필요할 수 있습니다.  <br/> |-  <br/> ||
|그룹 통화 픽업 배포 확인  <br/> | 호출을 배치 하 고 검색 하 여 구성이 예상 대로 작동 하는지 확인 합니다. 최소한 다음 사항을 확인 하세요. <br/>  그룹 통화 픽업 기능을 사용 하도록 설정 된 사용자에 게 전화를 걸고 다른 사용자가 통화를 검색 하도록 합니다. 다른 사용자는 같은 그룹에 있거나 다른 그룹에 있거나 그룹 통화 픽업 사용이 설정 되어 있지 않을 수 있습니다. <br/>  그룹 통화 픽업으로 설정 된 사용자에 게 전화를 걸고 전화를 받지 않습니다. <br/> |-  <br/> ||
   

