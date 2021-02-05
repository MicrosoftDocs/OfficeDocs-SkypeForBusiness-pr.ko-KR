---
title: 통화 및 모임에 대한 Teams 정책 기반 기록 & 소개
author: cabailey
ms.author: cabailey
manager: laurawi
ms.date: 05/11/2020
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: abybee
localization_priority: Normal
search.appverid: MET150
description: 모임에 대한 Teams 정책 기반 기록에 & 대해 자세히 알아보기
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
ms.openlocfilehash: fe1ef675396d5d858dea9430182d182a87f46beb
ms.sourcegitcommit: ac73536f790f83a61eeb2eb8c6b71662f7bd26fc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2021
ms.locfileid: "50110251"
---
# <a name="introduction-to-teams-policy-based-recording-for-callings--meetings"></a>모임에서 전화를 걸 수 있는 Teams 정책 기반 & 소개

정책 기반 기록을 사용하면 통화 및 온라인 모임을 관련 회사 또는 규정 정책에 따라 후속 처리 및 보존을 위해 자동으로 기록되고 캡처될 때 관리 정책을 사용하여 통화 및 모임에 대해 Microsoft Teams를 채택할 수 있습니다.

Teams는 Teams 통신을 구성, 관리, 기록, 저장 및 분석하기 위한 종단 간 솔루션을 제공하는 데 필요한 플랫폼 기능, 사용자 환경 및 관리 인터페이스를 포함하여 타사 녹음 솔루션의 통합을 지원하도록 향상되었습니다. 향상된 기능으로는 통신 플랫폼 API 및 기록을 위한 이벤트가 포함됩니다. 이 기능은 다음과 같습니다.

- 오디오, 비디오, 화면 공유 및 채팅에 지원되는 모든 엔드포인트와 장치 전반에 걸쳐 원활하고 고품질의 미디어 캡처를 제공합니다.

- Teams 사용자와 지원되는 통화 엔드포인트(Teams, Teams Mobile, 비즈니스용 Skype, PSTN) 간의 상호 작용 캡처 지원

- 기존 Teams 관리 통화 및 모임 도구 및 정책과의 통합을 포함하여 규정 준수 기록을 위한 새로운 관리 정책

Microsoft 365 A3/A5/E3/E5/Business Premium 및 Office 365 A3/A5/E3/E5 사용자에서 규정 준수 기록을 사용하도록 설정될 수 있습니다. 

