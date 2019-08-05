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
localization_priority: Normal
ms.assetid: 0b94f555-6888-4fe0-a048-4660a2513276
description: tblPrincipalMemberDifference에는 이후 Active Directory 도메인 서비스 동기화 단계에서 아직 처리 하지 않은 그룹 구성원 변경 (구성원을 추가 및 제거 함)이 포함 됩니다.
ms.openlocfilehash: 18d0f3f5c8700db0bb81470f5ee90851e8d277ad
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196614"
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
   

