---
title: 비즈니스용 Skype의 응답 그룹에 대 한 배포 프로세스
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d390c8a1-dc6e-44d8-b386-2be1fca9877c
description: 비즈니스용 Skype Server Enterprise Voice의 응답 그룹에 대 한 배포 프로세스 및 단계.
ms.openlocfilehash: 12497d143f9ff5c7630f81db8f416e2f7c74d574
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233528"
---
# <a name="deployment-process-for-response-group-in-skype-for-business"></a>비즈니스용 Skype의 응답 그룹에 대 한 배포 프로세스

비즈니스용 Skype Server Enterprise Voice의 응답 그룹에 대 한 배포 프로세스 및 단계.

응답 그룹은 헬프 데스크 또는 고객 서비스 데스크와 같이 상담원 이라고 하는 사용자 그룹에 대 한 수신 전화를 라우팅하고 대기 하는 Enterprise 음성 기능입니다.

응답 그룹이 필요로 하는 구성 요소는 엔터프라이즈 음성을 구축할 때 프런트 엔드 서버 또는 Standard Edition 서버에서 자동으로 설치 및 설정 됩니다. 사용자가 응답 그룹을 사용할 수 있도록 설정 하려면 에이전트 그룹, 큐 및 워크플로를 구성 해야 합니다. 또한 응답 그룹 관리자는 기존 워크플로의 구성을 응답 그룹 관리자에 게 위임할 수 있으며, 그런 다음 워크플로 및 관련 된 에이전트 그룹 및 큐를 수정 하 고 다시 구성할 수 있습니다.

응답 그룹을 구성 하려면 다음 관리 역할 중 하나 이상의 구성원 이어야 합니다.

|**Active Directory 보안 그룹 (1)** <br/> |워크플로 만들기  <br/> |관리자 할당  <br/> |에이전트 만들기/할당/큐  <br/> |휴일 및 업무 시간 만들기/관리  <br/> |워크플로 활성화/비활성화  <br/> |워크플로 구성 (IVR 또는 헌트 그룹)  <br/> |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|**CsResponseGroupAdministrator** <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |
|**CsResponseGroupManager** <br/> ||√ (2)  <br/> |√ (3)  <br/> |√ (3)  <br/> |√ (3)  <br/> |√ (3)  <br/> |
|**CsVoiceAdministrator** <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |
|**CsServerAdministrator** <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |
|**CsAdministrator** <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |
|**Csviewadministrator** <br/> |√ (4)  <br/> |√ (4)  <br/> |√ (4)  <br/> |√ (4)  <br/> |√ (4)  <br/> |√ (4)  <br/> |

> [!NOTE]
> **(1)** Active Directory 도메인 서비스 사용자 개체가 나열 된 active directory 보안 그룹의 구성원 이어야 합니다. 보안 그룹에 사용자를 추가 하는 적절 한 사용 권한이 있는 관리자 또는 기타 위임 된 Active Directory 그룹 구성원 (예: 관리자, 계정 운영자)이 사용자에 게 나열 된 보안 그룹 또는 그룹에 사용자 개체를 추가 해야 사용할 수 있습니다. 나열 된 함수를 수행 합니다. **(2)** CsResponseGroupAdministrator가 Csresponsegroupadministrator에 할당 한 워크플로에만 해당 합니다. **(3)** 응답 그룹 관리자가 CsResponseGroupManager의 다른 구성원을 현재 관리자가 이미 관리 하는 워크플로에 할당할 수 있습니다. **(4)** csviewonly 관리자는 동사 "Get" cmdlet만 실행할 수 있습니다.

## <a name="response-group-configuration-prerequisites"></a>응답 그룹 구성 필수 조건

응답 그룹에는 다음 구성 요소가 필요 합니다.

- 응용 프로그램 서비스

- 응답 그룹 응용 프로그램

- 언어 팩

- 파일 저장소 (오디오 파일 저장)

- 웹 서비스 (응답 그룹 구성 도구 및 에이전트의 로그인 및 로그 아웃 콘솔 포함)

이러한 구성 요소는 모두 엔터프라이즈 음성을 구축할 때 기본적으로 설치 됩니다.

응답 그룹을 구성 하기 전에 다음 작업을 수행 해야 할 수 있습니다.

