---
title: 향상된 9-1-1 및 위치 서비스 관리
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 비즈니스용 Skype 서버 비즈니스용 Skype 클라이언트에서 향상된 9-1-1(E9-1-1) 호출을 지원합니다. E9-1-1에 대한 비즈니스용 Skype 서버 구성하는 경우 비즈니스용 Skype 발생한 긴급 통화에는 위치 정보 서비스 데이터베이스의 ERL(긴급 대응 위치) 정보가 포함됩니다.
ms.openlocfilehash: 5b002e4043cb400b5f22a4b11bc70941a88abc2a
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65676010"
---
# <a name="manage-enhanced-9-1-1-and-the-location-service-in-skype-for-busines-server"></a>Busines 서버용 Skype 향상된 9-1-1 및 위치 서비스 관리

비즈니스용 Skype 서버 비즈니스용 Skype 클라이언트에서 향상된 9-1-1(E9-1-1) 호출을 지원합니다. E9-1-1에 대한 비즈니스용 Skype 서버 구성하는 경우 비즈니스용 Skype 발생한 긴급 통화에는 위치 정보 서비스 데이터베이스의 ERL(긴급 대응 위치) 정보가 포함됩니다. 이 문서의 절차를 사용하여 위치 정책을 관리합니다.

> [!Note]
> E9-1-1 및 위치 정보 서비스와 같은 고급 Enterprise Voice 기능 배포에 대한 자세한 내용은 [고급 Enterprise Voice 기능 배포](../deploy/deploy-enterprise-voice/deploy-advanced-enterprise-voice-features.md)를 참조하세요.

비즈니스용 Skype 서버 위치 정책을 사용하여 고급 9-1-1(E9-1-1) 기능과 관련된 설정과 사용자 또는 연락처의 위치 설정을 적용할 수 있습니다. 위치 정책은 사용자가 E9-1-1을 사용하도록 설정되어 있는지 여부를 확인하고, 설정된 경우 긴급 통화에 대한 동작을 결정합니다. 예를 들어 위치 정책을 사용하여 긴급 통화 번호(예: 한국의 경우 119), 회사 보안 부서에 자동으로 알림을 제공할지 여부 및 통화를 라우팅할 방법을 정의할 수 있습니다.

비즈니스용 Skype 서버 제어판 **네트워크 구성** 그룹에서 위치 정책을 구성할 수 있습니다. 비즈니스용 Skype 서버 제어판 위치 정책을 보거나, 만들고, 수정하거나, 삭제할 수 있습니다. 다음 절차에 따라 위치 정책에 대한 정보를 확인합니다. 


## <a name="view-location-policy-information"></a>위치 정책 정보 보기 

1.  RTCUniversalServerAdmins 그룹의 구성원이거나 동일한 사용자 권한이 있거나 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포의 모든 컴퓨터에 로그온합니다.

2.  브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판 엽니다. 

3.  왼쪽 탐색 모음에서 **네트워크 구성** 을 클릭한 다음 **위치 정책을** 클릭합니다.

4.  **위치 정책** 페이지에서 수정할 위치 정책을 선택합니다.

5.  **편집** 메뉴에서 **자세한 정보 표시** 를 클릭합니다.
 
    > [!NOTE]  
    > 한 번에 한 위치 정책에 대한 정보만 볼 수 있습니다.

글로벌이라는 단일 정책은 기본적으로 존재하며, 삭제하거나 이름을 바꿀 수 없습니다. 그러나 글로벌 정책을 수정할 수는 있습니다. 이 정책은 사이트 정책 또는 사용자별 정책을 만들지 않은 경우 모든 사용자 및 대화 상대에 적용됩니다. 사용자별 정책은 특정 사용자에게 적용해야 합니다.


## <a name="create-or-modify-a-location-policy"></a>위치 정책 만들기 또는 수정 

비즈니스용 Skype 서버 위치 정보 서비스에서 위치 업데이트에 대한 클라이언트 요청 간의 기본 시간을 재정의할 수 있습니다. 기본값은 4시간입니다. 기본값을 재정의하려면 LocationRefreshInterval 매개 변수를 포함하여 **Set-CsLocationPolicy** cmdlet을 사용합니다.


