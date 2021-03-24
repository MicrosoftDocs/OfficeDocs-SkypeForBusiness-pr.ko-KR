---
title: '비즈니스용 Skype 서버에서 전화 접속 회의 액세스 번호 관리 '
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
ms.assetid: a0d64779-93de-4d82-ae35-e4454ef8b8f6
description: '요약: 비즈니스용 Skype 서버에서 전화 접속 회의 액세스 번호를 관리하는 방법을 설명하는 정보를 제공합니다.'
ms.openlocfilehash: 4008293015beaa684f9a3d9fa0ec0dedf05e5b2b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51099154"
---
# <a name="manage-dial-in-conferencing-access-numbers-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 전화 접속 회의 액세스 번호 관리
 
**요약:** 비즈니스용 Skype 서버에서 전화 접속 회의 액세스 번호를 관리하는 방법을 배워야 합니다.
  
전화 접속 회의를 배포하려면 회의의 오디오 부분에 참가하기 위해 사용자가 PSTN(공중 전화망)을 통해 전화를 걸 수 있는 전화 번호를 설정해야 합니다. 이러한 전화 접속 액세스 번호는 모임 초대장 및 전화 접속 회의 설정 웹 페이지에 표시됩니다. 
  
이 항목에서는 기존 전화 접속 회의 액세스 번호를 보거나 수정하거나 삭제하는 방법에 대해 설명합니다. 초기 전화 접속 액세스 번호를 만드는 방법에 대한 자세한 내용은 [Configure dial-in conferencing in Skype for Business Server을 참조하십시오.](../../deploy/deploy-conferencing/dial-in-conferencing.md)
  
## <a name="view-dial-in-conferencing-access-numbers"></a>전화 접속 회의 액세스 번호 보기

비즈니스용 Skype 서버 제어판 또는 비즈니스용 Skype 서버 관리 셸을 사용하여 전화 접속 회의 액세스 번호를 볼 수 있습니다.
  
### <a name="view-dial-in-access-numbers-by-using-skype-for-business-server-control-panel"></a>비즈니스용 Skype 서버 제어판을 사용하여 전화 접속 액세스 번호 보기

1. CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.
    
2.  비즈니스용 Skype 서버 제어판을 니다.
    
3. 왼쪽 탐색 모음에서 **회의** 를 클릭한 다음 **전화 접속 액세스 번호** 를 클릭합니다.
    
4. **전화 접속 액세스 번호** 페이지에서 보려는 액세스 번호를 클릭합니다.
    
5. 편집에서 자세한 정보 **표시 확인란을** 선택합니다. 
    
### <a name="view-dial-in-access-numbers-by-using-skype-for-business-server-management-shell"></a>비즈니스용 Skype 서버 관리 셸을 사용하여 전화 접속 액세스 번호 보기

전화 접속 액세스 번호에 대한 정보를 보기 위해 **Get-CsDialInConferencingAccessNumber** cmdlet을 사용하세요.
  
다음 명령은 조직에서 사용하도록 구성된 모든 전화 접속 회의 액세스 번호 컬렉션을 반환합니다. 
  
```PowerShell
Get-CsDialInConferencingAccessNumber
```

다음은 반환되는 정보 유형의 예입니다.
  
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

자세한 내용은 [Get-CsDialInConferencingAccessNumber를 참조하십시오.](/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps)
  
## <a name="modify-dial-in-conferencing-access-numbers"></a>전화 접속 회의 액세스 번호 수정

비즈니스용 Skype 서버 제어판 또는 비즈니스용 Skype 서버 관리 셸을 사용하여 전화 접속 액세스 번호를 수정할 수 있습니다.
  
### <a name="modify-dial-in-access-numbers-by-using-skype-for-business-server-control-panel"></a>비즈니스용 Skype 서버 제어판을 사용하여 전화 접속 액세스 번호 수정

1. CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.
    
2.  비즈니스용 Skype 서버 제어판을 니다.
    
3. 왼쪽 탐색 모음에서 **회의** 를 클릭한 다음 **전화 접속 액세스 번호** 를 클릭합니다.
    
