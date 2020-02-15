---
title: 관리 도구 설치 및 열기
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
description: 이 항목에서는 비즈니스용 Skype를 배포 하 고 관리 하는 데 필요한 관리 도구를 설치 하 고 여는 방법에 대해 설명 합니다.
ms.openlocfilehash: b2d06d14263174229d35ff2e5108574296bb5034
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42031072"
---
# <a name="install-and-open-administrative-tools"></a>관리 도구 설치 및 열기

이 항목에서는 비즈니스용 Skype 서버를 배포 하 고 관리 하는 데 필요한 관리 도구를 설치 하는 방법에 대해 설명 합니다. 관리 도구는 비즈니스용 Skype 서버를 실행 하는 각 서버에 기본적으로 설치 됩니다. 또한 전용 관리 콘솔과 같은 다른 컴퓨터에 관리 도구를 설치할 수도 있습니다. Active Directory 도메인 서비스 준비 단계가 이미 완료 되었는지 확인 하기 위해 만드는 비즈니스용 Skype 서버 배포와 동일한 도메인 또는 포리스트에 있는 컴퓨터에 관리 도구를 설치 하는 것이 좋습니다. 이를 통해 나중에 해당 컴퓨터의 관리 도구를 사용 하 여 토폴로지를 게시할 수 있습니다. 또한 비즈니스용 Skype 서버 관리 도구를 설치 하거나 사용 하기 전에 필요한 요구 사항을 검토 해야 합니다. [비즈니스용 Skype 서버 2019](../../SfBServer2019/plan/system-requirements.md) 또는 [비즈니스용 skype 서버 2015](../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md)의 요구 사항 설명서를 참조 하세요.
 
> [!Important]
> 조직에서 IIS (인터넷 정보 서비스) 및 모든 웹 서비스를 시스템 드라이브 이외의 드라이브에 배치 해야 하는 경우 설치 대화 상자에서 비즈니스용 Skype 서버 파일용 설치 위치 경로를 변경할 수 있습니다. OCSCore를 포함 하 여이 경로에 설치 파일을 설치 하는 경우 비즈니스용 Skype 서버 파일의 나머지도이 드라이브에 배포 됩니다. 

## <a name="to-install-the-administrative-tools"></a>관리 도구를 설치 하려면

1. 관리 도구를 설치할 컴퓨터에 로컬 관리자(최소 요구 사항)로 로그온합니다. Windows에서 표준 사용자로 로그온 하 고 UAC (사용자 계정 컨트롤)를 사용 하는 경우 로컬 관리자 또는 도메인에 해당 하는 사용자 이름 및 암호를 입력 하 라는 메시지가 표시 됩니다.
2. 컴퓨터에서 설치 미디어를 찾은 후 \Setup\amd64\Setup.exe를 두 번 클릭합니다.
3. Microsoft Visual c # 배포 가능를 설치할지 묻는 메시지가 표시 되 면 **예**를 클릭 합니다.
4. 설치 위치 페이지에서 **확인**을 클릭 합니다. 다른 위치에 파일을 설치해야 하는 경우 이 경로를 다른 위치나 드라이브로 변경합니다.

    > [!Important]
    > 조직에서 IIS (인터넷 정보 서비스) 및 모든 웹 서비스를 시스템 드라이브 이외의 드라이브에 배치 해야 하는 경우 설치 대화 상자에서 비즈니스용 Skype 서버 파일용 설치 위치 경로를 변경할 수 있습니다. OCSCore를 포함 하 여이 경로에 설치 파일을 설치 하는 경우 비즈니스용 Skype 서버 파일의 나머지 부분도이 드라이브에 배포 됩니다. 

5. 최종 사용자 사용권 계약 페이지에서 사용 조건을 검토하고 **동의함**, **확인**을 차례로 클릭합니다. 계속하려면 이 단계를 수행해야 합니다.
6. 배포 마법사 페이지에서 **관리자 도구 설치**를 클릭 합니다. 
7. 설치가 완료되면 **끝내기**를 클릭합니다.

