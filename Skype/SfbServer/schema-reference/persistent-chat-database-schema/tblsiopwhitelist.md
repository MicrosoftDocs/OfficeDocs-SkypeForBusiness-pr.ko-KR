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
ms.openlocfilehash: 3f1ad0461bc227970d4a2a0864dbc6318ef0af32d854402180321bab74aa91e5
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54305380"
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
   

