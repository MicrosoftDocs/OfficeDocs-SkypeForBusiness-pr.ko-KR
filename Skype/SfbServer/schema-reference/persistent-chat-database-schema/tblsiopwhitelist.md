---
title: tblSiopWhiteList
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
ms.assetid: 05fc1df4-32eb-4d46-9d1c-e0b607091142
description: tblSiopWhiteList는 노드와 연결할 수 있는 등록된 추가 기능 목록입니다.
ms.openlocfilehash: cf7a727bd34e5c6f29f5bf0b203411983c90ae53
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831488"
---
# <a name="tblsiopwhitelist"></a>tblSiopWhiteList
 
tblSiopWhiteList는 노드와 연결할 수 있는 등록된 추가 기능 목록입니다.
  
**열**

|**열**|**유형**|**설명**|
|:-----|:-----|:-----|
|siopID  <br/> |GUID, null이 아님  <br/> |추가 기능의 GUID입니다.  <br/> |
|siopName  <br/> |nvarchar(50), null이 아님  <br/> |추가 기능의 표시 이름입니다.  <br/> |
|siopUrl  <br/> |nvarchar(255), null이 아님  <br/> |추가 기능의 URL입니다.  <br/> |
   
**키**

|**열**|**설명**|
|:-----|:-----|
|siopID  <br/> |기본 키입니다.  <br/> |
   

