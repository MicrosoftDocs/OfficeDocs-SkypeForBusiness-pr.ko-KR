---
title: 영구 채팅 서버 준수 테이블의 비즈니스용 Skype 서버
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 8563446e-90cc-47cc-8a8e-4883decfe195
description: 영구 채팅 준수 데이터베이스 schema는 다음 테이블로 구성됩니다.
---

# <a name="list-of-persistent-chat-server-compliance-tables-in-skype-for-business-server"></a>영구 채팅 서버 준수 테이블의 비즈니스용 Skype 서버
 
영구 채팅 준수 데이터베이스 schema는 다음 테이블로 구성됩니다.
  
## <a name="list-of-persistent-chat-server-compliance-tables"></a>영구 채팅 서버 준수 테이블 목록

|**표**|**설명**|
|:-----|:-----|
|[tblComplianceData](tblcompliancedata.md) <br/> |구성된 어댑터에서 아직 처리되지 않은 준수 이벤트를 포함합니다.  <br/> 이 테이블에는 채팅 메시지 및 파일 다운로드와 같은 영구 채팅 관련 이벤트가 포함되어 있습니다. 참가자 이벤트는 tblComplianceParticipant 테이블에서 추적됩니다.  <br/> 이 테이블의 이벤트를 처리한 서버는 tblComplianceFanout 테이블에 나열됩니다.  <br/> |
|[tblComplianceFanout](tblcompliancefanout.md) <br/> |준수 이벤트를 처리한 서버를 포함합니다. 이 테이블은 tblComplianceData 테이블과 밀접하게 결합되어 있습니다.  <br/> |
|[tblComplianceParticipant](tblcomplianceparticipant.md) <br/> |채팅 서비스 및 서버별 현재 참가자를 포함합니다. 영구 채팅 서비스에서 받은 참가 및 파트 준수 이벤트를 기반으로 유지 관리됩니다.  <br/> |
|[tblComplianceState](tblcompliancestate.md) <br/> |풀 전반의 준수 상태 정보를 포함합니다.  <br/> |
   

