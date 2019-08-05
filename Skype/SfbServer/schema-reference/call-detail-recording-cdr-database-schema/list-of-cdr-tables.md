---
title: 비즈니스용 Skype 서버 2015의 CDR 테이블 목록
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 031843fd-c7ff-4534-9b02-8847aad70807
description: CDR (통화 정보 기록) 데이터베이스 스키마는 다음 테이블로 구성 됩니다.
ms.openlocfilehash: a8d36d75f629b41c535de99c0b9aef42770ba573
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196735"
---
# <a name="list-of-cdr-tables-in-skype-for-business-server-2015"></a>비즈니스용 Skype 서버 2015의 CDR 테이블 목록
 
CDR (통화 정보 기록) 데이터베이스 스키마는 다음 테이블로 구성 됩니다. 
  
## <a name="static-tables"></a>정적 테이블

|**테이블로**|**설명**|
|:-----|:-----|
|[비즈니스용 Skype 서버 2015의 CallPriorities 순위 표](callpriorities.md) <br/> |긴급, 긴급, 일반, 비 긴급 등의 가능 통화 우선 순위 목록을 저장 합니다.  <br/> |
|[비즈니스용 Skype 서버 2015의 ConferenceJoinTimeThresholds 테이블](conferencejointimethresholds.md) <br/> |컨퍼런스 참가 시간 요약 보고서에 사용 되는 분류 경계를 저장 합니다.  <br/> |
|[비즈니스용 Skype 서버 2015의 DeRegisterType 테이블](deregistertype.md) <br/> |"클라이언트 시작 됨", "등록 만료," "클라이언트 충돌" 등의 사용 가능 사용자 등록 취소의 목록을 저장 합니다.  <br/> |
|[MediaList 테이블](medialist.md) <br/> |데이터베이스에 항목을 생성할 수 있는 미디어 유형 목록 (예: IM, 오디오, 비디오, 파일 전송)을 저장 합니다.  <br/> |
|[PurgeSettings 테이블](purgesettings.md) <br/> |오래 된 통화 정보 레코드가 CDR 데이터베이스에서 자동으로 삭제 되는지 여부를 지정 하는 정보를 저장 합니다.  <br/> |
|[Roles 테이블](roles.md) <br/> |가능한 컨퍼런스 역할 목록 (예: 참석자 및 발표자)을 저장 합니다.  <br/> |
|[SIPResponseMetaData 테이블](sipresponsemetadata.md) <br/> |SIP 응답 코드와 이러한 코드의 분류 및 정의 목록을 저장 합니다.  <br/> |
   
## <a name="supporting-tables"></a>지원 테이블

|**테이블로**|**설명**|
|:-----|:-----|
|[비즈니스용 Skype 서버 2015의 ClientVersions 테이블](clientversions.md) <br/> |이 데이터베이스에서 캡처한 정보를 사용 하 여 호출에 참여 하는 각 클라이언트의 클라이언트 (클라이언트 유형 및 버전 번호)를 저장 합니다.  <br/> |
|[비즈니스용 Skype 서버 2015의 ConferenceUris 테이블](conferenceuris.md) <br/> |전화 회의 관련 통화에 사용 되는 ConferenceURIs 목록을 저장 합니다.  <br/> |
|[비즈니스용 Skype 서버 2015의 ContentTypes 테이블](contenttypes.md) <br/> |피어 투 피어 통화와 전화 회의에 사용 되는 SIP (세션 초기화 프로토콜) 콘텐츠 형식 목록을 저장 합니다.  <br/> |
|[비즈니스용 Skype 서버 2015의 장치 테이블](devices.md) <br/> |제조업체, 하드웨어 버전, MAC 주소 등 장치 목록을 저장 합니다.  <br/> |
|[비즈니스용 Skype 서버 2015의 대화 상자 테이블](dialogs.md) <br/> |데이터베이스의 각 세션에 대 한 대화 상자 ID에 대 한 정보를 저장 합니다.  <br/> |
|[비즈니스용 Skype 서버 2015의 EdgeServers 테이블](edgeservers.md) <br/> |외부 통화에 사용 되는 Edge 서버의 목록을 저장 합니다.  <br/> |
|[비즈니스용 Skype 서버 2015의 게이트웨이 테이블](gateways.md) <br/> |VoIP (Voice over 인터넷 프로토콜) 통화에 사용 되는 게이트웨이 목록을 저장 합니다.  <br/> |
|[비즈니스용 Skype 서버 2015의 HardwareVersions 테이블](hardwareversions.md) <br/> |장치 (일반 전화기)의 하드웨어 버전 목록을 저장 합니다.  <br/> |
|[비즈니스용 Skype 서버 2015의 제조업체 테이블](manufacturers.md) <br/> |장치 제조업체 (일반 전화기) 목록을 저장 합니다.  <br/> |
|[비즈니스용 Skype 서버 2015의 Mcus 테이블](mcus.md) <br/> |다양 한 A/V 회의 서버와 해당 Uri에 대 한 정보를 저장 합니다.  <br/> |
|[MediationServers 테이블](mediationservers.md) <br/> |VoIP 통화에 사용 되는 중재 서버 목록을 저장 합니다.  <br/> |
|[Phones 테이블](phones.md) <br/> |보관 되었거나 통화 정보가 기록 된 VoIP 통화에 사용 된 모든 전화 번호를 저장 합니다.  <br/> |
|[Pools 테이블](pools.md) <br/> |메신저 대화 메시지가 캡처되는 풀의 이름을 저장 합니다.  <br/> |
|[Servers 테이블](servers.md) <br/> |통화에 관련 된 서버의 이름을 저장 합니다.  <br/> |
|[Tenants 테이블](tenants.md) <br/> |현재 배포에서 지원 되는 테 넌 트를 저장 합니다. 엔터프라이즈 사용자, 페더레이션 사용자, 공용 IM 연결 사용자, 익명 사용자를 위한 일부 빌드 비 테 넌 트가 있습니다.  <br/> |
|[UserAgentDef 테이블](useragentdef.md) <br/> |사용자 에이전트 식별자를 에이전트의 설명 이름에 매핑합니다.  <br/> |
|[Users 테이블](users.md) <br/> |이 데이터베이스에 기록 되거나 보관 된 세션에 참가 한 사용자의 사용자 Uri를 저장 합니다.  <br/> |
|[UserStatistics 테이블](userstatistics.md) <br/> |시스템의 개별 사용자 사용에 대 한 정보를 저장 합니다.  <br/> |
   
