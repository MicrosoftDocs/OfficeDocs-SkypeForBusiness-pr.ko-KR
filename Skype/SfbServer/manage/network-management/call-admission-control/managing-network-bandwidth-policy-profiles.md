---
title: 네트워크 대역폭 정책 프로필 관리
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 이 문서의 절차를 사용 하 여 네트워크 대역폭 정책 프로필을 보고, 만들고, 수정 하 고, 삭제할 수 있습니다.
ms.openlocfilehash: 3b2b62e5e823a9d86f1884d79b67483bce38a39f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188577"
---
# <a name="managing-network-bandwidth-policy-profiles-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 네트워크 대역폭 정책 프로필 관리

이 문서의 절차를 사용 하 여 네트워크 대역폭 정책 프로필을 보고, 만들고, 수정 하 고, 삭제할 수 있습니다.

## <a name="view-network-bandwidth-policy-profile-information"></a>네트워크 대역폭 정책 프로필 정보 보기

호출 허용 제어 (CAC)의 일부로 대역폭 정책은 특정 형식을 대역폭 제한을 정의 하는 데 사용 됩니다. 비즈니스용 Skype 서버에서 오디오 및 비디오 형식을 대역폭 제한을 할당할 수 있습니다. 전체 대역폭 제한 및 세션 제한을 설정할 수 있습니다. 비즈니스용 Skype Server 제어판을 사용 하 여 이러한 정책에 대 한 컨테이너 프로필을 만들거나 수정 하거나 삭제할 수 있습니다. 각 대역폭 정책 프로필을 하나 이상의 네트워크 사이트와 연결할 수 있습니다. 다음 절차를 사용 하 여 대역폭 정책 프로필을 봅니다. 

### <a name="to-view-a-bandwidth-policy-profile"></a>대역폭 정책 프로필을 보려면

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다. 

3.  왼쪽 탐색 모음에서 **네트워크 구성을** 클릭 한 다음 **대역폭 정책을**클릭 합니다.

4.  **대역폭 정책** 페이지에서 보려는 대역폭 정책 프로필을 클릭 합니다.

5.  **편집** 메뉴에서 **세부 정보 표시**를 클릭 합니다.


### <a name="viewing-network-bandwidth-policy-profile-information-by-using-windows-powershell-cmdlets"></a>Windows PowerShell cmdlet을 사용 하 여 네트워크 대역폭 정책 프로필 정보 보기

네트워크 대역폭 프로필은 Windows PowerShell 및 CsNetworkBandwidthPolicyProfile cmdlet을 사용 하 여 볼 수 있습니다. 이 cmdlet은 비즈니스용 Skype 서버 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다. 


### <a name="to-view-network-bandwidth-policy-profile-information"></a>네트워크 대역폭 정책 프로필 정보를 보려면

  - 모든 네트워크 대역폭 정책 프로필에 대 한 정보를 보려면 비즈니스용 Skype 서버 관리 셸에서 다음 명령을 입력 한 다음 enter 키를 누릅니다.
    
        Get-CsNetworkBandwidthPolicyProfile
    
    이는 다음과 같은 정보를 반환 합니다.
    
        Identity          : RedmondBandwidthPolicy
        BWPolicy          : {BWLimit=200;BWSessionLimit=200;
                            BWPolicyModality=Audio, 
                            BWLimit=1400;BWSessionLimit=500;
                            BWPolicyModality=Video}
        BWPolicyProfileID : RedmondBandwidthPolicy
        Description       :


자세한 내용은 Get-help cmdlet에 대 한 도움말 항목 [CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) 을 참조 하세요.


## <a name="create-or-modify-bandwidth-policy-profiles"></a>대역폭 정책 프로필 만들기 또는 수정

호출 허용 제어 (CAC)의 일부로 대역폭 정책은 특정 형식을 대역폭 제한을 정의 하는 데 사용 됩니다. 비즈니스용 Skype 서버에서 오디오 및 비디오 형식을 대역폭 제한을 할당할 수 있습니다. 전체 대역폭 제한 및 세션 제한을 설정할 수 있습니다. 비즈니스용 Skype Server 제어판을 사용 하 여 이러한 정책에 대 한 컨테이너 프로필을 만들거나 수정 하거나 삭제할 수 있습니다. 각 대역폭 정책 프로필을 하나 이상의 네트워크 사이트와 연결할 수 있습니다. 다음 절차를 사용 하 여 대역폭 정책 프로필을 만들거나 수정 합니다. 

### <a name="to-create-a-new-bandwidth-policy-profile"></a>새 대역폭 정책 프로필을 만들려면

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다. 

3.  왼쪽 탐색 모음에서 **네트워크 구성을**클릭 한 다음 **대역폭 정책을**클릭 합니다.

