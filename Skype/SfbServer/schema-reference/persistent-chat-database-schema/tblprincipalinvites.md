---
title: tblPrincipalInvites
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
ms.assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
description: tblPrincipalInvites에는 자동 초대가 켜진 모든 노드에 대해 프로비전된 모든 사용자에 대한 초대가 포함됩니다.
ms.openlocfilehash: c2f61f4edcbf82faf7e2f7b4af06ce18bd6afc70
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58604627"
---
# <a name="tblprincipalinvites"></a>tblPrincipalInvites
 
tblPrincipalInvites에는 자동 초대가 켜진 모든 노드에 대해 프로비전된 모든 사용자에 대한 초대가 포함됩니다.
  
**열**

|**열**|**유형**|**설명**|
|:-----|:-----|:-----|
|prinID  <br/> |int, null이 아님  <br/> |사용자 ID입니다.  <br/> |
|invID  <br/> |int, null이 아님  <br/> |tblLastInviteId 테이블에서 생성된 고유한 일련 번호(계정 ID당 하나)입니다.  <br/> |
|nodeID  <br/> |int, null이 아님  <br/> |노드 ID(대화방 전용)입니다.  <br/> |
|createdOn  <br/> |datetime, null이 아님  <br/> |만든 시간입니다.  <br/> |
   
**키**

|**열**|**설명**|
|:-----|:-----|
|\<prinID, nodeID\>  <br/> |기본 키입니다.  <br/> |
|prinID  <br/> |tblPrincipal.prinID 테이블에서 조회 기능이 있는 외래 키입니다.  <br/> |
|nodeID  <br/> |tblNode.nodeID 테이블에서 조회 기능이 있는 외래 키입니다.  <br/> |
   

