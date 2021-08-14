---
title: 사이트에 대한 통화 참가 제어 관리
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
description: 네트워크 사이트는 CAC(통화 제어), E9-1-1 및 미디어 우회 배포의 각 네트워크 지역 내의 사무실 또는 위치입니다.
ms.openlocfilehash: fd353980e7ac2a367b05c0f0be6ce760b7102fcc
ms.sourcegitcommit: 97c2faab08ec9b8fc9967827883308733ec162ea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/13/2021
ms.locfileid: "58233673"
---
# <a name="managing-call-admission-control-for-sites-in-skype-for-business-server"></a>비즈니스용 Skype에서 사이트에 대한 통화 허용 컨트롤 관리

네트워크 사이트는 CAC(통화 제어), E9-1-1 및 미디어 우회 배포의 각 네트워크 지역 내의 사무실 또는 위치입니다. 이 문서의 절차에 따라 네트워크 사이트에 대한 통화 전송 제어를 구성합니다.

## <a name="configure-network-site-links"></a>네트워크 사이트 링크 구성

CAC(통화 허용 제어) 구성 내에서 직접 연결된 사이트 간의 대역폭 제한을 정의하는 네트워크 사이트 간 정책을 만들 수 있습니다. 네트워크 사이트에서 직접 링크를 공유하는 경우 이 두 사이트 간에 오디오 및 비디오 연결에 대한 대역폭 제한이 정의될 수 있습니다. 비즈니스용 Skype 서버 제어판을 사용하여 네트워크 사이트 정책을 구성할 수는 없습니다. 이 비즈니스용 Skype 서버 관리 셸의 cmdlet을 사용하여 이 비즈니스용 Skype 서버 있습니다. 관리 셸에서 네트워크 사이트 링크(네트워크 사이트 간 정책)를 만들고 수정하고 제거할 비즈니스용 Skype 서버 있습니다.

### <a name="to-create-a-network-site-link"></a>네트워크 사이트 링크를 만들려면

1.  RTCUniversalServerAdmins 비즈니스용 Skype 서버 또는 필요한 사용자 권한으로 관리 셸이 설치된 컴퓨터에 로그온합니다.

2.  관리 비즈니스용 Skype 서버 시작: **시작,** 모든 프로그램, 비즈니스용 Skype 서버 를 클릭한 다음 관리 **비즈니스용 Skype 서버 클릭합니다.** 

3.  명령 프롬프트에서 다음 명령을 입력하여 구성에 대해 올바른 값으로 대체합니다.
    
     **New-CsNetworkInterSitePolicy -Identity Reno_Portland -NetworkSiteID1 Reno -NetworkSiteID2 Portland -BWPolicyProfileID LowBWLimits**
    
    이 예제에서는 Reno 네트워크 사이트와 포틀랜드 네트워크 사이트 간의 대역폭 제한을 설정하는 Reno Portland라는 새 네트워크 사이트 링크를 \_ 만듭니다. 네트워크 사이트 및 대역폭 정책 프로필은 이 명령을 실행하기 전에 이미 있어야 합니다.

자세한 매개 변수 설명은 [New-CsNetworkInterSitePolicy를 참조하세요.](/powershell/module/skype/New-CsNetworkInterSitePolicy) 네트워크 사이트 링크에 적용할 수 있는 대역폭 정책 프로필 목록을 검색하려면 **Get-CsNetworkBandwidthPolicyProfile** cmdlet을 호출합니다. 자세한 내용은 [Get-CsNetworkBandwidthPolicyProfile을 참조합니다.](/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)

### <a name="to-modify-a-network-site-link"></a>네트워크 사이트 링크를 수정하려면

1.  RTCUniversalServerAdmins 비즈니스용 Skype 서버 또는 필요한 사용자 권한으로 관리 셸이 설치된 컴퓨터에 로그온합니다.

2.  관리 비즈니스용 Skype 서버 시작: **시작,** 모든 프로그램, 비즈니스용 Skype 서버 를 클릭한 다음 관리 **비즈니스용 Skype 서버 클릭합니다.** 

