---
title: tblPrincipalInvites
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
ms.assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
description: tblPrincipalInvites는 자동 초대를 사용 하는 모든 노드에 대해 프로 비전 된 모든 사용자에 대 한 초대를 포함 합니다.
ms.openlocfilehash: dfa41ec5715c7c5255b26fcdb32561e74c4f08df
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814186"
---
# <a name="tblprincipalinvites"></a>tblPrincipalInvites
 
tblPrincipalInvites는 자동 초대를 사용 하는 모든 노드에 대해 프로 비전 된 모든 사용자에 대 한 초대를 포함 합니다.
  
**열**

|**열**|**유형**|**설명**|
|:-----|:-----|:-----|
|prinID  <br/> |int, null 아님  <br/> |Principal ID.  <br/> |
|invID  <br/> |int, null 아님  <br/> |TblLastInviteId 테이블에서 생성 된 고유 순차 번호 (주체 ID 당)입니다.  <br/> |
|nodeID  <br/> |int, null 아님  <br/> |노드 ID (대화방에만 해당).  <br/> |
|createdOn  <br/> |datetime, null 아님  <br/> |생성 시간.  <br/> |
   
**핵심**

|**열**|**설명**|
|:-----|:-----|
|\<prinID, nodeID\>  <br/> |기본 키입니다.  <br/> |
|prinID  <br/> |TblPrincipal 테이블에 조회를 포함 하는 외래 키입니다.  <br/> |
|nodeID  <br/> |NodeID 테이블에 조회를 포함 하는 외래 키입니다.  <br/> |
   

