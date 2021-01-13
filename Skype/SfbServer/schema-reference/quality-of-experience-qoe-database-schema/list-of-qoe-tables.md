---
title: QoE 테이블 목록
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/13/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 176194d7-d184-4e23-94bb-cb62b4db47f5
description: 데이터베이스 스키마는 다음 테이블로 구성됩니다.
ms.openlocfilehash: 291d2ddefefc264aa283480362a6f57cda9161cd
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834488"
---
# <a name="list-of-qoe-tables"></a>QoE 테이블 목록
 
데이터베이스 스키마는 다음 테이블로 구성됩니다. 
  
**지원 테이블**

|**표**|**설명**|
|:-----|:-----|
|[AppSharingMetricsThreshold 테이블](appsharingmetricsthreshold.md) <br/> |응용 프로그램 공유에 사용되는 체감 품질 메트릭에 대한 최적의 값과 적절한 값을 저장합니다.  <br/> |
|[CodecDescription 테이블](codecdescription.md) <br/> |고유 코덱 식별자를 해당 코덱에 매핑합니다.  <br/> |
|[IPAddress 테이블](ipaddress.md) <br/> |IP 주소를 체감 품질 데이터베이스의 다른 위치에서 사용되는 고유 IP 주소 식별자에 매핑합니다.  <br/> |
|[NetworkConnectionDetail 테이블](networkconnectiondetail.md) <br/> |네트워크 연결 유형을 체감 품질 데이터베이스의 다른 위치에서 사용되는 네트워크 연결 식별자에 매핑합니다.  <br/> |
|[PurgeSettings 테이블(QoE)](purgesettings-qoe.md) <br/> |오래된 체감 품질 레코드가 QoE 데이터베이스에서 자동으로 삭제되는지 여부 및 삭제되는 시간을 지정하는 정보를 저장합니다.  <br/> |
|[TraceRoute 테이블](traceroute.md) <br/> |통화 라우팅 정보를 저장합니다.  <br/> |
|[UserAgentDef 테이블(QoE)](useragentdef-qoe.md) <br/> |사용자 에이전트 식별자를 에이전트의 설명이 있는 이름에 매핑합니다.  <br/> |
|[VideoMetricsThreshold 테이블](videometricsthreshold.md) <br/> |비디오 통화에 사용되는 체감 품질 메트릭에 대한 최적의 값과 적절한 값을 저장합니다.  <br/> |
|[UserAgent 테이블](useragent.md) <br/> |오디오 및 비디오 세션에서 사용되는 SIP(Session Initiation Protocol) UA(사용자 에이전트) 문자열 및 UA 유형을 저장합니다.  <br/> |
|[User 테이블](user-0.md) <br/> |오디오 및 비디오 세션에서 사용되는 사용자, 회의 및 전화 URI를 저장합니다.  <br/> |
|[끝점 테이블](endpoint.md) <br/> |오디오 및 비디오 세션에 참가하는 끝점의 FQDN 컴퓨터 이름을 저장합니다.  <br/> |
|[Pool 테이블](pool.md) <br/> |메트릭 데이터가 속하는 풀 이름을 저장합니다.  <br/> |
|[Device 테이블](device.md) <br/> |오디오/비디오 통화에서 사용되는 캡처 장치 및 렌더링 장치를 저장합니다.  <br/> |
|[DeviceDriver 테이블](devicedriver.md) <br/> |오디오/비디오 통화에서 사용되는 캡처 장치 및 렌더링 장치에 대한 드라이버를 저장합니다.  <br/> |
|[Conference 테이블](conference.md) <br/> |회의 시나리오에 대한 회의 URI 또는 기타 시나리오에 대한 DialogID를 저장합니다.  <br/> |
|[SessionCorrelation 테이블](sessioncorrelation.md) <br/> |PSTN 통화에 대한 CorrelationID를 저장합니다.  <br/> |
|[PayloadDescription 테이블](payloaddescription.md) <br/> |오디오/비디오 통화에서 사용되는 코덱을 저장합니다.  <br/> |
|[AppliedBandwidthSource 테이블](appliedbandwidthsource.md) <br/> |오디오/비디오 통화에서 사용되는 대역폭 소스를 저장합니다.  <br/> |
|[MacAddress 테이블](macaddress.md) <br/> |오디오 및 비디오 세션에 참가하는 끝점의 MAC 주소를 저장합니다.  <br/> |
|[Dialog 테이블](dialog.md) <br/> |오디오 및 비디오 세션의 대화 ID를 저장합니다.  <br/> |
|[Region 테이블](region.md) <br/> |NCS 설정에 정의된 네트워크 영역을 저장합니다.  <br/> |
|[UserSite 테이블](usersite.md) <br/> |NCS 설정에 정의된 네트워크 사이트를 저장합니다.  <br/> |
|[서브넷 테이블](subnet.md) <br/> |NCS 설정에 정의된 서브넷을 저장합니다.  <br/> |
|[MonitoredRegionLink 테이블](monitoredregionlink.md) <br/> |NCS 설정에 정의된 영역 링크를 저장합니다.  <br/> |
|[MonitoredUserSiteLink 테이블](monitoredusersitelink.md) <br/> |NCS 설정에 정의된 네트워크 사이트를 저장합니다.  <br/> |
|[EndpointSubnet 테이블](endpointsubnet.md) <br/> |오디오 및 비디오 세션에 참가하는 끝점의 서브넷을 저장합니다.  <br/> |
|[Server 테이블](server.md) <br/> |미디어가 통과하는 서버의 FQDN 또는 IP 주소를 저장합니다.  <br/> |
   
