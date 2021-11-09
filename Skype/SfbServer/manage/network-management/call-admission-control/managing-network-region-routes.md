---
title: 네트워크 지역 경로 관리
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 네트워크 지역 경로는 네트워크 지역 쌍 간의 경로를 정의합니다. 통화 허용 제어 배포의 각 네트워크 지역 쌍에는 네트워크 지역 경로가 필요합니다.
ms.openlocfilehash: 18bee9a28eed10affae1b0dab855c379709b37bb
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60864755"
---
# <a name="managing-network-region-routes-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 네트워크 지역 경로 지정 관리

*네트워크 지역 경로* 는 네트워크 지역 쌍 간의 경로를 정의합니다. 통화 허용 제어 배포의 각 네트워크 지역 쌍에는 네트워크 지역 경로가 필요합니다. 이러한 경로가 있으면 배포 내의 모든 네트워크 지역이 다른 모든 지역에 액세스할 수 있습니다. 이 아트 아트의 절차에 따라 네트워크 지역 경로를 보거나, 만들거나, 수정하거나, 삭제할 수 있습니다.

## <a name="view-network-region-route-information"></a>네트워크 지역 경로 정보 보기 

CAC(통화 허용 제어) 구성 내의 모든 지역에는 다른 모든 지역에 액세스할 수 있는 방법이 있어야 합니다. 지역 링크는 지역 간 연결에 대한 대역폭 제한을 설정하고 실제 링크를 나타내며, 경로는 한 지역에서 다른 지역으로 연결이 트래버스되는 연결된 경로를 결정합니다. 다음 절차에 따라 제어판 또는 관리 셸에서 비즈니스용 Skype 서버 네트워크 지역 경로를 비즈니스용 Skype 서버 합니다. 

### <a name="to-view-network-region-route-information-in-skype-for-business-server-control-panel"></a>제어판에서 네트워크 지역 경로 비즈니스용 Skype 서버 보기

1.  RTCUniversalServerAdmins 그룹의 구성원 또는 이와 동등한 사용자 권한을 가졌다는 사용자 계정 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포의 컴퓨터에 로그온합니다.

2.  브라우저 창을 열고 관리 URL을 입력하여 관리 비즈니스용 Skype 서버 열 수 있습니다. 

3.  왼쪽 탐색 모음에서 네트워크 구성 **을 클릭한** 다음 **지역 경로를 클릭합니다.**

4.  **지역 경로** 페이지에서 보려는 지역 경로를 클릭합니다.


    > [!NOTE]
    > 한 번에 하나의 지역 경로만 볼 수 있습니다.


5.  **편집** 메뉴에서 **자세한 정보 표시** 를 클릭합니다.


### <a name="viewing-network-region-route-information-by-using-windows-powershell-cmdlets"></a>Cmdlet을 사용하여 네트워크 지역 경로 Windows PowerShell 보기

네트워크 지역 경로 정보는 네트워크 지역 경로 Windows PowerShell cmdlet을 사용하여 Get-CsNetworkInterRegionRoute 있습니다. 이 cmdlet은 관리 셸 또는 비즈니스용 Skype 서버 원격 세션에서 실행할 수 Windows PowerShell. 

### <a name="to-view-network-region-route-information"></a>네트워크 지역 경로 정보를 보기 위해

  - 모든 네트워크 지역 경로에 대한 정보를 보기 위해 비즈니스용 Skype 서버 관리 셸에서 다음 명령을 입력한 다음 Enter를 누를 수 있습니다.
    
    **Get-CsNetworkInterRegionRoute**
    
    그러면 다음과 같은 정보가 반환됩니다.
    
    IDENTITY: TransAmericaRoute<br/>
    NetworkRegionLinks : {NorthwestToNortheast}<br/>
    InterNetworkRegionRouteID : TransAmericaRoute<br/>
    NetworkRegionID1: 태평양 북서부<br/>
    NetworkRegionID2 : 북동부<br/>

자세한 내용은 [Get-CsNetworkInterRegionRoute](/powershell/module/skype/Get-CsNetworkInterRegionRoute) cmdlet에 대한 도움말 항목을 참조하십시오.


## <a name="create-or-modify-network-region-routes"></a>네트워크 지역 경로 만들기 또는 수정

CAC(통화 허용 제어) 구성 내의 모든 지역에는 다른 모든 지역에 액세스할 수 있는 방법이 있어야 합니다. 지역 링크는 지역 간 연결에 대한 대역폭 제한을 설정하고 실제 링크를 나타내며, 경로는 한 지역에서 다른 지역으로 연결이 트래버스되는 연결된 경로를 결정합니다. 제어판을 사용하여 비즈니스용 Skype 서버 지역 경로를 구성할 수 있습니다. 비즈니스용 Skype 서버 제어판에서 네트워크 지역 경로를 만들거나 수정하거나 삭제할 수 있습니다. 이 항목의 정보에 따라 네트워크 지역을 만들거나 수정하십시오. 

### <a name="to-create-a-network-region-route"></a>네트워크 지역 경로를 만들려면

