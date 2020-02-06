---
title: 사이트에 대 한 통화 허용 제어 관리
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
description: 네트워크 사이트는 호출 허용 제어 (CAC), E9-1-1, 미디어 바이패스 배포의 각 네트워크 영역 내에 있는 사무실 또는 위치입니다.
ms.openlocfilehash: ec2a3dda70bdd4b952169ca663ca271b76f98481
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817517"
---
# <a name="managing-call-admission-control-for-sites-in-skype-for-business-server"></a>비즈니스용 Skype에서 사이트에 대한 통화 허용 컨트롤 관리

네트워크 사이트는 호출 허용 제어 (CAC), E9-1-1, 미디어 바이패스 배포의 각 네트워크 영역 내에 있는 사무실 또는 위치입니다. 이 문서의 절차를 사용 하 여 네트워크 사이트에 대 한 통화 허용 제어를 구성 합니다.

## <a name="configure-network-site-links"></a>네트워크 사이트 링크 구성

CAC (call 허용 제어) 구성 내에서 직접 연결 된 사이트 간의 대역폭 제한을 정의 하는 네트워크 간 정책을 만들 수 있습니다. 네트워크 사이트에서 직접 링크를 공유 하는 경우 오디오 및 비디오 연결에 대 한 대역폭 제한이 해당 두 사이트 간에 정의 될 수 있습니다. 비즈니스용 Skype Server 제어판을 사용 하 여 네트워크 사이트 정책을 구성할 수는 없습니다 .이 작업은 비즈니스용 Skype 서버 관리 셸에서 cmdlet을 사용 하는 경우에만 가능 합니다. 비즈니스용 Skype 서버 관리 셸에서 네트워크 사이트 링크 (사이트 간 정책 라고도 함)를 만들고, 수정 하 고, 제거할 수 있습니다.

### <a name="to-create-a-network-site-link"></a>네트워크 사이트 링크를 만들려면

1.  비즈니스용 Skype 서버 관리 셸이 설치 되어 있는 컴퓨터에 RTCUniversalServerAdmins 그룹의 구성원 또는 필요한 사용자 권한을 사용 하 여 로그온 합니다.

2.  비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 서버**를 차례로 클릭 한 다음 비즈니스용 **skype server management shell**을 클릭 합니다.

3.  명령 프롬프트에서 다음 명령을 입력 하 고 구성에 유효한 값으로 대체 합니다.
    
        New-CsNetworkInterSitePolicy -Identity Reno_Portland -NetworkSiteID1 Reno -NetworkSiteID2 Portland -BWPolicyProfileID LowBWLimits
    
    이 예제에서는 Reno 및 포틀랜드 네트워크 사이트 간의 대역폭\_제한을 설정 하는 Reno 포틀랜드 이라는 새 네트워크 사이트 링크를 만듭니다. 네트워크 사이트 및 대역폭 정책 프로필은이 명령을 실행 하기 전에 이미 존재 해야 합니다.

자세한 매개 변수 설명은 [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy)을 참조 하세요. 네트워크 사이트 링크에 적용할 수 있는 대역폭 정책 프로필 목록을 검색 하려면 **CsNetworkBandwidthPolicyProfile** cmdlet을 호출 합니다. 자세한 내용은 [Get-help CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)을 참조 하세요.

### <a name="to-modify-a-network-site-link"></a>네트워크 사이트 링크를 수정 하려면

1.  비즈니스용 Skype 서버 관리 셸이 설치 되어 있는 컴퓨터에 RTCUniversalServerAdmins 그룹의 구성원 또는 필요한 사용자 권한을 사용 하 여 로그온 합니다.

2.  비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 서버**를 차례로 클릭 한 다음 비즈니스용 **skype server management shell**을 클릭 합니다.

3.  **Set-CsNetworkInterSitePolicy** cmdlet을 사용 하 여 지정 된 네트워크 사이트 링크의 속성을 수정 합니다. (또는 둘 다) 또는 연결 된 사이트를 수정할 수 있으며 링크와 연결 된 대역폭 정책 프로필을 수정할 수 있습니다. 다음은 Reno\_포틀랜드 라는 사이트 링크의 대역폭 정책 프로필을 수정 하는 예입니다.
    
        Set-CsNetworkInterSitePolicy -Identity Reno_Portland -BWPolicyProfileID HighBWLimits

자세한 매개 변수 설명은 [Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)을 참조 하세요.


### <a name="to-delete-a-network-site-link"></a>네트워크 사이트 링크를 삭제 하려면

1.  비즈니스용 Skype 서버 관리 셸이 설치 되어 있는 컴퓨터에 RTCUniversalServerAdmins 그룹의 구성원 또는 필요한 사용자 권한을 사용 하 여 로그온 합니다.

2.  비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 서버**를 차례로 클릭 한 다음 비즈니스용 **skype server management shell**을 클릭 합니다.

