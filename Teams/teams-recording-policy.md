---
title: 팀에 대 한 소개 정책 기반 기록 & 모임 통화
author: microsoftheidi
ms.author: heidip
manager: serdars
ms.date: 05/11/2020
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: abybee
localization_priority: Normal
search.appverid: MET150
description: 팀 정책 기반 & 모임 통화에 대 한 자세한 정보
f1.keywords:
- CSH
ms.custom:
- Adopt
- seo-marvel-mar2020
ms.collection:
- Teams_ITAdmin_Adopt
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: cc09323e7f0a25f0f7c7083307776ad1a08bf4fb
ms.sourcegitcommit: e0ed3b6478918c4737648e6c27eb01de0b622b0e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "44294053"
---
# <a name="introduction-to-teams-policy-based-recording-for-callings--meetings"></a>팀 소개 정책 기반 & 모임 기록

정책 기반 기록은 Microsoft 팀이 관리 정책을 사용 하 여 stipulate에 전화를 걸고 모임을 하는 조직에 게, 관련 회사 또는 규정 정책에서 요구 하는 후속 처리 및 보존을 위해 통화와 온라인 모임을 자동으로 기록 하 고 캡처할 수 있도록 합니다.

팀 통신을 구성, 관리, 기록, 저장 및 분석 하는 종단 간 솔루션을 제공 하는 데 필요한 플랫폼 기능, 사용자 환경, 관리 인터페이스를 비롯 한 타사 기록 솔루션의 통합을 지원 하도록 성능이 향상 되었습니다. 여기에는 다음을 제공 하는 기록에 대 한 통신 플랫폼 Api 및 이벤트가 포함 됩니다.

- 장치 간의 원활한 고품질 미디어 캡처 및 오디오, 비디오, 화면 공유, 채팅에 대해 지원 되는 모든 끝점

- 팀 사용자 간 상호 작용 캡처 지원 및 지원 되는 호출 끝점 (팀, 팀 모바일, 비즈니스용 Skype, PSTN)

- 기존 팀 관리 통화, 모임 도구 및 정책과의 통합을 포함 하 여 규정 준수 기록에 대 한 새로운 관리 정책

- 별도의 라이선스가 있는 팀 사용자에 대해 사용

