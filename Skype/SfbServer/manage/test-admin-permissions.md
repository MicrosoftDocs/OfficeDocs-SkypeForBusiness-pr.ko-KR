---
title: 2016에서 관리자 권한 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 2016에서 관리자 권한을 테스트하는 비즈니스용 Skype 서버
ms.openlocfilehash: 48ffbe6863a85ecaa98cb526c16819f3d520def0
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62391120"
---
# <a name="testing-admin-permissions-in-skype-for-business-server"></a>2016에서 관리자 권한 비즈니스용 Skype 서버

|&nbsp; |&nbsp; |
|--|--|
|확인 일정|초기 배포 비즈니스용 Skype 서버 후 사용 권한 관련 문제가 발생하는 경우 필요한 경우|
|테스트 도구|Windows PowerShell|
|필요한 권한|관리 셸을 비즈니스용 Skype 서버 로컬로 실행할 경우 사용자는 RTCUniversalServerAdmins 보안 그룹의 구성원이 되어야 합니다.<br><br/>원격 응용 Windows PowerShell 사용하여 실행할 경우 사용자에게 Test-CsOUPermission cmdlet을 실행할 수 있는 권한이 있는 RBAC 역할이 할당되어야 합니다. 이 cmdlet을 사용할 수 있는 모든 RBAC 역할의 목록을 표시하기 위해 이 cmdlet 프롬프트에서 Windows PowerShell 실행합니다.<br/><br/>Get-CsAdminRole Where-Object \| {$_를 사용합니다. Cmdlet -match "Test-CsOUPermission"}|
|||

## <a name="description"></a>설명

설치 비즈니스용 Skype 서버 설치 프로그램에서 수행한 작업 중 하나는 RTCUniversalUserAdmins 그룹에 사용자, 컴퓨터, 연락처, 응용 프로그램 연락처 및 InetOrg 사용자를 관리하는 데 필요한 Active Directory 권한을 제공합니다. Active Directory에서 사용 권한 상속을 사용하지 않도록 설정한 경우 설치 프로그램이 해당 권한을 할당할 수 없습니다. 따라서 RTCUniversalUserAdmins 그룹의 구성원은 해당 엔터티를 관리할 비즈니스용 Skype 서버 없습니다. 이러한 관리 권한은 도메인 관리자만 사용할 수 있습니다. 

이 Test-CsOUPermission cmdlet은 사용자, 컴퓨터 및 기타 개체를 관리하는 데 필요한 사용 권한이 Active Directory 컨테이너에 설정되어 있는지 확인합니다. 이러한 사용 권한이 설정되지 않은 경우 [Grant-CsOUPermission cmdlet](/powershell/module/skype/Grant-CsOUPermission)을 실행하여 이 문제를 해결할 수 있습니다. 

이 Grant-CsOUPermission RTCUniversalUserAdmins 그룹의 구성원에게만 권한을 할당할 수 있습니다. 이 cmdlet을 사용하여 임의의 사용자 또는 그룹에 사용 권한을 부여할 수 없습니다. 다른 사용자 또는 그룹에 사용자 관리 권한을 부여하려면 해당 사용자 또는 그룹을 RTCUniversalUserAdmins 그룹에 추가해야 합니다. 


## <a name="running-the-test"></a>테스트 실행

관리 권한이 컨테이너에 대해 설정되어 있는지 확인하려면 Test-CsOUPermission cmdlet을 실행하고 그 다음에 컨테이너의 고유 이름과 확인할 사용 권한 유형별로 실행합니다. 예를 들어 다음 명령은 OU ou=Redmond,dc=litwareinc,dc=com에 대한 사용자 권한이 설정되어 있는지 여부를 검사합니다.

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user"`

단일 명령을 사용하여 여러 사용 권한을 확인하려면 각 사용 권한 유형을 따오기 표시로 묶은 다음  각 사용 권한 유형을  각 유형에  각 묶은 다음  각 사용 권한을  각 유형에  각 묶어 구분합니다. 예를 들어 다음 명령은 사용자, 컴퓨터 및 연락처 권한을 확인합니다.

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "computer", "contact"`

자세한 내용은 [cmdlet에 대한 도움말 Test-CsOUPermission 참조하세요](/powershell/module/skype/test-csoupermission).

## <a name="determining-success-or-failure"></a>성공 또는 실패 결정

필요한 사용 권한이 이미 설정된 경우 Test-CsOUPermission 한 단어 응답이 반환됩니다.

참

필요한 사용 권한이 설정되지 않은 경우 Test-CsOUPermission False 값을 반환합니다. 이 값을 찾으기 위해 잠시 검색해야 할 수 있습니다. 일반적으로 함께 제공되는 여러 경고 안에 포함되어 있습니다. 예제:

경고: ACE(액세스 제어 항목) atl-cs-001\RTCUniversalUserReadOnlyGroup; allow; ReadProperty; ContainerInherit; Descendents; bf967aba-0de6-11d0-00aa003049e2; d819615a-3b9b-4738-b47e-f1bd8ee3aea4 

경고: "OU=NorthAmerica,DC=atl-cs-001\DC=litwareinc,DC=com" 개체의 AC(액세스 제어 항목)가 준비되지 않습니다. 

거짓 

경고: "Test-CsOUPermission" 처리가 경고로 완료되었습니다. 이 실행 중에 "2" 경고가 기록됩니다. 

경고: 자세한 결과는 "C:\Users\Admin\AppData\Local\Temp\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html"에서 찾을 수 있습니다. 

## <a name="reasons-why-the-test-might-have-failed"></a>테스트가 실패한 이유

오류가 Test-CsOUPermission 경우 일반적으로 지정된 권한이 RTCUniversalUserAdmins 그룹에 할당되지 않은 것입니다. 이 문제를 해결하고 cmdlet을 사용하여 필요한 권한을 할당할 Grant-CsOUPermission 있습니다. 예를 들어 다음 명령은 사용자, 연락처 및 inetOrgPersons에 대한 OU 권한을 RTCUniversalUserAdmins 그룹에 제공합니다.

`Grant-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "contact", "inetOrgPerson"`

자세한 내용은 [cmdlet에 대한 도움말 Test-CsOUPermission 참조하세요](/powershell/module/skype/test-csoupermission).