---
title: 'Lync Server 2013: cmdlet 인덱스'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2013 cmdlets index
ms:assetid: cd37aba7-3d27-4db9-b69f-3a6da1fb4b4a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398867(v=OCS.15)
ms:contentKeyID: 48185661
ms.date: 04/12/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2770c8da4b990cf1a1c7ab7f276d33b72b10878b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42209344"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-cmdlets-index"></a>Lync Server 2013 cmdlet 인덱스

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2016-04-12_

Microsoft Lync Server 2013에는 관리자가 명령줄에서 Lync Server 2013을 관리 하도록 해 주는 700 cmdlet이 더 이상 제공 됩니다. Lync Server cmdlet은 일반적으로 Lync Server 관리 셸에서 사용 됩니다. Lync server 관리 셸을 사용 하는 한 가지 방법은 Lync Server 서비스 또는 서버 역할을 실행 하는 컴퓨터에 로그온 하 고 **시작**, **모든 프로그램**, **Microsoft lync server 2013**을 차례로 클릭 한 다음 **Lync server 관리 셸을**클릭 하는 것입니다. 관리 셸이 열린 후에는 다음과 같은 명령을 입력 하 여 명령줄에서 직접 cmdlet에 대 한 도움말을 검색할 수 있습니다.

    Get-Help New-CsVoicePolicy -Full

위 명령은 **set-csvoicepolicy** cmdlet에 사용할 수 있는 전체 도움말을 검색 합니다. 다른 cmdlet에 대 한 도움말을 보려면 **set-csvoicepolicy** 를 도움말을 검색 하려는 cmdlet의 이름으로 바꿉니다.

Lync Server 관리에 사용할 수 있는 전체 cmdlet 목록을 검색 하려면 Lync Server 관리 셸 명령 프롬프트에 다음을 입력 합니다.

    Get-Command * -Module Lync -CommandType cmdlet

