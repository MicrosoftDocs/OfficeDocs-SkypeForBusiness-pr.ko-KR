---
title: 비즈니스용 Skype 서버의 CDR 테이블 목록
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 031843fd-c7ff-4534-9b02-8847aad70807
description: CDR(통화 정보 기록) 데이터베이스 스키마는 다음과 같은 테이블로 구성됩니다.
ms.openlocfilehash: 7bd76a4cf374e72582c585908309605c4845454e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827598"
---
# <a name="list-of-cdr-tables-in-skype-for-business-server-2015"></a>비즈니스용 Skype 서버의 CDR 테이블 목록
 
CDR(통화 정보 기록) 데이터베이스 스키마는 다음과 같은 테이블로 구성됩니다. 
  
## <a name="static-tables"></a>정적 테이블

|**표**|**설명**|
|:-----|:-----|
|[비즈니스용 Skype 서버의 CallPriorities 테이블](callpriorities.md) <br/> |응급, 긴급, 정상, 일반 등 가능한 통화 우선 순위 목록을 저장합니다.  <br/> |
|[비즈니스용 Skype 서버의 ConferenceJoinTimeThresholds 테이블](conferencejointimethresholds.md) <br/> |회의 참가 시간 요약 보고서에서 사용하는 분류 경계를 저장합니다.  <br/> |
|[비즈니스용 Skype 서버의 DeRegisterType 테이블](deregistertype.md) <br/> |"client initiated", "registration expired", "client crash" 등 가능한 사용자 등록 취소 이유 목록을 저장합니다.  <br/> |
|[MediaList 테이블](medialist.md) <br/> |데이터베이스에 항목을 생성할 수 있는 미디어 유형 목록(예: IM, 오디오, 비디오 및 파일 전송)을 저장합니다.  <br/> |
|[PurgeSettings 테이블](purgesettings.md) <br/> |오래된 통화 정보 기록이 CDR 데이터베이스에서 자동으로 삭제되는지 여부 및 삭제되는 시간을 지정하는 정보를 저장합니다.  <br/> |
|[Roles 테이블](roles.md) <br/> |가능한 회의 역할 목록(예: 참석자 및 발표자)을 저장합니다.  <br/> |
|[SIPResponseMetaData 테이블](sipresponsemetadata.md) <br/> |SIP 응답 코드 목록과 이러한 각 코드의 분류 및 정의를 저장합니다.  <br/> |
   
## <a name="supporting-tables"></a>지원 테이블

|**표**|**설명**|
|:-----|:-----|
|[비즈니스용 Skype 서버의 ClientVersions 테이블](clientversions.md) <br/> |이 데이터베이스에서 캡처된 정보와 함께 통화에 포함된 각 클라이언트의 클라이언트 정보(클라이언트 유형 및 버전 번호 모두)를 저장합니다.  <br/> |
|[비즈니스용 Skype 서버의 ConferenceUris 테이블](conferenceuris.md) <br/> |회의 관련 통화에 사용되는 ConferenceURIs 목록을 저장합니다.  <br/> |
|[비즈니스용 Skype 서버의 ContentTypes 테이블](contenttypes.md) <br/> |피어 투 피어 통화 및 회의 통화에 모두 사용되는 SIP(Session Initiation Protocol) 콘텐츠 유형의 목록을 저장합니다.  <br/> |
|[비즈니스용 Skype 서버의 Devices 테이블](devices.md) <br/> |제조업체, 하드웨어 버전 및 MAC 주소를 포함하는 장치 목록을 저장합니다.  <br/> |
|[비즈니스용 Skype 서버의 Dialogs 테이블](dialogs.md) <br/> |데이터베이스에 있는 각 세션의 대화 ID에 대한 정보를 저장합니다.  <br/> |
|[비즈니스용 Skype 서버의 EdgeServers 테이블](edgeservers.md) <br/> |외부 통화에 사용되는 에지 서버 목록을 저장합니다.  <br/> |
|[비즈니스용 Skype 서버의 Gateways 테이블](gateways.md) <br/> |VoIP(Voice over Internet Protocol) 통화에 사용되는 게이트웨이 목록을 저장합니다.  <br/> |
|[비즈니스용 Skype 서버의 HardwareVersions 테이블](hardwareversions.md) <br/> |장치(일반 전화)의 하드웨어 버전 목록을 저장합니다.  <br/> |
|[비즈니스용 Skype 서버의 Manufacturers 테이블](manufacturers.md) <br/> |장치(일반 전화)의 제조업체 목록을 저장합니다.  <br/> |
|[비즈니스용 Skype 서버의 Mcus 테이블](mcus.md) <br/> |다양한 A/V 회의 서버 및 해당 URL에 대한 정보를 저장합니다.  <br/> |
|[MediationServers 테이블](mediationservers.md) <br/> |VoIP 통화에 사용되는 중재 서버 목록을 저장합니다.  <br/> |
|[Phones 테이블](phones.md) <br/> |보관된 VoIP 통화에 사용되거나 해당 통화 세부 정보가 기록된 모든 전화 번호를 저장합니다.  <br/> |
|[Pools 테이블](pools.md) <br/> |IM 메시지가 캡처되는 풀의 이름을 저장합니다.  <br/> |
|[Servers 테이블](servers.md) <br/> |통화에 연관된 서버 이름을 저장합니다.  <br/> |
|[Tenants 테이블](tenants.md) <br/> |현재 배포에서 지원되는 테넌트를 저장합니다. 엔터프라이즈 사용자, 페더레이션 사용자, 공용 IM 연결 사용자 및 익명 사용자를 위한 몇 가지 기본 제공 테넌트가 있습니다.  <br/> |
|[UserAgentDef 테이블](useragentdef.md) <br/> |사용자 에이전트 식별자를 에이전트의 설명이 있는 이름에 매핑합니다.  <br/> |
|[Users 테이블](users.md) <br/> |이 데이터베이스에 기록 및 보관된 세션에 참여한 사용자의 사용자 URI를 저장합니다.  <br/> |
|[UserStatistics 테이블](userstatistics.md) <br/> |개별 사용자의 시스템 사용에 대한 정보를 저장합니다.  <br/> |
   
