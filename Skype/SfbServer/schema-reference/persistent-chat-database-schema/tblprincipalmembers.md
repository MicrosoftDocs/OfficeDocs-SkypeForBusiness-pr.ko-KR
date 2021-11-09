---
title: tblPrincipalMembers
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 9a3e24cf-6ef7-4b82-99fc-50ba41800b6f
description: tblPrincipalMembers에는 사용자 구성원 자격이 포함됩니다.
ms.openlocfilehash: 130ca3cc7f57435f95add202f6af13660bf71610
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60842610"
---
# <a name="tblprincipalmembers"></a>tblPrincipalMembers
 
tblPrincipalMembers에는 사용자 구성원 자격이 포함됩니다.
  
**열**

|**열**|**유형**|**설명**|
|:-----|:-----|:-----|
|prinID  <br/> |int, null이 아님  <br/> |사용자 ID입니다.  <br/> |
|memberADPath  <br/> |nvarchar(384), null이 아님  <br/> |구성원의 고유 이름입니다. 구성원은 tblPrincipal 테이블의 사용자일 필요가 없습니다.  <br/> |
   
**키**

|**열**|**설명**|
|:-----|:-----|
|\<prinID, memberADPath\>  <br/> |기본 키입니다.  <br/> |
|prinID  <br/> |tblPrincipal.prinID에서 조회 기능이 있는 외래 키입니다.  <br/> |
   

