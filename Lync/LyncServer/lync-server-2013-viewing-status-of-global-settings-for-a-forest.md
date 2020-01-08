---
title: 'Lync Server 2013: 포리스트의 전역 설정 상태 보기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View status of global settings for a forest
ms:assetid: 2ab0f2f1-9908-4e6f-aff3-d6b3cc474b6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn747889(v=OCS.15)
ms:contentKeyID: 63969590
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e2215e0514f019e94467a204ae86e604dcc0da61
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984424"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-status-of-global-settings-for-a-forest-in-lync-server-2013"></a>Lync Server 2013에서 포리스트의 전역 설정 상태 보기

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2014-05-20_

관리자는 월간 Lync Server 2013 배포에 대 한 전역 설정을 검토 해야 합니다. 목적은 설정이 유효한 지를 보장 하 고 기준 문서를 업데이트 해야 하는지 여부를 결정 하는 데 도움이 되는 기준 구성 등의 알려진 구성 집합에 대해 구현 된 설정을 검토 하는 것입니다. 전역 설정에 대 한 변경 사항은 새 설정의 문서화가 포함 되어야 하는 변경 제어 프로세스를 통해 구현 되어야 합니다.

검토 해야 하는 전역 설정은 다음 섹션에서 설명 합니다.

<div>

## <a name="check-general-settings"></a>일반 설정 확인

Lync Server 2013의 지원 되는 SIP (세션 초기화 프로토콜) 도메인을 비롯 한 일반 설정을 확인 합니다.

SIP 도메인 정보는 Windows PowerShell 및 **CsSipDomain** cmdlet을 사용 하 여 반환할 수 있습니다. 이 정보를 반환 하려면 `Get-CsSipDomain` Windows PowerShell 명령을 실행 합니다.

CsSipDomain는 승인 된 모든 SIP 도메인에 대해 다음과 유사한 정보를 반환 합니다.

Id 이름 IsDefault

\-------- ---- ---------

fabrikam.com fabrikam.com True

na.fabrikam.com na.fabrikam.com False

IsDefault 속성이 True로 설정 된 경우 해당 도메인은 기본 SIP 도메인입니다. Set-CsSipDomain cmdlet을 사용 하 여 조직의 기본 SIP 도메인을 변경할 수 있습니다. 그러나 기본 SIP 도메인을 삭제 해도 기본 도메인이 없을 수 있습니다. 이전 예제와 같이 fabrikam.com 도메인을 삭제 하려는 경우 먼저 na.fabrikam.com를 기본 도메인으로 구성 해야 합니다.

</div>

<div>

## <a name="check-meeting-settings"></a>모임 설정 확인

모임 설정에는 모임 정책 정의 및 모임에서 익명 사용자의 참여에 대 한 지원이 포함 됩니다.

Windows PowerShell 및 **CsMeetingConfiguration** cmdlet을 사용 하 여 모임 구성 설정을 검색할 수 있습니다. 예를 들어이 명령은 전역 모임 구성 설정에 대 한 정보를 반환 합니다.

CsMeetingConfiguration – 사이트 범위에서 Id "전역" 모임 구성 설정을 구성할 수도 있습니다. 이 때문에 모든 모임 구성 설정에 대 한 정보를 반환 하는 다음 명령을 사용할 수 있습니다.

`Get-CsMeetingConfiguration`

**Get-CsMeetingConfiguration** cmdlet은 다음과 유사한 정보를 반환 합니다.

Id: 전역

PstnCallersBypassLobby: True

EnableAssignedConferenceType: True

디자인: 회사

AssignedConferenceTypeByDefault: True

AdmitAnonymousUsersByDefault: True

다시 목록의 마지막 항목인 **AdmitAnonymousUsersByDefault**는 익명 사용자가 모임에 참가할 수 있도록 허용 하거나 허용 하지 않습니다.

모임 구성 설정을 확인할 때 현재 설정을 기본값과 비교 하는 것이 유용할 수 있습니다. 다음 명령을 실행 하 여 기본 모임 구성 설정을 볼 수 있습니다.

`New-CsMeetingConfiguration -Identity "Global" -InMemory`

