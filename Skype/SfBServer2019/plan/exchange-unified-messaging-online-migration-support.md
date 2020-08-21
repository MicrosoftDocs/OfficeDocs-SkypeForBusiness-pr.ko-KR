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
localization_priority: Normal
description: Microsoft는 2020년 2월 28일까지 Exchange 통합 메시징 온라인(ExchUMO) 서비스를 사용합니다. 이 문서에서는 영향을 받는 고객이 비즈니스 연속성을 계획하기 위해 알고 있어야 하는 사항과 계획을 세심화합니다.
ms.openlocfilehash: 587a6f0e17729181d7e0ba2389ed32faee07ff71
ms.sourcegitcommit: bb5229c9f7999358dcf0ba185ecfd7c881627a38
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46824899"
---
# <a name="exchange-unified-messaging-online-migration-support"></a>Exchange 통합 메시징 온라인 마이그레이션 지원

> [!IMPORTANT]
> **Exchange Online의 통합 메시징 서비스는 2020년 2월 28일, PM PM PM의 PM(이동 시간) 옵션을 지원하지 않습니다. 모든 음성 사서함 계정은 Microsoft에 의해 클라우드 음성 메일 서비스로 마이그레이션되었습니다. 남은 자동 전화 교환 트래픽은 모니터링되지 않고 때마다 어드레이될 수 있습니다.**