다음 절차에 따라 관리 도구를 열어 비즈니스용 Skype 서버 토폴로지를 배포, 구성 또는 문제를 해결 합니다.

- [배포 마법사](#deployment-wizard)
- [토폴로지 작성기](#topology-builder) 
- [비즈니스용 Skype 서버 제어판](#skype-for-business-server-control-panel)
- [비즈니스용 Skype 서버 관리 쉘](#skype-for-business-server-management-shell)

## <a name="deployment-wizard"></a>배포 마법사

다음 절차에 따라 배포 마법사를 사용 하 여 구성 요소 파일을 추가 하거나 제거 합니다.

**비즈니스용 Skype 서버 배포 마법사를 시작 하려면**

1. 비즈니스용 Skype 서버 배포 마법사가 Domain Admins 그룹 및 RTCUniversalServerAdmins 그룹의 구성원으로 설치 된 컴퓨터에 로그온 합니다.
2. **시작**, **모든 프로그램**, **skype for business server**를 차례로 클릭 한 다음 **비즈니스용 skype 서버 배포 마법사**를 클릭 합니다.


## <a name="topology-builder"></a>토폴로지 작성기 

다음 절차에 따라 비즈니스용 Skype 서버 토폴로지에 배포할 서버를 정의 하는 토폴로지 작성기를 엽니다.

**비즈니스용 Skype 서버 토폴로지 작성기를 열어 토폴로지를 디자인 하려면**

1. 토폴로지 작성기가 Domain Admins 그룹 및 RTCUniversalServerAdmins 그룹의 구성원으로 설치되어 있는 컴퓨터에 로그온합니다.
    > [!NOTE]
    > 로컬 Users 그룹의 구성원 인 계정을 사용 하 여 토폴로지를 정의할 수 있지만 서버에 비즈니스용 Skype 서버를 설치 하는 데 필요한 토폴로지를 읽거나 게시 하거나 사용 하도록 설정 하려면 Domain Admins 그룹의 구성원 인 계정을 사용 해야 합니다. RTCUniversalServerAdmins 그룹에서 토폴로지 작성기가 필요한 임의 액세스 제어 목록을 구성할 수 있도록 보관 파일 저장소에 사용할 파일 공유에 대 한 모든 권한 (읽기, 쓰기 및 수정)을 포함 합니다. Dacl) 또는이에 해당 하는 사용자 권한이 있는 계정
 
2. 토폴로지 작성기 시작: **시작**, **모든 프로그램**, **skype for business server**를 차례로 클릭 한 다음 **비즈니스용 skype 서버 토폴로지 작성기**를 클릭 합니다.

## <a name="skype-for-business-server-control-panel"></a>비즈니스용 Skype 서버 제어판 

다음 절차 중 하나를 사용 하 여 비즈니스용 Skype 서버 제어판을 열고 해당 환경의 서버, 사용자, 클라이언트 및 장치에 대 한 구성을 관리 합니다.

> [!NOTE]
> CsAdministrator 역할에 할당 된 사용자 계정을 사용 하 여 비즈니스용 Skype 서버 제어판에서 모든 작업을 수행할 수 있습니다. 다른 역할을 사용 하 여 비즈니스용 Skype 서버 제어판에 로그온 하 여 수행 해야 하는 작업에 따라 특정 관리 작업을 수행할 수 있습니다. 예를 들어 비즈니스용 Skype 서버 제어판에서 CSArchivingAdministrator을 사용 하 여 보관을 관리할 수 있습니다. 역할에 대 한 자세한 내용은 [역할 기반 액세스 제어 계획](https://technet.microsoft.com/library/gg425917(v=ocs.15).aspx)을 참조 하십시오. 특정 작업을 수행하기 위해 사용할 수 있는 역할에 대한 자세한 내용은 해당 작업에 대한 설명서를 참조하십시오. 

**조직의 방화벽 내부에 있는 컴퓨터에서 비즈니스용 Skype 서버 제어판을 열려면**

1. CsAdministrator 역할 또는 수행할 작업에 적절 한 사용자 권한 및 사용 권한이 있는 다른 역할에 할당 된 사용자 계정에서 최소 화면 해상도 1024 x 768을 사용 하 여 내부 배포의 컴퓨터에 로그온 합니다.

    > [!IMPORTANT]
    > 관리 단순 URL (uniform resource locator)을 구성한 경우 조직의 방화벽 내 모든 컴퓨터에서 실행 되는 인터넷 브라우저에서 비즈니스용 Skype 서버 제어판에 액세스할 수 있습니다. 관리 단순 URL을 구성 하는 방법에 대 한 자세한 내용은 [단순 Url 계획](https://technet.microsoft.com/library/gg398287(v=ocs.15).aspx) 및 [단순 url 편집 또는 구성](https://technet.microsoft.com/library/gg398063(v=ocs.15).aspx)를 참조 하세요. 

2. 브라우저 창을 열고 조직에 구성된 관리 URL을 입력합니다.

**비즈니스용 Skype 서버를 실행 하는 컴퓨터에서 비즈니스용 Skype 서버 제어판을 열려면**

1. CsAdministrator 역할 또는 수행할 작업에 적절 한 사용자 권한 및 사용 권한이 있는 다른 역할의 구성원 인 사용자 계정에서 비즈니스용 Skype 서버를 설치 하는 컴퓨터에 로그온 하거나 최소 비즈니스용 Skype 서버 관리 도구 설정을 구성 하려면 컴퓨터의 화면 해상도가 최소 1024 x 768 이어야 합니다.
2. 비즈니스용 Skype 서버 제어판 **시작을 클릭 하 고** **모든 프로그램**, **관리 도구**, **비즈니스용 Skype 서버**를 차례로 가리킨 다음 비즈니스용 **skype 서버 제어판**을 클릭 합니다.

## <a name="skype-for-business-server-management-shell"></a>비즈니스용 Skype 서버 관리 쉘 

다음 절차에 따라 명령줄을 사용 하 여 사용자 환경의 서버, 사용자, 클라이언트 및 장치를 관리 하기 위해 비즈니스용 Skype 서버 관리 셸을 엽니다.

> [!NOTE]
> CsAdministrator 역할에 할당 된 사용자 계정을 사용 하 여 비즈니스용 Skype 서버 관리 셸에서 모든 작업을 수행할 수 있습니다. 수행해야 하는 작업에 따라 다른 역할을 사용하여 로그온해서 특정 관리 작업을 수행할 수 있습니다. 예를 들어 CSArchivingAdministrator를 사용하여 보관 관리와 관련된 cmdlet을 실행할 수 있습니다. 역할에 대 한 자세한 내용은 [역할 기반 액세스 제어 계획](https://technet.microsoft.com/library/gg425917(v=ocs.15).aspx)을 참조 하십시오. 특정 cmdlet을 실행하기 위해 사용할 수 있는 역할에 대한 자세한 내용은 해당 cmdlet에 대한 설명서를 참조하십시오.<br/><br/>또한 cmdlet에 따라 RTCUniversalServerAdmins, RTCUniversalUserAdmins 또는 RTCUniversalReadOnlyAdmins 그룹의 사용자 계정을 사용하여 특정 cmdlet을 실행할 수도 있습니다. 

**비즈니스용 Skype 서버 관리 셸을 열려면**

비즈니스용 Skype 서버 관리 셸이 아닌 Windows PowerShell 창을 여는 경우 기본적으로 비즈니스용 Skype 서버 cmdlet을 실행할 수 없습니다. Windows PowerShell 내에서 비즈니스용 Skype 서버 cmdlet을 실행 하려면 Windows PowerShell 명령 프롬프트에 다음을 입력 합니다.

`Import-Module Lync`

비즈니스용 Skype 서버 관리 셸 시작: **시작**, **모든 프로그램**, **skype for business server**를 차례로 클릭 한 다음 **비즈니스용 skype 서버 관리 셸을**클릭 합니다.