3.  **Set-CsNetworkInterSitePolicy** cmdlet을 사용하여 해당 네트워크 사이트 링크의 속성을 수정합니다. 연결된 사이트 중 하나(또는 둘 다)를 수정할 수 있으며 링크와 연결된 대역폭 정책 프로필을 수정할 수 있습니다. 다음은 Reno Portland라는 사이트 링크의 대역폭 정책 프로필을 수정하는 \_ 예입니다.
    
    **Set-CsNetworkInterSitePolicy -Identity Reno_Portland -BWPolicyProfileID HighBWLimits**

자세한 매개 변수 설명은 [Set-CsNetworkInterSitePolicy를 참조하세요.](/powershell/module/skype/Set-CsNetworkInterSitePolicy)


### <a name="to-delete-a-network-site-link"></a>네트워크 사이트 링크를 삭제하려면

1.  RTCUniversalServerAdmins 비즈니스용 Skype 서버 또는 필요한 사용자 권한으로 관리 셸이 설치된 컴퓨터에 로그온합니다.

2.  관리 비즈니스용 Skype 서버 시작: **시작,** 모든 프로그램, 비즈니스용 Skype 서버 를 클릭한 다음 관리 **비즈니스용 Skype 서버 클릭합니다.** 

3.  **Remove-CsNetworkInterSitePolicy** cmdlet을 사용하여 네트워크 사이트 링크를 제거합니다. 다음 예제에서는 Reno Portland 네트워크 사이트 \_ 링크를 삭제합니다.
    
    **Remove-CsNetworkInterSitePolicy -Identity Reno_Portland**

자세한 매개 변수 설명은 [Remove-CsNetworkInterSitePolicy를 참조하세요.](/powershell/module/skype/Remove-CsNetworkInterSitePolicy)


## <a name="view-network-site-information"></a>네트워크 사이트 정보 보기

네트워크 사이트는 CAC(통화 허용 제어) 또는 고급 9-1-1 배포의 각 지역 내에 구성된 사무실 또는 위치입니다. 네트워크 사이트 정보는 비즈니스용 Skype 서버 관리 셸에서 볼 비즈니스용 Skype 서버 있습니다. 

### <a name="to-view-network-site-information-in-skype-for-business-server-control-panel"></a>제어판에서 네트워크 사이트 비즈니스용 Skype 서버 표시

1.  RTCUniversalServerAdmins 그룹의 구성원 또는 이와 동등한 사용자 권한을 가졌다는 사용자 계정 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포의 컴퓨터에 로그온합니다.

2.  브라우저 창을 열고 관리 URL을 입력하여 관리 비즈니스용 Skype 서버 열 수 있습니다. 

3.  왼쪽 탐색 모음에서 네트워크 **구성을 클릭한** 다음 사이트를 **클릭합니다.**

4.  사이트 **페이지에서** 보게 할 사이트를 클릭합니다.
 
    > [!NOTE]
    > 한 사이트에 대한 정보만 한 번만 볼 수 있습니다.

5.  **편집** 메뉴에서 **자세한 정보 표시** 를 클릭합니다.


### <a name="viewing-network-site-information-by-using-windows-powershell-cmdlets"></a>cmdlet을 사용하여 네트워크 사이트 Windows PowerShell 보기

네트워크 사이트 정보 및 cmdlet을 사용하여 네트워크 Windows PowerShell 볼 Get-CsNetworkSite 있습니다. 이 cmdlet은 관리 셸 또는 비즈니스용 Skype 서버 원격 세션에서 실행할 수 Windows PowerShell. 

### <a name="to-view-network-site-information"></a>네트워크 사이트 정보를 보기 위해

  - 모든 네트워크 사이트에 대한 정보를 보시다시피 비즈니스용 Skype 서버 관리 셸에서 다음 명령을 입력한 다음 Enter를 눌러야 합니다.
    
    **Get-CsNetworkSite**
    
    그러면 다음과 같은 정보가 반환됩니다.
    
    ID : Redmond<br/>
    NetworkSiteID : Redmond<br/>
    설명 :<br/>
    NetworkRegionID : 태평양 북서부<br/>
    BypassID : 3b232b84-2c1d-4da2-8181-e9330bafebe9<br/>
    BWPolicyProfileID :<br/>
    LocationPolicy :<br/>

