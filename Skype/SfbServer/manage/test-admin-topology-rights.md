---
title: 비즈니스용 Skype 서버에서 관리 토폴로지 권한 테스트
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 비즈니스용 Skype 서버에서 토폴로지 권한을 테스트 하는 방법
ms.openlocfilehash: 1664a7e7d2b202b596a882e4b393cc15220806c9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817314"
---
# <a name="testing-admin-topology-rights-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 관리 토폴로지 권한 테스트

| | |
|--|--|
|확인 일정|최초 비즈니스용 Skype 서버 배포 이후. 필요한 경우 사용 권한 관련 문제가 발생 합니다.|
|테스트 도구|Windows PowerShell|
|권한이 필요 함|비즈니스용 Skype Server Management Shell을 사용 하 여 로컬에서 실행 되는 경우 사용자는 RTCUniversalServerAdmins 보안 그룹의 구성원 이어야 합니다.<br/><br/>Windows PowerShell의 원격 인스턴스를 사용 하는 경우 사용자는 테스트-CsSetupPermission cmdlet을 실행할 권한이 있는 RBAC 역할을 할당 해야 합니다. 이 cmdlet을 사용할 수 있는 모든 RBAC 역할 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.<br/><br/>Get-CsAdminRole \| 위치-개체 {$ _. Cmdlet-"테스트-CsSetupPermission"} 일치|
|||

## <a name="description"></a>설명

기본적으로 도메인 관리자만 비즈니스용 Skype 서버 토폴로지를 사용 하도록 설정 하 고 비즈니스용 Skype 서버 인프라를 크게 변경할 수 있습니다. 이 문제는 도메인 관리자와 비즈니스용 Skype 서버 관리자가 한 곳에서 동일 하 게 작동 하는 동안에는 문제가 되지 않습니다. 대부분의 조직에서 비즈니스용 Skype 서버 관리자는 전체 도메인에 대 한 관리 권한을 보유 하 고 있지 않습니다. 기본적으로이는 RTCUniversalServerAdmins 그룹의 구성원으로 정의 된 이러한 관리자가 비즈니스용 Skype 서버 토폴로지 변경 내용을 만들 수 없음을 의미 합니다. RTCUniversalServerAdmins 그룹의 구성원에 게 토폴로지 변경 권한을 부여 하려면 [부여-CsSetupPermission](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsSetupPermission) cmdlet을 사용 하 여 필요한 Active Directory 권한을 할당 해야 합니다.
 
테스트-CsSetupPermission cmdlet은 비즈니스용 Skype Server를 설치 하는 데 필요한 사용 권한이 나 해당 구성 요소 중 하나가 지정 된 Active Directory 컨테이너에 구성 되어 있는지 확인 합니다. 사용 권한이 할당 되지 않은 경우에는 허용-CsSetupPermission cmdlet을 실행 하 여 RTCUniversalServerAdmins 그룹의 구성원에 게 비즈니스용 Skype 서버를 설치 하 고 사용할 수 있는 권한을 부여 합니다.

## <a name="running-the-test"></a>테스트 실행

Active Directory 컨테이너에 대 한 설정 권한이 할당 되었는지 확인 하려면 테스트-CsSetupPermission 권한 cmdlet을 호출 합니다. 검사할 컨테이너의 고유 이름을 지정 합니다. 예를 들어이 명령은 컨테이너 ou = CsServers, dc = litwareinc, dc = com에 대 한 설정 권한을 확인 합니다.

`Test-CsSetupPermission -ComputerOU "ou=CsServers,dc=litwareinc,dc=com"`

자세한 내용은 [테스트-CsSetupPermission](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsSetupPermission) cmdlet에 대 한 도움말 항목을 참조 하세요.

## <a name="determining-success-or-failure"></a>성공 또는 실패 확인

테스트-CsSetupPermission 권한 값이 Active Directory 컨테이너에 이미 설정 되어 있는 것으로 확인 되 면 cmdlet은 True를 반환 합니다.

False 

권한이 설정 되지 않은 경우 테스트-CsSetupPermission은 False 값을 반환 합니다. 일반적으로이 값은 많은 경고 메시지에 포함 됩니다. 예를 들면 다음과 같습니다.

경고: ACE (액세스 제어 항목) atl-cs-001\RTCUniversalServerAdmins 허용 ExtendedRight; 않아야 않아야 1131f6aa-9c07-11d1-f79f-00c04fc2dcd2 

경고: "CN = Computers, DC = litwareinc, DC = com" 개체의 Ace (액세스 제어 항목)가 준비 되어 있지 않습니다. 

해제 

경고: "테스트-CsSetupPermission" 처리가 경고와 함께 완료 되었습니다. 이 실행 중에 "2" 경고가 기록 되었습니다. 

경고: 자세한 결과는 "C:\Users\Admin\AppData\Local\Temp\Test-CsSetupPermission-1da99ba6-abe2-45e4-8b16-dfd244763118.html"에서 찾을 수 있습니다. 

## <a name="reasons-why-the-test-might-have-failed"></a>테스트가 실패할 수 있는 이유

드문 경우이 아니지만 일반적으로 지정 된 Active Directory 컨테이너에 대해 설정 권한이 할당 되지 않는다는 테스트-CsSetupPermission 권한이 실패할 경우 이러한 권한은 부여-CsSetupPermission cmdlet을 사용 하 여 할당할 수 있습니다. 예를 들어이 명령은 도메인 litwareinc.com의 컴퓨터 컨테이너에 대 한 설치 권한을 부여 합니다.

`Grant-CsSetupPermission -ComputerOU "cn=Computers,dc=litwareinc,dc=com"`

자세한 내용은 [테스트-CsSetupPermission](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsSetupPermission) cmdlet에 대 한 도움말 항목을 참조 하세요.
