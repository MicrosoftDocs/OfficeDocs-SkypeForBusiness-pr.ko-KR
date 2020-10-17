---
title: 'Lync Server 2013: 포리스트의 전역 설정 상태 보기'
description: 'Lync Server 2013: 포리스트의 전역 설정 상태를 확인 하는 중입니다.'
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
ms.openlocfilehash: d9f722ea66f6c54c816703bd1af1d3def57bbd84
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567594"
---
# <a name="view-status-of-global-settings-for-a-forest-in-lync-server-2013"></a><span data-ttu-id="cfc99-103">Lync Server 2013에서 포리스트의 전역 설정 상태 보기</span><span class="sxs-lookup"><span data-stu-id="cfc99-103">View status of global settings for a forest in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cfc99-104">_**마지막으로 수정 된 항목:** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="cfc99-104">_**Topic Last Modified:** 2014-05-20_</span></span>

<span data-ttu-id="cfc99-105">관리자는 Lync Server 2013 배포에 대 한 전역 설정을 매월 검토 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc99-105">Administrators should review the global settings for a Lync Server 2013 deployment monthly.</span></span> <span data-ttu-id="cfc99-106">이 목표는 알려진 구성 집합 (기준 구성)에 대해 구현 된 설정을 검토 하 여 해당 설정이 유효 하며 기준 문서를 업데이트 해야 하는지 여부를 결정 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="cfc99-106">The objective would be to review implemented settings against a set of known configurations—a baseline configuration to help guarantee that settings are valid and to determine whether the baseline documentation should be updated.</span></span> <span data-ttu-id="cfc99-107">전역 설정에 대 한 변경 내용은 새 설정의 문서화를 포함 해야 하는 변경 제어 프로세스를 통해 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc99-107">Changes to global setting should be implemented through a Change Control process which should include documenting the new settings.</span></span>

<span data-ttu-id="cfc99-108">검토 해야 하는 전역 설정은 다음 섹션에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc99-108">Global settings that should be reviewed are described in the following sections:</span></span>

<div>

## <a name="check-general-settings"></a><span data-ttu-id="cfc99-109">일반 설정 확인</span><span class="sxs-lookup"><span data-stu-id="cfc99-109">Check general settings</span></span>

<span data-ttu-id="cfc99-110">Lync Server 2013에 대해 지원 되는 SIP (Session 착수 프로토콜) 도메인을 비롯 한 일반 설정을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc99-110">Check general settings, including the supported Session Initiation Protocol (SIP) domains for Lync Server 2013.</span></span>

<span data-ttu-id="cfc99-111">SIP 도메인 정보는 Windows PowerShell 및 **new-cssipdomain** cmdlet을 사용 하 여 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc99-111">SIP domain information can be returned by using Windows PowerShell and the **Get-CsSipDomain** cmdlet.</span></span> <span data-ttu-id="cfc99-112">이 정보를 반환 하려면 `Get-CsSipDomain` Windows PowerShell 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc99-112">To return this information, run the `Get-CsSipDomain` Windows PowerShell command.</span></span>

<span data-ttu-id="cfc99-113">Get-CsSipDomain는 모든 권한 있는 SIP 도메인에 대해 다음과 같은 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc99-113">Get-CsSipDomain will return information similar to this for all the authorized SIP domains:</span></span>

<span data-ttu-id="cfc99-114">Id 이름 IsDefault</span><span class="sxs-lookup"><span data-stu-id="cfc99-114">Identity Name IsDefault</span></span>

<span data-ttu-id="cfc99-115">\-------- ---- ---------</span><span class="sxs-lookup"><span data-stu-id="cfc99-115">\-------- ---- ---------</span></span>

<span data-ttu-id="cfc99-116">fabrikam.com fabrikam.com True</span><span class="sxs-lookup"><span data-stu-id="cfc99-116">fabrikam.com fabrikam.com True</span></span>

<span data-ttu-id="cfc99-117">na.fabrikam.com na.fabrikam.com False</span><span class="sxs-lookup"><span data-stu-id="cfc99-117">na.fabrikam.com na.fabrikam.com False</span></span>

<span data-ttu-id="cfc99-118">IsDefault 속성이 True로 설정 된 경우 해당 도메인은 기본 SIP 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="cfc99-118">If the IsDefault property is set to True, the corresponding domain is your default SIP domain.</span></span> <span data-ttu-id="cfc99-119">Set-CsSipDomain cmdlet을 사용 하 여 조직의 기본 SIP 도메인을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc99-119">You can use the Set-CsSipDomain cmdlet to change the default SIP domain for your organization.</span></span> <span data-ttu-id="cfc99-120">그러나 기본 도메인을 제외 하 고는 기본 SIP 도메인을 삭제 하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cfc99-120">However, you can't just delete the default SIP domain because that would leave you without a default domain.</span></span> <span data-ttu-id="cfc99-121">이전 예제와 같이 fabrikam.com 도메인을 삭제 하려면 먼저 na.fabrikam.com를 기본 도메인으로 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc99-121">If you wanted to delete the fabrikam.com domain (as shown in the previous example), you would first have to configure na.fabrikam.com to be your default domain.</span></span>

</div>

<div>

## <a name="check-meeting-settings"></a><span data-ttu-id="cfc99-122">모임 설정 확인</span><span class="sxs-lookup"><span data-stu-id="cfc99-122">Check meeting settings</span></span>

<span data-ttu-id="cfc99-123">모임 설정에는 모임 정책 정의와 회의의 익명 사용자 참여에 대 한 지원이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cfc99-123">Meeting settings include meeting policy definitions and support for participation of anonymous users in meetings.</span></span>

<span data-ttu-id="cfc99-124">모임 구성 설정은 Windows PowerShell 및 **get-csmeetingconfiguration** cmdlet을 사용 하 여 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc99-124">Meeting configuration settings can be retrieved by using Windows PowerShell and the **Get-CsMeetingConfiguration** cmdlet.</span></span> <span data-ttu-id="cfc99-125">예를 들어 다음 명령은 전역 모임 구성 설정에 대 한 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc99-125">For example, this command returns information about the global meeting configuration settings:</span></span>

<span data-ttu-id="cfc99-126">Get-CsMeetingConfiguration-사이트 범위에서 Id "전역" 모임 구성 설정을 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc99-126">Get-CsMeetingConfiguration –Identity "Global"Meeting configuration settings can also be configured at the site scope.</span></span> <span data-ttu-id="cfc99-127">따라서 모든 모임 구성 설정에 대 한 정보를 반환 하는 다음 명령을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc99-127">Because of that, you might want to use the following command, which returns information about all the meeting configuration settings:</span></span>

