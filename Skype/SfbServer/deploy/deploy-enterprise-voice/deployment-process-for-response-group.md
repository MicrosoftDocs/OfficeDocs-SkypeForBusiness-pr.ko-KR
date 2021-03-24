---
title: 비즈니스용 Skype의 응답 그룹에 대한 배포 프로세스
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d390c8a1-dc6e-44d8-b386-2be1fca9877c
description: 비즈니스용 Skype 서버 서버의 응답 그룹에 대한 배포 프로세스 및 Enterprise Voice.
ms.openlocfilehash: b1a29c4f43deb260987492e0731b740500bff87e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103504"
---
# <a name="deployment-process-for-response-group-in-skype-for-business"></a>비즈니스용 Skype의 응답 그룹에 대한 배포 프로세스

비즈니스용 Skype 서버 서버의 응답 그룹에 대한 배포 프로세스 및 Enterprise Voice.

응답 그룹은 Enterprise Voice 지원 센터 또는 고객 서비스 센터와 같은 에이전트라고 하는 사용자 그룹으로 수신 전화를 라우팅하고 큐에 대기하는 관리 기능입니다.

응답 그룹에 필요한 구성 요소는 Enterprise Voice 배포 시 프런트 엔드 서버 또는 Standard Edition Server에 자동으로 설치되어 사용하도록 설정됩니다. 사용자가 응답 그룹을 사용할 수 있도록 하려면 에이전트 그룹을 구성한 다음 큐와 워크플로를 차례로 구성합니다. 또한 응답 그룹 관리자는 기존 워크플로의 구성을 응답 그룹 관리자에게 위임할 수 있으며, 그러면 워크플로 및 관련 에이전트 그룹 및 큐를 수정하고 다시 구성할 수 있습니다.

응답 그룹을 구성하려면 다음 관리 역할 중 하나 이상의 구성원이어야 합니다.

|**Active Directory 보안 그룹(1)** <br/> |워크플로 만들기  <br/> |관리자 지정  <br/> |에이전트, 큐 만들기/지정  <br/> |휴일 및 업무 시간 만들기/관리  <br/> |워크플로 활성화/비활성화  <br/> |워크플로 구성(IVR 또는 헌트 그룹)  <br/> |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|**CsResponseGroupAdministrator** <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |
|**CsResponseGroupManager** <br/> ||√(2)  <br/> |√(3)  <br/> |√(3)  <br/> |√(3)  <br/> |√(3)  <br/> |
|**CsVoiceAdministrator** <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |
|**CsServerAdministrator** <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |
|**CsAdministrator** <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |
|**CsViewOnlyAdministrator** <br/> |√(4)  <br/> |√(4)  <br/> |√(4)  <br/> |√(4)  <br/> |√(4)  <br/> |√(4)  <br/> |

> [!NOTE]
> **(1)** Active Directory 도메인 서비스 사용자 개체는 나열된 지정된 Active Directory 보안 그룹의 구성원이 되어야 합니다. 보안 그룹에 사용자를 추가할 수 있는 적절한 권한이 있는 관리자 또는 기타 위임된 Active Directory 그룹 구성원(예: 관리자, 계정 운영자)은 사용자가 나열된 기능을 수행할 수 있도록 나열된 보안 그룹 또는 그룹에 사용자 개체를 추가해야 합니다. **(2)** CsResponseGroupAdministrator가 CsResponseGroupManager에 할당한 워크플로에만 해당합니다. **(3)** 응답 그룹 관리자는 CsResponseGroupManager의 다른 구성원을 현재 관리자가 이미 관리하는 워크플로에 할당할 수 있습니다. **(4)** CsViewOnlyAdministrator는 동사 "Get" cmdlet만 실행할 수 있습니다.

## <a name="response-group-configuration-prerequisites"></a>응답 그룹 구성 도구 필수 구성 요소

응답 그룹에는 다음 구성 요소가 필요합니다.

- 응용 프로그램 서비스

- 응답 그룹 응용 프로그램

- 언어 팩

- 파일 저장소(오디오 파일 유지용)

- 웹 서비스(응답 그룹 구성 도구 및 에이전트의 로그인 및 로그인 콘솔 포함)