Lync Server 관리 셸을 사용 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 [https://go.microsoft.com/fwlink/p/?linkId=203150](https://go.microsoft.com/fwlink/p/?linkid=203150)를 참조 하세요.

<div>

## <a name="lync-server-2013-cmdlets"></a>Lync Server 2013 Cmdlet

다음은 Lync Server 2013와 함께 제공 되는 cmdlet 목록입니다.

  - [CsSlaDelegates 추가](https://technet.microsoft.com/library/Mt703199(v=OCS.15))

  - [승인-Get-csdeviceupdaterule](https://technet.microsoft.com/library/Gg398949(v=OCS.15))

  - [백업-CsPool](https://technet.microsoft.com/library/JJ204955(v=OCS.15))

  - [일반-CsDeviceUpdateFile](https://technet.microsoft.com/library/Gg425835(v=OCS.15))

  - [일반-CsDeviceUpdateLog](https://technet.microsoft.com/library/Gg412738(v=OCS.15))

  - [일반-Clear-cspersistentchatroom](https://technet.microsoft.com/library/JJ204976(v=OCS.15))

  - [변환-CsUserData](https://technet.microsoft.com/library/JJ205337(v=OCS.15))

  - [디버그-CsAddressBookReplication](https://technet.microsoft.com/library/JJ205232(v=OCS.15))

  - [Debug-csintrapoolreplication](https://technet.microsoft.com/library/JJ205103(v=OCS.15))

  - [Export-cslisconfiguration](https://technet.microsoft.com/library/Gg398710(v=OCS.15))

  - [사용 안 함-CsAdDomain](https://technet.microsoft.com/library/Gg398785(v=OCS.15))

  - [사용 안 함-CsAdForest](https://technet.microsoft.com/library/Gg398122(v=OCS.15))

  - [사용 안 함-CsComputer](https://technet.microsoft.com/library/Gg399023(v=OCS.15))

  - [사용 안 함-CsHostingProvider](https://technet.microsoft.com/library/Gg398481(v=OCS.15))

  - [사용 안 함-Enable-csmeetingroom](https://technet.microsoft.com/library/JJ204723(v=OCS.15))

  - [사용 안 함-Disable-cspublicprovider](https://technet.microsoft.com/library/Gg398984(v=OCS.15))

  - [사용 안 함-CsUser](https://technet.microsoft.com/library/Gg398747(v=OCS.15))

  - [Enable-CsAdDomain](https://technet.microsoft.com/library/Gg412764(v=OCS.15))

  - [Enable-CsAdForest](https://technet.microsoft.com/library/Gg425713(v=OCS.15))

  - [사용-CsComputer](https://technet.microsoft.com/library/Gg412815(v=OCS.15))

  - [Enable-CsHostingProvider](https://technet.microsoft.com/library/Gg398166(v=OCS.15))

  - [Enable-Enable-csmeetingroom](https://technet.microsoft.com/library/JJ205062(v=OCS.15))

  - [Enable-Disable-cspublicprovider](https://technet.microsoft.com/library/Gg398780(v=OCS.15))

  - [사용-CsReplica](https://technet.microsoft.com/library/Gg425965(v=OCS.15))

  - [Enable-Enable-cstopology](https://technet.microsoft.com/library/Gg398398(v=OCS.15))

  - [Enable-CsUser](https://technet.microsoft.com/library/Gg398711(v=OCS.15))

  - [Export-csarchivingdata](https://technet.microsoft.com/library/Gg398452(v=OCS.15))

  - [수출-CsConfiguration](https://technet.microsoft.com/library/Gg398627(v=OCS.15))

  - [Export-cslisconfiguration](https://technet.microsoft.com/library/Gg398539(v=OCS.15))

  - [Export-cspersistentchatdata](https://technet.microsoft.com/library/JJ205378(v=OCS.15))

  - [Export-csrgsconfiguration](https://technet.microsoft.com/library/JJ205011(v=OCS.15))

  - [수출-CsUserData](https://technet.microsoft.com/library/JJ204897(v=OCS.15))

  - [Set-csaccessedgeconfiguration](https://technet.microsoft.com/library/Gg398574(v=OCS.15))

  - [Get-CsAdContact](https://technet.microsoft.com/library/Gg412776(v=OCS.15))

  - [Get-CsAdDomain](https://technet.microsoft.com/library/Gg398453(v=OCS.15))

  - [Get-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398132(v=OCS.15))

  - [Get-CsAdForest](https://technet.microsoft.com/library/Gg412995(v=OCS.15))

  - [Get-CsAdminRole](https://technet.microsoft.com/library/Gg399050(v=OCS.15))

  - [Get-CsAdminRoleAssignment](https://technet.microsoft.com/library/Gg398434(v=OCS.15))

  - [Get-CsAdPrincipal](https://technet.microsoft.com/library/JJ205326(v=OCS.15))

  - [Get-CsAdServerSchema](https://technet.microsoft.com/library/Gg413070(v=OCS.15))

  - [Get-CsAdUser](https://technet.microsoft.com/library/Gg398592(v=OCS.15))

  - [Get-CsAllowedDomain](https://technet.microsoft.com/library/Gg398164(v=OCS.15))

  - [Move-csanalogdevice](https://technet.microsoft.com/library/Gg398748(v=OCS.15))

  - [Get-CsAnnouncement](https://technet.microsoft.com/library/Gg398937(v=OCS.15))

  - [Get-CsApplicationEndpoint](https://technet.microsoft.com/library/Gg398655(v=OCS.15))

  - [Get-csarchivingconfiguration](https://technet.microsoft.com/library/Gg399012(v=OCS.15))

  - [Grant-csarchivingpolicy](https://technet.microsoft.com/library/Gg425731(v=OCS.15))

  - [Get-CsAudioTestServiceApplication](https://technet.microsoft.com/library/Gg412984(v=OCS.15))

  - [Get-csautodiscoverconfiguration](https://technet.microsoft.com/library/Hh690014(v=OCS.15))

  - [Get-csavedgeconfiguration](https://technet.microsoft.com/library/Gg413008(v=OCS.15))

  - [Get-csbackupserviceconfiguration](https://technet.microsoft.com/library/JJ205087(v=OCS.15))

  - [Get-csbackupservicestatus](https://technet.microsoft.com/library/JJ205032(v=OCS.15))

  - [CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/library/Gg412727(v=OCS.15))

  - [Get-csblockeddomain](https://technet.microsoft.com/library/Gg398424(v=OCS.15))

  - [Get-cscallparkorbit](https://technet.microsoft.com/library/Gg398554(v=OCS.15))

  - [Get-cscdrconfiguration](https://technet.microsoft.com/library/Gg398298(v=OCS.15))

  - [Set-cscertificate](https://technet.microsoft.com/library/Gg398227(v=OCS.15))

  - [Get-CsClientAccessLicense](https://technet.microsoft.com/library/JJ204853(v=OCS.15))

  - [Get-csclientcertificate](https://technet.microsoft.com/library/Gg398143(v=OCS.15))

  - [Get-CsClientPinInfo](https://technet.microsoft.com/library/Gg425947(v=OCS.15))

  - [Get-CsClientPolicy](https://technet.microsoft.com/library/Gg398830(v=OCS.15))

  - [Get-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg399072(v=OCS.15))

  - [Get-CsClientVersionPolicy](https://technet.microsoft.com/library/Gg398957(v=OCS.15))

  - [Get-CsClientVersionPolicyRule](https://technet.microsoft.com/library/Gg413048(v=OCS.15))

  - [Get-CsClsRegion](https://technet.microsoft.com/library/JJ204879(v=OCS.15))

  - [Get-CsClsSearchTerm](https://technet.microsoft.com/library/JJ205061(v=OCS.15))

  - [Get-CsClsScenario](https://technet.microsoft.com/library/JJ205091(v=OCS.15))

  - [Get-CsClsSecurityGroup](https://technet.microsoft.com/library/JJ205285(v=OCS.15))

  - [Move-cscommonareaphone](https://technet.microsoft.com/library/Gg412934(v=OCS.15))

  - [온-CsComputer](https://technet.microsoft.com/library/Gg425959(v=OCS.15))

  - [Get-csconferencedirectory](https://technet.microsoft.com/library/Gg425771(v=OCS.15))

  - [Get-csconferencedisclaimer](https://technet.microsoft.com/library/Gg425714(v=OCS.15))

  - [Get-csconferencingconfiguration](https://technet.microsoft.com/library/Gg398965(v=OCS.15))

  - [Get-csconferencingpolicy](https://technet.microsoft.com/library/Gg398293(v=OCS.15))

  - [Remove-csconfigurationstorelocation](https://technet.microsoft.com/library/Gg412814(v=OCS.15))

  - [New-cscpsconfiguration](https://technet.microsoft.com/library/Gg398948(v=OCS.15))

  - [Get-csdatabasemirrorstate](https://technet.microsoft.com/library/JJ204845(v=OCS.15))

  - [New-csdeviceupdateconfiguration](https://technet.microsoft.com/library/Gg399030(v=OCS.15))

  - [Get-csdeviceupdaterule](https://technet.microsoft.com/library/Gg398215(v=OCS.15))

  - [Get-csdiagnosticconfiguration](https://technet.microsoft.com/library/Gg413034(v=OCS.15))

  - [Get-csdiagnosticheaderconfiguration](https://technet.microsoft.com/library/Gg412774(v=OCS.15))

  - [Get-csdialinconferencingaccessnumber](https://technet.microsoft.com/library/Gg413015(v=OCS.15))

  - [Get-csdialinconferencingconfiguration](https://technet.microsoft.com/library/Gg398575(v=OCS.15))

  - [Set-csdialinconferencingdtmfconfiguration](https://technet.microsoft.com/library/Gg398578(v=OCS.15))

  - [Get-csdialinconferencinglanguagelist](https://technet.microsoft.com/library/Gg425869(v=OCS.15))

  - [Get-CsDialPlan 플랜](https://technet.microsoft.com/library/Gg413043(v=OCS.15))

  - [Get-cseffectivepolicy](https://technet.microsoft.com/library/JJ204636(v=OCS.15))

  - [CsEnhancedEmergencyServiceDisclaimer](https://technet.microsoft.com/library/Gg412877(v=OCS.15))

  - [Get-csexternalaccesspolicy](https://technet.microsoft.com/library/Gg425805(v=OCS.15))

  - [Get-CsExUmContact](https://technet.microsoft.com/library/Gg412725(v=OCS.15))

  - [CsFileTransferFilterConfiguration](https://technet.microsoft.com/library/Gg398527(v=OCS.15))

  - [Get-CsFIPSConfiguration](https://technet.microsoft.com/library/JJ204904(v=OCS.15))

  - [Get-cshealthmonitoringconfiguration](https://technet.microsoft.com/library/Gg398667(v=OCS.15))

  - [Set-cshostedvoicemailpolicy](https://technet.microsoft.com/library/Gg398348(v=OCS.15))

  - [Get-CsHostingProvider](https://technet.microsoft.com/library/Gg413078(v=OCS.15))

  - [Get-CsImFilterConfiguration](https://technet.microsoft.com/library/Gg398980(v=OCS.15))

  - [Get-cskerberosaccountassignment](https://technet.microsoft.com/library/Gg398526(v=OCS.15))

  - [Test-csliscivicaddress](https://technet.microsoft.com/library/Gg398459(v=OCS.15))

  - [Get-cslislocation](https://technet.microsoft.com/library/Gg412834(v=OCS.15))

  - [CsLisPort](https://technet.microsoft.com/library/Gg398820(v=OCS.15))

  - [CsLisServiceProvider](https://technet.microsoft.com/library/Gg398116(v=OCS.15))

  - [CsLisSubnet](https://technet.microsoft.com/library/Gg398473(v=OCS.15))

  - [CsLisSwitch](https://technet.microsoft.com/library/Gg425769(v=OCS.15))

  - [CsLisWirelessAccessPoint](https://technet.microsoft.com/library/Gg398117(v=OCS.15))

  - [Get-CsLocationPolicy](https://technet.microsoft.com/library/Gg398911(v=OCS.15))

  - [Get-CsManagementConnection](https://technet.microsoft.com/library/Gg412849(v=OCS.15))

  - [Get-csmanagementstorereplicationstatus](https://technet.microsoft.com/library/Gg399052(v=OCS.15))

  - [Get-CsMcxConfiguration](https://technet.microsoft.com/library/Hh690031(v=OCS.15))

  - [Get-csmediaconfiguration](https://technet.microsoft.com/library/Gg398128(v=OCS.15))

  - [Get-csmeetingconfiguration](https://technet.microsoft.com/library/Gg425875(v=OCS.15))

  - [Enable-csmeetingroom](https://technet.microsoft.com/library/JJ205277(v=OCS.15))

  - [Get-csmobilitypolicy](https://technet.microsoft.com/library/Hh690017(v=OCS.15))

  - [Get-csnetworkbandwidthpolicyprofile](https://technet.microsoft.com/library/Gg425815(v=OCS.15))

  - [Get-csnetworkconfiguration](https://technet.microsoft.com/library/Gg398140(v=OCS.15))

  - [Get-csnetworkinterface](https://technet.microsoft.com/library/Gg398121(v=OCS.15))

  - [Get-Csnetworkinterroute](https://technet.microsoft.com/library/Gg425817(v=OCS.15))

  - [Remove-csnetworkintersitepolicy](https://technet.microsoft.com/library/Gg412769(v=OCS.15))

  - [Get-CsNetworkRegion](https://technet.microsoft.com/library/Gg398406(v=OCS.15))

  - [Get-Csnetwork지역 링크](https://technet.microsoft.com/library/Gg398972(v=OCS.15))

  - [Get-CsNetworkSite](https://technet.microsoft.com/library/Gg398766(v=OCS.15))

  - [Get-CsNetworkSubnet](https://technet.microsoft.com/library/Gg412825(v=OCS.15))

  - [Get-CsOAuthConfiguration](https://technet.microsoft.com/library/JJ205155(v=OCS.15))

  - [Get-CsOAuthServer](https://technet.microsoft.com/library/JJ205238(v=OCS.15))

  - [Get-csoutboundcallingnumbertranslationrule](https://technet.microsoft.com/library/JJ204962(v=OCS.15))

  - [New-csoutboundtranslationrule](https://technet.microsoft.com/library/Gg398104(v=OCS.15))

  - [Get-cspartnerapplication](https://technet.microsoft.com/library/JJ205128(v=OCS.15))

  - [Get-cspersistentchataddin](https://technet.microsoft.com/library/JJ204670(v=OCS.15))

  - [Get-cspersistentchatcategory](https://technet.microsoft.com/library/JJ204771(v=OCS.15))

  - [Get-cspersistentchatcomplianceconfiguration](https://technet.microsoft.com/library/JJ204625(v=OCS.15))

  - [Get-cspersistentchatconfiguration](https://technet.microsoft.com/library/JJ205140(v=OCS.15))

  - [Get-cspersistentchateligibleprincipal](https://technet.microsoft.com/library/JJ204891(v=OCS.15))

  - [Get-cspersistentchatendpoint](https://technet.microsoft.com/library/JJ204764(v=OCS.15))

  - [Grant-cspersistentchatpolicy](https://technet.microsoft.com/library/JJ204673(v=OCS.15))

  - [Clear-cspersistentchatroom](https://technet.microsoft.com/library/JJ205123(v=OCS.15))

  - [Set-cspersistentchatstate](https://technet.microsoft.com/library/JJ204915(v=OCS.15))

  - [Get-cspinpolicy](https://technet.microsoft.com/library/Gg398262(v=OCS.15))

  - [Get-CsPool](https://technet.microsoft.com/library/Gg398992(v=OCS.15))

  - [Get-cspoolbackuprelationship](https://technet.microsoft.com/library/JJ204745(v=OCS.15))

  - [Get-cspoolupgradereadinessstate](https://technet.microsoft.com/library/JJ204689(v=OCS.15))

  - [Get-cspresencepolicy](https://technet.microsoft.com/library/Gg398463(v=OCS.15))

  - [Remove-cspresenceprovider](https://technet.microsoft.com/library/JJ204705(v=OCS.15))

  - [Get-csprivacyconfiguration](https://technet.microsoft.com/library/Gg413002(v=OCS.15))

  - [Get-CsProxyConfiguration](https://technet.microsoft.com/library/Gg399011(v=OCS.15))

  - [G-CsPstnUsage 사용](https://technet.microsoft.com/library/Gg412734(v=OCS.15))

  - [Disable-cspublicprovider](https://technet.microsoft.com/library/Gg412945(v=OCS.15))

  - [Get-cspushnotificationconfiguration](https://technet.microsoft.com/library/Hh690049(v=OCS.15))

  - [Remove-csqoeconfiguration](https://technet.microsoft.com/library/Gg399004(v=OCS.15))

  - [Get-csregistrarconfiguration](https://technet.microsoft.com/library/Gg398483(v=OCS.15))

  - [Get-csreportingconfiguration](https://technet.microsoft.com/library/JJ205356(v=OCS.15))

  - [Get-csrgsagentgroup](https://technet.microsoft.com/library/Gg425793(v=OCS.15))

  - [Export-csrgsconfiguration](https://technet.microsoft.com/library/Gg412762(v=OCS.15))

  - [New-csrgsholidayset](https://technet.microsoft.com/library/Gg412983(v=OCS.15))

  - [Get-csrgshoursofbusiness](https://technet.microsoft.com/library/Gg398284(v=OCS.15))

  - [Get-csrgsqueue](https://technet.microsoft.com/library/Gg412759(v=OCS.15))

  - [Get-csrgsworkflow](https://technet.microsoft.com/library/Gg425766(v=OCS.15))

  - [Get-CsRoutingConfiguration](https://technet.microsoft.com/library/Gg425851(v=OCS.15))

  - [Get-CsServerApplication](https://technet.microsoft.com/library/Gg425948(v=OCS.15))

  - [Get-CsServerVersion](https://technet.microsoft.com/library/Gg398470(v=OCS.15))

  - [Get-CsService](https://technet.microsoft.com/library/Gg413038(v=OCS.15))

  - [Get-cssimpleurlconfiguration](https://technet.microsoft.com/library/Gg398392(v=OCS.15))

  - [New-cssipdomain](https://technet.microsoft.com/library/Gg398701(v=OCS.15))

  - [Get-cssipresponsecodetranslationrule](https://technet.microsoft.com/library/Gg398130(v=OCS.15))

  - [CsSlaConfiguration](https://technet.microsoft.com/library/Mt703200(v=OCS.15))

  - [Get-CsSite](https://technet.microsoft.com/library/Gg398185(v=OCS.15))

  - [Get-CsStaticRoutingConfiguration](https://technet.microsoft.com/library/Gg398754(v=OCS.15))

  - [Get-CsTestDevice](https://technet.microsoft.com/library/Gg398304(v=OCS.15))

  - [Get-cstestusercredential](https://technet.microsoft.com/library/JJ204759(v=OCS.15))

  - [Enable-cstopology](https://technet.microsoft.com/library/Gg412824(v=OCS.15))

  - [Get-cstrunk](https://technet.microsoft.com/library/JJ205244(v=OCS.15))

  - [Get-cstrunkconfiguration](https://technet.microsoft.com/library/Gg398224(v=OCS.15))

  - [New-cstrustedapplication](https://technet.microsoft.com/library/Gg399025(v=OCS.15))

  - [CsTrustedApplicationComputer](https://technet.microsoft.com/library/Gg425843(v=OCS.15))

  - [CsTrustedApplicationEndpoint](https://technet.microsoft.com/library/Gg413035(v=OCS.15))

  - [New-cstrustedapplicationpool](https://technet.microsoft.com/library/Gg413055(v=OCS.15))

  - [Set-csucphoneconfiguration](https://technet.microsoft.com/library/Gg398070(v=OCS.15))

  - [Get-csuiculture](https://technet.microsoft.com/library/Gg412900(v=OCS.15))

  - [New-csunassignednumber](https://technet.microsoft.com/library/Gg412792(v=OCS.15))

  - [Get-CsUser](https://technet.microsoft.com/library/Gg398125(v=OCS.15))

  - [Get-CsUserAcp](https://technet.microsoft.com/library/Gg398978(v=OCS.15))

  - [Get-CsUserDatabaseState](https://technet.microsoft.com/library/Gg398831(v=OCS.15))

  - [Get-CsUserPoolInfo](https://technet.microsoft.com/library/Gg398615(v=OCS.15))

  - [Get-csuserreplicatorconfiguration](https://technet.microsoft.com/library/Gg398548(v=OCS.15))

  - [Get-Csuser서비스 구성](https://technet.microsoft.com/library/Gg398133(v=OCS.15))

  - [Get-Csuser서비스 정책](https://technet.microsoft.com/library/JJ204838(v=OCS.15))

  - [CsVoiceConfiguration](https://technet.microsoft.com/library/Gg398815(v=OCS.15))

  - [New-csvoicemailreroutingconfiguration](https://technet.microsoft.com/library/Gg425732(v=OCS.15))

  - [Get-csvoicenormalizationrule](https://technet.microsoft.com/library/Gg398393(v=OCS.15))

  - [Set-csvoicepolicy](https://technet.microsoft.com/library/Gg398101(v=OCS.15))

  - [Get-csvoiceroute](https://technet.microsoft.com/library/Gg425926(v=OCS.15))

  - [Get-csvoiceroutingpolicy](https://technet.microsoft.com/library/JJ204940(v=OCS.15))

  - [수정한 구성은 test-csvoicetestconfiguration](https://technet.microsoft.com/library/Gg412957(v=OCS.15))

  - [Get-cswatchernodeconfiguration](https://technet.microsoft.com/library/JJ204739(v=OCS.15))

  - [Set-cswebserviceconfiguration](https://technet.microsoft.com/library/Gg425751(v=OCS.15))

  - [Get-CsWindowsService](https://technet.microsoft.com/library/Gg398803(v=OCS.15))

  - [Get-CsXmppAllowedPartner](https://technet.microsoft.com/library/JJ204981(v=OCS.15))

  - [Get-CsXmppGatewayConfiguration](https://technet.microsoft.com/library/JJ204869(v=OCS.15))

  - [Grant-csarchivingpolicy](https://technet.microsoft.com/library/Gg398475(v=OCS.15))

  - [부여-CsClientPolicy](https://technet.microsoft.com/library/Gg412942(v=OCS.15))

  - [부여-CsClientVersionPolicy](https://technet.microsoft.com/library/Gg412903(v=OCS.15))

  - [Get-csconferencingpolicy](https://technet.microsoft.com/library/Gg425937(v=OCS.15))

  - [부여-CsDialPlan 플랜](https://technet.microsoft.com/library/Gg398547(v=OCS.15))

  - [Get-csexternalaccesspolicy](https://technet.microsoft.com/library/Gg425942(v=OCS.15))

  - [Set-cshostedvoicemailpolicy](https://technet.microsoft.com/library/Gg412829(v=OCS.15))

  - [부여-CsLocationPolicy](https://technet.microsoft.com/library/Gg413049(v=OCS.15))

  - [Get-csmobilitypolicy](https://technet.microsoft.com/library/Hh690038(v=OCS.15))

  - [부여-CsOUPermission](https://technet.microsoft.com/library/Gg425739(v=OCS.15))

  - [Grant-cspersistentchatpolicy](https://technet.microsoft.com/library/JJ204907(v=OCS.15))

  - [Get-cspinpolicy](https://technet.microsoft.com/library/Gg398871(v=OCS.15))

  - [Get-cspresencepolicy](https://technet.microsoft.com/library/Gg398571(v=OCS.15))

  - [부여-CsSetupPermission](https://technet.microsoft.com/library/Gg398569(v=OCS.15))

  - [부여-Csuser서비스 정책](https://technet.microsoft.com/library/JJ205388(v=OCS.15))

  - [Set-csvoicepolicy](https://technet.microsoft.com/library/Gg398828(v=OCS.15))

  - [Get-csvoiceroutingpolicy](https://technet.microsoft.com/library/JJ205141(v=OCS.15))

  - [경우 import-csannouncementfile](https://technet.microsoft.com/library/Gg398472(v=OCS.15))

  - [Set-cscertificate](https://technet.microsoft.com/library/Gg398688(v=OCS.15))

  - [가져오기-CsConfiguration](https://technet.microsoft.com/library/Gg398800(v=OCS.15))

  - [가져오기-CsDeviceUpdate](https://technet.microsoft.com/library/Gg398861(v=OCS.15))

  - [Import-cslegacyconferencedirectory](https://technet.microsoft.com/library/Gg398418(v=OCS.15))

  - [Import-cslegacyconfiguration](https://technet.microsoft.com/library/Gg412923(v=OCS.15))

  - [Export-cslisconfiguration](https://technet.microsoft.com/library/Gg398380(v=OCS.15))

  - [Export-cspersistentchatdata](https://technet.microsoft.com/library/JJ204709(v=OCS.15))

  - [Import-csrgsaudiofile](https://technet.microsoft.com/library/Gg412830(v=OCS.15))

  - [Export-csrgsconfiguration](https://technet.microsoft.com/library/JJ205245(v=OCS.15))

  - [가져오기-CsUserData](https://technet.microsoft.com/library/JJ205373(v=OCS.15))

  - [설치-CsAdServerSchema](https://technet.microsoft.com/library/Gg398681(v=OCS.15))

  - [설치-CsDatabase](https://technet.microsoft.com/library/Gg399044(v=OCS.15))

  - [설치-CsMirrorDatabase](https://technet.microsoft.com/library/JJ204986(v=OCS.15))

  - [Invoke-csarchivingdatabasepurge-를 호출 합니다.](https://technet.microsoft.com/library/JJ204627(v=OCS.15))

  - [Invoke-csbackupservicesync-를 호출 합니다.](https://technet.microsoft.com/library/JJ205374(v=OCS.15))

  - [Invoke-cscdrdatabasepurge-를 호출 합니다.](https://technet.microsoft.com/library/JJ205113(v=OCS.15))

  - [CsDatabaseFailover 조치 (failover)](https://technet.microsoft.com/library/JJ204744(v=OCS.15))

  - [-CsManagementServerFailover 조치 (failover)](https://technet.microsoft.com/library/JJ204647(v=OCS.15))

  - [Invoke-csmanagementstorereplication-를 호출 합니다.](https://technet.microsoft.com/library/Gg413060(v=OCS.15))

  - [Invoke-cspoolfailback-를 호출 합니다.](https://technet.microsoft.com/library/JJ204873(v=OCS.15))

  - [Initialize-cspoolfailover-를 호출 합니다.](https://technet.microsoft.com/library/JJ205189(v=OCS.15))

  - [-CsQoEDatabasePurge를 호출 합니다.](https://technet.microsoft.com/library/JJ205247(v=OCS.15))

  - [Invoke-csucsrollback-를 호출 합니다.](https://technet.microsoft.com/library/JJ204661(v=OCS.15))

  - [잠금-CsClientPin](https://technet.microsoft.com/library/Gg398650(v=OCS.15))

  - [병합-Merge-cslegacytopology](https://technet.microsoft.com/library/Gg425870(v=OCS.15))

  - [이동-Move-csanalogdevice](https://technet.microsoft.com/library/Gg398816(v=OCS.15))

  - [CsApplicationEndpoint 이동](https://technet.microsoft.com/library/Gg398188(v=OCS.15))

  - [이동-Move-cscommonareaphone](https://technet.microsoft.com/library/Gg412837(v=OCS.15))

  - [이동-Get-csconferencedirectory](https://technet.microsoft.com/library/Gg412968(v=OCS.15))

  - [이사-CsExUmContact](https://technet.microsoft.com/library/Gg425842(v=OCS.15))

  - [이동-Move-cslegacyuser](https://technet.microsoft.com/library/Gg413025(v=OCS.15))

  - [이동-Move-csmanagementserver](https://technet.microsoft.com/library/Gg412921(v=OCS.15))

  - [이동-Enable-csmeetingroom](https://technet.microsoft.com/library/JJ204889(v=OCS.15))

  - [이동-Export-csrgsconfiguration](https://technet.microsoft.com/library/Gg398782(v=OCS.15))

  - [CsUser 이동](https://technet.microsoft.com/library/Gg398528(v=OCS.15))

  - [새-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398395(v=OCS.15))

  - [새-CsAdminRole](https://technet.microsoft.com/library/Gg398271(v=OCS.15))

  - [새-CsAllowedDomain](https://technet.microsoft.com/library/Gg398628(v=OCS.15))

  - [Move-csanalogdevice](https://technet.microsoft.com/library/Gg412937(v=OCS.15))

  - [새 CsAnnouncement](https://technet.microsoft.com/library/Gg398522(v=OCS.15))

  - [Get-csarchivingconfiguration](https://technet.microsoft.com/library/Gg398471(v=OCS.15))

  - [Grant-csarchivingpolicy](https://technet.microsoft.com/library/Gg399032(v=OCS.15))

  - [Get-csautodiscoverconfiguration](https://technet.microsoft.com/library/Hh690022(v=OCS.15))

  - [Get-csavedgeconfiguration](https://technet.microsoft.com/library/Gg412884(v=OCS.15))

  - [CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/library/Gg398175(v=OCS.15))

  - [Get-csblockeddomain](https://technet.microsoft.com/library/Gg398822(v=OCS.15))

  - [Get-cscallparkorbit](https://technet.microsoft.com/library/Gg398936(v=OCS.15))

  - [Get-cscdrconfiguration](https://technet.microsoft.com/library/Gg399018(v=OCS.15))

  - [신규-CsClientPolicy](https://technet.microsoft.com/library/Gg425949(v=OCS.15))

  - [새-CsClientPolicyEntry](https://technet.microsoft.com/library/Gg399046(v=OCS.15))

  - [새-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg399029(v=OCS.15))

  - [새-CsClientVersionPolicy](https://technet.microsoft.com/library/Gg398709(v=OCS.15))

  - [새-CsClientVersionPolicyRule](https://technet.microsoft.com/library/Gg398905(v=OCS.15))

  - [새-CsClsRegion](https://technet.microsoft.com/library/JJ204658(v=OCS.15))

  - [새 CsClsScenario](https://technet.microsoft.com/library/JJ205022(v=OCS.15))

  - [새-CsClsSecurityGroup](https://technet.microsoft.com/library/JJ205359(v=OCS.15))

  - [Move-cscommonareaphone](https://technet.microsoft.com/library/Gg398430(v=OCS.15))

  - [Get-csconferencedirectory](https://technet.microsoft.com/library/Gg413080(v=OCS.15))

  - [Get-csconferencingconfiguration](https://technet.microsoft.com/library/Gg412967(v=OCS.15))

  - [Get-csconferencingpolicy](https://technet.microsoft.com/library/Gg413019(v=OCS.15))

  - [New-cscpsconfiguration](https://technet.microsoft.com/library/Gg412919(v=OCS.15))

  - [New-csdeviceupdateconfiguration](https://technet.microsoft.com/library/Gg425761(v=OCS.15))

  - [Get-csdiagnosticconfiguration](https://technet.microsoft.com/library/Gg398733(v=OCS.15))

  - [Get-csdiagnosticheaderconfiguration](https://technet.microsoft.com/library/Gg398350(v=OCS.15))

  - [New-csdiagnosticsfilter](https://technet.microsoft.com/library/Gg413009(v=OCS.15))

  - [Get-csdialinconferencingaccessnumber](https://technet.microsoft.com/library/Gg398818(v=OCS.15))

  - [Get-csdialinconferencingconfiguration](https://technet.microsoft.com/library/Gg412816(v=OCS.15))

  - [Set-csdialinconferencingdtmfconfiguration](https://technet.microsoft.com/library/Gg425792(v=OCS.15))

  - [새 CsDialPlan 플랜](https://technet.microsoft.com/library/Gg425860(v=OCS.15))

  - [New-csextendedtest](https://technet.microsoft.com/library/JJ205275(v=OCS.15))

  - [Get-csexternalaccesspolicy](https://technet.microsoft.com/library/Gg398441(v=OCS.15))

  - [새 전자 메일 주소](https://technet.microsoft.com/library/Gg398139(v=OCS.15))

  - [CsFileTransferFilterConfiguration](https://technet.microsoft.com/library/Gg425897(v=OCS.15))

  - [새-CsFIPSConfiguration](https://technet.microsoft.com/library/JJ205114(v=OCS.15))

  - [Get-cshealthmonitoringconfiguration](https://technet.microsoft.com/library/Gg398718(v=OCS.15))

  - [Set-cshostedvoicemailpolicy](https://technet.microsoft.com/library/Gg398653(v=OCS.15))

  - [새-CsHostingProvider](https://technet.microsoft.com/library/Gg398490(v=OCS.15))

  - [새-CsImFilterConfiguration](https://technet.microsoft.com/library/Gg398244(v=OCS.15))

  - [New-csissuedcertid](https://technet.microsoft.com/library/Gg425814(v=OCS.15))

  - [새-C고 Ercosaccount](https://technet.microsoft.com/library/Gg398485(v=OCS.15))

  - [Get-cskerberosaccountassignment](https://technet.microsoft.com/library/Gg398074(v=OCS.15))

  - [새-CsLocationPolicy](https://technet.microsoft.com/library/Gg398231(v=OCS.15))

  - [새-CsMcxConfiguration](https://technet.microsoft.com/library/Hh690035(v=OCS.15))

  - [Get-csmediaconfiguration](https://technet.microsoft.com/library/Gg425881(v=OCS.15))

  - [Get-csmeetingconfiguration](https://technet.microsoft.com/library/Gg398065(v=OCS.15))

  - [Get-csmobilitypolicy](https://technet.microsoft.com/library/Hh689987(v=OCS.15))

  - [Get-csnetworkbandwidthpolicyprofile](https://technet.microsoft.com/library/Gg398675(v=OCS.15))

  - [CsNetworkBWAlternatePath](https://technet.microsoft.com/library/Gg398732(v=OCS.15))

  - [새-CsNetworkBWPolicy](https://technet.microsoft.com/library/Gg412916(v=OCS.15))

  - [새-Csnetworkinterroute](https://technet.microsoft.com/library/Gg398779(v=OCS.15))

  - [Remove-csnetworkintersitepolicy](https://technet.microsoft.com/library/Gg398994(v=OCS.15))

  - [새-CsNetworkMediaBypassConfiguration](https://technet.microsoft.com/library/Gg425718(v=OCS.15))

  - [새-CsNetworkRegion](https://technet.microsoft.com/library/Gg425829(v=OCS.15))

  - [새-Csnetwork지역 링크](https://technet.microsoft.com/library/Gg398437(v=OCS.15))

  - [새-CsNetworkSite](https://technet.microsoft.com/library/Gg398365(v=OCS.15))

  - [새-CsNetworkSubnet](https://technet.microsoft.com/library/Gg398226(v=OCS.15))

  - [새-CsOAuthServer](https://technet.microsoft.com/library/JJ205206(v=OCS.15))

  - [Get-csoutboundcallingnumbertranslationrule](https://technet.microsoft.com/library/JJ205097(v=OCS.15))

  - [New-csoutboundtranslationrule](https://technet.microsoft.com/library/Gg412803(v=OCS.15))

  - [Get-cspartnerapplication](https://technet.microsoft.com/library/JJ204628(v=OCS.15))

  - [Get-cspersistentchataddin](https://technet.microsoft.com/library/JJ204641(v=OCS.15))

  - [Get-cspersistentchatcategory](https://technet.microsoft.com/library/JJ204803(v=OCS.15))

  - [Get-cspersistentchatcomplianceconfiguration](https://technet.microsoft.com/library/JJ205163(v=OCS.15))

  - [Get-cspersistentchatconfiguration](https://technet.microsoft.com/library/JJ205330(v=OCS.15))

  - [Get-cspersistentchatendpoint](https://technet.microsoft.com/library/JJ204811(v=OCS.15))

  - [Grant-cspersistentchatpolicy](https://technet.microsoft.com/library/JJ205396(v=OCS.15))

  - [Clear-cspersistentchatroom](https://technet.microsoft.com/library/JJ205166(v=OCS.15))

  - [Get-cspinpolicy](https://technet.microsoft.com/library/Gg398935(v=OCS.15))

  - [Get-cspresencepolicy](https://technet.microsoft.com/library/Gg412747(v=OCS.15))

  - [Remove-cspresenceprovider](https://technet.microsoft.com/library/JJ204895(v=OCS.15))

  - [Get-csprivacyconfiguration](https://technet.microsoft.com/library/Gg398807(v=OCS.15))

  - [새-CsProxyConfiguration](https://technet.microsoft.com/library/Gg398335(v=OCS.15))

  - [Disable-cspublicprovider](https://technet.microsoft.com/library/Gg398161(v=OCS.15))

  - [Get-cspushnotificationconfiguration](https://technet.microsoft.com/library/Hh690027(v=OCS.15))

  - [Remove-csqoeconfiguration](https://technet.microsoft.com/library/Gg398325(v=OCS.15))

  - [Get-csregistrarconfiguration](https://technet.microsoft.com/library/Gg425893(v=OCS.15))

  - [Get-csreportingconfiguration](https://technet.microsoft.com/library/JJ204787(v=OCS.15))

  - [Get-csrgsagentgroup](https://technet.microsoft.com/library/Gg413065(v=OCS.15))

  - [New-csrgsanswer](https://technet.microsoft.com/library/Gg412812(v=OCS.15))

  - [New-csrgscallaction](https://technet.microsoft.com/library/Gg398136(v=OCS.15))

  - [New-csrgsholiday](https://technet.microsoft.com/library/Gg398075(v=OCS.15))

  - [New-csrgsholidayset](https://technet.microsoft.com/library/Gg398403(v=OCS.15))

  - [Get-csrgshoursofbusiness](https://technet.microsoft.com/library/Gg398291(v=OCS.15))

  - [New-csrgsprompt](https://technet.microsoft.com/library/Gg398486(v=OCS.15))

  - [New-csrgsquestion](https://technet.microsoft.com/library/Gg398186(v=OCS.15))

  - [Get-csrgsqueue](https://technet.microsoft.com/library/Gg398989(v=OCS.15))

  - [New-csrgstimerange](https://technet.microsoft.com/library/Gg399040(v=OCS.15))

  - [Get-csrgsworkflow](https://technet.microsoft.com/library/Gg398246(v=OCS.15))

  - [새-CsRoutingConfiguration](https://technet.microsoft.com/library/Gg399056(v=OCS.15))

  - [새-CsServerApplication](https://technet.microsoft.com/library/Gg398096(v=OCS.15))

  - [New-cssimpleurl](https://technet.microsoft.com/library/Gg398180(v=OCS.15))

  - [Get-cssimpleurlconfiguration](https://technet.microsoft.com/library/Gg425813(v=OCS.15))

  - [New-cssimpleurlentry](https://technet.microsoft.com/library/Gg425902(v=OCS.15))

  - [New-cssipdomain](https://technet.microsoft.com/library/Gg425857(v=OCS.15))

  - [New-cssipproxycustom](https://technet.microsoft.com/library/Gg425904(v=OCS.15))

  - [New-cssipproxyrealm](https://technet.microsoft.com/library/Gg413084(v=OCS.15))

  - [New-cssipproxytcp](https://technet.microsoft.com/library/Gg425745(v=OCS.15))

  - [New-cssipproxytls](https://technet.microsoft.com/library/Gg398629(v=OCS.15))

  - [New-cssipproxytransport](https://technet.microsoft.com/library/Gg398489(v=OCS.15))

  - [New-cssipproxyusedefault](https://technet.microsoft.com/library/Gg398274(v=OCS.15))

  - [New-cssipproxyusedefaultcert](https://technet.microsoft.com/library/Gg425858(v=OCS.15))

  - [Get-cssipresponsecodetranslationrule](https://technet.microsoft.com/library/Gg413041(v=OCS.15))

  - [새-CsStaticRoute](https://technet.microsoft.com/library/Gg398265(v=OCS.15))

  - [새-CsStaticRoutingConfiguration](https://technet.microsoft.com/library/Gg425811(v=OCS.15))

  - [신규-CsTestDevice](https://technet.microsoft.com/library/Gg425899(v=OCS.15))

  - [Get-cstrunkconfiguration](https://technet.microsoft.com/library/Gg413021(v=OCS.15))

  - [New-cstrustedapplication](https://technet.microsoft.com/library/Gg398259(v=OCS.15))

  - [CsTrustedApplicationComputer](https://technet.microsoft.com/library/Gg398405(v=OCS.15))

  - [CsTrustedApplicationEndpoint](https://technet.microsoft.com/library/Gg398594(v=OCS.15))

  - [New-cstrustedapplicationpool](https://technet.microsoft.com/library/Gg425804(v=OCS.15))

  - [Set-csucphoneconfiguration](https://technet.microsoft.com/library/Gg398445(v=OCS.15))

  - [New-csunassignednumber](https://technet.microsoft.com/library/Gg398651(v=OCS.15))

  - [Get-csuserreplicatorconfiguration](https://technet.microsoft.com/library/Gg399059(v=OCS.15))

  - [새-Csuser서비스 구성](https://technet.microsoft.com/library/Gg412926(v=OCS.15))

  - [새-Csuser서비스 정책](https://technet.microsoft.com/library/JJ205072(v=OCS.15))

  - [New-csvoicemailreroutingconfiguration](https://technet.microsoft.com/library/Gg425849(v=OCS.15))

  - [Get-csvoicenormalizationrule](https://technet.microsoft.com/library/Gg398240(v=OCS.15))

  - [Set-csvoicepolicy](https://technet.microsoft.com/library/Gg425856(v=OCS.15))

  - [CsVoiceRegex](https://technet.microsoft.com/library/Gg412751(v=OCS.15))

  - [Get-csvoiceroute](https://technet.microsoft.com/library/Gg398197(v=OCS.15))

  - [Get-csvoiceroutingpolicy](https://technet.microsoft.com/library/JJ205135(v=OCS.15))

  - [수정한 구성은 test-csvoicetestconfiguration](https://technet.microsoft.com/library/Gg398961(v=OCS.15))

  - [Get-cswatchernodeconfiguration](https://technet.microsoft.com/library/JJ205254(v=OCS.15))

  - [은 new-csweblink](https://technet.microsoft.com/library/Hh690053(v=OCS.15))

  - [Set-cswebserviceconfiguration](https://technet.microsoft.com/library/Gg398440(v=OCS.15))

  - [New-cswebtrustedcacertificate](https://technet.microsoft.com/library/Gg412746(v=OCS.15))

  - [새-CsXmppAllowedPartner](https://technet.microsoft.com/library/JJ204631(v=OCS.15))

  - [게시-Export-cslisconfiguration](https://technet.microsoft.com/library/Gg398364(v=OCS.15))

  - [게시-Enable-cstopology](https://technet.microsoft.com/library/Gg398953(v=OCS.15))

  - [CsAddressBookConfiguration 제거](https://technet.microsoft.com/library/Gg398934(v=OCS.15))

  - [제거-CsAdminRole](https://technet.microsoft.com/library/Gg413036(v=OCS.15))

  - [제거-CsAllowedDomain](https://technet.microsoft.com/library/Gg398913(v=OCS.15))

  - [Move-csanalogdevice을 제거 합니다.](rehttps://technet.microsoft.com/library/Gg398816(v=OCS.15))

  - [CsAnnouncement-사후 알림](https://technet.microsoft.com/library/Gg412766(v=OCS.15))

  - [Get-csarchivingconfiguration을 제거 합니다.](https://technet.microsoft.com/library/Gg398951(v=OCS.15))

  - [Grant-csarchivingpolicy을 제거 합니다.](https://technet.microsoft.com/library/Gg425924(v=OCS.15))

  - [Get-csautodiscoverconfiguration을 제거 합니다.](https://technet.microsoft.com/library/Hh690054(v=OCS.15))

  - [Get-csavedgeconfiguration을 제거 합니다.](https://technet.microsoft.com/library/Gg398786(v=OCS.15))

  - [Get-csbackupserviceconfiguration을 제거 합니다.](https://technet.microsoft.com/library/JJ204903(v=OCS.15))

  - [CsBandwidthPolicyServiceConfiguration을 제거 합니다.](https://technet.microsoft.com/library/Gg398877(v=OCS.15))

  - [Get-csblockeddomain을 제거 합니다.](https://technet.microsoft.com/library/Gg425832(v=OCS.15))

  - [Get-cscallparkorbit을 제거 합니다.](https://technet.microsoft.com/library/Gg412901(v=OCS.15))

  - [Get-cscdrconfiguration을 제거 합니다.](https://technet.microsoft.com/library/Gg398451(v=OCS.15))

  - [Set-cscertificate을 제거 합니다.](https://technet.microsoft.com/library/Gg412895(v=OCS.15))

  - [제거-CsClientPolicy](https://technet.microsoft.com/library/Gg425772(v=OCS.15))

  - [제거-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg425925(v=OCS.15))

  - [제거-CsClientVersionPolicy](https://technet.microsoft.com/library/Gg425801(v=OCS.15))

  - [제거-CsClientVersionPolicyRule](https://technet.microsoft.com/library/Gg398541(v=OCS.15))

  - [-CsClsRegion 제거](https://technet.microsoft.com/library/JJ204971(v=OCS.15))

  - [제거-CsClsScenario](https://technet.microsoft.com/library/JJ205010(v=OCS.15))

  - [제거-CsClsSecurityGroup](https://technet.microsoft.com/library/JJ204958(v=OCS.15))

  - [Move-cscommonareaphone을 제거 합니다.](rehttps://technet.microsoft.com/library/Gg412837(v=OCS.15))

  - [Get-csconferencedirectory을 제거 합니다.](rehttps://technet.microsoft.com/library/Gg412968(v=OCS.15))

  - [Get-csconferencedisclaimer을 제거 합니다.](https://technet.microsoft.com/library/Gg398243(v=OCS.15))

  - [Get-csconferencingconfiguration을 제거 합니다.](https://technet.microsoft.com/library/Gg412767(v=OCS.15))

  - [Get-csconferencingpolicy을 제거 합니다.](https://technet.microsoft.com/library/Gg398728(v=OCS.15))

  - [Remove-csconfigurationstorelocation을 제거 합니다.](https://technet.microsoft.com/library/Gg398214(v=OCS.15))

  - [New-cscpsconfiguration을 제거 합니다.](https://technet.microsoft.com/library/Gg398358(v=OCS.15))

  - [New-csdeviceupdateconfiguration을 제거 합니다.](https://technet.microsoft.com/library/Gg425933(v=OCS.15))

  - [Get-csdeviceupdaterule을 제거 합니다.](https://technet.microsoft.com/library/Gg425930(v=OCS.15))

  - [Get-csdiagnosticconfiguration을 제거 합니다.](https://technet.microsoft.com/library/Gg412853(v=OCS.15))

  - [Get-csdiagnosticheaderconfiguration을 제거 합니다.](https://technet.microsoft.com/library/Gg398941(v=OCS.15))

  - [Get-csdialinconferencingaccessnumber을 제거 합니다.](https://technet.microsoft.com/library/Gg412782(v=OCS.15))

  - [Get-csdialinconferencingconfiguration을 제거 합니다.](https://technet.microsoft.com/library/Gg398174(v=OCS.15))

  - [Set-csdialinconferencingdtmfconfiguration을 제거 합니다.](https://technet.microsoft.com/library/Gg425894(v=OCS.15))

  - [CsDialPlan 다이얼 플랜 제거](https://technet.microsoft.com/library/Gg398791(v=OCS.15))

  - [CsEnhancedEmergencyServiceDisclaimer을 제거 합니다.](https://technet.microsoft.com/library/Gg425810(v=OCS.15))

  - [Get-csexternalaccesspolicy을 제거 합니다.](https://technet.microsoft.com/library/Gg399057(v=OCS.15))

  - [제거-CsExUmContact](rehttps://technet.microsoft.com/library/Gg425842(v=OCS.15))

  - [CsFileTransferFilterConfiguration을 제거 합니다.](https://technet.microsoft.com/library/Gg413064(v=OCS.15))

  - [제거-CsFIPSConfiguration](https://technet.microsoft.com/library/JJ205201(v=OCS.15))

  - [Get-cshealthmonitoringconfiguration을 제거 합니다.](https://technet.microsoft.com/library/Gg425794(v=OCS.15))

  - [Set-cshostedvoicemailpolicy을 제거 합니다.](https://technet.microsoft.com/library/Gg398211(v=OCS.15))

  - [제거-CsHostingProvider](https://technet.microsoft.com/library/Gg425809(v=OCS.15))

  - [제거-CsImFilterConfiguration](https://technet.microsoft.com/library/Gg398171(v=OCS.15))

  - [Get-cskerberosaccountassignment을 제거 합니다.](https://technet.microsoft.com/library/Gg413052(v=OCS.15))

  - [Get-cslislocation을 제거 합니다.](https://technet.microsoft.com/library/Gg425722(v=OCS.15))

  - [CsLisPort을 제거 합니다.](https://technet.microsoft.com/library/Gg412899(v=OCS.15))

  - [CsLisServiceProvider을 제거 합니다.](https://technet.microsoft.com/library/Gg398904(v=OCS.15))

  - [CsLisSubnet을 제거 합니다.](https://technet.microsoft.com/library/Gg413053(v=OCS.15))

  - [CsLisSwitch을 제거 합니다.](https://technet.microsoft.com/library/Gg398352(v=OCS.15))

  - [CsLisWirelessAccessPoint을 제거 합니다.](https://technet.microsoft.com/library/Gg398461(v=OCS.15))

  - [제거-CsLocationPolicy](https://technet.microsoft.com/library/Gg398727(v=OCS.15))

  - [제거-CsManagementConnection](https://technet.microsoft.com/library/Gg425803(v=OCS.15))

  - [-CsMcxConfiguration을 제거 합니다.](https://technet.microsoft.com/library/Hh690026(v=OCS.15))

  - [Get-csmediaconfiguration을 제거 합니다.](https://technet.microsoft.com/library/Gg398705(v=OCS.15))

  - [Get-csmeetingconfiguration을 제거 합니다.](https://technet.microsoft.com/library/Gg412775(v=OCS.15))

  - [Get-csmobilitypolicy을 제거 합니다.](https://technet.microsoft.com/library/Hh690048(v=OCS.15))

  - [Get-csnetworkbandwidthpolicyprofile을 제거 합니다.](https://technet.microsoft.com/library/Gg398609(v=OCS.15))

  - [Get-csnetworkconfiguration을 제거 합니다.](https://technet.microsoft.com/library/Gg398938(v=OCS.15))

  - [제거-Csnetworkinterroute](https://technet.microsoft.com/library/Gg398743(v=OCS.15))

  - [Remove-csnetworkintersitepolicy을 제거 합니다.](https://technet.microsoft.com/library/Gg398963(v=OCS.15))

  - [CsNetworkRegion 제거](https://technet.microsoft.com/library/Gg398466(v=OCS.15))

  - [-Csnetwork지역 링크 제거](https://technet.microsoft.com/library/Gg413012(v=OCS.15))

  - [CsNetworkSite를 제거 합니다.](https://technet.microsoft.com/library/Gg398135(v=OCS.15))

  - [제거-CsNetworkSubnet](https://technet.microsoft.com/library/Gg425726(v=OCS.15))

  - [CsOAuthServer 제거](https://technet.microsoft.com/library/JJ205408(v=OCS.15))

  - [Get-csoutboundcallingnumbertranslationrule을 제거 합니다.](https://technet.microsoft.com/library/JJ204836(v=OCS.15))

  - [New-csoutboundtranslationrule을 제거 합니다.](https://technet.microsoft.com/library/Gg398556(v=OCS.15))

  - [Get-cspartnerapplication을 제거 합니다.](https://technet.microsoft.com/library/JJ204820(v=OCS.15))

  - [Get-cspersistentchataddin을 제거 합니다.](https://technet.microsoft.com/library/JJ205350(v=OCS.15))

  - [Get-cspersistentchatcategory을 제거 합니다.](https://technet.microsoft.com/library/JJ204660(v=OCS.15))

  - [Get-cspersistentchatcomplianceconfiguration을 제거 합니다.](https://technet.microsoft.com/library/JJ204767(v=OCS.15))

  - [Get-cspersistentchatconfiguration을 제거 합니다.](https://technet.microsoft.com/library/JJ204927(v=OCS.15))

  - [Get-cspersistentchatendpoint을 제거 합니다.](https://technet.microsoft.com/library/JJ204626(v=OCS.15))

  - [Test-cspersistentchatmessage을 제거 합니다.](https://technet.microsoft.com/library/JJ204668(v=OCS.15))

  - [Grant-cspersistentchatpolicy을 제거 합니다.](https://technet.microsoft.com/library/JJ205301(v=OCS.15))

  - [Clear-cspersistentchatroom을 제거 합니다.](https://technet.microsoft.com/library/JJ204639(v=OCS.15))

  - [Get-cspinpolicy을 제거 합니다.](https://technet.microsoft.com/library/Gg398431(v=OCS.15))

  - [Get-cspresencepolicy을 제거 합니다.](https://technet.microsoft.com/library/Gg399070(v=OCS.15))

  - [Remove-cspresenceprovider을 제거 합니다.](https://technet.microsoft.com/library/JJ205036(v=OCS.15))

  - [Get-csprivacyconfiguration을 제거 합니다.](https://technet.microsoft.com/library/Gg425821(v=OCS.15))

  - [CsProxyConfiguration 제거](https://technet.microsoft.com/library/Gg398553(v=OCS.15))

  - [Disable-cspublicprovider을 제거 합니다.](https://technet.microsoft.com/library/Gg412906(v=OCS.15))

  - [Get-cspushnotificationconfiguration을 제거 합니다.](https://technet.microsoft.com/library/Hh690028(v=OCS.15))

  - [Remove-csqoeconfiguration을 제거 합니다.](https://technet.microsoft.com/library/Gg425879(v=OCS.15))

  - [Get-csregistrarconfiguration을 제거 합니다.](https://technet.microsoft.com/library/Gg398482(v=OCS.15))

  - [Get-csreportingconfiguration을 제거 합니다.](https://technet.microsoft.com/library/JJ204711(v=OCS.15))

  - [Get-csrgsagentgroup을 제거 합니다.](https://technet.microsoft.com/library/Gg398969(v=OCS.15))

  - [New-csrgsholidayset을 제거 합니다.](https://technet.microsoft.com/library/Gg398521(v=OCS.15))

  - [Get-csrgshoursofbusiness을 제거 합니다.](https://technet.microsoft.com/library/Gg398568(v=OCS.15))

  - [Get-csrgsqueue을 제거 합니다.](https://technet.microsoft.com/library/Gg398576(v=OCS.15))

  - [Get-csrgsworkflow을 제거 합니다.](https://technet.microsoft.com/library/Gg398765(v=OCS.15))

  - [제거-CsRoutingConfiguration](https://technet.microsoft.com/library/Gg398643(v=OCS.15))

  - [CsServerApplication 제거](https://technet.microsoft.com/library/Gg398366(v=OCS.15))

  - [Get-cssimpleurlconfiguration을 제거 합니다.](https://technet.microsoft.com/library/Gg398515(v=OCS.15))

  - [New-cssipdomain을 제거 합니다.](https://technet.microsoft.com/library/Gg398865(v=OCS.15))

  - [Get-cssipresponsecodetranslationrule을 제거 합니다.](https://technet.microsoft.com/library/Gg412932(v=OCS.15))

  - [CsSlaConfiguration을 제거 합니다.](https://technet.microsoft.com/library/Mt703201(v=OCS.15))

  - [CsSlaDelegates을 제거 합니다.](https://technet.microsoft.com/library/Mt703203(v=OCS.15))

  - [제거-CsStaticRoutingConfiguration](https://technet.microsoft.com/library/Gg398668(v=OCS.15))

  - [제거-CsTestDevice](https://technet.microsoft.com/library/Gg398790(v=OCS.15))

  - [Get-cstestusercredential을 제거 합니다.](https://technet.microsoft.com/library/JJ204870(v=OCS.15))

  - [Get-cstrunkconfiguration을 제거 합니다.](https://technet.microsoft.com/library/Gg425943(v=OCS.15))

  - [New-cstrustedapplication을 제거 합니다.](https://technet.microsoft.com/library/Gg398176(v=OCS.15))

  - [CsTrustedApplicationComputer을 제거 합니다.](https://technet.microsoft.com/library/Gg398838(v=OCS.15))

  - [CsTrustedApplicationEndpoint을 제거 합니다.](https://technet.microsoft.com/library/Gg398837(v=OCS.15))

  - [New-cstrustedapplicationpool을 제거 합니다.](https://technet.microsoft.com/library/Gg398750(v=OCS.15))

  - [Set-csucphoneconfiguration을 제거 합니다.](https://technet.microsoft.com/library/Gg398249(v=OCS.15))

  - [New-csunassignednumber을 제거 합니다.](https://technet.microsoft.com/library/Gg398209(v=OCS.15))

  - [제거-CsUserAcp](https://technet.microsoft.com/library/Gg398982(v=OCS.15))

  - [Get-csuserreplicatorconfiguration을 제거 합니다.](https://technet.microsoft.com/library/Gg425738(v=OCS.15))

  - [Csuser서비스 구성 제거](https://technet.microsoft.com/library/Gg398722(v=OCS.15))

  - [Csuser서비스 정책 제거](https://technet.microsoft.com/library/JJ204629(v=OCS.15))

  - [CsUserStoreBackupData 제거](https://technet.microsoft.com/library/JJ205003(v=OCS.15))

  - [CsVoiceConfiguration을 제거 합니다.](https://technet.microsoft.com/library/Gg398804(v=OCS.15))

  - [New-csvoicemailreroutingconfiguration을 제거 합니다.](https://technet.microsoft.com/library/Gg398573(v=OCS.15))

  - [Get-csvoicenormalizationrule을 제거 합니다.](https://technet.microsoft.com/library/Gg398501(v=OCS.15))

  - [Set-csvoicepolicy을 제거 합니다.](https://technet.microsoft.com/library/Gg398309(v=OCS.15))

  - [Get-csvoiceroute을 제거 합니다.](https://technet.microsoft.com/library/Gg398468(v=OCS.15))

  - [Get-csvoiceroutingpolicy을 제거 합니다.](https://technet.microsoft.com/library/JJ204799(v=OCS.15))

  - [수정한 구성은 test-csvoicetestconfiguration을 제거 합니다.](https://technet.microsoft.com/library/Gg412813(v=OCS.15))

  - [Get-cswatchernodeconfiguration을 제거 합니다.](https://technet.microsoft.com/library/JJ204926(v=OCS.15))

  - [Set-cswebserviceconfiguration을 제거 합니다.](https://technet.microsoft.com/library/Gg398266(v=OCS.15))

  - [제거-CsXmppAllowedPartner](https://technet.microsoft.com/library/JJ205055(v=OCS.15))

  - [요청-Set-cscertificate](https://technet.microsoft.com/library/Gg425723(v=OCS.15))

  - [Reset-Get-csdeviceupdaterule](https://technet.microsoft.com/library/Gg398181(v=OCS.15))

  - [복원-Get-csdeviceupdaterule](https://technet.microsoft.com/library/Gg398305(v=OCS.15))

  - [Get-csclientcertificate](https://technet.microsoft.com/library/Gg425748(v=OCS.15))

  - [CsOUPermission](https://technet.microsoft.com/library/Gg398977(v=OCS.15))

  - [CsSetupPermission](https://technet.microsoft.com/library/Gg425834(v=OCS.15))

  - [Set-csaccessedgeconfiguration](https://technet.microsoft.com/library/Gg413017(v=OCS.15))

  - [설정-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg412784(v=OCS.15))

  - [설정-CsAdminRole](https://technet.microsoft.com/library/Gg399066(v=OCS.15))

  - [설정-CsAllowedDomain](https://technet.microsoft.com/library/Gg398931(v=OCS.15))

  - [Move-csanalogdevice](https://technet.microsoft.com/library/Gg412843(v=OCS.15))

  - [CsAnnouncement](https://technet.microsoft.com/library/Gg425752(v=OCS.15))

  - [설정-CsApplicationServer](https://technet.microsoft.com/library/Gg398562(v=OCS.15))

  - [Get-csarchivingconfiguration](https://technet.microsoft.com/library/Gg413030(v=OCS.15))

  - [Grant-csarchivingpolicy](https://technet.microsoft.com/library/Gg398294(v=OCS.15))

  - [CsArchivingServer](https://technet.microsoft.com/library/Gg398923(v=OCS.15))

  - [설정-CsAudioTestServiceApplication](https://technet.microsoft.com/library/Gg398907(v=OCS.15))

  - [Get-csautodiscoverconfiguration](https://technet.microsoft.com/library/Hh689980(v=OCS.15))

  - [Get-csavedgeconfiguration](https://technet.microsoft.com/library/Gg412869(v=OCS.15))

  - [Get-csbackupserviceconfiguration](https://technet.microsoft.com/library/JJ205006(v=OCS.15))

  - [CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/library/Gg412863(v=OCS.15))

  - [Get-csblockeddomain](https://technet.microsoft.com/library/Gg398090(v=OCS.15))

  - [Get-cscallparkorbit](https://technet.microsoft.com/library/Gg398796(v=OCS.15))

  - [Set-cscallparkservicemusiconholdfile](https://technet.microsoft.com/library/Gg412836(v=OCS.15))

  - [Get-cscdrconfiguration](https://technet.microsoft.com/library/Gg398774(v=OCS.15))

  - [Set-cscertificate](https://technet.microsoft.com/library/Gg398518(v=OCS.15))

  - [설정-CsClientPin](https://technet.microsoft.com/library/Gg398929(v=OCS.15))

  - [설정-CsClientPolicy](https://technet.microsoft.com/library/Gg398300(v=OCS.15))

  - [설정-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg398623(v=OCS.15))

  - [설정-CsClientVersionPolicy](https://technet.microsoft.com/library/Gg398876(v=OCS.15))

  - [설정-CsClientVersionPolicyRule](https://technet.microsoft.com/library/Gg425790(v=OCS.15))

  - [설정-CsClsRegion](https://technet.microsoft.com/library/JJ204746(v=OCS.15))

  - [설정-CsClsScenario](https://technet.microsoft.com/library/JJ204622(v=OCS.15))

  - [설정-CsClsSearchTerm](https://technet.microsoft.com/library/JJ204911(v=OCS.15))

  - [설정-CsClsSecurityGroup](https://technet.microsoft.com/library/JJ204700(v=OCS.15))

  - [Move-cscommonareaphone](https://technet.microsoft.com/library/Gg398579(v=OCS.15))

  - [Get-csconferencedisclaimer](https://technet.microsoft.com/library/Gg398776(v=OCS.15))

  - [Set-csconferenceserver](https://technet.microsoft.com/library/Gg398738(v=OCS.15))

  - [Get-csconferencingconfiguration](https://technet.microsoft.com/library/Gg412969(v=OCS.15))

  - [Get-csconferencingpolicy](https://technet.microsoft.com/library/Gg425788(v=OCS.15))

  - [Remove-csconfigurationstorelocation](https://technet.microsoft.com/library/Gg398258(v=OCS.15))

  - [New-cscpsconfiguration](https://technet.microsoft.com/library/Gg412721(v=OCS.15))

  - [New-csdeviceupdateconfiguration](https://technet.microsoft.com/library/Gg398320(v=OCS.15))

  - [Get-csdiagnosticconfiguration](https://technet.microsoft.com/library/Gg425734(v=OCS.15))

  - [Get-csdiagnosticheaderconfiguration](https://technet.microsoft.com/library/Gg399045(v=OCS.15))

  - [Get-csdialinconferencingaccessnumber](https://technet.microsoft.com/library/Gg425770(v=OCS.15))

  - [Get-csdialinconferencingconfiguration](https://technet.microsoft.com/library/Gg425825(v=OCS.15))

  - [Set-csdialinconferencingdtmfconfiguration](https://technet.microsoft.com/library/Gg398860(v=OCS.15))

  - [설정-CsDialPlan 플랜](https://technet.microsoft.com/library/Gg398644(v=OCS.15)) 설정-CsDialPlan 플랜

  - [설정-CsDirector](https://technet.microsoft.com/library/Gg398565(v=OCS.15))

  - [Set-csedgeserver](https://technet.microsoft.com/library/Gg398859(v=OCS.15))

  - [CsEnhancedEmergencyServiceDisclaimer](https://technet.microsoft.com/library/Gg398620(v=OCS.15))

  - [Get-csexternalaccesspolicy](https://technet.microsoft.com/library/Gg398916(v=OCS.15))

  - [Set-CsExUmContact](https://technet.microsoft.com/library/Gg412944(v=OCS.15))

  - [CsFileTransferFilterConfiguration](https://technet.microsoft.com/library/Gg425736(v=OCS.15))

  - [설정-CsFIPSConfiguration](https://technet.microsoft.com/library/JJ205084(v=OCS.15))

  - [Get-cshealthmonitoringconfiguration](https://technet.microsoft.com/library/Gg425847(v=OCS.15))

  - [Set-cshostedvoicemailpolicy](https://technet.microsoft.com/library/Gg412722(v=OCS.15))

  - [Set-CsHostingProvider](https://technet.microsoft.com/library/Gg398532(v=OCS.15))

  - [Set-CsImFilterConfiguration](https://technet.microsoft.com/library/Gg412960(v=OCS.15))

  - [Get-cskerberosaccountassignment](https://technet.microsoft.com/library/Gg398232(v=OCS.15))

  - [Set-CsKerberosAccountPassword](https://technet.microsoft.com/library/Gg398659(v=OCS.15))

  - [Get-cslislocation](https://technet.microsoft.com/library/Gg398757(v=OCS.15))

  - [CsLisPort](https://technet.microsoft.com/library/Gg398700(v=OCS.15))

  - [CsLisServiceProvider](https://technet.microsoft.com/library/Gg425911(v=OCS.15))

  - [CsLisSubnet](https://technet.microsoft.com/library/Gg399016(v=OCS.15))

  - [CsLisSwitch](https://technet.microsoft.com/library/Gg412823(v=OCS.15))

  - [CsLisWirelessAccessPoint](https://technet.microsoft.com/library/Gg412723(v=OCS.15))

  - [설정-CsLocationPolicy](https://technet.microsoft.com/library/Gg412987(v=OCS.15))

  - [설정-CsManagementConnection](https://technet.microsoft.com/library/Gg413045(v=OCS.15))

  - [-CsMcxConfiguration](https://technet.microsoft.com/library/Hh690050(v=OCS.15))

  - [Move-csmanagementserver](https://technet.microsoft.com/library/Gg398465(v=OCS.15))

  - [Get-csmediaconfiguration](https://technet.microsoft.com/library/Gg398580(v=OCS.15))

  - [Set-CsMediationServer](https://technet.microsoft.com/library/Gg398213(v=OCS.15))

  - [Get-csmeetingconfiguration](https://technet.microsoft.com/library/Gg398648(v=OCS.15))

  - [Enable-csmeetingroom](https://technet.microsoft.com/library/JJ204831(v=OCS.15))

  - [Get-csmobilitypolicy](https://technet.microsoft.com/library/Hh690021(v=OCS.15))

  - [CsMonitoringServer](https://technet.microsoft.com/library/Gg425776(v=OCS.15))

  - [Get-csnetworkbandwidthpolicyprofile](https://technet.microsoft.com/library/Gg398338(v=OCS.15))

  - [Get-csnetworkconfiguration](https://technet.microsoft.com/library/Gg398927(v=OCS.15))

  - [설정-Csnetworkinter지역 경로](https://technet.microsoft.com/library/Gg398410(v=OCS.15))

  - [Remove-csnetworkintersitepolicy](https://technet.microsoft.com/library/Gg398772(v=OCS.15))

  - [설정-CsNetworkRegion](https://technet.microsoft.com/library/Gg413089(v=OCS.15))

  - [설정-Csnetwork지역 링크](https://technet.microsoft.com/library/Gg412867(v=OCS.15))

  - [설정-CsNetworkSite](https://technet.microsoft.com/library/Gg398295(v=OCS.15))

  - [설정-CsNetworkSubnet](https://technet.microsoft.com/library/Gg412739(v=OCS.15))

  - [Set-CsOAuthConfiguration](https://technet.microsoft.com/library/JJ204841(v=OCS.15))

  - [Set-CsOAuthServer](https://technet.microsoft.com/library/JJ204896(v=OCS.15))

  - [Get-csoutboundcallingnumbertranslationrule](https://technet.microsoft.com/library/JJ205400(v=OCS.15))

  - [New-csoutboundtranslationrule](https://technet.microsoft.com/library/Gg413073(v=OCS.15))

  - [Get-cspartnerapplication](https://technet.microsoft.com/library/JJ204755(v=OCS.15))

  - [Set-cspersistentchatactiveserver](https://technet.microsoft.com/library/JJ205065(v=OCS.15))

  - [Get-cspersistentchataddin](https://technet.microsoft.com/library/JJ204721(v=OCS.15))

  - [Get-cspersistentchatcategory](https://technet.microsoft.com/library/JJ204952(v=OCS.15))

  - [Get-cspersistentchatcomplianceconfiguration](https://technet.microsoft.com/library/JJ204949(v=OCS.15))

  - [Get-cspersistentchatconfiguration](https://technet.microsoft.com/library/JJ205122(v=OCS.15))

  - [Grant-cspersistentchatpolicy](https://technet.microsoft.com/library/JJ205192(v=OCS.15))

  - [Clear-cspersistentchatroom](https://technet.microsoft.com/library/JJ204801(v=OCS.15))

  - [Set-cspersistentchatstate](https://technet.microsoft.com/library/JJ205109(v=OCS.15))

  - [Get-cspinpolicy](https://technet.microsoft.com/library/Gg412997(v=OCS.15))

  - [Get-cspresencepolicy](https://technet.microsoft.com/library/Gg425782(v=OCS.15))

  - [Remove-cspresenceprovider](https://technet.microsoft.com/library/JJ204833(v=OCS.15))

  - [Get-csprivacyconfiguration](https://technet.microsoft.com/library/Gg398484(v=OCS.15))

  - [설정-CsProxyConfiguration](https://technet.microsoft.com/library/Gg425796(v=OCS.15))

  - [설정-CsPstnGateway](https://technet.microsoft.com/library/Gg398408(v=OCS.15))

  - [설정-CsPstnUsage](https://technet.microsoft.com/library/Gg399069(v=OCS.15))

  - [Disable-cspublicprovider](https://technet.microsoft.com/library/Gg413087(v=OCS.15))

  - [Get-cspushnotificationconfiguration](https://technet.microsoft.com/library/Hh690013(v=OCS.15))

  - [Remove-csqoeconfiguration](https://technet.microsoft.com/library/Gg398245(v=OCS.15))

  - [CsRegistrar](https://technet.microsoft.com/library/Gg398993(v=OCS.15))

  - [Get-csregistrarconfiguration](https://technet.microsoft.com/library/Gg398764(v=OCS.15))

  - [Get-csreportingconfiguration](https://technet.microsoft.com/library/JJ205075(v=OCS.15))

  - [Get-csrgsagentgroup](https://technet.microsoft.com/library/Gg425955(v=OCS.15))

  - [Export-csrgsconfiguration](https://technet.microsoft.com/library/Gg425728(v=OCS.15))

  - [New-csrgsholidayset](https://technet.microsoft.com/library/Gg398736(v=OCS.15))

  - [Get-csrgshoursofbusiness](https://technet.microsoft.com/library/Gg412929(v=OCS.15))

  - [Get-csrgsqueue](https://technet.microsoft.com/library/Gg412947(v=OCS.15))

  - [Get-csrgsworkflow](https://technet.microsoft.com/library/Gg425845(v=OCS.15))

  - [설정-CsRoutingConfiguration](https://technet.microsoft.com/library/Gg412811(v=OCS.15))

  - [설정-CsServerApplication](https://technet.microsoft.com/library/Gg412850(v=OCS.15))

  - [Get-cssimpleurlconfiguration](https://technet.microsoft.com/library/Gg412991(v=OCS.15))

  - [New-cssipdomain](https://technet.microsoft.com/library/Gg412949(v=OCS.15))

  - [Get-cssipresponsecodetranslationrule](https://technet.microsoft.com/library/Gg425895(v=OCS.15))

  - [설정-CsSite](https://technet.microsoft.com/library/Gg413023(v=OCS.15))

  - [CsSlaConfiguration](https://technet.microsoft.com/library/Mt703202(v=OCS.15))

  - [설정-CsStaticRoutingConfiguration](https://technet.microsoft.com/library/Gg398724(v=OCS.15))

  - [설정-CsTestDevice](https://technet.microsoft.com/library/Gg398156(v=OCS.15))

  - [Get-cstrunkconfiguration](https://technet.microsoft.com/library/Gg398238(v=OCS.15))

  - [New-cstrustedapplication](https://technet.microsoft.com/library/Gg425840(v=OCS.15))

  - [CsTrustedApplicationEndpoint](https://technet.microsoft.com/library/Gg398509(v=OCS.15))

  - [New-cstrustedapplicationpool](https://technet.microsoft.com/library/Gg398187(v=OCS.15))

  - [Set-csucphoneconfiguration](https://technet.microsoft.com/library/Gg413042(v=OCS.15))

  - [Get-csuiculture](https://technet.microsoft.com/library/Gg398354(v=OCS.15))

  - [New-csunassignednumber](https://technet.microsoft.com/library/Gg399033(v=OCS.15))

  - [설정-CsUser](https://technet.microsoft.com/library/Gg398510(v=OCS.15))

  - [설정-CsUserAcp](https://technet.microsoft.com/library/Gg413018(v=OCS.15))

  - [설정-CsUserDatabaseState](https://technet.microsoft.com/library/Gg412973(v=OCS.15))

  - [Get-csuserreplicatorconfiguration](https://technet.microsoft.com/library/Gg398540(v=OCS.15))

  - [설정-CsUserServer](https://technet.microsoft.com/library/Gg413026(v=OCS.15))

  - [Csuser서비스 구성](https://technet.microsoft.com/library/Gg398340(v=OCS.15))

  - [설정-Csuser서비스 정책](https://technet.microsoft.com/library/JJ205414(v=OCS.15))

  - [CsVoiceConfiguration](https://technet.microsoft.com/library/Gg398967(v=OCS.15))

  - [New-csvoicemailreroutingconfiguration](https://technet.microsoft.com/library/Gg412948(v=OCS.15))

  - [Get-csvoicenormalizationrule](https://technet.microsoft.com/library/Gg398491(v=OCS.15))

  - [Set-csvoicepolicy](https://technet.microsoft.com/library/Gg399021(v=OCS.15))

  - [Get-csvoiceroute](https://technet.microsoft.com/library/Gg412893(v=OCS.15))

  - [Get-csvoiceroutingpolicy](https://technet.microsoft.com/library/JJ205313(v=OCS.15))

  - [수정한 구성은 test-csvoicetestconfiguration](https://technet.microsoft.com/library/Gg398614(v=OCS.15))

  - [Get-cswatchernodeconfiguration](https://technet.microsoft.com/library/JJ204620(v=OCS.15))

  - [Set-CsWebServer](https://technet.microsoft.com/library/Gg398759(v=OCS.15))

  - [Set-cswebserviceconfiguration](https://technet.microsoft.com/library/Gg398396(v=OCS.15))

  - [설정-CsXmppAllowedPartner](https://technet.microsoft.com/library/JJ204686(v=OCS.15))

  - [설정-CsXmppGatewayConfiguration](https://technet.microsoft.com/library/JJ204769(v=OCS.15))

  - [시작-CsWindowsService](https://technet.microsoft.com/library/Gg398561(v=OCS.15))

  - [CsWindowsService](https://technet.microsoft.com/library/Gg398426(v=OCS.15))

  - [동기화-CsUserData](https://technet.microsoft.com/library/JJ205242(v=OCS.15))

  - [테스트-CsAddressBookService](https://technet.microsoft.com/library/Gg398661(v=OCS.15))

  - [테스트-CsAddressBookWebQuery](https://technet.microsoft.com/library/Gg398773(v=OCS.15))

  - [테스트-CsASConference](https://technet.microsoft.com/library/JJ205227(v=OCS.15))

  - [Test-csaudioconferencingprovider](https://technet.microsoft.com/library/JJ205117(v=OCS.15))

  - [CsAVConference 테스트](https://technet.microsoft.com/library/Gg412749(v=OCS.15))

  - [Test-csavedgeconnectivity](https://technet.microsoft.com/library/JJ205138(v=OCS.15))

  - [Test-cscertificateconfiguration](https://technet.microsoft.com/library/Gg398647(v=OCS.15))

  - [테스트-CsComputer](https://technet.microsoft.com/library/Gg398162(v=OCS.15))

  - [테스트-CsDatabase](https://technet.microsoft.com/library/JJ204839(v=OCS.15))

  - [Test-csdataconference](https://technet.microsoft.com/library/JJ205219(v=OCS.15))

  - [Test-csdialinconferencing](https://technet.microsoft.com/library/Gg399013(v=OCS.15))

  - [테스트-CsDialPlan 플랜](https://technet.microsoft.com/library/Gg399024(v=OCS.15))

  - [Test-csexstorageconnectivity](https://technet.microsoft.com/library/JJ204740(v=OCS.15))

  - [Test-csexstoragenotification](https://technet.microsoft.com/library/JJ205331(v=OCS.15))

  - [Test-csexumconnectivity](https://technet.microsoft.com/library/JJ204784(v=OCS.15))

  - [테스트-CsExUMVoiceMail 메일](https://technet.microsoft.com/library/JJ205058(v=OCS.15))

  - [Test-csfederatedpartner](https://technet.microsoft.com/library/Gg398281(v=OCS.15))

  - [테스트-CsGroupExpansion](https://technet.microsoft.com/library/Gg399009(v=OCS.15))

  - [테스트-CsGroupIM](https://technet.microsoft.com/library/Gg398273(v=OCS.15))

  - [Test-CsIM](https://technet.microsoft.com/library/Gg425802(v=OCS.15))

  - [Test-csintertrunkrouting](https://technet.microsoft.com/library/JJ204741(v=OCS.15))

  - [Get-cskerberosaccountassignment](https://technet.microsoft.com/library/Gg425938(v=OCS.15))

  - [Test-csliscivicaddress](https://technet.microsoft.com/library/Gg425914(v=OCS.15))

  - [Export-cslisconfiguration](https://technet.microsoft.com/library/Gg398497(v=OCS.15))

  - [테스트-CsLocationPolicy](https://technet.microsoft.com/library/Gg425962(v=OCS.15))

  - [Test-CsMcxConference](https://technet.microsoft.com/library/Hh690045(v=OCS.15))

  - [Test-csmcxp2pim](https://technet.microsoft.com/library/Hh690020(v=OCS.15))

  - [Test-CsMcxPushNotification](https://technet.microsoft.com/library/Hh690043(v=OCS.15))

  - [테스트-CsOUPermission](https://technet.microsoft.com/library/Gg398787(v=OCS.15))

  - [Test-csp2pav](https://technet.microsoft.com/library/Gg412821(v=OCS.15))

  - [Test-cspersistentchatmessage](https://technet.microsoft.com/library/JJ204656(v=OCS.15))

  - [Test-csphonebootstrap](https://technet.microsoft.com/library/Gg412852(v=OCS.15))

  - [테스트-cspres](https://technet.microsoft.com/library/Gg398148(v=OCS.15))

  - [Test-cspstnoutboundcall](https://technet.microsoft.com/library/Gg398207(v=OCS.15))

  - [테스트-CsPstnPeerToPeerCall](https://technet.microsoft.com/library/Gg398662(v=OCS.15))

  - [테스트-CsRegistration](https://technet.microsoft.com/library/Gg412737(v=OCS.15))

  - [테스트-CsReplica](https://technet.microsoft.com/library/JJ205289(v=OCS.15))

  - [테스트-CsSetupPermission](https://technet.microsoft.com/library/Gg398428(v=OCS.15))

  - [Enable-cstopology](https://technet.microsoft.com/library/Gg398127(v=OCS.15))

  - [Get-cstrunkconfiguration](https://technet.microsoft.com/library/Gg398137(v=OCS.15))

  - [Test-csunifiedcontactstore](https://technet.microsoft.com/library/JJ204662(v=OCS.15))

  - [Get-csvoicenormalizationrule](https://technet.microsoft.com/library/Gg399003(v=OCS.15))

  - [Set-csvoicepolicy](https://technet.microsoft.com/library/Gg398310(v=OCS.15))

  - [Get-csvoiceroute](https://technet.microsoft.com/library/Gg425873(v=OCS.15))

  - [수정한 구성은 test-csvoicetestconfiguration](https://technet.microsoft.com/library/Gg398260(v=OCS.15))

  - [CsVoiceUser](https://technet.microsoft.com/library/Gg413013(v=OCS.15))

  - [Get-cswatchernodeconfiguration](https://technet.microsoft.com/library/JJ204652(v=OCS.15))

  - [Test-cswebapp](https://technet.microsoft.com/library/Hh689989(v=OCS.15))

  - [Test-cswebappanonymous](https://technet.microsoft.com/library/Hh690041(v=OCS.15))

  - [테스트-CsWebScheduler](https://technet.microsoft.com/library/JJ204829(v=OCS.15))

  - [테스트-CsXmppIM](https://technet.microsoft.com/library/JJ205423(v=OCS.15))

  - [제거-CsDatabase](unhttps://technet.microsoft.com/library/Gg399044(v=OCS.15))

  - [제거-CsMirrorDatabase](unhttps://technet.microsoft.com/library/JJ204986(v=OCS.15))

  - [잠금 해제-CsClientPin](unhttps://technet.microsoft.com/library/Gg398650(v=OCS.15))

  - [게시 취소-Export-cslisconfiguration](unhttps://technet.microsoft.com/library/Gg398364(v=OCS.15))

  - [업데이트-Update-csaddressbook](https://technet.microsoft.com/library/Gg398194(v=OCS.15))

  - [업데이트-CsAdminRole](https://technet.microsoft.com/library/JJ204851(v=OCS.15))

  - [업데이트-CsTenantMeetingUrl](https://technet.microsoft.com/library/Dn424754(v=OCS.15))

  - [업데이트-CsUserData](https://technet.microsoft.com/library/JJ205358(v=OCS.15))

  - [업데이트-CsUserDatabase](https://technet.microsoft.com/library/Gg398682(v=OCS.15))

</div>

</div>

<span> </span>

</div>

</div>

</div>

