---
title: Microsoft 팀 먼저 롤아웃
author: LaszloSomi
ms.author: lsomi
manager: swerth
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: lsomi
localization_priority: Normal
search.appverid: MET150
description: 이 지침을 사용 하 여 Microsoft 팀을 첫 번째 Office 365 작업으로 배포 합니다.
ROBOTS: NOINDEX, NOFOLLOW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 647f6879f7892c1a65599832e48deb67e183fae0
ms.sourcegitcommit: bdafa1f4146e615d325e27a50352f10c0d51ef1a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/01/2020
ms.locfileid: "44472349"
---
# <a name="roll-out-microsoft-teams-first"></a>Microsoft 팀 먼저 롤아웃

Microsoft 팀은 직원 들이 전세계에 있는 직원의 실제 근무 시간에 따라 서로 연결 하 고 공동 작업 하는 데 도움이 될 수 있습니다. 팀 내에서 채팅, 영상 모임, Office 문서 공동 작업을 할 수 있습니다. 회사가 생산성을 유지 하는 데 도움을 줍니다. 소규모 기업, 비 손익 또는 대규모 조직에 관계 없이 다른 Office 앱 이나 서비스를 배포 하기 전에 Office 365 suite의 첫 번째 작업 부하로 팀을 시작할 수 있습니다.

이 문서에서는 "팀 먼저" 접근 방법으로 수행 해야 하는 고려 사항에 대해 설명 합니다.

> [!IMPORTANT]
> 팀은 조직의 첫 번째 클라우드가 배포할 수 있지만 전체 클라우드 배포 전략의 일부로 팀을 배포 해야 합니다.

다른 Office 365 서비스와 팀이 이미 출시 된 경우 다음 작업 부하 (첫 단계 대신)에서 [팀을 배포 하는 방법](How-to-roll-out-teams.md)부터 시작 합니다.

## <a name="start-here"></a>여기에서 시작

먼저 팀을 배포 하려면 최소한 몇 가지 사전 요구 사항이 충족 되어야 합니다. 다음 목록에는 팀을 사용 하도록 설정 하기 전에 조직에 대해 필요한 항목이 표시 됩니다.

1.  도메인 이름으로 구성 된 Office 365 조직

2.  필수 특성이 모두 테 넌 트에서 동기화 되는 Azure Active Directory 연결 (AAD connect) 또는 유사한 클라우드 id 동기화 솔루션  
    AAD 동기화와 동기화 된 특성을 이해 하려면 [AZURE AD Connect 동기화 읽기: 특성을 Azure Active Directory와 동기화](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized) 됨

3.  팀에 할당 된 적절 한 사용자 라이선스  
    팀 라이선스를 이해 하려면 [Microsoft 팀 서비스 설명을](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)참조 하세요.

4.  조직에서 팀에 대해 준비한 네트워크  
    네트워크 준비를 이해 하려면 [팀에 대 한 조직의 네트워크 준비](prepare-network.md)를 읽어 보세요.

5.  Office 365: [office 365 url 및 IP 주소 범위](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)에서 Exchange, Sharepoint, 비즈니스용 OneDrive에 대 한 네트워크 액세스를 허용 합니다.

> [!NOTE]
> 2019 년 9 월 1 일 이후에 만든 테 넌 트를 팀 전용 모드로 프로 비전 합니다.
> 
> [!IMPORTANT]
> 비즈니스용 Skype 서버를 배포 하 고 테 넌 트가 2019 년 9 월 1 일 이후에 프로 비전 된 경우 고객 지원에 문의 하 여 팀에 공존 기능을 사용 하도록 설정 하세요. 사용자에 게 팀 라이선스를 할당 <span class="underline">하기 전에</span> ' 조직 전체 업그레이드 정책 '이 ' 섬 모드 '로 설정 되어 있는지 확인 합니다.

## <a name="migration-starting-points"></a>마이그레이션 시작 지점

시작 지점 및 온-프레미스 비즈니스용 Skype 또는 Lync server에 따라 팀에서 사용할 수 있는 Office 365 및 기능에 대 한 여행입니다. 다음 섹션에서는 위의 사전 요구 사항 외에도 기본적인 기능과 구성 옵션에 대해 자세히 설명 합니다. 이 출발점 시나리오를 다음 항목으로 세분 했습니다.

