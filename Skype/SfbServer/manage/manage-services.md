---
title: 비즈니스용 Skype 용 서비스 관리 서버
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c99ee134-8294-4481-bb4e-710fe85a39ca
description: 이 문서에서는 비즈니스용 Skype 서버 토폴로지에서 실행 되는 서비스를 관리 하는 방법을 설명 합니다.
ms.openlocfilehash: 9d1a79226422da57eee36e27590769f76b89b560
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188619"
---
# <a name="manage-services-for-skype-for-business-server"></a>비즈니스용 Skype 용 서비스 관리 서버

이 문서에서는 비즈니스용 Skype 서버 토폴로지에서 실행 되는 서비스를 관리 하는 방법을 설명 합니다.
  
## <a name="view-a-list-of-computers-running-skype-for-business-server"></a>비즈니스용 Skype 서버를 실행 하는 컴퓨터 목록 보기
<a name="view_list"> </a>

비즈니스용 Skype Server 제어판을 사용 하 여 토폴로지에서 비즈니스용 Skype Server를 실행 하는 모든 컴퓨터의 목록을 확인 하 고 각각의 서비스 상태를 확인할 수 있습니다. 컴퓨터, 풀 또는 사이트를 기준으로 목록을 정렬할 수 있습니다. 
  
### <a name="to-view-a-list-of-computers-running-skype-for-business-server"></a>비즈니스용 Skype 서버를 실행 하는 컴퓨터의 목록을 보려면

1. 비즈니스용 Skype Server의 미리 정의 된 관리 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다. 비즈니스용 Skype 서버에서 사용할 수 있는 미리 정의 된 관리 역할에 대 한 자세한 내용은 **역할 기반 액세스 제어 계획**을 참조 하세요.   
2. 브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.   
3. 왼쪽 탐색 모음에서 **토폴로지** 를 클릭 한 다음 **상태**를 클릭 합니다.   
4. **상태** 페이지에서 필요에 따라 다음 중 하나를 수행 합니다.
   - **컴퓨터**, **풀**또는 **사이트** 열 머리글을 클릭 한 다음 위쪽 화살표 또는 아래쪽 화살표를 클릭 하 여 목록을 정렬 합니다. 
   - **새로 고침** 을 클릭 하 여 최신 목록을 표시 합니다.  
   - 검색 필드에 컴퓨터 이름을 입력 하 여 특정 컴퓨터를 검색 합니다.
    
## <a name="view-the-status-of-services-running-on-a-skype-for-business-server"></a>비즈니스용 Skype 서버에서 실행 중인 서비스의 상태 보기
<a name="view-status"> </a>

비즈니스용 skype Server 제어판을 사용 하 여 비즈니스용 Skype Server 토폴로지의 특정 컴퓨터에서 실행 중인 모든 서비스를 보고 각 서비스의 상태를 확인할 수 있습니다.
  
### <a name="to-view-the-status-of-services-running-on-a-computer"></a>컴퓨터에서 실행 중인 서비스의 상태를 보려면

1. CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.
2. 브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다. 
3. 왼쪽 탐색 모음에서 **토폴로지**를 클릭 합니다. 
4. **상태** 페이지에서 필요에 따라 목록을 정렬 하거나 검색 하 여 원하는 컴퓨터를 찾은 다음 컴퓨터 이름을 클릭 합니다.
5. 다음 중 하나를 수행 합니다.
   - 컴퓨터에서 실행 중인 서비스의 최신 상태를 보려면 **서비스 상태 가져오기를**클릭 합니다.
   - 컴퓨터에서 실행 되는 특정 서비스 목록과 각 서비스의 상태를 확인 하려면 **속성**을 클릭 한 다음 **닫기를** 클릭 하 여 목록으로 돌아갑니다.
    
### <a name="viewing-service-status-with-windows-powershell-cmdlets"></a>Windows Powershell cmdlet을 사용 하 여 서비스 상태 보기