`Get-CsMeetingConfiguration`

<span data-ttu-id="cfc99-128">**Get-csmeetingconfiguration** cmdlet은 다음과 같은 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc99-128">The **Get-CsMeetingConfiguration** cmdlet returns information similar to the following:</span></span>

<span data-ttu-id="cfc99-129">Id: Global</span><span class="sxs-lookup"><span data-stu-id="cfc99-129">Identity : Global</span></span>

<span data-ttu-id="cfc99-130">PstnCallersBypassLobby: True</span><span class="sxs-lookup"><span data-stu-id="cfc99-130">PstnCallersBypassLobby : True</span></span>

<span data-ttu-id="cfc99-131">EnableAssignedConferenceType: True</span><span class="sxs-lookup"><span data-stu-id="cfc99-131">EnableAssignedConferenceType : True</span></span>

<span data-ttu-id="cfc99-132">DesignateAsPresenter: 회사</span><span class="sxs-lookup"><span data-stu-id="cfc99-132">DesignateAsPresenter : Company</span></span>

<span data-ttu-id="cfc99-133">AssignedConferenceTypeByDefault: True</span><span class="sxs-lookup"><span data-stu-id="cfc99-133">AssignedConferenceTypeByDefault : True</span></span>

<span data-ttu-id="cfc99-134">AdmitAnonymousUsersByDefault: True</span><span class="sxs-lookup"><span data-stu-id="cfc99-134">AdmitAnonymousUsersByDefault : True</span></span>

<span data-ttu-id="cfc99-135">다시 말하지만, 목록의 최종 항목 **AdmitAnonymousUsersByDefault**은 익명 사용자가 모임에 참가할 수 있는 기능을 사용 하거나 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc99-135">Again, the final item in the list, **AdmitAnonymousUsersByDefault**, enables or disables the ability of anonymous users to participate in meetings.</span></span>

<span data-ttu-id="cfc99-136">모임 구성 설정을 확인할 때 현재 설정을 기본값과 비교 하는 것이 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc99-136">When checking meeting configuration settings, you might find it useful to compare the current settings against the default equivalents.</span></span> <span data-ttu-id="cfc99-137">다음 명령을 실행 하 여 기본 모임 구성 설정을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc99-137">You can view the default meeting configuration settings by running the following command:</span></span>

`New-CsMeetingConfiguration -Identity "Global" -InMemory`

<span data-ttu-id="cfc99-138">이전 명령은 각 속성의 기본값을 사용 하는 인스턴스인 전체 모임 구성 설정에 대 한 메모리 전용 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="cfc99-138">The previous command creates an in-memory-only instance of the global meeting configuration settings, an instance that uses the default value for each property.</span></span> <span data-ttu-id="cfc99-139">명령을 실행할 때 실제 모임 구성 설정은 만들어지지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc99-139">No actual meeting configuration settings are created when you run the command.</span></span> <span data-ttu-id="cfc99-140">그러나 모든 기본 속성 값은 화면에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cfc99-140">However, all the default property values will be displayed on-screen.</span></span>

</div>

<div>

## <a name="check-edge-servers-and-their-settings"></a><span data-ttu-id="cfc99-141">에 지 서버 및 설정 확인</span><span class="sxs-lookup"><span data-stu-id="cfc99-141">Check Edge Servers and their settings</span></span>

<span data-ttu-id="cfc99-142">에 지 서버 정보는 Windows PowerShell을 사용 하 여 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc99-142">Edge Server information can be retrieved by using Windows PowerShell.</span></span> <span data-ttu-id="cfc99-143">이 명령은 조직에서 사용 하도록 구성 된 모든에 지 서버에 대 한 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc99-143">This command returns information about all the Edge Servers configured for use in your organization:</span></span>

`Get-CsService -EdgeServer`

<span data-ttu-id="cfc99-144">반환 되는 정보에는 각에 지 서버에 대 한 모든 FQDN 및 포트 설정이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cfc99-144">The returned information includes all of the FQDN and port settings for each Edge Server:</span></span>

<span data-ttu-id="cfc99-145">Identity: EdgeServer: dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="cfc99-145">Identity : EdgeServer: dc.fabrikam.com</span></span>

<span data-ttu-id="cfc99-146">등록자: 등록자: LYNC-SE.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="cfc99-146">Registrar : Registrar: LYNC-SE.fabrikam.com</span></span>

<span data-ttu-id="cfc99-147">AccessEdgeInternalSipPort: 5061</span><span class="sxs-lookup"><span data-stu-id="cfc99-147">AccessEdgeInternalSipPort : 5061</span></span>

<span data-ttu-id="cfc99-148">AccessEdgeExternalSipPort: 5061</span><span class="sxs-lookup"><span data-stu-id="cfc99-148">AccessEdgeExternalSipPort : 5061</span></span>

<span data-ttu-id="cfc99-149">AccessEdgeClientPort: 443</span><span class="sxs-lookup"><span data-stu-id="cfc99-149">AccessEdgeClientPort : 443</span></span>

<span data-ttu-id="cfc99-150">DataPsomServerPort: 8057</span><span class="sxs-lookup"><span data-stu-id="cfc99-150">DataPsomServerPort : 8057</span></span>

<span data-ttu-id="cfc99-151">DataPsomClientPort: 444</span><span class="sxs-lookup"><span data-stu-id="cfc99-151">DataPsomClientPort : 444</span></span>

<span data-ttu-id="cfc99-152">MediaRelayAuthEdgePort: 5062</span><span class="sxs-lookup"><span data-stu-id="cfc99-152">MediaRelayAuthEdgePort : 5062</span></span>

<span data-ttu-id="cfc99-153">MediaRelayAuthInternalTurnTcpPort: 443</span><span class="sxs-lookup"><span data-stu-id="cfc99-153">MediaRelayAuthInternalTurnTcpPort : 443</span></span>

<span data-ttu-id="cfc99-154">MediaRelayAuthExternalTurnTcpPort: 445</span><span class="sxs-lookup"><span data-stu-id="cfc99-154">MediaRelayAuthExternalTurnTcpPort : 445</span></span>

<span data-ttu-id="cfc99-155">MediaRelayAuthInternalTurnUdpPort: 3478</span><span class="sxs-lookup"><span data-stu-id="cfc99-155">MediaRelayAuthInternalTurnUdpPort : 3478</span></span>

<span data-ttu-id="cfc99-156">MediaRelayAuthExternalTurnUdpPort: 3478</span><span class="sxs-lookup"><span data-stu-id="cfc99-156">MediaRelayAuthExternalTurnUdpPort : 3478</span></span>

