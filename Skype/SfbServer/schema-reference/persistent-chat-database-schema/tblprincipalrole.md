---
title: tblPrincipalRole
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
description: tblPrincipalRole에는 노드에 할당 된 명시적 역할이 포함 됩니다.
ms.openlocfilehash: 9675713afba5753378f4d01b70489d0eee93b8bf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196607"
---
# <a name="tblprincipalrole"></a>tblPrincipalRole
 
tblPrincipalRole에는 노드에 할당 된 명시적 역할이 포함 됩니다.
  
**열**

|**열**|**유형**|**설명**|
|:-----|:-----|:-----|
|prinRoleNodeID  <br/> |int, null 아님  <br/> |역할이 적용 되는 노드 ID입니다.  <br/> |
|prinRolePrinID  <br/> |int, null 아님  <br/> |Principal ID.  <br/> |
|prinRoleTypeID  <br/> |int, null 아님  <br/> |역할 유형 ID (tblRoleType)입니다.  <br/> |
|prinRoleUpdatedBy  <br/> |int, null 아님  <br/> |이 항목을 마지막으로 업데이트 한 사용자의 ID입니다.  <br/> |
   
**핵심**

|**열**|**설명**|
|:-----|:-----|
|\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\>  <br/> |기본 키입니다.  <br/> |
|prinRoleNodeID  <br/> |NodeID 테이블에 조회를 포함 하는 외래 키입니다.  <br/> |
|prinRolePrinID  <br/> |TblPrincipal 테이블에 조회를 포함 하는 외래 키입니다.  <br/> |
|prinRoleTypeID  <br/> |TblRoleType의 조회를 포함 하는 외래 키입니다.  <br/> |
   

