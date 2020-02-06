---
title: tblRoleType
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
ms.assetid: 1eac3a54-656a-40ac-b771-edfc64d6e34b
description: tblRoleType는 역할 유형 및 연결 된 사용 권한 집합을 포함 하는 정적 조회 테이블입니다.
ms.openlocfilehash: 888628c1aca01e90694ed946569a81b1b7394b95
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812906"
---
# <a name="tblroletype"></a>tblRoleType
 
tblRoleType는 역할 유형 및 연결 된 사용 권한 집합을 포함 하는 정적 조회 테이블입니다.
  
**열**

|**열**|**유형**|**설명**|
|:-----|:-----|:-----|
|rtypeID  <br/> |int, null 아님  <br/> |역할 유형 ID입니다.  <br/> |
|rtypeDesc  <br/> |nvarchar (256), null 아님  <br/> | 역할 유형 설명입니다. 사용할 수 있는 역할은 네 가지가 있습니다. <br/>  회원: 채팅방 구성원 <br/>  관리자: 채팅방 관리자 <br/>  않지만: auditorium 채팅방의 발표자 <br/>  작성자: 채팅방을 만들 수 있습니다. <br/> |
|rtypeAllowedPermSet  <br/> |bigint, null이 아님  <br/> | 역할에 대 한 사용 권한 집합입니다. 사용 되는 비트는 다음과 같습니다. <br/>  2: 역할이 노드를 관리할 수 있는 경우 True입니다. <br/>  4: 역할이 자식 노드를 만들 수 있는 경우 True입니다. <br/>  7: 역할이 채팅방에 참가할 수 있으면 True이 고, 그렇지 않은 경우에는 범주에 있는 채팅방을 어린이에 게 보세요. <br/>  8: 역할이 채팅방에서 채팅을 할 수 있으면 True이 고, 그렇지 않은 경우에는 범주의 채팅방을 어린이에 게 보세요. <br/>  10: 채팅방에 참가 하지 않은 경우에도 역할이 채팅 기록을 읽을 수 있는 경우 True입니다. <br/>  11: 역할이 채팅방을 볼 수 있으면 True입니다. (범위 및 표시 유형 등의 요인에 따라 구체화 됩니다.) <br/>  12: 역할이 auditorium 채팅방에서 채팅을 할 수 있는 경우 True입니다. <br/>  13: 역할이 노드를 볼 때 표시 규칙을 무시할 수 있는 경우 True입니다. <br/> |
   
**키**

|**열**|**설명**|
|:-----|:-----|
|rtypeID  <br/> |기본 키입니다.  <br/> |
   

