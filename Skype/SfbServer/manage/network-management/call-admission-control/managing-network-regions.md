---
title: 네트워크 지역 관리
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
description: 네트워크 지역*은 통화 액세스 제어, E9-1-1 및 미디어 우회 구성에 사용되는 네트워크 허브 또는 백본입니다.
ms.openlocfilehash: 9e38528dd34f25fa2b70b51485657168868d6628
ms.sourcegitcommit: 97c2faab08ec9b8fc9967827883308733ec162ea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/13/2021
ms.locfileid: "58232803"
---
# <a name="managing-network-regions-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 네트워크 지역 관리

*네트워크 지역* 은 통화 허용 제어, E9-1-1 및 미디어 바이패스 구성에 사용되는 네트워크 허브 또는 백본입니다. 다음 절차에 따라 네트워크 지역을 확인, 작성 또는 수정합니다. 예를 들어 단일 음성 기능에 대해 네트워크 지역을 이미 만든 경우에는 새 네트워크 지역을 만들 필요가 없으며, 다른 고급 Enterprise Voice 기능도 같은 네트워크 지역을 사용합니다. 그러나 기존 네트워크 지역 정의를 수정하여 기능별 설정을 적용할 수는 있습니다. 예를 들어 E9-1-1용으로 네트워크 지역을 만든 후(연결된 중앙 사이트가 필요하지 않음) 통화 허용 제어를 배포하는 경우에는 네트워크 지역 정의를 수정하여 중앙 사이트를 지정해야 합니다. 

이 문서의 절차에 따라 네트워크 지역 정보를 보거나 네트워크 지역을 만들거나 수정하거나 삭제합니다. 

## <a name="view-network-region-information"></a>네트워크 지역 정보 보기 


네트워크 지역은 여러 지역의 많은 네트워크 부분을 교차합니다. 모든 네트워크 지역은 중앙 사이트와 연결되어야 합니다. 중앙 사이트는 CAC(통화 허용 제어) 대역폭 정책 서비스가 실행되는 데이터 센터 사이트입니다. 제어판을 사용하여 비즈니스용 Skype 서버 지역을 볼 수 있습니다. 네트워크 지역에는 오디오 및 비디오 연결에 대해 인터넷을 통한 대체 경로가 허용되는지 여부를 결정하는 설정이 포함됩니다. 이 항목을 사용하여 기존 네트워크 지역을 확인합니다. 

### <a name="to-view-information-about-a-network-region-with-skype-for-business-server-control-panel"></a>제어판이 있는 네트워크 지역에 대한 비즈니스용 Skype 서버 보기

1.  RTCUniversalServerAdmins 그룹의 구성원 또는 이와 동등한 사용자 권한을 가졌다는 사용자 계정 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포의 컴퓨터에 로그온합니다.

2.  브라우저 창을 열고 관리 URL을 입력하여 관리 비즈니스용 Skype 서버 열 수 있습니다. 

3.  왼쪽 탐색 모음에서 네트워크 **구성을 클릭한** 다음 지역 을 **클릭합니다.**

4.  **지역** 페이지에서 보려는 지역을 클릭합니다.
  
    > [!NOTE]  
    > 한 번에 한 지역만 볼 수 있습니다.

5.  **편집** 메뉴에서 **세부 정보 표시** 를 클릭합니다.


### <a name="viewing-network-region-information-by-using-windows-powershell-cmdlets"></a>cmdlet을 사용하여 네트워크 지역 Windows PowerShell 보기

네트워크 지역 정보와 **Get-CsNetworkRegion** cmdlet을 Windows PowerShell 볼 수 있습니다. 이 cmdlet은 관리 셸 또는 비즈니스용 Skype 서버 세션에서 실행할 수 Windows PowerShell. 

