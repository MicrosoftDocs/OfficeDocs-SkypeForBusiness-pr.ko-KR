---
title: 비즈니스용 Skype 서버의 영구 채팅 서버 준수 테이블 목록
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8563446e-90cc-47cc-8a8e-4883decfe195
description: 영구 채팅 준수 데이터베이스 스키마는 다음 테이블로 구성 됩니다.
ms.openlocfilehash: 92c87ee2783eb8ec064e017b5c3c5b0f6cb893a5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196662"
---
# <a name="list-of-persistent-chat-server-compliance-tables-in-skype-for-business-server"></a>비즈니스용 Skype 서버의 영구 채팅 서버 준수 테이블 목록
 
영구 채팅 준수 데이터베이스 스키마는 다음 테이블로 구성 됩니다.
  
## <a name="list-of-persistent-chat-server-compliance-tables"></a>영구 채팅 서버 준수 테이블 목록

|**테이블로**|**설명**|
|:-----|:-----|
|[tblComplianceData](tblcompliancedata.md) <br/> |구성 된 어댑터에서 아직 처리 하지 않은 준수 이벤트를 포함 합니다.  <br/> 이 표에는 채팅 메시지 및 파일 다운로드와 같은 지속적인 채팅 관련 이벤트가 포함 되어 있습니다. (참가자 이벤트는 tblComplianceParticipant 테이블에서 추적 됩니다.)  <br/> (이 테이블의 이벤트를 처리 하는 서버는 tblComplianceFanout 테이블에 나열 되어 있습니다.)  <br/> |
|[tblComplianceFanout](tblcompliancefanout.md) <br/> |규정 준수 이벤트를 처리 한 서버를 포함 합니다. 이 표는 tblComplianceData 테이블과 밀접 하 게 결합 되어 있습니다.  <br/> |
|[tblComplianceParticipant](tblcomplianceparticipant.md) <br/> |채팅 서비스 및 서버 별로 현재 참가자가 포함 되어 있습니다. 영구 채팅 서비스에서 받은 참가 및 파트 규정 준수 이벤트에 따라 유지 됩니다.  <br/> |
|[tblComplianceState](tblcompliancestate.md) <br/> |풀 전체의 준수 상태 정보를 포함 합니다.  <br/> |
   

