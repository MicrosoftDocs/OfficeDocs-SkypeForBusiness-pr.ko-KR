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
description: Microsoft는 2020 년 2 월 28 일부 터 ExchUMO (Exchange 통합 메시징 온라인) 서비스를 더 이상 중지 하 고 있습니다. 이 문서에서는 영향을 받는 고객이 비즈니스 연속성을 계획 하 고 수행 해야 하는 작업을 요약 하 여 설명 합니다.
ms.openlocfilehash: 57f7575626d00cbd7c592349ca7a5a92c75eb34c
ms.sourcegitcommit: 2874aec7768bb46ed4506c1a2d431841f47190bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2020
ms.locfileid: "47255441"
---
# <a name="exchange-unified-messaging-online-migration-support"></a>Exchange 통합 메시징 온라인 마이그레이션 지원

> [!IMPORTANT]
> **Exchange Online의 통합 메시징 서비스는 2020 년 2 월 28 일 오후 5 시 (태평양 표준시)로 지원 되지 않습니다. 모든 음성 메일 계정이 Microsoft에서 클라우드 음성 메일 서비스로 마이그레이션 되었습니다. 나머지 자동 전화 교환 트래픽은 모니터링 되지 않으며 언제 든 지 중단 될 수 있습니다.**

2019 년 2 월 8 일의 [공지 사항](https://blogs.technet.microsoft.com/exchange/2019/02/08/retiring-unified-messaging-in-exchange-online/) 에 대 한 참조에서 Microsoft는 Exchange um Online (ExchUMO) 서비스를 2020 년 2 월 28 일까 지를 중지 합니다. 이 문서에서는 영향을 받는 고객이 비즈니스 연속성을 계획 하 고 수행 해야 하는 항목에 대 한 요약 정보를 제공 합니다.

ExchUMO는 음성 메일, 자동 전화 교환, 통화 큐 및 팩스 통합 서비스에 대해 고객에 의해 배포 됩니다. 고객이 비즈니스용 Skype 온라인 및 Microsoft 팀에서 수천 명의 고객을 지원 하는 전화 시스템 서비스로 마이그레이션하는 데 도움이 되는 Microsoft 계획입니다.

음성 메일은 주로 Microsoft 기반 마이그레이션입니다. 고객 하위 집합에 대 한 관리 참여 및/또는 투자가 필요할 수도 있습니다. 자동 전화 교환은 관리 기반 마이그레이션입니다. 클라우드 자동 전화 교환 클라우드 서비스에서 기존 ExchUMO 자동 전화 교환 트리를 다시 만들어야 합니다. 타사 pbx로 ExchUMO 기능을 사용 하는 고객은 타사 PBX 시스템을 지원 하지 않으므로 Skype 클라우드 서비스로 마이그레이션되지 않습니다. 타사 지원에 대 한 만료 계획은 [이 블로그에서](https://techcommunity.microsoft.com/t5/Exchange-Team-Blog/New-date-for-discontinuation-of-support-for-Session-Border/ba-p/607853)발표 되었으며,이 배포 모델의 고객은 사용자를 Microsoft의 통합 통신 플랫폼/서비스 중 하나로 마이그레이션하거나 이러한 사용자의 타사 음성 메일 및/또는 자동 전화 교환 솔루션을 획득할 수 있습니다. 클라우드 기반 서비스에서는 팩스 통합이 지원 되지 않습니다. 고객은 타사 솔루션으로 마이그레이션해야 합니다.

## <a name="who-is-affected"></a>영향을 받는 사람은 누구 인가요?

Exchange 통합 메시징 온라인 서비스에서 다음 기능을 사용 하는 고객은 영향을 받습니다.

- 음성 메일 서비스
- 자동 전화 교환 서비스
- 통화 큐 서비스
- 팩스 통합

> [!Note]
> 통합 메시징을 사용 하 여 온-프레미스 Exchange Server를 사용 하는 고객은 영향을 받지 않습니다.

사용자 [환경](#user-experience-impact)에 미치는 영향에 대 한 자세한 내용은 사용자 및 관리자의 경험을 참고 하세요.

## <a name="migration-plan-overview"></a>마이그레이션 계획 개요

Microsoft는 ExchUMO의 기능을 소비 하는 다양 한 고객 배포를 파악 했으며 다음 계획에 따라 고객을 마이그레이션하도록 지원 합니다.

|고객 그룹 |시간 표시 막대  |세부 정보  |
|---------|---------|---------|
|마이그레이션할 준비가 된 고객<br><br>마이그레이션할 기능:<br><ul><li>음성 메일</ul>   |   3 월 2019 일 수 있음  |예제:<ul><li>    간단한 음성 메일 배포 및 사용 현황이 포함 된 고객<li>마이그레이션을 실행 하기 위해 Microsoft에 대해 설정 된 모든 요구 사항이 있는 고객<ul>|
|필수 구성 요소가 포함 된 고객<br><br>마이그레이션할 기능:<br><ul><li>음성 메일<li>자동 전화 교환<li>통화 큐</ul> |  5 월 2019 일 |예제: <br><ul><li>하이브리드 구성이 완료 되지 않음<li>하이브리드 PSTN 번호가 설정 되지 않음</ul>|
|고객 투자 & 관리 참여가 필요한 고객<br><br>마이그레이션할 기능:<ul><li>음성 메일<li>자동 전화 교환<li>통화 큐<li>팩스 통합</ul>| 2020 년 2 월  | 예제: <br><ul><li>ExchUMO 서비스는 타사 PBX에서 사용 됩니다.<li>PSTN 구독자 액세스 요구 사항이 있는 고객<li>SFB의 고객 2010 (지원 되지 않음)<li>팩스 통합</ul> |

## <a name="voicemail-migration-guidelines"></a>음성 메일 마이그레이션 지침

### <a name="get-informed"></a>알림을 받을

[블로그 알림과](https://blogs.technet.microsoft.com/exchange/2019/02/08/retiring-unified-messaging-in-exchange-online/) 이 문서를 숙지 하 여 사용자를 위한 원활한 마이그레이션을 계획 합니다. 전화 시스템 음성 메일 기능에 대 한 자세한 내용은 [비즈니스용 Skype 음성 메일 및 옵션 확인](https://support.office.com/article/check-skype-for-business-voicemail-and-options-2deea7f8-831f-4e85-a0d4-b34da55945a8) 을 참조 하십시오.  

### <a name="establish-a-skype-for-business-hybrid-topology"></a>비즈니스용 Skype 하이브리드 토폴로지 설정

비즈니스용 Skype 하이브리드 토폴로지가 설정 되어 있지 않은 경우에는 음성 메일 사용자를 원활 하 게 마이그레이션하도록 설정 하기 위해이 작업을 수행 해야 합니다. 자세한 내용은 [비즈니스용 Skype 하이브리드 구성을](../../SfbHybrid/hybrid/configure-federation-with-skype-for-business-online.md) 참조 하세요.

> [!Note]
> 음성 메일 서비스 마이그레이션을 위해 사용자를 온라인으로 마이그레이션할 필요는 없습니다. 그러나 온-프레미스 사용자가 전화 시스템 음성 메일 서비스를 활용 하려면 하이브리드 토폴로지를 설정 해야 합니다.

### <a name="plan-your-auto-attendant-migration"></a>자동 전화 교환 마이그레이션 계획

관리자는 언제 든 지 자동 전화 교환을 ExchUMO에서 클라우드 자동 전화 교환으로 마이그레이션할 수 있습니다. 자세한 내용은 [클라우드 자동 전화 교환 설정을](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant) 참조 하십시오.

Microsoft는 고객이 마이그레이션을 위해 고려할 수 있는 추가 자동 전화 교환 기능을 계속 제공 합니다. 관리자는 기능 집합을 평가 하 고 그에 따라 자동 전화 교환 인스턴스를 마이그레이션해야 합니다. 기능 목록 비교에 대 한 자세한 내용은 [ExchUMO 및 Azure 클라우드 기반 서비스 기능 매트릭스](#exchumo-and-azure-cloud-based-services-feature-matrix)를 참조 하십시오.

### <a name="plan-for-your-voicemail-post-migration-validation-and-testing"></a>음성 메일 마이그레이션 후 유효성 검사 및 테스트 계획

음성 메일 마이그레이션은 Microsoft 구동 방식입니다. 필수 구성 요소 하이브리드 토폴로지가 설정 된 경우 관리자는 별도의 작업을 수행 하지 않아도 됩니다. Microsoft는 사용자의 음성 메일 마이그레이션이 중단 되지 않도록 하기 위해 필요한 유효성 검사 및 테스트를 수행 합니다. 관리자는 해당 측면에서 테스트 및 유효성 검사를 수행 하는 것이 좋습니다. 권장 되는 테스트 계획을 보려면 [관리자에 게 제안 되는 테스트 계획 및 마이그레이션 후 유효성 검사](#suggested-test-plan-and-post-migration-validation-for-admins) 를 참조 하세요.

> [!Note]
> Lync Server 2010는 지원 되지 않습니다. 2010 서버를 배포 하는 경우에는 서버 업그레이드를 계획 하거나 사용자를 Microsoft 팀 이나 비즈니스용 Skype Online으로 마이그레이션하는 것을 고려해 야 합니다.  

### <a name="monitor-the-admin-notification-center"></a>관리 알림 센터 모니터링

추가 세부 정보 및 사용자의 마이그레이션과 관련 된 시간 표시 막대와 함께 관리자 알림 센터에서 공지를 시청 하세요. 알림은 마이그레이션 기간 보다 30 일 이상 전송 됩니다.

> [!Note]
> 사용자의 마이그레이션 시간 표시 막대에 대 한 알림을 받았으며 업무상 중요 한 이유로 마이그레이션을 연기 하려는 경우 Microsoft 지원에 문의 하 여이 작업을 수행할 수 있습니다. 만료 날짜 이후로 마이그레이션을 연기할 수 없는 이유는 2020 년 2 월 28 일입니다. 추가 질문이 있는 고객은 계정 팀 또는 Microsoft 지원에 문의 하세요. Microsoft 365 또는 Office 365을 이미 사용 하는 고객은 Microsoft 365 관리 센터를 통해 지원 사례를 제출할 수 있습니다.

### <a name="consider-opting-in-for-a-planned-migration"></a>계획 된 마이그레이션을 위해 옵트인 고려

계획 된 음성 메일 서비스 마이그레이션을 CVM으로 옵트인 할 수 있습니다. 이 문서의 세부 정보를 검토 하기 전에 특히 다음 섹션에서이 문서에 대해 설명 합니다.

- 마이그레이션 단계 (이 섹션)
- ExchUMO 및 Azure 클라우드 기반 서비스 기능 매트릭스
- 사용자 환경에 미치는 영향

관리 되는 마이그레이션을 선택 하면 Microsoft 365 관리 포털 메시지 센터에서 마이그레이션 전 30 일 알림이 수신 되지 않습니다.

계획 된 마이그레이션을 위해 옵트인 하려면 관리자의 전자 메일 주소에서 다음 정보를 사용 하 여 [cvm@microsoft.com](mailto:cvm@microsoft.com) 에 게 전자 메일 요청을 보냅니다.

- 기본 설정 날짜 (화요일): 마이그레이션 물결이 매주 화요일에 실행 됩니다. 12/3/2019이 넘지 않는 화요일에 있는 날짜를 선택 하세요.
 
- 테 넌 트 ID: 32 문자 번호는 0046728c-688a-4472-a38f-098fec60ac6x 형식입니다. Azure AD 아래의 Microsoft 365 관리 포털에서 또는 다음 PowerShell cmdlet을 사용 하 여 테 넌 트 ID를 찾을 수 있습니다. `Get-CsTenant | Select ObjectId`

테 넌 트가 성공적으로 마이그레이션된 경우 전자 메일 확인을 받게 됩니다.

## <a name="auto-attendant-migration-guidelines"></a>자동 전화 교환 마이그레이션 지침

Microsoft 365 및 Office 365 조직 관리자는 Microsoft 클라우드 자동 전화 교환 서비스에서 Exchange UM Online 자동 전화 교환을 다시 만들고 온-프레미스 전화 번호를 해당 사용자에 게 전환 하 여 Exchange UMO 서비스 만료 날짜를 2020 년 2 월 28 일 이전으로 설정 해야 합니다. 새 클라우드 자동 전화 교환을 성공적으로 마이그레이션 및 테스트 하기 위한 권장 지침입니다. 자동 전화 교환 수가 많은 경우 [EXCHANGE UM 자동 전화 교환을](https://github.com/NathanJBennett/ExUMAAMigrationToCloudAA) 사용 하 여 자동 전화 교환의 대량 마이그레이션을 간편 하 게 수행할 수 있습니다.

### <a name="auto-attendant-setup"></a>자동 전화 교환 설정

이전에 새로운 자동 전화 교환 설정을 시작 하 여 지난 몇 분간 문제가 발생 하지 않도록 하 고 클라우드 자동 전화 교환 서비스의 기능 및 경험을 익히는 것이 좋습니다. 하나 이상의 gap 기능이 필요한 자동 전화 교환의 경우에는 간격 기능을 사용 하 여 배포를 준비할 때 자동 전화 교환을 만들고 테스트할 수 있습니다. Gap 기능에 대 한 자세한 내용은 [부록](#appendix)을 참조 하십시오.

1. UMO cmdlet을 사용 하 여 기존의 자동 전화 교환에 대 한 구성을 [가져옵니다](https://docs.microsoft.com/powershell/module/exchange/unified-messaging/get-umautoattendant).  
2. Exchange Online PowerShell에서 [export-UMprompt](https://docs.microsoft.com/powershell/module/exchange/unified-messaging/export-umprompt) cmdlet을 사용 하 여 인사말 미디어 파일 (사용 된 경우)을 내보낸 다음. mp3 형식으로 변환 합니다.
3. [Plan cloud auto](../../SfbHybrid/hybrid/plan-cloud-auto-attendant.md) attendant의 지침을 따르고 Microsoft 팀 관리 센터 또는 Powershell을 사용 하 여 자동 전화 교환을 만들도록 [클라우드 자동 전화 교환을 설정](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant) 합니다.
4. 메뉴 옵션이 변경 된 경우 인사말을 검토 합니다.
5. 이 문서의 [알려진 문제](#known-issues) 섹션에 있는 "자동 전화 교환 통화를 PSTN으로 보내기" 대안을 사용 하 여 응답 그룹에 대 한 전송을 구성 합니다.  
6. 새 자동 전화 교환을 내부적으로 호출 하거나 테스트 전화 번호를 할당 하 여 테스트 합니다.  

### <a name="cutover"></a>단독형

1. Exchange UMO 자동 전화 교환에서 새 자동 전화 교환으로 전화 번호를 전환 합니다.
2. 대화 상대 개체의 SIP URI를 자원 계정으로 이동 합니다.
3. 새로 할당 된 전화 번호를 사용 하 여 자동 전화 교환을 테스트 하 고 유효성을 검사 합니다.

## <a name="appendix"></a>부록

### <a name="exchumo-and-azure-cloud-based-services-feature-matrix"></a>ExchUMO 및 Azure 클라우드 기반 서비스 기능 매트릭스

| 서비스 | 기능 수준 | 기능 | 참고  | 클라우드 VM/AA  | ExUMO |
|---------|-------|--------|----|--------|------|
| V  | 서비스 기능| 타사 PBX 지원    | Exchange UM Online에서 SIP notify 메시지를 사용 하 여 MWI (메시지 대기 표시기)와 같은 타사 PBX에 제공 되는 모든 기능 포함 | Kn   | 피지    |
| V | 서비스 기능  | 비즈니스용 Skype 서버 지원   |  | 피지 | 피지    |
| V | 서비스 기능 | Microsoft 팀 지원|  | 피지 | Kn    |
| V | 서비스 기능 | eDiscovery 및 보류  | 보안 및 규정 준수  | 피지 | 피지    |
| V | 서비스 기능 | Exchange 규칙 지원 | 보안 및 규정 준수  | 피지 | 피지    |
| V | 사용자 기능 | PSTN 전화 접속 액세스  | 구독자 액세스  | Kn | 피지    |
| V | 사용자 기능 | 대리인  | 부재 중 전화 전자 메일  | Kn | 피지    |
| V | 사용자 기능 | PSTN Outlook Voice Access   | 구독자 액세스  | Kn | 피지    |
| V | 사용자 기능 | 인증 된 끝점을 사용 하 여 전화 접속 | 음성 메시지를 듣고 음성을 음성으로 설정 하기 위해 음성 메일 서비스 호출| 피지 | 피지    |
| V | 사용자 기능 | 음성 메일을 사용 하지 않도록 설정할 사용자 설정   |  | 피지 | 피지    |
| V | 사용자 기능 | 개인 인사말을 변경 하기 위한 사용자 설정  |  | 피지 | 피지    |
| V | 사용자 기능 | OOF 인사말을 만드는 사용자 설정  |  | 피지 | 피지    |
| V | 사용자 기능 | 기본 언어를 변경 하기 위한 사용자 설정  |  | 피지 | 피지    |
| V | 사용자 기능 | 기본 인사말을 TTS로 덮어쓰도록 사용자 설정  |  | 피지 | Kn    |
| V | 사용자 기능 | 개인 인사말 녹음 (인증 된 장치) |  | 피지 | 피지    |
| V | 사용자 기능 | 녹음 개인 인사말 (PSTN)-전화에서 재생 |  | Kn | 피지    |
| V | 사용자 기능 | 기록을 사용 하지 않도록 설정할 수 있는 사용자 설정 |  | Kn | 피지    |
| V | 사용자 기능 | 기록  |  | 피지 | 피지    |
| V | 사용자 기능 | SIP notify 메시지를 사용한 MWI (메시지 대기 표시기) |  | Kn | 피지    |
| V | 사용자 기능 | Outlook의 MP3 오디오 파일 형식    |  | 피지 | 피지    |
| V | 사용자 기능 | 가변 속도 재생 컨트롤 |  | 피지 | 피지    |
| V | 사용자 기능 | 음성 메일 전달  | 다른 사용자에 게 받은 음성 메일 전달 | 피지 | 피지    |
| V | 사용자 기능 | 사용자 그룹에 음성 메시지 보내기  |음성 메일 브로드캐스트   | Kn | 피지   |
| V | 사용자 기능 | SMS를 사용한 음성 메일 알림    | 사용자에 게 새 음성 메일이 있을 때 SMS 수신 가능    | Kn | 피지    |
| V | 사용자 기능 | 지원 되는 인사말 언어 | 세부 정보: https://docs.microsoft.com/microsoftteams/what-are-phone-system-auto-attendants | 피지 | 피지    |
| V | 사용자 기능 | 전화 응답 규칙 |  | 피지 | 피지    |
| V | 사용자 기능 | 전화에서 재생 (PSTN)-재생 메시지 | 음성 메시지를 들으려면 내 셀에 전화 걸기  | Kn | 피지    |
| V | 사용자 기능 | 전화에서 재생 (인증)-재생 메시지 | 인증 된 장치에서 전화 걸기  | 피지 | 피지    |
| V | 사용자 기능 | 여러 사용자 간의 공유 사서함 |  | 피지 | 피지    |
| V | 발신자 기능  | 발신자 환경-보호 된 음성 메일 | 발신자는 기록 된 메시지를 보호 된 것으로 표시 하는 옵션을 선택할 수 있습니다.| Kn | 피지    |
| V | 발신자 기능  | 발신자 환경-개인 음성 메일 | 발신자는 기록 된 메시지를 비공개로 표시 하는 옵션을 선택할 수 있습니다.  | Kn | 피지    |
| V | 발신자 기능  | 소음 감지   |  | Kn | 피지    |
| V | 테 넌 트-관리 기능 | 서버 수준의 보호 된 음성 메일    | 테 넌 트-관리자는 들어오는 음성 메일을 보호 된 것으로 표시 하도록 서비스 수준 규칙을 구성할 수 있습니다. | 피지 | 피지    |
| V | 테 넌 트-관리 기능 | 녹음 기간 변경 시간 제한  |     | 피지 | 피지    |
| V | 테 넌 트-관리 기능 | 침묵 검색 시간 제한 변경    |  | 해당 없음    | 피지    |
| V | 테 넌 트-관리 기능 | 입력 실패 횟수 변경 | CVM: 하드 코드화 3 | Kn | 피지    |
| V | 테 넌 트-관리 기능 | 기본 언어 변경 |  | 피지 | 피지    |
| V | 테 넌 트-관리 기능 | 기록 사용/사용 안 함 |  | 피지 | 피지    |
| V | 테 넌 트-관리 기능 | 부재 중 전화 알림 사용/사용 안 함 |  | Kn | 피지    |
| V | 테 넌 트-관리 기능 | Microsoft에서 음성 메일 미리 보기 기능 향상 지원    |  | 피지 | 피지    |
| V | 테 넌 트-관리 기능 | 사용 하도록 설정 된 사용자에 대 한 텍스트 메시지 사용자 지정|  | 해당 없음    | 피지    |
| V | 테 넌 트-관리 기능 | 기록 불경 마스크|  | 피지 | Kn    |
| V | 테 넌 트-관리 기능 | 음성 메일 정책    |   | 피지 | 피지    |
| V | 테 넌 트-관리 기능 | 웹 포털 관리   |  | CY19   | 피지    |
| V | 테 넌 트-관리 기능 | PowerShell   |  | 피지 | 피지    |
| UM | 사용자 기능 | 비즈니스용 Skype 인증 전화에서 MWI (메시지 대기 표시기)   |전화 파트너가 제공할 수 있음  | 아니요 | 예    |
| A | 서비스 기능 | AA 지원 타사 PBX    |  | Kn | 피지    |
| A | 서비스 기능 | 비즈니스용 Skype 서버 지원   |  | 피지 | 피지    |
| A | 서비스 기능 | Microsoft 팀 지원|  | 피지 | Kn    |
| A | 서비스 기능 | 이름으로 전화 걸기, DTMF 입력    |  | 피지 | 피지    |
| A | 서비스 기능 | 이름으로 전화 걸기, 음성 입력  |  | 피지 | 피지    |
| A | 서비스 기능 | 다국어 지원 | 언어 세부 정보: https://docs.microsoft.com/microsoftteams/what-are-phone-system-auto-attendants | 피지 | 피지    |
| A | 서비스 기능 | 교환원, CQ 또는 사용자에 게 전송 |  | 피지 | 피지    |
| A | 서비스 기능 | 내부 PSTN 번호로 전송 (RNL 않음)  |  | 피지 | 피지    |
| A | 서비스 기능 | 외부로 PSTN 번호로 전송  |  | 아래의 알려진 문제 확인 섹션 | 피지    |
| A | 서비스 기능 | 업무 시간 |  | 피지 | 피지    |
| A | 서비스 기능 | 메뉴 옵션 | IVR 메뉴 옵션  | 피지 | 피지    |
| A | 서비스 기능 | AA에 클라우드 PSTN 번호 할당 |  | 피지 | Kn    |
| A | 서비스 기능 | AA에 온-프레미스 PSTN 번호 할당  |  | 피지 | 피지    |
| A | 서비스 기능 | 사용자 선택  | 발신자가 조직 사용자의 사용자 지정 목록에 도달 하도록 설정| 피지 | 피지    |
| A | 서비스 기능 | 근무 시간 및 휴일 처리  |  | 피지 | 피지    |
| A | 서비스 기능 | 텍스트 음성으로 사용자 지정 인사말 사용  |  | 피지 | 피지    |
| A | 서비스 기능 | 내선 통화   | 내선 번호를 사용 하 여 사용자에 게 연결  | 피지   | 피지    |
| A | 서비스 기능 | AA 발신자가 메시지를 남길 사서함    |  | 피지   | 피지    |
| A | 서비스 기능 | AA에 대 한 여러 PSTN 번호 할당|  | 피지 | 피지    |
| A | 테 넌 트-관리 기능 | 웹 포털 관리   |  | 피지 | Kn    |
| A | 테 넌 트-관리 기능 | PowerShell cmdlet  |  | 피지 | 피지    |
| 팩스| 서비스 기능 | 팩스 통합|  | Kn | 피지    |

### <a name="suggested-test-plan-and-post-migration-validation-for-admins"></a>관리자에 게 제안 되는 테스트 계획 및 마이그레이션 후 유효성 검사

사용자가 클라우드 음성 메일로 마이그레이션 되었는지 확인 하려면 음성 메일을 사용자에 게 유지 하 고 Outlook에서 메시지 본문을 확인 합니다. 클라우드 음성 메일 메시지에는 다음과 같은 바닥글이 포함 됩니다.

"기록을 사용해 주셔서 감사 합니다. 위의 대화 내용이 표시 되지 않으면 오디오 품질이 기록을까지 명확 하지 않아 발생 한 것입니다. "

사용자가 마이그레이션된 후에 음성 메일 기능을 테스트 하는 경우 다음 시나리오를 고려해 야 합니다.

- 앱 및 IP 전화와 같은 조직의 모든 끝점 유형에 서 음성 메일 액세스의 유효성을 검사 합니다.
- 샘플 사용자와 함께 구성 된 개인 설정 인사말이 발신자에 게 재생 되는지 확인 합니다.
- 조직에 사용자에 대 한 기록을 사용 하지 않도록 설정 하는 법률 또는 준수 요구 사항이 있는 경우 마이그레이션 후 사용 하지 않도록 설정 해야 합니다. 자세한 내용은 [Cloud 음성 메일 설정을](/microsoftteams/set-up-phone-system-voicemail)참조 하십시오.
- 이전에 Exchange VM 정책 및 규칙을 구성한 경우에는 해당 정책이 효과적 인지 확인 합니다.
- 사용자 설정을 변경 하기 위한 클라우드 음성 메일 서비스 PowerShell cmdlet을 숙지 합니다.  

### <a name="user-experience-impact"></a>사용자 환경에 미치는 영향

다음은 최종 사용자 음성 메일 마이그레이션 환경에 대 한 개요입니다.


|환경  |사용자 환경 변경|
|---------|---------|
|전자 메일 알림 | 변경되지 않음<br>사용자에 게 음성 메일 계정 활성화/마이그레이션에 대해 알리는 전자 메일이 전송 되지 않습니다. |
|이전 메시지에 대 한 액세스 | 변경되지 않음<br>사용자는 지원 되는 모든 끝점에서 이전 음성 메일 메시지에 액세스할 수 있습니다. |
|Outlook, SFB 앱에서 VM 받기| 변경되지 않음<br>사용자가 계속 해 서 지원 되는 모든 끝점에서 음성 메일 메시지를 받습니다. |
|기록 | 방식<br>CVM 기록의 정확도는 ExchUMO 보다 훨씬 더 높고 지원 되는 언어입니다. |
|사용자 설정 | 새로운 환경<br>사용자가 USP (사용자 설정 포털)에서 기본 설정을 변경할 수 있습니다. 사용자는 음성 메일 전자 메일의 하이퍼링크 또는 해당 SFB 클라이언트의 사용자 설정 단추에서 USP에 액세스할 수 있습니다. https://aka.ms/vmsettings.
 |기능| 자세한 내용은 기능 집합 비교를 참조 하세요. |
|VM 메시지에 대 한 Outlook 규칙 | 변경되지 않음<br>이전에 만든 규칙은 마이그레이션 후 CVM 메시지에 적용 됩니다.
 |

### <a name="user-management-and-provisioning-in-cvm"></a>CVM의 사용자 관리 및 구축

새 비즈니스용 Skype 사용자는 만들 때 클라우드 음성 메일에 대해 자동으로 프로 비전 됩니다. 새 음성 메일 사용자를 프로 비전 하기 위해 추가 관리자 작업 또는 라이선스가 필요 하지는 않습니다. 기존 및 새 사용자에 대 한 정책 관리에 대 한 자세한 내용은 [Cloud 음성 메일 설정을](/microsoftteams/set-up-phone-system-voicemail) 참조 하십시오.

### <a name="admin-auto-attendant-management-experience"></a>관리 자동 전화 교환 관리 환경

자동 전화 교환에 대 한 자세한 내용은 [Set up a Cloud auto attendant](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant)를 참조 하십시오.

### <a name="known-issues"></a>알려진 문제

#### <a name="greeting-inconsistencies"></a>인사말 불일치

모든 사용자가 클라우드 음성 메일로 마이그레이션된 후에도 서비스를 완전히 사용 하지 않으면 테 넌 트에 대 한 구독자 액세스를 계속할 수 있습니다. 사용자 혼란을 방지 하 고 일관성 없는 환경을 피하려면 마이그레이션 후에 인사말이 변경 된 후에 구독자 액세스를 사용 하지 않도록 설정 합니다. 이렇게 하려면을 사용 하 여 각 구독자 액세스 회선에 대 한 EXUM 연락처를 제거 `Get-CsExUmContact | ?{$_.IsSubscriberAccess -eq $true} | Remove-CsExUmContact` 합니다.

#### <a name="auto-attendant-call-transfer-to-pstn"></a>PSTN으로의 자동 전화 교환 통화 전송

비즈니스용 skype 서버 또는 RGS (응답 그룹 서비스)를 통해 외부 PSTN 전화 번호로 자동 전화 교환 통화를 전송 하려면 통화 전달을 PSTN 전화 번호 또는 RGS 전화 번호로 설정 하 여 온-프레미스 사용자를 새로 만듭니다. Enterprise Voice에 대해 사용자를 사용 하도록 설정 하 고 올바르게 구성 해야 하며 음성 정책이 할당 되어 있어야 합니다.

#### <a name="shared-mailbox-is-still-accessible"></a>공유 사서함에 계속 액세스할 수 있음

Exchange UM Online을 사용 하 여 구성 된 공유 사서함은 계속 해 서 CVM으로 마이그레이션 후 메시지를 수신 하 고 Outlook을 통해 사용자에 게 액세스 가능 합니다. 그러나 이러한 사서함의 인사말 메시지를 변경 하기 위한 액세스는 CVM으로 마이그레이션된 후에는 사용할 수 없습니다. 자동 전화 교환 발신자를 캡처하는 데 사용 되는 공유 사서함이 있는 고객은 자동 전화 교환 및 전화 큐 공유 사서함 기능 (즉, 에타 10 월 2019)을 활용 해야 합니다.
  
#### <a name="username-is-not-using-skype-for-business-banner-displays"></a>"사용자 이름이 비즈니스용 Skype를 사용 하 고 있지 않습니다." 배너 표시

CVM 서비스는 Microsoft 팀 인프라를 기반으로 하며 비즈니스용 Skype 클라이언트를 호출 하면 "Username is 비즈니스용 Skype를 사용 하 고 있지 않습니다." 라는 정보 배너가 클라이언트에 표시 될 수 있습니다. 보다 풍부한 환경을 위해 팀으로 전환 하거나 Skype 모임을 시작 합니다. "
이 배너가 나타나지 않도록 하려면 사용자의 비즈니스용 Skype 클라이언트를 최신 C2R 클라이언트 업데이트로 업데이트 해야 합니다.
  
#### <a name="set-up-voice-mail-takes-you-to-owa"></a>"음성 메일 설정"에서 OWA로 이동

클라이언트에서 **음성 메일 설정을** 클릭 하면 cvm으로 마이그레이션한 후 비즈니스용 Skype 서버 2015/2013 고객에 게 OWA (Office Web Access) 포털 페이지를 계속 사용할 수 있습니다. OWA의 음성 메일 탭에서 모든 설정이 제거 되었으며, 배너가 사용자를 CVM 사용자 설정 포털로 사용 하도록 리디렉션 링크와 함께 표시 됩니다.

#### <a name="changing-greeting-remotely"></a>원격으로 인사말 변경

PSTN 구독자 액세스는 CVM에서 지원 되지 않습니다. 사용자가 원격으로 인사말을 변경 해야 하는 경우에는 "인사말 변경" 메뉴 옵션이 모바일 클라이언트용 음성 메일 IVR 서비스에 추가 되었습니다. 사용자는 모바일 클라이언트 다이얼 패드에서 "1" 키를 누르고 있으면이 서비스를 호출할 수 있습니다.
