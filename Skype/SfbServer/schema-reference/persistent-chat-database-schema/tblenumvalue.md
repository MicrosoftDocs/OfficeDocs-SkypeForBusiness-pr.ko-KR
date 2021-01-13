---
title: tblEnumValue
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
ms.assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
description: tblEnumValue는 Node 테이블에 사용된 특성의 표시 및 동작 값이 포함된 하드코드된 테이블입니다.
ms.openlocfilehash: a13bfbe79d1eb118f0727f390816a26d35a508d0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816028"
---
# <a name="tblenumvalue"></a>tblEnumValue
 
tblEnumValue는 Node 테이블에 사용된 특성의 표시 및 동작 값이 포함된 하드코드된 테이블입니다.
  
**열**

|**열**|**유형**|**설명**|
|:-----|:-----|:-----|
|valueID  <br/> |smallint, null이 아님  <br/> |값의 ID입니다.  <br/> |
|attributeID  <br/> |smallint, null이 아님  <br/> |특성의 ID입니다.  <br/> |
|attributeValue  <br/> |nvarchar(256), null이 아님  <br/> |값의 이름입니다.  <br/> |
   
**키**

|**열**|**설명**|
|:-----|:-----|
|valueID  <br/> |기본 키입니다.  <br/> |
|attributeID  <br/> |tblEnumAttribute.attributeID 테이블에서 조회 기능이 있는 외래 키입니다.  <br/> |
   
**테이블 값**

|**valueID**|**attributeID**|**attributeValue**|
|:-----|:-----|:-----|
|2   <br/> |1   <br/> |private  <br/> |
|3   <br/> |1   <br/> |범위  <br/> |
|4   <br/> |2   <br/> |normal  <br/> |
|5   <br/> |2   <br/> |강당  <br/> |
|6   <br/> |1   <br/> |open  <br/> |
   
## <a name="see-also"></a>참고 항목

[tblNode](tblnode.md)
