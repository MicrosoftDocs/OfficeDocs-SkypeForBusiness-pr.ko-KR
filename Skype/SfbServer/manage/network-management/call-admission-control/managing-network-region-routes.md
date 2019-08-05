---
title: 네트워크 지역 경로 관리
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 네트워크 지역 경로는 네트워크 지역 쌍 간의 경로를 정의 합니다. 통화 허용 제어 배포의 각 네트워크 지역 쌍에는 네트워크 지역 경로가 필요 합니다.
ms.openlocfilehash: 174fdd021655f3e338001582a1409107b266582e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188568"
---
# <a name="managing-network-region-routes-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 네트워크 지역 경로 관리

*네트워크 지역 경로* 는 네트워크 지역 쌍 간의 경로를 정의 합니다. 통화 허용 제어 배포의 각 네트워크 지역 쌍에는 네트워크 지역 경로가 필요 합니다. 이렇게 하면 배포 내의 모든 네트워크 영역이 다른 모든 지역에 액세스할 수 있습니다. 이 artilce의 절차를 사용 하 여 네트워크 지역 경로를 보거나, 만들고, 수정 하 고, 삭제할 수 있습니다.

## <a name="view-network-region-route-information"></a>네트워크 지역 경로 정보 보기 

CAC (호출 허용 제어) 구성 내의 모든 지역에는 다른 모든 지역에 액세스 하는 방법이 있어야 합니다. 지역 링크는 지역 간 연결에 대 한 대역폭 제한을 설정 하 고 실제 링크를 표시 하는 경우 경로에 따라 연결이 한 영역에서 다른 지역으로 이동 하는 연결 경로가 결정 됩니다. 비즈니스용 Skype Server 제어판 또는 비즈니스용 Skype 서버 관리 셸에서 기존 네트워크 지역 경로를 보려면 다음 절차를 사용 합니다. 

### <a name="to-view-network-region-route-information-in-skype-for-business-server-control-panel"></a>비즈니스용 Skype Server 제어판에서 네트워크 지역 경로 정보를 보려면

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다. 

3.  왼쪽 탐색 모음에서 **네트워크 구성을**클릭 한 다음 **영역 경로**를 클릭 합니다.

4.  **지역 경로** 페이지에서 보려는 지역 경로를 클릭 합니다.


    > [!NOTE]  
    > 한 번에 하나의 지역 경로만 볼 수 있습니다.


5.  **편집** 메뉴에서 **세부 정보 표시**를 클릭 합니다.


### <a name="viewing-network-region-route-information-by-using-windows-powershell-cmdlets"></a>Windows PowerShell Cmdlet을 사용 하 여 네트워크 지역 영역 라우팅 정보 보기

네트워크 지역 경로 정보는 Windows PowerShell을 사용 하 여 보거나 Get-Csnetworkinter지역 경로 cmdlet을 통해 볼 수 있습니다. 이 cmdlet은 비즈니스용 Skype 서버 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다. 

### <a name="to-view-network-region-route-information"></a>네트워크 지역 경로 정보를 보려면

  - 모든 네트워크 지역 경로에 대 한 정보를 보려면 비즈니스용 Skype 서버 관리 셸에서 다음 명령을 입력 한 다음 enter 키를 누릅니다.
    
        Get-CsNetworkInterRegionRoute
    
    이는 다음과 같은 정보를 반환 합니다.
    
        Identity                  : TransAmericaRoute
        NetworkRegionLinks        : {NorthwestToNortheast}
        InterNetworkRegionRouteID : TransAmericaRoute
        NetworkRegionID1          : Pacific Northwest
        NetworkRegionID2          : Northeast

자세한 내용은 [Get-Csnetworkinter지역 경로](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute) cmdlet에 대 한 도움말 항목을 참조 하세요.


## <a name="create-or-modify-network-region-routes"></a>네트워크 지역 경로 만들기 또는 수정

CAC (호출 허용 제어) 구성 내의 모든 지역에는 다른 모든 지역에 액세스 하는 방법이 있어야 합니다. 지역 링크는 지역 간 연결에 대 한 대역폭 제한을 설정 하 고 실제 링크를 표시 하는 경우 경로에 따라 연결이 한 영역에서 다른 지역으로 이동 하는 연결 경로가 결정 됩니다. 비즈니스용 Skype 서버 제어판을 사용 하 여 네트워크 지역 경로를 구성할 수 있습니다. 비즈니스용 Skype 서버 제어판에서 네트워크 지역 경로를 만들거나 수정 하거나 삭제할 수 있습니다. 이 항목을 사용 하 여 네트워크 지역 경로를 만들거나 수정 합니다. 

