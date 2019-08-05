---
title: QoE 테이블 목록
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/13/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 176194d7-d184-4e23-94bb-cb62b4db47f5
description: 데이터베이스 스키마는 다음 테이블로 구성 됩니다.
ms.openlocfilehash: ba6f439d97692a40fd485a2c550da079092d7365
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196560"
---
# <a name="list-of-qoe-tables"></a>QoE 테이블 목록
 
데이터베이스 스키마는 다음 테이블로 구성 됩니다. 
  
**지원 테이블**

|**테이블로**|**설명**|
|:-----|:-----|
|[AppSharingMetricsThreshold 테이블](appsharingmetricsthreshold.md) <br/> |응용 프로그램 공유에 사용 되는 경험 메트릭의 품질 기준에 대해 최적 및 허용 가능한 값을 저장 합니다.  <br/> |
|[CodecDescription 테이블](codecdescription.md) <br/> |고유 코덱 식별자를 해당 하는 코덱에 매핑합니다.  <br/> |
|[IPAddress 테이블](ipaddress.md) <br/> |환경 데이터베이스의 다른 위치에서 사용 되는 고유한 IP 주소 식별자에 IP 주소를 매핑합니다.  <br/> |
|[NetworkConnectionDetail 테이블](networkconnectiondetail.md) <br/> |네트워크 연결 형식을 경력 데이터베이스의 다른 곳에 사용 되는 네트워크 연결 식별자에 매핑합니다.  <br/> |
|[PurgeSettings 테이블 (체감 품질)](purgesettings-qoe.md) <br/> |오래 된 경력 품질 레코드가 체감 품질 데이터베이스에서 자동으로 삭제 되는지 여부를 지정 하는 정보를 저장 합니다.  <br/> |
|[TraceRoute 테이블](traceroute.md) <br/> |통화에 대 한 라우팅 정보를 저장 합니다.  <br/> |
|[UserAgentDef 테이블 (체감 품질)](useragentdef-qoe.md) <br/> |사용자 에이전트 식별자를 에이전트의 설명 이름에 매핑합니다.  <br/> |
|[VideoMetricsThreshold 테이블](videometricsthreshold.md) <br/> |영상 통화에 사용 되는 경험 메트릭의 품질 기준에 대 한 최적 및 허용 가능한 값을 저장 합니다.  <br/> |
|[UserAgent 테이블](useragent.md) <br/> |오디오 및 비디오 세션에 사용 되는 SIP (세션 초기화 프로토콜) 및 ua (Session User Agent) 문자열 및 UA 형식을 저장 합니다.  <br/> |
|[User 테이블](user-0.md) <br/> |오디오 및 비디오 세션에 사용 되는 사용자, 회의 및 전화 Uri를 저장 합니다.  <br/> |
|[Endpoint 테이블](endpoint.md) <br/> |오디오 및 비디오 세션에 참가 하는 끝점의 FQDN 컴퓨터 이름을 저장 합니다.  <br/> |
|[Pool 테이블](pool.md) <br/> |메트릭 데이터가 속한 풀의 이름을 저장 합니다.  <br/> |
|[Device 테이블](device.md) <br/> |오디오/비디오 통화에 사용 되는 캡처 장치 및 렌더링 장치를 저장 합니다.  <br/> |
|[DeviceDriver 테이블](devicedriver.md) <br/> |캡처 디바이스의 드라이버와 오디오/비디오 통화에 사용 되는 렌더링 장치를 저장 합니다.  <br/> |
|[Conference 테이블](conference.md) <br/> |다른 시나리오의 경우 컨퍼런스 시나리오 또는 DialogID 용 전화 회의 Uri를 저장 합니다.  <br/> |
|[SessionCorrelation 테이블](sessioncorrelation.md) <br/> |PSTN 통화에 대 한 CorrelationID을 저장 합니다.  <br/> |
|[PayloadDescription 테이블](payloaddescription.md) <br/> |오디오/비디오 통화에 사용 되는 코덱을 저장 합니다.  <br/> |
|[AppliedBandwidthSource 테이블](appliedbandwidthsource.md) <br/> |오디오/비디오 통화에 사용 되는 대역폭 원본을 저장 합니다.  <br/> |
|[MacAddress 테이블](macaddress.md) <br/> |오디오 및 비디오 세션에 참가 하는 끝점의 MAC 주소를 저장 합니다.  <br/> |
|[Dialog 테이블](dialog.md) <br/> |오디오 및 비디오 세션의 대화 상자 ID를 저장 합니다.  <br/> |
|[Region 테이블](region.md) <br/> |NC 설정에 정의 된 네트워크 지역을 저장 합니다.  <br/> |
|[UserSite 테이블](usersite.md) <br/> |NC 설정에 정의 된 네트워크 사이트를 저장 합니다.  <br/> |
|[Subnet 테이블](subnet.md) <br/> |NC 설정에 정의 된 서브넷을 저장 합니다.  <br/> |
|[MonitoredRegionLink 테이블](monitoredregionlink.md) <br/> |NC 설정에 정의 된 지역 링크를 저장 합니다.  <br/> |
|[MonitoredUserSiteLink 테이블](monitoredusersitelink.md) <br/> |NC 설정에 정의 된 네트워크 사이트 링크를 저장 합니다.  <br/> |
|[EndpointSubnet 테이블](endpointsubnet.md) <br/> |오디오 및 비디오 세션에 참여 하는 끝점의 서브넷을 저장 합니다.  <br/> |
|[Server 테이블](server.md) <br/> |미디어가 거치는 서버의 FQDN 또는 IP 주소를 저장 합니다.  <br/> |
   
