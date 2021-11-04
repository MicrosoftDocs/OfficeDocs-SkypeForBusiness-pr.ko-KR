---
title: 네트워크 대역폭 정책 프로필 관리
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 이 문서의 절차에 따라 네트워크 대역폭 정책 프로필을 보거나, 만들거나, 수정하거나, 삭제합니다.
ms.openlocfilehash: 4c109c5512bfc3e0876aef036b8bb645cd2791fc
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60742124"
---
# <a name="managing-network-bandwidth-policy-profiles-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 네트워크 대역폭 정책 프로필 관리

이 문서의 절차에 따라 네트워크 대역폭 정책 프로필을 보거나, 만들거나, 수정하거나, 삭제합니다.

## <a name="view-network-bandwidth-policy-profile-information"></a>네트워크 대역폭 정책 프로필 정보 보기

대역폭 정책은 CAC(통화 허용 제어)의 일부로 특정 형식에 대한 대역폭 제한을 정의하는 데 사용됩니다. 이 비즈니스용 Skype 서버 오디오 및 비디오에만 대역폭 제한을 할당할 수 있습니다. 전체 대역폭 제한 및 세션 제한을 설정할 수 있습니다. 제어판을 비즈니스용 Skype 서버 정책에 대한 컨테이너 프로필을 만들거나 수정하거나 삭제할 수 있습니다. 각 대역폭 정책 프로필은 하나 이상의 네트워크 사이트에 연결할 수 있습니다. 다음 절차에 따라 대역폭 정책 프로필을 하세요. 

### <a name="to-view-a-bandwidth-policy-profile"></a>대역폭 정책 프로필을 보기 위해

1.  RTCUniversalServerAdmins 그룹의 구성원 또는 이와 동등한 사용자 권한을 가졌다는 사용자 계정 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포의 컴퓨터에 로그온합니다.

2.  브라우저 창을 열고 관리 URL을 입력하여 관리 비즈니스용 Skype 서버 열 수 있습니다. 

3.  왼쪽 탐색 모음에서 **네트워크 구성** 을 클릭하고 **대역폭 정책** 을 클릭합니다.

4.  대역폭 **정책 페이지에서** 보하려는 대역폭 정책 프로필을 클릭합니다.

5.  **편집** 메뉴에서 **자세한 정보 표시** 를 클릭합니다.


### <a name="viewing-network-bandwidth-policy-profile-information-by-using-windows-powershell-cmdlets"></a>cmdlet을 사용하여 네트워크 대역폭 정책 프로필 Windows PowerShell 보기

네트워크 대역폭 프로필은 네트워크 대역폭 Windows PowerShell cmdlet을 사용하여 Get-CsNetworkBandwidthPolicyProfile 있습니다. 이 cmdlet은 관리 셸 또는 비즈니스용 Skype 서버 원격 세션에서 실행할 수 Windows PowerShell. 


### <a name="to-view-network-bandwidth-policy-profile-information"></a>네트워크 대역폭 정책 프로필 정보를 보기 위해

  - 모든 네트워크 대역폭 정책 프로필에 대한 정보를 확인하려면 비즈니스용 Skype 서버 관리 셸에서 다음 명령을 입력한 다음 Enter를 누를 수 있습니다.
    
    **Get-CsNetworkBandwidthPolicyProfile**
    
    그러면 다음과 같은 정보가 반환됩니다.
    
    ID: RedmondBandwidthPolicy<br/>
    BWPolicy : {BWLimit=200; BWSessionLimit=200;<br/>
                        BWPolicyModality=Audio, <br/>
                        BWLimit=1400; BWSessionLimit=500;<br/>
                        BWPolicyModality=Video}<br/>
    BWPolicyProfileID : RedmondBandwidthPolicy<br/>
    설명 :

자세한 내용은 [Get-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) cmdlet 관련 도움말 항목을 참조하십시오.


## <a name="create-or-modify-bandwidth-policy-profiles"></a>대역폭 정책 프로필 만들기 또는 수정

대역폭 정책은 CAC(통화 허용 제어)의 일부로 특정 형식에 대한 대역폭 제한을 정의하는 데 사용됩니다. 이 비즈니스용 Skype 서버 오디오 및 비디오에만 대역폭 제한을 할당할 수 있습니다. 전체 대역폭 제한 및 세션 제한을 설정할 수 있습니다. 제어판을 비즈니스용 Skype 서버 정책에 대한 컨테이너 프로필을 만들거나 수정하거나 삭제할 수 있습니다. 각 대역폭 정책 프로필은 하나 이상의 네트워크 사이트에 연결할 수 있습니다. 다음 절차에 따라 대역폭 정책 프로필을 만들거나 수정합니다. 

### <a name="to-create-a-new-bandwidth-policy-profile"></a>새 대역폭 정책 프로필을 만들려면

1.  RTCUniversalServerAdmins 그룹의 구성원 또는 이와 동등한 사용자 권한을 가졌다는 사용자 계정 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포의 컴퓨터에 로그온합니다.

2.  브라우저 창을 열고 관리 URL을 입력하여 관리 비즈니스용 Skype 서버 열 수 있습니다. 

