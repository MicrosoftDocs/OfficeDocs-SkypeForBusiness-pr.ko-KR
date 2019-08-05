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
localization_priority: Normal
ms.assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
description: tblEnumValue는 노드 테이블에 사용 되는 특성의 Visibility 및 Behavior 값을 포함 하는 하드 코드 된 테이블입니다.
ms.openlocfilehash: bf1ddf75fc7b7fd78c85f47626b465a4d74e5ca2
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196630"
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
|2  <br/> |raid-1  <br/> |개인용  <br/> |
|3-4  <br/> |raid-1  <br/> |범위도  <br/> |
|4(tcp/ipv4)  <br/> |2  <br/> |크기로  <br/> |
|5mb  <br/> |2  <br/> |auditorium  <br/> |
|26  <br/> |raid-1  <br/> |열면  <br/> |
   
## <a name="see-also"></a>참고 항목

[tblNode](tblnode.md)
