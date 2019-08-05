---
title: 네트워크 서브넷 관리
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 호출 허용 제어 (CAC)가 구현 된 비즈니스용 Skype 서버를 대부분 배포 하는 경우에는 일반적으로 서브넷 수가 많습니다. 이 때문에 비즈니스용 Skype 서버 관리 셸에서 서브넷을 구성 하는 것이 가장 좋습니다.
ms.openlocfilehash: 354dd43fd526ba2a6c6f88c8e1f30d0aae37b3bb
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188559"
---
# <a name="managing-network-subnets-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 네트워크 서브넷 관리

비즈니스용 Skype Server 제어판 또는 비즈니스용 Skype Server Management Shell을 사용 하 여 네트워크 서브넷을 관리할 수 있습니다. 호출 허용 제어 (CAC)가 구현 된 비즈니스용 Skype 서버를 대부분 배포 하는 경우에는 일반적으로 서브넷 수가 많습니다. 이 때문에 비즈니스용 Skype 서버 관리 셸에서 서브넷을 구성 하는 것이 가장 좋습니다.

이 문서의 섹션을 사용 하 여 네트워크 서브넷 정보를 보거나 네트워크 서브넷을 만들거나 수정 하거나 삭제할 수 있습니다. 

## <a name="view-network-subnet-information"></a>네트워크 서브넷 정보 보기 

다음 절차를 사용 하 여 네트워크 서브넷을 볼 수 있습니다. 비즈니스용 Skype 서버 제어판에서 네트워크 서브넷을 만들거나 수정 하거나 삭제할 수 있습니다. 

### <a name="to-view-a-network-subnet"></a>네트워크 서브넷을 보려면

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다. 

3.  왼쪽 탐색 모음에서 **네트워크 구성을**클릭 한 다음 **서브넷**을 클릭 합니다.

4.  **서브넷** 페이지에서 보려는 서브넷을 클릭 합니다.
 
    > [!NOTE]  
    > 한 번에 하나의 서브넷만 볼 수 있습니다.

5.  **편집** 메뉴에서 **세부 정보 표시**를 클릭 합니다.

### <a name="view-network-subnet-configuration-information-by-using-windows-powershell-cmdlets"></a>Windows PowerShell cmdlet을 사용 하 여 네트워크 서브넷 구성 정보 보기

네트워크 서브넷 정보는 Windows PowerShell 및 Get-CsNetworkSubnet cmdlet을 사용 하 여 볼 수 있습니다. 이 cmdlet은 비즈니스용 Skype 서버 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다. 

### <a name="to-view-network-subnet-information"></a>네트워크 서브넷 정보를 보려면

  - 모든 네트워크 서브넷에 대 한 정보를 보려면 비즈니스용 Skype 서버 관리 셸에서 다음 명령을 입력 한 다음 enter 키를 누릅니다.
    
        Get-CsNetworkSubnet
    
    이는 다음과 같은 정보를 반환 합니다.
    
        Identity      : 172.11.15.0
        MaskBits      : 28
        Description   :
        NetworkSiteID : Redmond
        SubnetID      : 172.11.15.0


자세한 내용은 [Get CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet) cmdlet에 대 한 도움말 항목을 참조 하세요.


## <a name="create-or-modify-network-subnets"></a>네트워크 서브넷 만들기 또는 수정 

네트워크 서브넷이이 서브넷에 속한 호스트의 지리적 위치를 확인 하기 위해 네트워크 사이트와 연결 되어 있어야 합니다. 비즈니스용 Skype 서버 제어판을 사용 하 여 서브넷을 구성할 수 있습니다. 비즈니스용 Skype 서버 제어판에서 네트워크 서브넷을 만들거나 수정 하거나 삭제할 수 있습니다. 

호출 허용 제어 (CAC)가 구현 된 비즈니스용 Skype 서버를 대부분 배포 하는 경우에는 일반적으로 서브넷 수가 많습니다. 이 때문에 비즈니스용 Skype 서버 관리 셸에서 서브넷을 구성 하는 것이 가장 좋습니다. 여기서는 Windows PowerShell cmdlet **가져오기-CSV**와 함께 **새 csnetworksubnet** 을 호출할 수 있습니다. 이러한 cmdlet을 함께 사용 하 여 쉼표로 구분 된 값 (.csv) 파일의 서브넷 설정을 읽고 동시에 여러 개의 서브넷을 만들 수 있습니다. .Csv 파일에서 서브넷을 만드는 방법에 대 한 예는 [새 CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)을 참조 하세요.