## <a name="tables-specific-to-conference-cdr-records"></a>컨퍼런스 CDR 레코드에 해당 하는 테이블

|**테이블로**|**설명**|
|:-----|:-----|
|[비즈니스용 Skype 서버 2015의 컨퍼런스 표](conferences.md) <br/> |보관 되었거나 ConferenceURI, 시작 및 종료 시간을 비롯 한 세부 정보가 기록 된 모든 컨퍼런스에 대 한 정보를 저장 합니다.  <br/> |
|[비즈니스용 Skype 서버 2015의 ConferenceSessionDetails 테이블](conferencesessiondetails-0.md) <br/> |시작 및 종료 시간, 사용자 ID, 응답 코드, 각 세션에 대 한 진단 ID 등 모든 SIP 기반 회의 세션에 대 한 정보를 저장 합니다.  <br/> |
|[비즈니스용 Skype 서버 2015의 FocusJoinsAndLeaves 테이블](focusjoinsandleaves.md) <br/> |사용자 역할 및 클라이언트 버전을 포함 하 여 컨퍼런스 참가 및 탈퇴에 대 한 정보를 저장 합니다.  <br/> |
|[비즈니스용 Skype 서버 2015의 McuJoinsAndLeaves 테이블](mcujoinsandleaves.md) <br/> |회의와 관련 된 A/V 회의 서버와 사용자 참가 및 종료 시간에 대 한 정보를 저장 합니다.  <br/> |
   
## <a name="tables-for-messages-in-im-conferences"></a>메신저 대화 회의의 메시지 표

|**테이블로**|**설명**|
|:-----|:-----|
|[비즈니스용 Skype 서버 2015의 ConferenceMessageCount 테이블](conferencemessagecount.md) <br/> |각 메신저 대화 회의에 대해 각 사용자가 보낸 메시지 수를 저장 합니다.  <br/> |
|[비즈니스용 Skype 서버 2015의 IMReportSummary 테이블](imreportsummary.md) <br/> |조직에 보관 된 인스턴트 메시징 세션에 대 한 전체 보고서를 제공 합니다.  <br/> |
   
## <a name="tables-for-peer-to-peer-sessions"></a>피어 투 피어 세션 표

|**테이블로**|**설명**|
|:-----|:-----|
|[SessionDetails 테이블](sessiondetails.md) <br/> |시작 및 종료 시간, 사용자 ID, 응답 코드, 각 사용자의 메시지 수 등 모든 피어 투 피어 세션에 대 한 정보를 저장 합니다.  <br/> |
|[비즈니스용 Skype 서버 2015의 FileTransfers 테이블](filetransfers-0.md) <br/> |파일 이름 및 결과 (수락, 거부 또는 취소 됨)를 포함 하 여 파일 전송 세션에 대 한 정보를 저장 합니다.  <br/> |
|[Media 테이블](media.md) <br/> |피어 투 피어 세션에 관련 된 다양 한 미디어 형식에 대 한 정보를 저장 합니다.  <br/> |
   
## <a name="table-for-voip-call-details"></a>VoIP 통화 정보 표

|**테이블로**|**설명**|
|:-----|:-----|
|[VoipDetails 테이블](voipdetails-0.md) <br/> |두 개의 파티 VoIP/PSTN 통화에 대해 VoIP 전화기의 전화 ID, 게이트웨이 사용, 그리고 연결 끊긴 파티와 같은 통화에 대 한 정보를 저장 합니다. 호출 시작/종료 시간 및 응답 코드에 대 한 [Sessiondetails 테이블](sessiondetails.md) 을 참조 합니다. <br/> |
   
