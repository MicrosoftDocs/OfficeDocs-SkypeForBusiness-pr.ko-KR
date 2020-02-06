---
title: tblPrincipalType
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
ms.assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
description: tblPrincipalType에는 tblPrincipal 테이블에 있는 항목을 분류 하는 principal 형식이 포함 되어 있습니다.
ms.openlocfilehash: 1aacfdf34689bebc2c7e012c926731ae1f4a8349
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812936"
---
# <a name="tblprincipaltype"></a>tblPrincipalType
 
tblPrincipalType에는 tblPrincipal 테이블에 있는 항목을 분류 하는 principal 형식이 포함 되어 있습니다.
  
**열**

|**열**|**유형**|**설명**|
|:-----|:-----|:-----|
|ptypeID  <br/> |smallint, null이 아님  <br/> |Principal type ID.  <br/> |
|ptypeDesc  <br/> |nvarchar (256), null 아님  <br/> |형식에 대 한 설명입니다.  <br/> |
|ptypeIsSystemUser  <br/> |bit, null이 아님  <br/> |내부 용도에 사용 되는 주체에 해당 하는 형식인 경우 True입니다.  <br/> |
|ptypeIsUser  <br/> |bit, null이 아님  <br/> |형식이 사용자 형식인 경우 True입니다.  <br/> |
   
**키**

|**열**|**설명**|
|:-----|:-----|
|ptypeID  <br/> |기본 키입니다.  <br/> |
   
**Principal 값**

|**I**|**역할인**|**설명**|**사용자**|
|:-----|:-----|:-----|:-----|
|1  <br/> |이상  <br/> |알려진 형식이 없는 일반 주체입니다. TblPrincipal 테이블에서 사용 되지 않습니다.  <br/> ||
|2  <br/> |AnyUser  <br/> |사용자 유형의 일반 사용자입니다. TblPrincipal 테이블에서 사용 되지 않습니다.  <br/> |예  <br/> |
|3  <br/> |AnyGroup  <br/> |그룹 의미가 있는 일반 주체입니다. TblPrincipal 테이블에서 사용 되지 않습니다.  <br/> ||
|4(tcp/ipv4)  <br/> |SystemUser  <br/> |영구 채팅 서버에서 내부적으로 사용 하는 주체입니다.  <br/> ||
|5mb  <br/> |사용자  <br/> |일반 사용자.  <br/> |예  <br/> |
|20cm(8  <br/> |DC  <br/> |Active Directory 도메인 서비스 도메인 컨트롤러.  <br/> ||
|되었는지  <br/> |그룹과  <br/> |Active Directory 보안 그룹  <br/> ||
|1천만  <br/> |폴더  <br/> |Active Directory 컨테이너 또는 조직 구성 단위입니다.  <br/> ||
   
## <a name="see-also"></a>참고 항목

[tblPrincipal](tblprincipal.md)
