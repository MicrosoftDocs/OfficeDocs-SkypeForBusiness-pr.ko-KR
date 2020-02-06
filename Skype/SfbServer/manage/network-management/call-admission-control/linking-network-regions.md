---
title: 네트워크 지역 연결
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
description: '두 네트워크 지역 간의 링크를 CAC (call 허용 제어)의 일부로 구성할 수 있습니다. '
ms.openlocfilehash: 4a643f34b9525b53168b9015b77a7f8292abd417
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817527"
---
# <a name="linking-network-regions-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 네트워크 지역 연결

두 네트워크 지역 간의 링크를 CAC (call 허용 제어)의 일부로 구성할 수 있습니다. 이 문서의 섹션을 사용 하 여 newtwork 지역 링크 정보를 보거나 netwrok 지역 링크를 구성 하거나 삭제할 수 있습니다. 

## <a name="view-network-region-link-information"></a>네트워크 지역 링크 정보 보기 

호출 허용 제어 (CAC)의 일부로 두 네트워크 지역 간 링크를 볼 수 있습니다. 네트워크 내의 영역은 실제 WAN (광역 네트워크) 연결을 통해 연결 됩니다. 비즈니스용 Skype Server 제어판을 사용 하 여 두 네트워크 지역 간의 기존 링크를 볼 수 있습니다. 


### <a name="to-view-a-network-region-link-in-skype-for-business-server-control-panel"></a>비즈니스용 Skype Server 제어판에서 네트워크 지역 링크 보기

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다. 

3.  왼쪽 탐색 모음에서 **네트워크 구성을**클릭 한 다음 **지역 링크**를 클릭 합니다.

4.  **지역 링크** 페이지에서 보려는 지역 링크를 클릭 합니다.
    
    > [!NOTE]  
    > 한 번에 하나의 지역 링크에 대 한 정보만 볼 수 있습니다.

5.  **편집** 메뉴에서 **세부 정보 표시**를 선택 합니다.

### <a name="view-network-region-link-information-by-using-windows-powershell-cmdlets"></a>Windows PowerShell cmdlet을 사용 하 여 네트워크 지역 링크 정보 보기

Windows PowerShell 및 **Get-Csnetworkregion 링크** cmdlet을 사용 하 여 네트워크 지역 링크를 볼 수 있습니다. 이 cmdlet은 비즈니스용 Skype 서버 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다. 


### <a name="to-view-network-region-link-information"></a>네트워크 지역 링크 정보를 보려면

  - 모든 네트워크 지역 링크에 대 한 정보를 보려면 비즈니스용 Skype 서버 관리 셸에서 다음 명령을 입력 한 다음 enter 키를 누릅니다.
    
        Get-CsNetworkRegionLink
    
    이 명령은 다음과 같은 정보를 반환 합니다.
    
        Identity            : NorthwestToCalifornia
        BWPolicyProfileID   :
        NetworkRegionLinkID : NorthwestToCalifornia
        NetworkRegionID1    : Pacific Northwest
        NetworkRegionID2    : California


자세한 내용은 [Get-Csnetwork국가 링크](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)를 참조 하세요.


## <a name="configure-network-region-links"></a>네트워크 지역 링크 구성 

두 네트워크 지역 간의 링크를 CAC (call 허용 제어)의 일부로 구성할 수 있습니다. 네트워크 내의 영역은 실제 WAN (광역 네트워크) 연결을 통해 연결 됩니다. 비즈니스용 Skype Server 제어판을 사용 하 여 두 네트워크 지역 간의 링크를 정의 하 고 이러한 지역 간의 오디오 및 비디오 연결에 대 한 대역폭 제한을 설정할 수 있습니다.

### <a name="to-create-a-network-region-link"></a>네트워크 지역 링크를 만들려면

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다. 

3.  왼쪽 탐색 모음에서 **네트워크 구성을**클릭 한 다음 **지역 링크**를 클릭 합니다.

4.  **지역 링크** 페이지에서 **새로 만들기**를 클릭 합니다.

5.  **새 영역 링크**의 **이름** 필드에 값을 입력 합니다.
 
    > [!NOTE]  
    > 이 값은 비즈니스용 Skype 서버 배포 내에서 고유 해야 합니다.

6.  **네트워크 지역 \#1** 드롭다운 목록에서 연결할 두 지역 중 하나를 선택 합니다.

7.  **네트워크 지역 \#2** 드롭다운 목록에서 연결할 다른 영역을 선택 합니다. 이 지역은 네트워크 지역 \#1에 대해 선택한 지역과 달라 야 합니다.

8.  ) 이러한 지역 간의 오디오 또는 비디오 통화에 대 한 대역폭 제한을 설정 하려면 **대역폭 정책** 드롭다운 목록에서 대역폭 정책 프로필을 선택 합니다.

9.  **커밋**을 클릭합니다.

### <a name="to-modify-a-network-region-link"></a>네트워크 지역 링크를 수정 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다. 

3.  왼쪽 탐색 모음에서 **네트워크 구성을**클릭 한 다음 **지역 링크**를 클릭 합니다.

4.  **지역 링크** 페이지에서 수정 하려는 지역 링크를 클릭 합니다.

5.  **편집** 메뉴에서 **세부 정보 표시**를 클릭 합니다.

6.  **지역 편집 링크**에서 연결 된 영역이 나이 링크에 대 한 대역폭 정책 프로필을 수정할 수 있습니다.

7.  **커밋**을 클릭합니다.


## <a name="delete-network-region-links"></a>네트워크 지역 링크 삭제

두 네트워크 지역 간의 링크를 CAC (call 허용 제어)의 일부로 구성할 수 있습니다. 네트워크 내의 영역은 실제 WAN (광역 네트워크) 연결을 통해 연결 됩니다. 비즈니스용 Skype Server 제어판을 사용 하 여 두 네트워크 지역 간의 기존 링크를 삭제할 수 있습니다. 

### <a name="to-delete-a-network-region-link"></a>네트워크 지역 링크를 삭제 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다. 

3.  왼쪽 탐색 모음에서 **네트워크 구성을**클릭 한 다음 **지역 링크**를 클릭 합니다.

4.  **지역 링크** 페이지에서 삭제 하려는 지역 링크를 클릭 합니다.
 
    > [!NOTE]  
    > 한 번에 둘 이상의 지역 링크를 삭제할 수 있습니다. 이 작업을 수행 하려면 ctrl 키를 누른 채로 여러 지역 링크를 선택 합니다. 또는 모든 지역 링크를 선택 하려면 <STRONG>편집</STRONG> 메뉴에서 <STRONG>모두 선택을</STRONG> 클릭 합니다.

5.  **편집** 메뉴에서 **삭제**를 선택 합니다.

6.  **확인**을 클릭합니다.


## <a name="see-also"></a>참고 항목

[새-Csnetwork국가 링크](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegionLink)  

[Set-Csnetwork국가 링크](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegionLink)  

[-Csnetwork국가 링크 제거](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegionLink)  

[Get-Csnetwork국가 링크](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