**메트릭 데이터 테이블**

|**표**|**설명**|
|:-----|:-----|
|[AppSharingStream 테이블](appsharingstream.md) <br/> |응용 프로그램 공유에 사용되는 네트워크 스트림에 대한 체감 품질 메트릭을 저장합니다.  <br/> |
|[Session 테이블](session.md) <br/> |오디오 또는 오디오/비디오 세션에 대한 전체 정보를 저장합니다. 세션은 두 끝점 사이의 오디오 또는 비디오 SIP 대화로 정의됩니다.  <br/> |
|[MediaLine 테이블](medialine-0.md) <br/> |세션에서 각 미디어 회선에 대한 정보를 저장합니다. 미디어 회선은 하나 이상의 오디오 및 비디오 스트림의 모음입니다. 일반적으로 단일 미디어 회선에는 오디오 또는 비디오의 두 스트림이 포함됩니다.  <br/> |
|[AudioStream 테이블](audiostream.md) <br/> |미디어 회선에서 각 오디오 스트림에 대한 오디오 미디어 품질 메트릭을 저장합니다.  <br/> |
|[AudioSignal 테이블](audiosignal.md) <br/> |미디어 회선에서 오디오 미디어 품질 메트릭을 저장합니다. 여기에는 AEC(음향 반향 취소) 및 AGC(자동 게인 컨트롤) 메트릭이 포함됩니다.  <br/> |
|[VideoStream 테이블](videostream.md) <br/> |미디어 회선에서 각 오디오 스트림에 대한 비디오 미디어 품질 메트릭을 저장합니다.  <br/> |
|[AudioClientEvent 테이블](audioclientevent.md) <br/> |클라이언트 이벤트에서 수집된 오디오 미디어 품질 메트릭을 저장합니다.  <br/> |
|[VideoClientEvent 테이블](videoclientevent.md) <br/> |클라이언트 이벤트에서 수집된 비디오 미디어 품질 메트릭을 저장합니다.  <br/> |
|**DiagnosticData 테이블** <br/> |내부 전용인 진단 데이터를 저장합니다.  <br/> |
   
**요약 데이터 테이블**

|**표**|**설명**|
|:-----|:-----|
|**ServerSummary 테이블** <br/> |서버에 대한 요약 데이터를 저장합니다. 이러한 데이터는 QoE(체감 품질) 보고용으로만 사용됩니다.  <br/> |
|**UserSummary 테이블** <br/> |사용자에 대한 요약 데이터를 저장합니다. 이러한 데이터는 QoE 보고용으로만 사용됩니다.  <br/> |
|**CallTypeSummary 테이블** <br/> |호출 유형에 대한 요약 데이터를 저장합니다. 이러한 데이터는 QoE 보고용으로만 사용됩니다.  <br/> |
   
**모니터링 서버에서 사용하는 내부용 테이블**

|**표**|**설명**|
|:-----|:-----|
|**DbConfigDateTime** <br/> |내부 용도로만 사용됩니다.  <br/> |
|**DbConfigInt** <br/> |내부 용도로만 사용됩니다.  <br/> |
|**FrontEnd 테이블** <br/> |내부 용도로만 사용됩니다.  <br/> |
|**Task 테이블** <br/> |내부 용도로만 사용됩니다.  <br/> |
|**SummaryTableConfiguration** <br/> |내부 용도로만 사용됩니다.  <br/> |
|**DbErrorMessage** <br/> |내부 용도로만 사용됩니다.  <br/> |
|**MetricsThreshold** <br/> |내부 용도로만 사용됩니다.  <br/> |
|**DaylightSavingYears** <br/> |내부 용도로만 사용됩니다.  <br/> |
|**TimeZoneConfiguration** <br/> |내부 용도로만 사용됩니다.  <br/> |
|**TimeZones** <br/> |내부 용도로만 사용됩니다.  <br/> |
|**CallSummary 테이블** <br/> |내부 용도로만 사용됩니다.  <br/> |
|**DeviceCallSumary 테이블** <br/> |내부 용도로만 사용됩니다.  <br/> |
|**Tenant 테이블** <br/> |내부 용도로만 사용됩니다.  <br/> |
|**VideoCallSummaryTable** <br/> |내부 용도로만 사용됩니다.  <br/> |
|**ASCallSummaryTable** <br/> |내부 용도로만 사용됩니다.  <br/> |
   

