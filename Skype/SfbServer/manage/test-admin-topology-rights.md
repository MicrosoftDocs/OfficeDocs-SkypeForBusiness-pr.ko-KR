---
title: 2016에서 관리자 토폴로지 권한 비즈니스용 Skype 서버
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
description: 2016에서 토폴로지 권한을 테스트하는 비즈니스용 Skype 서버
ms.openlocfilehash: 9503476c5c97e692624a8c2535adaeabc14c0e88fc6be583927cdf048cf1ee2f
ms.sourcegitcommit: 2a76435beaac1e5daa647e93f693ea8672ec0135
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/11/2021
ms.locfileid: "57848103"
---
# <a name="testing-admin-topology-rights-in-skype-for-business-server"></a>2016에서 관리자 토폴로지 권한 비즈니스용 Skype 서버

|&nbsp; |&nbsp; |
|--|--|
|확인 일정|초기 배포 비즈니스용 Skype 서버 후 사용 권한 관련 문제가 발생하는 경우 필요한 경우|
|테스트 도구|Windows PowerShell|
|필요한 권한|관리 셸을 비즈니스용 Skype 서버 로컬로 실행할 경우 사용자는 RTCUniversalServerAdmins 보안 그룹의 구성원이 되어야 합니다.<br/><br/>원격 응용 Windows PowerShell 사용하여 실행할 경우 사용자에게 Test-CsSetupPermission cmdlet을 실행할 수 있는 권한이 있는 RBAC 역할이 할당되어야 합니다. 이 cmdlet을 사용할 수 있는 모든 RBAC 역할의 목록을 표시하기 위해 이 cmdlet 프롬프트에서 Windows PowerShell 실행합니다.<br/><br/>Get-CsAdminRole Where-Object \| {$_를 사용합니다. Cmdlet -match "Test-CsSetupPermission"}|
|||

## <a name="description"></a>설명

기본적으로 도메인 관리자만 비즈니스용 Skype 서버 토폴로지 및 비즈니스용 Skype 서버 변경할 수 있습니다. 도메인 관리자와 사용자 비즈니스용 Skype 서버 관리자가 같기만 하면 문제가되지 않습니다. 대부분의 조직에서는 비즈니스용 Skype 서버 전체 도메인에 대한 관리 권한을 보유하지 않습니다. 기본적으로 RTCUniversalServerAdmins 그룹의 구성원으로 정의된 이러한 관리자는 토폴로지 변경을 비즈니스용 Skype 서버 없습니다. RTCUniversalServerAdmins 그룹의 구성원에게 토폴로지 변경 권한을 부여하려면 [Grant-CsSetupPermission](/powershell/module/skype/Grant-CsSetupPermission) cmdlet을 사용하여 필요한 Active Directory 권한을 할당해야 합니다.
 
이 Test-CsSetupPermission cmdlet은 비즈니스용 Skype 서버 또는 해당 구성 요소 중 하나를 설치하는 데 필요한 사용 권한이 지정된 Active Directory 컨테이너에 구성되어 있는지 확인합니다. 사용 권한이 할당되지 않은 경우 Grant-CsSetupPermission cmdlet을 실행하여 RTCUniversalServerAdmins 그룹의 구성원에게 RTCUniversalServerAdmins 그룹의 구성원에게 RTCUniversalServerAdmins를 설치하고 사용하도록 설정할 수 있는 권한을 비즈니스용 Skype 서버.

## <a name="running-the-test"></a>테스트 실행

Active Directory 컨테이너에 대한 설치 권한이 할당되어 있는지 확인하려면 active Directory cmdlet을 Test-CsSetupPermission 호출합니다. 확인할 컨테이너의 고유 이름을 지정합니다. 예를 들어 다음 명령은 컨테이너 ou=CsServers,dc=litwareinc,dc=com에 대한 설치 권한을 검증합니다.

`Test-CsSetupPermission -ComputerOU "ou=CsServers,dc=litwareinc,dc=com"`

자세한 내용은 [Test-CsSetupPermission](/powershell/module/skype/Test-CsSetupPermission) cmdlet에 대한 도움말 항목을 참조하십시오.

## <a name="determining-success-or-failure"></a>성공 또는 실패 결정

이 Test-CsSetupPermission Active Directory 컨테이너에 대해 필요한 사용 권한이 이미 설정되어 있는지 확인하면 cmdlet은 True 값을 반환합니다.

참 

사용 권한이 설정되지 않은 경우 Test-CsSetupPermission 값을 반환합니다. 이 값은 일반적으로 많은 경고 메시지로 묶입니다. 예를 들어:

경고: ACE(액세스 제어 항목) atl-cs-001\RTCUniversalServerAdmins; 허용; ExtendedRight; 없음; 없음; 1131f6aa-9c07-11d1-f79f-00c04fc2dcd2 

경고: "CN=Computers,DC=litwareinc,DC=com" 개체의 AC(액세스 제어 항목)가 준비되지 않습니다. 

거짓 

경고: "Test-CsSetupPermission" 처리가 경고로 완료되었습니다. 이 실행 중에 "2" 경고가 기록됩니다. 

경고: 자세한 결과는 "C:\Users\Admin\AppData\Local\Temp\Test-CsSetupPermission-1da99ba6-abe2-45e4-8b16-dfd244763118.html"에서 찾을 수 있습니다. 

## <a name="reasons-why-the-test-might-have-failed"></a>테스트가 실패한 이유

예외는 거의 없습니다. 그러나 예외가 Test-CsSetupPermission 일반적으로 지정된 Active Directory 컨테이너에 대해 설치 권한이 할당되지 않는다는 의미입니다. 이러한 사용 권한은 cmdlet을 사용하여 할당할 Grant-CsSetupPermission 있습니다. 예를 들어 다음 명령은 다음 도메인의 Computers 컨테이너에 설치 권한을 litwareinc.com.

`Grant-CsSetupPermission -ComputerOU "cn=Computers,dc=litwareinc,dc=com"`

자세한 내용은 [Test-CsSetupPermission](/powershell/module/skype/Test-CsSetupPermission) cmdlet에 대한 도움말 항목을 참조하십시오.