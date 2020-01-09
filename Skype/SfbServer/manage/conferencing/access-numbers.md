---
title: '비즈니스용 Skype 서버에서 전화 접속 회의 액세스 번호 관리 '
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a0d64779-93de-4d82-ae35-e4454ef8b8f6
description: '요약: 비즈니스용 Skype 서버에서 전화 접속 회의 액세스 번호를 관리 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: bd2aff1789c040667062d34b8bc037fd0543c029
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991923"
---
# <a name="manage-dial-in-conferencing-access-numbers-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 전화 접속 회의 액세스 번호 관리
 
**요약:** 비즈니스용 Skype 서버에서 전화 접속 회의 액세스 번호를 관리 하는 방법에 대해 알아봅니다.
  
전화 접속 회의를 배포 하는 경우 오디오 회의에 참가 하기 위해 사용자가 PSTN (공개 전환 전화 네트워크)에서 전화를 걸 수 있는 전화 번호를 설정 해야 합니다. 이러한 전화 접속 액세스 번호는 모임 초대 및 전화 접속 회의 설정 웹 페이지에 표시 됩니다. 
  
이 항목에서는 기존 전화 접속 회의 액세스 번호를 보거나, 수정 하거나, 삭제 하는 방법에 대해 설명 합니다. 초기 전화 접속 액세스 번호를 만드는 방법에 대 한 자세한 내용은 비즈니스용 [Skype 서버에서 전화 접속 회의 구성을](../../deploy/deploy-conferencing/dial-in-conferencing.md)참조 하세요.
  
## <a name="view-dial-in-conferencing-access-numbers"></a>전화 접속 회의 액세스 번호 보기

비즈니스용 Skype Server 제어판을 사용 하거나 비즈니스용 Skype Server Management Shell을 사용 하 여 전화 접속 회의 액세스 번호를 볼 수 있습니다.
  
### <a name="view-dial-in-access-numbers-by-using-skype-for-business-server-control-panel"></a>비즈니스용 Skype 서버 제어판을 사용 하 여 전화 접속 액세스 번호 보기

1. CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.
    
2.  비즈니스용 Skype Server 제어판을 엽니다.
    
3. 왼쪽 탐색 모음에서 **회의**를 클릭 한 다음 **전화 접속 액세스 번호**를 클릭 합니다.
    
4. **전화 접속 액세스 번호** 페이지에서 보려는 액세스 번호를 클릭 합니다.
    
5. **편집**에서 **세부 정보 표시** 확인란을 선택 합니다.
    
### <a name="view-dial-in-access-numbers-by-using-skype-for-business-server-management-shell"></a>비즈니스용 Skype Server Management Shell을 사용 하 여 전화 접속 액세스 번호 보기

전화 접속 액세스 번호에 대 한 정보를 보려면 **Get-CsDialInConferencingAccessNumber** cmdlet을 사용 합니다.
  
다음 명령은 조직에서 사용 하도록 구성 된 모든 전화 접속 회의 액세스 번호의 컬렉션을 반환 합니다. 
  
```PowerShell
Get-CsDialInConferencingAccessNumber
```

다음은 반환 되는 정보 유형의 예입니다.
  
<pre>
Identity           : CN={20ca8dc8-5ff8-41f4-b5bb-22ba9972ae2e},
                     CN=Application Contacts,CN=RTCService=Services,
                     CN=Configuration,DC=litwareinc,DC=com
PrimaryUri         : sip:testnumber@litwareinc.com
DisplayName        : Test
DisplayNumber      : 1-425-555-1019
LineUri            : tel:+14255551019
PrimaryLanguage    : en-US
SecondaryLanguages : {}
Pool               : atl-cs-001.litwareinc.com
HostingProvider    :
Regions            : {US}
</pre>

자세한 내용은 [get-help를 CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps)을 참조 하세요.
  
## <a name="modify-dial-in-conferencing-access-numbers"></a>전화 접속 회의 액세스 번호 수정

Skype for Business Server 제어판을 사용 하거나 비즈니스용 Skype 서버 관리 셸을 사용 하 여 전화 접속 액세스 번호를 수정할 수 있습니다.
  
### <a name="modify-dial-in-access-numbers-by-using-skype-for-business-server-control-panel"></a>비즈니스용 Skype Server 제어판을 사용 하 여 전화 접속 액세스 번호 수정

1. CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.
    
2.  비즈니스용 Skype Server 제어판을 엽니다.
    
3. 왼쪽 탐색 모음에서 **회의**를 클릭 한 다음 **전화 접속 액세스 번호**를 클릭 합니다.
    
4. **전화 접속 액세스 번호** 페이지에서 목록에 있는 전화 접속 액세스 번호 중 하나를 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.
    
    > [!NOTE]
    > 검색 필드를 사용 하 여 전화 접속 액세스 번호 목록에서 열의 내용을 검색 하면 예상한 결과가 생성 되지 않을 수 있습니다. 대신 원하는 열을 기준으로 목록을 정렬 하 여 보거나 변경 하려는 전화 접속 액세스 번호를 확인 합니다. 
  
5. **표시 번호**에 공개 전환 전화 네트워크 (PSTN) 전화 사용자가 전화를 걸고 있는 전화 번호를 입력 합니다. 
    
    이 번호는 모임 초대 및 전화 접속 회의 설정 웹 페이지에 표시 됩니다.
    
6. **표시 이름**에 전화 접속 액세스 번호에 대 한 설명을 입력 합니다. 비즈니스용 Skype 검색 결과에서 전화 접속 액세스 번호와 연결 된 이름입니다.
    
    이 이름은 사용자가 액세스 번호를 호출할 때 클라이언트에 표시 됩니다. 
    
7. **줄 uri**에서 번호 앞에 + 기호를 포함 하 고 공백을 제외 하 고 TEL uri 형식의 전화 접속 액세스 번호에 대 한 E 자의 번호를 입력 합니다. 예를 들어, tel: + 14255550200.
    
    > [!NOTE]
    > 같은 회선 URI를 다른 전화 접속 회의 액세스 번호로 재사용할 수 없습니다. 
  
8. **SIP URI**에서 다음을 수행 합니다.
    
   입력란에이 전화 접속 회의 액세스 번호에 대 한 고유한 SIP URI를 입력 합니다. 이 SIP URI는 통화 알림 메시지 및 이전 버전의 Lync 클라이언트를 포함 하 여 다양 한 위치에 표시 됩니다.
    
    > [!NOTE]
    > 같은 SIP URI를 다른 전화 접속 회의 액세스 번호에서 다시 사용할 수 없습니다. 액세스 번호를 만든 후 SIP URI를 수정할 수 없습니다. SIP URI를 변경 하는 유일한 방법은 액세스 번호를 삭제 하 고 다시 만드는 것입니다. 
  
   드롭다운 목록 상자에서이 전화 접속 액세스 번호를 지 원하는 회의 수행자 응용 프로그램의 도메인을 클릭 합니다.
    
9. **풀**에서이 전화 접속 액세스 번호를 지 원하는 회의 전화 교환 인스턴스를 실행 하는 풀을 클릭 합니다.
    
    > [!NOTE]
    > 액세스 번호를 만든 후에 풀을 변경 해야 하는 경우 **-CsApplicationEndpoint** cmdlet을 사용 하거나 액세스 번호를 삭제 하 고 다시 만들어야 합니다.
  
10. **기본 언어**에서이 전화 접속 액세스 번호에 대 한 메시지가 재생 되는 언어를 클릭 합니다. 
    
    기본 언어는 회의 수행자가 통화에 응답 하는 데 사용 하는 언어입니다. 지원 되는 언어는 전화 접속 회의 설정 웹 페이지의 각 액세스 전화 번호 옆에 표시 됩니다.
    
11. ) **보조 언어 (최대 4 개)** 에서 **추가**를 클릭 하 고이 전화 접속 액세스 번호에 대 한 호출자에 대해 지원할 추가 언어를 하나 이상 선택 하 고 **확인**을 클릭 합니다. 
    
    각 전화 접속 액세스 번호에 대해 최대 4 개의 보조 언어를 선택할 수 있습니다. 사용자가 회의에 전화를 걸 때 전화 회의 ID를 입력 하기 전에 보조 언어를 선택할 수 있습니다.
    
12. 전화 접속 액세스 번호에 대 한 영역을 추가 하려면 **연결 된 지역**에서 **추가**를 클릭 하 고이 전화 접속 액세스 번호에 대 한 다이얼 플랜에 연결 된 하나 이상의 지역을 클릭 한 다음 **확인**을 클릭 합니다.
    