Windows PowerShell 및 **Get CsWindowsService** cmdlet을 사용 하 여 서비스 상태를 볼 수도 있습니다. 이 cmdlet은 비즈니스용 Skype 서버 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다. 원격 Windows PowerShell을 사용 하 여 비즈니스용 Skype Server에 연결 하는 방법에 대 한 자세한 내용은 블로그 문서 ["빠른 시작: 원격 PowerShell을 사용 하 여 Microsoft Lync Server 2010 관리"](https://go.microsoft.com/fwlink/p/?linkId=255876)를 참조 하세요. 이 프로세스는 비즈니스용 Skype 서버에서 동일 합니다.
  
### <a name="to-view-service-status"></a>서비스 상태를 보려면

컴퓨터에서 서비스 상태를 보려면 비즈니스용 Skype 서버 관리 셸에서 다음과 유사한 명령을 입력 한 다음 enter 키를 누릅니다.
  
```
Get-CsWindowsService -ComputerName atl-cs-001.litwareinc.com | Select-Object RoleName, Status
```

이 명령은 다음과 같은 정보를 반환 합니다.
  
|**RoleName**|**상태**|
|:-----|:-----|
|W3SVC  <br/> |실행  <br/> |
|{CentralManagement}  <br/> | 실행 <br/> |
|{ClsAgent}  <br/> |실행  <br/> |
|{등록자, UserServer, EdgeServer}  <br/> |실행  <br/> |
|{ApplicationServer}  <br/> |실행  <br/> |
|{ConferencingServer}  <br/> |실행  <br/> |
|{MediationServer}  <br/> |실행  <br/> |
   
자세한 내용은 [CsWindowsService 가져오기](https://docs.microsoft.com/powershell/module/skype/get-cswindowsservice.md?view=skype-ps)를 참조 하세요.
  
## <a name="view-details-about-a-service"></a>서비스에 대 한 세부 정보 보기
<a name="view_details"> </a>

비즈니스용 Skype Server 제어판을 사용 하 여 토폴로지의 특정 컴퓨터에서 실행 중인 각 서비스에 대 한 세부 정보를 확인할 수 있습니다. 각 서비스의 상태와 관련 데이터베이스, 포트, 종속 서비스 등의 세부 정보를 볼 수 있습니다.
  
### <a name="to-view-details-for-a-service"></a>서비스에 대 한 세부 정보를 보려면

1. 비즈니스용 Skype Server의 미리 정의 된 관리 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다. 비즈니스용 Skype 서버에서 사용할 수 있는 미리 정의 된 관리 역할에 대 한 자세한 내용은 **역할 기반 액세스 제어 계획**을 참조 하세요.
2. 브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다. 
3. 왼쪽 탐색 모음에서 **토폴로지** 를 클릭 한 다음 **상태**를 클릭 합니다.
4. **상태** 페이지에서 목록을 정렬 하거나 검색 한 다음 보려는 컴퓨터를 클릭 합니다.
5. **속성**을 클릭 합니다.
6. **컴퓨터 세부 정보 보기** 창에서 필요한 경우 서비스 목록을 정렬 하 고 보려는 서비스를 클릭 합니다.
7. 필요에 따라 다음 중 하나를 수행 합니다.
   - 해당 하는 특정 서비스의 최신 상태를 보려면 **서비스 상태 가져오기를**클릭 합니다.
   - 특정 서비스에 대 한 세부 정보를 보려면 **속성** 을 클릭 한 다음 **닫기를**클릭 합니다.
   - 토폴로지의 모든 컴퓨터 목록으로 돌아가려면 **닫기를**클릭 합니다.
    
## <a name="start-or-stop-skype-for-business-server-services"></a>비즈니스용 Skype 서버 서비스 시작 또는 중지
<a name="StartStop"> </a>

비즈니스용 Skype Server 제어판을 사용 하 여 특정 컴퓨터에서 실행 되는 모든 비즈니스용 Skype Server 서비스를 시작 하거나 중지 하거나 특정 서비스를 시작 하거나 중지할 수 있습니다.
  
### <a name="to-start-or-stop-all-skype-for-business-services-on-a-computer"></a>컴퓨터에서 비즈니스용 Skype 서비스를 모두 시작 하거나 중지 하려면

1. RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 비즈니스용 Skype 서버를 배포한 네트워크의 컴퓨터에 로그온 합니다. . 다음과 같은 명령을 실행 하 여 CsServerAdministrator 또는 CsAdministrator RBAC 역할을 할당 했는지 여부를 확인할 수 있습니다.
    
   ```
   Get-CsAdminRoleAssignment -Identity "kenmyer"
   ```

2. 브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다. 
3. 왼쪽 탐색 모음에서 **토폴로지** 를 클릭 한 다음 **상태**를 클릭 합니다.
4. **상태** 페이지에서 필요에 따라 목록을 정렬 하거나 검색 하 여 시작 하거나 중지할 서비스를 실행 하는 컴퓨터를 찾은 다음 클릭 합니다.
5. **동작**을 클릭 합니다.
6. **모든 서비스 시작** 또는 **모든 서비스 중지**를 클릭 합니다.
    
### <a name="to-start-or-stop-a-specific-service"></a>특정 서비스를 시작 하거나 중지 하려면

1. CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.
2. 브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다. 
3. 왼쪽 탐색 모음에서 **토폴로지** 를 클릭 한 다음 **상태**를 클릭 합니다.
4. **상태** 페이지에서 필요에 따라 목록을 정렬 하거나 검색 하 여 시작 하거나 중지할 서비스를 실행 하는 컴퓨터를 찾은 다음 클릭 합니다.
5. **속성**을 클릭 합니다.
6. 필요한 경우 서비스 목록을 정렬 하 고 시작 하거나 중지 하려는 서비스를 클릭 합니다.
7. **동작**을 클릭 합니다.
8. **서비스 시작** 또는 **서비스 중지**를 클릭 합니다.
9. **닫기를**클릭 합니다.
    
## <a name="prevent-sessions-for-services"></a>서비스에 대 한 세션 방지
<a name="prevent_session"> </a>

비즈니스용 skype Server 제어판을 사용 하 여 특정 컴퓨터에서 실행 중인 모든 비즈니스용 Skype Server services에 대 한 새 세션을 방지 하거나 특정 비즈니스용 Skype Server 서비스에 대 한 새 세션을 방지할 수 있습니다.
  
### <a name="to-prevent-new-sessions-for-all-skype-for-business-services-on-a-computer"></a>컴퓨터의 모든 비즈니스용 Skype 서비스에 대해 새 세션을 방지 하려면

1. RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 비즈니스용 Skype 서버를 배포한 네트워크의 컴퓨터에 로그온 합니다. .
2. 브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다. 
3. 왼쪽 탐색 모음에서 **토폴로지** 를 클릭 한 다음 **상태**를 클릭 합니다.
4. **상태** 페이지에서 필요에 따라 목록을 정렬 하거나 검색 하 여 새 세션을 방지 하려는 서비스를 실행 하는 컴퓨터를 찾은 다음 클릭 합니다.
5. **동작**을 클릭 합니다.
6. **모든 서비스에 대해 새 세션 금지를**클릭 합니다.
    
### <a name="to-prevent-new-sessions-for-a-specific-service"></a>특정 서비스에 대 한 새 세션을 방지 하려면

1. RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 비즈니스용 Skype 서버를 배포한 네트워크의 컴퓨터에 로그온 합니다. .
2. 브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다. 
3. 왼쪽 탐색 모음에서 **토폴로지** 를 클릭 한 다음 **상태**를 클릭 합니다.
4. **상태** 페이지에서 필요에 따라 목록을 정렬 하거나 검색 하 여 시작 하거나 중지할 서비스를 실행 하는 컴퓨터를 찾은 다음 클릭 합니다. 
5. **속성**을 클릭 합니다.
6. 필요한 경우 서비스 목록을 정렬 하 고 새 세션을 방지 하려는 서비스를 클릭 합니다.
7. **동작**을 클릭 합니다.
8. **서비스에 대해 새 세션 금지를**클릭 합니다.
9. **닫기를**클릭 합니다.
    

