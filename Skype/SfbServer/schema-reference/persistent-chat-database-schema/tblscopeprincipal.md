---
title: tblScopePrincipal
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
ms.assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
description: tblScopePrincipal에는 노드에 지정된 범위가 포함됩니다.
ms.openlocfilehash: efda792ab6f6c6cc7b188a9dffdaa7c324b24797
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831518"
---
# <a name="tblscopeprincipal"></a>tblScopePrincipal
 
tblScopePrincipal에는 노드에 지정된 범위가 포함됩니다.
  
**열**

|**열**|**유형**|**설명**|
|:-----|:-----|:-----|
|scopeNodeID  <br/> |int, null이 아님  <br/> |해당 범위가 적용되는 노드 ID입니다.  <br/> |
|scopePrinID  <br/> |int, null이 아님  <br/> |사용자 ID입니다.  <br/> |
|scopeIsDenied  <br/> |bit, null이 아님  <br/> |범위 유형이 Deny인 경우 True이고 Allow이면 False입니다.  <br/> |
|scopeUpdatedBy  <br/> |int, null이 아님  <br/> |이 항목을 마지막으로 업데이트한 사용자의 ID입니다.  <br/> |
   
**키**

|**열**|**설명**|
|:-----|:-----|
|\<scopeNodeID, scopePrinID\>  <br/> |기본 키입니다.  <br/> |
|scopeNodeID  <br/> |tblNode.nodeID 테이블에서 조회 기능이 있는 외래 키입니다.  <br/> |
|scopePrinID  <br/> |tblPrincipal.prinID 테이블에서 조회 기능이 있는 외래 키입니다.  <br/> |
   

