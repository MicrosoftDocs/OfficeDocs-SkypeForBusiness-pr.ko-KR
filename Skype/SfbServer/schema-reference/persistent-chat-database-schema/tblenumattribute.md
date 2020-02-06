---
title: tblEnumAttribute
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
ms.assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
description: tblEnumAttribute는 노드 테이블에 사용 되는 Visibility 및 Behavior 특성을 포함 하는 하드 코드 된 테이블입니다.
ms.openlocfilehash: 8244e2fb6ace6c4ed73f017f52df0c85d1f02315
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814616"
---
# <a name="tblenumattribute"></a>tblEnumAttribute
 
tblEnumAttribute는 노드 테이블에 사용 되는 Visibility 및 Behavior 특성을 포함 하는 하드 코드 된 테이블입니다.
  
**열**

|**열**|**유형**|**설명**|
|:-----|:-----|:-----|
|attributeID  <br/> |smallint, null이 아님  <br/> |특성의 ID입니다.  <br/> |
|attributeName  <br/> |nvarchar (256), null 아님  <br/> |특성의 이름입니다.  <br/> |
   
**키**

|**열**|**설명**|
|:-----|:-----|
|attributeID  <br/> |기본 키입니다.  <br/> |
   
**테이블 값**

|**attributeID**|**attributeName**|
|:-----|:-----|
|1  <br/> |시도가.  <br/> |
|2  <br/> |결과가.  <br/> |
   
## <a name="see-also"></a>참고 항목

[tblNode](tblnode.md)