이전 명령은 각 속성에 대 한 기본값을 사용 하는 인스턴스인 전역 모임 구성 설정의 메모리 내 전용 인스턴스를 만듭니다. 명령을 실행할 때 실제 모임 구성 설정이 만들어지지 않습니다. 그러나 모든 기본 속성 값은 화면에 표시 됩니다.

</div>

<div>

## <a name="check-edge-servers-and-their-settings"></a>Edge 서버 및 해당 설정 확인

Edge 서버 정보는 Windows PowerShell을 사용 하 여 검색할 수 있습니다. 이 명령은 조직에서 사용 하도록 구성 된 모든 Edge 서버에 대 한 정보를 반환 합니다.

`Get-CsService -EdgeServer`

반환 되는 정보에는 각 Edge 서버의 모든 FQDN 및 포트 설정이 포함 됩니다.

Id: EdgeServer: dc.fabrikam.com

등록자: 등록자: LYNC-SE.fabrikam.com

AccessEdgeInternalSipPort: 5061

AccessEdgeExternalSipPort: 5061

AccessEdgeClientPort: 443

DataPsomServerPort: 8057

DataPsomClientPort: 444

MediaRelayAuthEdgePort: 5062

MediaRelayAuthInternalTurnTcpPort: 443

MediaRelayAuthExternalTurnTcpPort: 445

MediaRelayAuthInternalTurnUdpPort: 3478

MediaRelayAuthExternalTurnUdpPort: 3478

MediaCommunicationPortStart: 5만

MediaComunicationPortCount: 1만

AccessEdgeExternalFqdn: dc.fabrikam.com

DataEdgeExternalFqdn: dc.fabrikam.com

AVEdgeExternalFqdn :

InternalInterfaceFqdn :

ExternalMrasFqdn: dc.fabrikam.com

DependentServiceList: {레지스트라: LYNC-SE.fabrikam.com,

ConferencingServer: LYNC-fabrikam

com, MediationServer: LYNC-SE

fabrikam.com}

ServiceId: fabrikam.com-EdgeServer-2

SiteId: site:: fabrikam.

PoolFqdn: dc.fabrikam.com

버전: 5

역할: EdgeServer

<div>

## <a name="check-federation-settings"></a>페더레이션 설정 확인

페더레이션 설정을 확인 하 고 (예: 구성 되었는지 여부, 대답이 "yes" 이면 FQDN 및 port)를 선택 합니다. 액세스에 지 구성 설정의 전역 컬렉션을 사용 하 여 페더레이션을 사용 하거나 사용 하지 않도록 설정 합니다. 그 외에,이는 페더레이션이 전체 조직에 대해 사용 하도록 설정 되어 있거나 조직 전체에 페더레이션이 사용 되지 않도록 하는 것을 의미 합니다.

Windows PowerShell을 사용 하 여 액세스에 지 구성 설정을 반환할 수 있습니다. 이렇게 하려면 다음 Windows PowerShell 명령을 실행 합니다.

`Get-CsAccessEdgeConfiguration`

그러면 해당 명령은 다음과 같은 데이터를 반환 합니다.

Id: 전역

AllowAnonymousUsers: False

AllowFederatedUsers: False

Allowout 사용자: False

BeClearingHouse: False

Enablediscovery 검색: False

EnableArchivingDisclaimer: False

KeepCrlsUpToDateForPeers: True

MarkSourceVerifiableOnOutgoingMessages: True

OutgoingTlsCountForFederatedPartners: 4

RoutingMethod: UseDnsSrvRouting

**AllowFederatedUsers** 속성을 True로 설정 하면 조직에 페더레이션이 설정 됨을 의미 합니다. ( **AllowFederatedUsers** 를 True로 설정 하는 것은 도메인 분할 시나리오에서 온-프레미스 사용자가 클라우드 사용자의 원활한 통신을 할 수 있다는 의미 이기도 합니다.)

Edge 서버의 FQDN 및 포트 설정을 검색 하려면 이전 작업 (Edge 서버 및 해당 설정)을 참조 하세요.

