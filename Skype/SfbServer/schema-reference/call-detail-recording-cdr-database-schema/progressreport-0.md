---
title: ProgressReport 보기
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b49f3fc7-0e2f-498f-8505-aaaf54e435f9
description: ProgressReport 보기에는 완료된 세션에 대한 정보가 저장됩니다. 진행률 보고서는 Lync Server 2013에서 진단 목적으로 유용할 수 있는 통화 및 세션에만 기록됩니다. 이 보기는 Microsoft Lync Server 2013에서 도입했습니다.
ms.openlocfilehash: 8e21b83b1ca6c4856ba31a579e4a7999ba8b31a6
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58623540"
---
# <a name="progressreport-view"></a>ProgressReport 보기
 
ProgressReport 보기에는 완료된 세션에 대한 정보가 저장됩니다. 진행률 보고서는 Lync Server 2013에서 진단 목적으로 유용할 수 있는 통화 및 세션에만 기록됩니다. 이 보기는 Microsoft Lync Server 2013에서 도입했습니다.
  
> [!NOTE]
> ErrorTime, ErrorReportSeq 및 ProgressReportSeq 필드는 반드시 오류를 참조하는 것이 아니라 통화 또는 메시지의 상태를 나타내는 메시지에 대한 참조입니다. 
  
|**열**|**데이터 형식**|**세부 정보**|
|:-----|:-----|:-----|
|**ErrorTime** <br/> |datetime  <br/> |오류가 발생한 시간입니다. ErrorReportSeq와 함께 오류를 고유하게 식별하기 위해 사용됩니다.  <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |오류를 식별하기 위한 ID 번호입니다. ErrorTime과 함께 오류를 고유하게 식별하기 위해 사용됩니다.  <br/> |
|**ProgressReportSeq** <br/> |int  <br/> |진행률 보고서를 식별하는 ID입니다. 동일한 오류 보고서의 진행률 보고서를 구분하는 데 사용됩니다.  <br/> |
|**MsDiagId** <br/> |int  <br/> |오류 보고서의 진단 ID입니다.  <br/> |
|**원본** <br/> |nvarchar(256)  <br/> |오류를 유발한 서버 이름입니다(보고서가 서버 구성 요소에서 전송된 경우).  <br/> |
|**응용 프로그램** <br/> |nvarchar(256)  <br/> |오류를 유발한 응용 프로그램 이름입니다(보고서가 서버 구성 요소에서 전송된 경우).  <br/> |
|**TelemetryId** <br/> |uniqueidentifier  <br/> |회의에 포함된 서로 다른 구성 요소의 참가 시간 정보와 연결된 고유 ID입니다.  <br/> |
|**SessionSetupTime** <br/> |int  <br/> |회의에 참가하는 특정 구성 요소에 필요한 시간(밀리초)입니다.  <br/> |
|**MsDiagHeader** <br/> |varchar(max)  <br/> |추가 오류 정보입니다.  <br/> |
   

