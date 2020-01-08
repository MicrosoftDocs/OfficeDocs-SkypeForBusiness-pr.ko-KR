---
title: 'Lync Server 2013: 주소록 관리용 가져오기-CsService'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Get-CsService for Address Book management
ms:assetid: 373b717d-5efa-4c36-a899-a23a5bd922b4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429698(v=OCS.15)
ms:contentKeyID: 48183853
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4cfa9bd42bb29ca32ab27dc64d2ee9a111abab8d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983378"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="get-csservice-for-address-book-management-in-lync-server-2013"></a>Lync Server 2013의 주소록 관리를 위한 Get CsService

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-11-01_

이 cmdlet을 실행할 수 있는 사용자: 기본적으로 다음 그룹의 구성원은 Get-CsService cmdlet을 로컬로 실행할 권한이 있습니다 (RTCUniversalUserAdmins, RTCUniversalServerAdmins). 이 cmdlet이 할당 된 모든 RBAC (역할 기반 액세스 제어) 역할 목록 (직접 만든 사용자 지정 RBAC 역할 포함)을 반환 하려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsService"}

Get-CsService는 인프라의 정의 된 웹 서비스에 대 한 현재 구성을 검색 하 고 표시 하는 데 유용 합니다. 풀의 FQDN (정규화 된 도메인 이름) 및 매개 변수 WebServer을 정의 하면 cmdlet은 주소록 처리기 및 메일 그룹 확장 Uri를 포함 하 여 서버에서 제공 하는 웹 기반 서비스를 반환 합니다.

예를 들면 다음과 같습니다.

    Get-CsService -PoolFqdn "fe01.contoso.net" -WebServer

이 cmdlet은 다음을 반환 합니다.

Id: WebServer "pool01.

작업 저장소: 네트워크 저장소:dc01. e 1.

UserServer: UserServer:pool01 net.tcp. e 1.

PrimaryHttpPort: 80

PrimaryHttpsPort: 443

ExternalHttpPort: 8080

ExternalHttpsPort: 4443

PublishedPrimaryHttpPort: 80

PublishedPrimaryHttpsPort: 443

PublishedExternalHttpPort: 80

PublishedExternalHttpsPort: 443

ReachPrimaryPsomServerPort: 8060

ReachExternalPsomServerPort: 8061

AppSharingPortStart: 49152

AppSharingPortCount: 16383

LIServiceInternalUri:https://internalweb.contoso.net/locationinformation/liservice.svc

ABHandlerInternalUri:https://internalweb.contoso.net/abs/handler

ABHandlerExternalUri:https://csweb.contoso.com/abs/handler

DLExpansionInternalUri :https://internalweb.contoso.net/groupexpansion/service.svc

DLExpansionExternalUri :https://csweb.contoso.com/groupexpansion/service.svc

CAHandlerInternalUri:https://internalweb.contoso.net/CertProv/CertProvisioningService.svc

CAHandlerInternalAnonUri:http://internalweb.contoso.net/CertProv/CertProvisioningService.svc

CollabContentInternalUri :https://internalweb.contoso.net/CollabContent

CollabContentExternalUri :https://csweb.contoso.com/CollabContent

CAHandlerExternalUri:https://csweb.contoso.com/CertProv/CertProvisioningService.svc

DeviceUpdateDownloadInternalUri:https://internalweb.contoso.net/RequestHandler/ucdevice.upx

DeviceUpdateDownloadExternalUri :https://csweb.contoso.com/RequestHandlerExt/ucdevice.upx

DeviceUpdateStoreInternalUri :http://internalweb.contoso.net/RequestHandler/Files

DeviceUpdateStoreExternalUri :https://csweb.contoso.com/RequestHandlerExt/Files

RgsAgentServiceInternalUri :https://internalweb.contoso.net/RgsClients/AgentService.svc

RgsAgentServiceExternalUri :https://csweb.contoso.com/RgsClients/AgentService.svc

MeetExternalUri :https://csweb.contoso.com/Meet

DialinExternalUri :https://csweb.contoso.com/Dialin

CscpInternalUri :https://internalweb.contoso.net/Cscp

ReachExternalUri :https://csweb.contoso.com/Reach

ReachInternalUri :https://internalweb.contoso.net/Reach

WebTicketExternalUri :https://csweb.contoso.com/WebTicket/WebTicketService.svc

WebTicketInternalUri :https://internalweb.contoso.net/WebTicket/WebTicketService.svc

ExternalFqdn: csweb.contoso.com

InternalFqdn: internalweb.contoso.net

DependentServiceList: {등록자 1], pool01. ConferencingServer:pool01. e t e}

ServiceId: 1-WebServices-1

SiteId: 사이트: Redmond

PoolFqdn: pool01.contoso.net

버전: 5

역할: WebServer

<div>

## <a name="see-also"></a>참고 항목


[Get-CsService](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