전역 범위에서 페더레이션을 사용 하면 사용자가 페더레이션 사용자와 통신할 수 있다는 것만 의미 합니다. 개인 사용자가 페더레이션 사용자와 실제로 통신할 수 있는지 여부를 확인 하려면 해당 사용자에 게 할당 된 외부 사용자 액세스 정책을 확인 해야 합니다.

외부 사용자 액세스 정보는 Windows PowerShell을 사용 하 여 반환할 수 있습니다. 예를 들어 다음 명령은 전역 외부 사용자 액세스 정책에 대 한 정보를 반환 합니다.

`Get-CsExternalAccessPolicy -Identity "Global"`

이 명령은 모든 외부 사용자 액세스 정책에 대 한 정보를 반환 합니다.

`Get-CsExternalAccessPolicy`

반환 되는 정보는 다음과 같습니다.

Id: False

설명은

EnableFederationAccess: False

EnablePublicCloudAccess: False

Enablepubliccloudaccess비디오 액세스: False

Enableout연결 액세스: False

**EnableFederationAccess** 가 True로 설정 되 면 지정 된 정책에서 관리 하는 사용자가 페더레이션 사용자와 통신할 수 있습니다.

</div>

</div>

<div>

## <a name="check-archiving-settings"></a>보관 설정 확인

내부 및 페더레이션 통신에 대 한 보관 설정을 확인 합니다. 내부 및 외부 보관에 대 한 설정을 확인 하기 전에 보관을 사용할 수 있는지 확인 해야 합니다.

Windows PowerShell 및 CsArchivingConfiguration cmdlet을 사용 하 여 보관 구성 설정을 확인할 수 있습니다.

`Get-CsArchivingConfiguration -Identity "Global"`

사이트 범위에서 보관 설정을 구성할 수도 있습니다. 모든 보관 설정에 대 한 정보를 반환 하려면 다음 명령을 사용 합니다.

`Get-CsArchivingConfiguration`

Get-CsArchivingConfiguration cmdlet은 다음과 같은 데이터를 반환 합니다.

Id: 전역

EnableArchiving: False

EnablePurging: False

PurgeExportedArchivesOnly: False

BlockOnArchiveFailure: False

KeepArchivingDataForDays: 14

PurgeHourOfDay: 2

ArchiveDuplicateMessages: True

CachePurgingInterval: 24

EnableArchiving 속성이 False로 설정 되어 있는 경우, 즉 통신 세션이 저장 되지 않습니다. 인스턴트 메시징 세션만 보관 하려는 경우 다음과 같은 명령을 사용 하 여 IM 세션 보관을 사용 하도록 설정 합니다.

`Set-CsArchivingConfiguration -Identity "Global" -EnableArchiving "IMOnly"`

회의 세션 및 인스턴트 메시징 세션을 보관 하려면 다음 명령을 사용 합니다.

`Set-CsArchivingConfiguration -Identity "Global" -EnableArchiving "IMOnly"`

현재 보관 설정을 기본 설정과 비교 하려면 다음 Windows PowerShell 명령을 실행 합니다.

`New-CsArchivingConfiguration -Identity "Global" -InMemory`

이 명령은 전역 보관 구성 설정의 메모리 내 전용 인스턴스를 만듭니다. 이는 Lync Server에서 사용 하는 실제 설정 모음이 아닙니다. 그러나 모든 보관 구성 속성에 대 한 기본값을 표시 합니다.

이 명령을 사용 하 여 보관 서버의 FQDN을 반환할 수도 있습니다.

`Get-CsService -ArchivingServer`

보관을 사용할 수 있는지 확인 한 후에는 보관 정책을 확인 하 여 내부 및 외부 통신 세션이 보관 되 고 있는지 확인 합니다.

CsArchivingPolicy cmdlet을 사용 하 여 보관 정책 정보를 검색할 수 있습니다. 예를 들어이 명령은 전역 보관 정책에 대 한 정보를 반환 합니다.

`Get-CsArchivingPolicy -Identity "Global"`

사이트 및 사용자별 범위에서 보관 정책을 구성할 수도 있으므로 모든 보관 정책에 대 한 정보를 반환 하는이 명령을 사용 하는 것도 가능 합니다.

