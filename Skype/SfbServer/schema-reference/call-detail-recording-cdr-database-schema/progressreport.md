---
title: ProgressReport 테이블
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 38e5f060-5e9b-4185-87b2-7ef61c4bb75f
description: 진행률 보고서는 통화 또는 세션이 완료된 후에 클라이언트가 데이터베이스에 업로드한 데이터를 기반으로 작성됩니다. 진행률 보고서는 비즈니스용 Skype 서버 2015에서 진단 목적으로 유용할 수 있는 통화 및 세션에만 기록됩니다.
ms.openlocfilehash: 4169ab029c0ce491b77b39735e309e102ac6e356
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823178"
---
# <a name="progressreport-table"></a>ProgressReport 테이블
 
진행률 보고서는 통화 또는 세션이 완료된 후에 클라이언트가 데이터베이스에 업로드한 데이터를 기반으로 작성됩니다. 진행률 보고서는 비즈니스용 Skype 서버 2015에서 진단 목적으로 유용할 수 있는 통화 및 세션에만 기록됩니다.
  
ErrorTime, ErrorReportSeq 및 ProgressReportSeq 필드는 반드시 오류를 참조하는 것이 아니라 통화 또는 메시지의 상태를 나타내는 메시지에 대한 참조입니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부 정보**|
|:-----|:-----|:-----|:-----|
|**ErrorTime** <br/> |datetime  <br/> |Primary, Foreign  <br/> |이 진행률 보고서를 포함하는 진행 상태 오류 보고서의 날짜 및 시간입니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 ErrorReport](errorreport.md) 테이블을 참조하세요. <br/> |
|**ErrorId** <br/> |int  <br/> |Primary, Foreign  <br/> |ErrorTime, ProgressReportSeq와 함께 진행률 보고서를 고유하게 식별하기 위해 사용된 ID 번호입니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 ErrorReport](errorreport.md) 테이블을 참조하세요. <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |Primary, Foreign  <br/> |오류 보고서를 식별하는 ID 번호입니다. ErrorReporSeq는 ErrorTime과 함께 오류 보고서를 고유하게 식별하는 데 사용됩니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 ErrorReport](errorreport.md) 테이블을 참조하세요. <br/> 이 필드는 Microsoft Lync Server 2013에서 도입했습니다.  <br/> |
|**ProgressReportSeq** <br/> |int  <br/> |Primary  <br/> |진행률 보고서를 식별하기 위한 ID 번호입니다. ErrorTime 및 ErrorReportSeq와 함께 진행률 보고서를 고유하게 식별하기 위해 사용됩니다.  <br/> |
|**MsDiagId** <br/> |int  <br/> ||진행률 보고서의 진단 ID입니다.  <br/> 이 필드는 Microsoft Lync Server 2013에서 도입했습니다.  <br/> |
|**SourceId** <br/> |int  <br/> |외계인  <br/> |오류 보고서를 보낸 서버입니다(보고서가 서버 구성 요소에서 전송된 경우). 자세한 내용은 [Servers 테이블을](servers.md) 참조하세요. 이 필드는 Microsoft Lync Server 2013에서 도입했습니다. <br/> |
|**ApplicationId** <br/> |int  <br/> ||보고서의 대상 Lync Server 프로세스입니다. 자세한 내용은 Application 테이블을 참조하십시오.  <br/> |
|**자세한 정보** <br/> |이미지  <br/> ||공간 절약을 위해 이진 형식으로 저장된 진행률 보고서 세부 정보입니다. 다음 구문을 사용하여 이 데이터를 텍스트 형식으로 변환할 수 있습니다.  <br/> cast(cast(Detail as varbinary(max)) as varchar(max))  <br/> |
|**TelemetryId** <br/> |uniqueIdentifier  <br/> ||전화 회의에 참가하는 각 구성 요소의 참가 시간 정보에 대해 상관 관계를 지정하는 고유 식별자입니다.  <br/> 이 필드는 Microsoft Lync Server 2013에서 도입했습니다.  <br/> |
|**SessionSetupTime** <br/> |int  <br/> ||특정 구성 요소가 전화 회의에 참가하는 시간(밀리초)입니다.  <br/> 이 필드는 Microsoft Lync Server 2013에서 도입했습니다.  <br/> |
   