<span data-ttu-id="cfc99-157">MediaCommunicationPortStart: 5만</span><span class="sxs-lookup"><span data-stu-id="cfc99-157">MediaCommunicationPortStart : 50000</span></span>

<span data-ttu-id="cfc99-158">MediaComunicationPortCount: 1만</span><span class="sxs-lookup"><span data-stu-id="cfc99-158">MediaComunicationPortCount : 10000</span></span>

<span data-ttu-id="cfc99-159">AccessEdgeExternalFqdn: dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="cfc99-159">AccessEdgeExternalFqdn : dc.fabrikam.com</span></span>

<span data-ttu-id="cfc99-160">DataEdgeExternalFqdn: dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="cfc99-160">DataEdgeExternalFqdn : dc.fabrikam.com</span></span>

<span data-ttu-id="cfc99-161">AVEdgeExternalFqdn :</span><span class="sxs-lookup"><span data-stu-id="cfc99-161">AVEdgeExternalFqdn :</span></span>

<span data-ttu-id="cfc99-162">InternalInterfaceFqdn :</span><span class="sxs-lookup"><span data-stu-id="cfc99-162">InternalInterfaceFqdn :</span></span>

<span data-ttu-id="cfc99-163">ExternalMrasFqdn: dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="cfc99-163">ExternalMrasFqdn : dc.fabrikam.com</span></span>

<span data-ttu-id="cfc99-164">DependentServiceList: {등록자: LYNC-SE.fabrikam.com,</span><span class="sxs-lookup"><span data-stu-id="cfc99-164">DependentServiceList : {Registrar:LYNC-SE.fabrikam.com,</span></span>

<span data-ttu-id="cfc99-165">ConferencingServer:-fabrikam</span><span class="sxs-lookup"><span data-stu-id="cfc99-165">ConferencingServer:LYNC-SE.fabrikam</span></span>

<span data-ttu-id="cfc99-166">com, MediationServer: LYNC-SE</span><span class="sxs-lookup"><span data-stu-id="cfc99-166">com, MediationServer:LYNC-SE.</span></span>

<span data-ttu-id="cfc99-167">fabrikam.com}</span><span class="sxs-lookup"><span data-stu-id="cfc99-167">fabrikam.com}</span></span>

<span data-ttu-id="cfc99-168">ServiceId: fabrikam.com-EdgeServer-2</span><span class="sxs-lookup"><span data-stu-id="cfc99-168">ServiceId : fabrikam.com-EdgeServer-2</span></span>

<span data-ttu-id="cfc99-169">SiteId: site:fabrikam.</span><span class="sxs-lookup"><span data-stu-id="cfc99-169">SiteId : site:fabrikam.com</span></span>

<span data-ttu-id="cfc99-170">PoolFqdn: dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="cfc99-170">PoolFqdn : dc.fabrikam.com</span></span>

<span data-ttu-id="cfc99-171">버전: 5</span><span class="sxs-lookup"><span data-stu-id="cfc99-171">Version : 5</span></span>

<span data-ttu-id="cfc99-172">역할: EdgeServer</span><span class="sxs-lookup"><span data-stu-id="cfc99-172">Role : EdgeServer</span></span>

<div>

## <a name="check-federation-settings"></a><span data-ttu-id="cfc99-173">페더레이션 설정 확인</span><span class="sxs-lookup"><span data-stu-id="cfc99-173">Check federation settings</span></span>

<span data-ttu-id="cfc99-174">페더레이션 설정 (예: 구성 여부) 및 FQDN과 포트가 "예" 인 경우의 대답이 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc99-174">Check Federation settings, such as whether it is configured and, if the answer is "yes,", the FQDN and port.</span></span> <span data-ttu-id="cfc99-175">액세스에 지 구성 설정의 전역 컬렉션을 사용 하 여 페더레이션을 사용 하도록 설정 하 고 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc99-175">Federation is enabled and disabled by using the global collection of Access Edge configuration settings.</span></span> <span data-ttu-id="cfc99-176">즉, 페더레이션이 전체 조직에 대해 사용 하도록 설정 되거나 전체 조직에 페더레이션이 사용 되지 않도록 설정 되어 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="cfc99-176">Among other things, these mean that federation is configured on an all-or-nothing basis: either federation is enabled for the whole organization or federation is disabled for the whole organization</span></span>

<span data-ttu-id="cfc99-177">액세스에 지 구성 설정은 Windows PowerShell을 사용 하 여 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc99-177">Your Access Edge configuration settings can be returned by using Windows PowerShell.</span></span> <span data-ttu-id="cfc99-178">이렇게 하려면 다음 Windows PowerShell 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc99-178">To do that, run the following Windows PowerShell command:</span></span>

`Get-CsAccessEdgeConfiguration`

<span data-ttu-id="cfc99-179">그러면 해당 명령은 다음과 같은 데이터를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc99-179">In turn, that command will return data similar to this:</span></span>

<span data-ttu-id="cfc99-180">Id: Global</span><span class="sxs-lookup"><span data-stu-id="cfc99-180">Identity : Global</span></span>

<span data-ttu-id="cfc99-181">AllowAnonymousUsers: False</span><span class="sxs-lookup"><span data-stu-id="cfc99-181">AllowAnonymousUsers : False</span></span>

<span data-ttu-id="cfc99-182">AllowFederatedUsers: False</span><span class="sxs-lookup"><span data-stu-id="cfc99-182">AllowFederatedUsers : False</span></span>

<span data-ttu-id="cfc99-183">AllowOutsideUsers: False</span><span class="sxs-lookup"><span data-stu-id="cfc99-183">AllowOutsideUsers : False</span></span>

<span data-ttu-id="cfc99-184">BeClearingHouse: False</span><span class="sxs-lookup"><span data-stu-id="cfc99-184">BeClearingHouse : False</span></span>

<span data-ttu-id="cfc99-185">Enable및 Discovery: False</span><span class="sxs-lookup"><span data-stu-id="cfc99-185">EnablePartnerDiscovery : False</span></span>

<span data-ttu-id="cfc99-186">EnableArchivingDisclaimer: False</span><span class="sxs-lookup"><span data-stu-id="cfc99-186">EnableArchivingDisclaimer : False</span></span>

<span data-ttu-id="cfc99-187">KeepCrlsUpToDateForPeers: True</span><span class="sxs-lookup"><span data-stu-id="cfc99-187">KeepCrlsUpToDateForPeers : True</span></span>

