---
title: ProgressReport 보기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b49f3fc7-0e2f-498f-8505-aaaf54e435f9
description: ProgressReport 보기는 완료 된 세션에 대 한 정보를 저장 합니다. 진행률 보고서는 Lync Server 2013이 진단 목적에 유용할 수 있는 통화 및 세션에 대해서만 기록 됩니다. 이 보기는 Microsoft Lync Server 2013에서 도입 되었습니다.
ms.openlocfilehash: c07b9db8ebd9f898ab9d8feb5b07c4723209522c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814986"
---
# <a name="progressreport-view"></a>ProgressReport 보기
 
ProgressReport 보기는 완료 된 세션에 대 한 정보를 저장 합니다. 진행률 보고서는 Lync Server 2013이 진단 목적에 유용할 수 있는 통화 및 세션에 대해서만 기록 됩니다. 이 보기는 Microsoft Lync Server 2013에서 도입 되었습니다.
  
> [!NOTE]
> ErrorTime, ErrorReportSeq 및 ProgressReportSeq 필드는 반드시 오류를 의미 하지는 않으며 호출 상태를 나타내는 메시지에만 해당 됩니다. 
  
|**열**|**데이터 형식**|**세부적인**|
|:-----|:-----|:-----|
|**ErrorTime** <br/> |dmtf  <br/> |오류가 발생 한 시간입니다. 오류를 고유 하 게 식별 하는 ErrorReportSeq와 함께 사용 합니다.  <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |오류를 식별 하는 ID 번호입니다. 오류를 고유 하 게 식별 하는 ErrorTime과 함께 사용 됩니다.  <br/> |
|**ProgressReportSeq** <br/> |int  <br/> |진행률 보고서를 식별 하는 ID입니다. 같은 오류 보고서의 진행률 보고서를 구분 하는 데 사용 됩니다.  <br/> |
|**MsDiagId** <br/> |int  <br/> |오류 보고서의 진단 ID입니다.  <br/> |
|**Source** <br/> |nvarchar (256)  <br/> |오류를 발생 시킨 서버의 이름입니다 (보고서가 서버 구성 요소에서 전송 된 경우).  <br/> |
|**응용 프로그램** <br/> |nvarchar (256)  <br/> |오류를 발생 시킨 응용 프로그램의 이름입니다 (보고서가 서버 구성 요소에서 전송 된 경우).  <br/> |
|**TelemetryId** <br/> |uniqueidentifier  <br/> |고유한 식별자는 회의에 관련 된 다양 한 구성 요소에 대 한 조인 시간 정보를 연결 합니다.  <br/> |
|**SessionSetupTime 시간** <br/> |int  <br/> |특정 구성 요소가 컨퍼런스에 참가 하는 데 필요한 시간 (밀리초 단위)입니다.  <br/> |
|**MsDiagHeader** <br/> |varchar (max)  <br/> |추가 오류 정보.  <br/> |
   

