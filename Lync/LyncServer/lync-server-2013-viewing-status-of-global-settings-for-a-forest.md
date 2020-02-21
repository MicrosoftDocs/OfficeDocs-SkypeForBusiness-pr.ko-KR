---
title: 'Lync Server 2013: 포리스트의 전역 설정 상태 보기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View status of global settings for a forest
ms:assetid: 2ab0f2f1-9908-4e6f-aff3-d6b3cc474b6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn747889(v=OCS.15)
ms:contentKeyID: 63969590
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ab574067b05b494601e0dd769003cb01904c52bc
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211106"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-status-of-global-settings-for-a-forest-in-lync-server-2013"></a>Lync Server 2013에서 포리스트의 전역 설정 상태 보기

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2014-05-20_

관리자는 Lync Server 2013 배포에 대 한 전역 설정을 매월 검토 해야 합니다. 이 목표는 알려진 구성 집합 (기준 구성)에 대해 구현 된 설정을 검토 하 여 해당 설정이 유효 하며 기준 문서를 업데이트 해야 하는지 여부를 결정 하는 것입니다. 전역 설정에 대 한 변경 내용은 새 설정의 문서화를 포함 해야 하는 변경 제어 프로세스를 통해 구현 해야 합니다.

검토 해야 하는 전역 설정은 다음 섹션에 설명 되어 있습니다.

<div>

## <a name="check-general-settings"></a>일반 설정 확인

Lync Server 2013에 대해 지원 되는 SIP (Session 착수 프로토콜) 도메인을 비롯 한 일반 설정을 확인 합니다.

SIP 도메인 정보는 Windows PowerShell 및 **new-cssipdomain** cmdlet을 사용 하 여 반환할 수 있습니다. 이 정보를 반환 하려면 `Get-CsSipDomain` Windows PowerShell 명령을 실행 합니다.

New-cssipdomain는 모든 권한 있는 SIP 도메인에 대해 다음과 같은 정보를 반환 합니다.

Id 이름 IsDefault

\-------- ---- ---------

fabrikam.com fabrikam.com True

na.fabrikam.com na.fabrikam.com False

IsDefault 속성이 True로 설정 된 경우 해당 도메인은 기본 SIP 도메인입니다. New-cssipdomain cmdlet을 사용 하 여 조직의 기본 SIP 도메인을 변경할 수 있습니다. 그러나 기본 도메인을 제외 하 고는 기본 SIP 도메인을 삭제 하기만 하면 됩니다. 이전 예제와 같이 fabrikam.com 도메인을 삭제 하려면 먼저 na.fabrikam.com를 기본 도메인으로 구성 해야 합니다.

</div>

<div>

## <a name="check-meeting-settings"></a>모임 설정 확인

모임 설정에는 모임 정책 정의와 회의의 익명 사용자 참여에 대 한 지원이 포함 됩니다.

모임 구성 설정은 Windows PowerShell 및 **get-csmeetingconfiguration** cmdlet을 사용 하 여 검색할 수 있습니다. 예를 들어 다음 명령은 전역 모임 구성 설정에 대 한 정보를 반환 합니다.

Get-csmeetingconfiguration – Id "Global" 모임 구성 설정을 사이트 범위에서 구성할 수도 있습니다. 따라서 모든 모임 구성 설정에 대 한 정보를 반환 하는 다음 명령을 사용할 수 있습니다.

`Get-CsMeetingConfiguration`

**Get-csmeetingconfiguration** cmdlet은 다음과 같은 정보를 반환 합니다.

Id: Global

PstnCallersBypassLobby: True

EnableAssignedConferenceType: True

DesignateAsPresenter: 회사

AssignedConferenceTypeByDefault: True

AdmitAnonymousUsersByDefault: True

다시 말하지만, 목록의 최종 항목 **AdmitAnonymousUsersByDefault**은 익명 사용자가 모임에 참가할 수 있는 기능을 사용 하거나 사용 하지 않도록 설정 합니다.