<span data-ttu-id="cfc99-188">MarkSourceVerifiableOnOutgoingMessages: True</span><span class="sxs-lookup"><span data-stu-id="cfc99-188">MarkSourceVerifiableOnOutgoingMessages : True</span></span>

<span data-ttu-id="cfc99-189">OutgoingTlsCountForFederatedPartners: 4</span><span class="sxs-lookup"><span data-stu-id="cfc99-189">OutgoingTlsCountForFederatedPartners : 4</span></span>

<span data-ttu-id="cfc99-190">RoutingMethod: Usednssrvrouting은</span><span class="sxs-lookup"><span data-stu-id="cfc99-190">RoutingMethod : UseDnsSrvRouting</span></span>

<span data-ttu-id="cfc99-191">**AllowFederatedUsers** 속성을 True로 설정 하면 조직에서 페더레이션을 사용할 수 있는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="cfc99-191">If the **AllowFederatedUsers** property is set to True, that means that federation is enabled for your organization.</span></span> <span data-ttu-id="cfc99-192">**AllowFederatedUsers** 를 True로 설정 하는 경우에도 분할 도메인 시나리오에서 온-프레미스 사용자가 클라우드 사용자와 원활 하 게 통신할 수 있음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc99-192">(Setting **AllowFederatedUsers** to True also means that, in a split domain scenario, your on-premises users will be able to communicate seamlessly with your in-the-cloud users.)</span></span>

<span data-ttu-id="cfc99-193">에 지 서버에 대 한 FQDN 및 포트 설정을 검색 하려면 이전 작업 (에 지 서버 및 해당 설정)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="cfc99-193">To retrieve the FQDN and port settings for your Edge Server, see the previous task (Edge Servers and their settings).</span></span>

<span data-ttu-id="cfc99-194">전역 범위에서 페더레이션을 사용 하도록 설정 하는 것은 사용자가 페더레이션 사용자와 통신할 가능성이 있는 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc99-194">Enabling federation at the global scope only means that users can potentially communicate with federated users.</span></span> <span data-ttu-id="cfc99-195">개별 사용자가 페더레이션 사용자와 통신할 수 있는지 여부를 확인 하려면 해당 사용자에 게 할당 된 외부 사용자 액세스 정책을 검사 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc99-195">To determine whether any individual users can actually communicate with federated users requires you to examine the external user access policy assigned to that user.</span></span>

<span data-ttu-id="cfc99-196">외부 사용자 액세스 정보는 Windows PowerShell을 사용 하 여 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc99-196">External user access information can be returned by using Windows PowerShell.</span></span> <span data-ttu-id="cfc99-197">예를 들어 다음 명령은 전역 외부 사용자 액세스 정책에 대 한 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc99-197">For example, this command returns information for the global external user access policy:</span></span>

`Get-CsExternalAccessPolicy -Identity "Global"`

<span data-ttu-id="cfc99-198">그리고이 명령은 모든 외부 사용자 액세스 정책에 대 한 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc99-198">And this command returns information for all the external user access policies:</span></span>

`Get-CsExternalAccessPolicy`

<span data-ttu-id="cfc99-199">반환 되는 정보는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc99-199">The returned information will resemble this:</span></span>

<span data-ttu-id="cfc99-200">Identity: False</span><span class="sxs-lookup"><span data-stu-id="cfc99-200">Identity : False</span></span>

<span data-ttu-id="cfc99-201">설명이</span><span class="sxs-lookup"><span data-stu-id="cfc99-201">Description :</span></span>

<span data-ttu-id="cfc99-202">EnableFederationAccess: False</span><span class="sxs-lookup"><span data-stu-id="cfc99-202">EnableFederationAccess : False</span></span>

<span data-ttu-id="cfc99-203">EnablePublicCloudAccess: False</span><span class="sxs-lookup"><span data-stu-id="cfc99-203">EnablePublicCloudAccess : False</span></span>

<span data-ttu-id="cfc99-204">Enablepubliccloudaccess오디오 Videoaccess: False</span><span class="sxs-lookup"><span data-stu-id="cfc99-204">EnablePublicCloudAccessAudioVideoAccess : False</span></span>

<span data-ttu-id="cfc99-205">Enableout연결 액세스: False</span><span class="sxs-lookup"><span data-stu-id="cfc99-205">EnableOutsideAccess : False</span></span>

<span data-ttu-id="cfc99-206">**EnableFederationAccess** 이 True로 설정 된 경우 지정 된 정책에 의해 관리 되는 사용자가 페더레이션 사용자와 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc99-206">If **EnableFederationAccess** is set to True, then users managed by the given policy can communicate with federated users.</span></span>

</div>

</div>

<div>

## <a name="check-archiving-settings"></a><span data-ttu-id="cfc99-207">보관 설정 확인</span><span class="sxs-lookup"><span data-stu-id="cfc99-207">Check archiving settings</span></span>

<span data-ttu-id="cfc99-208">내부 및 페더레이션 통신에 대 한 보관 설정을 확인 합니다. 내부 및 외부 보관에 대 한 설정을 확인 하기 전에 보관이 사용 하도록 설정 되어 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc99-208">Check archiving settings for internal and federated communications.Before verifying the settings for internal and external archiving, you should verify that archiving is enabled.</span></span>

<span data-ttu-id="cfc99-209">보관 구성 설정은 Windows PowerShell 및 Get-CsArchivingConfiguration cmdlet을 사용 하 여 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc99-209">Archiving configuration settings can be verified by using Windows PowerShell and the Get-CsArchivingConfiguration cmdlet:</span></span>

`Get-CsArchivingConfiguration -Identity "Global"`

<span data-ttu-id="cfc99-210">보관 설정도 사이트 범위에서 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc99-210">Note that archiving settings can also be configured at the site scope.</span></span> <span data-ttu-id="cfc99-211">모든 보관 설정에 대 한 정보를 반환 하려면 다음 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc99-211">To return information about all the archiving settings, use this command:</span></span>

`Get-CsArchivingConfiguration`

<span data-ttu-id="cfc99-212">Get-CsArchivingConfiguration cmdlet은 다음과 같은 데이터를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc99-212">The Get-CsArchivingConfiguration cmdlet returns data similar to this:</span></span>

<span data-ttu-id="cfc99-213">Id: Global</span><span class="sxs-lookup"><span data-stu-id="cfc99-213">Identity : Global</span></span>

<span data-ttu-id="cfc99-214">EnableArchiving: False</span><span class="sxs-lookup"><span data-stu-id="cfc99-214">EnableArchiving : False</span></span>

