---
title: tblEnumAttribute
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
ms.assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
description: tblEnumAttribute는 Node 테이블에 사용된 Visibility 및 Behavior 특성이 들어 있는 하드코드된 테이블입니다.
ms.openlocfilehash: 6996c95ca170082ec89ac7d8fd92648b60c933b1fd72515bb7c3974df8cd5e92
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54337587"
---
# <a name="tblenumattribute"></a>tblEnumAttribute
 
tblEnumAttribute는 Node 테이블에 사용된 Visibility 및 Behavior 특성이 들어 있는 하드코드된 테이블입니다.
  
**열**

|**열**|**유형**|**설명**|
|:-----|:-----|:-----|
|attributeID  <br/> |smallint, null이 아님  <br/> |특성의 ID입니다.  <br/> |
|attributeName  <br/> |nvarchar(256), null이 아님  <br/> |특성의 이름입니다.  <br/> |
   
**키**

|**열**|**설명**|
|:-----|:-----|
|attributeID  <br/> |기본 키입니다.  <br/> |
   
**테이블 값**

|**attributeID**|**attributeName**|
|:-----|:-----|
|1  <br/> |가시성.  <br/> |
|2  <br/> |동작.  <br/> |
   
## <a name="see-also"></a>참고 항목

[tblNode](tblnode.md)
