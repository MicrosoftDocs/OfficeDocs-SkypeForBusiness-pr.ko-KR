---
title: 서비스 관리 비즈니스용 Skype 서버
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
description: 서비스 상태를 보고, 서비스를 시작 및 중지하고, 서비스에 대한 세션을 방지하는 방법을 배워야 합니다.
ms.openlocfilehash: 8c1f527e32d50624fddc1b4b261f6fbd20e97a47
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58604827"
---
# <a name="manage-services-in-skype-for-business-server"></a>서비스 관리 비즈니스용 Skype 서버

비즈니스용 Skype 서버 제어판을 사용하여 토폴로지에서 비즈니스용 Skype 서버 실행 중인 모든 컴퓨터의 목록을 보고, 서비스 상태를 보고, 서비스를 시작 또는 중지하고, 서비스 세션을 차단할 수 있습니다.

- [실행 중인 컴퓨터 목록 비즈니스용 Skype 서버](#view-a-list-of-computers-running-skype-for-business-server)
- [현재 컴퓨터에서 실행 중인 서비스 상태를 비즈니스용 Skype](#view-the-status-of-services-running-on-a-computer-in-skype-for-business)
- [서비스 시작 또는 비즈니스용 Skype 중지](#start-or-stop-skype-for-business-services)
- [서비스에 대한 세션 방지](#prevent-sessions-for-services)

## <a name="view-a-list-of-computers-running-skype-for-business-server"></a>실행 중인 컴퓨터 목록 비즈니스용 Skype 서버

비즈니스용 Skype 서버 제어판을 사용하여 토폴로지에서 비즈니스용 Skype 실행 중인 모든 컴퓨터의 목록을 보고 각 컴퓨터의 서비스 상태를 확인할 수 있습니다. 컴퓨터, 풀 또는 사이트에 따라 목록을 정렬할 수 있습니다. 

1. 사용자 계정에 대해 미리 정의한 관리 역할에 할당된 사용자 비즈니스용 Skype 서버 내부 배포의 컴퓨터에 로그온합니다. 자세한 내용은 에 대한 RBAC(역할 기반 액세스 [제어)를 비즈니스용 Skype 서버.](../../plan-your-deployment/security/role-based-access-control-rbac.md)
2. 브라우저 창을 열고 관리 URL을 입력하여 관리 비즈니스용 Skype 서버 열 수 있습니다. 제어판을 시작하는 데 사용할 수 있는 다양한 방법에 대한 자세한 내용은 비즈니스용 Skype 서버 도구 설치 [및 열기 를 참조합니다.](../../management-tools/install-and-open-administrative-tools.md)
3. 왼쪽 탐색 모음에서 **토폴로지** 를 클릭하고 **상태** 를 클릭합니다.
4. 상태 페이지에서 필요한 경우 다음 중 하나를 선택합니다.
    - **컴퓨터**, **풀** 또는 **사이트** 열 머리글을 클릭한 다음 위쪽 화살표나 아래쪽 화살표를 클릭하여 목록을 정렬합니다.
    - **새로 고침** 을 클릭하여 최신 목록을 확인합니다.
    - 검색 필드에 컴퓨터 이름을 입력하여 특정 컴퓨터를 검색합니다.
   
## <a name="view-the-status-of-services-running-on-a-computer-in-skype-for-business"></a>현재 컴퓨터에서 실행 중인 서비스 상태를 비즈니스용 Skype

비즈니스용 Skype 서버 제어판을 사용하여 비즈니스용 Skype 서버 토폴로지의 특정 컴퓨터에서 실행 중인 모든 서비스를 보고 각 서비스의 상태를 확인합니다.

1. CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.
2. 브라우저 창을 열고 관리 URL을 입력하여 제어판을 니다. 제어판을 시작하는 데 사용할 수 있는 다양한 방법에 대한 자세한 내용은 비즈니스용 Skype 서버 도구 설치 [및 열기 를 참조합니다.](../../management-tools/install-and-open-administrative-tools.md)
3. 왼쪽 탐색 표시줄에서 **토폴로지** 를 클릭합니다.
4. 상태 페이지에서 필요에 따라 목록을 정렬하거나 검색하여 원하는 컴퓨터를 찾은 다음 컴퓨터 이름을 클릭합니다.
5. 다음 중 하나를 합니다.
    - 컴퓨터에서 실행되는 서비스의 최신 상태를 보려면 **서비스 상태 가져오기** 를 클릭합니다.
    - 컴퓨터에서 실행되는 특정 서비스 목록 및 각 서비스의 상태를 보려면 **속성** 을 클릭합니다. 목록으로 돌아오려면 **닫기** 를 클릭합니다.

### <a name="viewing-service-status-by-using-windows-powershell-cmdlets"></a>cmdlet을 사용하여 Windows PowerShell 상태 보기

또한 서비스 상태는 Windows PowerShell cmdlet을 사용하여 Get-CsWindowsService 있습니다. 비즈니스용 Skype 서버 관리 셸 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다. 자세한 내용은 관리 [셸 비즈니스용 Skype 서버 참조하세요.](../management-shell.md)

**서비스 상태를 보려면**

컴퓨터에서 서비스 상태를 확인하려면 비즈니스용 Skype 서버 관리 셸에 다음과 같은 명령을 입력한 다음 Enter를 누를 수 있습니다.

```powershell
Get-CsWindowsService -ComputerName atl-cs-001.litwareinc.com | Select-Object RoleName, Status
```

이 명령은 다음과 비슷한 정보를 반환합니다.

```console
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

자세한 내용은 [Get-CsWindowsService를 참조합니다.](/powershell/module/skype/Get-CsWindowsService)

## <a name="start-or-stop-skype-for-business-services"></a>서비스 시작 또는 비즈니스용 Skype 중지

비즈니스용 Skype 서버 제어판을 사용하여 특정 컴퓨터에서 실행되는 모든 비즈니스용 Skype 서버 서비스를 시작 또는 중지하거나 특정 서비스를 시작 또는 중지합니다.

### <a name="start-or-stop-all-skype-for-business-server-services-on-a-computer"></a>컴퓨터에서 모든 비즈니스용 Skype 서버 서비스 시작 또는 중지

1. RTCUniversalServerAdmins 그룹의 구성원(또는 이와 동등한 사용자 권한)의 사용자 계정 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 배포한 네트워크의 컴퓨터에 비즈니스용 Skype 서버. 다음과 같은 명령을 실행하여 CsServerAdministrator 또는 CsAdministrator RBAC 역할이 할당되어 있는지 확인할 수 있습니다.

    ```powershell
    Get-CsAdminRoleAssignment -Identity "kenmyer"`
    ```

2. 브라우저 창을 열고 관리 URL을 입력하여 관리 비즈니스용 Skype 서버 열 수 있습니다. 제어판을 시작하는 데 사용할 수 있는 다양한 방법에 대한 자세한 내용은 비즈니스용 Skype 서버 도구 설치 [및 열기 를 참조합니다.](../../management-tools/install-and-open-administrative-tools.md)
3. 왼쪽 탐색 모음에서 **토폴로지** 를 클릭하고 **상태** 를 클릭합니다.
4. 상태 페이지에서 시작하거나 중지할 서비스를 실행 중인 컴퓨터를 찾기 위해 필요한 경우 목록을 정렬하거나 검색한 다음 해당 서비스를 클릭합니다.
5. **동작** 을 클릭합니다.
6. **모든 서비스 시작** 또는 **모든 서비스 중지** 를 클릭합니다.

### <a name="start-or-stop-a-specific-service"></a>특정 서비스 시작 또는 중지

1. CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.
2. 브라우저 창을 열고 관리 URL을 입력하여 제어판을 니다. 제어판을 시작하는 데 사용할 수 있는 다양한 방법에 대한 자세한 내용은 비즈니스용 Skype 서버 도구 설치 [및 열기 를 참조합니다.](../../management-tools/install-and-open-administrative-tools.md)
3. 왼쪽 탐색 모음에서 **토폴로지** 를 클릭하고 **상태** 를 클릭합니다.
4. 상태 페이지에서 시작하거나 중지할 서비스를 실행 중인 컴퓨터를 찾기 위해 필요한 경우 목록을 정렬하거나 검색한 다음 해당 서비스를 클릭합니다.
5. **속성** 을 클릭합니다.
6. 필요한 경우 서비스 목록을 정렬하고 시작 또는 중지할 서비스를 클릭합니다.
7. **동작** 을 클릭합니다.
8. **서비스 시작** 또는 **서비스 중지** 를 클릭합니다.
9. **닫기** 를 클릭합니다.


## <a name="prevent-sessions-for-services"></a>서비스에 대한 세션 방지

비즈니스용 Skype 제어판을 사용하여 특정 컴퓨터에서 실행되는 모든 비즈니스용 Skype 서버 서비스에 대한 새 세션을 방지하거나 특정 서비스에 대한 새 세션을 방지할 수 있습니다.

### <a name="prevent-new-sessions-for-all--skype-for-business-server-services-on-a-computer"></a>컴퓨터의 모든 비즈니스용 Skype 서버 세션 방지

1. RTCUniversalServerAdmins 그룹의 구성원(또는 이와 동등한 사용자 권한)의 사용자 계정 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 배포한 네트워크의 컴퓨터에 비즈니스용 Skype 서버.
2. 브라우저 창을 열고 관리 URL을 입력하여 제어판을 니다. 제어판을 시작하는 데 사용할 수 있는 다양한 방법에 대한 자세한 내용은 비즈니스용 Skype 서버 도구 설치 [및 열기 를 참조합니다.](../../management-tools/install-and-open-administrative-tools.md)
3. 왼쪽 탐색 모음에서 **토폴로지** 를 클릭하고 **상태** 를 클릭합니다.
4. 상태 페이지에서 새 세션을 금지할 서비스를 실행 중인 컴퓨터를 찾기 위해 필요한 경우 목록을 정렬하거나 검색한 다음 해당 컴퓨터를 클릭합니다.
5. **동작** 을 클릭합니다.
6. **모든 서비스에 대한 새 세션 금지** 를 클릭합니다.

### <a name="prevent-new-sessions-for-a-specific-service"></a>특정 서비스에 대한 새 세션 방지

1. RTCUniversalServerAdmins 그룹의 구성원(또는 이와 동등한 사용자 권한)의 사용자 계정 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 배포한 네트워크의 컴퓨터에 비즈니스용 Skype 서버.
2. 브라우저 창을 열고 관리 URL을 입력하여 제어판을 니다. 제어판을 시작하는 데 사용할 수 있는 다양한 방법에 대한 자세한 내용은 비즈니스용 Skype 서버 도구 설치 [및 열기 를 참조합니다.](../../management-tools/install-and-open-administrative-tools.md)
3. 왼쪽 탐색 모음에서 **토폴로지** 를 클릭하고 **상태** 를 클릭합니다.
4. **속성** 을 클릭합니다.
5. 필요한 경우 서비스 목록을 정렬하고 새 세션을 금지할 서비스를 클릭합니다.
6. **동작** 을 클릭합니다.
7. **서비스에 대한 새 세션 금지** 를 클릭합니다.
8. **닫기** 를 클릭합니다.