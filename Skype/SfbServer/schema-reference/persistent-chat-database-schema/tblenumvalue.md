---
title: tblEnumValue
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
ms.assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
description: tblEnumValue는 노드 테이블에 사용 되는 특성의 Visibility 및 Behavior 값을 포함 하는 하드 코드 된 테이블입니다.
ms.openlocfilehash: accb9cb4801984bd4b3839cd44e5b7feb8d06baa
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814606"
---
# <a name="tblenumvalue"></a>tblEnumValue
 
tblEnumValue는 노드 테이블에 사용 되는 특성의 Visibility 및 Behavior 값을 포함 하는 하드 코드 된 테이블입니다.
  
**열**

|**열**|**유형**|**설명**|
|:-----|:-----|:-----|
|고 대 Eid  <br/> |smallint, null이 아님  <br/> |값의 ID입니다.  <br/> |
|attributeID  <br/> |smallint, null이 아님  <br/> |특성의 ID입니다.  <br/> |
|attributeValue  <br/> |nvarchar (256), null 아님  <br/> |값의 이름입니다.  <br/> |
   
**핵심**

|**열**|**설명**|
|:-----|:-----|
|고 대 Eid  <br/> |기본 키입니다.  <br/> |
|attributeID  <br/> |TblEnumAttribute의 조회가 포함 되어 있는 외래 키입니다.  <br/> |
   
**테이블 값**

|**고 대 Eid**|**attributeID**|**attributeValue**|
|:-----|:-----|:-----|
|2  <br/> |1  <br/> |개인용  <br/> |
|3  <br/> |1  <br/> |범위도  <br/> |
|4(tcp/ipv4)  <br/> |2  <br/> |크기로  <br/> |
|5mb  <br/> |2  <br/> |auditorium  <br/> |
|26  <br/> |1  <br/> |열면  <br/> |
   
## <a name="see-also"></a>참고 항목

[tblNode](tblnode.md)