**테 넌 트 팀 구성**: 테 넌 트 및 사용자 모드는 받는 사람의 동작을 제어 하는 데 사용 됩니다. 이러한 설정은 테 넌 트 수준이 나 조직의 사용자 수준에 할당할 수 있습니다. 자세한 내용은 [비즈니스용 Skype를 사용 하 여](coexistence-chat-calls-presence.md)함께 읽어 보세요.

**팀의 채팅/외부 통신**: 채팅 서비스는 및 조직 내에서 또는 조직 외부의 피어 투 피어 또는 그룹 채팅 대화를 가리킵니다. 외부 통신은 비즈니스용 Skype의 페더레이션이 라고도 합니다.

**팀에서 모임 만들기 및 보기**: 사용자가 언제 든 지 Outlook 팀 추가 기능을 통해 온라인 모임을 만들 수 있으며, 사용자가 사용이 허가 되 면 모든 시나리오에서 PSTN 전화 접속을 사용할 수 있습니다. 사용자의 Exchange 사서함에 있는 비즈니스용 Skype 스토어 일정 정보 온-프레미스 Exchange server는 팀 클라이언트가 사용자의 사서함과 상호 작용할 수 있으려면 Exchange Server 2016 CU3 이상 이상 이어야 합니다. Exchange 사서함 액세스 권한이 없는 경우 팀의 일정 아이콘은 표시 되지 않으며 사용자는 팀 클라이언트에서 모임을 보거나 만들거나 수정할 수 없게 됩니다.

**팀에서 기능 voip/PSTN 통화**: 통화는 Voip (VOICE over IP) 또는 Pstn (공공 교환 전화 네트워크) 일 수 있습니다. VoIP 연결은 팀 클라이언트 간에 기본적으로 발생 하는 반면, 사용자가 외부 전화 번호로 전화를 걸 때 PSTN 연결이 발생 합니다.  

팀은 두 가지 유형의 PSTN 연결을 지원 합니다. Microsoft는 microsoft가 사용자의 전화 번호를 포함 하는 전화 통신 인프라를 제공 하는 경우 또는 팀 사용자를 위해 SBC (세션 경계 컨트롤러)를 통해 고객이 전화 접속 연결을 제공 하는 직접 라우팅 구성을 제공할 수 있습니다.  
자세한 내용은 [사용자에 게 적합 한 통화 요금제](calling-plan-landing-page.md) 와 [전화 시스템 직접 라우팅을](direct-routing-landing-page.md)참고 하세요.

팀 **에서 팀과 채널 공동 작업**: 팀에서 팀은 작업, 프로젝트 또는 일반적인 관심사에 대해 함께 제공 되는 사용자 그룹입니다. 팀은 채널으로 구성 됩니다. 각 채널은 "팀 이벤트", 부서 이름 등의 주제를 중심으로 작성 되거나 재미 있습니다. 채널은 모임을 개최 하 고 대화를 하며 파일 작업을 함께 수행 하는 위치입니다. 공동 작업 중

**비즈니스용 onedrive (P2P 파일 공유) 팀의**경우 팀 사용자는 비즈니스용 Onedrive 또는 Citrix 파일, DropBox, Box, Google Drive와 같은 기타 P2P 공유 파일 프로그램을 사용 하 여 파일을 피어 투 피어에 공유할 수 있습니다. 비즈니스용 OneDrive의 경우 사용자에 게 SharePoint Online 라이선스가 할당 되어 있어야 합니다.

**응용 프로그램 플랫폼**: 앱은 조직의 다양 한 도구를 제공 하 여 팀을 최대한 활용할 수 있습니다. 이러한 앱은 Microsoft에서 제공 하는 제 3 자, 메시징 확장, 커넥터, 인공 지능 기능을 기반으로 하거나 조직의 개발자가 만듭니다.