4. 전화 **접속 액세스** 번호 페이지에서 목록의 전화 접속 액세스 번호 중 하나를 클릭하고 **편집을** 클릭한 다음 자세한 정보 **표시를 클릭합니다.**
    
    > [!NOTE]
    > 검색 필드를 사용하여 전화 접속 액세스 번호 목록에서 열의 내용을 검색하면 예상한 결과가 산출되지 않을 수 있습니다. 대신 보거나 변경할 전화 접속 액세스 번호를 식별하기 위해 원하는 열별로 목록을 정렬합니다. 
  
5. 표시 **번호에** PSTN(전화망) 전화 사용자가 전화 회의에 참가하기 위해 전화를 걸 전화 번호를 입력합니다. 
    
    이 번호는 모임 초대 및 전화 접속 회의 설정 웹 페이지로 표시됩니다.
    
6. 표시 **이름에** 전화 접속 액세스 번호에 대한 설명을 입력합니다. 비즈니스용 Skype 검색 결과의 전화 접속 액세스 번호와 연결된 이름입니다.
    
    이 이름은 사용자가 액세스 번호로 전화를 걸 때 클라이언트에 표시됩니다. 
    
7. 줄 **URI에** 번호 앞에 + 기호를 입력하고 공백을 제외한 전화 접속 액세스 번호의 E.164 번호를 TEL URI 형식으로 입력합니다. 예: tel:+14255550200.
    
    > [!NOTE]
    > 다른 전화 접속 회의 액세스 번호에서 동일한 줄 URI를 다시 사용할 수 없습니다. 
  
8. **SIP URI에서** 다음을 합니다.
    
   텍스트 상자에 이 전화 접속 회의 액세스 번호에 대한 고유한 SIP URI를 입력합니다. 이 SIP URI는 통화 알림 메시지 및 이전 버전의 Lync 클라이언트를 비롯한 다양한 위치에 표시됩니다.
    
    > [!NOTE]
    > 다른 전화 접속 회의 액세스 번호에서 동일한 SIP URI를 다시 사용할 수 없습니다. 액세스 번호를 만든 후 SIP URI를 수정할 수 없습니다. SIP URI를 변경하는 유일한 방법은 액세스 번호를 삭제하고 다시 만드는 것입니다. 
  
   드롭다운 목록 상자에서 이 전화 접속 액세스 번호를 지원하는 회의 전화 접속 응용 프로그램의 도메인을 클릭합니다.
    
9. **풀에서** 이 전화 접속 액세스 번호를 지원하는 회의 전화 접속자 인스턴스를 실행하는 풀을 클릭합니다.
    
    > [!NOTE]
    > 액세스 번호를 만든 후 풀을 변경해야 하는 경우 **Move-CsApplicationEndpoint** cmdlet을 사용하거나 액세스 번호를 삭제하고 다시 만들어야 합니다.
  
10. 기본 **언어에서** 이 전화 접속 액세스 번호에 대해 프롬프트가 재생되는 언어를 클릭합니다. 
    
    기본 언어는 회의 참석자에서 통화에 응답하는 데 사용하는 언어입니다. 지원되는 언어는 전화 접속 회의 설정 웹 페이지의 각 액세스 전화 번호와 함께 표시됩니다.
    
11. (선택 사항) 보조 **언어(최대 4개)에서** 추가를 클릭하고, 이 전화 접속 액세스 번호에 대한 발신자에 대해 지원할 추가 언어를 하나 이상 선택하고 확인을 **클릭합니다.**  
    
    각 전화 접속 액세스 번호에 대해 최대 4개의 보조 언어를 선택할 수 있습니다. 사용자는 전화 회의에 전화 접속할 때 전화 회의 ID를 입력하기 전에 보조 언어를 선택할 수 있습니다.
    
12. 전화 접속 액세스 번호에 대한 지역을 추가하려면 관련 지역 아래에서 **추가를** 클릭하고 이 전화 접속 액세스 번호의 다이얼 플랜과 연결된 하나 이상의 지역을 클릭한 다음 확인을 **클릭합니다.**
    
13. 전화 접속 액세스 번호에서 지역을 삭제하려면 연결된 지역 아래에서 삭제할 지역을 클릭한 다음 제거를 **클릭합니다.** 
    
