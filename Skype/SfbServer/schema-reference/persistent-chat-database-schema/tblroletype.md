---
title: tblRoleType
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
localization_priority: Normal
ms.assetid: 1eac3a54-656a-40ac-b771-edfc64d6e34b
description: tblRoleType은 역할 유형 및 연관된 권한 집합이 있는 정적 조회 테이블입니다.
ms.openlocfilehash: 2b03473b6f89e0dd2f572e2462b607bc72a2a2eb5f83aa18d2d779f9f66ee220
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54318681"
---
# <a name="tblroletype"></a>tblRoleType
 
tblRoleType은 역할 유형 및 연관된 권한 집합이 있는 정적 조회 테이블입니다.
  
**열**

|**열**|**유형**|**설명**|
|:-----|:-----|:-----|
|rtypeID  <br/> |int, null이 아님  <br/> |역할 유형 ID입니다.  <br/> |
|rtypeDesc  <br/> |nvarchar(256), null이 아님  <br/> | 역할 유형 설명입니다. 다음 네 가지 역할을 사용할 수 있습니다. <br/>  구성원: 대화방 구성원 <br/>  관리자: 대화방 관리자 <br/>  음성: 강당 대화방의 발표자 <br/>  작성자: 채팅방을 만들 수 있음 <br/> |
|rtypeAllowedPermSet  <br/> |bigint, null이 아님  <br/> | 역할에 대해 설정된 권한입니다. 사용되는 비트는 다음과 같습니다. <br/>  2: 역할이 노드를 관리할 수 있는 경우 True입니다. <br/>  4: 역할이 자식 노드를 만들 수 있는 경우 True입니다. <br/>  7: 역할이 대화방(또는 특정 범주의 자식 대화방)에 참가할 수 있는 경우 True입니다. <br/>  8: 역할이 대화방(또는 특정 범주의 자식 대화방)에서 채팅할 수 있는 경우 True입니다. <br/>  10: 역할이 대화방에 참가하지 않은 경우에도 채팅 기록을 읽을 수 있는 경우 True입니다. <br/>  11: 역할이 대화방을 볼 수 있는 경우 True입니다. 이 설정은 범위 및 표시 여부와 같은 요소로 세분화됩니다. <br/>  12: 역할이 강당 대화방에서 채팅할 수 있는 경우 True입니다. <br/>  13: 역할이 노드를 볼 때 표시 여부 규칙을 바이패스할 수 있는 경우 True입니다. <br/> |
   
**키**

|**열**|**설명**|
|:-----|:-----|
|rtypeID  <br/> |기본 키입니다.  <br/> |
   