이러한 구성 요소는 모두 Enterprise Voice를 배포할 때 기본적으로 설치됩니다.

응답 그룹을 구성하기 전에 다음 작업을 수행해야 할 수 있습니다.

- 사용자가 Lync Server 2013 및 Lync Server 2013을 Enterprise Voice.

- FIPS(Federal Information Processing Standards)를 준수하도록 구성 파일 수정

- 큐 이름 및 에이전트 그룹 이름에 Yi, Meng 및 Zang 문자를 지원하도록 데이터베이스 데이터 정렬 수정

### <a name="enabling-users"></a>사용자 설정

응답 그룹을 구성하는 첫 번째 단계는 에이전트 그룹을 만드는 작업입니다. 에이전트 그룹을 만들 수 있도록 설정하려면 비즈니스용 Skype 및 비즈니스용 Skype에 대한 응답 그룹에 대한 에이전트가 될 사용자를 사용하도록 설정해야 Enterprise Voice. 사용자가 비즈니스용 Skype를 사용할 수 있도록 설정하는 작업은 일반적으로 Enterprise Edition 서버 또는 Standard Edition 서버 배포의 한 단계입니다. 사용자가 비즈니스용 Skype를 사용할 수 있도록 설정하는 데 대한 자세한 내용은 [Enable or Disable Users for Lync Server 2013 Preview을 참조하세요.](/previous-versions/office/lync-server-2013/lync-server-2013-disable-or-re-enable-user-account-for-lync-server) 사용자가 Enterprise Voice를 사용할 수 있도록 설정하는 것은 일반적으로 Enterprise Voice 배포 단계에 속합니다. 자세한 내용은 [Enable users for Enterprise Voice in Skype for Business Server 을 참조하세요.](enable-users-for-enterprise-voice.md)

### <a name="complying-with-fips-requirements"></a>FIPS 요구 사항 준수

이 섹션은 조직에서 FIPS(Federal Information Processing Standards)를 준수해야 하는 경우에만 적용됩니다.