3.  네트워크 사이트 링크를 제거 하려면 **CsNetworkInterSitePolicy** cmdlet을 사용 합니다. 다음 예에서는 Reno\_포틀랜드 네트워크 사이트 링크를 삭제 합니다.
    
        Remove-CsNetworkInterSitePolicy -Identity Reno_Portland

자세한 매개 변수 설명은 [제거-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)을 참조 하세요.


## <a name="view-network-site-information"></a>네트워크 사이트 정보 보기

네트워크 사이트는 CAC (통화 허용 제어) 또는 향상 된 9-1-1 배포의 각 영역 내에서 구성 된 사무실 또는 위치입니다. 비즈니스용 Skype Server 제어판 또는 비즈니스용 Skype 서버 관리 셸에서는 네트워크 사이트 정보를 볼 수 있습니다. 

### <a name="to-view-network-site-information-in-skype-for-business-server-control-panel"></a>비즈니스용 Skype Server 제어판에서 네트워크 사이트 정보를 보려면

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다. 

3.  왼쪽 탐색 모음에서 **네트워크 구성을**클릭 한 다음 **사이트**를 클릭 합니다.

4.  **사이트** 페이지에서 보려는 사이트를 클릭 합니다.
 
    > [!NOTE]  
    > 한 번에 한 사이트의 정보만 볼 수 있습니다.

5.  **편집** 메뉴에서 **세부 정보 표시**를 클릭 합니다.


### <a name="viewing-network-site-information-by-using-windows-powershell-cmdlets"></a>Windows PowerShell cmdlet을 사용 하 여 네트워크 사이트 정보 보기

Windows PowerShell 및 Get-CsNetworkSite cmdlet을 사용 하 여 네트워크 사이트 정보를 볼 수 있습니다. 이 cmdlet은 비즈니스용 Skype 서버 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다. 

### <a name="to-view-network-site-information"></a>네트워크 사이트 정보를 보려면

  - 모든 네트워크 사이트에 대 한 정보를 보려면 비즈니스용 Skype 서버 관리 셸에서 다음 명령을 입력 한 다음 enter 키를 누릅니다.
    
        Get-CsNetworkSite
    
    이는 다음과 같은 정보를 반환 합니다.
    
        Identity          : Redmond
        NetworkSiteID     : Redmond
        Description       :
        NetworkRegionID   : Pacific Northwest
        BypassID          : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        BWPolicyProfileID :
        LocationPolicy    :

자세한 내용은 [Get CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite) cmdlet에 대 한 도움말 항목을 참조 하세요.


## <a name="create-or-modify-network-sites"></a>네트워크 사이트 만들기 또는 수정 

네트워크 사이트는 CAC (통화 허용 제어) 또는 향상 된 9-1-1 배포의 각 영역 내에서 구성 된 사무실 또는 위치입니다. 비즈니스용 Skype Server 제어판을 사용 하 여 사이트를 구성 하 고 지역을 연결할 수 있습니다. 예를 들어 북미, 레드먼드, Vancouver와 같은 네트워크 사이트에 북아메리카 네트워크 지역이 연결 되어 있을 수 있습니다. 사이트에 대 한 모든 사이트에 대해 CAC 네트워크 사이트를 만들어야 하는 경우에도 해당 사이트가 대역폭 제한 없이 구성 되어야 합니다. 비즈니스용 Skype Server 제어판에서 네트워크 사이트를 만들고, 수정 하 고, 삭제할 수 있습니다. 네트워크 사이트를 만들거나 수정 하려면 다음 절차를 사용 합니다. 

### <a name="to-create-a-network-site"></a>네트워크 사이트를 만들려면

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다. 

3.  왼쪽 탐색 모음에서 **네트워크 구성을**클릭 한 다음 **사이트**를 클릭 합니다.

4.  **사이트** 페이지에서 **새로 만들기**를 클릭 합니다.

5.  **새 사이트**의 **name (이름** ) 필드에이 사이트의 이름을 입력 합니다.

    > [!NOTE]  
    > 사이트 이름은 비즈니스용 Skype 서버 배포 내에서 고유 해야 합니다.

6.  **지역** 드롭다운 목록에서이 사이트와 연결할 네트워크 지역을 선택 합니다.

7.  ) 이 사이트에 대 한 오디오 또는 비디오 통화에 대 한 대역폭 제한을 설정 하려면 대역폭 **정책** 드롭다운 목록에서 적절 한 설정을 사용 하 여 대역폭 정책 프로필을 선택 합니다.
 
    > [!NOTE]  
    > **네트워크 구성** 그룹의 **정책 Profil** 페이지에서 사용 가능한 대역폭 정책 프로필의 세부 정보를 보거나 새 대역폭 정책 프로필을 만들 수 있습니다. 자세한 내용은 [네트워크 대역폭 정책 프로필 관리](managing-network-bandwidth-policy-profiles.md)를 참조 하세요.