### <a name="to-create-a-network-subnet"></a>네트워크 서브넷을 만들려면

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다. 

3.  왼쪽 탐색 모음에서 **네트워크 구성을**클릭 한 다음 **서브넷**을 클릭 합니다.

4.  **서브넷** 페이지에서 **새로 만들기**를 클릭 합니다.

5.  **새 서브넷**에서 **서브넷 ID** 필드에 값을 입력 합니다. 이는 IP 주소 (예: 174.11.12.0) 여야 하며 서브넷에 정의 된 IP 주소 범위에서 첫 번째 주소 여야 합니다.

6.  **마스크** 필드에 1부터 32 까지의 숫자 값을 입력 합니다.

    > [!NOTE]  
    > 이 값은 만들려는 서브넷에 적용 되는 비트 마스크입니다.

7.  **네트워크 사이트 ID**에서이 서브넷이 속한 사이트를 선택 합니다.

8.  ) 이름 만으로 표현할 수 없는이 서브넷에 대 한 자세한 정보를 제공 하려면 **설명** 필드에 값을 입력 합니다.

9.  **커밋**을 클릭합니다.


### <a name="to-modify-a-network-subnet"></a>네트워크 서브넷을 수정 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다. 

3.  왼쪽 탐색 모음에서 **네트워크 구성을**클릭 한 다음 **서브넷**을 클릭 합니다.

4.  **서브넷** 페이지에서 수정 하려는 서브넷을 클릭 합니다.

5.  **편집** 메뉴에서 **세부 정보 표시**를 클릭 합니다.

6.  **서브넷 편집** 페이지에서 비트 마스크, 관련 네트워크 사이트 또는 설명을 수정할 수 있습니다. 비트 마스크를 수정 하는 경우 서브넷 ID가 서브넷에 정의 된 IP 주소 범위에서 첫 번째 주소 여야 한다는 점에 유의 하세요.

7.  **커밋**을 클릭합니다.

## <a name="delete-network-subnets"></a>네트워크 서브넷 삭제

다음 절차를 사용 하 여 서브넷을 삭제할 수 있습니다. 비즈니스용 Skype 서버 제어판에서 네트워크 서브넷을 만들거나 수정 하거나 삭제할 수 있습니다. 

호출 허용 제어 (CAC)가 구현 된 비즈니스용 Skype 서버를 대부분 배포 하는 경우에는 일반적으로 서브넷 수가 많습니다. 이 때문에 비즈니스용 Skype 서버 관리 셸에서 서브넷을 구성 하는 것이 가장 좋습니다. 여기서는 Windows PowerShell cmdlet **가져오기-CSV**와 함께 **새 csnetworksubnet** 을 호출할 수 있습니다. 이러한 cmdlet을 함께 사용 하 여 쉼표로 구분 된 값 (.csv) 파일의 서브넷 설정을 읽고 동시에 여러 개의 서브넷을 만들 수 있습니다. .Csv 파일에서 서브넷을 만드는 방법에 대 한 예는 [새 CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)을 참조 하세요.


### <a name="to-delete-a-network-subnet"></a>네트워크 서브넷을 삭제 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다. 

3.  왼쪽 탐색 모음에서 **네트워크 구성을**클릭 한 다음 **서브넷**을 클릭 합니다.

4.  **서브넷** 페이지에서 삭제 하려는 서브넷을 클릭 합니다.
 
    > [!NOTE]  
    > 한 번에 둘 이상의 서브넷을 삭제할 수 있습니다. 이 작업을 수행 하려면 ctrl 키를 누른 채 여러 서브넷을 선택 합니다. 또는 모든 서브넷을 선택 하려면 **편집** 메뉴에서 **모두 선택을** 클릭 합니다.

5.  **편집** 메뉴에서 **삭제**를 클릭 합니다.

6.  **확인**을 클릭합니다.


## <a name="see-also"></a>참고 항목

[새-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)  

[Set-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSubnet)  

[CsNetworkSubnet 제거](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSubnet)  

[Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)  
