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
localization_priority: Normal
ms.assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
description: tblPrincipalInvites는 자동 초대를 사용 하는 모든 노드에 대해 프로 비전 된 모든 사용자에 대 한 초대를 포함 합니다.
ms.openlocfilehash: 21344cfc34ce046a1dffdf7cd3ee9557da20a7ef
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196615"
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
   