1.  RTCUniversalServerAdmins 그룹의 구성원 또는 이와 동등한 사용자 권한을 가졌다는 사용자 계정 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포의 컴퓨터에 로그온합니다.

2.  브라우저 창을 열고 관리 URL을 입력하여 관리 비즈니스용 Skype 서버 열 수 있습니다. 

3.  왼쪽 탐색 모음에서 네트워크 구성 **을 클릭한** 다음 **지역 경로를 클릭합니다.**

4.  **지역 경로** 페이지에서 **새로 만들기** 를 클릭합니다.

5.  **새 지역 경로** 에서 **이름** 필드에 값을 입력합니다.
   
    > [!NOTE]  
    > 이 값은 사용자 배포 내에서 고유해야 비즈니스용 Skype 서버 합니다.

6.  네트워크 **지역 \# 1** 드롭다운 목록에서 이 경로로 연결할 두 지역 중 하나를 선택합니다.

7.  네트워크 **지역 \# 2** 드롭다운 목록에서 이 경로의 다른 지역을 선택합니다. 이 지역은 네트워크 지역 1에 대해 선택한 지역과 달라야 \# 합니다.

8.  **네트워크 지역 링크** 목록 상자를 사용하여 경로에 지역 링크를 추가합니다. **추가** 단추를 클릭하여 **지역 링크** 페이지를 표시합니다. 이 경로에 추가할 지역 링크를 클릭한 다음 **확인** 을 클릭합니다.
    
    > [!NOTE]  
    > 계속해서 링크를 더 추가하려면 **추가** 단추를 클릭하고 링크를 제거하려면 링크를 선택하고 **제거** 를 클릭합니다.

9.  **커밋** 을 클릭합니다.


### <a name="to-modify-a-network-region-route"></a>네트워크 지역 경로를 수정하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 또는 이와 동등한 사용자 권한을 가졌다는 사용자 계정 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포의 컴퓨터에 로그온합니다.

2.  브라우저 창을 열고 관리 URL을 입력하여 관리 비즈니스용 Skype 서버 열 수 있습니다. 

3.  왼쪽 탐색 모음에서 네트워크 구성 **을 클릭한** 다음 **지역 경로를 클릭합니다.**

4.  **지역 경로** 페이지에서 수정할 지역 경로를 클릭합니다.

5.  **편집** 메뉴에서 **세부 정보 표시** 를 클릭합니다.

6.  **지역 경로 편집** 에서 이 경로에 참가하는 지역 및 해당 경로와 연결된 지역 링크를 수정할 수 있습니다.

7.  **커밋** 을 클릭합니다.


## <a name="delete-existing-network-region-routes"></a>기존 네트워크 지역 경로 삭제

CAC(통화 허용 제어) 구성 내의 모든 지역에는 다른 모든 지역에 액세스할 수 있는 방법이 있어야 합니다. 지역 링크는 지역 간 연결에 대한 대역폭 제한을 설정하고 실제 링크를 나타내며, 경로는 한 지역에서 다른 지역으로 연결이 트래버스되는 연결된 경로를 결정합니다. 제어판을 사용하여 비즈니스용 Skype 서버 지역 경로를 구성할 수 있습니다. 비즈니스용 Skype 서버 제어판에서 네트워크 지역 경로를 만들거나 수정하거나 삭제할 수 있습니다. 이 항목을 사용하여 기존 네트워크 지역 경로를 삭제합니다. 

### <a name="to-delete-a-network-region-route"></a>네트워크 지역 경로를 삭제하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 또는 이와 동등한 사용자 권한을 가졌다는 사용자 계정 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포의 컴퓨터에 로그온합니다.

2.  브라우저 창을 열고 관리 URL을 입력하여 관리 비즈니스용 Skype 서버 열 수 있습니다. 

3.  왼쪽 탐색 모음에서 네트워크 구성 **을 클릭한** 다음 **지역 경로를 클릭합니다.**

4.  지역 **경로 페이지에서** 삭제할 지역 경로를 클릭합니다.

    > [!NOTE]  
    > 한에 두 개 이상의 지역 경로를 삭제할 수 있습니다. 이렇게하려면 Ctrl 키를 누를 때 여러 지역 경로를 선택합니다. 또는 모든 지역 경로를 선택하려면 편집 메뉴에서 **모두** **선택을** 클릭합니다.

5.  **편집** 메뉴에서 **삭제** 를 클릭합니다.

6.  **확인** 을 클릭합니다.



## <a name="see-also"></a>참고 항목

[비즈니스용 Skype 서버에서 네트워크 지역 관리](managing-network-regions.md)

[New-CsNetworkInterRegionRoute](/powershell/module/skype/New-CsNetworkInterRegionRoute)  

[Set-CsNetworkInterRegionRoute](/powershell/module/skype/Set-CsNetworkInterRegionRoute) 
 
[Remove-CsNetworkInterRegionRoute](/powershell/module/skype/Remove-CsNetworkInterRegionRoute)  

[Get-CsNetworkInterRegionRoute](/powershell/module/skype/Get-CsNetworkInterRegionRoute)