---
title: Exchange 통합 메시징 온라인 마이그레이션 지원
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: waseemh, dstrome, balinger
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Microsoft는 2020년 2월 28일까지 Exchange ExchUMO(Unified Messaging Online) 서비스를 사용 중지합니다. 이 문서에서는 영향을 받는 고객이 비즈니스 연속성을 위해 알고 계획해야 하는 작업을 요약합니다.
ms.openlocfilehash: d9e041516f06b5ce5ddf4e411b261bf99a9703f9
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65676370"
---
# <a name="exchange-unified-messaging-online-migration-support"></a>Exchange 통합 메시징 온라인 마이그레이션 지원

> [!IMPORTANT]
> **Exchange Online 통합 메시징 서비스는 태평양 표준시인 2020년 2월 28일 오후 5시 현재 지원되지 않습니다. 모든 음성 메일 계정은 Microsoft에서 클라우드 음성 사서함 서비스로 마이그레이션되었습니다. 나머지 자동 전화 교환 트래픽은 모니터링되지 않으며 언제든지 중단될 수 있습니다.**

2019년 2월 8일 [발표](https://blogs.technet.microsoft.com/exchange/2019/02/08/retiring-unified-messaging-in-exchange-online/)와 관련하여 Microsoft는 2020년 2월 28일까지 Exchange ExchUMO(Unified Messaging Online) 서비스를 사용 중지합니다. 이 문서에서는 영향을 받는 고객이 비즈니스 연속성을 위해 알고 계획해야 하는 작업에 대한 요약을 제공합니다.

ExchUMO는 고객이 음성 메일, 자동 전화 교환, 통화 큐 및 팩스 통합 서비스를 위해 배포합니다. Microsoft는 고객이 이미 비즈니스용 Skype Online 및 Microsoft Teams 수천 명의 고객을 지원하는 전화 시스템 서비스로 마이그레이션할 수 있도록 지원할 계획입니다.

음성 메일은 주로 Microsoft 기반 마이그레이션입니다. 관리자 참여 및/또는 투자는 고객의 하위 집합에 필요할 수 있습니다. 자동 전화 교환은 관리자 기반 마이그레이션입니다. 클라우드 자동 전화 교환 클라우드 서비스에서 기존 ExchUMO 자동 전화 교환 트리를 다시 만들어야 합니다. 타사 PBX에서 ExchUMO 기능을 사용하는 고객은 타사 PBX 시스템을 지원하지 않으므로 Skype 클라우드 서비스로 마이그레이션되지 않습니다. 타사 지원에 대한 사용 중지 계획이 [이 블로그](https://techcommunity.microsoft.com/t5/Exchange-Team-Blog/New-date-for-discontinuation-of-support-for-Session-Border/ba-p/607853)에 발표되었으며, 이 배포 모델의 고객은 사용자를 Microsoft의 통합 통신 플랫폼/서비스 중 하나로 마이그레이션하거나 이러한 사용자를 위한 타사 음성 메일 및/또는 자동 전화 교환 솔루션을 획득할 수 있습니다. 팩스 통합은 클라우드 기반 서비스에서 지원되지 않습니다. 고객은 타사 솔루션으로 마이그레이션해야 합니다.

## <a name="who-is-affected"></a>Who 영향을 받습니까?

Exchange Unified Messaging Online 서비스에서 다음 기능을 사용하는 고객은 영향을 받습니다.

- 음성 메일 서비스
- 자동 전화 교환 서비스
- 통화 큐 서비스
- 팩스 통합

> [!Note]
> 통합 메시징에서 온-프레미스 Exchange Server 사용하는 고객은 영향을 받지 않습니다.

사용자 환경 영향의 사용자 및 관리자 환경에 미치는 영향에 대해 자세히 알아봅니 [다](#user-experience-impact).

## <a name="migration-plan-overview"></a>마이그레이션 계획 개요

Microsoft는 ExchUMO의 기능을 사용하는 다양한 고객 배포를 확인했으며 다음 계획에 따라 고객이 마이그레이션할 수 있도록 지원합니다.

|고객 그룹 |시간 표시 막대  |세부 정보  |
|---------|---------|---------|
|마이그레이션할 준비가 된 고객<br><br>마이그레이션할 기능:<br><ul><li>음성 메일</ul>   |   3월 - 2019년 5월  |예제:<ul><li>    간단한 음성 메일 배포 및 사용량이 있는 고객<li>Microsoft가 마이그레이션을 실행하기 위해 모든 요구 사항을 설정한 고객<ul>|
|필수 구성 요소가 있는 고객<br><br>마이그레이션할 기능:<br><ul><li>음성 메일<li>자동 전화 교환<li>통화 큐</ul> |  5월 - 2019년 12월 |예제: <br><ul><li>하이브리드 구성이 완료되지 않았습니다.<li>하이브리드 PSTN 번호가 설정되지 않음</ul>|
|고객 투자에 & 관리자 참여가 필요한 고객<br><br>마이그레이션할 기능:<ul><li>음성<li>자동 전화 교환<li>통화 큐<li>팩스 통합</ul>| 2020년 2월까지  | 예제: <br><ul><li>ExchUMO 서비스는 타사 PBX에서 사용됨<li>PSTN 구독자 액세스 요구 사항이 있는 고객<li>SFB 2010의 고객(지원되지 않음)<li>팩스 통합</ul> |

## <a name="voicemail-migration-guidelines"></a>음성 메일 마이그레이션 지침

### <a name="get-informed"></a>알림 받기

[블로그 공](https://blogs.technet.microsoft.com/exchange/2019/02/08/retiring-unified-messaging-in-exchange-online/)지 사항 및 이 문서를 숙지하여 사용자를 위한 원활한 마이그레이션을 계획하세요. 전화 시스템 음성 메일 기능에 대한 자세한 내용은 비즈니스용 Skype 음성 메일 [확인 및 옵션을](https://support.office.com/article/check-skype-for-business-voicemail-and-options-2deea7f8-831f-4e85-a0d4-b34da55945a8) 참조하세요.  

### <a name="establish-a-skype-for-business-hybrid-topology"></a>비즈니스용 Skype 하이브리드 토폴로지 설정

비즈니스용 Skype 하이브리드 토폴로지가 설정되지 않은 경우 음성 메일 사용자의 원활한 마이그레이션을 사용하도록 설정해야 합니다. 자세한 내용은 [비즈니스용 Skype 하이브리드 구성](../../SfbHybrid/hybrid/configure-federation-with-skype-for-business-online.md)을 참조하세요.

> [!Note]
> 음성 메일 서비스 마이그레이션을 위해 사용자를 온라인으로 마이그레이션할 필요가 없습니다. 그러나 온-프레미스 사용자가 전화 시스템 음성 메일 서비스를 활용하려면 하이브리드 토폴로지를 설정해야 합니다.

### <a name="plan-your-auto-attendant-migration"></a>자동 전화 교환 마이그레이션 계획

관리자는 언제든지 자동 전화 교환을 ExchUMO에서 클라우드 자동 전화 교환으로 마이그레이션할 수 있습니다. 자세한 내용은 [클라우드 자동 전화 교환 설정을](/microsoftteams/create-a-phone-system-auto-attendant) 참조하세요.

Microsoft는 고객이 마이그레이션에 필요한 것으로 간주할 수 있는 추가 자동 전화 교환 기능을 계속 제공합니다. 관리자는 기능 집합을 평가하고 그에 따라 자동 전화 교환 인스턴스를 마이그레이션해야 합니다. 기능 목록 비교는 [ExchUMO 및 Azure 클라우드 기반 서비스 기능 매트릭스를 참조하세요](#exchumo-and-azure-cloud-based-services-feature-matrix).

### <a name="plan-for-your-voicemail-post-migration-validation-and-testing"></a>음성 메일 마이그레이션 후 유효성 검사 및 테스트 계획

음성 메일 마이그레이션은 Microsoft 기반입니다. 필수 하이브리드 토폴로지가 설정된 경우 관리자는 아무 것도 수행할 필요가 없습니다. Microsoft는 사용자의 음성 메일 마이그레이션이 중단되지 않도록 필요한 유효성 검사 및 테스트를 수행합니다. 관리자는 해당 쪽에서 테스트 및 유효성 검사를 수행하는 것이 좋습니다. 권장 [테스트 계획은 관리자에 대한 제안된 테스트 계획 및 마이그레이션 후 유효성 검사를](#suggested-test-plan-and-post-migration-validation-for-admins) 참조하세요.

> [!Note]
> Lync Server 2010은 지원되지 않습니다. 2010년 서버 배포에 있는 경우 서버 업그레이드를 계획하거나 사용자를 Microsoft Teams 마이그레이션하는 것을 고려해야 합니다.  

### <a name="monitor-the-admin-notification-center"></a>관리 알림 센터 모니터링

관리 알림 센터에서 사용자의 마이그레이션에 대한 자세한 내용과 타임라인을 확인하세요. 알림은 마이그레이션 기간 30일 전에 전송됩니다.

> [!Note]
> 사용자의 마이그레이션 타임라인에 대한 알림을 받았고 중요 비즈니스용 이유로 마이그레이션을 연기하려는 경우 Microsoft 지원 문의하여 마이그레이션을 연기할 수 있습니다. 2020년 2월 28일의 사용 중지 날짜를 초과하여 마이그레이션을 연기할 수 없습니다. 더 많은 질문이 있을 수 있는 고객의 경우 계정 팀 또는 Microsoft 지원 문의하세요. 이미 Microsoft 365 또는 Office 365 사용하는 고객은 Microsoft 365 관리 센터 통해 지원 사례를 제출할 수 있습니다.

### <a name="consider-opting-in-for-a-planned-migration"></a>계획된 마이그레이션을 옵트인하는 것이 좋습니다.

CVM으로 계획된 Voicemail 서비스 마이그레이션을 옵트인할 수 있습니다. 옵트인하기 전에 이 문서의 세부 정보, 특히 다음 섹션을 검토합니다.

- 마이그레이션 단계(이 섹션)
- ExchUMO 및 Azure 클라우드 기반 서비스 기능 매트릭스
- 사용자 환경 영향

관리되는 마이그레이션을 선택하면 Microsoft 365 관리 포털 메시지 센터에서 마이그레이션 전 30일 알림이 수신되지 않습니다.

계획된 마이그레이션을 옵트인하려면 관리자의 이메일 주소에서 다음 정보를 사용하여 [cvm@microsoft.com](mailto:cvm@microsoft.com) 이메일 요청을 보냅니다.

- 기본 설정 날짜(화요일): 마이그레이션 웨이브는 매주 화요일에 실행됩니다. 2019년 12월 3일이 아닌 화요일에 날짜를 선택하세요.
 
- 테넌트 ID: 0046728c-688a-4472-a38f-098fec60ac6x 형식의 32자 번호입니다. Azure AD 아래의 Microsoft 365 관리 포털에서 또는 다음 PowerShell cmdlet을 사용하여 테넌트 ID를 찾을 수 있습니다.`Get-CsTenant | Select ObjectId`

테넌트가 성공적으로 마이그레이션되면 이메일 확인 메시지가 표시됩니다.

## <a name="auto-attendant-migration-guidelines"></a>자동 전화 교환 마이그레이션 지침

Microsoft 365 및 Office 365 조직 관리자는 Microsoft 클라우드 자동 전화 교환 서비스에서 Exchange UM Online 자동 전화 교환을 다시 만들고 2020년 2월 28일 Exchange UMO 서비스 사용 중지 날짜 이전에 온-프레미스 전화 번호를 전환해야 합니다. 새 클라우드 자동 전화 교환을 성공적으로 마이그레이션하고 테스트하는 데 권장되는 지침입니다. 자동 전화 교환이 많은 경우 [Exchange UM 자동 전화 교환을 클라우드 자동 전화 교환 마이그레이션 스크립트](https://github.com/NathanJBennett/ExUMAAMigrationToCloudAA)로 사용하여 자동 전화 교환의 대량 마이그레이션을 간소화할 수 있습니다.

### <a name="auto-attendant-setup"></a>자동 전화 교환 설정

마지막 순간 문제를 방지하고 클라우드 자동 전화 교환 서비스의 기능과 경험을 숙지하기 위해 새 자동 전화 교환 설정을 일찍 시작하는 것이 좋습니다. 하나 이상의 갭 기능이 필요한 자동 전화 교환의 경우 배포를 준비하는 데 갭 기능을 사용할 수 있는 경우 자동 전화 교환을 만들고 테스트할 수 있습니다. 간격 기능에 대한 자세한 내용은 [부록](#appendix)을 참조하세요.

1. Exchange UMO cmdlet을 사용하여 [Get-UMAutoAttendant](/powershell/module/exchange/unified-messaging/get-umautoattendant)를 사용하여 기존 자동 전화 교환의 구성을 내보냅니다.  

2. Exchange Online PowerShell에서 [Export-UMprompt](/powershell/module/exchange/unified-messaging/export-umprompt) cmdlet을 사용하여 인사말 미디어 파일(사용되는 경우)을 내보내고 .mp3 형식으로 변환합니다.

3. [Plan Cloud 자동 전화 교환](../../SfbHybrid/hybrid/plan-cloud-auto-attendant.md)의 지침에 따라 [클라우드 자동 전화 교환을 설정](/microsoftteams/create-a-phone-system-auto-attendant)하여 Microsoft Teams 관리 센터 또는 PowerShell을 사용하여 자동 전화 교환을 만듭니다.

4. 메뉴 옵션이 변경된 경우 인사말을 검토합니다.

5. 이 문서의 [알려진 문제](#known-issues) 섹션에서 "PSTN으로 자동 전화 교환 호출 전송" 해결 방법을 사용하여 응답 그룹에 대한 전송을 구성합니다.  

6. 내부적으로 전화하거나 테스트 전화 번호를 할당하여 새 자동 전화 교환을 테스트합니다.  

### <a name="cutover"></a>단독형

1. 전화 번호를 Exchange UMO 자동 전화 교환에서 새 자동 전화 교환으로 전환합니다.
2. 연락처 개체에서 리소스 계정으로 SIP URI를 이동합니다.
3. 새로 할당된 전화 번호를 사용하여 자동 전화 교환을 테스트하고 유효성을 검사합니다.

## <a name="appendix"></a>부록

### <a name="exchumo-and-azure-cloud-based-services-feature-matrix"></a>ExchUMO 및 Azure 클라우드 기반 서비스 기능 매트릭스

| 서비스 | 기능 수준 | 기능 | 메모  | 클라우드 VM/AA  | ExUMO |
|---------|-------|--------|----|--------|------|
| VM  | 서비스 기능| 타사 PBX 지원    | SIP를 사용하여 MWI(메시지 대기 표시기)와 같은 타사 PBX에 제공된 모든 기능 포함 Exchange UM Online의 메시지 알림 | N   | Y    |
| VM | 서비스 기능  | 지원 비즈니스용 Skype 서버   |  | Y | Y    |
| VM | 서비스 기능 | 지원 Microsoft Teams|  | Y | N    |
| VM | 서비스 기능 | eDiscovery 및 Hold  | 보안 및 규정 준수  | Y | Y    |
| VM | 서비스 기능 | Exchange 규칙 지원 | 보안 및 규정 준수  | Y | Y    |
| VM | 사용자 기능 | PSTN 전화 접속 액세스  | 구독자 액세스  | N | Y    |
| VM | 사용자 기능 | 대리인  | 부재 중 전화 메일  | N | Y    |
| VM | 사용자 기능 | PSTN Outlook Voice Access   | 구독자 액세스  | N | Y    |
| VM | 사용자 기능 | 인증된 엔드포인트를 사용하여 전화 접속 | 음성 메일 서비스에 전화하여 음성 메시지 수신 대기 및 음성 메일 설정 변경| Y | Y    |
| VM | 사용자 기능 | 음성 메일을 사용하지 않도록 설정하는 사용자 설정   |  | Y | Y    |
| VM | 사용자 기능 | 개인 인사말을 변경하는 사용자 설정  |  | Y | Y    |
| VM | 사용자 기능 | OOF 인사말을 만드는 사용자 설정  |  | Y | Y    |
| VM | 사용자 기능 | 기본 언어를 변경하는 사용자 설정  |  | Y | Y    |
| VM | 사용자 기능 | TTS를 사용하여 기본 인사말을 덮어쓰는 사용자 설정  |  | Y | N    |
| VM | 사용자 기능 | 개인 인사말 기록(인증된 디바이스) |  | Y | Y    |
| VM | 사용자 기능 | PSTN(개인 인사말 녹음) - 휴대폰으로 재생 |  | N | Y    |
| VM | 사용자 기능 | 전사를 사용하지 않도록 설정하는 사용자 설정 |  | N | Y    |
| VM | 사용자 기능 | 기록  |  | Y | Y    |
| VM | 사용자 기능 | SIP 알림 메시지를 사용하는 MWI(메시지 대기 표시기) |  | N | Y    |
| VM | 사용자 기능 | OUTLOOK MP3 오디오 파일 형식    |  | Y | Y    |
| VM | 사용자 기능 | 가변 속도 재생 컨트롤 |  | Y | Y    |
| VM | 사용자 기능 | 음성 메일 전달  | 받은 음성 메일을 다른 사용자에게 전달 | Y | Y    |
| VM | 사용자 기능 | 사용자 그룹에 음성 메시지 보내기  |음성 메일 브로드캐스트   | N | Y   |
| VM | 사용자 기능 | SMS 사용하여 음성 메일 알림    | 사용자는 새 음성 메일이 있는 경우 SMS 받을 수 있습니다.    | N | Y    |
| VM | 사용자 기능 | 지원되는 인사말 언어 | 세부 정보: [클라우드 자동 전화 교환이란?](/microsoftteams/what-are-phone-system-auto-attendants) | Y | Y    |
| VM | 사용자 기능 | 전화 응답 규칙 |  | Y | Y    |
| VM | 사용자 기능 | 전화(PSTN)에서 재생- 메시지 재생 | 내 셀에 전화를 걸어 음성 메시지를 듣습니다.  | N | Y    |
| VM | 사용자 기능 | 전화(인증)에서 재생 - 메시지 재생 | 인증된 디바이스에서 전화 걸기  | N | Y    |
| VM | 사용자 기능 | 여러 사용자 간의 공유 사서함 |  | Y | Y    |
| VM | 호출자 기능  | 발신자 환경 - 보호된 음성 메일 | 호출자는 기록된 메시지를 보호된 메시지로 표시하는 옵션을 선택할 수 있습니다.| N | Y    |
| VM | 호출자 기능  | 발신자 환경 - 개인 음성 메일 | 호출자는 기록된 메시지를 비공개로 표시하는 옵션을 선택할 수 있습니다.  | N | Y    |
| VM | 호출자 기능  | 무음 검색   |  | N | Y    |
| VM | Tenant-Admin 기능 | 서버 수준 보호 음성 메일    | 테넌트 관리자는 들어오는 음성 메일을 보호된 것으로 표시하도록 서비스 수준 규칙을 구성할 수 있습니다. | Y | Y    |
| VM | Tenant-Admin 기능 | 기록 기간 제한 변경  |     | Y | Y    |
| VM | Tenant-Admin 기능 | 무음 검색 시간 제한 변경    |  | 해당 없음    | Y    |
| VM | Tenant-Admin 기능 | 입력 오류 수 변경 | CVM: 하드 코딩된 3 | N | Y    |
| VM | Tenant-Admin 기능 | 기본 언어 변경 |  | Y | Y    |
| VM | Tenant-Admin 기능 | 전사 사용 안 함/사용 |  | Y | Y    |
| VM | Tenant-Admin 기능 | 부재 중 통화 알림 사용 안 함/사용 |  | N | Y    |
| VM | Tenant-Admin 기능 | Microsoft의 음성 메일 미리 보기 개선 지원    |  | Y | Y    |
| VM | Tenant-Admin 기능 | 사용하도록 설정된 사용자에 대한 문자 메시지 사용자 지정|  | 해당 없음    | Y    |
| VM | Tenant-Admin 기능 | 전사 욕설 마스킹|  | Y | N    |
| VM | Tenant-Admin 기능 | 음성 메일 정책    |   | Y | Y    |
| VM | Tenant-Admin 기능 | 웹 포털 관리   |  | CY19   | Y    |
| VM | Tenant-Admin 기능 | PowerShell   |  | Y | Y    |
| UM | 사용자 기능 | 비즈니스용 Skype 인증된 휴대폰의 MWI(메시지 대기 표시기)   |전화 파트너가 제공할 수 있습니다.  | 아니요 | 예    |
| AA | 서비스 기능 | AA는 타사 PBX를 지원합니다.    |  | N | Y    |
| AA | 서비스 기능 | 지원 비즈니스용 Skype 서버   |  | Y | Y    |
| AA | 서비스 기능 | 지원 Microsoft Teams|  | Y | N    |
| AA | 서비스 기능 | 이름으로 전화 걸기, DTMF 입력    |  | Y | Y    |
| AA | 서비스 기능 | 이름으로 전화 걸기, 음성 입력  |  | Y | Y    |
| AA | 서비스 기능 | 다국어 지원 | 언어 세부 정보: [클라우드 자동 전화 교환이란?](/microsoftteams/what-are-phone-system-auto-attendants) | Y | Y    |
| AA | 서비스 기능 | 운영자, CQ 또는 사용자로 전송 |  | Y | Y    |
| AA | 서비스 기능 | 내부적으로 PSTN 번호로 전송(DID RNL)  |  | Y | Y    |
| AA | 서비스 기능 | 외부적으로 PSTN 번호로 전송  |  | 아래의 알려진 문제 섹션을 확인하세요. | Y    |
| AA | 서비스 기능 | 업무 시간 |  | Y | Y    |
| AA | 서비스 기능 | 메뉴 옵션 | IVR 메뉴 옵션  | Y | Y    |
| AA | 서비스 기능 | AA에 클라우드 PSTN 번호 할당 |  | Y | N    |
| AA | 서비스 기능 | AA에 온-프레미스 PSTN 번호 할당  |  | Y | Y    |
| AA | 서비스 기능 | 사용자 지정 사용자 선택  | 발신자가 사용자 지정된 조직 사용자 목록에 도달할 수 있도록 설정| Y | Y    |
| AA | 서비스 기능 | 근무 시간 후 및 휴일 치료  |  | Y | Y    |
| AA | 서비스 기능 | 텍스트 음성 변환을 사용하는 사용자 지정 인사말  |  | Y | Y    |
| AA | 서비스 기능 | 내선 통화   | 확장 프로그램에 전화를 걸어 사용자에게 연결  | Y   | Y    |
| AA | 서비스 기능 | AA 발신자가 메시지를 남기는 사서함    |  | Y   | Y    |
| AA | 서비스 기능 | AA에 대한 여러 PSTN 번호 할당|  | Y | Y    |
| AA | Tenant-Admin 기능 | 웹 포털 관리   |  | Y | N    |
| AA | Tenant-Admin 기능 | PowerShell cmdlet  |  | Y | Y    |
| 팩스| 서비스 기능 | 팩스 통합|  | N | Y    |

### <a name="suggested-test-plan-and-post-migration-validation-for-admins"></a>관리자를 위한 제안된 테스트 계획 및 마이그레이션 후 유효성 검사

사용자가 클라우드 음성 사서함 마이그레이션되었는지 확인하려면 사용자에게 음성 메일을 두고 Outlook 메시지 본문을 확인합니다. 클라우드 음성 사서함 메시지에는 다음과 같은 바닥글이 있습니다.

"전사를 사용해 주셔서 감사합니다! 위의 대본이 보이지 않으면 오디오 품질이 충분히 명확하지 않았기 때문입니다."

사용자가 마이그레이션된 후 음성 메일 기능을 테스트할 때는 다음 시나리오를 고려해야 합니다.

- 앱 및 IP 휴대폰과 같은 조직의 모든 엔드포인트 유형에서 음성 메일 액세스의 유효성을 검사합니다.
- 구성된 개인 설정된 인사말이 발신자에게 재생되는지 샘플 사용자로 확인합니다.
- 조직에 사용자에 대한 전사를 사용하지 않도록 설정하는 법적 또는 규정 준수 요구 사항이 있는 경우 마이그레이션 후 비활성화되어 있는지 확인합니다. 자세한 내용은 [클라우드 음성 사서함 설정을](/microsoftteams/set-up-phone-system-voicemail) 참조하세요.
- 이전에 Exchange VM 정책 및 규칙을 구성한 경우 효과적인지 확인합니다.
- 사용자 설정을 변경하기 위해 클라우드 음성 사서함 서비스 PowerShell cmdlet을 숙지합니다.  

### <a name="user-experience-impact"></a>사용자 환경 영향

다음은 최종 사용자 음성 메일 마이그레이션 환경에 대한 개요입니다.


|환경  |사용자 환경 변경|
|---------|---------|
|전자 메일 알림 | 변경되지 않음<br>사용자에게 음성 메일 계정 활성화/마이그레이션에 대해 알리는 전자 메일이 전송되지 않습니다. |
|이전 메시지에 대한 액세스 | 변경되지 않음<br>사용자는 지원되는 모든 엔드포인트에서 이전 음성 메일 메시지에 액세스할 수 있습니다. |
|Outlook에서 VM 수신, SFB 앱| 변경되지 않음<br>사용자는 지원되는 모든 엔드포인트에서 음성 메일 메시지를 계속 받습니다. |
|기록 | 강화<br>CVM 전사는 ExchUMO보다 정확도 및 지원되는 언어가 훨씬 높습니다. |
|사용자 설정 | 새로운 환경<br>사용자는 USP(사용자 설정 포털)에서 기본 설정을 변경할 수 있습니다. 사용자는 음성 메일 전자 메일의 하이퍼링크 또는 SFB 클라이언트의 User-Settings 단추에서 USP에 액세스할 수 있습니다. https://aka.ms/vmsettings.
 |기능| 자세한 내용은 기능 집합 비교를 참조하세요. |
|VM 메시지에 대한 Outlook 규칙 | 변경되지 않음<br>이전에 만든 규칙은 마이그레이션 후 CVM 메시지에 적용됩니다.
 |

### <a name="user-management-and-provisioning-in-cvm"></a>CVM의 사용자 관리 및 프로비전

새 비즈니스용 Skype 사용자는 생성될 때 클라우드 음성 메일에 대해 자동으로 프로비전됩니다. 새 음성 메일 사용자를 프로비전하는 데 추가 관리자 작업 또는 라이선스가 필요하지 않습니다. 기존 및 새 사용자의 정책 관리에 대해 알아보려면 [클라우드 음성 사서함 설정을](/microsoftteams/set-up-phone-system-voicemail) 참조하세요.

### <a name="admin-auto-attendant-management-experience"></a>자동 전화 교환 관리 환경 관리

자동 전화 교환에 대한 자세한 내용은 [클라우드 자동 전화 교환 설정을](/microsoftteams/create-a-phone-system-auto-attendant) 참조하세요.

### <a name="known-issues"></a>알려진 문제

#### <a name="greeting-inconsistencies"></a>인사말 불일치

모든 사용자가 클라우드 음성 사서함 마이그레이션된 후에도 서비스가 완전히 사용 중지될 때까지 구독자 액세스는 테넌트에서 계속 작동할 수 있습니다. 사용자 혼란과 일관성 없는 환경을 방지하려면 마이그레이션 후 인사말이 변경되므로 구독자 액세스를 사용하지 않도록 설정합니다. 이렇게 하려면 .를 사용하여 각 구독자 액세스 줄에 대한 EXUM 연락처를 `Get-CsExUmContact | ?{$_.IsSubscriberAccess -eq $true} | Remove-CsExUmContact`제거합니다.

#### <a name="auto-attendant-call-transfer-to-pstn"></a>PSTN으로 자동 전화 교환 통화 전송

비즈니스용 Skype 서버 또는 비즈니스용 Skype 서버 RGS(응답 그룹 서비스)를 통해 외부 PSTN 전화 번호로 자동 전화 교환 통화를 전송하려면 착신 전환이 PSTN 전화 번호 또는 RGS 전화 번호로 설정된 새 온-프레미스 사용자를 만듭니다. 사용자는 Enterprise Voice 대해 사용하도록 설정되고 올바르게 구성되어야 하며 음성 정책이 할당되어 있어야 합니다.

#### <a name="shared-mailbox-is-still-accessible"></a>공유 사서함에 계속 액세스할 수 있음

Exchange UM Online을 사용하여 구성된 공유 사서함은 CVM으로 마이그레이션한 후에도 계속해서 메시지를 받고 Outlook 통해 사용자가 액세스할 수 있습니다. 그러나 CVM으로 마이그레이션한 후에는 이러한 사서함의 인사말 메시지를 변경하는 액세스 권한을 사용할 수 없습니다. 자동 전화 교환 발신자를 캡처하는 데 사용되는 공유 사서함이 있는 고객은 릴리스된 후 자동 전화 교환 및 통화 큐 공유 사서함 기능을 활용해야 합니다(ETA 2019년 10월).
  
#### <a name="username-is-not-using-skype-for-business-banner-displays"></a>"사용자 이름이 비즈니스용 Skype 사용하지 않음" 배너 표시

CVM 서비스는 Microsoft Teams 인프라를 기반으로 하며, 비즈니스용 Skype 클라이언트의 호출로 인해 클라이언트에 정보 배너가 표시될 수 있습니다. "사용자 이름은 비즈니스용 Skype 사용하고 있지 않습니다. 더 풍부한 환경을 위해 Teams 전환하거나 Skype 모임을 시작하세요."
이 배너가 표시되지 않도록 사용자의 비즈니스용 Skype 클라이언트를 최신 C2R 클라이언트 업데이트로 업데이트해야 합니다.
  
#### <a name="set-up-voice-mail-takes-you-to-owa"></a>"음성 메일 설정"은 OWA로 이동합니다.

클라이언트에서 **음성 메일 설정을** 클릭하면 CVM으로 마이그레이션한 후 비즈니스용 Skype 서버 2015/2013 고객을 OWA(Office Web Access) 포털 페이지로 계속 이동합니다. OWA의 음성 메일 탭에서 모든 설정이 제거되었으며 사용자를 CVM 사용자 설정 포털로 이동하도록 리디렉션 링크가 있는 배너가 표시됩니다.

#### <a name="changing-greeting-remotely"></a>원격으로 인사말 변경

PSTN 구독자 액세스는 CVM에서 지원되지 않습니다. 원격으로 인사말을 변경해야 하는 사용자의 경우 모바일 클라이언트용 음성 메일 IVR 서비스에 "인사말 변경" 메뉴 옵션이 추가되었습니다. 사용자는 모바일 클라이언트 다이얼 패드에서 "1" 키를 길게 눌러 이 서비스를 호출할 수 있습니다.