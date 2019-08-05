---
title: 비즈니스용 Skype 서버에서 관리자 권한 테스트
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 비즈니스용 Skype 서버에서 관리자 권한을 테스트 하는 방법
ms.openlocfilehash: 1bae61dd4e8d5a8636a64687d279536b4989d104
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188505"
---
# <a name="testing-admin-permissions-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 관리자 권한 테스트

| | |
|--|--|
|확인 일정|최초 비즈니스용 Skype 서버 배포 이후. 필요한 경우 사용 권한 관련 문제가 발생 합니다.|
|테스트 도구|Windows PowerShell|
|권한이 필요 함|비즈니스용 Skype Server Management Shell을 사용 하 여 로컬에서 실행 되는 경우 사용자는 RTCUniversalServerAdmins 보안 그룹의 구성원 이어야 합니다.<br><br/>Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 사용자에 게는 테스트-CsOUPermission cmdlet을 실행할 권한이 있는 RBAC 역할을 할당 해야 합니다. 이 cmdlet을 사용할 수 있는 모든 RBAC 역할 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.<br/><br/>Get-CsAdminRole \| 위치-개체 {$ _. Cmdlet-"테스트-CsOUPermission"} 일치|
|||

## <a name="description"></a>설명

비즈니스용 Skype 서버를 설치 하는 경우 설치 프로그램에서 수행 하는 작업 중 하나를 통해 사용자, 컴퓨터, 연락처, 응용 프로그램 연락처, InetOrg 관리에 필요한 Active Directory 사용 권한이 RTCUniversalUserAdmins 그룹에 제공 됩니다. 사람은. Active Directory에서 사용 권한 상속을 사용 하지 않도록 설정한 경우 설정에서 해당 사용 권한을 할당할 수 없습니다. 결과적으로 RTCUniversalUserAdmins 그룹의 구성원은 비즈니스용 Skype 서버 엔터티를 관리할 수 없습니다. 이러한 관리 권한은 도메인 관리자만 사용할 수 있습니다. 

테스트-CsOUPermission cmdlet은 사용자, 컴퓨터 및 기타 개체를 관리 하는 데 필요한 권한이 Active Directory 컨테이너에 설정 되어 있는지 확인 합니다. 이러한 권한이 설정 되어 있지 않으면 [부여-CsOUPermission cmdlet](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsOUPermission)을 실행 하 여이 문제를 해결할 수 있습니다. 

권한 부여-CsOUPermission는 RTCUniversalUserAdmins 그룹의 구성원 에게만 권한을 할당할 수 있습니다. 이 cmdlet을 사용 하 여 임의의 사용자 또는 그룹에 권한을 부여할 수는 없습니다. 다른 사용자 또는 그룹에 사용자 관리 권한을 부여 하려면 해당 사용자 (또는 그룹)를 RTCUniversalUserAdmins 그룹에 추가 해야 합니다. 


## <a name="running-the-test"></a>테스트 실행

컨테이너에 관리 권한이 설정 되어 있는지 확인 하려면 테스트-CsOUPermission cmdlet을 실행 한 다음 컨테이너의 고유 이름 및 확인 하려는 권한 유형을 기준으로 합니다. 예를 들어이 명령은 사용자 권한이 OU ou = Redmond, dc = litwareinc, dc = com에 설정 되어 있는지 여부를 확인 합니다.

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user"`

단일 명령을 사용 하 여 여러 사용 권한을 확인 하려면 각 사용 권한 형식을 따옴표로 묶어 묶은 다음 해당 형식을 쉼표를 사용 하 여 구분 합니다. 예를 들어 다음 명령은 사용자, 컴퓨터 및 연락처 사용 권한을 확인 합니다.

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "computer", "contact"`

자세한 내용은 [테스트-CsOUPermission cmdlet에 대 한 도움말 항목](https://docs.microsoft.com/en-us/powershell/module/skype/test-csoupermission)을 참조 하세요.

## <a name="determining-success-or-failure"></a>성공 또는 실패 확인

필요한 사용 권한이 이미 설정 된 경우 테스트-CsOUPermission는 한 단어씩 응답을 반환 합니다.

False

필요한 권한이 설정 되지 않은 경우 테스트-CsOUPermission는 False 값을 반환 합니다. 이 값을 찾기 위해 잠시 검색 해야 할 수 있습니다. 일반적으로이는 여러 개의 관련 된 경고 내에 포함 됩니다. 예를 들면 다음과 같습니다.

경고: ACE (액세스 제어 항목) atl-cs-001\RTCUniversalUserReadOnlyGroup 허용 ReadProperty; ContainerInherit; 파일만 bf967aba-0de6-11d0-00aa003049e2; d819615a-3b9b-4738-b47e-f1bd8ee3aea4 

경고: "OU = NorthAmerica, DC = atl-cs-001\DC = litwareinc, DC = com" 개체의 Ace (액세스 제어 항목)가 준비 되지 않았습니다. 

해제 

경고: "테스트-CsOUPermission" 처리가 경고와 함께 완료 되었습니다. 이 실행 중에 "2" 경고가 기록 되었습니다. 

경고: 자세한 결과는 "C:\Users\Admin\AppData\Local\Temp\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html"에서 찾을 수 있습니다. 

## <a name="reasons-why-the-test-might-have-failed"></a>테스트가 실패할 수 있는 이유

테스트-CsOUPermission에 실패 하는 경우 일반적으로 지정 된 사용 권한이 RTCUniversalUserAdmins 그룹에 할당 되지 않았음을 의미 합니다. 이 문제를 해결 하 고 필요한 권한을 할당할 수 있도록 허용-CsOUPermission cmdlet을 사용 합니다. 예를 들어이 명령은 사용자, 연락처 및 inetOrgPersons에 대 한 OU 권한을 RTCUniversalUserAdmins 그룹에 게 제공 합니다.

`Grant-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "contact", "inetOrgPerson"`

자세한 내용은 [테스트-CsOUPermission cmdlet에 대 한 도움말 항목](https://docs.microsoft.com/en-us/powershell/module/skype/test-csoupermission)을 참조 하세요.