### <a name="to-view-network-region-information"></a>네트워크 지역 정보를 보기 위해

  - 모든 네트워크 지역에 대한 정보를 보기 위해 비즈니스용 Skype 서버 관리 셸에서 다음 명령을 입력한 다음 Enter를 누를 수 있습니다.
    
    **Get-CsNetworkRegion**
    
    그러면 다음과 같은 정보가 반환됩니다.
    
    ID: 태평양 북서부<br/>
    설명 :<br/>
    BypassID : 3b232b84-2c1d-4da2-8181-e9330bafebe9<br/>
    CentralSite : Site:Redmond1<br/>
    BWAlternatePaths : {BWPolicyModality=Audio; AlternatePath=True, <br/>
                       BWPolicyModality=Video; AlternatePath=True}<br/>
    NetworkRegionID : 태평양 북서부<br/>

자세한 내용은 [Get-CsNetworkRegion](/powershell/module/skype/Get-CsNetworkRegionLink) cmdlet의 도움말 항목을 참조하십시오.


## <a name="create-or-modify-network-regions"></a>네트워크 지역 만들기 또는 수정 

네트워크 지역은 여러 지역의 많은 네트워크 부분을 교차합니다. 모든 네트워크 지역은 중앙 사이트와 연결되어야 합니다. 중앙 사이트는 CAC(통화 허용 제어) 대역폭 정책 서비스가 실행되는 데이터 센터 사이트입니다. 제어판을 사용하여 비즈니스용 Skype 서버 지역을 구성할 수 있습니다. 네트워크 지역에는 오디오 및 비디오 연결에 대해 인터넷을 통한 대체 경로가 허용되는지 여부를 결정하는 설정이 포함됩니다. 비즈니스용 Skype 서버 제어판에서 네트워크 지역을 만들거나 수정하거나 삭제할 수 있습니다. 이 항목을 사용하여 네트워크 지역을 만들고 수정할 수 있습니다. 

### <a name="to-create-a-network-region"></a>네트워크 지역을 만들려면

1.  RTCUniversalServerAdmins 그룹의 구성원 또는 이와 동등한 사용자 권한을 가졌다는 사용자 계정 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포의 컴퓨터에 로그온합니다.

2.  브라우저 창을 열고 관리 URL을 입력하여 관리 비즈니스용 Skype 서버 열 수 있습니다. 

3.  왼쪽 탐색 모음에서 네트워크 **구성을 클릭한** 다음 지역 을 **클릭합니다.**

4.  **지역** 페이지에서 **새로 만들기** 를 클릭합니다.

5.  **새 지역** 페이지의 **이름** 필드에 값을 입력합니다. 이 값은 사용자 배포 내에서 고유해야 비즈니스용 Skype 서버 합니다.

6.  **중앙 사이트** 드롭다운 목록에서 이 네트워크 지역에 대한 중앙 사이트를 선택합니다.

7.  **오디오 대체 경로 사용** 확인란은 기본적으로 선택됩니다. 이 필드는 기본 경로에 적절한 대역폭이 없는 경우 대체 경로를 통해 음성 통화를 라우팅할지 여부를 결정하며, 인터넷으로 오프로드를 해제해야 하는 경우에만 이 확인란을 선택 취소합니다. 통화가 인터넷 통화인 경우 대역폭 설정에 관계없이 이 확인란을 선택해야 합니다.

8.  **비디오 대체 경로 사용** 확인란은 기본적으로 선택됩니다. 이 필드는 기본 경로에 적절한 대역폭이 없는 경우 대체 경로를 통해 화상 통화를 라우팅할지 여부를 결정하며, 인터넷으로 오프로드를 해제해야 하는 경우에만 이 확인란을 선택 취소합니다. 통화가 인터넷 통화인 경우 대역폭 설정에 관계없이 이 확인란을 선택해야 합니다.

9.  (선택 사항) **설명** 필드에 값을 입력하여 이름 하나로만 표시될 수 없는 이 지역에 대해 추가 정보를 제공합니다.

10. **커밋** 을 클릭합니다.

네트워크 지역을 만드는 데 **연결된 사이트** 표는 사용되지 않습니다. 사이트를 만들거나 수정할 때 사이트와 지역이 연결됩니다. 자세한 내용은 [Managing call admission control for sites를 참조합니다.](managing-call-admission-control-for-sites.md)