**보안 및 규정 준수 기능:** 팀에는 보존 정책, DLP (데이터 손실 방지), eDiscovery 및 채널에 대 한 법적 고 지 사항, 채팅 및 파일, 감사 로그 검색을 비롯 하 여 규정 준수 영역에 도움이 되는 다양 한 정보가 있습니다. 자세한 내용은 [Microsoft 팀의 보안 및 규정 준수](security-compliance-overview.md)를 참고 하세요.  

> [!NOTE]
> 이동 eDiscovery 기능에는 E5 라이선스가 필요 합니다.

[라이선스 옵션을 비교](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)합니다.

[Exchange 및 Microsoft 팀이 어떻게 상호 작용](exchange-teams-interact.md) 하 여 시나리오에서 사용할 수 있는 규정 준수 기능에 대해 알아보세요.

## <a name="organizations-span-classunderlinewithoutspan-skype-for-business-or-lync-server"></a>비즈니스용 Skype 또는 Lync server가 **<span class="underline">없는</span>** 조직

이 시작 단계에서는 조직이 비즈니스용 Skype 또는 Lync server를 사용 하지 않는 것으로 가정 하 고 현재 그리고 팀이 Office 365의 첫 번째 응용 프로그램이 됩니다. 다음 표에서는 핵심 서비스에 대 한 팀의 상위 수준 구성과 최종 사용자 기능에 대해 설명 합니다.

<table>
<thead>
<tr class="header">
<th>항목</th>
<th>상속자</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>테 넌 트 팀 구성</td>
<td>팀 전용 모드, 모든 채팅 및 통화 기능은 팀 에서만 가능 합니다.</td>
</tr>
<tr class="even">
<td>팀에서 채팅/외부 통신</td>
<td><p>내부 (Office에서 365 조직 내) 및 팀에서 수행할 수 있는 외부 채팅 통신</p>
<p><em>참고: DNS 항목은 외부 액세스용으로 구성 해야 합니다. 비즈니스용 skype for 온-프레미스 또는 Office 365에서 Lync 및 비즈니스용 Skype 환경과 페더레이션이 허용 되지 않는 경우에도 비즈니스용 skype DNS 레코드가 필요 합니다.<br />
<a href="https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records">Office 365의 외부 도메인 이름 시스템 레코드</a></em></p></td>
</tr>
<tr class="odd">
<td><em>팀에서 모임 만들기 및 보기</em></td>
<td><p><em>Outlook 추가 기능을 통해 모임을 만들 수 있습니다.</em></p>
<p><em>PSTN 전화 접속 및 전화 접속 기능은 오디오 회의 라이선스를 통해 사용할 수 있습니다.<br />
참고: 팀 일정 액세스에는 Exchange 하이브리드이 설정 된 Exchange 2016 CU3 이상 + 온-프레미스를 배포 해야 합니다. 하이브리드 <a href="https://docs.microsoft.com/exchange/hybrid-deployment/deploy-hybrid">구성 마법사를 사용 하 여 하이브리드 배포 만들기</a><br />
Exchange 하이브리드 구성 외에 Exchange OAuth 인증 설정: <a href="https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help">exchange 및 Exchange Online 조 직 간의 oauth 인증 구성</a></em></p></td>
</tr>
<tr class="even">
<td>통화 기능<br />
팀의 VoIP/PSTN</td>
<td><p>테 넌 트를 내부 및 외부적으로 VoIP를 사용할 수 있습니다.</p>
<p>Microsoft 전화 시스템을 통해 PSTN 서비스를 구성 하 고 Microsoft 호출 계획 또는 직접 라우팅을 추가할 수 있습니다.</p></td>
</tr>
<tr class="odd">
<td>팀에서 팀 및 채널 공동 작업</td>
<td><p>규정 준수 기능을 비롯 한 모든 환경을 위해 사용자에 게 SharePoint Online 라이선스를 할당 해야 합니다.</p>
<p>기존 온-프레미스 SharePoint 사이트의 마이그레이션은 필요 하지 않습니다.</p></td>
</tr>
<tr class="even">
<td>비즈니스용 OneDrive (P2P 파일 공유)</td>
<td>비즈니스용 OneDrive에는 사용자가 SharePoint Online 라이선스를 할당 해야 합니다. 이 라이선스 없이 피어 투 피어 파일 공유를 사용할 수 없습니다.</td>
</tr>
<tr class="odd">
<td>응용 프로그램 플랫폼</td>
<td>사용자는 회사 정책에 따라 사용할 수 있도록 지정 된 앱을 사용할 수 있습니다.<br />
자세한 정보: <a href="https://docs.microsoft.com/microsoftteams/admin-settings">팀의 앱에 대 한 관리자 설정</a></td>
</tr>
<tr class="even">
<td>보안 및 규정 준수 기능</td>
<td><ul>
<li><p>보존 정책을 사용할 수 있습니다.</p></li>
<li><p>채널 메시지의 정책 준수에 대 한 eDiscovery 및 법률 보류가 지원 됩니다.</p></li>
<li><p>데이터 손실 방지 정책 (DLP)을 사용할 수 있습니다.</p></li>
</ul>
<p>Exchange Online과 함께 사용할 수 있는 모든 기능 집합 Exchange 온-프레미스에서는 이러한 기능 대부분을 지원 하며 Exchange와 팀이 전체 목록에 대해 <a href="https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact">상호 작용 하는 방법</a> 에 대해 알아봅니다.</p></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-without-skype-for-business-or-lync-server"></a>비즈니스용 Skype 또는 Lync Server를 사용 하지 않는 조직의 사용 단계