모임 구성 설정을 확인할 때 현재 설정을 기본값과 비교 하는 것이 유용할 수 있습니다. 다음 명령을 실행 하 여 기본 모임 구성 설정을 볼 수 있습니다.

`New-CsMeetingConfiguration -Identity "Global" -InMemory`

이전 명령은 각 속성의 기본값을 사용 하는 인스턴스인 전체 모임 구성 설정에 대 한 메모리 전용 인스턴스를 만듭니다. 명령을 실행할 때 실제 모임 구성 설정은 만들어지지 않습니다. 그러나 모든 기본 속성 값은 화면에 표시 됩니다.

</div>

<div>

## <a name="check-edge-servers-and-their-settings"></a>에 지 서버 및 설정 확인

에 지 서버 정보는 Windows PowerShell을 사용 하 여 검색할 수 있습니다. 이 명령은 조직에서 사용 하도록 구성 된 모든에 지 서버에 대 한 정보를 반환 합니다.

`Get-CsService -EdgeServer`

반환 되는 정보에는 각에 지 서버에 대 한 모든 FQDN 및 포트 설정이 포함 됩니다.

Identity: EdgeServer: dc.fabrikam.com

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

DependentServiceList: {등록자: LYNC-SE.fabrikam.com,

ConferencingServer:-fabrikam

com, MediationServer: LYNC-SE

fabrikam.com}

ServiceId: fabrikam.com-EdgeServer-2

SiteId: site:fabrikam.

PoolFqdn: dc.fabrikam.com

버전: 5

역할: EdgeServer

<div>

## <a name="check-federation-settings"></a>페더레이션 설정 확인

페더레이션 설정 (예: 구성 여부) 및 FQDN과 포트가 "예" 인 경우의 대답이 있는지 확인 합니다. 액세스에 지 구성 설정의 전역 컬렉션을 사용 하 여 페더레이션을 사용 하도록 설정 하 고 사용 하지 않도록 설정 합니다. 즉, 페더레이션이 전체 조직에 대해 사용 하도록 설정 되거나 전체 조직에 페더레이션이 사용 되지 않도록 설정 되어 있기 때문입니다.

액세스에 지 구성 설정은 Windows PowerShell을 사용 하 여 반환할 수 있습니다. 이렇게 하려면 다음 Windows PowerShell 명령을 실행 합니다.

`Get-CsAccessEdgeConfiguration`

그러면 해당 명령은 다음과 같은 데이터를 반환 합니다.

Id: Global

AllowAnonymousUsers: False

AllowFederatedUsers: False

AllowOutsideUsers: False

BeClearingHouse: False

Enable및 Discovery: False

EnableArchivingDisclaimer: False

KeepCrlsUpToDateForPeers: True

MarkSourceVerifiableOnOutgoingMessages: True

OutgoingTlsCountForFederatedPartners: 4

RoutingMethod: Usednssrvrouting은

**AllowFederatedUsers** 속성을 True로 설정 하면 조직에서 페더레이션을 사용할 수 있는 것입니다. **AllowFederatedUsers** 를 True로 설정 하는 경우에도 분할 도메인 시나리오에서 온-프레미스 사용자가 클라우드 사용자와 원활 하 게 통신할 수 있음을 의미 합니다.

에 지 서버에 대 한 FQDN 및 포트 설정을 검색 하려면 이전 작업 (에 지 서버 및 해당 설정)을 참조 하십시오.

전역 범위에서 페더레이션을 사용 하도록 설정 하는 것은 사용자가 페더레이션 사용자와 통신할 가능성이 있는 것을 의미 합니다. 개별 사용자가 페더레이션 사용자와 통신할 수 있는지 여부를 확인 하려면 해당 사용자에 게 할당 된 외부 사용자 액세스 정책을 검사 해야 합니다.

