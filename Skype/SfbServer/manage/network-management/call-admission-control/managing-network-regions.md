---
title: 네트워크 지역 관리
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 네트워크 지역 *은 통화 허용 제어 (E9-1-1) 및 미디어 바이패스 구성에 사용 되는 네트워크 허브나 백본.
ms.openlocfilehash: 8d1d60389fe910e2b5c2b8b1c357520aad30db96
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188565"
---
# <a name="managing-network-regions-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 네트워크 지역 관리

*네트워크 지역은* 통화 허용 제어 (E9-1-1) 및 미디어 바이패스 구성에 사용 되는 네트워크 허브나 백본. 네트워크 지역을 확인, 생성 또는 수정 하려면 다음 절차를 사용 합니다. 예를 들어 한 음성 기능에 대 한 네트워크 지역을 이미 만든 경우 새 네트워크 지역을 만들 필요가 없습니다. 그 밖의 고급 엔터프라이즈 음성 기능으로는 동일한 네트워크 지역을 사용할 수 있습니다. 그러나 기능별 설정을 적용 하려면 기존 네트워크 지역 정의를 수정 해야 할 수 있습니다. 예를 들어 E9 (연결 된 중앙 사이트가 필요 하지 않음)에 대 한 네트워크 지역을 만든 다음 통화 허용 제어를 배포 하는 경우에는 네트워크 지역 정의를 수정 하 여 중앙 사이트를 지정 해야 합니다. 

이 문서의 절차를 사용 하 여 네트워크 지역 정보를 보거나 네트워크 지역을 만들거나 수정 하거나 삭제할 수 있습니다. 

## <a name="view-network-region-information"></a>네트워크 지역 정보 보기 


네트워크 영역은 여러 지리적 영역에 걸친 네트워크의 다양 한 부분을 상호 구성 합니다. 모든 네트워크 지역은 중앙 사이트와 연결 되어 있어야 합니다. 중앙 사이트는 CAC (call 허용 제어) 대역폭 정책 서비스가 실행 되는 데이터 센터 사이트입니다. 비즈니스용 Skype Server 제어판을 사용 하 여 네트워크 지역을 볼 수 있습니다. 네트워크 영역에는 오디오 및 비디오 연결에 인터넷을 통한 대체 경로가 허용 되는지 여부를 결정 하는 설정이 포함 됩니다. 기존 네트워크 지역을 보려면이 항목을 사용 합니다. 

### <a name="to-view-information-about-a-network-region-with-skype-for-business-server-control-panel"></a>비즈니스용 Skype Server 제어판의 네트워크 지역에 대 한 정보를 보려면

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다. 

3.  왼쪽 탐색 모음에서 **네트워크 구성을**클릭 한 다음 **지역을**클릭 합니다.

4.  **지역** 페이지에서 보려는 지역을 클릭 합니다.
  
    > [!NOTE]  
    > 한 번에 한 영역만 볼 수 있습니다.

5.  **편집** 메뉴에서 **세부 정보 표시**를 클릭 합니다.


### <a name="viewing-network-region-information-by-using-windows-powershell-cmdlets"></a>Windows PowerShell cmdlet을 사용 하 여 네트워크 지역 정보 보기

Windows PowerShell 및 **Get-CsNetworkRegion** cmdlet을 사용 하 여 네트워크 지역 정보를 볼 수 있습니다. 이 cmdlet은 비즈니스용 Skype 서버 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다. 

### <a name="to-view-network-region-information"></a>네트워크 지역 정보를 보려면

  - 모든 네트워크 지역에 대 한 정보를 보려면 비즈니스용 Skype 서버 관리 셸에서 다음 명령을 입력 한 다음 enter 키를 누릅니다.
    
        Get-CsNetworkRegion
    
    이는 다음과 같은 정보를 반환 합니다.
    
        Identity         : Pacific Northwest
        Description      :
        BypassID         : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        CentralSite      : Site:Redmond1
        BWAlternatePaths : {BWPolicyModality=Audio;AlternatePath=True, 
                           BWPolicyModality=Video;AlternatePath=True}
        NetworkRegionID  : Pacific Northwest

자세한 내용은 [Get CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink) cmdlet에 대 한 도움말 항목을 참조 하세요.


## <a name="create-or-modify-network-regions"></a>네트워크 지역 만들기 또는 수정 

네트워크 영역은 여러 지리적 영역에 걸친 네트워크의 다양 한 부분을 상호 구성 합니다. 모든 네트워크 지역은 중앙 사이트와 연결 되어 있어야 합니다. 중앙 사이트는 CAC (call 허용 제어) 대역폭 정책 서비스가 실행 되는 데이터 센터 사이트입니다. 비즈니스용 Skype Server 제어판을 사용 하 여 네트워크 지역을 구성할 수 있습니다. 네트워크 영역에는 오디오 및 비디오 연결에 인터넷을 통한 대체 경로가 허용 되는지 여부를 결정 하는 설정이 포함 됩니다. 비즈니스용 Skype 서버 제어판에서 네트워크 지역을 만들거나 수정 하거나 삭제할 수 있습니다. 이 항목을 사용 하 여 네트워크 지역을 만들고 수정 합니다. 

### <a name="to-create-a-network-region"></a>네트워크 지역을 만들려면

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다. 

3.  왼쪽 탐색 모음에서 **네트워크 구성을**클릭 한 다음 **지역을**클릭 합니다.