준수 기록 [<span class="underline">및 Microsoft 팀 세션</span>](https://myignite.techcommunity.microsoft.com/sessions/83184?source=sessions)의 Ignite 2019 에서도 문제 해결 기록 솔루션 통합 기능을 검토 했습니다.

## <a name="teams-interaction-recording-overview"></a>팀 조작 기록 개요

조작 기록 사용 사례는 이미지에 표시 된 것 처럼 편리한, 함수형, 조직적, 합법적 가로채기의 네 가지 기본 범주로 나눌 수 있습니다.

![상호 작용 기록 및 그 이유를 보여 주는 스크린샷](media/recording-taxonomy.png "이미지에는 기록 범주가 표시 됩니다.")

각 범주는 녹음/녹화를 시작 하는 방법, 기록 되는 내용, 녹음/녹화의 위치, 알림 메시지, 액세스를 제어 하는 사용자, 보존이 처리 되는 방식에 대 한 요구 사항이 서로 다릅니다.

|                        | 방법일        | 작동         | 조직-일반      | 조직 규정 | 합법적 가로채기   |
| ---------------------- | ------------------ | ------------------ | ------------------ | --------------- | ------------------ |
| 사람              | 사용자               | 앱/솔루션       | 관리자 (시스템)     | 관리자 (시스템)  | LEA                |
| 대상                 | 통화 당/회의 | 통화 당/회의 | 통화 당/회의 | 사용자별        | 끝점 단위/ |
| 저장소 소유자          | 사용자               | 내                | 관리자              | 충족      | LEA                |
| 알림이 필요 한가요? | 예                | 예                | 예                | 예             | 아니요                 |
| 액세스 소유자           | 사용자               | 내                | 관리자              | 충족      | LEA                |
| 보존 정책      | 선택           | 예                | 예                | 예             | 예                |

팀은 모임 및 라이브 이벤트에 대 한 [<span class="underline">편리한</span>](https://docs.microsoft.com/microsoftteams/cloud-recording) 기능과 기능 기록을 위한 다양 한 기능을 제공 합니다. 조직 기록은 팀을 채택 하 여 stipulate에 게 전화를 걸고 모임을 하는 조직을 사용 하도록 설정 하는 것을 의미 합니다. 통화와 온라인 모임을 자동으로 기록 하 고 관련 회사 또는 규정 정책에 따라 후속 처리 및 보존을 위해 캡처할 수 있습니다. 이 정책에 속하는 사용자는 팀과의 디지털 조작이 기록 되 고 있음을 알 수 있지만,이는 조작이 완료 된 후에는 녹음/녹화에 액세스할 수 없게 됩니다. 기록은 eDiscovery, 법률 고 지, 기타 기업 보존 용도에 부합 하 고 법적 담당자가 사용할 수 있는 조직 아카이브의 일부가 됩니다.

## <a name="example-user-needs"></a>사용자 요구 예제

<table>
<thead>
<tr class="header">
<th><strong>가</strong></th>
<th><strong>성과</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>기록 된 사용자</td>
<td><ul>
<li><p>기록이 진행 중일 때 알림을 받을 수 있습니다.</p></li>
<li><p>정책 및 기록 오류로 인해 호출 동작이 변경 되는 경우 알림을 받을 수 있습니다.</p></li>
</ul></td>
</tr>
<tr class="even">
<td>통신 관리자</td>
<td><ul>
<li><p>팀 사용자/끝점에 기록 정책을 적용/시행 하는 이유와 방법에 대해 설명 합니다.</p></li>
<li><p>조직의 팀 기록 정책을 구성 하 고 유지 관리 합니다.</p></li>
<li><p>팀 전화 및 모임에서 기록 관련 문제를 모니터링 하 고 해결 합니다.</p></li>
<li><p>사용, 품질 및 안정성에 대 한 운영 분석을 통해 내부 규정 준수 책임자를 지원 합니다.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td>규정 준수 책임자</td>
<td><ul>
<li><p>적절 한 지역 경계에서 준수 의무를 충족 하는 데 필요한 방식으로 모든 팀의 의사 소통을 수집 합니다.</p></li>
<li><p>통신 관련 메타 데이터 또는 상호 작용 콘텐츠를 기준으로 상호 작용을 검색 합니다. 일반적인 예는 다음과 같습니다.</p>
<ul>
<li><p><strong>메타 데이터</strong> - 참가자, 시간, 방향, 전화 번호, 원래 번호, 사용자 지정 비즈니스 데이터</p></li>
<li><p><strong>콘텐츠 – 내용</strong> , 정서, 윗주, 관련 조작</p></li>
</ul></li>
<li><p>수집 되는 의사 소통을 모니터링 하는 기능을 포함 하 여 수집 된 통신을 분석 하 고 상호 작용 합니다.</p></li>
<li><p>수집 된 통신의 보안을 보장 하 고 모든 단계에서 변조를 방지 합니다.</p></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="solution-architecture-overview"></a>솔루션 아키텍처 개요

준수 기록 솔루션은 다음 다이어그램에 표시 된 것 처럼 팀과 통합 됩니다.

![팀 사용자 지정 앱 설정을 보여 주는 스크린샷](media/hp-compliance-recording-for-teams-calling-and-meetings.jpg "이미지는 팀 모임 또는 통화를 보내고 받을 때의 흐름을 보여 줍니다.")

## <a name="recorder"></a>녹음

준수 기록 솔루션의 핵심 구성 요소는 레코더입니다.
레코더는 microsoft [<span class="underline">의 통신 플랫폼을 활용</span>](https://docs.microsoft.com/graph/cloud-communications-concept-overview) 하 고 microsoft Graph를 사용 하 여 응용 프로그램으로 등록 하는 확장 가능한 Azure 기반 서비스 (bot)로 작성 되었습니다. 레코더는 팀 호출 및 모임 [<span class="underline">통신 플랫폼 api</span>](https://docs.microsoft.com/graph/api/resources/communications-api-overview?view=graph-rest-1.0) 와 직접 상호 작용을 제공 하 고 미디어 수집을 위한 끝점을 제공 합니다.

봇을 구성 하 고, 앱 인스턴스를 만들고, 준수 정책을 할당 하는 방법을 보여 주는 [<span class="underline">샘플 준수 기록 응용 프로그램을 사용할 수 있습니다</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/tree/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot) . 또한 샘플에는 [<span class="underline">들어오는 호출</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Http/Controllers/PlatformCallController.cs#L199-L244)   라우팅 처리, [<span class="underline">기록 상태 변경</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L135-L138), 그리고 [<span class="underline">기록 중인 사용자 제거</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L121-L126)와 같은 특정 조작을 기록 하는 API 사용에 대 한 예제가 포함 되어 있습니다.
특정 Api에 대 한 그래프 문서는 [<span class="underline">updateRecordingStatus</span>](https://docs.microsoft.com/graph/api/call-updaterecordingstatus?view=graph-rest-1.0&tabs=http) 및 [<span class="underline">incomingContext</span>](https://docs.microsoft.com/graph/api/resources/incomingcontext?view=graph-rest-1.0)에 대해 찾을 수 있습니다.

레코더 서비스의 정확한 구현은 파트너 마다 다르며, 팀의 대기 시간을 기록으로 줄이기 위해 배포의 고가용성 및 지리적 배포를 달성 하기 위해 여러 레코더를 지원 하도록 디자인 되어야 합니다. 또한, 복원성과 중복성을 고려 하 여 레코더 자체를 디자인 해야 합니다.

파트너는 인증을 위해 솔루션을 제출 하기 전에 microsoft Graph와 Sdk의 최소 필요한 릴리스 버전을 확인 하 여 준수 기록 통합의 모든 요구 사항이 지원 되는지 확인 해야 합니다.

다음과 같은 두 가지 특정 요구 사항은 시나리오의 준수 기록에 대 한 기본입니다.

- 레코더 봇을 Azure에 배포 해야 함

- 레코더 봇이 Azure의 Windows VM에서 실행 되어야 함

Azure 및 Windows VM 요구 사항은 팀 인공 지능 구성 요소에만 적용 되며, 파트너는 해당 사용자가 선택 하는 플랫폼의 나머지를 구현할 수 있으므로, 준수 기록에 대 한 관련 성능 및 기능적 요구 조건을 충족 합니다.

## <a name="compliance-recording-policy-assignment-and-provisioning"></a>준수 기록 정책 과제 및 프로비저닝

IT 관리자는 규정 준수 기록 정책을 만들고 할당 하 여 기록 되는 사용자와 각 사용자에 게 사용할 레코더를 결정할 수 있습니다. 녹음기는 통신 조작이 발생 하는 경우 이러한 정책의 구성을 기반으로 대화에 참여 하도록 자동으로 초대 됩니다. 준수 기록 정책은 [<span class="underline">Microsoft Powershell</span>](https://docs.microsoft.com/microsoftteams/teams-powershell-overview) 을 사용 하 여 관리 되며 각 조직에 대해 테 넌 트 및 사용자별 수준에서 적용 될 수 있습니다. Microsoft 문서에서 [<span class="underline">모임 정책</span>](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams) 및 [<span class="underline">통화 정책</span>](https://docs.microsoft.com/microsoftteams/teams-calling-policy)에 대 한 자세한 내용을 확인할 수 있습니다.

1. 테 넌 트에 응용 프로그램 인스턴스를 만듭니다.

```powershell
PS C:\> New-CsOnlineApplicationInstance -UserPrincipalName cr.instance@contoso.onmicrosoft.com -DisplayName ComplianceRecordingBotInstance -ApplicationId fcc88ff5-a42d-49cf-b3d8-f2e1f609d511

RunspaceId        : 4c13efa6-77bc-42db-b5bf-bdd62cdfc5df
ObjectId          : 5069aae5-c451-4983-9e57-9455ced220b7
TenantId          : 5b943d7c-5e14-474b-8237-5022eb8e0dc9
UserPrincipalName : cr.instance@contoso.onmicrosoft.com
ApplicationId     : fcc88ff5-a42d-49cf-b3d8-f2e1f609d511
DisplayName       : ComplianceRecordingBotInstance
PhoneNumber       :
```

```powershell
PS C:\> Sync-CsOnlineApplicationInstance -ObjectId 5069aae5-c451-4983-9e57-9455ced220b7
```

2. 준수 기록 정책을 만듭니다.

```powershell
PS C:\> New-CsTeamsComplianceRecordingPolicy -Identity TestComplianceRecordingPolicy -Enabled $true -Description "Test policy created by tenant admin"

Identity                        : Global
ComplianceRecordingApplications : {}
Enabled                         : True
WarnUserOnRemoval               : True
Description                     : Test policy created by tenant admin
```

```powershell
PS C:\> Set-CsTeamsComplianceRecordingPolicy -Identity TestComplianceRecordingPolicy `
-ComplianceRecordingApplications @(New-CsTeamsComplianceRecordingApplication -Id 5069aae5-c451-4983-9e57-9455ced220b7 -Parent TestComplianceRecordingPolicy)
```

[<span class="underline">https://docs.microsoft.com/powershell/module/skype/set-csteamscompliancerecordingpolicy?view=skype-ps</span>](https://docs.microsoft.com/powershell/module/skype/set-csteamscompliancerecordingpolicy?view=skype-ps)

3. 사용자에 게 준수 기록 정책을 할당 합니다.

```powershell
PS C:\> Grant-CsTeamsComplianceRecordingPolicy -Identity testuser@contoso.onmicrosoft.com -PolicyName TestComplianceRecordingPolicy
```

[<span class="underline">https://docs.microsoft.com/powershell/module/skype/grant-csteamscompliancerecordingpolicy?view=skype-ps</span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamscompliancerecordingpolicy?view=skype-ps)

```powershell
PS C:\> Get-CsOnlineUser testuser@contoso.onmicrosoft.com | select SipAddress, TenantId, TeamsComplianceRecordingPolicy | fl

UserPrincipalName              : testuser@contoso.onmicrosoft.com
TenantId                       : 5b943d7c-5e14-474b-8237-5022eb8e0dc9
TeamsComplianceRecordingPolicy : TestComplianceRecordingPolicy
```

## <a name="user-experiences"></a>사용자 환경

알림 지원은 팀 클라이언트 환경을 사용 하 여 설정 됩니다. 환경은 visual 또는 audio 일 수 있습니다.

**팀 클라이언트-시각적 알림**
- 데스크톱/웹
- 모바일 (iOS/Android)
- 팀 전화
- 팀 대화방

**기타 끝점-오디오 알림**
- SIP 전화
- 비즈니스용 Skype
- 오디오 회의
- PSTN 발신자

## <a name="compliance-recording-for-teams-certification-programs"></a>팀 인증 프로그램에 대 한 규정 준수 기록

파트너가 팀을 통해 CCaaS 개발 및 통합할 수 있도록 공개적으로 사용할 수 있는 Api를 게시 하는 것 외에, Microsoft 팀에서 각 파트너의 솔루션이 테스트를 수행 하 고 Microsoft 솔루션에서 기대 하는 품질, 호환성 및 안정성을 제공 하도록 확인 하는 것을 고객에 게 제공 하는 인증 프로그램에 대 한 준수 기록을 개발 했습니다.  

다음 파트너는 Microsoft 팀의 솔루션을 인증 하는 과정을 진행 중입니다.  

|Partner|솔루션 웹 사이트 |
|:--|:--|
|ASC 기술 |[https://www.asc.de/english/ASC_Recording_Insights_for_Microsoft_Teams.html](https://www.asc.de/english/ASC_Recording_Insights_for_Microsoft_Teams.html) |
|오디오 코드 |[https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/smarttap-360-recording](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/smarttap-360-recording) |
|CallCabinet |[https://www.callcabinet.com/compliance-microsoft-teams-call-recording](https://www.callcabinet.com/compliance-microsoft-teams-call-recording ) |
|좋지 |[https://www.niceactimize.com/compliance/ms-teams-recording.html](https://www.niceactimize.com/compliance/ms-teams-recording.html) |
|Numonix |[https://numonix.cloud](https://numonix.cloud)    |
|빨간색 상자 |[https://hubs.ly/H0qtN7Q0](https://hubs.ly/H0qtN7Q0)  |
|Verint |[https://www.verba.com/solutions/microsoft-teams-recording](https://www.verba.com/solutions/microsoft-teams-recording) |

이 목록은 더 많은 파트너가 참가 하 고 인증 기준을 충족 하면 업데이트 됩니다.

## <a name="next-steps"></a>다음 단계

인증 프로그램에 참여 하는 공급 업체를 찾고 있다면 메일을 <a href= "mailto:Teamscategorypartner@microsoft.com">Teamscategorypartner@microsoft.com</a> 바랍니다.