1.  위의 시작 위치 섹션에 자세히 설명 된 필수 조건을 충족 합니다.

2.  테 넌 트만 팀 전용 모드로 전환 (기존 테 넌 트에만 해당): [공존 및 업그레이드 설정을 설정](setting-your-coexistence-and-upgrade-settings.md)합니다.

3.  회사의 비즈니스/회사 정책에 따라 테 넌 트를 구성 합니다. [조직에 대 한 Microsoft 팀 설정을 관리](enable-features-office-365.md)합니다.

4.  팀 클라이언트를 사용자에 게 배포: [팀 용 클라이언트 가져오기](get-clients.md)

5.  채택을 프로그램 구동  
    [Microsoft 팀 채택](adopt-microsoft-teams-landing-page.md)
    
    [Microsoft 팀 채택 빠른 시작 검사 목록](teams-adoption-quick-start-checklist.md)

6.  다른 작업을 Office 365으로 이동 하기 위해 계획 시작

## <a name="organizations-span-classunderlinewithspan-skype-for-business-or-lync-server"></a>비즈니스용 Skype 또는 Lync server **<span class="underline">를 사용 하는</span>** 조직

이 시작 단계에서는 조직에서 비즈니스용 Skype 2019 또는 2015 + 또는 Lync 2013 + server 온-프레미스를 이용 한다고 가정 합니다. 지금까지 온-프레미스 서버에서 팀으로 마이그레이션하는 조직에 대 한 광범위 한 지침이 있으며, 이러한 시나리오를 따라야 합니다. 이 지침은 팀이 Office 365에서 사용 하는 첫 번째 응용 프로그램에 해당 하는 시나리오와 관련이 있습니다. 다음 표에서는 핵심 서비스에 대 한 팀의 상위 수준 구성과 최종 사용자 기능에 대해 설명 합니다.

