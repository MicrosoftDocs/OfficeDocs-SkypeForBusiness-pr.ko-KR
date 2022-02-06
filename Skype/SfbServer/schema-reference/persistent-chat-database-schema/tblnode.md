---
title: tblNode
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: a31d2961-aa83-4286-a12e-15d279c95f19
description: tblNode에는 제어판 및 관리 cmdlet에서 관리되는 개체 트리(범주 또는 채팅방 노드 포함)가 포함되어 있습니다.
---

# <a name="tblnode"></a>tblNode
 
tblNode에는 제어판 및 관리 cmdlet에서 관리되는 개체 트리(범주 또는 채팅방 노드 포함)가 포함되어 있습니다.
  
**열**

|**열**|**유형**|**설명**|
|:-----|:-----|:-----|
|nodeID  <br/> |int, null이 아님  <br/> |노드 ID(고유 번호)입니다.  <br/> |
|nodeGuid  <br/> |GUID, null이 아님  <br/> |노드 GUID입니다.  <br/> |
|parentID  <br/> |int  <br/> |부모의 노드 ID입니다. 루트 노드(ID 1)는 그 자신을 부모로 포함합니다.  <br/> |
|nodeType  <br/> |bit, null이 아님  <br/> |노드가 범주인 경우 True입니다.  <br/> 노드가 대화방인 경우 False입니다.  <br/> |
|nodeName  <br/> |nvarchar(256), null이 아님  <br/> |노드 이름입니다.  <br/> |
|nodeDesc  <br/> |nvarchar(256), null이 아님  <br/> |노드 설명입니다.  <br/> |
|invite  <br/> |bit  <br/> | 범주인 경우: <br/>  초대가 설정된 경우 True입니다. <br/>  초대가 해제된 경우 False입니다. <br/>  대화방인 경우: <br/>  초대가 해제된 경우 False입니다(부모 범주 재정의). <br/>  부모 범주에서 초대 설정이 상속된 경우 Null입니다. <br/> |
|logged  <br/> |bit  <br/> | 범주인 경우: <br/>  대화 기록이 설정된 경우 True입니다. <br/>  대화 기록이 해제된 경우 Fasle입니다. <br/>  대화방인 경우: <br/>  Null. <br/> |
|filePost  <br/> |bit  <br/> | 범주인 경우: <br/>  파일 업로드가 허용된 경우 True입니다. <br/>  파일 업로드가 허용되지 않은 경우 False입니다. <br/>  대화방인 경우: <br/>  Null. <br/> |
|비활성화됨  <br/> |bit, null이 아님  <br/> |대화방이 비활성화된 경우 True입니다. 대화방에만 적용됩니다. 범주의 경우 False입니다.  <br/> |
|동작  <br/> |smallint, null이 아님  <br/> | 동작(EnumValue 테이블에서 조회됨): <br/>  4: 일반(일반 대화방) <br/>  5: 강당(강당 대화방, 발표자만 기여할 수 있음) <br/>  대화방에만 적용됩니다. <br/> |
|visibility  <br/> |smallint, null이 아님  <br/> | 표시 유형(EnumValue 테이블에서 조회됨): <br/>  2: 개인 <br/>  3: 범위 지정 <br/>  6: 열려 있음 <br/>  대화방에만 적용됩니다. <br/> |
|siopID  <br/> |GUID  <br/> |추가 기능이 이 대화방과 연결된 경우 추가 기능 GUID입니다. (범주에는 추가 기능이 없습니다.)  <br/> 추가 기능 정보는 SiopWhiteList 테이블에서 조회됩니다.  <br/> |
|nodeAddedBy  <br/> |int, null이 아님  <br/> |이 노드를 만든 사용자의 ID입니다.  <br/> |
|nodeAddedOn  <br/> |bigint, null이 아님  <br/> |노드 작성의 타임스탬프입니다.  <br/> |
|nodeUpdatedBy  <br/> |int, null이 아님  <br/> |이 노드를 마지막으로 업데이트한 사용자의 ID입니다.  <br/> |
|nodeUpdatedOn  <br/> |bigint, null이 아님  <br/> |이 노드를 마지막으로 업데이트한 타임스탬프입니다.  <br/> |
|purgedOn  <br/> |datetime  <br/> |이 노드에 영향을 준 최근의 삭제 작업(ScopedPrincipal 테이블에서 범위 및 PrincipalRole 테이블에서 역할 제거)의 시간입니다. 이 서비스는 채팅 서비스의 내부 캐시 업데이트 메커니즘에 사용됩니다.  <br/> |
   
**키**

|**열**|**설명**|
|:-----|:-----|
|nodeID  <br/> |기본 키입니다.  <br/> |
|동작  <br/> |tblEnumValue.valueID 테이블에서 조회 기능이 있는 외래 키입니다.  <br/> |
|visibility  <br/> |tblEnumValue.valueID 테이블에서 조회 기능이 있는 외래 키입니다.  <br/> |
|parentID  <br/> |tblNode.nodeID 테이블에서 조회 기능이 있는 외래 키입니다.  <br/> |
|siopID  <br/> |tblSiopWhiteList.siopId 테이블에서 조회 기능이 있는 외래 키입니다.  <br/> |
   