8.  ) 이 사이트에 대 한 위치 설정을 제공 하려면 **위치 정책** 드롭다운 목록에서 위치 정책을 선택 합니다.

    > [!NOTE]  
    > 위치 정책은 사이트에 특정 향상 된 9-1-1 (E9-1-1) 및 클라이언트 위치 설정을 할당 합니다. **네트워크 구성** 그룹의 **위치 정책** 페이지에서 사용 가능한 위치 정책의 세부 정보를 보거나 새 위치 정책을 만들 수 있습니다. 

9.  ) 이름 만으로 표현할 수 없는이 사이트에 대 한 자세한 정보를 제공 하려면 **설명** 필드에 값을 입력 합니다.

10. **커밋**을 클릭합니다.

    > [!NOTE]  
    > 새 네트워크 사이트를 만들 때 **연결 된 서브넷** 테이블을 사용 하지 않습니다. 서브넷을 만들거나 수정할 때 서브넷을 사이트와 연결 합니다. 자세한 내용은 [네트워크 서브넷 관리](managing-network-subnets.md)를 참조 하세요.

### <a name="to-modify-a-network-site"></a>네트워크 사이트를 수정 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다. 

3.  왼쪽 탐색 모음에서 **네트워크 구성을**클릭 한 다음 **사이트**를 클릭 합니다.

4.  **사이트** 페이지에서 수정 하려는 사이트를 클릭 합니다.

5.  **편집** 메뉴에서 **세부 정보 표시**를 클릭 합니다.

6.  **사이트 편집** 페이지에서 설명, 지역, 대역폭 정책 프로필, 사이트와 연결 된 위치 정책을 수정할 수 있습니다. 자세한 내용은 위의 [네트워크 사이트 만들기를](#to-create-a-network-site) 참조 하세요.

7.  **커밋**을 클릭합니다.

이 페이지에서는 **연결 된 서브넷** 테이블을 수정할 수 없습니다. 사이트 설정을 수정할 때 어떤 서브넷에 영향을 미치는지 알 수 있도록 관련 서브넷 목록이 참조용으로 제공 됩니다.


## <a name="delete-an-existing-network-site"></a>기존 네트워크 사이트 삭제

네트워크 사이트는 CAC (통화 허용 제어) 또는 향상 된 9-1-1 배포의 각 영역 내에서 구성 된 사무실 또는 위치입니다. 비즈니스용 Skype Server 제어판을 사용 하 여 사이트를 구성 하 고 지역을 연결할 수 있습니다. 예를 들어 북미, 레드먼드, Vancouver와 같은 네트워크 사이트에 북아메리카 네트워크 지역이 연결 되어 있을 수 있습니다. 사이트에 대 한 모든 사이트에 대해 CAC 네트워크 사이트를 만들어야 하는 경우에도 해당 사이트가 대역폭 제한 없이 구성 되어야 합니다. 비즈니스용 Skype Server 제어판에서 네트워크 사이트를 만들고, 수정 하 고, 삭제할 수 있습니다. 다음 절차를 사용 하 여 기존 네트워크 사이트를 삭제 합니다. 네트워크 사이트를 만들거나 수정 하는 방법에 대 한 자세한 내용은 [사이트에 대 한 통화 허용 제어 관리](managing-call-admission-control-for-sites.md)를 참조 하세요.


### <a name="to-delete-a-network-site"></a>네트워크 사이트를 삭제 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다. 

3.  왼쪽 탐색 모음에서 **네트워크 구성을**클릭 한 다음 **사이트**를 클릭 합니다.

4.  **사이트** 페이지에서 삭제 하려는 사이트를 클릭 합니다.

    > [!NOTE]  
    > 한 번에 여러 사이트를 삭제할 수 있습니다. 이 작업을 수행 하려면 ctrl 키를 누른 채 여러 사이트를 선택 합니다. 또는 모든 사이트를 선택 하려면 **편집** 메뉴에서 **모두 선택을** 클릭 합니다.

5.  **편집** 메뉴에서 **삭제**를 클릭 합니다.

6.  **확인**을 클릭합니다.
    

    > [!WARNING]  
    > 네트워크 서브넷과 연결 된 네트워크 사이트는 제거할 수 없습니다. 서브넷과 연결 된 사이트를 제거 하려고 하면 오류 메시지가 표시 됩니다. 사이트가 서브넷과 연결 되어 있는지 확인 하려면 사이트를 클릭 한 다음 **편집** 메뉴에서 **자세한 정보 표시** 를 클릭 합니다.


## <a name="see-also"></a>참고 항목


[새로운 CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy) 
 
[Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)  

[제거-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)  

[Get-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterSitePolicy)  

[Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  

[새-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)

[집합-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSite)

[CsNetworkSite 사이트 제거](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSite)  

[Get-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite)  