FIPS를 준수하려면 웹 서비스를 설치한 후 다른 암호화 알고리즘을 사용하도록 응용 프로그램 수준 Web.config 파일을 수정해야 합니다. ASP.NET에서 3DES(Triple Data Encryption Standard) 알고리즘을 사용하여 보기 상태 데이터를 처리하도록 지정해야 합니다. 응답 그룹 응용 프로그램의 경우 이 요구 사항은 응답 그룹 구성 도구 및 에이전트 로그인 및 로그인 콘솔에 적용됩니다. 이 요구 사항에 대한 자세한 내용은 Microsoft 기술 자료 문서 911722, "ASP.NET 1.1에서 ASP.NET 2.0으로 업그레이드한 후 ViewState가 활성화된 ASP.NET 웹 페이지 액세스 시 오류 메시지가 표시될 수 있습니다." [https://go.microsoft.com/fwlink/p/?linkId=196183](https://go.microsoft.com/fwlink/p/?linkId=196183)

Web.config 파일을 수정하려면 다음을 수행합니다.

1. 메모장과 같은 텍스트 편집에서 응용 프로그램 수준 Web.config 파일을 엽니다.

2. Web.config 파일에서 섹션을  `<system.web>` 찾습니다.

3. 섹션에  `<machineKey>` 다음 섹션을 `<system.web>` 추가합니다.

   ```xml
   <machineKey validationKey="AutoGenerate,IsolateApps" decryptionKey="AutoGenerate,IsolateApps" validation="3DES" decryption="3DES"/>
   ```

4. Web.config 파일을 저장합니다.

5. 명령 프롬프트에서 다음 명령을 실행하여 IIS(인터넷 정보 서비스) 서비스를 다시 시작합니다.

   ```console
   iisreset
   ```

### <a name="supporting-yi-meng-and-zang-characters"></a>Yi, Meng 및 Zang 문자 지원

이 섹션은 조직에서 Yi, Meng 또는 Zang 문자를 지원해야 하는 경우에만 적용됩니다.

> [!NOTE]
> Yi, Meng 및 Zang 문자가 무엇일지와 배포에 중요한 이유에 대한 자세한 내용은 GB18030 문자 집합에 대한 정보를 [https://go.microsoft.com/fwlink/p/?linkId=240223](/previous-versions/sql/sql-server-2008-r2/ms180991(v=sql.105)) 참조하세요.

Yi, Meng 또는 Zang 문자를 지원하려면 Rgsconfig 데이터베이스에 대한 데이터 정렬을 수정해야 합니다. 각 Rgsconfig 데이터베이스의 다음 테이블에서 **이름** 열의 데이터 정렬을 변경합니다.

- dbo. AgentGroups

- dbo. BusinessHours

- dbo. HolidaySets

- dbo. 큐

- dbo. 워크플로

SQL Server 2008 R2 및 SQL Server 2012의 경우 Latin_General_100(강조색 구분) 데이터 데이터를 사용 합니다. 이 데이터 정렬을 사용하는 경우 모든 개체 이름이 대/소문자를 구분하지 않습니다.

Microsoft SQL Server Management Studio를 사용하여 데이터 정렬을 변경할 수 있습니다. 이 도구를 사용하는 데 대한 자세한 내용은 ["SQL Server Management Studio"를 참조하세요.](/sql/ssms/sql-server-management-studio-ssms) 다음 단계에 따라 데이터 정렬을 변경합니다.

1. 테이블을 다시 만들어야 하는 변경 작업을 허용하도록 SQL Server Management Studio가 구성되었는지 확인합니다. 자세한 내용은 ["저장(허용되지 않은) 대화 상자"를 참조합니다.](/sql/ssms/visual-db-tools/save-not-permitted-dialog-box) 열 데이터 데이터를 설정하는 방법에 대한 자세한 내용은 ["방법: 열 데이터 집합(Visual Database Tools)"을 참조합니다.](/previous-versions/sql/sql-server-2008-r2/ms187473(v=sql.105))

2. Microsoft SQL Server Management Studio를 사용하여 Rgsconfig 데이터베이스에 연결합니다.

3. Rgsconfig 데이터베이스에서 변경할 테이블을 찾아서 마우스 오른쪽 단추로 클릭한 다음 **디자인** 을 클릭합니다.

4. **이름** 열의 데이터 정렬을 변경하고 테이블을 저장합니다.

## <a name="response-group-deployment-steps"></a>응답 그룹 배포 단계

**응답 그룹 배포 프로세스**

|**작업 단계**|**단계**|**사용 권한**|**배포 설명서**|
|:-----|:-----|:-----|:-----|
|사용자가 비즈니스용 Skype 및 비즈니스용 Skype에 대해 Enterprise Voice  <br/> |비즈니스용 Skype 및 비즈니스용 Skype 에이전트로 사용할 사용자를 Enterprise Voice. 에이전트 그룹에 사용자를 추가하려면 해당 사용자가 사용되도록 설정해야 합니다. 일반적으로 사용자는 Enterprise Edition 또는 Standard Edition 서버 배포 중에 비즈니스용 Skype를 사용할 수 있습니다. 사용자가 배포 중에 Enterprise Voice 사용하도록 Enterprise Voice 있습니다.  <br/> |RTCUniversalUserAdmins  <br/> CsUserAdministrator  <br/> CsAdministrator  <br/> |[Lync Server 2013 미리 보기에 대해 사용자 사용 또는 사용 안 하도록 설정](/previous-versions/office/lync-server-2013/lync-server-2013-disable-or-re-enable-user-account-for-lync-server) <br/> [사용자가 비즈니스용 Skype Enterprise Voice 사용할 수 있도록 설정](enable-users-for-enterprise-voice.md) <br/> |
|에이전트 그룹, 큐 및 워크플로로 구성된 응답 그룹 만들기 및 구성  <br/> |1. 비즈니스용 Skype 서버 제어판 또는 비즈니스용 Skype 서버 관리 셸을 사용하여 다음을 실행합니다.  <br/> a. 에이전트 그룹을 만들고 구성합니다.  <br/> b. 큐를 만들고 구성합니다.  <br/> 2. 선택적으로 비즈니스용 Skype 서버 관리 셸을 사용하여 미리 정의한 응답 그룹 업무 시간 및 휴일을 만들 수 있습니다.  <br/> 3. 응답 그룹 구성 도구 또는 비즈니스용 Skype 서버 관리 셸을 사용하여 사용자 지정 응답 그룹 업무 시간 및 휴일을 비롯한 워크플로(헌트 그룹 또는 IVR(대화형 음성 응답) 통화 흐름)를 만들 수 있습니다.  <br/> 비즈니스용 Skype 서버 제어판을 통해 응답 그룹 구성 도구에 액세스할 수 있습니다.  <br/> |RTCUniversalServerAdmins  <br/> CsResponseGroupAdministrator  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> CsResponseGroupManager  <br/> |[응답 그룹 에이전트 그룹 만들기](/previous-versions/office/lync-server-2013/lync-server-2013-create-response-group-agent-groups) <br/> [응답 그룹 큐 만들기](/previous-versions/office/lync-server-2013/lync-server-2013-create-response-group-queues) <br/> [(선택 사항) 비즈니스용 Skype에서 응답 그룹 업무 시간 정의](optional-define-response-group-business-hours.md) <br/> [(선택 사항) 비즈니스용 Skype에서 응답 그룹 휴일 집합 정의](optional-define-response-group-holiday-sets.md) <br/> [비즈니스용 Skype에서 응답 그룹 워크플로 디자인 및 만들기](designing-and-creating-response-group-workflows.md) <br/> |
|(선택 사항) 응용 프로그램 수준 설정 사용자 지정  <br/> |비즈니스용 Skype 서버 관리 셸을 사용하여 기본 보류 음악 구성, 기본 통화 보류 오디오 파일, 에이전트 벨백 유예 기간 및 통화 컨텍스트 구성을 사용자 지정합니다.  <br/> |RTCUniversalServerAdmins  <br/> CsResponseGroupAdministrator  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[비즈니스용 Skype에서 응용 프로그램 수준 응답 그룹 설정 관리](managing-application-level-response-group-settings.md) <br/> |
|(선택 사항) 응답 그룹의 관리 위임  <br/> |사용자에게 CsResponseGroupManager 역할을 할당하여 응답 그룹의 구성을 위임합니다. 그런 다음 응답 그룹 관리자는 할당된 응답 그룹을 구성할 수 있습니다.  <br/> |RTCUniversalServerAdmins  <br/> CsResponseGroupAdministrator  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[역할 기반 액세스 제어 계획](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-role-based-access-control) <br/> |
|응답 그룹 배포 확인  <br/> |헌트 그룹 및 대화형 음성 응답 워크플로에 대한 통화 응답을 테스트하여 구성이 예상대로 작동하는지 확인합니다.  <br/> |-  <br/> |-  <br/> |

## <a name="overview-of-workflow-creation-scenarios"></a>워크플로 만들기 시나리오 개요

워크플로를 만들 때는 다음의 두 가지 시나리오를 사용할 수 있습니다.

- **관리자가 워크플로를 만들고 구성함** - CsResponseGroupAdministrator 역할 구성원 또는 그와 동일한 사용자가 워크플로 및 워크플로의 모든 요소(예: 에이전트 그룹, 큐, 휴일, 업무 시간, 통화 대기음 등)를 만들고 활성화합니다.

- **관리자(Administrator)가 워크플로를 만들고 관리자(Manager)가 옵션을 구성함** - CsResponseGroupAdministrator 역할 구성원 또는 그와 동일한 사용자가 기본 SIP URI와 표시 이름을 정의하고, CsResponseGroupManager 역할의 구성원을 한 명 이상 할당하고, 큐를 선택하고 워크플로를 할당합니다. 그러면 CsResponseGroupManager가 로그온한 다음 에이전트 그룹을 만들어 워크플로 구성을 편집할 수 있으며, 그룹을 큐에 할당하여 전화 번호, 휴일/업무 시간, 통화 대기음 등을 구성할 수 있습니다.

    > [!NOTE]
    > 관리되는 워크플로를 만들려면 워크플로를 활성으로 만들어야 합니다. 활성 관리되는 워크플로를 저장하고 나면 워크플로를 수정하고 비활성화할 수 있습니다.