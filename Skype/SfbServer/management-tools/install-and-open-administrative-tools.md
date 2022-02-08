---
title: 관리 도구 설치 및 열기
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
description: 이 항목에서는 배포하고 관리하는 데 필요한 관리 도구를 설치하고 여는 방법을 비즈니스용 Skype.
ms.openlocfilehash: e3df2fd72cafbbf724baed3f86d0b62d74583348
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62384196"
---
# <a name="install-and-open-administrative-tools"></a>관리 도구 설치 및 열기

이 항목에서는 배포 및 관리에 필요한 관리 도구를 설치하는 방법을 비즈니스용 Skype 서버. 관리 도구는 기본적으로 관리 도구를 실행하는 각 서버에 비즈니스용 Skype 서버. 또한 전용 관리 콘솔과 같은 다른 컴퓨터에 관리 도구를 설치할 수도 있습니다. 만들고 있는 비즈니스용 Skype 서버 배포와 동일한 도메인 또는 포리스트에 있는 컴퓨터에 관리 도구를 설치하여 Active Directory 도메인 서비스 준비 단계가 이미 완료되어 나중에 해당 컴퓨터에서 관리 도구를 사용하여 토폴로지 게시를 할 수 있도록 하는 것이 좋습니다. 또한 관리 도구를 설치하거나 사용하기 전에 필요한 요구 사항을 비즈니스용 Skype 서버 확인합니다. [2019 또는 비즈니스용 Skype 서버 2015](../../SfBServer2019/plan/system-requirements.md)의 요구 [사항 설명서를 비즈니스용 Skype 서버 참조하세요](../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md).
 
> [!Important]
> 조직에서 IIS(인터넷 정보 서비스) 및 모든 웹 서비스를 시스템 드라이브가 없는 드라이브에 배치해야 하는 경우 설치 대화 상자에서 비즈니스용 Skype 서버 파일의 설치 위치 경로를 변경할 수 있습니다. 설치 파일을 이 경로에 설치하는 경우 OCSCore.msi 나머지 비즈니스용 Skype 서버 파일도 이 드라이브에 배포됩니다. 

## <a name="to-install-the-administrative-tools"></a>관리 도구를 설치하려면

1. 관리 도구를 설치할 컴퓨터에 로컬 관리자(최소 요구 사항)로 로그온합니다. Windows 표준 사용자로 로그온한 경우 UAC(사용자 계정 컨트롤)가 사용하도록 설정되어 있는 경우 로컬 관리자 또는 도메인에 해당하는 사용자 이름과 암호를 입력하라는 메시지가 표시됩니다.
2. 컴퓨터에서 설치 미디어를 찾은 후 \Setup\amd64\Setup.exe를 두 번 클릭합니다.
3. 배포 가능한 배포 가능한 Microsoft Visual C++ 메시지가 표시되어 있는 경우 예를 **클릭합니다**.
4. 설치 위치 페이지에서 확인을 **클릭합니다**. 다른 위치에 파일을 설치해야 하는 경우 이 경로를 다른 위치나 드라이브로 변경합니다.

    > [!Important]
    > 조직에서 IIS(인터넷 정보 서비스) 및 모든 웹 서비스를 시스템 드라이브가 없는 드라이브에 배치해야 하는 경우 설치 대화 상자에서 비즈니스용 Skype 서버 파일의 설치 위치 경로를 변경할 수 있습니다. 설치 파일을 이 경로에 설치하는 경우 OCSCore.msi 나머지 비즈니스용 Skype 서버 파일도 이 드라이브에 배포됩니다. 

5. 최종 사용자 사용권 계약 페이지에서 사용 조건을 검토하고 **동의함**, **확인** 을 차례로 클릭합니다. 계속하려면 이 단계를 수행해야 합니다.
6. 배포 마법사 페이지에서 관리자 도구 **설치를 클릭합니다**. 
7. 설치가 완료되면 **끝내기** 를 클릭합니다.

다음 절차에 따라 관리 도구를 열어 토폴로지 배포, 구성 또는 비즈니스용 Skype 서버 합니다.