> [!NOTE]
> 한 통화에 대 한 한 자가 VoIP 사용자 이거나 중재 서버가 통화에 참여 하 고 있는 경우에는이 테이블에 레코드가 생성 됩니다. PSTN (공개 교환 통신망) 휴대폰을 포함 하지 않는 VoIP/VoIP 통화에 대 한 정보는 [Sessiondetails 테이블](sessiondetails.md)에서 캡처합니다. 
  
## <a name="table-for-e9-1-1-call-auditing"></a>E9-1-1 통화 감사 표

|**테이블로**|**설명**|
|:-----|:-----|
|[비즈니스용 Skype 서버 2015의 위치 테이블](locations.md) <br/> |향상 된 9-1-1 (E9-1) 통화와 같은 각 비상 통화에 대해 통화에 대 한 위치 정보를 저장 합니다. 호출 시작/종료 시간 및 응답 코드에 대 한 [Sessiondetails 테이블](sessiondetails.md) 을 참조 합니다. <br/> |
   
> [!NOTE]
> 이 표에는 E9-1-1 통화에 대 한 위치 blob만 포함 되어 있습니다. 통화에 대 한 기타 자세한 정보를 보려면 SessionDetails 테이블을 참조 하세요. 
  
## <a name="tables-for-troubleshooting"></a>문제 해결 표

|**테이블로**|**설명**|
|:-----|:-----|
|[비즈니스용 Skype 서버 2015의 응용 프로그램 테이블](application.md) <br/> |라우팅 및 연결과 관련 된 비즈니스용 Skype 서버 2015에 있는 다양 한 프로세스에 대 한 정보를 저장 합니다.  <br/> |
|[비즈니스용 Skype 서버 2015의 CallType 테이블](calltype.md) <br/> |"오디오", "인스턴트 메시징", "오디오 및 비디오" 및 "응용 프로그램 공유"와 같은 통화 유형에 대 한 정보를 저장 합니다.  <br/> |
|[비즈니스용 Skype 서버 2015의 ErrorCategory 테이블](errorcategory.md) <br/> |각 비즈니스용 Skype Server 2015 진단 분류에 대 한 친숙 한 이름을 저장 합니다.  <br/> |
|[비즈니스용 Skype 서버 2015의 ErrorDef 테이블](errordef.md) <br/> |오류 유형과 해당 정의에 대 한 정보를 저장 합니다.  <br/> |
|[비즈니스용 Skype 서버 2015의 ErrorReport 테이블](errorreport.md) <br/> |발생 한 오류에 대 한 정보를 저장 합니다.  <br/> |
|[ProgressReport 테이블](progressreport.md) <br/> |비즈니스용 Skype 서버 2015 프로세스에 포함 된 다양 한 단계의 진행 상황 보고서에 대 한 정보를 저장 합니다.  <br/> |
   
다음 목록의 표는 비즈니스용 Skype 서버 2015에서 내부적으로 사용 됩니다. 세부 정보는이 문서에 설명 되어 있지 않습니다.
  
## <a name="tables-for-internal-use-by-lync-server"></a>Lync 서버에서 내부용으로 사용 하는 테이블

|**테이블로**|**설명**|
|:-----|:-----|
|**DbConfigDateTime** <br/> |내부용 으로만 사용 됩니다.  <br/> |
|**DbConfigInt** <br/> |내부용 으로만 사용 됩니다.  <br/> |
|**DbErrorMessage** <br/> |내부용 으로만 사용 됩니다.  <br/> |
|**프런트 엔드 테이블** <br/> |내부용 으로만 사용 됩니다.  <br/> |
|**MSMQProcessing 테이블** <br/> |내부용 으로만 사용 됩니다.  <br/> |
|**SummaryTableConfiguration** <br/> |내부용 으로만 사용 됩니다.  <br/> |
|**Syndicators 테이블** <br/> |내부용 으로만 사용 됩니다.  <br/> |
|**SyndicatorsTenantMap 테이블** <br/> |내부용 으로만 사용 됩니다.  <br/> |
|**작업 테이블** <br/> |내부용 으로만 사용 됩니다.  <br/> |
|**UserStatistics** <br/> |내부용 으로만 사용 됩니다.  <br/> |
|**UsageSummary_UQ** <br/> |내부용 으로만 사용 됩니다.  <br/> |
|**Usagesmary** <br/> |내부용 으로만 사용 됩니다.  <br/> |
|**DaylightSavingYears** <br/> |내부용 으로만 사용 됩니다.  <br/> |
|**TimeZoneConfiguration** <br/> |내부용 으로만 사용 됩니다.  <br/> |
|**시간대** <br/> |내부용 으로만 사용 됩니다.  <br/> |
|**FailureSummary_UQ** <br/> |내부용 으로만 사용 됩니다.  <br/> |
|**FailureSummary** <br/> |내부용 으로만 사용 됩니다.  <br/> |
|**ServerSummary** <br/> |내부용 으로만 사용 됩니다.  <br/> |
|**MsDiagMetaData** <br/> |내부용 으로만 사용 됩니다.  <br/> |
   

