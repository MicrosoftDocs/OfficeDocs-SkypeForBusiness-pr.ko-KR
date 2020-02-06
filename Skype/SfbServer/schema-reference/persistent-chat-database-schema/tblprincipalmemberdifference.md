---
title: tblPrincipalMemberDifference
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
ms.assetid: 0b94f555-6888-4fe0-a048-4660a2513276
description: tblPrincipalMemberDifference에는 이후 Active Directory 도메인 서비스 동기화 단계에서 아직 처리 하지 않은 그룹 구성원 변경 (구성원을 추가 및 제거 함)이 포함 됩니다.
ms.openlocfilehash: c7e965658c9e351a7a2d079921b7abe8166b48ad
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814076"
---
# <a name="tblprincipalmemberdifference"></a>tblPrincipalMemberDifference
 
tblPrincipalMemberDifference에는 이후 Active Directory 도메인 서비스 동기화 단계에서 아직 처리 하지 않은 그룹 구성원 변경 (구성원을 추가 및 제거 함)이 포함 됩니다.
  
**열**

|**열**|**유형**|**설명**|
|:-----|:-----|:-----|
|prinGuid  <br/> |GUID (null 아님)  <br/> |변경 된 그룹의 Principal GUID입니다.  <br/> |
|memberADPath  <br/> |nvarchar (256)  <br/> |구성원의 고유 이름입니다.  <br/> |
|memberRemoved 됨  <br/> |bit, null이 아님  <br/> |구성원이 추가 된 경우 False입니다. 구성원이 제거 된 경우 True입니다.  <br/> |
   
**키**

|**열**|**설명**|
|:-----|:-----|
|\<prinGuid, memberADPath\>  <br/> |기본 키입니다.  <br/> |
   

