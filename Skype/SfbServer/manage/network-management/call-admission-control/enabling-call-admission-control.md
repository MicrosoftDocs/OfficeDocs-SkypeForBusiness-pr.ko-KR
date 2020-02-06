---
title: 통화 허용 제어 사용
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: " CAC (call 허용 컨트롤) 네트워크를 구성한 후에는 CAC를 사용 하도록 설정 하 여 대역폭 제한을 적용 해야 합니다."
ms.openlocfilehash: 4f9f3f09f943b417ec589f26dc5c6505d30831f9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817537"
---
# <a name="enabling-call-admission-control-in-skype-for-business-server"></a>비즈니스용 Skype에서 통화 허용 컨트롤을 사용하도록 설정

CAC(통화 허용 제어)는 사용 가능한 대역폭을 기반으로 오디오 및 비디오 전송에 제한을 둘 수 있는 지역, 사이트 및 서브넷의 네트워크입니다. CAC 네트워크를 구성한 후에는 CAC가 대역폭 제한을 적용 하도록 설정 해야 합니다. 비즈니스용 Skype 서버 제어판을 사용 하 여이 작업을 수행할 수 있습니다.


## <a name="to-enable-cac-from-the-skype-for-business-server-control-panel"></a>비즈니스용 Skype 서버 제어판에서 CAC를 사용 하도록 설정 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다. 

3.  왼쪽 탐색 모음에서 **네트워크 구성을**클릭 한 다음 **전역**을 클릭 합니다.

4.  **전역** 페이지에서 **전역** 구성을 클릭 합니다.
   
    > [!NOTE]  
    > 모든 비즈니스용 Skype 서버 배포에 대해 하나의 네트워크만 구성할 수 있으므로, 두 개 이상의 네트워크 구성은 목록에 표시 되지 않습니다. 전역 구성의 이름은 바꿀 수 없습니다.

5.  **편집** 메뉴에서 **세부 정보 표시**를 클릭 합니다.

6.  **전역 설정 편집** 페이지에서 **통화 허용 제어 사용** 확인란을 선택한 다음 **커밋을**클릭 합니다.

**커밋을**클릭 하면 구성 테스트를 실행 합니다. **전역 설정 편집** 대화 상자가 닫히고 **전역** 페이지로 돌아갑니다. 네트워크 구성에서 오류 또는 불일치가 검색 되어 제대로 작동 하지 않는 경우 (예: 모든 지역이 서로 다른 지역 경로를 통해 모든 지역에 연결 되어 있지 않은 경우) 경고가 표시 됩니다.

네트워크 구성을 변경할 경우 전역 구성을 열고 **커밋을**클릭 하 여 유효성 검사를 다시 실행할 수 있습니다. CAC를 먼저 사용 하지 않도록 설정할 필요는 없습니다. 확인란을 선택한 상태로 두고 **커밋을**클릭 합니다. 구성을 변경 하지 않고 언제 든 지이 작업을 수행할 수 있습니다.

## <a name="see-also"></a>참고 항목

[통화 허용 제어 계획](../../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md) 
 
[통화 허용 컨트롤 사용](../../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) 

[Get-Set-csnetworkconfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkConfiguration)  

[Set-Set-csnetworkconfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkConfiguration)  

[제거-Set-csnetworkconfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkConfiguration)  