### <a name="to-create-a-new-location-policy-in-the-skype-for-business-server-control-panel"></a>비즈니스용 Skype 서버 제어판 새 위치 정책을 만들려면

1.  RTCUniversalServerAdmins 그룹의 구성원이거나 동일한 사용자 권한이 있거나 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포의 모든 컴퓨터에 로그온합니다.

2.  브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판 엽니다. 

3.  왼쪽 탐색 모음에서 **네트워크 구성** 을 클릭한 다음 **위치 정책을** 클릭합니다.

4.  **위치 정책** 페이지에서 **새로 만들기** 를 클릭하고 만들려는 정책의 유형을 선택합니다.
    
      - 사이트 정책을 만들려면 **사이트 정책** 을 클릭합니다. **사이트 선택** 에서 정책을 적용할 사이트를 선택하고 **확인** 을 클릭합니다. **새 위치 정책** 페이지의 **범위** 필드에는 **사이트** 값이 있고, **이름** 필드에는 선택한 사이트의 이름이 있습니다. 이러한 필드는 수정할 수 없습니다. 사이트 정책은 지정된 사이트의 모든 사용자에게 자동으로 적용되며 이러한 사용자에 대한 글로벌 정책을 재정의합니다.
    
      - **사용자 정책** 을 만들려면 **사용자 정책** 을 클릭합니다. **새 위치 정책** 의 **범위** 필드에는 **사용자** 값이 있습니다. 이 값은 수정할 수 없습니다. **이름** 필드에 이 정책의 이름을 입력합니다. 사용자 정책은 어떤 사용자에게도 자동으로 적용되지 않습니다. 사용자 정책을 만든 후 정책을 적용할 사용자 또는 네트워크 사이트에 정책을 수동으로 부여해야 합니다.