자세한 내용은 [Get-CsNetworkSite](/powershell/module/skype/Get-CsNetworkSite) cmdlet에 대한 도움말 항목을 참조하십시오.


## <a name="create-or-modify-network-sites"></a>네트워크 사이트 만들기 또는 수정 

네트워크 사이트는 CAC(통화 허용 제어) 또는 고급 9-1-1 배포의 각 지역 내에 구성된 사무실 또는 위치입니다. 사이트 제어판을 사용하여 비즈니스용 Skype 서버 구성하고 지역과 연결합니다. 예를 들어 북미 지역의 네트워크 지역은 Chicago, Redmond 및 Vancouver와 같은 네트워크 사이트와 연결할 수 있습니다. 대역폭 제한이 없는 사이트를 포함하여 조직 내의 모든 사이트에는 CAC 네트워크 사이트를 만들어야 합니다. 비즈니스용 Skype 서버 제어판에서 네트워크 사이트를 만들고 수정하고 삭제할 수 있습니다. 다음 절차에 따라 네트워크 사이트를 만들거나 수정합니다. 

### <a name="to-create-a-network-site"></a>네트워크 사이트를 만들려면

1.  RTCUniversalServerAdmins 그룹의 구성원 또는 이와 동등한 사용자 권한을 가졌다는 사용자 계정 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포의 컴퓨터에 로그온합니다.

2.  브라우저 창을 열고 관리 URL을 입력하여 관리 비즈니스용 Skype 서버 열 수 있습니다. 

3.  왼쪽 탐색 모음에서 네트워크 **구성을 클릭한** 다음 사이트를 **클릭합니다.**

4.  **사이트** 페이지에서 **다음** 을 클릭합니다.

5.  **새 사이트** 에서 **이름** 필드에 해당 사이트의 이름을 입력합니다.

    > [!NOTE]  
    > 사이트 이름은 사이트 배포에서 고유해야 비즈니스용 Skype 서버 합니다.

6.  **지역** 드롭다운 목록에서 이 사이트에 연결할 네트워크 지역을 선택합니다.

7.  (선택 사항) 이 사이트에 대한 오디오 또는 비디오 통화에 대역폭 제한을 적용하려면 **대역폭 정책** 드롭다운 목록에서 적절한 설정이 포함된 대역폭 정책 프로필을 선택합니다.
 
    > [!NOTE]  
    > 네트워크 구성 그룹의 정책 프로파일 페이지에서 사용 가능한 대역폭 정책 프로필의 세부  정보를 보거나 새 대역폭 정책 프로필을 만들 **수** 있습니다. 자세한 내용은 [Managing network bandwidth policy profiles를 참조하세요.](managing-network-bandwidth-policy-profiles.md)

8.  (선택 사항) 이 사이트에 대해 위치 설정을 제공하려면 **위치 정책** 드롭다운 목록에서 위치 정책을 선택합니다.

    > [!NOTE]  
    > 위치 정책은 사이트에 특정 E9-1-1(고급 9-1-1) 및 클라이언트 위치 설정을 할당합니다. **네트워크 구성** 그룹의 **위치 정책** 페이지에서 사용 가능한 위치 정책의 세부 정보를 보거나 새 위치 정책을 만들 수 있습니다. 

9.  (선택 사항) 이름만으로는 표현할 수 없는 이 사이트에 대한 자세한 정보를 제공하려면 **설명** 필드에 값을 입력합니다.

10. **커밋** 을 클릭합니다.

    > [!NOTE]  
    > 새 네트워크 사이트를 만들 때는 **연결된 서브넷** 표를 사용하지 않습니다. 서브넷을 만들거나 수정할 때 서브넷을 사이트에 연결합니다. 자세한 내용은 [Managing network subnets를 참조합니다.](managing-network-subnets.md)

### <a name="to-modify-a-network-site"></a>네트워크 사이트를 수정하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 또는 이와 동등한 사용자 권한을 가졌다는 사용자 계정 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포의 컴퓨터에 로그온합니다.

2.  브라우저 창을 열고 관리 URL을 입력하여 관리 비즈니스용 Skype 서버 열 수 있습니다. 

3.  왼쪽 탐색 모음에서 네트워크 **구성을 클릭한** 다음 사이트를 **클릭합니다.**