외부 사용자 액세스 정보는 Windows PowerShell을 사용 하 여 반환할 수 있습니다. 예를 들어 다음 명령은 전역 외부 사용자 액세스 정책에 대 한 정보를 반환 합니다.

`Get-CsExternalAccessPolicy -Identity "Global"`

그리고이 명령은 모든 외부 사용자 액세스 정책에 대 한 정보를 반환 합니다.

`Get-CsExternalAccessPolicy`

반환 되는 정보는 다음과 같습니다.

Identity: False

설명이

EnableFederationAccess: False

EnablePublicCloudAccess: False

Enablepubliccloudaccess오디오 Videoaccess: False

Enableout연결 액세스: False

**EnableFederationAccess** 이 True로 설정 된 경우 지정 된 정책에 의해 관리 되는 사용자가 페더레이션 사용자와 통신할 수 있습니다.

</div>

</div>

<div>

## <a name="check-archiving-settings"></a>보관 설정 확인

내부 및 페더레이션 통신에 대 한 보관 설정을 확인 합니다. 내부 및 외부 보관에 대 한 설정을 확인 하기 전에 보관이 사용 하도록 설정 되어 있는지 확인 해야 합니다.

보관 구성 설정은 Windows PowerShell 및 Get-csarchivingconfiguration cmdlet을 사용 하 여 확인할 수 있습니다.

`Get-CsArchivingConfiguration -Identity "Global"`

보관 설정도 사이트 범위에서 구성할 수 있습니다. 모든 보관 설정에 대 한 정보를 반환 하려면 다음 명령을 사용 합니다.

`Get-CsArchivingConfiguration`

Get-csarchivingconfiguration cmdlet은 다음과 같은 데이터를 반환 합니다.

Id: Global

EnableArchiving: False

EnablePurging: False

PurgeExportedArchivesOnly: False

BlockOnArchiveFailure: False

KeepArchivingDataForDays: 14

PurgeHourOfDay: 2

ArchiveDuplicateMessages: True

CachePurgingInterval: 24

EnableArchiving 속성이 False로 설정 된 경우에는 통신 세션을 보관 하지 않습니다. 인스턴트 메시징 세션만 보관 하려면 IM 세션 보관을 사용 하도록 설정 하려면 다음과 같은 명령을 사용 합니다.

`Set-CsArchivingConfiguration -Identity "Global" -EnableArchiving "IMOnly"`

회의 세션과 인스턴트 메시징 세션을 보관 하려면 다음 명령을 사용 합니다.

`Set-CsArchivingConfiguration -Identity "Global" -EnableArchiving "IMOnly"`

현재 보관 설정을 기본 설정과 비교 하려면 다음 Windows PowerShell 명령을 실행 합니다.

`New-CsArchivingConfiguration -Identity "Global" -InMemory`

이 명령은 전체 보관 구성 설정에 대 한 메모리 전용 인스턴스를 만듭니다. Lync Server에서 사용 하는 실제 설정 모음이 아닙니다. 그러나 모든 보관 구성 속성에 대 한 기본값을 표시 합니다.

이 명령을 사용 하 여 보관 서버의 FQDN을 반환할 수도 있습니다.

`Get-CsService -ArchivingServer`

보관이 사용 하도록 설정 되어 있는지 확인 한 후에는 보관 정책을 확인 하 여 내부 및 외부 통신 세션의 보관 여부를 확인할 수 있습니다.

보관 정책 정보는 Grant-csarchivingpolicy cmdlet을 사용 하 여 검색할 수 있습니다. 예를 들어 다음 명령은 전역 보관 정책에 대 한 정보를 반환 합니다.

`Get-CsArchivingPolicy -Identity "Global"`

사이트 및 사용자별 범위에 보관 정책을 구성할 수도 있으므로 모든 보관 정책에 대 한 정보를 반환 하는이 명령을 사용 하는 것도 가능 합니다.

