---
title: QoE 보기 세부 정보
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
ms.assetid: 6a658318-a317-4546-a44c-a9c473d8e86a
description: 보기에는 QoE 데이터베이스에서 데이터를 반환하는 가장 일반적인 시나리오가 SQL 있습니다. 데이터베이스 테이블에 직접 액세스하는 대신 사용자 지정 보고서를 작성하는 데 사용되는 보기를 사용하는 것이 좋습니다. 이는 보기가 이후 릴리스와의 호환성을 유지할 가능성이 더 높기 때문에입니다.
ms.openlocfilehash: 7bed72ae4fe5a9468d6ac2b18148f62fe9aa0196
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58578592"
---
# <a name="qoe-view-details"></a>QoE 보기 세부 정보
 
보기에는 QoE 데이터베이스에서 데이터를 반환하는 가장 일반적인 시나리오가 SQL 있습니다. 데이터베이스 테이블에 직접 액세스하는 대신 사용자 지정 보고서를 작성하는 데 사용되는 보기를 사용하는 것이 좋습니다. 이는 보기가 이후 릴리스와의 호환성을 유지할 가능성이 더 높기 때문에입니다.
  
|**뷰 이름/View Name**|**설명**|
|:-----|:-----|
|[AudioStreamDetail 보기](audiostreamdetail.md) <br/> |데이터베이스의 각 오디오 스트림에 대한 정보를 저장합니다.  <br/> |
|[MediaLine 보기](medialine.md) <br/> |데이터베이스에 각 미디어 라인에 대한 정보를 저장합니다. 하나의 오디오 세션은 일반적으로 오디오 미디어 회선 하나를 포함합니다. 하나의 A/V(오디오 및 비디오) 세션은 보통 오디오 미디어 회선과 비디오 미디어 회선을 하나씩 포함하지만, 회의 장치나 갤러리 보기를 사용하는 경우에는 세션이 비디오 미디어 회선 두 개를 포함할 수 있습니다.  <br/> |
|[NetworkConfigurationSettings 보기](networkconfigurationsettings.md) <br/> |네트워크 구성에 대한 정보를 저장합니다.  <br/> |
|[세션 보기](session-0.md) <br/> |데이터베이스에 레코드가 있는 세션에 대한 정보를 저장합니다.  <br/> |
|[UserAgent 보기](useragent-0.md) <br/> |데이터베이스에 레코드가 있는 세션에 참여한 사용자 에이전트에 대한 정보를 저장합니다.  <br/> |
|[VideoStreamDetail 보기](videostreamdetail.md) <br/> |데이터베이스의 각 비디오 스트림에 대한 정보를 저장합니다.  <br/> |
   

