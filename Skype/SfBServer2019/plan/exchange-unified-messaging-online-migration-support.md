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
description: Microsoft는 2020년 2월 28일까지 Exchange ExchUMO(통합 메시징 온라인) 서비스를 중지합니다. 이 문서에서는 영향을 받는 고객이 알아야 할 내용과 비즈니스 연속성을 계획하기 위해 해야 하는 작업을 요약합니다.
ms.openlocfilehash: 933ba625506496c01242b26712e9b6d5b020dbb199c5f515444f7a8734fb84b9
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54279596"
---
# <a name="exchange-unified-messaging-online-migration-support"></a>Exchange 통합 메시징 온라인 마이그레이션 지원

> [!IMPORTANT]
> **2020년 2월 28일 오후 Exchange Online 태평양 표준시 현재 통합 메시징 서비스가 지원되지 않습니다. 모든 음성메일 계정이 Microsoft에서 클라우드 음성 사서함 서비스로 마이그레이션했습니다. 남은 자동 회의 트래픽은 모니터링되지 않습니다. 이로 인한 중단이 있을 수 있습니다.**

2019년 2월 8일 발표와 관련해 Microsoft는 2020년 2월 28일까지 Exchange ExchUMO(통합 메시징 온라인) 서비스를 중지합니다. [](https://blogs.technet.microsoft.com/exchange/2019/02/08/retiring-unified-messaging-in-exchange-online/) 이 문서에서는 영향을 받는 고객이 알아야 할 내용과 비즈니스 연속성을 계획하기 위해 해야 하는 작업을 요약하여 제공합니다.

ExchUMO는 고객이 음성 메일, 자동 전화 전송, 통화 큐 및 팩스 통합 서비스를 위해 배포합니다. Microsoft는 고객이 전화 시스템 Online 및 2013에서 이미 수천 명의 고객을 지원하는 비즈니스용 Skype 서비스로 마이그레이션하는 데 Microsoft Teams.

음성메일은 주로 Microsoft 주도 마이그레이션입니다. 일부 고객에게는 관리자 개입 및/또는 투자가 요구될 수 있습니다. 자동 수행은 관리자가 주도하는 마이그레이션입니다. 클라우드 서비스 클라우드 서비스에서 기존 ExchUMO 자동 자동 전화 교환 만들어야 합니다. 타사 PBX에서 ExchUMO 기능을 소비하는 고객은 타사 PBX 시스템을 지원하지 Skype 클라우드 서비스로 마이그레이션되지 않습니다. 타사 지원에 대한 사용 중지 계획이 [](https://techcommunity.microsoft.com/t5/Exchange-Team-Blog/New-date-for-discontinuation-of-support-for-Session-Border/ba-p/607853)이 블로그에 발표되었습니다. 이 배포 모델의 고객은 사용자를 Microsoft의 Unified Communications 플랫폼/서비스 중 하나로 마이그레이션하거나 이러한 사용자를 위한 타사 음성메일 및/또는 자동 길에서 솔루션을 취득할 수 있습니다. 팩스 통합은 클라우드 기반 서비스에서 지원되지 않습니다. 고객은 타사 솔루션으로 마이그레이션해야 합니다.

## <a name="who-is-affected"></a>Who 영향을 받나요?

통합 메시징 Online 서비스의 다음 Exchange 영향을 받는 고객은 다음과 같습니다.

- 음성메일 서비스
- 자동 전화 교환 서비스
- 통화 큐 서비스
- 팩스 통합

> [!Note]
> 통합 메시징과 함께 Exchange Server 모든 Exchange Server 사용하는 고객은 영향을 받지 않습니다.

사용자 환경 영향의 사용자 및 관리자 환경 [영향에 대해 자세히 알아보시다.](#user-experience-impact)

## <a name="migration-plan-overview"></a>마이그레이션 계획 개요

Microsoft는 ExchUMO의 기능을 사용하는 다양한 고객 배포를 확인하여 다음 계획을 기반으로 고객의 마이그레이션을 지원할 것입니다.

|고객 그룹 |시간 표시 막대  |세부 정보  |
|---------|---------|---------|
|마이그레이션할 준비가 된 고객<br><br>마이그레이션할 기능:<br><ul><li>음성 메일</ul>   |   2019년 3월 -5월  |예제:<ul><li>    간단한 음성메일 배포 및 사용이 있는 고객<li>Microsoft에서 마이그레이션을 실행할 수 있도록 모든 요구 사항이 설정된 고객<ul>|
|선행 조인이 있는 고객<br><br>마이그레이션할 기능:<br><ul><li>음성 메일<li>자동 전화 교환<li>통화 큐</ul> |  2019년 5월 -12월 |예제: <br><ul><li>하이브리드 구성이 완료되지 않습니다.<li>하이브리드 PSTN 번호가 설정되지 않습니다.</ul>|
|관리자 개입이 필요한 & 투자<br><br>마이그레이션할 기능:<ul><li>voicemail<li>자동 전화 교환<li>통화 큐<li>팩스 통합</ul>| 2020년 2월까지  | 예제: <br><ul><li>ExchUMO 서비스는 타사 PBX에서 사용<li>PSTN 구독자 액세스 요구 사항이 있는 고객<li>SFB 2010의 고객(지원되지 않습니다)<li>팩스 통합</ul> |

## <a name="voicemail-migration-guidelines"></a>음성메일 마이그레이션 지침

### <a name="get-informed"></a>정보 얻기

사용자를 위한 원활한 마이그레이션을 계획하기 위해 블로그 공지 및 이 문서에 익숙해지세요. [](https://blogs.technet.microsoft.com/exchange/2019/02/08/retiring-unified-messaging-in-exchange-online/) 음성 [비즈니스용 Skype](https://support.office.com/article/check-skype-for-business-voicemail-and-options-2deea7f8-831f-4e85-a0d4-b34da55945a8) 기능에 대한 자세한 내용은 음성 전화 시스템 확인을 참조하세요.  

### <a name="establish-a-skype-for-business-hybrid-topology"></a>하이브리드 비즈니스용 Skype 설정

하이브리드 토폴로지가 비즈니스용 Skype 없는 경우 음성메일 사용자를 원활하게 마이그레이션할 수 있도록 설정해야 합니다. 자세한 [비즈니스용 Skype 하이브리드](../../SfbHybrid/hybrid/configure-federation-with-skype-for-business-online.md) 구성을 참조합니다.

> [!Note]
> 음성메일 서비스 마이그레이션을 위해 온라인으로 사용자를 마이그레이션할 필요는 없습니다. 그러나 프레미스 사용자가 음성 전화 시스템 서비스를 활용하려면 하이브리드 토폴로지를 설정해야 합니다.

### <a name="plan-your-auto-attendant-migration"></a>자동 수행 마이그레이션 계획

관리자는 ExchUMO에서 클라우드 자동 회의로 자동 회의를 마이그레이션할 수 있습니다. 자세한 [내용은 클라우드 자동 회의](/microsoftteams/create-a-phone-system-auto-attendant) 설정하기를 참조합니다.

Microsoft는 고객이 마이그레이션에 필요한 것으로 고려할 수 있는 추가 자동 회의 기능을 계속 제공합니다. 관리자는 기능 집합을 평가하고 그에 따라 자동 회의 인스턴스를 마이그레이션해야 합니다. 기능 목록 비교는 ExchUMO 및 Azure 클라우드 기반 [서비스 기능 매트릭스를 참조하세요.](#exchumo-and-azure-cloud-based-services-feature-matrix)

### <a name="plan-for-your-voicemail-post-migration-validation-and-testing"></a>음성메일 마이그레이션 후 유효성 검사 및 테스트 계획

음성메일 마이그레이션은 Microsoft에서 주도합니다. 필수 하이브리드 토폴로지가 설정되었다고 하여 관리자는 아무 것도 할 필요는 없습니다. Microsoft는 필요한 유효성 검사 및 테스트를 수행하여 사용자의 음성메일 마이그레이션이 중단되지 않는지 확인합니다. 관리자는 테스트 및 유효성 검사를 수행하도록 권장됩니다. 권장 [테스트 계획은](#suggested-test-plan-and-post-migration-validation-for-admins) 관리자에 대한 권장 테스트 계획 및 마이그레이션 후 유효성 검사를 참조하세요.

> [!Note]
> Lync Server 2010은 지원되지 않습니다. 2010 서버 배포의 경우 서버 업그레이드를 계획하거나 사용자를 서버 업그레이드로 마이그레이션하는 Microsoft Teams.  

### <a name="monitor-the-admin-notification-center"></a>관리 알림 센터 모니터링

관리 알림 센터에서 사용자의 마이그레이션에 대한 추가 세부 정보 및 타임라인을 통해 알림을 시청하세요. 알림은 마이그레이션 기간 30일 전에 전송됩니다.

> [!Note]
> 사용자의 마이그레이션 일정에 대한 알림을 받았고 업무상 중요한 이유로 마이그레이션을 연기하려는 경우 Microsoft 지원에 문의하면 됩니다. 2020년 2월 28일의 사용 중지 날짜가 지난 마이그레이션은 연기할 수 없습니다. 더 많은 질문이 있을 수 있는 고객은 계정 팀 또는 Microsoft 지원에 문의하세요. 이미 고객 또는 Microsoft 365 Office 365 지원 사례를 제출할 수 Microsoft 365 관리 센터.

### <a name="consider-opting-in-for-a-planned-migration"></a>계획된 마이그레이션에 옵트인(opt in)을 고려합니다.

계획된 음성메일 서비스 마이그레이션을 CVM으로 옵트인(opt in)할 수 있습니다. 옵트인하기 전에 이 문서의 세부 정보, 특히 다음 섹션을 검토하세요.

- 마이그레이션 단계(이 섹션)
- ExchUMO 및 Azure 클라우드 기반 서비스 기능 매트릭스
- 사용자 환경 영향

관리되는 마이그레이션을 선택하면 Microsoft 365 포털 메시지 센터에서 마이그레이션 30일 전 알림이 수신되지 않습니다.

계획된 마이그레이션에 옵트인(opt in)을 수행하기 위해 관리자의 전자 메일 주소에서 다음 cvm@microsoft.com 전자 [메일](mailto:cvm@microsoft.com) 요청을 전송합니다.

- 기본 설정 날짜(화요일): 매주 화요일에 마이그레이션 단계가 실행됩니다. 2019년 12월 3일을 초과하지 않는 화요일 날짜를 선택하시기 바랍니다.
 
- 테넌트 ID: 0046728c-688a-4472-a38f-098fec60ac6x 형식의 32자 번호입니다. Azure AD의 Microsoft 365 포털에서 테넌트 ID를 찾거나 다음 PowerShell cmdlet을 사용하여 찾을 수 있습니다.`Get-CsTenant | Select ObjectId`

테넌트가 성공적으로 마이그레이션된 후 전자 메일 확인을 받게 됩니다.

## <a name="auto-attendant-migration-guidelines"></a>자동 수행 마이그레이션 지침

Microsoft 365 및 Office 365 조직 관리자는 Microsoft 클라우드 자동 전화 교환 서비스에서 Exchange UM Online 자동 전화 회의를 다시 만들고 2020년 2월 28일의 Exchange UMO 서비스 사용 중지 날짜 전에 해당 전화 번호를 해당 사용자로 전환해야 합니다. 이 지침은 새 클라우드 자동 전화 회의를 성공적으로 마이그레이션하고 테스트하는 데 권장되는 지침입니다. 자동 전화 회의 수가 많은 경우 Exchange [UM](https://github.com/NathanJBennett/ExUMAAMigrationToCloudAA) 자동 전화 교환 to Cloud 자동 전화 교환 마이그레이션 스크립트를 사용하여 자동 전화 회의의 일괄 마이그레이션을 간소화할 수 있습니다.

### <a name="auto-attendant-setup"></a>자동 전화 교환 설정

마지막 순간 문제를 방지하고 Cloud 자동 전화 교환 서비스의 기능에 익숙해지기 위해 새 자동 자동 전화 교환 설치하는 것이 좋습니다. 하나 이상의 갭 기능이 필요한 자동 참석의 경우 간격 기능을 사용하여 배포를 준비할 수 있는 경우 자동 자동 회의를 만들고 테스트할 수 있습니다. 갭 기능에 대한 자세한 내용은 [부록 을 참조하세요.](#appendix)

1. UMO cmdlet을 Exchange [Get-UMAutoAttendant를](/powershell/module/exchange/unified-messaging/get-umautoattendant)사용하여 기존 자동 회의의 구성을 내보낼 수 있습니다.  
2. PowerShell에서 [Export-UMprompt](/powershell/module/exchange/unified-messaging/export-umprompt) cmdlet을 Exchange Online 인사말 미디어 파일을 내보내고(사용하는 경우) 해당 파일을 .mp3 변환합니다.
3. Plan Cloud auto attendants 및 [Set up a Cloud auto attendant의](/microsoftteams/create-a-phone-system-auto-attendant) 지침에 따라 Microsoft Teams 관리 센터 또는 Powershell을 사용하여 자동 Microsoft Teams 만들 수 있습니다. [](../../SfbHybrid/hybrid/plan-cloud-auto-attendant.md)
4. 메뉴 옵션이 변경된 경우 인사말을 검토합니다.
5. 이 문서의 알려진 문제 섹션에서 "자동 전화 교환 PSTN으로 통화 전송" 해결 [](#known-issues) 방법을 사용하여 응답 그룹에 대한 전송을 구성합니다.  
6. 내부적으로 전화를 걸거나 테스트 전화 번호를 할당하여 새 자동 전화 번호를 테스트합니다.  

### <a name="cutover"></a>단독형

1. UMO 자동 전화 Exchange 전화 번호를 새 자동 전화 번호로 전환합니다.
2. 연락처 개체에서 리소스 계정으로 SIP URI를 이동합니다.
3. 새로 할당된 전화 번호를 사용하여 자동 전화 회의를 테스트하고 유효성을 검사합니다.

## <a name="appendix"></a>부록

### <a name="exchumo-and-azure-cloud-based-services-feature-matrix"></a>ExchUMO 및 Azure 클라우드 기반 서비스 기능 매트릭스

| 서비스 | 기능 수준 | 기능 | 메모  | 클라우드 VM/AA  | ExUMO |
|---------|-------|--------|----|--------|------|
| VM  | 서비스 기능| 자사 PBX 지원    | SIP 알림 메시지를 사용하여 MWI(Message Waiting Indicator)와 같은 타사 PBX에 제공되는 모든 Exchange 포함 | N   | Y    |
| VM | 서비스 기능  | 지원 비즈니스용 Skype 서버   |  | Y | Y    |
| VM | 서비스 기능 | 지원 Microsoft Teams|  | Y | N    |
| VM | 서비스 기능 | eDiscovery 및 보류  | 보안 및 규정 준수  | Y | Y    |
| VM | 서비스 기능 | Exchange 규칙 지원 | 보안 및 규정 준수  | Y | Y    |
| VM | 사용자 기능 | PSTN 전화 접속 액세스  | 구독자 액세스  | N | Y    |
| VM | 사용자 기능 | 대리인  | 부재 중 전화 전자 메일  | N | Y    |
| VM | 사용자 기능 | PSTN Outlook Voice Access   | 구독자 액세스  | N | Y    |
| VM | 사용자 기능 | 인증된 끝점을 사용한 전화 접속 | 음성 메일 서비스에서 음성 메시지를 듣고 음성 메일 설정을 변경하기 위해 호출| Y | Y    |
| VM | 사용자 기능 | 음성메일을 사용하지 않도록 설정하는 사용자 설정   |  | Y | Y    |
| VM | 사용자 기능 | 개인 인사말을 변경하기 위한 사용자 설정  |  | Y | Y    |
| VM | 사용자 기능 | OOF 인사말을 만들기 위한 사용자 설정  |  | Y | Y    |
| VM | 사용자 기능 | 기본 언어를 변경하는 사용자 설정  |  | Y | Y    |
| VM | 사용자 기능 | TTS로 기본 인사말을 덮어치기 위한 사용자 설정  |  | Y | N    |
| VM | 사용자 기능 | 개인 인사말 녹음(인증된 장치) |  | Y | Y    |
| VM | 사용자 기능 | PSTN(개인 인사말) 녹음 - 전화에서 재생 |  | N | Y    |
| VM | 사용자 기능 | 전사를 사용하지 않도록 설정하는 사용자 설정 |  | N | Y    |
| VM | 사용자 기능 | 기록  |  | Y | Y    |
| VM | 사용자 기능 | SIP 알림 메시지를 사용하는 MWI(Message Waiting Indicator) |  | N | Y    |
| VM | 사용자 기능 | MP3 오디오 파일 형식(Outlook    |  | Y | Y    |
| VM | 사용자 기능 | 가변 속도 재생 컨트롤 |  | Y | Y    |
| VM | 사용자 기능 | 음성메일 전달  | 받은 음성메일을 다른 사용자에게 전달 | Y | Y    |
| VM | 사용자 기능 | 사용자 그룹에 음성 메시지 보내기  |음성메일 브로드캐스트   | N | Y   |
| VM | 사용자 기능 | SMS를 사용한 음성 메일 알림    | 사용자가 새 음성 메시지를 받을 때 SMS를 받을 수 있습니다.    | N | Y    |
| VM | 사용자 기능 | 지원되는 인사말 언어 | 자세한 내용은 다음을 참조하세요. https://docs.microsoft.com/microsoftteams/what-are-phone-system-auto-attendants | Y | Y    |
| VM | 사용자 기능 | 전화 응답 규칙 |  | Y | Y    |
| VM | 사용자 기능 | 전화에서 재생(PSTN)- 메시지를 재생합니다. | 내 셀에서 전화로 음성 메시지를 들을 수 있습니다.  | N | Y    |
| VM | 사용자 기능 | 전화에서 재생(Auth)- 메시지를 재생합니다. | 인증된 장치에서 전화 걸기  | N | Y    |
| VM | 사용자 기능 | 여러 사용자 간의 공유 사서함 |  | Y | Y    |
| VM | 발신자 기능  | 발신자 환경 - 보호된 음성메일 | 발신자 는 녹음된 메시지를 보호된 메시지로 표시하는 옵션을 선택할 수 있습니다.| N | Y    |
| VM | 발신자 기능  | 발신자 환경 - 개인 음성메일 | 발신자에서 녹음된 메시지를 비공개로 표시하는 옵션을 선택할 수 있습니다.  | N | Y    |
| VM | 발신자 기능  | 침묵 감지   |  | N | Y    |
| VM | Tenant-Admin 기능 | 서버 수준 보호 음성메일    | 테넌트 관리자는 들어오는 음성 메일이 보호된 것으로 표시하도록 서비스 수준 규칙을 구성할 수 있습니다. | Y | Y    |
| VM | Tenant-Admin 기능 | 기록 기간 제한 변경  |     | Y | Y    |
| VM | Tenant-Admin 기능 | 침묵 감지 시간 제한 변경    |  | 해당 없음    | Y    |
| VM | Tenant-Admin 기능 | 입력 오류 발생 횟수 변경 | CVM: 3으로 하드 코딩 | N | Y    |
| VM | Tenant-Admin 기능 | 기본 언어 변경 |  | Y | Y    |
| VM | Tenant-Admin 기능 | 전사 사용/사용 안 하도록 설정 |  | Y | Y    |
| VM | Tenant-Admin 기능 | 부재 중 전화 알림 사용/사용 안 하도록 설정 |  | N | Y    |
| VM | Tenant-Admin 기능 | Microsoft에서 음성 메일 미리 보기 개선 지원    |  | Y | Y    |
| VM | Tenant-Admin 기능 | 사용하도록 설정된 사용자에 대해 문자 메시지 사용자 지정|  | 해당 없음    | Y    |
| VM | Tenant-Admin 기능 | 전사 비음성 마스킹|  | Y | N    |
| VM | Tenant-Admin 기능 | 음성메일 정책    |   | Y | Y    |
| VM | Tenant-Admin 기능 | 웹 포털 관리   |  | CY19   | Y    |
| VM | Tenant-Admin 기능 | PowerShell   |  | Y | Y    |
| UM | 사용자 기능 | 인증된 전화의 MWI(Message Waiting Indicator)비즈니스용 Skype 대기 중입니다.   |전화 파트너가 제공될 수 있습니다.  | 아니요 | 예    |
| AA | 서비스 기능 | AA에서 자사 PBX 지원    |  | N | Y    |
| AA | 서비스 기능 | 지원 비즈니스용 Skype 서버   |  | Y | Y    |
| AA | 서비스 기능 | 지원 Microsoft Teams|  | Y | N    |
| AA | 서비스 기능 | 이름으로 전화 걸기, DTMF 입력    |  | Y | Y    |
| AA | 서비스 기능 | 이름으로 전화 걸기, 음성 입력  |  | Y | Y    |
| AA | 서비스 기능 | 다국어 지원 | 언어 세부 정보는 다음과 같습니다. https://docs.microsoft.com/microsoftteams/what-are-phone-system-auto-attendants | Y | Y    |
| AA | 서비스 기능 | 운영자, CQ 또는 사용자로 전송 |  | Y | Y    |
| AA | 서비스 기능 | 내부적으로 PSTN 번호로 전송(DID RNL)  |  | Y | Y    |
| AA | 서비스 기능 | 외부에서 PSTN 번호로 전송  |  | 아래의 알려진 문제 섹션을 확인하세요. | Y    |
| AA | 서비스 기능 | 업무 시간 |  | Y | Y    |
| AA | 서비스 기능 | 메뉴 옵션 | IVR 메뉴 옵션  | Y | Y    |
| AA | 서비스 기능 | AA에 클라우드 PSTN 번호 할당 |  | Y | N    |
| AA | 서비스 기능 | AA에 프레미스 PSTN 번호 할당  |  | Y | Y    |
| AA | 서비스 기능 | 사용자 지정 사용자 선택  | 발신자에서 조직 사용자 목록에 연결하도록 설정| Y | Y    |
| AA | 서비스 기능 | 근무 시간 이후 및 휴일 처리  |  | Y | Y    |
| AA | 서비스 기능 | 텍스트 음성으로 인사말을 사용하는 사용자 지정 인사말  |  | Y | Y    |
| AA | 서비스 기능 | 내선 전화 걸기   | 내선 번호로 전화를 걸고 사용자에게 연결  | Y   | Y    |
| AA | 서비스 기능 | AA 발신자에 대해 메시지를 남길 사서함    |  | Y   | Y    |
| AA | 서비스 기능 | AA에 대한 여러 PSTN 번호 할당|  | Y | Y    |
| AA | Tenant-Admin 기능 | 웹 포털 관리   |  | Y | N    |
| AA | Tenant-Admin 기능 | PowerShell cmdlet  |  | Y | Y    |
| 팩스| 서비스 기능 | 팩스 통합|  | N | Y    |

### <a name="suggested-test-plan-and-post-migration-validation-for-admins"></a>관리자를 위한 제안된 테스트 계획 및 마이그레이션 후 유효성 검사

사용자가 마이그레이션된 메시지의 유효성을 클라우드 음성 사서함 음성 메일은 그대로 두고 메시지 본문은 Outlook. 클라우드 음성 사서함 메시지에 다음을 읽는 발자국이 있습니다.

"전사 사용에 감사합니다. 위의 녹음/소문자가 없는 경우 오디오 품질이 녹음할 수 있을 만큼 명확하지 않은 것이기 때문에 그에 해당합니다."

사용자가 마이그레이션된 후 음성메일 기능을 테스트할 때 다음 시나리오를 고려해야 합니다.

- 앱 및 IP 전화와 같은 조직의 모든 끝점 유형에서 음성메일 액세스의 유효성을 검사합니다.
- 샘플 사용자로 구성된 개인 설정 인사말이 발신자에 대해 재생하는지 유효성을 검사합니다.
- 조직에서 사용자에 대한 설명을 사용하지 않도록 설정해야 하는 법적 또는 규정 준수 요구 사항이 있는 경우 마이그레이션 후 사용되지 않도록 설정되어 있는지 확인하십시오. 자세한 내용은 Set [up 클라우드 음성 사서함.](/microsoftteams/set-up-phone-system-voicemail)
- 이전에 VM 정책 및 Exchange 구성한 경우 효과적인지 확인 합니다.
- 사용자 설정을 변경하기 위한 클라우드 음성 사서함 PowerShell cmdlet을 잘 알고 있습니다.  

### <a name="user-experience-impact"></a>사용자 환경 영향

다음은 최종 사용자 음성메일 마이그레이션 환경의 개요입니다.


|환경  |사용자 환경 변경|
|---------|---------|
|전자 메일 알림 | 변경되지 않음<br>사용자에게 음성 메일 계정 활성화/마이그레이션에 대해 알리는 전자 메일이 전송되지 않습니다. |
|이전 메시지에 대한 액세스 | 변경되지 않음<br>사용자는 지원되는 모든 끝점에서 이전 음성 메일 메시지에 액세스할 수 있습니다. |
|Outlook에서 VM 수신, SFB 앱| 변경되지 않음<br>사용자는 지원되는 모든 끝점에서 음성 메일 메시지를 계속 받게 됩니다. |
|기록 | 고급<br>CVM 전사는 ExchUMO보다 훨씬 더 정확도가 높고 지원되는 언어입니다. |
|사용자 설정 | 새 환경<br>사용자는 USP(사용자 설정 포털)에서 기본 설정을 변경할 수 있습니다. 사용자는 음성 메일 전자 메일의 하이퍼링크 또는 SFB 클라이언트의 User-Settings 단추에서 USP에 액세스할 수 있습니다. https://aka.ms/vmsettings.
 |기능| 자세한 내용은 기능 집합 비교를 참조하시기 바랍니다. |
|Outlook VM 메시지에 대한 규칙 | 변경되지 않음<br>이전에 만든 규칙은 마이그레이션 후 CVM 메시지에 적용됩니다.
 |

### <a name="user-management-and-provisioning-in-cvm"></a>CVM의 사용자 관리 및 프로비전

새 비즈니스용 Skype 클라우드 음성메일을 만들 때 자동으로 프로비전됩니다. 새 음성메일 사용자를 프로비전하는 데 추가 관리자 작업 또는 라이선스가 필요하지 않습니다. 기존 [및 클라우드 음성 사서함](/microsoftteams/set-up-phone-system-voicemail) 대한 정책 관리에 대한 자세한 내용은 Set up 클라우드 음성 사서함 참조합니다.

### <a name="admin-auto-attendant-management-experience"></a>관리 자동 전화 교환 환경

자동 회의에 대한 자세한 내용은 클라우드 자동 회의 설정 [을 참조합니다.](/microsoftteams/create-a-phone-system-auto-attendant)

### <a name="known-issues"></a>알려진 문제

#### <a name="greeting-inconsistencies"></a>인사말 불일치

구독자 액세스는 모든 사용자가 마이그레이션된 후에도 서비스가 완전히 사용 중지될 때까지 테넌트에 대해 클라우드 음성 사서함. 사용자 혼동과 불일치 환경을 방지하기 위해 마이그레이션 후 인사말이 변경되어 구독자 액세스를 사용하지 않도록 설정하세요. 이를 위해 를 사용하여 각 구독자 액세스 줄에 대한 EXUM 연락처를 `Get-CsExUmContact | ?{$_.IsSubscriberAccess -eq $true} | Remove-CsExUmContact` 제거합니다.

#### <a name="auto-attendant-call-transfer-to-pstn"></a>자동 전화 교환 PSTN으로 통화 전송

비즈니스용 Skype 서버 또는 RGS(응답 그룹 서비스)를 통해 외부 PSTN 전화 번호로 자동 전화 비즈니스용 Skype 서버 PSTN 전화 번호 또는 RGS 전화 번호로 통화 전달이 설정된 새 사내 사용자를 만드시오. 사용자를 사용하도록 설정하고 음성 정책이 할당된 Enterprise Voice 올바르게 구성해야 합니다.

#### <a name="shared-mailbox-is-still-accessible"></a>공유 사서함에 계속 액세스할 수 있습니다.

Exchange UM Online을 사용하여 구성된 공유 사서함은 CVM으로 마이그레이션한 후에도 계속 메시지를 수신하며, 이 사서함을 통해 사용자가 액세스할 수 Outlook. 그러나 CVM으로 마이그레이션한 후 이러한 사서함의 인사말 메시지를 변경하는 액세스는 사용할 수 없습니다. 자동 전화 걸기 발신자 캡처에 사용되는 공유 사서함을 사용하는 고객은 ETA(2019년 10월)가 출시된 후 자동 전화 걸기 및 통화 큐 공유 사서함 기능을 활용해야 합니다.
  
#### <a name="username-is-not-using-skype-for-business-banner-displays"></a>"사용자 이름이 사용자 이름을 사용하지 비즈니스용 Skype" 배너가 표시됩니다.

CVM 서비스는 Microsoft Teams 인프라를 기반으로 하며, 비즈니스용 Skype 클라이언트의 호출로 인해 클라이언트에 정보 배너가 표시될 수 있습니다. "Username is not using 비즈니스용 Skype. 더 풍부한 환경을 위해 Teams 전환하거나 Skype 시작하세요."
이 배너가 나타나지 않도록 사용자의 비즈니스용 Skype 클라이언트를 최신 C2R 클라이언트 업데이트로 업데이트해야 합니다.
  
#### <a name="set-up-voice-mail-takes-you-to-owa"></a>"음성 메일 설정"을 통해 OWA로 전송

클라이언트에서  음성 메일 설치를 클릭하면 비즈니스용 Skype 서버 2015/2013 고객을 CVM으로 마이그레이션한 후 OWA(Office Web Access) 포털 페이지로 계속 이동합니다. 모든 설정이 OWA의 음성메일 탭에서 제거되고 사용자를 CVM 사용자 설정 포털로 이동하는 리디렉션 링크가 배너에 표시됩니다.

#### <a name="changing-greeting-remotely"></a>원격으로 인사말 변경

PSTN 구독자 액세스는 CVM에서 지원되지 않습니다. 원격으로 인사말을 변경해야 하는 사용자의 경우 모바일 클라이언트용 음성메일 IVR 서비스에 "인사말 변경" 메뉴 옵션이 추가되었습니다. 사용자는 모바일 클라이언트 다이얼 패드에서 "1" 키를 눌러 이 서비스를 호출할 수 있습니다.