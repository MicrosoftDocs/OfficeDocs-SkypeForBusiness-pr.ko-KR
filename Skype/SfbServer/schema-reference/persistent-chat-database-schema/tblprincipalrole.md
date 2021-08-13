---
title: tblPrincipalRole
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
ms.assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
description: tblPrincipalRole 테이블에는 노드에 할당된 명시적 역할이 포함됩니다.
ms.openlocfilehash: 28e639a4894b89e449a70fc527b7c4315be57403e15bb582bcdae3933e3790a7
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54336388"
---
# <a name="tblprincipalrole"></a>tblPrincipalRole
 
tblPrincipalRole 테이블에는 노드에 할당된 명시적 역할이 포함됩니다.
  
**열**

|**열**|**유형**|**설명**|
|:-----|:-----|:-----|
|prinRoleNodeID  <br/> |int, null이 아님  <br/> |해당 역할이 적용되는 노드 ID입니다.  <br/> |
|prinRolePrinID  <br/> |int, null이 아님  <br/> |사용자 ID입니다.  <br/> |
|prinRoleTypeID  <br/> |int, null이 아님  <br/> |역할 유형 ID(tblRoleType)입니다.  <br/> |
|prinRoleUpdatedBy  <br/> |int, null이 아님  <br/> |이 항목을 마지막으로 업데이트한 사용자의 ID입니다.  <br/> |
   
**키**

|**열**|**설명**|
|:-----|:-----|
|\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\>  <br/> |기본 키입니다.  <br/> |
|prinRoleNodeID  <br/> |tblNode.nodeID 테이블에서 조회 기능이 있는 외래 키입니다.  <br/> |
|prinRolePrinID  <br/> |tblPrincipal.prinID 테이블에서 조회 기능이 있는 외래 키입니다.  <br/> |
|prinRoleTypeID  <br/> |tblRoleType.rtypeID 테이블에서 조회 기능이 있는 외래 키입니다.  <br/> |
   