4.  **대역폭 정책** 페이지에서 **새로 만들기**를 클릭 합니다.

5.  **새 대역폭 정책 프로필**의 **이름** 필드에 이름을 입력 합니다. 이 이름은 모든 대역폭 정책 프로필에서 고유 해야 합니다.

6.  **오디오 제한** 필드에 숫자 값을 입력 합니다. 이 값은 모든 오디오 연결에 할당할 수 있는 대역폭의 최대 양 (kbps로 표시 됨)입니다.

7.  **오디오 세션 제한** 필드에 숫자 값을 입력 합니다. 이 값은 kbps로 표시 되는 개별 오디오 연결에 할당할 수 있는 대역폭의 최대 양입니다. 이 값은 40 이상 이어야 합니다.

8.  **비디오 제한** 필드에 숫자 값을 입력 합니다. 이 값은 모든 비디오 연결에 할당할 수 있는 대역폭의 최대 양 (kbps)입니다.

9.  **비디오 세션 제한** 필드에 숫자 값을 입력 합니다. 이 값은 kbps로 표시 되는 개별 비디오 연결에 할당할 수 있는 대역폭의 최대 양입니다. 이 값은 100 이상 이어야 합니다.

10. ) 이름 만으로 표현할 수 없는이 대역폭 정책 프로필에 대 한 자세한 정보를 제공 하려면 **설명** 필드에 값을 입력 합니다.

11. **커밋**을 클릭합니다.

    > [!NOTE]  
    > 새 대역폭 정책 프로필을 만들면 자동으로 대역폭 제한이 적용 되지는 않습니다. 먼저 정책 프로필을 사이트와 연결 해야 합니다. 


### <a name="to-modify-a-bandwidth-policy-profile"></a>대역폭 정책 프로필을 수정 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다. 

3.  왼쪽 탐색 모음에서 **네트워크 구성을**클릭 한 다음 **대역폭 정책을**클릭 합니다.

4.  **대역폭 정책** 페이지에서 수정 하려는 대역폭 정책 프로필을 클릭 합니다.

5.  **편집** 메뉴에서 **세부 정보 표시**를 클릭 합니다.

6.  **대역폭 정책 프로필 편집** 페이지에서 필요에 따라 필드를 수정 합니다 (자세한 내용은 [새 대역폭 정책 프로필 만들기](#to-create-a-new-bandwidth-policy-profile)참조).

7.  **커밋**을 클릭합니다.

    > [!NOTE]  
    > 대역폭 정책 프로필을 수정 하면이 대역폭 정책 프로필에 연결 된 모든 네트워크 사이트의 대역폭 제한이 즉시 업데이트 됩니다.

  
## <a name="delete-network-bandwidth-policy-profiles"></a>네트워크 대역폭 정책 프로필 삭제

호출 허용 제어 (CAC)의 일부로 대역폭 정책은 특정 형식을 대역폭 제한을 정의 하는 데 사용 됩니다. 비즈니스용 Skype 서버에서 오디오 및 비디오 형식을 대역폭 제한을 할당할 수 있습니다. 전체 대역폭 제한 및 세션 제한을 설정할 수 있습니다. 비즈니스용 Skype Server 제어판을 사용 하 여 이러한 정책에 대 한 컨테이너 프로필을 만들거나 수정 하거나 삭제할 수 있습니다. 네트워크 대역폭 정책 프로필을 삭제 하려면 다음 절차를 사용 합니다. 

### <a name="to-delete-a-bandwidth-policy-profile"></a>대역폭 정책 프로필을 삭제 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다. 

3.  왼쪽 탐색 모음에서 **네트워크 구성을**클릭 한 다음 **대역폭 정책을**클릭 합니다.

4.  **대역폭 정책** 페이지에서 삭제 하려는 대역폭 정책 프로필을 클릭 합니다.

    > [!NOTE]  
    > 한 번에 여러 프로필을 삭제할 수 있습니다. 이 작업을 수행 하려면 ctrl 키를 누른 채 여러 프로필을 선택 합니다. 또는 모든 프로필을 선택 하려면 **편집** 메뉴에서 **모두 선택을** 클릭 합니다.

5.  **편집** 메뉴에서 **삭제**를 클릭 합니다.
   

    > [!WARNING]  
    > 네트워크 사이트와 연결 된 대역폭 정책 프로필은 삭제할 수 없습니다. 프로필을 삭제 하려면 먼저 네트워크 사이트와의 연결을 제거 해야 합니다. 


## <a name="see-also"></a>참고 항목

[사이트에 대 한 통화 허용 제어 관리](managing-call-admission-control-for-sites.md)
 
[새로운 CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)  

[Set-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)  

[Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  

[제거-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)  
  

