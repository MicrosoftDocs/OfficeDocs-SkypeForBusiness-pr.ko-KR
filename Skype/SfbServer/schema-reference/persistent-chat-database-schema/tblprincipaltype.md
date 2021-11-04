---
title: tblPrincipalType
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
description: tblPrincipalType에는 tblPrincipal 테이블에 있는 항목을 분류하기 위한 사용자 유형이 포함됩니다.
ms.openlocfilehash: 3fa86d3cfed058387681ff0fc5eb2b3ec7afb26d
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60743114"
---
# <a name="tblprincipaltype"></a>tblPrincipalType
 
tblPrincipalType에는 tblPrincipal 테이블에 있는 항목을 분류하기 위한 사용자 유형이 포함됩니다.
  
**열**

|**열**|**유형**|**설명**|
|:-----|:-----|:-----|
|ptypeID  <br/> |smallint, null이 아님  <br/> |사용자 유형 ID입니다.  <br/> |
|ptypeDesc  <br/> |nvarchar(256), null이 아님  <br/> |유형에 대한 설명입니다.  <br/> |
|ptypeIsSystemUser  <br/> |bit, null이 아님  <br/> |유형이 내부 용도로 사용되는 사용자에 해당하는 경우 True입니다.  <br/> |
|ptypeIsUser  <br/> |bit, null이 아님  <br/> |유형이 사용자 유형인 경우 True입니다.  <br/> |
   
**키**

|**열**|**설명**|
|:-----|:-----|
|ptypeID  <br/> |기본 키입니다.  <br/> |
   
**사용자 값**

|**ID**|**역할**|**설명**|**사용자**|
|:-----|:-----|:-----|:-----|
|1  <br/> |모두  <br/> |유형이 알려지지 않은 일반 사용자입니다. tblPrincipal 테이블에서 사용되지 않습니다.  <br/> ||
|2  <br/> |AnyUser  <br/> |사용자 유형의 일반 사용자입니다. tblPrincipal 테이블에서 사용되지 않습니다.  <br/> |예  <br/> |
|3   <br/> |AnyGroup  <br/> |그룹 체계를 포함하는 일반 사용자입니다. tblPrincipal 테이블에서 사용되지 않습니다.  <br/> ||
|4  <br/> |SystemUser  <br/> |영구 채팅 서버에서 내부적으로 사용되는 사용자입니다.  <br/> ||
|5  <br/> |사용자  <br/> |일반 사용자입니다.  <br/> |예  <br/> |
|8   <br/> |DC  <br/> |Active Directory 도메인 서비스 도메인 컨트롤러.  <br/> ||
|9   <br/> |그룹  <br/> |Active Directory 보안 그룹입니다.  <br/> ||
|10   <br/> |폴더  <br/> |Active Directory 컨테이너 또는 조직 단위입니다.  <br/> ||
   
## <a name="see-also"></a>참고 항목

[tblPrincipal](tblprincipal.md)