4.  **지역** 페이지에서 **새로 만들기**를 클릭 합니다.

5.  **새 지역** 페이지의 **이름** 필드에 값을 입력 합니다. 이 값은 비즈니스용 Skype 서버 배포 내에서 고유 해야 합니다.

6.  **중앙 사이트** 드롭다운 목록에서이 네트워크 영역에 대 한 중앙 사이트를 선택 합니다.

7.  **오디오 대체 경로 사용** 확인란이 기본적으로 선택 되어 있습니다. 이 필드는 기본 경로에 적절 한 대역폭이 없는 경우 오디오 통화가 대체 경로를 통해 라우팅되는 지를 결정 합니다. 인터넷에 대 한 오프 로드를 해제 해야 하는 경우에만이 확인란의 선택을 취소 합니다. 인터넷에 전화를 거는 경우 대역폭 설정에 관계 없이이 확인란을 선택 해야 합니다.

8.  **비디오 대체 경로 사용** 확인란이 기본적으로 선택 되어 있습니다. 이 필드는 기본 경로에 적절 한 대역폭이 없는 경우 영상 통화를 대체 경로를 통해 라우팅할 지 여부를 결정 합니다. 인터넷에 대 한 오프 로드를 해제 해야 하는 경우에만이 확인란의 선택을 취소 합니다. 인터넷에 전화를 거는 경우 대역폭 설정에 관계 없이이 확인란을 선택 해야 합니다.

9.  ) 이름 만으로 표현할 수 없는이 영역에 대 한 자세한 정보를 제공 하려면 **설명** 필드에 값을 입력 합니다.

10. **커밋**을 클릭합니다.

**연결 된 사이트** 테이블은 네트워크 지역을 만드는 데 사용 되지 않습니다. 사이트를 만들거나 수정할 때 사이트를 영역과 연결 합니다. 자세한 내용은 [사이트에 대 한 통화 허용 제어 관리](managing-call-admission-control-for-sites.md)를 참조 하세요.

### <a name="to-modify-a-network-region"></a>네트워크 지역 수정

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다. 

3.  왼쪽 탐색 모음에서 **네트워크 구성을**클릭 한 다음 **지역을**클릭 합니다.

4.  **지역** 페이지에서 수정 하려는 지역을 클릭 합니다.

5.  **편집** 메뉴에서 **세부 정보 표시**를 클릭 합니다.

6.  **지역 편집** 페이지에서 오디오 및 비디오 대체 경로를 사용 하거나 사용 하지 않도록 설정 하는 설정을 수정 하 고 설명 (자세한 내용은이 항목의 "네트워크 영역 만들기" 섹션을 참조 하세요.)을 변경할 수 있습니다.

7.  **커밋**을 클릭합니다.

이 페이지에서 **연결 된 사이트** 를 수정할 수 없습니다. 연결 된 사이트 목록은 지역 설정을 수정할 때 영향을 받는 사이트를 알 수 있도록 참조용으로 제공 됩니다.


## <a name="delete-existing-network-regions"></a>기존 네트워크 지역 삭제 

네트워크 영역은 여러 지리적 영역에 걸친 네트워크의 다양 한 부분을 상호 구성 합니다. 모든 네트워크 지역은 중앙 사이트와 연결 되어 있어야 합니다. 중앙 사이트는 CAC (call 허용 제어) 대역폭 정책 서비스가 실행 되는 데이터 센터 사이트입니다. 비즈니스용 Skype Server 제어판을 사용 하 여 네트워크 지역을 구성할 수 있습니다. 네트워크 영역에는 오디오 및 비디오 연결에 인터넷을 통한 대체 경로가 허용 되는지 여부를 결정 하는 설정이 포함 됩니다. 비즈니스용 Skype 서버 제어판에서 네트워크 지역을 만들거나 수정 하거나 삭제할 수 있습니다. 이 항목을 사용 하 여 기존 네트워크 지역을 삭제 합니다. 

### <a name="to-delete-a-network-region"></a>네트워크 지역을 삭제 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다. 

3.  왼쪽 탐색 모음에서 **네트워크 구성을**클릭 한 다음 **지역을**클릭 합니다.

4.  **지역** 페이지에서 삭제 하려는 지역을 클릭 합니다.
  
    > [!NOTE]  
    > 한 번에 여러 지역을 삭제할 수 있습니다. 이 작업을 수행 하려면 ctrl 키를 누른 채 여러 지역을 선택 합니다. 또는 모든 지역을 선택 하려면 **편집** 메뉴에서 **모두 선택을** 클릭 합니다.

5.  **편집** 메뉴에서 **삭제**를 클릭 합니다.

6.  **확인**을 클릭합니다.


    > [!WARNING]  
    > 네트워크 사이트와 연결 된 네트워크 지역은 제거할 수 없습니다. 사이트와 연결 된 영역을 제거 하려고 하면 오류 메시지가 표시 됩니다. 영역이 사이트와 연결 되어 있는지 확인 하려면 지역을 선택 하 고 **편집** 메뉴에서 **세부 정보 표시** 를 클릭 합니다.


## <a name="see-also"></a>참고 항목

[네트워크 지역 경로 관리](managing-network-region-routes.md)

[새-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)  

[Set-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegion)  

[CsNetworkRegion 제거](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegion)  

[Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
