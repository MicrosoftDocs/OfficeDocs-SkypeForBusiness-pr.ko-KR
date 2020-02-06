---
title: 비즈니스용 Skype 서버 2015의 Mcus 테이블
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
ms.assetid: 271b7963-8fd8-4d92-a701-1a62aaf895ee
description: Mcus 테이블은 지원 테이블입니다. 각 레코드는 하나의 회의 서비스에 대 한 정보를 저장 합니다. 여기에는 IM 회의 서비스 및 전화 통신 회의 서비스 (프런트 엔드 서버에서 프로세스로 실행 됨)와 웹 회의 서비스 및 A/V 회의 서비스가 포함 될 수 있습니다.
ms.openlocfilehash: 1e5141ee2a103e540d3ac50e99de0036f31262d7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815066"
---
# <a name="mcus-table-in-skype-for-business-server-2015"></a>비즈니스용 Skype 서버 2015의 Mcus 테이블
 
Mcus 테이블은 지원 테이블입니다. 각 레코드는 하나의 회의 서비스에 대 한 정보를 저장 합니다. 여기에는 IM 회의 서비스 및 전화 통신 회의 서비스 (프런트 엔드 서버에서 프로세스로 실행 됨)와 웹 회의 서비스 및 A/V 회의 서비스가 포함 될 수 있습니다. 
  
|**열**|**데이터 형식**|**키/인덱스**|**세부적인**|
|:-----|:-----|:-----|:-----|
|**McuId** <br/> |int  <br/> |주요한  <br/> |이 회의 서버를 식별 하는 고유 번호입니다.  <br/> |
|**McuUri** <br/> |nvarchar (450)  <br/> | <br/> | <br/> |
|**M가공선 Ypeid** <br/> |inyint  <br/> | 외부 <br/> |컨퍼런스: 채팅 (Im의 경우) 또는 컨퍼런스: 오디오-비디오 등의 회의 서버 유형입니다. 자세한 내용은 [UriTypes 테이블](uritypes.md) 을 참조 하세요. <br/> |
   