5.  나머지 필드를 다음과 같이 채웁니다.
    
      - **향상된 응급 서비스 사용**   E9-1-1에 대해 이 정책과 연결된 사용자를 사용하도록 설정하려면 이 확인란을 선택합니다. 응급 서비스를 사용하도록 설정하면 비즈니스용 Skype 서버 클라이언트는 등록에 대한 위치 정보를 검색하고 긴급 통화가 이루어질 때 해당 정보를 포함합니다.
    
      - **위치**   다음 값 중 하나를 지정합니다.
        
          - **필수**   새 위치에서 클라이언트를 등록할 때 사용자에게 위치 정보를 입력하라는 메시지가 나타납니다. 사용자는 정보를 입력하지 않고 프롬프트를 취소할 수 있습니다. 정보를 입력하면 긴급 통화가 걸려 온 경우 먼저 응급 서비스 공급자가 통화에 응답하여 위치를 확인한 후 PSAP(Public Safety Answering Point) 교환원(즉, 911 교환원)으로 통화가 라우팅됩니다.
        
          - **필요하지 않음**   사용자에게 위치를 묻는 메시지가 표시되지 않습니다. 위치 정보 없이 통화가 이루어지면 응급 서비스 공급자가 통화에 응답하고 위치를 묻습니다.
        
          - **면책 조항**   이 옵션은 사용자가 위치 정보를 입력하지 않고는 프롬프트를 해제할 수 없다는 점을 제외하고 **필수** 옵션과 동일합니다. 사용자는 여전히 긴급 통화를 완료할 수 있지만 정보를 입력하지 않고는 다른 통화를 완료할 수 없습니다. 또한 사용자에게 위치 정보 입력 거부의 결과에 대해 경고할 수 있는 고지 사항 텍스트가 표시됩니다. 고지 사항 텍스트를 설정하려면 비즈니스용 Skype 서버 관리 셸을 사용하여 EnhancedEmergencyServiceDisclaimer 매개 변수를 사용하여 **Set-CsLocationPolicy** cmdlet 또는 **New-CsLocationPolicy** cmdlet을 실행해야 합니다. 자세한 내용은 [Set-CsLocationPolicy](/powershell/module/skype/Set-CsLocationPolicy) 또는 [New-CsLocationPolicy를 참조하세요](/powershell/module/skype/New-CsLocationPolicy).
          
    
      - **응급 서비스에는 위치만 사용하고** 비즈니스용 Skype 다양한 이유로 위치 정보를 사용할 수 있습니다(예: 팀 동료에게 현재 위치를 알리기 위해). 위치 정보를 긴급 통화에만 사용할 수 있도록 하려면 이 확인란을 선택합니다.
    
      - **PSTN 사용**   이 프로필을 사용하는 클라이언트의 긴급 통화를 라우팅하는 데 사용될 음성 경로를 결정하는 데 사용할 공중 전화망(PSTN) 사용입니다. 이 사용과 연결된 경로는 긴급 통화 전용으로 지정된 SIP 트렁크 또는 가장 가까운 PSAP(Public Safety Answering Point)로 긴급 통화를 라우팅하는 ELIN(Emergency Location Identification Number) 게이트웨이를 가리켜야 합니다.
    
      - **긴급 전화 번호**   응급 서비스에 연결되는 번호입니다. 미국에서는 이 값이 911입니다. 이 문자열은 0에서 9 사이의 숫자로 구성되며 1자에서 10자 사이일 수 있습니다.
    
      - **긴급 전화 마스크**   이 번호로 걸려 온 전화는 긴급 전화 번호 값으로 변환됩니다. 예를 들어 긴급 전화 번호 필드의 값이 911이고 이 필드에 212 값을 입력한 경우 사용자가 212로 전화를 걸면 911로 연결됩니다. 이는 대체 긴급 번호로 전화를 걸어 응급 서비스와 통화할 수 있도록 합니다(예: 긴급 번호가 다른 국가 또는 지역의 사용자가 외국에서 해당 국가 또는 지역의 긴급 번호 대신 자신의 국가 또는 지역에서 사용되는 긴급 번호로 전화를 거는 경우). 값을 세미콜론으로 구분하여 여러 긴급 전화 마스크를 정의할 수 있습니다(예: 212;414). 최대 문자열 길이는 100자이고, 각 문자는 0에서 9사이의 숫자여야 합니다.
      

        > [!IMPORTANT]  
        > 지정된 다이얼 마스크 값은 통화 대기 파킹된 통화 번호 범위의 번호와 달라야 합니다. 통화 대기 라우팅은 긴급 전화 문자열 변환보다 우선합니다. 기존 통화 대기 파킹된 통화 번호 범위를 보려면 왼쪽 탐색 모음에서 **음성 기능** 을 클릭한 다음 **통화 대기** 를 클릭합니다. 

    
      - **알림 URI**   긴급 전화가 걸려 온 경우에 알림을 받을 하나 이상의 SIP URI(Uniform Resource Identifier)입니다. 예를 들어 회사의 보안 부서에서 긴급 전화가 걸려 올 때마다 인스턴트 메시지를 통해 알림을 받을 수 있습니다. 발신자의 위치를 파악할 수 있는 경우 해당 위치가 알림에 포함됩니다. 쉼표로 구분된 목록으로 여러 SIP URI를 포함할 수 있습니다. 예를 들면 "sip:security@litwareinc.com","sip:kmyer@litwareinc.com"과 같습니다. 메일 그룹도 지원됩니다. 이 문자열은 1자에서 256자 사이여야 하고 접두사 "sip:"로 시작해야 합니다. 알림 URI 필드를 클릭하기 전에 예가 표시됩니다.
    
      - **전화 회의 URI**   걸려 온 긴급 전화에 함께 응답할 제3자의 SIP URI(이 경우 전화 번호)입니다. 예를 들어 회사 보안 부서는 긴급 전화가 걸려 온 경우 **전화 회의 모드** 필드에 제공된 값에 따라 전화를 받고 통화 내용을 듣거나 참가할 수 있습니다. 이 문자열은 1자에서 256자 사이여야 하며 접두사 sip:로 시작해야 합니다. 이 필드를 클릭할 때까지 예가 표시됩니다.
    
      - **전화 회의 모드**   **전화 회의 URI** 필드에 값을 지정한 경우 **전화 회의 모드** 에 따라 제3자가 통화에 참가할 수 있는지 또는 통화 내용을 들을 수만 있는지가 결정됩니다. 다음 옵션 중 하나를 지정합니다.
        
          - **단방향**   제3자가 발신자와 PSAP 교환원 사이의 대화를 들을 수만 있습니다.
        
          - **양방향**   제3자가 발신자와 PSAP 교환원 사이의 대화를 듣고 통화에 참가할 수 있습니다.

