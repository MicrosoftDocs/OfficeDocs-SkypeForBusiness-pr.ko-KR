---
title: 통화 입장 제어 사용
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
description: " CAC(통화 제어) 네트워크를 구성한 후 대역폭 제한을 적용하려면 CAC를 사용하도록 설정해야 합니다."
ms.openlocfilehash: 86a3cbead644ac265fc29d15c4ee9167bb214925c9176f9dfd11efe89df12079
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54313006"
---
# <a name="enabling-call-admission-control-in-skype-for-business-server"></a>비즈니스용 Skype에서 통화 허용 컨트롤을 사용하도록 설정

CAC(통화 허용 제어)는 사용 가능한 대역폭을 기반으로 오디오 및 비디오 전송에 제한을 둘 수 있는 지역, 사이트 및 서브넷의 네트워크입니다. CAC 네트워크를 구성한 후에는 대역폭 제한을 적용할 수 있도록 CAC를 설정해야 합니다. 이 작업을 위해 비즈니스용 Skype 서버 수 있습니다.


## <a name="to-enable-cac-from-the-skype-for-business-server-control-panel"></a>제어판에서 CAC를 비즈니스용 Skype 서버

1.  RTCUniversalServerAdmins 그룹의 구성원 또는 이와 동등한 사용자 권한을 가졌다는 사용자 계정 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포의 컴퓨터에 로그온합니다.

2.  브라우저 창을 열고 관리 URL을 입력하여 관리 비즈니스용 Skype 서버 열 수 있습니다. 

3.  왼쪽 탐색 모음에서 네트워크 **구성을 클릭한** 다음 전역 을 **클릭합니다.**

4.  **전역** 페이지에서 **전역** 구성을 클릭합니다.
   
    > [!NOTE]  
    > 모든 배포에 대해 하나의 네트워크만 구성할 비즈니스용 Skype 서버 수 있으므로 목록에 네트워크 구성이 두 개 이상 있는 것은 아닙니다. 전역 구성은 이름을 바꿀 수 없습니다.

5.  **편집** 메뉴에서 **자세한 정보 표시** 를 클릭합니다.

6.  **전역 설정 편집** 페이지에서 **통화 허용 제어 사용** 확인란을 선택하고 **커밋** 을 클릭합니다.

**커밋** 을 클릭하면 구성 테스트가 실행됩니다. **전역 설정 편집** 대화 상자가 닫히고 **전역** 페이지로 돌아갑니다. 네트워크 구성에서 오류나 불일치 사항이 검색되어 구성이 제대로 작동하지 않는 경우(예: 모든 지역이 지역 간 경로를 통해 다른 모든 지역에 연결되어 있지 않은 경우)에는 경고가 표시됩니다.

네트워크 구성을 변경하는 경우 전역 구성을 열고 **커밋** 을 클릭하여 유효성 검사를 실행할 수 있습니다. 먼저 CAC를 사용하지 않도록 설정할 필요는 없으며, 확인란을 선택한 대로 두고 **커밋** 을 클릭하면 됩니다. 구성을 변경하지 않아도 언제든지 이 검사를 수행할 수 있습니다.

## <a name="see-also"></a>참고 항목

[통화 수당 제어 계획](../../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md) 
 
[통화 허용 컨트롤 사용](../../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) 

[Get-CsNetworkConfiguration](/powershell/module/skype/Get-CsNetworkConfiguration)  

[Set-CsNetworkConfiguration](/powershell/module/skype/Set-CsNetworkConfiguration)  

[Remove-CsNetworkConfiguration](/powershell/module/skype/Remove-CsNetworkConfiguration)