### <a name="to-modify-a-network-region"></a>네트워크 지역을 수정하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 또는 이와 동등한 사용자 권한을 가졌다는 사용자 계정 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포의 컴퓨터에 로그온합니다.

2.  브라우저 창을 열고 관리 URL을 입력하여 관리 비즈니스용 Skype 서버 열 수 있습니다. 

3.  왼쪽 탐색 모음에서 네트워크 **구성을 클릭한** 다음 지역 을 **클릭합니다.**

4.  **지역** 페이지에서 수정할 지역을 클릭합니다.

5.  **편집** 메뉴에서 **자세한 정보 표시** 를 클릭합니다.

6.  **지역 편집** 페이지에서 오디오 및 비디오 대체 경로를 사용하거나 사용하지 않도록 지정하는 설정을 수정하고 설명을 변경할 수 있습니다(자세한 내용은 이 항목의 이전 섹션인 "네트워크 지역을 만들려면" 섹션 참조).

7.  **커밋** 을 클릭합니다.

이 페이지에서 **연결된 사이트** 는 수정할 수 없습니다. 연결된 사이트 목록은 참조용으로 제공되므로 지역 설정을 수정할 때는 영향을 받는 사이트를 확인해야 합니다.


## <a name="delete-existing-network-regions"></a>기존 네트워크 지역 삭제 

네트워크 지역은 여러 지역의 많은 네트워크 부분을 교차합니다. 모든 네트워크 지역은 중앙 사이트와 연결되어야 합니다. 중앙 사이트는 CAC(통화 허용 제어) 대역폭 정책 서비스가 실행되는 데이터 센터 사이트입니다. 제어판을 사용하여 비즈니스용 Skype 서버 지역을 구성할 수 있습니다. 네트워크 지역에는 오디오 및 비디오 연결에 대해 인터넷을 통한 대체 경로가 허용되는지 여부를 결정하는 설정이 포함됩니다. 비즈니스용 Skype 서버 제어판에서 네트워크 지역을 만들거나 수정하거나 삭제할 수 있습니다. 이 항목을 참조하여 기존 네트워크 지역을 삭제하십시오. 

### <a name="to-delete-a-network-region"></a>네트워크 지역을 삭제하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 또는 이와 동등한 사용자 권한을 가졌다는 사용자 계정 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포의 컴퓨터에 로그온합니다.

2.  브라우저 창을 열고 관리 URL을 입력하여 관리 비즈니스용 Skype 서버 열 수 있습니다. 

3.  왼쪽 탐색 모음에서 네트워크 **구성을 클릭한** 다음 지역 을 **클릭합니다.**

4.  **지역** 페이지에서 삭제하려는 지역을 클릭합니다.
  
    > [!NOTE]  
    > 한 번에 둘 이상의 지역을 삭제할 수 있습니다. 이렇게 하려면 Ctrl 키를 누른 상태에서 여러 지역을 선택합니다. 또는 지역을 모두 선택하려면 **편집** 메뉴에서 **모두 선택** 을 클릭합니다.

5.  **편집** 메뉴에서 **삭제** 를 클릭합니다.

6.  **확인** 을 클릭합니다.


    > [!WARNING]  
    > 네트워크 사이트와 연결된 네트워크 지역은 제거할 수 없습니다. 사이트와 연결된 지역을 제거하려고 하면 오류 메시지가 표시됩니다. 지역이 사이트와 연결되어 있는지 확인하려면 지역을 선택하고 **편집** 메뉴에서 **자세한 정보 표시** 를 클릭합니다.


## <a name="see-also"></a>참고 항목

[네트워크 지역 경로 관리](managing-network-region-routes.md)

[New-CsNetworkRegion](/powershell/module/skype/New-CsNetworkRegion)  

[Set-CsNetworkRegion](/powershell/module/skype/Set-CsNetworkRegion)  

[Remove-CsNetworkRegion](/powershell/module/skype/Remove-CsNetworkRegion)  

[Get-CsNetworkRegion](/powershell/module/skype/Get-CsNetworkRegionLink)