<span data-ttu-id="cfc99-215">EnablePurging: False</span><span class="sxs-lookup"><span data-stu-id="cfc99-215">EnablePurging : False</span></span>

<span data-ttu-id="cfc99-216">PurgeExportedArchivesOnly: False</span><span class="sxs-lookup"><span data-stu-id="cfc99-216">PurgeExportedArchivesOnly : False</span></span>

<span data-ttu-id="cfc99-217">BlockOnArchiveFailure: False</span><span class="sxs-lookup"><span data-stu-id="cfc99-217">BlockOnArchiveFailure : False</span></span>

<span data-ttu-id="cfc99-218">KeepArchivingDataForDays: 14</span><span class="sxs-lookup"><span data-stu-id="cfc99-218">KeepArchivingDataForDays : 14</span></span>

<span data-ttu-id="cfc99-219">PurgeHourOfDay: 2</span><span class="sxs-lookup"><span data-stu-id="cfc99-219">PurgeHourOfDay : 2</span></span>

<span data-ttu-id="cfc99-220">ArchiveDuplicateMessages: True</span><span class="sxs-lookup"><span data-stu-id="cfc99-220">ArchiveDuplicateMessages : True</span></span>

<span data-ttu-id="cfc99-221">CachePurgingInterval: 24</span><span class="sxs-lookup"><span data-stu-id="cfc99-221">CachePurgingInterval : 24</span></span>

<span data-ttu-id="cfc99-222">EnableArchiving 속성이 False로 설정 된 경우에는 통신 세션을 보관 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc99-222">If the EnableArchiving property is set to False, that means that no communication sessions will be archived.</span></span> <span data-ttu-id="cfc99-223">인스턴트 메시징 세션만 보관 하려면 IM 세션 보관을 사용 하도록 설정 하려면 다음과 같은 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc99-223">If you want to archive instant messaging sessions only, use a command such as the following to enable the archiving of IM sessions:</span></span>

`Set-CsArchivingConfiguration -Identity "Global" -EnableArchiving "IMOnly"`

<span data-ttu-id="cfc99-224">회의 세션과 인스턴트 메시징 세션을 보관 하려면 다음 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc99-224">To archive conferencing sessions and instant messaging sessions, use this command:</span></span>

`Set-CsArchivingConfiguration -Identity "Global" -EnableArchiving "IMOnly"`

<span data-ttu-id="cfc99-225">현재 보관 설정을 기본 설정과 비교 하려면 다음 Windows PowerShell 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc99-225">If you’d like to compare your current archiving settings with the default settings, run the following Windows PowerShell command:</span></span>

`New-CsArchivingConfiguration -Identity "Global" -InMemory`

<span data-ttu-id="cfc99-226">이 명령은 전체 보관 구성 설정에 대 한 메모리 전용 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="cfc99-226">That command creates an in-memory-only instance of the global archiving configuration settings.</span></span> <span data-ttu-id="cfc99-227">Lync Server에서 사용 하는 실제 설정 모음이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="cfc99-227">This is not a real collection of settings that is used by Lync Server.</span></span> <span data-ttu-id="cfc99-228">그러나 모든 보관 구성 속성에 대 한 기본값을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc99-228">However, it does display the default values for all the archiving configuration properties.</span></span>

<span data-ttu-id="cfc99-229">이 명령을 사용 하 여 보관 서버의 FQDN을 반환할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc99-229">You can also use this command to return the FQDN of your Archiving servers:</span></span>

`Get-CsService -ArchivingServer`

<span data-ttu-id="cfc99-230">보관이 사용 하도록 설정 되어 있는지 확인 한 후에는 보관 정책을 확인 하 여 내부 및 외부 통신 세션의 보관 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc99-230">After you have verified that archiving is enabled, you can then view your archiving policies to determine whether internal and external communication sessions are being archived.</span></span>

<span data-ttu-id="cfc99-231">Get-CsArchivingPolicy cmdlet을 사용 하 여 보관 정책 정보를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc99-231">Archiving policy information can be retrieved by using the Get-CsArchivingPolicy cmdlet.</span></span> <span data-ttu-id="cfc99-232">예를 들어 다음 명령은 전역 보관 정책에 대 한 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc99-232">For example, this command returns information about the global archiving policy:</span></span>

`Get-CsArchivingPolicy -Identity "Global"`

<span data-ttu-id="cfc99-233">사이트 및 사용자별 범위에 보관 정책을 구성할 수도 있으므로 모든 보관 정책에 대 한 정보를 반환 하는이 명령을 사용 하는 것도 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc99-233">Because archiving policies can also be configured at the site and the per-user scope, you might also want to use this command, which returns information about all the archiving policies:</span></span>

`Get-CsArchivingPolicy`

<span data-ttu-id="cfc99-234">Get-CsArchivingPolicy에서 받는 정보는 다음과 유사 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc99-234">The information that you receive from Get-CsArchivingPolicy will resemble this:</span></span>

<span data-ttu-id="cfc99-235">Id: Global</span><span class="sxs-lookup"><span data-stu-id="cfc99-235">Identity : Global</span></span>

<span data-ttu-id="cfc99-236">설명이</span><span class="sxs-lookup"><span data-stu-id="cfc99-236">Description :</span></span>

<span data-ttu-id="cfc99-237">다음과 같이 archiveinternal: False</span><span class="sxs-lookup"><span data-stu-id="cfc99-237">ArchiveInternal : False</span></span>

<span data-ttu-id="cfc99-238">ArchiveExternal: False</span><span class="sxs-lookup"><span data-stu-id="cfc99-238">ArchiveExternal : False</span></span>

<span data-ttu-id="cfc99-239">기본적으로 보관 정책에서는 내부 및 외부 보관이 모두 사용 하지 않도록 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc99-239">Note that, by default, both internal and external archiving are disabled in an archiving policy.</span></span>

</div>

<div>

## <a name="check-cdr-settings"></a><span data-ttu-id="cfc99-240">CDR 설정 확인</span><span class="sxs-lookup"><span data-stu-id="cfc99-240">Check CDR settings</span></span>

<span data-ttu-id="cfc99-241">피어 투 피어, 회의 및 음성 통화 정보 기록에 대 한 CDR (통화 정보 기록) 설정을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc99-241">Check Call Detail Record (CDR) settings for peer-to-peer, conferencing, and Voice call detail recording.</span></span> <span data-ttu-id="cfc99-242">**Get-cscdrconfiguration** cmdlet을 사용 하 여 CDR 설정에 대 한 자세한 정보를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc99-242">Detailed information about your CDR settings can be returned by using the **Get-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="cfc99-243">예를 들어 다음 명령은 CDR 구성 설정의 전역 컬렉션에 대 한 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc99-243">For example, this command returns information about the global collection of CDR configuration settings:</span></span>