- [배포 마법사](#deployment-wizard)
- [토폴로지 작성기](#topology-builder) 
- [비즈니스용 Skype 서버 제어판](#skype-for-business-server-control-panel)
- [비즈니스용 Skype 서버 관리 쉘](#skype-for-business-server-management-shell)

## <a name="deployment-wizard"></a>배포 마법사

다음 절차에 따라 배포 마법사를 로컬로 시작하여 구성 요소 파일을 추가하거나 제거합니다.

**배포 비즈니스용 Skype 서버 시작**

1. 비즈니스용 Skype 서버 배포 마법사가 설치된 컴퓨터에 Domain Admins 그룹 및 RTCUniversalServerAdmins 그룹의 구성원으로 로그온합니다.
2. **시작,** **모든 프로그램**, 비즈니스용 Skype 서버, 배포 마법사 비즈니스용 Skype 서버 **클릭합니다**.


## <a name="topology-builder"></a>토폴로지 작성기 

다음 절차에 따라 토폴로지 작성기에서 토폴로지 작성기에서 배포할 서버를 비즈니스용 Skype 서버 합니다.

**토폴로지 비즈니스용 Skype 서버 열고 토폴로지 디자인**

1. 토폴로지 작성기가 Domain Admins 그룹 및 RTCUniversalServerAdmins 그룹의 구성원으로 설치되어 있는 컴퓨터에 로그온합니다.
    > [!NOTE]
    > 로컬 Users 그룹의 구성원인 계정을 사용하여 토폴로지 정의를 정의할 수 있지만 서버에 비즈니스용 Skype 서버 설치하는 데 필요한 토폴로지의 읽기, 게시 또는 사용하려면 Domain Admins 그룹 및 RTCUniversalServerAdmins 그룹의 구성원인 계정을 사용하고 모든 권한을 가진 계정(즉,  토폴로지 작성기에서 필요한 DACL(사용자 권한 제어 목록) 또는 동등한 사용자 권한이 있는 계정을 구성할 수 있도록 보관 파일 저장소에 사용할 파일 공유에 대한 읽기, 쓰기 및 수정
 
2. 토폴로지 작성기 시작 **: 시작,** 모든 프로그램, 비즈니스용 Skype 서버, 토폴로지 작성기 비즈니스용 Skype 서버 **클릭합니다**.

## <a name="skype-for-business-server-control-panel"></a>비즈니스용 Skype 서버 제어판 

다음 절차 중 하나를 사용하여 비즈니스용 Skype 서버 제어판을 열어 환경의 서버, 사용자, 클라이언트 및 장치의 구성을 관리합니다.

> [!NOTE]
> CsAdministrator 역할에 할당된 사용자 계정을 사용하여 비즈니스용 Skype 서버 제어판에서 작업을 수행할 수 있습니다. 다른 역할을 사용하여 비즈니스용 Skype 서버 제어판에 로그온하여 수행하는 작업에 따라 특정 관리 작업을 수행할 수 있습니다. 예를 들어 CSArchivingAdministrator를 사용하여 제어판에서 보관을 비즈니스용 Skype 서버 있습니다. 역할에 대한 자세한 내용은 역할 기반 액세스 [제어 계획을 참조합니다](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-role-based-access-control). 특정 작업을 수행하기 위해 사용할 수 있는 역할에 대한 자세한 내용은 해당 작업에 대한 설명서를 참조하십시오. 

**조직의 방화벽 비즈니스용 Skype 서버 컴퓨터에서 비즈니스용 Skype 서버 제어판을 열기 위해**

1. CsAdministrator 역할 또는 수행할 작업에 대한 적절한 사용자 권한이 있는 기타 역할에 할당된 사용자 계정에서 최소 화면 해상도가 1024 x 768인 내부 배포의 컴퓨터에 로그온합니다.

    > [!IMPORTANT]
    > 관리 단순 URL(Uniform Resource Locator)을 구성한 경우 조직의 방화벽 내의 모든 컴퓨터에서 실행되는 인터넷 브라우저에서 비즈니스용 Skype 서버 제어판에 액세스할 수 있습니다. 관리 단순 URL 구성에 대한 자세한 내용은 [Planning for simple URLs](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-simple-urls) 및 [Edit or configure simple URLs을 참조하세요](/previous-versions/office/lync-server-2013/lync-server-2013-edit-or-configure-simple-urls). 

2. 브라우저 창을 열고 조직에 구성된 관리 URL을 입력합니다.

**실행 중인 컴퓨터에서 비즈니스용 Skype 서버 제어판을 열 비즈니스용 Skype 서버**

1. CsAdministrator 역할의 구성원인 사용자 계정 또는 수행할 작업에 대한 적절한 사용자 권한 및 사용 권한이 있는 기타 역할에서 설치한 컴퓨터에 로그온하거나 최소한 비즈니스용 Skype 서버 비즈니스용 Skype 서버 컴퓨터에 로그온합니다. 설정을 구성하려면 컴퓨터의 최소 화면 해상도가 1024 x 768이 되어야 합니다.
2. 제어판 비즈니스용 Skype 서버 시작 **: 시작,** 모든 **프로그램, 관리** 도구, 비즈니스용 Skype 서버, 제어 **판 비즈니스용 Skype 서버 클릭합니다**.

## <a name="skype-for-business-server-management-shell"></a>비즈니스용 Skype 서버 관리 쉘 

다음 절차에 따라 명령줄을 사용하여 비즈니스용 Skype 서버 관리 셸을 열어 환경의 서버, 사용자, 클라이언트 및 장치를 관리합니다.

> [!NOTE]
> CsAdministrator 역할에 할당된 사용자 계정을 사용하여 관리 셸에서 작업을 비즈니스용 Skype 서버 있습니다. 수행해야 하는 작업에 따라 다른 역할을 사용하여 로그온해서 특정 관리 작업을 수행할 수 있습니다. 예를 들어 CSArchivingAdministrator를 사용하여 보관 관리와 관련된 cmdlet을 실행할 수 있습니다. 역할에 대한 자세한 내용은 역할 기반 액세스 [제어 계획을 참조합니다](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-role-based-access-control). 특정 cmdlet을 실행하기 위해 사용할 수 있는 역할에 대한 자세한 내용은 해당 cmdlet에 대한 설명서를 참조하십시오.<br/><br/>또한 cmdlet에 따라 RTCUniversalServerAdmins, RTCUniversalUserAdmins 또는 RTCUniversalReadOnlyAdmins 그룹의 사용자 계정을 사용하여 특정 cmdlet을 실행할 수도 있습니다. 

**관리 비즈니스용 Skype 서버 열기**

Windows PowerShell 관리 셸이 비즈니스용 Skype 서버 창을 여는 경우 기본적으로 비즈니스용 Skype 서버 수 없습니다. 비즈니스용 Skype 서버 cmdlet을 Windows PowerShell 명령 프롬프트에 Windows PowerShell 입력합니다.

`Import-Module Lync`

관리 비즈니스용 Skype 서버 시작 **: 시작,** 모든 프로그램, 비즈니스용 Skype 서버 및 관리 **비즈니스용 Skype 서버 클릭합니다**.