---
title: tblScopePrincipal
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
description: tblScopePrincipal에는 노드에 할당 된 범위가 포함 됩니다.
ms.openlocfilehash: 2fd8e434710c7bcd266c427fa492e23adacedb22
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196599"
---
# <a name="tblscopeprincipal"></a>tblScopePrincipal
 
tblScopePrincipal에는 노드에 할당 된 범위가 포함 됩니다.
  
**열**

|**열**|**유형**|**설명**|
|:-----|:-----|:-----|
|scopeNodeID  <br/> |int, null 아님  <br/> |범위가 적용 되는 노드 ID입니다.  <br/> |
|scopePrinID  <br/> |int, null 아님  <br/> |Principal ID.  <br/> |
|scopeIsDenied  <br/> |bit, null이 아님  <br/> |범위 형식이 Deny 이면 True이 고, 그렇지 않으면 false입니다. 허용 하는 경우 False  <br/> |
|scopeUpdatedBy  <br/> |int, null 아님  <br/> |이 항목을 마지막으로 업데이트 한 사용자의 ID입니다.  <br/> |
   
**핵심**

|**열**|**설명**|
|:-----|:-----|
|\<scopeNodeID, scopePrinID\>  <br/> |기본 키입니다.  <br/> |
|scopeNodeID  <br/> |NodeID 테이블에 조회를 포함 하는 외래 키입니다.  <br/> |
|scopePrinID  <br/> |TblPrincipal 테이블에 조회를 포함 하는 외래 키입니다.  <br/> |
   

