---
title: tblPrincipalMemberDifference
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 0b94f555-6888-4fe0-a048-4660a2513276
description: tblPrincipalMemberDifference에는 이후 Active Directory 도메인 서비스 동기화 단계에서 아직 처리하지 않은 그룹 구성원 변경(구성원 추가 및 제거된 구성원 모두)이 포함되어 있습니다.
ms.openlocfilehash: c52f1290eb0da442ffed9f8d8b645423b6f6c59c
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62410671"
---
# <a name="tblprincipalmemberdifference"></a>tblPrincipalMemberDifference
 
tblPrincipalMemberDifference에는 이후 Active Directory 도메인 서비스 동기화 단계에서 아직 처리하지 않은 그룹 구성원 변경(구성원 추가 및 제거된 구성원 모두)이 포함되어 있습니다.
  
**열**

|**열**|**유형**|**설명**|
|:-----|:-----|:-----|
|prinGuid  <br/> |GUID, null이 아님  <br/> |변경된 그룹의 사용자 GUID입니다.  <br/> |
|memberADPath  <br/> |nvarchar(256)  <br/> |구성원의 고유 이름입니다.  <br/> |
|memberRemoved  <br/> |bit, null이 아님  <br/> |구성원이 추가된 경우 False입니다. 구성원이 제거된 경우 True입니다.  <br/> |
   
**키**

|**열**|**설명**|
|:-----|:-----|
|\<prinGuid, memberADPath\>  <br/> |기본 키입니다.  <br/> |
   