`Get-CsCdrConfiguration -Identity "Global"`

<span data-ttu-id="cfc99-244">사이트 범위 에서도 CDR을 구성할 수 있으므로 모든 CDR 구성 설정에 대 한 정보를 반환 하는이 명령을 실행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc99-244">Because CDR can also be configured at the site scope, you might also want to run this command, which returns information about all the CDR configuration settings:</span></span>

`Get-CsCdrConfiguration`

<span data-ttu-id="cfc99-245">Get-CsCdrConfiguration cmdlet은 CDR 구성 설정의 각 컬렉션에 대해 다음과 같은 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc99-245">The Get-CsCdrConfiguration cmdlet returns information similar to this for each collection of CDR configuration settings:</span></span>

<span data-ttu-id="cfc99-246">Id: Global</span><span class="sxs-lookup"><span data-stu-id="cfc99-246">Identity : Global</span></span>

<span data-ttu-id="cfc99-247">EnableCDR: True</span><span class="sxs-lookup"><span data-stu-id="cfc99-247">EnableCDR : True</span></span>

<span data-ttu-id="cfc99-248">EnablePurging: True</span><span class="sxs-lookup"><span data-stu-id="cfc99-248">EnablePurging : True</span></span>

<span data-ttu-id="cfc99-249">Keepcalldetailfordays는: 60</span><span class="sxs-lookup"><span data-stu-id="cfc99-249">KeepCallDetailForDays : 60</span></span>

<span data-ttu-id="cfc99-250">KeepErrorReportForDays: 60</span><span class="sxs-lookup"><span data-stu-id="cfc99-250">KeepErrorReportForDays : 60</span></span>

<span data-ttu-id="cfc99-251">PurgeHourOfDay: 2</span><span class="sxs-lookup"><span data-stu-id="cfc99-251">PurgeHourOfDay : 2</span></span>

<span data-ttu-id="cfc99-252">Get-CsQoEConfiguration cmdlet을 사용 하 여 QoE 모니터링에 대 한 유사한 정보를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc99-252">Similar information can be returned for QoE monitoring by using the Get-CsQoEConfiguration cmdlet.</span></span> <span data-ttu-id="cfc99-253">예를 들어이 명령은 QoE 구성 설정의 전역 컬렉션에 대 한 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc99-253">For example, this command returns information about the global collection of QoE configuration settings:</span></span>

`Get-QoEConfiguration -Identity "Global"`

<span data-ttu-id="cfc99-254">이 정보는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc99-254">That information will resemble this:</span></span>

<span data-ttu-id="cfc99-255">Id: Global</span><span class="sxs-lookup"><span data-stu-id="cfc99-255">Identity : Global</span></span>

<span data-ttu-id="cfc99-256">ExternalConsumerIssuedCertId :</span><span class="sxs-lookup"><span data-stu-id="cfc99-256">ExternalConsumerIssuedCertId :</span></span>

<span data-ttu-id="cfc99-257">EnablePurging: True</span><span class="sxs-lookup"><span data-stu-id="cfc99-257">EnablePurging : True</span></span>

<span data-ttu-id="cfc99-258">KeepQoEDataForDays: 60</span><span class="sxs-lookup"><span data-stu-id="cfc99-258">KeepQoEDataForDays : 60</span></span>

<span data-ttu-id="cfc99-259">PurgeHourOfDay: 1</span><span class="sxs-lookup"><span data-stu-id="cfc99-259">PurgeHourOfDay : 1</span></span>

<span data-ttu-id="cfc99-260">EnableExternalConsumer: False</span><span class="sxs-lookup"><span data-stu-id="cfc99-260">EnableExternalConsumer : False</span></span>

<span data-ttu-id="cfc99-261">ExternalConsumerName :</span><span class="sxs-lookup"><span data-stu-id="cfc99-261">ExternalConsumerName :</span></span>

<span data-ttu-id="cfc99-262">ExternalConsumerURL :</span><span class="sxs-lookup"><span data-stu-id="cfc99-262">ExternalConsumerURL :</span></span>

<span data-ttu-id="cfc99-263">EnableQoE: True</span><span class="sxs-lookup"><span data-stu-id="cfc99-263">EnableQoE : True</span></span>

<span data-ttu-id="cfc99-264">현재 CDR 설정을 기본 CDR 설정과 비교 하려면 다음 명령을 실행 하 여 기본값을 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc99-264">If you want to compare your current CDR settings with the default CDR settings, the default values can be reviewed by running this command:</span></span>

`New-CsCdrConfiguration -Identity "Global" -InMemory`

<span data-ttu-id="cfc99-265">마찬가지로, 다음 명령을 사용 하 여 QoE 모니터링에 대 한 기본값을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc99-265">Likewise, the default values for QoE monitoring can be retrieved by using this command:</span></span>

`New-CsQoEConfiguration -Identity "Global" -InMemory`

<span data-ttu-id="cfc99-266">다음 명령을 실행 하 여 모니터링 서버의 FQDN을 반환할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc99-266">You can also return the FQDN of your Monitoring servers by running this command:</span></span>

`Get-CsService -MonitoringServer`

</div>

<div>

## <a name="check-voice-settings"></a><span data-ttu-id="cfc99-267">음성 설정 확인</span><span class="sxs-lookup"><span data-stu-id="cfc99-267">Check voice settings</span></span>

<span data-ttu-id="cfc99-268">음성 정책에는 보통 관리자에 게 중요 한 음성 설정 및 음성 경로에 포함 됩니다. 음성 정책은 개별 사용자에 게 제공 되는 기능 (예: 통화 전달 또는 전송 기능)을 결정 하는 설정을 포함 하 고, 음성 경로는 통화 (및 인 경우)를 PSTN을 통해 라우팅하는 방법을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc99-268">The voice settings typically important to administrators are contained in voice policies and voice routes: voice policies contain the settings that determine the capabilities exposed to individual users (such as the ability to forward or transfer calls), while voice routes determine how (and if) calls are routed across the PSTN.</span></span>

<span data-ttu-id="cfc99-269">음성 정책 정보는 Windows PowerShell을 사용 하 여 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc99-269">Voice policy information can be retrieved by using Windows PowerShell.</span></span> <span data-ttu-id="cfc99-270">예를 들어 다음 명령은 전역 음성 정책에 대 한 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc99-270">For example, this command returns information about the global voice policy:</span></span>

`Get-CsVoicePolicy -Identity "Global"`