- Lync Server 2013 및 Enterprise Voice에 대해 사용자를 사용 하도록 설정 합니다.

- 연방 정보 처리 표준 (FIPS)을 준수 하도록 구성 파일을 수정 합니다.

- 데이터베이스 데이터 정렬을 수정 하 여 대기열 이름과 에이전트 그룹 이름에 대해 Yi, Meng 및 Zang 문자를 지원 합니다.

### <a name="enabling-users"></a>사용자 설정

응답 그룹을 구성 하는 첫 번째 단계는 에이전트 그룹을 만드는 것입니다. 에이전트 그룹을 만들려면 비즈니스용 Skype 및 Enterprise Voice에 대 한 응답 그룹의 에이전트로 사용할 사용자를 사용 하도록 설정 해야 합니다. 비즈니스용 Skype 사용자를 사용 하도록 설정 하는 것은 일반적으로 Enterprise Edition server 또는 Standard Edition server 배포의 단계입니다. 비즈니스용 Skype 사용자를 사용 하도록 설정 하는 방법에 대 한 자세한 내용은 [Lync Server 2013 Preview에 대 한 사용자 활성화 또는 비활성화](https://technet.microsoft.com/library/12497d00-f665-4a97-be68-854c5a8be4fc.aspx)를 참조 하세요. 엔터프라이즈 음성에 대 한 사용자 사용은 일반적으로 엔터프라이즈 음성 배포의 단계입니다. 자세한 내용은 [비즈니스용 Skype 서버에서 엔터프라이즈 보이스 사용자 사용](enable-users-for-enterprise-voice.md)을 참조 하세요.

### <a name="complying-with-fips-requirements"></a>FIPS 요구 사항 준수

이 섹션은 조직이 FIPS (정보 처리 표준)를 준수 해야 하는 경우에만 적용 됩니다.

FIPS를 준수 하려면 웹 서비스를 설치한 후 다른 암호화 알고리즘을 사용 하도록 응용 프로그램 수준 Web.config 파일을 수정 해야 합니다. ASP.NET에서 3DES (삼중 데이터 암호화 표준) 알고리즘을 사용 하 여 뷰 상태 데이터를 처리 하도록 지정 해야 합니다. 응답 그룹 응용 프로그램의 경우이 요구 사항은 응답 그룹 구성 도구와 에이전트 로그인 및 로그 아웃 콘솔에 적용 됩니다. 이 요구 사항에 대 한 자세한 내용은 Microsoft 기술 자료 문서 911722, "ASP.NET 1.1에서 ASP.NET 2.0으로 업그레이드 한 후 ViewState가 설정 된 ASP.NET 웹 페이지에 액세스할 때 오류 메시지가 표시 될 수 있습니다 [https://go.microsoft.com/fwlink/p/?linkId=196183](https://go.microsoft.com/fwlink/p/?linkId=196183)."를 참조 하세요.

Web.config 파일을 수정 하려면 다음을 수행 합니다.

1. 메모장과 같은 텍스트 편집기에서 응용 프로그램 수준 Web.config 파일을 엽니다.

2. Web.config 파일에서 `<system.web>` 섹션을 찾습니다.

3. `<system.web>` 섹션에 다음 `<machineKey>` 섹션을 추가 합니다.

   ```
   <machineKey validationKey="AutoGenerate,IsolateApps" decryptionKey="AutoGenerate,IsolateApps" validation="3DES" decryption="3DES"/>
   ```

4. Web.config 파일을 저장 합니다.

5. 명령 프롬프트에서 다음 명령을 실행 하 여 IIS (인터넷 정보 서비스) 서비스를 다시 시작 합니다.

   ```
   iisreset
   ```

### <a name="supporting-yi-meng-and-zang-characters"></a>Yi, Meng 및 Zang 문자 지원

이 섹션은 조직에서 Yi, Meng 또는 Zang 문자를 지원 해야 하는 경우에만 적용 됩니다.

> [!NOTE]
> Yi, Meng 및 Zang 문자에 대 한 정보와 배포에 중요할 수 있는 이유는 GB18030 문자 집합 [https://go.microsoft.com/fwlink/p/?linkId=240223](https://go.microsoft.com/fwlink/p/?linkId=240223)에 대 한 정보를 참조 하세요.

Yi, Meng 또는 Zang 문자를 지원 하려면 Rgsconfig 데이터베이스에 대 한 데이터 정렬을 수정 해야 합니다. 각 Rgsconfig 데이터베이스의 다음 테이블에서 **이름** 열의 데이터 정렬을 변경 합니다.

- dbo. AgentGroups

- dbo. BusinessHours

- dbo. HolidaySets

- dbo. 시키고

- dbo. 과정

SQL Server 2008 R2 및 SQL Server 2012의 경우 Latin_General_100 (악센트 구분) 데이터 정렬을 사용 합니다. 이 데이터 정렬을 사용 하는 경우 모든 개체 이름은 대/소문자를 구분 하지 않습니다.

Microsoft SQL Server Management Studio를 사용 하 여 데이터 정렬을 변경할 수 있습니다. 이 도구를 사용 하는 방법에 대 한 자세한 내용은 ["SQL Server Management Studio 사용"](https://go.microsoft.com/fwlink/p/?linkId=196184)을 참조 하세요. 데이터 정렬을 변경 하려면 다음 단계를 따르세요.

1. 테이블을 다시 만들어야 하는 변경 내용을 허용 하도록 SQL Server Management Studio가 구성 되어 있는지 확인 합니다. 자세한 내용은 ["저장 (허용 안 함) 대화 상자"](https://go.microsoft.com/fwlink/p/?linkId=196186)를 참조 하세요. 열 데이터 정렬을 설정 하는 방법에 대 한 자세한 내용은 ["방법: 열 데이터 정렬 설정 (Visual Database Tools)"](https://go.microsoft.com/fwlink/p/?linkId=196185)을 참조 하세요.

2. Microsoft SQL Server Management Studio를 사용 하 여 Rgsconfig 데이터베이스에 연결 합니다.

3. Rgsconfig 데이터베이스에서 변경할 테이블을 찾고 테이블을 마우스 오른쪽 단추로 클릭 한 다음 **디자인**을 클릭 합니다.

4. **이름** 열의 데이터 정렬을 변경 하 고 테이블을 저장 합니다.

## <a name="response-group-deployment-steps"></a>응답 그룹 배포 단계

**응답 그룹 배포 프로세스**

|**단계의**|**방법은**|**필요한**|**배포 설명서**|
|:-----|:-----|:-----|:-----|
|비즈니스용 Skype 및 엔터프라이즈 음성에 대해 사용자 설정  <br/> |비즈니스용 Skype 및 Enterprise Voice의 에이전트로 사용할 사용자를 사용 하도록 설정 합니다. 사용자는 에이전트 그룹에 추가 하기 전에 먼저 사용 하도록 설정 해야 합니다. 일반적으로 사용자는 Enterprise Edition 또는 Standard Edition 서버 배포 중에 비즈니스용 Skype를 사용할 수 있습니다. 엔터프라이즈 음성 배포 중에 사용자가 엔터프라이즈 음성을 사용할 수 있습니다.  <br/> |RTCUniversalUserAdmins  <br/> CsUserAdministrator  <br/> CsAdministrator  <br/> |[Lync Server 2013 Preview에 대 한 사용자 사용 또는 사용 안 함](https://technet.microsoft.com/library/12497d00-f665-4a97-be68-854c5a8be4fc.aspx) <br/> [비즈니스용 Skype 서버에서 엔터프라이즈 음성에 대 한 사용자 활성화](enable-users-for-enterprise-voice.md) <br/> |
|에이전트 그룹, 큐 및 워크플로로 구성 된 응답 그룹을 만들고 구성 합니다.  <br/> |1. 비즈니스용 Skype Server 제어판 또는 비즈니스용 Skype Server Management Shell을 사용 하 여 다음을 수행 합니다.  <br/> 에서. 에이전트 그룹을 만들고 구성 합니다.  <br/> b. 큐를 만들고 구성 합니다.  <br/> 2. 필요에 따라 비즈니스용 Skype 서버 관리 셸을 사용 하 여 미리 정의 된 응답 그룹 비즈니스 시간 및 휴일을 만들 수 있습니다.  <br/> 3. 응답 그룹 구성 도구 또는 비즈니스용 Skype Server Management Shell을 사용 하 여 사용자 지정 응답 그룹 비즈니스 시간 및 휴일을 비롯 한 워크플로 (헌트 그룹 또는 IVR (대화형 음성 응답) 통화 흐름)를 만듭니다.  <br/> 비즈니스용 Skype Server 제어판을 통해 응답 그룹 구성 도구에 액세스할 수 있습니다.  <br/> |RTCUniversalServerAdmins  <br/> CsResponseGroupAdministrator  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> CsResponseGroupManager  <br/> |[응답 그룹 에이전트 그룹 만들기](https://technet.microsoft.com/library/2a80de17-ead0-46e8-8a27-7a4e233dbde0.aspx) <br/> [응답 그룹 대기열 만들기](https://technet.microsoft.com/library/49cb86c7-2cfd-4a53-8408-d407475174ed.aspx) <br/> [) 비즈니스용 Skype에서 응답 그룹 업무 시간 정의](optional-define-response-group-business-hours.md) <br/> [) 비즈니스용 Skype에서 응답 그룹의 공휴일 집합 정의](optional-define-response-group-holiday-sets.md) <br/> [비즈니스용 Skype에서 응답 그룹 워크플로 디자인 및 만들기](designing-and-creating-response-group-workflows.md) <br/> |
|) 응용 프로그램 수준 설정 사용자 지정  <br/> |비즈니스용 Skype Server Management Shell을 사용 하 여 기본 음악 보관 구성, 기본 음악 오디오 파일, 에이전트 ringback 유예 기간, 통화 컨텍스트 구성을 사용자 지정할 수 있습니다.  <br/> |RTCUniversalServerAdmins  <br/> CsResponseGroupAdministrator  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[비즈니스용 Skype에서 응용 프로그램 수준 응답 그룹 설정 관리](managing-application-level-response-group-settings.md) <br/> |
|) 응답 그룹의 관리 위임  <br/> |응답 그룹의 구성을 위임 하도록 CsResponseGroupManager 역할을 사용자에 게 할당 합니다. 그러면 응답 그룹 관리자가 자신에 게 할당 된 응답 그룹을 구성할 수 있습니다.  <br/> |RTCUniversalServerAdmins  <br/> CsResponseGroupAdministrator  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[역할 기반 액세스 제어 계획](https://technet.microsoft.com/library/41204ba3-ce5b-41a8-a6c3-b444468fa328.aspx) <br/> |
|응답 그룹 배포 확인  <br/> |헌트 그룹과 대화형 음성 응답 워크플로에 대 한 응답 전화를 테스트 하 여 구성이 예상 대로 작동 하는지 확인 합니다.  <br/> |-  <br/> |-  <br/> |

## <a name="overview-of-workflow-creation-scenarios"></a>워크플로 작성 시나리오의 개요

워크플로를 만들 때 다음과 같은 두 가지 시나리오가 가능 합니다.

- **관리자가 워크플로를 만들고 구성** 합니다 (CsResponseGroupAdministrator 역할 구성원 (또는 해당)은 워크플로 그룹, 큐, 공휴일, 업무 시간 등 워크플로의 모든 요소를 만들고이를 활성화 합니다. 음악을 대기 중입니다.

- **관리자가 워크플로를 만들고 관리자** 가 CsResponseGroupAdministrator 역할 구성원 (또는 동등한)이 기본 SIP URI, 표시 이름을 정의 하 고 Csresponsegroupadministrator 역할의 구성원 또는 멤버를 할당 하는 옵션을 구성 합니다. 큐를 선택 하 고 워크플로를 활성화 합니다. 그런 다음 CsResponseGroupManager는 에이전트 그룹을 만들어 워크플로 구성을 기록 하 고 해당 그룹을 큐에 할당 하 고, 전화 번호, 휴일 및 업무 시간, 보류 된 음악 등을 구성할 수 있습니다.

    > [!NOTE]
    > 관리 되는 워크플로를 만들려는 경우 워크플로를 활성으로 만들어야 합니다. 관리 되는 활성 워크플로를 저장 한 후 워크플로를 수정 하 고 비활성화할 수 있습니다.