4.  **사이트** 페이지에서 수정할 사이트를 클릭합니다.

5.  **편집** 메뉴에서 **자세한 정보 표시** 를 클릭합니다.

6.  **사이트 편집** 페이지에서 사이트에 연결된 위치 정책, 대역폭 정책 프로필, 지역 및 설명을 수정할 수 있습니다. 자세한 내용은 위의 네트워크 [사이트를 만들 수 있습니다.를](#to-create-a-network-site) 참조하세요.

7.  **커밋** 을 클릭합니다.

이 페이지의 **연결된 서브넷** 표는 수정할 수 없습니다. 연결된 서브넷 목록은 사이트 설정 수정 시 영향을 받는 서브넷을 확인할 수 있도록 참조용으로 제공됩니다.


## <a name="delete-an-existing-network-site"></a>기존 네트워크 사이트 삭제

네트워크 사이트는 CAC(통화 허용 제어) 또는 고급 9-1-1 배포의 각 지역 내에 구성된 사무실 또는 위치입니다. 사이트 제어판을 사용하여 비즈니스용 Skype 서버 구성하고 지역과 연결합니다. 예를 들어 북미 지역의 네트워크 지역은 Chicago, Redmond 및 Vancouver와 같은 네트워크 사이트와 연결할 수 있습니다. 대역폭 제한이 없는 사이트를 포함하여 조직 내의 모든 사이트에는 CAC 네트워크 사이트를 만들어야 합니다. 비즈니스용 Skype 서버 제어판에서 네트워크 사이트를 만들고 수정하고 삭제할 수 있습니다. 다음 절차에 따라 기존 네트워크 사이트를 삭제합니다. 네트워크 사이트를 만들거나 수정하는 데 대한 자세한 내용은 [Managing call admission control for sites를 참조합니다.](managing-call-admission-control-for-sites.md)


### <a name="to-delete-a-network-site"></a>네트워크 사이트를 삭제하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 또는 이와 동등한 사용자 권한을 가졌다는 사용자 계정 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포의 컴퓨터에 로그온합니다.

2.  브라우저 창을 열고 관리 URL을 입력하여 관리 비즈니스용 Skype 서버 열 수 있습니다. 

3.  왼쪽 탐색 모음에서 네트워크 **구성을 클릭한** 다음 사이트를 **클릭합니다.**

4.  **사이트** 페이지에서 삭제할 사이트를 클릭합니다.

    > [!NOTE]  
    > 한 번에 둘 이상의 사이트를 삭제할 수 있습니다. 이렇게 하려면 Ctrl 키를 누른 상태에서 여러 사이트를 선택합니다. 또는 모든 사이트를 선택하려면 **편집** 메뉴에서 **모두 선택** 을 클릭합니다.

5.  **편집** 메뉴에서 **삭제** 를 클릭합니다.

6.  **확인** 을 클릭합니다.
    

    > [!WARNING]  
    > 네트워크 서브넷과 연결된 네트워크 사이트는 제거할 수 없습니다. 서브넷과 연결된 사이트를 제거하려고 시도하면 오류 메시지가 표시됩니다. 사이트가 서브넷에 연결되어 있는지 확인하려면 **편집** 메뉴에서 **자세한 정보 표시** 를 클릭합니다.


## <a name="see-also"></a>참고 항목


[New-CsNetworkInterSitePolicy](/powershell/module/skype/New-CsNetworkInterSitePolicy) 
 
[Set-CsNetworkInterSitePolicy](/powershell/module/skype/Set-CsNetworkInterSitePolicy)  

[Remove-CsNetworkInterSitePolicy](/powershell/module/skype/Remove-CsNetworkInterSitePolicy)  

[Get-CsNetworkInterSitePolicy](/powershell/module/skype/Get-CsNetworkInterSitePolicy)  

[Get-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  

[New-CsNetworkSite](/powershell/module/skype/New-CsNetworkSite)

[Set-CsNetworkSite](/powershell/module/skype/Set-CsNetworkSite)

[Remove-CsNetworkSite](/powershell/module/skype/Remove-CsNetworkSite)  

[Get-CsNetworkSite](/powershell/module/skype/Get-CsNetworkSite)