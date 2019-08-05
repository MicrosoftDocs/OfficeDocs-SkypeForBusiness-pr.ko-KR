---
title: 비즈니스용 Skype 서버에서 서비스 관리
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 서비스 상태를 확인 하 고 서비스를 시작 및 중지 하 고 서비스에 대 한 세션을 방지 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: c3c0ad3a61543caf7866582413a67968c4c1c2d6
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187101"
---
# <a name="manage-services-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 서비스 관리

비즈니스용 Skype Server 제어판을 사용 하 여 토폴로지에서 비즈니스용 Skype Server를 실행 하는 모든 컴퓨터의 목록을 볼 수 있으며, 서비스의 상태를 확인 하 고, 서비스를 시작 하거나 중지 하 고, 서비스에 대 한 세션을 방지 합니다.

- [비즈니스용 Skype 서버를 실행 하는 컴퓨터 목록 보기](#view-a-list-of-computers-running-skype-for-business-server)
- [비즈니스용 Skype에서 컴퓨터에 실행 중인 서비스의 상태 보기](#view-the-status-of-services-running-on-a-computer-in-skype-for-business)
- [비즈니스용 Skype 서비스 시작 또는 중지](#start-or-stop-skype-for-business-services)
- [서비스에 대 한 세션 방지](#prevent-sessions-for-services)

## <a name="view-a-list-of-computers-running-skype-for-business-server"></a>비즈니스용 Skype 서버를 실행 하는 컴퓨터 목록 보기

비즈니스용 skype Server 제어판을 사용 하 여 토폴로지에서 비즈니스용 Skype를 실행 하는 모든 컴퓨터 목록을 확인 하 고 각각의 서비스 상태를 확인 합니다. 컴퓨터, 풀 또는 사이트를 기준으로 목록을 정렬할 수 있습니다. 

1. 비즈니스용 Skype Server의 미리 정의 된 관리 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다. 자세한 내용은 [비즈니스용 Skype 서버용 RBAC (역할 기반 액세스 제어](../../plan-your-deployment/security/role-based-access-control-rbac.md))를 참조 하세요.
2. 브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다. 비즈니스용 Skype Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [관리 도구 설치 및 열기](../../management-tools/install-and-open-administrative-tools.md)를 참조 하세요.
3. 왼쪽 탐색 모음에서 **토폴로지**를 클릭 한 다음 **상태**를 클릭 합니다.
4. 상태 페이지에서 필요에 따라 다음 중 하나를 수행 합니다.
    - **컴퓨터**, **풀**또는 **사이트** 열 머리글을 클릭 한 다음 위쪽 화살표 또는 아래쪽 화살표를 클릭 하 여 목록을 정렬 합니다.
    - **새로 고침** 을 클릭 하 여 최신 목록을 표시 합니다.
    - 검색 필드에 컴퓨터 이름을 입력 하 여 특정 컴퓨터를 검색 합니다.
   
## <a name="view-the-status-of-services-running-on-a-computer-in-skype-for-business"></a>비즈니스용 Skype에서 컴퓨터에 실행 중인 서비스의 상태 보기

비즈니스용 Skype Server 제어판을 사용 하 여 비즈니스용 Skype Server 토폴로지의 특정 컴퓨터에서 실행 중인 모든 서비스를 보고 각 서비스의 상태를 확인 합니다.

1. CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.
2. 브라우저 창을 열고 관리자 URL을 입력 하 여 제어판을 엽니다. 비즈니스용 Skype Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [관리 도구 설치 및 열기](../../management-tools/install-and-open-administrative-tools.md)를 참조 하세요.
3. 왼쪽 탐색 모음에서 **토폴로지**를 클릭 합니다.
4. 상태 페이지에서 필요에 따라 목록을 정렬 하거나 검색 하 여 원하는 컴퓨터를 찾은 다음 컴퓨터 이름을 클릭 합니다.
5. 다음 중 하나를 수행 합니다.
    - 컴퓨터에서 실행 중인 서비스의 최신 상태를 보려면 **서비스 상태 가져오기를**클릭 합니다.
    - 컴퓨터에서 실행 되는 특정 서비스 목록과 각 서비스의 상태를 확인 하려면 **속성**을 클릭 한 다음 **닫기를** 클릭 하 여 목록으로 돌아갑니다.

### <a name="viewing-service-status-by-using-windows-powershell-cmdlets"></a>Windows PowerShell Cmdlet을 사용 하 여 서비스 상태 보기

Windows PowerShell 및 Get CsWindowsService cmdlet을 사용 하 여 서비스 상태를 볼 수도 있습니다. 이 cmdlet은 비즈니스용 Skype 서버 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다. 자세한 내용은 [비즈니스용 Skype 서버 관리 셸을](../management-shell.md)참조 하세요.

**서비스 상태를 보려면**

컴퓨터에서 서비스 상태를 보려면 비즈니스용 Skype 서버 관리 셸에 다음과 유사한 명령을 입력 한 다음 enter 키를 누릅니다.

`Get-CsWindowsService -ComputerName atl-cs-001.litwareinc.com | Select-Object RoleName, Status`

이 명령은 다음과 같은 정보를 반환 합니다.

```
RoleName                                  Status
--------                                  ------
{W3SVC}                                   Running
{CentralManagement}                       Running
{ClsAgent}                                Running
{Registrar, UserServer, EdgeServer}       Running
{ApplicationServer}                       Running
{ConferencingServer}                      Running
{MediationServer}                         Running
```

자세한 내용은 [CsWindowsService 가져오기](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsWindowsService)를 참조 하세요.

## <a name="start-or-stop-skype-for-business-services"></a>비즈니스용 Skype 서비스 시작 또는 중지

비즈니스용 Skype Server 제어판을 사용 하 여 특정 컴퓨터에서 실행 되는 모든 비즈니스용 Skype Server 서비스를 시작 하거나 중지 하거나 특정 서비스를 시작 하거나 중지할 수 있습니다.

### <a name="start-or-stop-all-skype-for-business-server-services-on-a-computer"></a>컴퓨터에서 모든 비즈니스용 Skype 서버 서비스 시작 또는 중지

1. RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 비즈니스용 Skype 서버를 배포한 네트워크의 컴퓨터에 로그온 합니다. . 다음과 같은 명령을 실행 하 여 CsServerAdministrator 또는 CsAdministrator RBAC 역할을 할당 했는지 여부를 확인할 수 있습니다.

    `Get-CsAdminRoleAssignment -Identity "kenmyer"`

2. 브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다. 비즈니스용 Skype Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [관리 도구 설치 및 열기](../../management-tools/install-and-open-administrative-tools.md)를 참조 하세요.
3. 왼쪽 탐색 모음에서 **토폴로지**를 클릭 한 다음 **상태**를 클릭 합니다.
4. 상태 페이지에서 필요에 따라 목록을 정렬 하거나 검색 하 여 시작 하거나 중지할 서비스를 실행 하는 컴퓨터를 찾은 다음 클릭 합니다.
5. **동작**을 클릭 합니다.
6. **모든 서비스 시작** 또는 **모든 서비스 중지**를 클릭 합니다.

### <a name="start-or-stop-a-specific-service"></a>특정 서비스 시작 또는 중지

1. CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.
2. 브라우저 창을 열고 관리자 URL을 입력 하 여 제어판을 엽니다. 비즈니스용 Skype Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [관리 도구 설치 및 열기](../../management-tools/install-and-open-administrative-tools.md)를 참조 하세요.
3. 왼쪽 탐색 모음에서 **토폴로지**를 클릭 한 다음 **상태**를 클릭 합니다.
4. 상태 페이지에서 필요에 따라 목록을 정렬 하거나 검색 하 여 시작 하거나 중지할 서비스를 실행 하는 컴퓨터를 찾은 다음 클릭 합니다.
5. **속성**을 클릭 합니다.
6. 필요한 경우 서비스 목록을 정렬 하 고 시작 하거나 중지 하려는 서비스를 클릭 합니다.
7. **동작**을 클릭 합니다.
8. **서비스 시작** 또는 **서비스 중지**를 클릭 합니다.
9. **닫기를**클릭 합니다.


## <a name="prevent-sessions-for-services"></a>서비스에 대 한 세션 방지

비즈니스용 Skype 제어판을 사용 하 여 특정 컴퓨터에서 실행 되는 모든 비즈니스용 Skype Server services에 대 한 새 세션을 방지 하거나 특정 서비스에 대 한 새 세션을 방지 합니다.

### <a name="prevent-new-sessions-for-all--skype-for-business-server-services-on-a-computer"></a>컴퓨터에 있는 모든 비즈니스용 Skype Server 서비스에 대해 새 세션 방지

1. RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 비즈니스용 Skype 서버를 배포한 네트워크의 컴퓨터에 로그온 합니다. .
2. 브라우저 창을 열고 관리자 URL을 입력 하 여 제어판을 엽니다. 비즈니스용 Skype Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [관리 도구 설치 및 열기](../../management-tools/install-and-open-administrative-tools.md)를 참조 하세요.
3. 왼쪽 탐색 모음에서 **토폴로지** 를 클릭 한 다음 **상태**를 클릭 합니다.
4. 상태 페이지에서 필요에 따라 목록을 정렬 하거나 검색 하 여 새 세션을 방지 하려는 서비스를 실행 하는 컴퓨터를 찾은 다음 클릭 합니다.
5. **동작**을 클릭 합니다.
6. **모든 서비스에 대해 새 세션 금지를**클릭 합니다.

### <a name="prevent-new-sessions-for-a-specific-service"></a>특정 서비스에 대해 새 세션 방지

1. RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 비즈니스용 Skype 서버를 배포한 네트워크의 컴퓨터에 로그온 합니다. .
2. 브라우저 창을 열고 관리자 URL을 입력 하 여 제어판을 엽니다. 비즈니스용 Skype Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [관리 도구 설치 및 열기](../../management-tools/install-and-open-administrative-tools.md)를 참조 하세요.
3. 왼쪽 탐색 모음에서 **토폴로지**를 클릭 한 다음 **상태**를 클릭 합니다.
4. **속성**을 클릭 합니다.
5. 필요한 경우 서비스 목록을 정렬 하 고 새 세션을 방지 하려는 서비스를 클릭 합니다.
6. **동작**을 클릭 합니다.
7. **서비스에 대해 새 세션 금지를**클릭 합니다.
8. **닫기를**클릭 합니다.