`Get-CsArchivingPolicy`

Grant-csarchivingpolicy에서 수신 하는 정보는 다음과 같습니다.

Id: Global

설명이

다음과 같이 archiveinternal: False

ArchiveExternal: False

기본적으로 보관 정책에서는 내부 및 외부 보관이 모두 사용 하지 않도록 설정 되어 있습니다.

</div>

<div>

## <a name="check-cdr-settings"></a>CDR 설정 확인

피어 투 피어, 회의 및 음성 통화 정보 기록에 대 한 CDR (통화 정보 기록) 설정을 확인 합니다. **Get-cscdrconfiguration** cmdlet을 사용 하 여 CDR 설정에 대 한 자세한 정보를 반환할 수 있습니다. 예를 들어 다음 명령은 CDR 구성 설정의 전역 컬렉션에 대 한 정보를 반환 합니다.

`Get-CsCdrConfiguration -Identity "Global"`

사이트 범위 에서도 CDR을 구성할 수 있으므로 모든 CDR 구성 설정에 대 한 정보를 반환 하는이 명령을 실행할 수도 있습니다.

`Get-CsCdrConfiguration`

Get-cscdrconfiguration cmdlet은 CDR 구성 설정의 각 컬렉션에 대해 다음과 같은 정보를 반환 합니다.

Id: Global

EnableCDR: True

EnablePurging: True

Keepcalldetailfordays는: 60

KeepErrorReportForDays: 60

PurgeHourOfDay: 2

Remove-csqoeconfiguration cmdlet을 사용 하 여 QoE 모니터링에 대 한 유사한 정보를 반환할 수 있습니다. 예를 들어이 명령은 QoE 구성 설정의 전역 컬렉션에 대 한 정보를 반환 합니다.

`Get-QoEConfiguration -Identity "Global"`

이 정보는 다음과 같습니다.

Id: Global

ExternalConsumerIssuedCertId :

EnablePurging: True

KeepQoEDataForDays: 60

PurgeHourOfDay: 1

EnableExternalConsumer: False

ExternalConsumerName :

ExternalConsumerURL :

EnableQoE: True

현재 CDR 설정을 기본 CDR 설정과 비교 하려면 다음 명령을 실행 하 여 기본값을 검토할 수 있습니다.

`New-CsCdrConfiguration -Identity "Global" -InMemory`

마찬가지로, 다음 명령을 사용 하 여 QoE 모니터링에 대 한 기본값을 검색할 수 있습니다.

`New-CsQoEConfiguration -Identity "Global" -InMemory`

다음 명령을 실행 하 여 모니터링 서버의 FQDN을 반환할 수도 있습니다.

`Get-CsService -MonitoringServer`

</div>

<div>

## <a name="check-voice-settings"></a>음성 설정 확인

일반적으로 관리자에 게 중요 한 음성 설정은 음성 정책 및 음성 경로에 포함 되어 있습니다. 음성 정책에는 개별 사용자에 게 제공 되는 기능 (예: 통화 전달 또는 전송 기능)을 결정 하는 설정이 포함 되어 있습니다. 음성 경로는 통화를 PSTN 전체에 라우팅하는 방법을 결정 합니다.

음성 정책 정보는 Windows PowerShell을 사용 하 여 검색할 수 있습니다. 예를 들어 다음 명령은 전역 음성 정책에 대 한 정보를 반환 합니다.

`Get-CsVoicePolicy -Identity "Global"`

그리고이 명령은 조직에서 사용 하도록 구성 된 모든 음성 정책에 대 한 정보를 반환 합니다.

`Get-CsVoicePolicy`

Set-csvoicepolicy cmdlet이 반환 하는 정보는 다음과 유사 합니다.

Id: Global

PstnUsages{}

설명이

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

그리고이 명령은 착신 전환을 허용 하지 않는 모든 음성 정책을 반환 합니다.

