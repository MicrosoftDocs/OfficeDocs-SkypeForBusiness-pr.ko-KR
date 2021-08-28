---
title: 네트워크 서브넷 관리
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: CAC(통화 비즈니스용 Skype 서버 제어)가 구현되는 대부분의 배포에는 일반적으로 많은 수의 서브넷이 있습니다. 따라서 관리 셸에서 서브넷을 구성하는 것이 비즈니스용 Skype 서버 가장 좋은 경우가 있습니다.
ms.openlocfilehash: d7942026a00bd74a7cb21adb045b78dba3b93594
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58600043"
---
# <a name="managing-network-subnets-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 네트워크 서브넷 관리

제어판 또는 비즈니스용 Skype 서버 관리 셸을 사용하여 비즈니스용 Skype 서버 서브넷을 관리할 수 있습니다. CAC(통화 비즈니스용 Skype 서버 제어)가 구현되는 대부분의 배포에는 일반적으로 많은 수의 서브넷이 있습니다. 따라서 관리 셸에서 서브넷을 구성하는 것이 비즈니스용 Skype 서버 가장 좋은 경우가 있습니다.

이 문서의 섹션을 사용하여 네트워크 서브넷 정보를 보거나 네트워크 서브넷을 만들거나 수정하거나 삭제할 수 있습니다. 

## <a name="view-network-subnet-information"></a>네트워크 서브넷 정보 보기 

다음 절차에 따라 네트워크 서브넷을 볼 수 있습니다. 비즈니스용 Skype 서버 제어판에서 네트워크 서브넷을 만들거나 수정하거나 삭제할 수 있습니다. 

### <a name="to-view-a-network-subnet"></a>네트워크 서브넷을 보려면

1.  RTCUniversalServerAdmins 그룹의 구성원 또는 이와 동등한 사용자 권한을 가졌다는 사용자 계정 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포의 컴퓨터에 로그온합니다.

2.  브라우저 창을 열고 관리 URL을 입력하여 관리 비즈니스용 Skype 서버 열 수 있습니다. 

3.  왼쪽 탐색 모음에서 네트워크 구성 **을 클릭한** 다음 **서브넷 을 클릭합니다.**

4.  **서브넷** 페이지에서 보려는 서브넷을 클릭합니다.
 
    > [!NOTE]
    > 서브넷을 한 번에 하나만 볼 수 있습니다.

5.  **편집** 메뉴에서 **자세한 정보 표시** 를 클릭합니다.

### <a name="view-network-subnet-configuration-information-by-using-windows-powershell-cmdlets"></a>cmdlet을 사용하여 네트워크 서브넷 Windows PowerShell 보기

네트워크 서브넷 정보는 Windows PowerShell cmdlet을 사용하여 Get-CsNetworkSubnet 있습니다. 이 cmdlet은 관리 셸 또는 비즈니스용 Skype 서버 원격 세션에서 실행할 수 Windows PowerShell. 

### <a name="to-view-network-subnet-information"></a>네트워크 서브넷 정보를 보기 위해

  - 모든 네트워크 서브넷에 대한 정보를 보기 위해 비즈니스용 Skype 서버 관리 셸에서 다음 명령을 입력한 다음 Enter를 눌러야 합니다.
    
    **Get-CsNetworkSubnet**
    
    그러면 다음과 같은 정보가 반환됩니다.
    
    ID : 172.11.15.0<br/>
    MaskBits : 28<br/>
    설명 :<br/>
    NetworkSiteID : Redmond<br/>
    SubnetID : 172.11.15.0<br/>


자세한 내용은 [Get-CsNetworkSubnet](/powershell/module/skype/Get-CsNetworkSubnet) cmdlet의 도움말 항목을 참조하십시오.


## <a name="create-or-modify-network-subnets"></a>네트워크 서브넷 만들기 또는 수정 

네트워크 서브넷은 해당 서브넷에 속한 호스트의 지리적 위치를 확인할 수 있도록 네트워크 사이트에 연결되어야 합니다. 제어판을 사용하여 비즈니스용 Skype 서버 구성할 수 있습니다. 비즈니스용 Skype 서버 제어판에서 네트워크 서브넷을 만들거나 수정하거나 삭제할 수 있습니다. 

CAC(통화 비즈니스용 Skype 서버 제어)가 구현되는 대부분의 배포에는 일반적으로 많은 수의 서브넷이 있습니다. 따라서 관리 셸에서 서브넷을 구성하는 것이 비즈니스용 Skype 서버 가장 좋은 경우가 있습니다. 그런 다음 Import-CSV cmdlet과 함께 **New-CsNetworkSubnet을** 호출할 Windows PowerShell **있습니다.** 두 cmdlet을 함께 사용하면 CSV(쉼표로 구분된 값) 파일에서 서브넷 설정을 읽어와서 여러 개의 서브넷을 동시에 만들 수 있습니다. .csv 파일에서 서브넷을 만드는 방법의 예는 [New-CsNetworkSubnet](/powershell/module/skype/New-CsNetworkSubnet)을 참조하십시오.