<table>
<thead>
<tr class="header">
<th>항목</th>
<th>상속자</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>테 넌 트 팀 구성</td>
<td>아일랜드 모드</td>
</tr>
<tr class="even">
<td>팀에서 채팅/외부 통신</td>
<td>내부 테 넌 트에만 해당 됩니다. 비즈니스용 Skype 또는 Lync server 배포를 통해 외부 통신 (페더레이션)이 가능 합니다.</td>
</tr>
<tr class="odd">
<td>팀에서 모임 만들기 및 보기</td>
<td><p>Outlook 추가 기능을 통해 모임을 만들 수 있습니다.</p>
<p>PSTN 전화 접속 및 전화 접속 기능은 오디오 회의 라이선스를 통해 사용할 수 있습니다.<br />
팀 일정 액세스에는 Exchange 하이브리드이 설정 된 Exchange 2016 CU3 이상 + 온-프레미스를 배포 해야 합니다.<br />
<a href="https://docs.microsoft.com/exchange/hybrid-deployment/deploy-hybrid">하이브리드 구성 마법사를 사용 하 여 하이브리드 배포 만들기</a></p></td>
</tr>
<tr class="even">
<td>통화 기능<br />
팀의 VoIP/PSTN</td>
<td><p>테 넌 트에 대 한 VoIP는 내부적으로 사용할 수 있습니다.</p>
<p>사용자가 팀 전용 환경으로 이동할 때까지 PSTN 또는 통화 계획 서비스를 사용할 수 없습니다.</p></td>
</tr>
<tr class="odd">
<td>팀에서 팀 및 채널 공동 작업</td>
<td><p>규정 준수 기능을 비롯 한 모든 환경을 위해 사용자에 게 SharePoint Online 라이선스를 할당 해야 합니다.</p>
<p>기존 온-프레미스 SharePoint 사이트의 마이그레이션은 필요 하지 않습니다.</p></td>
</tr>
<tr class="even">
<td>비즈니스용 OneDrive (P2P 파일 공유)</td>
<td>비즈니스용 OneDrive에는 사용자가 SharePoint Online 라이선스를 할당 해야 합니다. 이 사용권을 사용 하지 않는 경우에는 피어 별 파일 공유를 사용할 수 없습니다.</td>
</tr>
<tr class="odd">
<td>응용 프로그램 플랫폼</td>
<td>사용자는 회사 정책에 따라 사용할 수 있도록 지정 된 앱을 사용할 수 있습니다.<br />
자세한 정보: <a href="https://docs.microsoft.com/microsoftteams/admin-settings">팀의 앱에 대 한 관리자 설정</a></td>
</tr>
<tr class="even">
<td>보안 및 규정 준수 기능</td>
<td><ul>
<li><p>보존 정책을 사용할 수 있습니다.</p></li>
<li><p>채널 메시지의 정책 준수에 대 한 eDiscovery 및 법률 보류가 지원 됩니다.</p></li>
<li><p>데이터 손실 방지 정책 (DLP)을 사용할 수 있습니다.</p></li>
</ul>
<p>Exchange Online에서 사용할 수 있는 전체 기능 집합 Exchange 온-프레미스에서는 이러한 기능을 대부분 지원 합니다.</p>
<p><a href="https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact">Exchange와 Teams의 상호 작용 방법</a></p>
<ul>
<li><p>전체 목록</p></li>
</ul></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-with-skype-for-business-server"></a>비즈니스용 Skype 서버를 사용 하는 조직에 대 한 사용 단계  

1.  위의 시작 위치 섹션에 설명 된 필수 조건을 충족 하세요.

2.  테 넌 트를 아일랜드 모드로 전환 (9/1/2019 후에 테 넌 트를 프로비저닝된 경우 지원 팀에 문의 하 여이 변경 사항 수행)  
    [공존 및 업그레이드 설정 설정](setting-your-coexistence-and-upgrade-settings.md)

3.  회사의 비즈니스/회사 정책에 따라 테 넌 트 구성  
    [조직에서 Microsoft Teams 설정 관리](enable-features-office-365.md)

4.  팀 클라이언트 배포  
    [Teams용 클라이언트 가져오기](get-clients.md)

5.   채택을 프로그램 구동  
    [Microsoft 팀 채택](adopt-microsoft-teams-landing-page.md)<br/>
    [Microsoft 팀 채택 빠른 시작 검사 목록](teams-adoption-quick-start-checklist.md)

6.  다른 작업을 Office 365으로 이동 하기 위해 계획 시작

7.  비즈니스용 Skype 하이브리드 설정 및 비즈니스용 Skype 및 Lync server의 권장 업그레이드 경로 팔 로우  
    [비즈니스용 Skype 온-프레미스에서 팀으로 업그레이드](upgrade-to-teams-execute-skypeforbusinesshybridonprem.md)

## <a name="closing-statement"></a>닫는 문