## <a name="tables-specific-to-conference-cdr-records"></a>회의 CDR 레코드 관련 테이블

|**표**|**설명**|
|:-----|:-----|
|[비즈니스용 Skype 서버의 전화 회의 테이블](conferences.md) <br/> |ConferenceURI 및 시작/종료 시간을 포함하여 보관된 회의 또는 세부 정보가 기록된 회의에 대한 모든 정보를 저장합니다.  <br/> |
|[비즈니스용 Skype 서버의 ConferenceSessionDetails 테이블](conferencesessiondetails-0.md) <br/> |시작 및 종료 시간, 사용자 ID, 응답 코드 및 각 세션에 대한 진단 ID를 포함하여 모든 SIP 기반 회의 세션에 대한 정보를 저장합니다.  <br/> |
|[비즈니스용 Skype 서버의 FocusJoinsAndLeaves 테이블](focusjoinsandleaves.md) <br/> |사용자의 역할 및 클라이언트 버전을 포함하여 회의 참가 및 퇴장에 대한 정보를 저장합니다.  <br/> |
|[비즈니스용 Skype 서버의 McuJoinsAndLeaves 테이블](mcujoinsandleaves.md) <br/> |회의에 관련된 A/V 회의 서버 및 사용자의 참가 및 종료 시간에 대한 정보를 저장합니다.  <br/> |
   
## <a name="tables-for-messages-in-im-conferences"></a>IM 회의의 메시지 테이블

|**표**|**설명**|
|:-----|:-----|
|[비즈니스용 Skype 서버의 ConferenceMessageCount 테이블](conferencemessagecount.md) <br/> |각 IM 회의에 대해 각 사용자가 전송한 메시지 수를 저장합니다.  <br/> |
|[비즈니스용 Skype 서버의 IMReportSummary 테이블](imreportsummary.md) <br/> |조직에서 보관하는 인스턴트 메시징 세션에 대한 전체 보고서를 제공합니다.  <br/> |
   
## <a name="tables-for-peer-to-peer-sessions"></a>피어 투 피어 세션 테이블

|**표**|**설명**|
|:-----|:-----|
|[SessionDetails 테이블](sessiondetails.md) <br/> |시작 및 종료 시간, 사용자 ID, 응답 코드 및 각 사용자에 대한 메시지 수를 포함하여 모든 피어 투 피어 세션에 대한 정보를 저장합니다.  <br/> |
|[비즈니스용 Skype 서버의 FileTransfers 테이블](filetransfers-0.md) <br/> |파일 이름 및 결과(수락, 거절 또는 취소)를 포함하여 파일 전송 세션에 대한 정보를 저장합니다.  <br/> |
|[Media 테이블](media.md) <br/> |피어 투 피어 세션에 포함된 여러 미디어 유형에 대한 정보를 저장합니다.  <br/> |
   
## <a name="table-for-voip-call-details"></a>VoIP 통화 세부 정보 테이블

|**표**|**설명**|
|:-----|:-----|
|[VoipDetails 테이블](voipdetails-0.md) <br/> |각 두 사용자 간 VoIP/PSTN 통화에 대해 VoIP 전화의 전화 ID, 사용된 게이트웨이 및 연결을 해제한 사용자 등 통화에 대한 정보를 저장합니다. 통화 시작/종료 시간 및 응답 코드에 대한 [SessionDetails](sessiondetails.md) 테이블을 참조합니다. <br/> |
   