### <a name="to-create-a-network-subnet"></a>네트워크 서브넷을 만들려면

1.  RTCUniversalServerAdmins 그룹의 구성원 또는 이와 동등한 사용자 권한을 가졌다는 사용자 계정 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포의 컴퓨터에 로그온합니다.

2.  브라우저 창을 열고 관리 URL을 입력하여 관리 비즈니스용 Skype 서버 열 수 있습니다. 

3.  왼쪽 탐색 모음에서 네트워크 구성 **을 클릭한** 다음 **서브넷 을 클릭합니다.**

4.  **서브넷** 페이지에서 **다음** 을 클릭합니다.

5.  **새 서브넷** 의 **서브넷 ID** 필드에 값을 입력합니다. 이 ID는 IP 주소(예: 174.11.12.0)여야 하며 서브넷으로 정의된 IP 주소 범위의 첫 번째 주소여야 합니다.

6.  **마스크** 필드에 1에서 32 사이의 숫자 값을 입력합니다.

    > [!NOTE]  
    > 이 값은 작성 중인 서브넷에 적용할 비트 마스크입니다.

7.  **네트워크 사이트 ID** 에서 이 서브넷이 속하는 사이트를 선택합니다.

8.  (선택 사항) 이름만으로는 표현할 수 없는 이 서브넷에 대한 자세한 정보를 제공하려면 **설명** 필드에 값을 입력합니다.

9.  **커밋** 을 클릭합니다.


### <a name="to-modify-a-network-subnet"></a>네트워크 서브넷을 수정하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 또는 이와 동등한 사용자 권한을 가졌다는 사용자 계정 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포의 컴퓨터에 로그온합니다.

2.  브라우저 창을 열고 관리 URL을 입력하여 관리 비즈니스용 Skype 서버 열 수 있습니다. 

3.  왼쪽 탐색 모음에서 네트워크 구성 **을 클릭한** 다음 **서브넷 을 클릭합니다.**

4.  **서브넷** 페이지에서 수정할 서브넷을 클릭합니다.

5.  **편집** 메뉴에서 **자세한 정보 표시** 를 클릭합니다.

6.  **서브넷 편집** 페이지에서 비트 마스크, 연결된 네트워크 사이트 또는 설명을 수정할 수 있습니다. 비트 마스크를 수정하는 경우에도 서브넷 ID는 서브넷으로 정의된 IP 주소 범위의 첫 번째 주소여야 합니다.

7.  **커밋** 을 클릭합니다.

## <a name="delete-network-subnets"></a>네트워크 서브넷 삭제

다음 절차를 사용하여 서브넷을 삭제할 수 있습니다. 비즈니스용 Skype 서버 제어판에서 네트워크 서브넷을 만들거나 수정하거나 삭제할 수 있습니다. 

CAC(통화 비즈니스용 Skype 서버 제어)가 구현되는 대부분의 배포에는 일반적으로 많은 수의 서브넷이 있습니다. 따라서 관리 셸에서 서브넷을 구성하는 것이 비즈니스용 Skype 서버 가장 좋은 경우가 있습니다. 그런 다음 Import-CSV cmdlet과 함께 **New-CsNetworkSubnet을** 호출할 Windows PowerShell **있습니다.** 두 cmdlet을 함께 사용하면 CSV(쉼표로 구분된 값) 파일에서 서브넷 설정을 읽어와서 여러 개의 서브넷을 동시에 만들 수 있습니다. .csv 파일에서 서브넷을 만드는 방법의 예제는 [New-CsNetworkSubnet](/powershell/module/skype/New-CsNetworkSubnet)을 참조하십시오.


### <a name="to-delete-a-network-subnet"></a>네트워크 서브넷을 삭제하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 또는 이와 동등한 사용자 권한을 가졌다는 사용자 계정 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포의 컴퓨터에 로그온합니다.

2.  브라우저 창을 열고 관리 URL을 입력하여 관리 비즈니스용 Skype 서버 열 수 있습니다. 

3.  왼쪽 탐색 모음에서 네트워크 구성 **을 클릭한** 다음 **서브넷 을 클릭합니다.**

4.  **서브넷** 페이지에서 삭제할 서브넷을 클릭합니다.
 
    > [!NOTE]  
    > 한 번에 둘 이상의 서브넷을 삭제할 수 있습니다. 이렇게 하려면 Ctrl 키를 누른 상태에서 여러 서브넷을 선택합니다. 또는 모든 서브넷을 선택하려면 **편집** 메뉴에서 **모두 선택** 을 클릭합니다.

5.  **편집** 메뉴에서 **삭제** 를 클릭합니다.

6.  **확인** 을 클릭합니다.


## <a name="see-also"></a>참고 항목

[New-CsNetworkSubnet](/powershell/module/skype/New-CsNetworkSubnet)  

[Set-CsNetworkSubnet](/powershell/module/skype/Set-CsNetworkSubnet)  

[Remove-CsNetworkSubnet](/powershell/module/skype/Remove-CsNetworkSubnet)  

[Get-CsNetworkSubnet](/powershell/module/skype/Get-CsNetworkSubnet)