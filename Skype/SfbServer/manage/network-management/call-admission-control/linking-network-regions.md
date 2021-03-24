---
title: 네트워크 지역 연결
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
description: 'CAC(통화 허용 제어)의 일환으로 두 네트워크 지역 간의 링크를 구성할 수 있습니다. '
ms.openlocfilehash: 163f214b05ba0dca3bc7dd4ec722f148cafe724e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096684"
---
# <a name="linking-network-regions-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 네트워크 지역 연결

CAC(통화 허용 제어)의 일환으로 두 네트워크 지역 간의 링크를 구성할 수 있습니다. 이 문서의 섹션을 사용하여 새 작업 영역 링크 정보를 보거나 netwrok 지역 링크를 구성하거나 삭제할 수 있습니다. 

## <a name="view-network-region-link-information"></a>네트워크 지역 링크 정보 보기 

CAC(통화 허용 제어)의 일환으로 두 네트워크 지역 간의 링크를 볼 수 있습니다. 네트워크 내의 지역은 실제 WAN(Wide Area Network) 연결을 통해 연결됩니다. 비즈니스용 Skype 서버 제어판을 사용하여 두 네트워크 지역 간의 기존 링크를 볼 수 있습니다. 


### <a name="to-view-a-network-region-link-in-skype-for-business-server-control-panel"></a>비즈니스용 Skype 서버 제어판에서 네트워크 지역 링크를 확인하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 또는 이와 동등한 사용자 권한을 가졌다는 사용자 계정 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포의 컴퓨터에 로그온합니다.

2.  브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다. 

3.  왼쪽 탐색 모음에서 네트워크 구성 **을 클릭한** 다음 **지역 링크를 클릭합니다.**

4.  **지역 링크** 페이지에서 보려는 지역 링크를 클릭합니다.
    
    > [!NOTE]  
    > 한 번에 하나의 지역 링크에 대한 정보만 볼 수 있습니다.

5.  **편집** 메뉴에서 **세부 정보 표시** 를 선택합니다.

### <a name="view-network-region-link-information-by-using-windows-powershell-cmdlets"></a>cmdlet을 사용하여 네트워크 지역 링크 Windows PowerShell 보기

네트워크 지역 링크는 **Get-CsNetworkRegionLink** cmdlet과 Windows PowerShell 볼 수 있습니다. 비즈니스용 Skype 서버 관리 셸 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다. 


### <a name="to-view-network-region-link-information"></a>네트워크 지역 링크 정보를 보려면

  - 모든 네트워크 지역 링크에 대한 정보를 보시다시피 비즈니스용 Skype 서버 관리 셸에 다음 명령을 입력한 다음 Enter를 누르고 있습니다.
    
        Get-CsNetworkRegionLink
    
    이 명령은 다음과 비슷한 정보를 반환합니다.
    
        Identity            : NorthwestToCalifornia
        BWPolicyProfileID   :
        NetworkRegionLinkID : NorthwestToCalifornia
        NetworkRegionID1    : Pacific Northwest
        NetworkRegionID2    : California


자세한 내용은 [Get-CsNetworkRegionLink](/powershell/module/skype/Get-CsNetworkRegionLink)을 참조하십시오.


## <a name="configure-network-region-links"></a>네트워크 지역 링크 구성 

CAC(통화 허용 제어)의 일환으로 두 네트워크 지역 간의 링크를 구성할 수 있습니다. 네트워크 내의 지역은 실제 WAN(Wide Area Network) 연결을 통해 연결됩니다. 비즈니스용 Skype 서버 제어판을 사용하여 두 네트워크 지역 간의 링크를 정의하고 이러한 지역 간의 오디오 및 비디오 연결에 대한 대역폭 제한을 설정할 수 있습니다.

### <a name="to-create-a-network-region-link"></a>네트워크 지역 링크를 만들려면