준수 기록 솔루션 통합 기능도 준수 기록 및 Microsoft Teams 세션의 Ignite 2019에서 [<span class="underline">검토했습니다.</span>](https://myignite.microsoft.com/archives/IG19-VCE40)

## <a name="teams-interaction-recording-overview"></a>Teams 상호 작용 기록 개요

상호 작용 기록 사용 사례는 이미지와 같이 편의성, 기능, 조직 및 법적인 가로채기 등 기록 기능의 네 가지 주요 범주로 효과적으로 구분할 수 있습니다.

![무엇을, 그 이유를 기록하는 상호 작용을 보여주는 스크린샷.](media/recording-taxonomy.png "이미지는 기록 범주를 보여줍니다.")

각 범주에는 기록이 시작되는 방법, 기록되는 항목, 기록이 저장되는 위치, 알림을 누가, 액세스를 제어하는 사용자 및 보존 처리 방법에 대한 다양한 요구 사항이 수반됩니다.

| 유형                   | 편의성(일반 팀 녹화) | Org - 규제(규정 준수 기록) |
| ---------------------- | ------------------ | --------------- |
| 초기자              | 사용자               | 관리자(시스템)  |
| 대상                 | 통화당/모임 | 사용자당        |
| 저장소 소유자          | 사용자               | 규정 준수      |
| 알림이 필요하세요? | 예                | 예             |
| 액세스 소유자           | 사용자               | 규정 준수      |
| 보존 정책이 있나요?      | 선택           | 예             |

Teams는 모임 및 [<span class="underline"></span>](https://docs.microsoft.com/microsoftteams/cloud-recording) 라이브 이벤트를 위한 편리하고 기능적인 기록을 위한 다양한 기능을 제공합니다. 조직 기록은 조직에서 관리 정책을 통해 통화 및 온라인 모임을 관련 회사 또는 규정 정책에 필요한 후속 처리 및 보존을 위해 자동으로 기록되고 캡처될 때 관리 정책을 통해 Teams를 채택할 수 있도록 하는 것입니다. 이 정책의 사용자는 Teams와의 디지털 상호 작용이 기록되고 있지만 기록을 사용하지 않도록 설정할 수 있으며 상호 작용이 완료되면 기록에 액세스할 수 없습니다. 기록은 eDiscovery, 법적 보존 및 기타 회사 보존 사용에 대한 규정 준수 및 법률 담당자가 사용할 수 있는 조직 보관의 일부가 됩니다.

## <a name="example-user-needs"></a>예제 사용자 요구

<table>
<thead>
<tr class="header">
<th><strong>Persona</strong></th>
<th><strong>요구</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>기록된 사용자</td>
<td><ul>
<li><p>녹음/녹화가 진행 중일 때 알림을 습니다.</p></li>
<li><p>정책 및/또는 레코더 오류로 인해 호출 동작이 변경되는 경우 알려야 합니다.</p></li>
</ul></td>
</tr>
<tr class="even">
<td>통신 관리자</td>
<td><ul>
<li><p>Teams 사용자/엔드포인트에 기록 정책을 적용/적용하는 이유와 방법을 이해합니다.</p></li>
<li><p>조직에 대한 Teams 기록 정책을 구성하고 유지 관리합니다.</p></li>
<li><p>Teams 통화 및 모임에서 기록 관련 문제를 모니터링하고 해결합니다.</p></li>
<li><p>사용, 품질 및 안정성에 대한 운영 분석을 통해 내부 규정 준수 담당자를 지원합니다.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td>규정 준수 책임자</td>
<td><ul>
<li><p>적절한 지역 경계에서 규정 준수 의무를 충족하는 데 필요한 방식으로 모든 Teams 통신을 수집합니다.</p></li>
<li><p>통신 관련 메타데이터 또는 상호 작용 콘텐츠를 기반으로 상호 작용을 검색합니다. 일반적인 예는 다음과 같습니다.</p>
<ul>
<li><p><strong>메타데이터</strong> - 참가자, 시간, 방향, 전화 걸기 번호, 원본 번호, 사용자 지정 비즈니스 데이터</p></li>
<li><p><strong>콘텐츠</strong> - 전사, 감정, 멘션, 관련 상호 작용</p></li>
</ul></li>
<li><p>수집되는 상호 작용을 모니터링하는 기능을 포함하여 수집된 통신을 분석하고 상호 작용합니다.</p></li>
<li><p>수집된 통신의 보안을 보장하고 모든 단계에서 변조를 방지합니다.</p></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="solution-architecture-overview"></a>솔루션 아키텍처 개요

규정 준수 기록 솔루션은 다음 다이어그램과 같이 Teams와 통합됩니다.

![팀 사용자 지정 앱 설정을 보여주는 스크린샷](media/hp-compliance-recording-for-teams-calling-and-meetings.jpg "이미지는 Teams 모임 또는 통화를 보내고 수신할 때 흐름을 보여줍니다.")

## <a name="recorder"></a>레코더

규정 준수 기록 솔루션의 핵심 구성 요소는 레코더입니다.
레코더는 [<span class="underline">Microsoft의</span>](https://docs.microsoft.com/graph/cloud-communications-concept-overview) 통신 플랫폼을 활용하고 Microsoft Graph에 애플리케이션으로 등록하는 확장성 있는 Azure 기반 서비스(봇)로 구축됩니다. 레코더는 Teams 호출 및 모임 통신 플랫폼 [<span class="underline">API와</span>](https://docs.microsoft.com/graph/api/resources/communications-api-overview?view=graph-rest-1.0) 직접 상호 작용하고 미디어를 위해 엔드포인트를 제공합니다.

[<span class="underline">봇을</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/tree/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot) 구성하고, 앱 인스턴스를 만들고, 규정 준수 정책을 할당하는 방법을 보여주는 샘플 규정 준수 레코더 애플리케이션을 사용할 수 있습니다. 또한 샘플에는 들어오는 호출 라우팅 [<span class="underline">처리,</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L135-L138)기록 [<span class="underline"></span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Http/Controllers/PlatformCallController.cs#L199-L244) 상태 변경 및 기록되는 사용자 제거와 같은 특정 상호 작용을 기록하기 위한 API 사용에 대한 예제도 [<span class="underline">있습니다.</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L121-L126)
특정 API에 대한 그래프 설명서는 [<span class="underline">updateRecordingStatus</span>](https://docs.microsoft.com/graph/api/call-updaterecordingstatus?view=graph-rest-1.0&tabs=http) 및 [<span class="underline">incomingContext에</span>](https://docs.microsoft.com/graph/api/resources/incomingcontext?view=graph-rest-1.0)대한 여기에서 찾을 수 있습니다.

레코더 서비스의 정확한 구현은 파트너에 따라 다르지만 Teams에서 레코더로의 대기 시간을 줄이기 위해 배포의 고가용성 및 지리적 분포를 달성하기 위해 여러 레코더를 지원하도록 설계되어야 합니다. 또한 레코더 자체는 탄력성 및 중복성에 유의하여 설계될 것으로 예상됩니다.

파트너는 인증을 위한 솔루션을 제출하기 전에 Microsoft Graph 통신 API 및 SDK의 최소 필수 릴리스 버전을 확인하여 규정 준수 기록 통합의 모든 요구 사항이 지원되도록 해야 합니다.

규정 준수 기록 시나리오에 대한 기본 요구 사항은 두 가지입니다.

- Azure에 레코더 봇을 배포해야 합니다.

- Azure의 Windows VM에서 레코더 봇을 실행해야 합니다.

Azure 및 Windows VM 요구 사항은 Teams 봇 구성 요소에만 적용됩니다. 즉, 파트너가 규정 준수 기록에 대한 관련 성능 및 기능 요구 사항을 충족할 수 있는 경우 파트너가 선택한 나머지 플랫폼을 구현할 수 있습니다.

## <a name="compliance-recording-policy-assignment-and-provisioning"></a>규정 준수 기록 정책 할당 및 프로비전

IT 관리자는 규정 준수 기록 정책을 만들고 할당하여 기록할 사용자와 각 사용자에 사용할 레코더를 결정할 수 있습니다. 통신 상호 작용이 수행될 때 이러한 정책의 구성에 따라 기록기에서 대화에 참여할 수 있습니다. 규정 준수 기록 정책은 [<span class="underline">Microsoft PowerShell을</span>](https://docs.microsoft.com/microsoftteams/teams-powershell-overview) 사용하여 관리되고 각 조직의 테넌트, 사용자당 및 보안 그룹 수준에서 적용할 수 있습니다. 모임 정책, 통화 정책 및 [<span class="underline"></span>](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams)그룹 정책에 대한 Microsoft Docs에 대한 자세한 [<span class="underline">정보를 찾을 수 있습니다.</span>](https://docs.microsoft.com/microsoftteams/assign-policies#assign-a-policy-to-a-group) [<span class="underline"></span>](https://docs.microsoft.com/microsoftteams/teams-calling-policy)

1. 테넌트에 애플리케이션 인스턴스를 만들 수 있습니다.

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

2. 규정 준수 기록 정책을 작성합니다.

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

   [<span class="underline">Set-CsTeamsComplianceRecordingPolicy</span>](https://docs.microsoft.com/powershell/module/skype/set-csteamscompliancerecordingpolicy?view=skype-ps)

3. 사용자에게 규정 준수 기록 정책을 할당합니다.

   ```powershell
   PS C:\> Grant-CsTeamsComplianceRecordingPolicy -Identity testuser@contoso.onmicrosoft.com -PolicyName TestComplianceRecordingPolicy
   ```

   [<span class="underline">Grant-CsTeamsComplianceRecordingPolicy</span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamscompliancerecordingpolicy?view=skype-ps)

   ```powershell
   PS C:\> Get-CsOnlineUser testuser@contoso.onmicrosoft.com | select SipAddress, TenantId, TeamsComplianceRecordingPolicy | fl

   UserPrincipalName              : testuser@contoso.onmicrosoft.com
   TenantId                       : 5b943d7c-5e14-474b-8237-5022eb8e0dc9
   TeamsComplianceRecordingPolicy : TestComplianceRecordingPolicy
   ```

## <a name="user-experiences"></a>사용자 환경

알림에 대한 지원은 Teams 클라이언트 환경을 사용하여 활성화됩니다. 환경은 시각적 또는 오디오일 수 있습니다.

**Teams 클라이언트 - 시각적 알림**
- 데스크톱/웹
- 모바일(iOS/Android)
- Teams 휴대폰
- Teams 회의실

**기타 엔드포인트 - 오디오 알림**
- SIP 휴대폰
- 비즈니스용 Skype
- 오디오 회의
- PSTN 호출자

## <a name="compliance-recording-for-teams-certification-programs"></a>Teams 인증 프로그램에 대한 규정 준수 기록

Microsoft는 파트너가 CCaaS 솔루션을 개발하고 Teams와 통합할 수 있는 공개적으로 사용 가능한 API를 게시하는 것 외에도 Microsoft Teams 인증 프로그램에 대한 규정 준수 기록을 개발하여 각 참여 파트너 솔루션이 Microsoft 솔루션에서 기대하는 품질, 호환성 및 안정성을 제공하도록 테스트 및 확인되었습니다.  

다음 파트너는 Microsoft Teams에 대한 솔루션을 인증했습니다.

|파트너|솔루션 웹 사이트 |
|:--|:--|
|AudioCodes |[https://www.audiocodes.com/solutions-products/voiceai/meetings-and-recording/smarttap-360](https://www.audiocodes.com/solutions-products/voiceai/meetings-and-recording/smarttap-360) |
|더버 |[https://www.dubber.net/call-recording/](https://www.dubber.net/call-recording/) |
|NICE |[https://www.niceactimize.com/compliance/ms-teams-recording.html](https://www.niceactimize.com/compliance/ms-teams-recording.html) |


다음 파트너는 Microsoft Teams에 대한 솔루션을 인증하는 과정에 있습니다.

|파트너|솔루션 웹 사이트 |
|:--|:--|
|ASC 기술 |[https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html](https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html) |
|CallCabinet |[https://www.callcabinet.com/compliance-microsoft-teams-call-recording](https://www.callcabinet.com/compliance-microsoft-teams-call-recording ) |
|Landis Technologies |[https://landistechnologies.com/](https://landistechnologies.com/) |
|Luware |[https://luware.com/en/solution/microsoft-teams-recording/](https://luware.com/en/solution/microsoft-teams-recording/) |
|Numonix |[https://numonix.cloud](https://numonix.cloud)    |
|Oak Innovation |[https://www.oakinnovate.com/call-recording](https://www.oakinnovate.com/call-recording) |
|빨간색 상자 |[https://www.redboxvoice.com/compliance-recording-for-microsoft-teams](https://www.redboxvoice.com/compliance-recording-for-microsoft-teams)  |
|Verint |[https://www.verba.com/solutions/microsoft-teams-recording](https://www.verba.com/solutions/microsoft-teams-recording) |

이 목록은 더 많은 파트너가 참가하고 인증 기준을 충족할 때 업데이트됩니다.

## <a name="next-steps"></a>다음 단계

인증 프로그램에 참여하기를 원하는 공급업체인 경우 다음을 메일로 <a href= "mailto:Teamscategorypartner@microsoft.com">Teamscategorypartner@microsoft.com.</a>