`Get-CsArchivingPolicy`

CsArchivingPolicy에서 받는 정보는 다음과 유사 합니다.

Id: 전역

설명은

ArchiveInternal: False

ArchiveExternal: False

기본적으로 보관 정책에서는 내부 및 외부 보관을 모두 사용할 수 없습니다.

</div>

<div>

## <a name="check-cdr-settings"></a>CDR 설정 확인

피어 투 피어, 회의 및 음성 통화 정보 기록에 대 한 CDR (통화 정보 기록) 설정을 확인 합니다. CDR 설정에 대 한 자세한 내용은 **CsCdrConfiguration** cmdlet을 사용 하 여 반환할 수 있습니다. 예를 들어이 명령은 CDR 구성 설정의 전역 컬렉션에 대 한 정보를 반환 합니다.

`Get-CsCdrConfiguration -Identity "Global"`

또한 사이트 범위에서 CDR를 구성할 수 있으므로 모든 CDR 구성 설정에 대 한 정보를 반환 하는이 명령을 실행 해야 할 수 있습니다.

`Get-CsCdrConfiguration`

CsCdrConfiguration cmdlet은 CDR 구성 설정의 각 컬렉션에 대해 다음과 유사한 정보를 반환 합니다.

Id: 전역

EnableCDR: True

EnablePurging: True

KeepCallDetailForDays: 60

KeepErrorReportForDays: 60

PurgeHourOfDay: 2

CsQoEConfiguration cmdlet을 사용 하 여 체감 품질 모니터링에 대해 유사한 정보가 반환 될 수 있습니다. 예를 들어이 명령은 체감 품질 구성 설정의 전역 컬렉션에 대 한 정보를 반환 합니다.

`Get-QoEConfiguration -Identity "Global"`

해당 정보는 다음과 같습니다.

Id: 전역

ExternalConsumerIssuedCertId :

EnablePurging: True

KeepQoEDataForDays: 60

PurgeHourOfDay: 1

EnableExternalConsumer: False

ExternalConsumerName :

ExternalConsumerURL :

EnableQoE: True

현재 CDR 설정을 기본 CDR 설정과 비교 하려는 경우 다음 명령을 실행 하 여 기본값을 검토할 수 있습니다.

`New-CsCdrConfiguration -Identity "Global" -InMemory`

마찬가지로 체감 품질 모니터링의 기본값은 다음 명령을 사용 하 여 검색할 수 있습니다.

`New-CsQoEConfiguration -Identity "Global" -InMemory`

다음 명령을 실행 하 여 모니터링 서버의 FQDN을 반환할 수도 있습니다.

`Get-CsService -MonitoringServer`

</div>

<div>

## <a name="check-voice-settings"></a>음성 설정 확인

일반적으로 관리자에 게 중요 한 음성 설정은 음성 정책 및 음성 경로에 포함 되어 있습니다. 음성 정책에는 개인 사용자에 게 제공 되는 기능 (예: 통화 전달 또는 전송 기능)을 결정 하는 설정이 포함 되어 있습니다. 음성 경로는 PSTN을 통해 통화가 라우팅되는 방법을 결정 합니다.

음성 정책 정보는 Windows PowerShell을 사용 하 여 검색할 수 있습니다. 예를 들어이 명령은 전역 음성 정책에 대 한 정보를 반환 합니다.

`Get-CsVoicePolicy -Identity "Global"`

이 명령은 조직에서 사용 하도록 구성 된 모든 음성 정책에 대 한 정보를 반환 합니다.

`Get-CsVoicePolicy`

Get-CsVoicePolicy cmdlet에서 반환 되는 정보는 다음과 유사 합니다.

Id: 전역

PstnUsages :{}

설명은

AllowSimulRing: True

AllowCallForwarding 전환: True

AllowPSTNReRouting: True

이름: DefaultPolicy

EnableDelegation: True

EnableTeamCall: True

EnableCallTransfer: True

EnableCallPark: False

EnableMaliciousCallTracing: False

EnableBWPolicyOverride: False

PreventPSTNTollBypass: False