1.  RTCUniversalServerAdmins 그룹의 구성원 또는 이와 동등한 사용자 권한을 가졌다는 사용자 계정 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포의 컴퓨터에 로그온합니다.

2.  브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다. 

3.  왼쪽 탐색 모음에서 네트워크 구성 **을 클릭한** 다음 **지역 링크를 클릭합니다.**

4.  **지역 링크** 페이지에서 **새로 만들기** 를 클릭합니다.

5.  **새 지역 링크** 에서 **이름** 필드에 값을 입력합니다.
 
    > [!NOTE]  
    > 이 값은 비즈니스용 Skype 서버 배포 내에서 고유해야 합니다.

6.  네트워크 **지역 \# 1** 드롭다운 목록에서 연결할 두 지역 중 하나를 선택합니다.

7.  네트워크 **지역 \# 2** 드롭다운 목록에서 연결할 다른 지역을 선택합니다. 이 지역은 네트워크 지역 1에 대해 선택한 지역과 달라야 \# 합니다.

8.  (선택 사항) 이러한 지역 간의 음성 또는 화상 통화에 대역폭 제한을 설정하려면 **대역폭 정책** 드롭다운 목록에서 대역폭 정책 프로필을 선택합니다.

9.  **커밋** 을 클릭합니다.

### <a name="to-modify-a-network-region-link"></a>네트워크 지역 링크를 수정하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 또는 이와 동등한 사용자 권한을 가졌다는 사용자 계정 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포의 컴퓨터에 로그온합니다.

2.  브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다. 

3.  왼쪽 탐색 모음에서 네트워크 구성 **을 클릭한** 다음 **지역 링크를 클릭합니다.**

4.  **지역 링크** 페이지에서 수정할 지역 링크를 클릭합니다.

5.  **편집** 메뉴에서 **자세한 정보 표시** 를 클릭합니다.

6.  **지역 링크 편집** 에서 연결된 지역 또는 이 링크에 대한 대역폭 정책 프로필을 수정할 수 있습니다.

7.  **커밋** 을 클릭합니다.


## <a name="delete-network-region-links"></a>네트워크 지역 링크 삭제

CAC(통화 허용 제어)의 일환으로 두 네트워크 지역 간의 링크를 구성할 수 있습니다. 네트워크 내의 지역은 실제 WAN(Wide Area Network) 연결을 통해 연결됩니다. 비즈니스용 Skype 서버 제어판을 사용하여 두 네트워크 지역 간의 기존 링크를 삭제할 수 있습니다. 

### <a name="to-delete-a-network-region-link"></a>네트워크 지역 링크를 삭제하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 또는 이와 동등한 사용자 권한을 가졌다는 사용자 계정 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포의 컴퓨터에 로그온합니다.

2.  브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다. 

3.  왼쪽 탐색 모음에서 네트워크 구성 **을 클릭한** 다음 **지역 링크를 클릭합니다.**

4.  **지역 링크** 페이지에서 삭제할 지역 링크를 클릭합니다.
 
    > [!NOTE]  
    > 한 번에 둘 이상의 지역 링크를 삭제할 수 있습니다. 이렇게 하려면 Ctrl 키를 누른 상태에서 여러 지역 링크를 선택합니다. 또는 모든 지역 링크를 선택하려면 <STRONG>편집</STRONG> 메뉴에서 <STRONG>모두 선택</STRONG>을 클릭합니다.

5.  **편집** 메뉴에서 **삭제** 를 선택합니다.

6.  **확인** 을 클릭합니다.


## <a name="see-also"></a>참고 항목

[New-CsNetworkRegionLink](/powershell/module/skype/New-CsNetworkRegionLink)  

[Set-CsNetworkRegionLink](/powershell/module/skype/Set-CsNetworkRegionLink)  

[Remove-CsNetworkRegionLink](/powershell/module/skype/Remove-CsNetworkRegionLink)  

[Get-CsNetworkRegionLink](/powershell/module/skype/Get-CsNetworkRegionLink)