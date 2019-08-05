---
title: tblNode
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a31d2961-aa83-4286-a12e-15d279c95f19
description: tblNode는 제어판 및 관리 cmdlet에서 관리 되는 개체 트리 (범주 또는 채팅방 노드 포함)를 포함 합니다.
ms.openlocfilehash: fedb7f88cd9b5a634fe9a6b34f746e61e6ee9be7
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196622"
---
# <a name="tblnode"></a>tblNode
 
tblNode는 제어판 및 관리 cmdlet에서 관리 되는 개체 트리 (범주 또는 채팅방 노드 포함)를 포함 합니다.
  
**열**

|**열**|**유형**|**설명**|
|:-----|:-----|:-----|
|nodeID  <br/> |int, null 아님  <br/> |노드 ID (고유 번호).  <br/> |
|nodeGuid  <br/> |GUID (null 아님)  <br/> |노드 GUID입니다.  <br/> |
|parentID  <br/> |int  <br/> |부모의 노드 ID입니다. 루트 노드 (ID 1)는 자신을 부모로도 포함 합니다.  <br/> |
|종류  <br/> |bit, null이 아님  <br/> |노드가 범주 이면 True입니다.  <br/> 노드가 채팅방 이면 False입니다.  <br/> |
|nodeName  <br/> |nvarchar (256), null 아님  <br/> |노드 이름입니다.  <br/> |
|nodeDesc  <br/> |nvarchar (256), null 아님  <br/> |노드 설명입니다.  <br/> |
|있도록  <br/> |다소  <br/> | 범주: <br/>  초대가 설정 된 경우 True입니다. <br/>  초대가 해제 된 경우 False입니다. <br/>  회의실: <br/>  초대가 해제 된 경우 False (상위 범주 무시) <br/>  초대 설정이 상위 범주에서 상속 되는 경우 Null입니다. <br/> |
|사람이  <br/> |다소  <br/> | 범주: <br/>  채팅 내역이 켜져 있는 경우 True입니다. <br/>  대화 내용이 설정 되어 있지 않으면 False입니다. <br/>  회의실: <br/>  L. <br/> |
|filePost  <br/> |다소  <br/> | 범주: <br/>  파일 업로드가 허용 되는 경우 True입니다. <br/>  False 이면 파일 업로드를 허용 하지 않습니다. <br/>  회의실: <br/>  L. <br/> |
|비활성화  <br/> |bit, null이 아님  <br/> |채팅방을 사용할 수 없는 경우 True입니다. 채팅방에만 적용 됩니다. (범주에 대 한 False)  <br/> |
|결과가  <br/> |smallint, null이 아님  <br/> | 동작 (EnumValue 테이블에서 조회): <br/>  4: 보통 (일반 채팅방). <br/>  5: Auditorium (Auditorium 채팅방은 발표자만 참가할 수 있습니다.) <br/>  채팅방에만 적용 됩니다. <br/> |
|시도가  <br/> |smallint, null이 아님  <br/> | 가시성 (EnumValue 표를 통해 조회): <br/>  2: 비공개 <br/>  3: 범위 지정 <br/>  6: 열림 <br/>  채팅방에만 적용 됩니다. <br/> |
|siopID  <br/> |SHAP  <br/> |추가 기능 GUID가이 채팅방과 연결 되어 있는 경우이를 사용 합니다. (범주에는 추가 기능이 없습니다.)  <br/> 추가 기능 정보는 SiopWhiteList 테이블에서 조회 됩니다.  <br/> |
|nodeAddedBy  <br/> |int, null 아님  <br/> |이 노드를 만든 사용자의 ID입니다.  <br/> |
|nodeAddedOn  <br/> |bigint, null이 아님  <br/> |노드 생성에 대 한 타임 스탬프입니다.  <br/> |
|nodeUpdatedBy  <br/> |int, null 아님  <br/> |이 노드의 최신 업데이트를 수행한 사용자의 ID입니다.  <br/> |
|nodeUpdatedOn  <br/> |bigint, null이 아님  <br/> |이 노드의 최신 업데이트에 대 한 타임 스탬프입니다.  <br/> |
|purgedOn  <br/> |dmtf  <br/> |이 노드에 영향을 주는 최신 지우기 작업의 시간 (tblScopedPrincipal table의 범위 제거 및 tblPrincipalRole 테이블에서 가져온 역할) 이는 채팅 서비스의 내부 캐시 업데이트 메커니즘에 사용 됩니다.  <br/> |
   
**핵심**

|**열**|**설명**|
|:-----|:-----|
|nodeID  <br/> |기본 키입니다.  <br/> |
|결과가  <br/> |TblEnumValue Eid 테이블의 조회가 포함 되어 있는 외래 키입니다.  <br/> |
|시도가  <br/> |TblEnumValue Eid 테이블의 조회가 포함 되어 있는 외래 키입니다.  <br/> |
|parentID  <br/> |NodeID 테이블에 조회를 포함 하는 외래 키입니다.  <br/> |
|siopID  <br/> |TblSiopWhiteList의 조회를 포함 하는 외래 키입니다.  <br/> |
   