14. **커밋** 을 클릭합니다.
    
### <a name="modify-dial-in-access-numbers-by-using-skype-for-business-server-management-shell"></a>비즈니스용 Skype 서버 관리 셸을 사용하여 전화 접속 액세스 번호 수정

전화 접속 액세스 번호를 수정하려면 **Set-CsDialInConferencingAccessNumber** cmdlet을 사용 합니다.
  
다음 명령은 ID가 id와 함께 전화 접속 회의 액세스 번호의 DisplayName 속성을 sip:RedmondDialIn@litwareinc.com. 이 예에서 표시 이름은 "Redmond Dial-In Access Number"로 설정됩니다.
  
```PowerShell
Set-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialIn@litwareinc.com" -DisplayName "Redmond Dial-In Access Number"
```

다음 예제에서는 ID가 id인 전화 접속 회의 액세스 sip:RedmondDialIn@litwareinc.com Redmond와 Seattle의 두 지역을 포함하기 위해 수정됩니다. 이 작업을 수행하기 위해 Region 매개 변수를 호출하고 뒤에 두 지역(쉼표로 구분된 두 개의 문자열 값)을 포함합니다. Redmond 및 Seattle 지역이 다이얼 플랜에 모두 정의되어 있지 않으면 이 명령은 실패합니다.
  
```PowerShell
Set-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialIn@litwareinc.com" -Regions "Redmond", "Seattle"
```

자세한 내용은 [Set-CsDialInConferencingAccessNumber를 참조하십시오.](/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps)
  
## <a name="delete-a-dial-in-conferencing-access-number"></a>전화 접속 회의 액세스 번호 삭제

비즈니스용 Skype 서버 제어판 또는 비즈니스용 Skype 서버 관리 셸을 사용하여 전화 접속 회의 액세스 번호를 삭제할 수 있습니다.
  
### <a name="delete-a-dial-in-conferencing-access-number-by-using-skype-for-business-server-control-panel"></a>비즈니스용 Skype 서버 제어판을 사용하여 전화 접속 회의 액세스 번호 삭제

1.  RTCUniversalServerAdmins 그룹의 구성원(또는 이와 동등한 사용자 권한)의 사용자 계정 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 비즈니스용 Skype 서버를 배포한 네트워크에 있는 컴퓨터에 로그온합니다.
    
2.  비즈니스용 Skype 서버 제어판을 니다.
    
3. 왼쪽 탐색 모음에서 **회의** 를 클릭한 다음 **전화 접속 액세스 번호** 를 클릭합니다.
    
4. 페이지의 목록에서 삭제할 전화 접속 번호를 클릭하고 **편집** 을 클릭한 후에 **삭제** 를 클릭합니다.
    
5. **확인** 을 클릭합니다.
    
### <a name="delete-a-dial-in-conferencing-access-number-by-using-skype-for-business-server-management-shell"></a>비즈니스용 Skype 서버 관리 셸을 사용하여 전화 접속 회의 액세스 번호 삭제

전화 접속 회의 액세스 번호를 삭제하려면 **Remove-CsDialInConferencingAccessNumber 를 사용 합니다.**
  
다음 명령은 ID가 id인 전화 접속 회의 액세스 번호를 sip:RedmondDialInAccess@litwareinc.com.
  
```PowerShell
Remove-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialInAccess@litwareinc.com"
```

다음 명령은 Northwest 지역과 연결된 모든 전화 접속 회의 액세스 번호를 삭제합니다.
  
```PowerShell
Get-CsDialInConferencingAccessNumber -Region "Northwest" | Remove-CsDialInConferencingAccessNumber
```

다음 명령은 이탈리아어가 기본 언어인 모든 전화 접속 회의 액세스 번호를 삭제합니다.
  
```PowerShell
Get-CsDialInConferencingAccessNumber | Where-Object {$_.PrimaryLanguage -eq "it-IT"} | Remove-CsDialInConferencingAccessNumber
```

자세한 내용은 [Remove-CsDialInConferencingAccessNumber를 참조하십시오.](/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps)