2019년 2월 8일에 공지된 면에서 Microsoft는 2020년 2월 28일까지 Exchange 통합 메시징 온라인(ExchUMO) 서비스를 사용하고 있습니다. [announcement](https://blogs.technet.microsoft.com/exchange/2019/02/08/retiring-unified-messaging-in-exchange-online/) 이 문서에서는 영향을 받는 고객이 알고 있어야 하는 사항에 대한 요약과 해당 비즈니스 지속성을 계획하기 위해 계획할 수 있습니다.

ExchUMO는 음성 메일, 자동 전화 교환, 통화 큐 및 팩스 통합 서비스에 대해 고객이 배포합니다. Microsoft는 고객이 비즈니스용 Skype 온라인 및 Microsoft Teams에서 수수명 고객을 이미 지원하는 전화 시스템 서비스로 마이그레이션하도록 도와주기 위해 계획합니다.

음성 사서함은 주로 Microsoft 주도 마이그레이션입니다. 고객 하위 집합에 대해 관리자의 투자 및/또는 투자가 필요할 수 있습니다. 자동 전화 교환은 관리자 기반 마이그레이션입니다. 클라우드 서비스에서 기존 ExchUMO 자동 전화 교환 트리를 다시 자동 전화 교환 합니다. 타사 PBX가 포함된 ExchUMO 기능을 사용하는 고객은 타사 PBX 시스템을 지원하지 않기 때문에 Skype 클라우드 서비스로 마이그레이션되지 않습니다. 타사 지원에 대한 서비스 만료 계획이 이 [블로그에 발표되었고,](https://techcommunity.microsoft.com/t5/Exchange-Team-Blog/New-date-for-discontinuation-of-support-for-Session-Border/ba-p/607853)이 배포 모델의 고객은 해당 사용자를 Microsoft의 통합 통신 플랫폼/서비스 중 하나로 마이그레이션하거나 이러한 사용자를 위한 타사 음성 메일 및/또는 자동 전화 교환 솔루션을 취득할 수 있습니다. 클라우드 기반 서비스에서 팩스 통합이 지원되지 않습니다. 고객은 타사 솔루션으로 마이그레이션해야 합니다.

## <a name="who-is-affected"></a>누가 영향을 받는사람인가요?

Exchange 통합 메시징 Online 서비스의 다음 기능 중 하나를 사용하는 고객에게는 다음 이 제한이 적용됩니다.

- 음성 메일 서비스
- 자동 전화 교환 서비스
- 통화 큐 서비스
- 팩스 통합

> [!Note]
> 통합 메시징에서 온-Exchange Server 온-프레미스를 사용하는 고객은 영향을 받지 않습니다.

사용자 환경 영향의 사용자 및 관리자 환경 영향에 대해 [자세히 알아봅니다.](#user-experience-impact)

## <a name="migration-plan-overview"></a>마이그레이션 계획 개요

Microsoft는 ExchUMO의 기능을 소비하고 다음 계획을 기반으로 고객을 마이그레이션하는 데 도와주하는 다양한 고객 배포를 확인하고 있습니다.

|고객 그룹 |시간 표시 막대  |세부 정보  |
|---------|---------|---------|
|마이그레이션 준비가 된 고객<br><br>마이그레이션할 기능:<br><ul><li>음성 메일</ul>   |   2019년 3월  |예제:<ul><li>    단순 음성 메일 배포 및 사용 방법을 보는 고객<li>Microsoft에서 마이그레이션을 실행하도록 모든 요구 사항을 설정한 고객<ul>|
|필수 구성 요소가 있는 고객<br><br>마이그레이션할 기능:<br><ul><li>음성 메일<li>자동 전화 교환<li>통화 큐</ul> |  2019년 12월 |예제: <br><ul><li>하이브리드 구성이 완료되지 않았습니다.<li>하이브리드 PSTN 번호가 설정되지 않았습니다.</ul>|
|고객의 투자가 필요로 하는 & 고객<br><br>마이그레이션할 기능:<ul><li>음성 메일<li>자동 전화 교환<li>통화 큐<li>팩스 통합</ul>| 2020년 2월  | 예제: <br><ul><li>ExchUMO 서비스는 타사 PBX에서 사용합니다.<li>PSTN 구독자 액세스 요구 사항이 있는 고객<li>SFB 2010 고객(지원되지 않음)<li>팩스 통합</ul> |

## <a name="voicemail-migration-guidelines"></a>음성 메일 마이그레이션 지침

### <a name="get-informed"></a>정보 받기

블로그 알림 및 이 문서를 숙지하여 사용자에게 자일스러운 마이그레이션을 계획하는 것이 좋습니다. [blog announcement](https://blogs.technet.microsoft.com/exchange/2019/02/08/retiring-unified-messaging-in-exchange-online/) 비즈니스용 [Skype 음성 메일 및 전화 시스템 음성 메일 기능에](https://support.office.com/article/check-skype-for-business-voicemail-and-options-2deea7f8-831f-4e85-a0d4-b34da55945a8) 대한 자세한 내용은 옵션을 확인하세요.  

### <a name="establish-a-skype-for-business-hybrid-topology"></a>비즈니스용 Skype 하이브리드 토폴로지 설정

비즈니스용 Skype 하이브리드 토폴로지를 설정하지 않은 경우 음성 사서함 사용자의 마이그레이션을 3단계 적확으로 수행할 수 있도록 해야 합니다. 자세한 [내용은 비즈니스용 Skype 하이브리드](../../SfbHybrid/hybrid/configure-federation-with-skype-for-business-online.md) 구성을 참조하세요.

> [!Note]
> 음성 사서함 서비스 마이그레이션을 위해 사용자를 온라인으로 마이그레이션할 필요는 없습니다. 그러나 온-프레미스 사용자가 전화 시스템 음성 메일 서비스를 사용하려면 하이브리드 토폴로지를 만들어야 합니다.

### <a name="plan-your-auto-attendant-migration"></a>자동 전화 교환 마이그레이션 계획

관리자는 자동 전화 교환을 자동 전화 교환을 ExchUMO에서 클라우드 자동 전화 교환으로 마이그레이션할 수 있습니다. 자세한 [내용은 클라우드 자동 전화 교환 설정을](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant) 참조하세요.

Microsoft는 고객이 마이그레이션에 필요한 것으로 간주할 수 있는 추가 자동 전화 교환 기능을 계속 제공합니다. 관리자는 기능 집합을 평가하고 이에 따라 자동 전화 교환 인스턴스를 마이그레이션해야 합니다. 기능 목록 비교는 [ExchUMO 및 Azure 클라우드 기반 서비스 기능 매트릭스를 참조하세요.](#exchumo-and-azure-cloud-based-services-feature-matrix)

### <a name="plan-for-your-voicemail-post-migration-validation-and-testing"></a>마이그레이션 후 유효성 검사 및 테스트 계획

음성 메일 마이그레이션은 Microsoft를 기본으로 제공합니다. 필수 구성 요소 하이브리드 토폴로지가 설정되지 않은 경우에는 관리자가 아무 작업도 수행할 필요가 없습니다. Microsoft는 필수 유효성 검사와 테스트를 수행하여 사용자의 음성 메일 마이그레이션이 위험하지 않았는지 확인합니다. 관리자는 측면에서 테스트 및 유효성 검사를 수행하는 데 좋습니다. 권장 [테스트 계획에 대한 관리자를 위한 제안 테스트 계획 및 마이그레이션 후](#suggested-test-plan-and-post-migration-validation-for-admins) 유효성 검사를 참조하세요.

> [!Note]
> Lync Server 2010은 지원되지 않습니다. 2010 서버 배포를 사용하고 있는 경우 서버 업그레이드를 계획하거나 사용자를 Microsoft Teams 또는 비즈니스용 Skype Online으로 마이그레이션하는 것을 고려해야 합니다.  

### <a name="monitor-the-admin-notification-center"></a>관리 알림 센터 모니터링

사용자의 마이그레이션과 관련한 세부 정보 및 타임라인을 사용하여 관리 알림 센터의 알림을 볼 수 있습니다. 마이그레이션 기간 30일 전에 알림이 적어도 30일 전에 전송됩니다.

> [!Note]
> 사용자의 마이그레이션 타임라인이 포함된 알림을 받고 업무상 중요한 이유로 마이그레이션을 연기하려면 Microsoft 지원 센터에 문의하면 됩니다. 2020년 2월 28일이 지나면 마이그레이션은 연기할 수 없습니다. 추가 질문이 있는 고객은 계정 팀 또는 Microsoft 지원 센터에 문의하세요. 이미 Microsoft 365 또는 Office 365를 사용하고 있는 고객은 Microsoft 365 관리 센터를 통해 지원 사례를 제출할 수 있습니다.

### <a name="consider-opting-in-for-a-planned-migration"></a>계획된 마이그레이션에 대한 옵트인 고려

CVM으로 계획된 음성 메일 서비스 마이그레이션에 옵트인을 할 수 있습니다. 옵트인하기 전에 이 문서의 세부 정보, 특히 다음 섹션을 검토하세요.

- 마이그레이션 단계(이 섹션)
- ExchUMO 및 Azure 클라우드 기반 서비스 기능 매트릭스
- 사용자 환경 영향

관리되는 마이그레이션을 선택하더라도 Microsoft 365 관리 포털 메시지 센터에는 30일 전 알림이 표시되지 않습니다.

계획된 마이그레이션을 옵트인하려면 관리자의 전자 메일 주소에서 다음 정보를 [cvm@microsoft.com](mailto:cvm@microsoft.com) 요청을 보냅니다.

- 기본 설정 날짜(화요일): 마이그레이션 프로세스는 화요일마다 실행됩니다. 화요일에서 2019년 12월 3일이 아니면 날짜를 선택하세요.
 
- 테넌트 ID: 이 형식의 32자 숫자 0046728c-688a-4472-a38f-098fec60ac6x 형식입니다. Azure AD의 Microsoft 365 관리 포털에서 또는 다음 PowerShell cmdlet을 사용하여 테넌트 ID를 찾을 수 있습니다. `Get-CsTenant | Select ObjectId`

테넌트가 마이그레이션되면 전자 메일 확인을 받게 됩니다.

## <a name="auto-attendant-migration-guidelines"></a>자동 전화 교환 마이그레이션 지침

Microsoft 365 및 Office 365 조직 관리자는 Exchange UMO 서비스 만료일이 2020년 2월 28일 이전에 Microsoft 클라우드 자동 전화 교환 서비스에서 Exchange UM Online 자동 전화 교환을 다시 만들고 온-프레미스 전화 번호를 두 전화 번호로 전환해야 합니다. 새 클라우드 자동 전화 교환을 성공적으로 마이그레이션하고 테스트하기 위한 권장 지침입니다. 많은 자동 전화 교환을 사용하는 경우 Exchange [UM 자동 전화 교환 to Cloud 자동 전화 교환 Migration 스크립트를](https://github.com/NathanJBennett/ExUMAAMigrationToCloudAA) 사용하여 자동 전화 교환의 대량 마이그레이션을 단순화할 수 있습니다.

### <a name="auto-attendant-setup"></a>자동 전화 교환 설정

지난 분 동안 문제를 방지하고 클라우드 자동 전화 교환 서비스의 기능과 환경에 익숙해지려면 새 자동 전화 교환 설치를 조기에 시작하는 것이 좋습니다. 하나 이상의 문자 표시 기능이 필요한 자동 전화 교환의 경우, 배포준비를 위해 Gap 기능을 사용할 수 있는 경우 자동 전화 교환을 만들고 테스트할 수 있습니다. 5월 기능에 대한 자세한 내용은 [부록을 참조하십시오.](#appendix)

1. Exchange UMO cmdlet을 사용하여 [Get-UMAutoAttendant를](https://docs.microsoft.com/powershell/module/exchange/unified-messaging/get-umautoattendant)사용하여 기존 자동 전화 교환의 구성을 내보낼 수 있습니다.  
2. Exchange Online [PowerShell에서 Export-UMprompt](https://docs.microsoft.com/powershell/module/exchange/unified-messaging/export-umprompt) cmdlet을 사용하여 인사색 미디어 파일(사용하는 경우)을 내보낸 다음 .mp3 형식으로 변환합니다.
3. 클라우드 자동 전화 교환 [계획의 지침을 따라](../../SfbHybrid/hybrid/plan-cloud-auto-attendant.md) [클라우드](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant) 자동 전화 교환을 설정하여 Microsoft Teams 관리 센터 또는 Powershell을 사용하여 자동 전화 교환을 만듭니다.
4. 메뉴 옵션이 변경된 경우 인사리를 검토합니다.
5. 이 문서의 알려진 문제 섹션에서 "자동 전화 교환 PSTN으로 통화 전송" 해결 방법을 [사용하여 응답 그룹에](#known-issues) 대한 전송을 구성합니다.  
6. 전화 걸기를 내부적으로 호출하거나 테스트 전화 번호를 할당하여 새 자동 전화 교환을 테스트합니다.  

### <a name="cutover"></a>단독형

1. Exchange UMO 자동 전화 교환에서 새 자동 전화 교환으로 전화 번호를 전환합니다.
2. 연락처 개체의 SIP URI를 리소스 계정으로 이동합니다.
3. 새로 할당된 전화 번호로 자동 전화 교환을 테스트하고 유효성을 검사합니다.

## <a name="appendix"></a>부록

### <a name="exchumo-and-azure-cloud-based-services-feature-matrix"></a>ExchUMO 및 Azure 클라우드 기반 서비스 기능 매트릭스

| 서비스 | 기능 수준 | 기능 | 참고  | 클라우드 VM/AA  | ExUMO |
|---------|-------|--------|----|--------|------|
| VM  | 서비스 기능| 타사 PBX 지원    | Exchange UM Online의 SIP 알림 메시지를 사용하여 MWI(Message Waiting Indicator) 같은 타사 PBX에 제공된 모든 기능 포함 | N   | 예    |
| VM | 서비스 기능  | 비즈니스용 Skype 서버 지원   |  | 예 | 예    |
| VM | 서비스 기능 | Microsoft Teams 지원|  | 예 | N    |
| VM | 서비스 기능 | eDiscovery 및 보류  | 보안 및 규정 준수를 위한 정보  | 예 | 예    |
| VM | 서비스 기능 | Exchange 규칙 지원 | 보안 및 규정 준수를 위한 정보  | 예 | 예    |
| VM | 사용자 기능 | PSTN 전화 접속 액세스  | 구독자 액세스  | N | 예    |
| VM | 사용자 기능 | 대리인  | 통화 보지 않음  | N | 예    |
| VM | 사용자 기능 | PSTN Outlook Voice Access   | 구독자 액세스  | N | 예    |
| VM | 사용자 기능 | 인증된 끝점을 사용하여 전화 접속 | 음성 메시지를 재생하고 음성 메일 설정을 변경하도록 음성 사서함 서비스 호출| 예 | 예    |
| VM | 사용자 기능 | 음성 사서함을 사용하지 않도록 설정하는 사용자 설정   |  | 예 | 예    |
| VM | 사용자 기능 | 개인 인사리스를 변경하는 사용자 설정  |  | 예 | 예    |
| VM | 사용자 기능 | OOF 인사트를 만들기 위한 사용자 설정  |  | 예 | 예    |
| VM | 사용자 기능 | 기본 언어를 변경하기 위한 사용자 설정  |  | 예 | 예    |
| VM | 사용자 기능 | TTS로 기본 인사사오를 덮어쓰기 위한 사용자 설정  |  | 예 | N    |
| VM | 사용자 기능 | 개인 인사소리 녹음(인증된 장치) |  | 예 | 예    |
| VM | 사용자 기능 | PR(개인 인사영) 기록 — 전화에서 재생 |  | N | 예    |
| VM | 사용자 기능 | 전사를 사용하지 않도록 설정하는 사용자 설정 |  | N | 예    |
| VM | 사용자 기능 | 기록  |  | 예 | 예    |
| VM | 사용자 기능 | 모든 끝점에서 음성 메일 만들기   | 지원되는 모든 끝점에서 재생, 삭제, 메시지 대기 표시기 및 상태 설정/상태 설정을 가리키는 사용자 제어  | 예 | 예    |
| VM | 사용자 기능 | Outlook의 MP3 오디오 파일 형식    |  | 예 | 예    |
| VM | 사용자 기능 | 가변 속도 재생 컨트롤 |  | 예 | 예    |
| VM | 사용자 기능 | 음성 메일 전달  | 수신한 음성 메일을 다른 사용자에게 전달 | 예 | 예    |
| VM | 사용자 기능 | 사용자 그룹에 음성 메시지 보내기  |음성 메일 브로드캐스트   | N | 예   |
| VM | 사용자 기능 | SMS를 사용하는 음성 메일 알림    | 사용자는 새 음성 사서함이 있을 경우 SMS를 받을 수 있습니다.    | N | 예    |
| VM | 사용자 기능 | 지원되는 인사사일 | 세부 정보는 다음을 참조하세요. https://docs.microsoft.com/microsoftteams/what-are-phone-system-auto-attendants | 예 | 예    |
| VM | 사용자 기능 | 전화 응답 규칙 |  | 예 | 예    |
| VM | 사용자 기능 | 전화에서 재생(PSTN) - 메시지를 재생 | 음성 메시지를 받기 위해 내 셀에서 전화 걸기  | N | 예    |
| VM | 사용자 기능 | 전화에서 재생(인증)- 메시지를 재생하기 | 인증된 디바이스에서 전화 걸기  | 예 | 예    |
| VM | 사용자 기능 | 여러 사용자 간 공유 사서함 |  | 예 | 예    |
| VM | 발신자 기능  | 발신자 환경 - 보호된 음성 메일 | 호출자는 녹음된 메시지를 보호된 것으로 표시하는 옵션을 선택할 수 있습니다.| N | 예    |
| VM | 발신자 기능  | 발신자 환경 - 비공개 음성 메일 | 호출자는 녹음된 메시지를 비공개로 표시하는 옵션을 선택할 수 있습니다.  | N | 예    |
| VM | 발신자 기능  | 자동 검색   |  | N | 예    |
| VM | 테넌트 관리 기능 | 서버 수준 보호 음성 메일    | 테넌트 관리자는 들어오는 음성 메일을 보호된 것으로 표시하도록 서비스 수준 규칙을 구성할 수 있습니다. | 예 | 예    |
| VM | 테넌트 관리 기능 | 녹음/녹화 기간 제한 변경  |     | 예 | 예    |
| VM | 테넌트 관리 기능 | 자동 감지 시간 제한 변경    |  | 해당 없음    | 예    |
| VM | 테넌트 관리 기능 | 입력 오류 발생 횟수 변경 | CVM: 3으로 하드 코드 | N | 예    |
| VM | 테넌트 관리 기능 | 기본 언어 변경 |  | 예 | 예    |
| VM | 테넌트 관리 기능 | 전사 사용 안 함/사용 하도록 설정 |  | 예 | 예    |
| VM | 테넌트 관리 기능 | "제한된 전화 알림 사용 안 함/사용 안 함 |  | N | 예    |
| VM | 테넌트 관리 기능 | Microsoft의 음성 메일 미리 보기 기능 개선    |  | 예 | 예    |
| VM | 테넌트 관리 기능 | 사용하도록 설정된 사용자에 대한 문자 메시지 사용자 지정|  | 해당 없음    | 예    |
| VM | 테넌트 관리 기능 | 전사 비행접성 마스크|  | 예 | N    |
| VM | 테넌트 관리 기능 | 음성 메일 정책    |   | 예 | 예    |
| VM | 테넌트 관리 기능 | 웹 포털 관리   |  | CY19   | 예    |
| VM | 테넌트 관리 기능 | PowerShell   |  | 예 | 예    |
| UM | 사용자 기능 | 비즈니스용 Skype 인증 전화기의 MWI(Message Waiting Indicator)   |전화 파트너가 제공할 수 있습니다.  | 아니요 | 예    |
| AA | 서비스 기능 | AA support 타사 PBX    |  | N | 예    |
| AA | 서비스 기능 | 비즈니스용 Skype 서버 지원   |  | 예 | 예    |
| AA | 서비스 기능 | Microsoft Teams 지원|  | 예 | N    |
| AA | 서비스 기능 | 이름으로 전화 걸기, DTMF 입력    |  | 예 | 예    |
| AA | 서비스 기능 | 이름으로 전화 걸기, 음성 입력  |  | 예 | 예    |
| AA | 서비스 기능 | 다국어 지원 | 여기서는 언어 정보를 제공합니다. https://docs.microsoft.com/microsoftteams/what-are-phone-system-auto-attendants | 예 | 예    |
| AA | 서비스 기능 | 연산자, CQ 또는 사용자에게 연결 |  | 예 | 예    |
| AA | 서비스 기능 | PSTN 번호를 내부적으로 전송(DID RNL)  |  | 예 | 예    |
| AA | 서비스 기능 | 외부에서 PSTN 번호로 전송  |  | 아래의 알려진 문제 섹션 확인 | 예    |
| AA | 서비스 기능 | 업무 시간 |  | 예 | 예    |
| AA | 서비스 기능 | 메뉴 옵션 | IVR 메뉴 옵션  | 예 | 예    |
| AA | 서비스 기능 | AA에 클라우드 PSTN 번호 할당 |  | 예 | N    |
| AA | 서비스 기능 | AA에 온-프레미스 PSTN 번호 할당  |  | 예 | 예    |
| AA | 서비스 기능 | 사용자 지정 사용자 선택  | 발신자가 사용자의 사용자 지정 목록으로 연결하도록 설정| 예 | 예    |
| AA | 서비스 기능 | 업무 시간 이후 및 휴일 처리  |  | 예 | 예    |
| AA | 서비스 기능 | 텍스트 음성 변환을 사용하는 사용자 지정 인사사사  |  | 예 | 예    |
| AA | 서비스 기능 | 내선 통화   | 내선 번호로 전화를 걸어 사용자에 연결  | 예   | 예    |
| AA | 서비스 기능 | AA 호출자가 메시지를 남기기 위한 사서함    |  | 예   | 예    |
| AA | 서비스 기능 | AA에 대한 여러 PSTN 번호 할당|  | 예 | 예    |
| AA | 테넌트 관리 기능 | 웹 포털 관리   |  | 예 | N    |
| AA | 테넌트 관리 기능 | PowerShell cmdlet  |  | 예 | 예    |
| 팩스| 서비스 기능 | 팩스 통합|  | N | 예    |

### <a name="suggested-test-plan-and-post-migration-validation-for-admins"></a>관리자에 대한 제안 테스트 계획 및 마이그레이션 후 유효성 검사

사용자가 클라우드 음성 메일로 마이그레이션되었는지 확인하려면 음성 메일을 사용자에게 남기고 Outlook에서 메시지 본문을 확인합니다. 클라우드 음성 메일 메시지의 내용이 다음과 같은 항목에서 읽을 수 있습니다.

"전기 감사합니다. 위에서 녹음메시지가 나타나지 않으면 오디오 품질이 기록하기에 충분하지 않았기 때문입니다."

사용자를 마이그레이션한 후 음성 메일 기능을 테스트할 때는 다음 시나리오를 고려해야 합니다.

- 앱 및 IP 전화 같은 조직의 모든 끝점 유형에서 음성 메일 액세스가 유효성을 검사합니다.
- 구성된 개인 설정 인사서가 발신자에 재생된 샘플 사용자와 유사합니다.
- 조직에 사용자의 전사적 을 사용하지 않도록 설정하는 법적 또는 규정 준수 요구 사항이 있는 경우 마이그레이션 후 해당 규정을 사용하지 않도록 설정설정되어 있는지 확인합니다. 자세한 내용은 클라우드 음성 [메일 설정을 참조하세요.](/microsoftteams/set-up-phone-system-voicemail)
- 이전에 Exchange VM 정책 및 규칙을 구성한 경우 규칙이 적용되는지 확인합니다.
- 사용자 설정 변경에 대 하여 클라우드 음성 메일 서비스 PowerShell cmdlet에 익숙해지고 있습니다.  

### <a name="user-experience-impact"></a>사용자 환경 영향

다음은 최종 사용자 음성 메일 마이그레이션 환경의 개요입니다.


|환경  |사용자 환경 변경|
|---------|---------|
|이메일 알림 | 변경되지 않음<br>사용자에게 음성 메일 계정 활성화/마이그레이션에 대해 사용자에게 전자 메일이 전송되지 않습니다. |
|이전 메시지 액세스 | 변경되지 않음<br>사용자는 지원되는 모든 끝점에서 이전 음성 메일 메시지에 액세스할 수 있습니다. |
|Outlook, SFB 앱의 VM 다운로드| 변경되지 않음<br>사용자는 지원되는 모든 끝점에서 계속 음성 메일 메시지를 받습니다. |
|기록 | 고급<br>CVM 메시지 처리 속도가 ExchUMO보다 훨씬 높습니다. |
|사용자 설정 | 새로운 환경<br>사용자는 USP(사용자 설정 포털)에서 자신의 기본 설정을 변경할 수 있습니다. 사용자는 음성 메일 전자 메일에 있는 하이퍼링크에서 USP에 액세스하거나, SFB 클라이언트의 사용자 설정 단추에 액세스할 수 있습니다. https://aka.ms/vmsettings.
 |기능| 자세한 내용은 기능 집합 비교를 참조하세요. |
|VM 메시지에 대한 Outlook 규칙 | 변경되지 않음<br>이전에 만든 규칙은 마이그레이션 후 CVM 메시지에 적용됩니다.
 |

### <a name="user-management-and-provisioning-in-cvm"></a>CVM의 사용자 관리 및 프로비전

새 비즈니스용 Skype 사용자가 만들어진 경우 자동으로 클라우드 음성 메일이 프로비저닝됩니다. 새 음성 메일 사용자를 프로비저닝하는 데 추가 관리자 작업 또는 라이선스는 필요하지 않습니다. 기존 [사용자 및 새 사용자에 대한 정책](/microsoftteams/set-up-phone-system-voicemail) 관리에 대해 알아보려면 클라우드 음성 사서함설정을 참조하세요.

### <a name="admin-auto-attendant-management-experience"></a>관리자 자동 전화 교환 관리 환경

자동 전화 교환에 대한 자세한 내용은 클라우드 [자동 전화 교환 설정을 참조하세요.](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant)

### <a name="known-issues"></a>알려진 문제

#### <a name="greeting-inconsistencies"></a>인사색 일관성 유지

모든 사용자가 클라우드 음성 메일로 마이그레이션된 후에도 서비스가 완전히 중지될 때까지 구독자 액세스는 테넌트에 대해 계속 작동할 수 있습니다. 사용자의 충돌과 일관되지 않은 환경을 방지하려면 인사간이 마이그레이션 이후 변경된 이후 구독자 액세스를 비활성화합니다. 이렇게 하려면 각 구독자 액세스 라인에 대한 EXUM 연락처를 `Get-CsExUmContact | ?{$_.IsSubscriberAccess -eq $true} | Remove-CsExUmContact` 제거합니다.

#### <a name="auto-attendant-call-transfer-to-pstn"></a>자동 전화 교환 통화를 PSTN으로 전송

비즈니스용 Skype 서버 또는 비즈니스용 Skype 서버에서 PSTN(응답 그룹 서비스)을 통해 자동 전화 교환 통화를 외부 PSTN 전화 번호로 전송하려면, 통화 전달이 PSTN 전화 번호 또는 RGS 전화 번호로 설정된 새 온-프레미스 사용자를 만듭니다. 사용자에게 규칙을 사용하도록 설정하고 음성 Enterprise Voice 가능하도록 올바르게 구성해야 합니다.

#### <a name="shared-mailbox-is-still-accessible"></a>공유 사서함에 계속 액세스 가능

Exchange UM Online을 사용하여 구성된 공유 사서함은 CVM으로 마이그레이션된 후 메시지를 받고 Outlook을 통해 사용자가 액세스할 수 있습니다. 그러나 마이그레이션된 사서함의 인사다리어 메시지 변경 기능은 CVM으로 마이그레이션된 후에 사용할 수 없습니다. 자동 전화 교환 발신자를 캡처하는 데 사용되는 공유 사서함을 사용하는 고객은 자동 전화 교환 및 통화 큐 공유 사서함 기능을 릴리스(2019년 10월) 이용해야 합니다.
  
#### <a name="username-is-not-using-skype-for-business-banner-displays"></a>"사용자 이름에서 비즈니스용 Skype를 사용하고 있지 않습니다." 배너 표시

CVM 서비스는 Microsoft Teams 인프라를 기반으로 하며 비즈니스용 Skype 클라이언트에서 오는 호출은 정보 배너가 "사용자 이름에 비즈니스용 Skype를 사용하고 있지 않습니다. 더욱 풍부한 환경을 위해 Teams로 전환하거나 Skype 모임을 시작하는 등의 작업을 지원하세요."
이 배너가 표시되지 않도록 사용자의 비즈니스용 Skype 클라이언트를 최신 C2R 클라이언트 업데이트로 업데이트해야 합니다.
  
#### <a name="set-up-voice-mail-takes-you-to-owa"></a>"음성 메일 을 설정"을 선택하면 OWA로 연결

클라이언트에서 **음성 메일을 설정을** 클릭하면 CVM으로 마이그레이션한 후에도 비즈니스용 Skype 서버 2015/2013 고객을 Office Web Access(OWA) 포털 페이지에 계속 연결합니다. OWA의 음성 메일 탭에서 모든 설정이 제거되었고 배너가 사용자를 CVM 사용자 설정 포털로 이동하기 위한 리디렉션 링크가 포함된 모습으로 표시됩니다.

#### <a name="changing-greeting-remotely"></a>원격으로 인사간 변경

CVM에서는 PSTN 구독자 액세스가 지원되지 않습니다. 인사영을 원격으로 변경해야 하는 사용자의 경우 모바일 클라이언트의 음성 메일 IVR 서비스에 "인사색 변경" 메뉴 옵션이 추가되었습니다. 사용자는 모바일 클라이언트 다이얼 패드에서 "1" 키를 길게 눌러 서고 통화할 수 있습니다.