> [!NOTE]
> 통화에서 한 사용자가 VoIP 사용자이거나 통화에 중재 서버가 포함된 경우 이 테이블에 레코드가 만들어집니다. PSTN(Public Switched Telephone Network) 전화가 사용되지 않는 VoIP/VoIP 통화에 대한 정보는 [SessionDetails](sessiondetails.md)테이블에 캡처됩니다. 
  
## <a name="table-for-e9-1-1-call-auditing"></a>E9-1-1 통화 감사 테이블

|**표**|**설명**|
|:-----|:-----|
|[비즈니스용 Skype 서버의 Locations 테이블](locations.md) <br/> |E9-1-1(Enhanced 9-1-1) 통화와 같은 각 긴급 통화에 대해서는 통화에 대한 위치 정보를 저장합니다. 통화 시작/종료 시간 및 응답 코드에 대한 [SessionDetails](sessiondetails.md) 테이블을 참조합니다. <br/> |
   
> [!NOTE]
> 이 테이블에는 E9-1-1 통화에 대한 위치 BLOB만 포함됩니다. 통화에 대한 다른 세부 정보는 SessionDetails 테이블을 참조하십시오. 
  
## <a name="tables-for-troubleshooting"></a>문제 해결 테이블

|**표**|**설명**|
|:-----|:-----|
|[비즈니스용 Skype 서버의 응용 프로그램 테이블](application.md) <br/> |라우팅 및 연결과 관련된 비즈니스용 Skype 서버 2015 내의 다양한 프로세스에 대한 정보를 저장합니다.  <br/> |
|[비즈니스용 Skype 서버의 CallType 테이블](calltype.md) <br/> |통화 유형(예: "오디오", "인스턴트 메시징", "오디오 및 비디오" 및 "응용 프로그램 공유")에 대한 정보를 저장합니다.  <br/> |
|[비즈니스용 Skype 서버의 ErrorCategory 테이블](errorcategory.md) <br/> |각 비즈니스용 Skype 서버 2015 진단 분류의 이름을 저장합니다.  <br/> |
|[비즈니스용 Skype 서버의 ErrorDef 테이블](errordef.md) <br/> |오류 유형 및 정의에 대한 정보를 저장합니다.  <br/> |
|[비즈니스용 Skype 서버의 ErrorReport 테이블](errorreport.md) <br/> |발생한 오류에 대한 정보를 저장합니다.  <br/> |
|[ProgressReport 테이블](progressreport.md) <br/> |비즈니스용 Skype 서버 2015 프로세스에 관련된 다양한 단계의 진행률 보고서에 대한 정보를 저장합니다.  <br/> |
   
다음 목록의 표는 비즈니스용 Skype 서버 2015에서 내부적으로 사용됩니다. 이러한 테이블의 세부 정보는 이 문서에서 설명하지 않습니다.
  
## <a name="tables-for-internal-use-by-lync-server"></a>Lync Server 내부용 테이블

|**표**|**설명**|
|:-----|:-----|
|**DbConfigDateTime** <br/> |내부 용도로만 사용됩니다.  <br/> |
|**DbConfigInt** <br/> |내부 용도로만 사용됩니다.  <br/> |
|**DbErrorMessage** <br/> |내부 용도로만 사용됩니다.  <br/> |
|**FrontEnd 테이블** <br/> |내부 용도로만 사용됩니다.  <br/> |
|**MSMQProcessing 테이블** <br/> |내부 용도로만 사용됩니다.  <br/> |
|**SummaryTableConfiguration** <br/> |내부 용도로만 사용됩니다.  <br/> |
|**Syndicators 테이블** <br/> |내부 용도로만 사용됩니다.  <br/> |
|**SyndicatorsTenantMap 테이블** <br/> |내부 용도로만 사용됩니다.  <br/> |
|**Task 테이블** <br/> |내부 용도로만 사용됩니다.  <br/> |
|**UserStatistics** <br/> |내부 용도로만 사용됩니다.  <br/> |
|**UsageSummary_UQ** <br/> |내부 용도로만 사용됩니다.  <br/> |
|**UsageSummary** <br/> |내부 용도로만 사용됩니다.  <br/> |
|**DaylightSavingYears** <br/> |내부 용도로만 사용됩니다.  <br/> |
|**TimeZoneConfiguration** <br/> |내부 용도로만 사용됩니다.  <br/> |
|**TimeZones** <br/> |내부 용도로만 사용됩니다.  <br/> |
|**FailureSummary_UQ** <br/> |내부 용도로만 사용됩니다.  <br/> |
|**FailureSummary** <br/> |내부 용도로만 사용됩니다.  <br/> |
|**ServerSummary** <br/> |내부 용도로만 사용됩니다.  <br/> |
|**MsDiagMetaData** <br/> |내부 용도로만 사용됩니다.  <br/> |
   

