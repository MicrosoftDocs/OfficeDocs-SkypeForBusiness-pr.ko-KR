---
title: ProgressReport 테이블
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 38e5f060-5e9b-4185-87b2-7ef61c4bb75f
description: 진행률 보고서는 호출 또는 세션이 완료 된 후 클라이언트에서 데이터베이스에 업로드 한 데이터를 기반으로 합니다. 진행률 보고서는 비즈니스용 Skype Server 2015에서 진단 목적으로 사용할 수 있는 통화 및 세션에 대해서만 기록 됩니다.
ms.openlocfilehash: a6cd89d7ba7f8cc03b25dc9310bdb408c85b50cb
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814976"
---
# <a name="progressreport-table"></a>ProgressReport 테이블
 
진행률 보고서는 호출 또는 세션이 완료 된 후 클라이언트에서 데이터베이스에 업로드 한 데이터를 기반으로 합니다. 진행률 보고서는 비즈니스용 Skype Server 2015에서 진단 목적으로 사용할 수 있는 통화 및 세션에 대해서만 기록 됩니다.
  
ErrorTime, ErrorReportSeq 및 ProgressReportSeq 필드는 반드시 오류를 의미 하지는 않으며 호출 상태를 나타내는 메시지에만 해당 됩니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부적인**|
|:-----|:-----|:-----|:-----|
|**ErrorTime** <br/> |dmtf  <br/> |기본, 외래  <br/> |이 진행률 보고서가 포함 된 진행률 오류 보고서의 날짜 및 시간입니다. 자세한 내용은 [비즈니스용 Skype 서버 2015에서 ErrorReport 테이블](errorreport.md) 을 참조 하세요. <br/> |
|**ErrorId** <br/> |int  <br/> |기본, 외래  <br/> |상태 보고서를 고유 하 게 식별 하는 ProgressReportSeq ErrorTime과 함께 사용 되는 ID 번호입니다. 자세한 내용은 [비즈니스용 Skype 서버 2015에서 ErrorReport 테이블](errorreport.md) 을 참조 하세요. <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |기본, 외래  <br/> |오류 보고서를 식별 하는 ID 번호입니다. ErrorReporSeq는 오류 보고서를 고유 하 게 식별 하는 ErrorTime과 함께 사용 됩니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 ErrorReport 표](errorreport.md) 를 참조 하세요. <br/> 이 필드는 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**ProgressReportSeq** <br/> |int  <br/> |주요한  <br/> |진행률 보고서를 식별 하는 ID 번호입니다. 진행률 보고서를 고유 하 게 식별 하는 ErrorTime 및 Errortime Seq와 함께 사용 됩니다.  <br/> |
|**MsDiagId** <br/> |int  <br/> ||진행률 보고서의 진단 ID입니다.  <br/> 이 필드는 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**SourceId** <br/> |int  <br/> |외부  <br/> |오류 보고서를 보낸 서버 (보고서가 서버 구성 요소에서 전송 된 경우) 자세한 내용은 [서버 테이블](servers.md) 을 참조 하세요. 이 필드는 Microsoft Lync Server 2013에서 도입 되었습니다. <br/> |
|**ApplicationId** <br/> |int  <br/> ||보고서에 대 한 Lync Server 프로세스입니다. 자세한 내용은 응용 프로그램 테이블을 참조 하세요.  <br/> |
|**도** <br/> |이미지  <br/> ||공간 절약을 위해 이진 형식으로 저장 된 진행률 보고서 세부 정보입니다. 이 구문을 사용 하 여이 데이터를 텍스트 형식으로 변환할 수 있습니다.  <br/> cast (cast (varbinary (max)로 Detail)를 varchar (max)로 캐스트)  <br/> |
|**TelemetryId** <br/> |uniqueIdentifier  <br/> ||컨퍼런스와 관련 된 다양 한 구성 요소에 대 한 조인 시간 정보를 연관 시키는 고유 식별자입니다.  <br/> 이 필드는 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**SessionSetupTime 시간** <br/> |int  <br/> ||특정 구성 요소가 컨퍼런스에 참가 하는 데 걸리는 시간 (밀리초 단위)입니다.  <br/> 이 필드는 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
   