3.  왼쪽 탐색 모음에서 네트워크 구성 **을 클릭한** 다음 **대역폭 정책을 클릭합니다.**

4.  **대역폭 정책** 페이지에서 **다음** 을 클릭합니다.

5.  **새 대역폭 정책 프로필** 에서 **이름** 필드에 이름을 입력합니다. 이 이름은 모든 대역폭 정책 프로필에서 고유해야 합니다.

6.  **오디오 제한** 필드에 숫자 값을 입력합니다. 이 값은 모든 오디오 연결에 대해 할당할 최대 대역폭 크기(kbps 단위)입니다.

7.  **오디오 세션 제한** 필드에 숫자 값을 입력합니다. 이 값은 개별 오디오 연결에 대해 할당할 최대 대역폭 크기(kbps 단위)입니다. 이 값은 40 이상이어야 합니다.

8.  **비디오 제한** 필드에 숫자 값을 입력합니다. 이 값은 모든 비디오 연결에 대해 할당할 최대 대역폭 크기(kbps 단위)입니다.

9.  **비디오 세션 제한** 필드에 숫자 값을 입력합니다. 이 값은 개별 비디오 연결에 대해 할당할 최대 대역폭 크기(kbps 단위)입니다. 이 값은 100 이상이어야 합니다.

10. (선택 사항) 이름만으로는 표현할 수 없는 이 대역폭 정책 프로필에 대한 자세한 정보를 제공하려면 **설명** 필드에 값을 입력합니다.

11. **커밋** 을 클릭합니다.

    > [!NOTE]  
    > 새 대역폭 정책 프로필을 만들어도 대역폭 제한이 자동으로 적용되지는 않습니다. 이렇게 하려면 먼저 정책 프로필을 사이트에 연결해야 합니다. 


### <a name="to-modify-a-bandwidth-policy-profile"></a>대역폭 정책 프로필을 수정하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 또는 이와 동등한 사용자 권한을 가졌다는 사용자 계정 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포의 컴퓨터에 로그온합니다.

2.  브라우저 창을 열고 관리 URL을 입력하여 관리 비즈니스용 Skype 서버 열 수 있습니다. 

3.  왼쪽 탐색 모음에서 네트워크 구성 **을 클릭한** 다음 **대역폭 정책을 클릭합니다.**

4.  **대역폭 정책** 페이지에서 수정할 대역폭 정책 프로필을 클릭합니다.

5.  **편집** 메뉴에서 **자세한 정보 표시** 를 클릭합니다.

6.  대역폭 **정책** 프로필 편집 페이지에서 필드를 필요한 경우 수정합니다(자세한 내용은 새 대역폭 정책 프로필을 만들 [수](#to-create-a-new-bandwidth-policy-profile)있습니다.참조).

7.  **커밋** 을 클릭합니다.

    > [!NOTE]  
    > 대역폭 정책 프로필을 수정하면 해당 대역폭 정책 프로필과 연결된 모든 네트워크 사이트의 대역폭 제한이 즉시 업데이트됩니다.

  
## <a name="delete-network-bandwidth-policy-profiles"></a>네트워크 대역폭 정책 프로필 삭제

대역폭 정책은 CAC(통화 허용 제어)의 일부로 특정 형식에 대한 대역폭 제한을 정의하는 데 사용됩니다. 이 비즈니스용 Skype 서버 오디오 및 비디오에만 대역폭 제한을 할당할 수 있습니다. 전체 대역폭 제한 및 세션 제한을 설정할 수 있습니다. 제어판을 비즈니스용 Skype 서버 정책에 대한 컨테이너 프로필을 만들거나 수정하거나 삭제할 수 있습니다. 다음 절차에 따라 네트워크 대역폭 정책 프로필을 삭제하십시오. 

### <a name="to-delete-a-bandwidth-policy-profile"></a>대역폭 정책 프로필을 삭제하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 또는 이와 동등한 사용자 권한을 가졌다는 사용자 계정 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포의 컴퓨터에 로그온합니다.

2.  브라우저 창을 열고 관리 URL을 입력하여 관리 비즈니스용 Skype 서버 열 수 있습니다. 

3.  왼쪽 탐색 모음에서 네트워크 구성 **을 클릭한** 다음 **대역폭 정책을 클릭합니다.**

4.  **대역폭 정책** 페이지에서 삭제하려는 대역폭 정책 프로필을 클릭합니다.

    > [!NOTE]  
    > 한 번에 둘 이상의 프로필을 삭제할 수 있습니다. 이렇게 하려면 Ctrl 키를 누른 상태에서 여러 프로필을 선택합니다. 또는 모든 프로필을 선택하려면 **편집** 메뉴에서 **모두 선택** 을 클릭합니다.

5.  **편집** 메뉴에서 **삭제** 를 클릭합니다.
   

    > [!WARNING]  
    > 네트워크 사이트에 연결된 대역폭 정책 프로필은 삭제할 수 없습니다. 프로필을 삭제하려면 먼저 네트워크 사이트와의 연결을 제거해야 합니다. 


## <a name="see-also"></a>참고 항목

[사이트에 대한 통화 참가 제어 관리](managing-call-admission-control-for-sites.md)
 
[New-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)  

[Set-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)  

[Get-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  

[Remove-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)  