Microsoft 팀은 조직의 모든 직원, 정보 근로자 및 Firstline worker를 단일 플랫폼에 함께 가져오는 것이 가능 합니다. 지금 바로 [시작할](https://products.office.com/microsoft-teams/group-chat-software) 수 있습니다. [여기](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog)에 있는 모든 최신 공지 사항 및 월간 제품 업데이트를 계속 해 서 연락할 수 있습니다.

또한 전세계의 회사가 현재 COVID-19 상황을 관리 하는 경우 팀을 활용 하는 데 도움이 되는 일련의 콘텐츠를 만들어 조직의 조직에서 최대한의 영향을 받습니다.

  - [COVID-19 중 고객의 약정](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/05/our-commitment-to-customers-during-covid-19/)

  - [2 주 후: 원격 작업에 대해 배운 내용](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/18/making-the-switch-to-remote-work-5-things-weve-learned/)

  - [온라인 모임 및 이벤트 제공](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/delivering-online-meetings-events/)

  - [중소 기업이 Teams와 원격으로 작업할 수 있도록 지원](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/helping-smb-customers-work-remotely-microsoft-teams/)

  - [라이브 이벤트의 디지털 변환: 일선에서 Bob의 1 월 관측값](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/13/digital-transformation-live-events-bob-bejans-observations-frontline/)

  - [Microsoft IT가 직원들의 원격 작업을 가능하게하는 9가지 방법](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/top-9-ways-microsoft-it-enabling-remote-work-employees/)

  - [원격 작업, 보안 유지 — CISOs에 대 한 팁](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/work-remotely-stay-secure-ciso-tips/)

  - [교사와 학생이 원격 학습으로 전환 하도록 도와주는 경우](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/11/helping-teachers-students-switch-remote-learning/)

  - [Microsoft 팀으로 원격 작업 하는 동안 생산성 유지](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/10/staying-productive-while-working-remotely-with-microsoft-teams/)

## <a name="support-services-reference"></a>지원 서비스 참조

팀은 Exchange Online, SharePoint Online, 비즈니스용 OneDrive 및 Microsoft 365 그룹에 의존 하 여 사용자에 게 완전 통합 Office 365 환경을 제공 합니다. 위에서 언급 한 것 처럼 팀은 제한 된 기능으로 이러한 서비스를 완전 하 게 배포 하지 않고 작동 합니다. 팀에 대 한 자세한 내용과 해당 필수 구성 요소를 읽어 보세요. [팀에 오신 것을 환영](teams-overview.md)합니다.

위에 나열 된 각 서비스에 대 한 자세한 내용은 아래 링크를 참조 하세요.

  - Exchange Online은 일정 기능에 사용 되며 팀에 피어 투 피어 메시지를 저장 합니다. 자세한 내용은 [Exchange 및 팀의 상호 작용 방법](exchange-teams-interact.md) 읽기를 참고 하세요.

> [!IMPORTANT]
> Exchange 온-프레미스와 팀 interop를 사용 하는 경우 [exchange 및 Exchange Online 조 직 간의 OAuth 인증 구성](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)에 설명 된 대로 새 Exchange OAuth 인증 프로토콜을 구성 해야 합니다.

  - SharePoint는 채널에서 파일을 공유 하는 데 사용 되는 반면, OneDrive for Business는 1:1 또는 그룹 채팅에서 파일을 공유 하는 데 사용 됩니다. 자세한 내용은 [SharePoint Online 및 비즈니스용 OneDrive에서 Microsoft 팀과 상호 작용 하는 방법을](sharepoint-onedrive-interact.md)읽어 보세요.

  - [Microsoft 365 그룹](office-365-groups.md) 은 팀 및 채널 생성/관리에 사용 됩니다.


## <a name="related-topics"></a>관련 항목

[Microsoft Teams IT 아키텍처 및 전화 통신 솔루션 포스터](teams-architecture-solutions-posters.md#teams-as-part-of-microsoft-365)

[비즈니스용 Skype 서버와 Office 365 간의 하이브리드 연결 플랜](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity)

[팀을 사용 하 여 원격 작업자 지원](support-remote-work-with-teams.md)

[Office 365로 원격 작업](https://aka.ms/remote-work)