`Get-CsVoicePolicy | Where-Object {$_.AllowCallForwarding -eq $False}`

Windows PowerShell에서 CsVoiceRouting cmdlet을 사용 하 여 음성 경로에 대 한 정보를 반환 합니다.

`Get-CsVoiceRoute`

이 명령은 모든 음성 경로에 대 한 다음과 같은 정보를 반환 합니다.

Identity: LocalRoute

우선 순위: 0

설명이

번호 패턴: ^ (\\+ 1\[0-9\]{10}) $

PstnUsages{}

PstnGatewayList{}

이름: LocalRoute

SuppressCallerId

AlternateCallerId

Lync Server에서는 PSTN을 사용 하지 않고 PSTN 게이트웨이를 지정 하지 않는 음성 경로를 만들 수 있습니다. 그러나 이러한 두 가지 속성 값이 구성 되지 않은 음성 경로에 대 한 통화는 실제로 라우팅할 수 없습니다. 따라서 PSTN 사용량이 없는 음성 경로의 id를 반환 하는이 명령을 주기적으로 실행 하는 것이 유용할 수 있습니다.

`Get-CsVoiceRoute | Where-Object {$_.PstnUsages -eq $Null} | Select-Object Identity`

마찬가지로이 명령은 PSTN 게이트웨이를 갖도록 구성 되지 않은 모든 음성 경로의 id를 반환 합니다.

`Get-CsVoiceRoute | Where-Object {$_.PstnGatewayList -eq $Null}} | Select-Object Identity`

</div>

<div>

## <a name="check-conferencing-attendant-settings"></a>회의 전화 교환 설정 확인

PSTN 전화 접속 회의에 대 한 회의 전화 교환 설정을 확인 합니다. 회의 전화 교환 설정은 **get-csdialinconferencingconfiguration** cmdlet을 사용 해야만 검색할 수 있습니다. 이 설정은 Lync Server 제어판에서는 사용할 수 없습니다. 회의 전화 교환 설정을 보려면 다음과 같은 Windows PowerShell 명령을 사용 하 여 회의 전화 교환 설정의 전역 컬렉션을 반환 합니다.

`Get-CsDialInConferencingConfiguration -Identity "Global"`

사이트 범위에서 회의 전화 교환 설정을 구성할 수도 있습니다. 모든 회의 전화 교환 설정에 대 한 정보를 반환 하려면 대신 다음 명령을 사용 합니다.

`Get-CsDialInConferencingConfiguration`

Get-csdialinconferencingconfiguration cmdlet은 다음과 같은 데이터를 반환 합니다.

Id: Global

EntryExitAnnouncementsType: UseNames

EnableNameRecording: True

EntryExitAnnouncementsEnabledByDefault: False

EntryExitAnnouncementsEnabledByDefault가 False로 설정 되 면 회의 알림이 사용 되지 않습니다. 항목 및 종료 알림을 사용 하도록 설정 하려면 다음과 같은 Windows PowerShell 명령을 실행 합니다.

`Set-CsDialInConferencingConfiguration -Identity "Global" -EntryExitAnnouncementsEnabledByDefault $True`

</div>

<div>

## <a name="see-also"></a>참고 항목


[New-cssipdomain](https://docs.microsoft.com/powershell/module/skype/Get-CsSipDomain)  
[Get-csmeetingconfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingConfiguration)  
[Get-CsService](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[Set-csaccessedgeconfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsAccessEdgeConfiguration)  
[Get-csexternalaccesspolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[Get-csarchivingconfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsArchivingConfiguration)  
[Get-cscdrconfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCdrConfiguration)  
[Remove-csqoeconfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsQoEConfiguration)  
[Set-csvoicepolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicePolicy)  
[Get-csvoiceroute](https://docs.microsoft.com/powershell/module/skype/Get-CsVoiceRoute)  
[Get-csdialinconferencingconfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsDialInConferencingConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