<span data-ttu-id="cfc99-271">그리고이 명령은 조직에서 사용 하도록 구성 된 모든 음성 정책에 대 한 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc99-271">And this command returns information about all the voice policies configured for use in the organization:</span></span>

`Get-CsVoicePolicy`

<span data-ttu-id="cfc99-272">Get-CsVoicePolicy cmdlet이 반환 하는 정보는 다음과 유사 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc99-272">The information returned by the Get-CsVoicePolicy cmdlet resembles the following:</span></span>

<span data-ttu-id="cfc99-273">Id: Global</span><span class="sxs-lookup"><span data-stu-id="cfc99-273">Identity : Global</span></span>

<span data-ttu-id="cfc99-274">PstnUsages {}</span><span class="sxs-lookup"><span data-stu-id="cfc99-274">PstnUsages : {}</span></span>

<span data-ttu-id="cfc99-275">설명이</span><span class="sxs-lookup"><span data-stu-id="cfc99-275">Description :</span></span>

<span data-ttu-id="cfc99-276">AllowSimulRing: True</span><span class="sxs-lookup"><span data-stu-id="cfc99-276">AllowSimulRing : True</span></span>

<span data-ttu-id="cfc99-277">AllowCallForwarding 전환: True</span><span class="sxs-lookup"><span data-stu-id="cfc99-277">AllowCallForwarding : True</span></span>

<span data-ttu-id="cfc99-278">AllowPSTNReRouting: True</span><span class="sxs-lookup"><span data-stu-id="cfc99-278">AllowPSTNReRouting : True</span></span>

<span data-ttu-id="cfc99-279">이름: DefaultPolicy</span><span class="sxs-lookup"><span data-stu-id="cfc99-279">Name : DefaultPolicy</span></span>

<span data-ttu-id="cfc99-280">EnableDelegation: True</span><span class="sxs-lookup"><span data-stu-id="cfc99-280">EnableDelegation : True</span></span>

<span data-ttu-id="cfc99-281">EnableTeamCall: True</span><span class="sxs-lookup"><span data-stu-id="cfc99-281">EnableTeamCall : True</span></span>

<span data-ttu-id="cfc99-282">EnableCallTransfer: True</span><span class="sxs-lookup"><span data-stu-id="cfc99-282">EnableCallTransfer : True</span></span>

<span data-ttu-id="cfc99-283">EnableCallPark: False</span><span class="sxs-lookup"><span data-stu-id="cfc99-283">EnableCallPark : False</span></span>

<span data-ttu-id="cfc99-284">EnableMaliciousCallTracing: False</span><span class="sxs-lookup"><span data-stu-id="cfc99-284">EnableMaliciousCallTracing : False</span></span>

<span data-ttu-id="cfc99-285">EnableBWPolicyOverride: False</span><span class="sxs-lookup"><span data-stu-id="cfc99-285">EnableBWPolicyOverride : False</span></span>

<span data-ttu-id="cfc99-286">PreventPSTNTollBypass: False</span><span class="sxs-lookup"><span data-stu-id="cfc99-286">PreventPSTNTollBypass : False</span></span>

<span data-ttu-id="cfc99-287">음성 정책의 하위 집합을 반환 하는 쿼리를 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc99-287">You can also create queries that returned a subset of your voice policies.</span></span> <span data-ttu-id="cfc99-288">예를 들어 다음 명령은 착신 전환을 허용 하는 모든 음성 정책을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc99-288">For example, this command returns all the voice policies that allow call forwarding:</span></span>

`Get-CsVoicePolicy | Where-Object {$_.AllowCallForwarding -eq $True}`

<span data-ttu-id="cfc99-289">그리고이 명령은 착신 전환을 허용 하지 않는 모든 음성 정책을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc99-289">And this command returns all the voice policies that don’t allow call forwarding:</span></span>

`Get-CsVoicePolicy | Where-Object {$_.AllowCallForwarding -eq $False}`

<span data-ttu-id="cfc99-290">Windows PowerShell에서 Get-CsVoiceRouting cmdlet을 사용 하 여 음성 경로에 대 한 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc99-290">In Windows PowerShell, use the Get-CsVoiceRouting cmdlet to return information about your voice routes:</span></span>

`Get-CsVoiceRoute`

<span data-ttu-id="cfc99-291">이 명령은 모든 음성 경로에 대 한 다음과 같은 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc99-291">That command returns information such as this for all the voice routes:</span></span>

<span data-ttu-id="cfc99-292">Identity: LocalRoute</span><span class="sxs-lookup"><span data-stu-id="cfc99-292">Identity : LocalRoute</span></span>

<span data-ttu-id="cfc99-293">우선 순위: 0</span><span class="sxs-lookup"><span data-stu-id="cfc99-293">Priority : 0</span></span>

<span data-ttu-id="cfc99-294">설명이</span><span class="sxs-lookup"><span data-stu-id="cfc99-294">Description :</span></span>

<span data-ttu-id="cfc99-295">번호 패턴: ^ ( \\ + 1 \[ 0-9 \] {10} ) $</span><span class="sxs-lookup"><span data-stu-id="cfc99-295">NumberPattern : ^(\\+1\[0-9\]{10})$</span></span>

<span data-ttu-id="cfc99-296">PstnUsages {}</span><span class="sxs-lookup"><span data-stu-id="cfc99-296">PstnUsages : {}</span></span>

<span data-ttu-id="cfc99-297">PstnGatewayList {}</span><span class="sxs-lookup"><span data-stu-id="cfc99-297">PstnGatewayList : {}</span></span>

<span data-ttu-id="cfc99-298">이름: LocalRoute</span><span class="sxs-lookup"><span data-stu-id="cfc99-298">Name : LocalRoute</span></span>

<span data-ttu-id="cfc99-299">SuppressCallerId</span><span class="sxs-lookup"><span data-stu-id="cfc99-299">SuppressCallerId :</span></span>

<span data-ttu-id="cfc99-300">AlternateCallerId</span><span class="sxs-lookup"><span data-stu-id="cfc99-300">AlternateCallerId :</span></span>

<span data-ttu-id="cfc99-301">Lync Server에서는 PSTN을 사용 하지 않고 PSTN 게이트웨이를 지정 하지 않는 음성 경로를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc99-301">Lync Server allows you to create voice routes that do not have a PSTN usage and do not specify a PSTN gateway.</span></span> <span data-ttu-id="cfc99-302">그러나 이러한 두 가지 속성 값이 구성 되지 않은 음성 경로에 대 한 통화는 실제로 라우팅할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc99-302">However, you can't actually route calls over a voice route that does not have these two property values configured.</span></span> <span data-ttu-id="cfc99-303">따라서 PSTN 사용량이 없는 음성 경로의 id를 반환 하는이 명령을 주기적으로 실행 하는 것이 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc99-303">Because of that, you might find it useful to periodically run this command, which returns the identity of any voice route that does not have a PSTN usage:</span></span>