### <a name="to-create-a-network-region-route"></a>네트워크 지역 경로를 만들려면

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다. 

3.  왼쪽 탐색 모음에서 **네트워크 구성을**클릭 한 다음 **영역 경로**를 클릭 합니다.

4.  **지역 경로** 페이지에서 **새로 만들기**를 클릭 합니다.

5.  **새 영역 경로**에서 **이름** 필드에 값을 입력 합니다.
   
    > [!NOTE]  
    > 이 값은 비즈니스용 Skype 서버 배포 내에서 고유 해야 합니다.

6.  **네트워크 지역 \#1** 드롭다운 목록에서이 경로로 연결할 두 지역 중 하나를 선택 합니다.

7.  **네트워크 지역 \#2** 드롭다운 목록에서이 경로의 다른 지역을 선택 합니다. 이 지역은 네트워크 지역 \#1에 대해 선택한 지역과 달라 야 합니다.

8.  **네트워크 영역 링크** 목록 상자를 사용 하 여 경로에 지역 링크를 추가 합니다. **추가** 단추를 클릭 하 여 **지역 링크** 페이지를 표시 합니다. 이 경로에 추가할 지역 링크를 클릭 한 다음 **확인**을 클릭 합니다.
    
    > [!NOTE]  
    > **추가** 단추를 계속 클릭 하 여 다른 링크를 추가 하거나 링크를 선택 하 고 **제거** 를 클릭 하 여 링크를 제거 합니다.

9.  **커밋**을 클릭합니다.


### <a name="to-modify-a-network-region-route"></a>네트워크 지역 경로를 수정 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다. 

3.  왼쪽 탐색 모음에서 **네트워크 구성을**클릭 한 다음 **영역 경로**를 클릭 합니다.

4.  **지역 경로** 페이지에서 수정 하려는 지역 경로를 클릭 합니다.

5.  **편집** 메뉴에서 **세부 정보 표시**를 클릭 합니다.

6.  **지역 경로 편집**에서이 경로 또는 경로와 연결 된 지역 링크를 통해 연결 된 영역을 수정할 수 있습니다.

7.  **커밋**을 클릭합니다.


## <a name="delete-existing-network-region-routes"></a>기존 네트워크 지역 경로 삭제

CAC (호출 허용 제어) 구성 내의 모든 지역에는 다른 모든 지역에 액세스 하는 방법이 있어야 합니다. 지역 링크는 지역 간 연결에 대 한 대역폭 제한을 설정 하 고 실제 링크를 표시 하는 경우 경로에 따라 연결이 한 영역에서 다른 지역으로 이동 하는 연결 경로가 결정 됩니다. 비즈니스용 Skype 서버 제어판을 사용 하 여 네트워크 지역 경로를 구성할 수 있습니다. 비즈니스용 Skype 서버 제어판에서 네트워크 지역 경로를 만들거나 수정 하거나 삭제할 수 있습니다. 기존 네트워크 지역 경로를 삭제 하려면이 항목을 사용 합니다. 

### <a name="to-delete-a-network-region-route"></a>네트워크 지역 경로를 삭제 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다. 

3.  왼쪽 탐색 모음에서 **네트워크 구성을**클릭 한 다음 **영역 경로**를 클릭 합니다.

4.  **지역 경로** 페이지에서 삭제 하려는 지역 경로를 클릭 합니다.

    > [!NOTE]  
    > 한 번에 둘 이상의 지역 경로를 삭제할 수 있습니다. 이 작업을 수행 하려면 CTRL 키를 누른 채로 여러 지역 경로를 선택 합니다. 또는 모든 지역 경로를 선택 하려면 **편집** 메뉴에서 **모두 선택을** 클릭 합니다.

5.  **편집** 메뉴에서 **삭제**를 클릭 합니다.

6.  **확인**을 클릭합니다.



## <a name="see-also"></a>참고 항목

[비즈니스용 Skype 서버에서 네트워크 지역 관리](managing-network-regions.md)

[새-Csnetworkinter국가 경로](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)  

[Set-Csnetworkinter국가 경로](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute) 
 
[제거-Csnetworkinter국가 경로](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)  

[Get-Csnetworkinter국가 경로](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)  