음성 정책의 하위 집합을 반환 하는 쿼리를 만들 수도 있습니다. 예를 들어 다음 명령은 착신 전환을 허용 하는 모든 음성 정책을 반환 합니다.

`Get-CsVoicePolicy | Where-Object {$_.AllowCallForwarding -eq $True}`

이 명령은 착신 전환을 허용 하지 않는 모든 음성 정책을 반환 합니다.

`Get-CsVoicePolicy | Where-Object {$_.AllowCallForwarding -eq $False}`

Windows PowerShell에서 CsVoiceRouting cmdlet을 사용 하 여 음성 경로에 대 한 정보를 반환 합니다.

`Get-CsVoiceRoute`

이 명령은 모든 음성 경로에 대해 다음과 같은 정보를 반환 합니다.

Id: LocalRoute

우선 순위: 0

설명은

번호 패턴: ^ (\\+ 1\[0-9\]{10}) $

PstnUsages :{}

PstnGatewayList :{}

이름: LocalRoute

SuppressCallerId :

AlternateCallerId :

Lync Server에서는 PSTN 사용량이 없으며 PSTN 게이트웨이를 지정 하지 않는 음성 경로를 만들 수 있습니다. 그러나 이러한 두 가지 속성 값이 구성 되지 않은 음성 경로를 통해 전화를 실제로 라우트할 수는 없습니다. 이 때문에 PSTN 사용량이 없는 모든 음성 경로의 id를 반환 하는이 명령을 정기적으로 실행 하는 것이 유용할 수 있습니다.

`Get-CsVoiceRoute | Where-Object {$_.PstnUsages -eq $Null} | Select-Object Identity`

마찬가지로이 명령은 PSTN 게이트웨이를 사용 하도록 구성 되지 않은 모든 음성 경로의 id를 반환 합니다.

`Get-CsVoiceRoute | Where-Object {$_.PstnGatewayList -eq $Null}} | Select-Object Identity`

</div>

<div>

## <a name="check-conferencing-attendant-settings"></a>회의 수행자 설정 확인

PSTN 전화 접속 회의를 위한 회의 수행자 설정을 확인 합니다. 회의 수행자 설정은 **Get-CsDialInConferencingConfiguration** cmdlet을 사용 하 여만 검색할 수 있습니다. 이 설정은 Lync Server 제어판에서 사용할 수 없습니다. 회의 수행자 설정을 보려면 다음과 같이 회의 수행자 설정의 전역 컬렉션을 반환 하는 Windows PowerShell 명령을 사용 합니다.

`Get-CsDialInConferencingConfiguration -Identity "Global"`

회의 수행자 설정은 사이트 범위 에서도 구성할 수 있습니다. 모든 회의 수행자 설정에 대 한 정보를 반환 하려면 대신 다음 명령을 사용 합니다.

`Get-CsDialInConferencingConfiguration`

Get-CsDialInConferencingConfiguration cmdlet은 다음과 같은 데이터를 반환 합니다.

Id: 전역

EntryExitAnnouncementsType : UseNames

EnableNameRecording: True

EntryExitAnnouncementsEnabledByDefault: False

EntryExitAnnouncementsEnabledByDefault가 False로 설정 된 경우에는 회의 알림을 사용할 수 없는 것입니다. 시작 및 종료 알림을 사용 하도록 설정 하려면 다음과 같은 Windows PowerShell 명령을 실행 합니다.

`Set-CsDialInConferencingConfiguration -Identity "Global" -EntryExitAnnouncementsEnabledByDefault $True`

</div>

<div>

## <a name="see-also"></a>참고 항목


[Get-CsSipDomain](https://docs.microsoft.com/powershell/module/skype/Get-CsSipDomain)  
[Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingConfiguration)  
[Get-CsService](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[Get-CsAccessEdgeConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsAccessEdgeConfiguration)  
[Get-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[Get-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsArchivingConfiguration)  
[Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCdrConfiguration)  
[Get-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsQoEConfiguration)  
[Get-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicePolicy)  
[Get-CsVoiceRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsVoiceRoute)  
[Get-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsDialInConferencingConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