`Get-CsVoiceRoute | Where-Object {$_.PstnUsages -eq $Null} | Select-Object Identity`

<span data-ttu-id="cfc99-304">마찬가지로이 명령은 PSTN 게이트웨이를 갖도록 구성 되지 않은 모든 음성 경로의 id를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc99-304">Similarly, this command returns the identity of any voice route that has not been configured to have a PSTN gateway:</span></span>

`Get-CsVoiceRoute | Where-Object {$_.PstnGatewayList -eq $Null}} | Select-Object Identity`

</div>

<div>

## <a name="check-conferencing-attendant-settings"></a><span data-ttu-id="cfc99-305">회의 전화 교환 설정 확인</span><span class="sxs-lookup"><span data-stu-id="cfc99-305">Check Conferencing Attendant settings</span></span>

<span data-ttu-id="cfc99-306">PSTN 전화 접속 회의에 대 한 회의 전화 교환 설정을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc99-306">Check conferencing Attendant settings for PSTN dial-in conferencing.</span></span> <span data-ttu-id="cfc99-307">회의 전화 교환 설정은 **get-csdialinconferencingconfiguration** cmdlet을 사용 해야만 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc99-307">Conferencing Attendant settings can only be retrieved by using the **Get-CsDialInConferencingConfiguration** cmdlet.</span></span> <span data-ttu-id="cfc99-308">이 설정은 Lync Server 제어판에서는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc99-308">These settings are not available in the Lync Server Control Panel.</span></span> <span data-ttu-id="cfc99-309">회의 전화 교환 설정을 보려면 다음과 같은 Windows PowerShell 명령을 사용 하 여 회의 전화 교환 설정의 전역 컬렉션을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc99-309">To view your Conferencing Attendant settings, use a Windows PowerShell command similar to the following, which returns the global collection of Conferencing Attendant settings:</span></span>

`Get-CsDialInConferencingConfiguration -Identity "Global"`

<span data-ttu-id="cfc99-310">사이트 범위에서 회의 전화 교환 설정을 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc99-310">Note that Conferencing Attendant settings can also be configured at the site scope.</span></span> <span data-ttu-id="cfc99-311">모든 회의 전화 교환 설정에 대 한 정보를 반환 하려면 대신 다음 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc99-311">To return information about all the Conferencing Attendant settings, use this command instead:</span></span>

`Get-CsDialInConferencingConfiguration`

<span data-ttu-id="cfc99-312">Get-CsDialInConferencingConfiguration cmdlet은 다음과 같은 데이터를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc99-312">The Get-CsDialInConferencingConfiguration cmdlet returns data similar to this:</span></span>

<span data-ttu-id="cfc99-313">Id: Global</span><span class="sxs-lookup"><span data-stu-id="cfc99-313">Identity : Global</span></span>

<span data-ttu-id="cfc99-314">EntryExitAnnouncementsType: UseNames</span><span class="sxs-lookup"><span data-stu-id="cfc99-314">EntryExitAnnouncementsType : UseNames</span></span>

<span data-ttu-id="cfc99-315">EnableNameRecording: True</span><span class="sxs-lookup"><span data-stu-id="cfc99-315">EnableNameRecording : True</span></span>

<span data-ttu-id="cfc99-316">EntryExitAnnouncementsEnabledByDefault: False</span><span class="sxs-lookup"><span data-stu-id="cfc99-316">EntryExitAnnouncementsEnabledByDefault : False</span></span>

<span data-ttu-id="cfc99-317">EntryExitAnnouncementsEnabledByDefault가 False로 설정 되 면 회의 알림이 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc99-317">If EntryExitAnnouncementsEnabledByDefault is set to False, that means the conferencing announcements are disabled.</span></span> <span data-ttu-id="cfc99-318">항목 및 종료 알림을 사용 하도록 설정 하려면 다음과 같은 Windows PowerShell 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc99-318">To enable entry and exit announcements, run a Windows PowerShell command similar to this:</span></span>

`Set-CsDialInConferencingConfiguration -Identity "Global" -EntryExitAnnouncementsEnabledByDefault $True`

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="cfc99-319">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cfc99-319">See Also</span></span>


[<span data-ttu-id="cfc99-320">New-cssipdomain</span><span class="sxs-lookup"><span data-stu-id="cfc99-320">Get-CsSipDomain</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsSipDomain)  
[<span data-ttu-id="cfc99-321">Get-csmeetingconfiguration</span><span class="sxs-lookup"><span data-stu-id="cfc99-321">Get-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingConfiguration)  
[<span data-ttu-id="cfc99-322">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="cfc99-322">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[<span data-ttu-id="cfc99-323">Set-csaccessedgeconfiguration</span><span class="sxs-lookup"><span data-stu-id="cfc99-323">Get-CsAccessEdgeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAccessEdgeConfiguration)  
[<span data-ttu-id="cfc99-324">Get-csexternalaccesspolicy</span><span class="sxs-lookup"><span data-stu-id="cfc99-324">Get-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[<span data-ttu-id="cfc99-325">Get-csarchivingconfiguration</span><span class="sxs-lookup"><span data-stu-id="cfc99-325">Get-CsArchivingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsArchivingConfiguration)  
[<span data-ttu-id="cfc99-326">Get-cscdrconfiguration</span><span class="sxs-lookup"><span data-stu-id="cfc99-326">Get-CsCdrConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCdrConfiguration)  
[<span data-ttu-id="cfc99-327">Remove-csqoeconfiguration</span><span class="sxs-lookup"><span data-stu-id="cfc99-327">Get-CsQoEConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsQoEConfiguration)  
[<span data-ttu-id="cfc99-328">Set-csvoicepolicy</span><span class="sxs-lookup"><span data-stu-id="cfc99-328">Get-CsVoicePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicePolicy)  
[<span data-ttu-id="cfc99-329">Get-csvoiceroute</span><span class="sxs-lookup"><span data-stu-id="cfc99-329">Get-CsVoiceRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsVoiceRoute)  
[<span data-ttu-id="cfc99-330">Get-csdialinconferencingconfiguration</span><span class="sxs-lookup"><span data-stu-id="cfc99-330">Get-CsDialInConferencingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsDialInConferencingConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