6.  **커밋** 을 클릭합니다.


    > [!IMPORTANT]  
    > 사용자 정책을 만든 경우 처음에는 이 정책이 사용자 또는 네트워크 사이트에 적용되지 않습니다. 정책을 사용자에게 적용하려면 왼쪽 탐색 모음에서 **사용자** 를 클릭합니다. 그런 다음 정책을 적용할 사용자를 찾습니다. **편집** 메뉴에서 **자세한 정보 표시** 를 클릭합니다. **서버 사용자 편집** 페이지의 **위치 정책** 드롭다운 목록에서 새 위치 정책을 선택한 다음 **커밋** 을 클릭합니다.<BR>정책을 네트워크 사이트에 적용하려면 왼쪽 탐색 모음에서 **네트워크 구성** 을 클릭한 다음 **사이트** 를 클릭합니다. 그런 다음 정책을 적용할 네트워크 사이트를 찾습니다. **편집** 메뉴에서 **자세한 정보 표시** 를 클릭합니다. **사이트 편집** 의 **위치 정책** 드롭다운 목록에서 새 위치 정책을 선택한 다음 **커밋** 을 클릭합니다.


### <a name="to-modify-a-location-policy-in-the-skype-for-business-server-control-panel"></a>비즈니스용 Skype 서버 제어판 위치 정책을 수정하려면

1.  RTCUniversalServerAdmins 그룹의 구성원이거나 동일한 사용자 권한이 있거나 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포의 모든 컴퓨터에 로그온합니다.

2.  브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판 엽니다. 

3.  왼쪽 탐색 모음에서 **네트워크 구성** 을 클릭한 다음 **위치 정책을** 클릭합니다.

4.  **위치 정책** 페이지에서 수정할 위치 정책을 선택합니다.

5.  **편집** 메뉴에서 **자세한 정보 표시** 를 클릭합니다.

6.  **위치 정책 편집** 페이지에서 필요에 따라 필드를 수정합니다. 자세한 내용은 이 항목의 앞부분에 설명된 "새 위치 정책을 만들려면" 절차의 5단계를 참조하십시오.

7.  **커밋** 을 클릭합니다.

        
## <a name="delete-a-location-policy"></a>위치 정책 삭제


1.  RTCUniversalServerAdmins 그룹의 구성원이거나 동일한 사용자 권한이 있거나 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포의 모든 컴퓨터에 로그온합니다.

2.  브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판 엽니다. 

3.  왼쪽 탐색 모음에서 **네트워크 구성** 을 클릭한 다음 **위치 정책을** 클릭합니다.

4.  **위치 정책** 페이지에서 삭제할 위치 정책을 선택합니다.
   
    > [!NOTE]  
    > 한 번에 둘 이상의 위치 정책을 삭제할 수 있습니다. 이렇게 하려면 Ctrl 키를 누른 채 여러 정책을 선택합니다. 또는 모든 정책을 선택하려면 **편집** 메뉴에서 **모두 선택** 을 클릭합니다.


5.  **편집** 메뉴에서 **삭제** 를 클릭합니다.

6.  **확인** 을 클릭합니다.

    > [!IMPORTANT]  
    > 전역 위치 정책은 삭제할 수 없습니다. 글로벌 정책을 삭제하려고 하면 경고 메시지가 나타나고 해당 정책이 기본값으로 다시 설정됩니다.


## <a name="see-also"></a>참고 항목

[네트워크 사이트 만들기 또는 수정](network-management/call-admission-control/managing-call-admission-control-for-sites.md#create-or-modify-network-sites)

[New-CsLocationPolicy](/powershell/module/skype/New-CsLocationPolicy)  

[Set-CsLocationPolicy](/powershell/module/skype/Set-CsLocationPolicy) 
 
[Remove-CsLocationPolicy](/powershell/module/skype/Remove-CsLocationPolicy)  

[Get-CsLocationPolicy](/powershell/module/skype/Get-CsLocationPolicy)