**메트릭 데이터 테이블**

|**테이블로**|**설명**|
|:-----|:-----|
|[AppSharingStream 테이블](appsharingstream.md) <br/> |응용 프로그램 공유에 사용 되는 네트워크 스트림에 대 한 경험 메트릭의 품질 기준을 저장 합니다. 응용 프로그램 공유에 사용 되는 네트워크 스트림에 대 한 경험 메트릭의 품질 메트릭입니다.  <br/> |
|[Session 테이블](session.md) <br/> |오디오 또는 오디오/비디오 세션에 대 한 전체 정보를 저장 합니다. 세션은 두 끝점 간의 오디오 또는 비디오 SIP 대화 상자로 정의 됩니다.  <br/> |
|[MediaLine 테이블](medialine-0.md) <br/> |세션의 각 미디어 라인에 대 한 정보를 저장 합니다. 미디어 선은 하나 이상의 오디오 및 비디오 스트림 모음입니다. 일반적으로 단일 미디어 회선에는 두 개의 스트림 (오디오 또는 비디오)이 있습니다.  <br/> |
|[AudioStream 테이블](audiostream.md) <br/> |미디어 라인에 각 오디오 스트림에 대 한 오디오 미디어 품질 메트릭을 저장 합니다.  <br/> |
|[AudioSignal 테이블](audiosignal.md) <br/> |미디어 라인에 오디오 미디어 품질 메트릭을 저장 합니다. 여기에는 AEC (음향 반향 제거) 및 AGC (자동 게인 제어) 메트릭이 포함 됩니다.  <br/> |
|[VideoStream 테이블](videostream.md) <br/> |미디어 라인의 각 오디오 스트림에 대 한 비디오 미디어 품질 기준을 저장 합니다.  <br/> |
|[AudioClientEvent 테이블](audioclientevent.md) <br/> |클라이언트 이벤트에서 수집 된 오디오 미디어 품질 메트릭을 저장 합니다.  <br/> |
|[VideoClientEvent 테이블](videoclientevent.md) <br/> |클라이언트 이벤트에서 수집 된 비디오 미디어 품질 메트릭을 저장 합니다.  <br/> |
|**DiagnosticData 테이블** <br/> |내부용 으로만 사용 되는 진단 데이터를 저장 합니다.  <br/> |
   
**요약 데이터 표**

|**테이블로**|**설명**|
|:-----|:-----|
|**ServerSummary 테이블** <br/> |서버에 대 한 요약 데이터를 저장 하 고, 이러한 데이터는 경력 (체감 품질) 보고용 으로만 사용 됩니다.  <br/> |
|**UserSummary 테이블** <br/> |사용자에 대 한 요약 데이터를 저장 하 고, 이러한 데이터는 체감 품질 보고에만 사용 됩니다.  <br/> |
|**Call유형 Ummary 테이블** <br/> |통화 형식에 대 한 요약 데이터를 저장 하는 경우 이러한 데이터는 체감 품질 보고에만 사용 됩니다.  <br/> |
   
**모니터링 서버에서 내부용으로 사용 되는 테이블**

|**테이블로**|**설명**|
|:-----|:-----|
|**DbConfigDateTime** <br/> |내부용 으로만 사용 됩니다.  <br/> |
|**DbConfigInt** <br/> |내부용 으로만 사용 됩니다.  <br/> |
|**프런트 엔드 테이블** <br/> |내부용 으로만 사용 됩니다.  <br/> |
|**작업 테이블** <br/> |내부용 으로만 사용 됩니다.  <br/> |
|**SummaryTableConfiguration** <br/> |내부용 으로만 사용 됩니다.  <br/> |
|**DbErrorMessage** <br/> |내부용 으로만 사용 됩니다.  <br/> |
|**MetricsThreshold** <br/> |내부용 으로만 사용 됩니다.  <br/> |
|**DaylightSavingYears** <br/> |내부용 으로만 사용 됩니다.  <br/> |
|**TimeZoneConfiguration** <br/> |내부용 으로만 사용 됩니다.  <br/> |
|**시간대** <br/> |내부용 으로만 사용 됩니다.  <br/> |
|**CallSummary 테이블** <br/> |내부용 으로만 사용 됩니다.  <br/> |
|**DeviceCallSumary 테이블** <br/> |내부용 으로만 사용 됩니다.  <br/> |
|**테 넌 트 테이블** <br/> |내부용 으로만 사용 됩니다.  <br/> |
|**VideoCallSummaryTable** <br/> |내부용 으로만 사용 됩니다.  <br/> |
|**Ascall요약 테이블** <br/> |내부용 으로만 사용 됩니다.  <br/> |
   

