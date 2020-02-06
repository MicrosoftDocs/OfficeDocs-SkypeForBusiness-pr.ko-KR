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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
description: tblPrincipalRole에는 노드에 할당 된 명시적 역할이 포함 됩니다.
ms.openlocfilehash: 1cc606ec3825bb664d4123154e97fabb15678cfd
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813366"
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
   