13. 전화 접속 액세스 번호에서 지역을 삭제 하려면 **연결 된 지역**에서 삭제할 지역을 클릭 한 다음 **제거**를 클릭 합니다.
    
14. **커밋**을 클릭합니다.
    
### <a name="modify-dial-in-access-numbers-by-using-skype-for-business-server-management-shell"></a>비즈니스용 Skype Server Management Shell을 사용 하 여 전화 접속 액세스 번호 수정

전화 접속 액세스 번호를 수정 하려면 **Set-CsDialInConferencingAccessNumber** cmdlet을 사용 합니다.
  
다음 명령은 Id sip:RedmondDialIn@litwareinc.com를 사용 하 여 전화 접속 회의 액세스 번호의 DisplayName 속성을 수정 합니다. 이 예제에서는 표시 이름이 "Redmond 전화 접속 액세스 번호"로 설정 됩니다.
  
```PowerShell
Set-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialIn@litwareinc.com" -DisplayName "Redmond Dial-In Access Number"
```

다음 예제에서 Id sip:RedmondDialIn@litwareinc.com를 사용한 전화 접속 회의 액세스 번호는 Redmond와 시애틀 두 지역을 포함 하도록 수정 됩니다. 이렇게 하려면 Regions 매개 변수를 호출한 다음 두 개의 영역 (쉼표로 구분 된 두 개의 문자열 값)을 입력 합니다. 이 명령은 Redmond 및 시애틀 지역 영역이 이미 다이얼 플랜에 정의 되어 있지 않는 한 실패 합니다.
  
```PowerShell
Set-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialIn@litwareinc.com" -Regions "Redmond", "Seattle"
```

자세한 내용은 [Set-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps)을 참조 하세요.
  
## <a name="delete-a-dial-in-conferencing-access-number"></a>전화 접속 회의 액세스 번호 삭제

비즈니스용 Skype Server 제어판을 사용 하거나 비즈니스용 Skype Server Management Shell을 사용 하 여 전화 접속 회의 액세스 번호를 삭제할 수 있습니다.
  
### <a name="delete-a-dial-in-conferencing-access-number-by-using-skype-for-business-server-control-panel"></a>비즈니스용 Skype 서버 제어판을 사용 하 여 전화 접속 회의 액세스 번호 삭제

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 비즈니스용 Skype 서버를 배포한 네트워크의 컴퓨터에 로그온 합니다. .
    
2.  비즈니스용 Skype Server 제어판을 엽니다.
    
3. 왼쪽 탐색 모음에서 **회의**를 클릭 한 다음 **전화 접속 액세스 번호**를 클릭 합니다.
    
4. 페이지에서 목록에서 삭제 하려는 전화 접속 번호를 클릭 하 고 **편집**을 클릭 한 다음 **삭제**를 클릭 합니다.
    
5. **확인**을 클릭합니다.
    
### <a name="delete-a-dial-in-conferencing-access-number-by-using-skype-for-business-server-management-shell"></a>비즈니스용 Skype Server Management Shell을 사용 하 여 전화 접속 회의 액세스 번호 삭제

전화 접속 회의 액세스 번호를 삭제 하려면 **제거-CsDialInConferencingAccessNumber**를 사용 합니다.
  
다음 명령은 Id sip:RedmondDialInAccess@litwareinc.com를 사용 하 여 전화 접속 회의 액세스 번호를 삭제 합니다.
  
```PowerShell
Remove-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialInAccess@litwareinc.com"
```

다음 명령은 북서쪽 지역과 연결 된 전화 접속 회의 액세스 번호를 모두 삭제 합니다.
  
```PowerShell
Get-CsDialInConferencingAccessNumber -Region "Northwest" | Remove-CsDialInConferencingAccessNumber
```

다음 명령은 이탈리아어가 기본 언어인 모든 전화 접속 회의 액세스 번호를 삭제 합니다.
  
```PowerShell
Get-CsDialInConferencingAccessNumber | Where-Object {$_.PrimaryLanguage -eq "it-IT"} | Remove-CsDialInConferencingAccessNumber
```

자세한 내용은 [제거-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps)를 참조 하세요.
  

